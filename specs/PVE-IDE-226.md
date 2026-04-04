# PVE IDE 226 - Discounts

> **Analyse**: Phases 1-4 2026-02-03 19:02 -> 19:02 (17s) | Assemblage 19:02
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PVE |
| IDE Position | 226 |
| Nom Programme | Discounts |
| Fichier source | `Prg_226.xml` |
| Dossier IDE | Packages |
| Taches | 2 (1 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 2 |

## 2. DESCRIPTION FONCTIONNELLE

**Discounts** assure la gestion complete de ce processus, accessible depuis [Menu Main (TPE) (IDE 403)](PVE-IDE-403.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (2 taches) : traitements metier divers

**Logique metier** : 3 regles identifiees couvrant conditions metier.

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (2 taches)

Traitements internes.

---

#### <a id="t1"></a>226 - Discount [[ECRAN]](#ecran-t1)

**Role** : Traitement : Discount.
**Ecran** : 1138 x 310 DLU (Type6) | [Voir mockup](#ecran-t1)
**Variables liees** : A (P. Discount), H (T Discount)
**Delegue a** : [Choix - Discounts (IDE 266)](PVE-IDE-266.md), [Lancement clavier (IDE 317)](PVE-IDE-317.md)

---

#### <a id="t2"></a>226.1 - Keyboard [[ECRAN]](#ecran-t2)

**Role** : Traitement : Keyboard.
**Ecran** : 199 x 80 DLU (MDI) | [Voir mockup](#ecran-t2)
**Delegue a** : [Lancement clavier (IDE 317)](PVE-IDE-317.md)


## 5. REGLES METIER

3 regles identifiees:

### Autres (3 regles)

#### <a id="rm-RM-001"></a>[RM-001] Traitement si Val (V Tab [K],'') est non nul

| Element | Detail |
|---------|--------|
| **Condition** | `Val (V Tab [K]` |
| **Si vrai** | '')<>0 |
| **Si faux** | 100*(1-Val (V Tab [K],'10')/P. Price [C]),0) |
| **Variables** | C (P. Price), K (V Tab) |
| **Expression source** | Expression 4 : `IF (Val (V Tab [K],'')<>0,100*(1-Val (V Tab [K],'10')/P. Pri` |
| **Exemple** | Si Val (V Tab [K] â†’ '')<>0. Sinon â†’ 100*(1-Val (V Tab [K],'10')/P. Price [C]),0) |

#### <a id="rm-RM-002"></a>[RM-002] Traitement conditionnel si P. Discount [A] est a zero

| Element | Detail |
|---------|--------|
| **Condition** | `P. Discount [A]=0` |
| **Si vrai** | 0 |
| **Si faux** | [N]) |
| **Variables** | A (P. Discount) |
| **Expression source** | Expression 6 : `IF (P. Discount [A]=0,0,[N])` |
| **Exemple** | Si P. Discount [A]=0 â†’ 0. Sinon â†’ [N]) |
| **Impact** | [226 - Discount](#t1) |

#### <a id="rm-RM-003"></a>[RM-003] Condition toujours vraie (flag actif)

| Element | Detail |
|---------|--------|
| **Condition** | `P. Discount [A]<>100` |
| **Si vrai** | 'Select the discount %'&IF (GetParam ('RENTAL')='TRUE'LOG |
| **Si faux** | ' or the discounted price','')&' and justify it with a reason from the list','justify discount with a reason from the list') |
| **Variables** | A (P. Discount) |
| **Expression source** | Expression 22 : `IF(P. Discount [A]<>100,'Select the discount %'&IF (GetParam` |
| **Exemple** | Si P. Discount [A]<>100 â†’ 'Select the discount %'&IF (GetParam ('RENTAL')='TRUE'LOG |
| **Impact** | [226 - Discount](#t1) |

## 6. CONTEXTE

- **Appele par**: [Menu Main (TPE) (IDE 403)](PVE-IDE-403.md)
- **Appelle**: 2 programmes | **Tables**: 2 (W:0 R:1 L:1) | **Taches**: 2 | **Expressions**: 29

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 2)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 226 | 226 | Discount | Type6 | 1138 | 310 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>226 - Discount
**Tache** : [226](#t1) | **Type** : Type6 | **Dimensions** : 1138 x 310 DLU
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
                         "x":  66,
                         "type":  "label",
                         "var":  "",
                         "y":  131,
                         "w":  162,
                         "fmt":  "",
                         "name":  "",
                         "h":  63,
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
                         "x":  78,
                         "type":  "label",
                         "var":  "",
                         "y":  139,
                         "w":  138,
                         "fmt":  "",
                         "name":  "",
                         "h":  14,
                         "color":  "189",
                         "text":  "Discount %",
                         "parent":  3
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
                         "parent":  4
                     },
                     {
                         "x":  662,
                         "type":  "label",
                         "var":  "",
                         "y":  55,
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
                         "y":  67,
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
                         "x":  664,
                         "type":  "label",
                         "var":  "",
                         "y":  69,
                         "w":  32,
                         "fmt":  "",
                         "name":  "",
                         "h":  21,
                         "color":  "144",
                         "text":  "Ø",
                         "parent":  27
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
                         "parent":  33
                     },
                     {
                         "x":  110,
                         "type":  "edit",
                         "var":  "",
                         "y":  160,
                         "w":  68,
                         "fmt":  "#3",
                         "name":  "V Chaine %",
                         "h":  19,
                         "color":  "110",
                         "text":  "",
                         "parent":  19
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
                         "parent":  33
                     },
                     {
                         "x":  716,
                         "type":  "edit",
                         "var":  "",
                         "y":  69,
                         "w":  274,
                         "fmt":  "",
                         "name":  "CTRL_001",
                         "h":  21,
                         "color":  "110",
                         "text":  "",
                         "parent":  27
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
                         "parent":  26
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
                         "parent":  24
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
                         "parent":  21
                     },
                     {
                         "x":  1000,
                         "type":  "button",
                         "var":  "",
                         "y":  68,
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
                         "y":  165,
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
                         "name":  "",
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
                         "fmt":  "\u0026Kbd",
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
                     }
                 ],
    "taskId":  "226",
    "height":  310
}
-->

