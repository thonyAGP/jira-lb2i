# PBG IDE 320 - Verification Aut sans ecran

> **Analyse**: Phases 1-4 2026-02-03 11:07 -> 11:07 (18s) | Assemblage 11:07
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBG |
| IDE Position | 320 |
| Nom Programme | Verification Aut sans ecran |
| Fichier source | `Prg_320.xml` |
| Dossier IDE | General |
| Taches | 20 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Verification Aut sans ecran** assure la gestion complete de ce processus, accessible depuis [Sejours personnel SubForm (IDE 0)](PBG-IDE-0.md), [Sejours personnel CallTask (IDE 196)](PBG-IDE-196.md), [Module Sejours CallTask (IDE 0)](PBG-IDE-0.md), [Module Sejours CallTask (IDE 94)](PBG-IDE-94.md), [Module Sejours SubForm (IDE 391)](PBG-IDE-391.md), [Logement Client (IDE 0)](PBG-IDE-0.md), [Logement Exterieur (IDE 0)](PBG-IDE-0.md), [Logement Personnel (IDE 0)](PBG-IDE-0.md), [Logement Exterieur (IDE 171)](PBG-IDE-171.md), [Logement Personnel (IDE 172)](PBG-IDE-172.md), [Logement Client (IDE 173)](PBG-IDE-173.md), [Logement Client pms-626 (IDE 174)](PBG-IDE-174.md), [Logement Client (IDE 385)](PBG-IDE-385.md), [Modules clients Identite (IDE 91)](PBG-IDE-91.md), [  Creation personnel identites (IDE 194)](PBG-IDE-194.md), [Personnel Identites (IDE 195)](PBG-IDE-195.md), [Annuaire Logement (IDE 304)](PBG-IDE-304.md), [ Integrite personnel identites (IDE 345)](PBG-IDE-345.md), [Module personnel identites (IDE 373)](PBG-IDE-373.md), [Creation personnel identites S (IDE 380)](PBG-IDE-380.md).

Le flux de traitement s'organise en **3 blocs fonctionnels** :

- **Traitement** (16 taches) : traitements metier divers
- **Validation** (3 taches) : controles et verifications de coherence
- **Creation** (1 tache) : insertion d'enregistrements en base (mouvements, prestations)

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Validation (3 taches)

- **320** - Verification Autorisation
- **320.12** - Aut.Validation
- **320.13** - Aut.Devalidation

#### Phase 2 : Creation (1 tache)

- **320.1** - Aut.Creation

#### Phase 3 : Traitement (16 taches)

- **320.2** - Aut.Modification
- **320.3** - Aut.Modification
- **320.4** - Aut.Affectation
- **320.5** - Aut.Affectation
- **320.6** - Aut.Prolongation
- **320.7** - Aut.Interruption
- **320.8** - Aut.Avancement
- **320.9** - Aut.Recodification
- **320.10** - Aut.Annulation
- **320.11** - Aut.Messagerie
- **320.14** - Aut.Immigration
- **320.15** - Aut.Liberation
- **320.16** - Aut.Blocage
- **320.17** - Aut.Statut
- **320.18** - Aut.Statut
- **320.19** - Aut.Statut

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Validation (3 taches)

Controles de coherence : 3 taches verifient les donnees et conditions.

---

#### <a id="t1"></a>320 - Verification Autorisation

**Role** : Verification : Verification Autorisation.
**Variables liees** : B (P0-Autorisation)

---

#### <a id="t13"></a>320.12 - Aut.Validation

**Role** : Verification : Aut.Validation.

---

#### <a id="t14"></a>320.13 - Aut.Devalidation

**Role** : Verification : Aut.Devalidation.


### 3.2 Creation (1 tache)

Insertion de nouveaux enregistrements en base.

---

#### <a id="t2"></a>320.1 - Aut.Creation

**Role** : Creation d'enregistrement : Aut.Creation.


### 3.3 Traitement (16 taches)

Traitements internes.

---

#### <a id="t3"></a>320.2 - Aut.Modification

**Role** : Traitement : Aut.Modification.

---

#### <a id="t4"></a>320.3 - Aut.Modification

**Role** : Traitement : Aut.Modification.

---

#### <a id="t5"></a>320.4 - Aut.Affectation

**Role** : Traitement : Aut.Affectation.

---

#### <a id="t6"></a>320.5 - Aut.Affectation

**Role** : Traitement : Aut.Affectation.

---

#### <a id="t7"></a>320.6 - Aut.Prolongation

**Role** : Traitement : Aut.Prolongation.

---

#### <a id="t8"></a>320.7 - Aut.Interruption

**Role** : Traitement : Aut.Interruption.

---

#### <a id="t9"></a>320.8 - Aut.Avancement

**Role** : Traitement : Aut.Avancement.

