# PBG IDE 360 - Zoom Selection Occupation

> **Analyse**: Phases 1-4 2026-02-03 11:24 -> 11:24 (17s) | Assemblage 11:24
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBG |
| IDE Position | 360 |
| Nom Programme | Zoom Selection Occupation |
| Fichier source | `Prg_360.xml` |
| Dossier IDE | Consultation |
| Taches | 1 (1 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Zoom Selection Occupation** assure la gestion complete de ce processus, accessible depuis [   Recodification Client (IDE 77)](PBG-IDE-77.md), [   Avancement Client (IDE 78)](PBG-IDE-78.md), [   Prolongation Client (IDE 83)](PBG-IDE-83.md), [  Recodification Personnel (IDE 187)](PBG-IDE-187.md), [  Avancement Personnel (IDE 188)](PBG-IDE-188.md), [  Prolongation Personnel (IDE 192)](PBG-IDE-192.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Consultation** (1 tache) : ecrans de recherche, selection et consultation

## 3. BLOCS FONCTIONNELS

### 3.1 Consultation (1 tache)

Ecrans de recherche et consultation.

---

#### <a id="t1"></a>360 - Selection Occupation [[ECRAN]](#ecran-t1)

**Role** : Selection par l'operateur : Selection Occupation.
**Ecran** : 386 x 153 DLU (MDI) | [Voir mockup](#ecran-t1)
**Variables liees** : C (< Occupation)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [   Recodification Client (IDE 77)](PBG-IDE-77.md), [   Avancement Client (IDE 78)](PBG-IDE-78.md), [   Prolongation Client (IDE 83)](PBG-IDE-83.md), [  Recodification Personnel (IDE 187)](PBG-IDE-187.md), [  Avancement Personnel (IDE 188)](PBG-IDE-188.md), [  Prolongation Personnel (IDE 192)](PBG-IDE-192.md)
- **Appelle**: 0 programmes | **Tables**: 1 (W:0 R:1 L:0) | **Taches**: 1 | **Expressions**: 7

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 1)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 360 | 360 | Selection Occupation | MDI | 386 | 153 | Consultation |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>360 - Selection Occupation
**Tache** : [360](#t1) | **Type** : MDI | **Dimensions** : 386 x 153 DLU
**Bloc** : Consultation | **Titre IDE** : Selection Occupation

<!-- FORM-DATA:
{
    "width":  386,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  107,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "196",
                         "w":  174,
                         "y":  6,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  12,
                         "h":  92,
                         "cols":  [
                                      {
                                          "title":  "Occupation",
                                          "layer":  1,
                                          "w":  139
                                      }
                                  ],
                         "rows":  1
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  127,
                         "w":  381,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  117,
                         "type":  "edit",
                         "var":  "",
                         "y":  22,
                         "w":  120,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "196",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  6,
                         "type":  "button",
                         "var":  "",
                         "y":  130,
                         "w":  154,
                         "fmt":  "\u0026Selectionner",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  220,
                         "type":  "button",
                         "var":  "",
                         "y":  130,
                         "w":  154,
                         "fmt":  "\u0026Quitter",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  161,
                         "type":  "image",
                         "var":  "",
                         "y":  103,
                         "w":  58,
                         "fmt":  "",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "360",
    "height":  153
}
-->

<details>
<summary><strong>Champs : 1 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 117,22 | (sans nom) | - | edit |

</details>

<details>
<summary><strong>Boutons : 2 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Selectionner | 6,130 | Ouvre la selection |
| Quitter | 220,130 | Quitte le programme |

</details>

## 9. NAVIGATION

Ecran unique: **Selection Occupation**

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **360.1** | [**Selection Occupation** (360)](#t1) [mockup](#ecran-t1) | MDI | 386x153 | Consultation |

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
| 112 | tables_paris |  | DB | R |   |   | 1 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 112 - tables_paris (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | >.code table | R | Alpha |
| B | > code langue | R | Alpha |
| C | < Occupation | R | Alpha |
| D | < Accord suite | R | Alpha |

</details>

## 11. VARIABLES

### 11.1 Autres (4)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | >.code table | Alpha | 1x refs |
| B | > code langue | Alpha | 1x refs |
| C | < Occupation | Alpha | [360](#t1) |
| D | < Accord suite | Alpha | - |

## 12. EXPRESSIONS

**7 / 7 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONSTANTE | 2 | 0 |
| OTHER | 2 | 0 |
| CONDITION | 3 | 0 |

### 12.2 Expressions cles par type

#### CONSTANTE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 6 | `'O'` | - |
| CONSTANTE | 2 | `'N'` | - |

#### OTHER (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 5 | `[G]` | - |
| OTHER | 1 | `MlsTrans ('Selection Occupation')` | - |

#### CONDITION (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 7 | `< Occupation [C]` | - |
| CONDITION | 4 | `> code langue [B]` | - |
| CONDITION | 3 | `>.code table [A]` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [   Recodification Client (IDE 77)](PBG-IDE-77.md) -> **Zoom Selection Occupation (IDE 360)**

Main -> ... -> [   Avancement Client (IDE 78)](PBG-IDE-78.md) -> **Zoom Selection Occupation (IDE 360)**

Main -> ... -> [   Prolongation Client (IDE 83)](PBG-IDE-83.md) -> **Zoom Selection Occupation (IDE 360)**

Main -> ... -> [  Recodification Personnel (IDE 187)](PBG-IDE-187.md) -> **Zoom Selection Occupation (IDE 360)**

Main -> ... -> [  Avancement Personnel (IDE 188)](PBG-IDE-188.md) -> **Zoom Selection Occupation (IDE 360)**

Main -> ... -> [  Prolongation Personnel (IDE 192)](PBG-IDE-192.md) -> **Zoom Selection Occupation (IDE 360)**

```mermaid
graph LR
    T360[360 Zoom Selection Occ...]
    style T360 fill:#58a6ff
    CC391[391 Module Sejours Sub...]
    style CC391 fill:#8b5cf6
    CC94[94 Module Sejours Call...]
    style CC94 fill:#8b5cf6
    CC196[196 Sejours personnel ...]
    style CC196 fill:#8b5cf6
    CC77[77 Recodification Client]
    style CC77 fill:#3fb950
    CC188[188 Avancement Personnel]
    style CC188 fill:#3fb950
    CC78[78 Avancement Client]
    style CC78 fill:#3fb950
    CC83[83 Prolongation Client]
    style CC83 fill:#3fb950
    CC187[187 Recodification Per...]
    style CC187 fill:#3fb950
    CC94 --> CC77
    CC391 --> CC77
    CC196 --> CC77
    CC94 --> CC78
    CC391 --> CC78
    CC196 --> CC78
    CC94 --> CC83
    CC391 --> CC83
    CC196 --> CC83
    CC94 --> CC187
    CC391 --> CC187
    CC196 --> CC187
    CC94 --> CC188
    CC391 --> CC188
    CC196 --> CC188
    CC77 --> T360
    CC78 --> T360
    CC83 --> T360
    CC187 --> T360
    CC188 --> T360
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [77](PBG-IDE-77.md) |    Recodification Client | 2 |
| [78](PBG-IDE-78.md) |    Avancement Client | 2 |
| [83](PBG-IDE-83.md) |    Prolongation Client | 2 |
| [187](PBG-IDE-187.md) |   Recodification Personnel | 1 |
| [188](PBG-IDE-188.md) |   Avancement Personnel | 1 |
| [192](PBG-IDE-192.md) |   Prolongation Personnel | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T360[360 Zoom Selection Occ...]
    style T360 fill:#58a6ff
    NONE[Aucun callee]
    T360 -.-> NONE
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
| Lignes de logique | 15 | Programme compact |
| Expressions | 7 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 15) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Consultation (1 tache: 1 ecran, 0 traitement)

- **Strategie** : Composants de recherche/selection en modales.
- 1 ecran : Selection Occupation

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 11:24*
