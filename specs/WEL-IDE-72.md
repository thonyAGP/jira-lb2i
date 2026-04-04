# WEL IDE 72 - Interruption Client

> **Analyse**: Phases 1-4 2026-02-03 21:34 -> 21:34 (11s) | Assemblage 21:34
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | WEL |
| IDE Position | 72 |
| Nom Programme | Interruption Client |
| Fichier source | `Prg_72.xml` |
| Dossier IDE | Sejour |
| Taches | 13 (0 ecrans visibles) |
| Tables modifiees | 6 |
| Programmes appeles | 3 |

## 2. DESCRIPTION FONCTIONNELLE

**Interruption Client** assure la gestion complete de ce processus, accessible depuis [Clients (IDE 9)](WEL-IDE-9.md).

Le flux de traitement s'organise en **5 blocs fonctionnels** :

- **Traitement** (8 taches) : traitements metier divers
- **Validation** (2 taches) : controles et verifications de coherence
- **Calcul** (1 tache) : calculs de montants, stocks ou compteurs
- **Saisie** (1 tache) : ecrans de saisie utilisateur (formulaires, champs, donnees)
- **Creation** (1 tache) : insertion d'enregistrements en base (mouvements, prestations)

**Donnees modifiees** : 6 tables en ecriture (gm-recherche_____gmr, hebergement______heb, client_gm, compte_gm________cgm, fichier_validation, groupe_arr_dep___vol).

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (8 taches)

