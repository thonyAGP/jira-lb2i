# CAB IDE 10 - Recuperation du titre

> **Analyse**: Phases 1-4 2026-02-03 09:59 -> 09:59 (16s) | Assemblage 09:59
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | CAB |
| IDE Position | 10 |
| Nom Programme | Recuperation du titre |
| Fichier source | `Prg_10.xml` |
| Domaine metier | General |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Recuperation du titre** assure la gestion complete de ce processus, accessible depuis [Menu caisse GM - scroll @ (IDE 22)](CAB-IDE-22.md), [Liste des affilies  @ (IDE 21)](CAB-IDE-21.md), [Messages  @ (IDE 24)](CAB-IDE-24.md), [Zoom moyen de règlement  @ (IDE 34)](CAB-IDE-34.md), [Zoom devise (68)  @ (IDE 35)](CAB-IDE-35.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>10 - Recuperation du titre

**Role** : Consultation/chargement : Recuperation du titre.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Menu caisse GM - scroll @ (IDE 22)](CAB-IDE-22.md), [Liste des affilies  @ (IDE 21)](CAB-IDE-21.md), [Messages  @ (IDE 24)](CAB-IDE-24.md), [Zoom moyen de règlement  @ (IDE 34)](CAB-IDE-34.md), [Zoom devise (68)  @ (IDE 35)](CAB-IDE-35.md)
- **Appelle**: 0 programmes | **Tables**: 1 (W:0 R:1 L:0) | **Taches**: 1 | **Expressions**: 4

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **10.1** | [**Recuperation du titre** (10)](#t1) | MDI | - | Traitement |

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
| CONSTANTE | 3 | `'CA'` | - |

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

Main -> ... -> [Menu caisse GM - scroll @ (IDE 22)](CAB-IDE-22.md) -> **Recuperation du titre (IDE 10)**

Main -> ... -> [Liste des affilies  @ (IDE 21)](CAB-IDE-21.md) -> **Recuperation du titre (IDE 10)**

Main -> ... -> [Messages  @ (IDE 24)](CAB-IDE-24.md) -> **Recuperation du titre (IDE 10)**

Main -> ... -> [Zoom moyen de règlement  @ (IDE 34)](CAB-IDE-34.md) -> **Recuperation du titre (IDE 10)**

Main -> ... -> [Zoom devise (68)  @ (IDE 35)](CAB-IDE-35.md) -> **Recuperation du titre (IDE 10)**

```mermaid
graph LR
    T10[10 Recuperation du titre]
    style T10 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC33[33 Visualisation Appel]
    style CC33 fill:#f59e0b
    CC35[35 Zoom devise 68 @]
    style CC35 fill:#3fb950
    CC21[21 Liste des affilies @]
    style CC21 fill:#3fb950
    CC22[22 Menu caisse GM - sc...]
    style CC22 fill:#3fb950
    CC24[24 Messages @]
    style CC24 fill:#3fb950
    CC34[34 Zoom moyen de règle...]
    style CC34 fill:#3fb950
    CC33 --> CC21
    CC33 --> CC22
    CC33 --> CC24
    CC33 --> CC34
    CC33 --> CC35
    CC1 --> CC33
    CC21 --> T10
    CC22 --> T10
    CC24 --> T10
    CC34 --> T10
    CC35 --> T10
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [22](CAB-IDE-22.md) | Menu caisse GM - scroll @ | 2 |
| [21](CAB-IDE-21.md) | Liste des affilies  @ | 1 |
| [24](CAB-IDE-24.md) | Messages  @ | 1 |
| [34](CAB-IDE-34.md) | Zoom moyen de règlement  @ | 1 |
| [35](CAB-IDE-35.md) | Zoom devise (68)  @ | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T10[10 Recuperation du titre]
    style T10 fill:#58a6ff
    NONE[Aucun callee]
    T10 -.-> NONE
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
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 09:59*
