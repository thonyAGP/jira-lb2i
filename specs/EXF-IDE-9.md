# EXF IDE 9 - Transporteur new

> **Analyse**: Phases 1-4 2026-02-03 10:53 -> 10:53 (16s) | Assemblage 10:53
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | EXF |
| IDE Position | 9 |
| Nom Programme | Transporteur new |
| Fichier source | `Prg_9.xml` |
| Dossier IDE | General |
| Taches | 27 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 1 |

## 2. DESCRIPTION FONCTIONNELLE

**Transporteur new** assure la gestion complete de ce processus, accessible depuis [Disponibilites@ verif stat (IDE 10)](EXF-IDE-10.md).

Le flux de traitement s'organise en **2 blocs fonctionnels** :

- **Traitement** (22 taches) : traitements metier divers
- **Impression** (5 taches) : generation de tickets et documents

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (22 taches)

- **9** - Veuillez patienter... **[[ECRAN]](#ecran-t1)**
- **9.1.1** - Impression
- **9.1.1.1** - Participants
- **9.1.1.1.1** - Details
- **9.1.2** - Impression
- **9.1.2.1** - Participants
- **9.1.2.1.1** - Details
- **9.2.1** - Impression
- **9.2.1.1** - Participants
- **9.2.1.1.1** - Details
- **9.2.2** - Impression
- **9.2.2.1** - Participants
- **9.2.2.1.1** - Details
- **9.3.1** - Impression
- **9.3.1.1** - Participants
- **9.3.1.1.1** - Details
- **9.4.1** - Impression
- **9.4.1.1** - Participants
- **9.4.1.1.1** - Details
- **9.5.1** - Impression
- **9.5.1.1** - Participants
- **9.5.1.1.1** - Details

#### Phase 2 : Impression (5 taches)

- **9.1** - Printer 1
- **9.2** - Printer 4
- **9.3** - Printer 6
- **9.4** - Printer 8
- **9.5** - Printer 9

Delegue a : [Raz Current Printer (IDE 20)](EXF-IDE-20.md)

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (22 taches)

Traitements internes.

---

#### <a id="t1"></a>9 - Veuillez patienter... [[ECRAN]](#ecran-t1)

**Role** : Tache d'orchestration : point d'entree du programme (22 sous-taches). Coordonne l'enchainement des traitements.
**Ecran** : 430 x 61 DLU (MDI) | [Voir mockup](#ecran-t1)

<details>
<summary>21 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [9.1.1](#t4) | Impression | Traitement |
| [9.1.1.1](#t5) | Participants | Traitement |
| [9.1.1.1.1](#t6) | Details | Traitement |
| [9.1.2](#t7) | Impression | Traitement |
| [9.1.2.1](#t8) | Participants | Traitement |
| [9.1.2.1.1](#t9) | Details | Traitement |
| [9.2.1](#t11) | Impression | Traitement |
| [9.2.1.1](#t12) | Participants | Traitement |
| [9.2.1.1.1](#t13) | Details | Traitement |
| [9.2.2](#t14) | Impression | Traitement |
| [9.2.2.1](#t15) | Participants | Traitement |
| [9.2.2.1.1](#t16) | Details | Traitement |
| [9.3.1](#t18) | Impression | Traitement |
| [9.3.1.1](#t19) | Participants | Traitement |
| [9.3.1.1.1](#t20) | Details | Traitement |
| [9.4.1](#t26) | Impression | Traitement |
| [9.4.1.1](#t27) | Participants | Traitement |
| [9.4.1.1.1](#t28) | Details | Traitement |
| [9.5.1](#t30) | Impression | Traitement |
| [9.5.1.1](#t31) | Participants | Traitement |
| [9.5.1.1.1](#t32) | Details | Traitement |

</details>

---

#### <a id="t4"></a>9.1.1 - Impression

**Role** : Generation du document : Impression.

---

#### <a id="t5"></a>9.1.1.1 - Participants

**Role** : Traitement : Participants.

---

#### <a id="t6"></a>9.1.1.1.1 - Details

**Role** : Traitement : Details.

---

#### <a id="t7"></a>9.1.2 - Impression

**Role** : Generation du document : Impression.

---

#### <a id="t8"></a>9.1.2.1 - Participants

**Role** : Traitement : Participants.

---

#### <a id="t9"></a>9.1.2.1.1 - Details

**Role** : Traitement : Details.

---

#### <a id="t11"></a>9.2.1 - Impression

**Role** : Generation du document : Impression.

---

#### <a id="t12"></a>9.2.1.1 - Participants

**Role** : Traitement : Participants.

---

#### <a id="t13"></a>9.2.1.1.1 - Details

**Role** : Traitement : Details.

---

#### <a id="t14"></a>9.2.2 - Impression

**Role** : Generation du document : Impression.

---

#### <a id="t15"></a>9.2.2.1 - Participants

**Role** : Traitement : Participants.

---

#### <a id="t16"></a>9.2.2.1.1 - Details

**Role** : Traitement : Details.

---

#### <a id="t18"></a>9.3.1 - Impression

**Role** : Generation du document : Impression.

---

#### <a id="t19"></a>9.3.1.1 - Participants

**Role** : Traitement : Participants.

---

#### <a id="t20"></a>9.3.1.1.1 - Details

**Role** : Traitement : Details.

---

#### <a id="t26"></a>9.4.1 - Impression

**Role** : Generation du document : Impression.

---

#### <a id="t27"></a>9.4.1.1 - Participants

**Role** : Traitement : Participants.

---

#### <a id="t28"></a>9.4.1.1.1 - Details

**Role** : Traitement : Details.

---

#### <a id="t30"></a>9.5.1 - Impression

**Role** : Generation du document : Impression.

---

#### <a id="t31"></a>9.5.1.1 - Participants

**Role** : Traitement : Participants.

---

#### <a id="t32"></a>9.5.1.1.1 - Details

**Role** : Traitement : Details.


### 3.2 Impression (5 taches)

Generation des documents et tickets.

---

#### <a id="t3"></a>9.1 - Printer 1

**Role** : Generation du document : Printer 1.
**Delegue a** : [Raz Current Printer (IDE 20)](EXF-IDE-20.md)

---

#### <a id="t10"></a>9.2 - Printer 4

**Role** : Generation du document : Printer 4.
**Delegue a** : [Raz Current Printer (IDE 20)](EXF-IDE-20.md)

---

#### <a id="t17"></a>9.3 - Printer 6

**Role** : Generation du document : Printer 6.
**Delegue a** : [Raz Current Printer (IDE 20)](EXF-IDE-20.md)

---

#### <a id="t25"></a>9.4 - Printer 8

**Role** : Generation du document : Printer 8.
**Delegue a** : [Raz Current Printer (IDE 20)](EXF-IDE-20.md)

---

#### <a id="t29"></a>9.5 - Printer 9

**Role** : Generation du document : Printer 9.
**Delegue a** : [Raz Current Printer (IDE 20)](EXF-IDE-20.md)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Disponibilites@ verif stat (IDE 10)](EXF-IDE-10.md)
- **Appelle**: 1 programmes | **Tables**: 8 (W:0 R:3 L:5) | **Taches**: 27 | **Expressions**: 10

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (27 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **9.1** | [**Veuillez patienter...** (9)](#t1) [mockup](#ecran-t1) | MDI | 430x61 | Traitement |
| 9.1.1 | [Impression (9.1.1)](#t4) | MDI | - | |
| 9.1.2 | [Participants (9.1.1.1)](#t5) | MDI | - | |
| 9.1.3 | [Details (9.1.1.1.1)](#t6) | MDI | - | |
| 9.1.4 | [Impression (9.1.2)](#t7) | MDI | - | |
| 9.1.5 | [Participants (9.1.2.1)](#t8) | MDI | - | |
| 9.1.6 | [Details (9.1.2.1.1)](#t9) | MDI | - | |
| 9.1.7 | [Impression (9.2.1)](#t11) | MDI | - | |
| 9.1.8 | [Participants (9.2.1.1)](#t12) | MDI | - | |
| 9.1.9 | [Details (9.2.1.1.1)](#t13) | MDI | - | |
| 9.1.10 | [Impression (9.2.2)](#t14) | MDI | - | |
| 9.1.11 | [Participants (9.2.2.1)](#t15) | MDI | - | |
| 9.1.12 | [Details (9.2.2.1.1)](#t16) | MDI | - | |
| 9.1.13 | [Impression (9.3.1)](#t18) | MDI | - | |
| 9.1.14 | [Participants (9.3.1.1)](#t19) | MDI | - | |
| 9.1.15 | [Details (9.3.1.1.1)](#t20) | MDI | - | |
| 9.1.16 | [Impression (9.4.1)](#t26) | MDI | - | |
| 9.1.17 | [Participants (9.4.1.1)](#t27) | MDI | - | |
| 9.1.18 | [Details (9.4.1.1.1)](#t28) | MDI | - | |
| 9.1.19 | [Impression (9.5.1)](#t30) | MDI | - | |
| 9.1.20 | [Participants (9.5.1.1)](#t31) | MDI | - | |
| 9.1.21 | [Details (9.5.1.1.1)](#t32) | MDI | - | |
| **9.2** | [**Printer 1** (9.1)](#t3) | MDI | - | Impression |
| 9.2.1 | [Printer 4 (9.2)](#t10) | MDI | - | |
| 9.2.2 | [Printer 6 (9.3)](#t17) | MDI | - | |
| 9.2.3 | [Printer 8 (9.4)](#t25) | MDI | - | |
| 9.2.4 | [Printer 9 (9.5)](#t29) | MDI | - | |

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

### Tables utilisees (8)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 34 | hebergement______heb | Hebergement (chambres) | DB |   |   | L | 7 |
| 102 | logement_go______lop |  | DB |   |   | L | 7 |
| 103 | logement_client__loc |  | DB |   |   | L | 7 |
| 298 | participants_____par |  | DB | R |   |   | 7 |
| 299 | excurs_planning__epl |  | DB | R |   |   | 7 |
| 300 | excursions_______exc |  | DB |   |   | L | 7 |
| 301 | details_partici__dpa |  | DB | R |   |   | 7 |
| 304 | tables_divers____tad |  | DB |   |   | L | 7 |

### Colonnes par table (2 / 3 tables avec colonnes identifiees)

<details>
<summary>Table 298 - participants_____par (R) - 7 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | W2 date debut | R | Alpha |
| B | W2 date fin | R | Alpha |

</details>

<details>
<summary>Table 299 - excurs_planning__epl (R) - 7 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | W1 chaine | R | Alpha |
| B | W1_Compteur | R | Numeric |

</details>

<details>
<summary>Table 301 - details_partici__dpa (R) - 7 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (4)

Variables recues du programme appelant ([Disponibilites@ verif stat (IDE 10)](EXF-IDE-10.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P0 nom village | Alpha | - |
| B | P0 masque montant | Alpha | - |
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

**10 / 10 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| OTHER | 3 | 0 |
| CONDITION | 6 | 0 |
| CAST_LOGIQUE | 1 | 0 |

### 12.2 Expressions cles par type

#### OTHER (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 10 | `SetParam ('CURRENTPAGENUMBER',0)` | - |
| OTHER | 2 | `SetCrsr (1)` | - |
| OTHER | 1 | `SetCrsr (2)` | - |

#### CONDITION (6 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 6 | `GetParam ('CURRENTPRINTERNUM')=8` | - |
| CONDITION | 7 | `GetParam ('CURRENTPRINTERNUM')=9` | - |
| CONDITION | 9 | `Counter (0)>=GetParam ('NUMBERCOPIES')` | - |
| CONDITION | 3 | `GetParam ('CURRENTPRINTERNUM')=1` | - |
| CONDITION | 4 | `GetParam ('CURRENTPRINTERNUM')=4` | - |
| ... | | *+1 autres* | |

#### CAST_LOGIQUE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 8 | `'TRUE'LOG` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Disponibilites@ verif stat (IDE 10)](EXF-IDE-10.md) -> **Transporteur new (IDE 9)**

```mermaid
graph LR
    T9[9 Transporteur new]
    style T9 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC13[13 Menu ventes]
    style CC13 fill:#f59e0b
    CC10[10 Disponibilites@ ver...]
    style CC10 fill:#3fb950
    CC13 --> CC10
    CC1 --> CC13
    CC10 --> T9
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [10](EXF-IDE-10.md) | Disponibilites@ verif stat | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T9[9 Transporteur new]
    style T9 fill:#58a6ff
    C20[20 Raz Current Printer]
    T9 --> C20
    style C20 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [20](EXF-IDE-20.md) | Raz Current Printer | 1 | Impression ticket/document |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 664 | Programme volumineux |
| Expressions | 10 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 1 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 664) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (22 taches: 1 ecran, 21 traitements)

- **Strategie** : Orchestrateur avec 1 ecrans (Razor/React) et 21 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 1 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Impression (5 taches: 0 ecran, 5 traitements)

- **Strategie** : Templates HTML -> PDF via wkhtmltopdf ou Puppeteer.
- `PrintService` injectable avec choix imprimante

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| [Raz Current Printer (IDE 20)](EXF-IDE-20.md) | Sous-programme | 1x | Normale - Impression ticket/document |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 10:53*
