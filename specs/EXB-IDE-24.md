# EXB IDE 24 - Imp Liste Participants

> **Analyse**: Phases 1-4 2026-02-03 10:39 -> 10:39 (15s) | Assemblage 10:39
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | EXB |
| IDE Position | 24 |
| Nom Programme | Imp Liste Participants |
| Fichier source | `Prg_24.xml` |
| Domaine metier | General |
| Taches | 8 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Imp Liste Participants** assure la gestion complete de ce processus, accessible depuis [Liste Participant (IDE 23)](EXB-IDE-23.md).

Le flux de traitement s'organise en **2 blocs fonctionnels** :

- **Traitement** (7 taches) : traitements metier divers
- **Impression** (1 tache) : generation de tickets et documents

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (7 taches)

- **24** - Veuillez patienter... **[[ECRAN]](#ecran-t1)**
- **24.2** - Impression
- **24.2.1** - Participants
- **24.2.1.1** - Details
- **24.3** - Impression
- **24.3.1** - Participants
- **24.3.1.1** - Details

#### Phase 2 : Impression (1 tache)

- **24.1** - Choix imprimante

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (7 taches)

Traitements internes.

---

#### <a id="t1"></a>24 - Veuillez patienter... [[ECRAN]](#ecran-t1)

**Role** : Tache d'orchestration : point d'entree du programme (7 sous-taches). Coordonne l'enchainement des traitements.
**Ecran** : 429 x 58 DLU (MDI) | [Voir mockup](#ecran-t1)

<details>
<summary>6 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [24.2](#t3) | Impression | Traitement |
| [24.2.1](#t4) | Participants | Traitement |
| [24.2.1.1](#t5) | Details | Traitement |
| [24.3](#t7) | Impression | Traitement |
| [24.3.1](#t8) | Participants | Traitement |
| [24.3.1.1](#t9) | Details | Traitement |

</details>

---

#### <a id="t3"></a>24.2 - Impression

**Role** : Generation du document : Impression.

---

#### <a id="t4"></a>24.2.1 - Participants

**Role** : Traitement : Participants.

---

#### <a id="t5"></a>24.2.1.1 - Details

**Role** : Traitement : Details.

---

#### <a id="t7"></a>24.3 - Impression

**Role** : Generation du document : Impression.

---

#### <a id="t8"></a>24.3.1 - Participants

**Role** : Traitement : Participants.

---

#### <a id="t9"></a>24.3.1.1 - Details

**Role** : Traitement : Details.


### 3.2 Impression (1 tache)

Generation des documents et tickets.

---

#### <a id="t2"></a>24.1 - Choix imprimante

**Role** : Selection par l'operateur : Choix imprimante.
**Variables liees** : H (W0 choix imprimante)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Liste Participant (IDE 23)](EXB-IDE-23.md)
- **Appelle**: 0 programmes | **Tables**: 9 (W:0 R:4 L:5) | **Taches**: 8 | **Expressions**: 2

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (8 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **24.1** | [**Veuillez patienter...** (24)](#t1) [mockup](#ecran-t1) | MDI | 429x58 | Traitement |
| 24.1.1 | [Impression (24.2)](#t3) | MDI | - | |
| 24.1.2 | [Participants (24.2.1)](#t4) | MDI | - | |
| 24.1.3 | [Details (24.2.1.1)](#t5) | MDI | - | |
| 24.1.4 | [Impression (24.3)](#t7) | MDI | - | |
| 24.1.5 | [Participants (24.3.1)](#t8) | MDI | - | |
| 24.1.6 | [Details (24.3.1.1)](#t9) | MDI | - | |
| **24.2** | [**Choix imprimante** (24.1)](#t2) | MDI | - | Impression |

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
| 24 | imprimante_______prn |  | DB | R |   |   | 1 |
| 34 | hebergement______heb | Hebergement (chambres) | DB |   |   | L | 2 |
| 102 | logement_go______lop |  | DB |   |   | L | 2 |
| 103 | logement_client__loc |  | DB |   |   | L | 2 |
| 298 | participants_____par |  | DB | R |   |   | 2 |
| 299 | excurs_planning__epl |  | DB | R |   |   | 2 |
| 300 | excursions_______exc |  | DB |   |   | L | 2 |
| 301 | details_partici__dpa |  | DB | R |   |   | 2 |
| 304 | tables_divers____tad |  | DB |   |   | L | 2 |

### Colonnes par table (3 / 4 tables avec colonnes identifiees)

<details>
<summary>Table 24 - imprimante_______prn (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| H | W0 choix imprimante | R | Numeric |

</details>

<details>
<summary>Table 298 - participants_____par (R) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | W2 date debut | R | Alpha |
| B | W2 date fin | R | Alpha |

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

Variables recues du programme appelant ([Liste Participant (IDE 23)](EXB-IDE-23.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P0 nom village | Alpha | - |
| B | P0 masque montant | Alpha | - |
| C | P0 type | Alpha | - |
| G | P0 option | Alpha | - |

### 11.2 Variables de travail (1)

Variables internes au programme.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| H | W0 choix imprimante | Numeric | - |

### 11.3 Autres (3)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| D | P0_Code | Numeric | - |
| E | P0_Date | Date | - |
| F | P0_Excursion | Alpha | - |

## 12. EXPRESSIONS

**2 / 2 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| OTHER | 2 | 0 |

### 12.2 Expressions cles par type

#### OTHER (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 2 | `SetCrsr (1)` | - |
| OTHER | 1 | `SetCrsr (2)` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Liste Participant (IDE 23)](EXB-IDE-23.md) -> **Imp Liste Participants (IDE 24)**

```mermaid
graph LR
    T24[24 Imp Liste Participants]
    style T24 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC31[31 Menu general]
    style CC31 fill:#f59e0b
    CC19[19 Menu editions]
    style CC19 fill:#f59e0b
    CC23[23 Liste Participant]
    style CC23 fill:#3fb950
    CC19 --> CC23
    CC31 --> CC19
    CC1 --> CC31
    CC23 --> T24
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [23](EXB-IDE-23.md) | Liste Participant | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T24[24 Imp Liste Participants]
    style T24 fill:#58a6ff
    NONE[Aucun callee]
    T24 -.-> NONE
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
| Lignes de logique | 198 | Programme compact |
| Expressions | 2 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 198) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (7 taches: 1 ecran, 6 traitements)

- **Strategie** : Orchestrateur avec 1 ecrans (Razor/React) et 6 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- Decomposer les taches en services unitaires testables.

#### Impression (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Templates HTML -> PDF via wkhtmltopdf ou Puppeteer.
- `PrintService` injectable avec choix imprimante

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 10:39*
