# VIL IDE 83 - Devises toutes sessions

> **Analyse**: Phases 1-4 2026-02-03 09:13 -> 09:13 (19s) | Assemblage 09:13
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | VIL |
| IDE Position | 83 |
| Nom Programme | Devises toutes sessions |
| Fichier source | `Prg_83.xml` |
| Domaine metier | Caisse |
| Taches | 9 (0 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Devises toutes sessions** assure la gestion complete de ce processus, accessible depuis [Update coffre maj (IDE 91)](VIL-IDE-91.md), [Calcul coffre auto avec (IDE 116)](VIL-IDE-116.md), [Update coffre auto (IDE 117)](VIL-IDE-117.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (9 taches) : traitements metier divers

**Donnees modifiees** : 1 tables en ecriture (pv_customer).

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (9 taches)

- **83** - toutes Sessions
- **83.1** - dern session
- **83.2** - Etat de la caisse
- **83.3** - mvt devises
- **83.3.1** - MAJ total de la journee
- **83.4** - Session devise
- **83.4.1** - MAJ total de la journee
- **83.5** - mvt devises
- **83.5.1** - MAJ total de la journee

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| pv_customer | **W** (3 usages) |  |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (9 taches)

Traitements internes.

---

#### <a id="t1"></a>83 - toutes Sessions

**Role** : Tache d'orchestration : point d'entree du programme (9 sous-taches). Coordonne l'enchainement des traitements.

<details>
<summary>8 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [83.1](#t2) | dern session | Traitement |
| [83.2](#t3) | Etat de la caisse | Traitement |
| [83.3](#t4) | mvt devises | Traitement |
| [83.3.1](#t5) | MAJ total de la journee | Traitement |
| [83.4](#t6) | Session devise | Traitement |
| [83.4.1](#t7) | MAJ total de la journee | Traitement |
| [83.5](#t10) | mvt devises | Traitement |
| [83.5.1](#t11) | MAJ total de la journee | Traitement |

</details>

---

#### <a id="t2"></a>83.1 - dern session

**Role** : Traitement : dern session.
**Variables liees** : E (lastSession)

---

#### <a id="t3"></a>83.2 - Etat de la caisse

**Role** : Traitement : Etat de la caisse.

---

#### <a id="t4"></a>83.3 - mvt devises

**Role** : Traitement : mvt devises.

---

#### <a id="t5"></a>83.3.1 - MAJ total de la journee

**Role** : Traitement : MAJ total de la journee.

---

#### <a id="t6"></a>83.4 - Session devise

**Role** : Traitement : Session devise.
**Variables liees** : E (lastSession)

---

#### <a id="t7"></a>83.4.1 - MAJ total de la journee

**Role** : Traitement : MAJ total de la journee.

---

#### <a id="t10"></a>83.5 - mvt devises

**Role** : Traitement : mvt devises.

---

#### <a id="t11"></a>83.5.1 - MAJ total de la journee

**Role** : Traitement : MAJ total de la journee.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Update coffre maj (IDE 91)](VIL-IDE-91.md), [Calcul coffre auto avec (IDE 116)](VIL-IDE-116.md), [Update coffre auto (IDE 117)](VIL-IDE-117.md)
- **Appelle**: 0 programmes | **Tables**: 5 (W:1 R:3 L:1) | **Taches**: 9 | **Expressions**: 4

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (9 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **83.1** | [**toutes Sessions** (83)](#t1) | MDI | - | Traitement |
| 83.1.1 | [dern session (83.1)](#t2) | MDI | - | |
| 83.1.2 | [Etat de la caisse (83.2)](#t3) | MDI | - | |
| 83.1.3 | [mvt devises (83.3)](#t4) | MDI | - | |
| 83.1.4 | [MAJ total de la journee (83.3.1)](#t5) | MDI | - | |
| 83.1.5 | [Session devise (83.4)](#t6) | MDI | - | |
| 83.1.6 | [MAJ total de la journee (83.4.1)](#t7) | MDI | - | |
| 83.1.7 | [mvt devises (83.5)](#t10) | MDI | - | |
| 83.1.8 | [MAJ total de la journee (83.5.1)](#t11) | MDI | - | |

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

### Tables utilisees (5)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 232 | gestion_devise_session | Sessions de caisse | DB | R |   |   | 1 |
| 246 | histo_sessions_caisse | Sessions de caisse | DB | R |   |   | 2 |
| 249 | histo_sessions_caisse_detail | Sessions de caisse | DB | R |   |   | 3 |
| 250 | histo_sessions_caisse_devise | Sessions de caisse | DB |   |   | L | 2 |
| 508 | pv_customer |  | TMP |   | **W** |   | 3 |

### Colonnes par table (2 / 4 tables avec colonnes identifiees)

<details>
<summary>Table 232 - gestion_devise_session (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| E | lastSession | R | Numeric |

</details>

<details>
<summary>Table 246 - histo_sessions_caisse (R) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | PI Coffre2 est actif | R | Alpha |
| B | PI Terminal du coffre2 | R | Numeric |
| C | PI Hostname du coffre2 | R | Unicode |
| D | PI cloture auto est en cours | R | Logical |
| E | lastSession | R | Numeric |
| F | existe ligne F/F | R | Logical |

</details>

<details>
<summary>Table 249 - histo_sessions_caisse_detail (R) - 3 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 508 - pv_customer (**W**) - 3 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (4)

Variables recues du programme appelant ([Update coffre maj (IDE 91)](VIL-IDE-91.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | PI Coffre2 est actif | Alpha | - |
| B | PI Terminal du coffre2 | Numeric | - |
| C | PI Hostname du coffre2 | Unicode | 1x parametre entrant |
| D | PI cloture auto est en cours | Logical | - |

### 11.2 Autres (2)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| E | lastSession | Numeric | - |
| F | existe ligne F/F | Logical | - |

## 12. EXPRESSIONS

**4 / 4 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| OTHER | 1 | 0 |
| NEGATION | 2 | 0 |
| REFERENCE_VG | 1 | 0 |

### 12.2 Expressions cles par type

#### OTHER (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 1 | `[H]` | - |

#### NEGATION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| NEGATION | 3 | `NOT VG39` | - |
| NEGATION | 2 | `NOT ([H]) AND NOT (PI Hostname du coffre2 [C])` | - |

#### REFERENCE_VG (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 4 | `VG39` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Update coffre maj (IDE 91)](VIL-IDE-91.md) -> **Devises toutes sessions (IDE 83)**

Main -> ... -> [Calcul coffre auto avec (IDE 116)](VIL-IDE-116.md) -> **Devises toutes sessions (IDE 83)**

Main -> ... -> [Update coffre auto (IDE 117)](VIL-IDE-117.md) -> **Devises toutes sessions (IDE 83)**

```mermaid
graph LR
    T83[83 Devises toutes sess...]
    style T83 fill:#58a6ff
    CC9[9 Pilotage avant sessions]
    style CC9 fill:#8b5cf6
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC78[78 Lance correspittivi]
    style CC78 fill:#8b5cf6
    CC10[10 Pilotage après sess...]
    style CC10 fill:#f59e0b
    CC148[148 CV Menu caisse vil...]
    style CC148 fill:#f59e0b
    CC161[161 Sortie de devises]
    style CC161 fill:#f59e0b
    CC86[86 Menu gestion caisse]
    style CC86 fill:#f59e0b
    CC100[100 Menu pièces de caisse]
    style CC100 fill:#f59e0b
    CC91[91 Update coffre maj]
    style CC91 fill:#3fb950
    CC116[116 Calcul coffre auto...]
    style CC116 fill:#3fb950
    CC117[117 Update coffre auto]
    style CC117 fill:#3fb950
    CC86 --> CC91
    CC100 --> CC91
    CC161 --> CC91
    CC10 --> CC91
    CC148 --> CC91
    CC86 --> CC116
    CC100 --> CC116
    CC161 --> CC116
    CC10 --> CC116
    CC148 --> CC116
    CC86 --> CC117
    CC100 --> CC117
    CC161 --> CC117
    CC10 --> CC117
    CC148 --> CC117
    CC9 --> CC86
    CC1 --> CC86
    CC78 --> CC86
    CC9 --> CC100
    CC1 --> CC100
    CC78 --> CC100
    CC9 --> CC161
    CC1 --> CC161
    CC78 --> CC161
    CC9 --> CC10
    CC1 --> CC10
    CC78 --> CC10
    CC9 --> CC148
    CC1 --> CC148
    CC78 --> CC148
    CC91 --> T83
    CC116 --> T83
    CC117 --> T83
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [91](VIL-IDE-91.md) | Update coffre maj | 1 |
| [116](VIL-IDE-116.md) | Calcul coffre auto avec | 1 |
| [117](VIL-IDE-117.md) | Update coffre auto | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T83[83 Devises toutes sess...]
    style T83 fill:#58a6ff
    NONE[Aucun callee]
    T83 -.-> NONE
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
| Lignes de logique | 122 | Programme compact |
| Expressions | 4 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 122) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (9 taches: 0 ecran, 9 traitements)

- **Strategie** : 9 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| pv_customer | Table WRITE (Temp) | 3x | Schema + repository |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 09:13*
