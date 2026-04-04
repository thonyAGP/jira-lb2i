# REF IDE 837 - Clause Where

> **Analyse**: Phases 1-4 2026-02-03 14:39 -> 14:39 (14s) | Assemblage 14:39
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | REF |
| IDE Position | 837 |
| Nom Programme | Clause Where |
| Fichier source | `Prg_837.xml` |
| Dossier IDE | General |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 1 |

## 2. DESCRIPTION FONCTIONNELLE

**Clause Where** assure la gestion complete de ce processus, accessible depuis [Requete fiche de police (IDE 666)](REF-IDE-666.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

**Logique metier** : 1 regles identifiees couvrant conditions metier.

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>837 - UTI054-Clause Where sans where

**Role** : Traitement : UTI054-Clause Where sans where.
**Variables liees** : A (<Clause where résultat), C (>avec Where au début?)
**Delegue a** : [Adapter guillemets SQL (IDE 839)](REF-IDE-839.md)


## 5. REGLES METIER

1 regles identifiees:

### Autres (1 regles)

#### <a id="rm-RM-001"></a>[RM-001] Si >Condition 19 [V] alors 'AND' sinon 'OR')

| Element | Detail |
|---------|--------|
| **Condition** | `>Condition 19 [V]` |
| **Si vrai** | 'AND' |
| **Si faux** | 'OR') |
| **Variables** | V (>Condition 19) |
| **Expression source** | Expression 46 : `IF(>Condition 19 [V],'AND','OR')` |
| **Exemple** | Si >Condition 19 [V] â†’ 'AND'. Sinon â†’ 'OR') |

## 6. CONTEXTE

