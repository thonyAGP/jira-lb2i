# PVE IDE 201 - Discounts

> **Analyse**: Phases 1-4 2026-02-03 18:52 -> 18:52 (12s) | Assemblage 18:52
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PVE |
| IDE Position | 201 |
| Nom Programme | Discounts |
| Fichier source | `Prg_201.xml` |
| Dossier IDE | Mobile |
| Taches | 4 (2 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 1 |

## 2. DESCRIPTION FONCTIONNELLE

**Discounts** assure la gestion complete de ce processus, accessible depuis [Main Sale (IDE 186)](PVE-IDE-186.md), [Main Sale-664 (IDE 187)](PVE-IDE-187.md), [Main Sale Sale Bar Code (IDE 214)](PVE-IDE-214.md), [Main Sale (IDE 363)](PVE-IDE-363.md), [Main Sale-664 (IDE 364)](PVE-IDE-364.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (4 taches) : traitements metier divers

**Donnees modifiees** : 1 tables en ecriture (pv_height).

**Logique metier** : 4 regles identifiees couvrant conditions metier.

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (4 taches)

- **201** - Discount **[[ECRAN]](#ecran-t1)**
- **201.1** - Discounts list **[[ECRAN]](#ecran-t2)**
- **201.2** - Keyboard **[[ECRAN]](#ecran-t3)**
- **201.3** - (sans nom)

Delegue a : [Lancement clavier (IDE 317)](PVE-IDE-317.md)

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| pv_height | **W**/L (2 usages) |  |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (4 taches)

Traitements internes.

---

#### <a id="t1"></a>201 - Discount [[ECRAN]](#ecran-t1)

**Role** : Traitement : Discount.
**Ecran** : 1138 x 310 DLU (Type6) | [Voir mockup](#ecran-t1)

<details>
<summary>3 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [201.1](#t2) | Discounts list **[[ECRAN]](#ecran-t2)** | Traitement |
| [201.2](#t3) | Keyboard **[[ECRAN]](#ecran-t3)** | Traitement |
| [201.3](#t7) | (sans nom) | Traitement |

</details>
**Variables liees** : A (P. Discount), I (T Discount)
**Delegue a** : [Lancement clavier (IDE 317)](PVE-IDE-317.md)

---

#### <a id="t2"></a>201.1 - Discounts list [[ECRAN]](#ecran-t2)

**Role** : Traitement : Discounts list.
**Ecran** : 245 x 161 DLU (Type6) | [Voir mockup](#ecran-t2)
**Delegue a** : [Lancement clavier (IDE 317)](PVE-IDE-317.md)

---

#### <a id="t3"></a>201.2 - Keyboard [[ECRAN]](#ecran-t3)

**Role** : Traitement : Keyboard.
**Ecran** : 199 x 80 DLU (MDI) | [Voir mockup](#ecran-t3)
**Delegue a** : [Lancement clavier (IDE 317)](PVE-IDE-317.md)

---

#### <a id="t7"></a>201.3 - (sans nom)

**Role** : Traitement interne.
**Delegue a** : [Lancement clavier (IDE 317)](PVE-IDE-317.md)


## 5. REGLES METIER

4 regles identifiees:

### Autres (4 regles)

#### <a id="rm-RM-001"></a>[RM-001] Traitement si Val (V Tab [L],'') est non nul

| Element | Detail |
|---------|--------|
| **Condition** | `Val (V Tab [L]` |
| **Si vrai** | '')<>0 |
| **Si faux** | 100*(1-Val (V Tab [L],'10')/P. Price [C]),0) |
| **Variables** | C (P. Price), L (V Tab) |
| **Expression source** | Expression 4 : `IF (Val (V Tab [L],'')<>0,100*(1-Val (V Tab [L],'10')/P. Pri` |
| **Exemple** | Si Val (V Tab [L] â†’ '')<>0. Sinon â†’ 100*(1-Val (V Tab [L],'10')/P. Price [C]),0) |

#### <a id="rm-RM-002"></a>[RM-002] Traitement conditionnel si P. Discount [A] est a zero

| Element | Detail |
|---------|--------|
| **Condition** | `P. Discount [A]=0` |
| **Si vrai** | 0 |
| **Si faux** | [O]) |
| **Variables** | A (P. Discount) |
| **Expression source** | Expression 6 : `IF (P. Discount [A]=0,0,[O])` |
| **Exemple** | Si P. Discount [A]=0 â†’ 0. Sinon â†’ [O]) |
| **Impact** | [201 - Discount](#t1) |

#### <a id="rm-RM-003"></a>[RM-003] Condition toujours vraie (flag actif)

| Element | Detail |
|---------|--------|
| **Condition** | `P. Discount [A]<>100` |
| **Si vrai** | 'Select the discount %'&IF (GetParam ('RENTAL')='TRUE'LOG |
| **Si faux** | ' or the discounted price','')&' and justify it with a reason from the list','justify discount with a reason from the list') |
| **Variables** | A (P. Discount) |
| **Expression source** | Expression 19 : `IF(P. Discount [A]<>100,'Select the discount %'&IF (GetParam` |
| **Exemple** | Si P. Discount [A]<>100 â†’ 'Select the discount %'&IF (GetParam ('RENTAL')='TRUE'LOG |
| **Impact** | [201 - Discount](#t1) |

#### <a id="rm-RM-004"></a>[RM-004] Condition toujours vraie (flag actif)

| Element | Detail |
|---------|--------|
| **Condition** | `GetParam('HARMONYDISC')` |
| **Si vrai** | [T]='TRUE'LOG |
| **Si faux** | 'TRUE'LOG) |
| **Expression source** | Expression 34 : `IF(GetParam('HARMONYDISC'),[T]='TRUE'LOG,'TRUE'LOG)` |
| **Exemple** | Si GetParam('HARMONYDISC') â†’ [T]='TRUE'LOG. Sinon â†’ 'TRUE'LOG) |

## 6. CONTEXTE

- **Appele par**: [Main Sale (IDE 186)](PVE-IDE-186.md), [Main Sale-664 (IDE 187)](PVE-IDE-187.md), [Main Sale Sale Bar Code (IDE 214)](PVE-IDE-214.md), [Main Sale (IDE 363)](PVE-IDE-363.md), [Main Sale-664 (IDE 364)](PVE-IDE-364.md)
- **Appelle**: 1 programmes | **Tables**: 2 (W:1 R:1 L:1) | **Taches**: 4 | **Expressions**: 35

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (2 / 4)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 201 | 201 | Discount | Type6 | 1138 | 310 | Traitement |
| 2 | 201.1 | 201.1 | Discounts list | Type6 | 245 | 161 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>201 - Discount
**Tache** : [201](#t1) | **Type** : Type6 | **Dimensions** : 1138 x 310 DLU
**Bloc** : Traitement | **Titre IDE** : Discount

<!-- FORM-DATA:
{
    "width":  1138,
    "vFactor":  8,
    "type":  "Type6",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  64,
                         "type":  "label",
                         "var":  "",
                         "y":  94,
                         "w":  162,
                         "fmt":  "",
                         "name":  "",
                         "h":  67,
                         "color":  "189",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  64,
                         "type":  "label",
                         "var":  "",
                         "y":  177,
                         "w":  162,
                         "fmt":  "",
                         "name":  "",
                         "h":  63,
                         "color":  "189",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  77,
                         "type":  "label",
                         "var":  "",
                         "y":  100,
                         "w":  138,
                         "fmt":  "",
                         "name":  "",
                         "h":  22,
                         "color":  "189",
                         "text":  "Discounted price",
                         "parent":  2
                     },
                     {
                         "x":  77,
                         "type":  "label",
                         "var":  "",
                         "y":  185,
                         "w":  138,
                         "fmt":  "",
                         "name":  "",
                         "h":  14,
                         "color":  "189",
                         "text":  "Discount %",
                         "parent":  3
                     },
                     {
                         "x":  662,
                         "type":  "label",
                         "var":  "",
                         "y":  51,
                         "w":  228,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "Reason",
                         "parent":  null
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  1118,
                         "fmt":  "",
                         "name":  "",
                         "h":  42,
                         "color":  "182",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  658,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "110",
                         "w":  342,
                         "y":  63,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  24,
                         "h":  193,
                         "cols":  [
                                      {
                                          "title":  "",
                                          "layer":  1,
                                          "w":  336
                                      }
                                  ],
                         "rows":  1
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  267,
                         "w":  1120,
                         "fmt":  "",
                         "name":  "",
                         "h":  37,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  22,
                         "type":  "label",
                         "var":  "",
                         "y":  280,
                         "w":  88,
                         "fmt":  "",
                         "name":  "",
                         "h":  11,
                         "color":  "110",
                         "text":  "Comment :",
                         "parent":  30
                     },
                     {
                         "x":  28,
                         "type":  "tab",
                         "var":  "",
                         "y":  50,
                         "w":  582,
                         "fmt":  "",
                         "name":  "V Tab",
                         "h":  208,
                         "color":  "62",
                         "text":  "%,Price",
                         "parent":  null
                     },
                     {
                         "x":  77,
                         "type":  "edit",
                         "var":  "",
                         "y":  126,
                         "w":  140,
                         "fmt":  "",
                         "name":  "V Chaine disc price",
                         "h":  19,
                         "color":  "110",
                         "text":  "",
                         "parent":  2
                     },
                     {
                         "x":  112,
                         "type":  "edit",
                         "var":  "",
                         "y":  279,
                         "w":  647,
                         "fmt":  "",
                         "name":  "Comment",
                         "h":  12,
                         "color":  "110",
                         "text":  "",
                         "parent":  30
                     },
                     {
                         "x":  717,
                         "type":  "edit",
                         "var":  "",
                         "y":  65,
                         "w":  274,
                         "fmt":  "",
                         "name":  "CTRL_001",
                         "h":  21,
                         "color":  "110",
                         "text":  "",
                         "parent":  25
                     },
                     {
                         "x":  1020,
                         "type":  "image",
                         "var":  "",
                         "y":  4,
                         "w":  96,
                         "fmt":  "",
                         "name":  "",
                         "h":  37,
                         "color":  "",
                         "text":  "",
                         "parent":  24
                     },
                     {
                         "x":  22,
                         "type":  "edit",
                         "var":  "",
                         "y":  14,
                         "w":  956,
                         "fmt":  "100",
                         "name":  "",
                         "h":  10,
                         "color":  "186",
                         "text":  "",
                         "parent":  22
                     },
                     {
                         "x":  76,
                         "type":  "edit",
                         "var":  "",
                         "y":  206,
                         "w":  140,
                         "fmt":  "N3.2",
                         "name":  "",
                         "h":  19,
                         "color":  "186",
                         "text":  "",
                         "parent":  19
                     },
                     {
                         "x":  1000,
                         "type":  "button",
                         "var":  "",
                         "y":  64,
                         "w":  88,
                         "fmt":  "ñ",
                         "name":  "",
                         "h":  98,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  264,
                         "type":  "button",
                         "var":  "",
                         "y":  79,
                         "w":  106,
                         "fmt":  "1",
                         "name":  "*1",
                         "h":  42,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  368,
                         "type":  "button",
                         "var":  "",
                         "y":  79,
                         "w":  106,
                         "fmt":  "2",
                         "name":  "*2",
                         "h":  42,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  472,
                         "type":  "button",
                         "var":  "",
                         "y":  79,
                         "w":  106,
                         "fmt":  "3",
                         "name":  "*3",
                         "h":  42,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  264,
                         "type":  "button",
                         "var":  "",
                         "y":  121,
                         "w":  106,
                         "fmt":  "4",
                         "name":  "*4",
                         "h":  42,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  368,
                         "type":  "button",
                         "var":  "",
                         "y":  121,
                         "w":  106,
                         "fmt":  "5",
                         "name":  "*5",
                         "h":  42,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  472,
                         "type":  "button",
                         "var":  "",
                         "y":  121,
                         "w":  106,
                         "fmt":  "6",
                         "name":  "*6",
                         "h":  42,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  264,
                         "type":  "button",
                         "var":  "",
                         "y":  163,
                         "w":  106,
                         "fmt":  "7",
                         "name":  "*7",
                         "h":  42,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  368,
                         "type":  "button",
                         "var":  "",
                         "y":  163,
                         "w":  106,
                         "fmt":  "8",
                         "name":  "*8",
                         "h":  42,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  472,
                         "type":  "button",
                         "var":  "",
                         "y":  163,
                         "w":  106,
                         "fmt":  "9",
                         "name":  "*9",
                         "h":  42,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  1000,
                         "type":  "button",
                         "var":  "",
                         "y":  161,
                         "w":  88,
                         "fmt":  "ò",
                         "name":  "",
                         "h":  95,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  264,
                         "type":  "button",
                         "var":  "",
                         "y":  205,
                         "w":  106,
                         "fmt":  "Clear",
                         "name":  "+CLEAR",
                         "h":  42,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  368,
                         "type":  "button",
                         "var":  "",
                         "y":  205,
                         "w":  106,
                         "fmt":  "0",
                         "name":  "*0",
                         "h":  42,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  472,
                         "type":  "button",
                         "var":  "",
                         "y":  205,
                         "w":  106,
                         "fmt":  "Del",
                         "name":  "+BACKSPACE",
                         "h":  42,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  884,
                         "type":  "button",
                         "var":  "",
                         "y":  272,
                         "w":  116,
                         "fmt":  "\u0026Cancel",
                         "name":  "B.Cancel",
                         "h":  28,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  768,
                         "type":  "button",
                         "var":  "",
                         "y":  272,
                         "w":  116,
                         "fmt":  "\u0026Keyboard",
                         "name":  "KEYBOARD",
                         "h":  28,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  1000,
                         "type":  "button",
                         "var":  "",
                         "y":  272,
                         "w":  116,
                         "fmt":  "\u0026Select",
                         "name":  "",
                         "h":  28,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  42,
                         "type":  "subform",
                         "var":  "",
                         "y":  76,
                         "w":  547,
                         "fmt":  "",
                         "name":  "Choix - Discounts",
                         "h":  177,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     }
                 ],
    "taskId":  "201",
    "height":  310
}
-->

<details>
<summary><strong>Champs : 5 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 77,126 | V Chaine disc price | - | edit |
| 112,279 | Comment | - | edit |
| 717,65 | CTRL_001 | - | edit |
| 22,14 | 100 | - | edit |
| 76,206 | N3.2 | - | edit |

</details>

<details>
<summary><strong>Boutons : 17 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| ñ | 1000,64 | Bouton fonctionnel |
| 1 | 264,79 | Bouton fonctionnel |
| 2 | 368,79 | Bouton fonctionnel |
| 3 | 472,79 | Bouton fonctionnel |
| 4 | 264,121 | Bouton fonctionnel |
| 5 | 368,121 | Bouton fonctionnel |
| 6 | 472,121 | Bouton fonctionnel |
| 7 | 264,163 | Bouton fonctionnel |
| 8 | 368,163 | Bouton fonctionnel |
| 9 | 472,163 | Bouton fonctionnel |
| ò | 1000,161 | Bouton fonctionnel |
| Clear | 264,205 | Bouton fonctionnel |
| 0 | 368,205 | Bouton fonctionnel |
| Del | 472,205 | Bouton fonctionnel |
| Cancel | 884,272 | Annule et retour au menu |
| Keyboard | 768,272 | Bouton fonctionnel |
| Select | 1000,272 | Ouvre la selection |

</details>

---

#### <a id="ecran-t2"></a>201.1 - Discounts list
**Tache** : [201.1](#t2) | **Type** : Type6 | **Dimensions** : 245 x 161 DLU
**Bloc** : Traitement | **Titre IDE** : Discounts list

<!-- FORM-DATA:
{
    "width":  245,
    "vFactor":  8,
    "type":  "Type6",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  6,
                         "type":  "label",
                         "var":  "",
                         "y":  1,
                         "w":  53,
                         "fmt":  "",
                         "name":  "",
                         "h":  13,
                         "color":  "183",
                         "text":  "%",
                         "parent":  null
                     },
                     {
                         "x":  72,
                         "type":  "label",
                         "var":  "",
                         "y":  1,
                         "w":  96,
                         "fmt":  "",
                         "name":  "",
                         "h":  13,
                         "color":  "183",
                         "text":  "Description",
                         "parent":  null
                     },
                     {
                         "x":  1,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "110",
                         "w":  198,
                         "y":  15,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  28,
                         "h":  143,
                         "cols":  [
                                      {
                                          "title":  "",
                                          "layer":  1,
                                          "w":  65
                                      },
                                      {
                                          "title":  "",
                                          "layer":  2,
                                          "w":  128
                                      }
                                  ],
                         "rows":  2
                     },
                     {
                         "x":  6,
                         "type":  "edit",
                         "var":  "",
                         "y":  17,
                         "w":  52,
                         "fmt":  "#2",
                         "name":  "",
                         "h":  24,
                         "color":  "110",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  71,
                         "type":  "edit",
                         "var":  "",
                         "y":  18,
                         "w":  120,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "110",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  199,
                         "type":  "button",
                         "var":  "",
                         "y":  15,
                         "w":  44,
                         "fmt":  "ñ",
                         "name":  "",
                         "h":  72,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  199,
                         "type":  "button",
                         "var":  "",
                         "y":  87,
                         "w":  44,
                         "fmt":  "ò",
                         "name":  "",
                         "h":  72,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "201.1",
    "height":  161
}
-->

<details>
<summary><strong>Champs : 2 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 6,17 | #2 | - | edit |
| 71,18 | (sans nom) | - | edit |

</details>

<details>
<summary><strong>Boutons : 2 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| ñ | 199,15 | Bouton fonctionnel |
| ò | 199,87 | Bouton fonctionnel |

</details>

## 9. NAVIGATION

### 9.1 Enchainement des ecrans

```mermaid
flowchart TD
    START([Entree])
    style START fill:#3fb950
    VF1[201 Discount]
    style VF1 fill:#58a6ff
    VF2[201.1 Discounts list]
    style VF2 fill:#58a6ff
    EXT317[IDE 317 Lancement clavier]
    style EXT317 fill:#3fb950
    FIN([Sortie])
    style FIN fill:#f85149
    START --> VF1
    VF1 -->|Sous-programme| EXT317
    EXT317 --> FIN
```

**Detail par enchainement :**

| Depuis | Action | Vers | Retour |
|--------|--------|------|--------|
| Discount | Sous-programme | [Lancement clavier (IDE 317)](PVE-IDE-317.md) | Retour ecran |

### 9.3 Structure hierarchique (4 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **201.1** | [**Discount** (201)](#t1) [mockup](#ecran-t1) | Type6 | 1138x310 | Traitement |
| 201.1.1 | [Discounts list (201.1)](#t2) [mockup](#ecran-t2) | Type6 | 245x161 | |
| 201.1.2 | [Keyboard (201.2)](#t3) [mockup](#ecran-t3) | MDI | 199x80 | |
| 201.1.3 | [(sans nom) (201.3)](#t7) | - | - | |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Choix - Discounts]
    UPDATE[MAJ 1 tables]
    ENDOK([END OK])

    START --> INIT --> SAISIE
    SAISIE --> UPDATE --> ENDOK

    style START fill:#3fb950,color:#000
    style ENDOK fill:#3fb950,color:#000
```

> **Legende**: Vert = START/END OK | Rouge = END KO | Bleu = Decisions
> *Algorigramme auto-genere. Utiliser `/algorigramme` pour une synthese metier detaillee.*

<!-- TAB:Donnees -->

## 10. TABLES

### Tables utilisees (2)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 386 | ski_frame |  | DB | R |   |   | 1 |
| 387 | pv_height |  | DB |   | **W** | L | 2 |

### Colonnes par table (2 / 2 tables avec colonnes identifiees)

<details>
<summary>Table 386 - ski_frame (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P. Discount | R | Numeric |
| B | P. Reason | R | Numeric |
| C | P. Price | R | Numeric |
| D | P. Label | R | Alpha |
| E | P. Comment | R | Alpha |
| F | P Remise Great Members | R | Logical |
| G | P. Prix net saisi | R | Numeric |
| H | V Chaine % | R | Alpha |
| I | T Discount | R | Logical |
| J | V Chaine disc price | R | Alpha |
| K | V Comment | R | Alpha |
| L | V Tab | R | Alpha |
| M | V.Echap | R | Logical |

</details>

<details>
<summary>Table 387 - pv_height (**W**/L) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P. Discount | W | Alpha |
| B | P.Remise Great Members | W | Logical |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (7)

Variables recues du programme appelant ([Main Sale (IDE 186)](PVE-IDE-186.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P. Discount | Numeric | [201](#t1), [201.1](#t2) |
| B | P. Reason | Numeric | 1x parametre entrant |
| C | P. Price | Numeric | 5x parametre entrant |
| D | P. Label | Alpha | - |
| E | P. Comment | Alpha | 1x parametre entrant |
| F | P Remise Great Members | Logical | - |
| G | P. Prix net saisi | Numeric | - |

### 11.2 Variables de session (5)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| H | V Chaine % | Alpha | 5x session |
| J | V Chaine disc price | Alpha | - |
| K | V Comment | Alpha | - |
| L | V Tab | Alpha | 4x session |
| M | V.Echap | Logical | 2x session |

### 11.3 Autres (1)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| I | T Discount | Logical | - |

## 12. EXPRESSIONS

**35 / 35 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCUL | 3 | 5 |
| CONDITION | 16 | 5 |
| CAST_LOGIQUE | 3 | 2 |
| CONSTANTE | 5 | 0 |
| OTHER | 6 | 0 |
| STRING | 2 | 0 |

### 12.2 Expressions cles par type

#### CALCUL (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCUL | 4 | `IF (Val (V Tab [L],'')<>0,100*(1-Val (V Tab [L],'10')/P. Price [C]),0)` | [RM-001](#rm-RM-001) |
| CALCUL | 30 | `IF (Val (V Tab [L],'')<>0,Val (V Tab [L],'10.2'),P. Price [C]*(1-P. Discount [A]/100))` | - |
| CALCUL | 5 | `100-100*Val (V Tab [L],'')/P. Price [C]` | - |

#### CONDITION (16 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 6 | `IF (P. Discount [A]=0,0,[O])` | [RM-002](#rm-RM-002) |
| CONDITION | 29 | `P. Discount [A]<>100` | - |
| CONDITION | 24 | `VG33='TB'` | - |
| CONDITION | 23 | `VG33<>'TB'` | - |
| CONDITION | 33 | `P. Discount [A]=100` | - |
| ... | | *+11 autres* | |

#### CAST_LOGIQUE (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 34 | `IF(GetParam('HARMONYDISC'),[T]='TRUE'LOG,'TRUE'LOG)` | [RM-004](#rm-RM-004) |
| CAST_LOGIQUE | 19 | `IF(P. Discount [A]<>100,'Select the discount %'&IF (GetParam ('RENTAL')='TRUE'LOG,' or the discounted price','')&' and justify it with a reason from the list','justify discount with a reason from the list')` | [RM-003](#rm-RM-003) |
| CAST_LOGIQUE | 28 | `'TRUE'LOG` | - |

#### CONSTANTE (5 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 27 | `''` | - |
| CONSTANTE | 32 | `0` | - |
| CONSTANTE | 26 | `0` | - |
| CONSTANTE | 10 | `'%'` | - |
| CONSTANTE | 16 | `''` | - |

#### OTHER (6 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 11 | `P. Comment [E]` | - |
| OTHER | 25 | `CtrlGoto('Comment',0,0)` | - |
| OTHER | 31 | `P. Price [C]` | - |
| OTHER | 1 | `GetParam ('SERVICE')` | - |
| OTHER | 7 | `[P]` | - |
| ... | | *+1 autres* | |

#### STRING (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| STRING | 3 | `Val (V Chaine % [H],'3')` | - |
| STRING | 2 | `Trim (Str (P. Discount [A],'3'))` | - |

### 12.3 Toutes les expressions (35)

<details>
<summary>Voir les 35 expressions</summary>

#### CALCUL (3)

| IDE | Expression Decodee |
|-----|-------------------|
| 5 | `100-100*Val (V Tab [L],'')/P. Price [C]` |
| 4 | `IF (Val (V Tab [L],'')<>0,100*(1-Val (V Tab [L],'10')/P. Price [C]),0)` |
| 30 | `IF (Val (V Tab [L],'')<>0,Val (V Tab [L],'10.2'),P. Price [C]*(1-P. Discount [A]/100))` |

#### CONDITION (16)

| IDE | Expression Decodee |
|-----|-------------------|
| 6 | `IF (P. Discount [A]=0,0,[O])` |
| 9 | `CndRange (P. Reason [B]<>0,P. Reason [B])` |
| 12 | `[Q]='%'` |
| 13 | `[Q]='P'` |
| 14 | `P. Discount [A]<>100` |
| 15 | `P. Discount [A]<>100 AND V Chaine % [H]='100'` |
| 20 | `[Q]='P'` |
| 21 | `V Chaine % [H]='100'` |
| 22 | `V Chaine % [H]<>'100'` |
| 23 | `VG33<>'TB'` |
| 24 | `VG33='TB'` |
| 29 | `P. Discount [A]<>100` |
| 33 | `P. Discount [A]=100` |
| 17 | `Val (V Chaine % [H],'3')>100` |
| 18 | `Val (V Tab [L],'')>=P. Price [C]` |
| 35 | `GetParam('HARMONYDISC') AND [S] AND Trim(V.Echap [M])=''` |

#### CAST_LOGIQUE (3)

| IDE | Expression Decodee |
|-----|-------------------|
| 19 | `IF(P. Discount [A]<>100,'Select the discount %'&IF (GetParam ('RENTAL')='TRUE'LOG,' or the discounted price','')&' and justify it with a reason from the list','justify discount with a reason from the list')` |
| 34 | `IF(GetParam('HARMONYDISC'),[T]='TRUE'LOG,'TRUE'LOG)` |
| 28 | `'TRUE'LOG` |

#### CONSTANTE (5)

| IDE | Expression Decodee |
|-----|-------------------|
| 10 | `'%'` |
| 16 | `''` |
| 26 | `0` |
| 27 | `''` |
| 32 | `0` |

#### OTHER (6)

| IDE | Expression Decodee |
|-----|-------------------|
| 1 | `GetParam ('SERVICE')` |
| 7 | `[P]` |
| 8 | `V.Echap [M]` |
| 11 | `P. Comment [E]` |
| 25 | `CtrlGoto('Comment',0,0)` |
| 31 | `P. Price [C]` |

#### STRING (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 2 | `Trim (Str (P. Discount [A],'3'))` |
| 3 | `Val (V Chaine % [H],'3')` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Main Sale (IDE 186)](PVE-IDE-186.md) -> **Discounts (IDE 201)**

Main -> ... -> [Main Sale-664 (IDE 187)](PVE-IDE-187.md) -> **Discounts (IDE 201)**

Main -> ... -> [Main Sale Sale Bar Code (IDE 214)](PVE-IDE-214.md) -> **Discounts (IDE 201)**

Main -> ... -> [Main Sale (IDE 363)](PVE-IDE-363.md) -> **Discounts (IDE 201)**

Main -> ... -> [Main Sale-664 (IDE 364)](PVE-IDE-364.md) -> **Discounts (IDE 201)**

```mermaid
graph LR
    T201[201 Discounts]
    style T201 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC143[143 START]
    style CC143 fill:#f59e0b
    CC185[185 Menu]
    style CC185 fill:#f59e0b
    CC186[186 Main Sale]
    style CC186 fill:#3fb950
    CC364[364 Main Sale-664]
    style CC364 fill:#3fb950
    CC187[187 Main Sale-664]
    style CC187 fill:#3fb950
    CC214[214 Main Sale Sale Bar...]
    style CC214 fill:#3fb950
    CC363[363 Main Sale]
    style CC363 fill:#3fb950
    CC185 --> CC186
    CC185 --> CC187
    CC185 --> CC214
    CC185 --> CC363
    CC185 --> CC364
    CC143 --> CC185
    CC1 --> CC143
    CC186 --> T201
    CC187 --> T201
    CC214 --> T201
    CC363 --> T201
    CC364 --> T201
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [186](PVE-IDE-186.md) | Main Sale | 2 |
| [187](PVE-IDE-187.md) | Main Sale-664 | 2 |
| [214](PVE-IDE-214.md) | Main Sale Sale Bar Code | 2 |
| [363](PVE-IDE-363.md) | Main Sale | 2 |
| [364](PVE-IDE-364.md) | Main Sale-664 | 2 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T201[201 Discounts]
    style T201 fill:#58a6ff
    C317[317 Lancement clavier]
    T201 --> C317
    style C317 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [317](PVE-IDE-317.md) | Lancement clavier | 1 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 112 | Programme compact |
| Expressions | 35 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 1 | Peu de dependances |
| Ecrans visibles | 2 | Quelques ecrans |
| Code desactive | 0% (0 / 112) | Code sain |
| Regles metier | 4 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (4 taches: 3 ecrans, 1 traitement)

- **Strategie** : Orchestrateur avec 3 ecrans (Razor/React) et 1 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 1 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| pv_height | Table WRITE (Database) | 1x | Schema + repository |
| [Lancement clavier (IDE 317)](PVE-IDE-317.md) | Sous-programme | 1x | Normale - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 18:52*
