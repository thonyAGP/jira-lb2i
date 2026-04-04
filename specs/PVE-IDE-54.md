# PVE IDE 54 - Create TemdbPackage ARCH

> **Analyse**: Phases 1-4 2026-02-03 08:59 -> 08:59 (21s) | Assemblage 08:59
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PVE |
| IDE Position | 54 |
| Nom Programme | Create TemdbPackage ARCH |
| Fichier source | `Prg_54.xml` |
| Domaine metier | General |
| Taches | 4 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Create TemdbPackage ARCH** assure la gestion complete de ce processus, accessible depuis [Get Temp Files (IDE 46)](PVE-IDE-46.md).

Le flux de traitement s'organise en **2 blocs fonctionnels** :

- **Traitement** (3 taches) : traitements metier divers
- **Creation** (1 tache) : insertion d'enregistrements en base (mouvements, prestations)

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Creation (1 tache)

- **54** - Create TemdbPackage ARCH **[[ECRAN]](#ecran-t1)**

#### Phase 2 : Traitement (3 taches)

- **54.1** - Packages
- **54.2** - Packages BCK
- **54.3** - Packages

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Creation (1 tache)

Insertion de nouveaux enregistrements en base.

---

#### <a id="t1"></a>54 - Create TemdbPackage ARCH [[ECRAN]](#ecran-t1)

**Role** : Traitement : Create TemdbPackage ARCH.
**Ecran** : 478 x 0 DLU | [Voir mockup](#ecran-t1)


### 3.2 Traitement (3 taches)

Traitements internes.

---

#### <a id="t2"></a>54.1 - Packages

**Role** : Traitement : Packages.

---

#### <a id="t3"></a>54.2 - Packages BCK

**Role** : Traitement : Packages BCK.

---

#### <a id="t4"></a>54.3 - Packages

**Role** : Traitement : Packages.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Get Temp Files (IDE 46)](PVE-IDE-46.md)
- **Appelle**: 0 programmes | **Tables**: 0 (W:0 R:0 L:0) | **Taches**: 4 | **Expressions**: 8

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (4 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **54.1** | [**Create TemdbPackage ARCH** (54)](#t1) [mockup](#ecran-t1) | - | 478x0 | Creation |
| **54.2** | [**Packages** (54.1)](#t2) | - | - | Traitement |
| 54.2.1 | [Packages BCK (54.2)](#t3) | - | - | |
| 54.2.2 | [Packages (54.3)](#t4) | - | - | |

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

### 11.1 Parametres entrants (5)

Variables recues du programme appelant ([Get Temp Files (IDE 46)](PVE-IDE-46.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P Nom Table | Alpha | - |
| B | P Refusal to sell | Numeric | 4x parametre entrant |
| C | P.Liste Service | Alpha | 4x parametre entrant |
| D | P Date Debut | Date | - |
| E | P Date Fin | Date | - |

### 11.2 Variables de session (1)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| F | v Clause Where | Alpha | 3x session |

## 12. EXPRESSIONS

**8 / 8 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONSTANTE | 1 | 0 |
| CONDITION | 4 | 0 |
| CONCATENATION | 3 | 0 |

### 12.2 Expressions cles par type

#### CONSTANTE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 1 | `' and '` | - |

#### CONDITION (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 5 | `P.Liste Service [C]<>'' AND(P Refusal to sell [B]=1 OR P Refusal to sell [B]=2)` | - |
| CONDITION | 7 | `P.Liste Service [C]<>''` | - |
| CONDITION | 3 | `P Refusal to sell [B]=1 OR P Refusal to sell [B]=2 OR P.Liste Service [C]<>''` | - |
| CONDITION | 4 | `P Refusal to sell [B]=1 OR P Refusal to sell [B]=2` | - |

#### CONCATENATION (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 8 | `Trim(v Clause Where [F])& ' and '` | - |
| CONCATENATION | 6 | `Trim(v Clause Where [F])&' a.arc_pv_service IN ('&Trim(P.Liste Service [C])&')'` | - |
| CONCATENATION | 2 | `Trim(v Clause Where [F])&IF(P Refusal to sell [B]=1,' a.arc_payment_type = ''REFUSAL TO SELL'' ',IF(P Refusal to sell [B]=2,' a.arc_payment_type <> ''REFUSAL TO SELL'' ',''))
` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Get Temp Files (IDE 46)](PVE-IDE-46.md) -> **Create TemdbPackage ARCH (IDE 54)**

```mermaid
graph LR
    T54[54 Create TemdbPackage...]
    style T54 fill:#58a6ff
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
    CC46 --> T54
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [46](PVE-IDE-46.md) | Get Temp Files | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T54[54 Create TemdbPackage...]
    style T54 fill:#58a6ff
    NONE[Aucun callee]
    T54 -.-> NONE
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
| Lignes de logique | 25 | Programme compact |
| Expressions | 8 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 25) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Creation (1 tache: 1 ecran, 0 traitement)

- **Strategie** : Repository pattern avec Entity Framework Core.
- Insertion via `IRepository<T>.CreateAsync()`

#### Traitement (3 taches: 0 ecran, 3 traitements)

- **Strategie** : 3 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 08:59*
