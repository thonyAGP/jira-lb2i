# PVE IDE 229 - Trace Modification package

> **Analyse**: Phases 1-4 2026-02-03 19:03 -> 19:04 (17s) | Assemblage 19:04
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PVE |
| IDE Position | 229 |
| Nom Programme | Trace Modification package |
| Fichier source | `Prg_229.xml` |
| Dossier IDE | Packages |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Trace Modification package** assure la gestion complete de ce processus, accessible depuis [Package setup (IDE 220)](PVE-IDE-220.md), [Package setup (IDE 367)](PVE-IDE-367.md), [Import - ProductsIO(Admin) (IDE 132)](PVE-IDE-132.md), [Menu Stocks Management (IDE 179)](PVE-IDE-179.md), [Stock - Sale/Cancel (IDE 233)](PVE-IDE-233.md), [Input Movement stock (IDE 237)](PVE-IDE-237.md), [Global Items (IDE 6)](PVE-IDE-6.md), [Export/Import Items (IDE 140)](PVE-IDE-140.md), [START (IDE 143)](PVE-IDE-143.md), [Batch validation inventory (IDE 244)](PVE-IDE-244.md), [Import - Products (IDE 445)](PVE-IDE-445.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>229 - Trace Modification package

**Role** : Traitement : Trace Modification package.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Package setup (IDE 220)](PVE-IDE-220.md), [Package setup (IDE 367)](PVE-IDE-367.md), [Import - ProductsIO(Admin) (IDE 132)](PVE-IDE-132.md), [Menu Stocks Management (IDE 179)](PVE-IDE-179.md), [Stock - Sale/Cancel (IDE 233)](PVE-IDE-233.md), [Input Movement stock (IDE 237)](PVE-IDE-237.md), [Global Items (IDE 6)](PVE-IDE-6.md), [Export/Import Items (IDE 140)](PVE-IDE-140.md), [START (IDE 143)](PVE-IDE-143.md), [Batch validation inventory (IDE 244)](PVE-IDE-244.md), [Import - Products (IDE 445)](PVE-IDE-445.md)
- **Appelle**: 0 programmes | **Tables**: 2 (W:0 R:1 L:1) | **Taches**: 1 | **Expressions**: 10

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **229.1** | [**Trace Modification package** (229)](#t1) | - | - | Traitement |

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
| 403 | pv_sellers |  | DB | R |   |   | 1 |
| 798 | type_article | Articles et stock | DB |   |   | L | 1 |

### Colonnes par table (2 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 403 - pv_sellers (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P.Type modif | R | Alpha |
| B | P.Cat new | R | Numeric |
| C | P.Subcat new | R | Numeric |
| D | P.Prod_id new | R | Numeric |
| E | P.Ordre new | R | Numeric |
| F | P.Label new | R | Alpha |
| G | P.Number_days new | R | Numeric |
| H | P.Prix de vente new | R | Numeric |
| I | P.block free new | R | Logical |
| J | P.block discount new | R | Logical |
| K | P.Tampon new | R | Alpha |
| L | P.Service new | R | Alpha |
| M | P.Code article new | R | Alpha |
| N | P.Prix achat new | R | Numeric |
| O | P.Art non gere en stock new | R | Logical |
| P | P.Art_qte_en_stock new | R | Numeric |
| Q | P.Art unit vente new | R | Alpha |
| R | P.Art TVA new | R | Numeric |
| S | P.Art volume vendu new | R | Numeric |
| T | P.Art decimales new | R | Numeric |
| U | P.Art volume achat new | R | Numeric |
| V | P.Art prix achat bottle new | R | Numeric |
| W | P.Art logique 1 new | R | Logical |
| X | P.Art logique 2 new | R | Logical |
| Y | P.Art actif | R | Unicode |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (25)

Variables recues du programme appelant ([Package setup (IDE 220)](PVE-IDE-220.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P.Type modif | Alpha | [229](#t1) |
| B | P.Cat new | Numeric | 1x parametre entrant |
| C | P.Subcat new | Numeric | 1x parametre entrant |
| D | P.Prod_id new | Numeric | 1x parametre entrant |
| E | P.Ordre new | Numeric | 1x parametre entrant |
| F | P.Label new | Alpha | 1x parametre entrant |
| G | P.Number_days new | Numeric | 1x parametre entrant |
| H | P.Prix de vente new | Numeric | 1x parametre entrant |
| I | P.block free new | Logical | 1x parametre entrant |
| J | P.block discount new | Logical | 1x parametre entrant |
| K | P.Tampon new | Alpha | 1x parametre entrant |
| L | P.Service new | Alpha | 1x parametre entrant |
| M | P.Code article new | Alpha | 1x parametre entrant |
| N | P.Prix achat new | Numeric | 1x parametre entrant |
| O | P.Art non gere en stock new | Logical | - |
| P | P.Art_qte_en_stock new | Numeric | 1x parametre entrant |
| Q | P.Art unit vente new | Alpha | 1x parametre entrant |
| R | P.Art TVA new | Numeric | 1x parametre entrant |
| S | P.Art volume vendu new | Numeric | 1x parametre entrant |
| T | P.Art decimales new | Numeric | 1x parametre entrant |
| U | P.Art volume achat new | Numeric | 1x parametre entrant |
| V | P.Art prix achat bottle new | Numeric | - |
| W | P.Art logique 1 new | Logical | 1x parametre entrant |
| X | P.Art logique 2 new | Logical | 1x parametre entrant |
| Y | P.Art actif | Unicode | 1x parametre entrant |

<details>
<summary>Toutes les 25 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| P0 | **A** | P.Type modif | Alpha |
| P0 | **B** | P.Cat new | Numeric |
| P0 | **C** | P.Subcat new | Numeric |
| P0 | **D** | P.Prod_id new | Numeric |
| P0 | **E** | P.Ordre new | Numeric |
| P0 | **F** | P.Label new | Alpha |
| P0 | **G** | P.Number_days new | Numeric |
| P0 | **H** | P.Prix de vente new | Numeric |
| P0 | **I** | P.block free new | Logical |
| P0 | **J** | P.block discount new | Logical |
| P0 | **K** | P.Tampon new | Alpha |
| P0 | **L** | P.Service new | Alpha |
| P0 | **M** | P.Code article new | Alpha |
| P0 | **N** | P.Prix achat new | Numeric |
| P0 | **O** | P.Art non gere en stock new | Logical |
| P0 | **P** | P.Art_qte_en_stock new | Numeric |
| P0 | **Q** | P.Art unit vente new | Alpha |
| P0 | **R** | P.Art TVA new | Numeric |
| P0 | **S** | P.Art volume vendu new | Numeric |
| P0 | **T** | P.Art decimales new | Numeric |
| P0 | **U** | P.Art volume achat new | Numeric |
| P0 | **V** | P.Art prix achat bottle new | Numeric |
| P0 | **W** | P.Art logique 1 new | Logical |
| P0 | **X** | P.Art logique 2 new | Logical |
| P0 | **Y** | P.Art actif | Unicode |

</details>

## 12. EXPRESSIONS

**10 / 10 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| DATE | 1 | 0 |
| OTHER | 6 | 0 |
| REFERENCE_VG | 1 | 0 |
| FORMAT | 2 | 0 |

### 12.2 Expressions cles par type

#### DATE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| DATE | 6 | `Date()` | - |

#### OTHER (6 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 4 | `P.Subcat new [C]` | - |
| OTHER | 5 | `P.Prod_id new [D]` | - |
| OTHER | 7 | `Time()` | - |
| OTHER | 1 | `GetParam('SERVICE')` | - |
| OTHER | 2 | `P.Type modif [A]` | - |
| ... | | *+1 autres* | |

#### REFERENCE_VG (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 8 | `VG1` | - |

#### FORMAT (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| FORMAT | 10 | `Trim(Str([AD],'2P0'))&';'&
Trim([AE])&';'&
Trim(Str([AF],'3.1'))&';'&
Trim(Str([AG],'N12.3C'))&';'&
Trim(IF([AH],'O','N'))&';'&
Trim(IF([AI],'O','N'))&';'&
Trim([AJ])&';'&
Trim([Z])&';'&
Trim([AK])&';'&
Trim(Str([AL],'N12.3C'))&';'&
Trim(IF([AM],'O','N'))&';'&
Trim(Str([AN],'N9.3'))&';'&
Trim([AO])&';'&
Trim(Str([AP],'#2.#'))&';'&
Trim(Str([AQ],'6.6'))&';'&
Trim(Str([AR],'#'))&';'&
Trim(Str([AS],'6.6'))&';'&
Trim(Str([AT],'N12.3C'))&';'&
Trim(IF([AU],'O','N'))&';'&
Trim(IF([AV],'O','N'))&';'&
IF([AW]='O','O','N')` | - |
| FORMAT | 9 | `Trim(Str(P.Ordre new [E],'2P0'))&';'&Trim(P.Label new [F])&';'&Trim(Str(P.Number_days new [G],'3.1'))&';'&Trim(Str(P.Prix de vente new [H],'N12.3C'))&';'&Trim(IF(P.block free new [I],'O','N'))&';'&Trim(IF(P.block discount new [J],'O','N'))&';'&Trim(P.Tampon new [K])&';'&Trim(P.Service new [L])&';'&Trim(P.Code article new [M])&';'&Trim(Str(P.Prix achat new [N],'N12.3C'))&';'&Trim(IF(P.Art non gere en stoc... [O],'O','N'))&';'&Trim(Str(P.Art_qte_en_stock new [P],'N9.3'))&';'&Trim(P.Art unit vente new [Q])&';'&Trim(Str(P.Art TVA new [R],'#2.#'))&';'&Trim(Str(P.Art volume vendu new [S],'6.6'))&';'&Trim(Str(P.Art decimales new [T],'#'))&';'&Trim(Str(P.Art volume achat new [U],'6.6'))&';'&Trim(Str(P.Art prix achat bottl... [V],'N12.3C'))&';'&Trim(IF(P.Art logique 1 new [W],'O','N'))&';'&Trim(IF(P.Art logique 2 new [X],'O','N'))&';'&IF(P.Art actif [Y]='O','O','N')` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Package setup (IDE 220)](PVE-IDE-220.md) -> **Trace Modification package (IDE 229)**

Main -> ... -> [Package setup (IDE 367)](PVE-IDE-367.md) -> **Trace Modification package (IDE 229)**

Main -> ... -> [Import - ProductsIO(Admin) (IDE 132)](PVE-IDE-132.md) -> **Trace Modification package (IDE 229)**

Main -> ... -> [Menu Stocks Management (IDE 179)](PVE-IDE-179.md) -> **Trace Modification package (IDE 229)**

Main -> ... -> [Stock - Sale/Cancel (IDE 233)](PVE-IDE-233.md) -> **Trace Modification package (IDE 229)**

Main -> ... -> [Input Movement stock (IDE 237)](PVE-IDE-237.md) -> **Trace Modification package (IDE 229)**

Main -> ... -> [Global Items (IDE 6)](PVE-IDE-6.md) -> **Trace Modification package (IDE 229)**

Main -> ... -> [Export/Import Items (IDE 140)](PVE-IDE-140.md) -> **Trace Modification package (IDE 229)**

Main -> ... -> [START (IDE 143)](PVE-IDE-143.md) -> **Trace Modification package (IDE 229)**

Main -> ... -> [Batch validation inventory (IDE 244)](PVE-IDE-244.md) -> **Trace Modification package (IDE 229)**

Main -> ... -> [Import - Products (IDE 445)](PVE-IDE-445.md) -> **Trace Modification package (IDE 229)**

```mermaid
graph LR
    T229[229 Trace Modification...]
    style T229 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC439[439 Menu]
    style CC439 fill:#8b5cf6
    CC185[185 Menu]
    style CC185 fill:#8b5cf6
    CC420[420 Menu==V4___]
    style CC420 fill:#8b5cf6
    CC353[353 Menu==V4]
    style CC353 fill:#8b5cf6
    CC178[178 Menu Administration]
    style CC178 fill:#8b5cf6
    CC132[132 Import - ProductsI...]
    style CC132 fill:#3fb950
    CC6[6 Global Items]
    style CC6 fill:#3fb950
    CC179[179 Menu Stocks Manage...]
    style CC179 fill:#3fb950
    CC143[143 START]
    style CC143 fill:#3fb950
    CC140[140 ExportImport Items]
    style CC140 fill:#3fb950
    CC178 --> CC6
    CC1 --> CC6
    CC185 --> CC6
    CC353 --> CC6
    CC420 --> CC6
    CC439 --> CC6
    CC178 --> CC132
    CC1 --> CC132
    CC185 --> CC132
    CC353 --> CC132
    CC420 --> CC132
    CC439 --> CC132
    CC178 --> CC140
    CC1 --> CC140
    CC185 --> CC140
    CC353 --> CC140
    CC420 --> CC140
    CC439 --> CC140
    CC178 --> CC143
    CC1 --> CC143
    CC185 --> CC143
    CC353 --> CC143
    CC420 --> CC143
    CC439 --> CC143
    CC178 --> CC179
    CC1 --> CC179
    CC185 --> CC179
    CC353 --> CC179
    CC420 --> CC179
    CC439 --> CC179
    CC6 --> T229
    CC132 --> T229
    CC140 --> T229
    CC143 --> T229
    CC179 --> T229
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [220](PVE-IDE-220.md) | Package setup | 10 |
| [367](PVE-IDE-367.md) | Package setup | 10 |
| [132](PVE-IDE-132.md) | Import - ProductsIO(Admin) | 2 |
| [179](PVE-IDE-179.md) | Menu Stocks Management | 2 |
| [233](PVE-IDE-233.md) | Stock - Sale/Cancel | 2 |
| [237](PVE-IDE-237.md) | Input Movement stock | 2 |
| [6](PVE-IDE-6.md) | Global Items | 1 |
| [140](PVE-IDE-140.md) | Export/Import Items | 1 |
| [143](PVE-IDE-143.md) | START | 1 |
| [244](PVE-IDE-244.md) | Batch validation inventory | 1 |
| [445](PVE-IDE-445.md) | Import - Products | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T229[229 Trace Modification...]
    style T229 fill:#58a6ff
    NONE[Aucun callee]
    T229 -.-> NONE
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
| Lignes de logique | 65 | Programme compact |
| Expressions | 10 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 65) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 0 ecran, 1 traitement)

- **Strategie** : 1 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 19:04*
