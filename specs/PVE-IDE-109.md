# PVE IDE 109 - Read Frame

> **Analyse**: Phases 1-4 2026-02-03 09:26 -> 09:27 (20s) | Assemblage 09:27
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PVE |
| IDE Position | 109 |
| Nom Programme | Read Frame |
| Fichier source | `Prg_109.xml` |
| Domaine metier | General |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Read Frame** assure la gestion complete de ce processus, accessible depuis [Label Management (IDE 105)](PVE-IDE-105.md), [Sticker List (IDE 112)](PVE-IDE-112.md), [Print label code barre DIN (IDE 113)](PVE-IDE-113.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>109 - Read Frame

**Role** : Traitement : Read Frame.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Label Management (IDE 105)](PVE-IDE-105.md), [Sticker List (IDE 112)](PVE-IDE-112.md), [Print label code barre DIN (IDE 113)](PVE-IDE-113.md)
- **Appelle**: 0 programmes | **Tables**: 1 (W:0 R:1 L:0) | **Taches**: 1 | **Expressions**: 5

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **109.1** | [**Read Frame** (109)](#t1) | MDI | - | Traitement |

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
| 390 | pv_inventory |  | DB | R |   |   | 1 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 390 - pv_inventory (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | Param X | R | Numeric |
| B | Param Y | R | Numeric |

</details>

## 11. VARIABLES

### 11.1 Autres (2)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | Param X | Numeric | - |
| B | Param Y | Numeric | - |

## 12. EXPRESSIONS

**5 / 5 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONSTANTE | 1 | 0 |
| OTHER | 4 | 0 |

### 12.2 Expressions cles par type

#### CONSTANTE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 1 | `'SKILABEL'` | - |

#### OTHER (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 4 | `[D]` | - |
| OTHER | 5 | `[E]` | - |
| OTHER | 2 | `SetParam ('FRAMEX',[D])` | - |
| OTHER | 3 | `SetParam ('FRAMEY',[E])` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Label Management (IDE 105)](PVE-IDE-105.md) -> **Read Frame (IDE 109)**

Main -> ... -> [Sticker List (IDE 112)](PVE-IDE-112.md) -> **Read Frame (IDE 109)**

Main -> ... -> [Print label code barre DIN (IDE 113)](PVE-IDE-113.md) -> **Read Frame (IDE 109)**

```mermaid
graph LR
    T109[109 Read Frame]
    style T109 fill:#58a6ff
    CC353[353 Menu==V4]
    style CC353 fill:#8b5cf6
    CC185[185 Menu]
    style CC185 fill:#8b5cf6
    CC439[439 Menu]
    style CC439 fill:#8b5cf6
    CC420[420 Menu==V4___]
    style CC420 fill:#8b5cf6
    CC209[209 Print Invoice or T...]
    style CC209 fill:#f59e0b
    CC411[411 Menu Equipment inv...]
    style CC411 fill:#f59e0b
    CC179[179 Menu Stocks Manage...]
    style CC179 fill:#f59e0b
    CC184[184 Menu Equipment inv...]
    style CC184 fill:#f59e0b
    CC105[105 Label Management]
    style CC105 fill:#3fb950
    CC112[112 Sticker List]
    style CC112 fill:#3fb950
    CC113[113 Print label code b...]
    style CC113 fill:#3fb950
    CC179 --> CC105
    CC184 --> CC105
    CC411 --> CC105
    CC209 --> CC105
    CC179 --> CC112
    CC184 --> CC112
    CC411 --> CC112
    CC209 --> CC112
    CC179 --> CC113
    CC184 --> CC113
    CC411 --> CC113
    CC209 --> CC113
    CC185 --> CC179
    CC353 --> CC179
    CC420 --> CC179
    CC439 --> CC179
    CC185 --> CC184
    CC353 --> CC184
    CC420 --> CC184
    CC439 --> CC184
    CC185 --> CC411
    CC353 --> CC411
    CC420 --> CC411
    CC439 --> CC411
    CC185 --> CC209
    CC353 --> CC209
    CC420 --> CC209
    CC439 --> CC209
    CC105 --> T109
    CC112 --> T109
    CC113 --> T109
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [105](PVE-IDE-105.md) | Label Management | 1 |
| [112](PVE-IDE-112.md) | Sticker List | 1 |
| [113](PVE-IDE-113.md) | Print label code barre DIN | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T109[109 Read Frame]
    style T109 fill:#58a6ff
    NONE[Aucun callee]
    T109 -.-> NONE
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
| Expressions | 5 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 14) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 0 ecran, 1 traitement)

- **Strategie** : 1 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 09:27*
