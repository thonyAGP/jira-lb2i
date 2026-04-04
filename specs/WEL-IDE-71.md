# WEL IDE 71 - Avancement Client

> **Analyse**: Phases 1-4 2026-02-03 21:34 -> 21:34 (10s) | Assemblage 21:34
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | WEL |
| IDE Position | 71 |
| Nom Programme | Avancement Client |
| Fichier source | `Prg_71.xml` |
| Dossier IDE | Sejour |
| Taches | 22 (0 ecrans visibles) |
| Tables modifiees | 8 |
| Programmes appeles | 7 |

## 2. DESCRIPTION FONCTIONNELLE

**Avancement Client** assure la gestion complete de ce processus, accessible depuis [Clients (IDE 9)](WEL-IDE-9.md).

Le flux de traitement s'organise en **5 blocs fonctionnels** :

- **Traitement** (14 taches) : traitements metier divers
- **Validation** (3 taches) : controles et verifications de coherence
- **Creation** (2 taches) : insertion d'enregistrements en base (mouvements, prestations)
- **Consultation** (2 taches) : ecrans de recherche, selection et consultation
- **Saisie** (1 tache) : ecrans de saisie utilisateur (formulaires, champs, donnees)

**Donnees modifiees** : 8 tables en ecriture (gm-recherche_____gmr, gm-complet_______gmc, hebergement______heb, client_gm, compte_gm________cgm, fichier_validation, groupe_arr_dep___vol, heb_circuit______hci).

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (14 taches)

