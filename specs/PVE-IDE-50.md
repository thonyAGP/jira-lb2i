# PVE IDE 50 - Create TempAccounting PMS

> **Analyse**: Phases 1-4 2026-02-03 08:57 -> 08:57 (22s) | Assemblage 08:57
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PVE |
| IDE Position | 50 |
| Nom Programme | Create TempAccounting PMS |
| Fichier source | `Prg_50.xml` |
| Domaine metier | General |
| Taches | 3 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Create TempAccounting PMS** assure la gestion complete de ce processus, accessible depuis [Get Temp Files (IDE 46)](PVE-IDE-46.md).

Le flux de traitement s'organise en **2 blocs fonctionnels** :

- **Creation** (2 taches) : insertion d'enregistrements en base (mouvements, prestations)
- **Traitement** (1 tache) : traitements metier divers

**Logique metier** : 1 regles identifiees couvrant conditions metier.

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Creation (2 taches)

- **50** - Create TempAccounting PMS **[[ECRAN]](#ecran-t1)**
- **50.2** - Accounting Sql Create

#### Phase 2 : Traitement (1 tache)

- **50.1** - Delete Doublons

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Creation (2 taches)

Insertion de nouveaux enregistrements en base.

---

#### <a id="t1"></a>50 - Create TempAccounting PMS [[ECRAN]](#ecran-t1)

**Role** : Traitement : Create TempAccounting PMS.
**Ecran** : 614 x 188 DLU | [Voir mockup](#ecran-t1)

---

#### <a id="t9"></a>50.2 - Accounting Sql Create

**Role** : Traitement : Accounting Sql Create.


### 3.2 Traitement (1 tache)

Traitements internes.

---

#### <a id="t2"></a>50.1 - Delete Doublons

**Role** : Traitement : Delete Doublons.


## 5. REGLES METIER

1 regles identifiees:

### Autres (1 regles)

#### <a id="rm-RM-001"></a>[RM-001] Traitement si {1,2} est renseigne

| Element | Detail |
|---------|--------|
| **Condition** | `{1` |
| **Si vrai** | 2}<>'' |
| **Si faux** | ' and pv_service in ('&Trim({1,2})&')','') |
| **Expression source** | Expression 3 : `IF({1,2}<>'', ' and pv_service in ('&Trim({1,2})&')','')` |
| **Exemple** | Si {1 â†’ 2}<>''. Sinon â†’ ' and pv_service in ('&Trim({1,2})&')','') |

## 6. CONTEXTE

- **Appele par**: [Get Temp Files (IDE 46)](PVE-IDE-46.md)
- **Appelle**: 0 programmes | **Tables**: 0 (W:0 R:0 L:0) | **Taches**: 3 | **Expressions**: 3

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (3 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **50.1** | [**Create TempAccounting PMS** (50)](#t1) [mockup](#ecran-t1) | - | 614x188 | Creation |
| 50.1.1 | [Accounting Sql Create (50.2)](#t9) | - | - | |
| **50.2** | [**Delete Doublons** (50.1)](#t2) | - | - | Traitement |

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

### Tables utilisees (0)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|

### Colonnes par table (0 / 0 tables avec colonnes identifiees)

## 11. VARIABLES

### 11.1 Parametres entrants (3)

Variables recues du programme appelant ([Get Temp Files (IDE 46)](PVE-IDE-46.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| B | P Liste Service | Alpha | - |
| C | P Date Debut | Date | - |
| D | P Date Fin | Date | - |

### 11.2 Autres (1)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | Nom Fichier | Alpha | - |

## 12. EXPRESSIONS

**3 / 3 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONDITION | 1 | 5 |
| FORMAT | 1 | 0 |
| STRING | 1 | 0 |

### 12.2 Expressions cles par type

#### CONDITION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 3 | `IF({1,2}<>'', ' and pv_service in ('&Trim({1,2})&')','')` | [RM-001](#rm-RM-001) |

#### FORMAT (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| FORMAT | 2 | `'('&DStr({1,3},'YYYYMMDD')&') and ('&DStr({1,4},'YYYYMMDD')&')'` | - |

#### STRING (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| STRING | 1 | `Trim({1,1})` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Get Temp Files (IDE 46)](PVE-IDE-46.md) -> **Create TempAccounting PMS (IDE 50)**

```mermaid
graph LR
    T50[50 Create TempAccounti...]
    style T50 fill:#58a6ff
    CC353[353 Menu==V4]
    style CC353 fill:#8b5cf6
    CC185[185 Menu]
    style CC185 fill:#8b5cf6
    CC439[439 Menu]
    style CC439 fill:#8b5cf6
    CC420[420 Menu==V4___]
    style CC420 fill:#8b5cf6
    CC182[182 Menu Reports]
    style CC182 fill:#f59e0b
    CC25[25 Report - Cost by Place]
    style CC25 fill:#f59e0b
    CC22[22 Report - Cost by Ca...]
    style CC22 fill:#f59e0b
    CC21[21 Report - Cost by Day]
    style CC21 fill:#f59e0b
    CC24[24 Report - Cost by Se...]
    style CC24 fill:#f59e0b
    CC23[23 Report - Cost by Pr...]
    style CC23 fill:#f59e0b
    CC46[46 Get Temp Files]
    style CC46 fill:#3fb950
    CC21 --> CC46
    CC22 --> CC46
    CC23 --> CC46
    CC24 --> CC46
    CC25 --> CC46
    CC182 --> CC21
    CC182 --> CC22
    CC182 --> CC23
    CC182 --> CC24
    CC182 --> CC25
    CC185 --> CC182
    CC353 --> CC182
    CC420 --> CC182
    CC439 --> CC182
    CC46 --> T50
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [46](PVE-IDE-46.md) | Get Temp Files | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T50[50 Create TempAccounti...]
    style T50 fill:#58a6ff
    NONE[Aucun callee]
    T50 -.-> NONE
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
| Lignes de logique | 10 | Programme compact |
| Expressions | 3 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 10) | Code sain |
| Regles metier | 1 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Creation (2 taches: 1 ecran, 1 traitement)

- **Strategie** : Repository pattern avec Entity Framework Core.
- Insertion via `IRepository<T>.CreateAsync()`

#### Traitement (1 tache: 0 ecran, 1 traitement)

- **Strategie** : 1 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 08:57*
