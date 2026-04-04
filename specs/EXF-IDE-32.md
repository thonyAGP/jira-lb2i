# EXF IDE 32 - Recuperation du titre Manager

> **Analyse**: Phases 1-4 2026-02-03 11:04 -> 11:04 (18s) | Assemblage 11:04
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | EXF |
| IDE Position | 32 |
| Nom Programme | Recuperation du titre Manager |
| Fichier source | `Prg_32.xml` |
| Dossier IDE | Utilitaires |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Recuperation du titre Manager** assure la gestion complete de ce processus, accessible depuis [  Participants general (IDE 37)](EXF-IDE-37.md), [  Participants date (IDE 38)](EXF-IDE-38.md), [Zoom Adherents VSP (IDE 41)](EXF-IDE-41.md), [Zoom Adherents Paiement (IDE 42)](EXF-IDE-42.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>32 - Recuperation du titre

**Role** : Consultation/chargement : Recuperation du titre.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [  Participants general (IDE 37)](EXF-IDE-37.md), [  Participants date (IDE 38)](EXF-IDE-38.md), [Zoom Adherents VSP (IDE 41)](EXF-IDE-41.md), [Zoom Adherents Paiement (IDE 42)](EXF-IDE-42.md)
- **Appelle**: 0 programmes | **Tables**: 1 (W:0 R:1 L:0) | **Taches**: 1 | **Expressions**: 4

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **32.1** | [**Recuperation du titre** (32)](#t1) | MDI | - | Traitement |

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
| 721 | arc_bl_detail |  | DB | R |   |   | 1 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 721 - arc_bl_detail (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | > code ecran | R | Numeric |
| B | < nom ecran | R | Alpha |
| C | code langue | R | Alpha |

</details>

## 11. VARIABLES

### 11.1 Autres (3)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | > code ecran | Numeric | 1x refs |
| B | < nom ecran | Alpha | - |
| C | code langue | Alpha | - |

## 12. EXPRESSIONS

**4 / 4 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONCATENATION | 1 | 0 |
| CONSTANTE | 1 | 0 |
| CONDITION | 1 | 0 |
| OTHER | 1 | 0 |

### 12.2 Expressions cles par type

#### CONCATENATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 3 | `Trim ([G])&' - '&Trim ([H])` | - |

#### CONSTANTE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 2 | `'EM'` | - |

#### CONDITION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 1 | `> code ecran [A]` | - |

#### OTHER (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 4 | `GetParam ('CODELANGUE')` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [  Participants general (IDE 37)](EXF-IDE-37.md) -> **Recuperation du titre Manager (IDE 32)**

Main -> ... -> [  Participants date (IDE 38)](EXF-IDE-38.md) -> **Recuperation du titre Manager (IDE 32)**

Main -> ... -> [Zoom Adherents VSP (IDE 41)](EXF-IDE-41.md) -> **Recuperation du titre Manager (IDE 32)**

Main -> ... -> [Zoom Adherents Paiement (IDE 42)](EXF-IDE-42.md) -> **Recuperation du titre Manager (IDE 32)**

```mermaid
graph LR
    T32[32 Recuperation du tit...]
    style T32 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC13[13 Menu ventes]
    style CC13 fill:#f59e0b
    CC35[35 Ventes Excursions]
    style CC35 fill:#f59e0b
    CC37[37 Participants general]
    style CC37 fill:#3fb950
    CC38[38 Participants date]
    style CC38 fill:#3fb950
    CC41[41 Zoom Adherents VSP]
    style CC41 fill:#3fb950
    CC42[42 Zoom Adherents Paie...]
    style CC42 fill:#3fb950
    CC35 --> CC37
    CC35 --> CC38
    CC35 --> CC41
    CC35 --> CC42
    CC13 --> CC35
    CC1 --> CC13
    CC37 --> T32
    CC38 --> T32
    CC41 --> T32
    CC42 --> T32
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [37](EXF-IDE-37.md) |   Participants general | 1 |
| [38](EXF-IDE-38.md) |   Participants date | 1 |
| [41](EXF-IDE-41.md) | Zoom Adherents VSP | 1 |
| [42](EXF-IDE-42.md) | Zoom Adherents Paiement | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T32[32 Recuperation du tit...]
    style T32 fill:#58a6ff
    NONE[Aucun callee]
    T32 -.-> NONE
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
| Lignes de logique | 13 | Programme compact |
| Expressions | 4 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 13) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 0 ecran, 1 traitement)

- **Strategie** : 1 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 11:04*
