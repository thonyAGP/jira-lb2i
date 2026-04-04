# PVE IDE 81 - Liste services=>tempo_userlist

> **Analyse**: Phases 1-4 2026-02-03 09:13 -> 09:13 (19s) | Assemblage 09:13
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PVE |
| IDE Position | 81 |
| Nom Programme | Liste services=>tempo_userlist |
| Fichier source | `Prg_81.xml` |
| Domaine metier | General |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Liste services=>tempo_userlist** assure la gestion complete de ce processus, accessible depuis [Get Temp Files (IDE 46)](PVE-IDE-46.md), [Ecran Prepaid Income GEST (IDE 82)](PVE-IDE-82.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>81 - Liste service [[ECRAN]](#ecran-t1)

**Role** : Traitement : Liste service.
**Ecran** : 654 x 303 DLU | [Voir mockup](#ecran-t1)
**Variables liees** : A (Pi.Service(TOUS), sinon liste), B (Po. Nombre Service coché)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Get Temp Files (IDE 46)](PVE-IDE-46.md), [Ecran Prepaid Income GEST (IDE 82)](PVE-IDE-82.md)
- **Appelle**: 0 programmes | **Tables**: 2 (W:0 R:1 L:1) | **Taches**: 1 | **Expressions**: 12

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **81.1** | [**Liste service** (81)](#t1) [mockup](#ecran-t1) | - | 654x303 | Traitement |

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

### Tables utilisees (2)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 67 | tables___________tab |  | DB | R |   |   | 1 |
| 637 | tempo_zone_secteur | Table temporaire ecran | DB |   |   | L | 1 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 67 - tables___________tab (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | Pi.Service(TOUS), sinon liste | R | Unicode |
| B | Po. Nombre Service coché | R | Numeric |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (2)

Variables recues du programme appelant ([Get Temp Files (IDE 46)](PVE-IDE-46.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | Pi.Service(TOUS), sinon liste | Unicode | - |
| B | Po. Nombre Service coché | Numeric | - |

## 12. EXPRESSIONS

**12 / 12 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCULATION | 1 | 0 |
| CONSTANTE | 4 | 0 |
| REFERENCE_VG | 1 | 0 |
| OTHER | 4 | 0 |
| FORMAT | 1 | 0 |
| STRING | 1 | 0 |

### 12.2 Expressions cles par type

#### CALCULATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 11 | `[AQ]+1` | - |

#### CONSTANTE (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 9 | `'O'` | - |
| CONSTANTE | 10 | `0` | - |
| CONSTANTE | 3 | `''` | - |
| CONSTANTE | 4 | `'VSERV'` | - |

#### REFERENCE_VG (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 1 | `VG1` | - |

#### OTHER (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 6 | `[Z]` | - |
| OTHER | 12 | `[AL]` | - |
| OTHER | 2 | `[Y]` | - |
| OTHER | 5 | `[V]` | - |

#### FORMAT (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| FORMAT | 7 | `InStr(Trim(Pi.Service(TOUS), sino... [A]),Trim([Z]))<>0 OR Trim(Pi.Service(TOUS), sino... [A])='TOUS'` | - |

#### STRING (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| STRING | 8 | `Trim([AD])` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Get Temp Files (IDE 46)](PVE-IDE-46.md) -> **Liste services=>tempo_userlist (IDE 81)**

Main -> ... -> [Ecran Prepaid Income GEST (IDE 82)](PVE-IDE-82.md) -> **Liste services=>tempo_userlist (IDE 81)**

```mermaid
graph LR
    T81[81 Liste services=temp...]
    style T81 fill:#58a6ff
    CC353[353 Menu==V4]
    style CC353 fill:#8b5cf6
    CC185[185 Menu]
    style CC185 fill:#8b5cf6
    CC439[439 Menu]
    style CC439 fill:#8b5cf6
    CC420[420 Menu==V4___]
    style CC420 fill:#8b5cf6
    CC25[25 Report - Cost by Place]
    style CC25 fill:#f59e0b
    CC182[182 Menu Reports]
    style CC182 fill:#f59e0b
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
    CC82[82 Ecran Prepaid Incom...]
    style CC82 fill:#3fb950
    CC21 --> CC46
    CC22 --> CC46
    CC23 --> CC46
    CC24 --> CC46
    CC25 --> CC46
    CC182 --> CC46
    CC21 --> CC82
    CC22 --> CC82
    CC23 --> CC82
    CC24 --> CC82
    CC25 --> CC82
    CC182 --> CC82
    CC185 --> CC21
    CC353 --> CC21
    CC420 --> CC21
    CC439 --> CC21
    CC185 --> CC22
    CC353 --> CC22
    CC420 --> CC22
    CC439 --> CC22
    CC185 --> CC23
    CC353 --> CC23
    CC420 --> CC23
    CC439 --> CC23
    CC185 --> CC24
    CC353 --> CC24
    CC420 --> CC24
    CC439 --> CC24
    CC185 --> CC25
    CC353 --> CC25
    CC420 --> CC25
    CC439 --> CC25
    CC185 --> CC182
    CC353 --> CC182
    CC420 --> CC182
    CC439 --> CC182
    CC46 --> T81
    CC82 --> T81
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [46](PVE-IDE-46.md) | Get Temp Files | 1 |
| [82](PVE-IDE-82.md) | Ecran Prepaid Income GEST | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T81[81 Liste services=temp...]
    style T81 fill:#58a6ff
    NONE[Aucun callee]
    T81 -.-> NONE
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
| Lignes de logique | 22 | Programme compact |
| Expressions | 12 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 22) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 1 ecran, 0 traitement)

- **Strategie** : 1 composant(s) UI (Razor/React) avec formulaires et validation.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 09:13*
