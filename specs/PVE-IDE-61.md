# PVE IDE 61 - Report - Dates selec&Print-719

> **Analyse**: Phases 1-4 2026-02-03 09:02 -> 09:03 (21s) | Assemblage 09:03
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PVE |
| IDE Position | 61 |
| Nom Programme | Report - Dates selec&Print-719 |
| Fichier source | `Prg_61.xml` |
| Domaine metier | Impression |
| Taches | 2 (1 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 2 |

## 2. DESCRIPTION FONCTIONNELLE

**Report - Dates selec&Print-719** assure la gestion complete de ce processus, accessible depuis [Menu Reports (IDE 182)](PVE-IDE-182.md).

Le flux de traitement s'organise en **2 blocs fonctionnels** :

- **Initialisation** (1 tache) : reinitialisation d'etats et de variables de travail
- **Consultation** (1 tache) : ecrans de recherche, selection et consultation

**Logique metier** : 3 regles identifiees couvrant conditions metier.

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Consultation (1 tache)

- **61** - Dates selection **[[ECRAN]](#ecran-t1)**

Delegue a : [Choix - Category (IDE 333)](PVE-IDE-333.md)

#### Phase 2 : Initialisation (1 tache)

- **61.1** - Init cat

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Consultation (1 tache)

Ecrans de recherche et consultation.

---

#### <a id="t1"></a>61 - Dates selection [[ECRAN]](#ecran-t1)

**Role** : Selection par l'operateur : Dates selection.
**Ecran** : 638 x 223 DLU (Type6) | [Voir mockup](#ecran-t1)
**Variables liees** : F (P.o.Output Selection), Q (P.ManualPrepaidSelection), V (v.Dates en anomalie)
**Delegue a** : [Choix - Category (IDE 333)](PVE-IDE-333.md)


### 3.2 Initialisation (1 tache)

Reinitialisation d'etats et variables de travail.

---

#### <a id="t2"></a>61.1 - Init cat

**Role** : Reinitialisation : Init cat.


## 5. REGLES METIER

3 regles identifiees:

### Consultation (1 regles)

#### <a id="rm-RM-001"></a>[RM-001] Si v.Date mini [R]='00/00/0000'DATE alors P.ManualPrepaidSelection [Q] sinon v.Date mini [R])

| Element | Detail |
|---------|--------|
| **Condition** | `v.Date mini [R]='00/00/0000'DATE` |
| **Si vrai** | P.ManualPrepaidSelection [Q] |
| **Si faux** | v.Date mini [R]) |
| **Variables** | Q (P.ManualPrepaidSelection), R (v.Date mini) |
| **Expression source** | Expression 4 : `IF (v.Date mini [R]='00/00/0000'DATE,P.ManualPrepaidSelectio` |
| **Exemple** | Si v.Date mini [R]='00/00/0000'DATE â†’ P.ManualPrepaidSelection [Q]. Sinon â†’ v.Date mini [R]) |
| **Impact** | Bloc Consultation |

### Autres (2 regles)

#### <a id="rm-RM-002"></a>[RM-002] Si v.Discount/FoC [T] alors 'X' sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `v.Discount/FoC [T]` |
| **Si vrai** | 'X' |
| **Si faux** | '') |
| **Variables** | T (v.Discount/FoC) |
| **Expression source** | Expression 28 : `IF(v.Discount/FoC [T],'X','')` |
| **Exemple** | Si v.Discount/FoC [T] â†’ 'X'. Sinon â†’ '') |

#### <a id="rm-RM-003"></a>[RM-003] Si P.Only Manual Prepaid? [P] alors 'X' sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `P.Only Manual Prepaid? [P]` |
| **Si vrai** | 'X' |
| **Si faux** | '') |
| **Variables** | P (P.Only Manual Prepaid?) |
| **Expression source** | Expression 29 : `IF(P.Only Manual Prepaid? [P],'X','')` |
| **Exemple** | Si P.Only Manual Prepaid? [P] â†’ 'X'. Sinon â†’ '') |

