# PBG IDE 101 - Verification Adherents

> **Analyse**: Phases 1-4 2026-02-03 09:22 -> 09:23 (20s) | Assemblage 09:23
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBG |
| IDE Position | 101 |
| Nom Programme | Verification Adherents |
| Fichier source | `Prg_101.xml` |
| Domaine metier | General |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Verification Adherents** assure la gestion complete de ce processus, accessible depuis [Affectation logement (IDE 98)](PBG-IDE-98.md), [Determination Affectation (IDE 104)](PBG-IDE-104.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Validation** (1 tache) : controles et verifications de coherence

**Logique metier** : 1 regles identifiees couvrant conditions metier.

## 3. BLOCS FONCTIONNELS

### 3.1 Validation (1 tache)

Controles de coherence : 1 tache verifie les donnees et conditions.

---

#### <a id="t1"></a>101 - Verification Occupation

**Role** : Verification : Verification Occupation.
**Variables liees** : D (P0-Occupation Std), E (P0-P/U Occupation), J (P0-Type Occupation), L (W0-Occupation), M (W0-Flag Occupation)


## 5. REGLES METIER

1 regles identifiees:

### Autres (1 regles)

#### <a id="rm-RM-001"></a>[RM-001] Condition toujours vraie (flag actif)

| Element | Detail |
|---------|--------|
| **Condition** | `W0-Flag Occupation [M]=6 AND W0-Flag Single [N]=6 AND W0-Flag Blocage [O]=6 AND W0-Flag Qualite [P]=6` |
| **Si vrai** | 'TRUE'LOG |
| **Si faux** | 'FALSE'LOG) |
| **Variables** | M (W0-Flag Occupation), N (W0-Flag Single), O (W0-Flag Blocage), P (W0-Flag Qualite) |
| **Expression source** | Expression 14 : `IF (W0-Flag Occupation [M]=6 AND W0-Flag Single [N]=6 AND W0` |
| **Exemple** | Si W0-Flag Occupation [M]=6 AND W0-Flag Single [N]=6 AND W0-Flag Blocage [O]=6 AND W0-Flag Qualite [P]=6 â†’ 'TRUE'LOG. Sinon â†’ 'FALSE'LOG) |

## 6. CONTEXTE

