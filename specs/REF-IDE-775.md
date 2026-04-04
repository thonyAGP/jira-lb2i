# REF IDE 775 - Determination Age Debut Sejour

> **Analyse**: Phases 1-4 2026-02-03 14:17 -> 14:18 (15s) | Assemblage 14:18
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | REF |
| IDE Position | 775 |
| Nom Programme | Determination Age Debut Sejour |
| Fichier source | `Prg_775.xml` |
| Dossier IDE | General |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Determination Age Debut Sejour** assure la gestion complete de ce processus, accessible depuis [Extraction biking (IDE 616)](REF-IDE-616.md), [Recalc age go (IDE 773)](REF-IDE-773.md), [Recalc age gm (IDE 774)](REF-IDE-774.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

**Logique metier** : 2 regles identifiees couvrant conditions metier.

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>775 - Determination Age

**Role** : Traitement : Determination Age.


## 5. REGLES METIER

2 regles identifiees:

### Autres (2 regles)

#### <a id="rm-RM-001"></a>[RM-001] Si P0-Date debut Sejour [B]='00/00/0000'DATE alors Date () sinon P0-Date debut Sejour [B])

| Element | Detail |
|---------|--------|
| **Condition** | `P0-Date debut Sejour [B]='00/00/0000'DATE` |
| **Si vrai** | Date () |
| **Si faux** | P0-Date debut Sejour [B]) |
| **Variables** | B (P0-Date debut Sejour) |
| **Expression source** | Expression 1 : `IF (P0-Date debut Sejour [B]='00/00/0000'DATE,Date (),P0-Dat` |
| **Exemple** | Si P0-Date debut Sejour [B]='00/00/0000'DATE â†’ Date (). Sinon â†’ P0-Date debut Sejour [B]) |

#### <a id="rm-RM-002"></a>[RM-002] Si Month (W0 Date debut sejour [E])<=Month (P0-Date de Naissance [A]) alors Month (W0 Date debut sejour [E])+12-Month (P0-Date de Naissance [A]) sinon Month (W0 Date debut sejour [E])-Month (P0-Date de Naissance [A]))

| Element | Detail |
|---------|--------|
| **Condition** | `Month (W0 Date debut sejour [E])<=Month (P0-Date de Naissance [A])` |
| **Si vrai** | Month (W0 Date debut sejour [E])+12-Month (P0-Date de Naissance [A]) |
| **Si faux** | Month (W0 Date debut sejour [E])-Month (P0-Date de Naissance [A])) |
| **Variables** | E (W0 Date debut sejour), A (P0-Date de Naissance) |
| **Expression source** | Expression 8 : `IF (Month (W0 Date debut sejour [E])<=Month (P0-Date de Nais` |
| **Exemple** | Si Month (W0 Date debut sejour [E])<=Month (P0-Date de Naissance [A]) â†’ Month (W0 Date debut sejour [E])+12-Month (P0-Date de Naissance [A]) |

## 6. CONTEXTE

- **Appele par**: [Extraction biking (IDE 616)](REF-IDE-616.md), [Recalc age go (IDE 773)](REF-IDE-773.md), [Recalc age gm (IDE 774)](REF-IDE-774.md)
- **Appelle**: 0 programmes | **Tables**: 0 (W:0 R:0 L:0) | **Taches**: 1 | **Expressions**: 17

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **775.1** | [**Determination Age** (775)](#t1) | MDI | - | Traitement |

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

### 11.1 Variables de travail (2)

Variables internes au programme.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| E | W0 Date debut sejour | Date | 5x calcul interne |
| F | W0 Nb de Mois | Numeric | 3x calcul interne |

### 11.2 Autres (5)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P0-Date de Naissance | Date | 8x refs |
| B | P0-Date debut Sejour | Date | 1x refs |
| C | P0-Age | Numeric | 3x refs |
| D | P0-Nb mois | Numeric | - |
| G | W0-Fin de Tache | Alpha | - |

## 12. EXPRESSIONS

**17 / 17 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCULATION | 3 | 0 |
| CONDITION | 10 | 2 |
| CONSTANTE | 3 | 0 |
| OTHER | 1 | 0 |

### 12.2 Expressions cles par type

#### CALCULATION (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 10 | `W0 Nb de Mois [F]-1` | - |
| CALCULATION | 5 | `P0-Age [C]-1` | - |
| CALCULATION | 3 | `Year (W0 Date debut sejour [E])-Year (P0-Date de Naissance [A])` | - |

#### CONDITION (10 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 1 | `IF (P0-Date debut Sejour [B]='00/00/0000'DATE,Date (),P0-Date debut Sejour [B])` | [RM-001](#rm-RM-001) |
| CONDITION | 8 | `IF (Month (W0 Date debut sejour [E])<=Month (P0-Date de Naissance [A]),Month (W0 Date debut sejour [E])+12-Month (P0-Date de Naissance [A]),Month (W0 Date debut sejour [E])-Month (P0-Date de Naissance [A]))` | [RM-002](#rm-RM-002) |
| CONDITION | 9 | `Day (W0 Date debut sejour [E])<Day (P0-Date de Naissance [A])` | - |
| CONDITION | 7 | `P0-Age [C]=0` | - |
| CONDITION | 13 | `P0-Date de Naissance [A]<=0` | - |
| ... | | *+5 autres* | |

#### CONSTANTE (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 16 | `40` | - |
| CONSTANTE | 14 | `0` | - |
| CONSTANTE | 12 | `1` | - |

#### OTHER (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 17 | `W0 Nb de Mois [F]` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Extraction biking (IDE 616)](REF-IDE-616.md) -> **Determination Age Debut Sejour (IDE 775)**

Main -> ... -> [Recalc age go (IDE 773)](REF-IDE-773.md) -> **Determination Age Debut Sejour (IDE 775)**

Main -> ... -> [Recalc age gm (IDE 774)](REF-IDE-774.md) -> **Determination Age Debut Sejour (IDE 775)**

```mermaid
graph LR
    T775[775 Determination Age ...]
    style T775 fill:#58a6ff
    CC774[774 Recalc age gm]
    style CC774 fill:#8b5cf6
    CC773[773 Recalc age go]
    style CC773 fill:#8b5cf6
    CC616[616 Extraction biking]
    style CC616 fill:#8b5cf6
    CC616 --> T775
    CC773 --> T775
    CC774 --> T775
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [616](REF-IDE-616.md) | Extraction biking | 1 |
| [773](REF-IDE-773.md) | Recalc age go | 1 |
| [774](REF-IDE-774.md) | Recalc age gm | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T775[775 Determination Age ...]
    style T775 fill:#58a6ff
    NONE[Aucun callee]
    T775 -.-> NONE
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
| Lignes de logique | 35 | Programme compact |
| Expressions | 17 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 35) | Code sain |
| Regles metier | 2 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 0 ecran, 1 traitement)

- **Strategie** : 1 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 14:18*
