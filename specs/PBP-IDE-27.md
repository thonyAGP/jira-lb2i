# PBP IDE 27 - Recherche GM Previsionnel

> **Analyse**: Phases 1-4 2026-02-03 01:14 -> 01:15 (39s) | Assemblage 01:15
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBP |
| IDE Position | 27 |
| Nom Programme | Recherche GM Previsionnel |
| Fichier source | `Prg_27.xml` |
| Domaine metier | Consultation |
| Taches | 4 (0 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Recherche GM Previsionnel** assure la gestion complete de ce processus, accessible depuis [Demande Edition GM (IDE 18)](PBP-IDE-18.md).

Le flux de traitement s'organise en **2 blocs fonctionnels** :

- **Consultation** (3 taches) : ecrans de recherche, selection et consultation
- **Traitement** (1 tache) : traitements metier divers

**Donnees modifiees** : 1 tables en ecriture (tempo_selection).

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Consultation (3 taches)

- **27** - Rechercge GM Previsionnel
- **27.2** - Recherche cabine
- **27.3** - Recherche muster

#### Phase 2 : Traitement (1 tache)

- **27.1** - Complete

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| tempo_selection | **W** (1 usages) | Table temporaire ecran |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Consultation (3 taches)

Ecrans de recherche et consultation.

---

#### <a id="t1"></a>27 - Rechercge GM Previsionnel

**Role** : Traitement : Rechercge GM Previsionnel.

---

#### <a id="t3"></a>27.2 - Recherche cabine

**Role** : Traitement : Recherche cabine.
**Variables liees** : B (v. cabine)

---

#### <a id="t4"></a>27.3 - Recherche muster

**Role** : Traitement : Recherche muster.
**Variables liees** : C (v. muster)


### 3.2 Traitement (1 tache)

Traitements internes.

---

#### <a id="t2"></a>27.1 - Complete

**Role** : Traitement : Complete.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Demande Edition GM (IDE 18)](PBP-IDE-18.md)
- **Appelle**: 0 programmes | **Tables**: 8 (W:1 R:3 L:4) | **Taches**: 4 | **Expressions**: 10

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (4 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **27.1** | [**Rechercge GM Previsionnel** (27)](#t1) | MDI | - | Consultation |
| 27.1.1 | [Recherche cabine (27.2)](#t3) | MDI | - | |
| 27.1.2 | [Recherche muster (27.3)](#t4) | MDI | - | |
| **27.2** | [**Complete** (27.1)](#t2) | MDI | - | Traitement |

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

### Tables utilisees (8)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 31 | gm-complet_______gmc |  | DB | R |   |   | 1 |
| 34 | hebergement______heb | Hebergement (chambres) | DB | R |   |   | 1 |
| 36 | client_gm |  | DB |   |   | L | 1 |
| 119 | tables_pays_tel_ |  | DB |   |   | L | 1 |
| 131 | fichier_validation |  | DB |   |   | L | 1 |
| 364 | pms_footer_comment |  | DB |   |   | L | 1 |
| 632 | tempo_selection | Table temporaire ecran | DB |   | **W** |   | 1 |
| 689 | sous_imputation_par_service | Services / filieres | DB | R |   |   | 1 |

### Colonnes par table (1 / 4 tables avec colonnes identifiees)

<details>
<summary>Table 31 - gm-complet_______gmc (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | > Date | R | Date |
| B | v. cabine | R | Alpha |
| C | v. muster | R | Numeric |
| D | v. deck | R | Alpha |
| E | v. zone | R | Numeric |

</details>

<details>
<summary>Table 34 - hebergement______heb (R) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 632 - tempo_selection (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 689 - sous_imputation_par_service (R) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Variables de session (4)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| B | v. cabine | Alpha | [27.2](#t3) |
| C | v. muster | Numeric | - |
| D | v. deck | Alpha | 1x session |
| E | v. zone | Numeric | 1x session |

### 11.2 Autres (1)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | > Date | Date | 2x refs |

## 12. EXPRESSIONS

**10 / 10 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONDITION | 2 | 0 |
| OTHER | 8 | 0 |

### 12.2 Expressions cles par type

#### CONDITION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 5 | `> Date [A]=v. cabine [B]` | - |
| CONDITION | 1 | `> Date [A]` | - |

#### OTHER (8 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 8 | `[K]` | - |
| OTHER | 7 | `GetParam ('LANGUE')` | - |
| OTHER | 10 | `[R]` | - |
| OTHER | 9 | `[V]` | - |
| OTHER | 3 | `v. zone [E]` | - |
| ... | | *+3 autres* | |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Demande Edition GM (IDE 18)](PBP-IDE-18.md) -> **Recherche GM Previsionnel (IDE 27)**

```mermaid
graph LR
    T27[27 Recherche GM Previs...]
    style T27 fill:#58a6ff
    CC18[18 Demande Edition GM]
    style CC18 fill:#8b5cf6
    CC18 --> T27
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [18](PBP-IDE-18.md) | Demande Edition GM | 2 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T27[27 Recherche GM Previs...]
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
| Lignes de logique | 136 | Programme compact |
| Expressions | 10 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 136) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Consultation (3 taches: 0 ecran, 3 traitements)

- **Strategie** : Composants de recherche/selection en modales.

#### Traitement (1 tache: 0 ecran, 1 traitement)

- **Strategie** : 1 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| tempo_selection | Table WRITE (Database) | 1x | Schema + repository |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 01:15*
