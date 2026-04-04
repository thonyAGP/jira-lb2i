# PVE IDE 414 - Print Invoice or Ticket==V4

> **Analyse**: Phases 1-4 2026-02-03 20:01 -> 20:01 (10s) | Assemblage 20:01
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PVE |
| IDE Position | 414 |
| Nom Programme | Print Invoice or Ticket==V4 |
| Fichier source | `Prg_414.xml` |
| Dossier IDE | A |
| Taches | 36 (0 ecrans visibles) |
| Tables modifiees | 9 |
| Programmes appeles | 7 |

## 2. DESCRIPTION FONCTIONNELLE

**Print Invoice or Ticket==V4** assure la gestion complete de ce processus, accessible depuis [Generate Preview OD==V4 (IDE 357)](PVE-IDE-357.md).

Le flux de traitement s'organise en **6 blocs fonctionnels** :

- **Traitement** (24 taches) : traitements metier divers
- **Consultation** (4 taches) : ecrans de recherche, selection et consultation
- **Impression** (4 taches) : generation de tickets et documents
- **Calcul** (2 taches) : calculs de montants, stocks ou compteurs
- **Creation** (1 tache) : insertion d'enregistrements en base (mouvements, prestations)
- **Initialisation** (1 tache) : reinitialisation d'etats et de variables de travail

**Donnees modifiees** : 9 tables en ecriture (transac_detail_bar, transac_entete_bar, comptable________cte, pv_ownership, pv_cust_packages, pv_package_composants, import_avertiss__an_val, cumul_mvt_stock_histo, Table_1501).

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Impression (4 taches)

