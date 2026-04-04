# REF IDE 598 - Browse - total_jour_forfait_sk

> **Analyse**: Phases 1-4 2026-02-03 13:02 -> 13:02 (17s) | Assemblage 13:02
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | REF |
| IDE Position | 598 |
| Nom Programme | Browse - total_jour_forfait_sk |
| Fichier source | `Prg_598.xml` |
| Dossier IDE | General |
| Taches | 1 (1 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 0 |
| :warning: Statut | **ORPHELIN_POTENTIEL** |

## 2. DESCRIPTION FONCTIONNELLE

**Browse - total_jour_forfait_sk** assure la gestion complete de ce processus.

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

**Donnees modifiees** : 1 tables en ecriture (total_jour_forfait_ski).

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>598 - Browse - total_jour_forfait_sk [[ECRAN]](#ecran-t1)

**Role** : Traitement : Browse - total_jour_forfait_sk.
**Ecran** : 1720 x 480 DLU | [Voir mockup](#ecran-t1)


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
| 1 | 598 | 598 | Browse - total_jour_forfait_sk | Type0 | 1720 | 480 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>598 - Browse - total_jour_forfait_sk
**Tache** : [598](#t1) | **Type** : Type0 | **Dimensions** : 1720 x 480 DLU
**Bloc** : Traitement | **Titre IDE** : Browse - total_jour_forfait_sk

<!-- FORM-DATA:
{
    "width":  1720,
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
                         "w":  1698,
                         "y":  8,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  13,
                         "h":  400,
                         "cols":  [
                                      {
                                          "title":  "tjfs_code_saison",
                                          "layer":  1,
                                          "w":  66
                                      },
                                      {
                                          "title":  "tjfs_date_retour",
                                          "layer":  2,
                                          "w":  68
                                      },
                                      {
                                          "title":  "tjfs_nb_forfait_demi_journee",
                                          "layer":  3,
                                          "w":  109
                                      },
                                      {
                                          "title":  "tjfs_nb_forfait_1jour",
                                          "layer":  4,
                                          "w":  77
                                      },
                                      {
                                          "title":  "tjfs_nb_forfait_2jours",
                                          "layer":  5,
                                          "w":  81
                                      },
                                      {
                                          "title":  "tjfs_nb_forfait_3jours",
                                          "layer":  6,
                                          "w":  81
                                      },
                                      {
                                          "title":  "tjfs_nb_forfait_4jours",
                                          "layer":  7,
                                          "w":  81
                                      },
                                      {
                                          "title":  "tjfs_nb_forfait_5jours",
                                          "layer":  8,
                                          "w":  81
                                      },
                                      {
                                          "title":  "tjfs_nb_forfait_6jours",
                                          "layer":  9,
                                          "w":  81
                                      },
                                      {
                                          "title":  "tjfs_nb_forfait_7jours",
                                          "layer":  10,
                                          "w":  81
                                      },
                                      {
                                          "title":  "tjfs_nb_forfait_8jours",
                                          "layer":  11,
                                          "w":  81
                                      },
                                      {
                                          "title":  "tjfs_nb_forfait_9jours",
                                          "layer":  12,
                                          "w":  81
                                      },
                                      {
                                          "title":  "tjfs_nb_forfait_10jours",
                                          "layer":  13,
                                          "w":  86
                                      },
                                      {
                                          "title":  "tjfs_nb_forfait_11jours",
                                          "layer":  14,
                                          "w":  86
                                      },
                                      {
                                          "title":  "tjfs_nb_forfait_12jours",
                                          "layer":  15,
                                          "w":  86
                                      },
                                      {
                                          "title":  "tjfs_nb_forfait_13jours",
                                          "layer":  16,
                                          "w":  86
                                      },
                                      {
                                          "title":  "tjfs_nb_forfait_14jours",
                                          "layer":  17,
                                          "w":  86
                                      },
                                      {
                                          "title":  "tjfs_nb_forfait_15jours",
                                          "layer":  18,
                                          "w":  86
                                      },
                                      {
                                          "title":  "tjfs_nb_forfait_total_journee",
                                          "layer":  19,
                                          "w":  107
                                      },
                                      {
                                          "title":  "tjfs_nb_forfait_total_JH",
                                          "layer":  20,
                                          "w":  90
                                      }
                                  ],
                         "rows":  20
                     },
                     {
                         "x":  12,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  9,
                         "fmt":  "",
                         "name":  "tjfs_code_saison",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  78,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  61,
                         "fmt":  "",
                         "name":  "tjfs_date_retour",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  146,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  18,
                         "fmt":  "",
                         "name":  "tjfs_nb_forfait_demi_journee",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  255,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  22,
                         "fmt":  "",
                         "name":  "tjfs_nb_forfait_1jour",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  332,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  22,
                         "fmt":  "",
                         "name":  "tjfs_nb_forfait_2jours",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  413,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  22,
                         "fmt":  "",
                         "name":  "tjfs_nb_forfait_3jours",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  494,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  22,
                         "fmt":  "",
                         "name":  "tjfs_nb_forfait_4jours",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  575,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  22,
                         "fmt":  "",
                         "name":  "tjfs_nb_forfait_5jours",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  656,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  22,
                         "fmt":  "",
                         "name":  "tjfs_nb_forfait_6jours",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  737,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  22,
                         "fmt":  "",
                         "name":  "tjfs_nb_forfait_7jours",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  818,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  22,
                         "fmt":  "",
                         "name":  "tjfs_nb_forfait_8jours",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  899,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  22,
                         "fmt":  "",
                         "name":  "tjfs_nb_forfait_9jours",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  980,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  22,
                         "fmt":  "",
                         "name":  "tjfs_nb_forfait_10jours",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  1066,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  22,
                         "fmt":  "",
                         "name":  "tjfs_nb_forfait_11jours",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  1152,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  22,
                         "fmt":  "",
                         "name":  "tjfs_nb_forfait_12jours",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  1238,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  22,
                         "fmt":  "",
                         "name":  "tjfs_nb_forfait_13jours",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  1324,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  22,
                         "fmt":  "",
                         "name":  "tjfs_nb_forfait_14jours",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  1410,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  22,
                         "fmt":  "",
                         "name":  "tjfs_nb_forfait_15jours",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  1496,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  22,
                         "fmt":  "",
                         "name":  "tjfs_nb_forfait_total_journee",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  1603,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  27,
                         "fmt":  "",
                         "name":  "tjfs_nb_forfait_total_JH",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     }
                 ],
    "taskId":  "598",
    "height":  480
}
-->

<details>
<summary><strong>Champs : 20 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 12,23 | tjfs_code_saison | - | edit |
| 78,23 | tjfs_date_retour | - | edit |
| 146,23 | tjfs_nb_forfait_demi_journee | - | edit |
| 255,23 | tjfs_nb_forfait_1jour | - | edit |
| 332,23 | tjfs_nb_forfait_2jours | - | edit |
| 413,23 | tjfs_nb_forfait_3jours | - | edit |
| 494,23 | tjfs_nb_forfait_4jours | - | edit |
| 575,23 | tjfs_nb_forfait_5jours | - | edit |
| 656,23 | tjfs_nb_forfait_6jours | - | edit |
| 737,23 | tjfs_nb_forfait_7jours | - | edit |
| 818,23 | tjfs_nb_forfait_8jours | - | edit |
| 899,23 | tjfs_nb_forfait_9jours | - | edit |
| 980,23 | tjfs_nb_forfait_10jours | - | edit |
| 1066,23 | tjfs_nb_forfait_11jours | - | edit |
| 1152,23 | tjfs_nb_forfait_12jours | - | edit |
| 1238,23 | tjfs_nb_forfait_13jours | - | edit |
| 1324,23 | tjfs_nb_forfait_14jours | - | edit |
| 1410,23 | tjfs_nb_forfait_15jours | - | edit |
| 1496,23 | tjfs_nb_forfait_total_journee | - | edit |
| 1603,23 | tjfs_nb_forfait_total_JH | - | edit |

</details>

## 9. NAVIGATION

Ecran unique: **Browse - total_jour_forfait_sk**

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **598.1** | [**Browse - total_jour_forfait_sk** (598)](#t1) [mockup](#ecran-t1) | - | 1720x480 | Traitement |

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
| 849 | total_jour_forfait_ski |  | DB |   | **W** |   | 1 |

### Colonnes par table (0 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 849 - total_jour_forfait_ski (**W**) - 1 usages</summary>

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
    T598[598 Browse - total_jou...]
    style T598 fill:#58a6ff
    NONE[Aucun caller]
    NONE -.-> T598
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| - | (aucun) | - |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T598[598 Browse - total_jou...]
    style T598 fill:#58a6ff
    NONE[Aucun callee]
    T598 -.-> NONE
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
| Lignes de logique | 21 | Programme compact |
| Expressions | 0 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 21) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 1 ecran, 0 traitement)

- **Strategie** : 1 composant(s) UI (Razor/React) avec formulaires et validation.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| total_jour_forfait_ski | Table WRITE (Database) | 1x | Schema + repository |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 13:02*