---

#### <a id="t10"></a>320.9 - Aut.Recodification

**Role** : Traitement : Aut.Recodification.

---

#### <a id="t11"></a>320.10 - Aut.Annulation

**Role** : Traitement : Aut.Annulation.

---

#### <a id="t12"></a>320.11 - Aut.Messagerie

**Role** : Traitement : Aut.Messagerie.

---

#### <a id="t15"></a>320.14 - Aut.Immigration

**Role** : Traitement : Aut.Immigration.

---

#### <a id="t16"></a>320.15 - Aut.Liberation

**Role** : Traitement : Aut.Liberation.

---

#### <a id="t17"></a>320.16 - Aut.Blocage

**Role** : Traitement : Aut.Blocage.

---

#### <a id="t18"></a>320.17 - Aut.Statut

**Role** : Traitement : Aut.Statut.

---

#### <a id="t19"></a>320.18 - Aut.Statut

**Role** : Traitement : Aut.Statut.

---

#### <a id="t22"></a>320.19 - Aut.Statut

**Role** : Traitement : Aut.Statut.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Sejours personnel SubForm (IDE 0)](PBG-IDE-0.md), [Sejours personnel CallTask (IDE 196)](PBG-IDE-196.md), [Module Sejours CallTask (IDE 0)](PBG-IDE-0.md), [Module Sejours CallTask (IDE 94)](PBG-IDE-94.md), [Module Sejours SubForm (IDE 391)](PBG-IDE-391.md), [Logement Client (IDE 0)](PBG-IDE-0.md), [Logement Exterieur (IDE 0)](PBG-IDE-0.md), [Logement Personnel (IDE 0)](PBG-IDE-0.md), [Logement Exterieur (IDE 171)](PBG-IDE-171.md), [Logement Personnel (IDE 172)](PBG-IDE-172.md), [Logement Client (IDE 173)](PBG-IDE-173.md), [Logement Client pms-626 (IDE 174)](PBG-IDE-174.md), [Logement Client (IDE 385)](PBG-IDE-385.md), [Modules clients Identite (IDE 91)](PBG-IDE-91.md), [  Creation personnel identites (IDE 194)](PBG-IDE-194.md), [Personnel Identites (IDE 195)](PBG-IDE-195.md), [Annuaire Logement (IDE 304)](PBG-IDE-304.md), [ Integrite personnel identites (IDE 345)](PBG-IDE-345.md), [Module personnel identites (IDE 373)](PBG-IDE-373.md), [Creation personnel identites S (IDE 380)](PBG-IDE-380.md)
- **Appelle**: 0 programmes | **Tables**: 1 (W:0 R:1 L:0) | **Taches**: 20 | **Expressions**: 22

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (20 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **320.1** | [**Verification Autorisation** (320)](#t1) | MDI | - | Validation |
| 320.1.1 | [Aut.Validation (320.12)](#t13) | MDI | - | |
| 320.1.2 | [Aut.Devalidation (320.13)](#t14) | MDI | - | |
| **320.2** | [**Aut.Creation** (320.1)](#t2) | MDI | - | Creation |
| **320.3** | [**Aut.Modification** (320.2)](#t3) | MDI | - | Traitement |
| 320.3.1 | [Aut.Modification (320.3)](#t4) | MDI | - | |
| 320.3.2 | [Aut.Affectation (320.4)](#t5) | MDI | - | |
| 320.3.3 | [Aut.Affectation (320.5)](#t6) | MDI | - | |
| 320.3.4 | [Aut.Prolongation (320.6)](#t7) | MDI | - | |
| 320.3.5 | [Aut.Interruption (320.7)](#t8) | MDI | - | |
| 320.3.6 | [Aut.Avancement (320.8)](#t9) | MDI | - | |
| 320.3.7 | [Aut.Recodification (320.9)](#t10) | MDI | - | |
| 320.3.8 | [Aut.Annulation (320.10)](#t11) | MDI | - | |
| 320.3.9 | [Aut.Messagerie (320.11)](#t12) | MDI | - | |
| 320.3.10 | [Aut.Immigration (320.14)](#t15) | MDI | - | |
| 320.3.11 | [Aut.Liberation (320.15)](#t16) | MDI | - | |
| 320.3.12 | [Aut.Blocage (320.16)](#t17) | MDI | - | |
| 320.3.13 | [Aut.Statut (320.17)](#t18) | MDI | - | |
| 320.3.14 | [Aut.Statut (320.18)](#t19) | MDI | - | |
| 320.3.15 | [Aut.Statut (320.19)](#t22) | MDI | - | |

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
| 691 | commandes |  | DB | R |   |   | 19 |

### Colonnes par table (0 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 691 - commandes (R) - 19 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Autres (4)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P0-Societe | Alpha | - |
| B | P0-Autorisation | Alpha | 19x refs |
| C | P0-Accord Suite | Alpha | - |
| D | W0-Code F008 | Alpha | - |

## 12. EXPRESSIONS

**22 / 22 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONSTANTE | 2 | 0 |
| CONDITION | 19 | 0 |
| REFERENCE_VG | 1 | 0 |

### 12.2 Expressions cles par type

#### CONSTANTE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 2 | `'F008'` | - |
| CONSTANTE | 1 | `'N'` | - |

#### CONDITION (19 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 15 | `P0-Autorisation [B]='21'` | - |
| CONDITION | 16 | `P0-Autorisation [B]='22'` | - |
| CONDITION | 13 | `P0-Autorisation [B]='19'` | - |
| CONDITION | 14 | `P0-Autorisation [B]='20'` | - |
| CONDITION | 17 | `P0-Autorisation [B]='23'` | - |
| ... | | *+14 autres* | |

#### REFERENCE_VG (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 22 | `VG28` | - |

### 12.3 Toutes les expressions (22)

<details>
<summary>Voir les 22 expressions</summary>

#### CONSTANTE (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 1 | `'N'` |
| 2 | `'F008'` |

#### CONDITION (19)

| IDE | Expression Decodee |
|-----|-------------------|
| 3 | `P0-Autorisation [B]='09'` |
| 4 | `P0-Autorisation [B]='10'` |
| 5 | `P0-Autorisation [B]='11'` |
| 6 | `P0-Autorisation [B]='12'` |
| 7 | `P0-Autorisation [B]='13'` |
| 8 | `P0-Autorisation [B]='14'` |
| 9 | `P0-Autorisation [B]='15'` |
| 10 | `P0-Autorisation [B]='16'` |
| 11 | `P0-Autorisation [B]='17'` |
| 12 | `P0-Autorisation [B]='18'` |
| 13 | `P0-Autorisation [B]='19'` |
| 14 | `P0-Autorisation [B]='20'` |
| 15 | `P0-Autorisation [B]='21'` |
| 16 | `P0-Autorisation [B]='22'` |
| 17 | `P0-Autorisation [B]='23'` |
| 18 | `P0-Autorisation [B]='24'` |
| 19 | `P0-Autorisation [B]='25'` |
| 20 | `P0-Autorisation [B]='26'` |
| 21 | `P0-Autorisation [B]='27'` |

#### REFERENCE_VG (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 22 | `VG28` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Sejours personnel SubForm (IDE 0)](PBG-IDE-0.md) -> **Verification Aut sans ecran (IDE 320)**

Main -> ... -> [Sejours personnel CallTask (IDE 196)](PBG-IDE-196.md) -> **Verification Aut sans ecran (IDE 320)**

Main -> ... -> [Module Sejours CallTask (IDE 0)](PBG-IDE-0.md) -> **Verification Aut sans ecran (IDE 320)**

Main -> ... -> [Module Sejours CallTask (IDE 94)](PBG-IDE-94.md) -> **Verification Aut sans ecran (IDE 320)**

Main -> ... -> [Module Sejours SubForm (IDE 391)](PBG-IDE-391.md) -> **Verification Aut sans ecran (IDE 320)**

Main -> ... -> [Logement Client (IDE 0)](PBG-IDE-0.md) -> **Verification Aut sans ecran (IDE 320)**

Main -> ... -> [Logement Exterieur (IDE 0)](PBG-IDE-0.md) -> **Verification Aut sans ecran (IDE 320)**

Main -> ... -> [Logement Personnel (IDE 0)](PBG-IDE-0.md) -> **Verification Aut sans ecran (IDE 320)**

Main -> ... -> [Logement Exterieur (IDE 171)](PBG-IDE-171.md) -> **Verification Aut sans ecran (IDE 320)**

Main -> ... -> [Logement Personnel (IDE 172)](PBG-IDE-172.md) -> **Verification Aut sans ecran (IDE 320)**

Main -> ... -> [Logement Client (IDE 173)](PBG-IDE-173.md) -> **Verification Aut sans ecran (IDE 320)**

Main -> ... -> [Logement Client pms-626 (IDE 174)](PBG-IDE-174.md) -> **Verification Aut sans ecran (IDE 320)**

Main -> ... -> [Logement Client (IDE 385)](PBG-IDE-385.md) -> **Verification Aut sans ecran (IDE 320)**

Main -> ... -> [Modules clients Identite (IDE 91)](PBG-IDE-91.md) -> **Verification Aut sans ecran (IDE 320)**

Main -> ... -> [  Creation personnel identites (IDE 194)](PBG-IDE-194.md) -> **Verification Aut sans ecran (IDE 320)**

Main -> ... -> [Personnel Identites (IDE 195)](PBG-IDE-195.md) -> **Verification Aut sans ecran (IDE 320)**

Main -> ... -> [Annuaire Logement (IDE 304)](PBG-IDE-304.md) -> **Verification Aut sans ecran (IDE 320)**

Main -> ... -> [ Integrite personnel identites (IDE 345)](PBG-IDE-345.md) -> **Verification Aut sans ecran (IDE 320)**

Main -> ... -> [Module personnel identites (IDE 373)](PBG-IDE-373.md) -> **Verification Aut sans ecran (IDE 320)**

Main -> ... -> [Creation personnel identites S (IDE 380)](PBG-IDE-380.md) -> **Verification Aut sans ecran (IDE 320)**

```mermaid
graph LR
    T320[320 Verification Aut s...]
    style T320 fill:#58a6ff
    CALLER196[196 Sejours personnel ...]
    CALLER196 --> T320
    style CALLER196 fill:#3fb950
    CALLER94[94 Module Sejours Call...]
    CALLER94 --> T320
    style CALLER94 fill:#3fb950
    CALLER391[391 Module Sejours Sub...]
    CALLER391 --> T320
    style CALLER391 fill:#3fb950
    CALLER171[171 Logement Exterieur]
    CALLER171 --> T320
    style CALLER171 fill:#3fb950
    CALLER172[172 Logement Personnel]
    CALLER172 --> T320
    style CALLER172 fill:#3fb950
    CALLER173[173 Logement Client]
    CALLER173 --> T320
    style CALLER173 fill:#3fb950
    CALLER174[174 Logement Client pm...]
    CALLER174 --> T320
    style CALLER174 fill:#3fb950
    CALLER385[385 Logement Client]
    CALLER385 --> T320
    style CALLER385 fill:#3fb950
    CALLER91[91 Modules clients Ide...]
    CALLER91 --> T320
    style CALLER91 fill:#3fb950
    CALLER194[194 Creation personnel...]
    CALLER194 --> T320
    style CALLER194 fill:#3fb950
    CALLER195[195 Personnel Identites]
    CALLER195 --> T320
    style CALLER195 fill:#3fb950
    CALLER304[304 Annuaire Logement]
    CALLER304 --> T320
    style CALLER304 fill:#3fb950
    CALLER345[345 Integrite personne...]
    CALLER345 --> T320
    style CALLER345 fill:#3fb950
    CALLER373[373 Module personnel i...]
    CALLER373 --> T320
    style CALLER373 fill:#3fb950
    CALLER380[380 Creation personnel...]
    CALLER380 --> T320
    style CALLER380 fill:#3fb950
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [0](PBG-IDE-0.md) | Sejours personnel SubForm | 11 |
| [196](PBG-IDE-196.md) | Sejours personnel CallTask | 11 |
| [0](PBG-IDE-0.md) | Module Sejours CallTask | 8 |
| [94](PBG-IDE-94.md) | Module Sejours CallTask | 8 |
| [391](PBG-IDE-391.md) | Module Sejours SubForm | 8 |
| [0](PBG-IDE-0.md) | Logement Client | 4 |
| [0](PBG-IDE-0.md) | Logement Exterieur | 4 |
| [0](PBG-IDE-0.md) | Logement Personnel | 4 |
| [171](PBG-IDE-171.md) | Logement Exterieur | 4 |
| [172](PBG-IDE-172.md) | Logement Personnel | 4 |
| [173](PBG-IDE-173.md) | Logement Client | 4 |
| [174](PBG-IDE-174.md) | Logement Client pms-626 | 4 |
| [385](PBG-IDE-385.md) | Logement Client | 4 |
| [91](PBG-IDE-91.md) | Modules clients Identite | 2 |
| [194](PBG-IDE-194.md) |   Creation personnel identites | 2 |
| [195](PBG-IDE-195.md) | Personnel Identites | 2 |
| [304](PBG-IDE-304.md) | Annuaire Logement | 2 |
| [345](PBG-IDE-345.md) |  Integrite personnel identites | 2 |
| [373](PBG-IDE-373.md) | Module personnel identites | 2 |
| [380](PBG-IDE-380.md) | Creation personnel identites S | 2 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T320[320 Verification Aut s...]
    style T320 fill:#58a6ff
    NONE[Aucun callee]
    T320 -.-> NONE
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
| Expressions | 22 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 198) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Validation (3 taches: 0 ecran, 3 traitements)

- **Strategie** : FluentValidation avec validators specifiques.
- Chaque tache de validation -> un validator injectable

#### Creation (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Repository pattern avec Entity Framework Core.
- Insertion via `IRepository<T>.CreateAsync()`

#### Traitement (16 taches: 0 ecran, 16 traitements)

- **Strategie** : 16 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 11:07*
