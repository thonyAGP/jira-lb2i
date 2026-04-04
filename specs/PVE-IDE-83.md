# PVE IDE 83 - Print Global Income

> **Analyse**: Phases 1-4 2026-02-03 09:14 -> 09:14 (20s) | Assemblage 09:14
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PVE |
| IDE Position | 83 |
| Nom Programme | Print Global Income |
| Fichier source | `Prg_83.xml` |
| Domaine metier | Impression |
| Taches | 14 (0 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 2 |

## 2. DESCRIPTION FONCTIONNELLE

**Print Global Income** assure la gestion complete de ce processus, accessible depuis [Menu Cloture du service (IDE 180)](PVE-IDE-180.md), [Menu Reports (IDE 182)](PVE-IDE-182.md), [Menu Service cloture v2 (IDE 397)](PVE-IDE-397.md), [Menu Service cloture (IDE 402)](PVE-IDE-402.md).

Le flux de traitement s'organise en **4 blocs fonctionnels** :

- **Traitement** (8 taches) : traitements metier divers
- **Impression** (4 taches) : generation de tickets et documents
- **Consultation** (1 tache) : ecrans de recherche, selection et consultation
- **Calcul** (1 tache) : calculs de montants, stocks ou compteurs

**Donnees modifiees** : 1 tables en ecriture (Table_1461).

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Impression (4 taches)

- **83** - Print Global Income **[[ECRAN]](#ecran-t1)**
- **83.1** - Print
- **83.1.2** - EDITION
- **83.1.2.1.2** - Print Totaux

#### Phase 2 : Consultation (1 tache)

- **83.1.1** - SELECTION **[[ECRAN]](#ecran-t3)**

Delegue a : [Get Temp Files (IDE 46)](PVE-IDE-46.md)

#### Phase 3 : Calcul (1 tache)

- **83.1.1.1** - Selection compta

#### Phase 4 : Traitement (8 taches)

- **83.1.1.1.1** - Temp generation
- **83.1.1.1.1.1** - Temp generation
- **83.1.1.2** - Temp generation
- **83.1.1.2.1** - Temp generation
- **83.1.2.1** - Lines
- **83.1.2.1.1** - Total
- **83.1.2.1.2.1** - Read Total
- **83.1.2.1.2.2** - Refund

Delegue a : [Get Temp Files (IDE 46)](PVE-IDE-46.md), [IoDel fichier CSV (IDE 56)](PVE-IDE-56.md)

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| Table_1461 | R/**W**/L (8 usages) |  |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Impression (4 taches)

Generation des documents et tickets.

---

#### <a id="t1"></a>83 - Print Global Income [[ECRAN]](#ecran-t1)

**Role** : Generation du document : Print Global Income.
**Ecran** : 312 x 173 DLU (MDI) | [Voir mockup](#ecran-t1)

<details>
<summary>3 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [83.1](#t2) | Print | Impression |
| [83.1.2](#t9) | EDITION | Impression |
| [83.1.2.1.2](#t12) | Print Totaux | Impression |

</details>
**Variables liees** : G (V Mode Global / Détail)

---

#### <a id="t2"></a>83.1 - Print

**Role** : Generation du document : Print.

---

#### <a id="t9"></a>83.1.2 - EDITION

**Role** : Generation du document : EDITION.

---

#### <a id="t12"></a>83.1.2.1.2 - Print Totaux

**Role** : Generation du document : Print Totaux.


### 3.2 Consultation (1 tache)

Ecrans de recherche et consultation.

---

#### <a id="t3"></a>83.1.1 - SELECTION [[ECRAN]](#ecran-t3)

**Role** : Selection par l'operateur : SELECTION.
**Ecran** : 721 x 282 DLU (MDI) | [Voir mockup](#ecran-t3)


### 3.3 Calcul (1 tache)

Calculs metier : montants, stocks, compteurs.

---

#### <a id="t4"></a>83.1.1.1 - Selection compta

**Role** : Selection par l'operateur : Selection compta.


### 3.4 Traitement (8 taches)

Traitements internes.

---

#### <a id="t5"></a>83.1.1.1.1 - Temp generation

**Role** : Traitement : Temp generation.
**Delegue a** : [Get Temp Files (IDE 46)](PVE-IDE-46.md), [IoDel fichier CSV (IDE 56)](PVE-IDE-56.md)

---

#### <a id="t6"></a>83.1.1.1.1.1 - Temp generation

**Role** : Traitement : Temp generation.
**Delegue a** : [Get Temp Files (IDE 46)](PVE-IDE-46.md), [IoDel fichier CSV (IDE 56)](PVE-IDE-56.md)

---

#### <a id="t7"></a>83.1.1.2 - Temp generation

**Role** : Traitement : Temp generation.
**Delegue a** : [Get Temp Files (IDE 46)](PVE-IDE-46.md), [IoDel fichier CSV (IDE 56)](PVE-IDE-56.md)

---

#### <a id="t8"></a>83.1.1.2.1 - Temp generation

**Role** : Traitement : Temp generation.
**Delegue a** : [Get Temp Files (IDE 46)](PVE-IDE-46.md), [IoDel fichier CSV (IDE 56)](PVE-IDE-56.md)

---

#### <a id="t10"></a>83.1.2.1 - Lines

**Role** : Traitement : Lines.
**Delegue a** : [Get Temp Files (IDE 46)](PVE-IDE-46.md), [IoDel fichier CSV (IDE 56)](PVE-IDE-56.md)

---

#### <a id="t11"></a>83.1.2.1.1 - Total

**Role** : Traitement : Total.
**Delegue a** : [Get Temp Files (IDE 46)](PVE-IDE-46.md), [IoDel fichier CSV (IDE 56)](PVE-IDE-56.md)

---

#### <a id="t13"></a>83.1.2.1.2.1 - Read Total

**Role** : Traitement : Read Total.
**Delegue a** : [Get Temp Files (IDE 46)](PVE-IDE-46.md), [IoDel fichier CSV (IDE 56)](PVE-IDE-56.md)

---

#### <a id="t14"></a>83.1.2.1.2.2 - Refund

**Role** : Traitement : Refund.
**Delegue a** : [Get Temp Files (IDE 46)](PVE-IDE-46.md), [IoDel fichier CSV (IDE 56)](PVE-IDE-56.md)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Menu Cloture du service (IDE 180)](PVE-IDE-180.md), [Menu Reports (IDE 182)](PVE-IDE-182.md), [Menu Service cloture v2 (IDE 397)](PVE-IDE-397.md), [Menu Service cloture (IDE 402)](PVE-IDE-402.md)
- **Appelle**: 2 programmes | **Tables**: 6 (W:1 R:4 L:3) | **Taches**: 14 | **Expressions**: 8

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (14 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **83.1** | [**Print Global Income** (83)](#t1) [mockup](#ecran-t1) | MDI | 312x173 | Impression |
| 83.1.1 | [Print (83.1)](#t2) | MDI | - | |
| 83.1.2 | [EDITION (83.1.2)](#t9) | MDI | - | |
| 83.1.3 | [Print Totaux (83.1.2.1.2)](#t12) | MDI | - | |
| **83.2** | [**SELECTION** (83.1.1)](#t3) [mockup](#ecran-t3) | MDI | 721x282 | Consultation |
| **83.3** | [**Selection compta** (83.1.1.1)](#t4) | MDI | - | Calcul |
| **83.4** | [**Temp generation** (83.1.1.1.1)](#t5) | MDI | - | Traitement |
| 83.4.1 | [Temp generation (83.1.1.1.1.1)](#t6) | MDI | - | |
| 83.4.2 | [Temp generation (83.1.1.2)](#t7) | MDI | - | |
| 83.4.3 | [Temp generation (83.1.1.2.1)](#t8) | MDI | - | |
| 83.4.4 | [Lines (83.1.2.1)](#t10) | MDI | - | |
| 83.4.5 | [Total (83.1.2.1.1)](#t11) | MDI | - | |
| 83.4.6 | [Read Total (83.1.2.1.2.1)](#t13) | MDI | - | |
| 83.4.7 | [Refund (83.1.2.1.2.2)](#t14) | MDI | - | |

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

### Tables utilisees (6)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 379 | pv_customer_temp |  | DB | R |   |   | 2 |
| 413 | pv_tva |  | DB |   |   | L | 1 |
| 420 | req_dispatch |  | DB | R |   |   | 1 |
| 523 | synthese_garanties | Depots et garanties | TMP | R |   |   | 1 |
| 1461 | Table_1461 |  | MEM | R | **W** | L | 8 |
| 1471 | Table_1471 |  | MEM |   |   | L | 1 |

### Colonnes par table (4 / 4 tables avec colonnes identifiees)

<details>
<summary>Table 379 - pv_customer_temp (R) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | v.total | R | Numeric |
| B | v..total gp | R | Numeric |
| C | v.montant taxes | R | Numeric |
| D | v.taxes multiples | R | Logical |
| E | V. Total General TTC | R | Numeric |
| F | V. Total General TVA | R | Numeric |

</details>

<details>
<summary>Table 420 - req_dispatch (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | Total Général TTC | R | Numeric |
| B | Total Général TVA | R | Numeric |
| C | Total Général HT | R | Numeric |

</details>

<details>
<summary>Table 523 - synthese_garanties (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | V Montant total ticket | R | Numeric |
| B | V Montant total ticket HT | R | Numeric |
| C | V Montant total ticket TVA | R | Numeric |
| D | v Montant Ht | R | Numeric |
| E | v Montant tva | R | Numeric |
| F | v Montant Prepaid Ht | R | Numeric |
| G | v Montant Prepaid Tva | R | Numeric |

</details>

<details>
<summary>Table 1461 - Table_1461 (R/**W**/L) - 8 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | p. refund | W | Logical |
| B | v Montnt Tva | W | Numeric |
| C | Total Location TVA | W | Numeric |
| D | Total General TTC | W | Numeric |
| E | Total General HT | W | Numeric |
| F | Total General TVA | W | Numeric |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (6)

Variables recues du programme appelant ([Menu Cloture du service (IDE 180)](PVE-IDE-180.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P. Masque | Alpha | - |
| B | P. Masque sans Z | Alpha | - |
| C | P. Date mini | Date | 4x parametre entrant |
| D | P. Date maxi | Date | 5x parametre entrant |
| E | P.Village | Alpha | - |
| F | P.I Flag Cloture Service | Logical | - |

### 11.2 Variables de session (5)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| G | V Mode Global / Détail | Alpha | - |
| H | v.NomFichierPdf | Alpha | 2x session |
| I | v.NomFichierPdf Archivage | Alpha | - |
| J | v.NomFichierCSV | Alpha | - |
| K | v.NomFichierCSV Archivage | Alpha | - |

## 12. EXPRESSIONS

**8 / 8 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONDITION | 2 | 0 |
| CONSTANTE | 1 | 0 |
| CONCATENATION | 4 | 0 |
| STRING | 1 | 0 |

### 12.2 Expressions cles par type

#### CONDITION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 6 | `(GetParam ('Output')='Extraction') AND FileExist (Trim(v.NomFichierPdf [H]))` | - |
| CONDITION | 1 | `P. Date maxi [D]<>'00/00/0000'DATE` | - |

#### CONSTANTE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 2 | `'D'` | - |

#### CONCATENATION (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 7 | `MlsTrans('%club_exportdata%')&Trim (GetParam ('VILLAGECODE'))&
Trim (GetParam ('SERVICE'))&'Global_Income_'&
DStr (P. Date mini [C],'YYYYMMDD')&'_'&DStr (P. Date maxi [D],'YYYYMMDD')&'.csv'` | - |
| CONCATENATION | 8 | `MlsTrans('%club_exportdata%')&'ArchivagePos\'&Trim (GetParam ('VILLAGECODE'))&
Trim (GetParam ('SERVICE'))&'Global_Income_'&
DStr (P. Date mini [C],'YYYYMMDD')&'_'&DStr (P. Date maxi [D],'YYYYMMDD')&'.csv'` | - |
| CONCATENATION | 4 | `Translate ('%club_exportdata%')&Trim (GetParam ('VILLAGECODE'))&Trim (GetParam ('SERVICE'))&'_GLOBAL_INCOME_'&DStr (P. Date mini [C],'YYYYMMDD')&'_'&DStr (P. Date maxi [D],'YYYYMMDD')&'.Pdf'` | - |
| CONCATENATION | 5 | `Translate ('%club_exportdata%')&'ArchivagePos\'&Trim (GetParam ('VILLAGECODE'))&Trim (GetParam ('SERVICE'))&'_GLOBAL_INCOME_'&DStr (P. Date mini [C],'YYYYMMDD')&'_'&DStr (P. Date maxi [D],'YYYYMMDD')&'.Pdf'` | - |

#### STRING (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| STRING | 3 | `FileDelete (Trim(v.NomFichierPdf [H]))` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Menu Cloture du service (IDE 180)](PVE-IDE-180.md) -> **Print Global Income (IDE 83)**

Main -> ... -> [Menu Reports (IDE 182)](PVE-IDE-182.md) -> **Print Global Income (IDE 83)**

Main -> ... -> [Menu Service cloture v2 (IDE 397)](PVE-IDE-397.md) -> **Print Global Income (IDE 83)**

Main -> ... -> [Menu Service cloture (IDE 402)](PVE-IDE-402.md) -> **Print Global Income (IDE 83)**

```mermaid
graph LR
    T83[83 Print Global Income]
    style T83 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC143[143 START]
    style CC143 fill:#f59e0b
    CC353[353 Menu==V4]
    style CC353 fill:#f59e0b
    CC420[420 Menu==V4___]
    style CC420 fill:#f59e0b
    CC439[439 Menu]
    style CC439 fill:#f59e0b
    CC185[185 Menu]
    style CC185 fill:#f59e0b
    CC182[182 Menu Reports]
    style CC182 fill:#3fb950
    CC180[180 Menu Cloture du se...]
    style CC180 fill:#3fb950
    CC402[402 Menu Service cloture]
    style CC402 fill:#3fb950
    CC397[397 Menu Service clotu...]
    style CC397 fill:#3fb950
    CC185 --> CC180
    CC353 --> CC180
    CC420 --> CC180
    CC439 --> CC180
    CC185 --> CC182
    CC353 --> CC182
    CC420 --> CC182
    CC439 --> CC182
    CC185 --> CC397
    CC353 --> CC397
    CC420 --> CC397
    CC439 --> CC397
    CC185 --> CC402
    CC353 --> CC402
    CC420 --> CC402
    CC439 --> CC402
    CC143 --> CC185
    CC143 --> CC353
    CC143 --> CC420
    CC143 --> CC439
    CC1 --> CC143
    CC180 --> T83
    CC182 --> T83
    CC397 --> T83
    CC402 --> T83
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [180](PVE-IDE-180.md) | Menu Cloture du service | 1 |
| [182](PVE-IDE-182.md) | Menu Reports | 1 |
| [397](PVE-IDE-397.md) | Menu Service cloture v2 | 1 |
| [402](PVE-IDE-402.md) | Menu Service cloture | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T83[83 Print Global Income]
    style T83 fill:#58a6ff
    C46[46 Get Temp Files]
    T83 --> C46
    style C46 fill:#3fb950
    C56[56 IoDel fichier CSV]
    T83 --> C56
    style C56 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [46](PVE-IDE-46.md) | Get Temp Files | 1 | Recuperation donnees |
| [56](PVE-IDE-56.md) | IoDel fichier CSV | 1 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 446 | Taille moyenne |
| Expressions | 8 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 2 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 3.1% (14 / 446) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Impression (4 taches: 1 ecran, 3 traitements)

- **Strategie** : Templates HTML -> PDF via wkhtmltopdf ou Puppeteer.
- `PrintService` injectable avec choix imprimante

#### Consultation (1 tache: 1 ecran, 0 traitement)

- **Strategie** : Composants de recherche/selection en modales.
- 1 ecran : SELECTION

#### Calcul (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Services de calcul purs (Domain Services).
- Migrer la logique de calcul (stock, compteurs, montants)

#### Traitement (8 taches: 0 ecran, 8 traitements)

- **Strategie** : 8 service(s) backend injectable(s) (Domain Services).
- 2 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| Table_1461 | Table WRITE (Memory) | 5x | Schema + repository |
| [IoDel fichier CSV (IDE 56)](PVE-IDE-56.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Get Temp Files (IDE 46)](PVE-IDE-46.md) | Sous-programme | 1x | Normale - Recuperation donnees |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 09:14*