<details>
<summary><strong>Champs : 6 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 110,160 | V Chaine % | - | edit |
| 77,126 | V Chaine disc price | - | edit |
| 112,279 | Comment | - | edit |
| 716,69 | CTRL_001 | - | edit |
| 22,14 | 100 | - | edit |
| 76,206 | N3.2 | - | edit |

</details>

<details>
<summary><strong>Boutons : 17 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| ñ | 1000,68 | Bouton fonctionnel |
| 1 | 264,79 | Bouton fonctionnel |
| 2 | 368,79 | Bouton fonctionnel |
| 3 | 472,79 | Bouton fonctionnel |
| 4 | 264,121 | Bouton fonctionnel |
| 5 | 368,121 | Bouton fonctionnel |
| 6 | 472,121 | Bouton fonctionnel |
| 7 | 264,163 | Bouton fonctionnel |
| 8 | 368,163 | Bouton fonctionnel |
| 9 | 472,163 | Bouton fonctionnel |
| ò | 1000,165 | Bouton fonctionnel |
| Clear | 264,205 | Bouton fonctionnel |
| 0 | 368,205 | Bouton fonctionnel |
| Del | 472,205 | Bouton fonctionnel |
| Cancel | 884,272 | Annule et retour au menu |
| Kbd | 768,272 | Bouton fonctionnel |
| Select | 1000,272 | Ouvre la selection |

</details>

## 9. NAVIGATION

Ecran unique: **Discount**