## 6. CONTEXTE

- **Appele par**: [Menu Reports (IDE 182)](PVE-IDE-182.md)
- **Appelle**: 2 programmes | **Tables**: 1 (W:0 R:1 L:0) | **Taches**: 2 | **Expressions**: 30

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 2)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 61 | 61 | Dates selection | Type6 | 638 | 223 | Consultation |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>61 - Dates selection
**Tache** : [61](#t1) | **Type** : Type6 | **Dimensions** : 638 x 223 DLU
**Bloc** : Consultation | **Titre IDE** : Dates selection

<!-- FORM-DATA:
{
    "width":  638,
    "vFactor":  8,
    "type":  "Type6",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  4,
                         "type":  "label",
                         "var":  "",
                         "y":  41,
                         "w":  249,
                         "fmt":  "",
                         "name":  "",
                         "h":  52,
                         "color":  "183",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  406,
                         "type":  "label",
                         "var":  "",
                         "y":  42,
                         "w":  229,
                         "fmt":  "",
                         "name":  "",
                         "h":  130,
                         "color":  "183",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  256,
                         "type":  "label",
                         "var":  "",
                         "y":  43,
                         "w":  146,
                         "fmt":  "",
                         "name":  "",
                         "h":  130,
                         "color":  "183",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  6,
                         "type":  "label",
                         "var":  "",
                         "y":  45,
                         "w":  215,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "187",
                         "text":  "Select the accounting period you want to print",
                         "parent":  null
                     },
                     {
                         "x":  263,
                         "type":  "label",
                         "var":  "",
                         "y":  47,
                         "w":  129,
                         "fmt":  "",
                         "name":  "",
                         "h":  15,
                         "color":  "187",
                         "text":  "Output",
                         "parent":  3
                     },
                     {
                         "x":  409,
                         "type":  "label",
                         "var":  "",
                         "y":  49,
                         "w":  221,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "187",
                         "text":  "Select the range of categories you want to print",
                         "parent":  null
                     },
                     {
                         "x":  11,
                         "type":  "label",
                         "var":  "",
                         "y":  60,
                         "w":  48,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "183",
                         "text":  "Date min",
                         "parent":  null
                     },
                     {
                         "x":  411,
                         "type":  "label",
                         "var":  "",
                         "y":  70,
                         "w":  69,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "183",
                         "text":  "Category min",
                         "parent":  null
                     },
                     {
                         "x":  11,
                         "type":  "label",
                         "var":  "",
                         "y":  76,
                         "w":  51,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "183",
                         "text":  "Date max",
                         "parent":  null
                     },
                     {
                         "x":  4,
                         "type":  "label",
                         "var":  "",
                         "y":  94,
                         "w":  249,
                         "fmt":  "",
                         "name":  "",
                         "h":  78,
                         "color":  "183",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  35,
                         "type":  "label",
                         "var":  "",
                         "y":  95,
                         "w":  158,
                         "fmt":  "",
                         "name":  "",
                         "h":  15,
                         "color":  "187",
                         "text":  "Discounts \u0026 Free",
                         "parent":  14
                     },
                     {
                         "x":  410,
                         "type":  "label",
                         "var":  "",
                         "y":  103,
                         "w":  72,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "183",
                         "text":  "Category max",
                         "parent":  null
                     },
                     {
                         "x":  263,
                         "type":  "label",
                         "var":  "",
                         "y":  109,
                         "w":  129,
                         "fmt":  "",
                         "name":  "",
                         "h":  15,
                         "color":  "187",
                         "text":  "Tax",
                         "parent":  3
                     },
                     {
                         "x":  409,
                         "type":  "line",
                         "var":  "",
                         "y":  145,
                         "w":  221,
                         "fmt":  "",
                         "name":  "",
                         "h":  0,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  435,
                         "type":  "label",
                         "var":  "",
                         "y":  154,
                         "w":  175,
                         "fmt":  "",
                         "name":  "",
                         "h":  13,
                         "color":  "183",
                         "text":  "Print only the MANUAL PREPAID",
                         "parent":  2
                     },
                     {
                         "x":  37,
                         "type":  "label",
                         "var":  "",
                         "y":  155,
                         "w":  184,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "183",
                         "text":  "Inclure ventes Giftpass dans gratuités",
                         "parent":  14
                     },
                     {
                         "x":  4,
                         "type":  "label",
                         "var":  "",
                         "y":  178,
                         "w":  631,
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
                         "w":  635,
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
                         "parent":  24
                     },
                     {
                         "x":  585,
                         "type":  "image",
                         "var":  "",
                         "y":  3,
                         "w":  48,
                         "fmt":  "",
                         "name":  "",
                         "h":  37,
                         "color":  "",
                         "text":  "",
                         "parent":  26
                     },
                     {
                         "x":  64,
                         "type":  "edit",
                         "var":  "",
                         "y":  60,
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
                         "y":  76,
                         "w":  73,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  261,
                         "type":  "listbox",
                         "var":  "",
                         "y":  64,
                         "w":  133,
                         "fmt":  "",
                         "name":  "V Printer/Extract_0001",
                         "h":  32,
                         "color":  "110",
                         "text":  "Printer,Extraction",
                         "parent":  3
                     },
                     {
                         "x":  412,
                         "type":  "edit",
                         "var":  "",
                         "y":  85,
                         "w":  22,
                         "fmt":  "",
                         "name":  "CATMINI",
                         "h":  12,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  441,
                         "type":  "edit",
                         "var":  "",
                         "y":  85,
                         "w":  152,
                         "fmt":  "",
                         "name":  "label",
                         "h":  12,
                         "color":  "183",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  34,
                         "type":  "listbox",
                         "var":  "",
                         "y":  112,
                         "w":  163,
                         "fmt":  "",
                         "name":  "Discount",
                         "h":  46,
                         "color":  "110",
                         "text":  "0,1,2",
                         "parent":  14
                     },
                     {
                         "x":  412,
                         "type":  "edit",
                         "var":  "",
                         "y":  120,
                         "w":  22,
                         "fmt":  "",
                         "name":  "CATMAXI",
                         "h":  12,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  442,
                         "type":  "edit",
                         "var":  "",
                         "y":  120,
                         "w":  152,
                         "fmt":  "",
                         "name":  "label_0001",
                         "h":  12,
                         "color":  "183",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  261,
                         "type":  "listbox",
                         "var":  "",
                         "y":  127,
                         "w":  133,
                         "fmt":  "",
                         "name":  "V Before tax/Tax inclusive",
                         "h":  46,
                         "color":  "110",
                         "text":  "Before tax,Tax included",
                         "parent":  3
                     },
                     {
                         "x":  225,
                         "type":  "checkbox",
                         "var":  "",
                         "y":  155,
                         "w":  20,
                         "fmt":  "",
                         "name":  "Print Preview",
                         "h":  13,
                         "color":  "186",
                         "text":  "",
                         "parent":  14
                     },
                     {
                         "x":  12,
                         "type":  "button",
                         "var":  "",
                         "y":  184,
                         "w":  68,
                         "fmt":  "\u0026Cancel",
                         "name":  "",
                         "h":  28,
                         "color":  "",
                         "text":  "",
                         "parent":  23
                     },
                     {
                         "x":  90,
                         "type":  "button",
                         "var":  "",
                         "y":  184,
                         "w":  68,
                         "fmt":  "\u0026Execute",
                         "name":  "",
                         "h":  28,
                         "color":  "",
                         "text":  "",
                         "parent":  23
                     },
                     {
                         "x":  413,
                         "type":  "checkbox",
                         "var":  "",
                         "y":  154,
                         "w":  20,
                         "fmt":  "",
                         "name":  "P.Only Manual Prepaid?_0001",
                         "h":  13,
                         "color":  "186",
                         "text":  "",
                         "parent":  2
                     }
                 ],
    "taskId":  "61",
    "height":  223
}
-->