- **72** - Interruption Client **[[ECRAN]](#ecran-t1)**
- **72.1** - Recuperation Periode
- **72.4** - Confirmation Interruption **[[ECRAN]](#ecran-t5)**
- **72.5** - Interruption Batch **[[ECRAN]](#ecran-t6)**
- **72.5.1** - Modification Hebergement
- **72.5.2** - Modification Package
- **72.5.3** - Modification Sejour
- **72.5.4** - Modification Sejour

#### Phase 2 : Saisie (1 tache)

- **72.2** - Saisie Date Fin **[[ECRAN]](#ecran-t3)**

#### Phase 3 : Creation (1 tache)

- **72.3** - Creation Groupe V/V

Delegue a : [Creation historique (IDE 80)](WEL-IDE-80.md), [Create logbook (IDE 81)](WEL-IDE-81.md)

#### Phase 4 : Validation (2 taches)

- **72.5.5** - Verification Compte
- **72.5.7** - Modification Validation

#### Phase 5 : Calcul (1 tache)

- **72.5.6** - Modification Compte

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| hebergement______heb | R/**W** (3 usages) | Hebergement (chambres) |
| gm-recherche_____gmr | R/**W** (2 usages) | Index de recherche |
| client_gm | R/**W** (2 usages) |  |
| fichier_validation | **W** (1 usages) |  |
| compte_gm________cgm | **W** (1 usages) | Comptes GM (generaux) |
| groupe_arr_dep___vol | **W** (1 usages) |  |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (8 taches)

Traitements internes.

---

#### <a id="t1"></a>72 - Interruption Client [[ECRAN]](#ecran-t1)

**Role** : Tache d'orchestration : point d'entree du programme (8 sous-taches). Coordonne l'enchainement des traitements.
**Ecran** : 132 x 48 DLU (MDI) | [Voir mockup](#ecran-t1)

<details>
<summary>7 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [72.1](#t2) | Recuperation Periode | Traitement |
| [72.4](#t5) | Confirmation Interruption **[[ECRAN]](#ecran-t5)** | Traitement |
| [72.5](#t6) | Interruption Batch **[[ECRAN]](#ecran-t6)** | Traitement |
| [72.5.1](#t7) | Modification Hebergement | Traitement |
| [72.5.2](#t8) | Modification Package | Traitement |
| [72.5.3](#t9) | Modification Sejour | Traitement |
| [72.5.4](#t10) | Modification Sejour | Traitement |

</details>

---

#### <a id="t2"></a>72.1 - Recuperation Periode

**Role** : Consultation/chargement : Recuperation Periode.

---

#### <a id="t5"></a>72.4 - Confirmation Interruption [[ECRAN]](#ecran-t5)

**Role** : Traitement : Confirmation Interruption.
**Ecran** : 132 x 32 DLU (MDI) | [Voir mockup](#ecran-t5)

---

#### <a id="t6"></a>72.5 - Interruption Batch [[ECRAN]](#ecran-t6)

**Role** : Traitement : Interruption Batch.
**Ecran** : 132 x 32 DLU (Modal) | [Voir mockup](#ecran-t6)

---

#### <a id="t7"></a>72.5.1 - Modification Hebergement

**Role** : Traitement : Modification Hebergement.

---

#### <a id="t8"></a>72.5.2 - Modification Package

**Role** : Traitement : Modification Package.

---

#### <a id="t9"></a>72.5.3 - Modification Sejour

**Role** : Traitement : Modification Sejour.

---

#### <a id="t10"></a>72.5.4 - Modification Sejour

**Role** : Traitement : Modification Sejour.


### 3.2 Saisie (1 tache)

L'operateur saisit les donnees de la transaction via 1 ecran (Saisie Date Fin).

---

#### <a id="t3"></a>72.2 - Saisie Date Fin [[ECRAN]](#ecran-t3)

**Role** : Saisie des donnees : Saisie Date Fin.
**Ecran** : 413 x 86 DLU (MDI) | [Voir mockup](#ecran-t3)
**Variables liees** : A (P.Date), D (W0-Date Debut), F (W0-Date Prevue), H (W0-Date Fin)


### 3.3 Creation (1 tache)

Insertion de nouveaux enregistrements en base.

---

#### <a id="t4"></a>72.3 - Creation Groupe V/V

**Role** : Creation d'enregistrement : Creation Groupe V/V.
**Delegue a** : [Creation historique (IDE 80)](WEL-IDE-80.md), [Create logbook (IDE 81)](WEL-IDE-81.md)


### 3.4 Validation (2 taches)

Controles de coherence : 2 taches verifient les donnees et conditions.

---

#### <a id="t11"></a>72.5.5 - Verification Compte

**Role** : Verification : Verification Compte.

---

#### <a id="t13"></a>72.5.7 - Modification Validation

**Role** : Verification : Modification Validation.


### 3.5 Calcul (1 tache)

Calculs metier : montants, stocks, compteurs.

---

#### <a id="t12"></a>72.5.6 - Modification Compte

**Role** : Traitement : Modification Compte.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Clients (IDE 9)](WEL-IDE-9.md)
- **Appelle**: 3 programmes | **Tables**: 6 (W:6 R:3 L:0) | **Taches**: 13 | **Expressions**: 7

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (13 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **72.1** | [**Interruption Client** (72)](#t1) [mockup](#ecran-t1) | MDI | 132x48 | Traitement |
| 72.1.1 | [Recuperation Periode (72.1)](#t2) | MDI | - | |
| 72.1.2 | [Confirmation Interruption (72.4)](#t5) [mockup](#ecran-t5) | MDI | 132x32 | |
| 72.1.3 | [Interruption Batch (72.5)](#t6) [mockup](#ecran-t6) | Modal | 132x32 | |
| 72.1.4 | [Modification Hebergement (72.5.1)](#t7) | MDI | - | |
| 72.1.5 | [Modification Package (72.5.2)](#t8) | MDI | - | |
| 72.1.6 | [Modification Sejour (72.5.3)](#t9) | MDI | - | |
| 72.1.7 | [Modification Sejour (72.5.4)](#t10) | MDI | - | |
| **72.2** | [**Saisie Date Fin** (72.2)](#t3) [mockup](#ecran-t3) | MDI | 413x86 | Saisie |
| **72.3** | [**Creation Groupe V/V** (72.3)](#t4) | MDI | - | Creation |
| **72.4** | [**Verification Compte** (72.5.5)](#t11) | MDI | - | Validation |
| 72.4.1 | [Modification Validation (72.5.7)](#t13) | MDI | - | |
| **72.5** | [**Modification Compte** (72.5.6)](#t12) | MDI | - | Calcul |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Traitement principal]
    UPDATE[MAJ 6 tables]
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

### Tables utilisees (6)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 30 | gm-recherche_____gmr | Index de recherche | DB | R | **W** |   | 2 |
| 34 | hebergement______heb | Hebergement (chambres) | DB | R | **W** |   | 3 |
| 36 | client_gm |  | DB | R | **W** |   | 2 |
| 47 | compte_gm________cgm | Comptes GM (generaux) | DB |   | **W** |   | 1 |
| 131 | fichier_validation |  | DB |   | **W** |   | 1 |
| 134 | groupe_arr_dep___vol |  | DB |   | **W** |   | 1 |

### Colonnes par table (2 / 6 tables avec colonnes identifiees)

<details>
<summary>Table 30 - gm-recherche_____gmr (R/**W**) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 34 - hebergement______heb (R/**W**) - 3 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 36 - client_gm (R/**W**) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | W1-Date Compte | W | Date |
| B | W1-Code Retour | W | Numeric |
| C | W1-Date Voyage | W | Date |
| D | W1-Heure Voyage | W | Alpha |
| E | W1-Fin de Sejour | W | Date |
| F | V.Sejour valide | W | Alpha |

</details>

<details>
<summary>Table 47 - compte_gm________cgm (**W**) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | W1-Date Compte | W | Date |

</details>

<details>
<summary>Table 131 - fichier_validation (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 134 - groupe_arr_dep___vol (**W**) - 1 usages</summary>

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
| M | W0 libelle transport | Alpha | - |

### 11.3 Autres (12)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| B | W0-Qualite | Alpha | - |
| C | W0-Complement | Alpha | - |
| D | W0-Date Debut | Date | - |
| E | W0-Heure Debut | Alpha | - |
| F | W0-Date Prevue | Date | - |
| G | W0-Heure Prevue | Alpha | - |
| H | W0-Date Fin | Date | - |
| I | W0-Heure Fin | Alpha | - |
| J | W0-Code Vol | Alpha | - |
| K | W0-Transport | Alpha | - |
| L | W0-Ville | Alpha | - |
| N | W0-Accord Suite | Alpha | 2x refs |

## 12. EXPRESSIONS

**7 / 7 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONSTANTE | 2 | 0 |
| REFERENCE_VG | 3 | 0 |
| CONDITION | 2 | 0 |

### 12.2 Expressions cles par type

#### CONSTANTE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 4 | `''` | - |
| CONSTANTE | 3 | `'R'` | - |

#### REFERENCE_VG (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 7 | `VG12` | - |
| REFERENCE_VG | 2 | `VG5` | - |
| REFERENCE_VG | 1 | `VG9` | - |

#### CONDITION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 6 | `W0-Accord Suite [N]='E'` | - |
| CONDITION | 5 | `W0-Accord Suite [N]='O'` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Clients (IDE 9)](WEL-IDE-9.md) -> **Interruption Client (IDE 72)**

```mermaid
graph LR
    T72[72 Interruption Client]
    style T72 fill:#58a6ff
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
    CC9 --> T72
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [9](WEL-IDE-9.md) | Clients | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T72[72 Interruption Client]
    style T72 fill:#58a6ff
    C80[80 Creation historique]
    T72 --> C80
    style C80 fill:#3fb950
    C81[81 Create logbook]
    T72 --> C81
    style C81 fill:#3fb950
    C103[103 Zoom groupe arrive...]
    T72 --> C103
    style C103 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [80](WEL-IDE-80.md) | Creation historique | 1 | Historique/consultation |
| [81](WEL-IDE-81.md) | Create logbook | 1 | Sous-programme |
| [103](WEL-IDE-103.md) | Zoom groupe arrivee depart | 1 | Selection/consultation |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 233 | Taille moyenne |
| Expressions | 7 | Peu de logique |
| Tables WRITE | 6 | Fort impact donnees |
| Sous-programmes | 3 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 233) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (8 taches: 3 ecrans, 5 traitements)

- **Strategie** : Orchestrateur avec 3 ecrans (Razor/React) et 5 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 3 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Saisie (1 tache: 1 ecran, 0 traitement)

- **Strategie** : Formulaire React/Blazor avec validation Zod/FluentValidation.
- Reproduire 1 ecran : Saisie Date Fin
- Validation temps reel cote client + serveur

#### Creation (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Repository pattern avec Entity Framework Core.
- Insertion via `IRepository<T>.CreateAsync()`

#### Validation (2 taches: 0 ecran, 2 traitements)

- **Strategie** : FluentValidation avec validators specifiques.
- Chaque tache de validation -> un validator injectable

#### Calcul (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Services de calcul purs (Domain Services).
- Migrer la logique de calcul (stock, compteurs, montants)

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| gm-recherche_____gmr | Table WRITE (Database) | 1x | Schema + repository |
| hebergement______heb | Table WRITE (Database) | 2x | Schema + repository |
| client_gm | Table WRITE (Database) | 1x | Schema + repository |
| compte_gm________cgm | Table WRITE (Database) | 1x | Schema + repository |
| fichier_validation | Table WRITE (Database) | 1x | Schema + repository |
| groupe_arr_dep___vol | Table WRITE (Database) | 1x | Schema + repository |
| [Zoom groupe arrivee depart (IDE 103)](WEL-IDE-103.md) | Sous-programme | 1x | Normale - Selection/consultation |
| [Create logbook (IDE 81)](WEL-IDE-81.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Creation historique (IDE 80)](WEL-IDE-80.md) | Sous-programme | 1x | Normale - Historique/consultation |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 21:34*
