# REF IDE 607 - Browse - param_gen_mail

> **Analyse**: Phases 1-4 2026-02-03 13:05 -> 13:06 (16s) | Assemblage 13:06
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | REF |
| IDE Position | 607 |
| Nom Programme | Browse - param_gen_mail |
| Fichier source | `Prg_607.xml` |
| Dossier IDE | General |
| Taches | 1 (1 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 0 |
| :warning: Statut | **ORPHELIN_POTENTIEL** |

## 2. DESCRIPTION FONCTIONNELLE

**Browse - param_gen_mail** assure la gestion complete de ce processus.

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

**Donnees modifiees** : 1 tables en ecriture (param_gen_mail).

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>607 - Browse - param_gen_mail [[ECRAN]](#ecran-t1)

**Role** : Traitement : Browse - param_gen_mail.
**Ecran** : 1475 x 195 DLU | [Voir mockup](#ecran-t1)


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
| 1 | 607 | 607 | Browse - param_gen_mail | Type0 | 1475 | 195 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>607 - Browse - param_gen_mail
**Tache** : [607](#t1) | **Type** : Type0 | **Dimensions** : 1475 x 195 DLU
**Bloc** : Traitement | **Titre IDE** : Browse - param_gen_mail

<!-- FORM-DATA:
{
    "width":  1475,
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
                         "w":  1453,
                         "y":  8,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  13,
                         "h":  182,
                         "cols":  [
                                      {
                                          "title":  "pgm_utilisateur",
                                          "layer":  1,
                                          "w":  122
                                      },
                                      {
                                          "title":  "pgm_password",
                                          "layer":  2,
                                          "w":  122
                                      },
                                      {
                                          "title":  "pgm_timeout_connexion",
                                          "layer":  3,
                                          "w":  95
                                      },
                                      {
                                          "title":  "pgm_serveur_mail_test",
                                          "layer":  4,
                                          "w":  94
                                      },
                                      {
                                          "title":  "pgm_user_mail_test",
                                          "layer":  5,
                                          "w":  178
                                      },
                                      {
                                          "title":  "pgm_user_mail_password",
                                          "layer":  6,
                                          "w":  178
                                      },
                                      {
                                          "title":  "pgm_serveur_mail_prod",
                                          "layer":  7,
                                          "w":  94
                                      },
                                      {
                                          "title":  "pgm_user_mail_prod",
                                          "layer":  8,
                                          "w":  178
                                      },
                                      {
                                          "title":  "pgm_user_mail_password_prod",
                                          "layer":  9,
                                          "w":  178
                                      },
                                      {
                                          "title":  "pgm_serveur_mail",
                                          "layer":  10,
                                          "w":  71
                                      },
                                      {
                                          "title":  "pgm_seuil_taille_fic_sauvegarde",
                                          "layer":  11,
                                          "w":  126
                                      }
                                  ],
                         "rows":  11
                     },
                     {
                         "x":  12,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  115,
                         "fmt":  "",
                         "name":  "pgm_utilisateur",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  134,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  115,
                         "fmt":  "",
                         "name":  "pgm_password",
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
                         "w":  18,
                         "fmt":  "",
                         "name":  "pgm_timeout_connexion",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  351,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  87,
                         "fmt":  "",
                         "name":  "pgm_serveur_mail_test",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  445,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  171,
                         "fmt":  "",
                         "name":  "pgm_user_mail_test",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  623,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  171,
                         "fmt":  "",
                         "name":  "pgm_user_mail_password",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  801,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  87,
                         "fmt":  "",
                         "name":  "pgm_serveur_mail_prod",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  895,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  171,
                         "fmt":  "",
                         "name":  "pgm_user_mail_prod",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  1073,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  171,
                         "fmt":  "",
                         "name":  "pgm_user_mail_password_prod",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  1251,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  9,
                         "fmt":  "",
                         "name":  "pgm_serveur_mail",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  1322,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  18,
                         "fmt":  "",
                         "name":  "pgm_seuil_taille_fic_sauvegarde",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     }
                 ],
    "taskId":  "607",
    "height":  195
}
-->

<details>
<summary><strong>Champs : 11 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 12,23 | pgm_utilisateur | - | edit |
| 134,23 | pgm_password | - | edit |
| 256,23 | pgm_timeout_connexion | - | edit |
| 351,23 | pgm_serveur_mail_test | - | edit |
| 445,23 | pgm_user_mail_test | - | edit |
| 623,23 | pgm_user_mail_password | - | edit |
| 801,23 | pgm_serveur_mail_prod | - | edit |
| 895,23 | pgm_user_mail_prod | - | edit |
| 1073,23 | pgm_user_mail_password_prod | - | edit |
| 1251,23 | pgm_serveur_mail | - | edit |
| 1322,23 | pgm_seuil_taille_fic_sauvegarde | - | edit |

</details>

## 9. NAVIGATION

Ecran unique: **Browse - param_gen_mail**

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **607.1** | [**Browse - param_gen_mail** (607)](#t1) [mockup](#ecran-t1) | - | 1475x195 | Traitement |

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
| 861 | param_gen_mail |  | DB |   | **W** |   | 1 |

### Colonnes par table (0 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 861 - param_gen_mail (**W**) - 1 usages</summary>

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
    T607[607 Browse - param_gen...]
    style T607 fill:#58a6ff
    NONE[Aucun caller]
    NONE -.-> T607
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| - | (aucun) | - |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T607[607 Browse - param_gen...]
    style T607 fill:#58a6ff
    NONE[Aucun callee]
    T607 -.-> NONE
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
| Lignes de logique | 12 | Programme compact |
| Expressions | 0 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 12) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 1 ecran, 0 traitement)

- **Strategie** : 1 composant(s) UI (Razor/React) avec formulaires et validation.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| param_gen_mail | Table WRITE (Database) | 1x | Schema + repository |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 13:06*
