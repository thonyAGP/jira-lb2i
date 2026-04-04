# PVE IDE 384 - Report - Revenue by Place

> **Analyse**: Phases 1-4 2026-02-03 19:52 -> 19:52 (11s) | Assemblage 19:52
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PVE |
| IDE Position | 384 |
| Nom Programme | Report - Revenue by Place |
| Fichier source | `Prg_384.xml` |
| Dossier IDE | A |
| Taches | 7 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 5 |
| :warning: Statut | **ORPHELIN_POTENTIEL** |

## 2. DESCRIPTION FONCTIONNELLE

**Report - Revenue by Place** assure la gestion complete de ce processus.

Le flux de traitement s'organise en **2 blocs fonctionnels** :

- **Traitement** (4 taches) : traitements metier divers
- **Impression** (3 taches) : generation de tickets et documents

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (4 taches)

- **384** - Report - Revenue before tax **[[ECRAN]](#ecran-t1)**
- **384.1.1.1** - Lines
- **384.1.1.1.1** - Total
- **384.1.1.1.2.1** - Refund

Delegue a : [IoDel fichier CSV (IDE 56)](PVE-IDE-56.md), [Report - Compute % (IDE 57)](PVE-IDE-57.md), [Choice today tomorrow (IDE 202)](PVE-IDE-202.md)

#### Phase 2 : Impression (3 taches)

- **384.1** - Print
- **384.1.1** - EDITION
- **384.1.1.1.2** - Print Totaux

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (4 taches)

Traitements internes.

---

#### <a id="t1"></a>384 - Report - Revenue before tax [[ECRAN]](#ecran-t1)

**Role** : Traitement : Report - Revenue before tax.
**Ecran** : 312 x 57 DLU (MDI) | [Voir mockup](#ecran-t1)

<details>
<summary>3 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [384.1.1.1](#t4) | Lines | Traitement |
| [384.1.1.1.1](#t5) | Total | Traitement |
| [384.1.1.1.2.1](#t7) | Refund | Traitement |

</details>
**Delegue a** : [IoDel fichier CSV (IDE 56)](PVE-IDE-56.md), [Report - Compute % (IDE 57)](PVE-IDE-57.md), [Choice today tomorrow (IDE 202)](PVE-IDE-202.md)

---

#### <a id="t4"></a>384.1.1.1 - Lines

**Role** : Traitement : Lines.
**Delegue a** : [IoDel fichier CSV (IDE 56)](PVE-IDE-56.md), [Report - Compute % (IDE 57)](PVE-IDE-57.md), [Choice today tomorrow (IDE 202)](PVE-IDE-202.md)

---

#### <a id="t5"></a>384.1.1.1.1 - Total

**Role** : Traitement : Total.
**Delegue a** : [IoDel fichier CSV (IDE 56)](PVE-IDE-56.md), [Report - Compute % (IDE 57)](PVE-IDE-57.md), [Choice today tomorrow (IDE 202)](PVE-IDE-202.md)

---

#### <a id="t7"></a>384.1.1.1.2.1 - Refund

**Role** : Traitement : Refund.
**Delegue a** : [IoDel fichier CSV (IDE 56)](PVE-IDE-56.md), [Report - Compute % (IDE 57)](PVE-IDE-57.md), [Choice today tomorrow (IDE 202)](PVE-IDE-202.md)


### 3.2 Impression (3 taches)

Generation des documents et tickets.

---

#### <a id="t2"></a>384.1 - Print

**Role** : Generation du document : Print.

---

#### <a id="t3"></a>384.1.1 - EDITION

**Role** : Generation du document : EDITION.

---

#### <a id="t6"></a>384.1.1.1.2 - Print Totaux

**Role** : Generation du document : Print Totaux.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: (aucun)
- **Appelle**: 5 programmes | **Tables**: 2 (W:0 R:2 L:1) | **Taches**: 7 | **Expressions**: 5

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (7 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **384.1** | [**Report - Revenue before tax** (384)](#t1) [mockup](#ecran-t1) | MDI | 312x57 | Traitement |
| 384.1.1 | [Lines (384.1.1.1)](#t4) | MDI | - | |
| 384.1.2 | [Total (384.1.1.1.1)](#t5) | MDI | - | |
| 384.1.3 | [Refund (384.1.1.1.2.1)](#t7) | MDI | - | |
| **384.2** | [**Print** (384.1)](#t2) | MDI | - | Impression |
| 384.2.1 | [EDITION (384.1.1)](#t3) | MDI | - | |
| 384.2.2 | [Print Totaux (384.1.1.1.2)](#t6) | MDI | - | |

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
| 524 | update_table_codes_log |  | TMP | R |   | L | 3 |
| 766 | temp_forfait_ski |  | DB | R |   |   | 1 |

### Colonnes par table (2 / 2 tables avec colonnes identifiees)

<details>
<summary>Table 524 - update_table_codes_log (R/L) - 3 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | Total location | R | Numeric |
| B | Total location HT | R | Numeric |
| C | Total location TTC | R | Numeric |
| D | Total General | R | Numeric |
| E | Total General HT | R | Numeric |
| F | Total General TTC | R | Numeric |

</details>

<details>
<summary>Table 766 - temp_forfait_ski (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | Total Lieu | R | Numeric |
| B | Total lieu HT | R | Numeric |
| C | Total lieu TTC | R | Numeric |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (5)

Variables recues en parametre.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P. Village Name | Alpha | - |
| B | P. Currency | Alpha | - |
| C | P. Masque | Alpha | - |
| D | P. Masque sans Z | Alpha | - |
| E | P. Decimales | Numeric | - |

### 11.2 Variables de session (4)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| F | V Date mini | Date | 1x session |
| G | V Date maxi | Date | 2x session |
| H | V Période nombre JH | Numeric | - |
| I | V Jours période | Numeric | - |

### 11.3 Autres (2)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| J | Param Mode Global / Détail | Alpha | - |
| K | ; | Alpha | 1x refs |

## 12. EXPRESSIONS

**5 / 5 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONDITION | 2 | 0 |
| CONSTANTE | 2 | 0 |
| CAST_LOGIQUE | 1 | 0 |

### 12.2 Expressions cles par type

#### CONDITION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 2 | `V Date maxi [G]<>'00/00/0000'DATE` | - |
| CONDITION | 1 | `V Date mini [F]='00/00/0000'DATE AND V Date maxi [G]='00/00/0000'DATE` | - |

#### CONSTANTE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 4 | `';'` | - |
| CONSTANTE | 3 | `'D'` | - |

#### CAST_LOGIQUE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 5 | `'TRUE'LOG` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

**Chemin**: (pas de callers directs)

```mermaid
graph LR
    T384[384 Report - Revenue b...]
    style T384 fill:#58a6ff
    NONE[Aucun caller]
    NONE -.-> T384
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| - | (aucun) | - |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T384[384 Report - Revenue b...]
    style T384 fill:#58a6ff
    C56[56 IoDel fichier CSV]
    T384 --> C56
    style C56 fill:#3fb950
    C57[57 Report - Compute %]
    T384 --> C57
    style C57 fill:#3fb950
    C202[202 Choice today tomorrow]
    T384 --> C202
    style C202 fill:#3fb950
    C396[396 Report - Selection...]
    T384 --> C396
    style C396 fill:#3fb950
    C448[448 Browse - pv_compta...]
    T384 --> C448
    style C448 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [56](PVE-IDE-56.md) | IoDel fichier CSV | 1 | Sous-programme |
| [57](PVE-IDE-57.md) | Report - Compute % | 1 | Sous-programme |
| [202](PVE-IDE-202.md) | Choice today tomorrow | 1 | Sous-programme |
| [396](PVE-IDE-396.md) | Report - Selection/Tempo | 1 | Selection/consultation |
| [448](PVE-IDE-448.md) | Browse - pv_comptab_temp | 1 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 164 | Programme compact |
| Expressions | 5 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 5 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 164) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (4 taches: 1 ecran, 3 traitements)

- **Strategie** : Orchestrateur avec 1 ecrans (Razor/React) et 3 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 5 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Impression (3 taches: 0 ecran, 3 traitements)

- **Strategie** : Templates HTML -> PDF via wkhtmltopdf ou Puppeteer.
- `PrintService` injectable avec choix imprimante

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| [Report - Selection/Tempo (IDE 396)](PVE-IDE-396.md) | Sous-programme | 1x | Normale - Selection/consultation |
| [Browse - pv_comptab_temp (IDE 448)](PVE-IDE-448.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Choice today tomorrow (IDE 202)](PVE-IDE-202.md) | Sous-programme | 1x | Normale - Sous-programme |
| [IoDel fichier CSV (IDE 56)](PVE-IDE-56.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Report - Compute % (IDE 57)](PVE-IDE-57.md) | Sous-programme | 1x | Normale - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 19:52*
