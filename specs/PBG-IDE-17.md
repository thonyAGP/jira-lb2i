# PBG IDE 17 - Rech si ch occup pour manuelle

> **Analyse**: Phases 1-4 2026-02-03 01:04 -> 01:05 (39s) | Assemblage 01:05
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBG |
| IDE Position | 17 |
| Nom Programme | Rech si ch occup pour manuelle |
| Fichier source | `Prg_17.xml` |
| Domaine metier | General |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Rech si ch occup pour manuelle** assure la gestion complete de ce processus, accessible depuis [Vérif affect Ch comm libre (IDE 175)](PBG-IDE-175.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t3"></a>17 - test dispo

**Role** : Verification : test dispo.
**Variables liees** : J (P.Dispo ?)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Vérif affect Ch comm libre (IDE 175)](PBG-IDE-175.md)
- **Appelle**: 0 programmes | **Tables**: 1 (W:0 R:1 L:0) | **Taches**: 1 | **Expressions**: 16

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **17.1** | [**test dispo** (17)](#t3) | - | - | Traitement |

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
| 34 | hebergement______heb | Hebergement (chambres) | DB | R |   |   | 1 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 34 - hebergement______heb (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P.Pas de gestion horaire ? | R | Logical |
| B | P.Logement | R | Alpha |
| C | P.Societe | R | Alpha |
| D | P.Date debut | R | Date |
| E | P.Heure debut | R | Alpha |
| F | P.Date fin | R | Date |
| G | P.Heure fin | R | Alpha |
| H | P.Occupation std | R | Numeric |
| I | P.Nb enf en bas age | R | Numeric |
| J | P.Dispo ? | R | Logical |
| K | V.Date/heure debut | R | Numeric |
| L | V.Date/heure fin | R | Numeric |
| M | V.Nb place prises | R | Numeric |
| N | V.Occupation | R | Numeric |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (10)

Variables recues du programme appelant ([Vérif affect Ch comm libre (IDE 175)](PBG-IDE-175.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P.Pas de gestion horaire ? | Logical | - |
| B | P.Logement | Alpha | - |
| C | P.Societe | Alpha | - |
| D | P.Date debut | Date | - |
| E | P.Heure debut | Alpha | - |
| F | P.Date fin | Date | - |
| G | P.Heure fin | Alpha | - |
| H | P.Occupation std | Numeric | - |
| I | P.Nb enf en bas age | Numeric | 1x parametre entrant |
| J | P.Dispo ? | Logical | - |

### 11.2 Variables de session (4)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| K | V.Date/heure debut | Numeric | - |
| L | V.Date/heure fin | Numeric | - |
| M | V.Nb place prises | Numeric | 1x session |
| N | V.Occupation | Numeric | 1x session |

## 12. EXPRESSIONS

**16 / 16 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCULATION | 1 | 0 |
| CONDITION | 5 | 0 |
| CONSTANTE | 1 | 0 |
| OTHER | 5 | 0 |
| CAST_LOGIQUE | 2 | 0 |
| NEGATION | 1 | 0 |
| STRING | 1 | 0 |

### 12.2 Expressions cles par type

#### CALCULATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 9 | `[X]+1` | - |

#### CONDITION (5 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 10 | `P.Nb enf en bas age [I]>0` | - |
| CONDITION | 15 | `VG38 AND VG40<>'' AND [AB]<>0` | - |
| CONDITION | 8 | `Counter(0)=0` | - |
| CONDITION | 11 | `[AA]-[X]>0` | - |
| CONDITION | 14 | `([AA]+[AB])-[X]>0` | - |

#### CONSTANTE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 2 | `'H'` | - |

#### OTHER (5 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 7 | `[O]` | - |
| OTHER | 12 | `V.Nb place prises [M]` | - |
| OTHER | 6 | `[Q]` | - |
| OTHER | 1 | `[S]` | - |
| OTHER | 5 | `V.Occupation [N]` | - |

#### CAST_LOGIQUE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 4 | `'FALSE'LOG` | - |
| CAST_LOGIQUE | 3 | `'TRUE'LOG` | - |

#### NEGATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| NEGATION | 16 | `NOT ExpCalc('47'EXP)` | - |

#### STRING (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| STRING | 13 | `Val(MID([T],2,2),'2')` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Vérif affect Ch comm libre (IDE 175)](PBG-IDE-175.md) -> **Rech si ch occup pour manuelle (IDE 17)**

```mermaid
graph LR
    T17[17 Rech si ch occup po...]
    style T17 fill:#58a6ff
    CC119[119 Recherche Logement]
    style CC119 fill:#8b5cf6
    CC117[117 Affiche rech logement]
    style CC117 fill:#f59e0b
    CC169[169 Affectation libera...]
    style CC169 fill:#f59e0b
    CC174[174 Logement Client pm...]
    style CC174 fill:#f59e0b
    CC21[21 Affec manuelle chambre]
    style CC21 fill:#f59e0b
    CC173[173 Logement Client]
    style CC173 fill:#f59e0b
    CC175[175 Vérif affect Ch co...]
    style CC175 fill:#3fb950
    CC21 --> CC175
    CC173 --> CC175
    CC174 --> CC175
    CC169 --> CC21
    CC169 --> CC173
    CC169 --> CC174
    CC117 --> CC169
    CC119 --> CC117
    CC175 --> T17
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [175](PBG-IDE-175.md) | Vérif affect Ch comm libre | 2 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T17[17 Rech si ch occup po...]
    style T17 fill:#58a6ff
    NONE[Aucun callee]
    T17 -.-> NONE
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
| Lignes de logique | 38 | Programme compact |
| Expressions | 16 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 38) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 0 ecran, 1 traitement)

- **Strategie** : 1 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 01:05*