<details>
<summary><strong>Champs : 8 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 64,60 | (sans nom) | - | edit |
| 64,76 | (sans nom) | - | edit |
| 412,85 | CATMINI | - | edit |
| 441,85 | label | - | edit |
| 412,120 | CATMAXI | - | edit |
| 442,120 | label_0001 | - | edit |
| 225,155 | Print Preview | - | checkbox |
| 413,154 | P.Only Manual Prepaid?_0001 | - | checkbox |

</details>

<details>
<summary><strong>Boutons : 2 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Cancel | 12,184 | Annule et retour au menu |
| Execute | 90,184 | Bouton fonctionnel |

</details>

## 9. NAVIGATION

Ecran unique: **Dates selection**

### 9.3 Structure hierarchique (2 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **61.1** | [**Dates selection** (61)](#t1) [mockup](#ecran-t1) | Type6 | 638x223 | Consultation |
| **61.2** | [**Init cat** (61.1)](#t2) | MDI | - | Initialisation |

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

### Tables utilisees (1)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 379 | pv_customer_temp |  | DB | R |   |   | 2 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 379 - pv_customer_temp (R) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P.o. Date mini | R | Date |
| B | P.o. Date Maxi | R | Date |
| C | P.i. Contrôle HD | R | Logical |
| D | P.o. Période nombre JH | R | Numeric |
| E | P.o. Jours Période | R | Numeric |
| F | P.o.Output Selection | R | Alpha |
| G | P.o.Before Tax/Tax Included | R | Alpha |
| H | P.i.Visible Tax | R | Logical |
| I | P.o.Execute Print Report | R | Logical |
| J | P.i.Categorie Visible | R | Logical |
| K | P.o.Catéorie Mini | R | Numeric |
| L | P.o.Catéorie Maxi | R | Numeric |
| M | P.i. Discount&Free Visible | R | Logical |
| N | P.o. Choix Discount,Free | R | Numeric |
| O | P.o.Giftpass dans gratuites? | R | Logical |
| P | P.Only Manual Prepaid? | R | Logical |
| Q | P.ManualPrepaidSelection | R | Logical |
| R | v.Date mini | R | Date |
| S | v.Date maxi | R | Date |
| T | v.Discount/FoC | R | Numeric |
| U | v.Giftpass dans gratuites? | R | Logical |
| V | v.Dates en anomalie | R | Unicode |
| W | v.Output | R | Alpha |
| X | v.Tax | R | Alpha |
| Y | v.Cat Mini | R | Numeric |
| Z | v.Cat Maxi | R | Numeric |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (17)

Variables recues du programme appelant ([Menu Reports (IDE 182)](PVE-IDE-182.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P.o. Date mini | Date | - |
| B | P.o. Date Maxi | Date | - |
| C | P.i. Contrôle HD | Logical | 1x parametre entrant |
| D | P.o. Période nombre JH | Numeric | - |
| E | P.o. Jours Période | Numeric | 1x parametre entrant |
| F | P.o.Output Selection | Alpha | - |
| G | P.o.Before Tax/Tax Included | Alpha | - |
| H | P.i.Visible Tax | Logical | 1x parametre entrant |
| I | P.o.Execute Print Report | Logical | - |
| J | P.i.Categorie Visible | Logical | 1x parametre entrant |
| K | P.o.Catéorie Mini | Numeric | - |
| L | P.o.Catéorie Maxi | Numeric | - |
| M | P.i. Discount&Free Visible | Logical | - |
| N | P.o. Choix Discount,Free | Numeric | - |
| O | P.o.Giftpass dans gratuites? | Logical | - |
| P | P.Only Manual Prepaid? | Logical | 1x parametre entrant |
| Q | P.ManualPrepaidSelection | Logical | 3x parametre entrant |

### 11.2 Variables de session (9)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| R | v.Date mini | Date | 3x session |
| S | v.Date maxi | Date | 1x session |
| T | v.Discount/FoC | Numeric | 2x session |
| U | v.Giftpass dans gratuites? | Logical | - |
| V | v.Dates en anomalie | Unicode | 2x session |
| W | v.Output | Alpha | 1x session |
| X | v.Tax | Alpha | 2x session |
| Y | v.Cat Mini | Numeric | - |
| Z | v.Cat Maxi | Numeric | - |

<details>
<summary>Toutes les 26 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| P0 | **A** | P.o. Date mini | Date |
| P0 | **B** | P.o. Date Maxi | Date |
| P0 | **C** | P.i. Contrôle HD | Logical |
| P0 | **D** | P.o. Période nombre JH | Numeric |
| P0 | **E** | P.o. Jours Période | Numeric |
| P0 | **F** | P.o.Output Selection | Alpha |
| P0 | **G** | P.o.Before Tax/Tax Included | Alpha |
| P0 | **H** | P.i.Visible Tax | Logical |
| P0 | **I** | P.o.Execute Print Report | Logical |
| P0 | **J** | P.i.Categorie Visible | Logical |
| P0 | **K** | P.o.Catéorie Mini | Numeric |
| P0 | **L** | P.o.Catéorie Maxi | Numeric |
| P0 | **M** | P.i. Discount&Free Visible | Logical |
| P0 | **N** | P.o. Choix Discount,Free | Numeric |
| P0 | **O** | P.o.Giftpass dans gratuites? | Logical |
| P0 | **P** | P.Only Manual Prepaid? | Logical |
| P0 | **Q** | P.ManualPrepaidSelection | Logical |
| V. | **R** | v.Date mini | Date |
| V. | **S** | v.Date maxi | Date |
| V. | **T** | v.Discount/FoC | Numeric |
| V. | **U** | v.Giftpass dans gratuites? | Logical |
| V. | **V** | v.Dates en anomalie | Unicode |
| V. | **W** | v.Output | Alpha |
| V. | **X** | v.Tax | Alpha |
| V. | **Y** | v.Cat Mini | Numeric |
| V. | **Z** | v.Cat Maxi | Numeric |

</details>

## 12. EXPRESSIONS

**30 / 30 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONDITION | 7 | 3 |
| CALCULATION | 1 | 0 |
| CONSTANTE | 3 | 0 |
| DATE | 1 | 0 |
| OTHER | 16 | 0 |
| CAST_LOGIQUE | 2 | 0 |

### 12.2 Expressions cles par type

#### CONDITION (7 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 28 | `IF(v.Discount/FoC [T],'X','')` | [RM-002](#rm-RM-002) |
| CONDITION | 4 | `IF (v.Date mini [R]='00/00/0000'DATE,P.ManualPrepaidSelection [Q],v.Date mini [R])` | [RM-001](#rm-RM-001) |
| CONDITION | 29 | `IF(P.Only Manual Prepaid? [P],'X','')` | [RM-003](#rm-RM-003) |
| CONDITION | 11 | `v.Giftpass dans gratui... [U]<>''` | - |
| CONDITION | 16 | `v.Dates en anomalie [V]='Printer'` | - |
| ... | | *+2 autres* | |

#### CALCULATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 9 | `StrBuild('No HD for @1@: Dispatch and Amount HT/HD will be wrong. Please communicate this information to your Financial Manager.', v.Giftpass dans gratui... [U])` | - |

#### CONSTANTE (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 8 | `0` | - |
| CONSTANTE | 2 | `'Printer'` | - |
| CONSTANTE | 1 | `'Before tax'` | - |

#### DATE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| DATE | 3 | `Date ()` | - |

#### OTHER (16 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 23 | `v.Tax [X]` | - |
| OTHER | 24 | `[AB]` | - |
| OTHER | 21 | `v.Tax [X]` | - |
| OTHER | 22 | `[AB]` | - |
| OTHER | 27 | `v.Discount/FoC [T]` | - |
| ... | | *+11 autres* | |

#### CAST_LOGIQUE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 18 | `'TRUE'LOG` | - |
| CAST_LOGIQUE | 17 | `'FALSE'LOG` | - |

### 12.3 Toutes les expressions (30)

<details>
<summary>Voir les 30 expressions</summary>

#### CONDITION (7)

| IDE | Expression Decodee |
|-----|-------------------|
| 5 | `v.Date mini [R]='00/00/0000'DATE OR v.Date mini [R]<P.ManualPrepaidSelection [Q]` |
| 4 | `IF (v.Date mini [R]='00/00/0000'DATE,P.ManualPrepaidSelection [Q],v.Date mini [R])` |
| 28 | `IF(v.Discount/FoC [T],'X','')` |
| 29 | `IF(P.Only Manual Prepaid? [P],'X','')` |
| 10 | `P.o. Jours Période [E]=0` |
| 11 | `v.Giftpass dans gratui... [U]<>''` |
| 16 | `v.Dates en anomalie [V]='Printer'` |

#### CALCULATION (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 9 | `StrBuild('No HD for @1@: Dispatch and Amount HT/HD will be wrong. Please communicate this information to your Financial Manager.', v.Giftpass dans gratui... [U])` |

#### CONSTANTE (3)

| IDE | Expression Decodee |
|-----|-------------------|
| 1 | `'Before tax'` |
| 2 | `'Printer'` |
| 8 | `0` |

#### DATE (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 3 | `Date ()` |

#### OTHER (16)

| IDE | Expression Decodee |
|-----|-------------------|
| 6 | `P.ManualPrepaidSelection [Q]` |
| 7 | `v.Date mini [R]` |
| 12 | `P.i. Contrôle HD [C]` |
| 13 | `v.Dates en anomalie [V]` |
| 14 | `v.Output [W]` |
| 15 | `P.i.Visible Tax [H]` |
| 19 | `P.i.Categorie Visible [J]` |
| 20 | `GetParam('SERVICE')` |
| 21 | `v.Tax [X]` |
| 22 | `[AB]` |
| 23 | `v.Tax [X]` |
| 24 | `[AB]` |
| 25 | `P.i. Discount&Free Vis... [M]` |
| 26 | `v.Date maxi [S]` |
| 27 | `v.Discount/FoC [T]` |
| 30 | `[AF]` |

#### CAST_LOGIQUE (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 17 | `'FALSE'LOG` |
| 18 | `'TRUE'LOG` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Menu Reports (IDE 182)](PVE-IDE-182.md) -> **Report - Dates selec&Print-719 (IDE 61)**

```mermaid
graph LR
    T61[61 Report - Dates sele...]
    style T61 fill:#58a6ff
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
    CC182 --> T61
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [182](PVE-IDE-182.md) | Menu Reports | 2 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T61[61 Report - Dates sele...]
    style T61 fill:#58a6ff
    C333[333 Choix - Category]
    T61 --> C333
    style C333 fill:#3fb950
    C58[58 Control Compute hot...]
    T61 --> C58
    style C58 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [333](PVE-IDE-333.md) | Choix - Category | 2 | Selection/consultation |
| [58](PVE-IDE-58.md) | Control & Compute hotel days | 1 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 86 | Programme compact |
| Expressions | 30 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 2 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 86) | Code sain |
| Regles metier | 3 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Consultation (1 tache: 1 ecran, 0 traitement)

- **Strategie** : Composants de recherche/selection en modales.
- 1 ecran : Dates selection

#### Initialisation (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Constructeur/methode `InitAsync()` dans l'orchestrateur.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| [Choix - Category (IDE 333)](PVE-IDE-333.md) | Sous-programme | 2x | Haute - Selection/consultation |
| [Control & Compute hotel days (IDE 58)](PVE-IDE-58.md) | Sous-programme | 1x | Normale - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 09:03*
