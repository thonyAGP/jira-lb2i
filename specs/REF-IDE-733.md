# REF IDE 733 - Stock - Mouvement

> **Analyse**: Phases 1-4 2026-02-03 14:01 -> 14:02 (17s) | Assemblage 14:02
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | REF |
| IDE Position | 733 |
| Nom Programme | Stock - Mouvement |
| Fichier source | `Prg_733.xml` |
| Dossier IDE | General |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Stock - Mouvement** assure la gestion complete de ce processus, accessible depuis [Stock - Sale/Cancel (IDE 732)](REF-IDE-732.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

**Donnees modifiees** : 1 tables en ecriture (pv_stock_movements).

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>733 - Action Cancel Exit

**Role** : Traitement : Action Cancel Exit.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Stock - Sale/Cancel (IDE 732)](REF-IDE-732.md)
- **Appelle**: 0 programmes | **Tables**: 1 (W:1 R:0 L:0) | **Taches**: 1 | **Expressions**: 15

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **733.1** | [**Action Cancel Exit** (733)](#t1) | MDI | - | Traitement |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Traitement principal]
    UPDATE[MAJ 1 tables]
    ENDOK([END OK])

    START --> INIT --> SAISIE
    SAISIE --> UPDATE --> ENDOK

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
| 740 | pv_stock_movements | Articles et stock | DB |   | **W** |   | 1 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 740 - pv_stock_movements (**W**) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P. Product | W | Numeric |
| B | P. Customer | W | Numeric |
| C | P. Package ID OUT | W | Numeric |
| D | P. Movement | W | Numeric |
| E | P. Quantity to destock | W | Numeric |
| F | P. In ou Out | W | Alpha |
| G | P. Quantité stock (product) | W | Numeric |
| H | P. Selling Price | W | Numeric |
| I | P. Purchasing Price | W | Numeric |
| J | P. Discount | W | Numeric |
| K | P. VAT | W | Numeric |
| L | P. Volume vendu | W | Numeric |
| M | V Amount discounted | W | Numeric |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (12)

Variables recues du programme appelant ([Stock - Sale/Cancel (IDE 732)](REF-IDE-732.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P. Product | Numeric | 1x parametre entrant |
| B | P. Customer | Numeric | 1x parametre entrant |
| C | P. Package ID OUT | Numeric | 1x parametre entrant |
| D | P. Movement | Numeric | 1x parametre entrant |
| E | P. Quantity to destock | Numeric | 2x parametre entrant |
| F | P. In ou Out | Alpha | 3x parametre entrant |
| G | P. Quantité stock (product) | Numeric | - |
| H | P. Selling Price | Numeric | 2x parametre entrant |
| I | P. Purchasing Price | Numeric | 1x parametre entrant |
| J | P. Discount | Numeric | 1x parametre entrant |
| K | P. VAT | Numeric | - |
| L | P. Volume vendu | Numeric | 1x parametre entrant |

### 11.2 Variables de session (1)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| M | V Amount discounted | Numeric | - |

## 12. EXPRESSIONS

**15 / 15 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCUL | 1 | 0 |
| CONDITION | 2 | 0 |
| DATE | 1 | 0 |
| OTHER | 10 | 0 |
| REFERENCE_VG | 1 | 0 |

### 12.2 Expressions cles par type

#### CALCUL (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCUL | 1 | `Round (P. Selling Price [H]*(1-P. Discount [J]/100),12,GetParam ('DECIMALNUMBER'))` | - |

#### CONDITION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 15 | `P. Quantité stock (pro... [G]+IF (P. In ou Out [F]='In',ABS (P. Quantity to destock [E]),- (ABS (P. Quantity to destock [E])))` | - |
| CONDITION | 11 | `[W]+IF (P. In ou Out [F]='In',ABS (P. Quantity to destock [E]),- (ABS (P. Quantity to destock [E])))` | - |

#### DATE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| DATE | 4 | `Date ()` | - |

#### OTHER (10 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 10 | `P. Customer [B]` | - |
| OTHER | 8 | `P. In ou Out [F]` | - |
| OTHER | 12 | `P. Selling Price [H]` | - |
| OTHER | 14 | `P. Volume vendu [L]` | - |
| OTHER | 13 | `P. Purchasing Price [I]` | - |
| ... | | *+5 autres* | |

#### REFERENCE_VG (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 9 | `VG1` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Stock - Sale/Cancel (IDE 732)](REF-IDE-732.md) -> **Stock - Mouvement (IDE 733)**

```mermaid
graph LR
    T733[733 Stock - Mouvement]
    style T733 fill:#58a6ff
    CC728[728 Package cancellation]
    style CC728 fill:#8b5cf6
    CC732[732 Stock - SaleCancel]
    style CC732 fill:#3fb950
    CC728 --> CC732
    CC732 --> T733
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [732](REF-IDE-732.md) | Stock - Sale/Cancel | 2 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T733[733 Stock - Mouvement]
    style T733 fill:#58a6ff
    NONE[Aucun callee]
    T733 -.-> NONE
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
| Lignes de logique | 41 | Programme compact |
| Expressions | 15 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 41) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 0 ecran, 1 traitement)

- **Strategie** : 1 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| pv_stock_movements | Table WRITE (Database) | 1x | Schema + repository |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 14:02*
