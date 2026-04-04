# PVE IDE 147 - Combo discount reasons

> **Analyse**: Phases 1-4 2026-02-03 09:43 -> 09:44 (17s) | Assemblage 09:44
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PVE |
| IDE Position | 147 |
| Nom Programme | Combo discount reasons |
| Fichier source | `Prg_147.xml` |
| Domaine metier | General |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Combo discount reasons** assure la gestion complete de ce processus, accessible depuis [Initialization (IDE 145)](PVE-IDE-145.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>147 - Combo discounts

**Role** : Traitement : Combo discounts.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Initialization (IDE 145)](PVE-IDE-145.md)
- **Appelle**: 0 programmes | **Tables**: 1 (W:0 R:1 L:0) | **Taches**: 1 | **Expressions**: 4

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **147.1** | [**Combo discounts** (147)](#t1) | MDI | - | Traitement |

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
| 386 | ski_frame |  | DB | R |   |   | 1 |

### Colonnes par table (0 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 386 - ski_frame (R) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

*(Programme sans variables locales mappees)*

## 12. EXPRESSIONS

**4 / 4 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCULATION | 1 | 0 |
| OTHER | 2 | 0 |
| CONCATENATION | 1 | 0 |

### 12.2 Expressions cles par type

#### CALCULATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 3 | `Left (v.list [A],Len (Trim (v.list [A]))-1)` | - |

#### OTHER (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 4 | `SetParam ('COMBODISCOUNT',v.list [A])` | - |
| OTHER | 1 | `GetParam ('SERVICE')` | - |

#### CONCATENATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 2 | `Trim (v.list [A])&Trim ([D])&','` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Initialization (IDE 145)](PVE-IDE-145.md) -> **Combo discount reasons (IDE 147)**

```mermaid
graph LR
    T147[147 Combo discount rea...]
    style T147 fill:#58a6ff
    CC178[178 Menu Administration]
    style CC178 fill:#8b5cf6
    CC185[185 Menu]
    style CC185 fill:#f59e0b
    CC12[12 General settings]
    style CC12 fill:#f59e0b
    CC353[353 Menu==V4]
    style CC353 fill:#f59e0b
    CC294[294 Get Service]
    style CC294 fill:#f59e0b
    CC5[5 Test Upgrade]
    style CC5 fill:#f59e0b
    CC1[1 Main Program]
    style CC1 fill:#f59e0b
    CC332[332 Choix - Services]
    style CC332 fill:#f59e0b
    CC143[143 START]
    style CC143 fill:#f59e0b
    CC145[145 Initialization]
    style CC145 fill:#3fb950
    CC1 --> CC145
    CC5 --> CC145
    CC143 --> CC145
    CC332 --> CC145
    CC12 --> CC1
    CC185 --> CC1
    CC294 --> CC1
    CC353 --> CC1
    CC12 --> CC5
    CC185 --> CC5
    CC294 --> CC5
    CC353 --> CC5
    CC12 --> CC143
    CC185 --> CC143
    CC294 --> CC143
    CC353 --> CC143
    CC12 --> CC332
    CC185 --> CC332
    CC294 --> CC332
    CC353 --> CC332
    CC178 --> CC12
    CC178 --> CC185
    CC178 --> CC294
    CC178 --> CC353
    CC145 --> T147
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [145](PVE-IDE-145.md) | Initialization | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T147[147 Combo discount rea...]
    style T147 fill:#58a6ff
    NONE[Aucun callee]
    T147 -.-> NONE
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
| Lignes de logique | 9 | Programme compact |
| Expressions | 4 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 9) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 0 ecran, 1 traitement)

- **Strategie** : 1 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 09:44*
