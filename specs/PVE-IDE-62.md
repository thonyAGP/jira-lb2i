# PVE IDE 62 - Report - Dates selection&PREPA

> **Analyse**: Phases 1-4 2026-02-03 09:03 -> 09:03 (20s) | Assemblage 09:03
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PVE |
| IDE Position | 62 |
| Nom Programme | Report - Dates selection&PREPA |
| Fichier source | `Prg_62.xml` |
| Domaine metier | Consultation |
| Taches | 1 (1 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 1 |

## 2. DESCRIPTION FONCTIONNELLE

**Report - Dates selection&PREPA** assure la gestion complete de ce processus, accessible depuis [Menu Reports (IDE 182)](PVE-IDE-182.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Consultation** (1 tache) : ecrans de recherche, selection et consultation

**Logique metier** : 2 regles identifiees couvrant conditions metier.

## 3. BLOCS FONCTIONNELS

### 3.1 Consultation (1 tache)

Ecrans de recherche et consultation.

---

#### <a id="t1"></a>62 - Dates selection [[ECRAN]](#ecran-t1)

**Role** : Selection par l'operateur : Dates selection.
**Ecran** : 440 x 220 DLU (Type6) | [Voir mockup](#ecran-t1)
**Variables liees** : F (P.Output Selection), U (V Dates en anomalie)


## 5. REGLES METIER

2 regles identifiees:

### Autres (2 regles)

#### <a id="rm-RM-001"></a>[RM-001] Si V Date maxi [S]='00/00/0000'DATE alors V Date mini [R] sinon V Date maxi [S])

| Element | Detail |
|---------|--------|
| **Condition** | `V Date maxi [S]='00/00/0000'DATE` |
| **Si vrai** | V Date mini [R] |
| **Si faux** | V Date maxi [S]) |
| **Variables** | R (V Date mini), S (V Date maxi) |
| **Expression source** | Expression 4 : `IF (V Date maxi [S]='00/00/0000'DATE,V Date mini [R],V Date ` |
| **Exemple** | Si V Date maxi [S]='00/00/0000'DATE â†’ V Date mini [R]. Sinon â†’ V Date maxi [S]) |

#### <a id="rm-RM-002"></a>[RM-002] Si P.Only Manual Prepaid? [O] alors 'X' sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `P.Only Manual Prepaid? [O]` |
| **Si vrai** | 'X' |
| **Si faux** | '') |
| **Variables** | O (P.Only Manual Prepaid?) |
| **Expression source** | Expression 18 : `IF(P.Only Manual Prepaid? [O],'X','')` |
| **Exemple** | Si P.Only Manual Prepaid? [O] â†’ 'X'. Sinon â†’ '') |

## 6. CONTEXTE

