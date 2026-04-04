# PVE IDE 65 - Export Insurance

> **Analyse**: Phases 1-4 2026-02-03 09:04 -> 09:05 (21s) | Assemblage 09:05
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PVE |
| IDE Position | 65 |
| Nom Programme | Export Insurance |
| Fichier source | `Prg_65.xml` |
| Domaine metier | General |
| Taches | 5 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 1 |

## 2. DESCRIPTION FONCTIONNELLE

**Export Insurance** assure la gestion complete de ce processus, accessible depuis [Menu Reports (IDE 182)](PVE-IDE-182.md).

Le flux de traitement s'organise en **3 blocs fonctionnels** :

- **Traitement** (3 taches) : traitements metier divers
- **Calcul** (1 tache) : calculs de montants, stocks ou compteurs
- **Consultation** (1 tache) : ecrans de recherche, selection et consultation

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (3 taches)

- **65** - Export Insurance **[[ECRAN]](#ecran-t1)**
- **65.2** - Export SQL
- **65.3** - Export SQL

Delegue a : [Get Temp Files (IDE 46)](PVE-IDE-46.md)

#### Phase 2 : Consultation (1 tache)

- **65.1** - SELECTION **[[ECRAN]](#ecran-t2)**

Delegue a : [Get Temp Files (IDE 46)](PVE-IDE-46.md)

#### Phase 3 : Calcul (1 tache)

- **65.1.1** - Selection compta

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (3 taches)

Traitements internes.

---

#### <a id="t1"></a>65 - Export Insurance [[ECRAN]](#ecran-t1)

**Role** : Traitement : Export Insurance.
**Ecran** : 312 x 121 DLU (MDI) | [Voir mockup](#ecran-t1)
**Delegue a** : [Get Temp Files (IDE 46)](PVE-IDE-46.md)

---

#### <a id="t4"></a>65.2 - Export SQL

**Role** : Traitement : Export SQL.
**Delegue a** : [Get Temp Files (IDE 46)](PVE-IDE-46.md)

---

#### <a id="t5"></a>65.3 - Export SQL

**Role** : Traitement : Export SQL.
**Delegue a** : [Get Temp Files (IDE 46)](PVE-IDE-46.md)


### 3.2 Consultation (1 tache)

Ecrans de recherche et consultation.

---

#### <a id="t2"></a>65.1 - SELECTION [[ECRAN]](#ecran-t2)

**Role** : Selection par l'operateur : SELECTION.
**Ecran** : 994 x 548 DLU (MDI) | [Voir mockup](#ecran-t2)


### 3.3 Calcul (1 tache)

Calculs metier : montants, stocks, compteurs.

---

#### <a id="t3"></a>65.1.1 - Selection compta

**Role** : Selection par l'operateur : Selection compta.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Menu Reports (IDE 182)](PVE-IDE-182.md)
- **Appelle**: 1 programmes | **Tables**: 4 (W:0 R:2 L:2) | **Taches**: 5 | **Expressions**: 14

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (5 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **65.1** | [**Export Insurance** (65)](#t1) [mockup](#ecran-t1) | MDI | 312x121 | Traitement |
| 65.1.1 | [Export SQL (65.2)](#t4) | - | - | |
| 65.1.2 | [Export SQL (65.3)](#t5) | - | - | |
| **65.2** | [**SELECTION** (65.1)](#t2) [mockup](#ecran-t2) | MDI | 994x548 | Consultation |
| **65.3** | [**Selection compta** (65.1.1)](#t3) | MDI | - | Calcul |

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

### Tables utilisees (4)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 30 | gm-recherche_____gmr | Index de recherche | DB | R |   |   | 1 |
| 523 | synthese_garanties | Depots et garanties | TMP | R |   |   | 1 |
| 1468 | Table_1468 |  | MEM |   |   | L | 1 |
| 1471 | Table_1471 |  | MEM |   |   | L | 1 |

### Colonnes par table (1 / 2 tables avec colonnes identifiees)

<details>
<summary>Table 30 - gm-recherche_____gmr (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | v.lien Gm Recherce | R | Logical |
| B | V date debut sejour customer | R | Date |
| C | V date fin sejour customer | R | Date |

</details>

<details>
<summary>Table 523 - synthese_garanties (R) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (5)

Variables recues du programme appelant ([Menu Reports (IDE 182)](PVE-IDE-182.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P.i.Date mini | Date | 1x parametre entrant |
| B | P.i.Date maxi | Date | 1x parametre entrant |
| C | P.o.File Name | Alpha | 1x parametre entrant |
| D | P.i.Service | Unicode | - |
| E | P.i.Categorie Assurance | Numeric | - |

### 11.2 Variables de session (4)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| G | v is item selected | Logical | 2x session |
| H | v is Item Customer selected | Logical | - |
| I | v is Item Package selected | Logical | - |
| J | v is Item Account selected | Logical | - |

### 11.3 Autres (7)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| F | Delimiter | Alpha | - |
| K | qualite | Unicode | - |
| L | lieu | Unicode | - |
| M | Code NA | Unicode | - |
| N | Num_Souscription | Unicode | - |
| O | Reason | Unicode | - |
| P | num_souscription | Unicode | - |

<details>
<summary>Toutes les 16 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| P0 | **A** | P.i.Date mini | Date |
| P0 | **B** | P.i.Date maxi | Date |
| P0 | **C** | P.o.File Name | Alpha |
| P0 | **D** | P.i.Service | Unicode |
| P0 | **E** | P.i.Categorie Assurance | Numeric |
| V. | **G** | v is item selected | Logical |
| V. | **H** | v is Item Customer selected | Logical |
| V. | **I** | v is Item Package selected | Logical |
| V. | **J** | v is Item Account selected | Logical |
| Autre | **F** | Delimiter | Alpha |
| Autre | **K** | qualite | Unicode |
| Autre | **L** | lieu | Unicode |
| Autre | **M** | Code NA | Unicode |
| Autre | **N** | Num_Souscription | Unicode |
| Autre | **O** | Reason | Unicode |
| Autre | **P** | num_souscription | Unicode |

</details>

## 12. EXPRESSIONS

**14 / 14 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONSTANTE | 1 | 0 |
| CONCATENATION | 2 | 0 |
| NEGATION | 1 | 0 |
| OTHER | 6 | 0 |
| CAST_LOGIQUE | 3 | 0 |
| STRING | 1 | 0 |

### 12.2 Expressions cles par type

#### CONSTANTE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 5 | `2` | - |

#### CONCATENATION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 13 | `'insurance_'&Trim(VG23)&'_'&DStr (P.i.Date mini [A],'YYYYMMDD')&'_'&DStr (P.i.Date maxi [B],'YYYYMMDD')&'.csv'` | - |
| CONCATENATION | 10 | `'%club_exportdata%'&'insurance_'&DStr (Date (),'YYYYMMDD')&'.csv'` | - |

#### NEGATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| NEGATION | 1 | `NOT (v is Item Customer sel... [H]) OR NOT(v is Item Package sele... [I]) OR NOT(v is Item Account sele... [J])` | - |

#### OTHER (6 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 11 | `NOT(VG90)` | - |
| OTHER | 12 | `NOT(IsComponent())` | - |
| OTHER | 14 | `NOT(VG114)` | - |
| OTHER | 2 | `INIGet ('[MAGIC_LOGICAL_NAMES]club_excel_separator')` | - |
| OTHER | 6 | `v is item selected [G]` | - |
| ... | | *+1 autres* | |

#### CAST_LOGIQUE (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 8 | `'TRUE'LOG` | - |
| CAST_LOGIQUE | 4 | `'FALSE'LOG` | - |
| CAST_LOGIQUE | 3 | `'TRUE'LOG` | - |

#### STRING (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| STRING | 9 | `Translate('%club_exportdata%')&Trim(P.o.File Name [C])` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Menu Reports (IDE 182)](PVE-IDE-182.md) -> **Export Insurance (IDE 65)**

```mermaid
graph LR
    T65[65 Export Insurance]
    style T65 fill:#58a6ff
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
    CC182 --> T65
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [182](PVE-IDE-182.md) | Menu Reports | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T65[65 Export Insurance]
    style T65 fill:#58a6ff
    C46[46 Get Temp Files]
    T65 --> C46
    style C46 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [46](PVE-IDE-46.md) | Get Temp Files | 1 | Recuperation donnees |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 137 | Programme compact |
| Expressions | 14 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 1 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 137) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (3 taches: 1 ecran, 2 traitements)

- **Strategie** : Orchestrateur avec 1 ecrans (Razor/React) et 2 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 1 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Consultation (1 tache: 1 ecran, 0 traitement)

- **Strategie** : Composants de recherche/selection en modales.
- 1 ecran : SELECTION

#### Calcul (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Services de calcul purs (Domain Services).
- Migrer la logique de calcul (stock, compteurs, montants)

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| [Get Temp Files (IDE 46)](PVE-IDE-46.md) | Sous-programme | 1x | Normale - Recuperation donnees |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 09:05*
