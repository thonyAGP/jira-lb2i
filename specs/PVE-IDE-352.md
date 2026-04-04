# PVE IDE 352 - Main Sale ===V4 bck

> **Analyse**: Phases 1-4 2026-02-03 19:43 -> 19:43 (11s) | Assemblage 19:43
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PVE |
| IDE Position | 352 |
| Nom Programme | Main Sale ===V4 bck |
| Fichier source | `Prg_352.xml` |
| Dossier IDE | Sauvegarde |
| Taches | 28 (15 ecrans visibles) |
| Tables modifiees | 2 |
| Programmes appeles | 20 |
| :warning: Statut | **ORPHELIN_POTENTIEL** |

## 2. DESCRIPTION FONCTIONNELLE

**Main Sale ===V4 bck** assure la gestion complete de ce processus.

Le flux de traitement s'organise en **6 blocs fonctionnels** :

- **Traitement** (21 taches) : traitements metier divers
- **Saisie** (3 taches) : ecrans de saisie utilisateur (formulaires, champs, donnees)
- **Calcul** (1 tache) : calculs de montants, stocks ou compteurs
- **Creation** (1 tache) : insertion d'enregistrements en base (mouvements, prestations)
- **Consultation** (1 tache) : ecrans de recherche, selection et consultation
- **Initialisation** (1 tache) : reinitialisation d'etats et de variables de travail

**Donnees modifiees** : 2 tables en ecriture (pv_customer, pv_sellers_by_week).

**Logique metier** : 9 regles identifiees couvrant conditions metier, valeurs par defaut.

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (21 taches)

