# PVE IDE 368 - Report - Selection/Tempo_V3

> **Analyse**: Phases 1-4 2026-02-03 19:48 -> 19:48 (11s) | Assemblage 19:48
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PVE |
| IDE Position | 368 |
| Nom Programme | Report - Selection/Tempo_V3 |
| Fichier source | `Prg_368.xml` |
| Dossier IDE | A |
| Taches | 5 (0 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 0 |
| :warning: Statut | **ORPHELIN_POTENTIEL** |

## 2. DESCRIPTION FONCTIONNELLE

**Report - Selection/Tempo_V3** assure la gestion complete de ce processus.

Le flux de traitement s'organise en **3 blocs fonctionnels** :

- **Traitement** (3 taches) : traitements metier divers
- **Consultation** (1 tache) : ecrans de recherche, selection et consultation
- **Calcul** (1 tache) : calculs de montants, stocks ou compteurs

**Donnees modifiees** : 1 tables en ecriture (Table_1461).

**Logique metier** : 1 regles identifiees couvrant conditions metier.

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Consultation (1 tache)

- **368** - SELECTION **[[ECRAN]](#ecran-t1)**

#### Phase 2 : Calcul (1 tache)

- **368.1** - Selection compta

#### Phase 3 : Traitement (3 taches)

- **368.1.1** - Temp generation
- **368.1.1.1** - Temp generation
- **368.1.2** - Movements

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| Table_1461 | **W** (2 usages) |  |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Consultation (1 tache)

Ecrans de recherche et consultation.

---

#### <a id="t1"></a>368 - SELECTION [[ECRAN]](#ecran-t1)

**Role** : Selection par l'operateur : SELECTION.
**Ecran** : 278 x 320 DLU (MDI) | [Voir mockup](#ecran-t1)


### 3.2 Calcul (1 tache)

Calculs metier : montants, stocks, compteurs.

---

#### <a id="t2"></a>368.1 - Selection compta

**Role** : Selection par l'operateur : Selection compta.


### 3.3 Traitement (3 taches)

Traitements internes.

---

#### <a id="t3"></a>368.1.1 - Temp generation

**Role** : Traitement : Temp generation.

---

#### <a id="t4"></a>368.1.1.1 - Temp generation

**Role** : Traitement : Temp generation.

---

#### <a id="t5"></a>368.1.2 - Movements

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

- **Appele par**: (aucun)
- **Appelle**: 0 programmes | **Tables**: 7 (W:1 R:3 L:4) | **Taches**: 5 | **Expressions**: 11

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (5 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **368.1** | [**SELECTION** (368)](#t1) [mockup](#ecran-t1) | MDI | 278x320 | Consultation |
| **368.2** | [**Selection compta** (368.1)](#t2) | MDI | - | Calcul |
| **368.3** | [**Temp generation** (368.1.1)](#t3) | MDI | - | Traitement |
| 368.3.1 | [Temp generation (368.1.1.1)](#t4) | MDI | - | |
| 368.3.2 | [Movements (368.1.2)](#t5) | MDI | - | |

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
| 534 | liste_des_caisses | Sessions de caisse | TMP |   |   | L | 1 |
| 762 | pv_mvt_stock_tempo | Table temporaire ecran | DB | R |   | L | 2 |
| 1461 | Table_1461 |  | MEM |   | **W** |   | 2 |

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
<summary>Table 762 - pv_mvt_stock_tempo (R/L) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 1461 - Table_1461 (**W**) - 2 usages</summary>

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

## 11. VARIABLES

### 11.1 Parametres entrants (11)

Variables recues en parametre.

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

**Chemin**: (pas de callers directs)

```mermaid
graph LR
    T368[368 Report - Selection...]
    style T368 fill:#58a6ff
    NONE[Aucun caller]
    NONE -.-> T368
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| - | (aucun) | - |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T368[368 Report - Selection...]
    style T368 fill:#58a6ff
    NONE[Aucun callee]
    T368 -.-> NONE
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
| Table_1461 | Table WRITE (Memory) | 2x | Schema + repository |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 19:48*
