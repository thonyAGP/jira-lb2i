# PVE IDE 429 - Print Invoice or Ticket==NEW

> **Analyse**: Phases 1-4 2026-02-03 20:05 -> 20:06 (18s) | Assemblage 20:06
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PVE |
| IDE Position | 429 |
| Nom Programme | Print Invoice or Ticket==NEW |
| Fichier source | `Prg_429.xml` |
| Dossier IDE | A |
| Taches | 39 (1 ecrans visibles) |
| Tables modifiees | 10 |
| Programmes appeles | 11 |
| :warning: Statut | **ORPHELIN_POTENTIEL** |

## 2. DESCRIPTION FONCTIONNELLE

**Print Invoice or Ticket==NEW** assure la gestion complete de ce processus.

Le flux de traitement s'organise en **7 blocs fonctionnels** :

- **Traitement** (25 taches) : traitements metier divers
- **Consultation** (5 taches) : ecrans de recherche, selection et consultation
- **Impression** (4 taches) : generation de tickets et documents
- **Calcul** (2 taches) : calculs de montants, stocks ou compteurs
- **Creation** (1 tache) : insertion d'enregistrements en base (mouvements, prestations)
- **Initialisation** (1 tache) : reinitialisation d'etats et de variables de travail
- **Validation** (1 tache) : controles et verifications de coherence

**Donnees modifiees** : 10 tables en ecriture (transac_detail_bar, transac_entete_bar, comptable________cte, pv_ownership, pv_cust_packages, pv_package_composants, import_avertiss__an_val, cumul_mvt_stock_histo, Table_1501, Table_1548).

**Logique metier** : 1 regles identifiees couvrant conditions metier.

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Impression (4 taches)

