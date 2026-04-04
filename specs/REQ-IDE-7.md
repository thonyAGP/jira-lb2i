# REQ IDE 7 - combo problem

> **Analyse**: Phases 1-4 2026-02-03 20:23 -> 20:24 (14s) | Assemblage 20:24
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | REQ |
| IDE Position | 7 |
| Nom Programme | combo problem |
| Fichier source | `Prg_7.xml` |
| Dossier IDE | Combos |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**combo problem** assure la gestion complete de ce processus, accessible depuis [  Load combos (IDE 31)](REQ-IDE-31.md), [MAJ Pb (IDE 32)](REQ-IDE-32.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Consultation** (1 tache) : ecrans de recherche, selection et consultation

## 3. BLOCS FONCTIONNELS

### 3.1 Consultation (1 tache)

Ecrans de recherche et consultation.

---

#### <a id="t1"></a>7 - Zoom service [[ECRAN]](#ecran-t1)

**Role** : Selection par l'operateur : Zoom service.
**Ecran** : 261 x 32 DLU (MDI) | [Voir mockup](#ecran-t1)
**Variables liees** : A (p.list services dispatched), B (p.list services complete)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [  Load combos (IDE 31)](REQ-IDE-31.md), [MAJ Pb (IDE 32)](REQ-IDE-32.md)
- **Appelle**: 0 programmes | **Tables**: 1 (W:0 R:1 L:0) | **Taches**: 1 | **Expressions**: 8

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **7.1** | [**Zoom service** (7)](#t1) [mockup](#ecran-t1) | MDI | 261x32 | Consultation |

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
| 430 | req_services | Services / filieres | DB | R |   |   | 1 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 430 - req_services (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | p.list services dispatched | R | Alpha |
| B | p.list services complete | R | Alpha |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (2)

Variables recues du programme appelant ([  Load combos (IDE 31)](REQ-IDE-31.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | p.list services dispatched | Alpha | - |
| B | p.list services complete | Alpha | 3x parametre entrant |

## 12. EXPRESSIONS

**8 / 8 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCULATION | 2 | 0 |
| CONSTANTE | 1 | 0 |
| CONCATENATION | 2 | 0 |
| STRING | 3 | 0 |

### 12.2 Expressions cles par type

#### CALCULATION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 5 | `Left (Trim (p.list services complete [B]),Len (Trim (p.list services complete [B]))-1)` | - |
| CALCULATION | 4 | `Left (Trim (p.list services dispat... [A]),Len (Trim (p.list services dispat... [A]))-1)` | - |

#### CONSTANTE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 1 | `''` | - |

#### CONCATENATION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 3 | `Trim (p.list services complete [B])&Trim ([D])&' : '&Trim ([E])&','` | - |
| CONCATENATION | 2 | `Trim (p.list services dispat... [A])&Trim ([D])&' : '&Trim ([E])&','` | - |

#### STRING (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| STRING | 8 | `SetParam ('TYPEPB',Trim (p.list services complete [B]))` | - |
| STRING | 7 | `SetParam (Trim ([C])&'TYPEPB',Trim (p.list services dispat... [A]))` | - |
| STRING | 6 | `Trim (p.list services dispat... [A])` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [  Load combos (IDE 31)](REQ-IDE-31.md) -> **combo problem (IDE 7)**

Main -> ... -> [MAJ Pb (IDE 32)](REQ-IDE-32.md) -> **combo problem (IDE 7)**

```mermaid
graph LR
    T7[7 combo problem]
    style T7 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC52[52 MAIN MENU]
    style CC52 fill:#f59e0b
    CC21[21 Menu requests]
    style CC21 fill:#f59e0b
    CC40[40 MAJ parameters]
    style CC40 fill:#f59e0b
    CC22[22 Menu Administration]
    style CC22 fill:#f59e0b
    CC29[29 Init REQ]
    style CC29 fill:#f59e0b
    CC41[41 MAJ Group profiles]
    style CC41 fill:#f59e0b
    CC31[31 Load combos]
    style CC31 fill:#3fb950
    CC32[32 MAJ Pb]
    style CC32 fill:#3fb950
    CC29 --> CC31
    CC41 --> CC31
    CC22 --> CC31
    CC29 --> CC32
    CC41 --> CC32
    CC22 --> CC32
    CC21 --> CC29
    CC40 --> CC29
    CC21 --> CC41
    CC40 --> CC41
    CC21 --> CC22
    CC40 --> CC22
    CC52 --> CC21
    CC52 --> CC40
    CC1 --> CC52
    CC31 --> T7
    CC32 --> T7
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [31](REQ-IDE-31.md) |   Load combos | 1 |
| [32](REQ-IDE-32.md) | MAJ Pb | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T7[7 combo problem]
    style T7 fill:#58a6ff
    NONE[Aucun callee]
    T7 -.-> NONE
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
| Lignes de logique | 14 | Programme compact |
| Expressions | 8 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 14) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Consultation (1 tache: 1 ecran, 0 traitement)

- **Strategie** : Composants de recherche/selection en modales.
- 1 ecran : Zoom service

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 20:24*
