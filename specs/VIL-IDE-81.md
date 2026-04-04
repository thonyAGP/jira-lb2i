# VIL IDE 81 - Calcul concurrence sessions v1

> **Analyse**: Phases 1-4 2026-02-03 09:12 -> 09:12 (19s) | Assemblage 09:12
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | VIL |
| IDE Position | 81 |
| Nom Programme | Calcul concurrence sessions v1 |
| Fichier source | `Prg_81.xml` |
| Domaine metier | Caisse |
| Taches | 3 (0 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Calcul concurrence sessions v1** assure la gestion complete de ce processus, accessible depuis [Menu gestion caisse (IDE 86)](VIL-IDE-86.md), [Sortie de devises (IDE 161)](VIL-IDE-161.md), [Contrôle caisse avec (IDE 97)](VIL-IDE-97.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (3 taches) : traitements metier divers

**Donnees modifiees** : 1 tables en ecriture (concurrence_sessions).

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (3 taches)

Traitements internes.

---

#### <a id="t1"></a>81 - (sans nom)

**Role** : Traitement interne.

---

#### <a id="t2"></a>81.1 - Blocage reception

**Role** : Traitement : Blocage reception.
**Variables liees** : D (PO saisie reception en cours)

---

#### <a id="t3"></a>81.2 - Deblocage reception

**Role** : Traitement : Deblocage reception.
**Variables liees** : D (PO saisie reception en cours)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Menu gestion caisse (IDE 86)](VIL-IDE-86.md), [Sortie de devises (IDE 161)](VIL-IDE-161.md), [Contrôle caisse avec (IDE 97)](VIL-IDE-97.md)
- **Appelle**: 0 programmes | **Tables**: 1 (W:1 R:1 L:0) | **Taches**: 3 | **Expressions**: 12

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (3 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **81.1** | [**(sans nom)** (81)](#t1) | MDI | - | Traitement |
| 81.1.1 | [Blocage reception (81.1)](#t2) | MDI | - | |
| 81.1.2 | [Deblocage reception (81.2)](#t3) | MDI | - | |

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
| 227 | concurrence_sessions | Sessions de caisse | DB | R | **W** |   | 3 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 227 - concurrence_sessions (R/**W**) - 3 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | PI code calcul | W | Alpha |
| B | PI avec coffre 2 | W | Alpha |
| C | PI terminal coffre 2 | W | Numeric |
| D | PO saisie reception en cours | W | Alpha |
| E | SaisieRec sans coffre 2 | W | Logical |
| F | SaisieRec avec coffre 2 | W | Logical |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (4)

Variables recues du programme appelant ([Menu gestion caisse (IDE 86)](VIL-IDE-86.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | PI code calcul | Alpha | 2x parametre entrant |
| B | PI avec coffre 2 | Alpha | 2x parametre entrant |
| C | PI terminal coffre 2 | Numeric | 1x parametre entrant |
| D | PO saisie reception en cours | Alpha | - |

### 11.2 Autres (2)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| E | SaisieRec sans coffre 2 | Logical | 2x refs |
| F | SaisieRec avec coffre 2 | Logical | - |

## 12. EXPRESSIONS

**12 / 12 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONSTANTE | 3 | 0 |
| CONDITION | 4 | 0 |
| OTHER | 3 | 0 |
| NEGATION | 2 | 0 |

### 12.2 Expressions cles par type

#### CONSTANTE (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 8 | `'O'` | - |
| CONSTANTE | 6 | `'O'` | - |
| CONSTANTE | 5 | `'R'` | - |

#### CONDITION (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 3 | `PI avec coffre 2 [B]='O'` | - |
| CONDITION | 4 | `PI code calcul [A]='D'` | - |
| CONDITION | 1 | `PI code calcul [A]='C'` | - |
| CONDITION | 2 | `PI avec coffre 2 [B]<>'O'` | - |

#### OTHER (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 10 | `[H]` | - |
| OTHER | 9 | `SaisieRec sans coffre 2 [E]` | - |
| OTHER | 7 | `PI terminal coffre 2 [C]` | - |

#### NEGATION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| NEGATION | 12 | `NOT ([H])` | - |
| NEGATION | 11 | `NOT (SaisieRec sans coffre 2 [E])` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Menu gestion caisse (IDE 86)](VIL-IDE-86.md) -> **Calcul concurrence sessions v1 (IDE 81)**

Main -> ... -> [Sortie de devises (IDE 161)](VIL-IDE-161.md) -> **Calcul concurrence sessions v1 (IDE 81)**

Main -> ... -> [Contrôle caisse avec (IDE 97)](VIL-IDE-97.md) -> **Calcul concurrence sessions v1 (IDE 81)**

```mermaid
graph LR
    T81[81 Calcul concurrence ...]
    style T81 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC78[78 Lance correspittivi]
    style CC78 fill:#8b5cf6
    CC100[100 Menu pièces de caisse]
    style CC100 fill:#f59e0b
    CC148[148 CV Menu caisse vil...]
    style CC148 fill:#f59e0b
    CC86[86 Menu gestion caisse]
    style CC86 fill:#3fb950
    CC97[97 Contrôle caisse avec]
    style CC97 fill:#3fb950
    CC161[161 Sortie de devises]
    style CC161 fill:#3fb950
    CC148 --> CC86
    CC100 --> CC86
    CC148 --> CC97
    CC100 --> CC97
    CC148 --> CC161
    CC100 --> CC161
    CC1 --> CC148
    CC78 --> CC148
    CC1 --> CC100
    CC78 --> CC100
    CC86 --> T81
    CC97 --> T81
    CC161 --> T81
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [86](VIL-IDE-86.md) | Menu gestion caisse | 6 |
| [161](VIL-IDE-161.md) | Sortie de devises | 2 |
| [97](VIL-IDE-97.md) | Contrôle caisse avec | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T81[81 Calcul concurrence ...]
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
| Lignes de logique | 63 | Programme compact |
| Expressions | 12 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 63) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (3 taches: 0 ecran, 3 traitements)

- **Strategie** : 3 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| concurrence_sessions | Table WRITE (Database) | 2x | Schema + repository |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 09:12*
