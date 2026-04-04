# PBG IDE 140 - Recuperation langue

> **Analyse**: Phases 1-4 2026-02-03 09:40 -> 09:40 (18s) | Assemblage 09:40
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBG |
| IDE Position | 140 |
| Nom Programme | Recuperation langue |
| Fichier source | `Prg_140.xml` |
| Domaine metier | General |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Recuperation langue** assure la gestion complete de ce processus, accessible depuis [Main Program (IDE 1)](PBG-IDE-1.md), [start (IDE 139)](PBG-IDE-139.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

**Logique metier** : 1 regles identifiees couvrant valeurs par defaut.

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>140 - Recuperation langue

**Role** : Consultation/chargement : Recuperation langue.


## 5. REGLES METIER

1 regles identifiees:

### Autres (1 regles)

#### <a id="rm-RM-001"></a>[RM-001] Valeur par defaut si [C] est vide

| Element | Detail |
|---------|--------|
| **Condition** | `[C]=''` |
| **Si vrai** | 'FRA' |
| **Si faux** | [C]) |
| **Expression source** | Expression 14 : `IF ([C]='','FRA',[C])` |
| **Exemple** | Si [C]='' â†’ 'FRA'. Sinon â†’ [C]) |

## 6. CONTEXTE

- **Appele par**: [Main Program (IDE 1)](PBG-IDE-1.md), [start (IDE 139)](PBG-IDE-139.md)
- **Appelle**: 0 programmes | **Tables**: 1 (W:0 R:1 L:0) | **Taches**: 1 | **Expressions**: 14

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **140.1** | [**Recuperation langue** (140)](#t1) | MDI | - | Traitement |

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
| 740 | pv_stock_movements | Articles et stock | DB | R |   |   | 1 |

### Colonnes par table (0 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 740 - pv_stock_movements (R) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

*(Programme sans variables locales mappees)*

## 12. EXPRESSIONS

**14 / 14 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONDITION | 2 | 5 |
| CONSTANTE | 1 | 0 |
| REFERENCE_VG | 1 | 0 |
| CAST_LOGIQUE | 8 | 0 |
| OTHER | 1 | 0 |
| STRING | 1 | 0 |

### 12.2 Expressions cles par type

#### CONDITION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 14 | `IF ([C]='','FRA',[C])` | [RM-001](#rm-RM-001) |
| CONDITION | 3 | `SetParam ('CODELANGUE',IF ([C]='','FRA',[C]))` | - |

#### CONSTANTE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 1 | `'C'` | - |

#### REFERENCE_VG (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 2 | `VG20` | - |

#### CAST_LOGIQUE (8 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 10 | `MnuShow ('6','TRUE'LOG)` | - |
| CAST_LOGIQUE | 9 | `MnuShow ('5','TRUE'LOG)` | - |
| CAST_LOGIQUE | 12 | `MnuShow ('8','TRUE'LOG)` | - |
| CAST_LOGIQUE | 11 | `MnuShow ('7','TRUE'LOG)` | - |
| CAST_LOGIQUE | 6 | `MnuShow ('2','TRUE'LOG)` | - |
| ... | | *+3 autres* | |

#### OTHER (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 13 | `SetParam ('UTIGROUPE',[D])` | - |

#### STRING (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| STRING | 4 | `SetLang (Trim ([C]))` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Main Program (IDE 1)](PBG-IDE-1.md) -> **Recuperation langue (IDE 140)**

Main -> ... -> [start (IDE 139)](PBG-IDE-139.md) -> **Recuperation langue (IDE 140)**

```mermaid
graph LR
    T140[140 Recuperation langue]
    style T140 fill:#58a6ff
    CC139[139 start]
    style CC139 fill:#8b5cf6
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC1 --> T140
    CC139 --> T140
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [1](PBG-IDE-1.md) | Main Program | 1 |
| [139](PBG-IDE-139.md) | start | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T140[140 Recuperation langue]
    style T140 fill:#58a6ff
    NONE[Aucun callee]
    T140 -.-> NONE
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
| Lignes de logique | 21 | Programme compact |
| Expressions | 14 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 21) | Code sain |
| Regles metier | 1 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 0 ecran, 1 traitement)

- **Strategie** : 1 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 09:40*
