# REF IDE 497 - Browse - parametre_generaux

> **Analyse**: Phases 1-4 2026-02-03 12:18 -> 12:19 (17s) | Assemblage 12:19
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | REF |
| IDE Position | 497 |
| Nom Programme | Browse - parametre_generaux |
| Fichier source | `Prg_497.xml` |
| Dossier IDE | General |
| Taches | 1 (1 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 0 |
| :warning: Statut | **ORPHELIN_POTENTIEL** |

## 2. DESCRIPTION FONCTIONNELLE

**Browse - parametre_generaux** assure la gestion complete de ce processus.

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

**Donnees modifiees** : 1 tables en ecriture (parametre_generaux).

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>497 - Browse - parametre_generaux [[ECRAN]](#ecran-t1)

**Role** : Traitement : Browse - parametre_generaux.
**Ecran** : 1230 x 195 DLU | [Voir mockup](#ecran-t1)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: (aucun)
- **Appelle**: 0 programmes | **Tables**: 1 (W:1 R:0 L:0) | **Taches**: 1 | **Expressions**: 0

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 1)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 497 | 497 | Browse - parametre_generaux | Type0 | 1230 | 195 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>497 - Browse - parametre_generaux
**Tache** : [497](#t1) | **Type** : Type0 | **Dimensions** : 1230 x 195 DLU
**Bloc** : Traitement | **Titre IDE** : Browse - parametre_generaux

<!-- FORM-DATA:
{
    "width":  1230,
    "vFactor":  8,
    "type":  "Type0",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  8,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "",
                         "w":  1208,
                         "y":  8,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  13,
                         "h":  182,
                         "cols":  [
                                      {
                                          "title":  "societe",
                                          "layer":  1,
                                          "w":  30
                                      },
                                      {
                                          "title":  "fiscalite_grec",
                                          "layer":  2,
                                          "w":  53
                                      },
                                      {
                                          "title":  "edition_od",
                                          "layer":  3,
                                          "w":  42
                                      },
                                      {
                                          "title":  "operation_durant_cloture",
                                          "layer":  4,
                                          "w":  98
                                      },
                                      {
                                          "title":  "net_time",
                                          "layer":  5,
                                          "w":  38
                                      },
                                      {
                                          "title":  "versionning",
                                          "layer":  6,
                                          "w":  46
                                      },
                                      {
                                          "title":  "sup_locks",
                                          "layer":  7,
                                          "w":  42
                                      },
                                      {
                                          "title":  "age_mineur",
                                          "layer":  8,
                                          "w":  47
                                      },
                                      {
                                          "title":  "activation_bar_limit",
                                          "layer":  9,
                                          "w":  75
                                      },
                                      {
                                          "title":  "age_bar_limit",
                                          "layer":  10,
                                          "w":  53
                                      },
                                      {
                                          "title":  "tai_obligatoire",
                                          "layer":  11,
                                          "w":  55
                                      },
                                      {
                                          "title":  "scroll_gm_od_light",
                                          "layer":  12,
                                          "w":  73
                                      },
                                      {
                                          "title":  "inhova",
                                          "layer":  13,
                                          "w":  29
                                      },
                                      {
                                          "title":  "jours_controle_date",
                                          "layer":  14,
                                          "w":  78
                                      },
                                      {
                                          "title":  "interfaces_tpe",
                                          "layer":  15,
                                          "w":  57
                                      },
                                      {
                                          "title":  "vide",
                                          "layer":  16,
                                          "w":  212
                                      },
                                      {
                                          "title":  "debut_exclu",
                                          "layer":  17,
                                          "w":  53
                                      },
                                      {
                                          "title":  "fin_exclu",
                                          "layer":  18,
                                          "w":  53
                                      },
                                      {
                                          "title":  "nbjoursvalidite",
                                          "layer":  19,
                                          "w":  57
                                      }
                                  ],
                         "rows":  19
                     },
                     {
                         "x":  12,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  9,
                         "fmt":  "",
                         "name":  "societe",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  42,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  31,
                         "fmt":  "",
                         "name":  "fiscalite_grec",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  95,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  31,
                         "fmt":  "",
                         "name":  "edition_od",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  137,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  31,
                         "fmt":  "",
                         "name":  "operation_durant_cloture",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  235,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  31,
                         "fmt":  "",
                         "name":  "net_time",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  273,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  31,
                         "fmt":  "",
                         "name":  "versionning",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  319,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  31,
                         "fmt":  "",
                         "name":  "sup_locks",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  361,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  14,
                         "fmt":  "",
                         "name":  "age_mineur",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  408,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  9,
                         "fmt":  "",
                         "name":  "activation_bar_limit",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  483,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  14,
                         "fmt":  "",
                         "name":  "age_bar_limit",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  536,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  9,
                         "fmt":  "",
                         "name":  "tai_obligatoire",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  591,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  9,
                         "fmt":  "",
                         "name":  "scroll_gm_od_light",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  664,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  9,
                         "fmt":  "",
                         "name":  "inhova",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  693,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  14,
                         "fmt":  "",
                         "name":  "jours_controle_date",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  771,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  9,
                         "fmt":  "",
                         "name":  "interfaces_tpe",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  828,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  205,
                         "fmt":  "",
                         "name":  "vide",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  1040,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  46,
                         "fmt":  "",
                         "name":  "debut_exclu",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  1093,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  46,
                         "fmt":  "",
                         "name":  "fin_exclu",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  1146,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  13,
                         "fmt":  "",
                         "name":  "nbjoursvalidite",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     }
                 ],
    "taskId":  "497",
    "height":  195
}
-->

<details>
<summary><strong>Champs : 19 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 12,23 | societe | - | edit |
| 42,23 | fiscalite_grec | - | edit |
| 95,23 | edition_od | - | edit |
| 137,23 | operation_durant_cloture | - | edit |
| 235,23 | net_time | - | edit |
| 273,23 | versionning | - | edit |
| 319,23 | sup_locks | - | edit |
| 361,23 | age_mineur | - | edit |
| 408,23 | activation_bar_limit | - | edit |
| 483,23 | age_bar_limit | - | edit |
| 536,23 | tai_obligatoire | - | edit |
| 591,23 | scroll_gm_od_light | - | edit |
| 664,23 | inhova | - | edit |
| 693,23 | jours_controle_date | - | edit |
| 771,23 | interfaces_tpe | - | edit |
| 828,23 | vide | - | edit |
| 1040,23 | debut_exclu | - | edit |
| 1093,23 | fin_exclu | - | edit |
| 1146,23 | nbjoursvalidite | - | edit |

</details>

## 9. NAVIGATION

Ecran unique: **Browse - parametre_generaux**

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **497.1** | [**Browse - parametre_generaux** (497)](#t1) [mockup](#ecran-t1) | - | 1230x195 | Traitement |

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
| 707 | parametre_generaux |  | DB |   | **W** |   | 1 |

### Colonnes par table (0 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 707 - parametre_generaux (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

*(Programme sans variables locales mappees)*

## 12. EXPRESSIONS

**0 / 0 expressions decodees (0%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|

### 12.2 Expressions cles par type

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

**Chemin**: (pas de callers directs)

```mermaid
graph LR
    T497[497 Browse - parametre...]
    style T497 fill:#58a6ff
    NONE[Aucun caller]
    NONE -.-> T497
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| - | (aucun) | - |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T497[497 Browse - parametre...]
    style T497 fill:#58a6ff
    NONE[Aucun callee]
    T497 -.-> NONE
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
| Lignes de logique | 20 | Programme compact |
| Expressions | 0 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 20) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 1 ecran, 0 traitement)

- **Strategie** : 1 composant(s) UI (Razor/React) avec formulaires et validation.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| parametre_generaux | Table WRITE (Database) | 1x | Schema + repository |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 12:19*
