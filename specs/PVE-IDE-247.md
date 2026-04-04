# PVE IDE 247 - Choix - Classification

> **Analyse**: Phases 1-4 2026-02-03 19:11 -> 19:11 (16s) | Assemblage 19:11
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PVE |
| IDE Position | 247 |
| Nom Programme | Choix - Classification |
| Fichier source | `Prg_247.xml` |
| Dossier IDE | Tables |
| Taches | 1 (1 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 2 |

## 2. DESCRIPTION FONCTIONNELLE

**Choix - Classification** assure la gestion complete de ce processus, accessible depuis [Menu Equipment inventory (IDE 184)](PVE-IDE-184.md), [Package setup (IDE 220)](PVE-IDE-220.md), [Package setup (IDE 367)](PVE-IDE-367.md), [Menu Equipment inventory (IDE 411)](PVE-IDE-411.md), [Label Management (IDE 105)](PVE-IDE-105.md), [Menu Administration (IDE 178)](PVE-IDE-178.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>247 - Equipment classification list [[ECRAN]](#ecran-t1)

**Role** : Traitement : Equipment classification list.
**Ecran** : 542 x 308 DLU (MDI) | [Voir mockup](#ecran-t1)
**Variables liees** : D (v.retour equipment)
**Delegue a** : [Choix - Equipment type (IDE 271)](PVE-IDE-271.md), [Action Cancel Query (IDE 302)](PVE-IDE-302.md)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Menu Equipment inventory (IDE 184)](PVE-IDE-184.md), [Package setup (IDE 220)](PVE-IDE-220.md), [Package setup (IDE 367)](PVE-IDE-367.md), [Menu Equipment inventory (IDE 411)](PVE-IDE-411.md), [Label Management (IDE 105)](PVE-IDE-105.md), [Menu Administration (IDE 178)](PVE-IDE-178.md)
- **Appelle**: 2 programmes | **Tables**: 3 (W:0 R:1 L:2) | **Taches**: 1 | **Expressions**: 10

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 1)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 247 | 247 | Equipment classification list | MDI | 542 | 308 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>247 - Equipment classification list
**Tache** : [247](#t1) | **Type** : MDI | **Dimensions** : 542 x 308 DLU
**Bloc** : Traitement | **Titre IDE** : Equipment classification list

<!-- FORM-DATA:
{
    "width":  542,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  74,
                         "type":  "label",
                         "var":  "",
                         "y":  62,
                         "w":  53,
                         "fmt":  "",
                         "name":  "",
                         "h":  13,
                         "color":  "183",
                         "text":  "Code",
                         "parent":  null
                     },
                     {
                         "x":  138,
                         "type":  "label",
                         "var":  "",
                         "y":  62,
                         "w":  96,
                         "fmt":  "",
                         "name":  "",
                         "h":  13,
                         "color":  "183",
                         "text":  "Description",
                         "parent":  null
                     },
                     {
                         "x":  354,
                         "type":  "label",
                         "var":  "",
                         "y":  62,
                         "w":  96,
                         "fmt":  "",
                         "name":  "",
                         "h":  13,
                         "color":  "183",
                         "text":  "Equipement",
                         "parent":  null
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  540,
                         "fmt":  "",
                         "name":  "",
                         "h":  42,
                         "color":  "182",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  20,
                         "type":  "label",
                         "var":  "",
                         "y":  15,
                         "w":  272,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "186",
                         "text":  "Add or select a classification",
                         "parent":  4
                     },
                     {
                         "x":  68,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "110",
                         "w":  352,
                         "y":  76,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  28,
                         "h":  169,
                         "cols":  [
                                      {
                                          "title":  "",
                                          "layer":  1,
                                          "w":  65
                                      },
                                      {
                                          "title":  "",
                                          "layer":  2,
                                          "w":  221
                                      },
                                      {
                                          "title":  "equipement_id",
                                          "layer":  3,
                                          "w":  59
                                      }
                                  ],
                         "rows":  3
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  273,
                         "w":  540,
                         "fmt":  "",
                         "name":  "",
                         "h":  34,
                         "color":  "6",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  75,
                         "type":  "edit",
                         "var":  "",
                         "y":  79,
                         "w":  52,
                         "fmt":  "2P0",
                         "name":  "",
                         "h":  24,
                         "color":  "110",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  139,
                         "type":  "edit",
                         "var":  "",
                         "y":  81,
                         "w":  210,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "110",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  490,
                         "type":  "image",
                         "var":  "",
                         "y":  4,
                         "w":  48,
                         "fmt":  "",
                         "name":  "",
                         "h":  37,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  424,
                         "type":  "button",
                         "var":  "",
                         "y":  77,
                         "w":  44,
                         "fmt":  "ñ",
                         "name":  "",
                         "h":  86,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  424,
                         "type":  "button",
                         "var":  "",
                         "y":  163,
                         "w":  44,
                         "fmt":  "ò",
                         "name":  "",
                         "h":  84,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  1,
                         "type":  "button",
                         "var":  "",
                         "y":  278,
                         "w":  78,
                         "fmt":  "\u0026Modify mode",
                         "name":  "",
                         "h":  28,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  78,
                         "type":  "button",
                         "var":  "",
                         "y":  278,
                         "w":  77,
                         "fmt":  "\u0026Add",
                         "name":  "",
                         "h":  28,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  154,
                         "type":  "button",
                         "var":  "",
                         "y":  278,
                         "w":  77,
                         "fmt":  "\u0026Delete",
                         "name":  "",
                         "h":  28,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  230,
                         "type":  "button",
                         "var":  "",
                         "y":  278,
                         "w":  77,
                         "fmt":  "\u0026Cancel",
                         "name":  "",
                         "h":  28,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  386,
                         "type":  "button",
                         "var":  "",
                         "y":  278,
                         "w":  77,
                         "fmt":  "\u0026Select",
                         "name":  "",
                         "h":  28,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  463,
                         "type":  "button",
                         "var":  "",
                         "y":  278,
                         "w":  77,
                         "fmt":  "\u0026Exit",
                         "name":  "",
                         "h":  28,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  359,
                         "type":  "edit",
                         "var":  "",
                         "y":  81,
                         "w":  52,
                         "fmt":  "2P0",
                         "name":  "equipement_id",
                         "h":  24,
                         "color":  "110",
                         "text":  "",
                         "parent":  7
                     }
                 ],
    "taskId":  "247",
    "height":  308
}
-->

<details>
<summary><strong>Champs : 3 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 75,79 | 2P0 | - | edit |
| 139,81 | (sans nom) | - | edit |
| 359,81 | equipement_id | - | edit |

</details>

<details>
<summary><strong>Boutons : 8 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| ñ | 424,77 | Bouton fonctionnel |
| ò | 424,163 | Bouton fonctionnel |
| Modify mode | 1,278 | Modifie l'element |
| Add | 78,278 | Ajoute un element |
| Delete | 154,278 | Supprime l'element selectionne |
| Cancel | 230,278 | Appel [Action Cancel Query (IDE 302)](PVE-IDE-302.md) |
| Select | 386,278 | Ouvre la selection |
| Exit | 463,278 | Quitte le programme |

</details>

## 9. NAVIGATION

Ecran unique: **Equipment classification list**

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **247.1** | [**Equipment classification list** (247)](#t1) [mockup](#ecran-t1) | MDI | 542x308 | Traitement |

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

### Tables utilisees (3)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 380 | pv_day_modes |  | DB |   |   | L | 1 |
| 389 | pv_equipment_inventory |  | DB |   |   | L | 1 |
| 401 | pv_cust_rentals_histo | Historique / journal | DB | R |   |   | 1 |

### Colonnes par table (2 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 401 - pv_cust_rentals_histo (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | p.classif id | R | Numeric |
| B | p.equipement | R | Numeric |
| C | v.retour package | R | Logical |
| D | v.retour equipment | R | Logical |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (2)

Variables recues du programme appelant ([Menu Equipment inventory (IDE 184)](PVE-IDE-184.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | p.classif id | Numeric | 1x parametre entrant |
| B | p.equipement | Numeric | 1x parametre entrant |

### 11.2 Variables de session (2)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| C | v.retour package | Logical | - |
| D | v.retour equipment | Logical | [247](#t1) |

## 12. EXPRESSIONS

**10 / 10 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| OTHER | 8 | 0 |
| REFERENCE_VG | 1 | 0 |
| CONDITION | 1 | 0 |

### 12.2 Expressions cles par type

#### OTHER (8 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 7 | `Stat (0,'M'MODE) AND NOT ([G]) AND NOT ([J])` | - |
| OTHER | 6 | `Stat (0,'CM'MODE)` | - |
| OTHER | 10 | `Stat(0,'CM'MODE)` | - |
| OTHER | 8 | `GetParam ('SERVICE')` | - |
| OTHER | 2 | `v.retour equipment [D]` | - |
| ... | | *+3 autres* | |

#### REFERENCE_VG (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 3 | `VG9` | - |

#### CONDITION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 9 | `CndRange(p.equipement [B]<>0,p.equipement [B])` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Menu Equipment inventory (IDE 184)](PVE-IDE-184.md) -> **Choix - Classification (IDE 247)**

Main -> ... -> [Package setup (IDE 220)](PVE-IDE-220.md) -> **Choix - Classification (IDE 247)**

Main -> ... -> [Package setup (IDE 367)](PVE-IDE-367.md) -> **Choix - Classification (IDE 247)**

Main -> ... -> [Menu Equipment inventory (IDE 411)](PVE-IDE-411.md) -> **Choix - Classification (IDE 247)**

Main -> ... -> [Label Management (IDE 105)](PVE-IDE-105.md) -> **Choix - Classification (IDE 247)**

Main -> ... -> [Menu Administration (IDE 178)](PVE-IDE-178.md) -> **Choix - Classification (IDE 247)**

```mermaid
graph LR
    T247[247 Choix - Classifica...]
    style T247 fill:#58a6ff
    CC411[411 Menu Equipment inv...]
    style CC411 fill:#8b5cf6
    CC439[439 Menu]
    style CC439 fill:#8b5cf6
    CC185[185 Menu]
    style CC185 fill:#8b5cf6
    CC420[420 Menu==V4___]
    style CC420 fill:#8b5cf6
    CC353[353 Menu==V4]
    style CC353 fill:#8b5cf6
    CC179[179 Menu Stocks Manage...]
    style CC179 fill:#8b5cf6
    CC178[178 Menu Administration]
    style CC178 fill:#3fb950
    CC105[105 Label Management]
    style CC105 fill:#3fb950
    CC367[367 Package setup]
    style CC367 fill:#3fb950
    CC220[220 Package setup]
    style CC220 fill:#3fb950
    CC184[184 Menu Equipment inv...]
    style CC184 fill:#3fb950
    CC179 --> CC105
    CC411 --> CC105
    CC185 --> CC105
    CC353 --> CC105
    CC420 --> CC105
    CC439 --> CC105
    CC179 --> CC178
    CC411 --> CC178
    CC185 --> CC178
    CC353 --> CC178
    CC420 --> CC178
    CC439 --> CC178
    CC179 --> CC184
    CC411 --> CC184
    CC185 --> CC184
    CC353 --> CC184
    CC420 --> CC184
    CC439 --> CC184
    CC179 --> CC220
    CC411 --> CC220
    CC185 --> CC220
    CC353 --> CC220
    CC420 --> CC220
    CC439 --> CC220
    CC179 --> CC367
    CC411 --> CC367
    CC185 --> CC367
    CC353 --> CC367
    CC420 --> CC367
    CC439 --> CC367
    CC105 --> T247
    CC178 --> T247
    CC184 --> T247
    CC220 --> T247
    CC367 --> T247
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [184](PVE-IDE-184.md) | Menu Equipment inventory | 2 |
| [220](PVE-IDE-220.md) | Package setup | 2 |
| [367](PVE-IDE-367.md) | Package setup | 2 |
| [411](PVE-IDE-411.md) | Menu Equipment inventory | 2 |
| [105](PVE-IDE-105.md) | Label Management | 1 |
| [178](PVE-IDE-178.md) | Menu Administration | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T247[247 Choix - Classifica...]
    style T247 fill:#58a6ff
    C271[271 Choix - Equipment ...]
    T247 --> C271
    style C271 fill:#3fb950
    C302[302 Action Cancel Query]
    T247 --> C302
    style C302 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [271](PVE-IDE-271.md) | Choix - Equipment type | 1 | Selection/consultation |
| [302](PVE-IDE-302.md) | Action Cancel Query | 1 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 23 | Programme compact |
| Expressions | 10 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 2 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 23) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 1 ecran, 0 traitement)

- **Strategie** : 1 composant(s) UI (Razor/React) avec formulaires et validation.
- 2 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| [Action Cancel Query (IDE 302)](PVE-IDE-302.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Choix - Equipment type (IDE 271)](PVE-IDE-271.md) | Sous-programme | 1x | Normale - Selection/consultation |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 19:11*