- **Appele par**: [Requete fiche de police (IDE 666)](REF-IDE-666.md)
- **Appelle**: 1 programmes | **Tables**: 0 (W:0 R:0 L:0) | **Taches**: 1 | **Expressions**: 46

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **837.1** | [**UTI054-Clause Where sans where** (837)](#t1) | - | - | Traitement |

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

### 11.1 Variables de session (1)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| X | v.And ou OR | Unicode | 20x session |

### 11.2 Autres (23)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | <Clause where résultat | Unicode | [837](#t1) |
| B | >AND? (sinon OR) | Logical | 2x refs |
| C | >avec Where au début? | Logical | [837](#t1) |
| D | >Condition 01 | Unicode | 2x refs |
| E | >Condition 02 | Unicode | 2x refs |
| F | >Condition 03 | Unicode | 2x refs |
| G | >Condition 04 | Unicode | 2x refs |
| H | >Condition 05 | Unicode | 2x refs |
| I | >Condition 06 | Unicode | 2x refs |
| J | >Condition 07 | Unicode | 2x refs |
| K | >Condition 08 | Unicode | 2x refs |
| L | >Condition 09 | Unicode | 2x refs |
| M | >Condition 10 | Unicode | 2x refs |
| N | >Condition 11 | Unicode | 2x refs |
| O | >Condition 12 | Unicode | 2x refs |
| P | >Condition 13 | Unicode | 2x refs |
| Q | >Condition 14 | Unicode | 2x refs |
| R | >Condition 15 | Unicode | 2x refs |
| S | >Condition 16 | Unicode | 2x refs |
| T | >Condition 17 | Unicode | 2x refs |
| U | >Condition 18 | Unicode | 2x refs |
| V | >Condition 19 | Unicode | 1x refs |
| W | >Condition 20 | Unicode | - |

<details>
<summary>Toutes les 24 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| V. | **X** | v.And ou OR | Unicode |
| Autre | **A** | <Clause where résultat | Unicode |
| Autre | **B** | >AND? (sinon OR) | Logical |
| Autre | **C** | >avec Where au début? | Logical |
| Autre | **D** | >Condition 01 | Unicode |
| Autre | **E** | >Condition 02 | Unicode |
| Autre | **F** | >Condition 03 | Unicode |
| Autre | **G** | >Condition 04 | Unicode |
| Autre | **H** | >Condition 05 | Unicode |
| Autre | **I** | >Condition 06 | Unicode |
| Autre | **J** | >Condition 07 | Unicode |
| Autre | **K** | >Condition 08 | Unicode |
| Autre | **L** | >Condition 09 | Unicode |
| Autre | **M** | >Condition 10 | Unicode |
| Autre | **N** | >Condition 11 | Unicode |
| Autre | **O** | >Condition 12 | Unicode |
| Autre | **P** | >Condition 13 | Unicode |
| Autre | **Q** | >Condition 14 | Unicode |
| Autre | **R** | >Condition 15 | Unicode |
| Autre | **S** | >Condition 16 | Unicode |
| Autre | **T** | >Condition 17 | Unicode |
| Autre | **U** | >Condition 18 | Unicode |
| Autre | **V** | >Condition 19 | Unicode |
| Autre | **W** | >Condition 20 | Unicode |

</details>

## 12. EXPRESSIONS

**46 / 46 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONDITION | 24 | 5 |
| CONSTANTE | 1 | 0 |
| CAST_LOGIQUE | 1 | 0 |
| CONCATENATION | 20 | 0 |

### 12.2 Expressions cles par type

#### CONDITION (24 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 46 | `IF(>Condition 19 [V],'AND','OR')` | [RM-001](#rm-RM-001) |
| CONDITION | 39 | `>Condition 13 [P]<>''` | - |
| CONDITION | 40 | `>Condition 14 [Q]<>''` | - |
| CONDITION | 38 | `>Condition 12 [O]<>''` | - |
| CONDITION | 36 | `>Condition 10 [M]<>''` | - |
| ... | | *+19 autres* | |

#### CONSTANTE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 1 | `''` | - |

#### CAST_LOGIQUE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 45 | `'TRUE'LOG` | - |

#### CONCATENATION (20 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 15 | `Trim(<Clause where résultat [A]) & IF(<Clause where résultat [A]<>'',' '&v.And ou OR [X]&'(','(')&Trim(>Condition 12 [O])&')'` | - |
| CONCATENATION | 16 | `Trim(<Clause where résultat [A]) & IF(<Clause where résultat [A]<>'',' '&v.And ou OR [X]&'(','(')&Trim(>Condition 13 [P])&')'` | - |
| CONCATENATION | 14 | `Trim(<Clause where résultat [A]) & IF(<Clause where résultat [A]<>'',' '&v.And ou OR [X]&'(','(')&Trim(>Condition 11 [N])&')'` | - |
| CONCATENATION | 12 | `Trim(<Clause where résultat [A]) & IF(<Clause where résultat [A]<>'',' '&v.And ou OR [X]&'(','(')&Trim(>Condition 09 [L])&')'` | - |
| CONCATENATION | 13 | `Trim(<Clause where résultat [A]) & IF(<Clause where résultat [A]<>'',' '&v.And ou OR [X]&'(','(')&Trim(>Condition 10 [M])&')'` | - |
| ... | | *+15 autres* | |

### 12.3 Toutes les expressions (46)

<details>
<summary>Voir les 46 expressions</summary>

#### CONDITION (24)

| IDE | Expression Decodee |
|-----|-------------------|
| 46 | `IF(>Condition 19 [V],'AND','OR')` |
| 24 | `<Clause where résultat [A]<>'' AND [Z]` |
| 25 | `>AND? (sinon OR) [B]<>''` |
| 26 | `>avec Where au début? [C]<>''` |
| 27 | `>Condition 01 [D]<>''` |
| 28 | `>Condition 02 [E]<>''` |
| 29 | `>Condition 03 [F]<>''` |
| 30 | `>Condition 04 [G]<>''` |
| 31 | `>Condition 05 [H]<>''` |
| 32 | `>Condition 06 [I]<>''` |
| 33 | `>Condition 07 [J]<>''` |
| 34 | `>Condition 08 [K]<>''` |
| 35 | `>Condition 09 [L]<>''` |
| 36 | `>Condition 10 [M]<>''` |
| 37 | `>Condition 11 [N]<>''` |
| 38 | `>Condition 12 [O]<>''` |
| 39 | `>Condition 13 [P]<>''` |
| 40 | `>Condition 14 [Q]<>''` |
| 41 | `>Condition 15 [R]<>''` |
| 42 | `>Condition 16 [S]<>''` |
| 43 | `>Condition 17 [T]<>''` |
| 44 | `>Condition 18 [U]<>''` |
| 22 | `Trim(<Clause where résultat [A])` |
| 23 | `'where '&Trim(<Clause where résultat [A])` |

#### CONSTANTE (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 1 | `''` |

#### CAST_LOGIQUE (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 45 | `'TRUE'LOG` |

#### CONCATENATION (20)

| IDE | Expression Decodee |
|-----|-------------------|
| 2 | `Trim(<Clause where résultat [A]) & IF(<Clause where résultat [A]<>'',' '&v.And ou OR [X]&'(','(')&Trim(>AND? (sinon OR) [B])&')'` |
| 3 | `Trim(<Clause where résultat [A]) & IF(<Clause where résultat [A]<>'',' '&v.And ou OR [X]&'(','(')&Trim(>avec Where au début? [C])&')'` |
| 4 | `Trim(<Clause where résultat [A]) & IF(<Clause where résultat [A]<>'',' '&v.And ou OR [X]&'(','(')&Trim(>Condition 01 [D])&')'` |
| 5 | `Trim(<Clause where résultat [A]) & IF(<Clause where résultat [A]<>'',' '&v.And ou OR [X]&'(','(')&Trim(>Condition 02 [E])&')'` |
| 6 | `Trim(<Clause where résultat [A]) & IF(<Clause where résultat [A]<>'',' '&v.And ou OR [X]&'(','(')&Trim(>Condition 03 [F])&')'` |
| 7 | `Trim(<Clause where résultat [A]) & IF(<Clause where résultat [A]<>'',' '&v.And ou OR [X]&'(','(')&Trim(>Condition 04 [G])&')'` |
| 8 | `Trim(<Clause where résultat [A]) & IF(<Clause where résultat [A]<>'',' '&v.And ou OR [X]&'(','(')&Trim(>Condition 05 [H])&')'` |
| 9 | `Trim(<Clause where résultat [A]) & IF(<Clause where résultat [A]<>'',' '&v.And ou OR [X]&'(','(')&Trim(>Condition 06 [I])&')'` |
| 10 | `Trim(<Clause where résultat [A]) & IF(<Clause where résultat [A]<>'',' '&v.And ou OR [X]&'(','(')&Trim(>Condition 07 [J])&')'` |
| 11 | `Trim(<Clause where résultat [A]) & IF(<Clause where résultat [A]<>'',' '&v.And ou OR [X]&'(','(')&Trim(>Condition 08 [K])&')'` |
| 12 | `Trim(<Clause where résultat [A]) & IF(<Clause where résultat [A]<>'',' '&v.And ou OR [X]&'(','(')&Trim(>Condition 09 [L])&')'` |
| 13 | `Trim(<Clause where résultat [A]) & IF(<Clause where résultat [A]<>'',' '&v.And ou OR [X]&'(','(')&Trim(>Condition 10 [M])&')'` |
| 14 | `Trim(<Clause where résultat [A]) & IF(<Clause where résultat [A]<>'',' '&v.And ou OR [X]&'(','(')&Trim(>Condition 11 [N])&')'` |
| 15 | `Trim(<Clause where résultat [A]) & IF(<Clause where résultat [A]<>'',' '&v.And ou OR [X]&'(','(')&Trim(>Condition 12 [O])&')'` |
| 16 | `Trim(<Clause where résultat [A]) & IF(<Clause where résultat [A]<>'',' '&v.And ou OR [X]&'(','(')&Trim(>Condition 13 [P])&')'` |
| 17 | `Trim(<Clause where résultat [A]) & IF(<Clause where résultat [A]<>'',' '&v.And ou OR [X]&'(','(')&Trim(>Condition 14 [Q])&')'` |
| 18 | `Trim(<Clause where résultat [A]) & IF(<Clause where résultat [A]<>'',' '&v.And ou OR [X]&'(','(')&Trim(>Condition 15 [R])&')'` |
| 19 | `Trim(<Clause where résultat [A]) & IF(<Clause where résultat [A]<>'',' '&v.And ou OR [X]&'(','(')&Trim(>Condition 16 [S])&')'` |
| 20 | `Trim(<Clause where résultat [A]) & IF(<Clause where résultat [A]<>'',' '&v.And ou OR [X]&'(','(')&Trim(>Condition 17 [T])&')'` |
| 21 | `Trim(<Clause where résultat [A]) & IF(<Clause where résultat [A]<>'',' '&v.And ou OR [X]&'(','(')&Trim(>Condition 18 [U])&')'` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Requete fiche de police (IDE 666)](REF-IDE-666.md) -> **Clause Where (IDE 837)**

```mermaid
graph LR
    T837[837 Clause Where]
    style T837 fill:#58a6ff
    CC666[666 Requete fiche de p...]
    style CC666 fill:#8b5cf6
    CC666 --> T837
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [666](REF-IDE-666.md) | Requete fiche de police | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T837[837 Clause Where]
    style T837 fill:#58a6ff
    C839[839 Adapter guillemets...]
    T837 --> C839
    style C839 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [839](REF-IDE-839.md) | Adapter guillemets SQL | 20 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 78 | Programme compact |
| Expressions | 46 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 1 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 78) | Code sain |
| Regles metier | 1 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 0 ecran, 1 traitement)

- **Strategie** : 1 service(s) backend injectable(s) (Domain Services).
- 1 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| [Adapter guillemets SQL (IDE 839)](REF-IDE-839.md) | Sous-programme | 20x | **CRITIQUE** - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 14:39*