- **Appele par**: [Menu Reports (IDE 182)](PVE-IDE-182.md)
- **Appelle**: 1 programmes | **Tables**: 0 (W:0 R:0 L:0) | **Taches**: 1 | **Expressions**: 24

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 1)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 62 | 62 | Dates selection | Type6 | 440 | 220 | Consultation |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>62 - Dates selection
**Tache** : [62](#t1) | **Type** : Type6 | **Dimensions** : 440 x 220 DLU
**Bloc** : Consultation | **Titre IDE** : Dates selection

<!-- FORM-DATA:
{
    "width":  440,
    "vFactor":  8,
    "type":  "Type6",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  4,
                         "type":  "label",
                         "var":  "",
                         "y":  42,
                         "w":  222,
                         "fmt":  "",
                         "name":  "",
                         "h":  60,
                         "color":  "183",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  230,
                         "type":  "label",
                         "var":  "",
                         "y":  42,
                         "w":  206,
                         "fmt":  "",
                         "name":  "",
                         "h":  130,
                         "color":  "183",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  237,
                         "type":  "label",
                         "var":  "",
                         "y":  46,
                         "w":  129,
                         "fmt":  "",
                         "name":  "",
                         "h":  15,
                         "color":  "187",
                         "text":  "Output",
                         "parent":  2
                     },
                     {
                         "x":  6,
                         "type":  "label",
                         "var":  "",
                         "y":  49,
                         "w":  215,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "187",
                         "text":  "Select the accounting period you want to print",
                         "parent":  null
                     },
                     {
                         "x":  11,
                         "type":  "label",
                         "var":  "",
                         "y":  65,
                         "w":  48,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "183",
                         "text":  "Date min",
                         "parent":  null
                     },
                     {
                         "x":  11,
                         "type":  "label",
                         "var":  "",
                         "y":  81,
                         "w":  51,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "183",
                         "text":  "Date max",
                         "parent":  null
                     },
                     {
                         "x":  5,
                         "type":  "label",
                         "var":  "",
                         "y":  102,
                         "w":  222,
                         "fmt":  "",
                         "name":  "",
                         "h":  70,
                         "color":  "183",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  37,
                         "type":  "label",
                         "var":  "",
                         "y":  108,
                         "w":  158,
                         "fmt":  "",
                         "name":  "",
                         "h":  15,
                         "color":  "187",
                         "text":  "Seminar",
                         "parent":  9
                     },
                     {
                         "x":  14,
                         "type":  "label",
                         "var":  "",
                         "y":  130,
                         "w":  62,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "183",
                         "text":  "Seminar :",
                         "parent":  null
                     },
                     {
                         "x":  227,
                         "type":  "line",
                         "var":  "",
                         "y":  145,
                         "w":  208,
                         "fmt":  "",
                         "name":  "",
                         "h":  0,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  14,
                         "type":  "label",
                         "var":  "",
                         "y":  150,
                         "w":  54,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "183",
                         "text":  "Order :",
                         "parent":  null
                     },
                     {
                         "x":  255,
                         "type":  "label",
                         "var":  "",
                         "y":  154,
                         "w":  175,
                         "fmt":  "",
                         "name":  "",
                         "h":  13,
                         "color":  "183",
                         "text":  "Print only the MANUAL PREPAID",
                         "parent":  null
                     },
                     {
                         "x":  4,
                         "type":  "label",
                         "var":  "",
                         "y":  176,
                         "w":  433,
                         "fmt":  "",
                         "name":  "",
                         "h":  43,
                         "color":  "183",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  438,
                         "fmt":  "",
                         "name":  "",
                         "h":  41,
                         "color":  "182",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  13,
                         "type":  "label",
                         "var":  "",
                         "y":  16,
                         "w":  243,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "186",
                         "text":  "Accounting period and print options",
                         "parent":  16
                     },
                     {
                         "x":  64,
                         "type":  "edit",
                         "var":  "",
                         "y":  65,
                         "w":  73,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  64,
                         "type":  "edit",
                         "var":  "",
                         "y":  81,
                         "w":  73,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  12,
                         "type":  "button",
                         "var":  "",
                         "y":  182,
                         "w":  68,
                         "fmt":  "\u0026Cancel",
                         "name":  "",
                         "h":  28,
                         "color":  "",
                         "text":  "",
                         "parent":  15
                     },
                     {
                         "x":  90,
                         "type":  "button",
                         "var":  "",
                         "y":  182,
                         "w":  68,
                         "fmt":  "\u0026Execute",
                         "name":  "",
                         "h":  28,
                         "color":  "",
                         "text":  "",
                         "parent":  15
                     },
                     {
                         "x":  375,
                         "type":  "image",
                         "var":  "",
                         "y":  3,
                         "w":  48,
                         "fmt":  "",
                         "name":  "",
                         "h":  37,
                         "color":  "",
                         "text":  "",
                         "parent":  18
                     },
                     {
                         "x":  235,
                         "type":  "listbox",
                         "var":  "",
                         "y":  66,
                         "w":  133,
                         "fmt":  "",
                         "name":  "V Printer/Extract_0001",
                         "h":  32,
                         "color":  "110",
                         "text":  "Printer,Extraction",
                         "parent":  2
                     },
                     {
                         "x":  233,
                         "type":  "checkbox",
                         "var":  "",
                         "y":  154,
                         "w":  20,
                         "fmt":  "",
                         "name":  "Print Preview",
                         "h":  13,
                         "color":  "186",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  82,
                         "type":  "combobox",
                         "var":  "",
                         "y":  131,
                         "w":  134,
                         "fmt":  "",
                         "name":  "V Seminaire",
                         "h":  12,
                         "color":  "",
                         "text":  "\\",
                         "parent":  null
                     },
                     {
                         "x":  82,
                         "type":  "combobox",
                         "var":  "",
                         "y":  151,
                         "w":  134,
                         "fmt":  "",
                         "name":  "V.Ordre_Tri",
                         "h":  12,
                         "color":  "",
                         "text":  "D,P,I,C",
                         "parent":  null
                     }
                 ],
    "taskId":  "62",
    "height":  220
}
-->

<details>
<summary><strong>Champs : 5 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 64,65 | (sans nom) | - | edit |
| 64,81 | (sans nom) | - | edit |
| 233,154 | Print Preview | - | checkbox |
| 82,131 | V Seminaire | - | combobox |
| 82,151 | V.Ordre_Tri | - | combobox |

</details>

