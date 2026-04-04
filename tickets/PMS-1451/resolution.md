# PMS-1451 - Résolution

> **Jira** : [PMS-1451](https://clubmed.atlassian.net/browse/PMS-1451)

## Statut: DIAGNOSTIC CONFIRMÉ

---

## Symptôme

**Archivage prématuré des GO avec plusieurs tronçons de séjour**

- GO archivés alors que leur 2ème tronçon était prévu en juin 2026
- La purge du 03/12/2025 (date cible 26/12/2025) a supprimé des GO actifs
- Seul le 1er tronçon (date 07/12/2025) a été vérifié

---

## Root Cause

### Programme fautif identifié

| Élément | Valeur |
|---------|--------|
| **Programme** | REF IDE 749.1 "séléction" (fichier Prg_726.xml) |
| **Main Source** | Table n°31 - gm_complet (cafil011_dat) |
| **Problème** | La Range utilise une date du GM sans vérifier les tronçons |

### Table manquante dans le DataView

| Table | Champ | Rôle |
|-------|-------|------|
| **Table n°167** - troncon (cafil145_dat) | `tro_date_depart_vol` | Date départ vol |
| | `tro_code_a_i_r` | A=Aller, I=Interne, **R=Retour** |
| | `tro_compte` | Clé de jointure avec gm_complet |
| | `tro_filiation` | Clé de jointure |

### DataView actuel de REF IDE 749.1 (BUG)

| Source | Table | Accès | Rôle |
|--------|-------|-------|------|
| Main Source | Table n°31 - gm_complet | READ | Itère sur tous les GM |
| Link 1 | Table n°34 - hebergement | READ | Joint l'hébergement |
| Link 2 | Table n°34 - hebergement | READ | Second lien (autre clé) |
| Link 3 | **Table n°808 - zselect** | **WRITE** | Écrit la liste des GO à supprimer |
| ⚠️ MANQUANT | Table n°167 - troncon | - | **Non joint = bug** |

---

## Fix proposé

### Modification de REF IDE 749.1

#### 1. Ajouter un Link vers Table n°167 (troncon)

| Link | Table | Accès | Clés de jointure |
|------|-------|-------|------------------|
| **Link 4** (nouveau) | Table n°167 - troncon | READ | `tro_societe`, `tro_compte`, `tro_filiation` |

#### 2. Ajouter une variable virtuelle

| Variable | Type | Expression | Description |
|----------|------|------------|-------------|
| **V.MaxDateRetour** | Date | Voir expression ci-dessous | Date du dernier vol retour |

**Expression pour V.MaxDateRetour** :
```
DbSum(Table n°167, tro_date_depart_vol,
      tro_compte = code_gm AND
      tro_filiation = filiation AND
      tro_code_a_i_r = 'R',
      MAX)
```

#### 3. Modifier la condition de sélection (Range)

| Élément | Avant (bug) | Après (fix) |
|---------|-------------|-------------|
| Condition Range | `date_gm < Variable C` | `V.MaxDateRetour < Variable C` |
| Variable C | Date de purge (formulaire) | Inchangé |

### Pseudo-code

**Avant (BUG)** :
```
FOR EACH gm_complet WHERE date < DatePurge
    INSERT INTO zselect (compte, filiation, ...)
END FOR

→ Ne vérifie PAS si le GM a d'autres tronçons après DatePurge
```

**Après (FIX)** :
```
FOR EACH gm_complet
    max_date_retour = MAX(troncon.tro_date_depart_vol)
                      WHERE tro_compte = compte
                      AND tro_filiation = filiation
                      AND tro_code_a_i_r = 'R'

    IF max_date_retour IS NULL THEN
        max_date_retour = date_gm  -- Fallback si pas de tronçon

    IF max_date_retour < DatePurge THEN
        INSERT INTO zselect (compte, filiation, ...)
    END IF
END FOR

→ Vérifie la date du DERNIER tronçon retour
```

---

## Approches alternatives

### Approche 2 : Modifier gmr_fin_sejour à l'import

Modifier **PBG IDE 225 - Traitement des Adherents** pour que `gmr_fin_sejour` (Table n°30) contienne la date du **dernier** tronçon.

| Avantages | Inconvénients |
|-----------|---------------|
| Pas de modification de la purge | Impact sur autres fonctionnalités |
| Performance optimale | Retraitement données existantes |

**Recommandation** : Approche 1 (modifier la sélection) est préférable car localisée.

---

## Flux d'archivage complet

```
┌───────────────────────────────────────────────────────────────┐
│  REF IDE 749 - lancement reparation                           │
│  Formulaire "Lancement de la sélection"                       │
│  Variable C = "date a partir d'ou on suprime"                 │
└───────────────────────┬───────────────────────────────────────┘
                        │ Bouton "Lancement"
                        ▼
┌───────────────────────────────────────────────────────────────┐
│  Tâche 749.1 - séléction                    ◄── FIX ICI      │
│  ─────────────────────────────────────────────────────────────│
│  Main Source: Table n°31 (gm_complet)                         │
│  Link 1-2: Table n°34 (hebergement)                           │
│  Link 3: Table n°808 (zselect) [WRITE]                        │
│  ─────────────────────────────────────────────────────────────│
│  ⚠️ AJOUTER: Link 4 vers Table n°167 (troncon)               │
│  ⚠️ AJOUTER: Variable V.MaxDateRetour                        │
│  ⚠️ MODIFIER: Condition Range sur V.MaxDateRetour            │
└───────────────────────┬───────────────────────────────────────┘
                        │ Remplit zselect
                        ▼
┌───────────────────────────────────────────────────────────────┐
│  Tâche 749.2 - supress des arrivées avant dim                 │
│  Nettoie zselect                                              │
└───────────────────────┬───────────────────────────────────────┘
                        │
                        ▼
┌───────────────────────────────────────────────────────────────┐
│  CallTask REF IDE 750-761 (suppress *)                        │
│  Chaque programme lit zselect et supprime dans sa table       │
└───────────────────────────────────────────────────────────────┘
```

---

## Validation

### Tests de non-régression

| Scénario | Données test | Résultat attendu |
|----------|--------------|------------------|
| GO 1 tronçon, fin < purge | Tronçon R au 01/12 | Archivé |
| GO 1 tronçon, fin > purge | Tronçon R au 15/01 | Conservé |
| GO 2 tronçons, 2ème > purge | T1=07/12, T2=15/06 | **Conservé** |
| GO 2 tronçons, 2ème < purge | T1=01/11, T2=15/12 | Archivé |
| GM sans tronçon R | Seulement A et I | Conservé (fallback) |

### Requête SQL de vérification

```sql
-- Trouver les GM qui auraient dû être conservés lors de la purge du 26/12
SELECT gmc.code_gm, gmc.filiation,
       MIN(t.tro_date_depart_vol) as premier_retour,
       MAX(t.tro_date_depart_vol) as dernier_retour
FROM cafil011_dat gmc  -- gm_complet
JOIN cafil145_dat t ON t.tro_compte = gmc.code_gm
                   AND t.tro_filiation = gmc.filiation
                   AND t.tro_code_a_i_r = 'R'
GROUP BY gmc.code_gm, gmc.filiation
HAVING MIN(t.tro_date_depart_vol) < '2025-12-26'
   AND MAX(t.tro_date_depart_vol) > '2025-12-26'
```

---

## Récupération des données

Les données supprimées sont dans la base **ARCHIVAGE**, pas définitivement perdues.

**Tables archivées** :
- Table n°722 - arc_gm-recherche
- Autres tables arc_*

---

## Références Magic IDE

### Tables concernées

| N° Table | Nom Logique | Nom Physique | Rôle |
|----------|-------------|--------------|------|
| 30 | gm-recherche | cafil008_dat | Index recherche GM |
| 31 | gm_complet | cafil011_dat | Main Source sélection |
| 34 | hebergement | cafil012_dat | Lié dans sélection |
| 167 | troncon | cafil145_dat | **À ajouter** |
| 808 | zselect | - | Liste GM à supprimer |

### Programmes

| IDE | Projet | Nom | Fichier | Rôle |
|-----|--------|-----|---------|------|
| 749 | REF | lancement reparation | Prg_726.xml | Orchestrateur |
| 749.1 | REF | séléction | Prg_726.xml | **À modifier** |
| 749.2 | REF | supress des arrivées avant dim | Prg_726.xml | Nettoyage |
| 750-761 | REF | suppress * | Prg_727-738.xml | Suppressions |

---

## Statut

| Étape | Statut | Date |
|-------|--------|------|
| Analyse | Terminée | 2026-01-22T19:30 |
| Diagnostic confirmé | Terminé | 2026-01-22T20:15 |
| Validation solution | En attente | |
| Implémentation | En attente | |
| Tests | En attente | |
| Déploiement | En attente | |

---

*Dernière mise à jour : 2026-01-22T20:15*
*Programme à modifier : REF IDE 749.1 "séléction"*
*Fix : Ajouter Link Table n°167 + vérifier MAX(tro_date_depart_vol) WHERE tro_code_a_i_r = 'R'*
