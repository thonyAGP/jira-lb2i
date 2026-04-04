# LOG IDE 5 - Recuperation du titre

> **Analyse**: Phases 1-4 2026-02-03 14:39 -> 14:39 (10s) | Assemblage 14:39
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | LOG |
| IDE Position | 5 |
| Nom Programme | Recuperation du titre |
| Fichier source | `Prg_5.xml` |
| Dossier IDE | Divers |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Recuperation du titre** assure la gestion complete de ce processus, accessible depuis [CL Mot de passe (IDE 12)](LOG-IDE-12.md), [CL mise à jour des sociétés (IDE 13)](LOG-IDE-13.md), [CL mise à jour des groupes (IDE 14)](LOG-IDE-14.md), [CL login utilisateur (IDE 15)](LOG-IDE-15.md), [   Droit / utilisateur (IDE 16)](LOG-IDE-16.md), [Gestion Opérateurs (IDE 17)](LOG-IDE-17.md), [CL login utilisateur   *SAV* (IDE 20)](LOG-IDE-20.md), [CL Menu (IDE 21)](LOG-IDE-21.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>5 - Recuperation du titre

**Role** : Consultation/chargement : Recuperation du titre.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [CL Mot de passe (IDE 12)](LOG-IDE-12.md), [CL mise à jour des sociétés (IDE 13)](LOG-IDE-13.md), [CL mise à jour des groupes (IDE 14)](LOG-IDE-14.md), [CL login utilisateur (IDE 15)](LOG-IDE-15.md), [   Droit / utilisateur (IDE 16)](LOG-IDE-16.md), [Gestion Opérateurs (IDE 17)](LOG-IDE-17.md), [CL login utilisateur   *SAV* (IDE 20)](LOG-IDE-20.md), [CL Menu (IDE 21)](LOG-IDE-21.md)
- **Appelle**: 0 programmes | **Tables**: 1 (W:0 R:1 L:0) | **Taches**: 1 | **Expressions**: 4

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **5.1** | [**Recuperation du titre** (5)](#t1) | MDI | - | Traitement |

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
| 719 | arc_transac_detail_bar |  | DB | R |   |   | 1 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 719 - arc_transac_detail_bar (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | > code ecran | R | Numeric |
| B | < nom ecran | R | Alpha |

</details>

## 11. VARIABLES

### 11.1 Autres (2)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | > code ecran | Numeric | 1x refs |
| B | < nom ecran | Alpha | - |

## 12. EXPRESSIONS

**4 / 4 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONCATENATION | 1 | 0 |
| CONSTANTE | 1 | 0 |
| OTHER | 1 | 0 |
| CONDITION | 1 | 0 |

### 12.2 Expressions cles par type

#### CONCATENATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 4 | `Trim ([F])&' - '&Trim ([G])` | - |

#### CONSTANTE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 3 | `'LO'` | - |

#### OTHER (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 1 | `GetParam ('CODELANGUE')` | - |

#### CONDITION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 2 | `> code ecran [A]` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [CL Mot de passe (IDE 12)](LOG-IDE-12.md) -> **Recuperation du titre (IDE 5)**

Main -> ... -> [CL mise à jour des sociétés (IDE 13)](LOG-IDE-13.md) -> **Recuperation du titre (IDE 5)**

Main -> ... -> [CL mise à jour des groupes (IDE 14)](LOG-IDE-14.md) -> **Recuperation du titre (IDE 5)**

Main -> ... -> [CL login utilisateur (IDE 15)](LOG-IDE-15.md) -> **Recuperation du titre (IDE 5)**

Main -> ... -> [   Droit / utilisateur (IDE 16)](LOG-IDE-16.md) -> **Recuperation du titre (IDE 5)**

Main -> ... -> [Gestion Opérateurs (IDE 17)](LOG-IDE-17.md) -> **Recuperation du titre (IDE 5)**

Main -> ... -> [CL login utilisateur   *SAV* (IDE 20)](LOG-IDE-20.md) -> **Recuperation du titre (IDE 5)**

Main -> ... -> [CL Menu (IDE 21)](LOG-IDE-21.md) -> **Recuperation du titre (IDE 5)**

```mermaid
graph LR
    T5[5 Recuperation du titre]
    style T5 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC21[21 CL Menu]
    style CC21 fill:#f59e0b
    CC20[20 CL login utilisateu...]
    style CC20 fill:#f59e0b
    CC12[12 CL Mot de passe]
    style CC12 fill:#3fb950
    CC16[16 Droit utilisateur]
    style CC16 fill:#3fb950
    CC13[13 CL mise à jour des ...]
    style CC13 fill:#3fb950
    CC14[14 CL mise à jour des ...]
    style CC14 fill:#3fb950
    CC15[15 CL login utilisateur]
    style CC15 fill:#3fb950
    CC20 --> CC12
    CC21 --> CC12
    CC20 --> CC13
    CC21 --> CC13
    CC20 --> CC14
    CC21 --> CC14
    CC20 --> CC15
    CC21 --> CC15
    CC20 --> CC16
    CC21 --> CC16
    CC1 --> CC20
    CC1 --> CC21
    CC12 --> T5
    CC13 --> T5
    CC14 --> T5
    CC15 --> T5
    CC16 --> T5
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [12](LOG-IDE-12.md) | CL Mot de passe | 1 |
| [13](LOG-IDE-13.md) | CL mise à jour des sociétés | 1 |
| [14](LOG-IDE-14.md) | CL mise à jour des groupes | 1 |
| [15](LOG-IDE-15.md) | CL login utilisateur | 1 |
| [16](LOG-IDE-16.md) |    Droit / utilisateur | 1 |
| [17](LOG-IDE-17.md) | Gestion Opérateurs | 1 |
| [20](LOG-IDE-20.md) | CL login utilisateur   *SAV* | 1 |
| [21](LOG-IDE-21.md) | CL Menu | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T5[5 Recuperation du titre]
    style T5 fill:#58a6ff
    NONE[Aucun callee]
    T5 -.-> NONE
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
| Lignes de logique | 12 | Programme compact |
| Expressions | 4 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 12) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 0 ecran, 1 traitement)

- **Strategie** : 1 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 14:39*
