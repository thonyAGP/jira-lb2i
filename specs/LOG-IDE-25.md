# LOG IDE 25 - Zoom des droits

> **Analyse**: Phases 1-4 2026-02-03 14:43 -> 14:43 (10s) | Assemblage 14:43
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | LOG |
| IDE Position | 25 |
| Nom Programme | Zoom des droits |
| Fichier source | `Prg_25.xml` |
| Dossier IDE | Zooms |
| Taches | 1 (1 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Zoom des droits** assure la gestion complete de ce processus, accessible depuis [CL mise à jour des groupes (IDE 14)](LOG-IDE-14.md), [   Droit / utilisateur (IDE 16)](LOG-IDE-16.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

**Donnees modifiees** : 1 tables en ecriture (type_de_continent).

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>25 - Liste des Droits [[ECRAN]](#ecran-t1)

**Role** : Traitement : Liste des Droits.
**Ecran** : 597 x 166 DLU (MDI) | [Voir mockup](#ecran-t1)
**Variables liees** : A (> Droits)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [CL mise à jour des groupes (IDE 14)](LOG-IDE-14.md), [   Droit / utilisateur (IDE 16)](LOG-IDE-16.md)
- **Appelle**: 0 programmes | **Tables**: 1 (W:1 R:0 L:0) | **Taches**: 1 | **Expressions**: 2

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 1)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 25 | 25 | Liste des Droits | MDI | 597 | 166 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>25 - Liste des Droits
**Tache** : [25](#t1) | **Type** : MDI | **Dimensions** : 597 x 166 DLU
**Bloc** : Traitement | **Titre IDE** : Liste des Droits

<!-- FORM-DATA:
{
    "width":  597,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  3,
                         "type":  "label",
                         "var":  "",
                         "y":  139,
                         "w":  589,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  37,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "196",
                         "w":  530,
                         "y":  8,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  11,
                         "h":  103,
                         "cols":  [
                                      {
                                          "title":  "Droit",
                                          "layer":  1,
                                          "w":  132
                                      },
                                      {
                                          "title":  "Description",
                                          "layer":  2,
                                          "w":  358
                                      }
                                  ],
                         "rows":  2
                     },
                     {
                         "x":  43,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  120,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "196",
                         "text":  "",
                         "parent":  21
                     },
                     {
                         "x":  174,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  344,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "196",
                         "text":  "",
                         "parent":  21
                     },
                     {
                         "x":  78,
                         "type":  "button",
                         "var":  "",
                         "y":  142,
                         "w":  160,
                         "fmt":  "\u0026Selectionner",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  356,
                         "type":  "button",
                         "var":  "",
                         "y":  142,
                         "w":  160,
                         "fmt":  "\u0026Quitter",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  268,
                         "type":  "image",
                         "var":  "",
                         "y":  115,
                         "w":  58,
                         "fmt":  "",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "25",
    "height":  166
}
-->

<details>
<summary><strong>Champs : 2 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 43,23 | (sans nom) | - | edit |
| 174,23 | (sans nom) | - | edit |

</details>

<details>
<summary><strong>Boutons : 2 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Selectionner | 78,142 | Ouvre la selection |
| Quitter | 356,142 | Quitte le programme |

</details>

## 9. NAVIGATION

Ecran unique: **Liste des Droits**

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **25.1** | [**Liste des Droits** (25)](#t1) [mockup](#ecran-t1) | MDI | 597x166 | Traitement |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Traitement principal]
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

### Tables utilisees (1)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 717 | type_de_continent |  | DB |   | **W** |   | 1 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 717 - type_de_continent (**W**) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | > Droits | W | Alpha |
| B | >ClauseWhere | W | Alpha |

</details>

## 11. VARIABLES

### 11.1 Autres (2)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | > Droits | Alpha | [25](#t1) |
| B | >ClauseWhere | Alpha | 1x refs |

## 12. EXPRESSIONS

**2 / 2 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONDITION | 2 | 0 |

### 12.2 Expressions cles par type

#### CONDITION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 2 | `>ClauseWhere [B]` | - |
| CONDITION | 1 | `> Droits [A]` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [CL mise à jour des groupes (IDE 14)](LOG-IDE-14.md) -> **Zoom des droits (IDE 25)**

Main -> ... -> [   Droit / utilisateur (IDE 16)](LOG-IDE-16.md) -> **Zoom des droits (IDE 25)**

```mermaid
graph LR
    T25[25 Zoom des droits]
    style T25 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC15[15 CL login utilisateur]
    style CC15 fill:#f59e0b
    CC20[20 CL login utilisateu...]
    style CC20 fill:#f59e0b
    CC21[21 CL Menu]
    style CC21 fill:#f59e0b
    CC14[14 CL mise à jour des ...]
    style CC14 fill:#3fb950
    CC16[16 Droit utilisateur]
    style CC16 fill:#3fb950
    CC21 --> CC14
    CC15 --> CC14
    CC20 --> CC14
    CC21 --> CC16
    CC15 --> CC16
    CC20 --> CC16
    CC1 --> CC21
    CC1 --> CC15
    CC1 --> CC20
    CC14 --> T25
    CC16 --> T25
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [14](LOG-IDE-14.md) | CL mise à jour des groupes | 1 |
| [16](LOG-IDE-16.md) |    Droit / utilisateur | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T25[25 Zoom des droits]
    style T25 fill:#58a6ff
    NONE[Aucun callee]
    T25 -.-> NONE
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
| Lignes de logique | 7 | Programme compact |
| Expressions | 2 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 7) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 1 ecran, 0 traitement)

- **Strategie** : 1 composant(s) UI (Razor/React) avec formulaires et validation.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| type_de_continent | Table WRITE (Database) | 1x | Schema + repository |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 14:43*
