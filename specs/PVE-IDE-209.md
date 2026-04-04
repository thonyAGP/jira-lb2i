# PVE IDE 209 - Print Invoice or Ticket-664

> **Analyse**: Phases 1-4 2026-02-03 18:55 -> 18:55 (16s) | Assemblage 18:55
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PVE |
| IDE Position | 209 |
| Nom Programme | Print Invoice or Ticket-664 |
| Fichier source | `Prg_209.xml` |
| Dossier IDE | Mobile |
| Taches | 51 (0 ecrans visibles) |
| Tables modifiees | 14 |
| Programmes appeles | 13 |

## 2. DESCRIPTION FONCTIONNELLE

**Print Invoice or Ticket-664** assure la gestion complete de ce processus, accessible depuis [Generate Preview Payments (IDE 189)](PVE-IDE-189.md), [Choice Re_Print Invoice (IDE 204)](PVE-IDE-204.md), [Generate Preview Payments 1212 (IDE 434)](PVE-IDE-434.md), [Generate Preview Payments 1112 (IDE 435)](PVE-IDE-435.md), [Generate Preview Payments 1012 (IDE 436)](PVE-IDE-436.md), [Generate Preview Payment 1212E (IDE 437)](PVE-IDE-437.md).

Le flux de traitement s'organise en **7 blocs fonctionnels** :

- **Traitement** (33 taches) : traitements metier divers
- **Consultation** (7 taches) : ecrans de recherche, selection et consultation
- **Impression** (4 taches) : generation de tickets et documents
- **Creation** (3 taches) : insertion d'enregistrements en base (mouvements, prestations)
- **Calcul** (2 taches) : calculs de montants, stocks ou compteurs
- **Initialisation** (1 tache) : reinitialisation d'etats et de variables de travail
- **Validation** (1 tache) : controles et verifications de coherence

**Donnees modifiees** : 14 tables en ecriture (transac_detail_bar, transac_entete_bar, comptable________cte, pv_ownership, pv_cust_packages, pv_package_composants, pv_sellers_by_week, import_avertiss__an_val, cumul_mvt_stock_histo, pms_chained_listing, arc_tai_gm, Affectation_Gift_Pass, Table_1501, Table_1548).

**Logique metier** : 1 regles identifiees couvrant conditions metier.

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Impression (4 taches)

