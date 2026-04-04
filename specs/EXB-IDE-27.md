# EXB IDE 27 - Imp Detail Excursion

> **Analyse**: Phases 1-4 2026-02-03 10:40 -> 10:40 (14s) | Assemblage 10:41
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | EXB |
| IDE Position | 27 |
| Nom Programme | Imp Detail Excursion |
| Fichier source | `Prg_27.xml` |
| Domaine metier | General |
| Taches | 7 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Imp Detail Excursion** assure la gestion complete de ce processus, accessible depuis [Detail Excursion (IDE 26)](EXB-IDE-26.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (7 taches) : traitements metier divers

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (7 taches)

- **27** - Veuillez patienter... **[[ECRAN]](#ecran-t1)**
- **27.1** - Impression
- **27.1.1** - Participants
- **27.1.1.1** - Details
- **27.2** - Impression
- **27.2.1** - Participants
- **27.2.1.1** - Details

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (7 taches)

Traitements internes.

---

#### <a id="t1"></a>27 - Veuillez patienter... [[ECRAN]](#ecran-t1)

**Role** : Tache d'orchestration : point d'entree du programme (7 sous-taches). Coordonne l'enchainement des traitements.
**Ecran** : 434 x 60 DLU (MDI) | [Voir mockup](#ecran-t1)

<details>
<summary>6 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [27.1](#t3) | Impression | Traitement |
| [27.1.1](#t4) | Participants | Traitement |
| [27.1.1.1](#t5) | Details | Traitement |
| [27.2](#t6) | Impression | Traitement |
| [27.2.1](#t7) | Participants | Traitement |
| [27.2.1.1](#t8) | Details | Traitement |

</details>

---

#### <a id="t3"></a>27.1 - Impression

**Role** : Generation du document : Impression.

---

#### <a id="t4"></a>27.1.1 - Participants

**Role** : Traitement : Participants.

---

#### <a id="t5"></a>27.1.1.1 - Details

**Role** : Traitement : Details.

---

#### <a id="t6"></a>27.2 - Impression

**Role** : Generation du document : Impression.

---

#### <a id="t7"></a>27.2.1 - Participants

**Role** : Traitement : Participants.

---

#### <a id="t8"></a>27.2.1.1 - Details

**Role** : Traitement : Details.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Detail Excursion (IDE 26)](EXB-IDE-26.md)
- **Appelle**: 0 programmes | **Tables**: 9 (W:0 R:3 L:6) | **Taches**: 7 | **Expressions**: 8

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (7 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **27.1** | [**Veuillez patienter...** (27)](#t1) [mockup](#ecran-t1) | MDI | 434x60 | Traitement |
| 27.1.1 | [Impression (27.1)](#t3) | MDI | - | |
| 27.1.2 | [Participants (27.1.1)](#t4) | MDI | - | |
| 27.1.3 | [Details (27.1.1.1)](#t5) | MDI | - | |
| 27.1.4 | [Impression (27.2)](#t6) | MDI | - | |
| 27.1.5 | [Participants (27.2.1)](#t7) | MDI | - | |
| 27.1.6 | [Details (27.2.1.1)](#t8) | MDI | - | |

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

### Tables utilisees (9)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 30 | gm-recherche_____gmr | Index de recherche | DB |   |   | L | 1 |
| 34 | hebergement______heb | Hebergement (chambres) | DB |   |   | L | 2 |
| 102 | logement_go______lop |  | DB |   |   | L | 2 |
| 103 | logement_client__loc |  | DB |   |   | L | 2 |
| 298 | participants_____par |  | DB | R |   |   | 2 |
| 299 | excurs_planning__epl |  | DB | R |   |   | 2 |
| 300 | excursions_______exc |  | DB |   |   | L | 2 |
| 301 | details_partici__dpa |  | DB | R |   |   | 2 |
| 304 | tables_divers____tad |  | DB |   |   | L | 2 |

### Colonnes par table (2 / 3 tables avec colonnes identifiees)

<details>
<summary>Table 298 - participants_____par (R) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | W2 TOTAL GO | R | Numeric |
| B | W2 GM | R | Numeric |
| C | W2 AUTRE | R | Numeric |
| D | W2 NB GO | R | Numeric |
| E | W2 NB GM | R | Numeric |
| F | W2 NB AUTRE | R | Numeric |

</details>

<details>
<summary>Table 299 - excurs_planning__epl (R) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | W1 chaine | R | Alpha |
| B | W1_Compteur | R | Numeric |

</details>

<details>
<summary>Table 301 - details_partici__dpa (R) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (4)

Variables recues du programme appelant ([Detail Excursion (IDE 26)](EXB-IDE-26.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P0 nom village | Alpha | - |
| B | P0 masque montant | Alpha | 1x parametre entrant |
| C | P0 type | Alpha | - |
| G | P0 option | Alpha | - |

### 11.2 Autres (3)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| D | P0_Code | Numeric | - |
| E | P0_Date | Date | - |
| F | P0_Excursion | Alpha | - |

## 12. EXPRESSIONS

**8 / 8 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONSTANTE | 2 | 0 |
| DATE | 1 | 0 |
| OTHER | 4 | 0 |
| CONDITION | 1 | 0 |

### 12.2 Expressions cles par type

#### CONSTANTE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 6 | `'1'` | - |
| CONSTANTE | 5 | `'SERVICE EXCURSION'` | - |

#### DATE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| DATE | 1 | `Date ()` | - |

#### OTHER (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 4 | `{1,5}` | - |
| OTHER | 7 | `P0 masque montant [B]` | - |
| OTHER | 2 | `{1,3}` | - |
| OTHER | 3 | `{1,4}` | - |

#### CONDITION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 8 | `INIGet ('[MAGIC_LOGICAL_NAMES]preview')='O'` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Detail Excursion (IDE 26)](EXB-IDE-26.md) -> **Imp Detail Excursion (IDE 27)**

```mermaid
graph LR
    T27[27 Imp Detail Excursion]
    style T27 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC31[31 Menu general]
    style CC31 fill:#f59e0b
    CC19[19 Menu editions]
    style CC19 fill:#f59e0b
    CC26[26 Detail Excursion]
    style CC26 fill:#3fb950
    CC19 --> CC26
    CC31 --> CC19
    CC1 --> CC31
    CC26 --> T27
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [26](EXB-IDE-26.md) | Detail Excursion | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T27[27 Imp Detail Excursion]
    style T27 fill:#58a6ff
    NONE[Aucun callee]
    T27 -.-> NONE
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
| Lignes de logique | 213 | Taille moyenne |
| Expressions | 8 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 213) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (7 taches: 1 ecran, 6 traitements)

- **Strategie** : Orchestrateur avec 1 ecrans (Razor/React) et 6 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 10:41*
