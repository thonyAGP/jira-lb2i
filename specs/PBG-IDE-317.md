# PBG IDE 317 - Recuperation du titre

> **Analyse**: Phases 1-4 2026-02-03 11:06 -> 11:06 (19s) | Assemblage 11:06
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBG |
| IDE Position | 317 |
| Nom Programme | Recuperation du titre |
| Fichier source | `Prg_317.xml` |
| Dossier IDE | General |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Recuperation du titre** assure la gestion complete de ce processus, accessible depuis [Validation Arrivants (IDE 124)](PBG-IDE-124.md), [Logement Client (IDE 0)](PBG-IDE-0.md), [Creation clients Identite (IDE 87)](PBG-IDE-87.md), [Logement Client (IDE 173)](PBG-IDE-173.md), [Logement Client pms-626 (IDE 174)](PBG-IDE-174.md), [Creation clients Identite SAV (IDE 379)](PBG-IDE-379.md), [Creation clients Identite P185 (IDE 382)](PBG-IDE-382.md), [Creation clients Identite PROD (IDE 383)](PBG-IDE-383.md), [Creation clients Identite en c (IDE 384)](PBG-IDE-384.md), [Logement Client (IDE 385)](PBG-IDE-385.md), [Creation clients Identite SAV* (IDE 386)](PBG-IDE-386.md), [Creation clients Identite_sav (IDE 387)](PBG-IDE-387.md), [Logement Personnel (IDE 0)](PBG-IDE-0.md), [Module des Prestations (IDE 75)](PBG-IDE-75.md), [Module des Circuits (IDE 76)](PBG-IDE-76.md), [Modules clients Identite (IDE 91)](PBG-IDE-91.md), [Create TAI GM (IDE 97)](PBG-IDE-97.md), [Recherche Logement (IDE 119)](PBG-IDE-119.md), [Logement Personnel (IDE 172)](PBG-IDE-172.md), [Traitement Import Personnel (IDE 290)](PBG-IDE-290.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>317 - Recuperation du titre

**Role** : Consultation/chargement : Recuperation du titre.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Validation Arrivants (IDE 124)](PBG-IDE-124.md), [Logement Client (IDE 0)](PBG-IDE-0.md), [Creation clients Identite (IDE 87)](PBG-IDE-87.md), [Logement Client (IDE 173)](PBG-IDE-173.md), [Logement Client pms-626 (IDE 174)](PBG-IDE-174.md), [Creation clients Identite SAV (IDE 379)](PBG-IDE-379.md), [Creation clients Identite P185 (IDE 382)](PBG-IDE-382.md), [Creation clients Identite PROD (IDE 383)](PBG-IDE-383.md), [Creation clients Identite en c (IDE 384)](PBG-IDE-384.md), [Logement Client (IDE 385)](PBG-IDE-385.md), [Creation clients Identite SAV* (IDE 386)](PBG-IDE-386.md), [Creation clients Identite_sav (IDE 387)](PBG-IDE-387.md), [Logement Personnel (IDE 0)](PBG-IDE-0.md), [Module des Prestations (IDE 75)](PBG-IDE-75.md), [Module des Circuits (IDE 76)](PBG-IDE-76.md), [Modules clients Identite (IDE 91)](PBG-IDE-91.md), [Create TAI GM (IDE 97)](PBG-IDE-97.md), [Recherche Logement (IDE 119)](PBG-IDE-119.md), [Logement Personnel (IDE 172)](PBG-IDE-172.md), [Traitement Import Personnel (IDE 290)](PBG-IDE-290.md)
- **Appelle**: 0 programmes | **Tables**: 1 (W:0 R:1 L:0) | **Taches**: 1 | **Expressions**: 4

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **317.1** | [**Recuperation du titre** (317)](#t1) | MDI | - | Traitement |

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

### Tables utilisees (1)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 719 | arc_transac_detail_bar |  | DB | R |   |   | 1 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 719 - arc_transac_detail_bar (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | > code ecran | R | Numeric |
| B | < nom ecran | R | Alpha |

</details>

## 11. VARIABLES

### 11.1 Autres (2)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | > code ecran | Numeric | 1x refs |
| B | < nom ecran | Alpha | - |

## 12. EXPRESSIONS

**4 / 4 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONCATENATION | 1 | 0 |
| CONSTANTE | 1 | 0 |
| OTHER | 1 | 0 |
| CONDITION | 1 | 0 |

### 12.2 Expressions cles par type

#### CONCATENATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 4 | `Trim (INIGet ('[MAGIC_LOGICAL_NAMES]club_front_back'))&' - '&Trim ([F])&' - '&Trim ([G])` | - |

#### CONSTANTE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 3 | `'PB'` | - |

#### OTHER (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 1 | `GetParam ('CODELANGUE')` | - |

#### CONDITION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 2 | `> code ecran [A]` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Validation Arrivants (IDE 124)](PBG-IDE-124.md) -> **Recuperation du titre (IDE 317)**

Main -> ... -> [Logement Client (IDE 0)](PBG-IDE-0.md) -> **Recuperation du titre (IDE 317)**

Main -> ... -> [Creation clients Identite (IDE 87)](PBG-IDE-87.md) -> **Recuperation du titre (IDE 317)**

Main -> ... -> [Logement Client (IDE 173)](PBG-IDE-173.md) -> **Recuperation du titre (IDE 317)**

Main -> ... -> [Logement Client pms-626 (IDE 174)](PBG-IDE-174.md) -> **Recuperation du titre (IDE 317)**

Main -> ... -> [Creation clients Identite SAV (IDE 379)](PBG-IDE-379.md) -> **Recuperation du titre (IDE 317)**

Main -> ... -> [Creation clients Identite P185 (IDE 382)](PBG-IDE-382.md) -> **Recuperation du titre (IDE 317)**

Main -> ... -> [Creation clients Identite PROD (IDE 383)](PBG-IDE-383.md) -> **Recuperation du titre (IDE 317)**

Main -> ... -> [Creation clients Identite en c (IDE 384)](PBG-IDE-384.md) -> **Recuperation du titre (IDE 317)**

Main -> ... -> [Logement Client (IDE 385)](PBG-IDE-385.md) -> **Recuperation du titre (IDE 317)**

Main -> ... -> [Creation clients Identite SAV* (IDE 386)](PBG-IDE-386.md) -> **Recuperation du titre (IDE 317)**

Main -> ... -> [Creation clients Identite_sav (IDE 387)](PBG-IDE-387.md) -> **Recuperation du titre (IDE 317)**

Main -> ... -> [Logement Personnel (IDE 0)](PBG-IDE-0.md) -> **Recuperation du titre (IDE 317)**

Main -> ... -> [Module des Prestations (IDE 75)](PBG-IDE-75.md) -> **Recuperation du titre (IDE 317)**

Main -> ... -> [Module des Circuits (IDE 76)](PBG-IDE-76.md) -> **Recuperation du titre (IDE 317)**

Main -> ... -> [Modules clients Identite (IDE 91)](PBG-IDE-91.md) -> **Recuperation du titre (IDE 317)**

Main -> ... -> [Create TAI GM (IDE 97)](PBG-IDE-97.md) -> **Recuperation du titre (IDE 317)**

Main -> ... -> [Recherche Logement (IDE 119)](PBG-IDE-119.md) -> **Recuperation du titre (IDE 317)**

Main -> ... -> [Logement Personnel (IDE 172)](PBG-IDE-172.md) -> **Recuperation du titre (IDE 317)**

Main -> ... -> [Traitement Import Personnel (IDE 290)](PBG-IDE-290.md) -> **Recuperation du titre (IDE 317)**

```mermaid
graph LR
    T317[317 Recuperation du titre]
    style T317 fill:#58a6ff
    CALLER124[124 Validation Arrivants]
    CALLER124 --> T317
    style CALLER124 fill:#3fb950
    CALLER87[87 Creation clients Id...]
    CALLER87 --> T317
    style CALLER87 fill:#3fb950
    CALLER173[173 Logement Client]
    CALLER173 --> T317
    style CALLER173 fill:#3fb950
    CALLER174[174 Logement Client pm...]
    CALLER174 --> T317
    style CALLER174 fill:#3fb950
    CALLER379[379 Creation clients I...]
    CALLER379 --> T317
    style CALLER379 fill:#3fb950
    CALLER382[382 Creation clients I...]
    CALLER382 --> T317
    style CALLER382 fill:#3fb950
    CALLER383[383 Creation clients I...]
    CALLER383 --> T317
    style CALLER383 fill:#3fb950
    CALLER384[384 Creation clients I...]
    CALLER384 --> T317
    style CALLER384 fill:#3fb950
    CALLER385[385 Logement Client]
    CALLER385 --> T317
    style CALLER385 fill:#3fb950
    CALLER386[386 Creation clients I...]
    CALLER386 --> T317
    style CALLER386 fill:#3fb950
    CALLER387[387 Creation clients I...]
    CALLER387 --> T317
    style CALLER387 fill:#3fb950
    CALLER75[75 Module des Prestations]
    CALLER75 --> T317
    style CALLER75 fill:#3fb950
    CALLER76[76 Module des Circuits]
    CALLER76 --> T317
    style CALLER76 fill:#3fb950
    CALLER91[91 Modules clients Ide...]
    CALLER91 --> T317
    style CALLER91 fill:#3fb950
    CALLER97[97 Create TAI GM]
    CALLER97 --> T317
    style CALLER97 fill:#3fb950
    CALLER119[119 Recherche Logement]
    CALLER119 --> T317
    style CALLER119 fill:#3fb950
    CALLER172[172 Logement Personnel]
    CALLER172 --> T317
    style CALLER172 fill:#3fb950
    CALLER290[290 Traitement Import ...]
    CALLER290 --> T317
    style CALLER290 fill:#3fb950
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [124](PBG-IDE-124.md) | Validation Arrivants | 7 |
| [0](PBG-IDE-0.md) | Logement Client | 3 |
| [87](PBG-IDE-87.md) | Creation clients Identite | 3 |
| [173](PBG-IDE-173.md) | Logement Client | 3 |
| [174](PBG-IDE-174.md) | Logement Client pms-626 | 3 |
| [379](PBG-IDE-379.md) | Creation clients Identite SAV | 3 |
| [382](PBG-IDE-382.md) | Creation clients Identite P185 | 3 |
| [383](PBG-IDE-383.md) | Creation clients Identite PROD | 3 |
| [384](PBG-IDE-384.md) | Creation clients Identite en c | 3 |
| [385](PBG-IDE-385.md) | Logement Client | 3 |
| [386](PBG-IDE-386.md) | Creation clients Identite SAV* | 3 |
| [387](PBG-IDE-387.md) | Creation clients Identite_sav | 3 |
| [0](PBG-IDE-0.md) | Logement Personnel | 2 |
| [75](PBG-IDE-75.md) | Module des Prestations | 2 |
| [76](PBG-IDE-76.md) | Module des Circuits | 2 |
| [91](PBG-IDE-91.md) | Modules clients Identite | 2 |
| [97](PBG-IDE-97.md) | Create TAI GM | 2 |
| [119](PBG-IDE-119.md) | Recherche Logement | 2 |
| [172](PBG-IDE-172.md) | Logement Personnel | 2 |
| [290](PBG-IDE-290.md) | Traitement Import Personnel | 2 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T317[317 Recuperation du titre]
    style T317 fill:#58a6ff
    NONE[Aucun callee]
    T317 -.-> NONE
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
| Expressions | 4 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 12) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 0 ecran, 1 traitement)

- **Strategie** : 1 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 11:06*
