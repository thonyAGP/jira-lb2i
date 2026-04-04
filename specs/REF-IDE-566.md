# REF IDE 566 - Browse - log_vod

> **Analyse**: Phases 1-4 2026-02-03 12:48 -> 12:49 (17s) | Assemblage 12:49
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | REF |
| IDE Position | 566 |
| Nom Programme | Browse - log_vod |
| Fichier source | `Prg_566.xml` |
| Dossier IDE | General |
| Taches | 1 (1 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 0 |
| :warning: Statut | **ORPHELIN_POTENTIEL** |

## 2. DESCRIPTION FONCTIONNELLE

**Browse - log_vod** assure la gestion complete de ce processus.

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

**Donnees modifiees** : 1 tables en ecriture (log_vod).

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>566 - Browse - log_vod [[ECRAN]](#ecran-t1)

**Role** : Traitement : Browse - log_vod.
**Ecran** : 1572 x 195 DLU | [Voir mockup](#ecran-t1)


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
| 1 | 566 | 566 | Browse - log_vod | Type0 | 1572 | 195 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>566 - Browse - log_vod
**Tache** : [566](#t1) | **Type** : Type0 | **Dimensions** : 1572 x 195 DLU
**Bloc** : Traitement | **Titre IDE** : Browse - log_vod

<!-- FORM-DATA:
{
    "width":  1572,
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
                         "w":  1395,
                         "y":  8,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  13,
                         "h":  182,
                         "cols":  [
                                      {
                                          "title":  "vod_datedebut",
                                          "layer":  1,
                                          "w":  68
                                      },
                                      {
                                          "title":  "vod_heuredebut",
                                          "layer":  2,
                                          "w":  66
                                      },
                                      {
                                          "title":  "vod_chambre",
                                          "layer":  3,
                                          "w":  55
                                      },
                                      {
                                          "title":  "vod_compte1",
                                          "layer":  4,
                                          "w":  55
                                      },
                                      {
                                          "title":  "vod_nom1",
                                          "layer":  5,
                                          "w":  299
                                      },
                                      {
                                          "title":  "vod_compte2",
                                          "layer":  6,
                                          "w":  55
                                      },
                                      {
                                          "title":  "vod_co_emis",
                                          "layer":  7,
                                          "w":  54
                                      },
                                      {
                                          "title":  "vod_ack_co",
                                          "layer":  8,
                                          "w":  51
                                      },
                                      {
                                          "title":  "vod_ver_co",
                                          "layer":  9,
                                          "w":  49
                                      },
                                      {
                                          "title":  "vod_ci_emis",
                                          "layer":  10,
                                          "w":  50
                                      },
                                      {
                                          "title":  "vod_ack_ci",
                                          "layer":  11,
                                          "w":  48
                                      },
                                      {
                                          "title":  "vod_ver_ci",
                                          "layer":  12,
                                          "w":  46
                                      },
                                      {
                                          "title":  "vod_stat_recu",
                                          "layer":  13,
                                          "w":  58
                                      },
                                      {
                                          "title":  "vod_ack_stat",
                                          "layer":  14,
                                          "w":  55
                                      },
                                      {
                                          "title":  "vod_info1_emis",
                                          "layer":  15,
                                          "w":  62
                                      },
                                      {
                                          "title":  "vod_ack_info1",
                                          "layer":  16,
                                          "w":  60
                                      },
                                      {
                                          "title":  "vod_info2_emis",
                                          "layer":  17,
                                          "w":  62
                                      },
                                      {
                                          "title":  "vod_ack_info2",
                                          "layer":  18,
                                          "w":  60
                                      },
                                      {
                                          "title":  "vod_datefin",
                                          "layer":  19,
                                          "w":  68
                                      },
                                      {
                                          "title":  "vod_heurefin",
                                          "layer":  20,
                                          "w":  53
                                      }
                                  ],
                         "rows":  20
                     },
                     {
                         "x":  12,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  61,
                         "fmt":  "",
                         "name":  "vod_datedebut",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  80,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  46,
                         "fmt":  "",
                         "name":  "vod_heuredebut",
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
                         "w":  37,
                         "fmt":  "",
                         "name":  "vod_chambre",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  201,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  42,
                         "fmt":  "",
                         "name":  "vod_compte1",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  256,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  292,
                         "fmt":  "",
                         "name":  "vod_nom1",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  555,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  42,
                         "fmt":  "",
                         "name":  "vod_compte2",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  610,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  31,
                         "fmt":  "",
                         "name":  "vod_co_emis",
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
                         "w":  31,
                         "fmt":  "",
                         "name":  "vod_ack_co",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  715,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  31,
                         "fmt":  "",
                         "name":  "vod_ver_co",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  764,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  31,
                         "fmt":  "",
                         "name":  "vod_ci_emis",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  814,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  31,
                         "fmt":  "",
                         "name":  "vod_ack_ci",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  862,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  31,
                         "fmt":  "",
                         "name":  "vod_ver_ci",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  908,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  31,
                         "fmt":  "",
                         "name":  "vod_stat_recu",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  966,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  31,
                         "fmt":  "",
                         "name":  "vod_ack_stat",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  1021,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  31,
                         "fmt":  "",
                         "name":  "vod_info1_emis",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  1083,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  31,
                         "fmt":  "",
                         "name":  "vod_ack_info1",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  1143,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  31,
                         "fmt":  "",
                         "name":  "vod_info2_emis",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  1205,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  31,
                         "fmt":  "",
                         "name":  "vod_ack_info2",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  1265,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  61,
                         "fmt":  "",
                         "name":  "vod_datefin",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  1333,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  46,
                         "fmt":  "",
                         "name":  "vod_heurefin",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     }
                 ],
    "taskId":  "566",
    "height":  195
}
-->

<details>
<summary><strong>Champs : 20 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 12,23 | vod_datedebut | - | edit |
| 80,23 | vod_heuredebut | - | edit |
| 146,23 | vod_chambre | - | edit |
| 201,23 | vod_compte1 | - | edit |
| 256,23 | vod_nom1 | - | edit |
| 555,23 | vod_compte2 | - | edit |
| 610,23 | vod_co_emis | - | edit |
| 664,23 | vod_ack_co | - | edit |
| 715,23 | vod_ver_co | - | edit |
| 764,23 | vod_ci_emis | - | edit |
| 814,23 | vod_ack_ci | - | edit |
| 862,23 | vod_ver_ci | - | edit |
| 908,23 | vod_stat_recu | - | edit |
| 966,23 | vod_ack_stat | - | edit |
| 1021,23 | vod_info1_emis | - | edit |
| 1083,23 | vod_ack_info1 | - | edit |
| 1143,23 | vod_info2_emis | - | edit |
| 1205,23 | vod_ack_info2 | - | edit |
| 1265,23 | vod_datefin | - | edit |
| 1333,23 | vod_heurefin | - | edit |

</details>

## 9. NAVIGATION

Ecran unique: **Browse - log_vod**

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **566.1** | [**Browse - log_vod** (566)](#t1) [mockup](#ecran-t1) | - | 1572x195 | Traitement |

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
| 788 | log_vod |  | DB |   | **W** |   | 1 |

### Colonnes par table (0 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 788 - log_vod (**W**) - 1 usages</summary>

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
    T566[566 Browse - log_vod]
    style T566 fill:#58a6ff
    NONE[Aucun caller]
    NONE -.-> T566
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| - | (aucun) | - |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T566[566 Browse - log_vod]
    style T566 fill:#58a6ff
    NONE[Aucun callee]
    T566 -.-> NONE
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
| log_vod | Table WRITE (Database) | 1x | Schema + repository |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 12:49*
