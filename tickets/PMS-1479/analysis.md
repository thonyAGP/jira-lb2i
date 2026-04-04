# PMS-1479 - Analyse

> **Analyse**: 2026-02-17 10:00 → 14:30 (investigation approfondie)

## 1. Contexte Ticket

| Champ | Valeur |
|-------|--------|
| **Titre** | [Caisse Adherent] Facture + document envoye apres solde en ECO |
| **Sujet reel** | Libelle taxe de sejour affiche "Caisse" au lieu de "TAXE DE SEJOUR" |
| **Village** | Pragelato (PHU) |
| **Priorite** | Moderee |
| **Labels** | ADH |

### Symptome

Sur le village Pragelato, la taxe de sejour apparait avec le libelle **"Caisse"** au lieu de **"TAXE DE SEJOUR"** (ou "TAXE SEJOURS") dans :
1. La facture (releve de depenses)
2. L'extrait de compte (ecran caisse)
3. Le ticket imprime

### Preuves (3 screenshots)

| Screenshot | Observation |
|------------|-------------|
| `image-20260204-092040.png` | Facture : ligne du 31/01/2026, designation "Caisse", 4.00 EUR x 14 = 56.00 |
| `image-20260204-092824.png` | Extrait compte CA0122 : Libelle = "Caisse", Libelle Supplementaire = "TAXE SEJOURS" |
| `image-20260204-093109.png` | Ticket imprime : label "Caisse" |

## 2. Analyse Technique

### 2.1 Table impactee

**Table #40 - comptable (cafil018_dat)** - 9349 lignes, 47 colonnes

| Colonne | Type | Contenu constate | Contenu attendu |
|---------|------|------------------|-----------------|
| `cte_libelle` (col 6) | nvarchar(20) | **"Caisse"** | "TAXE DE SEJOUR" ou "TAXE SEJOURS" |
| `cte_libelle_supplem_` (col 7) | nvarchar(20) | "TAXE SEJOURS" (correct) | "TAXE SEJOURS" |
| `cte_service` (col 26) | nvarchar(4) | Code service (ex: "GEST") | Code service |
| `cte_code_type` (col 10) | nvarchar(1) | "O" (OD) | "O" |
| `cte_mode_de_paiement` (col 13) | nvarchar(4) | "OD" | "OD" |

### 2.2 Origine du libelle "Caisse"

