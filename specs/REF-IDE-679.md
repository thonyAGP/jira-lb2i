# REF IDE 679 - Calcul des dépenses

> **Analyse**: Phases 1-4 2026-02-03 13:36 -> 13:37 (16s) | Assemblage 13:37
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | REF |
| IDE Position | 679 |
| Nom Programme | Calcul des dépenses |
| Fichier source | `Prg_679.xml` |
| Dossier IDE | General |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Calcul des dépenses** assure la gestion complete de ce processus, accessible depuis [Consultation Gift Pass (IDE 678)](REF-IDE-678.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Calcul** (1 tache) : calculs de montants, stocks ou compteurs

**Logique metier** : 1 regles identifiees couvrant valeurs par defaut.

## 3. BLOCS FONCTIONNELS

### 3.1 Calcul (1 tache)

Calculs metier : montants, stocks, compteurs.

---

#### <a id="t1"></a>679 - Calcul des dépenses

**Role** : Calcul : Calcul des dépenses.


## 5. REGLES METIER

1 regles identifiees:

### Autres (1 regles)

#### <a id="rm-RM-001"></a>[RM-001] Valeur par defaut si Trim(p.Service [B]) est vide

| Element | Detail |
|---------|--------|
| **Condition** | `Trim(p.Service [B])=''` |
| **Si vrai** | '' |
| **Si faux** | 'AND cte_service='''&Trim(p.Service [B])&'''') |
| **Variables** | B (p.Service) |
| **Expression source** | Expression 1 : `IF(Trim(p.Service [B])='','','AND cte_service='''&Trim(p.Ser` |
| **Exemple** | Si Trim(p.Service [B])='' â†’ ''. Sinon â†’ 'AND cte_service='''&Trim(p.Service [B])&'''') |

## 6. CONTEXTE

- **Appele par**: [Consultation Gift Pass (IDE 678)](REF-IDE-678.md)
- **Appelle**: 0 programmes | **Tables**: 0 (W:0 R:0 L:0) | **Taches**: 1 | **Expressions**: 3

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **679.1** | [**Calcul des dépenses** (679)](#t1) | - | - | Calcul |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Traitement principal]
    DECISION{p.Service}
    PROCESS[Traitement]
    ENDOK([END OK])
    ENDKO([END KO])

    START --> INIT --> SAISIE --> DECISION
    DECISION -->|OUI| PROCESS
    DECISION -->|NON| ENDKO
    PROCESS --> ENDOK

    style START fill:#3fb950,color:#000
    style ENDOK fill:#3fb950,color:#000
    style ENDKO fill:#f85149,color:#fff
    style DECISION fill:#58a6ff,color:#000
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

Variables recues du programme appelant ([Consultation Gift Pass (IDE 678)](REF-IDE-678.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | p.Compte | Numeric | - |
| B | p.Service | Unicode | 2x parametre entrant |
| C | p.Depenses | Numeric | - |

### 11.2 Autres (1)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| D | Depenses | Numeric | 1x refs |

## 12. EXPRESSIONS

**3 / 3 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCULATION | 1 | 0 |
| CONDITION | 2 | 5 |

### 12.2 Expressions cles par type

#### CALCULATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 3 | `Depenses [D]*(-1)` | - |

#### CONDITION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 1 | `IF(Trim(p.Service [B])='','','AND cte_service='''&Trim(p.Service [B])&'''')` | [RM-001](#rm-RM-001) |
| CONDITION | 2 | `IF(Trim(p.Service [B])='','','AND ven_service='''&Trim(p.Service [B])&'''')` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Consultation Gift Pass (IDE 678)](REF-IDE-678.md) -> **Calcul des dépenses (IDE 679)**

```mermaid
graph LR
    T679[679 Calcul des dépenses]
    style T679 fill:#58a6ff
    CC678[678 Consultation Gift ...]
    style CC678 fill:#8b5cf6
    CC678 --> T679
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [678](REF-IDE-678.md) | Consultation Gift Pass | 2 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T679[679 Calcul des dépenses]
    style T679 fill:#58a6ff
    NONE[Aucun callee]
    T679 -.-> NONE
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
| Lignes de logique | 6 | Programme compact |
| Expressions | 3 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 6) | Code sain |
| Regles metier | 1 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Calcul (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Services de calcul purs (Domain Services).
- Migrer la logique de calcul (stock, compteurs, montants)

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 13:37*