- **71** - Avancement Client **[[ECRAN]](#ecran-t1)**
- **71.1** - Age Bebe
- **71.2.1** - Determination Qualite
- **71.3** - Recuperation Debut
- **71.7** - Confirmation Avancement **[[ECRAN]](#ecran-t11)**
- **71.8** - Avancement Batch **[[ECRAN]](#ecran-t12)**
- **71.8.2** - Modification Package Retour
- **71.8.3** - Mofification Heure Deb Circuit
- **71.8.4** - Modification Package
- **71.8.5** - Modification Sejour
- **71.8.6** - Modification Sejour
- **71.8.7** - Modification Sejour
- **71.8.9** - Modification Package
- **71.8.10** - Modification Package

#### Phase 2 : Consultation (2 taches)

- **71.2** - Selection Qualite
- **71.6** - Selection Logement

Delegue a : [Zoom code occupation (IDE 102)](WEL-IDE-102.md), [Zoom groupe arrivee depart (IDE 103)](WEL-IDE-103.md), [Zoom lieu de sejour (IDE 104)](WEL-IDE-104.md), [Zoom code logement (IDE 105)](WEL-IDE-105.md), [Zoom qualite (IDE 106)](WEL-IDE-106.md)

#### Phase 3 : Saisie (1 tache)

- **71.4** - Saisie Date Debut **[[ECRAN]](#ecran-t6)**

#### Phase 4 : Creation (2 taches)

- **71.5** - Creation Groupe V/V
- **71.8.1** - Creation Hebergement

Delegue a : [Creation historique (IDE 80)](WEL-IDE-80.md), [Create logbook (IDE 81)](WEL-IDE-81.md)

#### Phase 5 : Validation (3 taches)

- **71.6.1** - Verification Lieu Sejour
- **71.6.2** - Verification Code Logement
- **71.8.8** - Modification Validation

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| hebergement______heb | R/**W** (7 usages) | Hebergement (chambres) |
| client_gm | **W**/L (2 usages) |  |
| gm-recherche_____gmr | **W** (1 usages) | Index de recherche |
| compte_gm________cgm | **W** (1 usages) | Comptes GM (generaux) |
| fichier_validation | **W** (1 usages) |  |
| groupe_arr_dep___vol | **W** (1 usages) |  |
| gm-complet_______gmc | **W** (1 usages) |  |
| heb_circuit______hci | **W** (1 usages) | Hebergement (chambres) |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (14 taches)

Traitements internes.

---

#### <a id="t1"></a>71 - Avancement Client [[ECRAN]](#ecran-t1)

**Role** : Tache d'orchestration : point d'entree du programme (14 sous-taches). Coordonne l'enchainement des traitements.
**Ecran** : 406 x 161 DLU (MDI) | [Voir mockup](#ecran-t1)

<details>
<summary>13 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [71.1](#t2) | Age Bebe | Traitement |
| [71.2.1](#t4) | Determination Qualite | Traitement |
| [71.3](#t5) | Recuperation Debut | Traitement |
| [71.7](#t11) | Confirmation Avancement **[[ECRAN]](#ecran-t11)** | Traitement |
| [71.8](#t12) | Avancement Batch **[[ECRAN]](#ecran-t12)** | Traitement |
| [71.8.2](#t14) | Modification Package Retour | Traitement |
| [71.8.3](#t15) | Mofification Heure Deb Circuit | Traitement |
| [71.8.4](#t16) | Modification Package | Traitement |
| [71.8.5](#t17) | Modification Sejour | Traitement |
| [71.8.6](#t18) | Modification Sejour | Traitement |
| [71.8.7](#t19) | Modification Sejour | Traitement |
| [71.8.9](#t21) | Modification Package | Traitement |
| [71.8.10](#t22) | Modification Package | Traitement |

</details>

---

#### <a id="t2"></a>71.1 - Age Bebe

**Role** : Traitement : Age Bebe.
**Variables liees** : Y (W0 Age bebe)

---

#### <a id="t4"></a>71.2.1 - Determination Qualite

**Role** : Traitement : Determination Qualite.
**Variables liees** : B (W0-Qualite)

---

#### <a id="t5"></a>71.3 - Recuperation Debut

**Role** : Consultation/chargement : Recuperation Debut.
**Variables liees** : D (W0-Date Debut), E (W0-Heure Debut)

---

#### <a id="t11"></a>71.7 - Confirmation Avancement [[ECRAN]](#ecran-t11)

**Role** : Traitement : Confirmation Avancement.
**Ecran** : 132 x 32 DLU (Modal) | [Voir mockup](#ecran-t11)

---

#### <a id="t12"></a>71.8 - Avancement Batch [[ECRAN]](#ecran-t12)

**Role** : Traitement : Avancement Batch.
**Ecran** : 132 x 32 DLU (Modal) | [Voir mockup](#ecran-t12)

---

#### <a id="t14"></a>71.8.2 - Modification Package Retour

**Role** : Traitement : Modification Package Retour.
**Variables liees** : N (W0 Code Ville Retour), O (W0 Lib Transp Retour), L (W0-Code Vol Retour), M (W0-Transport Retour)

---

#### <a id="t15"></a>71.8.3 - Mofification Heure Deb Circuit

**Role** : Traitement : Mofification Heure Deb Circuit.
**Variables liees** : E (W0-Heure Debut), G (W0-Heure Fin)

---

#### <a id="t16"></a>71.8.4 - Modification Package

**Role** : Traitement : Modification Package.

---

#### <a id="t17"></a>71.8.5 - Modification Sejour

**Role** : Traitement : Modification Sejour.
**Variables liees** : P (W0-Lieu de Sejour)

---

#### <a id="t18"></a>71.8.6 - Modification Sejour

**Role** : Traitement : Modification Sejour.
**Variables liees** : P (W0-Lieu de Sejour)

---

#### <a id="t19"></a>71.8.7 - Modification Sejour

**Role** : Traitement : Modification Sejour.
**Variables liees** : P (W0-Lieu de Sejour)

---

#### <a id="t21"></a>71.8.9 - Modification Package

**Role** : Traitement : Modification Package.

---

#### <a id="t22"></a>71.8.10 - Modification Package

**Role** : Traitement : Modification Package.


### 3.2 Consultation (2 taches)

Ecrans de recherche et consultation.

---

#### <a id="t3"></a>71.2 - Selection Qualite

**Role** : Selection par l'operateur : Selection Qualite.
**Variables liees** : B (W0-Qualite)
**Delegue a** : [Zoom code occupation (IDE 102)](WEL-IDE-102.md), [Zoom groupe arrivee depart (IDE 103)](WEL-IDE-103.md), [Zoom lieu de sejour (IDE 104)](WEL-IDE-104.md)

---

#### <a id="t8"></a>71.6 - Selection Logement

**Role** : Selection par l'operateur : Selection Logement.
**Variables liees** : Q (W0-Code Logement)
**Delegue a** : [Zoom code occupation (IDE 102)](WEL-IDE-102.md), [Zoom groupe arrivee depart (IDE 103)](WEL-IDE-103.md), [Zoom lieu de sejour (IDE 104)](WEL-IDE-104.md)


### 3.3 Saisie (1 tache)

L'operateur saisit les donnees de la transaction via 1 ecran (Saisie Date Debut).

---

#### <a id="t6"></a>71.4 - Saisie Date Debut [[ECRAN]](#ecran-t6)

**Role** : Saisie des donnees : Saisie Date Debut.
**Ecran** : 453 x 87 DLU (MDI) | [Voir mockup](#ecran-t6)
**Variables liees** : A (P.Date), D (W0-Date Debut), E (W0-Heure Debut), F (W0-Date Fin)


### 3.4 Creation (2 taches)

Insertion de nouveaux enregistrements en base.

---

#### <a id="t7"></a>71.5 - Creation Groupe V/V

**Role** : Creation d'enregistrement : Creation Groupe V/V.
**Delegue a** : [Creation historique (IDE 80)](WEL-IDE-80.md), [Create logbook (IDE 81)](WEL-IDE-81.md)

---

#### <a id="t13"></a>71.8.1 - Creation Hebergement

**Role** : Creation d'enregistrement : Creation Hebergement.
**Delegue a** : [Creation historique (IDE 80)](WEL-IDE-80.md), [Create logbook (IDE 81)](WEL-IDE-81.md)


### 3.5 Validation (3 taches)

Controles de coherence : 3 taches verifient les donnees et conditions.

---

#### <a id="t9"></a>71.6.1 - Verification Lieu Sejour

**Role** : Verification : Verification Lieu Sejour.
**Variables liees** : P (W0-Lieu de Sejour)

---

#### <a id="t10"></a>71.6.2 - Verification Code Logement

**Role** : Verification : Verification Code Logement.
**Variables liees** : N (W0 Code Ville Retour), V (W0 Code Sexe), W (W0 Code Fumeur), H (W0-Code Vol Aller), J (W0-Code Ville Aller)

---

#### <a id="t20"></a>71.8.8 - Modification Validation

**Role** : Verification : Modification Validation.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Clients (IDE 9)](WEL-IDE-9.md)
- **Appelle**: 7 programmes | **Tables**: 11 (W:8 R:4 L:2) | **Taches**: 22 | **Expressions**: 8

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (22 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **71.1** | [**Avancement Client** (71)](#t1) [mockup](#ecran-t1) | MDI | 406x161 | Traitement |
| 71.1.1 | [Age Bebe (71.1)](#t2) | MDI | - | |
| 71.1.2 | [Determination Qualite (71.2.1)](#t4) | MDI | - | |
| 71.1.3 | [Recuperation Debut (71.3)](#t5) | MDI | - | |
| 71.1.4 | [Confirmation Avancement (71.7)](#t11) [mockup](#ecran-t11) | Modal | 132x32 | |
| 71.1.5 | [Avancement Batch (71.8)](#t12) [mockup](#ecran-t12) | Modal | 132x32 | |
| 71.1.6 | [Modification Package Retour (71.8.2)](#t14) | MDI | - | |
| 71.1.7 | [Mofification Heure Deb Circuit (71.8.3)](#t15) | MDI | - | |
| 71.1.8 | [Modification Package (71.8.4)](#t16) | MDI | - | |
| 71.1.9 | [Modification Sejour (71.8.5)](#t17) | MDI | - | |
| 71.1.10 | [Modification Sejour (71.8.6)](#t18) | MDI | - | |
| 71.1.11 | [Modification Sejour (71.8.7)](#t19) | MDI | - | |
| 71.1.12 | [Modification Package (71.8.9)](#t21) | MDI | - | |
| 71.1.13 | [Modification Package (71.8.10)](#t22) | MDI | - | |
| **71.2** | [**Selection Qualite** (71.2)](#t3) | MDI | - | Consultation |
| 71.2.1 | [Selection Logement (71.6)](#t8) | MDI | - | |
| **71.3** | [**Saisie Date Debut** (71.4)](#t6) [mockup](#ecran-t6) | MDI | 453x87 | Saisie |
| **71.4** | [**Creation Groupe V/V** (71.5)](#t7) | MDI | - | Creation |
| 71.4.1 | [Creation Hebergement (71.8.1)](#t13) | MDI | - | |
| **71.5** | [**Verification Lieu Sejour** (71.6.1)](#t9) | MDI | - | Validation |
| 71.5.1 | [Verification Code Logement (71.6.2)](#t10) | MDI | - | |
| 71.5.2 | [Modification Validation (71.8.8)](#t20) | MDI | - | |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Traitement principal]
    UPDATE[MAJ 8 tables]
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

### Tables utilisees (11)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 30 | gm-recherche_____gmr | Index de recherche | DB |   | **W** |   | 1 |
| 31 | gm-complet_______gmc |  | DB |   | **W** |   | 1 |
| 34 | hebergement______heb | Hebergement (chambres) | DB | R | **W** |   | 7 |
| 36 | client_gm |  | DB |   | **W** | L | 2 |
| 47 | compte_gm________cgm | Comptes GM (generaux) | DB |   | **W** |   | 1 |
| 108 | code_logement____clo |  | DB | R |   |   | 2 |
| 113 | tables_village |  | DB | R |   |   | 1 |
| 118 | tables_imports |  | DB | R |   | L | 2 |
| 131 | fichier_validation |  | DB |   | **W** |   | 1 |
| 134 | groupe_arr_dep___vol |  | DB |   | **W** |   | 1 |
| 168 | heb_circuit______hci | Hebergement (chambres) | DB |   | **W** |   | 1 |

### Colonnes par table (4 / 11 tables avec colonnes identifiees)

<details>
<summary>Table 30 - gm-recherche_____gmr (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 31 - gm-complet_______gmc (**W**) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | W1-Code Retour | W | Numeric |
| B | W1 Age | W | Numeric |
| C | W1 Age Codifie | W | Alpha |
| D | W1 Nb mois | W | Numeric |

</details>

<details>
<summary>Table 34 - hebergement______heb (R/**W**) - 7 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 36 - client_gm (**W**/L) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 47 - compte_gm________cgm (**W**) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| B | W1-Compteur Lieu | W | Numeric |

</details>

<details>
<summary>Table 108 - code_logement____clo (R) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | W1-Fin de Tache | R | Alpha |
| B | W1-Compteur Lieu | R | Numeric |
| C | W1-Lieu General | R | Alpha |
| D | W1-Accord Logement | R | Alpha |
| E | W1-Accord Suite | R | Alpha |

</details>

<details>
<summary>Table 113 - tables_village (R) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 118 - tables_imports (R/L) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 131 - fichier_validation (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 134 - groupe_arr_dep___vol (**W**) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | v.Selection A/R | W | Alpha |
| B | v.date | W | Date |

</details>

<details>
<summary>Table 168 - heb_circuit______hci (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (1)

Variables recues du programme appelant ([Clients (IDE 9)](WEL-IDE-9.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P.Date | Date | - |

### 11.2 Variables de travail (8)

Variables internes au programme.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| K | W0 Lib Transp aller | Alpha | - |
| N | W0 Code Ville Retour | Alpha | - |
| O | W0 Lib Transp Retour | Alpha | - |
| U | W0 Nationalite | Alpha | - |
| V | W0 Code Sexe | Alpha | - |
| W | W0 Code Fumeur | Alpha | - |
| X | W0 Heb existe ? | Alpha | 1x calcul interne |
| Y | W0 Age bebe | Numeric | - |

### 11.3 Autres (17)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| B | W0-Qualite | Alpha | - |
| C | W0-Complement | Alpha | - |
| D | W0-Date Debut | Date | - |
| E | W0-Heure Debut | Alpha | - |
| F | W0-Date Fin | Date | - |
| G | W0-Heure Fin | Alpha | - |
| H | W0-Code Vol Aller | Alpha | - |
| I | W0-Transport Aller | Alpha | - |
| J | W0-Code Ville Aller | Alpha | - |
| L | W0-Code Vol Retour | Alpha | - |
| M | W0-Transport Retour | Alpha | - |
| P | W0-Lieu de Sejour | Alpha | - |
| Q | W0-Code Logement | Alpha | - |
| R | W0-Occupation | Alpha | - |
| S | W0-Base Occupation | Alpha | - |
| T | W0-Valide ? | Alpha | - |
| Z | W0-Accord Suite | Alpha | 3x refs |

<details>
<summary>Toutes les 26 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| P0 | **A** | P.Date | Date |
| W0 | **K** | W0 Lib Transp aller | Alpha |
| W0 | **N** | W0 Code Ville Retour | Alpha |
| W0 | **O** | W0 Lib Transp Retour | Alpha |
| W0 | **U** | W0 Nationalite | Alpha |
| W0 | **V** | W0 Code Sexe | Alpha |
| W0 | **W** | W0 Code Fumeur | Alpha |
| W0 | **X** | W0 Heb existe ? | Alpha |
| W0 | **Y** | W0 Age bebe | Numeric |
| Autre | **B** | W0-Qualite | Alpha |
| Autre | **C** | W0-Complement | Alpha |
| Autre | **D** | W0-Date Debut | Date |
| Autre | **E** | W0-Heure Debut | Alpha |
| Autre | **F** | W0-Date Fin | Date |
| Autre | **G** | W0-Heure Fin | Alpha |
| Autre | **H** | W0-Code Vol Aller | Alpha |
| Autre | **I** | W0-Transport Aller | Alpha |
| Autre | **J** | W0-Code Ville Aller | Alpha |
| Autre | **L** | W0-Code Vol Retour | Alpha |
| Autre | **M** | W0-Transport Retour | Alpha |
| Autre | **P** | W0-Lieu de Sejour | Alpha |
| Autre | **Q** | W0-Code Logement | Alpha |
| Autre | **R** | W0-Occupation | Alpha |
| Autre | **S** | W0-Base Occupation | Alpha |
| Autre | **T** | W0-Valide ? | Alpha |
| Autre | **Z** | W0-Accord Suite | Alpha |

</details>

## 12. EXPRESSIONS

**8 / 8 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONSTANTE | 5 | 0 |
| CONDITION | 3 | 0 |

### 12.2 Expressions cles par type

#### CONSTANTE (5 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 4 | `'A'` | - |
| CONSTANTE | 8 | `''` | - |
| CONSTANTE | 3 | `'R'` | - |
| CONSTANTE | 1 | `'TBAOC'` | - |
| CONSTANTE | 2 | `'TUP'` | - |

#### CONDITION (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 7 | `W0-Accord Suite [Z]='E'` | - |
| CONDITION | 6 | `W0-Accord Suite [Z]='O' AND W0 Heb existe ? [X]<>'O'` | - |
| CONDITION | 5 | `W0-Accord Suite [Z]='O'` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Clients (IDE 9)](WEL-IDE-9.md) -> **Avancement Client (IDE 71)**

```mermaid
graph LR
    T71[71 Avancement Client]
    style T71 fill:#58a6ff
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
    CC9 --> T71
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [9](WEL-IDE-9.md) | Clients | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T71[71 Avancement Client]
    style T71 fill:#58a6ff
    C102[102 Zoom code occupation]
    T71 --> C102
    style C102 fill:#3fb950
    C103[103 Zoom groupe arrive...]
    T71 --> C103
    style C103 fill:#3fb950
    C80[80 Creation historique]
    T71 --> C80
    style C80 fill:#3fb950
    C81[81 Create logbook]
    T71 --> C81
    style C81 fill:#3fb950
    C104[104 Zoom lieu de sejour]
    T71 --> C104
    style C104 fill:#3fb950
    C105[105 Zoom code logement]
    T71 --> C105
    style C105 fill:#3fb950
    C106[106 Zoom qualite]
    T71 --> C106
    style C106 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [102](WEL-IDE-102.md) | Zoom code occupation | 2 | Selection/consultation |
| [103](WEL-IDE-103.md) | Zoom groupe arrivee depart | 2 | Selection/consultation |
| [80](WEL-IDE-80.md) | Creation historique | 1 | Historique/consultation |
| [81](WEL-IDE-81.md) | Create logbook | 1 | Sous-programme |
| [104](WEL-IDE-104.md) | Zoom lieu de sejour | 1 | Selection/consultation |
| [105](WEL-IDE-105.md) | Zoom code logement | 1 | Selection/consultation |
| [106](WEL-IDE-106.md) | Zoom qualite | 1 | Selection/consultation |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 444 | Taille moyenne |
| Expressions | 8 | Peu de logique |
| Tables WRITE | 8 | Fort impact donnees |
| Sous-programmes | 7 | Dependances moderees |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 444) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (14 taches: 3 ecrans, 11 traitements)

- **Strategie** : Orchestrateur avec 3 ecrans (Razor/React) et 11 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 7 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Consultation (2 taches: 0 ecran, 2 traitements)

- **Strategie** : Composants de recherche/selection en modales.

#### Saisie (1 tache: 1 ecran, 0 traitement)

- **Strategie** : Formulaire React/Blazor avec validation Zod/FluentValidation.
- Reproduire 1 ecran : Saisie Date Debut
- Validation temps reel cote client + serveur

#### Creation (2 taches: 0 ecran, 2 traitements)

- **Strategie** : Repository pattern avec Entity Framework Core.
- Insertion via `IRepository<T>.CreateAsync()`

#### Validation (3 taches: 0 ecran, 3 traitements)

- **Strategie** : FluentValidation avec validators specifiques.
- Chaque tache de validation -> un validator injectable

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| gm-recherche_____gmr | Table WRITE (Database) | 1x | Schema + repository |
| gm-complet_______gmc | Table WRITE (Database) | 1x | Schema + repository |
| hebergement______heb | Table WRITE (Database) | 6x | Schema + repository |
| client_gm | Table WRITE (Database) | 1x | Schema + repository |
| compte_gm________cgm | Table WRITE (Database) | 1x | Schema + repository |
| fichier_validation | Table WRITE (Database) | 1x | Schema + repository |
| groupe_arr_dep___vol | Table WRITE (Database) | 1x | Schema + repository |
| heb_circuit______hci | Table WRITE (Database) | 1x | Schema + repository |
| [Zoom groupe arrivee depart (IDE 103)](WEL-IDE-103.md) | Sous-programme | 2x | Haute - Selection/consultation |
| [Zoom code occupation (IDE 102)](WEL-IDE-102.md) | Sous-programme | 2x | Haute - Selection/consultation |
| [Zoom code logement (IDE 105)](WEL-IDE-105.md) | Sous-programme | 1x | Normale - Selection/consultation |
| [Zoom qualite (IDE 106)](WEL-IDE-106.md) | Sous-programme | 1x | Normale - Selection/consultation |
| [Zoom lieu de sejour (IDE 104)](WEL-IDE-104.md) | Sous-programme | 1x | Normale - Selection/consultation |
| [Creation historique (IDE 80)](WEL-IDE-80.md) | Sous-programme | 1x | Normale - Historique/consultation |
| [Create logbook (IDE 81)](WEL-IDE-81.md) | Sous-programme | 1x | Normale - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 21:34*
