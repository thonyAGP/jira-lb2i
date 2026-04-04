# PVE IDE 214 - Main Sale Sale Bar Code

> **Analyse**: Phases 1-4 2026-02-03 18:57 -> 18:57 (18s) | Assemblage 18:57
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PVE |
| IDE Position | 214 |
| Nom Programme | Main Sale Sale Bar Code |
| Fichier source | `Prg_214.xml` |
| Dossier IDE | Packages |
| Taches | 64 (26 ecrans visibles) |
| Tables modifiees | 10 |
| Programmes appeles | 20 |

## 2. DESCRIPTION FONCTIONNELLE

**Main Sale Sale Bar Code** assure la gestion complete de ce processus, accessible depuis [Menu (IDE 185)](PVE-IDE-185.md).

Le flux de traitement s'organise en **7 blocs fonctionnels** :

- **Traitement** (44 taches) : traitements metier divers
- **Creation** (7 taches) : insertion d'enregistrements en base (mouvements, prestations)
- **Consultation** (5 taches) : ecrans de recherche, selection et consultation
- **Saisie** (3 taches) : ecrans de saisie utilisateur (formulaires, champs, donnees)
- **Validation** (2 taches) : controles et verifications de coherence
- **Initialisation** (2 taches) : reinitialisation d'etats et de variables de travail
- **Calcul** (1 tache) : calculs de montants, stocks ou compteurs

**Donnees modifiees** : 10 tables en ecriture (pv_customer, pv_customer_temp, pv_discount_reasons, pv_cust_rentals, pv_sellers_by_week, pv_tva, Table_1501, Table_1539, Table_1548, Table_1550).

**Logique metier** : 17 regles identifiees couvrant conditions metier, valeurs par defaut.

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (44 taches)

