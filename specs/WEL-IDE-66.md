# WEL IDE 66 - Avancement Personnel

> **Analyse**: Phases 1-4 2026-02-03 21:33 -> 21:33 (10s) | Assemblage 21:33
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | WEL |
| IDE Position | 66 |
| Nom Programme | Avancement Personnel |
| Fichier source | `Prg_66.xml` |
| Dossier IDE | Sejour |
| Taches | 14 (0 ecrans visibles) |
| Tables modifiees | 5 |
| Programmes appeles | 7 |

## 2. DESCRIPTION FONCTIONNELLE

**Avancement Personnel** assure la gestion complete de ce processus, accessible depuis [Clients (IDE 9)](WEL-IDE-9.md).

Le flux de traitement s'organise en **4 blocs fonctionnels** :

- **Traitement** (11 taches) : traitements metier divers
- **Validation** (1 tache) : controles et verifications de coherence
- **Creation** (1 tache) : insertion d'enregistrements en base (mouvements, prestations)
- **Saisie** (1 tache) : ecrans de saisie utilisateur (formulaires, champs, donnees)

**Donnees modifiees** : 5 tables en ecriture (gm-recherche_____gmr, gm-complet_______gmc, hebergement______heb, personnel_go______go, fichier_validation).

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (11 taches)

