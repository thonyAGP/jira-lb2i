# PVE IDE 360 - Select Product==V4

> **Analyse**: Phases 1-4 2026-02-03 19:46 -> 19:46 (11s) | Assemblage 19:46
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PVE |
| IDE Position | 360 |
| Nom Programme | Select Product==V4 |
| Fichier source | `Prg_360.xml` |
| Dossier IDE | Sauvegarde |
| Taches | 6 (4 ecrans visibles) |
| Tables modifiees | 3 |
| Programmes appeles | 5 |
| :warning: Statut | **ORPHELIN_POTENTIEL** |

## 2. DESCRIPTION FONCTIONNELLE

**Select Product==V4** assure la gestion complete de ce processus.

Le flux de traitement s'organise en **3 blocs fonctionnels** :

- **Impression** (3 taches) : generation de tickets et documents
- **Traitement** (2 taches) : traitements metier divers
- **Consultation** (1 tache) : ecrans de recherche, selection et consultation

**Donnees modifiees** : 3 tables en ecriture (pv_customer_temp, pv_cust_rentals, pv_sellers).

**Logique metier** : 2 regles identifiees couvrant conditions metier, valeurs par defaut.

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Consultation (1 tache)

- **360** - Select Product **[[ECRAN]](#ecran-t1)**

#### Phase 2 : Traitement (2 taches)

- **360.1** - Sub Category **[[ECRAN]](#ecran-t2)**
- **360.1.1** - Product **[[ECRAN]](#ecran-t3)**

Delegue a : [Delete Product (IDE 194)](PVE-IDE-194.md), [  Package Rental date (IDE 195)](PVE-IDE-195.md), [      Package=> account (IDE 196)](PVE-IDE-196.md), [Choice today tomorrow (IDE 202)](PVE-IDE-202.md), [Clavier Numerique (IDE 203)](PVE-IDE-203.md)

#### Phase 3 : Impression (3 taches)

- **360.1.1.1** - Ticket **[[ECRAN]](#ecran-t4)**
- **360.1.1.1.1** - Vidage Ticket
- **360.2** - Vidage Ticket

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| pv_cust_rentals | **W** (3 usages) |  |
| pv_sellers | **W**/L (2 usages) |  |
| pv_customer_temp | **W** (1 usages) |  |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Consultation (1 tache)

Ecrans de recherche et consultation.

---

#### <a id="t1"></a>360 - Select Product [[ECRAN]](#ecran-t1)

**Role** : Traitement : Select Product.
**Ecran** : 1414 x 308 DLU (Type6) | [Voir mockup](#ecran-t1)


### 3.2 Traitement (2 taches)

Traitements internes.

---

#### <a id="t2"></a>360.1 - Sub Category [[ECRAN]](#ecran-t2)

**Role** : Traitement : Sub Category.
**Ecran** : 444 x 218 DLU | [Voir mockup](#ecran-t2)
**Delegue a** : [Delete Product (IDE 194)](PVE-IDE-194.md), [  Package Rental date (IDE 195)](PVE-IDE-195.md), [      Package=> account (IDE 196)](PVE-IDE-196.md)

---

#### <a id="t3"></a>360.1.1 - Product [[ECRAN]](#ecran-t3)

**Role** : Traitement : Product.
**Ecran** : 611 x 216 DLU | [Voir mockup](#ecran-t3)
**Delegue a** : [Delete Product (IDE 194)](PVE-IDE-194.md), [  Package Rental date (IDE 195)](PVE-IDE-195.md), [      Package=> account (IDE 196)](PVE-IDE-196.md)


### 3.3 Impression (3 taches)

Generation des documents et tickets.

---

#### <a id="t4"></a>360.1.1.1 - Ticket [[ECRAN]](#ecran-t4)

**Role** : Generation du document : Ticket.
**Ecran** : 170 x 294 DLU | [Voir mockup](#ecran-t4)
**Variables liees** : K (v.TotalTicket)

---

#### <a id="t5"></a>360.1.1.1.1 - Vidage Ticket

**Role** : Generation du document : Vidage Ticket.
**Variables liees** : K (v.TotalTicket)

---

#### <a id="t6"></a>360.2 - Vidage Ticket

**Role** : Generation du document : Vidage Ticket.
**Variables liees** : K (v.TotalTicket)


## 5. REGLES METIER

2 regles identifiees:

### Autres (2 regles)

#### <a id="rm-RM-001"></a>[RM-001] Valeur par defaut si Trim(v.Qté [F]) est vide

| Element | Detail |
|---------|--------|
| **Condition** | `Trim(v.Qté [F])=''` |
| **Si vrai** | '01' |
| **Si faux** | v.Qté [F]) |
| **Variables** | F (v.Qté) |
| **Expression source** | Expression 1 : `IF(Trim(v.Qté [F])='','01',v.Qté [F])` |
| **Exemple** | Si Trim(v.Qté [F])='' â†’ '01'. Sinon â†’ v.Qté [F]) |

#### <a id="rm-RM-002"></a>[RM-002] Si VG41 alors 'p.V.valid_all [C]'FORM sinon 'p.Masque_Sans_Z [B]'FORM)

| Element | Detail |
|---------|--------|
| **Condition** | `VG41` |
| **Si vrai** | 'p.V.valid_all [C]'FORM |
| **Si faux** | 'p.Masque_Sans_Z [B]'FORM) |
| **Variables** | B (p.Masque_Sans_Z), C (p.V.valid_all) |
| **Expression source** | Expression 5 : `IF(VG41,'p.V.valid_all [C]'FORM,'p.Masque_Sans_Z [B]'FORM)` |
| **Exemple** | Si VG41 â†’ 'p.V.valid_all [C]'FORM. Sinon â†’ 'p.Masque_Sans_Z [B]'FORM) |

## 6. CONTEXTE

- **Appele par**: (aucun)
- **Appelle**: 5 programmes | **Tables**: 6 (W:3 R:1 L:3) | **Taches**: 6 | **Expressions**: 42

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (4 / 6)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 360 | 360 | Select Product | Type6 | 1414 | 308 | Consultation |
| 2 | 360.1 | 360.1 | Sub Category | Type0 | 444 | 218 | Traitement |
| 3 | 360.1.1 | 360.1.1 | Product | Type0 | 611 | 216 | Traitement |
| 4 | 360.1.1.1 | 360.1.1.1 | Ticket | Type0 | 170 | 294 | Impression |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>360 - Select Product
**Tache** : [360](#t1) | **Type** : Type6 | **Dimensions** : 1414 x 308 DLU
**Bloc** : Consultation | **Titre IDE** : Select Product

<!-- FORM-DATA:
{
    "width":  1414,
    "vFactor":  8,
    "type":  "Type6",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  1412,
                         "fmt":  "",
                         "name":  "",
                         "h":  31,
                         "color":  "189",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  40,
                         "type":  "label",
                         "var":  "",
                         "y":  11,
                         "w":  282,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "186",
                         "text":  "Select your product",
                         "parent":  1
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  31,
                         "w":  246,
                         "fmt":  "",
                         "name":  "",
                         "h":  231,
                         "color":  "183",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  248,
                         "type":  "label",
                         "var":  "",
                         "y":  31,
                         "w":  1164,
                         "fmt":  "",
                         "name":  "",
                         "h":  231,
                         "color":  "183",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  254,
                         "type":  "label",
                         "var":  "",
                         "y":  33,
                         "w":  180,
                         "fmt":  "",
                         "name":  "",
                         "h":  7,
                         "color":  "183",
                         "text":  "Category",
                         "parent":  null
                     },
                     {
                         "x":  554,
                         "type":  "label",
                         "var":  "",
                         "y":  33,
                         "w":  142,
                         "fmt":  "",
                         "name":  "",
                         "h":  7,
                         "color":  "183",
                         "text":  "Sub Category",
                         "parent":  null
                     },
                     {
                         "x":  870,
                         "type":  "label",
                         "var":  "",
                         "y":  33,
                         "w":  142,
                         "fmt":  "",
                         "name":  "",
                         "h":  7,
                         "color":  "183",
                         "text":  "Product",
                         "parent":  null
                     },
                     {
                         "x":  1214,
                         "type":  "label",
                         "var":  "",
                         "y":  33,
                         "w":  142,
                         "fmt":  "",
                         "name":  "",
                         "h":  7,
                         "color":  "183",
                         "text":  "Ticket",
                         "parent":  null
                     },
                     {
                         "x":  16,
                         "type":  "label",
                         "var":  "",
                         "y":  40,
                         "w":  70,
                         "fmt":  "",
                         "name":  "",
                         "h":  15,
                         "color":  "187",
                         "text":  "Stock",
                         "parent":  4
                     },
                     {
                         "x":  16,
                         "type":  "label",
                         "var":  "",
                         "y":  61,
                         "w":  70,
                         "fmt":  "",
                         "name":  "",
                         "h":  15,
                         "color":  "187",
                         "text":  "Quantity",
                         "parent":  4
                     },
                     {
                         "x":  16,
                         "type":  "label",
                         "var":  "",
                         "y":  82,
                         "w":  70,
                         "fmt":  "",
                         "name":  "",
                         "h":  15,
                         "color":  "187",
                         "text":  "Price",
                         "parent":  4
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  282,
                         "w":  1412,
                         "fmt":  "",
                         "name":  "",
                         "h":  26,
                         "color":  "6",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  250,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "183",
                         "w":  190,
                         "y":  42,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  24,
                         "h":  218,
                         "cols":  [
                                      {
                                          "title":  "label",
                                          "layer":  1,
                                          "w":  184
                                      }
                                  ],
                         "rows":  1
                     },
                     {
                         "x":  1338,
                         "type":  "image",
                         "var":  "",
                         "y":  2,
                         "w":  70,
                         "fmt":  "",
                         "name":  "",
                         "h":  27,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  122,
                         "type":  "edit",
                         "var":  "",
                         "y":  40,
                         "w":  108,
                         "fmt":  "",
                         "name":  "v.Stock",
                         "h":  15,
                         "color":  "183",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  254,
                         "type":  "button",
                         "var":  "",
                         "y":  43,
                         "w":  180,
                         "fmt":  "",
                         "name":  "label",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  19
                     },
                     {
                         "x":  440,
                         "type":  "button",
                         "var":  "",
                         "y":  42,
                         "w":  72,
                         "fmt":  "ñ",
                         "name":  "UP",
                         "h":  108,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  516,
                         "type":  "subform",
                         "var":  "",
                         "y":  43,
                         "w":  896,
                         "fmt":  "",
                         "name":  "SF_CATEG",
                         "h":  218,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  122,
                         "type":  "edit",
                         "var":  "",
                         "y":  61,
                         "w":  108,
                         "fmt":  "",
                         "name":  "v.Qté",
                         "h":  15,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  122,
                         "type":  "edit",
                         "var":  "",
                         "y":  82,
                         "w":  108,
                         "fmt":  "12",
                         "name":  "v.PrixSaisie",
                         "h":  15,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  8,
                         "type":  "button",
                         "var":  "",
                         "y":  110,
                         "w":  72,
                         "fmt":  "1",
                         "name":  "1",
                         "h":  27,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  88,
                         "type":  "button",
                         "var":  "",
                         "y":  110,
                         "w":  72,
                         "fmt":  "2",
                         "name":  "2",
                         "h":  27,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  166,
                         "type":  "button",
                         "var":  "",
                         "y":  110,
                         "w":  72,
                         "fmt":  "3",
                         "name":  "3",
                         "h":  27,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  8,
                         "type":  "button",
                         "var":  "",
                         "y":  140,
                         "w":  72,
                         "fmt":  "4",
                         "name":  "4",
                         "h":  27,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  88,
                         "type":  "button",
                         "var":  "",
                         "y":  140,
                         "w":  72,
                         "fmt":  "5",
                         "name":  "5",
                         "h":  27,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  166,
                         "type":  "button",
                         "var":  "",
                         "y":  140,
                         "w":  72,
                         "fmt":  "6",
                         "name":  "6",
                         "h":  27,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  440,
                         "type":  "button",
                         "var":  "",
                         "y":  150,
                         "w":  72,
                         "fmt":  "ò",
                         "name":  "DOWN",
                         "h":  110,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  8,
                         "type":  "button",
                         "var":  "",
                         "y":  170,
                         "w":  72,
                         "fmt":  "7",
                         "name":  "7",
                         "h":  27,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  88,
                         "type":  "button",
                         "var":  "",
                         "y":  170,
                         "w":  72,
                         "fmt":  "8",
                         "name":  "8",
                         "h":  27,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  166,
                         "type":  "button",
                         "var":  "",
                         "y":  170,
                         "w":  72,
                         "fmt":  "9",
                         "name":  "9",
                         "h":  27,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  8,
                         "type":  "button",
                         "var":  "",
                         "y":  200,
                         "w":  72,
                         "fmt":  "Clear",
                         "name":  "Clear",
                         "h":  57,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  88,
                         "type":  "button",
                         "var":  "",
                         "y":  200,
                         "w":  72,
                         "fmt":  "0",
                         "name":  "0",
                         "h":  27,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  166,
                         "type":  "button",
                         "var":  "",
                         "y":  200,
                         "w":  72,
                         "fmt":  "Del",
                         "name":  "Del",
                         "h":  57,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  88,
                         "type":  "button",
                         "var":  "",
                         "y":  230,
                         "w":  72,
                         "fmt":  ".",
                         "name":  "POINT",
                         "h":  27,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  646,
                         "type":  "edit",
                         "var":  "",
                         "y":  268,
                         "w":  602,
                         "fmt":  "",
                         "name":  "V.Désigantion",
                         "h":  11,
                         "color":  "183",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  1280,
                         "type":  "edit",
                         "var":  "",
                         "y":  268,
                         "w":  112,
                         "fmt":  "N8.3Z",
                         "name":  "v.TotalTicket",
                         "h":  11,
                         "color":  "183",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  232,
                         "type":  "button",
                         "var":  "",
                         "y":  286,
                         "w":  382,
                         "fmt":  "Cancel Order",
                         "name":  "CANCEL",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  628,
                         "type":  "button",
                         "var":  "",
                         "y":  286,
                         "w":  382,
                         "fmt":  "Validate Order",
                         "name":  "VALID",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  1024,
                         "type":  "button",
                         "var":  "",
                         "y":  286,
                         "w":  382,
                         "fmt":  "Make full payment",
                         "name":  "FULL",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "360",
    "height":  308
}
-->

<details>
<summary><strong>Champs : 5 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 122,40 | v.Stock | - | edit |
| 122,61 | v.Qté | - | edit |
| 122,82 | v.PrixSaisie | - | edit |
| 646,268 | V.Désigantion | - | edit |
| 1280,268 | v.TotalTicket | - | edit |

</details>

<details>
<summary><strong>Boutons : 19 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| label | 254,43 | Bouton fonctionnel |
| ñ | 440,42 | Bouton fonctionnel |
| 1 | 8,110 | Bouton fonctionnel |
| 2 | 88,110 | Bouton fonctionnel |
| 3 | 166,110 | Bouton fonctionnel |
| 4 | 8,140 | Bouton fonctionnel |
| 5 | 88,140 | Bouton fonctionnel |
| 6 | 166,140 | Bouton fonctionnel |
| ò | 440,150 | Bouton fonctionnel |
| 7 | 8,170 | Bouton fonctionnel |
| 8 | 88,170 | Bouton fonctionnel |
| 9 | 166,170 | Bouton fonctionnel |
| Clear | 8,200 | Bouton fonctionnel |
| 0 | 88,200 | Bouton fonctionnel |
| Del | 166,200 | Appel [Delete Product (IDE 194)](PVE-IDE-194.md) |
| . | 88,230 | Bouton fonctionnel |
| Cancel Order | 232,286 | Annule et retour au menu |
| Validate Order | 628,286 | Valide la saisie et enregistre |
| Make full payment | 1024,286 | Bouton fonctionnel |

</details>

---

#### <a id="ecran-t2"></a>360.1 - Sub Category
**Tache** : [360.1](#t2) | **Type** : Type0 | **Dimensions** : 444 x 218 DLU
**Bloc** : Traitement | **Titre IDE** : Sub Category

<!-- FORM-DATA:
{
    "width":  444,
    "vFactor":  8,
    "type":  "Type0",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "183",
                         "w":  99,
                         "y":  0,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  24,
                         "h":  216,
                         "cols":  [
                                      {
                                          "title":  "",
                                          "layer":  1,
                                          "w":  96
                                      }
                                  ],
                         "rows":  1
                     },
                     {
                         "x":  2,
                         "type":  "button",
                         "var":  "",
                         "y":  1,
                         "w":  94,
                         "fmt":  "",
                         "name":  "SUB_CAT",
                         "h":  23,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  99,
                         "type":  "button",
                         "var":  "",
                         "y":  0,
                         "w":  36,
                         "fmt":  "ñ",
                         "name":  "UP",
                         "h":  108,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  135,
                         "type":  "subform",
                         "var":  "",
                         "y":  0,
                         "w":  306,
                         "fmt":  "",
                         "name":  "SF_Product",
                         "h":  216,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  99,
                         "type":  "button",
                         "var":  "",
                         "y":  108,
                         "w":  36,
                         "fmt":  "ò",
                         "name":  "DOWN",
                         "h":  108,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "360.1",
    "height":  218
}
-->

<details>
<summary><strong>Boutons : 3 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| SUB_CAT | 2,1 | Bouton fonctionnel |
| ñ | 99,0 | Bouton fonctionnel |
| ò | 99,108 | Bouton fonctionnel |

</details>

---

#### <a id="ecran-t3"></a>360.1.1 - Product
**Tache** : [360.1.1](#t3) | **Type** : Type0 | **Dimensions** : 611 x 216 DLU
**Bloc** : Traitement | **Titre IDE** : Product

<!-- FORM-DATA:
{
    "width":  611,
    "vFactor":  8,
    "type":  "Type0",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "183",
                         "w":  290,
                         "y":  0,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  24,
                         "h":  216,
                         "cols":  [
                                      {
                                          "title":  "",
                                          "layer":  1,
                                          "w":  222
                                      },
                                      {
                                          "title":  "",
                                          "layer":  2,
                                          "w":  62
                                      }
                                  ],
                         "rows":  2
                     },
                     {
                         "x":  5,
                         "type":  "button",
                         "var":  "",
                         "y":  2,
                         "w":  218,
                         "fmt":  "",
                         "name":  "SAVE",
                         "h":  23,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  229,
                         "type":  "edit",
                         "var":  "",
                         "y":  3,
                         "w":  58,
                         "fmt":  "N12.3C",
                         "name":  "prix_de_vente",
                         "h":  22,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  290,
                         "type":  "button",
                         "var":  "",
                         "y":  0,
                         "w":  72,
                         "fmt":  "ñ",
                         "name":  "UP",
                         "h":  108,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  362,
                         "type":  "subform",
                         "var":  "",
                         "y":  1,
                         "w":  249,
                         "fmt":  "",
                         "name":  "SF_Ticket",
                         "h":  214,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  290,
                         "type":  "button",
                         "var":  "",
                         "y":  108,
                         "w":  72,
                         "fmt":  "ò",
                         "name":  "DOWN",
                         "h":  107,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "360.1.1",
    "height":  216
}
-->

<details>
<summary><strong>Champs : 1 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 229,3 | prix_de_vente | - | edit |

</details>

<details>
<summary><strong>Boutons : 3 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| SAVE | 5,2 | Bouton fonctionnel |
| ñ | 290,0 | Bouton fonctionnel |
| ò | 290,108 | Bouton fonctionnel |

</details>

---

#### <a id="ecran-t4"></a>360.1.1.1 - Ticket
**Tache** : [360.1.1.1](#t4) | **Type** : Type0 | **Dimensions** : 170 x 294 DLU
**Bloc** : Impression | **Titre IDE** : Ticket

<!-- FORM-DATA:
{
    "width":  170,
    "vFactor":  8,
    "type":  "Type0",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "6",
                         "w":  173,
                         "y":  2,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  32,
                         "h":  293,
                         "cols":  [
                                      {
                                          "title":  "",
                                          "layer":  1,
                                          "w":  20
                                      },
                                      {
                                          "title":  "",
                                          "layer":  2,
                                          "w":  116
                                      },
                                      {
                                          "title":  "",
                                          "layer":  3,
                                          "w":  33
                                      }
                                  ],
                         "rows":  3
                     },
                     {
                         "x":  3,
                         "type":  "edit",
                         "var":  "",
                         "y":  7,
                         "w":  16,
                         "fmt":  "N9",
                         "name":  "cpk_quantity",
                         "h":  27,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  20,
                         "type":  "button",
                         "var":  "",
                         "y":  3,
                         "w":  118,
                         "fmt":  "",
                         "name":  "DELETE",
                         "h":  31,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  138,
                         "type":  "edit",
                         "var":  "",
                         "y":  7,
                         "w":  31,
                         "fmt":  "N10C",
                         "name":  "price",
                         "h":  27,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     }
                 ],
    "taskId":  "360.1.1.1",
    "height":  294
}
-->

<details>
<summary><strong>Champs : 2 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 3,7 | cpk_quantity | - | edit |
| 138,7 | price | - | edit |

</details>

<details>
<summary><strong>Boutons : 1 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| DELETE | 20,3 | Appel [Delete Product (IDE 194)](PVE-IDE-194.md) |

</details>

## 9. NAVIGATION

### 9.1 Enchainement des ecrans

```mermaid
flowchart TD
    START([Entree])
    style START fill:#3fb950
    VF1[360 Select Product]
    style VF1 fill:#58a6ff
    VF2[360.1 Sub Category]
    style VF2 fill:#58a6ff
    VF3[360.1.1 Product]
    style VF3 fill:#58a6ff
    VF4[360.1.1.1 Ticket]
    style VF4 fill:#58a6ff
    EXT194[IDE 194 Delete Product]
    style EXT194 fill:#3fb950
    EXT195[IDE 195 Package Rental...]
    style EXT195 fill:#3fb950
    EXT196[IDE 196 Package= account]
    style EXT196 fill:#3fb950
    EXT202[IDE 202 Choice today t...]
    style EXT202 fill:#3fb950
    EXT203[IDE 203 Clavier Numerique]
    style EXT203 fill:#3fb950
    FIN([Sortie])
    style FIN fill:#f85149
    START --> VF1
    VF1 -->|Sous-programme| EXT194
    VF1 -->|Sous-programme| EXT195
    VF1 -->|Sous-programme| EXT196
    VF1 -->|Sous-programme| EXT202
    VF1 -->|Sous-programme| EXT203
    EXT203 --> FIN
```

**Detail par enchainement :**

| Depuis | Action | Vers | Retour |
|--------|--------|------|--------|
| Select Product | Sous-programme | [Delete Product (IDE 194)](PVE-IDE-194.md) | Retour ecran |
| Select Product | Sous-programme | [  Package Rental date (IDE 195)](PVE-IDE-195.md) | Retour ecran |
| Select Product | Sous-programme | [      Package=> account (IDE 196)](PVE-IDE-196.md) | Retour ecran |
| Select Product | Sous-programme | [Choice today tomorrow (IDE 202)](PVE-IDE-202.md) | Retour ecran |
| Select Product | Sous-programme | [Clavier Numerique (IDE 203)](PVE-IDE-203.md) | Retour ecran |

### 9.3 Structure hierarchique (6 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **360.1** | [**Select Product** (360)](#t1) [mockup](#ecran-t1) | Type6 | 1414x308 | Consultation |
| **360.2** | [**Sub Category** (360.1)](#t2) [mockup](#ecran-t2) | - | 444x218 | Traitement |
| 360.2.1 | [Product (360.1.1)](#t3) [mockup](#ecran-t3) | - | 611x216 | |
| **360.3** | [**Ticket** (360.1.1.1)](#t4) [mockup](#ecran-t4) | - | 170x294 | Impression |
| 360.3.1 | [Vidage Ticket (360.1.1.1.1)](#t5) | - | - | |
| 360.3.2 | [Vidage Ticket (360.2)](#t6) | - | - | |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Sub Category]
    UPDATE[MAJ 3 tables]
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
| 77 | articles_________art | Articles et stock | DB | R |   |   | 1 |
| 379 | pv_customer_temp |  | DB |   | **W** |   | 1 |
| 380 | pv_day_modes |  | DB |   |   | L | 1 |
| 400 | pv_cust_rentals |  | DB |   | **W** |   | 3 |
| 403 | pv_sellers |  | DB |   | **W** | L | 2 |
| 413 | pv_tva |  | DB |   |   | L | 2 |

### Colonnes par table (4 / 4 tables avec colonnes identifiees)

<details>
<summary>Table 77 - articles_________art (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | p.Category | R | Numeric |
| B | v.Start_Rental | R | Date |
| C | v.End_Rental | R | Date |
| D | T Article | R | Logical |
| E | T Product | R | Logical |

</details>

<details>
<summary>Table 379 - pv_customer_temp (**W**) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | p.Customer_Id | W | Numeric |
| B | p.Masque_Sans_Z | W | Alpha |
| C | p.V.valid_all | W | Logical |
| D | P.date debut sejour | W | Date |
| E | v.Stock | W | Numeric |
| F | v.Qté | W | Alpha |
| G | V.Désigantion | W | Alpha |
| H | v.Fin | W | Logical |
| I | v.StopDelete | W | Logical |
| J | RetourQuestion | W | Numeric |
| K | v.TotalTicket | W | Numeric |
| L | v.PrixSaisie | W | Alpha |
| M | v.PrixZero | W | Logical |
| N | v.Cat | W | Numeric |
| O | v.Sub_Cat | W | Numeric |
| P | v.Prod_ID | W | Numeric |
| Q | T S/Catégorie | W | Logical |

</details>

<details>
<summary>Table 400 - pv_cust_rentals (**W**) - 3 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | p.Customer_Id | W | Numeric |

</details>

<details>
<summary>Table 403 - pv_sellers (**W**/L) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | p.Category | W | Numeric |
| B | p.Sub_Category | W | Numeric |
| C | v.Retour Massage | W | Numeric |
| D | v.DbleClick | W | Logical |
| E | V.today ? | W | Logical |
| F | V.start rental date | W | Date |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (4)

Variables recues en parametre.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | p.Customer_Id | Numeric | - |
| B | p.Masque_Sans_Z | Alpha | 2x parametre entrant |
| C | p.V.valid_all | Logical | 1x parametre entrant |
| D | P.date debut sejour | Date | - |

### 11.2 Variables de session (11)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| E | v.Stock | Numeric | - |
| F | v.Qté | Alpha | 14x session |
| G | V.Désigantion | Alpha | - |
| H | v.Fin | Logical | 1x session |
| I | v.StopDelete | Logical | - |
| K | v.TotalTicket | Numeric | 2x session |
| L | v.PrixSaisie | Alpha | 12x session |
| M | v.PrixZero | Logical | 2x session |
| N | v.Cat | Numeric | - |
| O | v.Sub_Cat | Numeric | - |
| P | v.Prod_ID | Numeric | - |

### 11.3 Autres (2)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| J | RetourQuestion | Numeric | 1x refs |
| Q | T S/Catégorie | Logical | 1x refs |

<details>
<summary>Toutes les 17 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| P0 | **A** | p.Customer_Id | Numeric |
| P0 | **B** | p.Masque_Sans_Z | Alpha |
| P0 | **C** | p.V.valid_all | Logical |
| P0 | **D** | P.date debut sejour | Date |
| V. | **E** | v.Stock | Numeric |
| V. | **F** | v.Qté | Alpha |
| V. | **G** | V.Désigantion | Alpha |
| V. | **H** | v.Fin | Logical |
| V. | **I** | v.StopDelete | Logical |
| V. | **K** | v.TotalTicket | Numeric |
| V. | **L** | v.PrixSaisie | Alpha |
| V. | **M** | v.PrixZero | Logical |
| V. | **N** | v.Cat | Numeric |
| V. | **O** | v.Sub_Cat | Numeric |
| V. | **P** | v.Prod_ID | Numeric |
| Autre | **J** | RetourQuestion | Numeric |
| Autre | **Q** | T S/Catégorie | Logical |

</details>

## 12. EXPRESSIONS

**42 / 42 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONDITION | 6 | 2 |
| CONSTANTE | 2 | 0 |
| CAST_LOGIQUE | 4 | 0 |
| NEGATION | 1 | 0 |
| OTHER | 4 | 0 |
| STRING | 3 | 0 |
| CONCATENATION | 22 | 0 |

### 12.2 Expressions cles par type

#### CONDITION (6 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 5 | `IF(VG41,'p.V.valid_all [C]'FORM,'p.Masque_Sans_Z [B]'FORM)` | [RM-002](#rm-RM-002) |
| CONDITION | 1 | `IF(Trim(v.Qté [F])='','01',v.Qté [F])` | [RM-001](#rm-RM-001) |
| CONDITION | 41 | `RetourQuestion [J]=6` | - |
| CONDITION | 2 | `Trim(v.Qté [F])='01'` | - |
| CONDITION | 10 | `v.TotalTicket [K]>0` | - |
| ... | | *+1 autres* | |

#### CONSTANTE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 38 | `''` | - |
| CONSTANTE | 9 | `0` | - |

#### CAST_LOGIQUE (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 15 | `'FALSE'LOG` | - |
| CAST_LOGIQUE | 42 | `'TRUE'LOG` | - |
| CAST_LOGIQUE | 3 | `v.Fin [H]='TRUE'LOG` | - |
| CAST_LOGIQUE | 4 | `'TRUE'LOG` | - |

#### NEGATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| NEGATION | 6 | `NOT v.PrixZero [M]` | - |

#### OTHER (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 12 | `[T]` | - |
| OTHER | 13 | `GetParam ('SERVICE')` | - |
| OTHER | 7 | `v.PrixZero [M]` | - |
| OTHER | 8 | `T S/Catégorie [Q]` | - |

#### STRING (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| STRING | 40 | `Del (v.PrixSaisie [L],Len (Trim(v.PrixSaisie [L])),1)` | - |
| STRING | 39 | `Del (v.Qté [F],Len (Trim(v.Qté [F])),1)` | - |
| STRING | 14 | `Trim(p.Masque_Sans_Z [B])` | - |

#### CONCATENATION (22 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 30 | `Trim(v.Qté [F])&'7'` | - |
| CONCATENATION | 31 | `Trim(v.PrixSaisie [L])&'7'` | - |
| CONCATENATION | 29 | `Trim(v.PrixSaisie [L])&'6'` | - |
| CONCATENATION | 27 | `Trim(v.PrixSaisie [L])&'5'` | - |
| CONCATENATION | 28 | `Trim(v.Qté [F])&'6'` | - |
| ... | | *+17 autres* | |

### 12.3 Toutes les expressions (42)

<details>
<summary>Voir les 42 expressions</summary>

#### CONDITION (6)

| IDE | Expression Decodee |
|-----|-------------------|
| 1 | `IF(Trim(v.Qté [F])='','01',v.Qté [F])` |
| 5 | `IF(VG41,'p.V.valid_all [C]'FORM,'p.Masque_Sans_Z [B]'FORM)` |
| 10 | `v.TotalTicket [K]>0` |
| 11 | `v.TotalTicket [K]=0` |
| 41 | `RetourQuestion [J]=6` |
| 2 | `Trim(v.Qté [F])='01'` |

#### CONSTANTE (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 9 | `0` |
| 38 | `''` |

#### CAST_LOGIQUE (4)

| IDE | Expression Decodee |
|-----|-------------------|
| 3 | `v.Fin [H]='TRUE'LOG` |
| 4 | `'TRUE'LOG` |
| 15 | `'FALSE'LOG` |
| 42 | `'TRUE'LOG` |

#### NEGATION (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 6 | `NOT v.PrixZero [M]` |

#### OTHER (4)

| IDE | Expression Decodee |
|-----|-------------------|
| 7 | `v.PrixZero [M]` |
| 8 | `T S/Catégorie [Q]` |
| 12 | `[T]` |
| 13 | `GetParam ('SERVICE')` |

#### STRING (3)

| IDE | Expression Decodee |
|-----|-------------------|
| 14 | `Trim(p.Masque_Sans_Z [B])` |
| 39 | `Del (v.Qté [F],Len (Trim(v.Qté [F])),1)` |
| 40 | `Del (v.PrixSaisie [L],Len (Trim(v.PrixSaisie [L])),1)` |

#### CONCATENATION (22)

| IDE | Expression Decodee |
|-----|-------------------|
| 16 | `Trim(v.Qté [F])&'0'` |
| 17 | `Trim(v.PrixSaisie [L])&'0'` |
| 18 | `Trim(v.Qté [F])&'1'` |
| 19 | `Trim(v.PrixSaisie [L])&'1'` |
| 20 | `Trim(v.Qté [F])&'2'` |
| 21 | `Trim(v.PrixSaisie [L])&'2'` |
| 22 | `Trim(v.Qté [F])&'3'` |
| 23 | `Trim(v.PrixSaisie [L])&'3'` |
| 24 | `Trim(v.Qté [F])&'4'` |
| 25 | `Trim(v.PrixSaisie [L])&'4'` |
| 26 | `Trim(v.Qté [F])&'5'` |
| 27 | `Trim(v.PrixSaisie [L])&'5'` |
| 28 | `Trim(v.Qté [F])&'6'` |
| 29 | `Trim(v.PrixSaisie [L])&'6'` |
| 30 | `Trim(v.Qté [F])&'7'` |
| 31 | `Trim(v.PrixSaisie [L])&'7'` |
| 32 | `Trim(v.Qté [F])&'8'` |
| 33 | `Trim(v.PrixSaisie [L])&'8'` |
| 34 | `Trim(v.Qté [F])&'9'` |
| 35 | `Trim(v.PrixSaisie [L])&'9'` |
| 36 | `Trim(v.Qté [F])&'.'` |
| 37 | `Trim(v.PrixSaisie [L])&'.'` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

**Chemin**: (pas de callers directs)

```mermaid
graph LR
    T360[360 Select Product==V4]
    style T360 fill:#58a6ff
    NONE[Aucun caller]
    NONE -.-> T360
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| - | (aucun) | - |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T360[360 Select Product==V4]
    style T360 fill:#58a6ff
    C194[194 Delete Product]
    T360 --> C194
    style C194 fill:#3fb950
    C195[195 Package Rental date]
    T360 --> C195
    style C195 fill:#3fb950
    C196[196 Package= account]
    T360 --> C196
    style C196 fill:#3fb950
    C202[202 Choice today tomorrow]
    T360 --> C202
    style C202 fill:#3fb950
    C203[203 Clavier Numerique]
    T360 --> C203
    style C203 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [194](PVE-IDE-194.md) | Delete Product | 2 | Sous-programme |
| [195](PVE-IDE-195.md) |   Package Rental date | 2 | Sous-programme |
| [196](PVE-IDE-196.md) |       Package=> account | 1 | Sous-programme |
| [202](PVE-IDE-202.md) | Choice today tomorrow | 1 | Sous-programme |
| [203](PVE-IDE-203.md) | Clavier Numerique | 1 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 237 | Taille moyenne |
| Expressions | 42 | Peu de logique |
| Tables WRITE | 3 | Impact modere |
| Sous-programmes | 5 | Peu de dependances |
| Ecrans visibles | 4 | Quelques ecrans |
| Code desactive | 1.3% (3 / 237) | Code sain |
| Regles metier | 2 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Consultation (1 tache: 1 ecran, 0 traitement)

- **Strategie** : Composants de recherche/selection en modales.
- 1 ecran : Select Product

#### Traitement (2 taches: 2 ecrans, 0 traitement)

- **Strategie** : 2 composant(s) UI (Razor/React) avec formulaires et validation.
- 5 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Impression (3 taches: 1 ecran, 2 traitements)

- **Strategie** : Templates HTML -> PDF via wkhtmltopdf ou Puppeteer.
- `PrintService` injectable avec choix imprimante

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| pv_customer_temp | Table WRITE (Database) | 1x | Schema + repository |
| pv_cust_rentals | Table WRITE (Database) | 3x | Schema + repository |
| pv_sellers | Table WRITE (Database) | 1x | Schema + repository |
| [  Package Rental date (IDE 195)](PVE-IDE-195.md) | Sous-programme | 2x | Haute - Sous-programme |
| [Delete Product (IDE 194)](PVE-IDE-194.md) | Sous-programme | 2x | Haute - Sous-programme |
| [Clavier Numerique (IDE 203)](PVE-IDE-203.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Choice today tomorrow (IDE 202)](PVE-IDE-202.md) | Sous-programme | 1x | Normale - Sous-programme |
| [      Package=> account (IDE 196)](PVE-IDE-196.md) | Sous-programme | 1x | Normale - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 19:46*
