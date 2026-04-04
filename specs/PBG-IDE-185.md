# PBG IDE 185 - Verification Adherents

> **Analyse**: Phases 1-4 2026-02-03 10:02 -> 10:02 (21s) | Assemblage 10:02
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBG |
| IDE Position | 185 |
| Nom Programme | Verification Adherents |
| Fichier source | `Prg_185.xml` |
| Domaine metier | General |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Verification Adherents** assure la gestion complete de ce processus, accessible depuis [Logement Client (IDE 0)](PBG-IDE-0.md), [Logement Exterieur (IDE 0)](PBG-IDE-0.md), [Logement Personnel (IDE 0)](PBG-IDE-0.md), [Logement Exterieur (IDE 171)](PBG-IDE-171.md), [Logement Personnel (IDE 172)](PBG-IDE-172.md), [Logement Client (IDE 173)](PBG-IDE-173.md), [Logement Client pms-626 (IDE 174)](PBG-IDE-174.md), [Logement Client (IDE 385)](PBG-IDE-385.md), [Affec manuelle chambre (IDE 21)](PBG-IDE-21.md), [Determination Affectation (IDE 184)](PBG-IDE-184.md), [Chambres GM disponibles (IDE 291)](PBG-IDE-291.md), [Chambres GO disponibles (IDE 292)](PBG-IDE-292.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Validation** (1 tache) : controles et verifications de coherence

**Logique metier** : 1 regles identifiees couvrant conditions metier.

## 3. BLOCS FONCTIONNELS

### 3.1 Validation (1 tache)

Controles de coherence : 1 tache verifie les donnees et conditions.

---

#### <a id="t1"></a>185 - Verification Occupation

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

- **Appele par**: [Logement Client (IDE 0)](PBG-IDE-0.md), [Logement Exterieur (IDE 0)](PBG-IDE-0.md), [Logement Personnel (IDE 0)](PBG-IDE-0.md), [Logement Exterieur (IDE 171)](PBG-IDE-171.md), [Logement Personnel (IDE 172)](PBG-IDE-172.md), [Logement Client (IDE 173)](PBG-IDE-173.md), [Logement Client pms-626 (IDE 174)](PBG-IDE-174.md), [Logement Client (IDE 385)](PBG-IDE-385.md), [Affec manuelle chambre (IDE 21)](PBG-IDE-21.md), [Determination Affectation (IDE 184)](PBG-IDE-184.md), [Chambres GM disponibles (IDE 291)](PBG-IDE-291.md), [Chambres GO disponibles (IDE 292)](PBG-IDE-292.md)
- **Appelle**: 0 programmes | **Tables**: 1 (W:0 R:1 L:0) | **Taches**: 1 | **Expressions**: 21

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **185.1** | [**Verification Occupation** (185)](#t1) | MDI | - | Validation |

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
| E | P0-P/U Occupation | Alpha | [185](#t1) |
| F | P0-Date Debut | Date | 1x refs |
| G | P0-Heure Debut | Alpha | 1x refs |
| H | P0-Date Fin | Date | 1x refs |
| I | P0-Heure Fin | Alpha | 1x refs |
| J | P0-Type Occupation | Alpha | [185](#t1) |
| K | P0-Autorisation | Logical | - |
| L | W0-Occupation | Numeric | 3x refs |
| M | W0-Flag Occupation | Numeric | [185](#t1) |
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

**21 / 21 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCULATION | 3 | 0 |
| CALCUL | 1 | 0 |
| CAST_LOGIQUE | 3 | 5 |
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

#### CAST_LOGIQUE (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 14 | `IF (W0-Flag Occupation [M]=6 AND W0-Flag Single [N]=6 AND W0-Flag Blocage [O]=6 AND W0-Flag Qualite [P]=6,'TRUE'LOG,'FALSE'LOG)` | [RM-001](#rm-RM-001) |
| CAST_LOGIQUE | 21 | `'TRUE'LOG` | - |
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

### 12.3 Toutes les expressions (21)

<details>
<summary>Voir les 21 expressions</summary>

#### CALCULATION (3)

| IDE | Expression Decodee |
|-----|-------------------|
| 2 | `P0-Date Debut [F]*100+Val (P0-Heure Debut [G],'##')` |
| 3 | `P0-Date Fin [H]*100+Val (P0-Heure Fin [I],'##')` |
| 8 | `W0-Occupation [L]+1` |

#### CALCUL (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 7 | `[V]*100+Val ([W],'##')<W0-Date/Heure Fin [R] AND [X]*100+Val ([Y],'##')>W0-Date/Heure Debut [Q]` |

#### CAST_LOGIQUE (3)

| IDE | Expression Decodee |
|-----|-------------------|
| 14 | `IF (W0-Flag Occupation [M]=6 AND W0-Flag Single [N]=6 AND W0-Flag Blocage [O]=6 AND W0-Flag Qualite [P]=6,'TRUE'LOG,'FALSE'LOG)` |
| 1 | `'FALSE'LOG` |
| 21 | `'TRUE'LOG` |

#### CONSTANTE (3)

| IDE | Expression Decodee |
|-----|-------------------|
| 5 | `'H'` |
| 15 | `6` |
| 16 | `0` |

#### OTHER (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 4 | `P0-Code Societe [A]` |
| 6 | `P0-Nom Logement [C]` |

#### CONDITION (9)

| IDE | Expression Decodee |
|-----|-------------------|
| 9 | `[Z]<>ASCIIChr (15)` |
| 10 | `W0-Flag Blocage [O]<>6` |
| 11 | `W0-Flag Blocage [O]=6  AND W0-Flag Single [N]<>6` |
| 12 | `W0-Flag Blocage [O]=6 AND W0-Flag Single [N]=6 AND W0-Flag Occupation [M]<>6` |
| 13 | `W0-Flag Blocage [O]=6 AND W0-Flag Single [N]=6 AND W0-Flag Occupation [M]=6 AND W0-Flag Qualite [P]<>6` |
| 17 | `W0-Occupation [L]>=P0-Occupation Std [D]` |
| 19 | `[Z]=ASCIIChr (15)` |
| 20 | `P0-Type Occupation [J]<>[AA] AND [Z]<>ASCIIChr (15)` |
| 18 | `Trim(MID(P0-P/U Occupation [E],2,2))='1' AND W0-Occupation [L]>0 OR Trim(MID([Z],2,2))='1'` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Logement Client (IDE 0)](PBG-IDE-0.md) -> **Verification Adherents (IDE 185)**

Main -> ... -> [Logement Exterieur (IDE 0)](PBG-IDE-0.md) -> **Verification Adherents (IDE 185)**

Main -> ... -> [Logement Personnel (IDE 0)](PBG-IDE-0.md) -> **Verification Adherents (IDE 185)**

Main -> ... -> [Logement Exterieur (IDE 171)](PBG-IDE-171.md) -> **Verification Adherents (IDE 185)**

Main -> ... -> [Logement Personnel (IDE 172)](PBG-IDE-172.md) -> **Verification Adherents (IDE 185)**

Main -> ... -> [Logement Client (IDE 173)](PBG-IDE-173.md) -> **Verification Adherents (IDE 185)**

Main -> ... -> [Logement Client pms-626 (IDE 174)](PBG-IDE-174.md) -> **Verification Adherents (IDE 185)**

Main -> ... -> [Logement Client (IDE 385)](PBG-IDE-385.md) -> **Verification Adherents (IDE 185)**

Main -> ... -> [Affec manuelle chambre (IDE 21)](PBG-IDE-21.md) -> **Verification Adherents (IDE 185)**

Main -> ... -> [Determination Affectation (IDE 184)](PBG-IDE-184.md) -> **Verification Adherents (IDE 185)**

Main -> ... -> [Chambres GM disponibles (IDE 291)](PBG-IDE-291.md) -> **Verification Adherents (IDE 185)**

Main -> ... -> [Chambres GO disponibles (IDE 292)](PBG-IDE-292.md) -> **Verification Adherents (IDE 185)**

```mermaid
graph LR
    T185[185 Verification Adher...]
    style T185 fill:#58a6ff
    CC119[119 Recherche Logement]
    style CC119 fill:#8b5cf6
    CC117[117 Affiche rech logement]
    style CC117 fill:#f59e0b
    CC169[169 Affectation libera...]
    style CC169 fill:#f59e0b
    CC21[21 Affec manuelle chambre]
    style CC21 fill:#3fb950
    CC171[171 Logement Exterieur]
    style CC171 fill:#3fb950
    CC169 --> CC21
    CC169 --> CC171
    CC117 --> CC169
    CC119 --> CC117
    CC21 --> T185
    CC171 --> T185
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [0](PBG-IDE-0.md) | Logement Client | 2 |
| [0](PBG-IDE-0.md) | Logement Exterieur | 2 |
| [0](PBG-IDE-0.md) | Logement Personnel | 2 |
| [171](PBG-IDE-171.md) | Logement Exterieur | 2 |
| [172](PBG-IDE-172.md) | Logement Personnel | 2 |
| [173](PBG-IDE-173.md) | Logement Client | 2 |
| [174](PBG-IDE-174.md) | Logement Client pms-626 | 2 |
| [385](PBG-IDE-385.md) | Logement Client | 2 |
| [21](PBG-IDE-21.md) | Affec manuelle chambre | 1 |
| [184](PBG-IDE-184.md) | Determination Affectation | 1 |
| [291](PBG-IDE-291.md) | Chambres GM disponibles | 1 |
| [292](PBG-IDE-292.md) | Chambres GO disponibles | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T185[185 Verification Adher...]
    style T185 fill:#58a6ff
    NONE[Aucun callee]
    T185 -.-> NONE
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
| Lignes de logique | 59 | Programme compact |
| Expressions | 21 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 59) | Code sain |
| Regles metier | 1 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Validation (1 tache: 0 ecran, 1 traitement)

- **Strategie** : FluentValidation avec validators specifiques.
- Chaque tache de validation -> un validator injectable

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 10:02*
