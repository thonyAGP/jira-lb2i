# PVE IDE 401 - Menu Check IN / Exchange V4

> **Analyse**: Phases 1-4 2026-02-03 19:57 -> 19:57 (12s) | Assemblage 19:57
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PVE |
| IDE Position | 401 |
| Nom Programme | Menu Check IN / Exchange V4 |
| Fichier source | `Prg_401.xml` |
| Dossier IDE | A |
| Taches | 7 (3 ecrans visibles) |
| Tables modifiees | 2 |
| Programmes appeles | 5 |
| :warning: Statut | **ORPHELIN_POTENTIEL** |

## 2. DESCRIPTION FONCTIONNELLE

**Menu Check IN / Exchange V4** assure la gestion complete de ce processus.

Le flux de traitement s'organise en **2 blocs fonctionnels** :

- **Traitement** (6 taches) : traitements metier divers
- **Creation** (1 tache) : insertion d'enregistrements en base (mouvements, prestations)

**Donnees modifiees** : 2 tables en ecriture (pv_sellers_by_week, vente_par_moyen_paiement).

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (6 taches)

- **401** - Check IN / Swap **[[ECRAN]](#ecran-t1)**
- **401.1** - Rental operations **[[ECRAN]](#ecran-t2)**
- **401.1.1** - add rental
- **401.1.2** - Rentals **[[ECRAN]](#ecran-t4)**
- **401.1.3** - Rentals
- **401.1.4** - Confirm **[[ECRAN]](#ecran-t6)**

Delegue a : [    Package pricing (IDE 218)](PVE-IDE-218.md), [Update INV equipment status (IDE 93)](PVE-IDE-93.md), [Update Customer Details (IDE 316)](PVE-IDE-316.md)

#### Phase 2 : Creation (1 tache)

- **401.1.5** - create reponse

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| pv_sellers_by_week | R/**W**/L (4 usages) |  |
| vente_par_moyen_paiement | **W** (1 usages) | Donnees de ventes |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (6 taches)

Traitements internes.

---

#### <a id="t1"></a>401 - Check IN / Swap [[ECRAN]](#ecran-t1)

**Role** : Tache d'orchestration : point d'entree du programme (6 sous-taches). Coordonne l'enchainement des traitements.
**Ecran** : 1988 x 432 DLU (MDI) | [Voir mockup](#ecran-t1)

<details>
<summary>5 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [401.1](#t2) | Rental operations **[[ECRAN]](#ecran-t2)** | Traitement |
| [401.1.1](#t3) | add rental | Traitement |
| [401.1.2](#t4) | Rentals **[[ECRAN]](#ecran-t4)** | Traitement |
| [401.1.3](#t5) | Rentals | Traitement |
| [401.1.4](#t6) | Confirm **[[ECRAN]](#ecran-t6)** | Traitement |

</details>
**Delegue a** : [    Package pricing (IDE 218)](PVE-IDE-218.md), [Update INV equipment status (IDE 93)](PVE-IDE-93.md), [Update Customer Details (IDE 316)](PVE-IDE-316.md)

---

#### <a id="t2"></a>401.1 - Rental operations [[ECRAN]](#ecran-t2)

**Role** : Traitement : Rental operations.
**Ecran** : 1988 x 432 DLU (Type6) | [Voir mockup](#ecran-t2)
**Delegue a** : [    Package pricing (IDE 218)](PVE-IDE-218.md), [Update INV equipment status (IDE 93)](PVE-IDE-93.md), [Update Customer Details (IDE 316)](PVE-IDE-316.md)

---

#### <a id="t3"></a>401.1.1 - add rental

**Role** : Traitement : add rental.
**Delegue a** : [    Package pricing (IDE 218)](PVE-IDE-218.md), [Update INV equipment status (IDE 93)](PVE-IDE-93.md), [Update Customer Details (IDE 316)](PVE-IDE-316.md)

---

#### <a id="t4"></a>401.1.2 - Rentals [[ECRAN]](#ecran-t4)

**Role** : Traitement : Rentals.
**Ecran** : 632 x 197 DLU (Modal) | [Voir mockup](#ecran-t4)
**Delegue a** : [    Package pricing (IDE 218)](PVE-IDE-218.md), [Update INV equipment status (IDE 93)](PVE-IDE-93.md), [Update Customer Details (IDE 316)](PVE-IDE-316.md)

---

#### <a id="t5"></a>401.1.3 - Rentals

**Role** : Traitement : Rentals.
**Delegue a** : [    Package pricing (IDE 218)](PVE-IDE-218.md), [Update INV equipment status (IDE 93)](PVE-IDE-93.md), [Update Customer Details (IDE 316)](PVE-IDE-316.md)

---

#### <a id="t6"></a>401.1.4 - Confirm [[ECRAN]](#ecran-t6)

**Role** : Traitement : Confirm.
**Ecran** : 554 x 157 DLU (MDI) | [Voir mockup](#ecran-t6)
**Variables liees** : H (v.confirm <> classif)
**Delegue a** : [    Package pricing (IDE 218)](PVE-IDE-218.md), [Update INV equipment status (IDE 93)](PVE-IDE-93.md), [Update Customer Details (IDE 316)](PVE-IDE-316.md)


### 3.2 Creation (1 tache)

Insertion de nouveaux enregistrements en base.

---

#### <a id="t7"></a>401.1.5 - create reponse

**Role** : Traitement : create reponse.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: (aucun)
- **Appelle**: 5 programmes | **Tables**: 12 (W:2 R:2 L:10) | **Taches**: 7 | **Expressions**: 4

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (3 / 7)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 401.1 | 401.1 | Rental operations | Type6 | 1988 | 432 | Traitement |
| 2 | 401.1.2 | 401.1.2 | Rentals | Modal | 632 | 197 | Traitement |
| 3 | 401.1.4 | 401.1.4 | Confirm | MDI | 554 | 157 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t2"></a>401.1 - Rental operations
**Tache** : [401.1](#t2) | **Type** : Type6 | **Dimensions** : 1988 x 432 DLU
**Bloc** : Traitement | **Titre IDE** : Rental operations

<!-- FORM-DATA:
{
    "width":  1988,
    "vFactor":  8,
    "type":  "Type6",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  252,
                         "type":  "label",
                         "var":  "",
                         "y":  42,
                         "w":  158,
                         "fmt":  "",
                         "name":  "",
                         "h":  14,
                         "color":  "143",
                         "text":  "IN",
                         "parent":  null
                     },
                     {
                         "x":  1202,
                         "type":  "label",
                         "var":  "",
                         "y":  42,
                         "w":  158,
                         "fmt":  "",
                         "name":  "",
                         "h":  14,
                         "color":  "181",
                         "text":  "OUT",
                         "parent":  null
                     },
                     {
                         "x":  598,
                         "type":  "label",
                         "var":  "",
                         "y":  63,
                         "w":  406,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "181",
                         "text":  "Equipment to be checked \"IN\"",
                         "parent":  3
                     },
                     {
                         "x":  1404,
                         "type":  "label",
                         "var":  "",
                         "y":  270,
                         "w":  464,
                         "fmt":  "",
                         "name":  "",
                         "h":  66,
                         "color":  "189",
                         "text":  "Scan the equipment to be checked in.\r\n\r\nThen select the RETURN action or scan the equipment to be checked out if your customer is swaping equipments.",
                         "parent":  6
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  1980,
                         "fmt":  "",
                         "name":  "",
                         "h":  42,
                         "color":  "189",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  669,
                         "type":  "label",
                         "var":  "",
                         "y":  16,
                         "w":  650,
                         "fmt":  "",
                         "name":  "",
                         "h":  14,
                         "color":  "188",
                         "text":  "EQUIPMENT CHECK IN   \u0026   EXCHANGE",
                         "parent":  6
                     },
                     {
                         "x":  54,
                         "type":  "label",
                         "var":  "",
                         "y":  56,
                         "w":  530,
                         "fmt":  "",
                         "name":  "",
                         "h":  96,
                         "color":  "186",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  74,
                         "type":  "label",
                         "var":  "",
                         "y":  90,
                         "w":  154,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "181",
                         "text":  "Equipment :",
                         "parent":  10
                     },
                     {
                         "x":  74,
                         "type":  "label",
                         "var":  "",
                         "y":  109,
                         "w":  162,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "181",
                         "text":  "Classification :",
                         "parent":  10
                     },
                     {
                         "x":  1338,
                         "type":  "label",
                         "var":  "",
                         "y":  56,
                         "w":  530,
                         "fmt":  "",
                         "name":  "",
                         "h":  96,
                         "color":  "186",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  1358,
                         "type":  "label",
                         "var":  "",
                         "y":  90,
                         "w":  150,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "181",
                         "text":  "Equipment :",
                         "parent":  17
                     },
                     {
                         "x":  1358,
                         "type":  "label",
                         "var":  "",
                         "y":  109,
                         "w":  166,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "181",
                         "text":  "Classification :",
                         "parent":  17
                     },
                     {
                         "x":  850,
                         "type":  "label",
                         "var":  "",
                         "y":  88,
                         "w":  220,
                         "fmt":  "",
                         "name":  "",
                         "h":  31,
                         "color":  "186",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  1010,
                         "type":  "label",
                         "var":  "",
                         "y":  94,
                         "w":  52,
                         "fmt":  "",
                         "name":  "",
                         "h":  23,
                         "color":  "186",
                         "text":  "è",
                         "parent":  23
                     },
                     {
                         "x":  850,
                         "type":  "label",
                         "var":  "",
                         "y":  120,
                         "w":  220,
                         "fmt":  "",
                         "name":  "",
                         "h":  31,
                         "color":  "186",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  858,
                         "type":  "label",
                         "var":  "",
                         "y":  127,
                         "w":  52,
                         "fmt":  "",
                         "name":  "",
                         "h":  22,
                         "color":  "186",
                         "text":  "ç",
                         "parent":  26
                     },
                     {
                         "x":  74,
                         "type":  "label",
                         "var":  "",
                         "y":  163,
                         "w":  258,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "181",
                         "text":  "Status of equipment",
                         "parent":  null
                     },
                     {
                         "x":  54,
                         "type":  "label",
                         "var":  "",
                         "y":  182,
                         "w":  1280,
                         "fmt":  "",
                         "name":  "",
                         "h":  215,
                         "color":  "182",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  198,
                         "type":  "label",
                         "var":  "",
                         "y":  187,
                         "w":  106,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "186",
                         "text":  "Renter",
                         "parent":  32
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  396,
                         "w":  1980,
                         "fmt":  "",
                         "name":  "",
                         "h":  33,
                         "color":  "189",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  150,
                         "type":  "edit",
                         "var":  "",
                         "y":  61,
                         "w":  258,
                         "fmt":  "U10",
                         "name":  "v.serial IN",
                         "h":  27,
                         "color":  "110",
                         "text":  "",
                         "parent":  10
                     },
                     {
                         "x":  414,
                         "type":  "button",
                         "var":  "",
                         "y":  61,
                         "w":  74,
                         "fmt":  "",
                         "name":  "v.zoom",
                         "h":  29,
                         "color":  "",
                         "text":  "",
                         "parent":  10
                     },
                     {
                         "x":  1474,
                         "type":  "edit",
                         "var":  "",
                         "y":  61,
                         "w":  258,
                         "fmt":  "U10",
                         "name":  "v.serial OUT",
                         "h":  27,
                         "color":  "110",
                         "text":  "",
                         "parent":  17
                     },
                     {
                         "x":  250,
                         "type":  "edit",
                         "var":  "",
                         "y":  90,
                         "w":  328,
                         "fmt":  "30",
                         "name":  "",
                         "h":  12,
                         "color":  "181",
                         "text":  "",
                         "parent":  10
                     },
                     {
                         "x":  250,
                         "type":  "edit",
                         "var":  "",
                         "y":  109,
                         "w":  328,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "181",
                         "text":  "",
                         "parent":  10
                     },
                     {
                         "x":  1529,
                         "type":  "edit",
                         "var":  "",
                         "y":  90,
                         "w":  328,
                         "fmt":  "30",
                         "name":  "",
                         "h":  12,
                         "color":  "181",
                         "text":  "",
                         "parent":  17
                     },
                     {
                         "x":  1529,
                         "type":  "edit",
                         "var":  "",
                         "y":  109,
                         "w":  328,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "181",
                         "text":  "",
                         "parent":  17
                     },
                     {
                         "x":  1886,
                         "type":  "image",
                         "var":  "",
                         "y":  7,
                         "w":  96,
                         "fmt":  "",
                         "name":  "",
                         "h":  34,
                         "color":  "",
                         "text":  "",
                         "parent":  6
                     },
                     {
                         "x":  584,
                         "type":  "edit",
                         "var":  "",
                         "y":  59,
                         "w":  752,
                         "fmt":  "",
                         "name":  "",
                         "h":  30,
                         "color":  "191",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  850,
                         "type":  "button",
                         "var":  "",
                         "y":  93,
                         "w":  150,
                         "fmt":  "\u0026EXCHANGE",
                         "name":  "SWAP",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  24
                     },
                     {
                         "x":  916,
                         "type":  "button",
                         "var":  "",
                         "y":  125,
                         "w":  150,
                         "fmt":  "\u0026RETURN",
                         "name":  "RETURN",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  26
                     },
                     {
                         "x":  430,
                         "type":  "button",
                         "var":  "",
                         "y":  155,
                         "w":  154,
                         "fmt":  "Button",
                         "name":  "",
                         "h":  28,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  771,
                         "type":  "edit",
                         "var":  "",
                         "y":  161,
                         "w":  378,
                         "fmt":  "30",
                         "name":  "",
                         "h":  15,
                         "color":  "189",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  310,
                         "type":  "edit",
                         "var":  "",
                         "y":  187,
                         "w":  804,
                         "fmt":  "50",
                         "name":  "v.Renter",
                         "h":  12,
                         "color":  "189",
                         "text":  "",
                         "parent":  32
                     },
                     {
                         "x":  1828,
                         "type":  "button",
                         "var":  "",
                         "y":  401,
                         "w":  154,
                         "fmt":  "\u0026Exit",
                         "name":  "",
                         "h":  28,
                         "color":  "",
                         "text":  "",
                         "parent":  36
                     },
                     {
                         "x":  1462,
                         "type":  "edit",
                         "var":  "",
                         "y":  14,
                         "w":  406,
                         "fmt":  "30",
                         "name":  "",
                         "h":  18,
                         "color":  "174",
                         "text":  "",
                         "parent":  6
                     },
                     {
                         "x":  60,
                         "type":  "subform",
                         "var":  "",
                         "y":  202,
                         "w":  1265,
                         "fmt":  "",
                         "name":  "Rentals",
                         "h":  192,
                         "color":  "",
                         "text":  "",
                         "parent":  32
                     }
                 ],
    "taskId":  "401.1",
    "height":  432
}
-->

<details>
<summary><strong>Champs : 10 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 150,61 | v.serial IN | - | edit |
| 1474,61 | v.serial OUT | - | edit |
| 250,90 | 30 | - | edit |
| 250,109 | (sans nom) | - | edit |
| 1529,90 | 30 | - | edit |
| 1529,109 | (sans nom) | - | edit |
| 584,59 | (sans nom) | - | edit |
| 771,161 | 30 | - | edit |
| 310,187 | v.Renter | - | edit |
| 1462,14 | 30 | - | edit |

</details>

<details>
<summary><strong>Boutons : 5 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| v.zoom | 414,61 | Ouvre la selection |
| EXCHANGE | 850,93 | Modifie l'element |
| RETURN | 916,125 | Bouton fonctionnel |
| Button | 430,155 | Bouton fonctionnel |
| Exit | 1828,401 | Quitte le programme |

</details>

---

#### <a id="ecran-t4"></a>401.1.2 - Rentals
**Tache** : [401.1.2](#t4) | **Type** : Modal | **Dimensions** : 632 x 197 DLU
**Bloc** : Traitement | **Titre IDE** : Rentals

<!-- FORM-DATA:
{
    "width":  632,
    "vFactor":  8,
    "type":  "Modal",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  62,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "110",
                         "w":  459,
                         "y":  3,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  24,
                         "h":  182,
                         "cols":  [
                                      {
                                          "title":  "Product",
                                          "layer":  1,
                                          "w":  63
                                      },
                                      {
                                          "title":  "Classification",
                                          "layer":  2,
                                          "w":  65
                                      },
                                      {
                                          "title":  "Days",
                                          "layer":  3,
                                          "w":  26
                                      },
                                      {
                                          "title":  "Code",
                                          "layer":  4,
                                          "w":  78
                                      },
                                      {
                                          "title":  "Date out",
                                          "layer":  5,
                                          "w":  53
                                      },
                                      {
                                          "title":  "Date due",
                                          "layer":  6,
                                          "w":  54
                                      },
                                      {
                                          "title":  "Date in",
                                          "layer":  7,
                                          "w":  55
                                      },
                                      {
                                          "title":  "Status",
                                          "layer":  8,
                                          "w":  62
                                      }
                                  ],
                         "rows":  8
                     },
                     {
                         "x":  350,
                         "type":  "edit",
                         "var":  "",
                         "y":  16,
                         "w":  50,
                         "fmt":  "",
                         "name":  "",
                         "h":  22,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  66,
                         "type":  "edit",
                         "var":  "",
                         "y":  16,
                         "w":  57,
                         "fmt":  "",
                         "name":  "",
                         "h":  22,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  129,
                         "type":  "edit",
                         "var":  "",
                         "y":  16,
                         "w":  60,
                         "fmt":  "",
                         "name":  "",
                         "h":  22,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  194,
                         "type":  "edit",
                         "var":  "",
                         "y":  16,
                         "w":  21,
                         "fmt":  "3",
                         "name":  "",
                         "h":  22,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  221,
                         "type":  "edit",
                         "var":  "",
                         "y":  16,
                         "w":  71,
                         "fmt":  "U15",
                         "name":  "",
                         "h":  22,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  297,
                         "type":  "edit",
                         "var":  "",
                         "y":  16,
                         "w":  49,
                         "fmt":  "",
                         "name":  "",
                         "h":  22,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  460,
                         "type":  "edit",
                         "var":  "",
                         "y":  16,
                         "w":  51,
                         "fmt":  "",
                         "name":  "",
                         "h":  22,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  520,
                         "type":  "button",
                         "var":  "",
                         "y":  3,
                         "w":  39,
                         "fmt":  "ñ",
                         "name":  "",
                         "h":  91,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  520,
                         "type":  "button",
                         "var":  "",
                         "y":  94,
                         "w":  39,
                         "fmt":  "ò",
                         "name":  "",
                         "h":  91,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  406,
                         "type":  "edit",
                         "var":  "",
                         "y":  16,
                         "w":  50,
                         "fmt":  "10",
                         "name":  "",
                         "h":  22,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     }
                 ],
    "taskId":  "401.1.2",
    "height":  197
}
-->

<details>
<summary><strong>Champs : 8 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 350,16 | (sans nom) | - | edit |
| 66,16 | (sans nom) | - | edit |
| 129,16 | (sans nom) | - | edit |
| 194,16 | 3 | - | edit |
| 221,16 | U15 | - | edit |
| 297,16 | (sans nom) | - | edit |
| 460,16 | (sans nom) | - | edit |
| 406,16 | 10 | - | edit |

</details>

<details>
<summary><strong>Boutons : 2 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| ñ | 520,3 | Bouton fonctionnel |
| ò | 520,94 | Bouton fonctionnel |

</details>

---

#### <a id="ecran-t6"></a>401.1.4 - Confirm
**Tache** : [401.1.4](#t6) | **Type** : MDI | **Dimensions** : 554 x 157 DLU
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
                         "text":  "Exchange the equipments (Charged),Cancel",
                         "parent":  null
                     }
                 ],
    "taskId":  "401.1.4",
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
    VF2[401.1 Rental operations]
    style VF2 fill:#58a6ff
    VF4[401.1.2 Rentals]
    style VF4 fill:#58a6ff
    VF6[401.1.4 Confirm]
    style VF6 fill:#58a6ff
    EXT218[IDE 218 Package pricing]
    style EXT218 fill:#3fb950
    EXT93[IDE 93 Update INV equi...]
    style EXT93 fill:#3fb950
    EXT264[IDE 264 Choix - Equipment]
    style EXT264 fill:#3fb950
    EXT248[IDE 248 Choix - Status]
    style EXT248 fill:#3fb950
    EXT316[IDE 316 Update Custome...]
    style EXT316 fill:#3fb950
    FIN([Sortie])
    style FIN fill:#f85149
    START --> VF2
    VF2 -->|Sous-programme| EXT218
    VF2 -->|Mise a jour donnees| EXT93
    VF2 -->|Selection/consultation| EXT264
    VF2 -->|Selection/consultation| EXT248
    VF2 -->|Mise a jour donnees| EXT316
    EXT316 --> FIN
```

**Detail par enchainement :**

| Depuis | Action | Vers | Retour |
|--------|--------|------|--------|
| Rental operations | Sous-programme | [    Package pricing (IDE 218)](PVE-IDE-218.md) | Retour ecran |
| Rental operations | Mise a jour donnees | [Update INV equipment status (IDE 93)](PVE-IDE-93.md) | Retour ecran |
| Rental operations | Selection/consultation | [Choix - Equipment (IDE 264)](PVE-IDE-264.md) | Retour ecran |
| Rental operations | Selection/consultation | [Choix - Status (IDE 248)](PVE-IDE-248.md) | Retour ecran |
| Rental operations | Mise a jour donnees | [Update Customer Details (IDE 316)](PVE-IDE-316.md) | Retour ecran |

### 9.3 Structure hierarchique (7 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **401.1** | [**Check IN / Swap** (401)](#t1) [mockup](#ecran-t1) | MDI | 1988x432 | Traitement |
| 401.1.1 | [Rental operations (401.1)](#t2) [mockup](#ecran-t2) | Type6 | 1988x432 | |
| 401.1.2 | [add rental (401.1.1)](#t3) | MDI | - | |
| 401.1.3 | [Rentals (401.1.2)](#t4) [mockup](#ecran-t4) | Modal | 632x197 | |
| 401.1.4 | [Rentals (401.1.3)](#t5) | Modal | - | |
| 401.1.5 | [Confirm (401.1.4)](#t6) [mockup](#ecran-t6) | MDI | 554x157 | |
| **401.2** | [**create reponse** (401.1.5)](#t7) | - | - | Creation |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[online]
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

### Tables utilisees (12)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 380 | pv_day_modes |  | DB |   |   | L | 2 |
| 382 | pv_discount_reasons |  | DB | R |   |   | 2 |
| 388 | pv_hotel_days |  | DB |   |   | L | 1 |
| 389 | pv_equipment_inventory |  | DB |   |   | L | 2 |
| 398 | pv_prestations | Prestations/services vendus | DB |   |   | L | 1 |
| 400 | pv_cust_rentals |  | DB |   |   | L | 2 |
| 404 | pv_sellers_by_week |  | DB | R | **W** | L | 4 |
| 413 | pv_tva |  | DB |   |   | L | 1 |
| 419 | realise_articles_caution | Articles et stock | DB |   |   | L | 2 |
| 805 | vente_par_moyen_paiement | Donnees de ventes | DB |   | **W** |   | 1 |
| 806 | sale_channel |  | DB |   |   | L | 1 |
| 807 | plafond_lit |  | DB |   |   | L | 1 |

### Colonnes par table (3 / 3 tables avec colonnes identifiees)

<details>
<summary>Table 382 - pv_discount_reasons (R) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | r.equipment rental | R | Numeric |
| B | v.serial IN | R | Alpha |
| C | v.zoom | R | Alpha |
| D | v.serial OUT | R | Alpha |
| E | R.cust rental | R | Logical |
| F | v.Renter | R | Unicode |
| G | R.Equipment | R | Logical |
| H | v.confirm <> classif | R | Logical |
| I | v.cancel requested | R | Logical |
| J | v.operation choice | R | Alpha |
| K | v.new package id | R | Numeric |
| L | v.access serial in | R | Logical |
| M | v.flagDate | R | Numeric |
| N | V.Valider | R | Logical |

</details>

<details>
<summary>Table 404 - pv_sellers_by_week (R/**W**/L) - 4 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 805 - vente_par_moyen_paiement (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (3)

Variables recues en parametre.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | p.serial in | Alpha | 1x parametre entrant |
| B | p.serial out | Alpha | - |
| C | P Code Fidelisation | Alpha | - |

### 11.2 Variables de session (9)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| E | v.no exit | Logical | 1x session |
| F | v.Renter | Unicode | - |
| H | v.confirm <> classif | Logical | - |
| I | v.cancel requested | Logical | - |
| J | v.operation choice | Alpha | - |
| K | v.new package id | Numeric | - |
| L | v.access serial in | Logical | - |
| M | v.flagDate | Numeric | - |
| N | V.Valider | Logical | - |

### 11.3 Autres (2)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| D | PiForce Exchange | Logical | 1x refs |
| G | R.Equipment | Logical | - |

## 12. EXPRESSIONS

**4 / 4 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| OTHER | 1 | 0 |
| CAST_LOGIQUE | 1 | 0 |
| NEGATION | 2 | 0 |

### 12.2 Expressions cles par type

#### OTHER (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 1 | `p.serial in [A]` | - |

#### CAST_LOGIQUE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 2 | `'FALSE'LOG` | - |

#### NEGATION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| NEGATION | 4 | `NOT (PiForce Exchange [D])` | - |
| NEGATION | 3 | `NOT (v.no exit [E])` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

**Chemin**: (pas de callers directs)

```mermaid
graph LR
    T401[401 Menu Check IN Exch...]
    style T401 fill:#58a6ff
    NONE[Aucun caller]
    NONE -.-> T401
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| - | (aucun) | - |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T401[401 Menu Check IN Exch...]
    style T401 fill:#58a6ff
    C218[218 Package pricing]
    T401 --> C218
    style C218 fill:#3fb950
    C93[93 Update INV equipmen...]
    T401 --> C93
    style C93 fill:#3fb950
    C264[264 Choix - Equipment]
    T401 --> C264
    style C264 fill:#3fb950
    C248[248 Choix - Status]
    T401 --> C248
    style C248 fill:#3fb950
    C316[316 Update Customer De...]
    T401 --> C316
    style C316 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [218](PVE-IDE-218.md) |     Package pricing | 6 | Sous-programme |
| [93](PVE-IDE-93.md) | Update INV equipment status | 3 | Mise a jour donnees |
| [264](PVE-IDE-264.md) | Choix - Equipment | 2 | Selection/consultation |
| [248](PVE-IDE-248.md) | Choix - Status | 1 | Selection/consultation |
| [316](PVE-IDE-316.md) | Update Customer Details | 1 | Mise a jour donnees |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 441 | Taille moyenne |
| Expressions | 4 | Peu de logique |
| Tables WRITE | 2 | Impact faible |
| Sous-programmes | 5 | Peu de dependances |
| Ecrans visibles | 3 | Quelques ecrans |
| Code desactive | 0.2% (1 / 441) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (6 taches: 4 ecrans, 2 traitements)

- **Strategie** : Orchestrateur avec 4 ecrans (Razor/React) et 2 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 5 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Creation (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Repository pattern avec Entity Framework Core.
- Insertion via `IRepository<T>.CreateAsync()`

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| pv_sellers_by_week | Table WRITE (Database) | 1x | Schema + repository |
| vente_par_moyen_paiement | Table WRITE (Database) | 1x | Schema + repository |
| [    Package pricing (IDE 218)](PVE-IDE-218.md) | Sous-programme | 6x | **CRITIQUE** - Sous-programme |
| [Update INV equipment status (IDE 93)](PVE-IDE-93.md) | Sous-programme | 3x | **CRITIQUE** - Mise a jour donnees |
| [Choix - Equipment (IDE 264)](PVE-IDE-264.md) | Sous-programme | 2x | Haute - Selection/consultation |
| [Update Customer Details (IDE 316)](PVE-IDE-316.md) | Sous-programme | 1x | Normale - Mise a jour donnees |
| [Choix - Status (IDE 248)](PVE-IDE-248.md) | Sous-programme | 1x | Normale - Selection/consultation |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 19:57*