- **Appele par**: [Affectation logement (IDE 98)](PBG-IDE-98.md), [Determination Affectation (IDE 104)](PBG-IDE-104.md)
- **Appelle**: 0 programmes | **Tables**: 1 (W:0 R:1 L:0) | **Taches**: 1 | **Expressions**: 20

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **101.1** | [**Verification Occupation** (101)](#t1) | MDI | - | Validation |

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
| A | P0-Code Societe | R | Alpha |
| B | P0-Code Langue | R | Alpha |
| C | P0-Nom Logement | R | Alpha |
| D | P0-Occupation Std | R | Numeric |
| E | P0-P/U Occupation | R | Alpha |
| F | P0-Date Debut | R | Date |
| G | P0-Heure Debut | R | Alpha |
| H | P0-Date Fin | R | Date |
| I | P0-Heure Fin | R | Alpha |
| J | P0-Type Occupation | R | Alpha |
| K | P0-Autorisation | R | Logical |
| L | W0-Occupation | R | Numeric |
| M | W0-Flag Occupation | R | Numeric |
| N | W0-Flag Single | R | Numeric |
| O | W0-Flag Blocage | R | Numeric |
| P | W0-Flag Qualite | R | Numeric |
| Q | W0-Date/Heure Debut | R | Numeric |
| R | W0-Date/Heure Fin | R | Numeric |

</details>

## 11. VARIABLES

### 11.1 Autres (18)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P0-Code Societe | Alpha | 1x refs |
| B | P0-Code Langue | Alpha | - |
| C | P0-Nom Logement | Alpha | 1x refs |
| D | P0-Occupation Std | Numeric | 1x refs |
| E | P0-P/U Occupation | Alpha | [101](#t1) |
| F | P0-Date Debut | Date | 1x refs |
| G | P0-Heure Debut | Alpha | 1x refs |
| H | P0-Date Fin | Date | 1x refs |
| I | P0-Heure Fin | Alpha | 1x refs |
| J | P0-Type Occupation | Alpha | [101](#t1) |
| K | P0-Autorisation | Logical | - |
| L | W0-Occupation | Numeric | 3x refs |
| M | W0-Flag Occupation | Numeric | [101](#t1) |
| N | W0-Flag Single | Numeric | 4x refs |
| O | W0-Flag Blocage | Numeric | 5x refs |
| P | W0-Flag Qualite | Numeric | 2x refs |
| Q | W0-Date/Heure Debut | Numeric | 1x refs |
| R | W0-Date/Heure Fin | Numeric | 1x refs |

<details>
<summary>Toutes les 18 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| Autre | **A** | P0-Code Societe | Alpha |
| Autre | **B** | P0-Code Langue | Alpha |
| Autre | **C** | P0-Nom Logement | Alpha |
| Autre | **D** | P0-Occupation Std | Numeric |
| Autre | **E** | P0-P/U Occupation | Alpha |
| Autre | **F** | P0-Date Debut | Date |
| Autre | **G** | P0-Heure Debut | Alpha |
| Autre | **H** | P0-Date Fin | Date |
| Autre | **I** | P0-Heure Fin | Alpha |
| Autre | **J** | P0-Type Occupation | Alpha |
| Autre | **K** | P0-Autorisation | Logical |
| Autre | **L** | W0-Occupation | Numeric |
| Autre | **M** | W0-Flag Occupation | Numeric |
| Autre | **N** | W0-Flag Single | Numeric |
| Autre | **O** | W0-Flag Blocage | Numeric |
| Autre | **P** | W0-Flag Qualite | Numeric |
| Autre | **Q** | W0-Date/Heure Debut | Numeric |
| Autre | **R** | W0-Date/Heure Fin | Numeric |

</details>

## 12. EXPRESSIONS

**20 / 20 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCULATION | 3 | 0 |
| CALCUL | 1 | 0 |
| CAST_LOGIQUE | 2 | 5 |
| CONSTANTE | 3 | 0 |
| OTHER | 2 | 0 |
| CONDITION | 9 | 0 |

### 12.2 Expressions cles par type

#### CALCULATION (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 8 | `W0-Occupation [L]+1` | - |
| CALCULATION | 3 | `P0-Date Fin [H]*100+Val (P0-Heure Fin [I],'##')` | - |
| CALCULATION | 2 | `P0-Date Debut [F]*100+Val (P0-Heure Debut [G],'##')` | - |

#### CALCUL (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCUL | 7 | `[V]*100+Val ([W],'##')<W0-Date/Heure Fin [R] AND [X]*100+Val ([Y],'##')>W0-Date/Heure Debut [Q]` | - |

#### CAST_LOGIQUE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 14 | `IF (W0-Flag Occupation [M]=6 AND W0-Flag Single [N]=6 AND W0-Flag Blocage [O]=6 AND W0-Flag Qualite [P]=6,'TRUE'LOG,'FALSE'LOG)` | [RM-001](#rm-RM-001) |
| CAST_LOGIQUE | 1 | `'FALSE'LOG` | - |

#### CONSTANTE (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 16 | `0` | - |
| CONSTANTE | 15 | `6` | - |
| CONSTANTE | 5 | `'H'` | - |

#### OTHER (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 6 | `P0-Nom Logement [C]` | - |
| OTHER | 4 | `P0-Code Societe [A]` | - |

#### CONDITION (9 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 19 | `[Z]=ASCIIChr (15)` | - |
| CONDITION | 17 | `W0-Occupation [L]>=P0-Occupation Std [D]` | - |
| CONDITION | 18 | `Trim(MID(P0-P/U Occupation [E],2,2))='1' AND W0-Occupation [L]>0 OR Trim(MID([Z],2,2))='1'` | - |
| CONDITION | 20 | `P0-Type Occupation [J]<>[AA] AND [Z]<>ASCIIChr (15)` | - |
| CONDITION | 13 | `W0-Flag Blocage [O]=6 AND W0-Flag Single [N]=6 AND W0-Flag Occupation [M]=6 AND W0-Flag Qualite [P]<>6` | - |
| ... | | *+4 autres* | |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Affectation logement (IDE 98)](PBG-IDE-98.md) -> **Verification Adherents (IDE 101)**

Main -> ... -> [Determination Affectation (IDE 104)](PBG-IDE-104.md) -> **Verification Adherents (IDE 101)**

```mermaid
graph LR
    T101[101 Verification Adher...]
    style T101 fill:#58a6ff
    CC104[104 Determination Affe...]
    style CC104 fill:#8b5cf6
    CC98[98 Affectation logement]
    style CC98 fill:#8b5cf6
    CC98 --> T101
    CC104 --> T101
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [98](PBG-IDE-98.md) | Affectation logement | 2 |
| [104](PBG-IDE-104.md) | Determination Affectation | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T101[101 Verification Adher...]
    style T101 fill:#58a6ff
    NONE[Aucun callee]
    T101 -.-> NONE
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
| Lignes de logique | 58 | Programme compact |
| Expressions | 20 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 58) | Code sain |
| Regles metier | 1 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Validation (1 tache: 0 ecran, 1 traitement)

- **Strategie** : FluentValidation avec validators specifiques.
- Chaque tache de validation -> un validator injectable

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 09:23*
