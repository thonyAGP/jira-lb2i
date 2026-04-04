# REF IDE 611 - Browse - log_express_co

> **Analyse**: Phases 1-4 2026-02-03 13:07 -> 13:07 (17s) | Assemblage 13:07
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | REF |
| IDE Position | 611 |
| Nom Programme | Browse - log_express_co |
| Fichier source | `Prg_611.xml` |
| Dossier IDE | General |
| Taches | 1 (1 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 0 |
| :warning: Statut | **ORPHELIN_POTENTIEL** |

## 2. DESCRIPTION FONCTIONNELLE

**Browse - log_express_co** assure la gestion complete de ce processus.

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

**Donnees modifiees** : 1 tables en ecriture (log_express_co).

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>611 - Browse - log_express_co [[ECRAN]](#ecran-t1)

**Role** : Traitement : Browse - log_express_co.
**Ecran** : 4836 x 400 DLU | [Voir mockup](#ecran-t1)


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
| 1 | 611 | 611 | Browse - log_express_co | Type0 | 4836 | 400 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>611 - Browse - log_express_co
**Tache** : [611](#t1) | **Type** : Type0 | **Dimensions** : 4836 x 400 DLU
**Bloc** : Traitement | **Titre IDE** : Browse - log_express_co

<!-- FORM-DATA:
{
    "width":  4836,
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
                         "color":  "6",
                         "w":  4818,
                         "y":  8,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  13,
                         "h":  382,
                         "cols":  [
                                      {
                                          "title":  "leo_row_id",
                                          "layer":  1,
                                          "w":  58
                                      },
                                      {
                                          "title":  "leo_date_traitement",
                                          "layer":  2,
                                          "w":  78
                                      },
                                      {
                                          "title":  "leo_heure_traitement",
                                          "layer":  3,
                                          "w":  82
                                      },
                                      {
                                          "title":  "leo_user",
                                          "layer":  4,
                                          "w":  55
                                      },
                                      {
                                          "title":  "leo_compte",
                                          "layer":  5,
                                          "w":  49
                                      },
                                      {
                                          "title":  "leo_filiation",
                                          "layer":  6,
                                          "w":  45
                                      },
                                      {
                                          "title":  "leo_nom",
                                          "layer":  7,
                                          "w":  178
                                      },
                                      {
                                          "title":  "leo_prenom",
                                          "layer":  8,
                                          "w":  122
                                      },
                                      {
                                          "title":  "leo_email",
                                          "layer":  9,
                                          "w":  570
                                      },
                                      {
                                          "title":  "leo_dossier",
                                          "layer":  10,
                                          "w":  189
                                      },
                                      {
                                          "title":  "leo_transaction_validee",
                                          "layer":  11,
                                          "w":  93
                                      },
                                      {
                                          "title":  "leo_message_erreur",
                                          "layer":  12,
                                          "w":  1410
                                      },
                                      {
                                          "title":  "leo_creation_lsd",
                                          "layer":  13,
                                          "w":  65
                                      },
                                      {
                                          "title":  "leo_creation_exc",
                                          "layer":  14,
                                          "w":  68
                                      },
                                      {
                                          "title":  "leo_maj_solde",
                                          "layer":  15,
                                          "w":  57
                                      },
                                      {
                                          "title":  "leo_des_tel",
                                          "layer":  16,
                                          "w":  46
                                      },
                                      {
                                          "title":  "leo_des_CMP",
                                          "layer":  17,
                                          "w":  63
                                      },
                                      {
                                          "title":  "leo_creation_fac",
                                          "layer":  18,
                                          "w":  66
                                      },
                                      {
                                          "title":  "leo_fac_filename",
                                          "layer":  19,
                                          "w":  1444
                                      },
                                      {
                                          "title":  "leo_envoi_mail",
                                          "layer":  20,
                                          "w":  59
                                      }
                                  ],
                         "rows":  20
                     },
                     {
                         "x":  12,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  51,
                         "fmt":  "",
                         "name":  "leo_row_id",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  70,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  61,
                         "fmt":  "",
                         "name":  "leo_date_traitement",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  148,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  46,
                         "fmt":  "",
                         "name":  "leo_heure_traitement",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  230,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  48,
                         "fmt":  "",
                         "name":  "leo_user",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  285,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  42,
                         "fmt":  "",
                         "name":  "leo_compte",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  334,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  18,
                         "fmt":  "",
                         "name":  "leo_filiation",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  379,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  171,
                         "fmt":  "",
                         "name":  "leo_nom",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  557,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  115,
                         "fmt":  "",
                         "name":  "leo_prenom",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  679,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  563,
                         "fmt":  "",
                         "name":  "leo_email",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  1249,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  182,
                         "fmt":  "",
                         "name":  "leo_dossier",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  1438,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  31,
                         "fmt":  "",
                         "name":  "leo_transaction_validee",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  1531,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  1403,
                         "fmt":  "",
                         "name":  "leo_message_erreur",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  2941,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  31,
                         "fmt":  "",
                         "name":  "leo_creation_lsd",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  3006,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  31,
                         "fmt":  "",
                         "name":  "leo_creation_exc",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  3074,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  31,
                         "fmt":  "",
                         "name":  "leo_maj_solde",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  3131,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  32,
                         "fmt":  "",
                         "name":  "leo_des_tel",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  3177,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  32,
                         "fmt":  "",
                         "name":  "leo_des_leo_des_leo_des_CMP",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  3240,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  31,
                         "fmt":  "",
                         "name":  "leo_creation_fac",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  3306,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  1437,
                         "fmt":  "",
                         "name":  "leo_fac_filename",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  4750,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  31,
                         "fmt":  "",
                         "name":  "leo_envoi_mail",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     }
                 ],
    "taskId":  "611",
    "height":  400
}
-->

<details>
<summary><strong>Champs : 20 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 12,23 | leo_row_id | - | edit |
| 70,23 | leo_date_traitement | - | edit |
| 148,23 | leo_heure_traitement | - | edit |
| 230,23 | leo_user | - | edit |
| 285,23 | leo_compte | - | edit |
| 334,23 | leo_filiation | - | edit |
| 379,23 | leo_nom | - | edit |
| 557,23 | leo_prenom | - | edit |
| 679,23 | leo_email | - | edit |
| 1249,23 | leo_dossier | - | edit |
| 1438,23 | leo_transaction_validee | - | edit |
| 1531,23 | leo_message_erreur | - | edit |
| 2941,23 | leo_creation_lsd | - | edit |
| 3006,23 | leo_creation_exc | - | edit |
| 3074,23 | leo_maj_solde | - | edit |
| 3131,23 | leo_des_tel | - | edit |
| 3177,23 | leo_des_leo_des_leo_des_CMP | - | edit |
| 3240,23 | leo_creation_fac | - | edit |
| 3306,23 | leo_fac_filename | - | edit |
| 4750,23 | leo_envoi_mail | - | edit |

</details>

## 9. NAVIGATION

Ecran unique: **Browse - log_express_co**

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **611.1** | [**Browse - log_express_co** (611)](#t1) [mockup](#ecran-t1) | - | 4836x400 | Traitement |

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
| 876 | log_express_co |  | DB |   | **W** |   | 1 |

### Colonnes par table (0 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 876 - log_express_co (**W**) - 1 usages</summary>

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
    T611[611 Browse - log_expre...]
    style T611 fill:#58a6ff
    NONE[Aucun caller]
    NONE -.-> T611
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| - | (aucun) | - |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T611[611 Browse - log_expre...]
    style T611 fill:#58a6ff
    NONE[Aucun callee]
    T611 -.-> NONE
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
| log_express_co | Table WRITE (Database) | 1x | Schema + repository |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 13:07*