- **214** - Main Sale V4 **[[ECRAN]](#ecran-t1)**
- **214.1.1** - equipement **[[ECRAN]](#ecran-t3)**
- **214.1.1.1** - Equipment check out **[[ECRAN]](#ecran-t4)**
- **214.1.1.1.1** - clear
- **214.1.1.1.2** - Récupère Libellé Classif
- **214.1.1.2** - Equipment list **[[ECRAN]](#ecran-t7)**
- **214.1.1.2.1** - Equipment check out **[[ECRAN]](#ecran-t8)**
- **214.1.1.2.2** - Equipment list **[[ECRAN]](#ecran-t9)**
- **214.1.1.2.2.1** - Equipment check IN **[[ECRAN]](#ecran-t10)**
- **214.1.2** - Booking_ID **[[ECRAN]](#ecran-t11)**
- **214.1.2.2.2** - Packages **[[ECRAN]](#ecran-t15)**
- **214.1.2.2.2.1** - Sub cat **[[ECRAN]](#ecran-t16)**
- **214.1.2.2.2.1.1** - Products **[[ECRAN]](#ecran-t17)**
- **214.1.2.2.3** - Get last package id
- **214.1.2.2.4** - Package=> cust account **[[ECRAN]](#ecran-t19)**
- **214.1.3** - Onglet Booking **[[ECRAN]](#ecran-t23)**
- **214.1.3.2** - Booking **[[ECRAN]](#ecran-t25)**
- **214.1.3.3** - Screen **[[ECRAN]](#ecran-t26)**
- **214.1.3.4** - GetBookigsInfo
- **214.1.3.6** - Apparier /t forfait/package
- **214.1.3.7.2.1** - Del ligne vide
- **214.1.4** - Transac not PMS **[[ECRAN]](#ecran-t34)**
- **214.1.4.1** - Get prod id
- **214.1.4.2** - Get Cat & Subcat
- **214.1.5** - Sales and Payment **[[ECRAN]](#ecran-t37)**
- **214.1.5.1** - Payment **[[ECRAN]](#ecran-t38)**
- **214.1.5.1.2** - View
- **214.1.5.2** - Discount **[[ECRAN]](#ecran-t42)**
- **214.1.5.3** - Test Prepaid
- **214.1.5.4** - Special actions **[[ECRAN]](#ecran-t45)**
- **214.1.5.4.1** - Cancel other Packages **[[ECRAN]](#ecran-t46)**
- **214.1.5.4.1.1** - UpdateCustRentals
- **214.1.5.4.3** - End of rental **[[ECRAN]](#ecran-t49)**
- **214.1.5.4.4** - UpdateCustRentals
- **214.1.5.5** - Check Rentals
- **214.1.5.6** - Check Payments **[[ECRAN]](#ecran-t52)**
- **214.1.5.7** - Check Comment Refus. To Sell **[[ECRAN]](#ecran-t53)**
- **214.1.5.8** - Discount **[[ECRAN]](#ecran-t54)**
- **214.1.5.9** - Delete other Packages **[[ECRAN]](#ecran-t56)**
- **214.1.5.11** - SQL Total payement **[[ECRAN]](#ecran-t58)**
- **214.1.6** - Transac not PMS MBO **[[ECRAN]](#ecran-t59)**
- **214.1.6.1** - SQL Total payement **[[ECRAN]](#ecran-t60)**
- **214.1.1.2.1.1** - Confirm **[[ECRAN]](#ecran-t65)**
- **214.1.1.2.1.2** - Récupère Libellé Classif

Delegue a : [Update INV equipment status (IDE 93)](PVE-IDE-93.md), [Lancement clavier (IDE 317)](PVE-IDE-317.md), [      Package=> account (IDE 196)](PVE-IDE-196.md), [FindAppointments (IDE 176)](PVE-IDE-176.md), [Menu Check IN / Exchange (IDE 183)](PVE-IDE-183.md), [GetAppointment (IDE 161)](PVE-IDE-161.md), [Generate Preview Payments (IDE 189)](PVE-IDE-189.md), [Delete Product (IDE 194)](PVE-IDE-194.md), [Discounts (IDE 201)](PVE-IDE-201.md), [SynchronisationRecuPDF (IDE 320)](PVE-IDE-320.md), [Question M&E (IDE 324)](PVE-IDE-324.md), [SearchBooking (IDE 153)](PVE-IDE-153.md), [FindRooms (IDE 157)](PVE-IDE-157.md), [FindEmployees (IDE 158)](PVE-IDE-158.md)

#### Phase 2 : Consultation (5 taches)

- **214.1** - Choix Onglet **[[ECRAN]](#ecran-t2)**
- **214.1.2.2** - Select Appointments **[[ECRAN]](#ecran-t13)**
- **214.1.2.2.1** - Select all
- **214.1.3.7** - Select Appointments **[[ECRAN]](#ecran-t30)**
- **214.1.3.7.1** - Select all

Delegue a : [Choix - Equipements (IDE 342)](PVE-IDE-342.md), [GetAppointment (IDE 161)](PVE-IDE-161.md), [SynchronisationRecuPDF (IDE 320)](PVE-IDE-320.md)

#### Phase 3 : Creation (7 taches)

- **214.1.2.1** - CreateSales
- **214.1.2.2.4.1** - Create cust rentals **[[ECRAN]](#ecran-t20)**
- **214.1.2.2.4.2** - Create Card Type
- **214.1.2.2.4.3** - create cust package **[[ECRAN]](#ecran-t22)**
- **214.1.3.5** - CreateMail
- **214.1.3.7.2** - CreateSales
- **214.1.5.1.3** - create cardType

#### Phase 4 : Initialisation (2 taches)

- **214.1.3.1** - Raz mem booking
- **214.1.5.1.1** - init payer

#### Phase 5 : Saisie (3 taches)

- **214.1.5.2.1** - Saisie comment annulation **[[ECRAN]](#ecran-t43)**
- **214.1.5.4.2** - Saisie comment annulation **[[ECRAN]](#ecran-t48)**
- **214.1.5.8.1** - Saisie comment annulation **[[ECRAN]](#ecran-t55)**

Delegue a : [Saisie commentaire (IDE 200)](PVE-IDE-200.md)

#### Phase 6 : Validation (2 taches)

- **214.1.5.10** - Verif Multi-Payeurs comptes <> **[[ECRAN]](#ecran-t57)**
- **214.1.5.12** - verify not already canceled

Delegue a : [ControleBookingId (IDE 165)](PVE-IDE-165.md)

#### Phase 7 : Calcul (1 tache)

- **214.2** - calcul filiation

Delegue a : [Calcul - binding setting (IDE 95)](PVE-IDE-95.md)

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| pv_cust_rentals | R/**W**/L (22 usages) |  |
| pv_discount_reasons | R/**W**/L (16 usages) |  |
| Table_1539 | R/**W**/L (11 usages) |  |
| pv_sellers_by_week | **W**/L (9 usages) |  |
| pv_tva | **W**/L (9 usages) |  |
| Table_1548 | **W**/L (7 usages) |  |
| Table_1550 | **W**/L (5 usages) |  |
| pv_customer_temp | R/**W**/L (5 usages) |  |
| pv_customer | **W**/L (3 usages) |  |
| Table_1501 | **W** (1 usages) |  |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (44 taches)

Traitements internes.

---

#### <a id="t1"></a>214 - Main Sale V4 [[ECRAN]](#ecran-t1)

**Role** : Tache d'orchestration : point d'entree du programme (44 sous-taches). Coordonne l'enchainement des traitements.
**Ecran** : 1990 x 392 DLU (Modal) | [Voir mockup](#ecran-t1)

<details>
<summary>43 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [214.1.1](#t3) | equipement **[[ECRAN]](#ecran-t3)** | Traitement |
| [214.1.1.1](#t4) | Equipment check out **[[ECRAN]](#ecran-t4)** | Traitement |
| [214.1.1.1.1](#t5) | clear | Traitement |
| [214.1.1.1.2](#t6) | Récupère Libellé Classif | Traitement |
| [214.1.1.2](#t7) | Equipment list **[[ECRAN]](#ecran-t7)** | Traitement |
| [214.1.1.2.1](#t8) | Equipment check out **[[ECRAN]](#ecran-t8)** | Traitement |
| [214.1.1.2.2](#t9) | Equipment list **[[ECRAN]](#ecran-t9)** | Traitement |
| [214.1.1.2.2.1](#t10) | Equipment check IN **[[ECRAN]](#ecran-t10)** | Traitement |
| [214.1.2](#t11) | Booking_ID **[[ECRAN]](#ecran-t11)** | Traitement |
| [214.1.2.2.2](#t15) | Packages **[[ECRAN]](#ecran-t15)** | Traitement |
| [214.1.2.2.2.1](#t16) | Sub cat **[[ECRAN]](#ecran-t16)** | Traitement |
| [214.1.2.2.2.1.1](#t17) | Products **[[ECRAN]](#ecran-t17)** | Traitement |
| [214.1.2.2.3](#t18) | Get last package id | Traitement |
| [214.1.2.2.4](#t19) | Package=> cust account **[[ECRAN]](#ecran-t19)** | Traitement |
| [214.1.3](#t23) | Onglet Booking **[[ECRAN]](#ecran-t23)** | Traitement |
| [214.1.3.2](#t25) | Booking **[[ECRAN]](#ecran-t25)** | Traitement |
| [214.1.3.3](#t26) | Screen **[[ECRAN]](#ecran-t26)** | Traitement |
| [214.1.3.4](#t27) | GetBookigsInfo | Traitement |
| [214.1.3.6](#t29) | Apparier /t forfait/package | Traitement |
| [214.1.3.7.2.1](#t33) | Del ligne vide | Traitement |
| [214.1.4](#t34) | Transac not PMS **[[ECRAN]](#ecran-t34)** | Traitement |
| [214.1.4.1](#t35) | Get prod id | Traitement |
| [214.1.4.2](#t36) | Get Cat & Subcat | Traitement |
| [214.1.5](#t37) | Sales and Payment **[[ECRAN]](#ecran-t37)** | Traitement |
| [214.1.5.1](#t38) | Payment **[[ECRAN]](#ecran-t38)** | Traitement |
| [214.1.5.1.2](#t40) | View | Traitement |
| [214.1.5.2](#t42) | Discount **[[ECRAN]](#ecran-t42)** | Traitement |
| [214.1.5.3](#t44) | Test Prepaid | Traitement |
| [214.1.5.4](#t45) | Special actions **[[ECRAN]](#ecran-t45)** | Traitement |
| [214.1.5.4.1](#t46) | Cancel other Packages **[[ECRAN]](#ecran-t46)** | Traitement |
| [214.1.5.4.1.1](#t47) | UpdateCustRentals | Traitement |
| [214.1.5.4.3](#t49) | End of rental **[[ECRAN]](#ecran-t49)** | Traitement |
| [214.1.5.4.4](#t50) | UpdateCustRentals | Traitement |
| [214.1.5.5](#t51) | Check Rentals | Traitement |
| [214.1.5.6](#t52) | Check Payments **[[ECRAN]](#ecran-t52)** | Traitement |
| [214.1.5.7](#t53) | Check Comment Refus. To Sell **[[ECRAN]](#ecran-t53)** | Traitement |
| [214.1.5.8](#t54) | Discount **[[ECRAN]](#ecran-t54)** | Traitement |
| [214.1.5.9](#t56) | Delete other Packages **[[ECRAN]](#ecran-t56)** | Traitement |
| [214.1.5.11](#t58) | SQL Total payement **[[ECRAN]](#ecran-t58)** | Traitement |
| [214.1.6](#t59) | Transac not PMS MBO **[[ECRAN]](#ecran-t59)** | Traitement |
| [214.1.6.1](#t60) | SQL Total payement **[[ECRAN]](#ecran-t60)** | Traitement |
| [214.1.1.2.1.1](#t65) | Confirm **[[ECRAN]](#ecran-t65)** | Traitement |
| [214.1.1.2.1.2](#t71) | Récupère Libellé Classif | Traitement |

</details>

---

#### <a id="t3"></a>214.1.1 - equipement [[ECRAN]](#ecran-t3)

**Role** : Traitement : equipement.
**Ecran** : 971 x 229 DLU (Modal) | [Voir mockup](#ecran-t3)
**Variables liees** : S (v.LequipementID)

---

#### <a id="t4"></a>214.1.1.1 - Equipment check out [[ECRAN]](#ecran-t4)

**Role** : Traitement : Equipment check out.
**Ecran** : 320 x 254 DLU (MDI) | [Voir mockup](#ecran-t4)
**Variables liees** : B (v.LequipmentId)

---

#### <a id="t5"></a>214.1.1.1.1 - clear

**Role** : Traitement : clear.

---

#### <a id="t6"></a>214.1.1.1.2 - Récupère Libellé Classif

**Role** : Traitement : Récupère Libellé Classif.

---

#### <a id="t7"></a>214.1.1.2 - Equipment list [[ECRAN]](#ecran-t7)

**Role** : Traitement : Equipment list.
**Ecran** : 269 x 280 DLU (MDI) | [Voir mockup](#ecran-t7)
**Variables liees** : B (v.LequipmentId), L (v.Filiation_List)

---

#### <a id="t8"></a>214.1.1.2.1 - Equipment check out [[ECRAN]](#ecran-t8)

**Role** : Traitement : Equipment check out.
**Ecran** : 322 x 282 DLU (MDI) | [Voir mockup](#ecran-t8)
**Variables liees** : B (v.LequipmentId)

---

#### <a id="t9"></a>214.1.1.2.2 - Equipment list [[ECRAN]](#ecran-t9)

**Role** : Traitement : Equipment list.
**Ecran** : 190 x 280 DLU (MDI) | [Voir mockup](#ecran-t9)
**Variables liees** : B (v.LequipmentId), L (v.Filiation_List)

---

#### <a id="t10"></a>214.1.1.2.2.1 - Equipment check IN [[ECRAN]](#ecran-t10)

**Role** : Traitement : Equipment check IN.
**Ecran** : 642 x 281 DLU (Type6) | [Voir mockup](#ecran-t10)
**Variables liees** : B (v.LequipmentId)

---

#### <a id="t11"></a>214.1.2 - Booking_ID [[ECRAN]](#ecran-t11)

**Role** : Traitement : Booking_ID.
**Ecran** : 973 x 248 DLU (Modal) | [Voir mockup](#ecran-t11)

---

#### <a id="t15"></a>214.1.2.2.2 - Packages [[ECRAN]](#ecran-t15)

**Role** : Traitement : Packages.
**Ecran** : 581 x 366 DLU (MDI) | [Voir mockup](#ecran-t15)

---

#### <a id="t16"></a>214.1.2.2.2.1 - Sub cat [[ECRAN]](#ecran-t16)

**Role** : Traitement : Sub cat.
**Ecran** : 386 x 324 DLU (Modal) | [Voir mockup](#ecran-t16)

---

#### <a id="t17"></a>214.1.2.2.2.1.1 - Products [[ECRAN]](#ecran-t17)

**Role** : Traitement : Products.
**Ecran** : 182 x 314 DLU (Modal) | [Voir mockup](#ecran-t17)

---

#### <a id="t18"></a>214.1.2.2.3 - Get last package id

**Role** : Consultation/chargement : Get last package id.

---

#### <a id="t19"></a>214.1.2.2.4 - Package=> cust account [[ECRAN]](#ecran-t19)

**Role** : Traitement : Package=> cust account.
**Ecran** : 344 x 227 DLU (MDI) | [Voir mockup](#ecran-t19)
**Variables liees** : K (v.Customer_ID), P (V pms account from card), V (v.Titre Bt Customer)

---

#### <a id="t23"></a>214.1.3 - Onglet Booking [[ECRAN]](#ecran-t23)

**Role** : Traitement : Onglet Booking.
**Ecran** : 976 x 239 DLU (Modal) | [Voir mockup](#ecran-t23)
**Variables liees** : BN (v.FocusOngletBooking)

---

#### <a id="t25"></a>214.1.3.2 - Booking [[ECRAN]](#ecran-t25)

**Role** : Traitement : Booking.
**Ecran** : 440 x 136 DLU (Type6) | [Voir mockup](#ecran-t25)
**Variables liees** : BN (v.FocusOngletBooking)

---

#### <a id="t26"></a>214.1.3.3 - Screen [[ECRAN]](#ecran-t26)

**Role** : Traitement : Screen.
**Ecran** : 1845 x 250 DLU (Type6) | [Voir mockup](#ecran-t26)

---

#### <a id="t27"></a>214.1.3.4 - GetBookigsInfo

**Role** : Consultation/chargement : GetBookigsInfo.

---

#### <a id="t29"></a>214.1.3.6 - Apparier /t forfait/package

**Role** : Traitement : Apparier /t forfait/package.

---

#### <a id="t33"></a>214.1.3.7.2.1 - Del ligne vide

**Role** : Traitement : Del ligne vide.

---

#### <a id="t34"></a>214.1.4 - Transac not PMS [[ECRAN]](#ecran-t34)

**Role** : Traitement : Transac not PMS.
**Ecran** : 973 x 248 DLU (Modal) | [Voir mockup](#ecran-t34)

---

#### <a id="t35"></a>214.1.4.1 - Get prod id

**Role** : Consultation/chargement : Get prod id.
**Variables liees** : BF (v.Valid_Product_All)

---

#### <a id="t36"></a>214.1.4.2 - Get Cat & Subcat

**Role** : Consultation/chargement : Get Cat & Subcat.

---

#### <a id="t37"></a>214.1.5 - Sales and Payment [[ECRAN]](#ecran-t37)

**Role** : Traitement : Sales and Payment.
**Ecran** : 976 x 239 DLU (Modal) | [Voir mockup](#ecran-t37)
**Variables liees** : Z (v.All.Payment ?)

---

#### <a id="t38"></a>214.1.5.1 - Payment [[ECRAN]](#ecran-t38)

**Role** : Traitement : Payment.
**Ecran** : 238 x 63 DLU (MDI) | [Voir mockup](#ecran-t38)
**Variables liees** : Z (v.All.Payment ?)

---

#### <a id="t40"></a>214.1.5.1.2 - View

**Role** : Traitement : View.

---

#### <a id="t42"></a>214.1.5.2 - Discount [[ECRAN]](#ecran-t42)

**Role** : Traitement : Discount.
**Ecran** : 220 x 94 DLU (MDI) | [Voir mockup](#ecran-t42)
**Variables liees** : BA (v.L.Test Discount ?)

---

#### <a id="t44"></a>214.1.5.3 - Test Prepaid

**Role** : Verification : Test Prepaid.
**Variables liees** : BA (v.L.Test Discount ?)

---

#### <a id="t45"></a>214.1.5.4 - Special actions [[ECRAN]](#ecran-t45)

**Role** : Traitement : Special actions.
**Ecran** : 312 x 259 DLU (Type6) | [Voir mockup](#ecran-t45)

---

#### <a id="t46"></a>214.1.5.4.1 - Cancel other Packages [[ECRAN]](#ecran-t46)

**Role** : Traitement : Cancel other Packages.
**Ecran** : 312 x 259 DLU (Type6) | [Voir mockup](#ecran-t46)

---

#### <a id="t47"></a>214.1.5.4.1.1 - UpdateCustRentals

**Role** : Traitement : UpdateCustRentals.

---

#### <a id="t49"></a>214.1.5.4.3 - End of rental [[ECRAN]](#ecran-t49)

**Role** : Traitement : End of rental.
**Ecran** : 384 x 305 DLU (Type6) | [Voir mockup](#ecran-t49)

---

#### <a id="t50"></a>214.1.5.4.4 - UpdateCustRentals

**Role** : Traitement : UpdateCustRentals.

---

#### <a id="t51"></a>214.1.5.5 - Check Rentals

**Role** : Traitement : Check Rentals.

---

#### <a id="t52"></a>214.1.5.6 - Check Payments [[ECRAN]](#ecran-t52)

**Role** : Traitement : Check Payments.
**Ecran** : 926 x 449 DLU (MDI) | [Voir mockup](#ecran-t52)

---

#### <a id="t53"></a>214.1.5.7 - Check Comment Refus. To Sell [[ECRAN]](#ecran-t53)

**Role** : Traitement : Check Comment Refus. To Sell.
**Ecran** : 522 x 498 DLU | [Voir mockup](#ecran-t53)

---

#### <a id="t54"></a>214.1.5.8 - Discount [[ECRAN]](#ecran-t54)

**Role** : Traitement : Discount.
**Ecran** : 854 x 202 DLU (MDI) | [Voir mockup](#ecran-t54)
**Variables liees** : BA (v.L.Test Discount ?)

---

#### <a id="t56"></a>214.1.5.9 - Delete other Packages [[ECRAN]](#ecran-t56)

**Role** : Traitement : Delete other Packages.
**Ecran** : 312 x 259 DLU (Type6) | [Voir mockup](#ecran-t56)

---

#### <a id="t58"></a>214.1.5.11 - SQL Total payement [[ECRAN]](#ecran-t58)

**Role** : Traitement : SQL Total payement.
**Ecran** : 115 x 195 DLU | [Voir mockup](#ecran-t58)

---

#### <a id="t59"></a>214.1.6 - Transac not PMS MBO [[ECRAN]](#ecran-t59)

**Role** : Traitement : Transac not PMS MBO.
**Ecran** : 695 x 143 DLU (MDI) | [Voir mockup](#ecran-t59)

---

#### <a id="t60"></a>214.1.6.1 - SQL Total payement [[ECRAN]](#ecran-t60)

**Role** : Traitement : SQL Total payement.
**Ecran** : 115 x 195 DLU | [Voir mockup](#ecran-t60)

---

#### <a id="t65"></a>214.1.1.2.1.1 - Confirm [[ECRAN]](#ecran-t65)

**Role** : Traitement : Confirm.
**Ecran** : 554 x 157 DLU (MDI) | [Voir mockup](#ecran-t65)

---

#### <a id="t71"></a>214.1.1.2.1.2 - Récupère Libellé Classif

**Role** : Traitement : Récupère Libellé Classif.


### 3.2 Consultation (5 taches)

Ecrans de recherche et consultation.

---

#### <a id="t2"></a>214.1 - Choix Onglet [[ECRAN]](#ecran-t2)

**Role** : Selection par l'operateur : Choix Onglet.
**Ecran** : 987 x 261 DLU (MDI) | [Voir mockup](#ecran-t2)
**Variables liees** : BN (v.FocusOngletBooking)
**Delegue a** : [Choix - Equipements (IDE 342)](PVE-IDE-342.md)

---

#### <a id="t13"></a>214.1.2.2 - Select Appointments [[ECRAN]](#ecran-t13)

**Role** : Traitement : Select Appointments.
**Ecran** : 1464 x 266 DLU (Type6) | [Voir mockup](#ecran-t13)
**Delegue a** : [Choix - Equipements (IDE 342)](PVE-IDE-342.md)

---

#### <a id="t14"></a>214.1.2.2.1 - Select all

**Role** : Traitement : Select all.
**Delegue a** : [Choix - Equipements (IDE 342)](PVE-IDE-342.md)

---

#### <a id="t30"></a>214.1.3.7 - Select Appointments [[ECRAN]](#ecran-t30)

**Role** : Traitement : Select Appointments.
**Ecran** : 1464 x 266 DLU (Type6) | [Voir mockup](#ecran-t30)
**Delegue a** : [Choix - Equipements (IDE 342)](PVE-IDE-342.md)

---

#### <a id="t31"></a>214.1.3.7.1 - Select all

**Role** : Traitement : Select all.
**Delegue a** : [Choix - Equipements (IDE 342)](PVE-IDE-342.md)


### 3.3 Creation (7 taches)

Insertion de nouveaux enregistrements en base.

---

#### <a id="t12"></a>214.1.2.1 - CreateSales

**Role** : Traitement : CreateSales.

---

#### <a id="t20"></a>214.1.2.2.4.1 - Create cust rentals [[ECRAN]](#ecran-t20)

**Role** : Traitement : Create cust rentals.
**Ecran** : 173 x 115 DLU (MDI) | [Voir mockup](#ecran-t20)
**Variables liees** : K (v.Customer_ID), V (v.Titre Bt Customer)

---

#### <a id="t21"></a>214.1.2.2.4.2 - Create Card Type

**Role** : Traitement : Create Card Type.
**Variables liees** : O (V PoS payer id from card), P (V pms account from card), Q (V pms filiation from card)

---

#### <a id="t22"></a>214.1.2.2.4.3 - create cust package [[ECRAN]](#ecran-t22)

**Role** : Traitement : create cust package.
**Ecran** : 123 x 85 DLU (MDI) | [Voir mockup](#ecran-t22)
**Variables liees** : K (v.Customer_ID), V (v.Titre Bt Customer)

---

#### <a id="t28"></a>214.1.3.5 - CreateMail

**Role** : Traitement : CreateMail.

---

#### <a id="t32"></a>214.1.3.7.2 - CreateSales

**Role** : Traitement : CreateSales.

---

#### <a id="t41"></a>214.1.5.1.3 - create cardType

**Role** : Traitement : create cardType.


### 3.4 Initialisation (2 taches)

Reinitialisation d'etats et variables de travail.

---

#### <a id="t24"></a>214.1.3.1 - Raz mem booking

**Role** : Reinitialisation : Raz mem booking.
**Variables liees** : BN (v.FocusOngletBooking)

---

#### <a id="t39"></a>214.1.5.1.1 - init payer

**Role** : Reinitialisation : init payer.
**Variables liees** : O (V PoS payer id from card)


### 3.5 Saisie (3 taches)

L'operateur saisit les donnees de la transaction via 3 ecrans (Saisie comment annulation, Saisie comment annulation, Saisie comment annulation).

---

#### <a id="t43"></a>214.1.5.2.1 - Saisie comment annulation [[ECRAN]](#ecran-t43)

**Role** : Saisie des donnees : Saisie comment annulation.
**Ecran** : 318 x 135 DLU | [Voir mockup](#ecran-t43)
**Delegue a** : [Saisie commentaire (IDE 200)](PVE-IDE-200.md)

---

#### <a id="t48"></a>214.1.5.4.2 - Saisie comment annulation [[ECRAN]](#ecran-t48)

**Role** : Saisie des donnees : Saisie comment annulation.
**Ecran** : 322 x 136 DLU (Type6) | [Voir mockup](#ecran-t48)
**Delegue a** : [Saisie commentaire (IDE 200)](PVE-IDE-200.md)

---

#### <a id="t55"></a>214.1.5.8.1 - Saisie comment annulation [[ECRAN]](#ecran-t55)

**Role** : Saisie des donnees : Saisie comment annulation.
**Ecran** : 318 x 135 DLU | [Voir mockup](#ecran-t55)
**Delegue a** : [Saisie commentaire (IDE 200)](PVE-IDE-200.md)


### 3.6 Validation (2 taches)

Controles de coherence : 2 taches verifient les donnees et conditions.

---

#### <a id="t57"></a>214.1.5.10 - Verif Multi-Payeurs comptes <> [[ECRAN]](#ecran-t57)

**Role** : Verification : Verif Multi-Payeurs comptes <>.
**Ecran** : 123 x 195 DLU | [Voir mockup](#ecran-t57)
**Delegue a** : [ControleBookingId (IDE 165)](PVE-IDE-165.md)

---

#### <a id="t62"></a>214.1.5.12 - verify not already canceled

**Role** : Verification : verify not already canceled.
**Delegue a** : [ControleBookingId (IDE 165)](PVE-IDE-165.md)


### 3.7 Calcul (1 tache)

Calculs metier : montants, stocks, compteurs.

---

#### <a id="t61"></a>214.2 - calcul filiation

**Role** : Calcul : calcul filiation.
**Variables liees** : C (v.Update Tab Filiation), L (v.Filiation_List), Q (V pms filiation from card)
**Delegue a** : [Calcul - binding setting (IDE 95)](PVE-IDE-95.md)


## 5. REGLES METIER

17 regles identifiees:

### Autres (17 regles)

#### <a id="rm-RM-001"></a>[RM-001] Si Date()>[AH] OR Date()<[AG] alors 43 sinon 6)

| Element | Detail |
|---------|--------|
| **Condition** | `Date()>[AH] OR Date()<[AG]` |
| **Si vrai** | 43 |
| **Si faux** | 6) |
| **Expression source** | Expression 2 : `IF(Date()>[AH] OR Date()<[AG],43,6)` |
| **Exemple** | Si Date()>[AH] OR Date()<[AG] â†’ 43. Sinon â†’ 6) |

#### <a id="rm-RM-002"></a>[RM-002] Si Trim(VG33)='WS' alors 'TB' sinon IF(Trim(VG33)='TB','WS',VG33))

| Element | Detail |
|---------|--------|
| **Condition** | `Trim(VG33)='WS'` |
| **Si vrai** | 'TB' |
| **Si faux** | IF(Trim(VG33)='TB','WS',VG33)) |
| **Expression source** | Expression 3 : `IF(Trim(VG33)='WS','TB',IF(Trim(VG33)='TB','WS',VG33))` |
| **Exemple** | Si Trim(VG33)='WS' â†’ 'TB'. Sinon â†’ IF(Trim(VG33)='TB','WS',VG33)) |

#### <a id="rm-RM-003"></a>[RM-003] Si VG41 est FAUX, branche alternative

| Element | Detail |
|---------|--------|
| **Condition** | `NOT VG41` |
| **Si vrai** | 2 |
| **Si faux** | 3) |
| **Expression source** | Expression 8 : `IF(NOT VG41,2,3)` |
| **Exemple** | Si NOT VG41 â†’ 2. Sinon â†’ 3) |

#### <a id="rm-RM-004"></a>[RM-004] Valeur par defaut si v.LequipementID [S] est vide

| Element | Detail |
|---------|--------|
| **Condition** | `v.LequipementID [S]=''` |
| **Si vrai** | 'Sale' |
| **Si faux** | 'Equipment') |
| **Variables** | S (v.LequipementID) |
| **Expression source** | Expression 12 : `IF(v.LequipementID [S]='','Sale','Equipment')` |
| **Exemple** | Si v.LequipementID [S]='' â†’ 'Sale'. Sinon â†’ 'Equipment') |
| **Impact** | [214.1.1 - equipement](#t3) |

#### <a id="rm-RM-005"></a>[RM-005] Si [CE]='V' alors 'VIP' sinon IF([CE]='T','TOP VIP',''))

| Element | Detail |
|---------|--------|
| **Condition** | `[CE]='V'` |
| **Si vrai** | 'VIP' |
| **Si faux** | IF([CE]='T','TOP VIP','')) |
| **Expression source** | Expression 16 : `IF([CE]='V','VIP',IF([CE]='T','TOP VIP',''))` |
| **Exemple** | Si [CE]='V' â†’ 'VIP'. Sinon â†’ IF([CE]='T','TOP VIP','')) |

#### <a id="rm-RM-006"></a>[RM-006] Traitement si Trim(v.Libelle VIP [Y]) est renseigne

| Element | Detail |
|---------|--------|
| **Condition** | `Trim(v.Libelle VIP [Y])<>''` |
| **Si vrai** | Trim(v.Libelle VIP [Y]) |
| **Si faux** | Trim([DO])) |
| **Variables** | Y (v.Libelle VIP) |
| **Expression source** | Expression 17 : `IF(Trim(v.Libelle VIP [Y])<>'',Trim(v.Libelle VIP [Y]),Trim(` |
| **Exemple** | Si Trim(v.Libelle VIP [Y])<>'' â†’ Trim(v.Libelle VIP [Y]). Sinon â†’ Trim([DO])) |

#### <a id="rm-RM-007"></a>[RM-007] Condition toujours vraie (flag actif)

| Element | Detail |
|---------|--------|
| **Condition** | `V Lien Compte Seminaire [BK]='O' OR v.Garantie [T]='O'` |
| **Si vrai** | 'TRUE'LOG |
| **Si faux** | 'FALSE'LOG) |
| **Variables** | T (v.Garantie), BK (V Lien Compte Seminaire) |
| **Expression source** | Expression 18 : `IF(V Lien Compte Seminaire [BK]='O' OR v.Garantie [T]='O','T` |
| **Exemple** | Si V Lien Compte Seminaire [BK]='O' OR v.Garantie [T]='O' â†’ 'TRUE'LOG. Sinon â†’ 'FALSE'LOG) |

#### <a id="rm-RM-008"></a>[RM-008] Si VG87 alors V Lien Compte Seminaire [BK]='O' OR v.Garantie [T]='O' sinon V Lien Compte Seminaire [BK]='O') OR Trim(V.EtatCompte [BS])='TESTPES'

| Element | Detail |
|---------|--------|
| **Condition** | `VG87` |
| **Si vrai** | V Lien Compte Seminaire [BK]='O' OR v.Garantie [T]='O' |
| **Si faux** | V Lien Compte Seminaire [BK]='O') OR Trim(V.EtatCompte [BS])='TESTPES' |
| **Variables** | T (v.Garantie), BK (V Lien Compte Seminaire), BS (V.EtatCompte) |
| **Expression source** | Expression 19 : `IF(VG87,V Lien Compte Seminaire [BK]='O' OR v.Garantie [T]='` |
| **Exemple** | Si VG87 â†’ V Lien Compte Seminaire [BK]='O' OR v.Garantie [T]='O' |
| **Impact** | [214.1.5.3 - Test Prepaid](#t44) |

#### <a id="rm-RM-009"></a>[RM-009] Si VG17<>[AN] OR v.Update Tab Filiation [C] alors Trim (Str ([AM] sinon '3')),v.Tab_Filation1 [A])

| Element | Detail |
|---------|--------|
| **Condition** | `VG17<>[AN] OR v.Update Tab Filiation [C]` |
| **Si vrai** | Trim (Str ([AM] |
| **Si faux** | '3')),v.Tab_Filation1 [A]) |
| **Variables** | A (v.Tab_Filation1), C (v.Update Tab Filiation) |
| **Expression source** | Expression 20 : `IF(VG17<>[AN] OR v.Update Tab Filiation [C],Trim (Str ([AM],` |
| **Exemple** | Si VG17<>[AN] OR v.Update Tab Filiation [C] â†’ Trim (Str ([AM]. Sinon â†’ '3')),v.Tab_Filation1 [A]) |

#### <a id="rm-RM-010"></a>[RM-010] Si NOT(VG18) alors [CD] sinon [CC])

| Element | Detail |
|---------|--------|
| **Condition** | `NOT(VG18)` |
| **Si vrai** | [CD] |
| **Si faux** | [CC]) |
| **Expression source** | Expression 39 : `IF(NOT(VG18),[CD],[CC])` |
| **Exemple** | Si NOT(VG18) â†’ [CD]. Sinon â†’ [CC]) |

#### <a id="rm-RM-011"></a>[RM-011] Condition toujours vraie (flag actif)

| Element | Detail |
|---------|--------|
| **Condition** | `GetParam ('RENTAL')='TRUE'LOG` |
| **Si vrai** | 'Insurance' |
| **Si faux** | '') |
| **Expression source** | Expression 45 : `IF(GetParam ('RENTAL')='TRUE'LOG,'Insurance','')` |
| **Exemple** | Si GetParam ('RENTAL')='TRUE'LOG â†’ 'Insurance'. Sinon â†’ '') |

#### <a id="rm-RM-012"></a>[RM-012] Traitement si [CT],'Booking',IF(Trim(VG59) est renseigne

| Element | Detail |
|---------|--------|
| **Condition** | `[CT]` |
| **Si vrai** | 'Booking' |
| **Si faux** | IF(Trim(VG59)<>'',VG59,'Sale')) |
| **Expression source** | Expression 76 : `IF([CT],'Booking',IF(Trim(VG59)<>'',VG59,'Sale'))` |
| **Exemple** | Si [CT] â†’ 'Booking'. Sinon â†’ IF(Trim(VG59)<>'',VG59,'Sale')) |
| **Impact** | [214.1.3.2 - Booking](#t25) |

#### <a id="rm-RM-013"></a>[RM-013] Valeur par defaut si VG89 est vide

| Element | Detail |
|---------|--------|
| **Condition** | `VG89=''` |
| **Si vrai** | 247.5 |
| **Si faux** | 123.7) |
| **Expression source** | Expression 84 : `IF(VG89='',247.5,123.7)` |
| **Exemple** | Si VG89='' â†’ 247.5. Sinon â†’ 123.7) |

#### <a id="rm-RM-014"></a>[RM-014] Traitement si VG43 est non nul

| Element | Detail |
|---------|--------|
| **Condition** | `VG43<>0` |
| **Si vrai** | 'N11.'&Trim(Str(VG43 |
| **Si faux** | '#'))&'CZ','N13CZ') |
| **Expression source** | Expression 98 : `IF(VG43<>0,'N11.'&Trim(Str(VG43,'#'))&'CZ','N13CZ')` |
| **Exemple** | Si VG43<>0 â†’ 'N11.'&Trim(Str(VG43. Sinon â†’ '#'))&'CZ','N13CZ') |

#### <a id="rm-RM-015"></a>[RM-015] Si Trim(V.EtatCompte [BS])='TESTPES' alors Translate('%club_images%garantie_annulee.bmp') sinon IF(Trim(Btn.ExtraitCompte [BP])='CLUB' AND V.dateSolde [BT]='R',Translate('%club_images%garantie_club.bmp'),Translate('%club_images%garantie.bmp')))

| Element | Detail |
|---------|--------|
| **Condition** | `Trim(V.EtatCompte [BS])='TESTPES'` |
| **Si vrai** | Translate('%club_images%garantie_annulee.bmp') |
| **Si faux** | IF(Trim(Btn.ExtraitCompte [BP])='CLUB' AND V.dateSolde [BT]='R',Translate('%club_images%garantie_club.bmp'),Translate('%club_images%garantie.bmp'))) |
| **Variables** | BS (V.EtatCompte), BT (V.dateSolde), BP (Btn.ExtraitCompte) |
| **Expression source** | Expression 100 : `IF(Trim(V.EtatCompte [BS])='TESTPES',Translate('%club_images` |
| **Exemple** | Si Trim(V.EtatCompte [BS])='TESTPES' â†’ Translate('%club_images%garantie_annulee.bmp') |
| **Impact** | [214.1.5.3 - Test Prepaid](#t44) |

#### <a id="rm-RM-016"></a>[RM-016] Si ExpCalc('106'EXP) alors 'Garantie Annulée : '&Trim([BX]) sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `ExpCalc('106'EXP)` |
| **Si vrai** | 'Garantie Annulée : '&Trim([BX]) |
| **Si faux** | '') |
| **Expression source** | Expression 107 : `IF(ExpCalc('106'EXP),'Garantie Annulée : '&Trim([BX]),'')` |
| **Exemple** | Si ExpCalc('106'EXP) â†’ 'Garantie Annulée : '&Trim([BX]). Sinon â†’ '') |

#### <a id="rm-RM-017"></a>[RM-017] Si VG127 OR VG140 alors v.Deb_Sejour [BG] sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `VG127 OR VG140` |
| **Si vrai** | v.Deb_Sejour [BG] |
| **Si faux** | '') |
| **Variables** | BG (v.Deb_Sejour) |
| **Expression source** | Expression 110 : `IF(VG127 OR VG140,v.Deb_Sejour [BG],'')` |
| **Exemple** | Si VG127 OR VG140 â†’ v.Deb_Sejour [BG]. Sinon â†’ '') |

## 6. CONTEXTE

- **Appele par**: [Menu (IDE 185)](PVE-IDE-185.md)
- **Appelle**: 20 programmes | **Tables**: 40 (W:10 R:11 L:37) | **Taches**: 64 | **Expressions**: 115

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (26 / 64)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 214 | 214 | Main Sale V4 | Modal | 1990 | 392 | Traitement |
| 2 | 214.1 | 214.1 | Choix Onglet | MDI | 987 | 261 | Consultation |
| 3 | 214.1.1 | 214.1.1 | equipement | Modal | 971 | 229 | Traitement |
| 4 | 214.1.1.1 | 214.1.1.1 | Equipment check out | MDI | 320 | 254 | Traitement |
| 5 | 214.1.1.2 | 214.1.1.2 | Equipment list | MDI | 269 | 280 | Traitement |
| 6 | 214.1.1.2.1 | 214.1.1.2.1 | Equipment check out | MDI | 322 | 282 | Traitement |
| 7 | 214.1.1.2.2 | 214.1.1.2.2 | Equipment list | MDI | 190 | 280 | Traitement |
| 8 | 214.1.1.2.2.1 | 214.1.1.2.2.1 | Equipment check IN | Type6 | 642 | 281 | Traitement |
| 9 | 214.1.2 | 214.1.2 | Booking_ID | Modal | 973 | 248 | Traitement |
| 10 | 214.1.2.2 | 214.1.2.2 | Select Appointments | Type6 | 1464 | 266 | Consultation |
| 11 | 214.1.2.2.2 | 214.1.2.2.2 | Packages | MDI | 581 | 366 | Traitement |
| 12 | 214.1.2.2.2.1 | 214.1.2.2.2.1 | Sub cat | Modal | 386 | 324 | Traitement |
| 13 | 214.1.2.2.2.1.1 | 214.1.2.2.2.1.1 | Products | Modal | 182 | 314 | Traitement |
| 14 | 214.1.3 | 214.1.3 | Onglet Booking | Modal | 976 | 239 | Traitement |
| 15 | 214.1.3.2 | 214.1.3.2 | Booking | Type6 | 440 | 136 | Traitement |
| 16 | 214.1.3.3 | 214.1.3.3 | Screen | Type6 | 1845 | 250 | Traitement |
| 17 | 214.1.3.7 | 214.1.3.7 | Select Appointments | Type6 | 1464 | 266 | Consultation |
| 18 | 214.1.4 | 214.1.4 | Transac not PMS | Modal | 973 | 248 | Traitement |
| 19 | 214.1.5 | 214.1.5 | Sales and Payment | Modal | 976 | 239 | Traitement |
| 20 | 214.1.5.2.1 | 214.1.5.2.1 | Saisie comment annulation | Type0 | 318 | 135 | Saisie |
| 21 | 214.1.5.4 | 214.1.5.4 | Special actions | Type6 | 312 | 259 | Traitement |
| 22 | 214.1.5.4.2 | 214.1.5.4.2 | Saisie comment annulation | Type6 | 322 | 136 | Saisie |
| 23 | 214.1.5.4.3 | 214.1.5.4.3 | End of rental | Type6 | 384 | 305 | Traitement |
| 24 | 214.1.5.8.1 | 214.1.5.8.1 | Saisie comment annulation | Type0 | 318 | 135 | Saisie |
| 25 | 214.1.6 | 214.1.6 | Transac not PMS MBO | MDI | 695 | 143 | Traitement |
| 26 | 214.1.1.2.1.2 | 214.1.1.2.1.1 | Confirm | MDI | 554 | 157 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>214 - Main Sale V4
**Tache** : [214](#t1) | **Type** : Modal | **Dimensions** : 1990 x 392 DLU
**Bloc** : Traitement | **Titre IDE** : Main Sale V4

<!-- FORM-DATA:
{
    "width":  1990,
    "vFactor":  8,
    "type":  "Modal",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  2,
                         "type":  "label",
                         "var":  "",
                         "y":  61,
                         "w":  1974,
                         "fmt":  "",
                         "name":  "",
                         "h":  33,
                         "color":  "6",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  315,
                         "type":  "label",
                         "var":  "",
                         "y":  62,
                         "w":  96,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "Gender",
                         "parent":  1
                     },
                     {
                         "x":  411,
                         "type":  "label",
                         "var":  "",
                         "y":  62,
                         "w":  104,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "Type",
                         "parent":  1
                     },
                     {
                         "x":  515,
                         "type":  "label",
                         "var":  "",
                         "y":  62,
                         "w":  106,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "Room #",
                         "parent":  1
                     },
                     {
                         "x":  621,
                         "type":  "label",
                         "var":  "",
                         "y":  62,
                         "w":  72,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "Age",
                         "parent":  1
                     },
                     {
                         "x":  693,
                         "type":  "label",
                         "var":  "",
                         "y":  62,
                         "w":  208,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "Fidelity",
                         "parent":  1
                     },
                     {
                         "x":  901,
                         "type":  "label",
                         "var":  "",
                         "y":  62,
                         "w":  294,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  1195,
                         "type":  "label",
                         "var":  "",
                         "y":  62,
                         "w":  142,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "From",
                         "parent":  1
                     },
                     {
                         "x":  1337,
                         "type":  "label",
                         "var":  "",
                         "y":  62,
                         "w":  142,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "To",
                         "parent":  1
                     },
                     {
                         "x":  1481,
                         "type":  "label",
                         "var":  "",
                         "y":  62,
                         "w":  155,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "Quality / Sem",
                         "parent":  1
                     },
                     {
                         "x":  1636,
                         "type":  "label",
                         "var":  "",
                         "y":  62,
                         "w":  136,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  12,
                         "type":  "label",
                         "var":  "",
                         "y":  63,
                         "w":  110,
                         "fmt":  "",
                         "name":  "",
                         "h":  28,
                         "color":  "6",
                         "text":  "Customer #",
                         "parent":  1
                     },
                     {
                         "x":  315,
                         "type":  "line",
                         "var":  "",
                         "y":  74,
                         "w":  0,
                         "fmt":  "",
                         "name":  "",
                         "h":  20,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  407,
                         "type":  "line",
                         "var":  "",
                         "y":  74,
                         "w":  0,
                         "fmt":  "",
                         "name":  "",
                         "h":  20,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  511,
                         "type":  "line",
                         "var":  "",
                         "y":  74,
                         "w":  0,
                         "fmt":  "",
                         "name":  "",
                         "h":  20,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  617,
                         "type":  "line",
                         "var":  "",
                         "y":  74,
                         "w":  0,
                         "fmt":  "",
                         "name":  "",
                         "h":  20,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  691,
                         "type":  "line",
                         "var":  "",
                         "y":  74,
                         "w":  0,
                         "fmt":  "",
                         "name":  "",
                         "h":  20,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  899,
                         "type":  "line",
                         "var":  "",
                         "y":  74,
                         "w":  0,
                         "fmt":  "",
                         "name":  "",
                         "h":  20,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  1193,
                         "type":  "line",
                         "var":  "",
                         "y":  74,
                         "w":  0,
                         "fmt":  "",
                         "name":  "",
                         "h":  20,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  1335,
                         "type":  "line",
                         "var":  "",
                         "y":  74,
                         "w":  0,
                         "fmt":  "",
                         "name":  "",
                         "h":  20,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  1477,
                         "type":  "line",
                         "var":  "",
                         "y":  74,
                         "w":  0,
                         "fmt":  "",
                         "name":  "",
                         "h":  20,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  1635,
                         "type":  "line",
                         "var":  "",
                         "y":  74,
                         "w":  0,
                         "fmt":  "",
                         "name":  "",
                         "h":  20,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  2,
                         "type":  "button",
                         "var":  "",
                         "y":  1,
                         "w":  1980,
                         "fmt":  "SELLER -",
                         "name":  "SELLER",
                         "h":  28,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  2,
                         "type":  "button",
                         "var":  "",
                         "y":  31,
                         "w":  1980,
                         "fmt":  "CUSTOMER -",
                         "name":  "CUSTOMER",
                         "h":  28,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  140,
                         "type":  "edit",
                         "var":  "",
                         "y":  63,
                         "w":  169,
                         "fmt":  "10P0Z",
                         "name":  "xcust_id",
                         "h":  28,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  1784,
                         "type":  "button",
                         "var":  "",
                         "y":  63,
                         "w":  84,
                         "fmt":  "$",
                         "name":  "$",
                         "h":  29,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  1882,
                         "type":  "button",
                         "var":  "",
                         "y":  63,
                         "w":  84,
                         "fmt":  "F",
                         "name":  "F",
                         "h":  29,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  1483,
                         "type":  "edit",
                         "var":  "",
                         "y":  75,
                         "w":  148,
                         "fmt":  "",
                         "name":  "v.Qualite_0001",
                         "h":  9,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  1640,
                         "type":  "edit",
                         "var":  "",
                         "y":  75,
                         "w":  130,
                         "fmt":  "30",
                         "name":  "v.Insurance",
                         "h":  16,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  999,
                         "type":  "button",
                         "var":  "",
                         "y":  76,
                         "w":  192,
                         "fmt":  "\\Account Statement",
                         "name":  "B.ExtraitCompte",
                         "h":  14,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  357,
                         "type":  "edit",
                         "var":  "",
                         "y":  77,
                         "w":  18,
                         "fmt":  "",
                         "name":  "gm_sexe",
                         "h":  11,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  435,
                         "type":  "edit",
                         "var":  "",
                         "y":  77,
                         "w":  52,
                         "fmt":  "",
                         "name":  "cgm_qualite",
                         "h":  11,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  525,
                         "type":  "edit",
                         "var":  "",
                         "y":  77,
                         "w":  92,
                         "fmt":  "",
                         "name":  "v.RoomNumber",
                         "h":  11,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  629,
                         "type":  "edit",
                         "var":  "",
                         "y":  77,
                         "w":  40,
                         "fmt":  "##Z",
                         "name":  "gm_age",
                         "h":  11,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  701,
                         "type":  "edit",
                         "var":  "",
                         "y":  77,
                         "w":  188,
                         "fmt":  "30",
                         "name":  "",
                         "h":  11,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  906,
                         "type":  "image",
                         "var":  "",
                         "y":  77,
                         "w":  26,
                         "fmt":  "",
                         "name":  "v Image Garantie",
                         "h":  12,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  1199,
                         "type":  "edit",
                         "var":  "",
                         "y":  77,
                         "w":  136,
                         "fmt":  "WWW ##/##/####Z",
                         "name":  "gmr_debut_sejour",
                         "h":  11,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  1339,
                         "type":  "edit",
                         "var":  "",
                         "y":  77,
                         "w":  139,
                         "fmt":  "WWW ##/##/####Z",
                         "name":  "gmr_debut_sejour_0001",
                         "h":  11,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  936,
                         "type":  "image",
                         "var":  "",
                         "y":  78,
                         "w":  26,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  963,
                         "type":  "image",
                         "var":  "",
                         "y":  78,
                         "w":  34,
                         "fmt":  "",
                         "name":  "v Image Garantie",
                         "h":  12,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  1480,
                         "type":  "edit",
                         "var":  "",
                         "y":  84,
                         "w":  154,
                         "fmt":  "20",
                         "name":  "gm_seminaire_0001",
                         "h":  9,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  0,
                         "type":  "button",
                         "var":  "",
                         "y":  96,
                         "w":  1980,
                         "fmt":  "PRODUCT SELECTION",
                         "name":  "NEW SALE",
                         "h":  28,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  990,
                         "type":  "button",
                         "var":  "",
                         "y":  96,
                         "w":  990,
                         "fmt":  "Best Of",
                         "name":  "Best Of",
                         "h":  28,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  2,
                         "type":  "subform",
                         "var":  "",
                         "y":  127,
                         "w":  1980,
                         "fmt":  "",
                         "name":  "SB_List Sales",
                         "h":  264,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "214",
    "height":  392
}
-->

<details>
<summary><strong>Champs : 11 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 140,63 | xcust_id | - | edit |
| 1483,75 | v.Qualite_0001 | - | edit |
| 1640,75 | v.Insurance | - | edit |
| 357,77 | gm_sexe | - | edit |
| 435,77 | cgm_qualite | - | edit |
| 525,77 | v.RoomNumber | - | edit |
| 629,77 | gm_age | - | edit |
| 701,77 | 30 | - | edit |
| 1199,77 | gmr_debut_sejour | - | edit |
| 1339,77 | gmr_debut_sejour_0001 | - | edit |
| 1480,84 | gm_seminaire_0001 | - | edit |

</details>

<details>
<summary><strong>Boutons : 7 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| SELLER - | 2,1 | Bouton fonctionnel |
| CUSTOMER - | 2,31 | Bouton fonctionnel |
| $ | 1784,63 | Bouton fonctionnel |
| F | 1882,63 | Bouton fonctionnel |
| \Account Statement | 999,76 | Bouton fonctionnel |
| PRODUCT SELECTION | 0,96 | Appel [Delete Product (IDE 194)](PVE-IDE-194.md) |
| Best Of | 990,96 | Bouton fonctionnel |

</details>

---

#### <a id="ecran-t2"></a>214.1 - Choix Onglet
**Tache** : [214.1](#t2) | **Type** : MDI | **Dimensions** : 987 x 261 DLU
**Bloc** : Consultation | **Titre IDE** : Choix Onglet

<!-- FORM-DATA:
{
    "width":  987,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  2,
                         "type":  "tab",
                         "var":  "",
                         "y":  1,
                         "w":  985,
                         "fmt":  "",
                         "name":  "Onglet",
                         "h":  258,
                         "color":  "",
                         "text":  "Sale,Equipment,Payments,Scan Equipment,Booking,Booking ID",
                         "parent":  null
                     },
                     {
                         "x":  6,
                         "type":  "subform",
                         "var":  "",
                         "y":  6,
                         "w":  979,
                         "fmt":  "",
                         "name":  "Sales and Payment",
                         "h":  253,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  4,
                         "type":  "subform",
                         "var":  "",
                         "y":  12,
                         "w":  978,
                         "fmt":  "",
                         "name":  "Equipment",
                         "h":  244,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  0,
                         "type":  "subform",
                         "var":  "",
                         "y":  17,
                         "w":  981,
                         "fmt":  "",
                         "name":  "Payment",
                         "h":  238,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  4,
                         "type":  "subform",
                         "var":  "",
                         "y":  18,
                         "w":  977,
                         "fmt":  "",
                         "name":  "Scan",
                         "h":  238,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  2,
                         "type":  "subform",
                         "var":  "",
                         "y":  11,
                         "w":  978,
                         "fmt":  "",
                         "name":  "Booking",
                         "h":  244,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  2,
                         "type":  "subform",
                         "var":  "",
                         "y":  17,
                         "w":  977,
                         "fmt":  "",
                         "name":  "BookingID",
                         "h":  238,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     }
                 ],
    "taskId":  "214.1",
    "height":  261
}
-->

---

#### <a id="ecran-t3"></a>214.1.1 - equipement
**Tache** : [214.1.1](#t3) | **Type** : Modal | **Dimensions** : 971 x 229 DLU
**Bloc** : Traitement | **Titre IDE** : equipement

<!-- FORM-DATA:
{
    "width":  971,
    "vFactor":  8,
    "type":  "Modal",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  4,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  954,
                         "fmt":  "",
                         "name":  "",
                         "h":  18,
                         "color":  "182",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  6,
                         "type":  "label",
                         "var":  "",
                         "y":  164,
                         "w":  805,
                         "fmt":  "",
                         "name":  "",
                         "h":  39,
                         "color":  "182",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  214,
                         "type":  "line",
                         "var":  "",
                         "y":  164,
                         "w":  0,
                         "fmt":  "",
                         "name":  "",
                         "h":  39,
                         "color":  "63",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  540,
                         "type":  "line",
                         "var":  "",
                         "y":  164,
                         "w":  0,
                         "fmt":  "",
                         "name":  "",
                         "h":  39,
                         "color":  "63",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  568,
                         "type":  "label",
                         "var":  "",
                         "y":  167,
                         "w":  46,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "182",
                         "text":  "Comment",
                         "parent":  null
                     },
                     {
                         "x":  219,
                         "type":  "label",
                         "var":  "",
                         "y":  166,
                         "w":  63,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "186",
                         "text":  "Heel piece",
                         "parent":  null
                     },
                     {
                         "x":  14,
                         "type":  "label",
                         "var":  "",
                         "y":  168,
                         "w":  46,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "189",
                         "text":  "Creation",
                         "parent":  null
                     },
                     {
                         "x":  219,
                         "type":  "label",
                         "var":  "",
                         "y":  184,
                         "w":  63,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "186",
                         "text":  "Toe piece",
                         "parent":  null
                     },
                     {
                         "x":  14,
                         "type":  "label",
                         "var":  "",
                         "y":  181,
                         "w":  46,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "189",
                         "text":  "Modification",
                         "parent":  null
                     },
                     {
                         "x":  10,
                         "type":  "label",
                         "var":  "",
                         "y":  7,
                         "w":  48,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "189",
                         "text":  "Package #",
                         "parent":  null
                     },
                     {
                         "x":  78,
                         "type":  "label",
                         "var":  "",
                         "y":  7,
                         "w":  34,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "189",
                         "text":  "Action",
                         "parent":  null
                     },
                     {
                         "x":  141,
                         "type":  "label",
                         "var":  "",
                         "y":  7,
                         "w":  63,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "189",
                         "text":  "Product",
                         "parent":  null
                     },
                     {
                         "x":  257,
                         "type":  "label",
                         "var":  "",
                         "y":  7,
                         "w":  62,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "189",
                         "text":  "Classification",
                         "parent":  null
                     },
                     {
                         "x":  456,
                         "type":  "label",
                         "var":  "",
                         "y":  7,
                         "w":  34,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "189",
                         "text":  "CODE",
                         "parent":  null
                     },
                     {
                         "x":  524,
                         "type":  "label",
                         "var":  "",
                         "y":  7,
                         "w":  26,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "189",
                         "text":  "Days",
                         "parent":  null
                     },
                     {
                         "x":  577,
                         "type":  "label",
                         "var":  "",
                         "y":  5,
                         "w":  52,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "189",
                         "text":  "Due",
                         "parent":  null
                     },
                     {
                         "x":  659,
                         "type":  "label",
                         "var":  "",
                         "y":  6,
                         "w":  50,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "189",
                         "text":  "Out",
                         "parent":  null
                     },
                     {
                         "x":  747,
                         "type":  "label",
                         "var":  "",
                         "y":  6,
                         "w":  50,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "189",
                         "text":  "Check-in",
                         "parent":  null
                     },
                     {
                         "x":  836,
                         "type":  "label",
                         "var":  "",
                         "y":  6,
                         "w":  64,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "189",
                         "text":  "Rental Status",
                         "parent":  null
                     },
                     {
                         "x":  2,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "110",
                         "w":  917,
                         "y":  17,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  25,
                         "h":  146,
                         "cols":  [
                                      {
                                          "title":  "",
                                          "layer":  1,
                                          "w":  64
                                      },
                                      {
                                          "title":  "",
                                          "layer":  2,
                                          "w":  64
                                      },
                                      {
                                          "title":  "",
                                          "layer":  3,
                                          "w":  112
                                      },
                                      {
                                          "title":  "",
                                          "layer":  4,
                                          "w":  320
                                      },
                                      {
                                          "title":  "",
                                          "layer":  5,
                                          "w":  76
                                      },
                                      {
                                          "title":  "",
                                          "layer":  6,
                                          "w":  260
                                      }
                                  ],
                         "rows":  6
                     },
                     {
                         "x":  6,
                         "type":  "edit",
                         "var":  "",
                         "y":  30,
                         "w":  56,
                         "fmt":  "",
                         "name":  "xcust_id",
                         "h":  9,
                         "color":  "110",
                         "text":  "",
                         "parent":  30
                     },
                     {
                         "x":  6,
                         "type":  "edit",
                         "var":  "",
                         "y":  19,
                         "w":  58,
                         "fmt":  "",
                         "name":  "package_id",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  30
                     },
                     {
                         "x":  568,
                         "type":  "edit",
                         "var":  "",
                         "y":  20,
                         "w":  69,
                         "fmt":  "##/##/####",
                         "name":  "date__end_",
                         "h":  19,
                         "color":  "110",
                         "text":  "",
                         "parent":  30
                     },
                     {
                         "x":  568,
                         "type":  "edit",
                         "var":  "",
                         "y":  178,
                         "w":  238,
                         "fmt":  "",
                         "name":  "comment",
                         "h":  22,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  70,
                         "type":  "edit",
                         "var":  "",
                         "y":  20,
                         "w":  58,
                         "fmt":  "",
                         "name":  "action_type",
                         "h":  19,
                         "color":  "110",
                         "text":  "",
                         "parent":  30
                     },
                     {
                         "x":  134,
                         "type":  "edit",
                         "var":  "",
                         "y":  20,
                         "w":  104,
                         "fmt":  "",
                         "name":  "description",
                         "h":  19,
                         "color":  "110",
                         "text":  "",
                         "parent":  30
                     },
                     {
                         "x":  250,
                         "type":  "edit",
                         "var":  "",
                         "y":  20,
                         "w":  183,
                         "fmt":  "",
                         "name":  "description_0001",
                         "h":  19,
                         "color":  "110",
                         "text":  "",
                         "parent":  30
                     },
                     {
                         "x":  518,
                         "type":  "edit",
                         "var":  "",
                         "y":  20,
                         "w":  37,
                         "fmt":  "N3.1",
                         "name":  "#_rental_days_requested",
                         "h":  19,
                         "color":  "110",
                         "text":  "",
                         "parent":  30
                     },
                     {
                         "x":  437,
                         "type":  "button",
                         "var":  "",
                         "y":  19,
                         "w":  76,
                         "fmt":  "",
                         "name":  "SERIAL",
                         "h":  23,
                         "color":  "1",
                         "text":  "",
                         "parent":  30
                     },
                     {
                         "x":  288,
                         "type":  "edit",
                         "var":  "",
                         "y":  184,
                         "w":  26,
                         "fmt":  "",
                         "name":  "toe_piece",
                         "h":  12,
                         "color":  "186",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  288,
                         "type":  "edit",
                         "var":  "",
                         "y":  166,
                         "w":  26,
                         "fmt":  "",
                         "name":  "heel_piece",
                         "h":  12,
                         "color":  "186",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  351,
                         "type":  "edit",
                         "var":  "",
                         "y":  174,
                         "w":  26,
                         "fmt":  "",
                         "name":  "v.binding setting",
                         "h":  14,
                         "color":  "186",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  644,
                         "type":  "edit",
                         "var":  "",
                         "y":  20,
                         "w":  69,
                         "fmt":  "##/##/####",
                         "name":  "date_out",
                         "h":  19,
                         "color":  "110",
                         "text":  "",
                         "parent":  30
                     },
                     {
                         "x":  836,
                         "type":  "edit",
                         "var":  "",
                         "y":  20,
                         "w":  64,
                         "fmt":  "",
                         "name":  "status",
                         "h":  19,
                         "color":  "110",
                         "text":  "",
                         "parent":  30
                     },
                     {
                         "x":  63,
                         "type":  "edit",
                         "var":  "",
                         "y":  168,
                         "w":  48,
                         "fmt":  "",
                         "name":  "date_create",
                         "h":  8,
                         "color":  "189",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  115,
                         "type":  "edit",
                         "var":  "",
                         "y":  168,
                         "w":  31,
                         "fmt":  "",
                         "name":  "time_create",
                         "h":  8,
                         "color":  "189",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  151,
                         "type":  "edit",
                         "var":  "",
                         "y":  168,
                         "w":  53,
                         "fmt":  "",
                         "name":  "user_create",
                         "h":  8,
                         "color":  "189",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  63,
                         "type":  "edit",
                         "var":  "",
                         "y":  181,
                         "w":  48,
                         "fmt":  "",
                         "name":  "date_update",
                         "h":  8,
                         "color":  "189",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  115,
                         "type":  "edit",
                         "var":  "",
                         "y":  181,
                         "w":  31,
                         "fmt":  "",
                         "name":  "time_update",
                         "h":  8,
                         "color":  "189",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  151,
                         "type":  "edit",
                         "var":  "",
                         "y":  181,
                         "w":  53,
                         "fmt":  "",
                         "name":  "user_update",
                         "h":  8,
                         "color":  "189",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  811,
                         "type":  "button",
                         "var":  "",
                         "y":  164,
                         "w":  54,
                         "fmt":  "",
                         "name":  "",
                         "h":  39,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  865,
                         "type":  "button",
                         "var":  "",
                         "y":  164,
                         "w":  91,
                         "fmt":  "Check Out",
                         "name":  "",
                         "h":  39,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  921,
                         "type":  "button",
                         "var":  "",
                         "y":  90,
                         "w":  35,
                         "fmt":  "ò",
                         "name":  "",
                         "h":  75,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  921,
                         "type":  "button",
                         "var":  "",
                         "y":  18,
                         "w":  35,
                         "fmt":  "ñ",
                         "name":  "",
                         "h":  72,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  739,
                         "type":  "button",
                         "var":  "",
                         "y":  19,
                         "w":  76,
                         "fmt":  "10",
                         "name":  "CHECK IN",
                         "h":  23,
                         "color":  "1",
                         "text":  "",
                         "parent":  30
                     }
                 ],
    "taskId":  "214.1.1",
    "height":  229
}
-->

<details>
<summary><strong>Champs : 19 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 6,30 | xcust_id | - | edit |
| 6,19 | package_id | - | edit |
| 568,20 | date__end_ | - | edit |
| 568,178 | comment | - | edit |
| 70,20 | action_type | - | edit |
| 134,20 | description | - | edit |
| 250,20 | description_0001 | - | edit |
| 518,20 | #_rental_days_requested | - | edit |
| 288,184 | toe_piece | - | edit |
| 288,166 | heel_piece | - | edit |
| 351,174 | v.binding setting | - | edit |
| 644,20 | date_out | - | edit |
| 836,20 | status | - | edit |
| 63,168 | date_create | - | edit |
| 115,168 | time_create | - | edit |
| 151,168 | user_create | - | edit |
| 63,181 | date_update | - | edit |
| 115,181 | time_update | - | edit |
| 151,181 | user_update | - | edit |

</details>

<details>
<summary><strong>Boutons : 6 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| SERIAL | 437,19 | Bouton fonctionnel |
| (sans nom) | 811,164 | Action declenchee |
| Check Out | 865,164 | Appel [Menu Check IN / Exchange (IDE 183)](PVE-IDE-183.md) |
| ò | 921,90 | Bouton fonctionnel |
| ñ | 921,18 | Bouton fonctionnel |
| 10 | 739,19 | Bouton fonctionnel |

</details>

---

#### <a id="ecran-t4"></a>214.1.1.1 - Equipment check out
**Tache** : [214.1.1.1](#t4) | **Type** : MDI | **Dimensions** : 320 x 254 DLU
**Bloc** : Traitement | **Titre IDE** : Equipment check out

<!-- FORM-DATA:
{
    "width":  320,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  34,
                         "type":  "label",
                         "var":  "",
                         "y":  87,
                         "w":  81,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "187",
                         "text":  "Equipment :",
                         "parent":  null
                     },
                     {
                         "x":  34,
                         "type":  "label",
                         "var":  "",
                         "y":  102,
                         "w":  81,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "187",
                         "text":  "Classification :",
                         "parent":  null
                     },
                     {
                         "x":  145,
                         "type":  "line",
                         "var":  "",
                         "y":  130,
                         "w":  0,
                         "fmt":  "",
                         "name":  "",
                         "h":  80,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  88,
                         "type":  "label",
                         "var":  "",
                         "y":  133,
                         "w":  50,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "Model",
                         "parent":  null
                     },
                     {
                         "x":  88,
                         "type":  "label",
                         "var":  "",
                         "y":  146,
                         "w":  50,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "Year",
                         "parent":  null
                     },
                     {
                         "x":  88,
                         "type":  "label",
                         "var":  "",
                         "y":  159,
                         "w":  52,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "Manufacturer",
                         "parent":  null
                     },
                     {
                         "x":  72,
                         "type":  "line",
                         "var":  "",
                         "y":  175,
                         "w":  196,
                         "fmt":  "",
                         "name":  "",
                         "h":  0,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  88,
                         "type":  "label",
                         "var":  "",
                         "y":  181,
                         "w":  30,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "Lenght",
                         "parent":  null
                     },
                     {
                         "x":  88,
                         "type":  "label",
                         "var":  "",
                         "y":  195,
                         "w":  42,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "Nickname",
                         "parent":  null
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  319,
                         "fmt":  "",
                         "name":  "",
                         "h":  42,
                         "color":  "182",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  17,
                         "type":  "label",
                         "var":  "",
                         "y":  14,
                         "w":  133,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "186",
                         "text":  "Text",
                         "parent":  18
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  222,
                         "w":  319,
                         "fmt":  "",
                         "name":  "",
                         "h":  31,
                         "color":  "6",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  34,
                         "type":  "edit",
                         "var":  "",
                         "y":  52,
                         "w":  129,
                         "fmt":  "U10A",
                         "name":  "v.serial",
                         "h":  22,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  152,
                         "type":  "edit",
                         "var":  "",
                         "y":  146,
                         "w":  30,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  152,
                         "type":  "edit",
                         "var":  "",
                         "y":  181,
                         "w":  24,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  152,
                         "type":  "edit",
                         "var":  "",
                         "y":  195,
                         "w":  63,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  122,
                         "type":  "edit",
                         "var":  "",
                         "y":  87,
                         "w":  175,
                         "fmt":  "30",
                         "name":  "",
                         "h":  10,
                         "color":  "187",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  152,
                         "type":  "edit",
                         "var":  "",
                         "y":  159,
                         "w":  119,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  152,
                         "type":  "edit",
                         "var":  "",
                         "y":  133,
                         "w":  119,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  122,
                         "type":  "edit",
                         "var":  "",
                         "y":  102,
                         "w":  175,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "187",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  240,
                         "type":  "button",
                         "var":  "",
                         "y":  227,
                         "w":  77,
                         "fmt":  "\u0026Ok",
                         "name":  "bt ok",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  270,
                         "type":  "image",
                         "var":  "",
                         "y":  4,
                         "w":  48,
                         "fmt":  "",
                         "name":  "",
                         "h":  37,
                         "color":  "",
                         "text":  "",
                         "parent":  18
                     },
                     {
                         "x":  164,
                         "type":  "button",
                         "var":  "",
                         "y":  52,
                         "w":  31,
                         "fmt":  "",
                         "name":  "CLEAR",
                         "h":  23,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  164,
                         "type":  "button",
                         "var":  "",
                         "y":  227,
                         "w":  77,
                         "fmt":  "\u0026Cancel",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "214.1.1.1",
    "height":  254
}
-->

<details>
<summary><strong>Champs : 8 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 34,52 | v.serial | - | edit |
| 152,146 | (sans nom) | - | edit |
| 152,181 | (sans nom) | - | edit |
| 152,195 | (sans nom) | - | edit |
| 122,87 | 30 | - | edit |
| 152,159 | (sans nom) | - | edit |
| 152,133 | (sans nom) | - | edit |
| 122,102 | (sans nom) | - | edit |

</details>

<details>
<summary><strong>Boutons : 3 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Ok | 240,227 | Valide la saisie et enregistre |
| CLEAR | 164,52 | Bouton fonctionnel |
| Cancel | 164,227 | Annule et retour au menu |

</details>

---

#### <a id="ecran-t7"></a>214.1.1.2 - Equipment list
**Tache** : [214.1.1.2](#t7) | **Type** : MDI | **Dimensions** : 269 x 280 DLU
**Bloc** : Traitement | **Titre IDE** : Equipment list

<!-- FORM-DATA:
{
    "width":  269,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  55,
                         "type":  "label",
                         "var":  "",
                         "y":  49,
                         "w":  77,
                         "fmt":  "",
                         "name":  "",
                         "h":  20,
                         "color":  "185",
                         "text":  "OUT",
                         "parent":  null
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  269,
                         "fmt":  "",
                         "name":  "",
                         "h":  42,
                         "color":  "182",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  50,
                         "type":  "label",
                         "var":  "",
                         "y":  14,
                         "w":  169,
                         "fmt":  "",
                         "name":  "",
                         "h":  11,
                         "color":  "186",
                         "text":  "Equipment to be checked Out",
                         "parent":  2
                     },
                     {
                         "x":  10,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "110",
                         "w":  249,
                         "y":  76,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  28,
                         "h":  172,
                         "cols":  [
                                      {
                                          "title":  "",
                                          "layer":  1,
                                          "w":  226
                                      },
                                      {
                                          "title":  "",
                                          "layer":  2,
                                          "w":  20
                                      }
                                  ],
                         "rows":  2
                     },
                     {
                         "x":  13,
                         "type":  "edit",
                         "var":  "",
                         "y":  78,
                         "w":  225,
                         "fmt":  "61",
                         "name":  "",
                         "h":  25,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  239,
                         "type":  "edit",
                         "var":  "",
                         "y":  79,
                         "w":  17,
                         "fmt":  "",
                         "name":  "coche",
                         "h":  25,
                         "color":  "145",
                         "text":  "",
                         "parent":  4
                     }
                 ],
    "taskId":  "214.1.1.2",
    "height":  280
}
-->

<details>
<summary><strong>Champs : 2 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 13,78 | 61 | - | edit |
| 239,79 | coche | - | edit |

</details>

---

#### <a id="ecran-t8"></a>214.1.1.2.1 - Equipment check out
**Tache** : [214.1.1.2.1](#t8) | **Type** : MDI | **Dimensions** : 322 x 282 DLU
**Bloc** : Traitement | **Titre IDE** : Equipment check out

<!-- FORM-DATA:
{
    "width":  322,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  34,
                         "type":  "label",
                         "var":  "",
                         "y":  114,
                         "w":  81,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "187",
                         "text":  "Equipment :",
                         "parent":  null
                     },
                     {
                         "x":  34,
                         "type":  "label",
                         "var":  "",
                         "y":  129,
                         "w":  81,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "187",
                         "text":  "Classification :",
                         "parent":  null
                     },
                     {
                         "x":  145,
                         "type":  "line",
                         "var":  "",
                         "y":  157,
                         "w":  0,
                         "fmt":  "",
                         "name":  "",
                         "h":  80,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  88,
                         "type":  "label",
                         "var":  "",
                         "y":  160,
                         "w":  50,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "Model",
                         "parent":  null
                     },
                     {
                         "x":  88,
                         "type":  "label",
                         "var":  "",
                         "y":  173,
                         "w":  50,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "Year",
                         "parent":  null
                     },
                     {
                         "x":  88,
                         "type":  "label",
                         "var":  "",
                         "y":  186,
                         "w":  52,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "Manufacturer",
                         "parent":  null
                     },
                     {
                         "x":  72,
                         "type":  "line",
                         "var":  "",
                         "y":  202,
                         "w":  196,
                         "fmt":  "",
                         "name":  "",
                         "h":  0,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  88,
                         "type":  "label",
                         "var":  "",
                         "y":  208,
                         "w":  30,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "Lenght",
                         "parent":  null
                     },
                     {
                         "x":  88,
                         "type":  "label",
                         "var":  "",
                         "y":  222,
                         "w":  42,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "Nickname",
                         "parent":  null
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  319,
                         "fmt":  "",
                         "name":  "",
                         "h":  42,
                         "color":  "182",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  17,
                         "type":  "label",
                         "var":  "",
                         "y":  14,
                         "w":  242,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "186",
                         "text":  "Scan the equipment to check Out",
                         "parent":  20
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  249,
                         "w":  319,
                         "fmt":  "",
                         "name":  "",
                         "h":  31,
                         "color":  "6",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  34,
                         "type":  "edit",
                         "var":  "",
                         "y":  79,
                         "w":  129,
                         "fmt":  "U10A",
                         "name":  "v.serial",
                         "h":  22,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  152,
                         "type":  "edit",
                         "var":  "",
                         "y":  173,
                         "w":  30,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  152,
                         "type":  "edit",
                         "var":  "",
                         "y":  208,
                         "w":  24,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  152,
                         "type":  "edit",
                         "var":  "",
                         "y":  222,
                         "w":  63,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  121,
                         "type":  "edit",
                         "var":  "",
                         "y":  114,
                         "w":  175,
                         "fmt":  "30",
                         "name":  "",
                         "h":  10,
                         "color":  "187",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  152,
                         "type":  "edit",
                         "var":  "",
                         "y":  186,
                         "w":  119,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  152,
                         "type":  "edit",
                         "var":  "",
                         "y":  160,
                         "w":  119,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  121,
                         "type":  "edit",
                         "var":  "",
                         "y":  129,
                         "w":  175,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "187",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  240,
                         "type":  "button",
                         "var":  "",
                         "y":  254,
                         "w":  77,
                         "fmt":  "\u0026Ok",
                         "name":  "bt ok",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  270,
                         "type":  "image",
                         "var":  "",
                         "y":  4,
                         "w":  48,
                         "fmt":  "",
                         "name":  "",
                         "h":  37,
                         "color":  "",
                         "text":  "",
                         "parent":  22
                     },
                     {
                         "x":  55,
                         "type":  "edit",
                         "var":  "",
                         "y":  42,
                         "w":  214,
                         "fmt":  "",
                         "name":  "",
                         "h":  17,
                         "color":  "185",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  55,
                         "type":  "edit",
                         "var":  "",
                         "y":  60,
                         "w":  214,
                         "fmt":  "",
                         "name":  "",
                         "h":  17,
                         "color":  "185",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  164,
                         "type":  "button",
                         "var":  "",
                         "y":  254,
                         "w":  77,
                         "fmt":  "\u0026Cancel",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "214.1.1.2.1",
    "height":  282
}
-->

<details>
<summary><strong>Champs : 10 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 34,79 | v.serial | - | edit |
| 152,173 | (sans nom) | - | edit |
| 152,208 | (sans nom) | - | edit |
| 152,222 | (sans nom) | - | edit |
| 121,114 | 30 | - | edit |
| 152,186 | (sans nom) | - | edit |
| 152,160 | (sans nom) | - | edit |
| 121,129 | (sans nom) | - | edit |
| 55,42 | (sans nom) | - | edit |
| 55,60 | (sans nom) | - | edit |

</details>

<details>
<summary><strong>Boutons : 2 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Ok | 240,254 | Valide la saisie et enregistre |
| Cancel | 164,254 | Annule et retour au menu |

</details>

---

#### <a id="ecran-t9"></a>214.1.1.2.2 - Equipment list
**Tache** : [214.1.1.2.2](#t9) | **Type** : MDI | **Dimensions** : 190 x 280 DLU
**Bloc** : Traitement | **Titre IDE** : Equipment list

<!-- FORM-DATA:
{
    "width":  190,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  55,
                         "type":  "label",
                         "var":  "",
                         "y":  48,
                         "w":  77,
                         "fmt":  "",
                         "name":  "",
                         "h":  20,
                         "color":  "184",
                         "text":  "IN",
                         "parent":  null
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  186,
                         "fmt":  "",
                         "name":  "",
                         "h":  42,
                         "color":  "182",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  10,
                         "type":  "label",
                         "var":  "",
                         "y":  14,
                         "w":  164,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "186",
                         "text":  "Equipments to check In first",
                         "parent":  2
                     },
                     {
                         "x":  10,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "110",
                         "w":  170,
                         "y":  75,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  28,
                         "h":  172,
                         "cols":  [
                                      {
                                          "title":  "",
                                          "layer":  1,
                                          "w":  152
                                      },
                                      {
                                          "title":  "",
                                          "layer":  2,
                                          "w":  15
                                      }
                                  ],
                         "rows":  2
                     },
                     {
                         "x":  13,
                         "type":  "edit",
                         "var":  "",
                         "y":  77,
                         "w":  151,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  13,
                         "type":  "edit",
                         "var":  "",
                         "y":  91,
                         "w":  147,
                         "fmt":  "U15",
                         "name":  "",
                         "h":  11,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  165,
                         "type":  "edit",
                         "var":  "",
                         "y":  78,
                         "w":  12,
                         "fmt":  "",
                         "name":  "V.coche check in",
                         "h":  25,
                         "color":  "145",
                         "text":  "",
                         "parent":  4
                     }
                 ],
    "taskId":  "214.1.1.2.2",
    "height":  280
}
-->

<details>
<summary><strong>Champs : 3 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 13,77 | (sans nom) | - | edit |
| 13,91 | U15 | - | edit |
| 165,78 | V.coche check in | - | edit |

</details>

---

#### <a id="ecran-t10"></a>214.1.1.2.2.1 - Equipment check IN
**Tache** : [214.1.1.2.2.1](#t10) | **Type** : Type6 | **Dimensions** : 642 x 281 DLU
**Bloc** : Traitement | **Titre IDE** : Equipment check IN

<!-- FORM-DATA:
{
    "width":  642,
    "vFactor":  8,
    "type":  "Type6",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  68,
                         "type":  "label",
                         "var":  "",
                         "y":  114,
                         "w":  162,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "187",
                         "text":  "Equipment :",
                         "parent":  null
                     },
                     {
                         "x":  68,
                         "type":  "label",
                         "var":  "",
                         "y":  129,
                         "w":  162,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "187",
                         "text":  "Classification :",
                         "parent":  null
                     },
                     {
                         "x":  290,
                         "type":  "line",
                         "var":  "",
                         "y":  157,
                         "w":  0,
                         "fmt":  "",
                         "name":  "",
                         "h":  80,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  176,
                         "type":  "label",
                         "var":  "",
                         "y":  160,
                         "w":  100,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "Model",
                         "parent":  null
                     },
                     {
                         "x":  176,
                         "type":  "label",
                         "var":  "",
                         "y":  173,
                         "w":  100,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "Year",
                         "parent":  null
                     },
                     {
                         "x":  176,
                         "type":  "label",
                         "var":  "",
                         "y":  186,
                         "w":  104,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "Manufacturer",
                         "parent":  null
                     },
                     {
                         "x":  144,
                         "type":  "line",
                         "var":  "",
                         "y":  202,
                         "w":  392,
                         "fmt":  "",
                         "name":  "",
                         "h":  0,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  176,
                         "type":  "label",
                         "var":  "",
                         "y":  208,
                         "w":  60,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "Lenght",
                         "parent":  null
                     },
                     {
                         "x":  176,
                         "type":  "label",
                         "var":  "",
                         "y":  222,
                         "w":  84,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "Nickname",
                         "parent":  null
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  638,
                         "fmt":  "",
                         "name":  "",
                         "h":  42,
                         "color":  "182",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  34,
                         "type":  "label",
                         "var":  "",
                         "y":  14,
                         "w":  398,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "186",
                         "text":  "Scan the equipement to Check In",
                         "parent":  21
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  249,
                         "w":  638,
                         "fmt":  "",
                         "name":  "",
                         "h":  31,
                         "color":  "6",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  68,
                         "type":  "edit",
                         "var":  "",
                         "y":  79,
                         "w":  258,
                         "fmt":  "U10A",
                         "name":  "v.serial",
                         "h":  22,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  304,
                         "type":  "edit",
                         "var":  "",
                         "y":  173,
                         "w":  60,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  304,
                         "type":  "edit",
                         "var":  "",
                         "y":  208,
                         "w":  48,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  304,
                         "type":  "edit",
                         "var":  "",
                         "y":  222,
                         "w":  126,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  244,
                         "type":  "edit",
                         "var":  "",
                         "y":  114,
                         "w":  350,
                         "fmt":  "30",
                         "name":  "",
                         "h":  10,
                         "color":  "187",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  304,
                         "type":  "edit",
                         "var":  "",
                         "y":  186,
                         "w":  238,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  304,
                         "type":  "edit",
                         "var":  "",
                         "y":  160,
                         "w":  238,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  242,
                         "type":  "edit",
                         "var":  "",
                         "y":  129,
                         "w":  350,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "187",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  480,
                         "type":  "button",
                         "var":  "",
                         "y":  254,
                         "w":  154,
                         "fmt":  "\u0026Ok",
                         "name":  "bt ok",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  538,
                         "type":  "image",
                         "var":  "",
                         "y":  1,
                         "w":  96,
                         "fmt":  "",
                         "name":  "",
                         "h":  37,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  110,
                         "type":  "edit",
                         "var":  "",
                         "y":  42,
                         "w":  428,
                         "fmt":  "",
                         "name":  "",
                         "h":  17,
                         "color":  "184",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  110,
                         "type":  "edit",
                         "var":  "",
                         "y":  60,
                         "w":  428,
                         "fmt":  "",
                         "name":  "",
                         "h":  17,
                         "color":  "184",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  328,
                         "type":  "button",
                         "var":  "",
                         "y":  254,
                         "w":  154,
                         "fmt":  "\u0026Cancel",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "214.1.1.2.2.1",
    "height":  281
}
-->

<details>
<summary><strong>Champs : 10 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 68,79 | v.serial | - | edit |
| 304,173 | (sans nom) | - | edit |
| 304,208 | (sans nom) | - | edit |
| 304,222 | (sans nom) | - | edit |
| 244,114 | 30 | - | edit |
| 304,186 | (sans nom) | - | edit |
| 304,160 | (sans nom) | - | edit |
| 242,129 | (sans nom) | - | edit |
| 110,42 | (sans nom) | - | edit |
| 110,60 | (sans nom) | - | edit |

</details>

<details>
<summary><strong>Boutons : 2 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Ok | 480,254 | Valide la saisie et enregistre |
| Cancel | 328,254 | Annule et retour au menu |

</details>

---

#### <a id="ecran-t11"></a>214.1.2 - Booking_ID
**Tache** : [214.1.2](#t11) | **Type** : Modal | **Dimensions** : 973 x 248 DLU
**Bloc** : Traitement | **Titre IDE** : Booking_ID

<!-- FORM-DATA:
{
    "width":  973,
    "vFactor":  8,
    "type":  "Modal",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  354,
                         "type":  "label",
                         "var":  "",
                         "y":  76,
                         "w":  265,
                         "fmt":  "",
                         "name":  "",
                         "h":  96,
                         "color":  "186",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  422,
                         "type":  "edit",
                         "var":  "",
                         "y":  112,
                         "w":  129,
                         "fmt":  "18Z",
                         "name":  "BookingID",
                         "h":  24,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  5,
                         "type":  "button",
                         "var":  "",
                         "y":  201,
                         "w":  121,
                         "fmt":  "\u0026Keyboard",
                         "name":  "KEYBORD",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  145,
                         "type":  "button",
                         "var":  "",
                         "y":  201,
                         "w":  121,
                         "fmt":  "\u0026Validate",
                         "name":  "VALIDATE",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  286,
                         "type":  "button",
                         "var":  "",
                         "y":  201,
                         "w":  146,
                         "fmt":  "\u0026Appointment List",
                         "name":  "AppointmentList",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "214.1.2",
    "height":  248
}
-->

<details>
<summary><strong>Champs : 1 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 422,112 | BookingID | - | edit |

</details>

<details>
<summary><strong>Boutons : 3 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Keyboard | 5,201 | Bouton fonctionnel |
| Validate | 145,201 | Valide la saisie et enregistre |
| Appointment List | 286,201 | Appel [FindAppointments (IDE 176)](PVE-IDE-176.md) |

</details>

---

#### <a id="ecran-t13"></a>214.1.2.2 - Select Appointments
**Tache** : [214.1.2.2](#t13) | **Type** : Type6 | **Dimensions** : 1464 x 266 DLU
**Bloc** : Consultation | **Titre IDE** : Select Appointments

<!-- FORM-DATA:
{
    "width":  1464,
    "vFactor":  8,
    "type":  "Type6",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  10,
                         "type":  "label",
                         "var":  "",
                         "y":  2,
                         "w":  1445,
                         "fmt":  "",
                         "name":  "",
                         "h":  42,
                         "color":  "182",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  18,
                         "type":  "label",
                         "var":  "",
                         "y":  15,
                         "w":  389,
                         "fmt":  "",
                         "name":  "",
                         "h":  14,
                         "color":  "186",
                         "text":  "BOOKING ITEMS",
                         "parent":  1
                     },
                     {
                         "x":  10,
                         "type":  "label",
                         "var":  "",
                         "y":  47,
                         "w":  1445,
                         "fmt":  "",
                         "name":  "",
                         "h":  26,
                         "color":  "183",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  42,
                         "type":  "label",
                         "var":  "",
                         "y":  55,
                         "w":  58,
                         "fmt":  "",
                         "name":  "",
                         "h":  13,
                         "color":  "183",
                         "text":  "From",
                         "parent":  4
                     },
                     {
                         "x":  283,
                         "type":  "label",
                         "var":  "",
                         "y":  55,
                         "w":  34,
                         "fmt":  "",
                         "name":  "",
                         "h":  13,
                         "color":  "183",
                         "text":  "To",
                         "parent":  4
                     },
                     {
                         "x":  9,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "6",
                         "w":  1358,
                         "y":  76,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  22,
                         "h":  156,
                         "cols":  [
                                      {
                                          "title":  "Select",
                                          "layer":  1,
                                          "w":  78
                                      },
                                      {
                                          "title":  "Created on",
                                          "layer":  2,
                                          "w":  188
                                      },
                                      {
                                          "title":  "Customer Name",
                                          "layer":  3,
                                          "w":  321
                                      },
                                      {
                                          "title":  "Service Name",
                                          "layer":  4,
                                          "w":  357
                                      },
                                      {
                                          "title":  "Appointment On",
                                          "layer":  5,
                                          "w":  185
                                      },
                                      {
                                          "title":  "Booking ID",
                                          "layer":  6,
                                          "w":  223
                                      }
                                  ],
                         "rows":  6
                     },
                     {
                         "x":  1355,
                         "type":  "image",
                         "var":  "",
                         "y":  6,
                         "w":  96,
                         "fmt":  "",
                         "name":  "",
                         "h":  37,
                         "color":  "",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  1332,
                         "type":  "button",
                         "var":  "",
                         "y":  54,
                         "w":  118,
                         "fmt":  "Refresh",
                         "name":  "Btn.Refresh",
                         "h":  14,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  111,
                         "type":  "edit",
                         "var":  "",
                         "y":  55,
                         "w":  122,
                         "fmt":  "",
                         "name":  "v.DateDebut",
                         "h":  11,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  327,
                         "type":  "edit",
                         "var":  "",
                         "y":  55,
                         "w":  122,
                         "fmt":  "",
                         "name":  "v.DateFin",
                         "h":  11,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  26,
                         "type":  "checkbox",
                         "var":  "",
                         "y":  92,
                         "w":  42,
                         "fmt":  "",
                         "name":  "Checked",
                         "h":  16,
                         "color":  "",
                         "text":  "o",
                         "parent":  10
                     },
                     {
                         "x":  93,
                         "type":  "edit",
                         "var":  "",
                         "y":  91,
                         "w":  107,
                         "fmt":  "##/##/####Z",
                         "name":  "CreatedDate",
                         "h":  17,
                         "color":  "6",
                         "text":  "",
                         "parent":  10
                     },
                     {
                         "x":  208,
                         "type":  "edit",
                         "var":  "",
                         "y":  91,
                         "w":  59,
                         "fmt":  "HH:MMZ",
                         "name":  "CreatedTime",
                         "h":  17,
                         "color":  "6",
                         "text":  "",
                         "parent":  10
                     },
                     {
                         "x":  281,
                         "type":  "edit",
                         "var":  "",
                         "y":  92,
                         "w":  305,
                         "fmt":  "",
                         "name":  "description",
                         "h":  17,
                         "color":  "6",
                         "text":  "",
                         "parent":  10
                     },
                     {
                         "x":  602,
                         "type":  "edit",
                         "var":  "",
                         "y":  92,
                         "w":  342,
                         "fmt":  "",
                         "name":  "PraticienFullName",
                         "h":  17,
                         "color":  "6",
                         "text":  "",
                         "parent":  10
                     },
                     {
                         "x":  959,
                         "type":  "edit",
                         "var":  "",
                         "y":  92,
                         "w":  107,
                         "fmt":  "##/##/####Z",
                         "name":  "DateDebut",
                         "h":  17,
                         "color":  "6",
                         "text":  "",
                         "parent":  10
                     },
                     {
                         "x":  1074,
                         "type":  "edit",
                         "var":  "",
                         "y":  92,
                         "w":  59,
                         "fmt":  "HH:MMZ",
                         "name":  "Heure",
                         "h":  17,
                         "color":  "6",
                         "text":  "",
                         "parent":  10
                     },
                     {
                         "x":  1144,
                         "type":  "edit",
                         "var":  "",
                         "y":  91,
                         "w":  204,
                         "fmt":  "",
                         "name":  "BookingID",
                         "h":  17,
                         "color":  "6",
                         "text":  "",
                         "parent":  10
                     },
                     {
                         "x":  1369,
                         "type":  "button",
                         "var":  "",
                         "y":  76,
                         "w":  86,
                         "fmt":  "ñ",
                         "name":  "UP",
                         "h":  78,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  1369,
                         "type":  "button",
                         "var":  "",
                         "y":  154,
                         "w":  86,
                         "fmt":  "ò",
                         "name":  "DOWN",
                         "h":  78,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  1092,
                         "type":  "button",
                         "var":  "",
                         "y":  235,
                         "w":  172,
                         "fmt":  "\u0026Validate",
                         "name":  "Valider",
                         "h":  27,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  1283,
                         "type":  "button",
                         "var":  "",
                         "y":  235,
                         "w":  172,
                         "fmt":  "\u0026Quit",
                         "name":  "Exit",
                         "h":  27,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "214.1.2.2",
    "height":  266
}
-->

<details>
<summary><strong>Champs : 10 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 111,55 | v.DateDebut | - | edit |
| 327,55 | v.DateFin | - | edit |
| 26,92 | Checked | - | checkbox |
| 93,91 | CreatedDate | - | edit |
| 208,91 | CreatedTime | - | edit |
| 281,92 | description | - | edit |
| 602,92 | PraticienFullName | - | edit |
| 959,92 | DateDebut | - | edit |
| 1074,92 | Heure | - | edit |
| 1144,91 | BookingID | - | edit |

</details>

<details>
<summary><strong>Boutons : 5 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Refresh | 1332,54 | Rafraichit l'affichage |
| ñ | 1369,76 | Bouton fonctionnel |
| ò | 1369,154 | Bouton fonctionnel |
| Validate | 1092,235 | Valide la saisie et enregistre |
| Quit | 1283,235 | Bouton fonctionnel |

</details>

---

#### <a id="ecran-t15"></a>214.1.2.2.2 - Packages
**Tache** : [214.1.2.2.2](#t15) | **Type** : MDI | **Dimensions** : 581 x 366 DLU
**Bloc** : Traitement | **Titre IDE** : Packages

<!-- FORM-DATA:
{
    "width":  581,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  10,
                         "type":  "label",
                         "var":  "",
                         "y":  64,
                         "w":  116,
                         "fmt":  "",
                         "name":  "",
                         "h":  13,
                         "color":  "183",
                         "text":  "Category",
                         "parent":  null
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  562,
                         "fmt":  "",
                         "name":  "",
                         "h":  42,
                         "color":  "186",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  20,
                         "type":  "label",
                         "var":  "",
                         "y":  15,
                         "w":  456,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "186",
                         "text":  "Choose your package",
                         "parent":  2
                     },
                     {
                         "x":  10,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "110",
                         "w":  121,
                         "y":  78,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  25,
                         "h":  258,
                         "cols":  [
                                      {
                                          "title":  "",
                                          "layer":  1,
                                          "w":  117
                                      }
                                  ],
                         "rows":  1
                     },
                     {
                         "x":  114,
                         "type":  "label",
                         "var":  "",
                         "y":  86,
                         "w":  11,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "144",
                         "text":  "ü",
                         "parent":  6
                     },
                     {
                         "x":  16,
                         "type":  "edit",
                         "var":  "",
                         "y":  86,
                         "w":  97,
                         "fmt":  "",
                         "name":  "CTRL_001",
                         "h":  12,
                         "color":  "110",
                         "text":  "",
                         "parent":  6
                     },
                     {
                         "x":  508,
                         "type":  "image",
                         "var":  "",
                         "y":  4,
                         "w":  48,
                         "fmt":  "",
                         "name":  "",
                         "h":  37,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  130,
                         "type":  "button",
                         "var":  "",
                         "y":  79,
                         "w":  44,
                         "fmt":  "ñ",
                         "name":  "",
                         "h":  127,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  130,
                         "type":  "button",
                         "var":  "",
                         "y":  206,
                         "w":  44,
                         "fmt":  "ò",
                         "name":  "",
                         "h":  126,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  174,
                         "type":  "subform",
                         "var":  "",
                         "y":  42,
                         "w":  388,
                         "fmt":  "",
                         "name":  "Sub cat",
                         "h":  311,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "214.1.2.2.2",
    "height":  366
}
-->

<details>
<summary><strong>Champs : 1 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 16,86 | CTRL_001 | - | edit |

</details>

<details>
<summary><strong>Boutons : 2 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| ñ | 130,79 | Bouton fonctionnel |
| ò | 130,206 | Bouton fonctionnel |

</details>

---

#### <a id="ecran-t16"></a>214.1.2.2.2.1 - Sub cat
**Tache** : [214.1.2.2.2.1](#t16) | **Type** : Modal | **Dimensions** : 386 x 324 DLU
**Bloc** : Traitement | **Titre IDE** : Sub cat

<!-- FORM-DATA:
{
    "width":  386,
    "vFactor":  8,
    "type":  "Modal",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  2,
                         "type":  "label",
                         "var":  "",
                         "y":  24,
                         "w":  118,
                         "fmt":  "",
                         "name":  "",
                         "h":  13,
                         "color":  "183",
                         "text":  "Sub category",
                         "parent":  null
                     },
                     {
                         "x":  178,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  206,
                         "fmt":  "",
                         "name":  "",
                         "h":  323,
                         "color":  "189",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  2,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "110",
                         "w":  121,
                         "y":  37,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  25,
                         "h":  252,
                         "cols":  [
                                      {
                                          "title":  "",
                                          "layer":  1,
                                          "w":  117
                                      }
                                  ],
                         "rows":  1
                     },
                     {
                         "x":  105,
                         "type":  "label",
                         "var":  "",
                         "y":  45,
                         "w":  11,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "144",
                         "text":  "ü",
                         "parent":  4
                     },
                     {
                         "x":  5,
                         "type":  "edit",
                         "var":  "",
                         "y":  45,
                         "w":  98,
                         "fmt":  "",
                         "name":  "CTRL_001",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  121,
                         "type":  "button",
                         "var":  "",
                         "y":  38,
                         "w":  44,
                         "fmt":  "ñ",
                         "name":  "",
                         "h":  126,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  121,
                         "type":  "button",
                         "var":  "",
                         "y":  164,
                         "w":  44,
                         "fmt":  "ò",
                         "name":  "",
                         "h":  127,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  180,
                         "type":  "subform",
                         "var":  "",
                         "y":  5,
                         "w":  200,
                         "fmt":  "",
                         "name":  "Products",
                         "h":  316,
                         "color":  "",
                         "text":  "",
                         "parent":  2
                     }
                 ],
    "taskId":  "214.1.2.2.2.1",
    "height":  324
}
-->

<details>
<summary><strong>Champs : 1 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 5,45 | CTRL_001 | - | edit |

</details>

<details>
<summary><strong>Boutons : 2 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| ñ | 121,38 | Bouton fonctionnel |
| ò | 121,164 | Bouton fonctionnel |

</details>

---

#### <a id="ecran-t17"></a>214.1.2.2.2.1.1 - Products
**Tache** : [214.1.2.2.2.1.1](#t17) | **Type** : Modal | **Dimensions** : 182 x 314 DLU
**Bloc** : Traitement | **Titre IDE** : Products

<!-- FORM-DATA:
{
    "width":  182,
    "vFactor":  8,
    "type":  "Modal",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  20,
                         "w":  131,
                         "fmt":  "",
                         "name":  "",
                         "h":  13,
                         "color":  "181",
                         "text":  "Pricing",
                         "parent":  null
                     },
                     {
                         "x":  1,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "110",
                         "w":  134,
                         "y":  35,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  25,
                         "h":  252,
                         "cols":  [
                                      {
                                          "title":  "",
                                          "layer":  1,
                                          "w":  129
                                      }
                                  ],
                         "rows":  1
                     },
                     {
                         "x":  118,
                         "type":  "label",
                         "var":  "",
                         "y":  42,
                         "w":  10,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "208",
                         "text":  "ü",
                         "parent":  3
                     },
                     {
                         "x":  3,
                         "type":  "edit",
                         "var":  "",
                         "y":  42,
                         "w":  69,
                         "fmt":  "",
                         "name":  "CTRL_001",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  75,
                         "type":  "edit",
                         "var":  "",
                         "y":  42,
                         "w":  41,
                         "fmt":  "N12.3C",
                         "name":  "CTRL_002",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  133,
                         "type":  "button",
                         "var":  "",
                         "y":  15,
                         "w":  44,
                         "fmt":  "1/2",
                         "name":  "",
                         "h":  23,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  132,
                         "type":  "button",
                         "var":  "",
                         "y":  37,
                         "w":  44,
                         "fmt":  "ñ",
                         "name":  "",
                         "h":  127,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  132,
                         "type":  "button",
                         "var":  "",
                         "y":  164,
                         "w":  44,
                         "fmt":  "ò",
                         "name":  "",
                         "h":  125,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  3,
                         "type":  "button",
                         "var":  "",
                         "y":  289,
                         "w":  173,
                         "fmt":  "Select",
                         "name":  "(bt) Select",
                         "h":  23,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "214.1.2.2.2.1.1",
    "height":  314
}
-->

<details>
<summary><strong>Champs : 2 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 3,42 | CTRL_001 | - | edit |
| 75,42 | CTRL_002 | - | edit |

</details>

<details>
<summary><strong>Boutons : 4 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| 1/2 | 133,15 | Bouton fonctionnel |
| ñ | 132,37 | Bouton fonctionnel |
| ò | 132,164 | Bouton fonctionnel |
| Select | 3,289 | Appel [Print Equipment SELECT (IDE 96)](PVE-IDE-96.md) |

</details>

---

#### <a id="ecran-t23"></a>214.1.3 - Onglet Booking
**Tache** : [214.1.3](#t23) | **Type** : Modal | **Dimensions** : 976 x 239 DLU
**Bloc** : Traitement | **Titre IDE** : Onglet Booking

<!-- FORM-DATA:
{
    "width":  976,
    "vFactor":  8,
    "type":  "Modal",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  2,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "6",
                         "w":  928,
                         "y":  0,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  24,
                         "h":  152,
                         "cols":  [
                                      {
                                          "title":  "Package #",
                                          "layer":  1,
                                          "w":  64
                                      },
                                      {
                                          "title":  "Description",
                                          "layer":  2,
                                          "w":  210
                                      },
                                      {
                                          "title":  "Booking ID",
                                          "layer":  3,
                                          "w":  156
                                      },
                                      {
                                          "title":  "Status",
                                          "layer":  4,
                                          "w":  143
                                      },
                                      {
                                          "title":  "Print selection",
                                          "layer":  5,
                                          "w":  107
                                      }
                                  ],
                         "rows":  5
                     },
                     {
                         "x":  5,
                         "type":  "edit",
                         "var":  "",
                         "y":  18,
                         "w":  53,
                         "fmt":  "10Z",
                         "name":  "package_id_out",
                         "h":  17,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  72,
                         "type":  "edit",
                         "var":  "",
                         "y":  18,
                         "w":  201,
                         "fmt":  "50",
                         "name":  "description",
                         "h":  17,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  280,
                         "type":  "button",
                         "var":  "",
                         "y":  17,
                         "w":  146,
                         "fmt":  "30",
                         "name":  "booking_ID",
                         "h":  17,
                         "color":  "1",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  439,
                         "type":  "button",
                         "var":  "",
                         "y":  17,
                         "w":  130,
                         "fmt":  "30",
                         "name":  "Status_Booking",
                         "h":  17,
                         "color":  "1",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  604,
                         "type":  "checkbox",
                         "var":  "",
                         "y":  17,
                         "w":  20,
                         "fmt":  "",
                         "name":  "Checked",
                         "h":  16,
                         "color":  "",
                         "text":  "o",
                         "parent":  1
                     },
                     {
                         "x":  931,
                         "type":  "button",
                         "var":  "",
                         "y":  0,
                         "w":  41,
                         "fmt":  "ñ",
                         "name":  "UP",
                         "h":  76,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  931,
                         "type":  "button",
                         "var":  "",
                         "y":  77,
                         "w":  41,
                         "fmt":  "ò",
                         "name":  "DOWN",
                         "h":  76,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  495,
                         "type":  "button",
                         "var":  "",
                         "y":  154,
                         "w":  140,
                         "fmt":  "\u0026Screen",
                         "name":  "Screen",
                         "h":  27,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  642,
                         "type":  "button",
                         "var":  "",
                         "y":  154,
                         "w":  140,
                         "fmt":  "\u0026Email",
                         "name":  "Email",
                         "h":  27,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  790,
                         "type":  "button",
                         "var":  "",
                         "y":  154,
                         "w":  140,
                         "fmt":  "\u0026Print",
                         "name":  "Print",
                         "h":  27,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "214.1.3",
    "height":  239
}
-->

<details>
<summary><strong>Champs : 3 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 5,18 | package_id_out | - | edit |
| 72,18 | description | - | edit |
| 604,17 | Checked | - | checkbox |

</details>

<details>
<summary><strong>Boutons : 7 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| 30 | 280,17 | Bouton fonctionnel |
| 30 | 439,17 | Bouton fonctionnel |
| ñ | 931,0 | Bouton fonctionnel |
| ò | 931,77 | Bouton fonctionnel |
| Screen | 495,154 | Bouton fonctionnel |
| Email | 642,154 | Bouton fonctionnel |
| Print | 790,154 | Appel [Print Equipment SELECT (IDE 96)](PVE-IDE-96.md) |

</details>

---

#### <a id="ecran-t25"></a>214.1.3.2 - Booking
**Tache** : [214.1.3.2](#t25) | **Type** : Type6 | **Dimensions** : 440 x 136 DLU
**Bloc** : Traitement | **Titre IDE** : Booking

<!-- FORM-DATA:
{
    "width":  440,
    "vFactor":  8,
    "type":  "Type6",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  4,
                         "type":  "label",
                         "var":  "",
                         "y":  102,
                         "w":  434,
                         "fmt":  "",
                         "name":  "",
                         "h":  32,
                         "color":  "6",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  4,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  434,
                         "fmt":  "",
                         "name":  "",
                         "h":  42,
                         "color":  "186",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  14,
                         "type":  "label",
                         "var":  "",
                         "y":  10,
                         "w":  235,
                         "fmt":  "",
                         "name":  "",
                         "h":  22,
                         "color":  "186",
                         "text":  "Enter a booking ID",
                         "parent":  3
                     },
                     {
                         "x":  389,
                         "type":  "image",
                         "var":  "",
                         "y":  4,
                         "w":  48,
                         "fmt":  "",
                         "name":  "",
                         "h":  37,
                         "color":  "",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  4,
                         "type":  "edit",
                         "var":  "",
                         "y":  60,
                         "w":  434,
                         "fmt":  "18Z",
                         "name":  "Booking ID",
                         "h":  19,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  5,
                         "type":  "button",
                         "var":  "",
                         "y":  107,
                         "w":  121,
                         "fmt":  "\u0026Keyboard",
                         "name":  "KEYBORD",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  2
                     },
                     {
                         "x":  160,
                         "type":  "button",
                         "var":  "",
                         "y":  107,
                         "w":  121,
                         "fmt":  "\u0026Exit",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  2
                     },
                     {
                         "x":  316,
                         "type":  "button",
                         "var":  "",
                         "y":  107,
                         "w":  121,
                         "fmt":  "\u0026OK",
                         "name":  "OK",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  2
                     }
                 ],
    "taskId":  "214.1.3.2",
    "height":  136
}
-->

<details>
<summary><strong>Champs : 1 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 4,60 | Booking ID | - | edit |

</details>

<details>
<summary><strong>Boutons : 3 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Keyboard | 5,107 | Bouton fonctionnel |
| Exit | 160,107 | Quitte le programme |
| OK | 316,107 | Valide la saisie et enregistre |

</details>

---

#### <a id="ecran-t26"></a>214.1.3.3 - Screen
**Tache** : [214.1.3.3](#t26) | **Type** : Type6 | **Dimensions** : 1845 x 250 DLU
**Bloc** : Traitement | **Titre IDE** : Screen

<!-- FORM-DATA:
{
    "width":  1845,
    "vFactor":  8,
    "type":  "Type6",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  2,
                         "type":  "label",
                         "var":  "",
                         "y":  2,
                         "w":  1834,
                         "fmt":  "",
                         "name":  "",
                         "h":  42,
                         "color":  "182",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  11,
                         "type":  "label",
                         "var":  "",
                         "y":  15,
                         "w":  524,
                         "fmt":  "",
                         "name":  "",
                         "h":  14,
                         "color":  "186",
                         "text":  "BOOKING ITEMS",
                         "parent":  1
                     },
                     {
                         "x":  1,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "6",
                         "w":  1834,
                         "y":  46,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  24,
                         "h":  168,
                         "cols":  [
                                      {
                                          "title":  "Package #",
                                          "layer":  1,
                                          "w":  148
                                      },
                                      {
                                          "title":  "Description",
                                          "layer":  2,
                                          "w":  449
                                      },
                                      {
                                          "title":  "Start date",
                                          "layer":  3,
                                          "w":  140
                                      },
                                      {
                                          "title":  "Start time",
                                          "layer":  4,
                                          "w":  117
                                      },
                                      {
                                          "title":  "End date",
                                          "layer":  5,
                                          "w":  134
                                      },
                                      {
                                          "title":  "End time",
                                          "layer":  6,
                                          "w":  105
                                      },
                                      {
                                          "title":  "Employee",
                                          "layer":  7,
                                          "w":  357
                                      },
                                      {
                                          "title":  "Room",
                                          "layer":  8,
                                          "w":  375
                                      }
                                  ],
                         "rows":  8
                     },
                     {
                         "x":  1740,
                         "type":  "image",
                         "var":  "",
                         "y":  6,
                         "w":  96,
                         "fmt":  "",
                         "name":  "",
                         "h":  37,
                         "color":  "",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  8,
                         "type":  "edit",
                         "var":  "",
                         "y":  61,
                         "w":  142,
                         "fmt":  "10Z",
                         "name":  "package_id_out",
                         "h":  17,
                         "color":  "6",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  155,
                         "type":  "edit",
                         "var":  "",
                         "y":  61,
                         "w":  441,
                         "fmt":  "",
                         "name":  "description",
                         "h":  17,
                         "color":  "6",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  604,
                         "type":  "edit",
                         "var":  "",
                         "y":  61,
                         "w":  126,
                         "fmt":  "##/##/####Z",
                         "name":  "Date",
                         "h":  17,
                         "color":  "6",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  745,
                         "type":  "edit",
                         "var":  "",
                         "y":  61,
                         "w":  86,
                         "fmt":  "HH:MMZ",
                         "name":  "Heure",
                         "h":  17,
                         "color":  "6",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  861,
                         "type":  "edit",
                         "var":  "",
                         "y":  61,
                         "w":  122,
                         "fmt":  "##/##/####Z",
                         "name":  "DateFin",
                         "h":  17,
                         "color":  "6",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  996,
                         "type":  "edit",
                         "var":  "",
                         "y":  61,
                         "w":  93,
                         "fmt":  "HH:MMZ",
                         "name":  "HeureFin",
                         "h":  17,
                         "color":  "6",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  1100,
                         "type":  "edit",
                         "var":  "",
                         "y":  61,
                         "w":  342,
                         "fmt":  "",
                         "name":  "PraticienFullName",
                         "h":  17,
                         "color":  "6",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  1457,
                         "type":  "edit",
                         "var":  "",
                         "y":  61,
                         "w":  326,
                         "fmt":  "",
                         "name":  "CabineName",
                         "h":  17,
                         "color":  "6",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  1402,
                         "type":  "button",
                         "var":  "",
                         "y":  219,
                         "w":  140,
                         "fmt":  "\u0026Email",
                         "name":  "Email",
                         "h":  27,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  1550,
                         "type":  "button",
                         "var":  "",
                         "y":  219,
                         "w":  140,
                         "fmt":  "\u0026Print",
                         "name":  "Print",
                         "h":  27,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  1698,
                         "type":  "button",
                         "var":  "",
                         "y":  219,
                         "w":  140,
                         "fmt":  "\u0026Exit",
                         "name":  "Exit",
                         "h":  27,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "214.1.3.3",
    "height":  250
}
-->

<details>
<summary><strong>Champs : 8 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 8,61 | package_id_out | - | edit |
| 155,61 | description | - | edit |
| 604,61 | Date | - | edit |
| 745,61 | Heure | - | edit |
| 861,61 | DateFin | - | edit |
| 996,61 | HeureFin | - | edit |
| 1100,61 | PraticienFullName | - | edit |
| 1457,61 | CabineName | - | edit |

</details>

<details>
<summary><strong>Boutons : 3 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Email | 1402,219 | Bouton fonctionnel |
| Print | 1550,219 | Appel [Print Equipment SELECT (IDE 96)](PVE-IDE-96.md) |
| Exit | 1698,219 | Quitte le programme |

</details>

---

#### <a id="ecran-t30"></a>214.1.3.7 - Select Appointments
**Tache** : [214.1.3.7](#t30) | **Type** : Type6 | **Dimensions** : 1464 x 266 DLU
**Bloc** : Consultation | **Titre IDE** : Select Appointments

<!-- FORM-DATA:
{
    "width":  1464,
    "vFactor":  8,
    "type":  "Type6",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  10,
                         "type":  "label",
                         "var":  "",
                         "y":  2,
                         "w":  1445,
                         "fmt":  "",
                         "name":  "",
                         "h":  42,
                         "color":  "182",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  18,
                         "type":  "label",
                         "var":  "",
                         "y":  15,
                         "w":  389,
                         "fmt":  "",
                         "name":  "",
                         "h":  14,
                         "color":  "186",
                         "text":  "BOOKING ITEMS",
                         "parent":  1
                     },
                     {
                         "x":  10,
                         "type":  "label",
                         "var":  "",
                         "y":  47,
                         "w":  1445,
                         "fmt":  "",
                         "name":  "",
                         "h":  26,
                         "color":  "183",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  42,
                         "type":  "label",
                         "var":  "",
                         "y":  55,
                         "w":  58,
                         "fmt":  "",
                         "name":  "",
                         "h":  13,
                         "color":  "183",
                         "text":  "From",
                         "parent":  4
                     },
                     {
                         "x":  283,
                         "type":  "label",
                         "var":  "",
                         "y":  55,
                         "w":  34,
                         "fmt":  "",
                         "name":  "",
                         "h":  13,
                         "color":  "183",
                         "text":  "To",
                         "parent":  4
                     },
                     {
                         "x":  9,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "6",
                         "w":  1358,
                         "y":  76,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  22,
                         "h":  156,
                         "cols":  [
                                      {
                                          "title":  "Select",
                                          "layer":  1,
                                          "w":  78
                                      },
                                      {
                                          "title":  "Created on",
                                          "layer":  2,
                                          "w":  188
                                      },
                                      {
                                          "title":  "Customer Name",
                                          "layer":  3,
                                          "w":  321
                                      },
                                      {
                                          "title":  "Service Name",
                                          "layer":  4,
                                          "w":  357
                                      },
                                      {
                                          "title":  "Appointment On",
                                          "layer":  5,
                                          "w":  185
                                      },
                                      {
                                          "title":  "Booking ID",
                                          "layer":  6,
                                          "w":  223
                                      }
                                  ],
                         "rows":  6
                     },
                     {
                         "x":  1355,
                         "type":  "image",
                         "var":  "",
                         "y":  6,
                         "w":  96,
                         "fmt":  "",
                         "name":  "",
                         "h":  37,
                         "color":  "",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  1332,
                         "type":  "button",
                         "var":  "",
                         "y":  54,
                         "w":  118,
                         "fmt":  "Refresh",
                         "name":  "Btn.Refresh",
                         "h":  14,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  111,
                         "type":  "edit",
                         "var":  "",
                         "y":  55,
                         "w":  122,
                         "fmt":  "",
                         "name":  "v.DateDebut",
                         "h":  11,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  327,
                         "type":  "edit",
                         "var":  "",
                         "y":  55,
                         "w":  122,
                         "fmt":  "",
                         "name":  "v.DateFin",
                         "h":  11,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  26,
                         "type":  "checkbox",
                         "var":  "",
                         "y":  92,
                         "w":  42,
                         "fmt":  "",
                         "name":  "Checked",
                         "h":  16,
                         "color":  "",
                         "text":  "o",
                         "parent":  10
                     },
                     {
                         "x":  93,
                         "type":  "edit",
                         "var":  "",
                         "y":  91,
                         "w":  107,
                         "fmt":  "##/##/####Z",
                         "name":  "CreatedDate",
                         "h":  17,
                         "color":  "6",
                         "text":  "",
                         "parent":  10
                     },
                     {
                         "x":  208,
                         "type":  "edit",
                         "var":  "",
                         "y":  91,
                         "w":  59,
                         "fmt":  "HH:MMZ",
                         "name":  "CreatedTime",
                         "h":  17,
                         "color":  "6",
                         "text":  "",
                         "parent":  10
                     },
                     {
                         "x":  281,
                         "type":  "edit",
                         "var":  "",
                         "y":  92,
                         "w":  305,
                         "fmt":  "",
                         "name":  "description",
                         "h":  17,
                         "color":  "6",
                         "text":  "",
                         "parent":  10
                     },
                     {
                         "x":  602,
                         "type":  "edit",
                         "var":  "",
                         "y":  92,
                         "w":  342,
                         "fmt":  "",
                         "name":  "PraticienFullName",
                         "h":  17,
                         "color":  "6",
                         "text":  "",
                         "parent":  10
                     },
                     {
                         "x":  959,
                         "type":  "edit",
                         "var":  "",
                         "y":  92,
                         "w":  107,
                         "fmt":  "##/##/####Z",
                         "name":  "DateDebut",
                         "h":  17,
                         "color":  "6",
                         "text":  "",
                         "parent":  10
                     },
                     {
                         "x":  1074,
                         "type":  "edit",
                         "var":  "",
                         "y":  92,
                         "w":  59,
                         "fmt":  "HH:MMZ",
                         "name":  "Heure",
                         "h":  17,
                         "color":  "6",
                         "text":  "",
                         "parent":  10
                     },
                     {
                         "x":  1144,
                         "type":  "edit",
                         "var":  "",
                         "y":  91,
                         "w":  204,
                         "fmt":  "",
                         "name":  "BookingID",
                         "h":  17,
                         "color":  "6",
                         "text":  "",
                         "parent":  10
                     },
                     {
                         "x":  1369,
                         "type":  "button",
                         "var":  "",
                         "y":  76,
                         "w":  86,
                         "fmt":  "ñ",
                         "name":  "UP",
                         "h":  78,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  1369,
                         "type":  "button",
                         "var":  "",
                         "y":  154,
                         "w":  86,
                         "fmt":  "ò",
                         "name":  "DOWN",
                         "h":  78,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  1092,
                         "type":  "button",
                         "var":  "",
                         "y":  235,
                         "w":  172,
                         "fmt":  "\u0026Validate",
                         "name":  "Valider",
                         "h":  27,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  1283,
                         "type":  "button",
                         "var":  "",
                         "y":  235,
                         "w":  172,
                         "fmt":  "\u0026Quit",
                         "name":  "Exit",
                         "h":  27,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "214.1.3.7",
    "height":  266
}
-->

<details>
<summary><strong>Champs : 10 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 111,55 | v.DateDebut | - | edit |
| 327,55 | v.DateFin | - | edit |
| 26,92 | Checked | - | checkbox |
| 93,91 | CreatedDate | - | edit |
| 208,91 | CreatedTime | - | edit |
| 281,92 | description | - | edit |
| 602,92 | PraticienFullName | - | edit |
| 959,92 | DateDebut | - | edit |
| 1074,92 | Heure | - | edit |
| 1144,91 | BookingID | - | edit |

</details>

<details>
<summary><strong>Boutons : 5 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Refresh | 1332,54 | Rafraichit l'affichage |
| ñ | 1369,76 | Bouton fonctionnel |
| ò | 1369,154 | Bouton fonctionnel |
| Validate | 1092,235 | Valide la saisie et enregistre |
| Quit | 1283,235 | Bouton fonctionnel |

</details>

---

#### <a id="ecran-t34"></a>214.1.4 - Transac not PMS
**Tache** : [214.1.4](#t34) | **Type** : Modal | **Dimensions** : 973 x 248 DLU
**Bloc** : Traitement | **Titre IDE** : Transac not PMS

<!-- FORM-DATA:
{
    "width":  973,
    "vFactor":  8,
    "type":  "Modal",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  354,
                         "type":  "label",
                         "var":  "",
                         "y":  76,
                         "w":  265,
                         "fmt":  "",
                         "name":  "",
                         "h":  96,
                         "color":  "186",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  422,
                         "type":  "edit",
                         "var":  "",
                         "y":  112,
                         "w":  129,
                         "fmt":  "10A",
                         "name":  "SERIAL",
                         "h":  24,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  5,
                         "type":  "button",
                         "var":  "",
                         "y":  201,
                         "w":  121,
                         "fmt":  "\u0026Keyboard",
                         "name":  "KEYBORD",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  142,
                         "type":  "button",
                         "var":  "",
                         "y":  201,
                         "w":  121,
                         "fmt":  "\u0026Validate",
                         "name":  "VALIDATE",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "214.1.4",
    "height":  248
}
-->

<details>
<summary><strong>Champs : 1 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 422,112 | SERIAL | - | edit |

</details>

<details>
<summary><strong>Boutons : 2 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Keyboard | 5,201 | Bouton fonctionnel |
| Validate | 142,201 | Valide la saisie et enregistre |

</details>

---

#### <a id="ecran-t37"></a>214.1.5 - Sales and Payment
**Tache** : [214.1.5](#t37) | **Type** : Modal | **Dimensions** : 976 x 239 DLU
**Bloc** : Traitement | **Titre IDE** : Sales and Payment

<!-- FORM-DATA:
{
    "width":  976,
    "vFactor":  8,
    "type":  "Modal",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  2,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  15,
                         "color":  "6",
                         "w":  928,
                         "y":  0,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  27,
                         "h":  152,
                         "cols":  [
                                      {
                                          "title":  "Date / Time",
                                          "layer":  1,
                                          "w":  62
                                      },
                                      {
                                          "title":  "User / Seller",
                                          "layer":  2,
                                          "w":  65
                                      },
                                      {
                                          "title":  "ID",
                                          "layer":  3,
                                          "w":  44
                                      },
                                      {
                                          "title":  "Description",
                                          "layer":  4,
                                          "w":  220
                                      },
                                      {
                                          "title":  "Comt",
                                          "layer":  5,
                                          "w":  32
                                      },
                                      {
                                          "title":  "",
                                          "layer":  6,
                                          "w":  73
                                      },
                                      {
                                          "title":  "Price",
                                          "layer":  7,
                                          "w":  111
                                      },
                                      {
                                          "title":  "Quantity",
                                          "layer":  8,
                                          "w":  58
                                      },
                                      {
                                          "title":  "Payment",
                                          "layer":  9,
                                          "w":  260
                                      }
                                  ],
                         "rows":  9
                     },
                     {
                         "x":  6,
                         "type":  "edit",
                         "var":  "",
                         "y":  18,
                         "w":  56,
                         "fmt":  "##/##/####Z",
                         "name":  "date_update",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  13,
                         "type":  "edit",
                         "var":  "",
                         "y":  30,
                         "w":  33,
                         "fmt":  "HH:MMZ",
                         "name":  "time_update",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  67,
                         "type":  "edit",
                         "var":  "",
                         "y":  18,
                         "w":  59,
                         "fmt":  "50",
                         "name":  "user_create",
                         "h":  12,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  67,
                         "type":  "button",
                         "var":  "",
                         "y":  30,
                         "w":  61,
                         "fmt":  "Vendeur",
                         "name":  "B.Vendeur",
                         "h":  12,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  132,
                         "type":  "edit",
                         "var":  "",
                         "y":  18,
                         "w":  39,
                         "fmt":  "10Z",
                         "name":  "package_id_out",
                         "h":  12,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  178,
                         "type":  "edit",
                         "var":  "",
                         "y":  18,
                         "w":  210,
                         "fmt":  "",
                         "name":  "description",
                         "h":  12,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  395,
                         "type":  "button",
                         "var":  "",
                         "y":  18,
                         "w":  30,
                         "fmt":  "*",
                         "name":  "COMMENT",
                         "h":  24,
                         "color":  "2",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  435,
                         "type":  "edit",
                         "var":  "",
                         "y":  18,
                         "w":  56,
                         "fmt":  "",
                         "name":  "action_type",
                         "h":  12,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  428,
                         "type":  "edit",
                         "var":  "",
                         "y":  30,
                         "w":  32,
                         "fmt":  "DD/MM",
                         "name":  "date__end_",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  464,
                         "type":  "edit",
                         "var":  "",
                         "y":  30,
                         "w":  32,
                         "fmt":  "DD/MM",
                         "name":  "date__start_",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  572,
                         "type":  "button",
                         "var":  "",
                         "y":  17,
                         "w":  37,
                         "fmt":  "--%",
                         "name":  "DISCOUNT",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  506,
                         "type":  "edit",
                         "var":  "",
                         "y":  18,
                         "w":  61,
                         "fmt":  "N8.3CZ",
                         "name":  "price",
                         "h":  12,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  506,
                         "type":  "edit",
                         "var":  "",
                         "y":  30,
                         "w":  61,
                         "fmt":  "N5.3CZ",
                         "name":  "price",
                         "h":  12,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  616,
                         "type":  "edit",
                         "var":  "",
                         "y":  18,
                         "w":  41,
                         "fmt":  "N9.3Z",
                         "name":  "cpk_quantity",
                         "h":  12,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  748,
                         "type":  "button",
                         "var":  "",
                         "y":  17,
                         "w":  82,
                         "fmt":  "15",
                         "name":  "PAYMENT",
                         "h":  24,
                         "color":  "1",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  832,
                         "type":  "button",
                         "var":  "",
                         "y":  17,
                         "w":  30,
                         "fmt":  "",
                         "name":  "DELETE",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  866,
                         "type":  "button",
                         "var":  "",
                         "y":  17,
                         "w":  30,
                         "fmt":  "",
                         "name":  "ACTION",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  899,
                         "type":  "button",
                         "var":  "",
                         "y":  17,
                         "w":  30,
                         "fmt":  "o",
                         "name":  "VALIDER_LIGNE",
                         "h":  24,
                         "color":  "1",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  671,
                         "type":  "edit",
                         "var":  "",
                         "y":  18,
                         "w":  71,
                         "fmt":  "30",
                         "name":  "",
                         "h":  20,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  931,
                         "type":  "button",
                         "var":  "",
                         "y":  0,
                         "w":  41,
                         "fmt":  "ñ",
                         "name":  "UP",
                         "h":  76,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  931,
                         "type":  "button",
                         "var":  "",
                         "y":  77,
                         "w":  41,
                         "fmt":  "ò",
                         "name":  "DOWN",
                         "h":  76,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  2,
                         "type":  "button",
                         "var":  "",
                         "y":  154,
                         "w":  970,
                         "fmt":  "DISCOUNT",
                         "name":  "DISCOUNT ALL",
                         "h":  27,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  2,
                         "type":  "button",
                         "var":  "",
                         "y":  182,
                         "w":  487,
                         "fmt":  "PAYMENT",
                         "name":  "VALIDATION_ALL",
                         "h":  27,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  497,
                         "type":  "button",
                         "var":  "",
                         "y":  182,
                         "w":  475,
                         "fmt":  "PAYMENT - ALL FILIATIONS",
                         "name":  "VALIDATION_ALLF",
                         "h":  27,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  2,
                         "type":  "button",
                         "var":  "",
                         "y":  210,
                         "w":  970,
                         "fmt":  "RECEIPTS",
                         "name":  "RECEIPTS",
                         "h":  26,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "214.1.5",
    "height":  239
}
-->

<details>
<summary><strong>Champs : 12 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 6,18 | date_update | - | edit |
| 13,30 | time_update | - | edit |
| 67,18 | user_create | - | edit |
| 132,18 | package_id_out | - | edit |
| 178,18 | description | - | edit |
| 435,18 | action_type | - | edit |
| 428,30 | date__end_ | - | edit |
| 464,30 | date__start_ | - | edit |
| 506,18 | price | - | edit |
| 506,30 | price | - | edit |
| 616,18 | cpk_quantity | - | edit |
| 671,18 | 30 | - | edit |

</details>

<details>
<summary><strong>Boutons : 13 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Vendeur | 67,30 | Bouton fonctionnel |
| * | 395,18 | Bouton fonctionnel |
| --% | 572,17 | Bouton fonctionnel |
| 15 | 748,17 | Bouton fonctionnel |
| DELETE | 832,17 | Appel [Delete Product (IDE 194)](PVE-IDE-194.md) |
| ACTION | 866,17 | Bouton fonctionnel |
| o | 899,17 | Bouton fonctionnel |
| ñ | 931,0 | Bouton fonctionnel |
| ò | 931,77 | Bouton fonctionnel |
| DISCOUNT | 2,154 | Appel [Discounts (IDE 201)](PVE-IDE-201.md) |
| PAYMENT | 2,182 | Appel [Generate Preview Payments (IDE 189)](PVE-IDE-189.md) |
| PAYMENT - ALL FILIATIONS | 497,182 | Appel [Generate Preview Payments (IDE 189)](PVE-IDE-189.md) |
| RECEIPTS | 2,210 | Bouton fonctionnel |

</details>

---

#### <a id="ecran-t43"></a>214.1.5.2.1 - Saisie comment annulation
**Tache** : [214.1.5.2.1](#t43) | **Type** : Type0 | **Dimensions** : 318 x 135 DLU
**Bloc** : Saisie | **Titre IDE** : Saisie comment annulation

<!-- FORM-DATA:
{
    "width":  318,
    "vFactor":  8,
    "type":  "Type0",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  102,
                         "w":  314,
                         "fmt":  "",
                         "name":  "",
                         "h":  32,
                         "color":  "6",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  4,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  310,
                         "fmt":  "",
                         "name":  "",
                         "h":  42,
                         "color":  "186",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  14,
                         "type":  "label",
                         "var":  "",
                         "y":  10,
                         "w":  235,
                         "fmt":  "",
                         "name":  "",
                         "h":  22,
                         "color":  "186",
                         "text":  "Enter a comment for the cancelation",
                         "parent":  3
                     },
                     {
                         "x":  265,
                         "type":  "image",
                         "var":  "",
                         "y":  4,
                         "w":  48,
                         "fmt":  "",
                         "name":  "",
                         "h":  37,
                         "color":  "",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  43,
                         "type":  "edit",
                         "var":  "",
                         "y":  60,
                         "w":  234,
                         "fmt":  "",
                         "name":  "Comment",
                         "h":  19,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  5,
                         "type":  "button",
                         "var":  "",
                         "y":  106,
                         "w":  97,
                         "fmt":  "\u0026Keyboard",
                         "name":  "CLAVIER",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  155,
                         "type":  "button",
                         "var":  "",
                         "y":  106,
                         "w":  74,
                         "fmt":  "\u0026Exit",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  235,
                         "type":  "button",
                         "var":  "",
                         "y":  106,
                         "w":  74,
                         "fmt":  "\u0026OK",
                         "name":  "CANCEL",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "214.1.5.2.1",
    "height":  135
}
-->

<details>
<summary><strong>Champs : 1 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 43,60 | Comment | - | edit |

</details>

<details>
<summary><strong>Boutons : 3 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Keyboard | 5,106 | Bouton fonctionnel |
| Exit | 155,106 | Quitte le programme |
| OK | 235,106 | Valide la saisie et enregistre |

</details>

---

#### <a id="ecran-t45"></a>214.1.5.4 - Special actions
**Tache** : [214.1.5.4](#t45) | **Type** : Type6 | **Dimensions** : 312 x 259 DLU
**Bloc** : Traitement | **Titre IDE** : Special actions

<!-- FORM-DATA:
{
    "width":  312,
    "vFactor":  8,
    "type":  "Type6",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  30,
                         "type":  "label",
                         "var":  "",
                         "y":  48,
                         "w":  259,
                         "fmt":  "",
                         "name":  "",
                         "h":  22,
                         "color":  "187",
                         "text":  "Each update will generate a (+/-) charge on the account",
                         "parent":  null
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  227,
                         "w":  312,
                         "fmt":  "",
                         "name":  "",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  310,
                         "fmt":  "",
                         "name":  "",
                         "h":  42,
                         "color":  "186",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  10,
                         "type":  "label",
                         "var":  "",
                         "y":  10,
                         "w":  235,
                         "fmt":  "",
                         "name":  "",
                         "h":  22,
                         "color":  "186",
                         "text":  "Select the update you want to perform on this package",
                         "parent":  3
                     },
                     {
                         "x":  23,
                         "type":  "label",
                         "var":  "",
                         "y":  76,
                         "w":  116,
                         "fmt":  "",
                         "name":  "",
                         "h":  34,
                         "color":  "186",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  110,
                         "type":  "label",
                         "var":  "",
                         "y":  84,
                         "w":  26,
                         "fmt":  "",
                         "name":  "",
                         "h":  22,
                         "color":  "186",
                         "text":  "ç",
                         "parent":  6
                     },
                     {
                         "x":  172,
                         "type":  "label",
                         "var":  "",
                         "y":  76,
                         "w":  116,
                         "fmt":  "",
                         "name":  "",
                         "h":  34,
                         "color":  "186",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  259,
                         "type":  "label",
                         "var":  "",
                         "y":  84,
                         "w":  26,
                         "fmt":  "",
                         "name":  "",
                         "h":  22,
                         "color":  "186",
                         "text":  "è",
                         "parent":  8
                     },
                     {
                         "x":  23,
                         "type":  "label",
                         "var":  "",
                         "y":  129,
                         "w":  116,
                         "fmt":  "",
                         "name":  "",
                         "h":  34,
                         "color":  "186",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  111,
                         "type":  "label",
                         "var":  "",
                         "y":  134,
                         "w":  24,
                         "fmt":  "",
                         "name":  "",
                         "h":  13,
                         "color":  "186",
                         "text":  "è",
                         "parent":  12
                     },
                     {
                         "x":  73,
                         "type":  "label",
                         "var":  "",
                         "y":  135,
                         "w":  26,
                         "fmt":  "",
                         "name":  "",
                         "h":  22,
                         "color":  "66",
                         "text":  "è",
                         "parent":  12
                     },
                     {
                         "x":  111,
                         "type":  "label",
                         "var":  "",
                         "y":  148,
                         "w":  26,
                         "fmt":  "",
                         "name":  "",
                         "h":  14,
                         "color":  "186",
                         "text":  "ç",
                         "parent":  12
                     },
                     {
                         "x":  205,
                         "type":  "button",
                         "var":  "",
                         "y":  232,
                         "w":  100,
                         "fmt":  "\u0026Exit",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  24,
                         "type":  "button",
                         "var":  "",
                         "y":  81,
                         "w":  86,
                         "fmt":  "\u0026CANCELATION",
                         "name":  "CANCEL",
                         "h":  28,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  173,
                         "type":  "button",
                         "var":  "",
                         "y":  81,
                         "w":  86,
                         "fmt":  "\u0026EXTEND",
                         "name":  "EXTEND",
                         "h":  28,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  25,
                         "type":  "button",
                         "var":  "",
                         "y":  134,
                         "w":  86,
                         "fmt":  "\u0026EXCHANGE",
                         "name":  "EXCHANGE",
                         "h":  28,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  261,
                         "type":  "image",
                         "var":  "",
                         "y":  4,
                         "w":  48,
                         "fmt":  "",
                         "name":  "",
                         "h":  37,
                         "color":  "",
                         "text":  "",
                         "parent":  5
                     }
                 ],
    "taskId":  "214.1.5.4",
    "height":  259
}
-->

<details>
<summary><strong>Boutons : 4 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Exit | 205,232 | Quitte le programme |
| CANCELATION | 24,81 | Annule et retour au menu |
| EXTEND | 173,81 | Bouton fonctionnel |
| EXCHANGE | 25,134 | Appel [Menu Check IN / Exchange (IDE 183)](PVE-IDE-183.md) |

</details>

---

#### <a id="ecran-t48"></a>214.1.5.4.2 - Saisie comment annulation
**Tache** : [214.1.5.4.2](#t48) | **Type** : Type6 | **Dimensions** : 322 x 136 DLU
**Bloc** : Saisie | **Titre IDE** : Saisie comment annulation

<!-- FORM-DATA:
{
    "width":  322,
    "vFactor":  8,
    "type":  "Type6",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  102,
                         "w":  318,
                         "fmt":  "",
                         "name":  "",
                         "h":  32,
                         "color":  "6",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  4,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  310,
                         "fmt":  "",
                         "name":  "",
                         "h":  42,
                         "color":  "186",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  14,
                         "type":  "label",
                         "var":  "",
                         "y":  10,
                         "w":  235,
                         "fmt":  "",
                         "name":  "",
                         "h":  22,
                         "color":  "186",
                         "text":  "Enter a comment for the cancelation",
                         "parent":  3
                     },
                     {
                         "x":  265,
                         "type":  "image",
                         "var":  "",
                         "y":  4,
                         "w":  48,
                         "fmt":  "",
                         "name":  "",
                         "h":  37,
                         "color":  "",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  43,
                         "type":  "edit",
                         "var":  "",
                         "y":  60,
                         "w":  234,
                         "fmt":  "",
                         "name":  "Comment",
                         "h":  19,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  5,
                         "type":  "button",
                         "var":  "",
                         "y":  107,
                         "w":  100,
                         "fmt":  "\u0026Keyboard",
                         "name":  "KEYBORD",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  110,
                         "type":  "button",
                         "var":  "",
                         "y":  107,
                         "w":  100,
                         "fmt":  "\u0026Exit",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  215,
                         "type":  "button",
                         "var":  "",
                         "y":  107,
                         "w":  100,
                         "fmt":  "\u0026OK",
                         "name":  "OK",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "214.1.5.4.2",
    "height":  136
}
-->

<details>
<summary><strong>Champs : 1 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 43,60 | Comment | - | edit |

</details>

<details>
<summary><strong>Boutons : 3 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Keyboard | 5,107 | Bouton fonctionnel |
| Exit | 110,107 | Quitte le programme |
| OK | 215,107 | Valide la saisie et enregistre |

</details>

---

#### <a id="ecran-t49"></a>214.1.5.4.3 - End of rental
**Tache** : [214.1.5.4.3](#t49) | **Type** : Type6 | **Dimensions** : 384 x 305 DLU
**Bloc** : Traitement | **Titre IDE** : End of rental

<!-- FORM-DATA:
{
    "width":  384,
    "vFactor":  8,
    "type":  "Type6",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  1,
                         "w":  382,
                         "fmt":  "",
                         "name":  "",
                         "h":  42,
                         "color":  "186",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  10,
                         "type":  "label",
                         "var":  "",
                         "y":  11,
                         "w":  167,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "186",
                         "text":  "Select the last day of rental",
                         "parent":  2
                     },
                     {
                         "x":  7,
                         "type":  "label",
                         "var":  "",
                         "y":  175,
                         "w":  370,
                         "fmt":  "",
                         "name":  "",
                         "h":  98,
                         "color":  "182",
                         "text":  "Selected Date Range",
                         "parent":  null
                     },
                     {
                         "x":  18,
                         "type":  "label",
                         "var":  "",
                         "y":  195,
                         "w":  178,
                         "fmt":  "",
                         "name":  "",
                         "h":  18,
                         "color":  "187",
                         "text":  " Start :",
                         "parent":  5
                     },
                     {
                         "x":  18,
                         "type":  "label",
                         "var":  "",
                         "y":  219,
                         "w":  178,
                         "fmt":  "",
                         "name":  "",
                         "h":  18,
                         "color":  "187",
                         "text":  " End :",
                         "parent":  5
                     },
                     {
                         "x":  18,
                         "type":  "label",
                         "var":  "",
                         "y":  243,
                         "w":  178,
                         "fmt":  "",
                         "name":  "",
                         "h":  18,
                         "color":  "187",
                         "text":  " Cancel the entire period",
                         "parent":  5
                     },
                     {
                         "x":  334,
                         "type":  "image",
                         "var":  "",
                         "y":  5,
                         "w":  48,
                         "fmt":  "",
                         "name":  "",
                         "h":  37,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  7,
                         "type":  "edit",
                         "var":  "",
                         "y":  63,
                         "w":  370,
                         "fmt":  "",
                         "name":  "V.Calendar",
                         "h":  102,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  62,
                         "type":  "edit",
                         "var":  "",
                         "y":  196,
                         "w":  133,
                         "fmt":  "",
                         "name":  "V.DateSatrtSelected",
                         "h":  16,
                         "color":  "110",
                         "text":  "",
                         "parent":  6
                     },
                     {
                         "x":  62,
                         "type":  "edit",
                         "var":  "",
                         "y":  220,
                         "w":  133,
                         "fmt":  "",
                         "name":  "V.DateEndSelected",
                         "h":  16,
                         "color":  "110",
                         "text":  "",
                         "parent":  8
                     },
                     {
                         "x":  175,
                         "type":  "checkbox",
                         "var":  "",
                         "y":  245,
                         "w":  20,
                         "fmt":  "",
                         "name":  "Checked",
                         "h":  15,
                         "color":  "",
                         "text":  "o",
                         "parent":  10
                     },
                     {
                         "x":  7,
                         "type":  "button",
                         "var":  "",
                         "y":  278,
                         "w":  100,
                         "fmt":  "\u0026Exit",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  277,
                         "type":  "button",
                         "var":  "",
                         "y":  278,
                         "w":  100,
                         "fmt":  "\u0026OK",
                         "name":  "Valider",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "214.1.5.4.3",
    "height":  305
}
-->

<details>
<summary><strong>Champs : 4 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 7,63 | V.Calendar | - | edit |
| 62,196 | V.DateSatrtSelected | - | edit |
| 62,220 | V.DateEndSelected | - | edit |
| 175,245 | Checked | - | checkbox |

</details>

<details>
<summary><strong>Boutons : 2 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Exit | 7,278 | Quitte le programme |
| OK | 277,278 | Valide la saisie et enregistre |

</details>

---

#### <a id="ecran-t55"></a>214.1.5.8.1 - Saisie comment annulation
**Tache** : [214.1.5.8.1](#t55) | **Type** : Type0 | **Dimensions** : 318 x 135 DLU
**Bloc** : Saisie | **Titre IDE** : Saisie comment annulation

<!-- FORM-DATA:
{
    "width":  318,
    "vFactor":  8,
    "type":  "Type0",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  102,
                         "w":  314,
                         "fmt":  "",
                         "name":  "",
                         "h":  32,
                         "color":  "6",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  4,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  310,
                         "fmt":  "",
                         "name":  "",
                         "h":  42,
                         "color":  "186",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  14,
                         "type":  "label",
                         "var":  "",
                         "y":  10,
                         "w":  235,
                         "fmt":  "",
                         "name":  "",
                         "h":  22,
                         "color":  "186",
                         "text":  "Enter a comment for the cancelation",
                         "parent":  3
                     },
                     {
                         "x":  265,
                         "type":  "image",
                         "var":  "",
                         "y":  4,
                         "w":  48,
                         "fmt":  "",
                         "name":  "",
                         "h":  37,
                         "color":  "",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  43,
                         "type":  "edit",
                         "var":  "",
                         "y":  60,
                         "w":  234,
                         "fmt":  "",
                         "name":  "Comment",
                         "h":  19,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  5,
                         "type":  "button",
                         "var":  "",
                         "y":  106,
                         "w":  97,
                         "fmt":  "\u0026Keyboard",
                         "name":  "CLAVIER",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  155,
                         "type":  "button",
                         "var":  "",
                         "y":  106,
                         "w":  74,
                         "fmt":  "\u0026Exit",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  235,
                         "type":  "button",
                         "var":  "",
                         "y":  106,
                         "w":  74,
                         "fmt":  "\u0026OK",
                         "name":  "CANCEL",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "214.1.5.8.1",
    "height":  135
}
-->

<details>
<summary><strong>Champs : 1 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 43,60 | Comment | - | edit |

</details>

<details>
<summary><strong>Boutons : 3 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Keyboard | 5,106 | Bouton fonctionnel |
| Exit | 155,106 | Quitte le programme |
| OK | 235,106 | Valide la saisie et enregistre |

</details>

---

#### <a id="ecran-t59"></a>214.1.6 - Transac not PMS MBO
**Tache** : [214.1.6](#t59) | **Type** : MDI | **Dimensions** : 695 x 143 DLU
**Bloc** : Traitement | **Titre IDE** : Transac not PMS MBO

<!-- FORM-DATA:
{
    "width":  695,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  1,
                         "type":  "label",
                         "var":  "",
                         "y":  1,
                         "w":  690,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "189",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  4,
                         "type":  "label",
                         "var":  "",
                         "y":  3,
                         "w":  38,
                         "fmt":  "",
                         "name":  "",
                         "h":  7,
                         "color":  "189",
                         "text":  "Package #",
                         "parent":  null
                     },
                     {
                         "x":  44,
                         "type":  "label",
                         "var":  "",
                         "y":  3,
                         "w":  31,
                         "fmt":  "",
                         "name":  "",
                         "h":  7,
                         "color":  "189",
                         "text":  "Product",
                         "parent":  null
                     },
                     {
                         "x":  109,
                         "type":  "label",
                         "var":  "",
                         "y":  3,
                         "w":  59,
                         "fmt":  "",
                         "name":  "",
                         "h":  7,
                         "color":  "189",
                         "text":  "Customer",
                         "parent":  null
                     },
                     {
                         "x":  207,
                         "type":  "label",
                         "var":  "",
                         "y":  3,
                         "w":  35,
                         "fmt":  "",
                         "name":  "",
                         "h":  7,
                         "color":  "189",
                         "text":  "Payer",
                         "parent":  null
                     },
                     {
                         "x":  290,
                         "type":  "label",
                         "var":  "",
                         "y":  3,
                         "w":  60,
                         "fmt":  "",
                         "name":  "",
                         "h":  7,
                         "color":  "189",
                         "text":  "Payment",
                         "parent":  null
                     },
                     {
                         "x":  354,
                         "type":  "label",
                         "var":  "",
                         "y":  3,
                         "w":  48,
                         "fmt":  "",
                         "name":  "",
                         "h":  7,
                         "color":  "189",
                         "text":  "Quantity",
                         "parent":  null
                     },
                     {
                         "x":  409,
                         "type":  "label",
                         "var":  "",
                         "y":  3,
                         "w":  62,
                         "fmt":  "",
                         "name":  "",
                         "h":  7,
                         "color":  "189",
                         "text":  "Amount",
                         "parent":  null
                     },
                     {
                         "x":  1,
                         "type":  "label",
                         "var":  "",
                         "y":  126,
                         "w":  690,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "189",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  7,
                         "type":  "label",
                         "var":  "",
                         "y":  128,
                         "w":  29,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "189",
                         "text":  "Creation",
                         "parent":  9
                     },
                     {
                         "x":  359,
                         "type":  "label",
                         "var":  "",
                         "y":  128,
                         "w":  26,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "182",
                         "text":  "Total",
                         "parent":  9
                     },
                     {
                         "x":  1,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "110",
                         "w":  659,
                         "y":  12,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  18,
                         "h":  111,
                         "cols":  [
                                      {
                                          "title":  "",
                                          "layer":  1,
                                          "w":  41
                                      },
                                      {
                                          "title":  "cte_libelle",
                                          "layer":  2,
                                          "w":  65
                                      },
                                      {
                                          "title":  "gm_prenom client",
                                          "layer":  3,
                                          "w":  98
                                      },
                                      {
                                          "title":  "gm_prenom payeur",
                                          "layer":  4,
                                          "w":  83
                                      },
                                      {
                                          "title":  "payment_type",
                                          "layer":  5,
                                          "w":  64
                                      },
                                      {
                                          "title":  "",
                                          "layer":  6,
                                          "w":  55
                                      },
                                      {
                                          "title":  "cte_montant",
                                          "layer":  7,
                                          "w":  68
                                      },
                                      {
                                          "title":  "",
                                          "layer":  8,
                                          "w":  47
                                      }
                                  ],
                         "rows":  8
                     },
                     {
                         "x":  478,
                         "type":  "label",
                         "var":  "",
                         "y":  14,
                         "w":  48,
                         "fmt":  "",
                         "name":  "",
                         "h":  7,
                         "color":  "61",
                         "text":  "GIFT PASS",
                         "parent":  16
                     },
                     {
                         "x":  207,
                         "type":  "edit",
                         "var":  "",
                         "y":  15,
                         "w":  80,
                         "fmt":  "",
                         "name":  "",
                         "h":  6,
                         "color":  "110",
                         "text":  "",
                         "parent":  16
                     },
                     {
                         "x":  4,
                         "type":  "edit",
                         "var":  "",
                         "y":  14,
                         "w":  34,
                         "fmt":  "10P0Z",
                         "name":  "",
                         "h":  6,
                         "color":  "110",
                         "text":  "",
                         "parent":  16
                     },
                     {
                         "x":  44,
                         "type":  "edit",
                         "var":  "",
                         "y":  15,
                         "w":  60,
                         "fmt":  "",
                         "name":  "",
                         "h":  6,
                         "color":  "110",
                         "text":  "",
                         "parent":  16
                     },
                     {
                         "x":  44,
                         "type":  "edit",
                         "var":  "",
                         "y":  24,
                         "w":  60,
                         "fmt":  "",
                         "name":  "cte_libelle_supplem_",
                         "h":  6,
                         "color":  "110",
                         "text":  "",
                         "parent":  16
                     },
                     {
                         "x":  409,
                         "type":  "edit",
                         "var":  "",
                         "y":  15,
                         "w":  62,
                         "fmt":  "N10.3C",
                         "name":  "",
                         "h":  6,
                         "color":  "110",
                         "text":  "",
                         "parent":  16
                     },
                     {
                         "x":  40,
                         "type":  "edit",
                         "var":  "",
                         "y":  128,
                         "w":  34,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "189",
                         "text":  "",
                         "parent":  9
                     },
                     {
                         "x":  77,
                         "type":  "edit",
                         "var":  "",
                         "y":  128,
                         "w":  22,
                         "fmt":  "HH:MM",
                         "name":  "",
                         "h":  8,
                         "color":  "189",
                         "text":  "",
                         "parent":  9
                     },
                     {
                         "x":  103,
                         "type":  "edit",
                         "var":  "",
                         "y":  128,
                         "w":  38,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "189",
                         "text":  "",
                         "parent":  9
                     },
                     {
                         "x":  109,
                         "type":  "edit",
                         "var":  "",
                         "y":  24,
                         "w":  95,
                         "fmt":  "",
                         "name":  "gm_nom client",
                         "h":  6,
                         "color":  "110",
                         "text":  "",
                         "parent":  16
                     },
                     {
                         "x":  109,
                         "type":  "edit",
                         "var":  "",
                         "y":  15,
                         "w":  80,
                         "fmt":  "",
                         "name":  "",
                         "h":  6,
                         "color":  "110",
                         "text":  "",
                         "parent":  16
                     },
                     {
                         "x":  290,
                         "type":  "edit",
                         "var":  "",
                         "y":  15,
                         "w":  60,
                         "fmt":  "",
                         "name":  "",
                         "h":  6,
                         "color":  "110",
                         "text":  "",
                         "parent":  16
                     },
                     {
                         "x":  407,
                         "type":  "edit",
                         "var":  "",
                         "y":  128,
                         "w":  62,
                         "fmt":  "N10.3C",
                         "name":  "V.Total payement",
                         "h":  8,
                         "color":  "182",
                         "text":  "",
                         "parent":  9
                     },
                     {
                         "x":  354,
                         "type":  "edit",
                         "var":  "",
                         "y":  15,
                         "w":  48,
                         "fmt":  "N9.3Z",
                         "name":  "",
                         "h":  6,
                         "color":  "110",
                         "text":  "",
                         "parent":  16
                     },
                     {
                         "x":  207,
                         "type":  "edit",
                         "var":  "",
                         "y":  24,
                         "w":  95,
                         "fmt":  "",
                         "name":  "gm_nom payeur",
                         "h":  6,
                         "color":  "110",
                         "text":  "",
                         "parent":  16
                     },
                     {
                         "x":  660,
                         "type":  "button",
                         "var":  "",
                         "y":  67,
                         "w":  31,
                         "fmt":  "ò",
                         "name":  "",
                         "h":  56,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  660,
                         "type":  "button",
                         "var":  "",
                         "y":  13,
                         "w":  31,
                         "fmt":  "ñ",
                         "name":  "",
                         "h":  53,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "214.1.6",
    "height":  143
}
-->

<details>
<summary><strong>Champs : 14 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 207,15 | (sans nom) | - | edit |
| 4,14 | 10P0Z | - | edit |
| 44,15 | (sans nom) | - | edit |
| 44,24 | cte_libelle_supplem_ | - | edit |
| 409,15 | N10.3C | - | edit |
| 40,128 | (sans nom) | - | edit |
| 77,128 | HH:MM | - | edit |
| 103,128 | (sans nom) | - | edit |
| 109,24 | gm_nom client | - | edit |
| 109,15 | (sans nom) | - | edit |
| 290,15 | (sans nom) | - | edit |
| 407,128 | V.Total payement | - | edit |
| 354,15 | N9.3Z | - | edit |
| 207,24 | gm_nom payeur | - | edit |

</details>

<details>
<summary><strong>Boutons : 2 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| ò | 660,67 | Bouton fonctionnel |
| ñ | 660,13 | Bouton fonctionnel |

</details>

---

#### <a id="ecran-t65"></a>214.1.1.2.1.2 - Confirm
**Tache** : [214.1.1.2.1.1](#t65) | **Type** : MDI | **Dimensions** : 554 x 157 DLU
**Bloc** : Traitement | **Titre IDE** : Confirm

<!-- FORM-DATA:
{
    "width":  554,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  26,
                         "type":  "label",
                         "var":  "",
                         "y":  40,
                         "w":  501,
                         "fmt":  "",
                         "name":  "",
                         "h":  18,
                         "color":  "183",
                         "text":  "Please confirm what you intend to do :",
                         "parent":  null
                     },
                     {
                         "x":  3,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  546,
                         "fmt":  "",
                         "name":  "",
                         "h":  36,
                         "color":  "182",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  199,
                         "type":  "button",
                         "var":  "",
                         "y":  130,
                         "w":  154,
                         "fmt":  "\u0026Ok",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  5,
                         "type":  "image",
                         "var":  "",
                         "y":  5,
                         "w":  76,
                         "fmt":  "",
                         "name":  "",
                         "h":  30,
                         "color":  "",
                         "text":  "",
                         "parent":  2
                     },
                     {
                         "x":  26,
                         "type":  "radio",
                         "var":  "",
                         "y":  60,
                         "w":  501,
                         "fmt":  "",
                         "name":  "V.action",
                         "h":  53,
                         "color":  "183",
                         "text":  "E,W,C",
                         "parent":  null
                     }
                 ],
    "taskId":  "214.1.1.2.1.2",
    "height":  157
}
-->

<details>
<summary><strong>Boutons : 1 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Ok | 199,130 | Valide la saisie et enregistre |

</details>

## 9. NAVIGATION

### 9.1 Enchainement des ecrans

```mermaid
flowchart TD
    START([Entree])
    style START fill:#3fb950
    VF1[214 Main Sale V4]
    style VF1 fill:#58a6ff
    VF2[214.1 Choix Onglet]
    style VF2 fill:#58a6ff
    VF3[214.1.1 equipement]
    style VF3 fill:#58a6ff
    VF4[214.1.1.1 Equipment check out]
    style VF4 fill:#58a6ff
    VF7[214.1.1.2 Equipment list]
    style VF7 fill:#58a6ff
    VF8[214.1.1.2.1 Equipment check out]
    style VF8 fill:#58a6ff
    VF9[214.1.1.2.2 Equipment list]
    style VF9 fill:#58a6ff
    VF10[214.1.1.2.2.1 Equipment check IN]
    style VF10 fill:#58a6ff
    VF11[214.1.2 Booking_ID]
    style VF11 fill:#58a6ff
    VF13[214.1.2.2 Select Appointments]
    style VF13 fill:#58a6ff
    VF15[214.1.2.2.2 Packages]
    style VF15 fill:#58a6ff
    VF16[214.1.2.2.2.1 Sub cat]
    style VF16 fill:#58a6ff
    VF17[214.1.2.2.2.1.1 Products]
    style VF17 fill:#58a6ff
    VF23[214.1.3 Onglet Booking]
    style VF23 fill:#58a6ff
    VF25[214.1.3.2 Booking]
    style VF25 fill:#58a6ff
    VF26[214.1.3.3 Screen]
    style VF26 fill:#58a6ff
    VF30[214.1.3.7 Select Appointments]
    style VF30 fill:#58a6ff
    VF34[214.1.4 Transac not PMS]
    style VF34 fill:#58a6ff
    VF37[214.1.5 Sales and Payment]
    style VF37 fill:#58a6ff
    VF43[214.1.5.2.1 Saisie comment ann...]
    style VF43 fill:#58a6ff
    VF45[214.1.5.4 Special actions]
    style VF45 fill:#58a6ff
    VF48[214.1.5.4.2 Saisie comment ann...]
    style VF48 fill:#58a6ff
    VF49[214.1.5.4.3 End of rental]
    style VF49 fill:#58a6ff
    VF55[214.1.5.8.1 Saisie comment ann...]
    style VF55 fill:#58a6ff
    VF59[214.1.6 Transac not PMS MBO]
    style VF59 fill:#58a6ff
    VF65[214.1.1.2.1.1 Confirm]
    style VF65 fill:#58a6ff
    EXT93[IDE 93 Update INV equi...]
    style EXT93 fill:#3fb950
    EXT317[IDE 317 Lancement clavier]
    style EXT317 fill:#3fb950
    EXT196[IDE 196 Package= account]
    style EXT196 fill:#3fb950
    EXT200[IDE 200 Saisie comment...]
    style EXT200 fill:#3fb950
    EXT176[IDE 176 FindAppointments]
    style EXT176 fill:#3fb950
    EXT183[IDE 183 Menu Check IN ...]
    style EXT183 fill:#3fb950
    EXT207[IDE 207 Edition Recap ...]
    style EXT207 fill:#3fb950
    EXT342[IDE 342 Choix - Equipe...]
    style EXT342 fill:#3fb950
    EXT161[IDE 161 GetAppointment]
    style EXT161 fill:#3fb950
    EXT189[IDE 189 Generate Previ...]
    style EXT189 fill:#3fb950
    EXT194[IDE 194 Delete Product]
    style EXT194 fill:#3fb950
    EXT201[IDE 201 Discounts]
    style EXT201 fill:#3fb950
    EXT320[IDE 320 Synchronisatio...]
    style EXT320 fill:#3fb950
    EXT324[IDE 324 Question ME]
    style EXT324 fill:#3fb950
    EXT95[IDE 95 Calcul - bindin...]
    style EXT95 fill:#3fb950
    EXT96[IDE 96 Print Equipment...]
    style EXT96 fill:#3fb950
    EXT153[IDE 153 SearchBooking]
    style EXT153 fill:#3fb950
    EXT157[IDE 157 FindRooms]
    style EXT157 fill:#3fb950
    EXT158[IDE 158 FindEmployees]
    style EXT158 fill:#3fb950
    EXT165[IDE 165 ControleBookingId]
    style EXT165 fill:#3fb950
    FIN([Sortie])
    style FIN fill:#f85149
    START --> VF1
    VF1 -->|Mise a jour donnees| EXT93
    VF1 -->|Sous-programme| EXT317
    VF1 -->|Sous-programme| EXT196
    VF1 -->|Sous-programme| EXT200
    VF1 -->|Sous-programme| EXT176
    VF1 -->|Navigation menu| EXT183
    VF1 -->|Impression ticket/document| EXT207
    VF1 -->|Selection/consultation| EXT342
    EXT165 --> FIN
```

**Detail par enchainement :**

| Depuis | Action | Vers | Retour |
|--------|--------|------|--------|
| Main Sale V4 | Mise a jour donnees | [Update INV equipment status (IDE 93)](PVE-IDE-93.md) | Retour ecran |
| Main Sale V4 | Sous-programme | [Lancement clavier (IDE 317)](PVE-IDE-317.md) | Retour ecran |
| Main Sale V4 | Sous-programme | [      Package=> account (IDE 196)](PVE-IDE-196.md) | Retour ecran |
| Main Sale V4 | Sous-programme | [Saisie commentaire (IDE 200)](PVE-IDE-200.md) | Retour ecran |
| Main Sale V4 | Sous-programme | [FindAppointments (IDE 176)](PVE-IDE-176.md) | Retour ecran |
| Main Sale V4 | Navigation menu | [Menu Check IN / Exchange (IDE 183)](PVE-IDE-183.md) | Retour ecran |
| Main Sale V4 | Impression ticket/document | [Edition Recap Rendez-vous (IDE 207)](PVE-IDE-207.md) | Retour ecran |
| Main Sale V4 | Selection/consultation | [Choix - Equipements (IDE 342)](PVE-IDE-342.md) | Retour ecran |
| Main Sale V4 | Recuperation donnees | [GetAppointment (IDE 161)](PVE-IDE-161.md) | Retour ecran |
| Main Sale V4 | Sous-programme | [Generate Preview Payments (IDE 189)](PVE-IDE-189.md) | Retour ecran |
| Main Sale V4 | Sous-programme | [Delete Product (IDE 194)](PVE-IDE-194.md) | Retour ecran |
| Main Sale V4 | Sous-programme | [Discounts (IDE 201)](PVE-IDE-201.md) | Retour ecran |
| Main Sale V4 | Recuperation donnees | [SynchronisationRecuPDF (IDE 320)](PVE-IDE-320.md) | Retour ecran |
| Main Sale V4 | Sous-programme | [Question M&E (IDE 324)](PVE-IDE-324.md) | Retour ecran |
| Main Sale V4 | Calcul de donnees | [Calcul - binding setting (IDE 95)](PVE-IDE-95.md) | Retour ecran |
| Main Sale V4 | Impression ticket/document | [Print Equipment SELECT (IDE 96)](PVE-IDE-96.md) | Retour ecran |
| Main Sale V4 | Sous-programme | [SearchBooking (IDE 153)](PVE-IDE-153.md) | Retour ecran |
| Main Sale V4 | Sous-programme | [FindRooms (IDE 157)](PVE-IDE-157.md) | Retour ecran |
| Main Sale V4 | Sous-programme | [FindEmployees (IDE 158)](PVE-IDE-158.md) | Retour ecran |
| Main Sale V4 | Controle/validation | [ControleBookingId (IDE 165)](PVE-IDE-165.md) | Retour ecran |

### 9.3 Structure hierarchique (64 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **214.1** | [**Main Sale V4** (214)](#t1) [mockup](#ecran-t1) | Modal | 1990x392 | Traitement |
| 214.1.1 | [equipement (214.1.1)](#t3) [mockup](#ecran-t3) | Modal | 971x229 | |
| 214.1.2 | [Equipment check out (214.1.1.1)](#t4) [mockup](#ecran-t4) | MDI | 320x254 | |
| 214.1.3 | [clear (214.1.1.1.1)](#t5) | MDI | - | |
| 214.1.4 | [Récupère Libellé Classif (214.1.1.1.2)](#t6) | - | - | |
| 214.1.5 | [Equipment list (214.1.1.2)](#t7) [mockup](#ecran-t7) | MDI | 269x280 | |
| 214.1.6 | [Equipment check out (214.1.1.2.1)](#t8) [mockup](#ecran-t8) | MDI | 322x282 | |
| 214.1.7 | [Equipment list (214.1.1.2.2)](#t9) [mockup](#ecran-t9) | MDI | 190x280 | |
| 214.1.8 | [Equipment check IN (214.1.1.2.2.1)](#t10) [mockup](#ecran-t10) | Type6 | 642x281 | |
| 214.1.9 | [Booking_ID (214.1.2)](#t11) [mockup](#ecran-t11) | Modal | 973x248 | |
| 214.1.10 | [Packages (214.1.2.2.2)](#t15) [mockup](#ecran-t15) | MDI | 581x366 | |
| 214.1.11 | [Sub cat (214.1.2.2.2.1)](#t16) [mockup](#ecran-t16) | Modal | 386x324 | |
| 214.1.12 | [Products (214.1.2.2.2.1.1)](#t17) [mockup](#ecran-t17) | Modal | 182x314 | |
| 214.1.13 | [Get last package id (214.1.2.2.3)](#t18) | MDI | - | |
| 214.1.14 | [Package=> cust account (214.1.2.2.4)](#t19) [mockup](#ecran-t19) | MDI | 344x227 | |
| 214.1.15 | [Onglet Booking (214.1.3)](#t23) [mockup](#ecran-t23) | Modal | 976x239 | |
| 214.1.16 | [Booking (214.1.3.2)](#t25) [mockup](#ecran-t25) | Type6 | 440x136 | |
| 214.1.17 | [Screen (214.1.3.3)](#t26) [mockup](#ecran-t26) | Type6 | 1845x250 | |
| 214.1.18 | [GetBookigsInfo (214.1.3.4)](#t27) | - | - | |
| 214.1.19 | [Apparier /t forfait/package (214.1.3.6)](#t29) | - | - | |
| 214.1.20 | [Del ligne vide (214.1.3.7.2.1)](#t33) | - | - | |
| 214.1.21 | [Transac not PMS (214.1.4)](#t34) [mockup](#ecran-t34) | Modal | 973x248 | |
| 214.1.22 | [Get prod id (214.1.4.1)](#t35) | - | - | |
| 214.1.23 | [Get Cat & Subcat (214.1.4.2)](#t36) | - | - | |
| 214.1.24 | [Sales and Payment (214.1.5)](#t37) [mockup](#ecran-t37) | Modal | 976x239 | |
| 214.1.25 | [Payment (214.1.5.1)](#t38) [mockup](#ecran-t38) | MDI | 238x63 | |
| 214.1.26 | [View (214.1.5.1.2)](#t40) | - | - | |
| 214.1.27 | [Discount (214.1.5.2)](#t42) [mockup](#ecran-t42) | MDI | 220x94 | |
| 214.1.28 | [Test Prepaid (214.1.5.3)](#t44) | MDI | - | |
| 214.1.29 | [Special actions (214.1.5.4)](#t45) [mockup](#ecran-t45) | Type6 | 312x259 | |
| 214.1.30 | [Cancel other Packages (214.1.5.4.1)](#t46) [mockup](#ecran-t46) | Type6 | 312x259 | |
| 214.1.31 | [UpdateCustRentals (214.1.5.4.1.1)](#t47) | - | - | |
| 214.1.32 | [End of rental (214.1.5.4.3)](#t49) [mockup](#ecran-t49) | Type6 | 384x305 | |
| 214.1.33 | [UpdateCustRentals (214.1.5.4.4)](#t50) | - | - | |
| 214.1.34 | [Check Rentals (214.1.5.5)](#t51) | MDI | - | |
| 214.1.35 | [Check Payments (214.1.5.6)](#t52) [mockup](#ecran-t52) | MDI | 926x449 | |
| 214.1.36 | [Check Comment Refus. To Sell (214.1.5.7)](#t53) [mockup](#ecran-t53) | - | 522x498 | |
| 214.1.37 | [Discount (214.1.5.8)](#t54) [mockup](#ecran-t54) | MDI | 854x202 | |
| 214.1.38 | [Delete other Packages (214.1.5.9)](#t56) [mockup](#ecran-t56) | Type6 | 312x259 | |
| 214.1.39 | [SQL Total payement (214.1.5.11)](#t58) [mockup](#ecran-t58) | - | 115x195 | |
| 214.1.40 | [Transac not PMS MBO (214.1.6)](#t59) [mockup](#ecran-t59) | MDI | 695x143 | |
| 214.1.41 | [SQL Total payement (214.1.6.1)](#t60) [mockup](#ecran-t60) | - | 115x195 | |
| 214.1.42 | [Confirm (214.1.1.2.1.1)](#t65) [mockup](#ecran-t65) | MDI | 554x157 | |
| 214.1.43 | [Récupère Libellé Classif (214.1.1.2.1.2)](#t71) | - | - | |
| **214.2** | [**Choix Onglet** (214.1)](#t2) [mockup](#ecran-t2) | MDI | 987x261 | Consultation |
| 214.2.1 | [Select Appointments (214.1.2.2)](#t13) [mockup](#ecran-t13) | Type6 | 1464x266 | |
| 214.2.2 | [Select all (214.1.2.2.1)](#t14) | - | - | |
| 214.2.3 | [Select Appointments (214.1.3.7)](#t30) [mockup](#ecran-t30) | Type6 | 1464x266 | |
| 214.2.4 | [Select all (214.1.3.7.1)](#t31) | - | - | |
| **214.3** | [**CreateSales** (214.1.2.1)](#t12) | - | - | Creation |
| 214.3.1 | [Create cust rentals (214.1.2.2.4.1)](#t20) [mockup](#ecran-t20) | MDI | 173x115 | |
| 214.3.2 | [Create Card Type (214.1.2.2.4.2)](#t21) | MDI | - | |
| 214.3.3 | [create cust package (214.1.2.2.4.3)](#t22) [mockup](#ecran-t22) | MDI | 123x85 | |
| 214.3.4 | [CreateMail (214.1.3.5)](#t28) | - | - | |
| 214.3.5 | [CreateSales (214.1.3.7.2)](#t32) | - | - | |
| 214.3.6 | [create cardType (214.1.5.1.3)](#t41) | MDI | - | |
| **214.4** | [**Raz mem booking** (214.1.3.1)](#t24) | - | - | Initialisation |
| 214.4.1 | [init payer (214.1.5.1.1)](#t39) | MDI | - | |
| **214.5** | [**Saisie comment annulation** (214.1.5.2.1)](#t43) [mockup](#ecran-t43) | - | 318x135 | Saisie |
| 214.5.1 | [Saisie comment annulation (214.1.5.4.2)](#t48) [mockup](#ecran-t48) | Type6 | 322x136 | |
| 214.5.2 | [Saisie comment annulation (214.1.5.8.1)](#t55) [mockup](#ecran-t55) | - | 318x135 | |
| **214.6** | [**Verif Multi-Payeurs comptes <>** (214.1.5.10)](#t57) [mockup](#ecran-t57) | - | 123x195 | Validation |
| 214.6.1 | [verify not already canceled (214.1.5.12)](#t62) | - | - | |
| **214.7** | [**calcul filiation** (214.2)](#t61) | MDI | - | Calcul |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Choix Onglet]
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

### Tables utilisees (40)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 30 | gm-recherche_____gmr | Index de recherche | DB | R |   |   | 2 |
| 34 | hebergement______heb | Hebergement (chambres) | DB |   |   | L | 1 |
| 36 | client_gm |  | DB |   |   | L | 1 |
| 39 | depot_garantie___dga | Depots et garanties | DB |   |   | L | 1 |
| 47 | compte_gm________cgm | Comptes GM (generaux) | DB |   |   | L | 2 |
| 67 | tables___________tab |  | DB | R |   |   | 1 |
| 69 | initialisation___ini |  | DB |   |   | L | 1 |
| 77 | articles_________art | Articles et stock | DB | R |   | L | 3 |
| 79 | gratuites________gra |  | DB |   |   | L | 2 |
| 120 | tables_qualites__qua |  | DB |   |   | L | 1 |
| 285 | email |  | DB |   |   | L | 1 |
| 358 | import_mod |  | DB |   |   | L | 1 |
| 377 | pv_contracts |  | DB |   |   | L | 1 |
| 378 | pv_customer |  | DB |   | **W** | L | 3 |
| 379 | pv_customer_temp |  | DB | R | **W** | L | 5 |
| 380 | pv_day_modes |  | DB | R |   | L | 9 |
| 382 | pv_discount_reasons |  | DB | R | **W** | L | 16 |
| 388 | pv_hotel_days |  | DB |   |   | L | 3 |
| 389 | pv_equipment_inventory |  | DB | R |   | L | 8 |
| 398 | pv_prestations | Prestations/services vendus | DB |   |   | L | 3 |
| 400 | pv_cust_rentals |  | DB | R | **W** | L | 22 |
| 401 | pv_cust_rentals_histo | Historique / journal | DB | R |   | L | 2 |
| 403 | pv_sellers |  | DB | R |   | L | 17 |
| 404 | pv_sellers_by_week |  | DB |   | **W** | L | 9 |
| 411 | sk_testcab |  | DB |   |   | L | 1 |
| 413 | pv_tva |  | DB |   | **W** | L | 9 |
| 418 | pv_years |  | DB |   |   | L | 1 |
| 419 | realise_articles_caution | Articles et stock | DB |   |   | L | 6 |
| 728 | arc_cc_total |  | DB |   |   | L | 1 |
| 756 | Country_ISO |  | DB |   |   | L | 1 |
| 765 | tranche_age |  | DB |   |   | L | 1 |
| 766 | temp_forfait_ski |  | DB |   |   | L | 1 |
| 786 | qualite_avant_reprise |  | DB |   |   | L | 1 |
| 845 | stat_vendeur_date |  | TMP |   |   | L | 1 |
| 1488 | Table_1488 |  | MEM |   |   | L | 2 |
| 1501 | Table_1501 |  | MEM |   | **W** |   | 1 |
| 1520 | Table_1520 |  | MEM |   |   | L | 1 |
| 1539 | Table_1539 |  | MEM | R | **W** | L | 11 |
| 1548 | Table_1548 |  | MEM |   | **W** | L | 7 |
| 1550 | Table_1550 |  | MEM |   | **W** | L | 5 |

### Colonnes par table (21 / 17 tables avec colonnes identifiees)

<details>
<summary>Table 30 - gm-recherche_____gmr (R) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | v.Tab_Filation1 | R | Alpha |
| B | v.LequipmentId | R | Alpha |
| C | v.Update Tab Filiation | R | Logical |
| D | P. Date | R | Date |
| E | P. Category | R | Numeric |
| F | P. Sub cat | R | Numeric |
| G | P. Product | R | Numeric |
| H | P. Payment type | R | Alpha |
| I | P. Equipment id | R | Alpha |
| J | P. FlagDate | R | Numeric |
| K | P. Quantity | R | Numeric |
| L | P. ART Quantité en stock | R | Numeric |
| M | P.Prix | R | Numeric |
| N | P.Montant PrePaid | R | Numeric |
| O | P.Service | R | Alpha |
| P | P.Code Fidelisation | R | Alpha |
| Q | P.Start location date | R | Date |
| R | P.Art Prix Libre | R | Logical |
| S | P.BookingID | R | Unicode |
| T | P.BookingOrderID | R | Numeric |
| U | P.without invoicing | R | Logical |
| V | P. FBO Description | R | Unicode |
| W | P. Num package id (new) | R | Numeric |
| X | V New package id | R | Numeric |
| Y | v.Libelle VIP | R | Alpha |
| Z | v.All.Payment ? | R | Logical |
| BA | v.L.Test Discount ? | R | Logical |
| BB | v.SodeCompte== | R | Numeric |
| BC | V Garantie (O/N) | R | Alpha |
| BD | v.Clause Where | R | Alpha |
| BE | R.retour Message | R | Numeric |
| BF | v.Valid_Product_All | R | Logical |
| BG | v.Deb_Sejour | R | Date |
| BH | v.Fin_sejour | R | Date |
| BI | v.Qualite | R | Unicode |
| BJ | v.End | R | Logical |
| BK | V Lien Compte Seminaire | R | Logical |
| BL | v.Libelle Fidelisation | R | Unicode |
| BM | v.Insurance | R | Alpha |
| BN | v.FocusOngletBooking | R | Logical |
| BO | V."Best of" Interdit Mineur/A ? | R | Logical |
| BP | Btn.ExtraitCompte | R | Alpha |
| BQ | V.CodeRerourExtraitCompte | R | Alpha |
| BR | V.SoldeCompte | R | Numeric |
| BS | V.EtatCompte | R | Alpha |
| BT | V.dateSolde | R | Date |
| BU | V.GarantieO/N | R | Alpha |

</details>

<details>
<summary>Table 67 - tables___________tab (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P.Categorie | R | Numeric |
| B | P.Sous categorie | R | Numeric |
| C | v.visible 3 | R | Logical |
| D | v.font 3 | R | Numeric |
| E | BP. Create | R | Alpha |
| F | BP. Modify | R | Alpha |
| G | BP. Delete | R | Alpha |
| H | V.Existe vente ? | R | Logical |
| I | V.Existe vente Archivée | R | Logical |
| J | v Possible Création ? | R | Logical |
| K | v Nouveau Num Produit | R | Numeric |
| L | v_Mode | R | Unicode |
| M | (bt) Select | R | Alpha |
| N | (bt) Cancel | R | Alpha |

</details>

<details>
<summary>Table 77 - articles_________art (R/L) - 3 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | p.Customer_ID | R | Numeric |
| B | v.Onglet | R | Alpha |
| C | v.RetourMessage | R | Numeric |
| D | v.Stop Delete | R | Logical |
| E | L_Package_IN | R | Logical |
| F | v.Existe Remise_Great_Number | R | Logical |
| G | v.Lien lieu vente / imputation | R | Logical |
| H | v.lien imputation article | R | Logical |
| I | v.Lien Package non valide | R | Logical |
| J | PackageIdOrigine | R | Numeric |
| K | v.ImputationGratuite | R | Logical |
| L | BP.Gift Pass | R | Alpha |
| M | BP. Print | R | Alpha |
| N | V Action type | R | Alpha |
| O | V Solde Gift Pass | R | Numeric |
| P | V Montant  Eligible Gift Pass | R | Numeric |
| Q | V Type | R | Alpha |
| R | v.Card Type (Param) | R | Alpha |
| S | v.Prépaid ? | R | Logical |
| T | v.EmptyRental | R | Logical |
| U | v.EmptyPayment | R | Logical |
| V | V empty comment(Refus.to sell) | R | Logical |
| W | v.Action Type | R | Alpha |
| X | v.Confirme Action | R | Numeric |
| Y | v.AllPayments | R | Logical |
| Z | v.AnnulPayment | R | Logical |
| BA |  v Montant Credit Conso / Free | R | Numeric |
| BB | v.Adresse Mail | R | Alpha |
| BC | v.Langue | R | Alpha |
| BD | v.Envoi Email | R | Logical |
| BE | v.nbrTotalAValider | R | Numeric |
| BF | v.NbrwithoutBooking | R | Numeric |
| BG | v.NotCancelBooking | R | Logical |
| BH | ConfirmCancelBooking | R | Numeric |
| BI | V.day difference | R | Numeric |
| BJ | V.Allow Cancel | R | Logical |
| BK | v.count | R | Numeric |
| BL | v.Existe Forfait Package | R | Logical |
| BM | v. already canceled? | R | Logical |
| BN | v.commentaire KO? REFUSALL2SALE | R | Logical |
| BO | v.Activer Bouton Payment? | R | Logical |
| BP | V.Blocage | R | Logical |

</details>

<details>
<summary>Table 378 - pv_customer (**W**/L) - 3 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P. Customer | W | Numeric |
| K | v.Customer_ID | W | Numeric |
| V | v.Titre Bt Customer | W | Alpha |

</details>

<details>
<summary>Table 379 - pv_customer_temp (R/**W**/L) - 5 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P.Valider | W | Logical |
| B | P.Package/Forfait | W | Logical |
| C | v.DateDebut | W | Date |
| D | v.DateFin | W | Date |
| E | v.NbrSelected | W | Numeric |
| F | P.Action Type-z | W | Unicode |
| G | v.visible 1 | W | Logical |
| H | v.font 1 | W | Numeric |
| I | V.ComboActive | W | Alpha |
| J | L Indicateur | W | Logical |
| K | BP. Create | W | Alpha |
| L | BP. Modif | W | Alpha |
| M | L S/Category ? | W | Logical |
| N | BP. Delete | W | Alpha |
| O | BP. Exit | W | Alpha |
| P | V.Masque | W | Alpha |
| Q | V.Masque sans Z | W | Alpha |
| R | V.Decimals | W | Numeric |
| S | V.Category | W | Numeric |
| T | L.Existe sous cat ? | W | Logical |
| U | V.Eligible Credit GO - VISIBLE? | W | Logical |
| V | BT. Select | W | Alpha |
| W | CHG_REASON_V.ComboActive | W | Numeric |
| X | CHG_PRV_V.ComboActive | W | Alpha |

</details>

<details>
<summary>Table 380 - pv_day_modes (R/L) - 9 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 382 - pv_discount_reasons (R/**W**/L) - 16 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P.Societe | W | Alpha |
| B | P.Compte | W | Numeric |
| C | P.Filiation | W | Numeric |
| D | v.binding setting | W | Numeric |
| E | v.Date In Alpha | W | Alpha |
| F | v.color | W | Numeric |
| G | bt swap | W | Alpha |
| H | V.Exchange automatique | W | Logical |
| I | p.Checkin, Exchange, les deux | W | Alpha |

</details>

<details>
<summary>Table 389 - pv_equipment_inventory (R/L) - 8 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | v.serial | R | Alpha |
| B | v.confirm <> Type matos | R | Numeric |
| C | v.confirm <> classif | R | Numeric |
| D | v.Existe_equipment? | R | Logical |
| E | v. action choice | R | Alpha |
| F | v. cancel requested | R | Logical |
| G | CHG_PRV_v.serial | R | Alpha |

</details>

<details>
<summary>Table 400 - pv_cust_rentals (R/**W**/L) - 22 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P New package id | W | Numeric |
| B | v.Desciption | W | Unicode |
| C | V allow cancel | W | Logical |
| D | montant_free_extra | W | Numeric |
| E | V Total | W | Numeric |
| F | V.Clause where | W | Alpha |
| G | V.Add jointure | W | Alpha |
| H | V.AnnulerToutLaPeriode | W | Logical |

</details>

<details>
<summary>Table 401 - pv_cust_rentals_histo (R/L) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P.Societe | R | Alpha |
| B | P.Compte | R | Numeric |
| C | P.Filiation | R | Numeric |
| D | v.Serial Id | R | Alpha |
| E | v.retour equipment | R | Logical |
| F | v.retour produit | R | Logical |
| G | V.Cat | R | Numeric |
| H | V.SubCat | R | Numeric |
| I | V.Exist package price ? | R | Logical |
| J | V. M&E Price | R | Numeric |
| K | V.Start rental date | R | Date |
| L | V.Today ? | R | Logical |
| M | V.Prod id | R | Numeric |
| N | v.Facturé au M&E? | R | Logical |
| O | v.% de réduction | R | Numeric |
| P | v.prix du produit | R | Numeric |

</details>

<details>
<summary>Table 403 - pv_sellers (R/L) - 17 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P.BookingID | R | Unicode |
| B | v.Facturé au M&E? | R | Logical |
| C | v.% de réduction | R | Numeric |
| D | v.prix du produit | R | Numeric |
| E | V.BookingID | R | Unicode |
| F | BookingIDIsOK? | R | Logical |
| G | BouttonValiderGrise? | R | Logical |
| H | V.OrderID | R | Numeric |
| I | B Ok | R | Alpha |

</details>

<details>
<summary>Table 404 - pv_sellers_by_week (**W**/L) - 9 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 413 - pv_tva (**W**/L) - 9 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P.Categorie | W | Numeric |
| B | v.visible 2 | W | Logical |
| C | v.font 2 | W | Numeric |
| D | V.ComboActive | W | Alpha |
| E | L Indicateur | W | Logical |
| F | BP. Create | W | Alpha |
| G | BP. Modify | W | Alpha |
| H | L Product ? | W | Logical |
| I | BP. Delete | W | Alpha |
| J | BP. Classification | W | Alpha |
| K | BP. Matos | W | Alpha |
| L | L Discount article | W | Logical |
| M | BP. Article id | W | Alpha |
| N | BP. Authorize | W | Alpha |
| O | L.Sub cat | W | Numeric |
| P | V.Existe produit ? | W | Logical |
| Q | v.Matos Modif | W | Logical |
| R | CHG_REASON_V.ComboActive | W | Numeric |
| S | CHG_PRV_V.ComboActive | W | Alpha |

</details>

<details>
<summary>Table 1501 - Table_1501 (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 1539 - Table_1539 (R/**W**/L) - 11 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | BookingID | W | Unicode |
| B | BookingNumber | W | Numeric |
| C | IsSuccessGetBooking | W | Logical |
| D | ErrorMessage | W | Alpha |
| E | Exists? | W | Logical |
| F | v.AppointmentsSelected | W | Logical |
| G | L.Categ | W | Numeric |
| H | L. Sub Categ | W | Numeric |
| I | L. Sub sub categ | W | Numeric |
| J | L. Descript | W | Unicode |
| K | L. Prix | W | Numeric |
| L | L.Num Package statique | W | Numeric |
| M | L.Package Forfait (O/N) | W | Logical |

</details>

<details>
<summary>Table 1548 - Table_1548 (**W**/L) - 7 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | v.DateDebut | W | Date |
| B | v.DateFin | W | Date |
| C | v.NbrSelected | W | Numeric |
| D | Btn.Refresh | W | Alpha |
| E | CHG_REASON_Select | W | Numeric |
| F | CHG_PRV_Select | W | Logical |

</details>

<details>
<summary>Table 1550 - Table_1550 (**W**/L) - 5 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Variables de session (44)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | v.Tab_Filation1 | Alpha | 1x session |
| B | v.LequipmentId | Alpha | - |
| C | v.Update Tab Filiation | Logical | [214.2](#t61) |
| D | v.Masque | Alpha | 1x session |
| E | v.Masque sans Z | Alpha | - |
| F | v.RechercheClubmedPass | Alpha | - |
| G | v.Compte Sauvegarde | Numeric | - |
| H | v.Societe | Unicode | 3x session |
| I | v.Compte | Numeric | 3x session |
| J | v..Filation | Numeric | 3x session |
| K | v.Customer_ID | Numeric | 2x session |
| L | v.Filiation_List | Alpha | - |
| M | v.TabOption | Alpha | - |
| N | v.RoomNumber | Alpha | 1x session |
| O | V PoS payer id from card | Numeric | [214.1.2.2.4.2](#t21), [214.1.5.1.1](#t39), [214.1.5.1.3](#t41) |
| P | V pms account from card | Numeric | [214.1.2.2.4](#t19), [214.1.2.2.4.2](#t21), [214.1.5.1.3](#t41) |
| Q | V pms filiation from card | Numeric | [214.1.2.2.4.2](#t21), [214.1.5.1.3](#t41), [214.2](#t61) |
| R | V Club Med Pass | Alpha | 1x session |
| S | v.LequipementID | Alpha | 1x session |
| T | v.Garantie | Unicode | 2x session |
| U | v Existe Cr.Conso/Gift Pass | Logical | - |
| V | v.Titre Bt Customer | Alpha | 2x session |
| X | v.Code fidelisation | Alpha | - |
| Y | v.Libelle VIP | Alpha | 1x session |
| Z | v.All.Payment ? | Logical | - |
| BA | v.L.Test Discount ? | Logical | - |
| BB | v.SodeCompte== | Numeric | - |
| BC | V Garantie (O/N) | Alpha | 1x session |
| BD | v.Clause Where | Alpha | - |
| BF | v.Valid_Product_All | Logical | - |
| BG | v.Deb_Sejour | Date | 5x session |
| BH | v.Fin_sejour | Date | - |
| BI | v.Qualite | Unicode | - |
| BJ | v.End | Logical | - |
| BK | V Lien Compte Seminaire | Logical | [214.1.5.10](#t57) |
| BL | v.Libelle Fidelisation | Unicode | 1x session |
| BM | v.Insurance | Alpha | 1x session |
| BN | v.FocusOngletBooking | Logical | - |
| BO | V."Best of" Interdit Mineur/A ? | Logical | - |
| BQ | V.CodeRerourExtraitCompte | Alpha | - |
| BR | V.SoldeCompte | Numeric | 1x session |
| BS | V.EtatCompte | Alpha | 3x session |
| BT | V.dateSolde | Date | 1x session |
| BU | V.GarantieO/N | Alpha | - |

### 11.2 Autres (3)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| W | L.Pakage_Id | Numeric | - |
| BE | R.retour Message | Numeric | - |
| BP | Btn.ExtraitCompte | Alpha | 1x refs |

<details>
<summary>Toutes les 47 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| V. | **A** | v.Tab_Filation1 | Alpha |
| V. | **B** | v.LequipmentId | Alpha |
| V. | **C** | v.Update Tab Filiation | Logical |
| V. | **D** | v.Masque | Alpha |
| V. | **E** | v.Masque sans Z | Alpha |
| V. | **F** | v.RechercheClubmedPass | Alpha |
| V. | **G** | v.Compte Sauvegarde | Numeric |
| V. | **H** | v.Societe | Unicode |
| V. | **I** | v.Compte | Numeric |
| V. | **J** | v..Filation | Numeric |
| V. | **K** | v.Customer_ID | Numeric |
| V. | **L** | v.Filiation_List | Alpha |
| V. | **M** | v.TabOption | Alpha |
| V. | **N** | v.RoomNumber | Alpha |
| V. | **O** | V PoS payer id from card | Numeric |
| V. | **P** | V pms account from card | Numeric |
| V. | **Q** | V pms filiation from card | Numeric |
| V. | **R** | V Club Med Pass | Alpha |
| V. | **S** | v.LequipementID | Alpha |
| V. | **T** | v.Garantie | Unicode |
| V. | **U** | v Existe Cr.Conso/Gift Pass | Logical |
| V. | **V** | v.Titre Bt Customer | Alpha |
| V. | **X** | v.Code fidelisation | Alpha |
| V. | **Y** | v.Libelle VIP | Alpha |
| V. | **Z** | v.All.Payment ? | Logical |
| V. | **BA** | v.L.Test Discount ? | Logical |
| V. | **BB** | v.SodeCompte== | Numeric |
| V. | **BC** | V Garantie (O/N) | Alpha |
| V. | **BD** | v.Clause Where | Alpha |
| V. | **BF** | v.Valid_Product_All | Logical |
| V. | **BG** | v.Deb_Sejour | Date |
| V. | **BH** | v.Fin_sejour | Date |
| V. | **BI** | v.Qualite | Unicode |
| V. | **BJ** | v.End | Logical |
| V. | **BK** | V Lien Compte Seminaire | Logical |
| V. | **BL** | v.Libelle Fidelisation | Unicode |
| V. | **BM** | v.Insurance | Alpha |
| V. | **BN** | v.FocusOngletBooking | Logical |
| V. | **BO** | V."Best of" Interdit Mineur/A ? | Logical |
| V. | **BQ** | V.CodeRerourExtraitCompte | Alpha |
| V. | **BR** | V.SoldeCompte | Numeric |
| V. | **BS** | V.EtatCompte | Alpha |
| V. | **BT** | V.dateSolde | Date |
| V. | **BU** | V.GarantieO/N | Alpha |
| Autre | **W** | L.Pakage_Id | Numeric |
| Autre | **BE** | R.retour Message | Numeric |
| Autre | **BP** | Btn.ExtraitCompte | Alpha |

</details>

## 12. EXPRESSIONS

**115 / 115 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCULATION | 8 | 0 |
| CAST_LOGIQUE | 7 | 2 |
| CONDITION | 35 | 15 |
| CONSTANTE | 8 | 0 |
| OTHER | 37 | 0 |
| REFERENCE_VG | 16 | 0 |
| STRING | 3 | 0 |
| CONCATENATION | 1 | 0 |

### 12.2 Expressions cles par type

#### CALCULATION (8 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 38 | `Left (Trim (v.Masque [D]),Len (Trim (v.Masque [D]))-1)` | - |
| CALCULATION | 36 | `CallProg ('{305,-1}'PROG,[AK],[AL])` | - |
| CALCULATION | 88 | `'BEST OF -  '&GetParam('LIBELBESTOF')` | - |
| CALCULATION | 85 | `'BEST OF -  '&GetParam('LIBELBESTOF')` | - |
| CALCULATION | 30 | `'USER LOGON - '&Trim(VG39)` | - |
| ... | | *+3 autres* | |

#### CAST_LOGIQUE (7 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 45 | `IF(GetParam ('RENTAL')='TRUE'LOG,'Insurance','')` | [RM-011](#rm-RM-011) |
| CAST_LOGIQUE | 18 | `IF(V Lien Compte Seminaire [BK]='O' OR v.Garantie [T]='O','TRUE'LOG,'FALSE'LOG)` | [RM-007](#rm-RM-007) |
| CAST_LOGIQUE | 47 | `GetParam ('RENTAL')='TRUE'LOG` | - |
| CAST_LOGIQUE | 82 | `'FALSE'LOG` | - |
| CAST_LOGIQUE | 44 | `INIPut('AllowUpdateInQuery=Y','FALSE'LOG)` | - |
| ... | | *+2 autres* | |

#### CONDITION (35 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 39 | `IF(NOT(VG18),[CD],[CC])` | [RM-010](#rm-RM-010) |
| CONDITION | 76 | `IF([CT],'Booking',IF(Trim(VG59)<>'',VG59,'Sale'))` | [RM-012](#rm-RM-012) |
| CONDITION | 19 | `IF(VG87,V Lien Compte Seminaire [BK]='O' OR v.Garantie [T]='O',V Lien Compte Seminaire [BK]='O') OR Trim(V.EtatCompte [BS])='TESTPES'` | [RM-008](#rm-RM-008) |
| CONDITION | 20 | `IF(VG17<>[AN] OR v.Update Tab Filiation [C],Trim (Str ([AM],'3')),v.Tab_Filation1 [A])` | [RM-009](#rm-RM-009) |
| CONDITION | 100 | `IF(Trim(V.EtatCompte [BS])='TESTPES',Translate('%club_images%garantie_annulee.bmp'),IF(Trim(Btn.ExtraitCompte [BP])='CLUB' AND V.dateSolde [BT]='R',Translate('%club_images%garantie_club.bmp'),Translate('%club_images%garantie.bmp')))` | [RM-015](#rm-RM-015) |
| ... | | *+30 autres* | |

#### CONSTANTE (8 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 91 | `''` | - |
| CONSTANTE | 83 | `'P'` | - |
| CONSTANTE | 102 | `'SB_List Sales'` | - |
| CONSTANTE | 96 | `'PVE'` | - |
| CONSTANTE | 13 | `0` | - |
| ... | | *+3 autres* | |

#### OTHER (37 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 71 | `[AG]` | - |
| OTHER | 70 | `V Club Med Pass [R]` | - |
| OTHER | 73 | `v.RoomNumber [N]` | - |
| OTHER | 72 | `[AH]` | - |
| OTHER | 69 | `V pms filiation from card [Q]` | - |
| ... | | *+32 autres* | |

#### REFERENCE_VG (16 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 58 | `VG55` | - |
| REFERENCE_VG | 59 | `VG56` | - |
| REFERENCE_VG | 56 | `VG53` | - |
| REFERENCE_VG | 57 | `VG54` | - |
| REFERENCE_VG | 92 | `VG92` | - |
| ... | | *+11 autres* | |

#### STRING (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| STRING | 112 | `Trim(v.Deb_Sejour [BG])` | - |
| STRING | 90 | `Val(Right(VG89,2),'2P0')` | - |
| STRING | 89 | `Val(Left(VG89,2),'2P0')` | - |

#### CONCATENATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 113 | `Trim([CO])&IF(VG145 AND [DN]='O',' NGM','')` | - |

### 12.3 Toutes les expressions (115)

<details>
<summary>Voir les 115 expressions</summary>

#### CALCULATION (8)

| IDE | Expression Decodee |
|-----|-------------------|
| 9 | `CallProg ('{305,-1}'PROG,[AK],[AL])` |
| 30 | `'USER LOGON - '&Trim(VG39)` |
| 31 | `'SELECT CUSTOMER - '&Trim(v.Titre Bt Customer [V])` |
| 35 | `CallProg ('{295,-1}'PROG,[AK],[AL],[AM])` |
| 36 | `CallProg ('{305,-1}'PROG,[AK],[AL])` |
| 38 | `Left (Trim (v.Masque [D]),Len (Trim (v.Masque [D]))-1)` |
| 85 | `'BEST OF -  '&GetParam('LIBELBESTOF')` |
| 88 | `'BEST OF -  '&GetParam('LIBELBESTOF')` |

#### CAST_LOGIQUE (7)

| IDE | Expression Decodee |
|-----|-------------------|
| 40 | `'Version = '& Trim(VG3)& '  -  Mobilité = '&IF(VG32='TRUE'LOG,'Vrai','Faux')&'  --- Support = '&Trim(VG33)& '===> Voulez-vous changer ?'` |
| 18 | `IF(V Lien Compte Seminaire [BK]='O' OR v.Garantie [T]='O','TRUE'LOG,'FALSE'LOG)` |
| 45 | `IF(GetParam ('RENTAL')='TRUE'LOG,'Insurance','')` |
| 1 | `'TRUE'LOG` |
| 44 | `INIPut('AllowUpdateInQuery=Y','FALSE'LOG)` |
| 47 | `GetParam ('RENTAL')='TRUE'LOG` |
| 82 | `'FALSE'LOG` |

#### CONDITION (35)

| IDE | Expression Decodee |
|-----|-------------------|
| 108 | `'Quality'&IF(Trim(v.Deb_Sejour [BG])<>'' AND VG127,' / Sem','')` |
| 109 | `'Fidelity'&IF(Trim(v.Deb_Sejour [BG])<>'' AND VG127,' / Sem','')` |
| 111 | `Trim(v.Deb_Sejour [BG])<>'' AND Trim([AI])='GM-SEM' AND VG140` |
| 2 | `IF(Date()>[AH] OR Date()<[AG],43,6)` |
| 3 | `IF(Trim(VG33)='WS','TB',IF(Trim(VG33)='TB','WS',VG33))` |
| 8 | `IF(NOT VG41,2,3)` |
| 12 | `IF(v.LequipementID [S]='','Sale','Equipment')` |
| 16 | `IF([CE]='V','VIP',IF([CE]='T','TOP VIP',''))` |
| 17 | `IF(Trim(v.Libelle VIP [Y])<>'',Trim(v.Libelle VIP [Y]),Trim([DO]))` |
| 19 | `IF(VG87,V Lien Compte Seminaire [BK]='O' OR v.Garantie [T]='O',V Lien Compte Seminaire [BK]='O') OR Trim(V.EtatCompte [BS])='TESTPES'` |
| 20 | `IF(VG17<>[AN] OR v.Update Tab Filiation [C],Trim (Str ([AM],'3')),v.Tab_Filation1 [A])` |
| 39 | `IF(NOT(VG18),[CD],[CC])` |
| 76 | `IF([CT],'Booking',IF(Trim(VG59)<>'',VG59,'Sale'))` |
| 84 | `IF(VG89='',247.5,123.7)` |
| 87 | `IF(VG89='',200.625,100)` |
| 98 | `IF(VG43<>0,'N11.'&Trim(Str(VG43,'#'))&'CZ','N13CZ')` |
| 100 | `IF(Trim(V.EtatCompte [BS])='TESTPES',Translate('%club_images%garantie_annulee.bmp'),IF(Trim(Btn.ExtraitCompte [BP])='CLUB' AND V.dateSolde [BT]='R',Translate('%club_images%garantie_club.bmp'),Translate('%club_images%garantie.bmp')))` |
| 107 | `IF(ExpCalc('106'EXP),'Garantie Annulée : '&Trim([BX]),'')` |
| 110 | `IF(VG127 OR VG140,v.Deb_Sejour [BG],'')` |
| 6 | `VG17<>0` |
| 7 | `[AE]=6` |
| 14 | `v.Insurance [BM]='R'` |
| 15 | `[CG]='O'` |
| 32 | `GetParam ('SERVICELIB')<>''` |
| 34 | `[AN]<>0` |
| 41 | `[CR]>0` |
| 75 | `[AN]<>0` |
| 86 | `VG89<>''` |
| 94 | `VG92 AND VG89<>''` |
| 95 | `[AN]<>0 AND (NOT(VG92) OR (VG92 AND NOT([DA])))` |
| 99 | `VG93 AND [AL] <> 0` |
| 101 | `[AN]=0` |
| 106 | `V.SoldeCompte [BR]='X' AND V.EtatCompte [BS]='TESTPES'` |
| 33 | `Trim(VG38)<>''` |
| 93 | `VG92 AND [CZ] AND ([AR]<>0 AND [AR]<Val([CV],'2'))` |

#### CONSTANTE (8)

| IDE | Expression Decodee |
|-----|-------------------|
| 5 | `'R'` |
| 13 | `0` |
| 77 | `'SB_List Sales'` |
| 78 | `'Sale'` |
| 83 | `'P'` |
| 91 | `''` |
| 96 | `'PVE'` |
| 102 | `'SB_List Sales'` |

#### OTHER (37)

| IDE | Expression Decodee |
|-----|-------------------|
| 4 | `[AJ]` |
| 10 | `v.Libelle Fidelisation [BL]` |
| 11 | `V Lien Compte Seminaire [BK]` |
| 21 | `[CD]` |
| 22 | `[AK]` |
| 24 | `[AL]` |
| 25 | `[AM]` |
| 26 | `v.Societe [H]` |
| 27 | `v.Compte [I]` |
| 28 | `v..Filation [J]` |
| 29 | `v.Customer_ID [K]` |
| 37 | `GetParam ('AMOUNTFORMAT')` |
| 42 | `[AN]` |
| 43 | `GetParam('SERVICE')` |
| 46 | `Assurance_SKI([AL],[AM])` |
| 48 | `GetParam ('RENTAL') AND VG114` |
| 62 | `v.Titre Bt Customer [V]` |
| 63 | `v.Customer_ID [K]` |
| 64 | `v.Societe [H]` |
| 65 | `v.Compte [I]` |
| 66 | `v..Filation [J]` |
| 67 | `V PoS payer id from card [O]` |
| 68 | `V pms account from card [P]` |
| 69 | `V pms filiation from card [Q]` |
| 70 | `V Club Med Pass [R]` |
| 71 | `[AG]` |
| 72 | `[AH]` |
| 73 | `v.RoomNumber [N]` |
| 74 | `[AI]` |
| 79 | `NOT([CT])` |
| 80 | `[AG]` |
| 81 | `[AH]` |
| 103 | `v.Societe [H]` |
| 104 | `v.Compte [I]` |
| 105 | `v..Filation [J]` |
| 114 | `V Garantie (O/N) [BC]` |
| 115 | `MID([AI],4,4)` |

#### REFERENCE_VG (16)

| IDE | Expression Decodee |
|-----|-------------------|
| 23 | `VG19` |
| 49 | `VG46` |
| 50 | `VG47` |
| 51 | `VG48` |
| 52 | `VG49` |
| 53 | `VG50` |
| 54 | `VG51` |
| 55 | `VG52` |
| 56 | `VG53` |
| 57 | `VG54` |
| 58 | `VG55` |
| 59 | `VG56` |
| 60 | `VG57` |
| 61 | `VG58` |
| 92 | `VG92` |
| 97 | `VG23` |

#### STRING (3)

| IDE | Expression Decodee |
|-----|-------------------|
| 89 | `Val(Left(VG89,2),'2P0')` |
| 90 | `Val(Right(VG89,2),'2P0')` |
| 112 | `Trim(v.Deb_Sejour [BG])` |

#### CONCATENATION (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 113 | `Trim([CO])&IF(VG145 AND [DN]='O',' NGM','')` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Menu (IDE 185)](PVE-IDE-185.md) -> **Main Sale Sale Bar Code (IDE 214)**

```mermaid
graph LR
    T214[214 Main Sale Sale Bar...]
    style T214 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC143[143 START]
    style CC143 fill:#f59e0b
    CC185[185 Menu]
    style CC185 fill:#3fb950
    CC143 --> CC185
    CC1 --> CC143
    CC185 --> T214
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [185](PVE-IDE-185.md) | Menu | 2 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T214[214 Main Sale Sale Bar...]
    style T214 fill:#58a6ff
    C93[93 Update INV equipmen...]
    T214 --> C93
    style C93 fill:#3fb950
    C317[317 Lancement clavier]
    T214 --> C317
    style C317 fill:#3fb950
    C196[196 Package= account]
    T214 --> C196
    style C196 fill:#3fb950
    C200[200 Saisie commentaire]
    T214 --> C200
    style C200 fill:#3fb950
    C176[176 FindAppointments]
    T214 --> C176
    style C176 fill:#3fb950
    C183[183 Menu Check IN Exch...]
    T214 --> C183
    style C183 fill:#3fb950
    C207[207 Edition Recap Rend...]
    T214 --> C207
    style C207 fill:#3fb950
    C342[342 Choix - Equipements]
    T214 --> C342
    style C342 fill:#3fb950
    C161[161 GetAppointment]
    T214 --> C161
    style C161 fill:#3fb950
    C189[189 Generate Preview P...]
    T214 --> C189
    style C189 fill:#3fb950
    C194[194 Delete Product]
    T214 --> C194
    style C194 fill:#3fb950
    C201[201 Discounts]
    T214 --> C201
    style C201 fill:#3fb950
    C320[320 SynchronisationRec...]
    T214 --> C320
    style C320 fill:#3fb950
    C324[324 Question ME]
    T214 --> C324
    style C324 fill:#3fb950
    C95[95 Calcul - binding se...]
    T214 --> C95
    style C95 fill:#3fb950
    C96[96 Print Equipment SELECT]
    T214 --> C96
    style C96 fill:#3fb950
    C153[153 SearchBooking]
    T214 --> C153
    style C153 fill:#3fb950
    C157[157 FindRooms]
    T214 --> C157
    style C157 fill:#3fb950
    C158[158 FindEmployees]
    T214 --> C158
    style C158 fill:#3fb950
    C165[165 ControleBookingId]
    T214 --> C165
    style C165 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [93](PVE-IDE-93.md) | Update INV equipment status | 6 | Mise a jour donnees |
| [317](PVE-IDE-317.md) | Lancement clavier | 6 | Sous-programme |
| [196](PVE-IDE-196.md) |       Package=> account | 5 | Sous-programme |
| [200](PVE-IDE-200.md) | Saisie commentaire | 5 | Sous-programme |
| [176](PVE-IDE-176.md) | FindAppointments | 4 | Sous-programme |
| [183](PVE-IDE-183.md) | Menu Check IN / Exchange | 4 | Navigation menu |
| [207](PVE-IDE-207.md) | Edition Recap Rendez-vous | 4 | Impression ticket/document |
| [342](PVE-IDE-342.md) | Choix - Equipements | 4 | Selection/consultation |
| [161](PVE-IDE-161.md) | GetAppointment | 3 | Recuperation donnees |
| [189](PVE-IDE-189.md) | Generate Preview Payments | 2 | Sous-programme |
| [194](PVE-IDE-194.md) | Delete Product | 2 | Sous-programme |
| [201](PVE-IDE-201.md) | Discounts | 2 | Sous-programme |
| [320](PVE-IDE-320.md) | SynchronisationRecuPDF | 2 | Recuperation donnees |
| [324](PVE-IDE-324.md) | Question M&E | 2 | Sous-programme |
| [95](PVE-IDE-95.md) | Calcul - binding setting | 1 | Calcul de donnees |
| [96](PVE-IDE-96.md) | Print Equipment SELECT | 1 | Impression ticket/document |
| [153](PVE-IDE-153.md) | SearchBooking | 1 | Sous-programme |
| [157](PVE-IDE-157.md) | FindRooms | 1 | Sous-programme |
| [158](PVE-IDE-158.md) | FindEmployees | 1 | Sous-programme |
| [165](PVE-IDE-165.md) | ControleBookingId | 1 | Controle/validation |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 3076 | Programme volumineux |
| Expressions | 115 | Logique moderee |
| Tables WRITE | 10 | Fort impact donnees |
| Sous-programmes | 20 | Forte dependance |
| Ecrans visibles | 26 | Interface complexe multi-ecrans |
| Code desactive | 1.4% (43 / 3076) | Code sain |
| Regles metier | 17 | Logique metier riche |

### 14.2 Plan de migration par bloc

#### Traitement (44 taches: 30 ecrans, 14 traitements)

- **Strategie** : Orchestrateur avec 30 ecrans (Razor/React) et 14 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 20 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Consultation (5 taches: 3 ecrans, 2 traitements)

- **Strategie** : Composants de recherche/selection en modales.
- 3 ecrans : Choix Onglet, Select Appointments, Select Appointments

#### Creation (7 taches: 2 ecrans, 5 traitements)

- **Strategie** : Repository pattern avec Entity Framework Core.
- Insertion via `IRepository<T>.CreateAsync()`

#### Initialisation (2 taches: 0 ecran, 2 traitements)

- **Strategie** : Constructeur/methode `InitAsync()` dans l'orchestrateur.

#### Saisie (3 taches: 3 ecrans, 0 traitement)

- **Strategie** : Formulaire React/Blazor avec validation Zod/FluentValidation.
- Reproduire 3 ecrans : Saisie comment annulation, Saisie comment annulation, Saisie comment annulation
- Validation temps reel cote client + serveur

#### Validation (2 taches: 1 ecran, 1 traitement)

- **Strategie** : FluentValidation avec validators specifiques.
- Chaque tache de validation -> un validator injectable

#### Calcul (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Services de calcul purs (Domain Services).
- Migrer la logique de calcul (stock, compteurs, montants)

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| pv_customer | Table WRITE (Database) | 2x | Schema + repository |
| pv_customer_temp | Table WRITE (Database) | 1x | Schema + repository |
| pv_discount_reasons | Table WRITE (Database) | 1x | Schema + repository |
| pv_cust_rentals | Table WRITE (Database) | 1x | Schema + repository |
| pv_sellers_by_week | Table WRITE (Database) | 4x | Schema + repository |
| pv_tva | Table WRITE (Database) | 1x | Schema + repository |
| Table_1501 | Table WRITE (Memory) | 1x | Schema + repository |
| Table_1539 | Table WRITE (Memory) | 2x | Schema + repository |
| Table_1548 | Table WRITE (Memory) | 3x | Schema + repository |
| Table_1550 | Table WRITE (Memory) | 1x | Schema + repository |
| [Lancement clavier (IDE 317)](PVE-IDE-317.md) | Sous-programme | 6x | **CRITIQUE** - Sous-programme |
| [Update INV equipment status (IDE 93)](PVE-IDE-93.md) | Sous-programme | 6x | **CRITIQUE** - Mise a jour donnees |
| [Saisie commentaire (IDE 200)](PVE-IDE-200.md) | Sous-programme | 5x | **CRITIQUE** - Sous-programme |
| [      Package=> account (IDE 196)](PVE-IDE-196.md) | Sous-programme | 5x | **CRITIQUE** - Sous-programme |
| [Edition Recap Rendez-vous (IDE 207)](PVE-IDE-207.md) | Sous-programme | 4x | **CRITIQUE** - Impression ticket/document |
| [Choix - Equipements (IDE 342)](PVE-IDE-342.md) | Sous-programme | 4x | **CRITIQUE** - Selection/consultation |
| [FindAppointments (IDE 176)](PVE-IDE-176.md) | Sous-programme | 4x | **CRITIQUE** - Sous-programme |
| [Menu Check IN / Exchange (IDE 183)](PVE-IDE-183.md) | Sous-programme | 4x | **CRITIQUE** - Navigation menu |
| [GetAppointment (IDE 161)](PVE-IDE-161.md) | Sous-programme | 3x | **CRITIQUE** - Recuperation donnees |
| [SynchronisationRecuPDF (IDE 320)](PVE-IDE-320.md) | Sous-programme | 2x | Haute - Recuperation donnees |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 18:57*
