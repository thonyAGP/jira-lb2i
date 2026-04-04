# REF IDE 732 - Stock - Sale/Cancel

> **Analyse**: Phases 1-4 2026-02-03 14:01 -> 14:01 (16s) | Assemblage 14:01
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | REF |
| IDE Position | 732 |
| Nom Programme | Stock - Sale/Cancel |
| Fichier source | `Prg_732.xml` |
| Dossier IDE | General |
| Taches | 3 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 2 |

## 2. DESCRIPTION FONCTIONNELLE

**Stock - Sale/Cancel** assure la gestion complete de ce processus, accessible depuis [Package cancellation (IDE 728)](REF-IDE-728.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (3 taches) : traitements metier divers

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (3 taches)

Traitements internes.

---

#### <a id="t2"></a>732 - Action Cancel Exit

**Role** : Traitement : Action Cancel Exit.
**Delegue a** : [Trace Modification package (IDE 734)](REF-IDE-734.md)

---

#### <a id="t11"></a>732.1 - Product

**Role** : Traitement : Product.
**Variables liees** : A (Pi. Product)
**Delegue a** : [Trace Modification package (IDE 734)](REF-IDE-734.md)

---

#### <a id="t12"></a>732.2 - Package detail

**Role** : Traitement : Package detail.
**Variables liees** : C (P. Package ID OUT)
**Delegue a** : [Trace Modification package (IDE 734)](REF-IDE-734.md)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Package cancellation (IDE 728)](REF-IDE-728.md)
- **Appelle**: 2 programmes | **Tables**: 2 (W:0 R:1 L:1) | **Taches**: 3 | **Expressions**: 1

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (3 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **732.1** | [**Action Cancel Exit** (732)](#t2) | MDI | - | Traitement |
| 732.1.1 | [Product (732.1)](#t11) | MDI | - | |
| 732.1.2 | [Package detail (732.2)](#t12) | MDI | - | |

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

### Tables utilisees (2)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 399 | pv_package_price |  | DB | R |   |   | 2 |
| 737 | pv_package_detail |  | DB |   |   | L | 2 |

### Colonnes par table (2 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 399 - pv_package_price (R) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | V Quantity to destock | R | Numeric |
| B | v.Stock géré par détail ? | R | Logical |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (8)

Variables recues du programme appelant ([Package cancellation (IDE 728)](REF-IDE-728.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | Pi. Product | Numeric | - |
| B | Pi. Customer | Numeric | - |
| C | P. Package ID OUT | Numeric | - |
| D | P. Movement | Numeric | - |
| E | P. In/Out | Alpha | - |
| F | P. Quantity sale | Numeric | - |
| G | P. Discount sale | Numeric | - |
| H | P. TVA sale | Numeric | - |

### 11.2 Variables de session (1)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| I | v.Article géré en stock ? | Logical | 1x session |

## 12. EXPRESSIONS

**1 / 1 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| NEGATION | 1 | 0 |

### 12.2 Expressions cles par type

#### NEGATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| NEGATION | 1 | `NOT VG50 OR v.Article géré en stock ? [I]` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Package cancellation (IDE 728)](REF-IDE-728.md) -> **Stock - Sale/Cancel (IDE 732)**

```mermaid
graph LR
    T732[732 Stock - SaleCancel]
    style T732 fill:#58a6ff
    CC728[728 Package cancellation]
    style CC728 fill:#8b5cf6
    CC728 --> T732
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [728](REF-IDE-728.md) | Package cancellation | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T732[732 Stock - SaleCancel]
    style T732 fill:#58a6ff
    C733[733 Stock - Mouvement]
    T732 --> C733
    style C733 fill:#3fb950
    C734[734 Trace Modification...]
    T732 --> C734
    style C734 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [733](REF-IDE-733.md) | Stock - Mouvement | 2 | Calcul de donnees |
| [734](REF-IDE-734.md) | Trace Modification package | 2 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 102 | Programme compact |
| Expressions | 1 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 2 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 102) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (3 taches: 0 ecran, 3 traitements)

- **Strategie** : 3 service(s) backend injectable(s) (Domain Services).
- 2 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| [Trace Modification package (IDE 734)](REF-IDE-734.md) | Sous-programme | 2x | Haute - Sous-programme |
| [Stock - Mouvement (IDE 733)](REF-IDE-733.md) | Sous-programme | 2x | Haute - Calcul de donnees |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 14:01*