### 9.3 Structure hierarchique (2 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **226.1** | [**Discount** (226)](#t1) [mockup](#ecran-t1) | Type6 | 1138x310 | Traitement |
| 226.1.1 | [Keyboard (226.1)](#t2) [mockup](#ecran-t2) | MDI | 199x80 | |

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

### Tables utilisees (2)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 386 | ski_frame |  | DB | R |   |   | 1 |
| 387 | pv_height |  | DB |   |   | L | 1 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

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
| G | V Chaine % | R | Alpha |
| H | T Discount | R | Logical |
| I | V Chaine disc price | R | Alpha |
| J | V Comment | R | Alpha |
| K | V Tab | R | Alpha |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (6)

Variables recues du programme appelant ([Menu Main (TPE) (IDE 403)](PVE-IDE-403.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P. Discount | Numeric | [226](#t1) |
| B | P. Reason | Numeric | 2x parametre entrant |
| C | P. Price | Numeric | 3x parametre entrant |
| D | P. Label | Alpha | - |
| E | P. Comment | Alpha | 1x parametre entrant |
| F | P Remise Great Members | Logical | - |

### 11.2 Variables de session (4)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| G | V Chaine % | Alpha | 7x session |
| I | V Chaine disc price | Alpha | - |
| J | V Comment | Alpha | - |
| K | V Tab | Alpha | 3x session |

### 11.3 Autres (1)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| H | T Discount | Logical | - |

## 12. EXPRESSIONS

**29 / 29 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCUL | 2 | 5 |
| CONDITION | 15 | 5 |
| CAST_LOGIQUE | 2 | 5 |
| CONSTANTE | 3 | 0 |
| OTHER | 5 | 0 |
| STRING | 2 | 0 |

### 12.2 Expressions cles par type

#### CALCUL (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCUL | 4 | `IF (Val (V Tab [K],'')<>0,100*(1-Val (V Tab [K],'10')/P. Price [C]),0)` | [RM-001](#rm-RM-001) |
| CALCUL | 5 | `100-100*Val (V Tab [K],'')/P. Price [C]` | - |

#### CONDITION (15 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 6 | `IF (P. Discount [A]=0,0,[N])` | [RM-002](#rm-RM-002) |
| CONDITION | 26 | `V Chaine % [G]='100' AND [L]=''` | - |
| CONDITION | 25 | `V Chaine % [G]<>'100'` | - |
| CONDITION | 24 | `V Chaine % [G]='100'` | - |
| CONDITION | 27 | `VG33<>'TB'` | - |
| ... | | *+10 autres* | |

#### CAST_LOGIQUE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 22 | `IF(P. Discount [A]<>100,'Select the discount %'&IF (GetParam ('RENTAL')='TRUE'LOG,' or the discounted price','')&' and justify it with a reason from the list','justify discount with a reason from the list')` | [RM-003](#rm-RM-003) |
| CAST_LOGIQUE | 23 | `GetParam ('RENTAL')='TRUE'LOG AND [P]='P'` | - |

#### CONSTANTE (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 21 | `'%,Price'` | - |
| CONSTANTE | 17 | `''` | - |
| CONSTANTE | 11 | `'%'` | - |

#### OTHER (5 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 12 | `P. Comment [E]` | - |
| OTHER | 29 | `CtrlGoto('Comment',0,0)` | - |
| OTHER | 8 | `[L]` | - |
| OTHER | 1 | `GetParam ('SERVICE')` | - |
| OTHER | 7 | `[O]` | - |

#### STRING (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| STRING | 3 | `Val (V Chaine % [G],'3')` | - |
| STRING | 2 | `Trim (Str (P. Discount [A],'3'))` | - |

### 12.3 Toutes les expressions (29)

<details>
<summary>Voir les 29 expressions</summary>

#### CALCUL (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 5 | `100-100*Val (V Tab [K],'')/P. Price [C]` |
| 4 | `IF (Val (V Tab [K],'')<>0,100*(1-Val (V Tab [K],'10')/P. Price [C]),0)` |

#### CONDITION (15)

| IDE | Expression Decodee |
|-----|-------------------|
| 6 | `IF (P. Discount [A]=0,0,[N])` |
| 9 | `CndRange (P. Reason [B]<>0,P. Reason [B])` |
| 10 | `P. Reason [B]=[N]` |
| 13 | `[P]='%'` |
| 14 | `[P]='P'` |
| 15 | `P. Discount [A]<>100` |
| 16 | `P. Discount [A]<>100 AND V Chaine % [G]='100'` |
| 20 | `V Chaine % [G]='100' AND [L]=''` |
| 24 | `V Chaine % [G]='100'` |
| 25 | `V Chaine % [G]<>'100'` |
| 26 | `V Chaine % [G]='100' AND [L]=''` |
| 27 | `VG33<>'TB'` |
| 28 | `VG33='TB'` |
| 18 | `Val (V Chaine % [G],'3')>100` |
| 19 | `Val (V Tab [K],'')>=P. Price [C]` |

#### CAST_LOGIQUE (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 22 | `IF(P. Discount [A]<>100,'Select the discount %'&IF (GetParam ('RENTAL')='TRUE'LOG,' or the discounted price','')&' and justify it with a reason from the list','justify discount with a reason from the list')` |
| 23 | `GetParam ('RENTAL')='TRUE'LOG AND [P]='P'` |

#### CONSTANTE (3)

| IDE | Expression Decodee |
|-----|-------------------|
| 11 | `'%'` |
| 17 | `''` |
| 21 | `'%,Price'` |

#### OTHER (5)

| IDE | Expression Decodee |
|-----|-------------------|
| 1 | `GetParam ('SERVICE')` |
| 7 | `[O]` |
| 8 | `[L]` |
| 12 | `P. Comment [E]` |
| 29 | `CtrlGoto('Comment',0,0)` |

#### STRING (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 2 | `Trim (Str (P. Discount [A],'3'))` |
| 3 | `Val (V Chaine % [G],'3')` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Menu Main (TPE) (IDE 403)](PVE-IDE-403.md) -> **Discounts (IDE 226)**

```mermaid
graph LR
    T226[226 Discounts]
    style T226 fill:#58a6ff
    CC403[403 Menu Main TPE]
    style CC403 fill:#8b5cf6
    CC403 --> T226
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [403](PVE-IDE-403.md) | Menu Main (TPE) | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T226[226 Discounts]
    style T226 fill:#58a6ff
    C266[266 Choix - Discounts]
    T226 --> C266
    style C266 fill:#3fb950
    C317[317 Lancement clavier]
    T226 --> C317
    style C317 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [266](PVE-IDE-266.md) | Choix - Discounts | 2 | Selection/consultation |
| [317](PVE-IDE-317.md) | Lancement clavier | 1 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 99 | Programme compact |
| Expressions | 29 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 2 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 10.1% (10 / 99) | A verifier |
| Regles metier | 3 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (2 taches: 2 ecrans, 0 traitement)

- **Strategie** : 2 composant(s) UI (Razor/React) avec formulaires et validation.
- 2 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| [Choix - Discounts (IDE 266)](PVE-IDE-266.md) | Sous-programme | 2x | Haute - Selection/consultation |
| [Lancement clavier (IDE 317)](PVE-IDE-317.md) | Sous-programme | 1x | Normale - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 19:02*
