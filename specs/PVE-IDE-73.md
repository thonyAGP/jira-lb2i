# PVE IDE 73 - Report - Revenue by product

> **Analyse**: Phases 1-4 2026-02-03 09:09 -> 09:09 (27s) | Assemblage 09:09
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PVE |
| IDE Position | 73 |
| Nom Programme | Report - Revenue by product |
| Fichier source | `Prg_73.xml` |
| Domaine metier | General |
| Taches | 8 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 3 |

## 2. DESCRIPTION FONCTIONNELLE

**Report - Revenue by product** assure la gestion complete de ce processus, accessible depuis [Menu Reports (IDE 182)](PVE-IDE-182.md).

Le flux de traitement s'organise en **2 blocs fonctionnels** :

- **Traitement** (5 taches) : traitements metier divers
- **Impression** (3 taches) : generation de tickets et documents

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (5 taches)

- **73** - Report - Revenue by product **[[ECRAN]](#ecran-t1)**
- **73.1.1.1** - Lines
- **73.1.1.1.1** - Total
- **73.1.1.1.2.1** - Refund
- **73.1.1.2** - Budget

Delegue a : [Get Temp Files (IDE 46)](PVE-IDE-46.md), [IoDel fichier CSV (IDE 56)](PVE-IDE-56.md)

#### Phase 2 : Impression (3 taches)

- **73.1** - Print
- **73.1.1** - EDITION
- **73.1.1.1.2** - Print Totaux

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (5 taches)

Traitements internes.

---

#### <a id="t1"></a>73 - Report - Revenue by product [[ECRAN]](#ecran-t1)

**Role** : Traitement : Report - Revenue by product.
**Ecran** : 312 x 57 DLU (MDI) | [Voir mockup](#ecran-t1)

<details>
<summary>4 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [73.1.1.1](#t4) | Lines | Traitement |
| [73.1.1.1.1](#t5) | Total | Traitement |
| [73.1.1.1.2.1](#t7) | Refund | Traitement |
| [73.1.1.2](#t8) | Budget | Traitement |

</details>
**Delegue a** : [Get Temp Files (IDE 46)](PVE-IDE-46.md), [IoDel fichier CSV (IDE 56)](PVE-IDE-56.md), [Report - Selection/By Product (IDE 74)](PVE-IDE-74.md)

---

#### <a id="t4"></a>73.1.1.1 - Lines

**Role** : Traitement : Lines.
**Delegue a** : [Get Temp Files (IDE 46)](PVE-IDE-46.md), [IoDel fichier CSV (IDE 56)](PVE-IDE-56.md)

---

#### <a id="t5"></a>73.1.1.1.1 - Total

**Role** : Traitement : Total.
**Delegue a** : [Get Temp Files (IDE 46)](PVE-IDE-46.md), [IoDel fichier CSV (IDE 56)](PVE-IDE-56.md)

---

#### <a id="t7"></a>73.1.1.1.2.1 - Refund

**Role** : Traitement : Refund.
**Delegue a** : [Get Temp Files (IDE 46)](PVE-IDE-46.md), [IoDel fichier CSV (IDE 56)](PVE-IDE-56.md)

---

#### <a id="t8"></a>73.1.1.2 - Budget

**Role** : Consultation/chargement : Budget.
**Delegue a** : [Get Temp Files (IDE 46)](PVE-IDE-46.md), [IoDel fichier CSV (IDE 56)](PVE-IDE-56.md)


### 3.2 Impression (3 taches)

Generation des documents et tickets.

---

#### <a id="t2"></a>73.1 - Print

**Role** : Generation du document : Print.

---

#### <a id="t3"></a>73.1.1 - EDITION

**Role** : Generation du document : EDITION.

---

#### <a id="t6"></a>73.1.1.1.2 - Print Totaux

**Role** : Generation du document : Print Totaux.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Menu Reports (IDE 182)](PVE-IDE-182.md)
- **Appelle**: 3 programmes | **Tables**: 5 (W:0 R:3 L:3) | **Taches**: 8 | **Expressions**: 6

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (8 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **73.1** | [**Report - Revenue by product** (73)](#t1) [mockup](#ecran-t1) | MDI | 312x57 | Traitement |
| 73.1.1 | [Lines (73.1.1.1)](#t4) | MDI | - | |
| 73.1.2 | [Total (73.1.1.1.1)](#t5) | MDI | - | |
| 73.1.3 | [Refund (73.1.1.1.2.1)](#t7) | MDI | - | |
| 73.1.4 | [Budget (73.1.1.2)](#t8) | - | - | |
| **73.2** | [**Print** (73.1)](#t2) | MDI | - | Impression |
| 73.2.1 | [EDITION (73.1.1)](#t3) | MDI | - | |
| 73.2.2 | [Print Totaux (73.1.1.1.2)](#t6) | MDI | - | |

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

### Tables utilisees (5)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 376 | pv_classification |  | DB | R |   |   | 1 |
| 379 | pv_customer_temp |  | DB | R |   |   | 1 |
| 403 | pv_sellers |  | DB |   |   | L | 1 |
| 413 | pv_tva |  | DB |   |   | L | 1 |
| 1461 | Table_1461 |  | MEM | R |   | L | 3 |

### Colonnes par table (2 / 3 tables avec colonnes identifiees)

<details>
<summary>Table 376 - pv_classification (R) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 379 - pv_customer_temp (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | Total Product | R | Numeric |
| B | Total Product HT | R | Numeric |
| C | Total Product TTC | R | Numeric |
| D | Total Product TvA | R | Numeric |
| E | Total Product Prepaid HT | R | Numeric |
| F | Total Product Prepaid TTC | R | Numeric |
| G | Total Product Prepaid TvA | R | Numeric |
| H | Total Quantity Prepaid | R | Numeric |
| I | Total General HT | R | Numeric |
| J | Total General TTC | R | Numeric |
| K | Total General TvA | R | Numeric |
| L | Total Quantity | R | Numeric |
| M | v.Total Dispatch | R | Numeric |

</details>

<details>
<summary>Table 1461 - Table_1461 (R/L) - 3 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | Total Location | R | Numeric |
| B | Total Location HT | R | Numeric |
| C | Total Location TTC | R | Numeric |
| D | Total Location TVA | R | Numeric |
| E | Total General | R | Numeric |
| F | Total General HT | R | Numeric |
| G | Total General TTC | R | Numeric |
| H | Total General TVA | R | Numeric |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (12)

Variables recues du programme appelant ([Menu Reports (IDE 182)](PVE-IDE-182.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P. Village Name | Alpha | - |
| B | P. Currency | Alpha | - |
| C | P. Masque | Alpha | - |
| D | P. Masque sans Z | Alpha | - |
| E | P. Decimales | Numeric | - |
| F | P. Pèriode contrôle HD | Logical | - |
| G | P Période nombre JH | Numeric | - |
| H | P Jours période | Numeric | - |
| I | P Date mini | Date | - |
| J | P Date maxi | Date | 1x parametre entrant |
| K | P Catégorie Mini | Numeric | - |
| L | P Catégorie Maxi | Numeric | - |

### 11.2 Variables de session (1)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| O | v.NomFichierPdf | Alpha | 1x session |

### 11.3 Autres (2)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| M | Param Mode Global / Détail | Alpha | - |
| N | S | Alpha | 1x refs |

## 12. EXPRESSIONS

**6 / 6 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONDITION | 1 | 0 |
| CONSTANTE | 1 | 0 |
| CONCATENATION | 1 | 0 |
| REFERENCE_VG | 1 | 0 |
| NEGATION | 1 | 0 |
| STRING | 1 | 0 |

### 12.2 Expressions cles par type

#### CONDITION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 1 | `P Date maxi [J]<>'00/00/0000'DATE` | - |

#### CONSTANTE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 2 | `'D'` | - |

#### CONCATENATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 4 | `Translate ('%club_exportdata%')&Trim (GetParam ('VILLAGECODE'))&Trim (GetParam ('SERVICE'))&'_REVENUE_BY_PRODUCT_'&DStr (Date(),'YYYYMMDD')&'_'&TStr (Time(),'HHMMSS')&'.Pdf'` | - |

#### REFERENCE_VG (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 3 | `VG37` | - |

#### NEGATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| NEGATION | 6 | `NOT (GetParam ('Output')='Printer')` | - |

#### STRING (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| STRING | 5 | `FileDelete (Trim(v.NomFichierPdf [O]))` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Menu Reports (IDE 182)](PVE-IDE-182.md) -> **Report - Revenue by product (IDE 73)**

```mermaid
graph LR
    T73[73 Report - Revenue by...]
    style T73 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC143[143 START]
    style CC143 fill:#f59e0b
    CC439[439 Menu]
    style CC439 fill:#f59e0b
    CC420[420 Menu==V4___]
    style CC420 fill:#f59e0b
    CC185[185 Menu]
    style CC185 fill:#f59e0b
    CC353[353 Menu==V4]
    style CC353 fill:#f59e0b
    CC182[182 Menu Reports]
    style CC182 fill:#3fb950
    CC185 --> CC182
    CC353 --> CC182
    CC420 --> CC182
    CC439 --> CC182
    CC143 --> CC185
    CC143 --> CC353
    CC143 --> CC420
    CC143 --> CC439
    CC1 --> CC143
    CC182 --> T73
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [182](PVE-IDE-182.md) | Menu Reports | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T73[73 Report - Revenue by...]
    style T73 fill:#58a6ff
    C46[46 Get Temp Files]
    T73 --> C46
    style C46 fill:#3fb950
    C56[56 IoDel fichier CSV]
    T73 --> C56
    style C56 fill:#3fb950
    C74[74 Report - SelectionB...]
    T73 --> C74
    style C74 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [46](PVE-IDE-46.md) | Get Temp Files | 1 | Recuperation donnees |
| [56](PVE-IDE-56.md) | IoDel fichier CSV | 1 | Sous-programme |
| [74](PVE-IDE-74.md) | Report - Selection/By Product | 1 | Selection/consultation |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 229 | Taille moyenne |
| Expressions | 6 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 3 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 229) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (5 taches: 1 ecran, 4 traitements)

- **Strategie** : Orchestrateur avec 1 ecrans (Razor/React) et 4 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 3 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Impression (3 taches: 0 ecran, 3 traitements)

- **Strategie** : Templates HTML -> PDF via wkhtmltopdf ou Puppeteer.
- `PrintService` injectable avec choix imprimante

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| [Report - Selection/By Product (IDE 74)](PVE-IDE-74.md) | Sous-programme | 1x | Normale - Selection/consultation |
| [IoDel fichier CSV (IDE 56)](PVE-IDE-56.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Get Temp Files (IDE 46)](PVE-IDE-46.md) | Sous-programme | 1x | Normale - Recuperation donnees |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 09:09*
