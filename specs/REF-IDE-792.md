# REF IDE 792 - Verification Autorisation

> **Analyse**: Phases 1-4 2026-02-03 14:23 -> 14:24 (14s) | Assemblage 14:24
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | REF |
| IDE Position | 792 |
| Nom Programme | Verification Autorisation |
| Fichier source | `Prg_792.xml` |
| Dossier IDE | General |
| Taches | 20 (0 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 0 |
| :warning: Statut | **ORPHELIN_POTENTIEL** |

## 2. DESCRIPTION FONCTIONNELLE

**Verification Autorisation** assure la gestion complete de ce processus.

Le flux de traitement s'organise en **3 blocs fonctionnels** :

- **Traitement** (16 taches) : traitements metier divers
- **Validation** (3 taches) : controles et verifications de coherence
- **Creation** (1 tache) : insertion d'enregistrements en base (mouvements, prestations)

**Donnees modifiees** : 1 tables en ecriture (tables_operateurs).

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Validation (3 taches)

- **792** - Verification Autorisation
- **792.13** - Aut.Validation
- **792.14** - Aut.Devalidation

#### Phase 2 : Traitement (16 taches)

- **792.1** - Aut.Statut
- **792.3** - Aut.Modification
- **792.4** - Aut.Modification
- **792.5** - Aut.Affectation
- **792.6** - Aut.Affectation
- **792.7** - Aut.Prolongation
- **792.8** - Aut.Interruption
- **792.9** - Aut.Avancement
- **792.10** - Aut.Recodification
- **792.11** - Aut.Annulation
- **792.12** - Aut.Messagerie
- **792.15** - Aut.Immigration
- **792.16** - Aut.Liberation
- **792.17** - Aut.Blocage
- **792.18** - Aut.Statut
- **792.19** - Aut.Statut

#### Phase 3 : Creation (1 tache)

- **792.2** - Aut.Creation

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| tables_operateurs | **W** (19 usages) |  |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Validation (3 taches)

Controles de coherence : 3 taches verifient les donnees et conditions.

---

#### <a id="t1"></a>792 - Verification Autorisation

**Role** : Verification : Verification Autorisation.
**Variables liees** : B (P0-Autorisation)

---

#### <a id="t14"></a>792.13 - Aut.Validation

**Role** : Verification : Aut.Validation.

---

#### <a id="t15"></a>792.14 - Aut.Devalidation

**Role** : Verification : Aut.Devalidation.


### 3.2 Traitement (16 taches)

Traitements internes.

---

#### <a id="t2"></a>792.1 - Aut.Statut

**Role** : Traitement : Aut.Statut.

---

#### <a id="t4"></a>792.3 - Aut.Modification

**Role** : Traitement : Aut.Modification.

---

#### <a id="t5"></a>792.4 - Aut.Modification

**Role** : Traitement : Aut.Modification.

---

#### <a id="t6"></a>792.5 - Aut.Affectation

**Role** : Traitement : Aut.Affectation.

---

#### <a id="t7"></a>792.6 - Aut.Affectation

**Role** : Traitement : Aut.Affectation.

---

#### <a id="t8"></a>792.7 - Aut.Prolongation

**Role** : Traitement : Aut.Prolongation.

---

#### <a id="t9"></a>792.8 - Aut.Interruption

**Role** : Traitement : Aut.Interruption.

---

#### <a id="t10"></a>792.9 - Aut.Avancement

**Role** : Traitement : Aut.Avancement.

---

#### <a id="t11"></a>792.10 - Aut.Recodification

**Role** : Traitement : Aut.Recodification.

---

#### <a id="t12"></a>792.11 - Aut.Annulation

**Role** : Traitement : Aut.Annulation.

---

#### <a id="t13"></a>792.12 - Aut.Messagerie

**Role** : Traitement : Aut.Messagerie.

---

#### <a id="t16"></a>792.15 - Aut.Immigration

**Role** : Traitement : Aut.Immigration.

---

#### <a id="t17"></a>792.16 - Aut.Liberation

**Role** : Traitement : Aut.Liberation.

---

#### <a id="t18"></a>792.17 - Aut.Blocage

**Role** : Traitement : Aut.Blocage.

---

#### <a id="t19"></a>792.18 - Aut.Statut

**Role** : Traitement : Aut.Statut.

---

#### <a id="t20"></a>792.19 - Aut.Statut

**Role** : Traitement : Aut.Statut.


### 3.3 Creation (1 tache)

Insertion de nouveaux enregistrements en base.

---

#### <a id="t3"></a>792.2 - Aut.Creation

**Role** : Creation d'enregistrement : Aut.Creation.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: (aucun)
- **Appelle**: 0 programmes | **Tables**: 1 (W:1 R:0 L:0) | **Taches**: 20 | **Expressions**: 22

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (20 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **792.1** | [**Verification Autorisation** (792)](#t1) | MDI | - | Validation |
| 792.1.1 | [Aut.Validation (792.13)](#t14) | MDI | - | |
| 792.1.2 | [Aut.Devalidation (792.14)](#t15) | MDI | - | |
| **792.2** | [**Aut.Statut** (792.1)](#t2) | MDI | - | Traitement |
| 792.2.1 | [Aut.Modification (792.3)](#t4) | MDI | - | |
| 792.2.2 | [Aut.Modification (792.4)](#t5) | MDI | - | |
| 792.2.3 | [Aut.Affectation (792.5)](#t6) | MDI | - | |
| 792.2.4 | [Aut.Affectation (792.6)](#t7) | MDI | - | |
| 792.2.5 | [Aut.Prolongation (792.7)](#t8) | MDI | - | |
| 792.2.6 | [Aut.Interruption (792.8)](#t9) | MDI | - | |
| 792.2.7 | [Aut.Avancement (792.9)](#t10) | MDI | - | |
| 792.2.8 | [Aut.Recodification (792.10)](#t11) | MDI | - | |
| 792.2.9 | [Aut.Annulation (792.11)](#t12) | MDI | - | |
| 792.2.10 | [Aut.Messagerie (792.12)](#t13) | MDI | - | |
| 792.2.11 | [Aut.Immigration (792.15)](#t16) | MDI | - | |
| 792.2.12 | [Aut.Liberation (792.16)](#t17) | MDI | - | |
| 792.2.13 | [Aut.Blocage (792.17)](#t18) | MDI | - | |
| 792.2.14 | [Aut.Statut (792.18)](#t19) | MDI | - | |
| 792.2.15 | [Aut.Statut (792.19)](#t20) | MDI | - | |
| **792.3** | [**Aut.Creation** (792.2)](#t3) | MDI | - | Creation |

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

### Tables utilisees (1)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 116 | tables_operateurs |  | DB |   | **W** |   | 19 |

### Colonnes par table (0 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 116 - tables_operateurs (**W**) - 19 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Autres (4)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P0-Societe | Alpha | - |
| B | P0-Autorisation | Alpha | 19x refs |
| C | P0-Accord Suite | Alpha | 1x refs |
| D | W0-Code F008 | Alpha | - |

## 12. EXPRESSIONS

**22 / 22 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONSTANTE | 2 | 0 |
| CONDITION | 20 | 0 |

### 12.2 Expressions cles par type

#### CONSTANTE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 2 | `'F008'` | - |
| CONSTANTE | 1 | `'N'` | - |

#### CONDITION (20 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 16 | `P0-Autorisation [B]='22'` | - |
| CONDITION | 17 | `P0-Autorisation [B]='23'` | - |
| CONDITION | 15 | `P0-Autorisation [B]='21'` | - |
| CONDITION | 13 | `P0-Autorisation [B]='19'` | - |
| CONDITION | 14 | `P0-Autorisation [B]='20'` | - |
| ... | | *+15 autres* | |

### 12.3 Toutes les expressions (22)

<details>
<summary>Voir les 22 expressions</summary>

#### CONSTANTE (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 1 | `'N'` |
| 2 | `'F008'` |

#### CONDITION (20)

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
| 22 | `P0-Accord Suite [C]='N'` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

**Chemin**: (pas de callers directs)

```mermaid
graph LR
    T792[792 Verification Autor...]
    style T792 fill:#58a6ff
    NONE[Aucun caller]
    NONE -.-> T792
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| - | (aucun) | - |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T792[792 Verification Autor...]
    style T792 fill:#58a6ff
    NONE[Aucun callee]
    T792 -.-> NONE
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
| Lignes de logique | 199 | Programme compact |
| Expressions | 22 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 199) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Validation (3 taches: 0 ecran, 3 traitements)

- **Strategie** : FluentValidation avec validators specifiques.
- Chaque tache de validation -> un validator injectable

#### Traitement (16 taches: 0 ecran, 16 traitements)

- **Strategie** : 16 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

#### Creation (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Repository pattern avec Entity Framework Core.
- Insertion via `IRepository<T>.CreateAsync()`

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| tables_operateurs | Table WRITE (Database) | 19x | Schema + repository |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 14:24*