Le libelle "Caisse" correspond au **nom du service** dans la table de reference VSERV (#67 cafil045_dat).
La table des services (`tab_nom_table='VSERV'`) contient un `tab_libelle20` par service.

**Confirme** : Lors de la creation de l'OD de taxe de sejour, le programme ecrit dans `cte_libelle` le libelle du **service** (ex: "Caisse" pour le service GEST) au lieu du libelle descriptif de l'operation ("TAXE DE SEJOUR").

Le `cte_libelle_supplem_` recoit correctement "TAXE SEJOURS", ce qui confirme que l'information est connue mais placee dans le mauvais champ.

### 2.3 Programme qui cree les OD comptables - IDENTIFIE

#### ADH IDE 247 - Deversement Transaction (Prg_243.xml)

**C'est LE programme qui cree physiquement les OD dans cafil018_dat.**

| Attribut | Valeur |
|----------|--------|
| **PublicName** | DEVERSEMENT |
| **Type** | Batch (TaskType="B") |
| **Parametres** | 15 (entree/sortie) |
| **Partage ECF** | PBP, PVE, VIL, RET, WEL |
| **Sous-taches** | 25 (dont "creation d'un O.D. v1", "creation d'un O.D. T2H", "creation d'un O.D. Gratuit") |

**Subtask 247.2 (ISN_2=3) - "creation d'un O.D. v1":**
- Cree des records dans table #40 (comptable) via Link Mode="A" (Append)
- Lit table #67 (VSERV) pour lookup reference
- Source principale: table #47 (compte_gm)

**Logique d'affectation des libelles (Record Suffix, Expression PMS-28):**

```
SI NOT(VG59) OU type='O' (OD):
  cte_libelle       ← Expression 11 → {1,19} = colonne 6 table source parent
  cte_libelle_supp  ← Expression 12 → {1,20} = colonne 7 table source parent
SINON:
  cte_libelle       ← Expression 42 → {1,19} = colonne 6 table source parent
  cte_libelle_supp  ← Expression 43 → {1,20} = colonne 7 table source parent
```

**RESULTAT: Dans TOUS les cas, `cte_libelle` = colonne 6 de la table source et `cte_libelle_supplem_` = colonne 7.**

Le programme DEVERSEMENT ne decide PAS du libelle - il copie fidelement les colonnes 6 et 7 de sa table source.

### 2.4 Table source du DEVERSEMENT

La table source du parent (DATAVIEW_SRC IDX=14) est une table de transactions temporaires avec une structure identique a cafil018_dat :
- Col 6 = libelle (equivalent de `ven_libelle` ou `cte_libelle`)
- Col 7 = libelle supplementaire

La table **caisse_vente** (#263) a exactement la meme structure :

| Col | cafil018_dat (comptable) | caisse_vente (vente) |
|-----|--------------------------|---------------------|
| 6 | cte_libelle | ven_libelle |
| 7 | cte_libelle_supplem_ | ven_libelle_supplem_ |
| 10 | cte_code_type | ven_code_type |
| 13 | cte_mode_de_paiement | ven_mode_de_paiement |
| 26 | cte_service | ven_service |

**Le DEVERSEMENT "deverse" (transfere) les records de la table vente vers la table comptable en copiant colonne par colonne.**

### 2.5 Programmes qui appellent DEVERSEMENT (15 callers)

| Programme ADH | IDE | Nom |
|---------------|-----|-----|
| Prg_233 | 237 | **Vente GP** |
| Prg_234 | 238 | Vente Boutique (probable) |
| Prg_235 | 239 | Vente variante |
| Prg_236 | 240 | Vente variante |
| Prg_239 | 243 | Histo ventes payantes |
| Prg_240 | 244 | Histo ventes payantes /PMS-605 |
| Prg_241 | 245 | Histo ventes payantes /PMS-623 |
| Prg_249 | 253 | Histo ventes Gratuites |
| Prg_302 | 305 | Ventes Gratuites |
| Prg_304 | 307 | Saisie transaction 154 N.U |
| Prg_307 | 310 | (variant) |
| Prg_309 | 312 | Historique des ventes - Gratui |
| Prg_312 | 315 | Ventes Gratuites |
| Prg_315 | (TBD) | (variant) |
| Prg_316 | (TBD) | (variant) |

**TOUS les callers sont des programmes Vente/Historique.** Le DEVERSEMENT n'est PAS appele directement par un programme de solde/checkout.

### 2.6 Chaine d'execution CONFIRMEE

```
Vente GP (ADH IDE 237) ou programme Vente equivalent
  │
  ├── Cree record dans table source (vente #263 ou temp)
  │     ├── col 6 (ven_libelle)       ← NOM DU SERVICE ("Caisse")  ← BUG ICI
  │     └── col 7 (ven_libelle_supp)  ← DESCRIPTION OD ("TAXE SEJOURS") ← CORRECT
  │
  └── Appelle DEVERSEMENT (ADH IDE 247)
        └── Sous-tache "creation d'un O.D. v1" (ISN_2=3)
              ├── Lit col 6 source → ecrit cte_libelle = "Caisse"
              └── Lit col 7 source → ecrit cte_libelle_supplem_ = "TAXE SEJOURS"
```

### 2.7 Diagnostic final

| Aspect | Constat |
|--------|---------|
| **Type de bug** | Donnees ecrites (WRITE) dans la table source des ventes |
| **Cause racine** | Le programme Vente (probablement ADH IDE 237 ou ses variants) utilise le libelle du service VSERV ("Caisse") comme libelle principal pour TOUTES les transactions, y compris les OD de taxe de sejour |
| **Comportement attendu** | Pour les OD de taxe de sejour, le libelle principal devrait etre "TAXE DE SEJOUR" ou la description de l'OD |
| **Programme DEVERSEMENT** | N'est PAS fautif - il copie fidelement les donnees source |
| **ADH IDE 61/105** | NE creent PAS les OD (IDE 105 met uniquement a jour num_facture/flag) |

## 3. Programmes analyses en detail

### ADH IDE 247 - Deversement Transaction (Prg_243.xml)

- 25 sous-taches
- Tables: #26, #30, #31, #34, #38(W), #40(W), #77, #89, #263(W), #264(W), #268(W), #271(W), #382, #596(W), #839, #847, #933, #980(W)
- 15 parametres
- PublicName: DEVERSEMENT
- Partage ECF: PBP, PVE, VIL, RET, WEL
- NE decide PAS du libelle - copie depuis la source

### ADH IDE 105 - Maj des lignes saisies V3 (Prg_105.xml)

- **ELIMINE comme cause racine** (confirme par lecture XML complete)
- Source principale: table #866 (maj_appli_tpe), PAS table #40
- Link vers #40 uniquement pour UPDATE (num_facture, flag_application)
- NE cree PAS de records dans cafil018_dat
- NE modifie PAS cte_libelle

### PBG IDE 343 - Gestion Taxes Sejour

- Calcule les taxes par jour de sejour
- Tables: #30, #31, #372, #834
- NE touche PAS la table comptable (#40) ni la table vente (#263)
- Retourne le montant de taxe calcule

### ADH IDE 193 - Solde compte fin sejour (SOLDE_COMPTE)

- AFFICHE l'extrait de compte (lit table #40)
- NE cree PAS les OD
- N'appelle PAS DEVERSEMENT

## 4. Cartographie complete

```
Programme Vente (IDE 237 Vente GP, 238 Boutique, etc.)
  ├── Cree record vente (col 6 = service label, col 7 = description)
  ├── Appelle DEVERSEMENT (IDE 247, Prg_243.xml)
  │     ├── Tache parent: itere table source
  │     ├── Sous-tache ISN_2=3 "creation O.D. v1"
  │     │     ├── Link Mode=A → cree dans #40 (cafil018_dat)
  │     │     ├── cte_libelle ← {1,19} = col 6 source = "Caisse"
  │     │     └── cte_libelle_supplem_ ← {1,20} = col 7 source = "TAXE SEJOURS"
  │     ├── Sous-tache ISN_2=4 "creation O.D. T2H"
  │     └── Sous-tache ISN_2=5 "creation O.D. Gratuit"
  └── ADH IDE 105 met a jour num_facture/flag (post-creation)

PBG IDE 343 (Gestion Taxes Sejour)
  └── Calcule montant taxe → retourne au programme appelant

ADH IDE 193 (SOLDE_COMPTE)
  └── Affiche extrait de compte (lecture seule)
```

## 5. Impact

| Impact | Detail |
|--------|--------|
| **Fonctionnel** | Le client voit "Caisse" au lieu de "TAXE DE SEJOUR" sur facture/extrait |
| **Operationnel** | Confusion pour le caissier et le client |
| **Donnees** | Toutes les OD de taxe de sejour dans cafil018_dat ont le mauvais libelle |
| **Scope** | Potentiellement TOUS les villages (meme chaine Vente → DEVERSEMENT) |
| **Programmes affectes** | 15 programmes Vente appellent DEVERSEMENT - le bug est dans la creation du record source |