- **209** - Print Invoice **[[ECRAN]](#ecran-t1)**
- **209.10.1** - EDITION **[[ECRAN]](#ecran-t18)**
- **209.4** - PRINT AGAIN **[[ECRAN]](#ecran-t33)**
- **209.4.1** - Print Again Gener

Delegue a : [Creation pied Ticket(Tva) (IDE 281)](PVE-IDE-281.md), [Print label code barre DIN (IDE 113)](PVE-IDE-113.md), [Edition ticket (Tva) LEX (IDE 205)](PVE-IDE-205.md), [Edition ticket (Tva) (IDE 206)](PVE-IDE-206.md)

#### Phase 2 : Traitement (33 taches)

- **209.1** - PARAMETERS
- **209.2.1.1.1** - Temp generation Gift Pass
- **209.2.1.1.2** - Temp generation
- **209.2.1.1.3** - Temp generation
- **209.2.1.1.4** - Temp generation Gift Pass
- **209.2.1.2** - AddAppointmentToList
- **209.2.1.4.1** - AddAppointmentToList
- **209.2.2.1** - Temp gen 2
- **209.2.3.1** - Temp generation
- **209.10.1.1** - Package line **[[ECRAN]](#ecran-t19)**
- **209.10.1.1.1** - Package line
- **209.10.1.2** - Package blank line
- **209.10.1.3** - Filiations **[[ECRAN]](#ecran-t22)**
- **209.10.1.3.1** - Rental type ski
- **209.10.1.4** - Editer TVA
- **209.3** - HISTO
- **209.3.1** - Generation
- **209.3.1.1** - Get header Id
- **209.3.1.3** - Entete Club Med Pass
- **209.3.1.4** - Lines
- **209.3.2** - Package line
- **209.3.2.1** - Club Med Pass
- **209.4.1.2.1** - Temp gen 2
- **209.4.1.3.1** - Temp generation
- **209.4.2** - Trace Again
- **209.5** - CHECK HISTO
- **209.8** - Generation CGV Files
- **209.9** - Save File in DB
- **209.10** - (sans nom)
- **209.11** - Search for Gift Pass **[[ECRAN]](#ecran-t54)**
- **209.12.1** - Package
- **209.12.2** - Filiation
- **209.12.3** - Filiations new **[[ECRAN]](#ecran-t59)**

Delegue a : [TraceLogBooker (IDE 175)](PVE-IDE-175.md), [CancelAppointment (IDE 159)](PVE-IDE-159.md), [AddPaymentToOrder (IDE 169)](PVE-IDE-169.md), [GetLocationPaymentSettings (IDE 174)](PVE-IDE-174.md), [AddSpecialToOrder-392 (IDE 170)](PVE-IDE-170.md), [Set Village Address (IDE 277)](PVE-IDE-277.md), [Set Customer (IDE 278)](PVE-IDE-278.md), [Search  for messages (IDE 279)](PVE-IDE-279.md), [SynchronisationRecuPDF (IDE 320)](PVE-IDE-320.md)

#### Phase 3 : Consultation (7 taches)

- **209.2** - SELECTION **[[ECRAN]](#ecran-t3)**
- **209.2.1** - Selection Packages **[[ECRAN]](#ecran-t4)**
- **209.2.1.4** - Selection Packages **[[ECRAN]](#ecran-t12)**
- **209.2.2** - Selection Filiations
- **209.2.3** - Selection Filiations
- **209.4.1.2** - Selection Filiations
- **209.4.1.3** - Selection Filiations

Delegue a : [GetLocationPaymentSettings (IDE 174)](PVE-IDE-174.md), [SynchronisationRecuPDF (IDE 320)](PVE-IDE-320.md)

#### Phase 4 : Calcul (2 taches)

- **209.2.1.1** - Selection Pv_Compta
- **209.4.1.1** - Load temp compta

#### Phase 5 : Validation (1 tache)

- **209.2.1.3** - Validate/Cancel Booker

#### Phase 6 : Creation (3 taches)

- **209.3.1.2** - Create Header SQL
- **209.6** - CreationMail pour File Traitem
- **209.7** - CreationMail File Traitem 2

#### Phase 7 : Initialisation (1 tache)

- **209.12** - RAZ TEMPO

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| cumul_mvt_stock_histo | **W**/L (14 usages) | Articles et stock |
| import_avertiss__an_val | **W**/L (5 usages) |  |
| pms_chained_listing | **W**/L (4 usages) |  |
| pv_sellers_by_week | **W**/L (3 usages) |  |
| Table_1548 | **W** (3 usages) |  |
| pv_ownership | R/**W** (2 usages) |  |
| Table_1501 | **W** (2 usages) |  |
| arc_tai_gm | **W**/L (2 usages) |  |
| pv_cust_packages | **W**/L (2 usages) |  |
| pv_package_composants | **W** (1 usages) |  |
| Affectation_Gift_Pass | **W** (1 usages) |  |
| transac_entete_bar | **W** (1 usages) |  |
| transac_detail_bar | **W** (1 usages) |  |
| comptable________cte | **W** (1 usages) |  |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Impression (4 taches)

Generation des documents et tickets.

---

#### <a id="t1"></a>209 - Print Invoice [[ECRAN]](#ecran-t1)

**Role** : Generation du document : Print Invoice.
**Ecran** : 869 x 291 DLU (MDI) | [Voir mockup](#ecran-t1)

<details>
<summary>3 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [209.10.1](#t18) | EDITION **[[ECRAN]](#ecran-t18)** | Impression |
| [209.4](#t33) | PRINT AGAIN **[[ECRAN]](#ecran-t33)** | Impression |
| [209.4.1](#t34) | Print Again Gener | Impression |

</details>
**Variables liees** : G (P. PrintAgain), T (P.PrintAgainPreview), BG (PrintAgainExecution), BH (PrintAgainCopy)
**Delegue a** : [Creation pied Ticket(Tva) (IDE 281)](PVE-IDE-281.md), [Print label code barre DIN (IDE 113)](PVE-IDE-113.md), [Edition ticket (Tva) LEX (IDE 205)](PVE-IDE-205.md)

---

#### <a id="t18"></a>209.10.1 - EDITION [[ECRAN]](#ecran-t18)

**Role** : Generation du document : EDITION.
**Ecran** : 287 x 168 DLU (MDI) | [Voir mockup](#ecran-t18)
**Variables liees** : CH (v.Edition mobilité ?)
**Delegue a** : [Creation pied Ticket(Tva) (IDE 281)](PVE-IDE-281.md), [Print label code barre DIN (IDE 113)](PVE-IDE-113.md), [Edition ticket (Tva) LEX (IDE 205)](PVE-IDE-205.md)

---

#### <a id="t33"></a>209.4 - PRINT AGAIN [[ECRAN]](#ecran-t33)

**Role** : Generation du document : PRINT AGAIN.
**Ecran** : 375 x 240 DLU (MDI) | [Voir mockup](#ecran-t33)
**Variables liees** : G (P. PrintAgain), T (P.PrintAgainPreview), BG (PrintAgainExecution), BH (PrintAgainCopy)
**Delegue a** : [Creation pied Ticket(Tva) (IDE 281)](PVE-IDE-281.md), [Print label code barre DIN (IDE 113)](PVE-IDE-113.md), [Edition ticket (Tva) LEX (IDE 205)](PVE-IDE-205.md)

---

#### <a id="t34"></a>209.4.1 - Print Again Gener

**Role** : Generation du document : Print Again Gener.
**Variables liees** : G (P. PrintAgain), T (P.PrintAgainPreview), BG (PrintAgainExecution), BH (PrintAgainCopy)
**Delegue a** : [Creation pied Ticket(Tva) (IDE 281)](PVE-IDE-281.md), [Print label code barre DIN (IDE 113)](PVE-IDE-113.md), [Edition ticket (Tva) LEX (IDE 205)](PVE-IDE-205.md)


### 3.2 Traitement (33 taches)

Traitements internes.

---

#### <a id="t2"></a>209.1 - PARAMETERS

**Role** : Traitement : PARAMETERS.

---

#### <a id="t6"></a>209.2.1.1.1 - Temp generation Gift Pass

**Role** : Calcul fidelite/avantage : Temp generation Gift Pass.
**Variables liees** : J (P. Club Med Pass), BV (v Solde Gift Pass), BW (v Existe Gift Pass), BX (v.Message Solde Gift Pass)

---

#### <a id="t7"></a>209.2.1.1.2 - Temp generation

**Role** : Traitement : Temp generation.

---

#### <a id="t8"></a>209.2.1.1.3 - Temp generation

**Role** : Traitement : Temp generation.

---

#### <a id="t9"></a>209.2.1.1.4 - Temp generation Gift Pass

**Role** : Calcul fidelite/avantage : Temp generation Gift Pass.
**Variables liees** : J (P. Club Med Pass), BV (v Solde Gift Pass), BW (v Existe Gift Pass), BX (v.Message Solde Gift Pass)

---

#### <a id="t10"></a>209.2.1.2 - AddAppointmentToList

**Role** : Traitement : AddAppointmentToList.

---

#### <a id="t13"></a>209.2.1.4.1 - AddAppointmentToList

**Role** : Traitement : AddAppointmentToList.

---

#### <a id="t15"></a>209.2.2.1 - Temp gen 2

**Role** : Traitement : Temp gen 2.

---

#### <a id="t17"></a>209.2.3.1 - Temp generation

**Role** : Traitement : Temp generation.

---

#### <a id="t19"></a>209.10.1.1 - Package line [[ECRAN]](#ecran-t19)

**Role** : Traitement : Package line.
**Ecran** : 557 x 327 DLU (MDI) | [Voir mockup](#ecran-t19)
**Variables liees** : F (P. Package id), BJ (HeaderLine01), BK (HeaderLine02), BL (HeaderLine03), BM (HeaderLine04)

---

#### <a id="t20"></a>209.10.1.1.1 - Package line

**Role** : Traitement : Package line.
**Variables liees** : F (P. Package id), BJ (HeaderLine01), BK (HeaderLine02), BL (HeaderLine03), BM (HeaderLine04)

---

#### <a id="t21"></a>209.10.1.2 - Package blank line

**Role** : Traitement : Package blank line.
**Variables liees** : F (P. Package id), BJ (HeaderLine01), BK (HeaderLine02), BL (HeaderLine03), BM (HeaderLine04)

---

#### <a id="t22"></a>209.10.1.3 - Filiations [[ECRAN]](#ecran-t22)

**Role** : Traitement : Filiations.
**Ecran** : 924 x 557 DLU (MDI) | [Voir mockup](#ecran-t22)

---

#### <a id="t23"></a>209.10.1.3.1 - Rental type ski

**Role** : Traitement : Rental type ski.
**Variables liees** : K (P. Card type), CD (v.NbrRentals)

---

#### <a id="t24"></a>209.10.1.4 - Editer TVA

**Role** : Traitement : Editer TVA.

---

#### <a id="t25"></a>209.3 - HISTO

**Role** : Traitement : HISTO.
**Variables liees** : BI (L ExistHistoric ?)

---

#### <a id="t26"></a>209.3.1 - Generation

**Role** : Traitement : Generation.

---

#### <a id="t27"></a>209.3.1.1 - Get header Id

**Role** : Consultation/chargement : Get header Id.
**Variables liees** : CF (V.header_chrono), BJ (HeaderLine01), BK (HeaderLine02), BL (HeaderLine03), BM (HeaderLine04)

---

#### <a id="t29"></a>209.3.1.3 - Entete Club Med Pass

**Role** : Traitement : Entete Club Med Pass.
**Variables liees** : J (P. Club Med Pass), BV (v Solde Gift Pass), BW (v Existe Gift Pass), BX (v.Message Solde Gift Pass)

---

#### <a id="t30"></a>209.3.1.4 - Lines

**Role** : Traitement : Lines.

---

#### <a id="t31"></a>209.3.2 - Package line

**Role** : Traitement : Package line.
**Variables liees** : F (P. Package id), BJ (HeaderLine01), BK (HeaderLine02), BL (HeaderLine03), BM (HeaderLine04)

---

#### <a id="t32"></a>209.3.2.1 - Club Med Pass

**Role** : Traitement : Club Med Pass.
**Variables liees** : J (P. Club Med Pass), BV (v Solde Gift Pass), BW (v Existe Gift Pass), BX (v.Message Solde Gift Pass)

---

#### <a id="t37"></a>209.4.1.2.1 - Temp gen 2

**Role** : Traitement : Temp gen 2.

---

#### <a id="t39"></a>209.4.1.3.1 - Temp generation

**Role** : Traitement : Temp generation.

---

#### <a id="t40"></a>209.4.2 - Trace Again

**Role** : Traitement : Trace Again.
**Variables liees** : G (P. PrintAgain), T (P.PrintAgainPreview), BG (PrintAgainExecution), BH (PrintAgainCopy)

---

#### <a id="t41"></a>209.5 - CHECK HISTO

**Role** : Traitement : CHECK HISTO.
**Variables liees** : BI (L ExistHistoric ?)

---

#### <a id="t49"></a>209.8 - Generation CGV Files

**Role** : Traitement : Generation CGV Files.

---

#### <a id="t50"></a>209.9 - Save File in DB

**Role** : Traitement : Save File in DB.
**Variables liees** : P (P.File Name Signature mobilité), CE (v.CGV_FileName), CG (V.receipt_file)

---

#### <a id="t51"></a>209.10 - (sans nom)

**Role** : Traitement interne.

---

#### <a id="t54"></a>209.11 - Search for Gift Pass [[ECRAN]](#ecran-t54)

**Role** : Calcul fidelite/avantage : Search for Gift Pass.
**Ecran** : 175 x 195 DLU | [Voir mockup](#ecran-t54)
**Variables liees** : J (P. Club Med Pass), BV (v Solde Gift Pass), BW (v Existe Gift Pass), BX (v.Message Solde Gift Pass)

---

#### <a id="t57"></a>209.12.1 - Package

**Role** : Traitement : Package.
**Variables liees** : F (P. Package id)

---

#### <a id="t58"></a>209.12.2 - Filiation

**Role** : Traitement : Filiation.
**Variables liees** : E (P. Filiation), O (P.Filiation)

---

#### <a id="t59"></a>209.12.3 - Filiations new [[ECRAN]](#ecran-t59)

**Role** : Traitement : Filiations new.
**Ecran** : 438 x 195 DLU | [Voir mockup](#ecran-t59)


### 3.3 Consultation (7 taches)

Ecrans de recherche et consultation.

---

#### <a id="t3"></a>209.2 - SELECTION [[ECRAN]](#ecran-t3)

**Role** : Selection par l'operateur : SELECTION.
**Ecran** : 640 x 0 DLU (MDI) | [Voir mockup](#ecran-t3)

---

#### <a id="t4"></a>209.2.1 - Selection Packages [[ECRAN]](#ecran-t4)

**Role** : Selection par l'operateur : Selection Packages.
**Ecran** : 814 x 0 DLU (MDI) | [Voir mockup](#ecran-t4)

---

#### <a id="t12"></a>209.2.1.4 - Selection Packages [[ECRAN]](#ecran-t12)

**Role** : Selection par l'operateur : Selection Packages.
**Ecran** : 814 x 0 DLU (MDI) | [Voir mockup](#ecran-t12)

---

#### <a id="t14"></a>209.2.2 - Selection Filiations

**Role** : Selection par l'operateur : Selection Filiations.

---

#### <a id="t16"></a>209.2.3 - Selection Filiations

**Role** : Selection par l'operateur : Selection Filiations.

---

#### <a id="t36"></a>209.4.1.2 - Selection Filiations

**Role** : Selection par l'operateur : Selection Filiations.

---

#### <a id="t38"></a>209.4.1.3 - Selection Filiations

**Role** : Selection par l'operateur : Selection Filiations.


### 3.4 Calcul (2 taches)

Calculs metier : montants, stocks, compteurs.

---

#### <a id="t5"></a>209.2.1.1 - Selection Pv_Compta

**Role** : Selection par l'operateur : Selection Pv_Compta.

---

#### <a id="t35"></a>209.4.1.1 - Load temp compta

**Role** : Traitement : Load temp compta.


### 3.5 Validation (1 tache)

Controles de coherence : 1 tache verifie les donnees et conditions.

---

#### <a id="t11"></a>209.2.1.3 - Validate/Cancel Booker

**Role** : Verification : Validate/Cancel Booker.


### 3.6 Creation (3 taches)

Insertion de nouveaux enregistrements en base.

---

#### <a id="t28"></a>209.3.1.2 - Create Header SQL

**Role** : Traitement : Create Header SQL.
**Variables liees** : CF (V.header_chrono), BJ (HeaderLine01), BK (HeaderLine02), BL (HeaderLine03), BM (HeaderLine04)

---

#### <a id="t47"></a>209.6 - CreationMail pour File Traitem

**Role** : Creation d'enregistrement : CreationMail pour File Traitem.
**Variables liees** : P (P.File Name Signature mobilité), CE (v.CGV_FileName), CG (V.receipt_file), CM (v.Total pour affich M&E)
**Delegue a** : [Creation pied Ticket(Tva) (IDE 281)](PVE-IDE-281.md)

---

#### <a id="t48"></a>209.7 - CreationMail File Traitem 2

**Role** : Creation d'enregistrement : CreationMail File Traitem 2.
**Variables liees** : P (P.File Name Signature mobilité), CE (v.CGV_FileName), CG (V.receipt_file)
**Delegue a** : [Creation pied Ticket(Tva) (IDE 281)](PVE-IDE-281.md)


### 3.7 Initialisation (1 tache)

Reinitialisation d'etats et variables de travail.

---

#### <a id="t56"></a>209.12 - RAZ TEMPO

**Role** : Reinitialisation : RAZ TEMPO.


## 5. REGLES METIER

1 regles identifiees:

### Autres (1 regles)

#### <a id="rm-RM-001"></a>[RM-001] Si VG33='TB' alors v Solde Gift Pass [BV] sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `VG33='TB'` |
| **Si vrai** | v Solde Gift Pass [BV] |
| **Si faux** | '') |
| **Variables** | BV (v Solde Gift Pass) |
| **Expression source** | Expression 16 : `IF(VG33='TB',v Solde Gift Pass [BV],'')
` |
| **Exemple** | Si VG33='TB' â†’ v Solde Gift Pass [BV]. Sinon â†’ '') |

## 6. CONTEXTE

- **Appele par**: [Generate Preview Payments (IDE 189)](PVE-IDE-189.md), [Choice Re_Print Invoice (IDE 204)](PVE-IDE-204.md), [Generate Preview Payments 1212 (IDE 434)](PVE-IDE-434.md), [Generate Preview Payments 1112 (IDE 435)](PVE-IDE-435.md), [Generate Preview Payments 1012 (IDE 436)](PVE-IDE-436.md), [Generate Preview Payment 1212E (IDE 437)](PVE-IDE-437.md)
- **Appelle**: 13 programmes | **Tables**: 32 (W:14 R:7 L:19) | **Taches**: 51 | **Expressions**: 40

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (51 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **209.1** | [**Print Invoice** (209)](#t1) [mockup](#ecran-t1) | MDI | 869x291 | Impression |
| 209.1.1 | [EDITION (209.10.1)](#t18) [mockup](#ecran-t18) | MDI | 287x168 | |
| 209.1.2 | [PRINT AGAIN (209.4)](#t33) [mockup](#ecran-t33) | MDI | 375x240 | |
| 209.1.3 | [Print Again Gener (209.4.1)](#t34) | MDI | - | |
| **209.2** | [**PARAMETERS** (209.1)](#t2) | MDI | - | Traitement |
| 209.2.1 | [Temp generation Gift Pass (209.2.1.1.1)](#t6) | MDI | - | |
| 209.2.2 | [Temp generation (209.2.1.1.2)](#t7) | MDI | - | |
| 209.2.3 | [Temp generation (209.2.1.1.3)](#t8) | MDI | - | |
| 209.2.4 | [Temp generation Gift Pass (209.2.1.1.4)](#t9) | MDI | - | |
| 209.2.5 | [AddAppointmentToList (209.2.1.2)](#t10) | MDI | - | |
| 209.2.6 | [AddAppointmentToList (209.2.1.4.1)](#t13) | MDI | - | |
| 209.2.7 | [Temp gen 2 (209.2.2.1)](#t15) | - | - | |
| 209.2.8 | [Temp generation (209.2.3.1)](#t17) | MDI | - | |
| 209.2.9 | [Package line (209.10.1.1)](#t19) [mockup](#ecran-t19) | MDI | 557x327 | |
| 209.2.10 | [Package line (209.10.1.1.1)](#t20) | MDI | - | |
| 209.2.11 | [Package blank line (209.10.1.2)](#t21) | MDI | - | |
| 209.2.12 | [Filiations (209.10.1.3)](#t22) [mockup](#ecran-t22) | MDI | 924x557 | |
| 209.2.13 | [Rental type ski (209.10.1.3.1)](#t23) | - | - | |
| 209.2.14 | [Editer TVA (209.10.1.4)](#t24) | - | - | |
| 209.2.15 | [HISTO (209.3)](#t25) | MDI | - | |
| 209.2.16 | [Generation (209.3.1)](#t26) | MDI | - | |
| 209.2.17 | [Get header Id (209.3.1.1)](#t27) | - | - | |
| 209.2.18 | [Entete Club Med Pass (209.3.1.3)](#t29) | MDI | - | |
| 209.2.19 | [Lines (209.3.1.4)](#t30) | MDI | - | |
| 209.2.20 | [Package line (209.3.2)](#t31) | MDI | - | |
| 209.2.21 | [Club Med Pass (209.3.2.1)](#t32) | MDI | - | |
| 209.2.22 | [Temp gen 2 (209.4.1.2.1)](#t37) | - | - | |
| 209.2.23 | [Temp generation (209.4.1.3.1)](#t39) | MDI | - | |
| 209.2.24 | [Trace Again (209.4.2)](#t40) | MDI | - | |
| 209.2.25 | [CHECK HISTO (209.5)](#t41) | MDI | - | |
| 209.2.26 | [Generation CGV Files (209.8)](#t49) | - | - | |
| 209.2.27 | [Save File in DB (209.9)](#t50) | - | - | |
| 209.2.28 | [(sans nom) (209.10)](#t51) | - | - | |
| 209.2.29 | [Search for Gift Pass (209.11)](#t54) [mockup](#ecran-t54) | - | 175x195 | |
| 209.2.30 | [Package (209.12.1)](#t57) | MDI | - | |
| 209.2.31 | [Filiation (209.12.2)](#t58) | MDI | - | |
| 209.2.32 | [Filiations new (209.12.3)](#t59) [mockup](#ecran-t59) | - | 438x195 | |
| **209.3** | [**SELECTION** (209.2)](#t3) [mockup](#ecran-t3) | MDI | 640x0 | Consultation |
| 209.3.1 | [Selection Packages (209.2.1)](#t4) [mockup](#ecran-t4) | MDI | 814x0 | |
| 209.3.2 | [Selection Packages (209.2.1.4)](#t12) [mockup](#ecran-t12) | MDI | 814x0 | |
| 209.3.3 | [Selection Filiations (209.2.2)](#t14) | MDI | - | |
| 209.3.4 | [Selection Filiations (209.2.3)](#t16) | MDI | - | |
| 209.3.5 | [Selection Filiations (209.4.1.2)](#t36) | MDI | - | |
| 209.3.6 | [Selection Filiations (209.4.1.3)](#t38) | MDI | - | |
| **209.4** | [**Selection Pv_Compta** (209.2.1.1)](#t5) | MDI | - | Calcul |
| 209.4.1 | [Load temp compta (209.4.1.1)](#t35) | MDI | - | |
| **209.5** | [**Validate/Cancel Booker** (209.2.1.3)](#t11) | MDI | - | Validation |
| **209.6** | [**Create Header SQL** (209.3.1.2)](#t28) | - | - | Creation |
| 209.6.1 | [CreationMail pour File Traitem (209.6)](#t47) | - | - | |
| 209.6.2 | [CreationMail File Traitem 2 (209.7)](#t48) | - | - | |
| **209.7** | [**RAZ TEMPO** (209.12)](#t56) | MDI | - | Initialisation |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Traitement principal]
    UPDATE[MAJ 14 tables]
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

### Tables utilisees (32)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 14 | transac_detail_bar |  | DB |   | **W** |   | 1 |
| 15 | transac_entete_bar |  | DB |   | **W** |   | 1 |
| 31 | gm-complet_______gmc |  | DB | R |   |   | 1 |
| 36 | client_gm |  | DB | R |   |   | 1 |
| 40 | comptable________cte |  | DB |   | **W** |   | 1 |
| 67 | tables___________tab |  | DB |   |   | L | 1 |
| 263 | vente | Donnees de ventes | DB |   |   | L | 1 |
| 268 | cc_total_par_type |  | DB | R |   |   | 1 |
| 377 | pv_contracts |  | DB | R |   |   | 1 |
| 379 | pv_customer_temp |  | DB | R |   |   | 2 |
| 382 | pv_discount_reasons |  | DB | R |   | L | 10 |
| 391 | pv_invoicehistoheader | Historique / journal | DB |   |   | L | 2 |
| 395 | pv_ownership |  | DB | R | **W** |   | 2 |
| 396 | pv_cust_packages |  | DB |   | **W** | L | 2 |
| 397 | pv_package_composants |  | DB |   | **W** |   | 1 |
| 400 | pv_cust_rentals |  | DB |   |   | L | 5 |
| 403 | pv_sellers |  | DB |   |   | L | 3 |
| 404 | pv_sellers_by_week |  | DB |   | **W** | L | 3 |
| 413 | pv_tva |  | DB |   |   | L | 2 |
| 419 | realise_articles_caution | Articles et stock | DB |   |   | L | 3 |
| 421 | req_location |  | DB |   |   | L | 2 |
| 531 | import_avertiss__an_val |  | DB |   | **W** | L | 5 |
| 533 | cumul_mvt_stock_histo | Articles et stock | TMP |   | **W** | L | 14 |
| 563 | pms_chained_listing |  | TMP |   | **W** | L | 4 |
| 731 | arc_tai_gm |  | DB |   | **W** | L | 2 |
| 808 | Selection des noms a supprimer |  | DB |   |   | L | 2 |
| 820 | Commentaire supprime |  | DB |   |   | L | 1 |
| 868 | Affectation_Gift_Pass |  | DB |   | **W** |   | 1 |
| 1501 | Table_1501 |  | MEM |   | **W** |   | 2 |
| 1539 | Table_1539 |  | MEM |   |   | L | 2 |
| 1548 | Table_1548 |  | MEM |   | **W** |   | 3 |
| 1620 | Table_1620 |  | MEM |   |   | L | 2 |

### Colonnes par table (17 / 20 tables avec colonnes identifiees)

<details>
<summary>Table 14 - transac_detail_bar (**W**) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| V | P.Num Id_transaction_Axis | W | Alpha |

</details>

<details>
<summary>Table 15 - transac_entete_bar (**W**) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| V | P.Num Id_transaction_Axis | W | Alpha |

</details>

<details>
<summary>Table 31 - gm-complet_______gmc (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | CautionExist | R | Logical |
| B | v.texte_conditions_gen_francais | R | Unicode |
| C | v.texte_conditions_gen_anglais | R | Unicode |
| D | PrintLinePackagesInCurrentPage | R | Numeric |
| E | CurrentLinePackagesChrono | R | Numeric |
| F | TotalLinePackagesChrono | R | Numeric |
| G | PageNumber | R | Numeric |
| H | TotalLinePackages | R | Numeric |
| I | TotalTVA | R | Numeric |
| J | TotalTTCDiscounted | R | Numeric |
| K | TotalTo Pay | R | Numeric |
| L | TotalOnAccount | R | Numeric |
| M | ExisteMontantTva | R | Logical |
| N | AssuranceOnly | R | Logical |
| O | v.# filiat skier profile PAS ok | R | Numeric |
| P | v.Binding settings DIN | R | Numeric |

</details>

<details>
<summary>Table 36 - client_gm (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P. Payer XCust Id | R | Numeric |
| B | P. Customer Id | R | Numeric |
| C | P. Societe | R | Alpha |
| D | P. Compte | R | Numeric |
| E | P. Filiation | R | Numeric |
| F | P. Package id | R | Numeric |
| G | P. PrintAgain | R | Logical |
| H | P. Total Ticket | R | Numeric |
| I | P. Total Crédit Conso | R | Numeric |
| J | P. Club Med Pass | R | Alpha |
| K | P. Card type | R | Alpha |
| L | P. Service | R | Alpha |
| M | P.Societe | R | Alpha |
| N | P.Adherent | R | Numeric |
| O | P.Filiation | R | Numeric |
| P | P.File Name Signature mobilité | R | Numeric |
| Q | p.ValidationMail | R | Logical |
| R | P Adresse Mail (MOB) | R | Alpha |
| S | p.No_Facture | R | Numeric |
| T | P.PrintAgainPreview | R | Logical |
| U | P.NomFichierPdf | R | Alpha |
| V | P.Num Id_transaction_Axis | R | Alpha |
| W | P.Num Id_Acceptation | R | Alpha |
| X | P.NotCancelBooking | R | Logical |
| Y | P.O N° Chrono | R | Numeric |
| Z | v. Copies | R | Numeric |
| BA | V VillageCode | R | Alpha |
| BB | V AmountFormat | R | Alpha |
| BC | V AmountFormat SANS Z | R | Alpha |
| BD | V VatValue | R | Numeric |
| BE | V Currency | R | Alpha |
| BF | V Decimal | R | Numeric |
| BG | PrintAgainExecution | R | Logical |
| BH | PrintAgainCopy | R | Numeric |
| BI | L ExistHistoric ? | R | Logical |
| BJ | HeaderLine01 | R | Alpha |
| BK | HeaderLine02 | R | Alpha |
| BL | HeaderLine03 | R | Alpha |
| BM | HeaderLine04 | R | Alpha |
| BN | HeaderLine05 | R | Alpha |
| BO | HeaderLine06 | R | Alpha |
| BP | HeaderLine07 | R | Alpha |
| BQ | HeaderLine08 | R | Alpha |
| BR | HeaderLine09 | R | Alpha |
| BS | HeaderLine10 | R | Alpha |
| BT | HeaderLine11 | R | Alpha |
| BU | V Facture | R | Numeric |
| BV | v Solde Gift Pass | R | Numeric |
| BW | v Existe Gift Pass | R | Logical |
| BX | v.Message Solde Gift Pass | R | Alpha |
| BY | V Nom Fic Pdf Ticket Mobilit | R | Alpha |
| BZ | v Langue Mail | R | Alpha |
| CA | v Validation envoi mail ? | R | Logical |
| CB | V.Fait parti d'un séminaire? | R | Logical |
| CC | v.NbrSales | R | Numeric |
| CD | v.NbrRentals | R | Numeric |
| CE | v.CGV_FileName | R | Alpha |
| CF | V.header_chrono | R | Numeric |
| CG | V.receipt_file | R | Unicode |
| CH | v.Edition mobilité ? | R | Logical |
| CI | v.Montant Service | R | Numeric |
| CJ | v.Montant Product | R | Numeric |
| CK | v.Article forcé? | R | Logical |
| CL | v. message | R | Alpha |
| CM | v.Total pour affich M&E | R | Numeric |

</details>

<details>
<summary>Table 40 - comptable________cte (**W**) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | T OD ? | W | Logical |
| B | T Vente ? | W | Logical |

</details>

<details>
<summary>Table 268 - cc_total_par_type (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | v.type rental Ski / Board | R | Alpha |
| B | v.type "4" snowboard trouvé? | R | Logical |
| CM | v.Total pour affich M&E | R | Numeric |
| F | TotalLinePackagesChrono | R | Numeric |
| H | P. Total Ticket | R | Numeric |
| I | P. Total Crédit Conso | R | Numeric |
| J | TotalTTCDiscounted | R | Numeric |
| K | P. Card type | R | Alpha |
| L | TotalOnAccount | R | Numeric |

</details>

<details>
<summary>Table 377 - pv_contracts (R) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 379 - pv_customer_temp (R) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | v.Update pour booker | R | Unicode |
| B | V.packageID | R | Numeric |
| C | V.PaymentMethodeID | R | Numeric |
| D | FirstRecord | R | Logical |
| E | L.Forfait/Package existe | R | Logical |
| F | v.Log | R | Unicode |

</details>

<details>
<summary>Table 382 - pv_discount_reasons (R/L) - 10 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | v.existe deja? | R | Logical |
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
| M | v.Taxes Multiples | R | Logical |
| N | v.Early Return avec Gift Pass? | R | Logical |

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
| D | PrintLinePackagesInCurrentPage | W | Numeric |
| E | CurrentLinePackagesChrono | W | Numeric |
| F | TotalLinePackagesChrono | W | Numeric |
| H | TotalLinePackages | W | Numeric |

</details>

<details>
<summary>Table 397 - pv_package_composants (**W**) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | V.packageID | W | Numeric |
| B | V.packageID | W | Numeric |
| C | -------------package IN | W | Alpha |
| D | PrintLinePackagesInCurrentPage | W | Numeric |
| E | L.Forfait/Package existe | W | Logical |
| F | P. Package id | W | Numeric |
| H | TotalLinePackages | W | Numeric |

</details>

<details>
<summary>Table 404 - pv_sellers_by_week (**W**/L) - 3 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | v.type "2" ski trouvé? | W | Logical |
| B | v.type "4" snowboard trouvé? | W | Logical |

</details>

<details>
<summary>Table 531 - import_avertiss__an_val (**W**/L) - 5 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 533 - cumul_mvt_stock_histo (**W**/L) - 14 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | V.Chrono TENV10 | W | Numeric |
| B | v.Date Ticket | W | Date |
| C | v.Heure Ticket | W | Time |

</details>

<details>
<summary>Table 563 - pms_chained_listing (**W**/L) - 4 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 731 - arc_tai_gm (**W**/L) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | v.sales_cgv_file_name | W | Alpha |
| B | v.rentals_cgv_file_name | W | Alpha |
| C | v.RepertoireCGV | W | Alpha |

</details>

<details>
<summary>Table 868 - Affectation_Gift_Pass (**W**) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | v.Avec Gift Pass? | W | Logical |
| BV | v Solde Gift Pass | W | Numeric |
| BW | v Existe Gift Pass | W | Logical |
| BX | v.Message Solde Gift Pass | W | Alpha |
| J | P. Club Med Pass | W | Alpha |
| L | Iteration Edit Gift Pass | W | Numeric |
| N | v.Early Return avec Gift Pass? | W | Logical |

</details>

<details>
<summary>Table 1501 - Table_1501 (**W**) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 1548 - Table_1548 (**W**) - 3 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (25)

Variables recues du programme appelant ([Generate Preview Payments (IDE 189)](PVE-IDE-189.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P. Payer XCust Id | Numeric | 3x parametre entrant |
| B | P. Customer Id | Numeric | 2x parametre entrant |
| C | P. Societe | Alpha | - |
| D | P. Compte | Numeric | 1x parametre entrant |
| E | P. Filiation | Numeric | [209.2.2](#t14), [209.2.3](#t16), [209.10.1.3](#t22) |
| F | P. Package id | Numeric | [209.2.1](#t4), [209.2.1.4](#t12), [209.10.1.1](#t19) |
| G | P. PrintAgain | Logical | 3x parametre entrant |
| H | P. Total Ticket | Numeric | - |
| I | P. Total Crédit Conso | Numeric | 1x parametre entrant |
| J | P. Club Med Pass | Alpha | - |
| K | P. Card type | Alpha | - |
| L | P. Service | Alpha | - |
| M | P.Societe | Alpha | 2x parametre entrant |
| N | P.Adherent | Numeric | - |
| O | P.Filiation | Numeric | - |
| P | P.File Name Signature mobilité | Numeric | - |
| Q | p.ValidationMail | Logical | 1x parametre entrant |
| R | P Adresse Mail (MOB) | Alpha | [209.6](#t47), [209.7](#t48) |
| S | p.No_Facture | Numeric | - |
| T | P.PrintAgainPreview | Logical | - |
| U | P.NomFichierPdf | Alpha | - |
| V | P.Num Id_transaction_Axis | Alpha | - |
| W | P.Num Id_Acceptation | Alpha | - |
| X | P.NotCancelBooking | Logical | - |
| Y | P.O N° Chrono | Numeric | - |

### 11.2 Variables de session (26)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| Z | v. Copies | Numeric | - |
| BA | V VillageCode | Alpha | 1x session |
| BB | V AmountFormat | Alpha | 1x session |
| BC | V AmountFormat SANS Z | Alpha | 1x session |
| BD | V VatValue | Numeric | - |
| BE | V Currency | Alpha | - |
| BF | V Decimal | Numeric | - |
| BU | V Facture | Numeric | - |
| BV | v Solde Gift Pass | Numeric | [209.2.1.1.1](#t6), [209.2.1.1.4](#t9), [209.3.1.3](#t29) |
| BW | v Existe Gift Pass | Logical | - |
| BX | v.Message Solde Gift Pass | Alpha | - |
| BY | V Nom Fic Pdf Ticket Mobilit | Alpha | - |
| BZ | v Langue Mail | Alpha | - |
| CA | v Validation envoi mail ? | Logical | - |
| CB | V.Fait parti d'un séminaire? | Logical | - |
| CC | v.NbrSales | Numeric | - |
| CD | v.NbrRentals | Numeric | - |
| CE | v.CGV_FileName | Alpha | 1x session |
| CF | V.header_chrono | Numeric | - |
| CG | V.receipt_file | Unicode | - |
| CH | v.Edition mobilité ? | Logical | - |
| CI | v.Montant Service | Numeric | - |
| CJ | v.Montant Product | Numeric | - |
| CK | v.Article forcé? | Logical | - |
| CL | v. message | Alpha | 1x session |
| CM | v.Total pour affich M&E | Numeric | - |

### 11.3 Autres (14)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| BG | PrintAgainExecution | Logical | - |
| BH | PrintAgainCopy | Numeric | - |
| BI | L ExistHistoric ? | Logical | - |
| BJ | HeaderLine01 | Alpha | 1x refs |
| BK | HeaderLine02 | Alpha | 1x refs |
| BL | HeaderLine03 | Alpha | - |
| BM | HeaderLine04 | Alpha | 1x refs |
| BN | HeaderLine05 | Alpha | 1x refs |
| BO | HeaderLine06 | Alpha | 1x refs |
| BP | HeaderLine07 | Alpha | - |
| BQ | HeaderLine08 | Alpha | - |
| BR | HeaderLine09 | Alpha | 1x refs |
| BS | HeaderLine10 | Alpha | 1x refs |
| BT | HeaderLine11 | Alpha | - |

<details>
<summary>Toutes les 65 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| P0 | **A** | P. Payer XCust Id | Numeric |
| P0 | **B** | P. Customer Id | Numeric |
| P0 | **C** | P. Societe | Alpha |
| P0 | **D** | P. Compte | Numeric |
| P0 | **E** | P. Filiation | Numeric |
| P0 | **F** | P. Package id | Numeric |
| P0 | **G** | P. PrintAgain | Logical |
| P0 | **H** | P. Total Ticket | Numeric |
| P0 | **I** | P. Total Crédit Conso | Numeric |
| P0 | **J** | P. Club Med Pass | Alpha |
| P0 | **K** | P. Card type | Alpha |
| P0 | **L** | P. Service | Alpha |
| P0 | **M** | P.Societe | Alpha |
| P0 | **N** | P.Adherent | Numeric |
| P0 | **O** | P.Filiation | Numeric |
| P0 | **P** | P.File Name Signature mobilité | Numeric |
| P0 | **Q** | p.ValidationMail | Logical |
| P0 | **R** | P Adresse Mail (MOB) | Alpha |
| P0 | **S** | p.No_Facture | Numeric |
| P0 | **T** | P.PrintAgainPreview | Logical |
| P0 | **U** | P.NomFichierPdf | Alpha |
| P0 | **V** | P.Num Id_transaction_Axis | Alpha |
| P0 | **W** | P.Num Id_Acceptation | Alpha |
| P0 | **X** | P.NotCancelBooking | Logical |
| P0 | **Y** | P.O N° Chrono | Numeric |
| V. | **Z** | v. Copies | Numeric |
| V. | **BA** | V VillageCode | Alpha |
| V. | **BB** | V AmountFormat | Alpha |
| V. | **BC** | V AmountFormat SANS Z | Alpha |
| V. | **BD** | V VatValue | Numeric |
| V. | **BE** | V Currency | Alpha |
| V. | **BF** | V Decimal | Numeric |
| V. | **BU** | V Facture | Numeric |
| V. | **BV** | v Solde Gift Pass | Numeric |
| V. | **BW** | v Existe Gift Pass | Logical |
| V. | **BX** | v.Message Solde Gift Pass | Alpha |
| V. | **BY** | V Nom Fic Pdf Ticket Mobilit | Alpha |
| V. | **BZ** | v Langue Mail | Alpha |
| V. | **CA** | v Validation envoi mail ? | Logical |
| V. | **CB** | V.Fait parti d'un séminaire? | Logical |
| V. | **CC** | v.NbrSales | Numeric |
| V. | **CD** | v.NbrRentals | Numeric |
| V. | **CE** | v.CGV_FileName | Alpha |
| V. | **CF** | V.header_chrono | Numeric |
| V. | **CG** | V.receipt_file | Unicode |
| V. | **CH** | v.Edition mobilité ? | Logical |
| V. | **CI** | v.Montant Service | Numeric |
| V. | **CJ** | v.Montant Product | Numeric |
| V. | **CK** | v.Article forcé? | Logical |
| V. | **CL** | v. message | Alpha |
| V. | **CM** | v.Total pour affich M&E | Numeric |
| Autre | **BG** | PrintAgainExecution | Logical |
| Autre | **BH** | PrintAgainCopy | Numeric |
| Autre | **BI** | L ExistHistoric ? | Logical |
| Autre | **BJ** | HeaderLine01 | Alpha |
| Autre | **BK** | HeaderLine02 | Alpha |
| Autre | **BL** | HeaderLine03 | Alpha |
| Autre | **BM** | HeaderLine04 | Alpha |
| Autre | **BN** | HeaderLine05 | Alpha |
| Autre | **BO** | HeaderLine06 | Alpha |
| Autre | **BP** | HeaderLine07 | Alpha |
| Autre | **BQ** | HeaderLine08 | Alpha |
| Autre | **BR** | HeaderLine09 | Alpha |
| Autre | **BS** | HeaderLine10 | Alpha |
| Autre | **BT** | HeaderLine11 | Alpha |

</details>

## 12. EXPRESSIONS

**40 / 40 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| FORMAT | 4 | 0 |
| CONDITION | 8 | 5 |
| CONSTANTE | 6 | 0 |
| NEGATION | 3 | 0 |
| OTHER | 13 | 0 |
| CAST_LOGIQUE | 1 | 0 |
| REFERENCE_VG | 3 | 0 |
| STRING | 1 | 0 |
| CONCATENATION | 1 | 0 |

### 12.2 Expressions cles par type

#### FORMAT (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| FORMAT | 17 | `'Receipt_'&Trim(P.Societe [M])&'_'&Trim(Str([AU],'6Z'))&'_'&DStr(Date(),'YYYYMMDD')&'.pdf'` | - |
| FORMAT | 24 | `'Error during the sale receipt generation.
Please contact the support with the following information :
Payer Id : '&Str(P. Payer XCust Id [A],'9')&ASCIIChr(13)
&'Customer Id : '&IF(P. Customer Id [B]=0,'All Filiations',Str(P. Customer Id [B],'9'))&ASCIIChr(13)
&'Package Id : '&IF(P. Package id [F]=0,'All Packages',Str(P. Package id [F],'9'))&ASCIIChr(13)
&'Date : '&DStr(Date(),'DD/MM/YYYY')&ASCIIChr(13)
&'Time : '&TStr(Time(),'HH:MM:SS')` | - |
| FORMAT | 32 | `StrBuild('Ticket @1@ @2@ @3@ (@4@/@5@, package @6@)', HeaderLine02 [BK], HeaderLine01 [BJ], Str(P. Total Crédit Conso [I], 'N10.2'), Str(P. Compte [D], '8'), Str(P. Filiation [E], '3'), IF(P. Package id [F]=0, '(all)',Str(P. Package id [F], '10')))` | - |
| FORMAT | 12 | `'Solde Gift Pass au : '&DStr(Date(),'DD/MM/YYYY')&' à : '&TStr(Time(),('HH:MM:SS'))` | - |

#### CONDITION (8 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 16 | `IF(VG33='TB',v Solde Gift Pass [BV],'')
` | [RM-001](#rm-RM-001) |
| CONDITION | 27 | `HeaderLine09 [BR] > 0 OR HeaderLine10 [BS] > 0` | - |
| CONDITION | 33 | `VG33='TB' AND p.ValidationMail [Q]<>0 AND NOT P. PrintAgain [G]` | - |
| CONDITION | 40 | `Trim(v. message [CL])<>''` | - |
| CONDITION | 15 | `VG33='TB'` | - |
| ... | | *+3 autres* | |

#### CONSTANTE (6 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 29 | `'ERROR'` | - |
| CONSTANTE | 30 | `'PRINT INVOICE/TICKET'` | - |
| CONSTANTE | 31 | `'ERR'` | - |
| CONSTANTE | 2 | `1` | - |
| CONSTANTE | 9 | `'VSERV'` | - |
| ... | | *+1 autres* | |

#### NEGATION (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| NEGATION | 22 | `NOT VG95` | - |
| NEGATION | 7 | `NOT ([AI])` | - |
| NEGATION | 5 | `NOT (P. PrintAgain [G])` | - |

#### OTHER (13 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 36 | `MAX(v.CGV_FileName [CE],1)` | - |
| OTHER | 35 | `P.Societe [M]` | - |
| OTHER | 34 | `NULL()` | - |
| OTHER | 39 | `HeaderLine06 [BO]` | - |
| OTHER | 38 | `HeaderLine05 [BN]` | - |
| ... | | *+8 autres* | |

#### CAST_LOGIQUE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 8 | `GetParam ('RENTAL')='TRUE'LOG` | - |

#### REFERENCE_VG (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 26 | `VG83` | - |
| REFERENCE_VG | 23 | `VG95` | - |
| REFERENCE_VG | 13 | `VG29` | - |

#### STRING (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| STRING | 25 | `FileExist(Trim(v Solde Gift Pass [BV]))` | - |

#### CONCATENATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 28 | `Trim(VG79)&Trim(V AmountFormat SANS Z [BC])` | - |

### 12.3 Toutes les expressions (40)

<details>
<summary>Voir les 40 expressions</summary>

#### FORMAT (4)

| IDE | Expression Decodee |
|-----|-------------------|
| 32 | `StrBuild('Ticket @1@ @2@ @3@ (@4@/@5@, package @6@)', HeaderLine02 [BK], HeaderLine01 [BJ], Str(P. Total Crédit Conso [I], 'N10.2'), Str(P. Compte [D], '8'), Str(P. Filiation [E], '3'), IF(P. Package id [F]=0, '(all)',Str(P. Package id [F], '10')))` |
| 12 | `'Solde Gift Pass au : '&DStr(Date(),'DD/MM/YYYY')&' à : '&TStr(Time(),('HH:MM:SS'))` |
| 17 | `'Receipt_'&Trim(P.Societe [M])&'_'&Trim(Str([AU],'6Z'))&'_'&DStr(Date(),'YYYYMMDD')&'.pdf'` |
| 24 | `'Error during the sale receipt generation.
Please contact the support with the following information :
Payer Id : '&Str(P. Payer XCust Id [A],'9')&ASCIIChr(13)
&'Customer Id : '&IF(P. Customer Id [B]=0,'All Filiations',Str(P. Customer Id [B],'9'))&ASCIIChr(13)
&'Package Id : '&IF(P. Package id [F]=0,'All Packages',Str(P. Package id [F],'9'))&ASCIIChr(13)
&'Date : '&DStr(Date(),'DD/MM/YYYY')&ASCIIChr(13)
&'Time : '&TStr(Time(),'HH:MM:SS')` |

#### CONDITION (8)

| IDE | Expression Decodee |
|-----|-------------------|
| 16 | `IF(VG33='TB',v Solde Gift Pass [BV],'')
` |
| 1 | `P. Payer XCust Id [A]=0` |
| 3 | `DbRecs ('{533,3}'DSOURCE,'')=0` |
| 4 | `DbRecs ('{533,3}'DSOURCE,'')>0` |
| 15 | `VG33='TB'` |
| 27 | `HeaderLine09 [BR] > 0 OR HeaderLine10 [BS] > 0` |
| 33 | `VG33='TB' AND p.ValidationMail [Q]<>0 AND NOT P. PrintAgain [G]` |
| 40 | `Trim(v. message [CL])<>''` |

#### CONSTANTE (6)

| IDE | Expression Decodee |
|-----|-------------------|
| 2 | `1` |
| 9 | `'VSERV'` |
| 10 | `'O'` |
| 29 | `'ERROR'` |
| 30 | `'PRINT INVOICE/TICKET'` |
| 31 | `'ERR'` |

#### NEGATION (3)

| IDE | Expression Decodee |
|-----|-------------------|
| 5 | `NOT (P. PrintAgain [G])` |
| 7 | `NOT ([AI])` |
| 22 | `NOT VG95` |

#### OTHER (13)

| IDE | Expression Decodee |
|-----|-------------------|
| 6 | `P. PrintAgain [G]` |
| 11 | `GetParam('SERVICE')` |
| 14 | `V VillageCode [BA]` |
| 18 | `SetCrsr (1)` |
| 19 | `P. Payer XCust Id [A]` |
| 20 | `P. Customer Id [B]` |
| 21 | `P Adresse Mail (MOB) [R]` |
| 34 | `NULL()` |
| 35 | `P.Societe [M]` |
| 36 | `MAX(v.CGV_FileName [CE],1)` |
| 37 | `HeaderLine04 [BM]` |
| 38 | `HeaderLine05 [BN]` |
| 39 | `HeaderLine06 [BO]` |

#### CAST_LOGIQUE (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 8 | `GetParam ('RENTAL')='TRUE'LOG` |

#### REFERENCE_VG (3)

| IDE | Expression Decodee |
|-----|-------------------|
| 13 | `VG29` |
| 23 | `VG95` |
| 26 | `VG83` |

#### STRING (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 25 | `FileExist(Trim(v Solde Gift Pass [BV]))` |

#### CONCATENATION (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 28 | `Trim(VG79)&Trim(V AmountFormat SANS Z [BC])` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Generate Preview Payments (IDE 189)](PVE-IDE-189.md) -> **Print Invoice or Ticket-664 (IDE 209)**

Main -> ... -> [Choice Re_Print Invoice (IDE 204)](PVE-IDE-204.md) -> **Print Invoice or Ticket-664 (IDE 209)**

Main -> ... -> [Generate Preview Payments 1212 (IDE 434)](PVE-IDE-434.md) -> **Print Invoice or Ticket-664 (IDE 209)**

Main -> ... -> [Generate Preview Payments 1112 (IDE 435)](PVE-IDE-435.md) -> **Print Invoice or Ticket-664 (IDE 209)**

Main -> ... -> [Generate Preview Payments 1012 (IDE 436)](PVE-IDE-436.md) -> **Print Invoice or Ticket-664 (IDE 209)**

Main -> ... -> [Generate Preview Payment 1212E (IDE 437)](PVE-IDE-437.md) -> **Print Invoice or Ticket-664 (IDE 209)**

```mermaid
graph LR
    T209[209 Print Invoice or T...]
    style T209 fill:#58a6ff
    CC214[214 Main Sale Sale Bar...]
    style CC214 fill:#8b5cf6
    CC187[187 Main Sale-664]
    style CC187 fill:#8b5cf6
    CC186[186 Main Sale]
    style CC186 fill:#8b5cf6
    CC364[364 Main Sale-664]
    style CC364 fill:#8b5cf6
    CC363[363 Main Sale]
    style CC363 fill:#8b5cf6
    CC189[189 Generate Preview P...]
    style CC189 fill:#3fb950
    CC434[434 Generate Preview P...]
    style CC434 fill:#3fb950
    CC204[204 Choice Re_Print In...]
    style CC204 fill:#3fb950
    CC436[436 Generate Preview P...]
    style CC436 fill:#3fb950
    CC435[435 Generate Preview P...]
    style CC435 fill:#3fb950
    CC186 --> CC189
    CC187 --> CC189
    CC214 --> CC189
    CC363 --> CC189
    CC364 --> CC189
    CC186 --> CC204
    CC187 --> CC204
    CC214 --> CC204
    CC363 --> CC204
    CC364 --> CC204
    CC186 --> CC434
    CC187 --> CC434
    CC214 --> CC434
    CC363 --> CC434
    CC364 --> CC434
    CC186 --> CC435
    CC187 --> CC435
    CC214 --> CC435
    CC363 --> CC435
    CC364 --> CC435
    CC186 --> CC436
    CC187 --> CC436
    CC214 --> CC436
    CC363 --> CC436
    CC364 --> CC436
    CC189 --> T209
    CC204 --> T209
    CC434 --> T209
    CC435 --> T209
    CC436 --> T209
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [189](PVE-IDE-189.md) | Generate Preview Payments | 1 |
| [204](PVE-IDE-204.md) | Choice Re_Print Invoice | 1 |
| [434](PVE-IDE-434.md) | Generate Preview Payments 1212 | 1 |
| [435](PVE-IDE-435.md) | Generate Preview Payments 1112 | 1 |
| [436](PVE-IDE-436.md) | Generate Preview Payments 1012 | 1 |
| [437](PVE-IDE-437.md) | Generate Preview Payment 1212E | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T209[209 Print Invoice or T...]
    style T209 fill:#58a6ff
    C175[175 TraceLogBooker]
    T209 --> C175
    style C175 fill:#3fb950
    C159[159 CancelAppointment]
    T209 --> C159
    style C159 fill:#3fb950
    C169[169 AddPaymentToOrder]
    T209 --> C169
    style C169 fill:#3fb950
    C174[174 GetLocationPayment...]
    T209 --> C174
    style C174 fill:#3fb950
    C281[281 Creation pied Tick...]
    T209 --> C281
    style C281 fill:#3fb950
    C113[113 Print label code b...]
    T209 --> C113
    style C113 fill:#3fb950
    C170[170 AddSpecialToOrder-392]
    T209 --> C170
    style C170 fill:#3fb950
    C205[205 Edition ticket Tva...]
    T209 --> C205
    style C205 fill:#3fb950
    C206[206 Edition ticket Tva]
    T209 --> C206
    style C206 fill:#3fb950
    C277[277 Set Village Address]
    T209 --> C277
    style C277 fill:#3fb950
    C278[278 Set Customer]
    T209 --> C278
    style C278 fill:#3fb950
    C279[279 Search for messages]
    T209 --> C279
    style C279 fill:#3fb950
    C320[320 SynchronisationRec...]
    T209 --> C320
    style C320 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [175](PVE-IDE-175.md) | TraceLogBooker | 3 | Sous-programme |
| [159](PVE-IDE-159.md) | CancelAppointment | 2 | Sous-programme |
| [169](PVE-IDE-169.md) | AddPaymentToOrder | 2 | Sous-programme |
| [174](PVE-IDE-174.md) | GetLocationPaymentSettings | 2 | Recuperation donnees |
| [281](PVE-IDE-281.md) | Creation pied Ticket(Tva) | 2 | Impression ticket/document |
| [113](PVE-IDE-113.md) | Print label code barre DIN | 1 | Impression ticket/document |
| [170](PVE-IDE-170.md) | AddSpecialToOrder-392 | 1 | Sous-programme |
| [205](PVE-IDE-205.md) | Edition ticket (Tva) LEX | 1 | Impression ticket/document |
| [206](PVE-IDE-206.md) | Edition ticket (Tva) | 1 | Impression ticket/document |
| [277](PVE-IDE-277.md) | Set Village Address | 1 | Sous-programme |
| [278](PVE-IDE-278.md) | Set Customer | 1 | Sous-programme |
| [279](PVE-IDE-279.md) | Search  for messages | 1 | Sous-programme |
| [320](PVE-IDE-320.md) | SynchronisationRecuPDF | 1 | Recuperation donnees |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 1686 | Programme volumineux |
| Expressions | 40 | Peu de logique |
| Tables WRITE | 14 | Fort impact donnees |
| Sous-programmes | 13 | Forte dependance |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 2.1% (35 / 1686) | Code sain |
| Regles metier | 1 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Impression (4 taches: 3 ecrans, 1 traitement)

- **Strategie** : Templates HTML -> PDF via wkhtmltopdf ou Puppeteer.
- `PrintService` injectable avec choix imprimante

#### Traitement (33 taches: 4 ecrans, 29 traitements)

- **Strategie** : Orchestrateur avec 4 ecrans (Razor/React) et 29 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 13 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Consultation (7 taches: 3 ecrans, 4 traitements)

- **Strategie** : Composants de recherche/selection en modales.
- 3 ecrans : SELECTION, Selection Packages, Selection Packages

#### Calcul (2 taches: 0 ecran, 2 traitements)

- **Strategie** : Services de calcul purs (Domain Services).
- Migrer la logique de calcul (stock, compteurs, montants)

#### Validation (1 tache: 0 ecran, 1 traitement)

- **Strategie** : FluentValidation avec validators specifiques.
- Chaque tache de validation -> un validator injectable

#### Creation (3 taches: 0 ecran, 3 traitements)

- **Strategie** : Repository pattern avec Entity Framework Core.
- Insertion via `IRepository<T>.CreateAsync()`

#### Initialisation (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Constructeur/methode `InitAsync()` dans l'orchestrateur.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| transac_detail_bar | Table WRITE (Database) | 1x | Schema + repository |
| transac_entete_bar | Table WRITE (Database) | 1x | Schema + repository |
| comptable________cte | Table WRITE (Database) | 1x | Schema + repository |
| pv_ownership | Table WRITE (Database) | 1x | Schema + repository |
| pv_cust_packages | Table WRITE (Database) | 1x | Schema + repository |
| pv_package_composants | Table WRITE (Database) | 1x | Schema + repository |
| pv_sellers_by_week | Table WRITE (Database) | 1x | Schema + repository |
| import_avertiss__an_val | Table WRITE (Database) | 3x | Schema + repository |
| cumul_mvt_stock_histo | Table WRITE (Temp) | 7x | Schema + repository |
| pms_chained_listing | Table WRITE (Temp) | 3x | Schema + repository |
| arc_tai_gm | Table WRITE (Database) | 1x | Schema + repository |
| Affectation_Gift_Pass | Table WRITE (Database) | 1x | Schema + repository |
| Table_1501 | Table WRITE (Memory) | 2x | Schema + repository |
| Table_1548 | Table WRITE (Memory) | 3x | Schema + repository |
| [TraceLogBooker (IDE 175)](PVE-IDE-175.md) | Sous-programme | 3x | **CRITIQUE** - Sous-programme |
| [GetLocationPaymentSettings (IDE 174)](PVE-IDE-174.md) | Sous-programme | 2x | Haute - Recuperation donnees |
| [Creation pied Ticket(Tva) (IDE 281)](PVE-IDE-281.md) | Sous-programme | 2x | Haute - Impression ticket/document |
| [CancelAppointment (IDE 159)](PVE-IDE-159.md) | Sous-programme | 2x | Haute - Sous-programme |
| [AddPaymentToOrder (IDE 169)](PVE-IDE-169.md) | Sous-programme | 2x | Haute - Sous-programme |
| [Set Customer (IDE 278)](PVE-IDE-278.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Set Village Address (IDE 277)](PVE-IDE-277.md) | Sous-programme | 1x | Normale - Sous-programme |
| [SynchronisationRecuPDF (IDE 320)](PVE-IDE-320.md) | Sous-programme | 1x | Normale - Recuperation donnees |
| [Search  for messages (IDE 279)](PVE-IDE-279.md) | Sous-programme | 1x | Normale - Sous-programme |
| [AddSpecialToOrder-392 (IDE 170)](PVE-IDE-170.md) | Sous-programme | 1x | Normale - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 18:55*
