# REQ IDE 8 - combo intervenant

> **Analyse**: Phases 1-4 2026-02-03 20:24 -> 20:24 (14s) | Assemblage 20:24
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | REQ |
| IDE Position | 8 |
| Nom Programme | combo intervenant |
| Fichier source | `Prg_8.xml` |
| Dossier IDE | Combos |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**combo intervenant** assure la gestion complete de ce processus, accessible depuis [  Load combos (IDE 31)](REQ-IDE-31.md), [MAJ assignee (IDE 33)](REQ-IDE-33.md), [MAJ locations (IDE 35)](REQ-IDE-35.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Consultation** (1 tache) : ecrans de recherche, selection et consultation

## 3. BLOCS FONCTIONNELS

### 3.1 Consultation (1 tache)

Ecrans de recherche et consultation.

---

#### <a id="t1"></a>8 - Zoom service [[ECRAN]](#ecran-t1)

**Role** : Selection par l'operateur : Zoom service.
**Ecran** : 272 x 62 DLU (MDI) | [Voir mockup](#ecran-t1)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [  Load combos (IDE 31)](REQ-IDE-31.md), [MAJ assignee (IDE 33)](REQ-IDE-33.md), [MAJ locations (IDE 35)](REQ-IDE-35.md)
- **Appelle**: 0 programmes | **Tables**: 1 (W:0 R:1 L:0) | **Taches**: 1 | **Expressions**: 5

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **8.1** | [**Zoom service** (8)](#t1) [mockup](#ecran-t1) | MDI | 272x62 | Consultation |

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
| 438 | resto_param |  | DB | R |   |   | 1 |

### Colonnes par table (0 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 438 - resto_param (R) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

*(Programme sans variables locales mappees)*

## 12. EXPRESSIONS

**5 / 5 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCULATION | 1 | 0 |
| CONSTANTE | 1 | 0 |
| CONCATENATION | 1 | 0 |
| STRING | 2 | 0 |

### 12.2 Expressions cles par type

#### CALCULATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 3 | `Left (Trim (p.list by dispatch [A]),Len (Trim (p.list by dispatch [A]))-1)` | - |

#### CONSTANTE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 1 | `''` | - |

#### CONCATENATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 2 | `Trim (p.list by dispatch [A])&Trim ([C])&' : '&Trim ([D])&','` | - |

#### STRING (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| STRING | 5 | `SetParam (Trim ([B])&'TYPETECH',Trim (p.list by dispatch [A]))` | - |
| STRING | 4 | `Trim (p.list by dispatch [A])` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [  Load combos (IDE 31)](REQ-IDE-31.md) -> **combo intervenant (IDE 8)**

Main -> ... -> [MAJ assignee (IDE 33)](REQ-IDE-33.md) -> **combo intervenant (IDE 8)**

Main -> ... -> [MAJ locations (IDE 35)](REQ-IDE-35.md) -> **combo intervenant (IDE 8)**

```mermaid
graph LR
    T8[8 combo intervenant]
    style T8 fill:#58a6ff
    CC52[52 MAIN MENU]
    style CC52 fill:#8b5cf6
    CC21[21 Menu requests]
    style CC21 fill:#f59e0b
    CC40[40 MAJ parameters]
    style CC40 fill:#f59e0b
    CC22[22 Menu Administration]
    style CC22 fill:#f59e0b
    CC36[36 MAJ request type]
    style CC36 fill:#f59e0b
    CC29[29 Init REQ]
    style CC29 fill:#f59e0b
    CC41[41 MAJ Group profiles]
    style CC41 fill:#f59e0b
    CC31[31 Load combos]
    style CC31 fill:#3fb950
    CC33[33 MAJ assignee]
    style CC33 fill:#3fb950
    CC35[35 MAJ locations]
    style CC35 fill:#3fb950
    CC29 --> CC31
    CC41 --> CC31
    CC22 --> CC31
    CC36 --> CC31
    CC29 --> CC33
    CC41 --> CC33
    CC22 --> CC33
    CC36 --> CC33
    CC29 --> CC35
    CC41 --> CC35
    CC22 --> CC35
    CC36 --> CC35
    CC21 --> CC29
    CC40 --> CC29
    CC21 --> CC41
    CC40 --> CC41
    CC21 --> CC22
    CC40 --> CC22
    CC21 --> CC36
    CC40 --> CC36
    CC52 --> CC21
    CC52 --> CC40
    CC31 --> T8
    CC33 --> T8
    CC35 --> T8
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [31](REQ-IDE-31.md) |   Load combos | 1 |
| [33](REQ-IDE-33.md) | MAJ assignee | 1 |
| [35](REQ-IDE-35.md) | MAJ locations | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T8[8 combo intervenant]
    style T8 fill:#58a6ff
    NONE[Aucun callee]
    T8 -.-> NONE
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
| Expressions | 5 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 10) | Code sain |
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