- **352** - Main Sale ===V4 bck **[[ECRAN]](#ecran-t1)**
- **352.1.1** - Transac not PMS **[[ECRAN]](#ecran-t3)**
- **352.1.2** - equip **[[ECRAN]](#ecran-t4)**
- **352.1.2.1** - Equipment check out **[[ECRAN]](#ecran-t5)**
- **352.1.2.1.1** - clear
- **352.1.2.2** - Equipment list **[[ECRAN]](#ecran-t7)**
- **352.1.2.2.1** - Equipment check out **[[ECRAN]](#ecran-t8)**
- **352.1.2.2.2** - Equipment list **[[ECRAN]](#ecran-t9)**
- **352.1.2.2.2.1** - Equipment check IN **[[ECRAN]](#ecran-t10)**
- **352.1.3** - Sales and Payment **[[ECRAN]](#ecran-t11)**
- **352.1.3.1** - Payment **[[ECRAN]](#ecran-t12)**
- **352.1.3.1.2** - View
- **352.1.3.2** - Discount **[[ECRAN]](#ecran-t16)**
- **352.1.3.3** - Test Prepaid
- **352.1.3.4** - Special actions **[[ECRAN]](#ecran-t19)**
- **352.1.3.5** - Check Rentals
- **352.1.3.6** - Check Payments **[[ECRAN]](#ecran-t22)**
- **352.1.3.7** - Check Comment Refus. To Sell **[[ECRAN]](#ecran-t23)**
- **352.1.3.8** - Discount **[[ECRAN]](#ecran-t24)**
- **352.1.4** - Transac not PMS MBO **[[ECRAN]](#ecran-t26)**
- **352.1.4.1** - SQL Total payement **[[ECRAN]](#ecran-t27)**

Delegue a : [Update INV equipment status (IDE 93)](PVE-IDE-93.md), [Menu Check IN / Exchange (IDE 410)](PVE-IDE-410.md), [Generate Preview OD==LEX (IDE 424)](PVE-IDE-424.md), [Discounts (IDE 443)](PVE-IDE-443.md), [Browse - pv_cust_package (IDE 447)](PVE-IDE-447.md), [Affiliations Customer (IDE 191)](PVE-IDE-191.md), [Delete Product (IDE 194)](PVE-IDE-194.md), [      Package=> account (IDE 196)](PVE-IDE-196.md), [Packages sales online (IDE 216)](PVE-IDE-216.md), [    Package pricing (IDE 218)](PVE-IDE-218.md), [Search for Credit / Gift Pass (IDE 231)](PVE-IDE-231.md), [Search Resolution by Computer (IDE 312)](PVE-IDE-312.md)

#### Phase 2 : Consultation (1 tache)

- **352.1** - Choix Onglet **[[ECRAN]](#ecran-t2)**

Delegue a : [Seller - selection (IDE 190)](PVE-IDE-190.md), [Select Product (IDE 192)](PVE-IDE-192.md), [Credit card - select (IDE 224)](PVE-IDE-224.md), [Payments - select (IDE 225)](PVE-IDE-225.md)

#### Phase 3 : Initialisation (1 tache)

- **352.1.3.1.1** - init payer

#### Phase 4 : Creation (1 tache)

- **352.1.3.1.3** - create cardType

#### Phase 5 : Saisie (3 taches)

- **352.1.3.2.1** - Saisie comment annulation **[[ECRAN]](#ecran-t17)**
- **352.1.3.4.1** - Saisie comment annulation **[[ECRAN]](#ecran-t20)**
- **352.1.3.8.1** - Saisie comment annulation **[[ECRAN]](#ecran-t25)**

Delegue a : [Saisie commentaire (IDE 200)](PVE-IDE-200.md)

#### Phase 6 : Calcul (1 tache)

- **352.2** - calcul filiation

Delegue a : [Browse - pv_comptab (IDE 446)](PVE-IDE-446.md), [Calcul - binding setting (IDE 95)](PVE-IDE-95.md), [Search for Credit / Gift Pass (IDE 231)](PVE-IDE-231.md)

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| pv_sellers_by_week | **W**/L (5 usages) |  |
| pv_customer | **W** (1 usages) |  |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (21 taches)

Traitements internes.

---

#### <a id="t1"></a>352 - Main Sale ===V4 bck [[ECRAN]](#ecran-t1)

**Role** : Tache d'orchestration : point d'entree du programme (21 sous-taches). Coordonne l'enchainement des traitements.
**Ecran** : 1990 x 392 DLU (Modal) | [Voir mockup](#ecran-t1)

<details>
<summary>20 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [352.1.1](#t3) | Transac not PMS **[[ECRAN]](#ecran-t3)** | Traitement |
| [352.1.2](#t4) | equip **[[ECRAN]](#ecran-t4)** | Traitement |
| [352.1.2.1](#t5) | Equipment check out **[[ECRAN]](#ecran-t5)** | Traitement |
| [352.1.2.1.1](#t6) | clear | Traitement |
| [352.1.2.2](#t7) | Equipment list **[[ECRAN]](#ecran-t7)** | Traitement |
| [352.1.2.2.1](#t8) | Equipment check out **[[ECRAN]](#ecran-t8)** | Traitement |
| [352.1.2.2.2](#t9) | Equipment list **[[ECRAN]](#ecran-t9)** | Traitement |
| [352.1.2.2.2.1](#t10) | Equipment check IN **[[ECRAN]](#ecran-t10)** | Traitement |
| [352.1.3](#t11) | Sales and Payment **[[ECRAN]](#ecran-t11)** | Traitement |
| [352.1.3.1](#t12) | Payment **[[ECRAN]](#ecran-t12)** | Traitement |
| [352.1.3.1.2](#t14) | View | Traitement |
| [352.1.3.2](#t16) | Discount **[[ECRAN]](#ecran-t16)** | Traitement |
| [352.1.3.3](#t18) | Test Prepaid | Traitement |
| [352.1.3.4](#t19) | Special actions **[[ECRAN]](#ecran-t19)** | Traitement |
| [352.1.3.5](#t21) | Check Rentals | Traitement |
| [352.1.3.6](#t22) | Check Payments **[[ECRAN]](#ecran-t22)** | Traitement |
| [352.1.3.7](#t23) | Check Comment Refus. To Sell **[[ECRAN]](#ecran-t23)** | Traitement |
| [352.1.3.8](#t24) | Discount **[[ECRAN]](#ecran-t24)** | Traitement |
| [352.1.4](#t26) | Transac not PMS MBO **[[ECRAN]](#ecran-t26)** | Traitement |
| [352.1.4.1](#t27) | SQL Total payement **[[ECRAN]](#ecran-t27)** | Traitement |

</details>

---

#### <a id="t3"></a>352.1.1 - Transac not PMS [[ECRAN]](#ecran-t3)

**Role** : Traitement : Transac not PMS.
**Ecran** : 973 x 248 DLU (Modal) | [Voir mockup](#ecran-t3)

---

#### <a id="t4"></a>352.1.2 - equip [[ECRAN]](#ecran-t4)

**Role** : Traitement : equip.
**Ecran** : 971 x 229 DLU (Modal) | [Voir mockup](#ecran-t4)
**Variables liees** : B (v.LequipmentId), T (v.LequipementID)

---

#### <a id="t5"></a>352.1.2.1 - Equipment check out [[ECRAN]](#ecran-t5)

**Role** : Traitement : Equipment check out.
**Ecran** : 320 x 254 DLU (MDI) | [Voir mockup](#ecran-t5)
**Variables liees** : B (v.LequipmentId)

---

#### <a id="t6"></a>352.1.2.1.1 - clear

**Role** : Traitement : clear.

---

#### <a id="t7"></a>352.1.2.2 - Equipment list [[ECRAN]](#ecran-t7)

**Role** : Traitement : Equipment list.
**Ecran** : 188 x 280 DLU (MDI) | [Voir mockup](#ecran-t7)
**Variables liees** : B (v.LequipmentId), M (v.Filiation_List)

---

#### <a id="t8"></a>352.1.2.2.1 - Equipment check out [[ECRAN]](#ecran-t8)

**Role** : Traitement : Equipment check out.
**Ecran** : 322 x 282 DLU (MDI) | [Voir mockup](#ecran-t8)
**Variables liees** : B (v.LequipmentId)

---

#### <a id="t9"></a>352.1.2.2.2 - Equipment list [[ECRAN]](#ecran-t9)

**Role** : Traitement : Equipment list.
**Ecran** : 190 x 280 DLU (MDI) | [Voir mockup](#ecran-t9)
**Variables liees** : B (v.LequipmentId), M (v.Filiation_List)

---

#### <a id="t10"></a>352.1.2.2.2.1 - Equipment check IN [[ECRAN]](#ecran-t10)

**Role** : Traitement : Equipment check IN.
**Ecran** : 642 x 281 DLU (Type6) | [Voir mockup](#ecran-t10)
**Variables liees** : B (v.LequipmentId)

---

#### <a id="t11"></a>352.1.3 - Sales and Payment [[ECRAN]](#ecran-t11)

**Role** : Traitement : Sales and Payment.
**Ecran** : 979 x 238 DLU (Modal) | [Voir mockup](#ecran-t11)
**Variables liees** : BA (v.All.Payment ?)

---

#### <a id="t12"></a>352.1.3.1 - Payment [[ECRAN]](#ecran-t12)

**Role** : Traitement : Payment.
**Ecran** : 238 x 63 DLU (MDI) | [Voir mockup](#ecran-t12)
**Variables liees** : BA (v.All.Payment ?)

---

#### <a id="t14"></a>352.1.3.1.2 - View

**Role** : Traitement : View.

---

#### <a id="t16"></a>352.1.3.2 - Discount [[ECRAN]](#ecran-t16)

**Role** : Traitement : Discount.
**Ecran** : 220 x 94 DLU (MDI) | [Voir mockup](#ecran-t16)
**Variables liees** : BB (v.L.Test Discount ?)

---

#### <a id="t18"></a>352.1.3.3 - Test Prepaid

**Role** : Verification : Test Prepaid.
**Variables liees** : BB (v.L.Test Discount ?)

---

#### <a id="t19"></a>352.1.3.4 - Special actions [[ECRAN]](#ecran-t19)

**Role** : Traitement : Special actions.
**Ecran** : 312 x 259 DLU (Type6) | [Voir mockup](#ecran-t19)

---

#### <a id="t21"></a>352.1.3.5 - Check Rentals

**Role** : Traitement : Check Rentals.

---

#### <a id="t22"></a>352.1.3.6 - Check Payments [[ECRAN]](#ecran-t22)

**Role** : Traitement : Check Payments.
**Ecran** : 926 x 449 DLU (MDI) | [Voir mockup](#ecran-t22)

---

#### <a id="t23"></a>352.1.3.7 - Check Comment Refus. To Sell [[ECRAN]](#ecran-t23)

**Role** : Traitement : Check Comment Refus. To Sell.
**Ecran** : 522 x 498 DLU | [Voir mockup](#ecran-t23)

---

#### <a id="t24"></a>352.1.3.8 - Discount [[ECRAN]](#ecran-t24)

**Role** : Traitement : Discount.
**Ecran** : 854 x 202 DLU (MDI) | [Voir mockup](#ecran-t24)
**Variables liees** : BB (v.L.Test Discount ?)

---

#### <a id="t26"></a>352.1.4 - Transac not PMS MBO [[ECRAN]](#ecran-t26)

**Role** : Traitement : Transac not PMS MBO.
**Ecran** : 695 x 143 DLU (MDI) | [Voir mockup](#ecran-t26)

---

#### <a id="t27"></a>352.1.4.1 - SQL Total payement [[ECRAN]](#ecran-t27)

**Role** : Traitement : SQL Total payement.
**Ecran** : 115 x 195 DLU | [Voir mockup](#ecran-t27)


### 3.2 Consultation (1 tache)

Ecrans de recherche et consultation.

---

#### <a id="t2"></a>352.1 - Choix Onglet [[ECRAN]](#ecran-t2)

**Role** : Selection par l'operateur : Choix Onglet.
**Ecran** : 986 x 264 DLU (MDI) | [Voir mockup](#ecran-t2)
**Delegue a** : [Seller - selection (IDE 190)](PVE-IDE-190.md), [Select Product (IDE 192)](PVE-IDE-192.md), [Credit card - select (IDE 224)](PVE-IDE-224.md)


### 3.3 Initialisation (1 tache)

Reinitialisation d'etats et variables de travail.

---

#### <a id="t13"></a>352.1.3.1.1 - init payer

**Role** : Reinitialisation : init payer.
**Variables liees** : P (V PoS payer id from card)


### 3.4 Creation (1 tache)

Insertion de nouveaux enregistrements en base.

---

#### <a id="t15"></a>352.1.3.1.3 - create cardType

**Role** : Traitement : create cardType.


### 3.5 Saisie (3 taches)

L'operateur saisit les donnees de la transaction via 3 ecrans (Saisie comment annulation, Saisie comment annulation, Saisie comment annulation).

---

#### <a id="t17"></a>352.1.3.2.1 - Saisie comment annulation [[ECRAN]](#ecran-t17)

**Role** : Saisie des donnees : Saisie comment annulation.
**Ecran** : 318 x 135 DLU | [Voir mockup](#ecran-t17)
**Delegue a** : [Saisie commentaire (IDE 200)](PVE-IDE-200.md)

---

#### <a id="t20"></a>352.1.3.4.1 - Saisie comment annulation [[ECRAN]](#ecran-t20)

**Role** : Saisie des donnees : Saisie comment annulation.
**Ecran** : 322 x 136 DLU (Type6) | [Voir mockup](#ecran-t20)
**Delegue a** : [Saisie commentaire (IDE 200)](PVE-IDE-200.md)

---

#### <a id="t25"></a>352.1.3.8.1 - Saisie comment annulation [[ECRAN]](#ecran-t25)

**Role** : Saisie des donnees : Saisie comment annulation.
**Ecran** : 318 x 135 DLU | [Voir mockup](#ecran-t25)
**Delegue a** : [Saisie commentaire (IDE 200)](PVE-IDE-200.md)


### 3.6 Calcul (1 tache)

Calculs metier : montants, stocks, compteurs.

---

#### <a id="t28"></a>352.2 - calcul filiation

**Role** : Calcul : calcul filiation.
**Variables liees** : C (v.Update Tab Filiation), M (v.Filiation_List), R (V pms filiation from card)
**Delegue a** : [Browse - pv_comptab (IDE 446)](PVE-IDE-446.md), [Calcul - binding setting (IDE 95)](PVE-IDE-95.md)


## 5. REGLES METIER

9 regles identifiees:

### Autres (9 regles)

#### <a id="rm-RM-001"></a>[RM-001] Si Date()>[AI] OR Date()<[AH] alors 43 sinon 6)

| Element | Detail |
|---------|--------|
| **Condition** | `Date()>[AI] OR Date()<[AH]` |
| **Si vrai** | 43 |
| **Si faux** | 6) |
| **Expression source** | Expression 2 : `IF(Date()>[AI] OR Date()<[AH],43,6)` |
| **Exemple** | Si Date()>[AI] OR Date()<[AH] â†’ 43. Sinon â†’ 6) |

#### <a id="rm-RM-002"></a>[RM-002] Si Trim(VG33)='WS' alors 'TB' sinon IF(Trim(VG33)='TB','WS',VG33))

| Element | Detail |
|---------|--------|
| **Condition** | `Trim(VG33)='WS'` |
| **Si vrai** | 'TB' |
| **Si faux** | IF(Trim(VG33)='TB','WS',VG33)) |
| **Expression source** | Expression 3 : `IF(Trim(VG33)='WS','TB',IF(Trim(VG33)='TB','WS',VG33))` |
| **Exemple** | Si Trim(VG33)='WS' â†’ 'TB'. Sinon â†’ IF(Trim(VG33)='TB','WS',VG33)) |

#### <a id="rm-RM-003"></a>[RM-003] Valeur par defaut si v.LequipementID [T] est vide

| Element | Detail |
|---------|--------|
| **Condition** | `v.LequipementID [T]=''` |
| **Si vrai** | 'Sale' |
| **Si faux** | 'Equipment') |
| **Variables** | T (v.LequipementID) |
| **Expression source** | Expression 12 : `IF(v.LequipementID [T]='','Sale','Equipment')` |
| **Exemple** | Si v.LequipementID [T]='' â†’ 'Sale'. Sinon â†’ 'Equipment') |
| **Impact** | [352.1.2 - equip](#t4) |

#### <a id="rm-RM-004"></a>[RM-004] Si [BV]='V' alors 'VIP' sinon IF([BV]='T','TOP VIP',''))

| Element | Detail |
|---------|--------|
| **Condition** | `[BV]='V'` |
| **Si vrai** | 'VIP' |
| **Si faux** | IF([BV]='T','TOP VIP','')) |
| **Expression source** | Expression 16 : `IF([BV]='V','VIP',IF([BV]='T','TOP VIP',''))` |
| **Exemple** | Si [BV]='V' â†’ 'VIP'. Sinon â†’ IF([BV]='T','TOP VIP','')) |

#### <a id="rm-RM-005"></a>[RM-005] Traitement si Trim(v.Libelle VIP [Z]) est renseigne

| Element | Detail |
|---------|--------|
| **Condition** | `Trim(v.Libelle VIP [Z])<>''` |
| **Si vrai** | Trim(v.Libelle VIP [Z]) |
| **Si faux** | Trim([CF])) |
| **Variables** | Z (v.Libelle VIP) |
| **Expression source** | Expression 17 : `IF(Trim(v.Libelle VIP [Z])<>'',Trim(v.Libelle VIP [Z]),Trim(` |
| **Exemple** | Si Trim(v.Libelle VIP [Z])<>'' â†’ Trim(v.Libelle VIP [Z]). Sinon â†’ Trim([CF])) |

#### <a id="rm-RM-006"></a>[RM-006] Condition toujours vraie (flag actif)

| Element | Detail |
|---------|--------|
| **Condition** | `v.Qualite [BJ]='O' OR v.Garantie [U]='O'` |
| **Si vrai** | 'TRUE'LOG |
| **Si faux** | 'FALSE'LOG) |
| **Variables** | U (v.Garantie), BJ (v.Qualite) |
| **Expression source** | Expression 18 : `IF(v.Qualite [BJ]='O' OR v.Garantie [U]='O','TRUE'LOG,'FALSE` |
| **Exemple** | Si v.Qualite [BJ]='O' OR v.Garantie [U]='O' â†’ 'TRUE'LOG. Sinon â†’ 'FALSE'LOG) |

#### <a id="rm-RM-007"></a>[RM-007] Si VG17<>[AO] OR v.Update Tab Filiation [C] alors Trim (Str ([AN] sinon '3')),v.Tab_Filation1 [A])

| Element | Detail |
|---------|--------|
| **Condition** | `VG17<>[AO] OR v.Update Tab Filiation [C]` |
| **Si vrai** | Trim (Str ([AN] |
| **Si faux** | '3')),v.Tab_Filation1 [A]) |
| **Variables** | A (v.Tab_Filation1), C (v.Update Tab Filiation) |
| **Expression source** | Expression 19 : `IF(VG17<>[AO] OR v.Update Tab Filiation [C],Trim (Str ([AN],` |
| **Exemple** | Si VG17<>[AO] OR v.Update Tab Filiation [C] â†’ Trim (Str ([AN]. Sinon â†’ '3')),v.Tab_Filation1 [A]) |

#### <a id="rm-RM-008"></a>[RM-008] Si NOT(VG18) alors [BU] sinon [BT])

| Element | Detail |
|---------|--------|
| **Condition** | `NOT(VG18)` |
| **Si vrai** | [BU] |
| **Si faux** | [BT]) |
| **Expression source** | Expression 38 : `IF(NOT(VG18),[BU],[BT])` |
| **Exemple** | Si NOT(VG18) â†’ [BU]. Sinon â†’ [BT]) |

#### <a id="rm-RM-009"></a>[RM-009] Condition toujours vraie (flag actif)

| Element | Detail |
|---------|--------|
| **Condition** | `GetParam ('RENTAL')='TRUE'LOG` |
| **Si vrai** | 'Insurance' |
| **Si faux** | '') |
| **Expression source** | Expression 45 : `IF(GetParam ('RENTAL')='TRUE'LOG,'Insurance','')` |
| **Exemple** | Si GetParam ('RENTAL')='TRUE'LOG â†’ 'Insurance'. Sinon â†’ '') |

## 6. CONTEXTE

- **Appele par**: (aucun)
- **Appelle**: 20 programmes | **Tables**: 24 (W:2 R:6 L:21) | **Taches**: 28 | **Expressions**: 72

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (15 / 28)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 352 | 352 | Main Sale ===V4 bck | Modal | 1990 | 392 | Traitement |
| 2 | 352.1 | 352.1 | Choix Onglet | MDI | 986 | 264 | Consultation |
| 3 | 352.1.1 | 352.1.1 | Transac not PMS | Modal | 973 | 248 | Traitement |
| 4 | 352.1.2 | 352.1.2 | equip | Modal | 971 | 229 | Traitement |
| 5 | 352.1.2.1 | 352.1.2.1 | Equipment check out | MDI | 320 | 254 | Traitement |
| 6 | 352.1.2.2 | 352.1.2.2 | Equipment list | MDI | 188 | 280 | Traitement |
| 7 | 352.1.2.2.1 | 352.1.2.2.1 | Equipment check out | MDI | 322 | 282 | Traitement |
| 8 | 352.1.2.2.2 | 352.1.2.2.2 | Equipment list | MDI | 190 | 280 | Traitement |
| 9 | 352.1.2.2.2.1 | 352.1.2.2.2.1 | Equipment check IN | Type6 | 642 | 281 | Traitement |
| 10 | 352.1.3 | 352.1.3 | Sales and Payment | Modal | 979 | 238 | Traitement |
| 11 | 352.1.3.2.1 | 352.1.3.2.1 | Saisie comment annulation | Type0 | 318 | 135 | Saisie |
| 12 | 352.1.3.4 | 352.1.3.4 | Special actions | Type6 | 312 | 259 | Traitement |
| 13 | 352.1.3.4.1 | 352.1.3.4.1 | Saisie comment annulation | Type6 | 322 | 136 | Saisie |
| 14 | 352.1.3.8.1 | 352.1.3.8.1 | Saisie comment annulation | Type0 | 318 | 135 | Saisie |
| 15 | 352.1.4 | 352.1.4 | Transac not PMS MBO | MDI | 695 | 143 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>352 - Main Sale ===V4 bck
**Tache** : [352](#t1) | **Type** : Modal | **Dimensions** : 1990 x 392 DLU
**Bloc** : Traitement | **Titre IDE** : Main Sale ===V4 bck

<!-- FORM-DATA:
{
    "width":  1990,
    "vFactor":  8,
    "type":  "Modal",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  61,
                         "w":  1976,
                         "fmt":  "",
                         "name":  "",
                         "h":  33,
                         "color":  "6",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  328,
                         "type":  "label",
                         "var":  "",
                         "y":  62,
                         "w":  96,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "Sex",
                         "parent":  1
                     },
                     {
                         "x":  424,
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
                         "x":  528,
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
                         "x":  634,
                         "type":  "label",
                         "var":  "",
                         "y":  62,
                         "w":  108,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "Age",
                         "parent":  1
                     },
                     {
                         "x":  742,
                         "type":  "label",
                         "var":  "",
                         "y":  62,
                         "w":  218,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "Fidelity",
                         "parent":  1
                     },
                     {
                         "x":  962,
                         "type":  "label",
                         "var":  "",
                         "y":  62,
                         "w":  246,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  1208,
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
                         "x":  1350,
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
                         "x":  1494,
                         "type":  "label",
                         "var":  "",
                         "y":  62,
                         "w":  142,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "Quality",
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
                         "x":  328,
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
                         "x":  420,
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
                         "x":  524,
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
                         "x":  630,
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
                         "x":  740,
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
                         "x":  958,
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
                         "x":  1206,
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
                         "x":  1348,
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
                         "x":  1490,
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
                         "x":  1632,
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
                         "w":  182,
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
                         "x":  986,
                         "type":  "image",
                         "var":  "",
                         "y":  76,
                         "w":  34,
                         "fmt":  "",
                         "name":  "v Image Garantie",
                         "h":  12,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  370,
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
                         "x":  448,
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
                         "x":  538,
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
                         "x":  668,
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
                         "x":  758,
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
                         "x":  1038,
                         "type":  "image",
                         "var":  "",
                         "y":  77,
                         "w":  34,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  1086,
                         "type":  "image",
                         "var":  "",
                         "y":  77,
                         "w":  34,
                         "fmt":  "",
                         "name":  "v Image Garantie",
                         "h":  12,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  1214,
                         "type":  "edit",
                         "var":  "",
                         "y":  77,
                         "w":  131,
                         "fmt":  "WWW ##/##/####Z",
                         "name":  "gmr_debut_sejour",
                         "h":  11,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  1356,
                         "type":  "edit",
                         "var":  "",
                         "y":  77,
                         "w":  131,
                         "fmt":  "WWW ##/##/####Z",
                         "name":  "gmr_debut_sejour_0001",
                         "h":  11,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  1501,
                         "type":  "edit",
                         "var":  "",
                         "y":  77,
                         "w":  130,
                         "fmt":  "",
                         "name":  "v.Qualite_0001",
                         "h":  11,
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
                         "x":  2,
                         "type":  "subform",
                         "var":  "",
                         "y":  127,
                         "w":  1978,
                         "fmt":  "",
                         "name":  "SB_List Sales",
                         "h":  264,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "352",
    "height":  392
}
-->

<details>
<summary><strong>Champs : 9 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 140,63 | xcust_id | - | edit |
| 370,77 | gm_sexe | - | edit |
| 448,77 | cgm_qualite | - | edit |
| 538,77 | v.RoomNumber | - | edit |
| 668,77 | gm_age | - | edit |
| 758,77 | 30 | - | edit |
| 1214,77 | gmr_debut_sejour | - | edit |
| 1356,77 | gmr_debut_sejour_0001 | - | edit |
| 1501,77 | v.Qualite_0001 | - | edit |

</details>

<details>
<summary><strong>Boutons : 5 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| SELLER - | 2,1 | Appel [Seller - selection (IDE 190)](PVE-IDE-190.md) |
| CUSTOMER - | 2,31 | Appel [Affiliations Customer (IDE 191)](PVE-IDE-191.md) |
| $ | 1784,63 | Bouton fonctionnel |
| F | 1882,63 | Bouton fonctionnel |
| PRODUCT SELECTION | 0,96 | Appel [Select Product (IDE 192)](PVE-IDE-192.md) |

</details>

---

#### <a id="ecran-t2"></a>352.1 - Choix Onglet
**Tache** : [352.1](#t2) | **Type** : MDI | **Dimensions** : 986 x 264 DLU
**Bloc** : Consultation | **Titre IDE** : Choix Onglet

<!-- FORM-DATA:
{
    "width":  986,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  3,
                         "type":  "tab",
                         "var":  "",
                         "y":  1,
                         "w":  981,
                         "fmt":  "",
                         "name":  "Onglet",
                         "h":  263,
                         "color":  "",
                         "text":  "Sale,Equipment,Payments,Scan Equipment",
                         "parent":  null
                     },
                     {
                         "x":  3,
                         "type":  "subform",
                         "var":  "",
                         "y":  9,
                         "w":  978,
                         "fmt":  "",
                         "name":  "Sales and Payment",
                         "h":  256,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  5,
                         "type":  "subform",
                         "var":  "",
                         "y":  12,
                         "w":  968,
                         "fmt":  "",
                         "name":  "Equipment",
                         "h":  256,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  3,
                         "type":  "subform",
                         "var":  "",
                         "y":  17,
                         "w":  968,
                         "fmt":  "",
                         "name":  "Payment",
                         "h":  256,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  5,
                         "type":  "subform",
                         "var":  "",
                         "y":  16,
                         "w":  968,
                         "fmt":  "",
                         "name":  "Scan",
                         "h":  256,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     }
                 ],
    "taskId":  "352.1",
    "height":  264
}
-->

---

#### <a id="ecran-t3"></a>352.1.1 - Transac not PMS
**Tache** : [352.1.1](#t3) | **Type** : Modal | **Dimensions** : 973 x 248 DLU
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
                         "fmt":  "10",
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
    "taskId":  "352.1.1",
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

#### <a id="ecran-t4"></a>352.1.2 - equip
**Tache** : [352.1.2](#t4) | **Type** : Modal | **Dimensions** : 971 x 229 DLU
**Bloc** : Traitement | **Titre IDE** : equip

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
                         "text":  "In/Exchange",
                         "parent":  null
                     },
                     {
                         "x":  853,
                         "type":  "label",
                         "var":  "",
                         "y":  6,
                         "w":  46,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "189",
                         "text":  "Status",
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
                         "y":  17,
                         "w":  76,
                         "fmt":  "8",
                         "name":  "CHECK IN",
                         "h":  23,
                         "color":  "1",
                         "text":  "",
                         "parent":  30
                     }
                 ],
    "taskId":  "352.1.2",
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
| Check Out | 865,164 | Appel [Menu Check IN / Exchange (IDE 410)](PVE-IDE-410.md) |
| ò | 921,90 | Bouton fonctionnel |
| ñ | 921,18 | Bouton fonctionnel |
| 8 | 739,17 | Bouton fonctionnel |

</details>

---

#### <a id="ecran-t5"></a>352.1.2.1 - Equipment check out
**Tache** : [352.1.2.1](#t5) | **Type** : MDI | **Dimensions** : 320 x 254 DLU
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
    "taskId":  "352.1.2.1",
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

#### <a id="ecran-t7"></a>352.1.2.2 - Equipment list
**Tache** : [352.1.2.2](#t7) | **Type** : MDI | **Dimensions** : 188 x 280 DLU
**Bloc** : Traitement | **Titre IDE** : Equipment list

<!-- FORM-DATA:
{
    "width":  188,
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
                         "w":  167,
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
                                          "w":  167
                                      }
                                  ],
                         "rows":  1
                     },
                     {
                         "x":  161,
                         "type":  "label",
                         "var":  "",
                         "y":  78,
                         "w":  14,
                         "fmt":  "",
                         "name":  "",
                         "h":  26,
                         "color":  "145",
                         "text":  "ü",
                         "parent":  4
                     },
                     {
                         "x":  13,
                         "type":  "edit",
                         "var":  "",
                         "y":  78,
                         "w":  145,
                         "fmt":  "",
                         "name":  "",
                         "h":  25,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     }
                 ],
    "taskId":  "352.1.2.2",
    "height":  280
}
-->

<details>
<summary><strong>Champs : 1 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 13,78 | (sans nom) | - | edit |

</details>

---

#### <a id="ecran-t8"></a>352.1.2.2.1 - Equipment check out
**Tache** : [352.1.2.2.1](#t8) | **Type** : MDI | **Dimensions** : 322 x 282 DLU
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
    "taskId":  "352.1.2.2.1",
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

#### <a id="ecran-t9"></a>352.1.2.2.2 - Equipment list
**Tache** : [352.1.2.2.2](#t9) | **Type** : MDI | **Dimensions** : 190 x 280 DLU
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
                                          "w":  167
                                      }
                                  ],
                         "rows":  1
                     },
                     {
                         "x":  161,
                         "type":  "label",
                         "var":  "",
                         "y":  77,
                         "w":  14,
                         "fmt":  "",
                         "name":  "",
                         "h":  26,
                         "color":  "145",
                         "text":  "ü",
                         "parent":  4
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
                     }
                 ],
    "taskId":  "352.1.2.2.2",
    "height":  280
}
-->

<details>
<summary><strong>Champs : 2 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 13,77 | (sans nom) | - | edit |
| 13,91 | U15 | - | edit |

</details>

---

#### <a id="ecran-t10"></a>352.1.2.2.2.1 - Equipment check IN
**Tache** : [352.1.2.2.2.1](#t10) | **Type** : Type6 | **Dimensions** : 642 x 281 DLU
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
    "taskId":  "352.1.2.2.2.1",
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

#### <a id="ecran-t11"></a>352.1.3 - Sales and Payment
**Tache** : [352.1.3](#t11) | **Type** : Modal | **Dimensions** : 979 x 238 DLU
**Bloc** : Traitement | **Titre IDE** : Sales and Payment

<!-- FORM-DATA:
{
    "width":  979,
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
                         "fmt":  "",
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
                         "w":  48,
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
                         "w":  48,
                         "fmt":  "ò",
                         "name":  "DOWN",
                         "h":  76,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  3,
                         "type":  "button",
                         "var":  "",
                         "y":  154,
                         "w":  976,
                         "fmt":  "DISCOUNT",
                         "name":  "DISCOUNT ALL",
                         "h":  27,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  3,
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
                         "x":  492,
                         "type":  "button",
                         "var":  "",
                         "y":  182,
                         "w":  487,
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
                         "w":  976,
                         "fmt":  "RECEIPTS",
                         "name":  "RECEIPTS",
                         "h":  27,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "352.1.3",
    "height":  238
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
| DISCOUNT | 3,154 | Appel [Discounts (IDE 443)](PVE-IDE-443.md) |
| PAYMENT | 3,182 | Appel [Payments - select (IDE 225)](PVE-IDE-225.md) |
| PAYMENT - ALL FILIATIONS | 492,182 | Appel [Payments - select (IDE 225)](PVE-IDE-225.md) |
| RECEIPTS | 2,210 | Bouton fonctionnel |

</details>

---

#### <a id="ecran-t17"></a>352.1.3.2.1 - Saisie comment annulation
**Tache** : [352.1.3.2.1](#t17) | **Type** : Type0 | **Dimensions** : 318 x 135 DLU
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
    "taskId":  "352.1.3.2.1",
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

#### <a id="ecran-t19"></a>352.1.3.4 - Special actions
**Tache** : [352.1.3.4](#t19) | **Type** : Type6 | **Dimensions** : 312 x 259 DLU
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
    "taskId":  "352.1.3.4",
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
| EXCHANGE | 25,134 | Appel [Menu Check IN / Exchange (IDE 410)](PVE-IDE-410.md) |

</details>

---

#### <a id="ecran-t20"></a>352.1.3.4.1 - Saisie comment annulation
**Tache** : [352.1.3.4.1](#t20) | **Type** : Type6 | **Dimensions** : 322 x 136 DLU
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
    "taskId":  "352.1.3.4.1",
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

#### <a id="ecran-t25"></a>352.1.3.8.1 - Saisie comment annulation
**Tache** : [352.1.3.8.1](#t25) | **Type** : Type0 | **Dimensions** : 318 x 135 DLU
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
    "taskId":  "352.1.3.8.1",
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

#### <a id="ecran-t26"></a>352.1.4 - Transac not PMS MBO
**Tache** : [352.1.4](#t26) | **Type** : MDI | **Dimensions** : 695 x 143 DLU
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
                         "w":  37,
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
    "taskId":  "352.1.4",
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

## 9. NAVIGATION

### 9.1 Enchainement des ecrans

```mermaid
flowchart TD
    START([Entree])
    style START fill:#3fb950
    VF1[352 Main Sale ===V4 bck]
    style VF1 fill:#58a6ff
    VF2[352.1 Choix Onglet]
    style VF2 fill:#58a6ff
    VF3[352.1.1 Transac not PMS]
    style VF3 fill:#58a6ff
    VF4[352.1.2 equip]
    style VF4 fill:#58a6ff
    VF5[352.1.2.1 Equipment check out]
    style VF5 fill:#58a6ff
    VF7[352.1.2.2 Equipment list]
    style VF7 fill:#58a6ff
    VF8[352.1.2.2.1 Equipment check out]
    style VF8 fill:#58a6ff
    VF9[352.1.2.2.2 Equipment list]
    style VF9 fill:#58a6ff
    VF10[352.1.2.2.2.1 Equipment check IN]
    style VF10 fill:#58a6ff
    VF11[352.1.3 Sales and Payment]
    style VF11 fill:#58a6ff
    VF17[352.1.3.2.1 Saisie comment ann...]
    style VF17 fill:#58a6ff
    VF19[352.1.3.4 Special actions]
    style VF19 fill:#58a6ff
    VF20[352.1.3.4.1 Saisie comment ann...]
    style VF20 fill:#58a6ff
    VF25[352.1.3.8.1 Saisie comment ann...]
    style VF25 fill:#58a6ff
    VF26[352.1.4 Transac not PMS MBO]
    style VF26 fill:#58a6ff
    EXT93[IDE 93 Update INV equi...]
    style EXT93 fill:#3fb950
    EXT200[IDE 200 Saisie comment...]
    style EXT200 fill:#3fb950
    EXT410[IDE 410 Menu Check IN ...]
    style EXT410 fill:#3fb950
    EXT424[IDE 424 Generate Previ...]
    style EXT424 fill:#3fb950
    EXT443[IDE 443 Discounts]
    style EXT443 fill:#3fb950
    EXT446[IDE 446 Browse - pv_co...]
    style EXT446 fill:#3fb950
    EXT447[IDE 447 Browse - pv_cu...]
    style EXT447 fill:#3fb950
    EXT95[IDE 95 Calcul - bindin...]
    style EXT95 fill:#3fb950
    EXT96[IDE 96 Print Equipment...]
    style EXT96 fill:#3fb950
    EXT190[IDE 190 Seller - selec...]
    style EXT190 fill:#3fb950
    EXT191[IDE 191 Affiliations C...]
    style EXT191 fill:#3fb950
    EXT192[IDE 192 Select Product]
    style EXT192 fill:#3fb950
    EXT194[IDE 194 Delete Product]
    style EXT194 fill:#3fb950
    EXT196[IDE 196 Package= account]
    style EXT196 fill:#3fb950
    EXT216[IDE 216 Packages sales...]
    style EXT216 fill:#3fb950
    EXT218[IDE 218 Package pricing]
    style EXT218 fill:#3fb950
    EXT224[IDE 224 Credit card - ...]
    style EXT224 fill:#3fb950
    EXT225[IDE 225 Payments - select]
    style EXT225 fill:#3fb950
    EXT231[IDE 231 Search for Cre...]
    style EXT231 fill:#3fb950
    EXT312[IDE 312 Search Resolut...]
    style EXT312 fill:#3fb950
    FIN([Sortie])
    style FIN fill:#f85149
    START --> VF1
    VF1 -->|Mise a jour donnees| EXT93
    VF1 -->|Sous-programme| EXT200
    VF1 -->|Navigation menu| EXT410
    VF1 -->|Sous-programme| EXT424
    VF1 -->|Sous-programme| EXT443
    VF1 -->|Sous-programme| EXT446
    VF1 -->|Sous-programme| EXT447
    VF1 -->|Calcul de donnees| EXT95
    EXT312 --> FIN
```

**Detail par enchainement :**

| Depuis | Action | Vers | Retour |
|--------|--------|------|--------|
| Main Sale ===V4 bck | Mise a jour donnees | [Update INV equipment status (IDE 93)](PVE-IDE-93.md) | Retour ecran |
| Main Sale ===V4 bck | Sous-programme | [Saisie commentaire (IDE 200)](PVE-IDE-200.md) | Retour ecran |
| Main Sale ===V4 bck | Navigation menu | [Menu Check IN / Exchange (IDE 410)](PVE-IDE-410.md) | Retour ecran |
| Main Sale ===V4 bck | Sous-programme | [Generate Preview OD==LEX (IDE 424)](PVE-IDE-424.md) | Retour ecran |
| Main Sale ===V4 bck | Sous-programme | [Discounts (IDE 443)](PVE-IDE-443.md) | Retour ecran |
| Main Sale ===V4 bck | Sous-programme | [Browse - pv_comptab (IDE 446)](PVE-IDE-446.md) | Retour ecran |
| Main Sale ===V4 bck | Sous-programme | [Browse - pv_cust_package (IDE 447)](PVE-IDE-447.md) | Retour ecran |
| Main Sale ===V4 bck | Calcul de donnees | [Calcul - binding setting (IDE 95)](PVE-IDE-95.md) | Retour ecran |
| Main Sale ===V4 bck | Impression ticket/document | [Print Equipment SELECT (IDE 96)](PVE-IDE-96.md) | Retour ecran |
| Main Sale ===V4 bck | Selection/consultation | [Seller - selection (IDE 190)](PVE-IDE-190.md) | Retour ecran |
| Main Sale ===V4 bck | Sous-programme | [Affiliations Customer (IDE 191)](PVE-IDE-191.md) | Retour ecran |
| Main Sale ===V4 bck | Selection/consultation | [Select Product (IDE 192)](PVE-IDE-192.md) | Retour ecran |
| Main Sale ===V4 bck | Sous-programme | [Delete Product (IDE 194)](PVE-IDE-194.md) | Retour ecran |
| Main Sale ===V4 bck | Sous-programme | [      Package=> account (IDE 196)](PVE-IDE-196.md) | Retour ecran |
| Main Sale ===V4 bck | Sous-programme | [Packages sales online (IDE 216)](PVE-IDE-216.md) | Retour ecran |
| Main Sale ===V4 bck | Sous-programme | [    Package pricing (IDE 218)](PVE-IDE-218.md) | Retour ecran |
| Main Sale ===V4 bck | Selection/consultation | [Credit card - select (IDE 224)](PVE-IDE-224.md) | Retour ecran |
| Main Sale ===V4 bck | Selection/consultation | [Payments - select (IDE 225)](PVE-IDE-225.md) | Retour ecran |
| Main Sale ===V4 bck | Verification solde | [Search for Credit / Gift Pass (IDE 231)](PVE-IDE-231.md) | Retour ecran |
| Main Sale ===V4 bck | Sous-programme | [Search Resolution by Computer (IDE 312)](PVE-IDE-312.md) | Retour ecran |

### 9.3 Structure hierarchique (28 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **352.1** | [**Main Sale ===V4 bck** (352)](#t1) [mockup](#ecran-t1) | Modal | 1990x392 | Traitement |
| 352.1.1 | [Transac not PMS (352.1.1)](#t3) [mockup](#ecran-t3) | Modal | 973x248 | |
| 352.1.2 | [equip (352.1.2)](#t4) [mockup](#ecran-t4) | Modal | 971x229 | |
| 352.1.3 | [Equipment check out (352.1.2.1)](#t5) [mockup](#ecran-t5) | MDI | 320x254 | |
| 352.1.4 | [clear (352.1.2.1.1)](#t6) | MDI | - | |
| 352.1.5 | [Equipment list (352.1.2.2)](#t7) [mockup](#ecran-t7) | MDI | 188x280 | |
| 352.1.6 | [Equipment check out (352.1.2.2.1)](#t8) [mockup](#ecran-t8) | MDI | 322x282 | |
| 352.1.7 | [Equipment list (352.1.2.2.2)](#t9) [mockup](#ecran-t9) | MDI | 190x280 | |
| 352.1.8 | [Equipment check IN (352.1.2.2.2.1)](#t10) [mockup](#ecran-t10) | Type6 | 642x281 | |
| 352.1.9 | [Sales and Payment (352.1.3)](#t11) [mockup](#ecran-t11) | Modal | 979x238 | |
| 352.1.10 | [Payment (352.1.3.1)](#t12) [mockup](#ecran-t12) | MDI | 238x63 | |
| 352.1.11 | [View (352.1.3.1.2)](#t14) | - | - | |
| 352.1.12 | [Discount (352.1.3.2)](#t16) [mockup](#ecran-t16) | MDI | 220x94 | |
| 352.1.13 | [Test Prepaid (352.1.3.3)](#t18) | MDI | - | |
| 352.1.14 | [Special actions (352.1.3.4)](#t19) [mockup](#ecran-t19) | Type6 | 312x259 | |
| 352.1.15 | [Check Rentals (352.1.3.5)](#t21) | MDI | - | |
| 352.1.16 | [Check Payments (352.1.3.6)](#t22) [mockup](#ecran-t22) | MDI | 926x449 | |
| 352.1.17 | [Check Comment Refus. To Sell (352.1.3.7)](#t23) [mockup](#ecran-t23) | - | 522x498 | |
| 352.1.18 | [Discount (352.1.3.8)](#t24) [mockup](#ecran-t24) | MDI | 854x202 | |
| 352.1.19 | [Transac not PMS MBO (352.1.4)](#t26) [mockup](#ecran-t26) | MDI | 695x143 | |
| 352.1.20 | [SQL Total payement (352.1.4.1)](#t27) [mockup](#ecran-t27) | - | 115x195 | |
| **352.2** | [**Choix Onglet** (352.1)](#t2) [mockup](#ecran-t2) | MDI | 986x264 | Consultation |
| **352.3** | [**init payer** (352.1.3.1.1)](#t13) | MDI | - | Initialisation |
| **352.4** | [**create cardType** (352.1.3.1.3)](#t15) | MDI | - | Creation |
| **352.5** | [**Saisie comment annulation** (352.1.3.2.1)](#t17) [mockup](#ecran-t17) | - | 318x135 | Saisie |
| 352.5.1 | [Saisie comment annulation (352.1.3.4.1)](#t20) [mockup](#ecran-t20) | Type6 | 322x136 | |
| 352.5.2 | [Saisie comment annulation (352.1.3.8.1)](#t25) [mockup](#ecran-t25) | - | 318x135 | |
| **352.6** | [**calcul filiation** (352.2)](#t28) | MDI | - | Calcul |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Choix Onglet]
    UPDATE[MAJ 2 tables]
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

### Tables utilisees (24)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 30 | gm-recherche_____gmr | Index de recherche | DB | R |   |   | 1 |
| 39 | depot_garantie___dga | Depots et garanties | DB |   |   | L | 1 |
| 47 | compte_gm________cgm | Comptes GM (generaux) | DB |   |   | L | 1 |
| 77 | articles_________art | Articles et stock | DB | R |   |   | 1 |
| 358 | import_mod |  | DB |   |   | L | 1 |
| 377 | pv_contracts |  | DB |   |   | L | 1 |
| 378 | pv_customer |  | DB |   | **W** |   | 1 |
| 380 | pv_day_modes |  | DB |   |   | L | 6 |
| 382 | pv_discount_reasons |  | DB | R |   | L | 13 |
| 388 | pv_hotel_days |  | DB |   |   | L | 3 |
| 389 | pv_equipment_inventory |  | DB | R |   | L | 5 |
| 398 | pv_prestations | Prestations/services vendus | DB |   |   | L | 3 |
| 400 | pv_cust_rentals |  | DB | R |   | L | 11 |
| 401 | pv_cust_rentals_histo | Historique / journal | DB |   |   | L | 1 |
| 403 | pv_sellers |  | DB | R |   | L | 5 |
| 404 | pv_sellers_by_week |  | DB |   | **W** | L | 5 |
| 411 | sk_testcab |  | DB |   |   | L | 1 |
| 413 | pv_tva |  | DB |   |   | L | 1 |
| 419 | realise_articles_caution | Articles et stock | DB |   |   | L | 6 |
| 765 | tranche_age |  | DB |   |   | L | 1 |
| 766 | temp_forfait_ski |  | DB |   |   | L | 1 |
| 786 | qualite_avant_reprise |  | DB |   |   | L | 1 |
| 845 | stat_vendeur_date |  | TMP |   |   | L | 1 |
| 1488 | Table_1488 |  | MEM |   |   | L | 1 |

### Colonnes par table (13 / 8 tables avec colonnes identifiees)

<details>
<summary>Table 30 - gm-recherche_____gmr (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | v.Tab_Filation1 | R | Alpha |
| B | v.LequipmentId | R | Alpha |
| C | v.Update Tab Filiation | R | Logical |
| D | v.Decimal | R | Numeric |
| E | v.Masque | R | Alpha |
| F | v.Masque sans Z | R | Alpha |
| G | v.RechercheClubmedPass | R | Alpha |
| H | v.Compte Sauvegarde | R | Numeric |
| I | v.Societe | R | Unicode |
| J | v.Compte | R | Numeric |
| K | v..Filation | R | Numeric |
| L | v.Customer_ID | R | Numeric |
| M | v.Filiation_List | R | Alpha |
| N | v.TabOption | R | Alpha |
| O | v.RoomNumber | R | Alpha |
| P | V PoS payer id from card | R | Numeric |
| Q | V pms account from card | R | Numeric |
| R | V pms filiation from card | R | Numeric |
| S | V EZcard | R | Alpha |
| T | v.LequipementID | R | Alpha |
| U | v.Garantie | R | Unicode |
| V | v Existe Cr.Conso/Gift Pass | R | Logical |
| W | v.Titre Bt Customer | R | Alpha |
| X | L.Pakage_Id | R | Numeric |
| Y | v.Code fidelisation | R | Alpha |
| Z | v.Libelle VIP | R | Alpha |
| BA | v.All.Payment ? | R | Logical |
| BB | v.L.Test Discount ? | R | Logical |
| BC | v.SodeCompte== | R | Numeric |
| BD | V Garantie (O/N) | R | Alpha |
| BE | v.Clause Where | R | Alpha |
| BF | R.retour Message | R | Numeric |
| BG | v.Valid_Product_All | R | Logical |
| BH | v.Deb_Sejour | R | Date |
| BI | v.Fin_sejour | R | Date |
| BJ | v.Qualite | R | Unicode |
| BK | v.End | R | Logical |
| BL | V Lien Compte Spéciaux | R | Logical |

</details>

<details>
<summary>Table 77 - articles_________art (R) - 1 usages</summary>

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
| J | BP.Gift Pass | R | Alpha |
| K | BP. Print | R | Alpha |
| L | V Action type | R | Alpha |
| M | V Solde Gift Pass | R | Numeric |
| N | V Montant  Eligible Gift Pass | R | Numeric |
| O | V Type | R | Alpha |
| P | v.Card Type (Param) | R | Alpha |
| Q | v.Prépaid ? | R | Logical |
| R | v.EmptyRental | R | Logical |
| S | v.EmptyPayment | R | Logical |
| T | V empty comment(Refus.to sell) | R | Logical |
| U | v.Action Type | R | Alpha |
| V | v.Confirme Action | R | Numeric |
| W | v.AllPayments | R | Logical |
| X | v.AnnulPayment | R | Logical |
| Y |  v Montant Credit Conso / Free | R | Numeric |
| Z | v.Adresse Mail | R | Alpha |
| BA | v.Langue | R | Alpha |
| BB | v.Envoi Email | R | Logical |

</details>

<details>
<summary>Table 378 - pv_customer (**W**) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | p.Customer_ID | W | Numeric |
| L | v.Customer_ID | W | Numeric |
| W | v.Titre Bt Customer | W | Alpha |

</details>

<details>
<summary>Table 382 - pv_discount_reasons (R/L) - 13 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P.Societe | R | Alpha |
| B | P.Compte | R | Numeric |
| C | P.Filiation | R | Numeric |
| D | v.binding setting | R | Numeric |
| E | v.color | R | Numeric |
| F | bt swap | R | Alpha |
| G | V Saisie Commentaire Ok ? | R | Logical |

</details>

<details>
<summary>Table 389 - pv_equipment_inventory (R/L) - 5 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | v.serial | R | Alpha |
| B | v.confirm <> classif | R | Numeric |
| C | r.equipment | R | Logical |
| D | bt ok | R | Alpha |

</details>

<details>
<summary>Table 400 - pv_cust_rentals (R/L) - 11 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P.Societe | R | Alpha |
| B | P.Compte | R | Numeric |
| C | P.Filiation | R | Numeric |
| D | V Total | R | Numeric |
| E | V.Clause where | R | Alpha |
| F | V.Add jointure | R | Alpha |

</details>

<details>
<summary>Table 403 - pv_sellers (R/L) - 5 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P.Societe | R | Alpha |
| B | P.Compte | R | Numeric |
| C | P.Filiation | R | Numeric |
| D | v.Serial Id | R | Alpha |
| E | v.retour equipment | R | Logical |
| F | V.exist package ? | R | Logical |

</details>

<details>
<summary>Table 404 - pv_sellers_by_week (**W**/L) - 5 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Variables de session (36)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | v.Tab_Filation1 | Alpha | 1x session |
| B | v.LequipmentId | Alpha | - |
| C | v.Update Tab Filiation | Logical | [352.2](#t28) |
| D | v.Decimal | Numeric | - |
| E | v.Masque | Alpha | 1x session |
| F | v.Masque sans Z | Alpha | - |
| G | v.RechercheClubmedPass | Alpha | - |
| H | v.Compte Sauvegarde | Numeric | - |
| I | v.Societe | Unicode | 2x session |
| J | v.Compte | Numeric | 2x session |
| K | v..Filation | Numeric | 2x session |
| L | v.Customer_ID | Numeric | 2x session |
| M | v.Filiation_List | Alpha | - |
| N | v.TabOption | Alpha | - |
| O | v.RoomNumber | Alpha | 1x session |
| P | V PoS payer id from card | Numeric | [352.1.3.1.1](#t13), [352.1.3.1.3](#t15) |
| Q | V pms account from card | Numeric | [352.1.3.1.3](#t15) |
| R | V pms filiation from card | Numeric | [352.1.3.1.3](#t15), [352.2](#t28) |
| S | V EZcard | Alpha | 1x session |
| T | v.LequipementID | Alpha | 1x session |
| U | v.Garantie | Unicode | 1x session |
| V | v Existe Cr.Conso/Gift Pass | Logical | - |
| W | v.Titre Bt Customer | Alpha | 2x session |
| Y | v.Code fidelisation | Alpha | - |
| Z | v.Libelle VIP | Alpha | 1x session |
| BA | v.All.Payment ? | Logical | - |
| BB | v.L.Test Discount ? | Logical | - |
| BC | v.SodeCompte== | Numeric | - |
| BD | V Garantie (O/N) | Alpha | - |
| BE | v.Clause Where | Alpha | - |
| BG | v.Valid_Product_All | Logical | - |
| BH | v.Deb_Sejour | Date | - |
| BI | v.Fin_sejour | Date | - |
| BJ | v.Qualite | Unicode | 2x session |
| BK | v.End | Logical | 1x session |
| BL | V Lien Compte Spéciaux | Logical | 1x session |

### 11.2 Autres (2)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| X | L.Pakage_Id | Numeric | - |
| BF | R.retour Message | Numeric | - |

<details>
<summary>Toutes les 38 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| V. | **A** | v.Tab_Filation1 | Alpha |
| V. | **B** | v.LequipmentId | Alpha |
| V. | **C** | v.Update Tab Filiation | Logical |
| V. | **D** | v.Decimal | Numeric |
| V. | **E** | v.Masque | Alpha |
| V. | **F** | v.Masque sans Z | Alpha |
| V. | **G** | v.RechercheClubmedPass | Alpha |
| V. | **H** | v.Compte Sauvegarde | Numeric |
| V. | **I** | v.Societe | Unicode |
| V. | **J** | v.Compte | Numeric |
| V. | **K** | v..Filation | Numeric |
| V. | **L** | v.Customer_ID | Numeric |
| V. | **M** | v.Filiation_List | Alpha |
| V. | **N** | v.TabOption | Alpha |
| V. | **O** | v.RoomNumber | Alpha |
| V. | **P** | V PoS payer id from card | Numeric |
| V. | **Q** | V pms account from card | Numeric |
| V. | **R** | V pms filiation from card | Numeric |
| V. | **S** | V EZcard | Alpha |
| V. | **T** | v.LequipementID | Alpha |
| V. | **U** | v.Garantie | Unicode |
| V. | **V** | v Existe Cr.Conso/Gift Pass | Logical |
| V. | **W** | v.Titre Bt Customer | Alpha |
| V. | **Y** | v.Code fidelisation | Alpha |
| V. | **Z** | v.Libelle VIP | Alpha |
| V. | **BA** | v.All.Payment ? | Logical |
| V. | **BB** | v.L.Test Discount ? | Logical |
| V. | **BC** | v.SodeCompte== | Numeric |
| V. | **BD** | V Garantie (O/N) | Alpha |
| V. | **BE** | v.Clause Where | Alpha |
| V. | **BG** | v.Valid_Product_All | Logical |
| V. | **BH** | v.Deb_Sejour | Date |
| V. | **BI** | v.Fin_sejour | Date |
| V. | **BJ** | v.Qualite | Unicode |
| V. | **BK** | v.End | Logical |
| V. | **BL** | V Lien Compte Spéciaux | Logical |
| Autre | **X** | L.Pakage_Id | Numeric |
| Autre | **BF** | R.retour Message | Numeric |

</details>

## 12. EXPRESSIONS

**72 / 72 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCULATION | 6 | 0 |
| CAST_LOGIQUE | 5 | 2 |
| CONDITION | 16 | 7 |
| CONSTANTE | 3 | 0 |
| OTHER | 28 | 0 |
| REFERENCE_VG | 14 | 0 |

### 12.2 Expressions cles par type

#### CALCULATION (6 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 34 | `CallProg ('{295,-1}'PROG,[AL],[AM],[AN])` | - |
| CALCULATION | 35 | `CallProg ('{305,-1}'PROG,[AL],[AM])` | - |
| CALCULATION | 37 | `Left (Trim (v.Masque [E]),Len (Trim (v.Masque [E]))-1)` | - |
| CALCULATION | 8 | `CallProg ('{305,-1}'PROG,[AL],[AM])` | - |
| CALCULATION | 29 | `'USER LOGON - '&Trim(VG39)` | - |
| ... | | *+1 autres* | |

#### CAST_LOGIQUE (5 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 18 | `IF(v.Qualite [BJ]='O' OR v.Garantie [U]='O','TRUE'LOG,'FALSE'LOG)` | [RM-006](#rm-RM-006) |
| CAST_LOGIQUE | 45 | `IF(GetParam ('RENTAL')='TRUE'LOG,'Insurance','')` | [RM-009](#rm-RM-009) |
| CAST_LOGIQUE | 44 | `INIPut('AllowUpdateInQuery=Y','FALSE'LOG)` | - |
| CAST_LOGIQUE | 1 | `'TRUE'LOG` | - |
| CAST_LOGIQUE | 40 | `'Version = '& Trim(VG3)& '  -  Mobilité = '&IF(VG32='TRUE'LOG,'Vrai','Faux')&'  --- Support = '&Trim(VG33)& '===> Voulez-vous changer ?'` | - |

#### CONDITION (16 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 17 | `IF(Trim(v.Libelle VIP [Z])<>'',Trim(v.Libelle VIP [Z]),Trim([CF]))` | [RM-005](#rm-RM-005) |
| CONDITION | 19 | `IF(VG17<>[AO] OR v.Update Tab Filiation [C],Trim (Str ([AN],'3')),v.Tab_Filation1 [A])` | [RM-007](#rm-RM-007) |
| CONDITION | 38 | `IF(NOT(VG18),[BU],[BT])` | [RM-008](#rm-RM-008) |
| CONDITION | 16 | `IF([BV]='V','VIP',IF([BV]='T','TOP VIP',''))` | [RM-004](#rm-RM-004) |
| CONDITION | 2 | `IF(Date()>[AI] OR Date()<[AH],43,6)` | [RM-001](#rm-RM-001) |
| ... | | *+11 autres* | |

#### CONSTANTE (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 39 | `'S'` | - |
| CONSTANTE | 13 | `0` | - |
| CONSTANTE | 5 | `'R'` | - |

#### OTHER (28 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 62 | `v.Compte [J]` | - |
| OTHER | 63 | `v..Filation [K]` | - |
| OTHER | 64 | `V PoS payer id from card [P]` | - |
| OTHER | 61 | `v.Societe [I]` | - |
| OTHER | 43 | `GetParam('SERVICE')` | - |
| ... | | *+23 autres* | |

#### REFERENCE_VG (14 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 54 | `VG54` | - |
| REFERENCE_VG | 53 | `VG53` | - |
| REFERENCE_VG | 52 | `VG52` | - |
| REFERENCE_VG | 55 | `VG55` | - |
| REFERENCE_VG | 58 | `VG58` | - |
| ... | | *+9 autres* | |

### 12.3 Toutes les expressions (72)

<details>
<summary>Voir les 72 expressions</summary>

#### CALCULATION (6)

| IDE | Expression Decodee |
|-----|-------------------|
| 8 | `CallProg ('{305,-1}'PROG,[AL],[AM])` |
| 29 | `'USER LOGON - '&Trim(VG39)` |
| 30 | `'SELECT CUSTOMER - '&Trim(v.Titre Bt Customer [W])` |
| 34 | `CallProg ('{295,-1}'PROG,[AL],[AM],[AN])` |
| 35 | `CallProg ('{305,-1}'PROG,[AL],[AM])` |
| 37 | `Left (Trim (v.Masque [E]),Len (Trim (v.Masque [E]))-1)` |

#### CAST_LOGIQUE (5)

| IDE | Expression Decodee |
|-----|-------------------|
| 40 | `'Version = '& Trim(VG3)& '  -  Mobilité = '&IF(VG32='TRUE'LOG,'Vrai','Faux')&'  --- Support = '&Trim(VG33)& '===> Voulez-vous changer ?'` |
| 18 | `IF(v.Qualite [BJ]='O' OR v.Garantie [U]='O','TRUE'LOG,'FALSE'LOG)` |
| 45 | `IF(GetParam ('RENTAL')='TRUE'LOG,'Insurance','')` |
| 1 | `'TRUE'LOG` |
| 44 | `INIPut('AllowUpdateInQuery=Y','FALSE'LOG)` |

#### CONDITION (16)

| IDE | Expression Decodee |
|-----|-------------------|
| 2 | `IF(Date()>[AI] OR Date()<[AH],43,6)` |
| 3 | `IF(Trim(VG33)='WS','TB',IF(Trim(VG33)='TB','WS',VG33))` |
| 12 | `IF(v.LequipementID [T]='','Sale','Equipment')` |
| 16 | `IF([BV]='V','VIP',IF([BV]='T','TOP VIP',''))` |
| 17 | `IF(Trim(v.Libelle VIP [Z])<>'',Trim(v.Libelle VIP [Z]),Trim([CF]))` |
| 19 | `IF(VG17<>[AO] OR v.Update Tab Filiation [C],Trim (Str ([AN],'3')),v.Tab_Filation1 [A])` |
| 38 | `IF(NOT(VG18),[BU],[BT])` |
| 6 | `VG17<>0` |
| 7 | `[AF]=6` |
| 14 | `V Lien Compte Spéciaux [BL]='R'` |
| 15 | `[BX]='O'` |
| 31 | `GetParam ('SERVICELIB')<>''` |
| 33 | `[AO]<>0` |
| 41 | `[CI]>0` |
| 72 | `[AO]<>0` |
| 32 | `Trim(VG38)<>''` |

#### CONSTANTE (3)

| IDE | Expression Decodee |
|-----|-------------------|
| 5 | `'R'` |
| 13 | `0` |
| 39 | `'S'` |

#### OTHER (28)

| IDE | Expression Decodee |
|-----|-------------------|
| 4 | `[AK]` |
| 9 | `v.End [BK]` |
| 10 | `v.Qualite [BJ]` |
| 11 | `GetParam ('DECIMALNUMBER')` |
| 20 | `[BU]` |
| 21 | `[AL]` |
| 23 | `[AM]` |
| 24 | `[AN]` |
| 25 | `v.Societe [I]` |
| 26 | `v.Compte [J]` |
| 27 | `v..Filation [K]` |
| 28 | `v.Customer_ID [L]` |
| 36 | `GetParam ('AMOUNTFORMAT')` |
| 42 | `[AO]` |
| 43 | `GetParam('SERVICE')` |
| 59 | `v.Titre Bt Customer [W]` |
| 60 | `v.Customer_ID [L]` |
| 61 | `v.Societe [I]` |
| 62 | `v.Compte [J]` |
| 63 | `v..Filation [K]` |
| 64 | `V PoS payer id from card [P]` |
| 65 | `V pms account from card [Q]` |
| 66 | `V pms filiation from card [R]` |
| 67 | `V EZcard [S]` |
| 68 | `[AH]` |
| 69 | `[AI]` |
| 70 | `v.RoomNumber [O]` |
| 71 | `[AJ]` |

#### REFERENCE_VG (14)

| IDE | Expression Decodee |
|-----|-------------------|
| 22 | `VG19` |
| 46 | `VG46` |
| 47 | `VG47` |
| 48 | `VG48` |
| 49 | `VG49` |
| 50 | `VG50` |
| 51 | `VG51` |
| 52 | `VG52` |
| 53 | `VG53` |
| 54 | `VG54` |
| 55 | `VG55` |
| 56 | `VG56` |
| 57 | `VG57` |
| 58 | `VG58` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

**Chemin**: (pas de callers directs)

```mermaid
graph LR
    T352[352 Main Sale ===V4 bck]
    style T352 fill:#58a6ff
    NONE[Aucun caller]
    NONE -.-> T352
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| - | (aucun) | - |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T352[352 Main Sale ===V4 bck]
    style T352 fill:#58a6ff
    C93[93 Update INV equipmen...]
    T352 --> C93
    style C93 fill:#3fb950
    C200[200 Saisie commentaire]
    T352 --> C200
    style C200 fill:#3fb950
    C410[410 Menu Check IN Exch...]
    T352 --> C410
    style C410 fill:#3fb950
    C424[424 Generate Preview O...]
    T352 --> C424
    style C424 fill:#3fb950
    C443[443 Discounts]
    T352 --> C443
    style C443 fill:#3fb950
    C446[446 Browse - pv_comptab]
    T352 --> C446
    style C446 fill:#3fb950
    C447[447 Browse - pv_cust_p...]
    T352 --> C447
    style C447 fill:#3fb950
    C95[95 Calcul - binding se...]
    T352 --> C95
    style C95 fill:#3fb950
    C96[96 Print Equipment SELECT]
    T352 --> C96
    style C96 fill:#3fb950
    C190[190 Seller - selection]
    T352 --> C190
    style C190 fill:#3fb950
    C191[191 Affiliations Customer]
    T352 --> C191
    style C191 fill:#3fb950
    C192[192 Select Product]
    T352 --> C192
    style C192 fill:#3fb950
    C194[194 Delete Product]
    T352 --> C194
    style C194 fill:#3fb950
    C196[196 Package= account]
    T352 --> C196
    style C196 fill:#3fb950
    C216[216 Packages sales online]
    T352 --> C216
    style C216 fill:#3fb950
    C218[218 Package pricing]
    T352 --> C218
    style C218 fill:#3fb950
    C224[224 Credit card - select]
    T352 --> C224
    style C224 fill:#3fb950
    C225[225 Payments - select]
    T352 --> C225
    style C225 fill:#3fb950
    C231[231 Search for Credit ...]
    T352 --> C231
    style C231 fill:#3fb950
    C312[312 Search Resolution ...]
    T352 --> C312
    style C312 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [93](PVE-IDE-93.md) | Update INV equipment status | 4 | Mise a jour donnees |
| [200](PVE-IDE-200.md) | Saisie commentaire | 3 | Sous-programme |
| [410](PVE-IDE-410.md) | Menu Check IN / Exchange | 2 | Navigation menu |
| [424](PVE-IDE-424.md) | Generate Preview OD==LEX | 2 | Sous-programme |
| [443](PVE-IDE-443.md) | Discounts | 2 | Sous-programme |
| [446](PVE-IDE-446.md) | Browse - pv_comptab | 2 | Sous-programme |
| [447](PVE-IDE-447.md) | Browse - pv_cust_package | 2 | Sous-programme |
| [95](PVE-IDE-95.md) | Calcul - binding setting | 1 | Calcul de donnees |
| [96](PVE-IDE-96.md) | Print Equipment SELECT | 1 | Impression ticket/document |
| [190](PVE-IDE-190.md) | Seller - selection | 1 | Selection/consultation |
| [191](PVE-IDE-191.md) | Affiliations Customer | 1 | Sous-programme |
| [192](PVE-IDE-192.md) | Select Product | 1 | Selection/consultation |
| [194](PVE-IDE-194.md) | Delete Product | 1 | Sous-programme |
| [196](PVE-IDE-196.md) |       Package=> account | 1 | Sous-programme |
| [216](PVE-IDE-216.md) | Packages sales online | 1 | Sous-programme |
| [218](PVE-IDE-218.md) |     Package pricing | 1 | Sous-programme |
| [224](PVE-IDE-224.md) | Credit card - select | 1 | Selection/consultation |
| [225](PVE-IDE-225.md) | Payments - select | 1 | Selection/consultation |
| [231](PVE-IDE-231.md) | Search for Credit / Gift Pass | 1 | Verification solde |
| [312](PVE-IDE-312.md) | Search Resolution by Computer | 1 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 1226 | Programme volumineux |
| Expressions | 72 | Logique moderee |
| Tables WRITE | 2 | Impact faible |
| Sous-programmes | 20 | Forte dependance |
| Ecrans visibles | 15 | Interface complexe multi-ecrans |
| Code desactive | 1% (12 / 1226) | Code sain |
| Regles metier | 9 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (21 taches: 17 ecrans, 4 traitements)

- **Strategie** : Orchestrateur avec 17 ecrans (Razor/React) et 4 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 20 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Consultation (1 tache: 1 ecran, 0 traitement)

- **Strategie** : Composants de recherche/selection en modales.
- 1 ecran : Choix Onglet

#### Initialisation (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Constructeur/methode `InitAsync()` dans l'orchestrateur.

#### Creation (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Repository pattern avec Entity Framework Core.
- Insertion via `IRepository<T>.CreateAsync()`

#### Saisie (3 taches: 3 ecrans, 0 traitement)

- **Strategie** : Formulaire React/Blazor avec validation Zod/FluentValidation.
- Reproduire 3 ecrans : Saisie comment annulation, Saisie comment annulation, Saisie comment annulation
- Validation temps reel cote client + serveur

#### Calcul (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Services de calcul purs (Domain Services).
- Migrer la logique de calcul (stock, compteurs, montants)

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| pv_customer | Table WRITE (Database) | 1x | Schema + repository |
| pv_sellers_by_week | Table WRITE (Database) | 1x | Schema + repository |
| [Update INV equipment status (IDE 93)](PVE-IDE-93.md) | Sous-programme | 4x | **CRITIQUE** - Mise a jour donnees |
| [Saisie commentaire (IDE 200)](PVE-IDE-200.md) | Sous-programme | 3x | **CRITIQUE** - Sous-programme |
| [Browse - pv_comptab (IDE 446)](PVE-IDE-446.md) | Sous-programme | 2x | Haute - Sous-programme |
| [Browse - pv_cust_package (IDE 447)](PVE-IDE-447.md) | Sous-programme | 2x | Haute - Sous-programme |
| [Discounts (IDE 443)](PVE-IDE-443.md) | Sous-programme | 2x | Haute - Sous-programme |
| [Menu Check IN / Exchange (IDE 410)](PVE-IDE-410.md) | Sous-programme | 2x | Haute - Navigation menu |
| [Generate Preview OD==LEX (IDE 424)](PVE-IDE-424.md) | Sous-programme | 2x | Haute - Sous-programme |
| [Credit card - select (IDE 224)](PVE-IDE-224.md) | Sous-programme | 1x | Normale - Selection/consultation |
| [    Package pricing (IDE 218)](PVE-IDE-218.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Packages sales online (IDE 216)](PVE-IDE-216.md) | Sous-programme | 1x | Normale - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 19:43*
