# PVE IDE 264 - Choix - Equipment

> **Analyse**: Phases 1-4 2026-02-03 19:17 -> 19:18 (11s) | Assemblage 19:18
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PVE |
| IDE Position | 264 |
| Nom Programme | Choix - Equipment |
| Fichier source | `Prg_264.xml` |
| Dossier IDE | Tables |
| Taches | 1 (1 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Choix - Equipment** assure la gestion complete de ce processus, accessible depuis [Menu Check IN / Exchange (IDE 183)](PVE-IDE-183.md), [Menu Check IN / Exchange V4 (IDE 401)](PVE-IDE-401.md), [Menu Check IN / Exchange (IDE 410)](PVE-IDE-410.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>264 - Equipment type list [[ECRAN]](#ecran-t1)

**Role** : Traitement : Equipment type list.
**Ecran** : 542 x 308 DLU (MDI) | [Voir mockup](#ecran-t1)
**Variables liees** : B (p.type matos), D (p.equipment id)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Menu Check IN / Exchange (IDE 183)](PVE-IDE-183.md), [Menu Check IN / Exchange V4 (IDE 401)](PVE-IDE-401.md), [Menu Check IN / Exchange (IDE 410)](PVE-IDE-410.md)
- **Appelle**: 0 programmes | **Tables**: 5 (W:0 R:1 L:4) | **Taches**: 1 | **Expressions**: 13

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 1)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 264 | 264 | Equipment type list | MDI | 542 | 308 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>264 - Equipment type list
**Tache** : [264](#t1) | **Type** : MDI | **Dimensions** : 542 x 308 DLU
**Bloc** : Traitement | **Titre IDE** : Equipment type list

<!-- FORM-DATA:
{
    "width":  542,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  21,
                         "type":  "label",
                         "var":  "",
                         "y":  73,
                         "w":  53,
                         "fmt":  "",
                         "name":  "",
                         "h":  13,
                         "color":  "183",
                         "text":  "Type",
                         "parent":  null
                     },
                     {
                         "x":  154,
                         "type":  "label",
                         "var":  "",
                         "y":  73,
                         "w":  96,
                         "fmt":  "",
                         "name":  "",
                         "h":  13,
                         "color":  "183",
                         "text":  "Classification",
                         "parent":  null
                     },
                     {
                         "x":  337,
                         "type":  "label",
                         "var":  "",
                         "y":  73,
                         "w":  96,
                         "fmt":  "",
                         "name":  "",
                         "h":  13,
                         "color":  "183",
                         "text":  "Equipment Id",
                         "parent":  null
                     },
                     {
                         "x":  1,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  539,
                         "fmt":  "",
                         "name":  "",
                         "h":  42,
                         "color":  "182",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  14,
                         "type":  "label",
                         "var":  "",
                         "y":  15,
                         "w":  272,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "186",
                         "text":  "Select an equipment",
                         "parent":  4
                     },
                     {
                         "x":  16,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "110",
                         "w":  463,
                         "y":  87,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  28,
                         "h":  170,
                         "cols":  [
                                      {
                                          "title":  "",
                                          "layer":  1,
                                          "w":  135
                                      },
                                      {
                                          "title":  "",
                                          "layer":  2,
                                          "w":  181
                                      },
                                      {
                                          "title":  "",
                                          "layer":  3,
                                          "w":  147
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
                         "x":  21,
                         "type":  "edit",
                         "var":  "",
                         "y":  89,
                         "w":  125,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "110",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  154,
                         "type":  "edit",
                         "var":  "",
                         "y":  89,
                         "w":  175,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "110",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  337,
                         "type":  "edit",
                         "var":  "",
                         "y":  89,
                         "w":  138,
                         "fmt":  "U10",
                         "name":  "",
                         "h":  24,
                         "color":  "110",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  482,
                         "type":  "button",
                         "var":  "",
                         "y":  88,
                         "w":  44,
                         "fmt":  "ñ",
                         "name":  "",
                         "h":  86,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  482,
                         "type":  "button",
                         "var":  "",
                         "y":  174,
                         "w":  44,
                         "fmt":  "ò",
                         "name":  "",
                         "h":  84,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  385,
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
                         "x":  462,
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
                         "x":  22,
                         "type":  "edit",
                         "var":  "",
                         "y":  288,
                         "w":  350,
                         "fmt":  "100",
                         "name":  "",
                         "h":  10,
                         "color":  "36",
                         "text":  "",
                         "parent":  16
                     }
                 ],
    "taskId":  "264",
    "height":  308
}
-->

<details>
<summary><strong>Champs : 4 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 21,89 | (sans nom) | - | edit |
| 154,89 | (sans nom) | - | edit |
| 337,89 | U10 | - | edit |
| 22,288 | 100 | - | edit |

</details>

<details>
<summary><strong>Boutons : 4 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| ñ | 482,88 | Bouton fonctionnel |
| ò | 482,174 | Bouton fonctionnel |
| Select | 385,278 | Ouvre la selection |
| Exit | 462,278 | Quitte le programme |

</details>

## 9. NAVIGATION

Ecran unique: **Equipment type list**

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **264.1** | [**Equipment type list** (264)](#t1) [mockup](#ecran-t1) | MDI | 542x308 | Traitement |

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

### Tables utilisees (5)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 380 | pv_day_modes |  | DB |   |   | L | 1 |
| 382 | pv_discount_reasons |  | DB |   |   | L | 1 |
| 389 | pv_equipment_inventory |  | DB | R |   |   | 1 |
| 404 | pv_sellers_by_week |  | DB |   |   | L | 1 |
| 419 | realise_articles_caution | Articles et stock | DB |   |   | L | 1 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 389 - pv_equipment_inventory (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | p. status | R | Alpha |
| B | p.type matos | R | Numeric |
| C | p. classification | R | Numeric |
| D | p.equipment id | R | Alpha |
| E | v.Client trouvé ? | R | Logical |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (4)

Variables recues du programme appelant ([Menu Check IN / Exchange (IDE 183)](PVE-IDE-183.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | p. status | Alpha | 1x parametre entrant |
| B | p.type matos | Numeric | 1x parametre entrant |
| C | p. classification | Numeric | 1x parametre entrant |
| D | p.equipment id | Alpha | 1x parametre entrant |

### 11.2 Variables de session (1)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| E | v.Client trouvé ? | Logical | - |

## 12. EXPRESSIONS

**13 / 13 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCULATION | 2 | 0 |
| CONDITION | 3 | 0 |
| OTHER | 7 | 0 |
| CONCATENATION | 1 | 0 |

### 12.2 Expressions cles par type

#### CALCULATION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 12 | `'00/00/0000'DATE` | - |
| CALCULATION | 11 | `'01/01/2000'DATE` | - |

#### CONDITION (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 5 | `CndRange (Trim (p. status [A])<>'',p. status [A])` | - |
| CONDITION | 3 | `CndRange (p. classification [C]<>0,p. classification [C])` | - |
| CONDITION | 1 | `CndRange (p.type matos [B]<>0,p.type matos [B])` | - |

#### OTHER (7 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 8 | `GetParam ('SERVICE')` | - |
| OTHER | 9 | `[U]` | - |
| OTHER | 13 | `[Y]` | - |
| OTHER | 7 | `[O]` | - |
| OTHER | 2 | `[F]` | - |
| ... | | *+2 autres* | |

#### CONCATENATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 10 | `RTrim([X]) & ' ' & [W]` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Menu Check IN / Exchange (IDE 183)](PVE-IDE-183.md) -> **Choix - Equipment (IDE 264)**

Main -> ... -> [Menu Check IN / Exchange V4 (IDE 401)](PVE-IDE-401.md) -> **Choix - Equipment (IDE 264)**

Main -> ... -> [Menu Check IN / Exchange (IDE 410)](PVE-IDE-410.md) -> **Choix - Equipment (IDE 264)**

```mermaid
graph LR
    T264[264 Choix - Equipment]
    style T264 fill:#58a6ff
    CC353[353 Menu==V4]
    style CC353 fill:#8b5cf6
    CC420[420 Menu==V4___]
    style CC420 fill:#8b5cf6
    CC187[187 Main Sale-664]
    style CC187 fill:#f59e0b
    CC214[214 Main Sale Sale Bar...]
    style CC214 fill:#f59e0b
    CC352[352 Main Sale ===V4 bck]
    style CC352 fill:#f59e0b
    CC185[185 Menu]
    style CC185 fill:#f59e0b
    CC186[186 Main Sale]
    style CC186 fill:#f59e0b
    CC183[183 Menu Check IN Exch...]
    style CC183 fill:#3fb950
    CC401[401 Menu Check IN Exch...]
    style CC401 fill:#3fb950
    CC410[410 Menu Check IN Exch...]
    style CC410 fill:#3fb950
    CC185 --> CC183
    CC186 --> CC183
    CC187 --> CC183
    CC214 --> CC183
    CC352 --> CC183
    CC185 --> CC401
    CC186 --> CC401
    CC187 --> CC401
    CC214 --> CC401
    CC352 --> CC401
    CC185 --> CC410
    CC186 --> CC410
    CC187 --> CC410
    CC214 --> CC410
    CC352 --> CC410
    CC353 --> CC185
    CC420 --> CC185
    CC353 --> CC186
    CC420 --> CC186
    CC353 --> CC187
    CC420 --> CC187
    CC353 --> CC214
    CC420 --> CC214
    CC353 --> CC352
    CC420 --> CC352
    CC183 --> T264
    CC401 --> T264
    CC410 --> T264
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [183](PVE-IDE-183.md) | Menu Check IN / Exchange | 2 |
| [401](PVE-IDE-401.md) | Menu Check IN / Exchange V4 | 2 |
| [410](PVE-IDE-410.md) | Menu Check IN / Exchange | 2 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T264[264 Choix - Equipment]
    style T264 fill:#58a6ff
    NONE[Aucun callee]
    T264 -.-> NONE
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| - | (aucun) | - | - |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 41 | Programme compact |
| Expressions | 13 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 41) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 1 ecran, 0 traitement)

- **Strategie** : 1 composant(s) UI (Razor/React) avec formulaires et validation.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 19:18*
