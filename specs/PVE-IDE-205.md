# PVE IDE 205 - Edition ticket (Tva) LEX

> **Analyse**: Phases 1-4 2026-02-03 18:53 -> 18:53 (14s) | Assemblage 18:53
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PVE |
| IDE Position | 205 |
| Nom Programme | Edition ticket (Tva) LEX |
| Fichier source | `Prg_205.xml` |
| Dossier IDE | Mobile |
| Taches | 36 (1 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 8 |

## 2. DESCRIPTION FONCTIONNELLE

**Edition ticket (Tva) LEX** assure la gestion complete de ce processus, accessible depuis [Print Invoice or Ticket (IDE 358)](PVE-IDE-358.md), [Print Invoice or Ticket==NEW (IDE 429)](PVE-IDE-429.md), [Choice Re_Print Invoice (IDE 204)](PVE-IDE-204.md), [Print Invoice or Ticket (IDE 208)](PVE-IDE-208.md), [Print Invoice or Ticket-664 (IDE 209)](PVE-IDE-209.md).

Le flux de traitement s'organise en **2 blocs fonctionnels** :

- **Traitement** (25 taches) : traitements metier divers
- **Impression** (11 taches) : generation de tickets et documents

**Logique metier** : 3 regles identifiees couvrant conditions metier.

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (25 taches)

- **205** - Please be patient ... **[[ECRAN]](#ecran-t1)**
- **205.1.1** - Impression reçu change **[[ECRAN]](#ecran-t3)**
- **205.1.2** - Impression reçu change **[[ECRAN]](#ecran-t4)**
- **205.1.2.2** - Impression reçu change **[[ECRAN]](#ecran-t6)**
- **205.1.2.3** - GetBookigsInfo
- **205.1.2.3.1** - GetBookigsInfo
- **205.2** - Counter
- **205.2.1** - Impression reçu change
- **205.2.2** - Impression reçu change
- **205.2.2.2** - Impression reçu change **[[ECRAN]](#ecran-t14)**
- **205.3.1** - Veuillez patienter ... **[[ECRAN]](#ecran-t16)**
- **205.3.2** - Veuillez patienter ... **[[ECRAN]](#ecran-t17)**
- **205.3.2.2** - Veuillez patienter ... **[[ECRAN]](#ecran-t19)**
- **205.4.1** - Veuillez patienter ... **[[ECRAN]](#ecran-t21)**
- **205.4.2** - Veuillez patienter ... **[[ECRAN]](#ecran-t22)**
- **205.4.2.2** - Veuillez patienter ... **[[ECRAN]](#ecran-t24)**
- **205.4.2.3** - GetBookigsInfo
- **205.4.2.3.1** - GetBookigsInfo
- **205.5** - Counter
- **205.5.1** - Impression reçu change **[[ECRAN]](#ecran-t29)**
- **205.5.2** - Impression reçu change **[[ECRAN]](#ecran-t30)**
- **205.5.2.2** - Impression reçu change **[[ECRAN]](#ecran-t32)**
- **205.5.2.3** - GetBookigsInfo
- **205.5.2.3.1** - GetBookigsInfo
- **205.6** - Search Gift Pass

Delegue a : [Concatène libellé Cat/Ss-Cat (IDE 321)](PVE-IDE-321.md), [GetAppointment (IDE 161)](PVE-IDE-161.md), [Set Listing Number (IDE 274)](PVE-IDE-274.md), [Search  for messages (IDE 279)](PVE-IDE-279.md)

#### Phase 2 : Impression (11 taches)

- **205.1** - Printer 1
- **205.1.2.1** - Print Tva **[[ECRAN]](#ecran-t5)**
- **205.1.2.4** - Print Appointments **[[ECRAN]](#ecran-t9)**
- **205.2.2.1** - Print Tva **[[ECRAN]](#ecran-t13)**
- **205.3** - Printer 5 **[[ECRAN]](#ecran-t15)**
- **205.3.2.1** - Print Tva **[[ECRAN]](#ecran-t18)**
- **205.4** - Printer 9 **[[ECRAN]](#ecran-t20)**
- **205.4.2.1** - Print Tva **[[ECRAN]](#ecran-t23)**
- **205.4.2.4** - Print Appointments **[[ECRAN]](#ecran-t27)**
- **205.5.2.1** - Print Tva **[[ECRAN]](#ecran-t31)**
- **205.5.2.4** - Print Appointments **[[ECRAN]](#ecran-t35)**

Delegue a : [Creation pied Ticket(Tva) (IDE 281)](PVE-IDE-281.md), [Set Listing Number (IDE 274)](PVE-IDE-274.md), [Raz Current Printer (IDE 275)](PVE-IDE-275.md), [Get Printer (IDE 276)](PVE-IDE-276.md), [GetPrinter/t impression (IDE 283)](PVE-IDE-283.md)

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (25 taches)

Traitements internes.

---

#### <a id="t1"></a>205 - Please be patient ... [[ECRAN]](#ecran-t1)

**Role** : Tache d'orchestration : point d'entree du programme (25 sous-taches). Coordonne l'enchainement des traitements.
**Ecran** : 427 x 57 DLU (MDI) | [Voir mockup](#ecran-t1)

<details>
<summary>24 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [205.1.1](#t3) | Impression reçu change **[[ECRAN]](#ecran-t3)** | Traitement |
| [205.1.2](#t4) | Impression reçu change **[[ECRAN]](#ecran-t4)** | Traitement |
| [205.1.2.2](#t6) | Impression reçu change **[[ECRAN]](#ecran-t6)** | Traitement |
| [205.1.2.3](#t7) | GetBookigsInfo | Traitement |
| [205.1.2.3.1](#t8) | GetBookigsInfo | Traitement |
| [205.2](#t10) | Counter | Traitement |
| [205.2.1](#t11) | Impression reçu change | Traitement |
| [205.2.2](#t12) | Impression reçu change | Traitement |
| [205.2.2.2](#t14) | Impression reçu change **[[ECRAN]](#ecran-t14)** | Traitement |
| [205.3.1](#t16) | Veuillez patienter ... **[[ECRAN]](#ecran-t16)** | Traitement |
| [205.3.2](#t17) | Veuillez patienter ... **[[ECRAN]](#ecran-t17)** | Traitement |
| [205.3.2.2](#t19) | Veuillez patienter ... **[[ECRAN]](#ecran-t19)** | Traitement |
| [205.4.1](#t21) | Veuillez patienter ... **[[ECRAN]](#ecran-t21)** | Traitement |
| [205.4.2](#t22) | Veuillez patienter ... **[[ECRAN]](#ecran-t22)** | Traitement |
| [205.4.2.2](#t24) | Veuillez patienter ... **[[ECRAN]](#ecran-t24)** | Traitement |
| [205.4.2.3](#t25) | GetBookigsInfo | Traitement |
| [205.4.2.3.1](#t26) | GetBookigsInfo | Traitement |
| [205.5](#t28) | Counter | Traitement |
| [205.5.1](#t29) | Impression reçu change **[[ECRAN]](#ecran-t29)** | Traitement |
| [205.5.2](#t30) | Impression reçu change **[[ECRAN]](#ecran-t30)** | Traitement |
| [205.5.2.2](#t32) | Impression reçu change **[[ECRAN]](#ecran-t32)** | Traitement |
| [205.5.2.3](#t33) | GetBookigsInfo | Traitement |
| [205.5.2.3.1](#t34) | GetBookigsInfo | Traitement |
| [205.6](#t36) | Search Gift Pass | Traitement |

</details>

---

#### <a id="t3"></a>205.1.1 - Impression reçu change [[ECRAN]](#ecran-t3)

**Role** : Generation du document : Impression reçu change.
**Ecran** : 630 x 0 DLU (MDI) | [Voir mockup](#ecran-t3)

---

#### <a id="t4"></a>205.1.2 - Impression reçu change [[ECRAN]](#ecran-t4)

**Role** : Generation du document : Impression reçu change.
**Ecran** : 1205 x 0 DLU (MDI) | [Voir mockup](#ecran-t4)

---

#### <a id="t6"></a>205.1.2.2 - Impression reçu change [[ECRAN]](#ecran-t6)

**Role** : Generation du document : Impression reçu change.
**Ecran** : 574 x 0 DLU (MDI) | [Voir mockup](#ecran-t6)

---

#### <a id="t7"></a>205.1.2.3 - GetBookigsInfo

**Role** : Consultation/chargement : GetBookigsInfo.

---

#### <a id="t8"></a>205.1.2.3.1 - GetBookigsInfo

**Role** : Consultation/chargement : GetBookigsInfo.

---

#### <a id="t10"></a>205.2 - Counter

**Role** : Traitement : Counter.

---

#### <a id="t11"></a>205.2.1 - Impression reçu change

**Role** : Generation du document : Impression reçu change.

---

#### <a id="t12"></a>205.2.2 - Impression reçu change

**Role** : Generation du document : Impression reçu change.

---

#### <a id="t14"></a>205.2.2.2 - Impression reçu change [[ECRAN]](#ecran-t14)

**Role** : Generation du document : Impression reçu change.
**Ecran** : 574 x 0 DLU (MDI) | [Voir mockup](#ecran-t14)

---

#### <a id="t16"></a>205.3.1 - Veuillez patienter ... [[ECRAN]](#ecran-t16)

**Role** : Traitement : Veuillez patienter ....
**Ecran** : 426 x 57 DLU (MDI) | [Voir mockup](#ecran-t16)

---

#### <a id="t17"></a>205.3.2 - Veuillez patienter ... [[ECRAN]](#ecran-t17)

**Role** : Traitement : Veuillez patienter ....
**Ecran** : 424 x 56 DLU (MDI) | [Voir mockup](#ecran-t17)

---

#### <a id="t19"></a>205.3.2.2 - Veuillez patienter ... [[ECRAN]](#ecran-t19)

**Role** : Traitement : Veuillez patienter ....
**Ecran** : 424 x 56 DLU (MDI) | [Voir mockup](#ecran-t19)

---

#### <a id="t21"></a>205.4.1 - Veuillez patienter ... [[ECRAN]](#ecran-t21)

**Role** : Traitement : Veuillez patienter ....
**Ecran** : 424 x 56 DLU (MDI) | [Voir mockup](#ecran-t21)

---

#### <a id="t22"></a>205.4.2 - Veuillez patienter ... [[ECRAN]](#ecran-t22)

**Role** : Traitement : Veuillez patienter ....
**Ecran** : 1242 x 399 DLU (MDI) | [Voir mockup](#ecran-t22)

---

#### <a id="t24"></a>205.4.2.2 - Veuillez patienter ... [[ECRAN]](#ecran-t24)

**Role** : Traitement : Veuillez patienter ....
**Ecran** : 424 x 56 DLU (MDI) | [Voir mockup](#ecran-t24)

---

#### <a id="t25"></a>205.4.2.3 - GetBookigsInfo

**Role** : Consultation/chargement : GetBookigsInfo.

---

#### <a id="t26"></a>205.4.2.3.1 - GetBookigsInfo

**Role** : Consultation/chargement : GetBookigsInfo.

---

#### <a id="t28"></a>205.5 - Counter

**Role** : Traitement : Counter.

---

#### <a id="t29"></a>205.5.1 - Impression reçu change [[ECRAN]](#ecran-t29)

**Role** : Generation du document : Impression reçu change.
**Ecran** : 630 x 0 DLU (MDI) | [Voir mockup](#ecran-t29)

---

#### <a id="t30"></a>205.5.2 - Impression reçu change [[ECRAN]](#ecran-t30)

**Role** : Generation du document : Impression reçu change.
**Ecran** : 574 x 0 DLU (MDI) | [Voir mockup](#ecran-t30)

---

#### <a id="t32"></a>205.5.2.2 - Impression reçu change [[ECRAN]](#ecran-t32)

**Role** : Generation du document : Impression reçu change.
**Ecran** : 574 x 0 DLU (MDI) | [Voir mockup](#ecran-t32)

---

#### <a id="t33"></a>205.5.2.3 - GetBookigsInfo

**Role** : Consultation/chargement : GetBookigsInfo.

---

#### <a id="t34"></a>205.5.2.3.1 - GetBookigsInfo

**Role** : Consultation/chargement : GetBookigsInfo.

---

#### <a id="t36"></a>205.6 - Search Gift Pass

**Role** : Calcul fidelite/avantage : Search Gift Pass.
**Variables liees** : BJ (V Existe Gift Pass), BK (V.Solde  Gift Pass), BL (v.Affichage Ligne Gift Pass?), BM (V.Message Solde Gift Pass), BN (V Editer Solde Gift Pass a 0)


### 3.2 Impression (11 taches)

Generation des documents et tickets.

---

#### <a id="t2"></a>205.1 - Printer 1

**Role** : Generation du document : Printer 1.

---

#### <a id="t5"></a>205.1.2.1 - Print Tva [[ECRAN]](#ecran-t5)

**Role** : Generation du document : Print Tva.
**Ecran** : 506 x 0 DLU | [Voir mockup](#ecran-t5)
**Variables liees** : B (P. PrintAgainExecution), C (P. PrintAgainPreview)

---

#### <a id="t9"></a>205.1.2.4 - Print Appointments [[ECRAN]](#ecran-t9)

**Role** : Generation du document : Print Appointments.
**Ecran** : 506 x 0 DLU | [Voir mockup](#ecran-t9)
**Variables liees** : B (P. PrintAgainExecution), C (P. PrintAgainPreview)

---

#### <a id="t13"></a>205.2.2.1 - Print Tva [[ECRAN]](#ecran-t13)

**Role** : Generation du document : Print Tva.
**Ecran** : 127 x 0 DLU | [Voir mockup](#ecran-t13)
**Variables liees** : B (P. PrintAgainExecution), C (P. PrintAgainPreview)

---

#### <a id="t15"></a>205.3 - Printer 5 [[ECRAN]](#ecran-t15)

**Role** : Generation du document : Printer 5.
**Ecran** : 424 x 56 DLU (MDI) | [Voir mockup](#ecran-t15)

---

#### <a id="t18"></a>205.3.2.1 - Print Tva [[ECRAN]](#ecran-t18)

**Role** : Generation du document : Print Tva.
**Ecran** : 506 x 0 DLU | [Voir mockup](#ecran-t18)
**Variables liees** : B (P. PrintAgainExecution), C (P. PrintAgainPreview)

---

#### <a id="t20"></a>205.4 - Printer 9 [[ECRAN]](#ecran-t20)

**Role** : Generation du document : Printer 9.
**Ecran** : 424 x 56 DLU (MDI) | [Voir mockup](#ecran-t20)

---

#### <a id="t23"></a>205.4.2.1 - Print Tva [[ECRAN]](#ecran-t23)

**Role** : Generation du document : Print Tva.
**Ecran** : 506 x 0 DLU | [Voir mockup](#ecran-t23)
**Variables liees** : B (P. PrintAgainExecution), C (P. PrintAgainPreview)

---

#### <a id="t27"></a>205.4.2.4 - Print Appointments [[ECRAN]](#ecran-t27)

**Role** : Generation du document : Print Appointments.
**Ecran** : 506 x 0 DLU | [Voir mockup](#ecran-t27)
**Variables liees** : B (P. PrintAgainExecution), C (P. PrintAgainPreview)

---

#### <a id="t31"></a>205.5.2.1 - Print Tva [[ECRAN]](#ecran-t31)

**Role** : Generation du document : Print Tva.
**Ecran** : 506 x 0 DLU | [Voir mockup](#ecran-t31)
**Variables liees** : B (P. PrintAgainExecution), C (P. PrintAgainPreview)

---

#### <a id="t35"></a>205.5.2.4 - Print Appointments [[ECRAN]](#ecran-t35)

**Role** : Generation du document : Print Appointments.
**Ecran** : 506 x 0 DLU | [Voir mockup](#ecran-t35)
**Variables liees** : B (P. PrintAgainExecution), C (P. PrintAgainPreview)


## 5. REGLES METIER

3 regles identifiees:

### Autres (3 regles)

#### <a id="rm-RM-001"></a>[RM-001] Si [AR] vaut '010' alors 'Tva', sinon 'Vat'

| Element | Detail |
|---------|--------|
| **Condition** | `[AR]='010'` |
| **Si vrai** | 'Tva' |
| **Si faux** | 'Vat') |
| **Expression source** | Expression 47 : `IF([AR]='010','Tva','Vat')` |
| **Exemple** | Si [AR]='010' â†’ 'Tva'. Sinon â†’ 'Vat') |

#### <a id="rm-RM-002"></a>[RM-002] Si [DC] alors V.Payer [BG] sinon [CW])

| Element | Detail |
|---------|--------|
| **Condition** | `[DC]` |
| **Si vrai** | V.Payer [BG] |
| **Si faux** | [CW]) |
| **Variables** | BG (V.Payer) |
| **Expression source** | Expression 52 : `IF([DC],V.Payer [BG],[CW])` |
| **Exemple** | Si [DC] â†’ V.Payer [BG]. Sinon â†’ [CW]) |

#### <a id="rm-RM-003"></a>[RM-003] Si [DD] alors v.Affichage Ligne Gift... [BL] sinon [CY])

| Element | Detail |
|---------|--------|
| **Condition** | `[DD]` |
| **Si vrai** | v.Affichage Ligne Gift... [BL] |
| **Si faux** | [CY]) |
| **Expression source** | Expression 53 : `IF([DD],v.Affichage Ligne Gift... [BL],[CY])` |
| **Exemple** | Si [DD] â†’ v.Affichage Ligne Gift... [BL]. Sinon â†’ [CY]) |

## 6. CONTEXTE

- **Appele par**: [Print Invoice or Ticket (IDE 358)](PVE-IDE-358.md), [Print Invoice or Ticket==NEW (IDE 429)](PVE-IDE-429.md), [Choice Re_Print Invoice (IDE 204)](PVE-IDE-204.md), [Print Invoice or Ticket (IDE 208)](PVE-IDE-208.md), [Print Invoice or Ticket-664 (IDE 209)](PVE-IDE-209.md)
- **Appelle**: 8 programmes | **Tables**: 17 (W:0 R:7 L:13) | **Taches**: 36 | **Expressions**: 54

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 36)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 205 | 205 | Please be patient ... | MDI | 427 | 57 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>205 - Please be patient ...
**Tache** : [205](#t1) | **Type** : MDI | **Dimensions** : 427 x 57 DLU
**Bloc** : Traitement | **Titre IDE** : Please be patient ...

<!-- FORM-DATA:
{
    "width":  427,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  423,
                         "fmt":  "",
                         "name":  "",
                         "h":  29,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  120,
                         "type":  "label",
                         "var":  "",
                         "y":  10,
                         "w":  221,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "7",
                         "text":  "Print in progress ...",
                         "parent":  null
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  29,
                         "w":  423,
                         "fmt":  "",
                         "name":  "",
                         "h":  27,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  114,
                         "type":  "label",
                         "var":  "",
                         "y":  38,
                         "w":  203,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Ticket edition",
                         "parent":  null
                     },
                     {
                         "x":  4,
                         "type":  "image",
                         "var":  "",
                         "y":  2,
                         "w":  72,
                         "fmt":  "",
                         "name":  "",
                         "h":  25,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "205",
    "height":  57
}
-->

## 9. NAVIGATION

Ecran unique: **Please be patient ...**

### 9.3 Structure hierarchique (36 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **205.1** | [**Please be patient ...** (205)](#t1) [mockup](#ecran-t1) | MDI | 427x57 | Traitement |
| 205.1.1 | [Impression reçu change (205.1.1)](#t3) [mockup](#ecran-t3) | MDI | 630x0 | |
| 205.1.2 | [Impression reçu change (205.1.2)](#t4) [mockup](#ecran-t4) | MDI | 1205x0 | |
| 205.1.3 | [Impression reçu change (205.1.2.2)](#t6) [mockup](#ecran-t6) | MDI | 574x0 | |
| 205.1.4 | [GetBookigsInfo (205.1.2.3)](#t7) | - | - | |
| 205.1.5 | [GetBookigsInfo (205.1.2.3.1)](#t8) | - | - | |
| 205.1.6 | [Counter (205.2)](#t10) | MDI | - | |
| 205.1.7 | [Impression reçu change (205.2.1)](#t11) | MDI | - | |
| 205.1.8 | [Impression reçu change (205.2.2)](#t12) | MDI | - | |
| 205.1.9 | [Impression reçu change (205.2.2.2)](#t14) [mockup](#ecran-t14) | MDI | 574x0 | |
| 205.1.10 | [Veuillez patienter ... (205.3.1)](#t16) [mockup](#ecran-t16) | MDI | 426x57 | |
| 205.1.11 | [Veuillez patienter ... (205.3.2)](#t17) [mockup](#ecran-t17) | MDI | 424x56 | |
| 205.1.12 | [Veuillez patienter ... (205.3.2.2)](#t19) [mockup](#ecran-t19) | MDI | 424x56 | |
| 205.1.13 | [Veuillez patienter ... (205.4.1)](#t21) [mockup](#ecran-t21) | MDI | 424x56 | |
| 205.1.14 | [Veuillez patienter ... (205.4.2)](#t22) [mockup](#ecran-t22) | MDI | 1242x399 | |
| 205.1.15 | [Veuillez patienter ... (205.4.2.2)](#t24) [mockup](#ecran-t24) | MDI | 424x56 | |
| 205.1.16 | [GetBookigsInfo (205.4.2.3)](#t25) | - | - | |
| 205.1.17 | [GetBookigsInfo (205.4.2.3.1)](#t26) | - | - | |
| 205.1.18 | [Counter (205.5)](#t28) | MDI | - | |
| 205.1.19 | [Impression reçu change (205.5.1)](#t29) [mockup](#ecran-t29) | MDI | 630x0 | |
| 205.1.20 | [Impression reçu change (205.5.2)](#t30) [mockup](#ecran-t30) | MDI | 574x0 | |
| 205.1.21 | [Impression reçu change (205.5.2.2)](#t32) [mockup](#ecran-t32) | MDI | 574x0 | |
| 205.1.22 | [GetBookigsInfo (205.5.2.3)](#t33) | - | - | |
| 205.1.23 | [GetBookigsInfo (205.5.2.3.1)](#t34) | - | - | |
| 205.1.24 | [Search Gift Pass (205.6)](#t36) | - | - | |
| **205.2** | [**Printer 1** (205.1)](#t2) | MDI | - | Impression |
| 205.2.1 | [Print Tva (205.1.2.1)](#t5) [mockup](#ecran-t5) | - | 506x0 | |
| 205.2.2 | [Print Appointments (205.1.2.4)](#t9) [mockup](#ecran-t9) | - | 506x0 | |
| 205.2.3 | [Print Tva (205.2.2.1)](#t13) [mockup](#ecran-t13) | - | 127x0 | |
| 205.2.4 | [Printer 5 (205.3)](#t15) [mockup](#ecran-t15) | MDI | 424x56 | |
| 205.2.5 | [Print Tva (205.3.2.1)](#t18) [mockup](#ecran-t18) | - | 506x0 | |
| 205.2.6 | [Printer 9 (205.4)](#t20) [mockup](#ecran-t20) | MDI | 424x56 | |
| 205.2.7 | [Print Tva (205.4.2.1)](#t23) [mockup](#ecran-t23) | - | 506x0 | |
| 205.2.8 | [Print Appointments (205.4.2.4)](#t27) [mockup](#ecran-t27) | - | 506x0 | |
| 205.2.9 | [Print Tva (205.5.2.1)](#t31) [mockup](#ecran-t31) | - | 506x0 | |
| 205.2.10 | [Print Appointments (205.5.2.4)](#t35) [mockup](#ecran-t35) | - | 506x0 | |

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

### Tables utilisees (17)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 31 | gm-complet_______gmc |  | DB | R |   |   | 1 |
| 34 | hebergement______heb | Hebergement (chambres) | DB |   |   | L | 1 |
| 36 | client_gm |  | DB |   |   | L | 1 |
| 67 | tables___________tab |  | DB |   |   | L | 1 |
| 69 | initialisation___ini |  | DB |   |   | L | 1 |
| 268 | cc_total_par_type |  | DB | R |   |   | 1 |
| 372 | pv_budget |  | DB |   |   | L | 1 |
| 378 | pv_customer |  | DB | R |   | L | 5 |
| 379 | pv_customer_temp |  | DB |   |   | L | 3 |
| 382 | pv_discount_reasons |  | DB |   |   | L | 1 |
| 400 | pv_cust_rentals |  | DB | R |   | L | 18 |
| 403 | pv_sellers |  | DB | R |   | L | 13 |
| 417 | pv_weight |  | DB |   |   | L | 3 |
| 533 | cumul_mvt_stock_histo | Articles et stock | TMP |   |   | L | 19 |
| 868 | Affectation_Gift_Pass |  | DB | R |   |   | 5 |
| 1539 | Table_1539 |  | MEM | R |   |   | 3 |
| 1548 | Table_1548 |  | MEM |   |   | L | 3 |

### Colonnes par table (8 / 7 tables avec colonnes identifiees)

<details>
<summary>Table 31 - gm-complet_______gmc (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P. Decimal | R | Numeric |
| B | P. PrintAgainExecution | R | Logical |
| C | P. PrintAgainPreview | R | Logical |
| D | P. Facture | R | Numeric |
| E | P.Service | R | Alpha |
| F | P.Nom Pdf Ticket Mobilite | R | Alpha |
| G | P Viens de reedition Mobilite | R | Logical |
| H | p.File_Name_Signature | R | Numeric |
| I | p.NomVendeur | R | Alpha |
| J | p.Vente Mobility | R | Logical |
| K | p.Mail | R | Logical |
| L | p.Num id_transaction AXIS | R | Alpha |
| M | p.Num id_Acceptation | R | Alpha |
| N | V Devise locale | R | Alpha |
| O | V Masque | R | Alpha |
| P | V Masque sans Z | R | Alpha |
| Q | V Date | R | Date |
| R | V En-tête ? | R | Alpha |
| S | V Fin tâche | R | Alpha |
| T | v.Service interne ClubMed? | R | Logical |
| U | V.Fait parti d'un séminaire? | R | Logical |
| V | e.Hebergement_package_A? | R | Logical |
| W | e.Hebergement_package_Z? | R | Logical |
| X | heb_date_debut | R | Date |
| Y | heb_date_fin | R | Date |
| Z | V Imprimante 2 | R | Numeric |
| BA | V Copies | R | Numeric |
| BB | L Avec Réduction | R | Logical |
| BC | L Annulation | R | Logical |
| BD | V Type Paiement | R | Alpha |
| BE | V Masque TM88III | R | Alpha |
| BF | V.Customer | R | Alpha |
| BG | V.Payer | R | Alpha |
| BH | V.Message on Ticket ? | R | Logical |
| BI | V.Message | R | Alpha |
| BJ | V Existe Gift Pass | R | Logical |
| BK | V.Solde  Gift Pass | R | Numeric |
| BL | v.Affichage Ligne Gift Pass? | R | Logical |
| BM | V.Message Solde Gift Pass | R | Alpha |
| BN | V Editer Solde Gift Pass a 0 | R | Logical |
| BO | v Editer TVA | R | Logical |
| BP | v.Liste des TVA taux Réduit | R | Unicode |
| BQ | v.Nombre de taux réduit | R | Numeric |
| BR | v.N° Taux reduit en cours | R | Numeric |
| BS | v.Taux réduit en cours | R | Unicode |
| BT | v.Text à éditer si pdt tx redu | R | Unicode |
| BU | v.Libelle TVA | R | Unicode |
| BV | v.Libelle Montant HT | R | Unicode |
| BW | v.Montant Service | R | Numeric |
| BX | v.Montant Product | R | Numeric |
| BY | v.Article forçage? | R | Logical |
| BZ | v.Edition detail carte ? | R | Logical |
| CA | v.Total pour affich M&E | R | Numeric |

</details>

<details>
<summary>Table 268 - cc_total_par_type (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | V TOTAL | R | Numeric |
| B | v.Total | R | Numeric |
| BD | V Type Paiement | R | Alpha |
| C | v.Total HT | R | Numeric |
| CA | v.Total pour affich M&E | R | Numeric |
| E | v.Total | R | Numeric |
| F | v.Total Montant HT | R | Numeric |

</details>

<details>
<summary>Table 378 - pv_customer (R/L) - 5 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| E | v.Total Ticket | R | Numeric |
| F | v.Total Ticket HT | R | Numeric |
| G | v.Ligne Montant TTC | R | Numeric |
| H | v.Ligne Montant HT | R | Numeric |

</details>

<details>
<summary>Table 400 - pv_cust_rentals (R/L) - 18 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P.CustomerID | R | Numeric |
| BF | V.Customer | R | Alpha |

</details>

<details>
<summary>Table 403 - pv_sellers (R/L) - 13 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | Durée | R | Time |
| B | PassageGroupe | R | Logical |

</details>

<details>
<summary>Table 868 - Affectation_Gift_Pass (R) - 5 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| B | PassageGroupe | R | Logical |
| BJ | V Existe Gift Pass | R | Logical |
| BK | V.Solde  Gift Pass | R | Numeric |
| BL | v.Affichage Ligne Gift Pass? | R | Logical |
| BM | V.Message Solde Gift Pass | R | Alpha |
| BN | V Editer Solde Gift Pass a 0 | R | Logical |
| M | V Ecrire Ligne Gift Pass | R | Numeric |
| S | v.Editer Ligne Gift Pass | R | Logical |

</details>

<details>
<summary>Table 1539 - Table_1539 (R) - 3 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (13)

Variables recues du programme appelant ([Print Invoice or Ticket (IDE 358)](PVE-IDE-358.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P. Decimal | Numeric | - |
| B | P. PrintAgainExecution | Logical | 1x parametre entrant |
| C | P. PrintAgainPreview | Logical | 1x parametre entrant |
| D | P. Facture | Numeric | - |
| E | P.Service | Alpha | 1x parametre entrant |
| F | P.Nom Pdf Ticket Mobilite | Alpha | - |
| G | P Viens de reedition Mobilite | Logical | - |
| H | p.File_Name_Signature | Numeric | - |
| I | p.NomVendeur | Alpha | - |
| J | p.Vente Mobility | Logical | 2x parametre entrant |
| K | p.Mail | Logical | 2x parametre entrant |
| L | p.Num id_transaction AXIS | Alpha | 1x parametre entrant |
| M | p.Num id_Acceptation | Alpha | - |

### 11.2 Variables de session (34)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| N | V Devise locale | Alpha | - |
| O | V Masque | Alpha | 2x session |
| P | V Masque sans Z | Alpha | - |
| Q | V Date | Date | - |
| R | V En-tête ? | Alpha | - |
| S | V Fin tâche | Alpha | - |
| T | v.Service interne ClubMed? | Logical | - |
| U | V.Fait parti d'un séminaire? | Logical | - |
| Z | V Imprimante 2 | Numeric | - |
| BA | V Copies | Numeric | 1x session |
| BD | V Type Paiement | Alpha | - |
| BE | V Masque TM88III | Alpha | - |
| BF | V.Customer | Alpha | - |
| BG | V.Payer | Alpha | 1x session |
| BH | V.Message on Ticket ? | Logical | - |
| BI | V.Message | Alpha | - |
| BJ | V Existe Gift Pass | Logical | - |
| BK | V.Solde  Gift Pass | Numeric | - |
| BL | v.Affichage Ligne Gift Pass? | Logical | - |
| BM | V.Message Solde Gift Pass | Alpha | - |
| BN | V Editer Solde Gift Pass a 0 | Logical | - |
| BO | v Editer TVA | Logical | 1x session |
| BP | v.Liste des TVA taux Réduit | Unicode | - |
| BQ | v.Nombre de taux réduit | Numeric | - |
| BR | v.N° Taux reduit en cours | Numeric | - |
| BS | v.Taux réduit en cours | Unicode | - |
| BT | v.Text à éditer si pdt tx redu | Unicode | - |
| BU | v.Libelle TVA | Unicode | - |
| BV | v.Libelle Montant HT | Unicode | - |
| BW | v.Montant Service | Numeric | - |
| BX | v.Montant Product | Numeric | 2x session |
| BY | v.Article forçage? | Logical | 3x session |
| BZ | v.Edition detail carte ? | Logical | - |
| CA | v.Total pour affich M&E | Numeric | 1x session |

### 11.3 Autres (6)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| V | e.Hebergement_package_A? | Logical | - |
| W | e.Hebergement_package_Z? | Logical | - |
| X | heb_date_debut | Date | 1x refs |
| Y | heb_date_fin | Date | - |
| BB | L Avec Réduction | Logical | - |
| BC | L Annulation | Logical | - |

<details>
<summary>Toutes les 53 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| P0 | **A** | P. Decimal | Numeric |
| P0 | **B** | P. PrintAgainExecution | Logical |
| P0 | **C** | P. PrintAgainPreview | Logical |
| P0 | **D** | P. Facture | Numeric |
| P0 | **E** | P.Service | Alpha |
| P0 | **F** | P.Nom Pdf Ticket Mobilite | Alpha |
| P0 | **G** | P Viens de reedition Mobilite | Logical |
| P0 | **H** | p.File_Name_Signature | Numeric |
| P0 | **I** | p.NomVendeur | Alpha |
| P0 | **J** | p.Vente Mobility | Logical |
| P0 | **K** | p.Mail | Logical |
| P0 | **L** | p.Num id_transaction AXIS | Alpha |
| P0 | **M** | p.Num id_Acceptation | Alpha |
| V. | **N** | V Devise locale | Alpha |
| V. | **O** | V Masque | Alpha |
| V. | **P** | V Masque sans Z | Alpha |
| V. | **Q** | V Date | Date |
| V. | **R** | V En-tête ? | Alpha |
| V. | **S** | V Fin tâche | Alpha |
| V. | **T** | v.Service interne ClubMed? | Logical |
| V. | **U** | V.Fait parti d'un séminaire? | Logical |
| V. | **Z** | V Imprimante 2 | Numeric |
| V. | **BA** | V Copies | Numeric |
| V. | **BD** | V Type Paiement | Alpha |
| V. | **BE** | V Masque TM88III | Alpha |
| V. | **BF** | V.Customer | Alpha |
| V. | **BG** | V.Payer | Alpha |
| V. | **BH** | V.Message on Ticket ? | Logical |
| V. | **BI** | V.Message | Alpha |
| V. | **BJ** | V Existe Gift Pass | Logical |
| V. | **BK** | V.Solde  Gift Pass | Numeric |
| V. | **BL** | v.Affichage Ligne Gift Pass? | Logical |
| V. | **BM** | V.Message Solde Gift Pass | Alpha |
| V. | **BN** | V Editer Solde Gift Pass a 0 | Logical |
| V. | **BO** | v Editer TVA | Logical |
| V. | **BP** | v.Liste des TVA taux Réduit | Unicode |
| V. | **BQ** | v.Nombre de taux réduit | Numeric |
| V. | **BR** | v.N° Taux reduit en cours | Numeric |
| V. | **BS** | v.Taux réduit en cours | Unicode |
| V. | **BT** | v.Text à éditer si pdt tx redu | Unicode |
| V. | **BU** | v.Libelle TVA | Unicode |
| V. | **BV** | v.Libelle Montant HT | Unicode |
| V. | **BW** | v.Montant Service | Numeric |
| V. | **BX** | v.Montant Product | Numeric |
| V. | **BY** | v.Article forçage? | Logical |
| V. | **BZ** | v.Edition detail carte ? | Logical |
| V. | **CA** | v.Total pour affich M&E | Numeric |
| Autre | **V** | e.Hebergement_package_A? | Logical |
| Autre | **W** | e.Hebergement_package_Z? | Logical |
| Autre | **X** | heb_date_debut | Date |
| Autre | **Y** | heb_date_fin | Date |
| Autre | **BB** | L Avec Réduction | Logical |
| Autre | **BC** | L Annulation | Logical |

</details>

## 12. EXPRESSIONS

**54 / 54 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCULATION | 1 | 0 |
| FORMAT | 3 | 0 |
| CONCATENATION | 4 | 0 |
| CONDITION | 15 | 3 |
| CONSTANTE | 8 | 0 |
| DATE | 1 | 0 |
| OTHER | 20 | 0 |
| CAST_LOGIQUE | 1 | 0 |
| REFERENCE_VG | 1 | 0 |

### 12.2 Expressions cles par type

#### CALCULATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 9 | `Left (Trim (V Masque [O]),Len (Trim (V Masque [O]))-1)` | - |

#### FORMAT (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| FORMAT | 32 | `'Gift Pass Balance'&' : '&Str(v.Article forçage? [BY],'N5.2')&' as of '&DStr(Date(),'DD/MM/YY')&' '&TStr(Time(),('HH:MM'))` | - |
| FORMAT | 31 | `'Gift Pass Balance'&' : '&Str(v.Article forçage? [BY],'N7.2')&' as of '&DStr(Date(),'DD/MM/YYYY')&' '&TStr(Time(),('HH:MM:SS'))` | - |
| FORMAT | 37 | `Str(V Editer Solde Gift Pa... [BN],'##')&' / '&VG33&' / '&IF(p.Mail [K],'Mail=oui','Mail=NON')&' / '&IF(p.Vente Mobility [J],'Vente Mobility=OUI','Vente Mobility=NON')` | - |

#### CONCATENATION (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 19 | `Trim([AP])&' '&Trim([AQ])` | - |
| CONCATENATION | 20 | `Trim([AZ])&' '&Trim(V Copies [BA])` | - |
| CONCATENATION | 44 | `Trim('* '&[CI])&MlsTrans('% reduction rate item')` | - |
| CONCATENATION | 15 | `'N'&Right ('## ### ### ###'&Left ('.',heb_date_debut [X])&Fill ('#',heb_date_debut [X]),13)` | - |

#### CONDITION (15 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 52 | `IF([DC],V.Payer [BG],[CW])` | [RM-002](#rm-RM-002) |
| CONDITION | 53 | `IF([DD],v.Affichage Ligne Gift... [BL],[CY])` | [RM-003](#rm-RM-003) |
| CONDITION | 47 | `IF([AR]='010','Tva','Vat')` | [RM-001](#rm-RM-001) |
| CONDITION | 50 | `VG29 AND v.Montant Product [BX] AND (v.Article forçage? [BY]>0 OR (v.Article forçage? [BY]=0 AND v.Total pour affich M&E [CA]))` | - |
| CONDITION | 43 | `[AC]='I'` | - |
| ... | | *+10 autres* | |

#### CONSTANTE (8 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 39 | `'Z'` | - |
| CONSTANTE | 38 | `'A'` | - |
| CONSTANTE | 41 | `201` | - |
| CONSTANTE | 40 | `'W'` | - |
| CONSTANTE | 13 | `1` | - |
| ... | | *+3 autres* | |

#### DATE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| DATE | 11 | `Date ()` | - |

#### OTHER (20 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 30 | `DbDel('{868,3}'DSOURCE,'')` | - |
| OTHER | 34 | `v.Montant Product [BX] AND [CQ]` | - |
| OTHER | 28 | `[AV]` | - |
| OTHER | 26 | `[AT]` | - |
| OTHER | 27 | `[AU]` | - |
| ... | | *+15 autres* | |

#### CAST_LOGIQUE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 29 | `'TRUE'LOG` | - |

#### REFERENCE_VG (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 33 | `VG29` | - |

### 12.3 Toutes les expressions (54)

<details>
<summary>Voir les 54 expressions</summary>

#### CALCULATION (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 9 | `Left (Trim (V Masque [O]),Len (Trim (V Masque [O]))-1)` |

#### FORMAT (3)

| IDE | Expression Decodee |
|-----|-------------------|
| 37 | `Str(V Editer Solde Gift Pa... [BN],'##')&' / '&VG33&' / '&IF(p.Mail [K],'Mail=oui','Mail=NON')&' / '&IF(p.Vente Mobility [J],'Vente Mobility=OUI','Vente Mobility=NON')` |
| 31 | `'Gift Pass Balance'&' : '&Str(v.Article forçage? [BY],'N7.2')&' as of '&DStr(Date(),'DD/MM/YYYY')&' '&TStr(Time(),('HH:MM:SS'))` |
| 32 | `'Gift Pass Balance'&' : '&Str(v.Article forçage? [BY],'N5.2')&' as of '&DStr(Date(),'DD/MM/YY')&' '&TStr(Time(),('HH:MM'))` |

#### CONCATENATION (4)

| IDE | Expression Decodee |
|-----|-------------------|
| 44 | `Trim('* '&[CI])&MlsTrans('% reduction rate item')` |
| 15 | `'N'&Right ('## ### ### ###'&Left ('.',heb_date_debut [X])&Fill ('#',heb_date_debut [X]),13)` |
| 19 | `Trim([AP])&' '&Trim([AQ])` |
| 20 | `Trim([AZ])&' '&Trim(V Copies [BA])` |

#### CONDITION (15)

| IDE | Expression Decodee |
|-----|-------------------|
| 47 | `IF([AR]='010','Tva','Vat')` |
| 48 | `IF([AR]='010','Montant HT','Amount WT')` |
| 52 | `IF([DC],V.Payer [BG],[CW])` |
| 53 | `IF([DD],v.Affichage Ligne Gift... [BL],[CY])` |
| 3 | `V Editer Solde Gift Pa... [BN]=1` |
| 4 | `V Editer Solde Gift Pa... [BN]=4` |
| 5 | `V Editer Solde Gift Pa... [BN]=8` |
| 6 | `V Editer Solde Gift Pa... [BN]=9` |
| 14 | `v Editer TVA [BO]=0` |
| 36 | `VG33='WS' AND NOT (p.Vente Mobility [J]) OR VG33='TB' AND NOT (p.Vente Mobility [J]) AND NOT(p.Mail [K])` |
| 43 | `[AC]='I'` |
| 50 | `VG29 AND v.Montant Product [BX] AND (v.Article forçage? [BY]>0 OR (v.Article forçage? [BY]=0 AND v.Total pour affich M&E [CA]))` |
| 10 | `Right(Trim (V Masque [O]),1)='Z'` |
| 51 | `Trim(p.Num id_transaction AXIS [L])<>'' AND VG133` |
| 54 | `Trim([DJ])<>''` |

#### CONSTANTE (8)

| IDE | Expression Decodee |
|-----|-------------------|
| 12 | `201` |
| 13 | `1` |
| 16 | `'VSERV'` |
| 18 | `'O'` |
| 38 | `'A'` |
| 39 | `'Z'` |
| 40 | `'W'` |
| 41 | `201` |

#### DATE (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 11 | `Date ()` |

#### OTHER (20)

| IDE | Expression Decodee |
|-----|-------------------|
| 1 | `SetCrsr (2)` |
| 2 | `SetCrsr (1)` |
| 7 | `GetParam ('CURRENCYVALUE')` |
| 8 | `GetParam ('AMOUNTFORMAT')` |
| 17 | `P.Service [E]` |
| 21 | `[AG]` |
| 22 | `[AJ]` |
| 23 | `[AK]` |
| 24 | `[AL]` |
| 25 | `[AF]` |
| 26 | `[AT]` |
| 27 | `[AU]` |
| 28 | `[AV]` |
| 30 | `DbDel('{868,3}'DSOURCE,'')` |
| 34 | `v.Montant Product [BX] AND [CQ]` |
| 35 | `[AB]` |
| 42 | `v.Service interne Club... [T]` |
| 45 | `StrTokenCnt([CC],',')` |
| 46 | `StrToken([CC],[CG],',')` |
| 49 | `P. PrintAgainExecution [B] OR P. PrintAgainPreview [C] OR P Viens de reedition M... [G]` |

#### CAST_LOGIQUE (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 29 | `'TRUE'LOG` |

#### REFERENCE_VG (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 33 | `VG29` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Print Invoice or Ticket (IDE 358)](PVE-IDE-358.md) -> **Edition ticket (Tva) LEX (IDE 205)**

Main -> ... -> [Print Invoice or Ticket==NEW (IDE 429)](PVE-IDE-429.md) -> **Edition ticket (Tva) LEX (IDE 205)**

Main -> ... -> [Choice Re_Print Invoice (IDE 204)](PVE-IDE-204.md) -> **Edition ticket (Tva) LEX (IDE 205)**

Main -> ... -> [Print Invoice or Ticket (IDE 208)](PVE-IDE-208.md) -> **Edition ticket (Tva) LEX (IDE 205)**

Main -> ... -> [Print Invoice or Ticket-664 (IDE 209)](PVE-IDE-209.md) -> **Edition ticket (Tva) LEX (IDE 205)**

```mermaid
graph LR
    T205[205 Edition ticket Tva...]
    style T205 fill:#58a6ff
    CC187[187 Main Sale-664]
    style CC187 fill:#8b5cf6
    CC186[186 Main Sale]
    style CC186 fill:#8b5cf6
    CC214[214 Main Sale Sale Bar...]
    style CC214 fill:#8b5cf6
    CC363[363 Main Sale]
    style CC363 fill:#8b5cf6
    CC204[204 Choice Re_Print In...]
    style CC204 fill:#3fb950
    CC209[209 Print Invoice or T...]
    style CC209 fill:#3fb950
    CC208[208 Print Invoice or T...]
    style CC208 fill:#3fb950
    CC429[429 Print Invoice or T...]
    style CC429 fill:#3fb950
    CC358[358 Print Invoice or T...]
    style CC358 fill:#3fb950
    CC186 --> CC204
    CC187 --> CC204
    CC214 --> CC204
    CC363 --> CC204
    CC186 --> CC208
    CC187 --> CC208
    CC214 --> CC208
    CC363 --> CC208
    CC186 --> CC209
    CC187 --> CC209
    CC214 --> CC209
    CC363 --> CC209
    CC186 --> CC358
    CC187 --> CC358
    CC214 --> CC358
    CC363 --> CC358
    CC186 --> CC429
    CC187 --> CC429
    CC214 --> CC429
    CC363 --> CC429
    CC204 --> T205
    CC208 --> T205
    CC209 --> T205
    CC358 --> T205
    CC429 --> T205
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [358](PVE-IDE-358.md) | Print Invoice or Ticket | 2 |
| [429](PVE-IDE-429.md) | Print Invoice or Ticket==NEW | 2 |
| [204](PVE-IDE-204.md) | Choice Re_Print Invoice | 1 |
| [208](PVE-IDE-208.md) | Print Invoice or Ticket | 1 |
| [209](PVE-IDE-209.md) | Print Invoice or Ticket-664 | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T205[205 Edition ticket Tva...]
    style T205 fill:#58a6ff
    C281[281 Creation pied Tick...]
    T205 --> C281
    style C281 fill:#3fb950
    C321[321 Concatène libellé ...]
    T205 --> C321
    style C321 fill:#3fb950
    C161[161 GetAppointment]
    T205 --> C161
    style C161 fill:#3fb950
    C274[274 Set Listing Number]
    T205 --> C274
    style C274 fill:#3fb950
    C275[275 Raz Current Printer]
    T205 --> C275
    style C275 fill:#3fb950
    C276[276 Get Printer]
    T205 --> C276
    style C276 fill:#3fb950
    C279[279 Search for messages]
    T205 --> C279
    style C279 fill:#3fb950
    C283[283 GetPrintert impres...]
    T205 --> C283
    style C283 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [281](PVE-IDE-281.md) | Creation pied Ticket(Tva) | 5 | Impression ticket/document |
| [321](PVE-IDE-321.md) | Concatène libellé Cat/Ss-Cat | 4 | Sous-programme |
| [161](PVE-IDE-161.md) | GetAppointment | 3 | Recuperation donnees |
| [274](PVE-IDE-274.md) | Set Listing Number | 1 | Configuration impression |
| [275](PVE-IDE-275.md) | Raz Current Printer | 1 | Impression ticket/document |
| [276](PVE-IDE-276.md) | Get Printer | 1 | Impression ticket/document |
| [279](PVE-IDE-279.md) | Search  for messages | 1 | Sous-programme |
| [283](PVE-IDE-283.md) | GetPrinter/t impression | 1 | Impression ticket/document |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 1859 | Programme volumineux |
| Expressions | 54 | Logique moderee |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 8 | Dependances moderees |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 1.1% (21 / 1859) | Code sain |
| Regles metier | 3 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (25 taches: 14 ecrans, 11 traitements)

- **Strategie** : Orchestrateur avec 14 ecrans (Razor/React) et 11 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 8 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Impression (11 taches: 10 ecrans, 1 traitement)

- **Strategie** : Templates HTML -> PDF via wkhtmltopdf ou Puppeteer.
- `PrintService` injectable avec choix imprimante

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| [Creation pied Ticket(Tva) (IDE 281)](PVE-IDE-281.md) | Sous-programme | 5x | **CRITIQUE** - Impression ticket/document |
| [Concatène libellé Cat/Ss-Cat (IDE 321)](PVE-IDE-321.md) | Sous-programme | 4x | **CRITIQUE** - Sous-programme |
| [GetAppointment (IDE 161)](PVE-IDE-161.md) | Sous-programme | 3x | **CRITIQUE** - Recuperation donnees |
| [Search  for messages (IDE 279)](PVE-IDE-279.md) | Sous-programme | 1x | Normale - Sous-programme |
| [GetPrinter/t impression (IDE 283)](PVE-IDE-283.md) | Sous-programme | 1x | Normale - Impression ticket/document |
| [Get Printer (IDE 276)](PVE-IDE-276.md) | Sous-programme | 1x | Normale - Impression ticket/document |
| [Set Listing Number (IDE 274)](PVE-IDE-274.md) | Sous-programme | 1x | Normale - Configuration impression |
| [Raz Current Printer (IDE 275)](PVE-IDE-275.md) | Sous-programme | 1x | Normale - Impression ticket/document |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 18:53*
