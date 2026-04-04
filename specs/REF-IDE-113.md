# REF IDE 113 - Browse - tables_qualites__qua

> **Analyse**: Phases 1-4 2026-02-03 09:27 -> 09:28 (20s) | Assemblage 09:28
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | REF |
| IDE Position | 113 |
| Nom Programme | Browse - tables_qualites__qua |
| Fichier source | `Prg_113.xml` |
| Domaine metier | General |
| Taches | 1 (1 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 0 |
| :warning: Statut | **ORPHELIN_POTENTIEL** |

## 2. DESCRIPTION FONCTIONNELLE

**Browse - tables_qualites__qua** assure la gestion complete de ce processus.

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

**Donnees modifiees** : 1 tables en ecriture (tables_qualites__qua).

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>113 - Browse - tables_qualites__qua [[ECRAN]](#ecran-t1)

**Role** : Traitement : Browse - tables_qualites__qua.
**Ecran** : 828 x 220 DLU | [Voir mockup](#ecran-t1)


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
| 1 | 113 | 113 | Browse - tables_qualites__qua | Type0 | 828 | 220 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>113 - Browse - tables_qualites__qua
**Tache** : [113](#t1) | **Type** : Type0 | **Dimensions** : 828 x 220 DLU
**Bloc** : Traitement | **Titre IDE** : Browse - tables_qualites__qua

<!-- FORM-DATA:
{
    "width":  828,
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
                         "w":  1299,
                         "y":  8,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  13,
                         "h":  182,
                         "cols":  [
                                      {
                                          "title":  "qua_societe",
                                          "layer":  1,
                                          "w":  50
                                      },
                                      {
                                          "title":  "qua_code_selection",
                                          "layer":  2,
                                          "w":  80
                                      },
                                      {
                                          "title":  "qua_code_tri",
                                          "layer":  3,
                                          "w":  53
                                      },
                                      {
                                          "title":  "qua_code_qualite",
                                          "layer":  4,
                                          "w":  71
                                      },
                                      {
                                          "title":  "qua_compl__qualite",
                                          "layer":  5,
                                          "w":  79
                                      },
                                      {
                                          "title":  "qua_libelle",
                                          "layer":  6,
                                          "w":  145
                                      },
                                      {
                                          "title":  "qua_valeur",
                                          "layer":  7,
                                          "w":  46
                                      },
                                      {
                                          "title":  "qua_1",
                                          "layer":  8,
                                          "w":  27
                                      },
                                      {
                                          "title":  "qua_acces",
                                          "layer":  9,
                                          "w":  46
                                      },
                                      {
                                          "title":  "qua_2",
                                          "layer":  10,
                                          "w":  34
                                      },
                                      {
                                          "title":  "qua_forfait_ski",
                                          "layer":  11,
                                          "w":  58
                                      },
                                      {
                                          "title":  "qua_priorite",
                                          "layer":  12,
                                          "w":  47
                                      },
                                      {
                                          "title":  "qua_tab_remplissage",
                                          "layer":  13,
                                          "w":  83
                                      },
                                      {
                                          "title":  "qua_type_jh",
                                          "layer":  14,
                                          "w":  50
                                      },
                                      {
                                          "title":  "qua_libelle_ang",
                                          "layer":  15,
                                          "w":  145
                                      },
                                      {
                                          "title":  "qua_stat_nuitee",
                                          "layer":  16,
                                          "w":  64
                                      },
                                      {
                                          "title":  "qua_regroup_famille",
                                          "layer":  17,
                                          "w":  79
                                      },
                                      {
                                          "title":  "qua_liste_menage",
                                          "layer":  18,
                                          "w":  72
                                      },
                                      {
                                          "title":  "qua_loc_free",
                                          "layer":  19,
                                          "w":  53
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
                         "name":  "qua_societe",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  36
                     },
                     {
                         "x":  62,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  9,
                         "fmt":  "",
                         "name":  "qua_code_selection",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  36
                     },
                     {
                         "x":  142,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  14,
                         "fmt":  "",
                         "name":  "qua_code_tri",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  36
                     },
                     {
                         "x":  195,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  20,
                         "fmt":  "",
                         "name":  "qua_code_qualite",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  36
                     },
                     {
                         "x":  266,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  26,
                         "fmt":  "",
                         "name":  "qua_compl__qualite",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  36
                     },
                     {
                         "x":  345,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  138,
                         "fmt":  "",
                         "name":  "qua_libelle",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  36
                     },
                     {
                         "x":  490,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  9,
                         "fmt":  "",
                         "name":  "qua_valeur",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  36
                     },
                     {
                         "x":  536,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  9,
                         "fmt":  "",
                         "name":  "qua_1",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  36
                     },
                     {
                         "x":  563,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  9,
                         "fmt":  "",
                         "name":  "qua_acces",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  36
                     },
                     {
                         "x":  609,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  27,
                         "fmt":  "",
                         "name":  "qua_2",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  36
                     },
                     {
                         "x":  643,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  31,
                         "fmt":  "",
                         "name":  "qua_forfait_ski",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  36
                     },
                     {
                         "x":  701,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  18,
                         "fmt":  "",
                         "name":  "qua_priorite",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  36
                     },
                     {
                         "x":  748,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  31,
                         "fmt":  "",
                         "name":  "qua_tab_remplissage",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  36
                     },
                     {
                         "x":  831,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  20,
                         "fmt":  "",
                         "name":  "qua_type_jh",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  36
                     },
                     {
                         "x":  881,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  138,
                         "fmt":  "",
                         "name":  "qua_libelle_ang",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  36
                     },
                     {
                         "x":  1026,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  31,
                         "fmt":  "",
                         "name":  "qua_stat_nuitee",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  36
                     },
                     {
                         "x":  1090,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  31,
                         "fmt":  "",
                         "name":  "qua_regroup_famille",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  36
                     },
                     {
                         "x":  1169,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  31,
                         "fmt":  "",
                         "name":  "qua_liste_menage",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  36
                     },
                     {
                         "x":  1241,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  31,
                         "fmt":  "",
                         "name":  "qua_loc_as_GM",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  36
                     }
                 ],
    "taskId":  "113",
    "height":  220
}
-->

<details>
<summary><strong>Champs : 19 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 12,23 | qua_societe | - | edit |
| 62,23 | qua_code_selection | - | edit |
| 142,23 | qua_code_tri | - | edit |
| 195,23 | qua_code_qualite | - | edit |
| 266,23 | qua_compl__qualite | - | edit |
| 345,23 | qua_libelle | - | edit |
| 490,23 | qua_valeur | - | edit |
| 536,23 | qua_1 | - | edit |
| 563,23 | qua_acces | - | edit |
| 609,23 | qua_2 | - | edit |
| 643,23 | qua_forfait_ski | - | edit |
| 701,23 | qua_priorite | - | edit |
| 748,23 | qua_tab_remplissage | - | edit |
| 831,23 | qua_type_jh | - | edit |
| 881,23 | qua_libelle_ang | - | edit |
| 1026,23 | qua_stat_nuitee | - | edit |
| 1090,23 | qua_regroup_famille | - | edit |
| 1169,23 | qua_liste_menage | - | edit |
| 1241,23 | qua_loc_as_GM | - | edit |

</details>

## 9. NAVIGATION

Ecran unique: **Browse - tables_qualites__qua**

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **113.1** | [**Browse - tables_qualites__qua** (113)](#t1) [mockup](#ecran-t1) | - | 828x220 | Traitement |

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
| 120 | tables_qualites__qua |  | DB |   | **W** |   | 1 |

### Colonnes par table (0 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 120 - tables_qualites__qua (**W**) - 1 usages</summary>

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
    T113[113 Browse - tables_qu...]
    style T113 fill:#58a6ff
    NONE[Aucun caller]
    NONE -.-> T113
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| - | (aucun) | - |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T113[113 Browse - tables_qu...]
    style T113 fill:#58a6ff
    NONE[Aucun callee]
    T113 -.-> NONE
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
| tables_qualites__qua | Table WRITE (Database) | 1x | Schema + repository |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 09:28*
