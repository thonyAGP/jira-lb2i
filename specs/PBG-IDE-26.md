# PBG IDE 26 - Mise à jour passeport par nom

> **Analyse**: Phases 1-4 2026-02-03 01:13 -> 01:14 (39s) | Assemblage 01:14
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBG |
| IDE Position | 26 |
| Nom Programme | Mise à jour passeport par nom |
| Fichier source | `Prg_26.xml` |
| Domaine metier | General |
| Taches | 2 (1 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |
| :warning: Statut | **ORPHELIN_POTENTIEL** |

## 2. DESCRIPTION FONCTIONNELLE

**Mise à jour passeport par nom** assure la gestion complete de ce processus.

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (2 taches) : traitements metier divers

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (2 taches)

Traitements internes.

---

#### <a id="t1"></a>26 - Mise à jour passeport par nom [[ECRAN]](#ecran-t1)

**Role** : Traitement : Mise à jour passeport par nom.
**Ecran** : 630 x 300 DLU (MDI) | [Voir mockup](#ecran-t1)
**Variables liees** : F (v. pays delivrance passeport)

---

#### <a id="t2"></a>26.1 - Mise à jour passeport [[ECRAN]](#ecran-t2)

**Role** : Traitement : Mise à jour passeport.
**Ecran** : 621 x 289 DLU (MDI) | [Voir mockup](#ecran-t2)
**Variables liees** : F (v. pays delivrance passeport)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: (aucun)
- **Appelle**: 0 programmes | **Tables**: 7 (W:0 R:1 L:6) | **Taches**: 2 | **Expressions**: 1

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 2)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 26.1 | 26.1 | Mise à jour passeport | MDI | 621 | 289 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t2"></a>26.1 - Mise à jour passeport
**Tache** : [26.1](#t2) | **Type** : MDI | **Dimensions** : 621 x 289 DLU
**Bloc** : Traitement | **Titre IDE** : Mise à jour passeport

<!-- FORM-DATA:
{
    "width":  621,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  619,
                         "fmt":  "",
                         "name":  "",
                         "h":  246,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  4,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  11,
                         "color":  "110",
                         "w":  611,
                         "y":  7,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  16,
                         "h":  219,
                         "cols":  [
                                      {
                                          "title":  "Nom",
                                          "layer":  1,
                                          "w":  154
                                      },
                                      {
                                          "title":  "Prénom",
                                          "layer":  2,
                                          "w":  128
                                      },
                                      {
                                          "title":  "N° Passeport",
                                          "layer":  3,
                                          "w":  130
                                      },
                                      {
                                          "title":  "Date délivrance",
                                          "layer":  4,
                                          "w":  91
                                      },
                                      {
                                          "title":  "Nationalité",
                                          "layer":  5,
                                          "w":  90
                                      }
                                  ],
                         "rows":  5
                     },
                     {
                         "x":  6,
                         "type":  "label",
                         "var":  "",
                         "y":  231,
                         "w":  63,
                         "fmt":  "",
                         "name":  "",
                         "h":  11,
                         "color":  "",
                         "text":  "Pays naissance",
                         "parent":  1
                     },
                     {
                         "x":  251,
                         "type":  "label",
                         "var":  "",
                         "y":  231,
                         "w":  65,
                         "fmt":  "",
                         "name":  "",
                         "h":  11,
                         "color":  "",
                         "text":  "Pays delivrance",
                         "parent":  1
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  246,
                         "w":  619,
                         "fmt":  "",
                         "name":  "",
                         "h":  40,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  234,
                         "type":  "label",
                         "var":  "",
                         "y":  251,
                         "w":  171,
                         "fmt":  "",
                         "name":  "",
                         "h":  33,
                         "color":  "7",
                         "text":  "Recherche par Nom",
                         "parent":  null
                     },
                     {
                         "x":  260,
                         "type":  "edit",
                         "var":  "",
                         "y":  266,
                         "w":  119,
                         "fmt":  "U20",
                         "name":  "",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  17
                     },
                     {
                         "x":  8,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  144,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  2
                     },
                     {
                         "x":  165,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  117,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  2
                     },
                     {
                         "x":  291,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  116,
                         "fmt":  "U20",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  2
                     },
                     {
                         "x":  433,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  62,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  2
                     },
                     {
                         "x":  510,
                         "type":  "combobox",
                         "var":  "",
                         "y":  20,
                         "w":  90,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "110",
                         "text":  "1,2",
                         "parent":  2
                     },
                     {
                         "x":  79,
                         "type":  "edit",
                         "var":  "",
                         "y":  231,
                         "w":  74,
                         "fmt":  "U12",
                         "name":  "",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  79,
                         "type":  "combobox",
                         "var":  "",
                         "y":  231,
                         "w":  119,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "110",
                         "text":  "1,2",
                         "parent":  null
                     },
                     {
                         "x":  325,
                         "type":  "combobox",
                         "var":  "",
                         "y":  231,
                         "w":  119,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "110",
                         "text":  "1,2",
                         "parent":  null
                     },
                     {
                         "x":  325,
                         "type":  "edit",
                         "var":  "",
                         "y":  231,
                         "w":  203,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     }
                 ],
    "taskId":  "26.1",
    "height":  289
}
-->

<details>
<summary><strong>Champs : 10 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 260,266 | U20 | - | edit |
| 8,23 | (sans nom) | - | edit |
| 165,23 | (sans nom) | - | edit |
| 291,23 | U20 | - | edit |
| 433,23 | (sans nom) | - | edit |
| 510,20 | 1,2 | - | combobox |
| 79,231 | U12 | - | edit |
| 79,231 | 1,2 | - | combobox |
| 325,231 | 1,2 | - | combobox |
| 325,231 | (sans nom) | - | edit |

</details>

## 9. NAVIGATION

Ecran unique: **Mise à jour passeport**

### 9.3 Structure hierarchique (2 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **26.1** | [**Mise à jour passeport par nom** (26)](#t1) [mockup](#ecran-t1) | MDI | 630x300 | Traitement |
| 26.1.1 | [Mise à jour passeport (26.1)](#t2) [mockup](#ecran-t2) | MDI | 621x289 | |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Mise à jour passeport]
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

### Tables utilisees (7)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 30 | gm-recherche_____gmr | Index de recherche | DB | R |   |   | 1 |
| 31 | gm-complet_______gmc |  | DB |   |   | L | 1 |
| 35 | personnel_go______go |  | DB |   |   | L | 1 |
| 36 | client_gm |  | DB |   |   | L | 1 |
| 119 | tables_pays_tel_ |  | DB |   |   | L | 1 |
| 131 | fichier_validation |  | DB |   |   | L | 1 |
| 281 | crew |  | DB |   |   | L | 1 |

### Colonnes par table (2 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 30 - gm-recherche_____gmr (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | W1 nom | R | Alpha |
| B | v. cdrt gm | R | Logical |
| C | v. cdrt go | R | Logical |
| D | v. nationalite | R | Alpha |
| E | v. pays naissance | R | Alpha |
| F | v. pays delivrance passeport | R | Alpha |
| G | v. pay go delivrance | R | Alpha |

</details>

## 11. VARIABLES

### 11.1 Variables de session (4)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| D | v. nationalite | Alpha | - |
| E | v. pays naissance | Alpha | - |
| F | v. pays delivrance passeport | Alpha | - |
| G | v. pay go delivrance | Alpha | - |

### 11.2 Variables de travail (2)

Variables internes au programme.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| B | W0 nom | Alpha | - |
| C | W0 fin | Logical | 1x calcul interne |

### 11.3 Autres (1)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | > GO | Logical | - |

## 12. EXPRESSIONS

**1 / 1 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| OTHER | 1 | 0 |

### 12.2 Expressions cles par type

#### OTHER (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 1 | `W0 fin [C]` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

**Chemin**: (pas de callers directs)

```mermaid
graph LR
    T26[26 Mise à jour passepo...]
    style T26 fill:#58a6ff
    NONE[Aucun caller]
    NONE -.-> T26
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| - | (aucun) | - |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T26[26 Mise à jour passepo...]
    style T26 fill:#58a6ff
    NONE[Aucun callee]
    T26 -.-> NONE
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
| Lignes de logique | 102 | Programme compact |
| Expressions | 1 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 102) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (2 taches: 2 ecrans, 0 traitement)

- **Strategie** : 2 composant(s) UI (Razor/React) avec formulaires et validation.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 01:14*
