# PVE IDE 59 - Report - Compute % _V3

> **Analyse**: Phases 1-4 2026-02-03 09:01 -> 09:02 (21s) | Assemblage 09:02
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PVE |
| IDE Position | 59 |
| Nom Programme | Report - Compute % _V3 |
| Fichier source | `Prg_59.xml` |
| Domaine metier | General |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Report - Compute % _V3** assure la gestion complete de ce processus, accessible depuis [Report - Revenue by Category (IDE 75)](PVE-IDE-75.md), [Report - Revenue by Place *NU* (IDE 421)](PVE-IDE-421.md), [Report - Revenue by Seller *NU (IDE 422)](PVE-IDE-422.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

**Donnees modifiees** : 1 tables en ecriture (Table_1461).

**Logique metier** : 1 regles identifiees couvrant conditions metier.

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>59 - Compute

**Role** : Traitement : Compute.


## 5. REGLES METIER

1 regles identifiees:

### Autres (1 regles)

#### <a id="rm-RM-001"></a>[RM-001] Traitement si P. D or C or P or L or V [C]='L',[H] est renseigne

| Element | Detail |
|---------|--------|
| **Condition** | `P. D or C or P or L or V [C]='L'` |
| **Si vrai** | [H]<>'' AND [H]<>'ZZZZZZ' |
| **Si faux** | IF(P. D or C or P or L or V [C]='C',[F]<>0 AND [F]<>99,IF(P. D or C or P or L or V [C]='D',[F]<>0 AND [F]<>766644,IF(P. D or C or P or L or V [C]='P',[F]<>0 AND [F]<>999999,IF(P. D or C or P or L or V [C]='V',[G]<>'' AND [G]<>'ZZZZZZZZ','TRUE'LOG))))) |
| **Variables** | C (P. D or C or P or L or V) |
| **Expression source** | Expression 8 : `IF(P. D or C or P or L or V [C]='L',[H]<>'' AND [H]<>'ZZZZZZ` |
| **Exemple** | Si P. D or C or P or L or V [C]='L' â†’ [H]<>'' AND [H]<>'ZZZZZZ' |

## 6. CONTEXTE

