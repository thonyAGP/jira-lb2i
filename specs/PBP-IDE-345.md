# PBP IDE 345 - Facturation

> **Analyse**: Phases 1-4 2026-02-03 16:33 -> 16:33 (13s) | Assemblage 16:33
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBP |
| IDE Position | 345 |
| Nom Programme | Facturation |
| Fichier source | `Prg_345.xml` |
| Dossier IDE | Specif |
| Taches | 1 (1 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 6 |
| :warning: Statut | **ORPHELIN_POTENTIEL** |

## 2. DESCRIPTION FONCTIONNELLE

**Facturation** assure la gestion complete de ce processus.

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>345 - Facturation [[ECRAN]](#ecran-t1)

**Role** : Traitement : Facturation.
**Ecran** : 733 x 165 DLU (MDI) | [Voir mockup](#ecran-t1)
**Delegue a** : [   Generation Facturation (IDE 346)](PBP-IDE-346.md), [   Edit GO/GM date naissance=0 (IDE 349)](PBP-IDE-349.md), [Escale (IDE 12)](PBP-IDE-12.md)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: (aucun)
- **Appelle**: 6 programmes | **Tables**: 0 (W:0 R:0 L:0) | **Taches**: 1 | **Expressions**: 10

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 1)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 345 | 345 | Facturation | MDI | 733 | 165 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>345 - Facturation
**Tache** : [345](#t1) | **Type** : MDI | **Dimensions** : 733 x 165 DLU
**Bloc** : Traitement | **Titre IDE** : Facturation

<!-- FORM-DATA:
{
    "width":  733,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  729,
                         "fmt":  "",
                         "name":  "",
                         "h":  20,
                         "color":  "1",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  40,
                         "type":  "label",
                         "var":  "",
                         "y":  34,
                         "w":  380,
                         "fmt":  "",
                         "name":  "",
                         "h":  29,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  539,
                         "type":  "label",
                         "var":  "",
                         "y":  34,
                         "w":  178,
                         "fmt":  "",
                         "name":  "",
                         "h":  91,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  62,
                         "type":  "label",
                         "var":  "",
                         "y":  44,
                         "w":  45,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "Date",
                         "parent":  5
                     },
                     {
                         "x":  40,
                         "type":  "label",
                         "var":  "",
                         "y":  62,
                         "w":  380,
                         "fmt":  "",
                         "name":  "",
                         "h":  25,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  62,
                         "type":  "label",
                         "var":  "",
                         "y":  70,
                         "w":  96,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Preview",
                         "parent":  10
                     },
                     {
                         "x":  544,
                         "type":  "line",
                         "var":  "",
                         "y":  92,
                         "w":  168,
                         "fmt":  "",
                         "name":  "",
                         "h":  0,
                         "color":  "",
                         "text":  "",
                         "parent":  6
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  138,
                         "w":  727,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "1",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  202,
                         "type":  "edit",
                         "var":  "",
                         "y":  43,
                         "w":  126,
                         "fmt":  "",
                         "name":  "w0_Date",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  330,
                         "type":  "button",
                         "var":  "",
                         "y":  43,
                         "w":  25,
                         "fmt":  "...",
                         "name":  "b_Date",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  202,
                         "type":  "checkbox",
                         "var":  "",
                         "y":  68,
                         "w":  21,
                         "fmt":  "",
                         "name":  "v. preview",
                         "h":  11,
                         "color":  "",
                         "text":  "v. edit C5",
                         "parent":  null
                     },
                     {
                         "x":  550,
                         "type":  "button",
                         "var":  "",
                         "y":  101,
                         "w":  154,
                         "fmt":  "\u0026Imprimer",
                         "name":  "b_Edition",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  445,
                         "type":  "button",
                         "var":  "",
                         "y":  141,
                         "w":  272,
                         "fmt":  "Date \u0026Naissance non saisies",
                         "name":  "b_Edition date naissance=0",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  6,
                         "type":  "edit",
                         "var":  "",
                         "y":  2,
                         "w":  267,
                         "fmt":  "20",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  397,
                         "type":  "edit",
                         "var":  "",
                         "y":  7,
                         "w":  325,
                         "fmt":  "WWW DD MMM YYYYT",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  6,
                         "type":  "edit",
                         "var":  "",
                         "y":  11,
                         "w":  325,
                         "fmt":  "30",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  548,
                         "type":  "image",
                         "var":  "",
                         "y":  39,
                         "w":  159,
                         "fmt":  "",
                         "name":  "",
                         "h":  47,
                         "color":  "",
                         "text":  "",
                         "parent":  6
                     },
                     {
                         "x":  8,
                         "type":  "button",
                         "var":  "",
                         "y":  141,
                         "w":  154,
                         "fmt":  "\u0026Quitter",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  13
                     }
                 ],
    "taskId":  "345",
    "height":  165
}
-->

<details>
<summary><strong>Champs : 5 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 202,43 | w0_Date | - | edit |
| 202,68 | v. preview | - | checkbox |
| 6,2 | 20 | - | edit |
| 397,7 | WWW DD MMM YYYYT | - | edit |
| 6,11 | 30 | - | edit |

</details>

<details>
<summary><strong>Boutons : 4 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| ... | 330,43 | Bouton fonctionnel |
| Imprimer | 550,101 | Lance l'impression |
| Date Naissance non saisies | 445,141 | Appel [   Edit GO/GM date naissance=0 (IDE 349)](PBP-IDE-349.md) |
| Quitter | 8,141 | Quitte le programme |

</details>

## 9. NAVIGATION

Ecran unique: **Facturation**

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **345.1** | [**Facturation** (345)](#t1) [mockup](#ecran-t1) | MDI | 733x165 | Traitement |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Traitement principal]
    ENDOK([END OK])

    START --> INIT --> SAISIE
    SAISIE --> ENDOK

    style START fill:#3fb950,color:#000
    style ENDOK fill:#3fb950,color:#000
```

> **Legende**: Vert = START/END OK | Rouge = END KO | Bleu = Decisions
> *Algorigramme auto-genere. Utiliser `/algorigramme` pour une synthese metier detaillee.*

<!-- TAB:Donnees -->

## 10. TABLES

### Tables utilisees (0)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|

### Colonnes par table (0 / 0 tables avec colonnes identifiees)

## 11. VARIABLES

### 11.1 Variables de session (2)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | v. commandant | Alpha | - |
| D | v. preview | Logical | 1x session |

### 11.2 Autres (4)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| B | w0_Date | Date | - |
| C | b_Date | Alpha | - |
| E | b_Edition | Alpha | - |
| F | b_Edition date naissance=0 | Alpha | - |

## 12. EXPRESSIONS

**10 / 10 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONSTANTE | 2 | 0 |
| DATE | 1 | 0 |
| REFERENCE_VG | 1 | 0 |
| OTHER | 4 | 0 |
| CAST_LOGIQUE | 2 | 0 |

### 12.2 Expressions cles par type

#### CONSTANTE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 4 | `'Date &Naissance non saisies'` | - |
| CONSTANTE | 1 | `'...'` | - |

#### DATE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| DATE | 3 | `Date ()` | - |

#### REFERENCE_VG (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 2 | `VG2` | - |

#### OTHER (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 7 | `SetCrsr (1)` | - |
| OTHER | 10 | `DbDel ('{641,2}'DSOURCE,'')` | - |
| OTHER | 5 | `GetParam ('VILLAGE')` | - |
| OTHER | 6 | `SetCrsr (2)` | - |

#### CAST_LOGIQUE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 9 | `INIPut ('[PREVIEW]'&Trim (Str (VG85,'4'))&'pview=N','FALSE'LOG)` | - |
| CAST_LOGIQUE | 8 | `INIPut ('[PREVIEW]'&Trim (Str (VG85,'4'))&'pview='&IF (v. preview [D],'O','N'),'FALSE'LOG)` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

**Chemin**: (pas de callers directs)

```mermaid
graph LR
    T345[345 Facturation]
    style T345 fill:#58a6ff
    NONE[Aucun caller]
    NONE -.-> T345
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| - | (aucun) | - |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T345[345 Facturation]
    style T345 fill:#58a6ff
    C346[346 Generation Factura...]
    T345 --> C346
    style C346 fill:#3fb950
    C349[349 Edit GOGM date nai...]
    T345 --> C349
    style C349 fill:#3fb950
    C350[350 Calcul date de nai...]
    T345 --> C350
    style C350 fill:#3fb950
    C12[12 Escale]
    T345 --> C12
    style C12 fill:#3fb950
    C347[347 Edit Recap Facture]
    T345 --> C347
    style C347 fill:#3fb950
    C348[348 Edit Detail de Fac...]
    T345 --> C348
    style C348 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [346](PBP-IDE-346.md) |    Generation Facturation | 2 | Sous-programme |
| [349](PBP-IDE-349.md) |    Edit GO/GM date naissance=0 | 2 | Sous-programme |
| [350](PBP-IDE-350.md) | Calcul date de naisssance | 2 | Calcul de donnees |
| [12](PBP-IDE-12.md) | Escale | 1 | Sous-programme |
| [347](PBP-IDE-347.md) |    Edit Recap Facture | 1 | Sous-programme |
| [348](PBP-IDE-348.md) |    Edit Detail de Facture | 1 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 45 | Programme compact |
| Expressions | 10 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 6 | Dependances moderees |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 45) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 1 ecran, 0 traitement)

- **Strategie** : 1 composant(s) UI (Razor/React) avec formulaires et validation.
- 6 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| [Calcul date de naisssance (IDE 350)](PBP-IDE-350.md) | Sous-programme | 2x | Haute - Calcul de donnees |
| [   Edit GO/GM date naissance=0 (IDE 349)](PBP-IDE-349.md) | Sous-programme | 2x | Haute - Sous-programme |
| [   Generation Facturation (IDE 346)](PBP-IDE-346.md) | Sous-programme | 2x | Haute - Sous-programme |
| [   Edit Detail de Facture (IDE 348)](PBP-IDE-348.md) | Sous-programme | 1x | Normale - Sous-programme |
| [   Edit Recap Facture (IDE 347)](PBP-IDE-347.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Escale (IDE 12)](PBP-IDE-12.md) | Sous-programme | 1x | Normale - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 16:33*