- **414** - Print Invoice **[[ECRAN]](#ecran-t1)**
- **414.3** - EDITION
- **414.5** - PRINT AGAIN **[[ECRAN]](#ecran-t25)**
- **414.5.1** - Print Again Gener

Delegue a : [Edition ticket (Tva) (IDE 280)](PVE-IDE-280.md), [Edition ticket (IDE 273)](PVE-IDE-273.md)

#### Phase 2 : Traitement (24 taches)

- **414.1** - PARAMETERS
- **414.2.1.1.1** - Temp generation Gift Pass
- **414.2.1.1.2** - Temp generation
- **414.2.1.1.3** - Temp generation
- **414.2.1.1.4** - Temp generation Gift Pass
- **414.2.2.1** - Temp generation
- **414.3.1** - Package line **[[ECRAN]](#ecran-t13)**
- **414.3.1.1** - Package line
- **414.3.2** - Package blank line
- **414.3.3** - Filiations
- **414.3.3.1** - Ski Shoes Name
- **414.4** - HISTO
- **414.4.1** - Generation
- **414.4.1.1** - header
- **414.4.1.1.1** - Entete EZcard
- **414.4.1.2** - Lines
- **414.4.2** - Package line
- **414.4.2.1** - Ligne EZcard
- **414.5.1.2.1** - Temp generation
- **414.5.2** - Trace Again
- **414.6** - CHECK HISTO
- **414.7.1** - Package
- **414.7.2** - Filiation
- **414.8** - Search for Gift Pass **[[ECRAN]](#ecran-t35)**

Delegue a : [Set Customer (IDE 278)](PVE-IDE-278.md), [Get default email address (IDE 314)](PVE-IDE-314.md)

#### Phase 3 : Consultation (4 taches)

- **414.2** - SELECTION **[[ECRAN]](#ecran-t3)**
- **414.2.1** - Selection Packages **[[ECRAN]](#ecran-t4)**
- **414.2.2** - Selection Filiations
- **414.5.1.2** - Selection Filiations

Delegue a : [Recherche Adresse Mail (IDE 308)](PVE-IDE-308.md), [Get default email address (IDE 314)](PVE-IDE-314.md)

#### Phase 4 : Calcul (2 taches)

- **414.2.1.1** - Selection Pv_Compta
- **414.5.1.1** - Load temp compta

#### Phase 5 : Initialisation (1 tache)

- **414.7** - RAZ TEMPO

#### Phase 6 : Creation (1 tache)

- **414.9** - CreationMail pour File Traitem

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| cumul_mvt_stock_histo | **W**/L (13 usages) | Articles et stock |
| import_avertiss__an_val | **W**/L (4 usages) |  |
| pv_ownership | R/**W** (2 usages) |  |
| pv_cust_packages | **W**/L (2 usages) |  |
| comptable________cte | **W** (1 usages) |  |
| pv_package_composants | **W** (1 usages) |  |
| Table_1501 | **W** (1 usages) |  |
| transac_entete_bar | **W** (1 usages) |  |
| transac_detail_bar | **W** (1 usages) |  |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Impression (4 taches)

Generation des documents et tickets.

---

#### <a id="t1"></a>414 - Print Invoice [[ECRAN]](#ecran-t1)

**Role** : Generation du document : Print Invoice.
**Ecran** : 640 x 65 DLU (MDI) | [Voir mockup](#ecran-t1)

<details>
<summary>3 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [414.3](#t12) | EDITION | Impression |
| [414.5](#t25) | PRINT AGAIN **[[ECRAN]](#ecran-t25)** | Impression |
| [414.5.1](#t26) | Print Again Gener | Impression |

</details>
**Variables liees** : G (P. PrintAgain), U (PrintAgainPreview), BA (PrintAgainExecution), BB (PrintAgainCopy)
**Delegue a** : [Edition ticket (Tva) (IDE 280)](PVE-IDE-280.md), [Edition ticket (IDE 273)](PVE-IDE-273.md)

---

#### <a id="t12"></a>414.3 - EDITION

**Role** : Generation du document : EDITION.
**Delegue a** : [Edition ticket (Tva) (IDE 280)](PVE-IDE-280.md), [Edition ticket (IDE 273)](PVE-IDE-273.md)

---

#### <a id="t25"></a>414.5 - PRINT AGAIN [[ECRAN]](#ecran-t25)

**Role** : Generation du document : PRINT AGAIN.
**Ecran** : 375 x 240 DLU (MDI) | [Voir mockup](#ecran-t25)
**Variables liees** : G (P. PrintAgain), U (PrintAgainPreview), BA (PrintAgainExecution), BB (PrintAgainCopy)
**Delegue a** : [Edition ticket (Tva) (IDE 280)](PVE-IDE-280.md), [Edition ticket (IDE 273)](PVE-IDE-273.md)

---

#### <a id="t26"></a>414.5.1 - Print Again Gener

**Role** : Generation du document : Print Again Gener.
**Variables liees** : G (P. PrintAgain), U (PrintAgainPreview), BA (PrintAgainExecution), BB (PrintAgainCopy)
**Delegue a** : [Edition ticket (Tva) (IDE 280)](PVE-IDE-280.md), [Edition ticket (IDE 273)](PVE-IDE-273.md)


### 3.2 Traitement (24 taches)

Traitements internes.

---

#### <a id="t2"></a>414.1 - PARAMETERS

**Role** : Traitement : PARAMETERS.

---

#### <a id="t6"></a>414.2.1.1.1 - Temp generation Gift Pass

**Role** : Calcul fidelite/avantage : Temp generation Gift Pass.
**Variables liees** : BP (v Solde Gift Pass), BQ (v Existe Gift Pass), BR (v.Message Solde Gift Pass)

---

#### <a id="t7"></a>414.2.1.1.2 - Temp generation

**Role** : Traitement : Temp generation.

---

#### <a id="t8"></a>414.2.1.1.3 - Temp generation

**Role** : Traitement : Temp generation.

---

#### <a id="t9"></a>414.2.1.1.4 - Temp generation Gift Pass

**Role** : Calcul fidelite/avantage : Temp generation Gift Pass.
**Variables liees** : BP (v Solde Gift Pass), BQ (v Existe Gift Pass), BR (v.Message Solde Gift Pass)

---

#### <a id="t11"></a>414.2.2.1 - Temp generation

**Role** : Traitement : Temp generation.

---

#### <a id="t13"></a>414.3.1 - Package line [[ECRAN]](#ecran-t13)

**Role** : Traitement : Package line.
**Ecran** : 557 x 327 DLU (MDI) | [Voir mockup](#ecran-t13)
**Variables liees** : F (P. Package id), BD (HeaderLine01), BE (HeaderLine02), BF (HeaderLine03), BG (HeaderLine04)

---

#### <a id="t14"></a>414.3.1.1 - Package line

**Role** : Traitement : Package line.
**Variables liees** : F (P. Package id), BD (HeaderLine01), BE (HeaderLine02), BF (HeaderLine03), BG (HeaderLine04)

---

#### <a id="t15"></a>414.3.2 - Package blank line

**Role** : Traitement : Package blank line.
**Variables liees** : F (P. Package id), BD (HeaderLine01), BE (HeaderLine02), BF (HeaderLine03), BG (HeaderLine04)

---

#### <a id="t16"></a>414.3.3 - Filiations

**Role** : Traitement : Filiations.

---

#### <a id="t17"></a>414.3.3.1 - Ski Shoes Name

**Role** : Traitement : Ski Shoes Name.
**Variables liees** : Q (P.File Name Signature)

---

#### <a id="t18"></a>414.4 - HISTO

**Role** : Traitement : HISTO.
**Variables liees** : BC (L ExistHistoric ?)

---

#### <a id="t19"></a>414.4.1 - Generation

**Role** : Traitement : Generation.

---

#### <a id="t20"></a>414.4.1.1 - header

**Role** : Traitement : header.
**Variables liees** : BD (HeaderLine01), BE (HeaderLine02), BF (HeaderLine03), BG (HeaderLine04), BH (HeaderLine05)

---

#### <a id="t21"></a>414.4.1.1.1 - Entete EZcard

**Role** : Traitement : Entete EZcard.
**Variables liees** : K (P. EZcard)

---

#### <a id="t22"></a>414.4.1.2 - Lines

**Role** : Traitement : Lines.

---

#### <a id="t23"></a>414.4.2 - Package line

**Role** : Traitement : Package line.
**Variables liees** : F (P. Package id), BD (HeaderLine01), BE (HeaderLine02), BF (HeaderLine03), BG (HeaderLine04)

---

#### <a id="t24"></a>414.4.2.1 - Ligne EZcard

**Role** : Traitement : Ligne EZcard.
**Variables liees** : K (P. EZcard)

---

#### <a id="t29"></a>414.5.1.2.1 - Temp generation

**Role** : Traitement : Temp generation.

---

#### <a id="t30"></a>414.5.2 - Trace Again

**Role** : Traitement : Trace Again.
**Variables liees** : G (P. PrintAgain), U (PrintAgainPreview), BA (PrintAgainExecution), BB (PrintAgainCopy)

---

#### <a id="t31"></a>414.6 - CHECK HISTO

**Role** : Traitement : CHECK HISTO.
**Variables liees** : BC (L ExistHistoric ?)

---

#### <a id="t33"></a>414.7.1 - Package

**Role** : Traitement : Package.
**Variables liees** : F (P. Package id)

---

#### <a id="t34"></a>414.7.2 - Filiation

**Role** : Traitement : Filiation.
**Variables liees** : E (P. Filiation), P (P.Filiation)

---

#### <a id="t35"></a>414.8 - Search for Gift Pass [[ECRAN]](#ecran-t35)

**Role** : Calcul fidelite/avantage : Search for Gift Pass.
**Ecran** : 175 x 195 DLU | [Voir mockup](#ecran-t35)
**Variables liees** : BP (v Solde Gift Pass), BQ (v Existe Gift Pass), BR (v.Message Solde Gift Pass)


### 3.3 Consultation (4 taches)

Ecrans de recherche et consultation.

---

#### <a id="t3"></a>414.2 - SELECTION [[ECRAN]](#ecran-t3)

**Role** : Selection par l'operateur : SELECTION.
**Ecran** : 640 x 0 DLU (MDI) | [Voir mockup](#ecran-t3)
**Delegue a** : [Recherche Adresse Mail (IDE 308)](PVE-IDE-308.md)

---

#### <a id="t4"></a>414.2.1 - Selection Packages [[ECRAN]](#ecran-t4)

**Role** : Selection par l'operateur : Selection Packages.
**Ecran** : 814 x 0 DLU (MDI) | [Voir mockup](#ecran-t4)
**Delegue a** : [Recherche Adresse Mail (IDE 308)](PVE-IDE-308.md)

---

#### <a id="t10"></a>414.2.2 - Selection Filiations

**Role** : Selection par l'operateur : Selection Filiations.
**Delegue a** : [Recherche Adresse Mail (IDE 308)](PVE-IDE-308.md)

---

#### <a id="t28"></a>414.5.1.2 - Selection Filiations

**Role** : Selection par l'operateur : Selection Filiations.
**Delegue a** : [Recherche Adresse Mail (IDE 308)](PVE-IDE-308.md)


### 3.4 Calcul (2 taches)

Calculs metier : montants, stocks, compteurs.

---

#### <a id="t5"></a>414.2.1.1 - Selection Pv_Compta

**Role** : Selection par l'operateur : Selection Pv_Compta.

---

#### <a id="t27"></a>414.5.1.1 - Load temp compta

**Role** : Traitement : Load temp compta.


### 3.5 Initialisation (1 tache)

Reinitialisation d'etats et variables de travail.

---

#### <a id="t32"></a>414.7 - RAZ TEMPO

**Role** : Reinitialisation : RAZ TEMPO.


### 3.6 Creation (1 tache)

Insertion de nouveaux enregistrements en base.

---

#### <a id="t36"></a>414.9 - CreationMail pour File Traitem

**Role** : Creation d'enregistrement : CreationMail pour File Traitem.
**Variables liees** : Q (P.File Name Signature)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Generate Preview OD==V4 (IDE 357)](PVE-IDE-357.md)
- **Appelle**: 7 programmes | **Tables**: 18 (W:9 R:6 L:9) | **Taches**: 36 | **Expressions**: 36

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (36 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **414.1** | [**Print Invoice** (414)](#t1) [mockup](#ecran-t1) | MDI | 640x65 | Impression |
| 414.1.1 | [EDITION (414.3)](#t12) | MDI | - | |
| 414.1.2 | [PRINT AGAIN (414.5)](#t25) [mockup](#ecran-t25) | MDI | 375x240 | |
| 414.1.3 | [Print Again Gener (414.5.1)](#t26) | MDI | - | |
| **414.2** | [**PARAMETERS** (414.1)](#t2) | MDI | - | Traitement |
| 414.2.1 | [Temp generation Gift Pass (414.2.1.1.1)](#t6) | MDI | - | |
| 414.2.2 | [Temp generation (414.2.1.1.2)](#t7) | MDI | - | |
| 414.2.3 | [Temp generation (414.2.1.1.3)](#t8) | MDI | - | |
| 414.2.4 | [Temp generation Gift Pass (414.2.1.1.4)](#t9) | MDI | - | |
| 414.2.5 | [Temp generation (414.2.2.1)](#t11) | MDI | - | |
| 414.2.6 | [Package line (414.3.1)](#t13) [mockup](#ecran-t13) | MDI | 557x327 | |
| 414.2.7 | [Package line (414.3.1.1)](#t14) | MDI | - | |
| 414.2.8 | [Package blank line (414.3.2)](#t15) | MDI | - | |
| 414.2.9 | [Filiations (414.3.3)](#t16) | MDI | - | |
| 414.2.10 | [Ski Shoes Name (414.3.3.1)](#t17) | MDI | - | |
| 414.2.11 | [HISTO (414.4)](#t18) | MDI | - | |
| 414.2.12 | [Generation (414.4.1)](#t19) | MDI | - | |
| 414.2.13 | [header (414.4.1.1)](#t20) | MDI | - | |
| 414.2.14 | [Entete EZcard (414.4.1.1.1)](#t21) | MDI | - | |
| 414.2.15 | [Lines (414.4.1.2)](#t22) | MDI | - | |
| 414.2.16 | [Package line (414.4.2)](#t23) | MDI | - | |
| 414.2.17 | [Ligne EZcard (414.4.2.1)](#t24) | MDI | - | |
| 414.2.18 | [Temp generation (414.5.1.2.1)](#t29) | MDI | - | |
| 414.2.19 | [Trace Again (414.5.2)](#t30) | MDI | - | |
| 414.2.20 | [CHECK HISTO (414.6)](#t31) | MDI | - | |
| 414.2.21 | [Package (414.7.1)](#t33) | MDI | - | |
| 414.2.22 | [Filiation (414.7.2)](#t34) | MDI | - | |
| 414.2.23 | [Search for Gift Pass (414.8)](#t35) [mockup](#ecran-t35) | - | 175x195 | |
| **414.3** | [**SELECTION** (414.2)](#t3) [mockup](#ecran-t3) | MDI | 640x0 | Consultation |
| 414.3.1 | [Selection Packages (414.2.1)](#t4) [mockup](#ecran-t4) | MDI | 814x0 | |
| 414.3.2 | [Selection Filiations (414.2.2)](#t10) | MDI | - | |
| 414.3.3 | [Selection Filiations (414.5.1.2)](#t28) | MDI | - | |
| **414.4** | [**Selection Pv_Compta** (414.2.1.1)](#t5) | MDI | - | Calcul |
| 414.4.1 | [Load temp compta (414.5.1.1)](#t27) | MDI | - | |
| **414.5** | [**RAZ TEMPO** (414.7)](#t32) | MDI | - | Initialisation |
| **414.6** | [**CreationMail pour File Traitem** (414.9)](#t36) | - | - | Creation |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Traitement principal]
    UPDATE[MAJ 9 tables]
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

### Tables utilisees (18)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 14 | transac_detail_bar |  | DB |   | **W** |   | 1 |
| 15 | transac_entete_bar |  | DB |   | **W** |   | 1 |
| 31 | gm-complet_______gmc |  | DB | R |   |   | 2 |
| 34 | hebergement______heb | Hebergement (chambres) | DB |   |   | L | 1 |
| 40 | comptable________cte |  | DB |   | **W** |   | 1 |
| 67 | tables___________tab |  | DB | R |   |   | 1 |
| 263 | vente | Donnees de ventes | DB |   |   | L | 1 |
| 377 | pv_contracts |  | DB | R |   |   | 1 |
| 382 | pv_discount_reasons |  | DB | R |   | L | 8 |
| 395 | pv_ownership |  | DB | R | **W** |   | 2 |
| 396 | pv_cust_packages |  | DB |   | **W** | L | 2 |
| 397 | pv_package_composants |  | DB |   | **W** |   | 1 |
| 400 | pv_cust_rentals |  | DB |   |   | L | 5 |
| 404 | pv_sellers_by_week |  | DB | R |   | L | 4 |
| 419 | realise_articles_caution | Articles et stock | DB |   |   | L | 3 |
| 531 | import_avertiss__an_val |  | DB |   | **W** | L | 4 |
| 533 | cumul_mvt_stock_histo | Articles et stock | TMP |   | **W** | L | 13 |
| 1501 | Table_1501 |  | MEM |   | **W** |   | 1 |

### Colonnes par table (10 / 14 tables avec colonnes identifiees)

<details>
<summary>Table 14 - transac_detail_bar (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 15 - transac_entete_bar (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 31 - gm-complet_______gmc (R) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | CautionExist | R | Logical |
| B | PrintLinePackagesInCurrentPage | R | Numeric |
| C | CurrentLinePackagesChrono | R | Numeric |
| D | TotalLinePackagesChrono | R | Numeric |
| E | PageNumber | R | Numeric |
| F | TotalLinePackages | R | Numeric |
| G | TotalTVA | R | Numeric |
| H | TotalTTCDiscounted | R | Numeric |
| I | TotalTo Pay | R | Numeric |
| J | TotalOnAccount | R | Numeric |
| K | ExisteMontantTva | R | Logical |
| L | AssuranceOnly | R | Logical |

</details>

<details>
<summary>Table 40 - comptable________cte (**W**) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | T OD ? | W | Logical |
| B | T Vente ? | W | Logical |

</details>

<details>
<summary>Table 67 - tables___________tab (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P. Payer XCust Id | R | Numeric |
| B | P. Customer Id | R | Numeric |
| C | P. Societe | R | Alpha |
| D | P. Compte | R | Numeric |
| E | P. Filiation | R | Numeric |
| F | P. Package id | R | Numeric |
| G | P. PrintAgain | R | Logical |
| H | P. Copies | R | Numeric |
| I | P. Total Ticket | R | Numeric |
| J | P. Total Crédit Conso | R | Numeric |
| K | P. EZcard | R | Alpha |
| L | P. Card type | R | Alpha |
| M | P. Service | R | Alpha |
| N | P.Societe | R | Alpha |
| O | P.Adherent | R | Numeric |
| P | P.Filiation | R | Numeric |
| Q | P.File Name Signature | R | Numeric |
| R | p.ValidationMail | R | Logical |
| S | P Adresse Mail (MOB) | R | Alpha |
| T | p.No_Facture | R | Numeric |
| U | PrintAgainPreview | R | Logical |
| V | V VillageCode | R | Alpha |
| W | V AmountFormat | R | Alpha |
| X | V VatValue | R | Numeric |
| Y | V Currency | R | Alpha |
| Z | V Decimal | R | Numeric |
| BA | PrintAgainExecution | R | Logical |
| BB | PrintAgainCopy | R | Numeric |
| BC | L ExistHistoric ? | R | Logical |
| BD | HeaderLine01 | R | Alpha |
| BE | HeaderLine02 | R | Alpha |
| BF | HeaderLine03 | R | Alpha |
| BG | HeaderLine04 | R | Alpha |
| BH | HeaderLine05 | R | Alpha |
| BI | HeaderLine06 | R | Alpha |
| BJ | HeaderLine07 | R | Alpha |
| BK | HeaderLine08 | R | Alpha |
| BL | HeaderLine09 | R | Alpha |
| BM | HeaderLine10 | R | Alpha |
| BN | HeaderLine11 | R | Alpha |
| BO | V Facture | R | Numeric |
| BP | v Solde Gift Pass | R | Numeric |
| BQ | v Existe Gift Pass | R | Logical |
| BR | v.Message Solde Gift Pass | R | Alpha |
| BS | V Nom Fic Pdf Ticket Mobilit | R | Alpha |
| BT | v Langue Mail | R | Alpha |
| BU | v Existe Vente Mobilité | R | Logical |
| BV | v Validation envoi mail ? | R | Logical |

</details>

<details>
<summary>Table 377 - pv_contracts (R) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 382 - pv_discount_reasons (R/L) - 8 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | -------------package OUT | R | Alpha |
| B | v lien Package Out | R | Logical |
| C | -------------rentals OUT | R | Alpha |
| D | -------------package IN | R | Alpha |
| E | v lien Package In | R | Logical |
| F | -------------rentals IN | R | Alpha |
| G | Libellé | R | Alpha |
| H | StartDate | R | Date |
| I | EndDate | R | Date |
| J | Days | R | Numeric |
| K | LibelléAssurance | R | Alpha |
| L | Iteration Edit Gift Pass | R | Numeric |

</details>

<details>
<summary>Table 395 - pv_ownership (R/**W**) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 396 - pv_cust_packages (**W**/L) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P. Payer XCust Id | W | Numeric |
| B | P. Customer Id | W | Numeric |
| C | CurrentLinePackagesChrono | W | Numeric |
| D | TotalLinePackagesChrono | W | Numeric |
| F | TotalLinePackages | W | Numeric |

</details>

<details>
<summary>Table 397 - pv_package_composants (**W**) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | -------------package OUT | W | Alpha |
| B | PrintLinePackagesInCurrentPage | W | Numeric |
| C | CurrentLinePackagesChrono | W | Numeric |
| D | TotalLinePackagesChrono | W | Numeric |
| E | v lien Package In | W | Logical |
| F | P. Package id | W | Numeric |

</details>

<details>
<summary>Table 404 - pv_sellers_by_week (R/L) - 4 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 531 - import_avertiss__an_val (**W**/L) - 4 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 533 - cumul_mvt_stock_histo (**W**/L) - 13 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| BC | L ExistHistoric ? | W | Logical |

</details>

<details>
<summary>Table 1501 - Table_1501 (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (20)

Variables recues du programme appelant ([Generate Preview OD==V4 (IDE 357)](PVE-IDE-357.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P. Payer XCust Id | Numeric | 2x parametre entrant |
| B | P. Customer Id | Numeric | 1x parametre entrant |
| C | P. Societe | Alpha | - |
| D | P. Compte | Numeric | - |
| E | P. Filiation | Numeric | - |
| F | P. Package id | Numeric | - |
| G | P. PrintAgain | Logical | 2x parametre entrant |
| H | P. Copies | Numeric | - |
| I | P. Total Ticket | Numeric | - |
| J | P. Total Crédit Conso | Numeric | - |
| K | P. EZcard | Alpha | - |
| L | P. Card type | Alpha | - |
| M | P. Service | Alpha | 1x parametre entrant |
| N | P.Societe | Alpha | - |
| O | P.Adherent | Numeric | - |
| P | P.Filiation | Numeric | - |
| Q | P.File Name Signature | Numeric | [414.3.3.1](#t17) |
| R | p.ValidationMail | Logical | 2x parametre entrant |
| S | P Adresse Mail (MOB) | Alpha | [414.9](#t36) |
| T | p.No_Facture | Numeric | - |

### 11.2 Variables de session (13)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| V | V VillageCode | Alpha | - |
| W | V AmountFormat | Alpha | - |
| X | V VatValue | Numeric | - |
| Y | V Currency | Alpha | - |
| Z | V Decimal | Numeric | - |
| BO | V Facture | Numeric | - |
| BP | v Solde Gift Pass | Numeric | - |
| BQ | v Existe Gift Pass | Logical | - |
| BR | v.Message Solde Gift Pass | Alpha | - |
| BS | V Nom Fic Pdf Ticket Mobilit | Alpha | - |
| BT | v Langue Mail | Alpha | - |
| BU | v Existe Vente Mobilité | Logical | - |
| BV | v Validation envoi mail ? | Logical | - |

### 11.3 Autres (15)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| U | PrintAgainPreview | Logical | - |
| BA | PrintAgainExecution | Logical | - |
| BB | PrintAgainCopy | Numeric | - |
| BC | L ExistHistoric ? | Logical | - |
| BD | HeaderLine01 | Alpha | - |
| BE | HeaderLine02 | Alpha | - |
| BF | HeaderLine03 | Alpha | - |
| BG | HeaderLine04 | Alpha | - |
| BH | HeaderLine05 | Alpha | - |
| BI | HeaderLine06 | Alpha | - |
| BJ | HeaderLine07 | Alpha | - |
| BK | HeaderLine08 | Alpha | - |
| BL | HeaderLine09 | Alpha | - |
| BM | HeaderLine10 | Alpha | - |
| BN | HeaderLine11 | Alpha | - |

<details>
<summary>Toutes les 48 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| P0 | **A** | P. Payer XCust Id | Numeric |
| P0 | **B** | P. Customer Id | Numeric |
| P0 | **C** | P. Societe | Alpha |
| P0 | **D** | P. Compte | Numeric |
| P0 | **E** | P. Filiation | Numeric |
| P0 | **F** | P. Package id | Numeric |
| P0 | **G** | P. PrintAgain | Logical |
| P0 | **H** | P. Copies | Numeric |
| P0 | **I** | P. Total Ticket | Numeric |
| P0 | **J** | P. Total Crédit Conso | Numeric |
| P0 | **K** | P. EZcard | Alpha |
| P0 | **L** | P. Card type | Alpha |
| P0 | **M** | P. Service | Alpha |
| P0 | **N** | P.Societe | Alpha |
| P0 | **O** | P.Adherent | Numeric |
| P0 | **P** | P.Filiation | Numeric |
| P0 | **Q** | P.File Name Signature | Numeric |
| P0 | **R** | p.ValidationMail | Logical |
| P0 | **S** | P Adresse Mail (MOB) | Alpha |
| P0 | **T** | p.No_Facture | Numeric |
| V. | **V** | V VillageCode | Alpha |
| V. | **W** | V AmountFormat | Alpha |
| V. | **X** | V VatValue | Numeric |
| V. | **Y** | V Currency | Alpha |
| V. | **Z** | V Decimal | Numeric |
| V. | **BO** | V Facture | Numeric |
| V. | **BP** | v Solde Gift Pass | Numeric |
| V. | **BQ** | v Existe Gift Pass | Logical |
| V. | **BR** | v.Message Solde Gift Pass | Alpha |
| V. | **BS** | V Nom Fic Pdf Ticket Mobilit | Alpha |
| V. | **BT** | v Langue Mail | Alpha |
| V. | **BU** | v Existe Vente Mobilité | Logical |
| V. | **BV** | v Validation envoi mail ? | Logical |
| Autre | **U** | PrintAgainPreview | Logical |
| Autre | **BA** | PrintAgainExecution | Logical |
| Autre | **BB** | PrintAgainCopy | Numeric |
| Autre | **BC** | L ExistHistoric ? | Logical |
| Autre | **BD** | HeaderLine01 | Alpha |
| Autre | **BE** | HeaderLine02 | Alpha |
| Autre | **BF** | HeaderLine03 | Alpha |
| Autre | **BG** | HeaderLine04 | Alpha |
| Autre | **BH** | HeaderLine05 | Alpha |
| Autre | **BI** | HeaderLine06 | Alpha |
| Autre | **BJ** | HeaderLine07 | Alpha |
| Autre | **BK** | HeaderLine08 | Alpha |
| Autre | **BL** | HeaderLine09 | Alpha |
| Autre | **BM** | HeaderLine10 | Alpha |
| Autre | **BN** | HeaderLine11 | Alpha |

</details>

## 12. EXPRESSIONS

**36 / 36 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CAST_LOGIQUE | 2 | 0 |
| CONSTANTE | 5 | 0 |
| FORMAT | 4 | 0 |
| CONDITION | 7 | 0 |
| NEGATION | 3 | 0 |
| OTHER | 12 | 0 |
| REFERENCE_VG | 1 | 0 |
| STRING | 1 | 0 |
| CONCATENATION | 1 | 0 |

### 12.2 Expressions cles par type

#### CAST_LOGIQUE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 21 | `VG32='TRUE'LOG AND VG33='TB'` | - |
| CAST_LOGIQUE | 3 | `Trim(P Adresse Mail (MOB) [S])&' / '&'Validation ='&IF(p.ValidationMail [R]='TRUE'LOG,'Vrai','Faux')` | - |

#### CONSTANTE (5 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 26 | `'Ticket has been generated, and will be send by an Email .'` | - |
| CONSTANTE | 27 | `'Ticket has been generated.'` | - |
| CONSTANTE | 14 | `'O'` | - |
| CONSTANTE | 2 | `1` | - |
| CONSTANTE | 13 | `'VSERV'` | - |

#### FORMAT (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| FORMAT | 6 | `FileRename (Trim(VG80)&Trim(Str(P.File Name Signature [Q],'6Z'))&'.gif',Trim(VG80)&Trim(Str([AO],'6Z'))&'.gif')` | - |
| FORMAT | 32 | `Trim(VG80)&Trim(Str([AO],'6Z'))&'.gif'` | - |
| FORMAT | 17 | `'Solde Free  Extra au : '&DStr(Date(),'DD/MM/YYYY')&' à : '&TStr(Time(),('HH:MM:SS'))` | - |
| FORMAT | 23 | `'Receipt_'&Trim(P. Service [M])&'_'&Trim(Str([AO],'6Z'))&'_'&DStr(Date(),'YYYYMMDD')&'.pdf'` | - |

#### CONDITION (7 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 24 | `VG32 AND VG33='WS'` | - |
| CONDITION | 35 | `VG32 AND VG33='TB'` | - |
| CONDITION | 33 | `Trim(P Adresse Mail (MOB) [S])=''` | - |
| CONDITION | 11 | `GetParam ('SERVICE')='SKIN'` | - |
| CONDITION | 1 | `P. Payer XCust Id [A]=0` | - |
| ... | | *+2 autres* | |

#### NEGATION (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| NEGATION | 12 | `NOT (GetParam ('SERVICE')='SKIN')` | - |
| NEGATION | 10 | `NOT ([AC])` | - |
| NEGATION | 7 | `NOT (P. PrintAgain [G])` | - |

#### OTHER (12 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 30 | `P. Payer XCust Id [A]` | - |
| OTHER | 29 | `NOT([AZ])` | - |
| OTHER | 28 | `[AZ]` | - |
| OTHER | 36 | `FileDelete(ExpCalc('32'EXP))` | - |
| OTHER | 34 | `p.ValidationMail [R]` | - |
| ... | | *+7 autres* | |

#### REFERENCE_VG (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 18 | `VG29` | - |

#### STRING (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| STRING | 20 | `FileDelete (Trim([AW]))` | - |

#### CONCATENATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 22 | `INIGet ('[MAGIC_LOGICAL_NAMES]club_exportdata')&'Ticket\'&Trim([AW])` | - |

### 12.3 Toutes les expressions (36)

<details>
<summary>Voir les 36 expressions</summary>

#### CAST_LOGIQUE (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 3 | `Trim(P Adresse Mail (MOB) [S])&' / '&'Validation ='&IF(p.ValidationMail [R]='TRUE'LOG,'Vrai','Faux')` |
| 21 | `VG32='TRUE'LOG AND VG33='TB'` |

#### CONSTANTE (5)

| IDE | Expression Decodee |
|-----|-------------------|
| 2 | `1` |
| 13 | `'VSERV'` |
| 14 | `'O'` |
| 26 | `'Ticket has been generated, and will be send by an Email .'` |
| 27 | `'Ticket has been generated.'` |

#### FORMAT (4)

| IDE | Expression Decodee |
|-----|-------------------|
| 17 | `'Solde Free  Extra au : '&DStr(Date(),'DD/MM/YYYY')&' à : '&TStr(Time(),('HH:MM:SS'))` |
| 23 | `'Receipt_'&Trim(P. Service [M])&'_'&Trim(Str([AO],'6Z'))&'_'&DStr(Date(),'YYYYMMDD')&'.pdf'` |
| 6 | `FileRename (Trim(VG80)&Trim(Str(P.File Name Signature [Q],'6Z'))&'.gif',Trim(VG80)&Trim(Str([AO],'6Z'))&'.gif')` |
| 32 | `Trim(VG80)&Trim(Str([AO],'6Z'))&'.gif'` |

#### CONDITION (7)

| IDE | Expression Decodee |
|-----|-------------------|
| 1 | `P. Payer XCust Id [A]=0` |
| 4 | `DbRecs ('{533,3}'DSOURCE,'')=0` |
| 5 | `DbRecs ('{533,3}'DSOURCE,'')>0` |
| 11 | `GetParam ('SERVICE')='SKIN'` |
| 24 | `VG32 AND VG33='WS'` |
| 35 | `VG32 AND VG33='TB'` |
| 33 | `Trim(P Adresse Mail (MOB) [S])=''` |

#### NEGATION (3)

| IDE | Expression Decodee |
|-----|-------------------|
| 7 | `NOT (P. PrintAgain [G])` |
| 10 | `NOT ([AC])` |
| 12 | `NOT (GetParam ('SERVICE')='SKIN')` |

#### OTHER (12)

| IDE | Expression Decodee |
|-----|-------------------|
| 8 | `P. PrintAgain [G]` |
| 9 | `[AA]` |
| 15 | `GetParam('SERVICE')` |
| 16 | `NOT(VG20)` |
| 19 | `[AU]` |
| 25 | `SetCrsr (1)` |
| 28 | `[AZ]` |
| 29 | `NOT([AZ])` |
| 30 | `P. Payer XCust Id [A]` |
| 31 | `P. Customer Id [B]` |
| 34 | `p.ValidationMail [R]` |
| 36 | `FileDelete(ExpCalc('32'EXP))` |

#### REFERENCE_VG (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 18 | `VG29` |

#### STRING (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 20 | `FileDelete (Trim([AW]))` |

#### CONCATENATION (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 22 | `INIGet ('[MAGIC_LOGICAL_NAMES]club_exportdata')&'Ticket\'&Trim([AW])` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Generate Preview OD==V4 (IDE 357)](PVE-IDE-357.md) -> **Print Invoice or Ticket==V4 (IDE 414)**

```mermaid
graph LR
    T414[414 Print Invoice or T...]
    style T414 fill:#58a6ff
    CC357[357 Generate Preview O...]
    style CC357 fill:#8b5cf6
    CC357 --> T414
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [357](PVE-IDE-357.md) | Generate Preview OD==V4 | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T414[414 Print Invoice or T...]
    style T414 fill:#58a6ff
    C280[280 Edition ticket Tva]
    T414 --> C280
    style C280 fill:#3fb950
    C232[232 Existe Vente Mobilité]
    T414 --> C232
    style C232 fill:#3fb950
    C273[273 Edition ticket]
    T414 --> C273
    style C273 fill:#3fb950
    C278[278 Set Customer]
    T414 --> C278
    style C278 fill:#3fb950
    C308[308 Recherche Adresse ...]
    T414 --> C308
    style C308 fill:#3fb950
    C314[314 Get default email ...]
    T414 --> C314
    style C314 fill:#3fb950
    C365[365 Saisie Signature]
    T414 --> C365
    style C365 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [280](PVE-IDE-280.md) | Edition ticket (Tva) | 2 | Impression ticket/document |
| [232](PVE-IDE-232.md) | Existe Vente Mobilité | 1 | Sous-programme |
| [273](PVE-IDE-273.md) | Edition ticket | 1 | Impression ticket/document |
| [278](PVE-IDE-278.md) | Set Customer | 1 | Sous-programme |
| [308](PVE-IDE-308.md) | Recherche Adresse Mail | 1 | Sous-programme |
| [314](PVE-IDE-314.md) | Get default email address | 1 | Recuperation donnees |
| [365](PVE-IDE-365.md) | Saisie Signature | 1 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 1182 | Programme volumineux |
| Expressions | 36 | Peu de logique |
| Tables WRITE | 9 | Fort impact donnees |
| Sous-programmes | 7 | Dependances moderees |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 3.2% (38 / 1182) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Impression (4 taches: 2 ecrans, 2 traitements)

- **Strategie** : Templates HTML -> PDF via wkhtmltopdf ou Puppeteer.
- `PrintService` injectable avec choix imprimante

#### Traitement (24 taches: 2 ecrans, 22 traitements)

- **Strategie** : Orchestrateur avec 2 ecrans (Razor/React) et 22 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 7 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Consultation (4 taches: 2 ecrans, 2 traitements)

- **Strategie** : Composants de recherche/selection en modales.
- 2 ecrans : SELECTION, Selection Packages

#### Calcul (2 taches: 0 ecran, 2 traitements)

- **Strategie** : Services de calcul purs (Domain Services).
- Migrer la logique de calcul (stock, compteurs, montants)

#### Initialisation (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Constructeur/methode `InitAsync()` dans l'orchestrateur.

#### Creation (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Repository pattern avec Entity Framework Core.
- Insertion via `IRepository<T>.CreateAsync()`

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| transac_detail_bar | Table WRITE (Database) | 1x | Schema + repository |
| transac_entete_bar | Table WRITE (Database) | 1x | Schema + repository |
| comptable________cte | Table WRITE (Database) | 1x | Schema + repository |
| pv_ownership | Table WRITE (Database) | 1x | Schema + repository |
| pv_cust_packages | Table WRITE (Database) | 1x | Schema + repository |
| pv_package_composants | Table WRITE (Database) | 1x | Schema + repository |
| import_avertiss__an_val | Table WRITE (Database) | 3x | Schema + repository |
| cumul_mvt_stock_histo | Table WRITE (Temp) | 7x | Schema + repository |
| Table_1501 | Table WRITE (Memory) | 1x | Schema + repository |
| [Edition ticket (Tva) (IDE 280)](PVE-IDE-280.md) | Sous-programme | 2x | Haute - Impression ticket/document |
| [Recherche Adresse Mail (IDE 308)](PVE-IDE-308.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Get default email address (IDE 314)](PVE-IDE-314.md) | Sous-programme | 1x | Normale - Recuperation donnees |
| [Saisie Signature (IDE 365)](PVE-IDE-365.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Existe Vente Mobilité (IDE 232)](PVE-IDE-232.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Edition ticket (IDE 273)](PVE-IDE-273.md) | Sous-programme | 1x | Normale - Impression ticket/document |
| [Set Customer (IDE 278)](PVE-IDE-278.md) | Sous-programme | 1x | Normale - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 20:01*