<details>
<summary><strong>Boutons : 2 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Cancel | 12,182 | Annule et retour au menu |
| Execute | 90,182 | Bouton fonctionnel |

</details>

## 9. NAVIGATION

Ecran unique: **Dates selection**

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **62.1** | [**Dates selection** (62)](#t1) [mockup](#ecran-t1) | Type6 | 440x220 | Consultation |

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

### 11.1 Parametres entrants (17)

Variables recues du programme appelant ([Menu Reports (IDE 182)](PVE-IDE-182.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P. Date mini | Date | - |
| B | P. Date Maxi | Date | - |
| C | P. Contrôle HD? | Logical | 1x parametre entrant |
| D | P. Période nombre JH | Numeric | - |
| E | P. Jours Période | Numeric | 1x parametre entrant |
| F | P.Output Selection | Alpha | - |
| G | P.Before Tax/Tax Included | Alpha | - |
| H | P.Visible Tax? | Logical | - |
| I | P.Execute Print Report? | Logical | - |
| J | P.Categorie Visible? | Logical | - |
| K | P.Catéorie Mini | Numeric | - |
| L | P.Catéorie Maxi | Numeric | - |
| M | P. Discount&Free Visible? | Logical | - |
| N | P. Choix Discount,Free | Numeric | - |
| O | P.Only Manual Prepaid? | Logical | 2x parametre entrant |
| P | P.o.Ordre_Tri | Unicode | 1x parametre entrant |
| Q | P.o.Seminaire | Unicode | 2x parametre entrant |

### 11.2 Variables de session (7)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| R | V Date mini | Date | [62](#t1) |
| S | V Date maxi | Date | [62](#t1) |
| T | V Discount/FoC | Numeric | - |
| U | V Dates en anomalie | Unicode | [62](#t1) |
| V | V Output | Alpha | 1x session |
| W | V Tax | Alpha | 1x session |
| X | V.Service Gestion? | Logical | 1x session |

<details>
<summary>Toutes les 24 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| P0 | **A** | P. Date mini | Date |
| P0 | **B** | P. Date Maxi | Date |
| P0 | **C** | P. Contrôle HD? | Logical |
| P0 | **D** | P. Période nombre JH | Numeric |
| P0 | **E** | P. Jours Période | Numeric |
| P0 | **F** | P.Output Selection | Alpha |
| P0 | **G** | P.Before Tax/Tax Included | Alpha |
| P0 | **H** | P.Visible Tax? | Logical |
| P0 | **I** | P.Execute Print Report? | Logical |
| P0 | **J** | P.Categorie Visible? | Logical |
| P0 | **K** | P.Catéorie Mini | Numeric |
| P0 | **L** | P.Catéorie Maxi | Numeric |
| P0 | **M** | P. Discount&Free Visible? | Logical |
| P0 | **N** | P. Choix Discount,Free | Numeric |
| P0 | **O** | P.Only Manual Prepaid? | Logical |
| P0 | **P** | P.o.Ordre_Tri | Unicode |
| P0 | **Q** | P.o.Seminaire | Unicode |
| V. | **R** | V Date mini | Date |
| V. | **S** | V Date maxi | Date |
| V. | **T** | V Discount/FoC | Numeric |
| V. | **U** | V Dates en anomalie | Unicode |
| V. | **V** | V Output | Alpha |
| V. | **W** | V Tax | Alpha |
| V. | **X** | V.Service Gestion? | Logical |

</details>

## 12. EXPRESSIONS

**24 / 24 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONDITION | 9 | 2 |
| CALCULATION | 1 | 0 |
| CONSTANTE | 4 | 0 |
| DATE | 1 | 0 |
| OTHER | 7 | 0 |
| CAST_LOGIQUE | 2 | 0 |

### 12.2 Expressions cles par type

#### CONDITION (9 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 4 | `IF (V Date maxi [S]='00/00/0000'DATE,V Date mini [R],V Date maxi [S])` | [RM-001](#rm-RM-001) |
| CONDITION | 18 | `IF(P.Only Manual Prepaid? [O],'X','')` | [RM-002](#rm-RM-002) |
| CONDITION | 22 | `GetParam('SERVICE')='GEST'` | - |
| CONDITION | 21 | `Trim(P.o.Seminaire [Q])<>''` | - |
| CONDITION | 24 | `VG127 AND Trim(P.o.Seminaire [Q])<>'' AND P.o.Ordre_Tri [P]=''` | - |
| ... | | *+4 autres* | |

#### CALCULATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 9 | `StrBuild('No HD for @1@: Dispatch and Amount HT/HD will be wrong. Please communicate this information to your Financial Manager.', V Dates en anomalie [U])` | - |

#### CONSTANTE (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 8 | `0` | - |
| CONSTANTE | 17 | `'C'` | - |
| CONSTANTE | 1 | `'Before tax'` | - |
| CONSTANTE | 2 | `'Printer'` | - |

#### DATE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| DATE | 3 | `Date ()` | - |

#### OTHER (7 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 14 | `V Tax [W]` | - |
| OTHER | 19 | `NOT(ISNULL(P.Only Manual Prepaid? [O]))` | - |
| OTHER | 20 | `ASCIIChr(33)` | - |
| OTHER | 13 | `V Output [V]` | - |
| OTHER | 6 | `V Date mini [R]` | - |
| ... | | *+2 autres* | |

#### CAST_LOGIQUE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 16 | `'TRUE'LOG` | - |
| CAST_LOGIQUE | 15 | `'FALSE'LOG` | - |

### 12.3 Toutes les expressions (24)

<details>
<summary>Voir les 24 expressions</summary>

#### CONDITION (9)

| IDE | Expression Decodee |
|-----|-------------------|
| 5 | `V Date maxi [S]='00/00/0000'DATE OR V Date maxi [S]<V Date mini [R]` |
| 4 | `IF (V Date maxi [S]='00/00/0000'DATE,V Date mini [R],V Date maxi [S])` |
| 18 | `IF(P.Only Manual Prepaid? [O],'X','')` |
| 23 | `IF(V.Service Gestion? [X],'Service and Date,Service and Person,Service and Item Label,Service and Item Category',
      'Date,Person,Item Label,Item Category')` |
| 10 | `P. Jours Période [E]=0` |
| 11 | `V Dates en anomalie [U]<>''` |
| 22 | `GetParam('SERVICE')='GEST'` |
| 21 | `Trim(P.o.Seminaire [Q])<>''` |
| 24 | `VG127 AND Trim(P.o.Seminaire [Q])<>'' AND P.o.Ordre_Tri [P]=''` |

#### CALCULATION (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 9 | `StrBuild('No HD for @1@: Dispatch and Amount HT/HD will be wrong. Please communicate this information to your Financial Manager.', V Dates en anomalie [U])` |

#### CONSTANTE (4)

| IDE | Expression Decodee |
|-----|-------------------|
| 1 | `'Before tax'` |
| 2 | `'Printer'` |
| 8 | `0` |
| 17 | `'C'` |

#### DATE (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 3 | `Date ()` |

#### OTHER (7)

| IDE | Expression Decodee |
|-----|-------------------|
| 6 | `V Date mini [R]` |
| 7 | `V Date maxi [S]` |
| 12 | `P. Contrôle HD? [C]` |
| 13 | `V Output [V]` |
| 14 | `V Tax [W]` |
| 19 | `NOT(ISNULL(P.Only Manual Prepaid? [O]))` |
| 20 | `ASCIIChr(33)` |

#### CAST_LOGIQUE (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 15 | `'FALSE'LOG` |
| 16 | `'TRUE'LOG` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Menu Reports (IDE 182)](PVE-IDE-182.md) -> **Report - Dates selection&PREPA (IDE 62)**

```mermaid
graph LR
    T62[62 Report - Dates sele...]
    style T62 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC143[143 START]
    style CC143 fill:#f59e0b
    CC439[439 Menu]
    style CC439 fill:#f59e0b
    CC420[420 Menu==V4___]
    style CC420 fill:#f59e0b
    CC185[185 Menu]
    style CC185 fill:#f59e0b
    CC353[353 Menu==V4]
    style CC353 fill:#f59e0b
    CC182[182 Menu Reports]
    style CC182 fill:#3fb950
    CC185 --> CC182
    CC353 --> CC182
    CC420 --> CC182
    CC439 --> CC182
    CC143 --> CC185
    CC143 --> CC353
    CC143 --> CC420
    CC143 --> CC439
    CC1 --> CC143
    CC182 --> T62
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [182](PVE-IDE-182.md) | Menu Reports | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T62[62 Report - Dates sele...]
    style T62 fill:#58a6ff
    C58[58 Control Compute hot...]
    T62 --> C58
    style C58 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [58](PVE-IDE-58.md) | Control & Compute hotel days | 1 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 55 | Programme compact |
| Expressions | 24 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 1 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 55) | Code sain |
| Regles metier | 2 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Consultation (1 tache: 1 ecran, 0 traitement)

- **Strategie** : Composants de recherche/selection en modales.
- 1 ecran : Dates selection

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| [Control & Compute hotel days (IDE 58)](PVE-IDE-58.md) | Sous-programme | 1x | Normale - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 09:03*
