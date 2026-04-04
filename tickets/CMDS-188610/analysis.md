# CMDS-188610 — Edition VENTE TPE : Total VISA doublé

> **Analyse**: 2026-03-27 → 2026-03-28
> **Village**: Da Balaia
> **Symptôme**: L'édition "VENTE TPE" affiche le total VISA doublé (2×1 080.40 = 2 160.80)

## 1. Contexte

Le village Da Balaia signale que l'édition "VENTE TPE" du 24/03/26 affiche :

```
TPE (Boutique)   = 1 080.40
TPE 5 (Boutique) = 1 080.40
TOTAL VISA       = 2 160.80   ← DOUBLÉ
```

Le montant 1 080.40 apparaît deux fois : une ligne sans numéro de terminal et une ligne pour le terminal #5. L'utilisateur confirme que c'est récent (quelques jours) et qu'aucun paramétrage n'a été modifié.

## 2. Configuration TPE Da Balaia

D'après la capture d'écran de configuration :

| # Terminal | Type | Description |
|-----------|------|-------------|
| 4 | ZZZ | (inactif?) |
| 5 | AMEX/CCAU/VISA | BTQ PISCINE VISA 869390 |
| 6 | AMEX/CCAU/VISA | BTQ VISA 871424 |

**Deux terminaux VISA actifs** (#5 et #6). C'est potentiellement un ajout récent.

## 3. Chaîne de programmes

### Préparation des données

```
VIL IDE 29 "Listings cloture HTML" (Prg_538.xml)
  ├─ ... (autres editions)
  ├─ CallProgram → VIL Prg_583 "Genere tempo vente telecollec"
  └─ CallProgram → VIL IDE 77 "Edition HTML Ventes TPE" (Prg_580.xml)
```

### Programme de préparation : VIL Prg_583

**Rôle** : Alimente la table temporaire `import_resort_credit` (table 914) avec les données VISA/AMEX depuis plusieurs sources.

**Flux d'exécution (Task Suffix du root ISN_2=1)** :

```
1. DbDel import_resort_credit    ← RAZ table temporaire
2. IF NOT VG39 : "Lect compta v1" (ISN_2=5)
   - Source : table 40 (comptabilité)
   - Filtre : (MOP='VISA' OR MOP='AMEX') AND (status='S' OR status='V') AND montant<>0
   - Écrit dans 914
3. IF NOT VG39 : "Lect caisse_vente v1" (ISN_2=2)
   - Source : table 263 (caisse_vente)
   - Filtre : (MOP='VISA' OR MOP='AMEX') AND (status='S' OR status='V') AND montant<>0
   - Écrit dans 914 avec type 'C'
4. IF VG39 : "Lect compta T2H" (ISN_2=9)
5. IF VG39 : "Lect caisse_vente T2H" (ISN_2=12)
6. TOUJOURS : "Lect ticket tpe" (ISN_2=6)
   - Source : table 260 (tickets_tpe)
   - Filtre : montant <> 0
   - Écrit dans 914 avec type 'B', montant NÉGATIF (-montant)
   - Inclut numero_tpe comme Str(numero_tpe,'2')
```

### Programme d'édition : VIL IDE 77 (Prg_580.xml)

**Rôle** : Lit `import_resort_credit` (914) et génère le HTML.

- Table principale : import_resort_credit (914)
- 3 niveaux de Group breaks (terminal, MOP, etc.)
- Sous-tâche "Recapitulatif" (ISN_2=4) pour les totaux

## 4. Programme de calcul : VIL IDE 121 (Prg_425.xml)

**Rôle** : Calcule les totaux TPE/MOP (appelé par VIL IDE 97 "Contrôle caisse").

**Structure** :
- ISN_2=1 : Root, 2 params (societe, date)
- ISN_2=2 : RAZ — remet à zéro total_ventes_par_mop (265) pour la date
- ISN_2=3 : SAISIE v1 (si NOT VG39) — itère tickets_tpe → écrit total_ventes_par_mop
- ISN_2=6 : SAISIE T2H (si VG39) — même chose, mode T2H

### DataView SAISIE v1 (ISN_2=3)

| Source | Table | Accès | Colonnes clés |
|--------|-------|-------|---------------|
| Main | tickets_tpe (260) | READ | numero_tpe, date_comptable, moyen_de_paiement, montant, service |
| Link | tpe_par_service (259) | READ | terminal_ims, numero_tpe, mode_de_paiement |
| Link | arc_pv_cust_packages (734) | READ | - |
| Link | total_ventes_par_mop (265) | **WRITE** | societe, date, service, mop, montant_calcule, montant_saisi |

### Expressions clés SAISIE v1

| Exp | Syntaxe | Rôle |
|-----|---------|------|
| 1 | `{1,2}` | Date comptable (range sur tickets_tpe) |
| 5 | `{1,1}` | Societe (locate total_ventes_par_mop) |
| 6 | `{1,2}` | Date (locate total_ventes_par_mop) |
| 8 | `{0,3}` | MOP (locate total_ventes_par_mop) |
| 9 | `{0,17}+{0,5}` | montant_calcule += montant (accumulation) |
| 10 | `{0,18}+{0,5}` | montant_saisi += montant (accumulation) |
| 11 | `IF(VG25,{0,37},{0,12})` | Service (conditionnel) |

### Tables SQL impliquées

| Table Magic | Table SQL | Colonnes clés | Rows |
|-------------|-----------|---------------|------|
| tickets_tpe (260) | caisse_tpe_ticket | numero_tpe, date_comptable, moyen_de_paiement, montant, service | - |
| tpe_par_service (259) | caisse_tpe_terminal | terminal_ims, numero_tpe, mode_de_paiement | - |
| total_ventes_par_mop (265) | caisse_vente_par_mop | societe, date, service, mop, montant_calcule, montant_saisi | 20 851 |
| caisse_vente (263) | caisse_vente | ven_societe, ven_mode_de_paiement, ven_montant, ven_num_terminal_vente | 2 931 |

## 5. Diagnostic — Root Cause

### Hypothèse principale : Double lecture des transactions VISA

Le programme de préparation (Prg_583) copie les transactions VISA depuis **deux sources indépendantes** vers la même table temporaire :

1. **"Lect caisse_vente v1"** : lit `caisse_vente` filtré sur VISA/AMEX → écrit dans import_resort_credit
2. **"Lect ticket tpe"** : lit `tickets_tpe` filtré sur montant<>0 → écrit dans import_resort_credit

Pour une transaction VISA au TPE, le montant existe dans **les deux tables source** :
- `caisse_vente` : la vente enregistrée par la caisse (côté POS)
- `tickets_tpe` : le ticket enregistré par le terminal TPE (côté banque)

L'édition additionne les deux dans le total VISA → **montant doublé**.

### Labels dans l'édition

| Label affiché | Source probable | Type | Terminal |
|---------------|----------------|------|----------|
| "TPE (Boutique)" | caisse_vente (type 'C') | Vente caisse | pas de # terminal |
| "TPE 5 (Boutique)" | tickets_tpe (type 'B') | Ticket TPE | terminal #5 |

### Pourquoi "ça marchait avant"

**Scénarios possibles** (du plus probable au moins probable) :

1. **Ajout récent du terminal #6** : l'ajout d'un 2ème terminal VISA a possiblement modifié le flux de données (nouvelles écritures dans caisse_vente qui passent maintenant le filtre status='S'/'V')
2. **Changement de statut des transactions** : les ventes VISA sont passées de status 'N' à 'S' ou 'V' récemment, faisant qu'elles sont maintenant captées par "Lect caisse_vente"
3. **Changement côté télécollecte** : la récupération des tickets TPE a commencé à générer des enregistrements supplémentaires dans tickets_tpe

## 6. Pistes de résolution

### Option A — Exclure les doublons dans Prg_583

Ajouter un filtre dans "Lect caisse_vente v1" (ISN_2=2) pour exclure les transactions qui ont déjà un ticket TPE correspondant. Ou inversement, ne pas inclure dans "Lect ticket tpe" les transactions déjà présentes via caisse_vente.

### Option B — Séparer les totaux dans l'édition

Modifier VIL IDE 77 pour que les totaux distinguent les lignes 'C' (caisse) et 'B' (TPE), sans les additionner ensemble.

### Option C — Filtrer par type dans le total

Dans le Group Suffix de VIL IDE 77, ne cumuler que les lignes de type 'B' (tickets TPE) dans le total, en ignorant les lignes 'C'.

## 7. Vérification recommandée

Pour confirmer le diagnostic, vérifier sur la base de Da Balaia :

```sql
-- Transactions VISA du 24/03/26 dans caisse_vente
SELECT ven_date_comptable, ven_mode_de_paiement, ven_montant, ven_num_terminal_vente
FROM caisse_vente
WHERE ven_mode_de_paiement = 'VISA'
  AND ven_date_comptable = '20260324'
ORDER BY ven_montant;

-- Tickets TPE VISA du 24/03/26
SELECT numero_tpe, date_comptable, moyen_de_paiement, montant
FROM caisse_tpe_ticket
WHERE moyen_de_paiement = 'VISA'
  AND date_comptable = '20260324'
ORDER BY montant;
```

Si les mêmes montants apparaissent dans les deux requêtes → confirmation du doublement.

## 8. Programmes analysés

| Programme | Fichier XML | Description | Rôle |
|-----------|-------------|-------------|------|
| VIL IDE 29 | Prg_538.xml | Listings cloture HTML | Orchestrateur |
| VIL Prg_583 | Prg_583.xml | Genere tempo vente telecollec | **Préparation données** |
| VIL IDE 77 | Prg_580.xml | Edition HTML Ventes TPE | **Rendu HTML** |
| VIL IDE 121 | Prg_425.xml | Calcul TPE/MOP | Calcul totaux |

## 9. Captures d'écran

- `image-20260325-140954.png` : Édition montrant le total doublé (cercle rouge)
- `image-20260325-153445.png` : Configuration TPE Da Balaia (2 terminaux VISA #5 et #6)
