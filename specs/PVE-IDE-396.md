# PVE IDE 396 - Report - Selection/Tempo

> **Analyse**: Phases 1-4 2026-02-03 19:56 -> 19:56 (10s) | Assemblage 19:56
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PVE |
| IDE Position | 396 |
| Nom Programme | Report - Selection/Tempo |
| Fichier source | `Prg_396.xml` |
| Dossier IDE | A |
| Taches | 5 (0 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Report - Selection/Tempo** assure la gestion complete de ce processus, accessible depuis [Report - Margin by Product (IDE 373)](PVE-IDE-373.md), [Report - Margin by Category (IDE 374)](PVE-IDE-374.md), [Report - Margin by Day (IDE 375)](PVE-IDE-375.md), [Report - Margin by Place (IDE 376)](PVE-IDE-376.md), [Report - Margin by Seller (IDE 377)](PVE-IDE-377.md), [Report - Net Margin by Product (IDE 378)](PVE-IDE-378.md), [Report - Revenue by Category (IDE 383)](PVE-IDE-383.md), [Report - Revenue by Place (IDE 384)](PVE-IDE-384.md), [Report - Revenue by Seller (IDE 385)](PVE-IDE-385.md), [Report - Revenue by Day (IDE 390)](PVE-IDE-390.md).

Le flux de traitement s'organise en **3 blocs fonctionnels** :

- **Traitement** (3 taches) : traitements metier divers
- **Consultation** (1 tache) : ecrans de recherche, selection et consultation
- **Calcul** (1 tache) : calculs de montants, stocks ou compteurs

**Donnees modifiees** : 1 tables en ecriture (update_table_codes_log).

**Logique metier** : 1 regles identifiees couvrant conditions metier.

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Consultation (1 tache)

- **396** - SELECTION **[[ECRAN]](#ecran-t1)**

#### Phase 2 : Calcul (1 tache)

- **396.1** - Selection compta

#### Phase 3 : Traitement (3 taches)

- **396.1.1** - Temp generation
- **396.1.1.1** - Temp generation
- **396.1.2** - Movements

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| update_table_codes_log | **W** (2 usages) |  |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Consultation (1 tache)

Ecrans de recherche et consultation.

---

#### <a id="t1"></a>396 - SELECTION [[ECRAN]](#ecran-t1)

**Role** : Selection par l'operateur : SELECTION.
**Ecran** : 318 x 268 DLU (MDI) | [Voir mockup](#ecran-t1)


### 3.2 Calcul (1 tache)

Calculs metier : montants, stocks, compteurs.

---

#### <a id="t2"></a>396.1 - Selection compta

**Role** : Selection par l'operateur : Selection compta.


### 3.3 Traitement (3 taches)

Traitements internes.

---

#### <a id="t3"></a>396.1.1 - Temp generation

**Role** : Traitement : Temp generation.

---

#### <a id="t4"></a>396.1.1.1 - Temp generation

**Role** : Traitement : Temp generation.

---

#### <a id="t5"></a>396.1.2 - Movements

**Role** : Traitement : Movements.


## 5. REGLES METIER

1 regles identifiees:

### Autres (1 regles)

#### <a id="rm-RM-001"></a>[RM-001] Traitement si P. D or C or P or L or V [F]='L',[AF] est renseigne

| Element | Detail |
|---------|--------|
| **Condition** | `P. D or C or P or L or V [F]='L'` |
| **Si vrai** | [AF]<>'' |
| **Si faux** | IF(P. D or C or P or L or V [F]='V',[AG]<>'','TRUE'LOG)) |
| **Variables** | F (P. D or C or P or L or V) |
| **Expression source** | Expression 8 : `IF(P. D or C or P or L or V [F]='L',[AF]<>'',IF(P. D or C or` |
| **Exemple** | Si P. D or C or P or L or V [F]='L' â†’ [AF]<>''. Sinon â†’ IF(P. D or C or P or L or V [F]='V',[AG]<>'','TRUE'LOG)) |

## 6. CONTEXTE

- **Appele par**: [Report - Margin by Product (IDE 373)](PVE-IDE-373.md), [Report - Margin by Category (IDE 374)](PVE-IDE-374.md), [Report - Margin by Day (IDE 375)](PVE-IDE-375.md), [Report - Margin by Place (IDE 376)](PVE-IDE-376.md), [Report - Margin by Seller (IDE 377)](PVE-IDE-377.md), [Report - Net Margin by Product (IDE 378)](PVE-IDE-378.md), [Report - Revenue by Category (IDE 383)](PVE-IDE-383.md), [Report - Revenue by Place (IDE 384)](PVE-IDE-384.md), [Report - Revenue by Seller (IDE 385)](PVE-IDE-385.md), [Report - Revenue by Day (IDE 390)](PVE-IDE-390.md)
- **Appelle**: 0 programmes | **Tables**: 7 (W:1 R:3 L:4) | **Taches**: 5 | **Expressions**: 11

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (5 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **396.1** | [**SELECTION** (396)](#t1) [mockup](#ecran-t1) | MDI | 318x268 | Consultation |
| **396.2** | [**Selection compta** (396.1)](#t2) | MDI | - | Calcul |
| **396.3** | [**Temp generation** (396.1.1)](#t3) | MDI | - | Traitement |
| 396.3.1 | [Temp generation (396.1.1.1)](#t4) | MDI | - | |
| 396.3.2 | [Movements (396.1.2)](#t5) | MDI | - | |

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

### Tables utilisees (7)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 379 | pv_customer_temp |  | DB | R |   |   | 1 |
| 403 | pv_sellers |  | DB |   |   | L | 1 |
| 413 | pv_tva |  | DB |   |   | L | 1 |
| 523 | synthese_garanties | Depots et garanties | TMP | R |   |   | 1 |
| 524 | update_table_codes_log |  | TMP |   | **W** |   | 2 |
| 534 | liste_des_caisses | Sessions de caisse | TMP |   |   | L | 1 |
| 762 | pv_mvt_stock_tempo | Table temporaire ecran | DB | R |   | L | 2 |

### Colonnes par table (2 / 4 tables avec colonnes identifiees)

<details>
<summary>Table 379 - pv_customer_temp (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P. Date mini | R | Date |
| B | P. Date Maxi | R | Date |
| C | P. Decimales | R | Numeric |
| D | P. Item selected | R | Logical |
| E | P. Total General | R | Numeric |
| F | P. D or C or P or L or V | R | Alpha |
| G | P. avec Cost | R | Logical |
| H | P. Total Cost | R | Numeric |
| I | P. Total Revenue HT | R | Numeric |
| J | P. Total Revenue TTC | R | Numeric |
| K | P. Total Revenue VAT | R | Numeric |
| L | V Product | R | Numeric |

</details>

<details>
<summary>Table 523 - synthese_garanties (R) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 524 - update_table_codes_log (**W**) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P(0) Refund | W | Logical |
| B | V Montant HT ou TTC | W | Numeric |
| C | V.Montant HT | W | Numeric |
| D | V.Montant TTC | W | Numeric |
| E | V.Montant VAT | W | Numeric |
| F | V.Montant prepaid HT ou TTC | W | Numeric |
| G | V.Montant prepaid HT | W | Numeric |
| H | V.Montant prepaid TTC | W | Numeric |
| I | V.Montant prepaid VAT | W | Numeric |

</details>

<details>
<summary>Table 762 - pv_mvt_stock_tempo (R/L) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (11)

Variables recues du programme appelant ([Report - Margin by Product (IDE 373)](PVE-IDE-373.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P. Date mini | Date | 1x parametre entrant |
| B | P. Date Maxi | Date | 1x parametre entrant |
| C | P. Decimales | Numeric | - |
| D | P. Item selected | Logical | - |
| E | P. Total General | Numeric | - |
| F | P. D or C or P or L or V | Alpha | 1x parametre entrant |
| G | P. avec Cost | Logical | - |
| H | P. Total Cost | Numeric | - |
| I | P. Total Revenue HT | Numeric | - |
| J | P. Total Revenue TTC | Numeric | - |
| K | P. Total Revenue VAT | Numeric | - |

### 11.2 Variables de session (1)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| L | V Product | Numeric | - |

## 12. EXPRESSIONS

**11 / 11 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCULATION | 1 | 0 |
| CAST_LOGIQUE | 2 | 5 |
| OTHER | 8 | 0 |

### 12.2 Expressions cles par type

#### CALCULATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 4 | `[O]*10^4+[P]*100+[Q]` | - |

#### CAST_LOGIQUE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 8 | `IF(P. D or C or P or L or V [F]='L',[AF]<>'',IF(P. D or C or P or L or V [F]='V',[AG]<>'','TRUE'LOG))` | [RM-001](#rm-RM-001) |
| CAST_LOGIQUE | 7 | `'TRUE'LOG` | - |

#### OTHER (8 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 9 | `[Q]` | - |
| OTHER | 6 | `[AH]` | - |
| OTHER | 11 | `P. Date Maxi [B]` | - |
| OTHER | 10 | `P. Date mini [A]` | - |
| OTHER | 2 | `[O]` | - |
| ... | | *+3 autres* | |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Report - Margin by Product (IDE 373)](PVE-IDE-373.md) -> **Report - Selection/Tempo (IDE 396)**

Main -> ... -> [Report - Margin by Category (IDE 374)](PVE-IDE-374.md) -> **Report - Selection/Tempo (IDE 396)**

Main -> ... -> [Report - Margin by Day (IDE 375)](PVE-IDE-375.md) -> **Report - Selection/Tempo (IDE 396)**

Main -> ... -> [Report - Margin by Place (IDE 376)](PVE-IDE-376.md) -> **Report - Selection/Tempo (IDE 396)**

Main -> ... -> [Report - Margin by Seller (IDE 377)](PVE-IDE-377.md) -> **Report - Selection/Tempo (IDE 396)**

Main -> ... -> [Report - Net Margin by Product (IDE 378)](PVE-IDE-378.md) -> **Report - Selection/Tempo (IDE 396)**

Main -> ... -> [Report - Revenue by Category (IDE 383)](PVE-IDE-383.md) -> **Report - Selection/Tempo (IDE 396)**

Main -> ... -> [Report - Revenue by Place (IDE 384)](PVE-IDE-384.md) -> **Report - Selection/Tempo (IDE 396)**

Main -> ... -> [Report - Revenue by Seller (IDE 385)](PVE-IDE-385.md) -> **Report - Selection/Tempo (IDE 396)**

Main -> ... -> [Report - Revenue by Day (IDE 390)](PVE-IDE-390.md) -> **Report - Selection/Tempo (IDE 396)**

```mermaid
graph LR
    T396[396 Report - Selection...]
    style T396 fill:#58a6ff
    CC376[376 Report - Margin by...]
    style CC376 fill:#8b5cf6
    CC377[377 Report - Margin by...]
    style CC377 fill:#8b5cf6
    CC375[375 Report - Margin by...]
    style CC375 fill:#8b5cf6
    CC373[373 Report - Margin by...]
    style CC373 fill:#8b5cf6
    CC374[374 Report - Margin by...]
    style CC374 fill:#8b5cf6
    CC373 --> T396
    CC374 --> T396
    CC375 --> T396
    CC376 --> T396
    CC377 --> T396
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [373](PVE-IDE-373.md) | Report - Margin by Product | 1 |
| [374](PVE-IDE-374.md) | Report - Margin by Category | 1 |
| [375](PVE-IDE-375.md) | Report - Margin by Day | 1 |
| [376](PVE-IDE-376.md) | Report - Margin by Place | 1 |
| [377](PVE-IDE-377.md) | Report - Margin by Seller | 1 |
| [378](PVE-IDE-378.md) | Report - Net Margin by Product | 1 |
| [383](PVE-IDE-383.md) | Report - Revenue by Category | 1 |
| [384](PVE-IDE-384.md) | Report - Revenue by Place | 1 |
| [385](PVE-IDE-385.md) | Report - Revenue by Seller | 1 |
| [390](PVE-IDE-390.md) | Report - Revenue by Day | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T396[396 Report - Selection...]
    style T396 fill:#58a6ff
    NONE[Aucun callee]
    T396 -.-> NONE
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
| Lignes de logique | 228 | Taille moyenne |
| Expressions | 11 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0.4% (1 / 228) | Code sain |
| Regles metier | 1 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Consultation (1 tache: 1 ecran, 0 traitement)

- **Strategie** : Composants de recherche/selection en modales.
- 1 ecran : SELECTION

#### Calcul (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Services de calcul purs (Domain Services).
- Migrer la logique de calcul (stock, compteurs, montants)

#### Traitement (3 taches: 0 ecran, 3 traitements)

- **Strategie** : 3 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| update_table_codes_log | Table WRITE (Temp) | 2x | Schema + repository |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 19:56*