- **Appele par**: [Report - Revenue by Category (IDE 75)](PVE-IDE-75.md), [Report - Revenue by Place *NU* (IDE 421)](PVE-IDE-421.md), [Report - Revenue by Seller *NU (IDE 422)](PVE-IDE-422.md)
- **Appelle**: 0 programmes | **Tables**: 1 (W:1 R:0 L:0) | **Taches**: 1 | **Expressions**: 10

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **59.1** | [**Compute** (59)](#t1) | MDI | - | Traitement |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Traitement principal]
    DECISION{D or C or P or L or V}
    PROCESS[Traitement]
    UPDATE[MAJ 1 tables]
    ENDOK([END OK])
    ENDKO([END KO])

    START --> INIT --> SAISIE --> DECISION
    DECISION -->|OUI| PROCESS
    DECISION -->|NON| ENDKO
    PROCESS --> UPDATE --> ENDOK

    style START fill:#3fb950,color:#000
    style ENDOK fill:#3fb950,color:#000
    style ENDKO fill:#f85149,color:#fff
    style DECISION fill:#58a6ff,color:#000
```

> **Legende**: Vert = START/END OK | Rouge = END KO | Bleu = Decisions
> *Algorigramme auto-genere. Utiliser `/algorigramme` pour une synthese metier detaillee.*

<!-- TAB:Donnees -->

## 10. TABLES

### Tables utilisees (1)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 1461 | Table_1461 |  | MEM |   | **W** |   | 1 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 1461 - Table_1461 (**W**) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P. Total Revenue | W | Numeric |
| B | P. Total Cost | W | Numeric |
| C | P. D or C or P or L or V | W | Alpha |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (3)

Variables recues du programme appelant ([Report - Revenue by Category (IDE 75)](PVE-IDE-75.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P. Total Revenue | Numeric | 3x parametre entrant |
| B | P. Total Cost | Numeric | 2x parametre entrant |
| C | P. D or C or P or L or V | Alpha | 1x parametre entrant |

## 12. EXPRESSIONS

**10 / 10 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCUL | 4 | 0 |
| CALCULATION | 2 | 0 |
| CAST_LOGIQUE | 1 | 5 |
| OTHER | 3 | 0 |

### 12.2 Expressions cles par type

#### CALCUL (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCUL | 4 | `[L]*100/P. Total Cost [B]` | - |
| CALCUL | 7 | `[N]*100/(P. Total Revenue [A]-P. Total Cost [B])` | - |
| CALCUL | 2 | `[J]*100/P. Total Revenue [A]` | - |
| CALCUL | 3 | `[P]*100/P. Total Revenue [A]` | - |

#### CALCULATION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 6 | `[P]-[L]` | - |
| CALCULATION | 5 | `[J]-[L]` | - |

#### CAST_LOGIQUE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 8 | `IF(P. D or C or P or L or V [C]='L',[H]<>'' AND [H]<>'ZZZZZZ',IF(P. D or C or P or L or V [C]='C',[F]<>0 AND [F]<>99,IF(P. D or C or P or L or V [C]='D',[F]<>0 AND [F]<>766644,IF(P. D or C or P or L or V [C]='P',[F]<>0 AND [F]<>999999,IF(P. D or C or P or L or V [C]='V',[G]<>'' AND [G]<>'ZZZZZZZZ','TRUE'LOG)))))` | [RM-001](#rm-RM-001) |

#### OTHER (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 10 | `[Q]` | - |
| OTHER | 9 | `NOT([Q])` | - |
| OTHER | 1 | `GetParam ('SERVICE')` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Report - Revenue by Category (IDE 75)](PVE-IDE-75.md) -> **Report - Compute % _V3 (IDE 59)**

Main -> ... -> [Report - Revenue by Place *NU* (IDE 421)](PVE-IDE-421.md) -> **Report - Compute % _V3 (IDE 59)**

Main -> ... -> [Report - Revenue by Seller *NU (IDE 422)](PVE-IDE-422.md) -> **Report - Compute % _V3 (IDE 59)**

```mermaid
graph LR
    T59[59 Report - Compute % _V3]
    style T59 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC143[143 START]
    style CC143 fill:#f59e0b
    CC353[353 Menu==V4]
    style CC353 fill:#f59e0b
    CC420[420 Menu==V4___]
    style CC420 fill:#f59e0b
    CC439[439 Menu]
    style CC439 fill:#f59e0b
    CC185[185 Menu]
    style CC185 fill:#f59e0b
    CC182[182 Menu Reports]
    style CC182 fill:#f59e0b
    CC75[75 Report - Revenue by...]
    style CC75 fill:#3fb950
    CC421[421 Report - Revenue b...]
    style CC421 fill:#3fb950
    CC422[422 Report - Revenue b...]
    style CC422 fill:#3fb950
    CC182 --> CC75
    CC182 --> CC421
    CC182 --> CC422
    CC185 --> CC182
    CC353 --> CC182
    CC420 --> CC182
    CC439 --> CC182
    CC143 --> CC185
    CC143 --> CC353
    CC143 --> CC420
    CC143 --> CC439
    CC1 --> CC143
    CC75 --> T59
    CC421 --> T59
    CC422 --> T59
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [75](PVE-IDE-75.md) | Report - Revenue by Category | 1 |
| [421](PVE-IDE-421.md) | Report - Revenue by Place *NU* | 1 |
| [422](PVE-IDE-422.md) | Report - Revenue by Seller *NU | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T59[59 Report - Compute % _V3]
    style T59 fill:#58a6ff
    NONE[Aucun callee]
    T59 -.-> NONE
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
| Lignes de logique | 29 | Programme compact |
| Expressions | 10 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 29) | Code sain |
| Regles metier | 1 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 0 ecran, 1 traitement)

- **Strategie** : 1 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| Table_1461 | Table WRITE (Memory) | 1x | Schema + repository |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 09:02*
