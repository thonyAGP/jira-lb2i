# PBG IDE 113 - Avertissement Import

> **Analyse**: Phases 1-4 2026-02-03 09:28 -> 09:28 (20s) | Assemblage 09:28
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBG |
| IDE Position | 113 |
| Nom Programme | Avertissement Import |
| Fichier source | `Prg_113.xml` |
| Domaine metier | General |
| Taches | 8 (1 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 2 |

## 2. DESCRIPTION FONCTIONNELLE

**Avertissement Import** assure la gestion complete de ce processus, accessible depuis [Compte Rendu Arrivants (IDE 248)](PBG-IDE-248.md).

Le flux de traitement s'organise en **3 blocs fonctionnels** :

- **Traitement** (6 taches) : traitements metier divers
- **Consultation** (1 tache) : ecrans de recherche, selection et consultation
- **Validation** (1 tache) : controles et verifications de coherence

**Donnees modifiees** : 1 tables en ecriture (pv_pms_prestations_tmp).

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (6 taches)

- **113** - Avertissement Import **[[ECRAN]](#ecran-t1)**
- **113.2.1** - Visualisation Avertissement **[[ECRAN]](#ecran-t4)**
- **113.2.1.1** - Visualisation Code H **[[ECRAN]](#ecran-t5)**
- **113.2.1.2** - Visualisation Code I **[[ECRAN]](#ecran-t6)**
- **113.2.1.3** - Visualisation Code J **[[ECRAN]](#ecran-t7)**
- **113.2.1.4** - Visualisation Sans Code **[[ECRAN]](#ecran-t8)**

Delegue a : [   Impression avert. Import (IDE 112)](PBG-IDE-112.md), [Recuperation du titre (IDE 317)](PBG-IDE-317.md)

#### Phase 2 : Validation (1 tache)

- **113.1** - Verification Affichage

#### Phase 3 : Consultation (1 tache)

- **113.2** - Affichage Avertissement **[[ECRAN]](#ecran-t3)**

Delegue a : [Recuperation du titre (IDE 317)](PBG-IDE-317.md)

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| pv_pms_prestations_tmp | R/**W** (2 usages) | Prestations/services vendus |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (6 taches)

Traitements internes.

---

#### <a id="t1"></a>113 - Avertissement Import [[ECRAN]](#ecran-t1)

**Role** : Tache d'orchestration : point d'entree du programme (6 sous-taches). Coordonne l'enchainement des traitements.
**Ecran** : 190 x 11 DLU (MDI) | [Voir mockup](#ecran-t1)

<details>
<summary>5 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [113.2.1](#t4) | Visualisation Avertissement **[[ECRAN]](#ecran-t4)** | Traitement |
| [113.2.1.1](#t5) | Visualisation Code H **[[ECRAN]](#ecran-t5)** | Traitement |
| [113.2.1.2](#t6) | Visualisation Code I **[[ECRAN]](#ecran-t6)** | Traitement |
| [113.2.1.3](#t7) | Visualisation Code J **[[ECRAN]](#ecran-t7)** | Traitement |
| [113.2.1.4](#t8) | Visualisation Sans Code **[[ECRAN]](#ecran-t8)** | Traitement |

</details>
**Delegue a** : [   Impression avert. Import (IDE 112)](PBG-IDE-112.md), [Recuperation du titre (IDE 317)](PBG-IDE-317.md)

---

#### <a id="t4"></a>113.2.1 - Visualisation Avertissement [[ECRAN]](#ecran-t4)

**Role** : Traitement : Visualisation Avertissement.
**Ecran** : 200 x 8 DLU (MDI) | [Voir mockup](#ecran-t4)
**Delegue a** : [   Impression avert. Import (IDE 112)](PBG-IDE-112.md), [Recuperation du titre (IDE 317)](PBG-IDE-317.md)

---

#### <a id="t5"></a>113.2.1.1 - Visualisation Code H [[ECRAN]](#ecran-t5)

**Role** : Traitement : Visualisation Code H.
**Ecran** : 187 x 23 DLU (MDI) | [Voir mockup](#ecran-t5)
**Variables liees** : A (P0-Code Choix), B (P0-Code Societe), C (P0-Code Langue), D (W0-Code Suite), E (W0-Code B031)
**Delegue a** : [   Impression avert. Import (IDE 112)](PBG-IDE-112.md), [Recuperation du titre (IDE 317)](PBG-IDE-317.md)

---

#### <a id="t6"></a>113.2.1.2 - Visualisation Code I [[ECRAN]](#ecran-t6)

**Role** : Traitement : Visualisation Code I.
**Ecran** : 232 x 33 DLU (MDI) | [Voir mockup](#ecran-t6)
**Variables liees** : A (P0-Code Choix), B (P0-Code Societe), C (P0-Code Langue), D (W0-Code Suite), E (W0-Code B031)
**Delegue a** : [   Impression avert. Import (IDE 112)](PBG-IDE-112.md), [Recuperation du titre (IDE 317)](PBG-IDE-317.md)

---

#### <a id="t7"></a>113.2.1.3 - Visualisation Code J [[ECRAN]](#ecran-t7)

**Role** : Traitement : Visualisation Code J.
**Ecran** : 166 x 14 DLU (MDI) | [Voir mockup](#ecran-t7)
**Variables liees** : A (P0-Code Choix), B (P0-Code Societe), C (P0-Code Langue), D (W0-Code Suite), E (W0-Code B031)
**Delegue a** : [   Impression avert. Import (IDE 112)](PBG-IDE-112.md), [Recuperation du titre (IDE 317)](PBG-IDE-317.md)

---

#### <a id="t8"></a>113.2.1.4 - Visualisation Sans Code [[ECRAN]](#ecran-t8)

**Role** : Traitement : Visualisation Sans Code.
**Ecran** : 166 x 18 DLU (MDI) | [Voir mockup](#ecran-t8)
**Variables liees** : A (P0-Code Choix), B (P0-Code Societe), C (P0-Code Langue), D (W0-Code Suite), E (W0-Code B031)
**Delegue a** : [   Impression avert. Import (IDE 112)](PBG-IDE-112.md), [Recuperation du titre (IDE 317)](PBG-IDE-317.md)


### 3.2 Validation (1 tache)

Controles de coherence : 1 tache verifie les donnees et conditions.

---

#### <a id="t2"></a>113.1 - Verification Affichage

**Role** : Verification : Verification Affichage.


### 3.3 Consultation (1 tache)

Ecrans de recherche et consultation.

---

#### <a id="t3"></a>113.2 - Affichage Avertissement [[ECRAN]](#ecran-t3)

**Role** : Reinitialisation : Affichage Avertissement.
**Ecran** : 1002 x 251 DLU (MDI) | [Voir mockup](#ecran-t3)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Compte Rendu Arrivants (IDE 248)](PBG-IDE-248.md)
- **Appelle**: 2 programmes | **Tables**: 1 (W:1 R:1 L:0) | **Taches**: 8 | **Expressions**: 6

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 8)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 113.2 | 113.2 | Affichage Avertissement | MDI | 1002 | 251 | Consultation |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t3"></a>113.2 - Affichage Avertissement
**Tache** : [113.2](#t3) | **Type** : MDI | **Dimensions** : 1002 x 251 DLU
**Bloc** : Consultation | **Titre IDE** : Affichage Avertissement

<!-- FORM-DATA:
{
    "width":  1002,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  998,
                         "fmt":  "",
                         "name":  "",
                         "h":  21,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  6,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  13,
                         "color":  "110",
                         "w":  989,
                         "y":  26,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  19,
                         "h":  190,
                         "cols":  [
                                      {
                                          "title":  "Import",
                                          "layer":  1,
                                          "w":  82
                                      },
                                      {
                                          "title":  "Date",
                                          "layer":  2,
                                          "w":  113
                                      },
                                      {
                                          "title":  "Rubrique",
                                          "layer":  3,
                                          "w":  129
                                      },
                                      {
                                          "title":  "Dossier",
                                          "layer":  4,
                                          "w":  185
                                      },
                                      {
                                          "title":  "Libellé",
                                          "layer":  5,
                                          "w":  447
                                      }
                                  ],
                         "rows":  5
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  224,
                         "w":  996,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  14,
                         "type":  "edit",
                         "var":  "",
                         "y":  45,
                         "w":  19,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  32,
                         "type":  "edit",
                         "var":  "",
                         "y":  45,
                         "w":  53,
                         "fmt":  "#5PO",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  96,
                         "type":  "edit",
                         "var":  "",
                         "y":  45,
                         "w":  102,
                         "fmt":  "DD/MM/YYYYT",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  208,
                         "type":  "edit",
                         "var":  "",
                         "y":  45,
                         "w":  117,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  520,
                         "type":  "edit",
                         "var":  "",
                         "y":  41,
                         "w":  437,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  520,
                         "type":  "edit",
                         "var":  "",
                         "y":  49,
                         "w":  437,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  6,
                         "type":  "edit",
                         "var":  "",
                         "y":  6,
                         "w":  267,
                         "fmt":  "20",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  789,
                         "type":  "edit",
                         "var":  "",
                         "y":  6,
                         "w":  203,
                         "fmt":  "WWW DD MMM YYYYT",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  336,
                         "type":  "edit",
                         "var":  "",
                         "y":  41,
                         "w":  40,
                         "fmt":  "30",
                         "name":  "",
                         "h":  8,
                         "color":  "146",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  376,
                         "type":  "edit",
                         "var":  "",
                         "y":  41,
                         "w":  135,
                         "fmt":  "30",
                         "name":  "",
                         "h":  8,
                         "color":  "146",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  336,
                         "type":  "edit",
                         "var":  "",
                         "y":  49,
                         "w":  40,
                         "fmt":  "30",
                         "name":  "",
                         "h":  8,
                         "color":  "144",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  376,
                         "type":  "edit",
                         "var":  "",
                         "y":  49,
                         "w":  135,
                         "fmt":  "30",
                         "name":  "",
                         "h":  8,
                         "color":  "144",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  6,
                         "type":  "button",
                         "var":  "",
                         "y":  227,
                         "w":  154,
                         "fmt":  "\u0026Quitter",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  665,
                         "type":  "button",
                         "var":  "",
                         "y":  227,
                         "w":  154,
                         "fmt":  "\u0026Impression",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  834,
                         "type":  "button",
                         "var":  "",
                         "y":  227,
                         "w":  154,
                         "fmt":  "\u0026Visualiser",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "113.2",
    "height":  251
}
-->

<details>
<summary><strong>Champs : 12 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 14,45 | (sans nom) | - | edit |
| 32,45 | #5PO | - | edit |
| 96,45 | DD/MM/YYYYT | - | edit |
| 208,45 | (sans nom) | - | edit |
| 520,41 | (sans nom) | - | edit |
| 520,49 | (sans nom) | - | edit |
| 6,6 | 20 | - | edit |
| 789,6 | WWW DD MMM YYYYT | - | edit |
| 336,41 | 30 | - | edit |
| 376,41 | 30 | - | edit |
| 336,49 | 30 | - | edit |
| 376,49 | 30 | - | edit |

</details>

<details>
<summary><strong>Boutons : 3 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Quitter | 6,227 | Quitte le programme |
| Impression | 665,227 | Appel [   Impression avert. Import (IDE 112)](PBG-IDE-112.md) |
| Visualiser | 834,227 | Bouton fonctionnel |

</details>

## 9. NAVIGATION

Ecran unique: **Affichage Avertissement**

### 9.3 Structure hierarchique (8 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **113.1** | [**Avertissement Import** (113)](#t1) [mockup](#ecran-t1) | MDI | 190x11 | Traitement |
| 113.1.1 | [Visualisation Avertissement (113.2.1)](#t4) [mockup](#ecran-t4) | MDI | 200x8 | |
| 113.1.2 | [Visualisation Code H (113.2.1.1)](#t5) [mockup](#ecran-t5) | MDI | 187x23 | |
| 113.1.3 | [Visualisation Code I (113.2.1.2)](#t6) [mockup](#ecran-t6) | MDI | 232x33 | |
| 113.1.4 | [Visualisation Code J (113.2.1.3)](#t7) [mockup](#ecran-t7) | MDI | 166x14 | |
| 113.1.5 | [Visualisation Sans Code (113.2.1.4)](#t8) [mockup](#ecran-t8) | MDI | 166x18 | |
| **113.2** | [**Verification Affichage** (113.1)](#t2) | MDI | - | Validation |
| **113.3** | [**Affichage Avertissement** (113.2)](#t3) [mockup](#ecran-t3) | MDI | 1002x251 | Consultation |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Affichage Avertissement]
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
| 574 | pv_pms_prestations_tmp | Prestations/services vendus | TMP | R | **W** |   | 2 |

### Colonnes par table (0 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 574 - pv_pms_prestations_tmp (R/**W**) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Autres (5)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P0-Code Choix | Alpha | - |
| B | P0-Code Societe | Alpha | - |
| C | P0-Code Langue | Alpha | - |
| D | W0-Code Suite | Alpha | 2x refs |
| E | W0-Code B031 | Alpha | - |

## 12. EXPRESSIONS

**6 / 6 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONSTANTE | 2 | 0 |
| OTHER | 2 | 0 |
| CONDITION | 2 | 0 |

### 12.2 Expressions cles par type

#### CONSTANTE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 6 | `'B031'` | - |
| CONSTANTE | 3 | `''` | - |

#### OTHER (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 2 | `GetParam ('LANGUE')` | - |
| OTHER | 1 | `GetParam ('SOCIETE')` | - |

#### CONDITION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 5 | `W0-Code Suite [D]='O'` | - |
| CONDITION | 4 | `W0-Code Suite [D]='N'` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Compte Rendu Arrivants (IDE 248)](PBG-IDE-248.md) -> **Avertissement Import (IDE 113)**

```mermaid
graph LR
    T113[113 Avertissement Import]
    style T113 fill:#58a6ff
    CC206[206 Traitement des arr...]
    style CC206 fill:#8b5cf6
    CC248[248 Compte Rendu Arriv...]
    style CC248 fill:#3fb950
    CC206 --> CC248
    CC248 --> T113
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [248](PBG-IDE-248.md) | Compte Rendu Arrivants | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T113[113 Avertissement Import]
    style T113 fill:#58a6ff
    C112[112 Impression avert. ...]
    T113 --> C112
    style C112 fill:#3fb950
    C317[317 Recuperation du titre]
    T113 --> C317
    style C317 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [112](PBG-IDE-112.md) |    Impression avert. Import | 1 | Sous-programme |
| [317](PBG-IDE-317.md) | Recuperation du titre | 1 | Recuperation donnees |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 60 | Programme compact |
| Expressions | 6 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 2 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 60) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (6 taches: 6 ecrans, 0 traitement)

- **Strategie** : 6 composant(s) UI (Razor/React) avec formulaires et validation.
- 2 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Validation (1 tache: 0 ecran, 1 traitement)

- **Strategie** : FluentValidation avec validators specifiques.
- Chaque tache de validation -> un validator injectable

#### Consultation (1 tache: 1 ecran, 0 traitement)

- **Strategie** : Composants de recherche/selection en modales.
- 1 ecran : Affichage Avertissement

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| pv_pms_prestations_tmp | Table WRITE (Temp) | 1x | Schema + repository |
| [Recuperation du titre (IDE 317)](PBG-IDE-317.md) | Sous-programme | 1x | Normale - Recuperation donnees |
| [   Impression avert. Import (IDE 112)](PBG-IDE-112.md) | Sous-programme | 1x | Normale - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 09:28*