- **429** - Print Invoice **[[ECRAN]](#ecran-t1)**
- **429.3** - EDITION
- **429.5** - PRINT AGAIN **[[ECRAN]](#ecran-t28)**
- **429.5.1** - Print Again Gener

Delegue a : [Edition ticket (Tva) LEX (IDE 205)](PVE-IDE-205.md), [Edition ticket (IDE 273)](PVE-IDE-273.md)

#### Phase 2 : Traitement (25 taches)

- **429.1** - PARAMETERS
- **429.2.1.1.1** - Temp generation Gift Pass
- **429.2.1.1.2** - Temp generation
- **429.2.1.1.3** - Temp generation
- **429.2.1.1.4** - Temp generation Gift Pass
- **429.2.1.2** - AddAppointmentToList
- **429.2.3.1** - Temp generation
- **429.3.1** - Package line **[[ECRAN]](#ecran-t16)**
- **429.3.1.1** - Package line
- **429.3.2** - Package blank line
- **429.3.3** - Filiations
- **429.3.3.1** - Ski Shoes Name
- **429.4** - HISTO
- **429.4.1** - Generation
- **429.4.1.1** - header
- **429.4.1.1.1** - Entete EZcard
- **429.4.1.2** - Lines
- **429.4.2** - Package line
- **429.4.2.1** - Ligne EZcard
- **429.5.1.2.1** - Temp generation
- **429.5.2** - Trace Again
- **429.6** - CHECK HISTO
- **429.7.1** - Package
- **429.7.2** - Filiation
- **429.8** - Search for Gift Pass **[[ECRAN]](#ecran-t38)**

Delegue a : [CancelAppointment (IDE 159)](PVE-IDE-159.md), [AddPaymentToOrder (IDE 169)](PVE-IDE-169.md), [GetLocationPaymentSettings (IDE 174)](PVE-IDE-174.md), [Set Customer (IDE 278)](PVE-IDE-278.md), [Get default email address (IDE 314)](PVE-IDE-314.md), [SynchronisationRecuPDF (IDE 320)](PVE-IDE-320.md)

#### Phase 3 : Consultation (5 taches)

- **429.2** - SELECTION **[[ECRAN]](#ecran-t3)**
- **429.2.1** - Selection Packages **[[ECRAN]](#ecran-t4)**
- **429.2.2** - View Selection Packages **[[ECRAN]](#ecran-t12)**
- **429.2.3** - Selection Filiations
- **429.5.1.2** - Selection Filiations

Delegue a : [GetLocationPaymentSettings (IDE 174)](PVE-IDE-174.md), [Recherche Adresse Mail (IDE 308)](PVE-IDE-308.md), [Get default email address (IDE 314)](PVE-IDE-314.md), [SynchronisationRecuPDF (IDE 320)](PVE-IDE-320.md)

#### Phase 4 : Calcul (2 taches)

- **429.2.1.1** - Selection Pv_Compta
- **429.5.1.1** - Load temp compta

#### Phase 5 : Validation (1 tache)

- **429.2.1.3** - Validate/Cancel Booker

#### Phase 6 : Initialisation (1 tache)

- **429.7** - RAZ TEMPO

#### Phase 7 : Creation (1 tache)

- **429.9** - CreationMail pour File Traitem

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| cumul_mvt_stock_histo | **W**/L (13 usages) | Articles et stock |
| import_avertiss__an_val | **W**/L (4 usages) |  |
| Table_1548 | **W** (2 usages) |  |
| pv_ownership | R/**W** (2 usages) |  |
| pv_cust_packages | **W**/L (2 usages) |  |
| pv_package_composants | **W** (1 usages) |  |
| comptable________cte | **W** (1 usages) |  |
| Table_1501 | **W** (1 usages) |  |
| transac_entete_bar | **W** (1 usages) |  |
| transac_detail_bar | **W** (1 usages) |  |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Impression (4 taches)

Generation des documents et tickets.

---

#### <a id="t1"></a>429 - Print Invoice [[ECRAN]](#ecran-t1)

**Role** : Generation du document : Print Invoice.
**Ecran** : 869 x 291 DLU (MDI) | [Voir mockup](#ecran-t1)

<details>
<summary>3 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [429.3](#t15) | EDITION | Impression |
| [429.5](#t28) | PRINT AGAIN **[[ECRAN]](#ecran-t28)** | Impression |
| [429.5.1](#t29) | Print Again Gener | Impression |

</details>
**Variables liees** : G (P. PrintAgain), U (P.PrintAgainPreview), BD (PrintAgainExecution), BE (PrintAgainCopy)
**Delegue a** : [Edition ticket (Tva) LEX (IDE 205)](PVE-IDE-205.md), [Edition ticket (IDE 273)](PVE-IDE-273.md)

---

#### <a id="t15"></a>429.3 - EDITION

**Role** : Generation du document : EDITION.
**Delegue a** : [Edition ticket (Tva) LEX (IDE 205)](PVE-IDE-205.md), [Edition ticket (IDE 273)](PVE-IDE-273.md)

---

#### <a id="t28"></a>429.5 - PRINT AGAIN [[ECRAN]](#ecran-t28)

**Role** : Generation du document : PRINT AGAIN.
**Ecran** : 375 x 240 DLU (MDI) | [Voir mockup](#ecran-t28)
**Variables liees** : G (P. PrintAgain), U (P.PrintAgainPreview), BD (PrintAgainExecution), BE (PrintAgainCopy)
**Delegue a** : [Edition ticket (Tva) LEX (IDE 205)](PVE-IDE-205.md), [Edition ticket (IDE 273)](PVE-IDE-273.md)

---

#### <a id="t29"></a>429.5.1 - Print Again Gener

**Role** : Generation du document : Print Again Gener.
**Variables liees** : G (P. PrintAgain), U (P.PrintAgainPreview), BD (PrintAgainExecution), BE (PrintAgainCopy)
**Delegue a** : [Edition ticket (Tva) LEX (IDE 205)](PVE-IDE-205.md), [Edition ticket (IDE 273)](PVE-IDE-273.md)


### 3.2 Traitement (25 taches)

Traitements internes.

---

#### <a id="t2"></a>429.1 - PARAMETERS

**Role** : Traitement : PARAMETERS.

---

#### <a id="t6"></a>429.2.1.1.1 - Temp generation Gift Pass

**Role** : Calcul fidelite/avantage : Temp generation Gift Pass.
**Variables liees** : BS (v Solde Gift Pass), BT (v Existe Gift Pass), BU (v.Message Solde Gift Pass)

---

#### <a id="t7"></a>429.2.1.1.2 - Temp generation

**Role** : Traitement : Temp generation.

---

#### <a id="t8"></a>429.2.1.1.3 - Temp generation

**Role** : Traitement : Temp generation.

---

#### <a id="t9"></a>429.2.1.1.4 - Temp generation Gift Pass

**Role** : Calcul fidelite/avantage : Temp generation Gift Pass.
**Variables liees** : BS (v Solde Gift Pass), BT (v Existe Gift Pass), BU (v.Message Solde Gift Pass)

---

#### <a id="t10"></a>429.2.1.2 - AddAppointmentToList

**Role** : Traitement : AddAppointmentToList.

---

#### <a id="t14"></a>429.2.3.1 - Temp generation

**Role** : Traitement : Temp generation.

---

#### <a id="t16"></a>429.3.1 - Package line [[ECRAN]](#ecran-t16)

**Role** : Traitement : Package line.
**Ecran** : 557 x 327 DLU (MDI) | [Voir mockup](#ecran-t16)
**Variables liees** : F (P. Package id), BG (HeaderLine01), BH (HeaderLine02), BI (HeaderLine03), BJ (HeaderLine04)

---

#### <a id="t17"></a>429.3.1.1 - Package line

**Role** : Traitement : Package line.
**Variables liees** : F (P. Package id), BG (HeaderLine01), BH (HeaderLine02), BI (HeaderLine03), BJ (HeaderLine04)

---

#### <a id="t18"></a>429.3.2 - Package blank line

**Role** : Traitement : Package blank line.
**Variables liees** : F (P. Package id), BG (HeaderLine01), BH (HeaderLine02), BI (HeaderLine03), BJ (HeaderLine04)

---

#### <a id="t19"></a>429.3.3 - Filiations

**Role** : Traitement : Filiations.

---

#### <a id="t20"></a>429.3.3.1 - Ski Shoes Name

**Role** : Traitement : Ski Shoes Name.
**Variables liees** : Q (P.File Name Signature)

---

#### <a id="t21"></a>429.4 - HISTO

**Role** : Traitement : HISTO.
**Variables liees** : BF (L ExistHistoric ?)

---

#### <a id="t22"></a>429.4.1 - Generation

**Role** : Traitement : Generation.

---

#### <a id="t23"></a>429.4.1.1 - header

**Role** : Traitement : header.
**Variables liees** : BG (HeaderLine01), BH (HeaderLine02), BI (HeaderLine03), BJ (HeaderLine04), BK (HeaderLine05)

---

#### <a id="t24"></a>429.4.1.1.1 - Entete EZcard

**Role** : Traitement : Entete EZcard.
**Variables liees** : K (P. EZcard)

---

#### <a id="t25"></a>429.4.1.2 - Lines

**Role** : Traitement : Lines.

---

#### <a id="t26"></a>429.4.2 - Package line

**Role** : Traitement : Package line.
**Variables liees** : F (P. Package id), BG (HeaderLine01), BH (HeaderLine02), BI (HeaderLine03), BJ (HeaderLine04)

---

#### <a id="t27"></a>429.4.2.1 - Ligne EZcard

**Role** : Traitement : Ligne EZcard.
**Variables liees** : K (P. EZcard)

---

#### <a id="t32"></a>429.5.1.2.1 - Temp generation

**Role** : Traitement : Temp generation.

---

#### <a id="t33"></a>429.5.2 - Trace Again

**Role** : Traitement : Trace Again.
**Variables liees** : G (P. PrintAgain), U (P.PrintAgainPreview), BD (PrintAgainExecution), BE (PrintAgainCopy)

---

#### <a id="t34"></a>429.6 - CHECK HISTO

**Role** : Traitement : CHECK HISTO.
**Variables liees** : BF (L ExistHistoric ?)

---

#### <a id="t36"></a>429.7.1 - Package

**Role** : Traitement : Package.
**Variables liees** : F (P. Package id)

---

#### <a id="t37"></a>429.7.2 - Filiation

**Role** : Traitement : Filiation.
**Variables liees** : E (P. Filiation), P (P.Filiation)

---

#### <a id="t38"></a>429.8 - Search for Gift Pass [[ECRAN]](#ecran-t38)

**Role** : Calcul fidelite/avantage : Search for Gift Pass.
**Ecran** : 175 x 195 DLU | [Voir mockup](#ecran-t38)
**Variables liees** : BS (v Solde Gift Pass), BT (v Existe Gift Pass), BU (v.Message Solde Gift Pass)


### 3.3 Consultation (5 taches)

Ecrans de recherche et consultation.

---

#### <a id="t3"></a>429.2 - SELECTION [[ECRAN]](#ecran-t3)

**Role** : Selection par l'operateur : SELECTION.
**Ecran** : 640 x 0 DLU (MDI) | [Voir mockup](#ecran-t3)
**Delegue a** : [Recherche Adresse Mail (IDE 308)](PVE-IDE-308.md)

---

#### <a id="t4"></a>429.2.1 - Selection Packages [[ECRAN]](#ecran-t4)

**Role** : Selection par l'operateur : Selection Packages.
**Ecran** : 814 x 0 DLU (MDI) | [Voir mockup](#ecran-t4)
**Delegue a** : [Recherche Adresse Mail (IDE 308)](PVE-IDE-308.md)

---

#### <a id="t12"></a>429.2.2 - View Selection Packages [[ECRAN]](#ecran-t12)

**Role** : Selection par l'operateur : View Selection Packages.
**Ecran** : 1016 x 200 DLU (MDI) | [Voir mockup](#ecran-t12)
**Variables liees** : U (P.PrintAgainPreview)
**Delegue a** : [Recherche Adresse Mail (IDE 308)](PVE-IDE-308.md)

---

#### <a id="t13"></a>429.2.3 - Selection Filiations

**Role** : Selection par l'operateur : Selection Filiations.
**Delegue a** : [Recherche Adresse Mail (IDE 308)](PVE-IDE-308.md)

---

#### <a id="t31"></a>429.5.1.2 - Selection Filiations

**Role** : Selection par l'operateur : Selection Filiations.
**Delegue a** : [Recherche Adresse Mail (IDE 308)](PVE-IDE-308.md)


### 3.4 Calcul (2 taches)

Calculs metier : montants, stocks, compteurs.

---

#### <a id="t5"></a>429.2.1.1 - Selection Pv_Compta

**Role** : Selection par l'operateur : Selection Pv_Compta.

---

#### <a id="t30"></a>429.5.1.1 - Load temp compta

**Role** : Traitement : Load temp compta.


### 3.5 Validation (1 tache)

Controles de coherence : 1 tache verifie les donnees et conditions.

---

#### <a id="t11"></a>429.2.1.3 - Validate/Cancel Booker

**Role** : Verification : Validate/Cancel Booker.


### 3.6 Initialisation (1 tache)

Reinitialisation d'etats et variables de travail.

---

#### <a id="t35"></a>429.7 - RAZ TEMPO

**Role** : Reinitialisation : RAZ TEMPO.


### 3.7 Creation (1 tache)

Insertion de nouveaux enregistrements en base.

---

#### <a id="t39"></a>429.9 - CreationMail pour File Traitem

**Role** : Creation d'enregistrement : CreationMail pour File Traitem.
**Variables liees** : Q (P.File Name Signature)


## 5. REGLES METIER

1 regles identifiees:

### Autres (1 regles)

#### <a id="rm-RM-001"></a>[RM-001] Si VG33='TB' alors Trim(VG79)&Trim([AZ]) sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `VG33='TB'` |
| **Si vrai** | Trim(VG79)&Trim([AZ]) |
| **Si faux** | '') |
| **Expression source** | Expression 22 : `IF(VG33='TB',Trim(VG79)&Trim([AZ]),'')
` |
| **Exemple** | Si VG33='TB' â†’ Trim(VG79)&Trim([AZ]). Sinon â†’ '') |

## 6. CONTEXTE

- **Appele par**: (aucun)
- **Appelle**: 11 programmes | **Tables**: 23 (W:10 R:7 L:12) | **Taches**: 39 | **Expressions**: 38

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 39)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 429.2.2 | 429.2.2 | View Selection Packages | MDI | 1016 | 200 | Consultation |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t12"></a>429.2.2 - View Selection Packages
**Tache** : [429.2.2](#t12) | **Type** : MDI | **Dimensions** : 1016 x 200 DLU
**Bloc** : Consultation | **Titre IDE** : View Selection Packages

<!-- FORM-DATA:
{
    "width":  1016,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  8,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "",
                         "w":  1001,
                         "y":  8,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  13,
                         "h":  182,
                         "cols":  [
                                      {
                                          "title":  "pv_service",
                                          "layer":  1,
                                          "w":  45
                                      },
                                      {
                                          "title":  "ordre_edition",
                                          "layer":  2,
                                          "w":  52
                                      },
                                      {
                                          "title":  "pos_id",
                                          "layer":  3,
                                          "w":  58
                                      },
                                      {
                                          "title":  "payment_type",
                                          "layer":  4,
                                          "w":  94
                                      },
                                      {
                                          "title":  "xcust_id",
                                          "layer":  5,
                                          "w":  58
                                      },
                                      {
                                          "title":  "gm_societe",
                                          "layer":  6,
                                          "w":  46
                                      },
                                      {
                                          "title":  "gm_compte",
                                          "layer":  7,
                                          "w":  49
                                      },
                                      {
                                          "title":  "gm_filiation",
                                          "layer":  8,
                                          "w":  45
                                      },
                                      {
                                          "title":  "package_id_out",
                                          "layer":  9,
                                          "w":  65
                                      },
                                      {
                                          "title":  "package_id_in",
                                          "layer":  10,
                                          "w":  59
                                      },
                                      {
                                          "title":  "action_type",
                                          "layer":  11,
                                          "w":  66
                                      },
                                      {
                                          "title":  "payer_xcust_id",
                                          "layer":  12,
                                          "w":  60
                                      },
                                      {
                                          "title":  "validated__",
                                          "layer":  13,
                                          "w":  47
                                      },
                                      {
                                          "title":  "id_booker",
                                          "layer":  14,
                                          "w":  58
                                      },
                                      {
                                          "title":  "booking_id",
                                          "layer":  15,
                                          "w":  178
                                      }
                                  ],
                         "rows":  15
                     },
                     {
                         "x":  12,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  26,
                         "fmt":  "",
                         "name":  "pv_service",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  57,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  22,
                         "fmt":  "",
                         "name":  "ordre_edition",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  109,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  51,
                         "fmt":  "",
                         "name":  "pos_id",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  167,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  87,
                         "fmt":  "",
                         "name":  "payment_type",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  261,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  51,
                         "fmt":  "",
                         "name":  "xcust_id",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  319,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  9,
                         "fmt":  "",
                         "name":  "gm_societe",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  365,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  42,
                         "fmt":  "",
                         "name":  "gm_compte",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  414,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  18,
                         "fmt":  "",
                         "name":  "gm_filiation",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  459,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  51,
                         "fmt":  "",
                         "name":  "package_id_out",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  524,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  51,
                         "fmt":  "",
                         "name":  "package_id_in",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  583,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  59,
                         "fmt":  "",
                         "name":  "action_type",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  649,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  51,
                         "fmt":  "",
                         "name":  "payer_xcust_id",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  709,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  31,
                         "fmt":  "",
                         "name":  "validated__",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  756,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  51,
                         "fmt":  "",
                         "name":  "id_booker",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  814,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  171,
                         "fmt":  "",
                         "name":  "booking_id",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     }
                 ],
    "taskId":  "429.2.2",
    "height":  200
}
-->

<details>
<summary><strong>Champs : 15 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 12,23 | pv_service | - | edit |
| 57,23 | ordre_edition | - | edit |
| 109,23 | pos_id | - | edit |
| 167,23 | payment_type | - | edit |
| 261,23 | xcust_id | - | edit |
| 319,23 | gm_societe | - | edit |
| 365,23 | gm_compte | - | edit |
| 414,23 | gm_filiation | - | edit |
| 459,23 | package_id_out | - | edit |
| 524,23 | package_id_in | - | edit |
| 583,23 | action_type | - | edit |
| 649,23 | payer_xcust_id | - | edit |
| 709,23 | validated__ | - | edit |
| 756,23 | id_booker | - | edit |
| 814,23 | booking_id | - | edit |

</details>

## 9. NAVIGATION

Ecran unique: **View Selection Packages**

### 9.3 Structure hierarchique (39 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **429.1** | [**Print Invoice** (429)](#t1) [mockup](#ecran-t1) | MDI | 869x291 | Impression |
| 429.1.1 | [EDITION (429.3)](#t15) | MDI | - | |
| 429.1.2 | [PRINT AGAIN (429.5)](#t28) [mockup](#ecran-t28) | MDI | 375x240 | |
| 429.1.3 | [Print Again Gener (429.5.1)](#t29) | MDI | - | |
| **429.2** | [**PARAMETERS** (429.1)](#t2) | MDI | - | Traitement |
| 429.2.1 | [Temp generation Gift Pass (429.2.1.1.1)](#t6) | MDI | - | |
| 429.2.2 | [Temp generation (429.2.1.1.2)](#t7) | MDI | - | |
| 429.2.3 | [Temp generation (429.2.1.1.3)](#t8) | MDI | - | |
| 429.2.4 | [Temp generation Gift Pass (429.2.1.1.4)](#t9) | MDI | - | |
| 429.2.5 | [AddAppointmentToList (429.2.1.2)](#t10) | MDI | - | |
| 429.2.6 | [Temp generation (429.2.3.1)](#t14) | MDI | - | |
| 429.2.7 | [Package line (429.3.1)](#t16) [mockup](#ecran-t16) | MDI | 557x327 | |
| 429.2.8 | [Package line (429.3.1.1)](#t17) | MDI | - | |
| 429.2.9 | [Package blank line (429.3.2)](#t18) | MDI | - | |
| 429.2.10 | [Filiations (429.3.3)](#t19) | MDI | - | |
| 429.2.11 | [Ski Shoes Name (429.3.3.1)](#t20) | MDI | - | |
| 429.2.12 | [HISTO (429.4)](#t21) | MDI | - | |
| 429.2.13 | [Generation (429.4.1)](#t22) | MDI | - | |
| 429.2.14 | [header (429.4.1.1)](#t23) | MDI | - | |
| 429.2.15 | [Entete EZcard (429.4.1.1.1)](#t24) | MDI | - | |
| 429.2.16 | [Lines (429.4.1.2)](#t25) | MDI | - | |
| 429.2.17 | [Package line (429.4.2)](#t26) | MDI | - | |
| 429.2.18 | [Ligne EZcard (429.4.2.1)](#t27) | MDI | - | |
| 429.2.19 | [Temp generation (429.5.1.2.1)](#t32) | MDI | - | |
| 429.2.20 | [Trace Again (429.5.2)](#t33) | MDI | - | |
| 429.2.21 | [CHECK HISTO (429.6)](#t34) | MDI | - | |
| 429.2.22 | [Package (429.7.1)](#t36) | MDI | - | |
| 429.2.23 | [Filiation (429.7.2)](#t37) | MDI | - | |
| 429.2.24 | [Search for Gift Pass (429.8)](#t38) [mockup](#ecran-t38) | - | 175x195 | |
| **429.3** | [**SELECTION** (429.2)](#t3) [mockup](#ecran-t3) | MDI | 640x0 | Consultation |
| 429.3.1 | [Selection Packages (429.2.1)](#t4) [mockup](#ecran-t4) | MDI | 814x0 | |
| 429.3.2 | [View Selection Packages (429.2.2)](#t12) [mockup](#ecran-t12) | MDI | 1016x200 | |
| 429.3.3 | [Selection Filiations (429.2.3)](#t13) | MDI | - | |
| 429.3.4 | [Selection Filiations (429.5.1.2)](#t31) | MDI | - | |
| **429.4** | [**Selection Pv_Compta** (429.2.1.1)](#t5) | MDI | - | Calcul |
| 429.4.1 | [Load temp compta (429.5.1.1)](#t30) | MDI | - | |
| **429.5** | [**Validate/Cancel Booker** (429.2.1.3)](#t11) | MDI | - | Validation |
| **429.6** | [**RAZ TEMPO** (429.7)](#t35) | MDI | - | Initialisation |
| **429.7** | [**CreationMail pour File Traitem** (429.9)](#t39) | - | - | Creation |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Traitement principal]
    UPDATE[MAJ 10 tables]
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

### Tables utilisees (23)

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
| 379 | pv_customer_temp |  | DB | R |   |   | 2 |
| 382 | pv_discount_reasons |  | DB | R |   | L | 9 |
| 395 | pv_ownership |  | DB | R | **W** |   | 2 |
| 396 | pv_cust_packages |  | DB |   | **W** | L | 2 |
| 397 | pv_package_composants |  | DB |   | **W** |   | 1 |
| 400 | pv_cust_rentals |  | DB |   |   | L | 6 |
| 403 | pv_sellers |  | DB |   |   | L | 2 |
| 404 | pv_sellers_by_week |  | DB | R |   | L | 4 |
| 413 | pv_tva |  | DB |   |   | L | 2 |
| 419 | realise_articles_caution | Articles et stock | DB |   |   | L | 3 |
| 531 | import_avertiss__an_val |  | DB |   | **W** | L | 4 |
| 533 | cumul_mvt_stock_histo | Articles et stock | TMP |   | **W** | L | 13 |
| 1501 | Table_1501 |  | MEM |   | **W** |   | 1 |
| 1539 | Table_1539 |  | MEM |   |   | L | 2 |
| 1548 | Table_1548 |  | MEM |   | **W** |   | 2 |

### Colonnes par table (11 / 16 tables avec colonnes identifiees)

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
| U | P.PrintAgainPreview | R | Logical |
| V | P.NomFichierPdf | R | Alpha |
| W | P.Num Dossier AXIS | R | Alpha |
| X | P.Num Acceptation | R | Alpha |
| Y | V VillageCode | R | Alpha |
| Z | V AmountFormat | R | Alpha |
| BA | V VatValue | R | Numeric |
| BB | V Currency | R | Alpha |
| BC | V Decimal | R | Numeric |
| BD | PrintAgainExecution | R | Logical |
| BE | PrintAgainCopy | R | Numeric |
| BF | L ExistHistoric ? | R | Logical |
| BG | HeaderLine01 | R | Alpha |
| BH | HeaderLine02 | R | Alpha |
| BI | HeaderLine03 | R | Alpha |
| BJ | HeaderLine04 | R | Alpha |
| BK | HeaderLine05 | R | Alpha |
| BL | HeaderLine06 | R | Alpha |
| BM | HeaderLine07 | R | Alpha |
| BN | HeaderLine08 | R | Alpha |
| BO | HeaderLine09 | R | Alpha |
| BP | HeaderLine10 | R | Alpha |
| BQ | HeaderLine11 | R | Alpha |
| BR | V Facture | R | Numeric |
| BS | v Solde Gift Pass | R | Numeric |
| BT | v Existe Gift Pass | R | Logical |
| BU | v.Message Solde Gift Pass | R | Alpha |
| BV | V Nom Fic Pdf Ticket Mobilit | R | Alpha |
| BW | v Langue Mail | R | Alpha |
| BX | v Existe Vente Mobilité | R | Logical |
| BY | v Validation envoi mail ? | R | Logical |

</details>

<details>
<summary>Table 377 - pv_contracts (R) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 379 - pv_customer_temp (R) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | V.packageID | R | Numeric |
| B | V.PaymentMethodeID | R | Numeric |
| C | FirstRecord | R | Logical |

</details>

<details>
<summary>Table 382 - pv_discount_reasons (R/L) - 9 usages</summary>

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
| A | V.packageID | W | Numeric |
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
| A | V.HeaderChrono | W | Numeric |
| B | V.Chrono TENV10 | W | Numeric |

</details>

<details>
<summary>Table 1501 - Table_1501 (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 1548 - Table_1548 (**W**) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (24)

Variables recues en parametre.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P. Payer XCust Id | Numeric | 3x parametre entrant |
| B | P. Customer Id | Numeric | 2x parametre entrant |
| C | P. Societe | Alpha | - |
| D | P. Compte | Numeric | - |
| E | P. Filiation | Numeric | - |
| F | P. Package id | Numeric | [429.2.1](#t4), [429.2.2](#t12), [429.3.1](#t16) |
| G | P. PrintAgain | Logical | 2x parametre entrant |
| H | P. Copies | Numeric | - |
| I | P. Total Ticket | Numeric | - |
| J | P. Total Crédit Conso | Numeric | - |
| K | P. EZcard | Alpha | - |
| L | P. Card type | Alpha | - |
| M | P. Service | Alpha | 3x parametre entrant |
| N | P.Societe | Alpha | - |
| O | P.Adherent | Numeric | - |
| P | P.Filiation | Numeric | - |
| Q | P.File Name Signature | Numeric | [429.3.3.1](#t20) |
| R | p.ValidationMail | Logical | 2x parametre entrant |
| S | P Adresse Mail (MOB) | Alpha | [429.9](#t39) |
| T | p.No_Facture | Numeric | - |
| U | P.PrintAgainPreview | Logical | - |
| V | P.NomFichierPdf | Alpha | - |
| W | P.Num Dossier AXIS | Alpha | - |
| X | P.Num Acceptation | Alpha | - |

### 11.2 Variables de session (13)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| Y | V VillageCode | Alpha | - |
| Z | V AmountFormat | Alpha | - |
| BA | V VatValue | Numeric | - |
| BB | V Currency | Alpha | - |
| BC | V Decimal | Numeric | 2x session |
| BR | V Facture | Numeric | - |
| BS | v Solde Gift Pass | Numeric | - |
| BT | v Existe Gift Pass | Logical | - |
| BU | v.Message Solde Gift Pass | Alpha | - |
| BV | V Nom Fic Pdf Ticket Mobilit | Alpha | - |
| BW | v Langue Mail | Alpha | - |
| BX | v Existe Vente Mobilité | Logical | - |
| BY | v Validation envoi mail ? | Logical | - |

### 11.3 Autres (14)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| BD | PrintAgainExecution | Logical | - |
| BE | PrintAgainCopy | Numeric | - |
| BF | L ExistHistoric ? | Logical | - |
| BG | HeaderLine01 | Alpha | - |
| BH | HeaderLine02 | Alpha | - |
| BI | HeaderLine03 | Alpha | - |
| BJ | HeaderLine04 | Alpha | - |
| BK | HeaderLine05 | Alpha | - |
| BL | HeaderLine06 | Alpha | - |
| BM | HeaderLine07 | Alpha | - |
| BN | HeaderLine08 | Alpha | - |
| BO | HeaderLine09 | Alpha | - |
| BP | HeaderLine10 | Alpha | - |
| BQ | HeaderLine11 | Alpha | - |

<details>
<summary>Toutes les 51 variables (liste complete)</summary>

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
| P0 | **U** | P.PrintAgainPreview | Logical |
| P0 | **V** | P.NomFichierPdf | Alpha |
| P0 | **W** | P.Num Dossier AXIS | Alpha |
| P0 | **X** | P.Num Acceptation | Alpha |
| V. | **Y** | V VillageCode | Alpha |
| V. | **Z** | V AmountFormat | Alpha |
| V. | **BA** | V VatValue | Numeric |
| V. | **BB** | V Currency | Alpha |
| V. | **BC** | V Decimal | Numeric |
| V. | **BR** | V Facture | Numeric |
| V. | **BS** | v Solde Gift Pass | Numeric |
| V. | **BT** | v Existe Gift Pass | Logical |
| V. | **BU** | v.Message Solde Gift Pass | Alpha |
| V. | **BV** | V Nom Fic Pdf Ticket Mobilit | Alpha |
| V. | **BW** | v Langue Mail | Alpha |
| V. | **BX** | v Existe Vente Mobilité | Logical |
| V. | **BY** | v Validation envoi mail ? | Logical |
| Autre | **BD** | PrintAgainExecution | Logical |
| Autre | **BE** | PrintAgainCopy | Numeric |
| Autre | **BF** | L ExistHistoric ? | Logical |
| Autre | **BG** | HeaderLine01 | Alpha |
| Autre | **BH** | HeaderLine02 | Alpha |
| Autre | **BI** | HeaderLine03 | Alpha |
| Autre | **BJ** | HeaderLine04 | Alpha |
| Autre | **BK** | HeaderLine05 | Alpha |
| Autre | **BL** | HeaderLine06 | Alpha |
| Autre | **BM** | HeaderLine07 | Alpha |
| Autre | **BN** | HeaderLine08 | Alpha |
| Autre | **BO** | HeaderLine09 | Alpha |
| Autre | **BP** | HeaderLine10 | Alpha |
| Autre | **BQ** | HeaderLine11 | Alpha |

</details>

## 12. EXPRESSIONS

**38 / 38 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CAST_LOGIQUE | 1 | 0 |
| CONDITION | 10 | 5 |
| CONSTANTE | 5 | 0 |
| FORMAT | 5 | 0 |
| NEGATION | 3 | 0 |
| OTHER | 12 | 0 |
| REFERENCE_VG | 1 | 0 |
| STRING | 1 | 0 |

### 12.2 Expressions cles par type

#### CAST_LOGIQUE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 3 | `Trim(P Adresse Mail (MOB) [S])&' / '&'Validation ='&IF(p.ValidationMail [R]='TRUE'LOG,'Vrai','Faux')` | - |

#### CONDITION (10 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 22 | `IF(VG33='TB',Trim(VG79)&Trim([AZ]),'')
` | [RM-001](#rm-RM-001) |
| CONDITION | 35 | `VG33='TB'` | - |
| CONDITION | 24 | `VG32 AND VG33='WS'` | - |
| CONDITION | 33 | `Trim(P Adresse Mail (MOB) [S])=''` | - |
| CONDITION | 38 | `VG33='TB'` | - |
| ... | | *+5 autres* | |

#### CONSTANTE (5 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 26 | `'Ticket has been generated, and will be send by an Email .'` | - |
| CONSTANTE | 27 | `'Ticket has been generated.'` | - |
| CONSTANTE | 14 | `'O'` | - |
| CONSTANTE | 2 | `1` | - |
| CONSTANTE | 13 | `'VSERV'` | - |

#### FORMAT (5 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| FORMAT | 6 | `FileRename (Trim(VG80)&Trim(Str(P.File Name Signature [Q],'6Z'))&'.gif',Trim(VG80)&Trim(Str([AR],'6Z'))&'.gif')` | - |
| FORMAT | 32 | `Trim(VG80)&Trim(Str([AR],'6Z'))&'.gif'` | - |
| FORMAT | 37 | `'Error during the sale receipt generation.
Please contact the support with the following information :
Payer Id : '&Str(P. Payer XCust Id [A],'9')&ASCIIChr(13)
&'Customer Id : '&IF(P. Customer Id [B]=0,'All Filiations',Str(P. Customer Id [B],'9'))&ASCIIChr(13)
&'Package Id : '&IF(P. Package id [F]=0,'All Packages',Str(P. Package id [F],'9'))&ASCIIChr(13)
&'Date : '&DStr(Date(),'DD/MM/YYYY')&ASCIIChr(13)
&'Time : '&TStr(Time(),'HH:MM:SS')` | - |
| FORMAT | 17 | `'Solde Free  Extra au : '&DStr(Date(),'DD/MM/YYYY')&' à : '&TStr(Time(),('HH:MM:SS'))` | - |
| FORMAT | 23 | `'Receipt_'&Trim(P. Service [M])&'_'&Trim(Str([AR],'6Z'))&'_'&DStr(Date(),'YYYYMMDD')&'.pdf'` | - |

#### NEGATION (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| NEGATION | 12 | `NOT (P. Service [M]='SKIN')` | - |
| NEGATION | 10 | `NOT ([AF])` | - |
| NEGATION | 7 | `NOT (P. PrintAgain [G])` | - |

#### OTHER (12 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 30 | `P. Payer XCust Id [A]` | - |
| OTHER | 29 | `NOT(V Decimal [BC])` | - |
| OTHER | 28 | `V Decimal [BC]` | - |
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
| STRING | 20 | `FileDelete (Trim([AZ]))` | - |

### 12.3 Toutes les expressions (38)

<details>
<summary>Voir les 38 expressions</summary>

#### CAST_LOGIQUE (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 3 | `Trim(P Adresse Mail (MOB) [S])&' / '&'Validation ='&IF(p.ValidationMail [R]='TRUE'LOG,'Vrai','Faux')` |

#### CONDITION (10)

| IDE | Expression Decodee |
|-----|-------------------|
| 22 | `IF(VG33='TB',Trim(VG79)&Trim([AZ]),'')
` |
| 1 | `P. Payer XCust Id [A]=0` |
| 4 | `DbRecs ('{533,3}'DSOURCE,'')=0` |
| 5 | `DbRecs ('{533,3}'DSOURCE,'')>0` |
| 11 | `P. Service [M]='SKIN'` |
| 21 | `VG33='TB'` |
| 24 | `VG32 AND VG33='WS'` |
| 35 | `VG33='TB'` |
| 38 | `VG33='TB'` |
| 33 | `Trim(P Adresse Mail (MOB) [S])=''` |

#### CONSTANTE (5)

| IDE | Expression Decodee |
|-----|-------------------|
| 2 | `1` |
| 13 | `'VSERV'` |
| 14 | `'O'` |
| 26 | `'Ticket has been generated, and will be send by an Email .'` |
| 27 | `'Ticket has been generated.'` |

#### FORMAT (5)

| IDE | Expression Decodee |
|-----|-------------------|
| 17 | `'Solde Free  Extra au : '&DStr(Date(),'DD/MM/YYYY')&' à : '&TStr(Time(),('HH:MM:SS'))` |
| 23 | `'Receipt_'&Trim(P. Service [M])&'_'&Trim(Str([AR],'6Z'))&'_'&DStr(Date(),'YYYYMMDD')&'.pdf'` |
| 37 | `'Error during the sale receipt generation.
Please contact the support with the following information :
Payer Id : '&Str(P. Payer XCust Id [A],'9')&ASCIIChr(13)
&'Customer Id : '&IF(P. Customer Id [B]=0,'All Filiations',Str(P. Customer Id [B],'9'))&ASCIIChr(13)
&'Package Id : '&IF(P. Package id [F]=0,'All Packages',Str(P. Package id [F],'9'))&ASCIIChr(13)
&'Date : '&DStr(Date(),'DD/MM/YYYY')&ASCIIChr(13)
&'Time : '&TStr(Time(),'HH:MM:SS')` |
| 6 | `FileRename (Trim(VG80)&Trim(Str(P.File Name Signature [Q],'6Z'))&'.gif',Trim(VG80)&Trim(Str([AR],'6Z'))&'.gif')` |
| 32 | `Trim(VG80)&Trim(Str([AR],'6Z'))&'.gif'` |

#### NEGATION (3)

| IDE | Expression Decodee |
|-----|-------------------|
| 7 | `NOT (P. PrintAgain [G])` |
| 10 | `NOT ([AF])` |
| 12 | `NOT (P. Service [M]='SKIN')` |

#### OTHER (12)

| IDE | Expression Decodee |
|-----|-------------------|
| 8 | `P. PrintAgain [G]` |
| 9 | `[AD]` |
| 15 | `GetParam('SERVICE')` |
| 16 | `NOT(VG20)` |
| 19 | `[AX]` |
| 25 | `SetCrsr (1)` |
| 28 | `V Decimal [BC]` |
| 29 | `NOT(V Decimal [BC])` |
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
| 20 | `FileDelete (Trim([AZ]))` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

**Chemin**: (pas de callers directs)

```mermaid
graph LR
    T429[429 Print Invoice or T...]
    style T429 fill:#58a6ff
    NONE[Aucun caller]
    NONE -.-> T429
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| - | (aucun) | - |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T429[429 Print Invoice or T...]
    style T429 fill:#58a6ff
    C159[159 CancelAppointment]
    T429 --> C159
    style C159 fill:#3fb950
    C169[169 AddPaymentToOrder]
    T429 --> C169
    style C169 fill:#3fb950
    C174[174 GetLocationPayment...]
    T429 --> C174
    style C174 fill:#3fb950
    C205[205 Edition ticket Tva...]
    T429 --> C205
    style C205 fill:#3fb950
    C232[232 Existe Vente Mobilité]
    T429 --> C232
    style C232 fill:#3fb950
    C273[273 Edition ticket]
    T429 --> C273
    style C273 fill:#3fb950
    C278[278 Set Customer]
    T429 --> C278
    style C278 fill:#3fb950
    C308[308 Recherche Adresse ...]
    T429 --> C308
    style C308 fill:#3fb950
    C314[314 Get default email ...]
    T429 --> C314
    style C314 fill:#3fb950
    C320[320 SynchronisationRec...]
    T429 --> C320
    style C320 fill:#3fb950
    C365[365 Saisie Signature]
    T429 --> C365
    style C365 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [159](PVE-IDE-159.md) | CancelAppointment | 2 | Sous-programme |
| [169](PVE-IDE-169.md) | AddPaymentToOrder | 2 | Sous-programme |
| [174](PVE-IDE-174.md) | GetLocationPaymentSettings | 2 | Recuperation donnees |
| [205](PVE-IDE-205.md) | Edition ticket (Tva) LEX | 2 | Impression ticket/document |
| [232](PVE-IDE-232.md) | Existe Vente Mobilité | 1 | Sous-programme |
| [273](PVE-IDE-273.md) | Edition ticket | 1 | Impression ticket/document |
| [278](PVE-IDE-278.md) | Set Customer | 1 | Sous-programme |
| [308](PVE-IDE-308.md) | Recherche Adresse Mail | 1 | Sous-programme |
| [314](PVE-IDE-314.md) | Get default email address | 1 | Recuperation donnees |
| [320](PVE-IDE-320.md) | SynchronisationRecuPDF | 1 | Recuperation donnees |
| [365](PVE-IDE-365.md) | Saisie Signature | 1 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 1331 | Programme volumineux |
| Expressions | 38 | Peu de logique |
| Tables WRITE | 10 | Fort impact donnees |
| Sous-programmes | 11 | Forte dependance |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 3.3% (44 / 1331) | Code sain |
| Regles metier | 1 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Impression (4 taches: 2 ecrans, 2 traitements)

- **Strategie** : Templates HTML -> PDF via wkhtmltopdf ou Puppeteer.
- `PrintService` injectable avec choix imprimante

#### Traitement (25 taches: 2 ecrans, 23 traitements)

- **Strategie** : Orchestrateur avec 2 ecrans (Razor/React) et 23 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 11 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Consultation (5 taches: 3 ecrans, 2 traitements)

- **Strategie** : Composants de recherche/selection en modales.
- 3 ecrans : SELECTION, Selection Packages, View Selection Packages

#### Calcul (2 taches: 0 ecran, 2 traitements)

- **Strategie** : Services de calcul purs (Domain Services).
- Migrer la logique de calcul (stock, compteurs, montants)

#### Validation (1 tache: 0 ecran, 1 traitement)

- **Strategie** : FluentValidation avec validators specifiques.
- Chaque tache de validation -> un validator injectable

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
| Table_1548 | Table WRITE (Memory) | 2x | Schema + repository |
| [GetLocationPaymentSettings (IDE 174)](PVE-IDE-174.md) | Sous-programme | 2x | Haute - Recuperation donnees |
| [Edition ticket (Tva) LEX (IDE 205)](PVE-IDE-205.md) | Sous-programme | 2x | Haute - Impression ticket/document |
| [CancelAppointment (IDE 159)](PVE-IDE-159.md) | Sous-programme | 2x | Haute - Sous-programme |
| [AddPaymentToOrder (IDE 169)](PVE-IDE-169.md) | Sous-programme | 2x | Haute - Sous-programme |
| [Get default email address (IDE 314)](PVE-IDE-314.md) | Sous-programme | 1x | Normale - Recuperation donnees |
| [SynchronisationRecuPDF (IDE 320)](PVE-IDE-320.md) | Sous-programme | 1x | Normale - Recuperation donnees |
| [Saisie Signature (IDE 365)](PVE-IDE-365.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Recherche Adresse Mail (IDE 308)](PVE-IDE-308.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Existe Vente Mobilité (IDE 232)](PVE-IDE-232.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Edition ticket (IDE 273)](PVE-IDE-273.md) | Sous-programme | 1x | Normale - Impression ticket/document |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 20:06*
