# PVE IDE 118 - Recuperation du titre

> **Analyse**: Phases 1-4 2026-02-03 09:31 -> 09:31 (17s) | Assemblage 09:31
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PVE |
| IDE Position | 118 |
| Nom Programme | Recuperation du titre |
| Fichier source | `Prg_118.xml` |
| Domaine metier | General |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Recuperation du titre** assure la gestion complete de ce processus, accessible depuis [Saisie des OD (IDE 119)](PVE-IDE-119.md), [Extrait - Sélection d'un GM (IDE 120)](PVE-IDE-120.md), [Extrait de compte (IDE 121)](PVE-IDE-121.md), [Zoom articles imputation (IDE 335)](PVE-IDE-335.md), [Zoom articles code (IDE 336)](PVE-IDE-336.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

**Logique metier** : 1 regles identifiees couvrant valeurs par defaut.

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>118 - Recuperation du titre

**Role** : Consultation/chargement : Recuperation du titre.


## 5. REGLES METIER

1 regles identifiees:

### Autres (1 regles)

#### <a id="rm-RM-001"></a>[RM-001] Valeur par defaut si > type prog [C] est vide

| Element | Detail |
|---------|--------|
| **Condition** | `> type prog [C]=''` |
| **Si vrai** | 'CA' |
| **Si faux** | > type prog [C]) |
| **Variables** | C (> type prog) |
| **Expression source** | Expression 3 : `IF (> type prog [C]='','CA',> type prog [C])` |
| **Exemple** | Si > type prog [C]='' â†’ 'CA'. Sinon â†’ > type prog [C]) |

## 6. CONTEXTE

- **Appele par**: [Saisie des OD (IDE 119)](PVE-IDE-119.md), [Extrait - Sélection d'un GM (IDE 120)](PVE-IDE-120.md), [Extrait de compte (IDE 121)](PVE-IDE-121.md), [Zoom articles imputation (IDE 335)](PVE-IDE-335.md), [Zoom articles code (IDE 336)](PVE-IDE-336.md)
- **Appelle**: 0 programmes | **Tables**: 1 (W:0 R:1 L:0) | **Taches**: 1 | **Expressions**: 4

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **118.1** | [**Recuperation du titre** (118)](#t1) | MDI | - | Traitement |

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
| A | > code écran | R | Numeric |
| B | < nom ecran | R | Alpha |
| C | > type prog | R | Alpha |

</details>

## 11. VARIABLES

### 11.1 Autres (3)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | > code écran | Numeric | 1x refs |
| B | < nom ecran | Alpha | - |
| C | > type prog | Alpha | 1x refs |

## 12. EXPRESSIONS

**4 / 4 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONCATENATION | 1 | 0 |
| CONDITION | 2 | 5 |
| OTHER | 1 | 0 |

### 12.2 Expressions cles par type

#### CONCATENATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 4 | `Trim ([G])&' - '&Trim ([H])` | - |

#### CONDITION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 3 | `IF (> type prog [C]='','CA',> type prog [C])` | [RM-001](#rm-RM-001) |
| CONDITION | 2 | `> code écran [A]` | - |

#### OTHER (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 1 | `GetParam ('CODELANGUE')` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Saisie des OD (IDE 119)](PVE-IDE-119.md) -> **Recuperation du titre (IDE 118)**

Main -> ... -> [Extrait - Sélection d'un GM (IDE 120)](PVE-IDE-120.md) -> **Recuperation du titre (IDE 118)**

Main -> ... -> [Extrait de compte (IDE 121)](PVE-IDE-121.md) -> **Recuperation du titre (IDE 118)**

Main -> ... -> [Zoom articles imputation (IDE 335)](PVE-IDE-335.md) -> **Recuperation du titre (IDE 118)**

Main -> ... -> [Zoom articles code (IDE 336)](PVE-IDE-336.md) -> **Recuperation du titre (IDE 118)**

```mermaid
graph LR
    T118[118 Recuperation du titre]
    style T118 fill:#58a6ff
    CC180[180 Menu Cloture du se...]
    style CC180 fill:#8b5cf6
    CC397[397 Menu Service clotu...]
    style CC397 fill:#8b5cf6
    CC402[402 Menu Service cloture]
    style CC402 fill:#8b5cf6
    CC404[404 Fin de journéeTele...]
    style CC404 fill:#f59e0b
    CC102[102 Etiquette CAB]
    style CC102 fill:#f59e0b
    CC114[114 Fin de journée]
    style CC114 fill:#f59e0b
    CC120[120 Extrait - Sélectio...]
    style CC120 fill:#3fb950
    CC119[119 Saisie des OD]
    style CC119 fill:#3fb950
    CC121[121 Extrait de compte]
    style CC121 fill:#3fb950
    CC336[336 Zoom articles code]
    style CC336 fill:#3fb950
    CC335[335 Zoom articles impu...]
    style CC335 fill:#3fb950
    CC114 --> CC119
    CC404 --> CC119
    CC102 --> CC119
    CC114 --> CC120
    CC404 --> CC120
    CC102 --> CC120
    CC114 --> CC121
    CC404 --> CC121
    CC102 --> CC121
    CC114 --> CC335
    CC404 --> CC335
    CC102 --> CC335
    CC114 --> CC336
    CC404 --> CC336
    CC102 --> CC336
    CC180 --> CC114
    CC397 --> CC114
    CC402 --> CC114
    CC180 --> CC404
    CC397 --> CC404
    CC402 --> CC404
    CC180 --> CC102
    CC397 --> CC102
    CC402 --> CC102
    CC119 --> T118
    CC120 --> T118
    CC121 --> T118
    CC335 --> T118
    CC336 --> T118
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [119](PVE-IDE-119.md) | Saisie des OD | 1 |
| [120](PVE-IDE-120.md) | Extrait - Sélection d'un GM | 1 |
| [121](PVE-IDE-121.md) | Extrait de compte | 1 |
| [335](PVE-IDE-335.md) | Zoom articles imputation | 1 |
| [336](PVE-IDE-336.md) | Zoom articles code | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T118[118 Recuperation du titre]
    style T118 fill:#58a6ff
    NONE[Aucun callee]
    T118 -.-> NONE
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
| Lignes de logique | 13 | Programme compact |
| Expressions | 4 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 13) | Code sain |
| Regles metier | 1 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 0 ecran, 1 traitement)

- **Strategie** : 1 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 09:31*