- **66** - Avancement Personnel **[[ECRAN]](#ecran-t1)**
- **66.1** - Age Bebe
- **66.2** - Recuperation Debut
- **66.4** - Confirmation Avancement **[[ECRAN]](#ecran-t5)**
- **66.5** - Avancement Batch **[[ECRAN]](#ecran-t6)**
- **66.5.1** - Recuperation Hebergement
- **66.5.3** - Modification Package
- **66.5.4** - Modification Sejour
- **66.5.5** - Modification Sejour
- **66.5.6** - Modification Sejour
- **66.5.8** - Modification Package

Delegue a : [Création Village/Village (IDE 77)](WEL-IDE-77.md)

#### Phase 2 : Saisie (1 tache)

- **66.3** - Saisie Date Début **[[ECRAN]](#ecran-t4)**

Delegue a : [Saisie lieu de sejour (IDE 70)](WEL-IDE-70.md)

#### Phase 3 : Creation (1 tache)

- **66.5.2** - Creation Hebergement

Delegue a : [Creation historique (IDE 80)](WEL-IDE-80.md), [Create logbook (IDE 81)](WEL-IDE-81.md)

#### Phase 4 : Validation (1 tache)

- **66.5.7** - Modification Validation

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| hebergement______heb | R/**W** (5 usages) | Hebergement (chambres) |
| personnel_go______go | R/**W** (2 usages) |  |
| gm-complet_______gmc | **W** (1 usages) |  |
| fichier_validation | **W** (1 usages) |  |
| gm-recherche_____gmr | **W** (1 usages) | Index de recherche |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (11 taches)

Traitements internes.

---

#### <a id="t1"></a>66 - Avancement Personnel [[ECRAN]](#ecran-t1)

**Role** : Tache d'orchestration : point d'entree du programme (11 sous-taches). Coordonne l'enchainement des traitements.
**Ecran** : 132 x 56 DLU (MDI) | [Voir mockup](#ecran-t1)

<details>
<summary>10 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [66.1](#t2) | Age Bebe | Traitement |
| [66.2](#t3) | Recuperation Debut | Traitement |
| [66.4](#t5) | Confirmation Avancement **[[ECRAN]](#ecran-t5)** | Traitement |
| [66.5](#t6) | Avancement Batch **[[ECRAN]](#ecran-t6)** | Traitement |
| [66.5.1](#t7) | Recuperation Hebergement | Traitement |
| [66.5.3](#t9) | Modification Package | Traitement |
| [66.5.4](#t10) | Modification Sejour | Traitement |
| [66.5.5](#t11) | Modification Sejour | Traitement |
| [66.5.6](#t12) | Modification Sejour | Traitement |
| [66.5.8](#t14) | Modification Package | Traitement |

</details>

---

#### <a id="t2"></a>66.1 - Age Bebe

**Role** : Traitement : Age Bebe.
**Variables liees** : B (W0 Age Bebe)

---

#### <a id="t3"></a>66.2 - Recuperation Debut

**Role** : Consultation/chargement : Recuperation Debut.
**Variables liees** : E (W0-Date Debut), F (W0-Heure Debut)

---

#### <a id="t5"></a>66.4 - Confirmation Avancement [[ECRAN]](#ecran-t5)

**Role** : Traitement : Confirmation Avancement.
**Ecran** : 132 x 32 DLU (MDI) | [Voir mockup](#ecran-t5)

---

#### <a id="t6"></a>66.5 - Avancement Batch [[ECRAN]](#ecran-t6)

**Role** : Traitement : Avancement Batch.
**Ecran** : 132 x 32 DLU (Modal) | [Voir mockup](#ecran-t6)

---

#### <a id="t7"></a>66.5.1 - Recuperation Hebergement

**Role** : Consultation/chargement : Recuperation Hebergement.

---

#### <a id="t9"></a>66.5.3 - Modification Package

**Role** : Traitement : Modification Package.

---

#### <a id="t10"></a>66.5.4 - Modification Sejour

**Role** : Traitement : Modification Sejour.
**Variables liees** : K (W0-Lieu de sejour)

---

#### <a id="t11"></a>66.5.5 - Modification Sejour

**Role** : Traitement : Modification Sejour.
**Variables liees** : K (W0-Lieu de sejour)

---

#### <a id="t12"></a>66.5.6 - Modification Sejour

**Role** : Traitement : Modification Sejour.
**Variables liees** : K (W0-Lieu de sejour)

---

#### <a id="t14"></a>66.5.8 - Modification Package

**Role** : Traitement : Modification Package.


### 3.2 Saisie (1 tache)

L'operateur saisit les donnees de la transaction via 1 ecran (Saisie Date Début).

---

#### <a id="t4"></a>66.3 - Saisie Date Début [[ECRAN]](#ecran-t4)

**Role** : Saisie des donnees : Saisie Date Début.
**Ecran** : 539 x 87 DLU (MDI) | [Voir mockup](#ecran-t4)
**Variables liees** : A (P.Date), E (W0-Date Debut), G (W0-Date Fin)
**Delegue a** : [Saisie lieu de sejour (IDE 70)](WEL-IDE-70.md)


### 3.3 Creation (1 tache)

Insertion de nouveaux enregistrements en base.

---

#### <a id="t8"></a>66.5.2 - Creation Hebergement

**Role** : Creation d'enregistrement : Creation Hebergement.
**Delegue a** : [Creation historique (IDE 80)](WEL-IDE-80.md), [Create logbook (IDE 81)](WEL-IDE-81.md)


### 3.4 Validation (1 tache)

Controles de coherence : 1 tache verifie les donnees et conditions.

---

#### <a id="t13"></a>66.5.7 - Modification Validation

**Role** : Verification : Modification Validation.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Clients (IDE 9)](WEL-IDE-9.md)
- **Appelle**: 7 programmes | **Tables**: 7 (W:5 R:3 L:1) | **Taches**: 14 | **Expressions**: 12

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (14 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **66.1** | [**Avancement Personnel** (66)](#t1) [mockup](#ecran-t1) | MDI | 132x56 | Traitement |
| 66.1.1 | [Age Bebe (66.1)](#t2) | MDI | - | |
| 66.1.2 | [Recuperation Debut (66.2)](#t3) | MDI | - | |
| 66.1.3 | [Confirmation Avancement (66.4)](#t5) [mockup](#ecran-t5) | MDI | 132x32 | |
| 66.1.4 | [Avancement Batch (66.5)](#t6) [mockup](#ecran-t6) | Modal | 132x32 | |
| 66.1.5 | [Recuperation Hebergement (66.5.1)](#t7) | MDI | - | |
| 66.1.6 | [Modification Package (66.5.3)](#t9) | MDI | - | |
| 66.1.7 | [Modification Sejour (66.5.4)](#t10) | MDI | - | |
| 66.1.8 | [Modification Sejour (66.5.5)](#t11) | MDI | - | |
| 66.1.9 | [Modification Sejour (66.5.6)](#t12) | MDI | - | |
| 66.1.10 | [Modification Package (66.5.8)](#t14) | MDI | - | |
| **66.2** | [**Saisie Date Début** (66.3)](#t4) [mockup](#ecran-t4) | MDI | 539x87 | Saisie |
| **66.3** | [**Creation Hebergement** (66.5.2)](#t8) | MDI | - | Creation |
| **66.4** | [**Modification Validation** (66.5.7)](#t13) | MDI | - | Validation |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Traitement principal]
    UPDATE[MAJ 5 tables]
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

### Tables utilisees (7)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 30 | gm-recherche_____gmr | Index de recherche | DB |   | **W** |   | 1 |
| 31 | gm-complet_______gmc |  | DB |   | **W** |   | 1 |
| 34 | hebergement______heb | Hebergement (chambres) | DB | R | **W** |   | 5 |
| 35 | personnel_go______go |  | DB | R | **W** |   | 2 |
| 113 | tables_village |  | DB | R |   |   | 1 |
| 131 | fichier_validation |  | DB |   | **W** |   | 1 |
| 134 | groupe_arr_dep___vol |  | DB |   |   | L | 1 |

### Colonnes par table (1 / 6 tables avec colonnes identifiees)

<details>
<summary>Table 30 - gm-recherche_____gmr (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 31 - gm-complet_______gmc (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 34 - hebergement______heb (R/**W**) - 5 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 35 - personnel_go______go (R/**W**) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | W1-Statut Sejour | W | Alpha |
| B | W1-Libelle | W | Alpha |
| C | W1-Nationalite | W | Alpha |
| D | W1-Code Sexe | W | Alpha |
| E | W1-Code Fumeur | W | Alpha |
| F | W1 Age | W | Numeric |
| G | W1 Age codifie | W | Alpha |
| H | W1 Nb mois | W | Numeric |
| I | W1 Lieu de sejour | W | Alpha |

</details>

<details>
<summary>Table 113 - tables_village (R) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 131 - fichier_validation (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (1)

Variables recues du programme appelant ([Clients (IDE 9)](WEL-IDE-9.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P.Date | Date | - |

### 11.2 Variables de travail (1)

Variables internes au programme.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| B | W0 Age Bebe | Numeric | - |

### 11.3 Autres (13)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| C | W0-Qualite | Alpha | - |
| D | W0-Complement | Alpha | 1x refs |
| E | W0-Date Debut | Date | - |
| F | W0-Heure Debut | Alpha | - |
| G | W0-Date Fin | Date | - |
| H | W0-Heure Fin | Alpha | - |
| I | W0-Occupation | Alpha | - |
| J | W0-Base Occupation | Alpha | - |
| K | W0-Lieu de sejour | Alpha | [66.5.4](#t10), [66.5.5](#t11), [66.5.6](#t12) |
| L | W0-Accord Suite | Alpha | 3x refs |
| M | W0-Existe Code VV | Logical | 1x refs |
| N | W0-Code VV | Alpha | - |
| O | W0-Heure VV | Alpha | - |

## 12. EXPRESSIONS

**12 / 12 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONDITION | 3 | 0 |
| CONSTANTE | 5 | 0 |
| REFERENCE_VG | 3 | 0 |
| OTHER | 1 | 0 |

### 12.2 Expressions cles par type

#### CONDITION (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 8 | `W0-Accord Suite [L]='E'` | - |
| CONDITION | 6 | `W0-Accord Suite [L]='O'` | - |
| CONDITION | 7 | `W0-Accord Suite [L]='O' AND W0-Lieu de sejour [K]='*'  AND VG31>1 AND IN(W0-Complement [D],'VILL','GE','LOC','STAG','ANS')` | - |

#### CONSTANTE (5 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 10 | `'A'` | - |
| CONSTANTE | 12 | `'P'` | - |
| CONSTANTE | 9 | `''` | - |
| CONSTANTE | 4 | `'TBAOC'` | - |
| CONSTANTE | 5 | `'P'` | - |

#### REFERENCE_VG (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 3 | `VG5` | - |
| REFERENCE_VG | 2 | `VG9` | - |
| REFERENCE_VG | 1 | `VG12` | - |

#### OTHER (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 11 | `NOT(W0-Existe Code VV [M])` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Clients (IDE 9)](WEL-IDE-9.md) -> **Avancement Personnel (IDE 66)**

```mermaid
graph LR
    T66[66 Avancement Personnel]
    style T66 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC34[34 Lancement]
    style CC34 fill:#f59e0b
    CC55[55 Mobile Welcome]
    style CC55 fill:#f59e0b
    CC9[9 Clients]
    style CC9 fill:#3fb950
    CC55 --> CC9
    CC34 --> CC55
    CC1 --> CC34
    CC9 --> T66
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [9](WEL-IDE-9.md) | Clients | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T66[66 Avancement Personnel]
    style T66 fill:#58a6ff
    C70[70 Saisie lieu de sejour]
    T66 --> C70
    style C70 fill:#3fb950
    C77[77 Création VillageVil...]
    T66 --> C77
    style C77 fill:#3fb950
    C80[80 Creation historique]
    T66 --> C80
    style C80 fill:#3fb950
    C81[81 Create logbook]
    T66 --> C81
    style C81 fill:#3fb950
    C102[102 Zoom code occupation]
    T66 --> C102
    style C102 fill:#3fb950
    C106[106 Zoom qualite]
    T66 --> C106
    style C106 fill:#3fb950
    C107[107 Zoom villagevillage]
    T66 --> C107
    style C107 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [70](WEL-IDE-70.md) | Saisie lieu de sejour | 1 | Sous-programme |
| [77](WEL-IDE-77.md) | Création Village/Village | 1 | Sous-programme |
| [80](WEL-IDE-80.md) | Creation historique | 1 | Historique/consultation |
| [81](WEL-IDE-81.md) | Create logbook | 1 | Sous-programme |
| [102](WEL-IDE-102.md) | Zoom code occupation | 1 | Selection/consultation |
| [106](WEL-IDE-106.md) | Zoom qualite | 1 | Selection/consultation |
| [107](WEL-IDE-107.md) | Zoom village/village | 1 | Selection/consultation |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 285 | Taille moyenne |
| Expressions | 12 | Peu de logique |
| Tables WRITE | 5 | Impact modere |
| Sous-programmes | 7 | Dependances moderees |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 285) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (11 taches: 3 ecrans, 8 traitements)

- **Strategie** : Orchestrateur avec 3 ecrans (Razor/React) et 8 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 7 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Saisie (1 tache: 1 ecran, 0 traitement)

- **Strategie** : Formulaire React/Blazor avec validation Zod/FluentValidation.
- Reproduire 1 ecran : Saisie Date Début
- Validation temps reel cote client + serveur

#### Creation (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Repository pattern avec Entity Framework Core.
- Insertion via `IRepository<T>.CreateAsync()`

#### Validation (1 tache: 0 ecran, 1 traitement)

- **Strategie** : FluentValidation avec validators specifiques.
- Chaque tache de validation -> un validator injectable

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| gm-recherche_____gmr | Table WRITE (Database) | 1x | Schema + repository |
| gm-complet_______gmc | Table WRITE (Database) | 1x | Schema + repository |
| hebergement______heb | Table WRITE (Database) | 3x | Schema + repository |
| personnel_go______go | Table WRITE (Database) | 1x | Schema + repository |
| fichier_validation | Table WRITE (Database) | 1x | Schema + repository |
| [Zoom code occupation (IDE 102)](WEL-IDE-102.md) | Sous-programme | 1x | Normale - Selection/consultation |
| [Zoom qualite (IDE 106)](WEL-IDE-106.md) | Sous-programme | 1x | Normale - Selection/consultation |
| [Zoom village/village (IDE 107)](WEL-IDE-107.md) | Sous-programme | 1x | Normale - Selection/consultation |
| [Create logbook (IDE 81)](WEL-IDE-81.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Saisie lieu de sejour (IDE 70)](WEL-IDE-70.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Création Village/Village (IDE 77)](WEL-IDE-77.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Creation historique (IDE 80)](WEL-IDE-80.md) | Sous-programme | 1x | Normale - Historique/consultation |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 21:33*
