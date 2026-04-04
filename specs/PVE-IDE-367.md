# PVE IDE 367 - Package setup

> **Analyse**: Phases 1-4 2026-02-03 19:48 -> 19:48 (12s) | Assemblage 19:48
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PVE |
| IDE Position | 367 |
| Nom Programme | Package setup |
| Fichier source | `Prg_367.xml` |
| Dossier IDE | A |
| Taches | 34 (9 ecrans visibles) |
| Tables modifiees | 4 |
| Programmes appeles | 10 |
| :warning: Statut | **ORPHELIN_POTENTIEL** |

## 2. DESCRIPTION FONCTIONNELLE

**Package setup** assure la gestion complete de ce processus.

Le flux de traitement s'organise en **3 blocs fonctionnels** :

- **Traitement** (23 taches) : traitements metier divers
- **Creation** (9 taches) : insertion d'enregistrements en base (mouvements, prestations)
- **Consultation** (2 taches) : ecrans de recherche, selection et consultation

**Donnees modifiees** : 4 tables en ecriture (pv_customer_temp, pv_cust_rentals_histo, pv_sellers, pv_tva).

**Logique metier** : 2 regles identifiees couvrant conditions metier.

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (23 taches)

- **367** - Package setup
- **367.1** - Packages **[[ECRAN]](#ecran-t2)**
- **367.1.1** - Sub cat **[[ECRAN]](#ecran-t3)**
- **367.1.1.1** - Products **[[ECRAN]](#ecran-t4)**
- **367.1.1.1.2.2** - Package Detail **[[ECRAN]](#ecran-t9)**
- **367.1.1.1.3** - compute 1/2 day auto
- **367.1.1.1.5.1** - Read File
- **367.1.1.2** - matos components **[[ECRAN]](#ecran-t14)**
- **367.1.1.4** - delete
- **367.1.1.4.1** - Delete prod
- **367.1.1.4.2** - Delete components
- **367.1.1.5** - Discount
- **367.1.1.5.1** - Maj products
- **367.1.3** - delete
- **367.1.3.1** - Delete subcat
- **367.1.3.2** - Delete prod
- **367.1.3.3** - Delete components
- **367.1.4** - Categorie 1
- **367.1.5** - Desactiver Cat
- **367.1.6** - Existe actif et inactif ?
- **367.1.7** - Package inactif ?
- **367.1.8** - Existe sub cat ?
- **367.2** - Crédit Conso Actif ?

Delegue a : [Trace Modification package (IDE 229)](PVE-IDE-229.md), [Concatène libellé Cat/Ss-Cat (IDE 321)](PVE-IDE-321.md), [FindTreatments (IDE 154)](PVE-IDE-154.md), [   Accounting articles (IDE 222)](PVE-IDE-222.md), [Suppression packages orphelins (IDE 230)](PVE-IDE-230.md)

#### Phase 2 : Creation (9 taches)

- **367.1.1.1.1** - Create **[[ECRAN]](#ecran-t5)**
- **367.1.1.1.1.1** - create subsubcat batch
- **367.1.1.1.2** - Create **[[ECRAN]](#ecran-t7)**
- **367.1.1.1.2.1** - create subsubcat batch
- **367.1.1.3** - Create **[[ECRAN]](#ecran-t15)**
- **367.1.1.3.1** - create subcat batch
- **367.1.1.3.2** - Create prices auto
- **367.1.2** - Create **[[ECRAN]](#ecran-t23)**
- **367.1.2.1** - create cat batch

#### Phase 3 : Consultation (2 taches)

- **367.1.1.1.4** - Recherche Existence Article +1
- **367.1.1.1.5** - Recherche Trou

Delegue a : [Choix - Classification (IDE 247)](PVE-IDE-247.md), [Choix - TVA (IDE 267)](PVE-IDE-267.md), [   Select - equipment type (IDE 221)](PVE-IDE-221.md), [Choix - Selling Units (IDE 265)](PVE-IDE-265.md), [Choix - Products (IDE 328)](PVE-IDE-328.md)

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| pv_sellers | R/**W**/L (15 usages) |  |
| pv_tva | R/**W**/L (7 usages) |  |
| pv_customer_temp | R/**W**/L (5 usages) |  |
| pv_cust_rentals_histo | **W** (3 usages) | Historique / journal |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (23 taches)

Traitements internes.

---

#### <a id="t1"></a>367 - Package setup

**Role** : Tache d'orchestration : point d'entree du programme (23 sous-taches). Coordonne l'enchainement des traitements.

<details>
<summary>22 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [367.1](#t2) | Packages **[[ECRAN]](#ecran-t2)** | Traitement |
| [367.1.1](#t3) | Sub cat **[[ECRAN]](#ecran-t3)** | Traitement |
| [367.1.1.1](#t4) | Products **[[ECRAN]](#ecran-t4)** | Traitement |
| [367.1.1.1.2.2](#t9) | Package Detail **[[ECRAN]](#ecran-t9)** | Traitement |
| [367.1.1.1.3](#t10) | compute 1/2 day auto | Traitement |
| [367.1.1.1.5.1](#t13) | Read File | Traitement |
| [367.1.1.2](#t14) | matos components **[[ECRAN]](#ecran-t14)** | Traitement |
| [367.1.1.4](#t18) | delete | Traitement |
| [367.1.1.4.1](#t19) | Delete prod | Traitement |
| [367.1.1.4.2](#t20) | Delete components | Traitement |
| [367.1.1.5](#t21) | Discount | Traitement |
| [367.1.1.5.1](#t22) | Maj products | Traitement |
| [367.1.3](#t25) | delete | Traitement |
| [367.1.3.1](#t26) | Delete subcat | Traitement |
| [367.1.3.2](#t27) | Delete prod | Traitement |
| [367.1.3.3](#t28) | Delete components | Traitement |
| [367.1.4](#t29) | Categorie 1 | Traitement |
| [367.1.5](#t30) | Desactiver Cat | Traitement |
| [367.1.6](#t31) | Existe actif et inactif ? | Traitement |
| [367.1.7](#t32) | Package inactif ? | Traitement |
| [367.1.8](#t33) | Existe sub cat ? | Traitement |
| [367.2](#t34) | Crédit Conso Actif ? | Traitement |

</details>
**Variables liees** : O (v.Cat ou package inactif ?)

---

#### <a id="t2"></a>367.1 - Packages [[ECRAN]](#ecran-t2)

**Role** : Traitement : Packages.
**Ecran** : 811 x 398 DLU (MDI) | [Voir mockup](#ecran-t2)

---

#### <a id="t3"></a>367.1.1 - Sub cat [[ECRAN]](#ecran-t3)

**Role** : Traitement : Sub cat.
**Ecran** : 634 x 324 DLU (Modal) | [Voir mockup](#ecran-t3)

---

#### <a id="t4"></a>367.1.1.1 - Products [[ECRAN]](#ecran-t4)

**Role** : Traitement : Products.
**Ecran** : 182 x 314 DLU (Modal) | [Voir mockup](#ecran-t4)

---

#### <a id="t9"></a>367.1.1.1.2.2 - Package Detail [[ECRAN]](#ecran-t9)

**Role** : Traitement : Package Detail.
**Ecran** : 365 x 241 DLU (MDI) | [Voir mockup](#ecran-t9)
**Variables liees** : O (v.Cat ou package inactif ?)

---

#### <a id="t10"></a>367.1.1.1.3 - compute 1/2 day auto

**Role** : Traitement : compute 1/2 day auto.

---

#### <a id="t13"></a>367.1.1.1.5.1 - Read File

**Role** : Traitement : Read File.

---

#### <a id="t14"></a>367.1.1.2 - matos components [[ECRAN]](#ecran-t14)

**Role** : Traitement : matos components.
**Ecran** : 242 x 169 DLU (Modal) | [Voir mockup](#ecran-t14)

---

#### <a id="t18"></a>367.1.1.4 - delete

**Role** : Traitement : delete.
**Variables liees** : H (BP. Delete)

---

#### <a id="t19"></a>367.1.1.4.1 - Delete prod

**Role** : Traitement : Delete prod.
**Variables liees** : T (V Produit Actif ?), H (BP. Delete)

---

#### <a id="t20"></a>367.1.1.4.2 - Delete components

**Role** : Traitement : Delete components.
**Variables liees** : H (BP. Delete)

---

#### <a id="t21"></a>367.1.1.5 - Discount

**Role** : Traitement : Discount.

---

#### <a id="t22"></a>367.1.1.5.1 - Maj products

**Role** : Traitement : Maj products.

---

#### <a id="t25"></a>367.1.3 - delete

**Role** : Traitement : delete.
**Variables liees** : H (BP. Delete)

---

#### <a id="t26"></a>367.1.3.1 - Delete subcat

**Role** : Traitement : Delete subcat.
**Variables liees** : H (BP. Delete)

---

#### <a id="t27"></a>367.1.3.2 - Delete prod

**Role** : Traitement : Delete prod.
**Variables liees** : T (V Produit Actif ?), H (BP. Delete)

---

#### <a id="t28"></a>367.1.3.3 - Delete components

**Role** : Traitement : Delete components.
**Variables liees** : H (BP. Delete)

---

#### <a id="t29"></a>367.1.4 - Categorie 1

**Role** : Traitement : Categorie 1.

---

#### <a id="t30"></a>367.1.5 - Desactiver Cat

**Role** : Traitement : Desactiver Cat.

---

#### <a id="t31"></a>367.1.6 - Existe actif et inactif ?

**Role** : Traitement : Existe actif et inactif ?.
**Variables liees** : B (v.Existe actif ?), C (v.Existe inactif ?), D (v.Changement actif/inacti ?f), O (v.Cat ou package inactif ?), S (v.Inactif ?)

---

#### <a id="t32"></a>367.1.7 - Package inactif ?

**Role** : Traitement : Package inactif ?.
**Variables liees** : C (v.Existe inactif ?), O (v.Cat ou package inactif ?), S (v.Inactif ?)

---

#### <a id="t33"></a>367.1.8 - Existe sub cat ?

**Role** : Traitement : Existe sub cat ?.
**Variables liees** : B (v.Existe actif ?), C (v.Existe inactif ?), N (L.Existe sous cat ?)

---

#### <a id="t34"></a>367.2 - Crédit Conso Actif ?

**Role** : Traitement : Crédit Conso Actif ?.
**Variables liees** : B (v.Existe actif ?), C (v.Existe inactif ?), D (v.Changement actif/inacti ?f), O (v.Cat ou package inactif ?), S (v.Inactif ?)


### 3.2 Creation (9 taches)

Insertion de nouveaux enregistrements en base.

---

#### <a id="t5"></a>367.1.1.1.1 - Create [[ECRAN]](#ecran-t5)

**Role** : Traitement : Create.
**Ecran** : 312 x 236 DLU (MDI) | [Voir mockup](#ecran-t5)
**Variables liees** : E (BP. Create)

---

#### <a id="t6"></a>367.1.1.1.1.1 - create subsubcat batch

**Role** : Traitement : create subsubcat batch.
**Variables liees** : E (BP. Create)

---

#### <a id="t7"></a>367.1.1.1.2 - Create [[ECRAN]](#ecran-t7)

**Role** : Traitement : Create.
**Ecran** : 365 x 320 DLU (MDI) | [Voir mockup](#ecran-t7)
**Variables liees** : E (BP. Create)

---

#### <a id="t8"></a>367.1.1.1.2.1 - create subsubcat batch

**Role** : Traitement : create subsubcat batch.
**Variables liees** : E (BP. Create)

---

#### <a id="t15"></a>367.1.1.3 - Create [[ECRAN]](#ecran-t15)

**Role** : Traitement : Create.
**Ecran** : 278 x 134 DLU (MDI) | [Voir mockup](#ecran-t15)
**Variables liees** : E (BP. Create)

---

#### <a id="t16"></a>367.1.1.3.1 - create subcat batch

**Role** : Traitement : create subcat batch.
**Variables liees** : E (BP. Create)

---

#### <a id="t17"></a>367.1.1.3.2 - Create prices auto

**Role** : Traitement : Create prices auto.
**Variables liees** : E (BP. Create)

---

#### <a id="t23"></a>367.1.2 - Create [[ECRAN]](#ecran-t23)

**Role** : Traitement : Create.
**Ecran** : 282 x 191 DLU (MDI) | [Voir mockup](#ecran-t23)
**Variables liees** : E (BP. Create)

---

#### <a id="t24"></a>367.1.2.1 - create cat batch

**Role** : Traitement : create cat batch.
**Variables liees** : E (BP. Create)


### 3.3 Consultation (2 taches)

Ecrans de recherche et consultation.

---

#### <a id="t11"></a>367.1.1.1.4 - Recherche Existence Article +1

**Role** : Traitement : Recherche Existence Article +1.
**Delegue a** : [Choix - Classification (IDE 247)](PVE-IDE-247.md), [Choix - TVA (IDE 267)](PVE-IDE-267.md), [   Select - equipment type (IDE 221)](PVE-IDE-221.md)

---

#### <a id="t12"></a>367.1.1.1.5 - Recherche Trou

**Role** : Traitement : Recherche Trou.
**Delegue a** : [Choix - Classification (IDE 247)](PVE-IDE-247.md), [Choix - TVA (IDE 267)](PVE-IDE-267.md), [   Select - equipment type (IDE 221)](PVE-IDE-221.md)


## 5. REGLES METIER

2 regles identifiees:

### Autres (2 regles)

#### <a id="rm-RM-001"></a>[RM-001] Si {1 alors 2} AND {1 sinon 3}, 'O', 'A')

| Element | Detail |
|---------|--------|
| **Condition** | `{1` |
| **Si vrai** | 2} AND {1 |
| **Si faux** | 3}, 'O', 'A') |
| **Expression source** | Expression 24 : `IF({1,2} AND {1,3}, 'O', 'A')` |
| **Exemple** | Si {1 â†’ 2} AND {1. Sinon â†’ 3}, 'O', 'A') |

#### <a id="rm-RM-002"></a>[RM-002] Si BP. Exit [I] alors 110 sinon 208)

| Element | Detail |
|---------|--------|
| **Condition** | `BP. Exit [I]` |
| **Si vrai** | 110 |
| **Si faux** | 208) |
| **Variables** | I (BP. Exit) |
| **Expression source** | Expression 26 : `IF(BP. Exit [I],110,208)` |
| **Exemple** | Si BP. Exit [I] â†’ 110. Sinon â†’ 208) |

## 6. CONTEXTE

- **Appele par**: (aucun)
- **Appelle**: 10 programmes | **Tables**: 11 (W:4 R:4 L:9) | **Taches**: 34 | **Expressions**: 36

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (9 / 34)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 367.1 | 367.1 | Packages | MDI | 811 | 398 | Traitement |
| 2 | 367.1.1 | 367.1.1 | Sub cat | Modal | 634 | 324 | Traitement |
| 3 | 367.1.1.1 | 367.1.1.1 | Products | Modal | 182 | 314 | Traitement |
| 4 | 367.1.1.1.1 | 367.1.1.1.1 | Create | MDI | 312 | 236 | Creation |
| 5 | 367.1.1.1.2 | 367.1.1.1.2 | Create | MDI | 365 | 320 | Creation |
| 6 | 367.1.1.1.2.2 | 367.1.1.1.2.2 | Package Detail | MDI | 365 | 241 | Traitement |
| 7 | 367.1.1.2 | 367.1.1.2 | matos components | Modal | 242 | 169 | Traitement |
| 8 | 367.1.1.3 | 367.1.1.3 | Create | MDI | 278 | 134 | Creation |
| 9 | 367.1.2 | 367.1.2 | Create | MDI | 282 | 191 | Creation |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t2"></a>367.1 - Packages
**Tache** : [367.1](#t2) | **Type** : MDI | **Dimensions** : 811 x 398 DLU
**Bloc** : Traitement | **Titre IDE** : Packages

<!-- FORM-DATA:
{
    "width":  811,
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
                         "w":  808,
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
                         "w":  725,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "186",
                         "text":  "Create all items or services \u0026 products for sale in your service shop. Then configure them with the appropriate attributes",
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
                         "parent":  7
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  366,
                         "w":  808,
                         "fmt":  "",
                         "name":  "",
                         "h":  29,
                         "color":  "6",
                         "text":  "",
                         "parent":  null
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
                         "parent":  7
                     },
                     {
                         "x":  11,
                         "type":  "button",
                         "var":  "",
                         "y":  332,
                         "w":  55,
                         "fmt":  "\u0026Create",
                         "name":  "BP. Create",
                         "h":  25,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  66,
                         "type":  "button",
                         "var":  "",
                         "y":  332,
                         "w":  55,
                         "fmt":  "\u0026Modify",
                         "name":  "BP. Modif",
                         "h":  25,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  120,
                         "type":  "button",
                         "var":  "",
                         "y":  332,
                         "w":  54,
                         "fmt":  "\u0026Delete",
                         "name":  "BP. Delete",
                         "h":  25,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  758,
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
                         "x":  730,
                         "type":  "button",
                         "var":  "",
                         "y":  370,
                         "w":  77,
                         "fmt":  "\u0026Exit",
                         "name":  "BP. Exit",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  174,
                         "type":  "subform",
                         "var":  "",
                         "y":  42,
                         "w":  637,
                         "fmt":  "",
                         "name":  "Sub cat",
                         "h":  311,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  10,
                         "type":  "combobox",
                         "var":  "",
                         "y":  43,
                         "w":  121,
                         "fmt":  "",
                         "name":  "v.STATUT",
                         "h":  23,
                         "color":  "183",
                         "text":  "A,O,N",
                         "parent":  null
                     }
                 ],
    "taskId":  "367.1",
    "height":  398
}
-->

<details>
<summary><strong>Champs : 2 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 16,86 | CTRL_001 | - | edit |
| 10,43 | v.STATUT | - | combobox |

</details>

<details>
<summary><strong>Boutons : 6 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Create | 11,332 | Bouton fonctionnel |
| Modify | 66,332 | Appel [Trace Modification package (IDE 229)](PVE-IDE-229.md) |
| Delete | 120,332 | Supprime l'element selectionne |
| ñ | 130,79 | Bouton fonctionnel |
| ò | 130,206 | Bouton fonctionnel |
| Exit | 730,370 | Quitte le programme |

</details>

---

#### <a id="ecran-t3"></a>367.1.1 - Sub cat
**Tache** : [367.1.1](#t3) | **Type** : Modal | **Dimensions** : 634 x 324 DLU
**Bloc** : Traitement | **Titre IDE** : Sub cat

<!-- FORM-DATA:
{
    "width":  634,
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
                         "w":  454,
                         "fmt":  "",
                         "name":  "",
                         "h":  323,
                         "color":  "189",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  385,
                         "type":  "label",
                         "var":  "",
                         "y":  19,
                         "w":  232,
                         "fmt":  "",
                         "name":  "",
                         "h":  50,
                         "color":  "189",
                         "text":  "Classification",
                         "parent":  2
                     },
                     {
                         "x":  385,
                         "type":  "label",
                         "var":  "",
                         "y":  77,
                         "w":  110,
                         "fmt":  "",
                         "name":  "",
                         "h":  50,
                         "color":  "189",
                         "text":  "Imputation",
                         "parent":  2
                     },
                     {
                         "x":  507,
                         "type":  "label",
                         "var":  "",
                         "y":  77,
                         "w":  110,
                         "fmt":  "",
                         "name":  "",
                         "h":  50,
                         "color":  "189",
                         "text":  "Action",
                         "parent":  2
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
                         "parent":  12
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
                         "parent":  12
                     },
                     {
                         "x":  517,
                         "type":  "combobox",
                         "var":  "",
                         "y":  96,
                         "w":  89,
                         "fmt":  "",
                         "name":  "CTRL_002",
                         "h":  12,
                         "color":  "110",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  2,
                         "type":  "button",
                         "var":  "",
                         "y":  291,
                         "w":  55,
                         "fmt":  "\u0026Create",
                         "name":  "BP. Create",
                         "h":  25,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  56,
                         "type":  "button",
                         "var":  "",
                         "y":  291,
                         "w":  55,
                         "fmt":  "\u0026Modify",
                         "name":  "BP. Modify",
                         "h":  25,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  110,
                         "type":  "button",
                         "var":  "",
                         "y":  291,
                         "w":  54,
                         "fmt":  "\u0026Delete",
                         "name":  "BP. Delete",
                         "h":  25,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  399,
                         "type":  "button",
                         "var":  "",
                         "y":  33,
                         "w":  205,
                         "fmt":  "Classification",
                         "name":  "BP. Classification",
                         "h":  25,
                         "color":  "",
                         "text":  "",
                         "parent":  2
                     },
                     {
                         "x":  395,
                         "type":  "button",
                         "var":  "",
                         "y":  92,
                         "w":  89,
                         "fmt":  "",
                         "name":  "BP. Article id",
                         "h":  25,
                         "color":  "",
                         "text":  "",
                         "parent":  2
                     },
                     {
                         "x":  383,
                         "type":  "button",
                         "var":  "",
                         "y":  12,
                         "w":  232,
                         "fmt":  "Authorize",
                         "name":  "AUTHO",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
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
                         "x":  383,
                         "type":  "button",
                         "var":  "",
                         "y":  40,
                         "w":  232,
                         "fmt":  "Forbid",
                         "name":  "FORBID",
                         "h":  24,
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
                     },
                     {
                         "x":  383,
                         "type":  "subform",
                         "var":  "",
                         "y":  127,
                         "w":  242,
                         "fmt":  "",
                         "name":  "matos components",
                         "h":  194,
                         "color":  "",
                         "text":  "",
                         "parent":  2
                     }
                 ],
    "taskId":  "367.1.1",
    "height":  324
}
-->

<details>
<summary><strong>Champs : 2 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 5,45 | CTRL_001 | - | edit |
| 517,96 | CTRL_002 | - | combobox |

</details>

<details>
<summary><strong>Boutons : 9 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Create | 2,291 | Bouton fonctionnel |
| Modify | 56,291 | Appel [Trace Modification package (IDE 229)](PVE-IDE-229.md) |
| Delete | 110,291 | Supprime l'element selectionne |
| Classification | 399,33 | Appel [Choix - Classification (IDE 247)](PVE-IDE-247.md) |
| BP. Article id | 395,92 | Bouton fonctionnel |
| Authorize | 383,12 | Bouton fonctionnel |
| ñ | 121,38 | Bouton fonctionnel |
| Forbid | 383,40 | Bouton fonctionnel |
| ò | 121,164 | Bouton fonctionnel |

</details>

---

#### <a id="ecran-t4"></a>367.1.1.1 - Products
**Tache** : [367.1.1.1](#t4) | **Type** : Modal | **Dimensions** : 182 x 314 DLU
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
                         "w":  133,
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
                         "x":  1,
                         "type":  "button",
                         "var":  "",
                         "y":  288,
                         "w":  59,
                         "fmt":  "\u0026Create",
                         "name":  "BP. Create",
                         "h":  25,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  59,
                         "type":  "button",
                         "var":  "",
                         "y":  288,
                         "w":  59,
                         "fmt":  "\u0026Modify",
                         "name":  "BP. Modify",
                         "h":  25,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  118,
                         "type":  "button",
                         "var":  "",
                         "y":  288,
                         "w":  58,
                         "fmt":  "\u0026Delete",
                         "name":  "BP. Delete",
                         "h":  25,
                         "color":  "",
                         "text":  "",
                         "parent":  null
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
                     }
                 ],
    "taskId":  "367.1.1.1",
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
<summary><strong>Boutons : 6 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Create | 1,288 | Bouton fonctionnel |
| Modify | 59,288 | Appel [Trace Modification package (IDE 229)](PVE-IDE-229.md) |
| Delete | 118,288 | Supprime l'element selectionne |
| 1/2 | 133,15 | Bouton fonctionnel |
| ñ | 132,37 | Bouton fonctionnel |
| ò | 132,164 | Bouton fonctionnel |

</details>

---

#### <a id="ecran-t5"></a>367.1.1.1.1 - Create
**Tache** : [367.1.1.1.1](#t5) | **Type** : MDI | **Dimensions** : 312 x 236 DLU
**Bloc** : Creation | **Titre IDE** : Create

<!-- FORM-DATA:
{
    "width":  312,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  180,
                         "type":  "label",
                         "var":  "",
                         "y":  45,
                         "w":  76,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "Block Discount",
                         "parent":  null
                     },
                     {
                         "x":  11,
                         "type":  "label",
                         "var":  "",
                         "y":  46,
                         "w":  60,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "Description",
                         "parent":  null
                     },
                     {
                         "x":  180,
                         "type":  "label",
                         "var":  "",
                         "y":  75,
                         "w":  76,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "Block Free",
                         "parent":  null
                     },
                     {
                         "x":  11,
                         "type":  "label",
                         "var":  "",
                         "y":  76,
                         "w":  38,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "# days",
                         "parent":  null
                     },
                     {
                         "x":  11,
                         "type":  "label",
                         "var":  "",
                         "y":  105,
                         "w":  40,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "VAT",
                         "parent":  null
                     },
                     {
                         "x":  180,
                         "type":  "label",
                         "var":  "",
                         "y":  105,
                         "w":  86,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "Non-stock item",
                         "parent":  null
                     },
                     {
                         "x":  12,
                         "type":  "label",
                         "var":  "",
                         "y":  135,
                         "w":  84,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "Active Product ?",
                         "parent":  null
                     },
                     {
                         "x":  180,
                         "type":  "label",
                         "var":  "",
                         "y":  135,
                         "w":  132,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "Sales Place Independant ?",
                         "parent":  null
                     },
                     {
                         "x":  12,
                         "type":  "label",
                         "var":  "",
                         "y":  171,
                         "w":  84,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "Gift Pass ?",
                         "parent":  null
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  311,
                         "fmt":  "",
                         "name":  "",
                         "h":  40,
                         "color":  "186",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  18,
                         "type":  "label",
                         "var":  "",
                         "y":  13,
                         "w":  183,
                         "fmt":  "",
                         "name":  "",
                         "h":  14,
                         "color":  "186",
                         "text":  "?",
                         "parent":  13
                     },
                     {
                         "x":  4,
                         "type":  "label",
                         "var":  "",
                         "y":  206,
                         "w":  307,
                         "fmt":  "",
                         "name":  "",
                         "h":  29,
                         "color":  "6",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  11,
                         "type":  "edit",
                         "var":  "",
                         "y":  57,
                         "w":  142,
                         "fmt":  "",
                         "name":  "V Label",
                         "h":  12,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  11,
                         "type":  "edit",
                         "var":  "",
                         "y":  86,
                         "w":  28,
                         "fmt":  "",
                         "name":  "V # days",
                         "h":  12,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  180,
                         "type":  "combobox",
                         "var":  "",
                         "y":  57,
                         "w":  55,
                         "fmt":  "",
                         "name":  "V Block Discount",
                         "h":  12,
                         "color":  "183",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  180,
                         "type":  "combobox",
                         "var":  "",
                         "y":  85,
                         "w":  55,
                         "fmt":  "",
                         "name":  "V Block Free",
                         "h":  12,
                         "color":  "183",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  11,
                         "type":  "button",
                         "var":  "",
                         "y":  116,
                         "w":  53,
                         "fmt":  "",
                         "name":  "BP. VAT",
                         "h":  14,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  180,
                         "type":  "combobox",
                         "var":  "",
                         "y":  116,
                         "w":  55,
                         "fmt":  "",
                         "name":  "V Non géré en stock",
                         "h":  12,
                         "color":  "183",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  227,
                         "type":  "image",
                         "var":  "",
                         "y":  1,
                         "w":  48,
                         "fmt":  "",
                         "name":  "",
                         "h":  37,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  155,
                         "type":  "button",
                         "var":  "",
                         "y":  211,
                         "w":  77,
                         "fmt":  "\u0026Cancel",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  22
                     },
                     {
                         "x":  232,
                         "type":  "button",
                         "var":  "",
                         "y":  211,
                         "w":  77,
                         "fmt":  "\u0026Validate",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  22
                     },
                     {
                         "x":  12,
                         "type":  "combobox",
                         "var":  "",
                         "y":  148,
                         "w":  56,
                         "fmt":  "",
                         "name":  "V Produit Actif ?",
                         "h":  12,
                         "color":  "110",
                         "text":  "Yes,No",
                         "parent":  null
                     },
                     {
                         "x":  180,
                         "type":  "combobox",
                         "var":  "",
                         "y":  148,
                         "w":  56,
                         "fmt":  "",
                         "name":  "V Sales Place Independant",
                         "h":  12,
                         "color":  "110",
                         "text":  "Yes,No",
                         "parent":  null
                     },
                     {
                         "x":  12,
                         "type":  "combobox",
                         "var":  "",
                         "y":  184,
                         "w":  56,
                         "fmt":  "",
                         "name":  "V.Gift Pass_0001",
                         "h":  12,
                         "color":  "110",
                         "text":  "Yes,No",
                         "parent":  null
                     }
                 ],
    "taskId":  "367.1.1.1.1",
    "height":  236
}
-->

<details>
<summary><strong>Champs : 8 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 11,57 | V Label | - | edit |
| 11,86 | V # days | - | edit |
| 180,57 | V Block Discount | - | combobox |
| 180,85 | V Block Free | - | combobox |
| 180,116 | V Non géré en stock | - | combobox |
| 12,148 | V Produit Actif ? | - | combobox |
| 180,148 | V Sales Place Independant | - | combobox |
| 12,184 | V.Gift Pass_0001 | - | combobox |

</details>

<details>
<summary><strong>Boutons : 3 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| BP. VAT | 11,116 | Bouton fonctionnel |
| Cancel | 155,211 | Annule et retour au menu |
| Validate | 232,211 | Valide la saisie et enregistre |

</details>

---

#### <a id="ecran-t7"></a>367.1.1.1.2 - Create
**Tache** : [367.1.1.1.2](#t7) | **Type** : MDI | **Dimensions** : 365 x 320 DLU
**Bloc** : Creation | **Titre IDE** : Create

<!-- FORM-DATA:
{
    "width":  365,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  13,
                         "type":  "label",
                         "var":  "",
                         "y":  45,
                         "w":  60,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "Description",
                         "parent":  null
                     },
                     {
                         "x":  202,
                         "type":  "label",
                         "var":  "",
                         "y":  45,
                         "w":  76,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "Product code",
                         "parent":  null
                     },
                     {
                         "x":  12,
                         "type":  "label",
                         "var":  "",
                         "y":  75,
                         "w":  60,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "Sale Label",
                         "parent":  null
                     },
                     {
                         "x":  12,
                         "type":  "label",
                         "var":  "",
                         "y":  106,
                         "w":  62,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "Selling Price",
                         "parent":  null
                     },
                     {
                         "x":  76,
                         "type":  "label",
                         "var":  "",
                         "y":  106,
                         "w":  43,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "Tax Included",
                         "parent":  null
                     },
                     {
                         "x":  129,
                         "type":  "label",
                         "var":  "",
                         "y":  106,
                         "w":  59,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "Selling Unit",
                         "parent":  null
                     },
                     {
                         "x":  203,
                         "type":  "label",
                         "var":  "",
                         "y":  106,
                         "w":  77,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "Selling Quantity",
                         "parent":  null
                     },
                     {
                         "x":  294,
                         "type":  "label",
                         "var":  "",
                         "y":  107,
                         "w":  48,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "Decimals",
                         "parent":  null
                     },
                     {
                         "x":  12,
                         "type":  "label",
                         "var":  "",
                         "y":  136,
                         "w":  76,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "Block Discount",
                         "parent":  null
                     },
                     {
                         "x":  115,
                         "type":  "label",
                         "var":  "",
                         "y":  136,
                         "w":  68,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "Block Free",
                         "parent":  null
                     },
                     {
                         "x":  203,
                         "type":  "label",
                         "var":  "",
                         "y":  136,
                         "w":  86,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "VAT",
                         "parent":  null
                     },
                     {
                         "x":  12,
                         "type":  "label",
                         "var":  "",
                         "y":  167,
                         "w":  97,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "Purchasing Volume",
                         "parent":  null
                     },
                     {
                         "x":  202,
                         "type":  "label",
                         "var":  "",
                         "y":  167,
                         "w":  86,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "Purchasing Price",
                         "parent":  null
                     },
                     {
                         "x":  289,
                         "type":  "label",
                         "var":  "",
                         "y":  167,
                         "w":  43,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "Before Tax",
                         "parent":  null
                     },
                     {
                         "x":  12,
                         "type":  "label",
                         "var":  "",
                         "y":  198,
                         "w":  105,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "Unit Purchasing Price",
                         "parent":  null
                     },
                     {
                         "x":  120,
                         "type":  "label",
                         "var":  "",
                         "y":  198,
                         "w":  43,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "Before Tax",
                         "parent":  null
                     },
                     {
                         "x":  202,
                         "type":  "label",
                         "var":  "",
                         "y":  198,
                         "w":  86,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "Non-stock item",
                         "parent":  null
                     },
                     {
                         "x":  316,
                         "type":  "label",
                         "var":  "",
                         "y":  198,
                         "w":  38,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "# days",
                         "parent":  null
                     },
                     {
                         "x":  12,
                         "type":  "label",
                         "var":  "",
                         "y":  225,
                         "w":  105,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "Active Product ?",
                         "parent":  null
                     },
                     {
                         "x":  202,
                         "type":  "label",
                         "var":  "",
                         "y":  225,
                         "w":  56,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "Gift Pass ?",
                         "parent":  null
                     },
                     {
                         "x":  12,
                         "type":  "label",
                         "var":  "",
                         "y":  255,
                         "w":  132,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "183",
                         "text":  "Sales Place Independant ?",
                         "parent":  null
                     },
                     {
                         "x":  202,
                         "type":  "label",
                         "var":  "",
                         "y":  255,
                         "w":  94,
                         "fmt":  "",
                         "name":  "",
                         "h":  11,
                         "color":  "183",
                         "text":  "Eligible Credit GO ?",
                         "parent":  null
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  362,
                         "fmt":  "",
                         "name":  "",
                         "h":  42,
                         "color":  "186",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  18,
                         "type":  "label",
                         "var":  "",
                         "y":  13,
                         "w":  183,
                         "fmt":  "",
                         "name":  "",
                         "h":  14,
                         "color":  "186",
                         "text":  "?",
                         "parent":  33
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  286,
                         "w":  363,
                         "fmt":  "",
                         "name":  "",
                         "h":  29,
                         "color":  "6",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  12,
                         "type":  "edit",
                         "var":  "",
                         "y":  56,
                         "w":  173,
                         "fmt":  "",
                         "name":  "V Label",
                         "h":  12,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  202,
                         "type":  "edit",
                         "var":  "",
                         "y":  56,
                         "w":  137,
                         "fmt":  "",
                         "name":  "V Product code",
                         "h":  12,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  12,
                         "type":  "edit",
                         "var":  "",
                         "y":  85,
                         "w":  173,
                         "fmt":  "",
                         "name":  "V Sale Label",
                         "h":  12,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  12,
                         "type":  "edit",
                         "var":  "",
                         "y":  117,
                         "w":  83,
                         "fmt":  "N12.3C",
                         "name":  "V Vente prix",
                         "h":  12,
                         "color":  "146",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  139,
                         "type":  "button",
                         "var":  "",
                         "y":  117,
                         "w":  46,
                         "fmt":  "",
                         "name":  "BP. Selling Unit",
                         "h":  14,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  202,
                         "type":  "edit",
                         "var":  "",
                         "y":  117,
                         "w":  78,
                         "fmt":  "6.2",
                         "name":  "V Vente volume",
                         "h":  12,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  318,
                         "type":  "edit",
                         "var":  "",
                         "y":  118,
                         "w":  21,
                         "fmt":  "",
                         "name":  "V Décimales",
                         "h":  12,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  12,
                         "type":  "combobox",
                         "var":  "",
                         "y":  147,
                         "w":  55,
                         "fmt":  "",
                         "name":  "V Block Discount",
                         "h":  12,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  116,
                         "type":  "combobox",
                         "var":  "",
                         "y":  147,
                         "w":  55,
                         "fmt":  "",
                         "name":  "V Block Free",
                         "h":  12,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  202,
                         "type":  "button",
                         "var":  "",
                         "y":  147,
                         "w":  53,
                         "fmt":  "",
                         "name":  "VAT",
                         "h":  14,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  12,
                         "type":  "edit",
                         "var":  "",
                         "y":  178,
                         "w":  85,
                         "fmt":  "6.2",
                         "name":  "V Achat volume",
                         "h":  12,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  202,
                         "type":  "edit",
                         "var":  "",
                         "y":  178,
                         "w":  85,
                         "fmt":  "N12.3C",
                         "name":  "V Achat prix (bottle)",
                         "h":  12,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  12,
                         "type":  "edit",
                         "var":  "",
                         "y":  209,
                         "w":  85,
                         "fmt":  "N12.3C",
                         "name":  "V Achat prix unitaire",
                         "h":  12,
                         "color":  "146",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  201,
                         "type":  "combobox",
                         "var":  "",
                         "y":  209,
                         "w":  55,
                         "fmt":  "",
                         "name":  "V Non géré en stock",
                         "h":  12,
                         "color":  "110",
                         "text":  "Yes,No",
                         "parent":  null
                     },
                     {
                         "x":  316,
                         "type":  "edit",
                         "var":  "",
                         "y":  209,
                         "w":  28,
                         "fmt":  "",
                         "name":  "V # days",
                         "h":  12,
                         "color":  "6",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  313,
                         "type":  "image",
                         "var":  "",
                         "y":  4,
                         "w":  48,
                         "fmt":  "",
                         "name":  "",
                         "h":  37,
                         "color":  "",
                         "text":  "",
                         "parent":  33
                     },
                     {
                         "x":  2,
                         "type":  "button",
                         "var":  "",
                         "y":  290,
                         "w":  93,
                         "fmt":  "\u0026Package detail",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  208,
                         "type":  "button",
                         "var":  "",
                         "y":  290,
                         "w":  77,
                         "fmt":  "\u0026Cancel",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  285,
                         "type":  "button",
                         "var":  "",
                         "y":  290,
                         "w":  77,
                         "fmt":  "\u0026Validate",
                         "name":  "V Validation",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  12,
                         "type":  "combobox",
                         "var":  "",
                         "y":  238,
                         "w":  56,
                         "fmt":  "",
                         "name":  "V Produit Actif ?",
                         "h":  12,
                         "color":  "110",
                         "text":  "Yes,No",
                         "parent":  null
                     },
                     {
                         "x":  201,
                         "type":  "combobox",
                         "var":  "",
                         "y":  238,
                         "w":  56,
                         "fmt":  "",
                         "name":  "V Gift Pass",
                         "h":  12,
                         "color":  "110",
                         "text":  "Yes,No",
                         "parent":  null
                     },
                     {
                         "x":  12,
                         "type":  "combobox",
                         "var":  "",
                         "y":  268,
                         "w":  56,
                         "fmt":  "",
                         "name":  "v Sales Place Independant",
                         "h":  12,
                         "color":  "110",
                         "text":  "Yes,No",
                         "parent":  null
                     },
                     {
                         "x":  201,
                         "type":  "combobox",
                         "var":  "",
                         "y":  268,
                         "w":  56,
                         "fmt":  "",
                         "name":  "V Eligible Credit GO",
                         "h":  12,
                         "color":  "110",
                         "text":  "Yes,No",
                         "parent":  null
                     },
                     {
                         "x":  204,
                         "type":  "checkbox",
                         "var":  "",
                         "y":  85,
                         "w":  100,
                         "fmt":  "",
                         "name":  "Copy Cat \u0026 Sub Cat",
                         "h":  12,
                         "color":  "183",
                         "text":  " Copy Cat and Sub Cat",
                         "parent":  null
                     }
                 ],
    "taskId":  "367.1.1.1.2",
    "height":  320
}
-->

<details>
<summary><strong>Champs : 18 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 12,56 | V Label | - | edit |
| 202,56 | V Product code | - | edit |
| 12,85 | V Sale Label | - | edit |
| 12,117 | V Vente prix | - | edit |
| 202,117 | V Vente volume | - | edit |
| 318,118 | V Décimales | - | edit |
| 12,147 | V Block Discount | - | combobox |
| 116,147 | V Block Free | - | combobox |
| 12,178 | V Achat volume | - | edit |
| 202,178 | V Achat prix (bottle) | - | edit |
| 12,209 | V Achat prix unitaire | - | edit |
| 201,209 | V Non géré en stock | - | combobox |
| 316,209 | V # days | - | edit |
| 12,238 | V Produit Actif ? | - | combobox |
| 201,238 | V Gift Pass | - | combobox |
| 12,268 | v Sales Place Independant | - | combobox |
| 201,268 | V Eligible Credit GO | - | combobox |
| 204,85 | Copy Cat & Sub Cat | - | checkbox |

</details>

<details>
<summary><strong>Boutons : 5 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| BP. Selling Unit | 139,117 | Bouton fonctionnel |
| VAT | 202,147 | Bouton fonctionnel |
| Package detail | 2,290 | Appel [Trace Modification package (IDE 229)](PVE-IDE-229.md) |
| Cancel | 208,290 | Annule et retour au menu |
| Validate | 285,290 | Valide la saisie et enregistre |

</details>

---

#### <a id="ecran-t9"></a>367.1.1.1.2.2 - Package Detail
**Tache** : [367.1.1.1.2.2](#t9) | **Type** : MDI | **Dimensions** : 365 x 241 DLU
**Bloc** : Traitement | **Titre IDE** : Package Detail

<!-- FORM-DATA:
{
    "width":  365,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  362,
                         "fmt":  "",
                         "name":  "",
                         "h":  42,
                         "color":  "186",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  18,
                         "type":  "label",
                         "var":  "",
                         "y":  13,
                         "w":  183,
                         "fmt":  "",
                         "name":  "",
                         "h":  14,
                         "color":  "186",
                         "text":  "Input the detail of the package",
                         "parent":  1
                     },
                     {
                         "x":  30,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  16,
                         "color":  "110",
                         "w":  300,
                         "y":  58,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  18,
                         "h":  138,
                         "cols":  [
                                      {
                                          "title":  "Product",
                                          "layer":  1,
                                          "w":  163
                                      },
                                      {
                                          "title":  "Quantity in package",
                                          "layer":  2,
                                          "w":  133
                                      }
                                  ],
                         "rows":  2
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  209,
                         "w":  363,
                         "fmt":  "",
                         "name":  "",
                         "h":  31,
                         "color":  "6",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  289,
                         "type":  "edit",
                         "var":  "",
                         "y":  76,
                         "w":  27,
                         "fmt":  "",
                         "name":  "",
                         "h":  14,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  33,
                         "type":  "button",
                         "var":  "",
                         "y":  76,
                         "w":  158,
                         "fmt":  "",
                         "name":  "DETAIL",
                         "h":  14,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  196,
                         "type":  "edit",
                         "var":  "",
                         "y":  76,
                         "w":  87,
                         "fmt":  "6.2",
                         "name":  "CTRL_001",
                         "h":  14,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  313,
                         "type":  "image",
                         "var":  "",
                         "y":  4,
                         "w":  48,
                         "fmt":  "",
                         "name":  "",
                         "h":  37,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  284,
                         "type":  "button",
                         "var":  "",
                         "y":  215,
                         "w":  77,
                         "fmt":  "\u0026Exit",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  2,
                         "type":  "button",
                         "var":  "",
                         "y":  216,
                         "w":  77,
                         "fmt":  "\u0026Create line",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  80,
                         "type":  "button",
                         "var":  "",
                         "y":  216,
                         "w":  77,
                         "fmt":  "\u0026Delete line",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  157,
                         "type":  "button",
                         "var":  "",
                         "y":  216,
                         "w":  77,
                         "fmt":  "\u0026Modify",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "367.1.1.1.2.2",
    "height":  241
}
-->

<details>
<summary><strong>Champs : 2 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 289,76 | (sans nom) | - | edit |
| 196,76 | CTRL_001 | - | edit |

</details>

<details>
<summary><strong>Boutons : 5 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| DETAIL | 33,76 | Affiche les details |
| Exit | 284,215 | Quitte le programme |
| Create line | 2,216 | Bouton fonctionnel |
| Delete line | 80,216 | Supprime l'element selectionne |
| Modify | 157,216 | Appel [Trace Modification package (IDE 229)](PVE-IDE-229.md) |

</details>

---

#### <a id="ecran-t14"></a>367.1.1.2 - matos components
**Tache** : [367.1.1.2](#t14) | **Type** : Modal | **Dimensions** : 242 x 169 DLU
**Bloc** : Traitement | **Titre IDE** : matos components

<!-- FORM-DATA:
{
    "width":  242,
    "vFactor":  8,
    "type":  "Modal",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  3,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  81,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "181",
                         "text":  "Equipment",
                         "parent":  null
                     },
                     {
                         "x":  90,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  86,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "181",
                         "text":  "Classification",
                         "parent":  null
                     },
                     {
                         "x":  193,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  46,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "181",
                         "text":  "Appear ?",
                         "parent":  null
                     },
                     {
                         "x":  1,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "110",
                         "w":  239,
                         "y":  13,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  27,
                         "h":  153,
                         "cols":  [
                                      {
                                          "title":  "",
                                          "layer":  1,
                                          "w":  232
                                      }
                                  ],
                         "rows":  1
                     },
                     {
                         "x":  91,
                         "type":  "button",
                         "var":  "",
                         "y":  14,
                         "w":  113,
                         "fmt":  "Classification",
                         "name":  "btn classification",
                         "h":  25,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  205,
                         "type":  "button",
                         "var":  "",
                         "y":  14,
                         "w":  32,
                         "fmt":  "o",
                         "name":  "btn auto generate",
                         "h":  25,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  3,
                         "type":  "button",
                         "var":  "",
                         "y":  14,
                         "w":  87,
                         "fmt":  "Equipment",
                         "name":  "btn matos",
                         "h":  25,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     }
                 ],
    "taskId":  "367.1.1.2",
    "height":  169
}
-->

<details>
<summary><strong>Boutons : 3 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Classification | 91,14 | Appel [Choix - Classification (IDE 247)](PVE-IDE-247.md) |
| o | 205,14 | Bouton fonctionnel |
| Equipment | 3,14 | Appel [   Select - equipment type (IDE 221)](PVE-IDE-221.md) |

</details>

---

#### <a id="ecran-t15"></a>367.1.1.3 - Create
**Tache** : [367.1.1.3](#t15) | **Type** : MDI | **Dimensions** : 278 x 134 DLU
**Bloc** : Creation | **Titre IDE** : Create

<!-- FORM-DATA:
{
    "width":  278,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  13,
                         "type":  "label",
                         "var":  "",
                         "y":  43,
                         "w":  120,
                         "fmt":  "",
                         "name":  "",
                         "h":  13,
                         "color":  "183",
                         "text":  "Description",
                         "parent":  null
                     },
                     {
                         "x":  13,
                         "type":  "label",
                         "var":  "",
                         "y":  57,
                         "w":  120,
                         "fmt":  "",
                         "name":  "",
                         "h":  13,
                         "color":  "183",
                         "text":  "Free under (years old)",
                         "parent":  null
                     },
                     {
                         "x":  13,
                         "type":  "label",
                         "var":  "",
                         "y":  70,
                         "w":  120,
                         "fmt":  "",
                         "name":  "",
                         "h":  11,
                         "color":  "183",
                         "text":  "Alcooholic products",
                         "parent":  null
                     },
                     {
                         "x":  13,
                         "type":  "label",
                         "var":  "",
                         "y":  86,
                         "w":  30,
                         "fmt":  "",
                         "name":  "",
                         "h":  11,
                         "color":  "183",
                         "text":  "Active",
                         "parent":  null
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  277,
                         "fmt":  "",
                         "name":  "",
                         "h":  41,
                         "color":  "186",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  13,
                         "type":  "label",
                         "var":  "",
                         "y":  13,
                         "w":  201,
                         "fmt":  "",
                         "name":  "",
                         "h":  13,
                         "color":  "186",
                         "text":  "Enter the name of the sub category",
                         "parent":  7
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  105,
                         "w":  277,
                         "fmt":  "",
                         "name":  "",
                         "h":  29,
                         "color":  "6",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  138,
                         "type":  "edit",
                         "var":  "",
                         "y":  43,
                         "w":  137,
                         "fmt":  "",
                         "name":  "SUB CAT",
                         "h":  13,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  123,
                         "type":  "button",
                         "var":  "",
                         "y":  110,
                         "w":  77,
                         "fmt":  "\u0026Cancel",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  200,
                         "type":  "button",
                         "var":  "",
                         "y":  110,
                         "w":  77,
                         "fmt":  "\u0026Validate",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  227,
                         "type":  "image",
                         "var":  "",
                         "y":  3,
                         "w":  48,
                         "fmt":  "",
                         "name":  "",
                         "h":  37,
                         "color":  "",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  138,
                         "type":  "edit",
                         "var":  "",
                         "y":  57,
                         "w":  22,
                         "fmt":  "",
                         "name":  "V.maximum_age_for_gratuity",
                         "h":  12,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  138,
                         "type":  "checkbox",
                         "var":  "",
                         "y":  70,
                         "w":  18,
                         "fmt":  "",
                         "name":  "V.alcooholic_products",
                         "h":  13,
                         "color":  "183",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  138,
                         "type":  "checkbox",
                         "var":  "",
                         "y":  85,
                         "w":  18,
                         "fmt":  "",
                         "name":  "active",
                         "h":  13,
                         "color":  "183",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "367.1.1.3",
    "height":  134
}
-->

<details>
<summary><strong>Champs : 4 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 138,43 | SUB CAT | - | edit |
| 138,57 | V.maximum_age_for_gratuity | - | edit |
| 138,70 | V.alcooholic_products | - | checkbox |
| 138,85 | active | - | checkbox |

</details>

<details>
<summary><strong>Boutons : 2 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Cancel | 123,110 | Annule et retour au menu |
| Validate | 200,110 | Valide la saisie et enregistre |

</details>

---

#### <a id="ecran-t23"></a>367.1.2 - Create
**Tache** : [367.1.2](#t23) | **Type** : MDI | **Dimensions** : 282 x 191 DLU
**Bloc** : Creation | **Titre IDE** : Create

<!-- FORM-DATA:
{
    "width":  282,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  70,
                         "type":  "label",
                         "var":  "",
                         "y":  51,
                         "w":  137,
                         "fmt":  "",
                         "name":  "",
                         "h":  11,
                         "color":  "183",
                         "text":  "Description",
                         "parent":  null
                     },
                     {
                         "x":  70,
                         "type":  "label",
                         "var":  "",
                         "y":  81,
                         "w":  48,
                         "fmt":  "",
                         "name":  "",
                         "h":  11,
                         "color":  "183",
                         "text":  "Id Booker",
                         "parent":  null
                     },
                     {
                         "x":  70,
                         "type":  "label",
                         "var":  "",
                         "y":  116,
                         "w":  30,
                         "fmt":  "",
                         "name":  "",
                         "h":  11,
                         "color":  "183",
                         "text":  "Active",
                         "parent":  null
                     },
                     {
                         "x":  27,
                         "type":  "label",
                         "var":  "",
                         "y":  139,
                         "w":  85,
                         "fmt":  "",
                         "name":  "",
                         "h":  11,
                         "color":  "183",
                         "text":  "Forfait / Package",
                         "parent":  null
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  277,
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
                         "y":  13,
                         "w":  186,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "186",
                         "text":  "Enter the name of the category",
                         "parent":  7
                     },
                     {
                         "x":  2,
                         "type":  "label",
                         "var":  "",
                         "y":  160,
                         "w":  277,
                         "fmt":  "",
                         "name":  "",
                         "h":  31,
                         "color":  "6",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  70,
                         "type":  "edit",
                         "var":  "",
                         "y":  63,
                         "w":  137,
                         "fmt":  "",
                         "name":  "label",
                         "h":  12,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  123,
                         "type":  "button",
                         "var":  "",
                         "y":  165,
                         "w":  77,
                         "fmt":  "\u0026Cancel",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  200,
                         "type":  "button",
                         "var":  "",
                         "y":  165,
                         "w":  77,
                         "fmt":  "\u0026Validate",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  227,
                         "type":  "image",
                         "var":  "",
                         "y":  4,
                         "w":  48,
                         "fmt":  "",
                         "name":  "",
                         "h":  37,
                         "color":  "",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  114,
                         "type":  "checkbox",
                         "var":  "",
                         "y":  113,
                         "w":  20,
                         "fmt":  "",
                         "name":  "v.active",
                         "h":  16,
                         "color":  "2",
                         "text":  "o",
                         "parent":  null
                     },
                     {
                         "x":  70,
                         "type":  "edit",
                         "var":  "",
                         "y":  93,
                         "w":  137,
                         "fmt":  "10Z",
                         "name":  "IdBooker",
                         "h":  12,
                         "color":  "183",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  114,
                         "type":  "checkbox",
                         "var":  "",
                         "y":  136,
                         "w":  20,
                         "fmt":  "",
                         "name":  "v.Forfait/Package active",
                         "h":  16,
                         "color":  "",
                         "text":  "o",
                         "parent":  null
                     }
                 ],
    "taskId":  "367.1.2",
    "height":  191
}
-->

<details>
<summary><strong>Champs : 4 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 70,63 | label | - | edit |
| 114,113 | v.active | - | checkbox |
| 70,93 | IdBooker | - | edit |
| 114,136 | v.Forfait/Package active | - | checkbox |

</details>

<details>
<summary><strong>Boutons : 2 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Cancel | 123,165 | Annule et retour au menu |
| Validate | 200,165 | Valide la saisie et enregistre |

</details>

## 9. NAVIGATION

### 9.1 Enchainement des ecrans

```mermaid
flowchart TD
    START([Entree])
    style START fill:#3fb950
    VF2[367.1 Packages]
    style VF2 fill:#58a6ff
    VF3[367.1.1 Sub cat]
    style VF3 fill:#58a6ff
    VF4[367.1.1.1 Products]
    style VF4 fill:#58a6ff
    VF5[367.1.1.1.1 Create]
    style VF5 fill:#58a6ff
    VF7[367.1.1.1.2 Create]
    style VF7 fill:#58a6ff
    VF9[367.1.1.1.2.2 Package Detail]
    style VF9 fill:#58a6ff
    VF14[367.1.1.2 matos components]
    style VF14 fill:#58a6ff
    VF15[367.1.1.3 Create]
    style VF15 fill:#58a6ff
    VF23[367.1.2 Create]
    style VF23 fill:#58a6ff
    EXT229[IDE 229 Trace Modifica...]
    style EXT229 fill:#3fb950
    EXT321[IDE 321 Concatène libe...]
    style EXT321 fill:#3fb950
    EXT247[IDE 247 Choix - Classi...]
    style EXT247 fill:#3fb950
    EXT267[IDE 267 Choix - TVA]
    style EXT267 fill:#3fb950
    EXT154[IDE 154 FindTreatments]
    style EXT154 fill:#3fb950
    EXT221[IDE 221 Select - equip...]
    style EXT221 fill:#3fb950
    EXT222[IDE 222 Accounting art...]
    style EXT222 fill:#3fb950
    EXT230[IDE 230 Suppression pa...]
    style EXT230 fill:#3fb950
    EXT265[IDE 265 Choix - Sellin...]
    style EXT265 fill:#3fb950
    EXT328[IDE 328 Choix - Products]
    style EXT328 fill:#3fb950
    FIN([Sortie])
    style FIN fill:#f85149
    START --> VF2
    VF2 -->|Sous-programme| EXT229
    VF2 -->|Sous-programme| EXT321
    VF2 -->|Selection/consultation| EXT247
    VF2 -->|Selection/consultation| EXT267
    VF2 -->|Sous-programme| EXT154
    VF2 -->|Selection/consultation| EXT221
    VF2 -->|Sous-programme| EXT222
    VF2 -->|Sous-programme| EXT230
    EXT328 --> FIN
```

**Detail par enchainement :**

| Depuis | Action | Vers | Retour |
|--------|--------|------|--------|
| Packages | Sous-programme | [Trace Modification package (IDE 229)](PVE-IDE-229.md) | Retour ecran |
| Packages | Sous-programme | [Concatène libellé Cat/Ss-Cat (IDE 321)](PVE-IDE-321.md) | Retour ecran |
| Packages | Selection/consultation | [Choix - Classification (IDE 247)](PVE-IDE-247.md) | Retour ecran |
| Packages | Selection/consultation | [Choix - TVA (IDE 267)](PVE-IDE-267.md) | Retour ecran |
| Packages | Sous-programme | [FindTreatments (IDE 154)](PVE-IDE-154.md) | Retour ecran |
| Packages | Selection/consultation | [   Select - equipment type (IDE 221)](PVE-IDE-221.md) | Retour ecran |
| Packages | Sous-programme | [   Accounting articles (IDE 222)](PVE-IDE-222.md) | Retour ecran |
| Packages | Sous-programme | [Suppression packages orphelins (IDE 230)](PVE-IDE-230.md) | Retour ecran |
| Packages | Selection/consultation | [Choix - Selling Units (IDE 265)](PVE-IDE-265.md) | Retour ecran |
| Packages | Selection/consultation | [Choix - Products (IDE 328)](PVE-IDE-328.md) | Retour ecran |

### 9.3 Structure hierarchique (34 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **367.1** | [**Package setup** (367)](#t1) | - | - | Traitement |
| 367.1.1 | [Packages (367.1)](#t2) [mockup](#ecran-t2) | MDI | 811x398 | |
| 367.1.2 | [Sub cat (367.1.1)](#t3) [mockup](#ecran-t3) | Modal | 634x324 | |
| 367.1.3 | [Products (367.1.1.1)](#t4) [mockup](#ecran-t4) | Modal | 182x314 | |
| 367.1.4 | [Package Detail (367.1.1.1.2.2)](#t9) [mockup](#ecran-t9) | MDI | 365x241 | |
| 367.1.5 | [compute 1/2 day auto (367.1.1.1.3)](#t10) | MDI | - | |
| 367.1.6 | [Read File (367.1.1.1.5.1)](#t13) | - | - | |
| 367.1.7 | [matos components (367.1.1.2)](#t14) [mockup](#ecran-t14) | Modal | 242x169 | |
| 367.1.8 | [delete (367.1.1.4)](#t18) | MDI | - | |
| 367.1.9 | [Delete prod (367.1.1.4.1)](#t19) | MDI | - | |
| 367.1.10 | [Delete components (367.1.1.4.2)](#t20) | MDI | - | |
| 367.1.11 | [Discount (367.1.1.5)](#t21) | MDI | - | |
| 367.1.12 | [Maj products (367.1.1.5.1)](#t22) | MDI | - | |
| 367.1.13 | [delete (367.1.3)](#t25) | MDI | - | |
| 367.1.14 | [Delete subcat (367.1.3.1)](#t26) | MDI | - | |
| 367.1.15 | [Delete prod (367.1.3.2)](#t27) | MDI | - | |
| 367.1.16 | [Delete components (367.1.3.3)](#t28) | MDI | - | |
| 367.1.17 | [Categorie 1 (367.1.4)](#t29) | - | - | |
| 367.1.18 | [Desactiver Cat (367.1.5)](#t30) | - | - | |
| 367.1.19 | [Existe actif et inactif ? (367.1.6)](#t31) | - | - | |
| 367.1.20 | [Package inactif ? (367.1.7)](#t32) | - | - | |
| 367.1.21 | [Existe sub cat ? (367.1.8)](#t33) | - | - | |
| 367.1.22 | [Crédit Conso Actif ? (367.2)](#t34) | - | - | |
| **367.2** | [**Create** (367.1.1.1.1)](#t5) [mockup](#ecran-t5) | MDI | 312x236 | Creation |
| 367.2.1 | [create subsubcat batch (367.1.1.1.1.1)](#t6) | MDI | - | |
| 367.2.2 | [Create (367.1.1.1.2)](#t7) [mockup](#ecran-t7) | MDI | 365x320 | |
| 367.2.3 | [create subsubcat batch (367.1.1.1.2.1)](#t8) | MDI | - | |
| 367.2.4 | [Create (367.1.1.3)](#t15) [mockup](#ecran-t15) | MDI | 278x134 | |
| 367.2.5 | [create subcat batch (367.1.1.3.1)](#t16) | MDI | - | |
| 367.2.6 | [Create prices auto (367.1.1.3.2)](#t17) | MDI | - | |
| 367.2.7 | [Create (367.1.2)](#t23) [mockup](#ecran-t23) | MDI | 282x191 | |
| 367.2.8 | [create cat batch (367.1.2.1)](#t24) | MDI | - | |
| **367.3** | [**Recherche Existence Article +1** (367.1.1.1.4)](#t11) | - | - | Consultation |
| 367.3.1 | [Recherche Trou (367.1.1.1.5)](#t12) | - | - | |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Package setup]
    UPDATE[MAJ 4 tables]
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

### Tables utilisees (11)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 67 | tables___________tab |  | DB | R |   |   | 4 |
| 77 | articles_________art | Articles et stock | DB |   |   | L | 1 |
| 379 | pv_customer_temp |  | DB | R | **W** | L | 5 |
| 380 | pv_day_modes |  | DB |   |   | L | 2 |
| 400 | pv_cust_rentals |  | DB |   |   | L | 1 |
| 401 | pv_cust_rentals_histo | Historique / journal | DB |   | **W** |   | 3 |
| 403 | pv_sellers |  | DB | R | **W** | L | 15 |
| 413 | pv_tva |  | DB | R | **W** | L | 7 |
| 419 | realise_articles_caution | Articles et stock | DB |   |   | L | 1 |
| 756 | Country_ISO |  | DB |   |   | L | 1 |
| 759 | Temp_service_cash | Services / filieres | DB |   |   | L | 1 |

### Colonnes par table (5 / 5 tables avec colonnes identifiees)

<details>
<summary>Table 67 - tables___________tab (R) - 4 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| I | V Vente volume | R | Numeric |
| O | V Achat volume | R | Numeric |

</details>

<details>
<summary>Table 379 - pv_customer_temp (R/**W**/L) - 5 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | p.mode | W | Alpha |
| B | v.label cat | W | Alpha |
| C | IdBooker | W | Numeric |
| D | L.modify | W | Logical |
| E | v.Active | W | Logical |
| F | V.SubCatActive | W | Logical |
| G | v.Forfait/Package active | W | Logical |

</details>

<details>
<summary>Table 401 - pv_cust_rentals_histo (**W**) - 3 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P.i.Categorie | W | Numeric |
| B | P.i.Sous categorie | W | Numeric |
| C | P.i.Matos Modif | W | Logical |
| D | btn classification | W | Alpha |
| E | btn auto generate | W | Alpha |
| F | btn matos | W | Alpha |
| G | Save_expression | W | Numeric |
| H | v.count | W | Numeric |
| I | v.calssif | W | Numeric |

</details>

<details>
<summary>Table 403 - pv_sellers (R/**W**/L) - 15 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P(0) Mode | W | Alpha |
| B | V Label | W | Alpha |
| C | V # days | W | Numeric |
| D | V Block Discount | W | Logical |
| E | V Block Free | W | Logical |
| F | V VAT | W | Numeric |
| G | BP. VAT | W | Alpha |
| H | V Non géré en stock | W | Logical |
| I | V.Produit Actif ? | W | Logical |
| J | V Sales Place Independant... | W | Logical |
| K | V.Gift Pass | W | Logical |
| L | v.Confirmer TVA | W | Numeric |

</details>

<details>
<summary>Table 413 - pv_tva (R/**W**/L) - 7 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P.Categorie | W | Numeric |
| B | v.visible 2 | W | Logical |
| C | v.font 2 | W | Numeric |
| D | L Indicateur | W | Logical |
| E | BP. Create | W | Alpha |
| F | BP. Modify | W | Alpha |
| G | L Product ? | W | Logical |
| H | BP. Delete | W | Alpha |
| I | BP. Classification | W | Alpha |
| J | BP. Matos | W | Alpha |
| K | L Discount article | W | Logical |
| L | BP. Article id | W | Alpha |
| M | BP. Authorize | W | Alpha |
| N | L.Sub cat | W | Numeric |
| O | V.Existe produit ? | W | Logical |
| P | v.Existe package inactif  ? | W | Logical |
| Q | v.Subcat ou package inactif ? | W | Logical |
| R | v.Matos Modif | W | Logical |

</details>

## 11. VARIABLES

### 11.1 Variables de session (15)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | V.Eligible Credit GO - VISIBLE? | Logical | - |
| B | v.Existe actif ? | Logical | [367.1.6](#t31), [367.1.7](#t32), [367.2](#t34) |
| C | v.Existe inactif ? | Logical | [367.1.6](#t31), [367.1.7](#t32) |
| D | v.Changement actif/inacti ?f | Logical | - |
| J | V.Masque | Alpha | 2x session |
| K | V.Masque sans Z | Alpha | 2x session |
| L | V.Decimals | Numeric | - |
| M | V.Category | Numeric | - |
| O | v.Cat ou package inactif ? | Logical | - |
| S | v.Inactif ? | Logical | - |
| T | V Produit Actif ? | Logical | - |
| U | V Gift Pass | Logical | 1x session |
| V | V Eligible Credit GO | Logical | - |
| W | V Sales Place Independant | Logical | - |
| X | v.Confirmer TVA | Numeric | - |

### 11.2 Autres (9)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| E | BP. Create | Alpha | [367.1.1.1.1](#t5), [367.1.1.1.1.1](#t6), [367.1.1.1.2](#t7) |
| F | BP. Modif | Alpha | - |
| G | L S/Category ? | Logical | 2x refs |
| H | BP. Delete | Alpha | - |
| I | BP. Exit | Alpha | 1x refs |
| N | L.Existe sous cat ? | Logical | - |
| P | CHG_REASON_V.ComboActive | Numeric | - |
| Q | CHG_PRV_V.ComboActive | Alpha | 1x refs |
| R | i.Catégrorie | Numeric | - |

<details>
<summary>Toutes les 24 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| V. | **A** | V.Eligible Credit GO - VISIBLE? | Logical |
| V. | **B** | v.Existe actif ? | Logical |
| V. | **C** | v.Existe inactif ? | Logical |
| V. | **D** | v.Changement actif/inacti ?f | Logical |
| V. | **J** | V.Masque | Alpha |
| V. | **K** | V.Masque sans Z | Alpha |
| V. | **L** | V.Decimals | Numeric |
| V. | **M** | V.Category | Numeric |
| V. | **O** | v.Cat ou package inactif ? | Logical |
| V. | **S** | v.Inactif ? | Logical |
| V. | **T** | V Produit Actif ? | Logical |
| V. | **U** | V Gift Pass | Logical |
| V. | **V** | V Eligible Credit GO | Logical |
| V. | **W** | V Sales Place Independant | Logical |
| V. | **X** | v.Confirmer TVA | Numeric |
| Autre | **E** | BP. Create | Alpha |
| Autre | **F** | BP. Modif | Alpha |
| Autre | **G** | L S/Category ? | Logical |
| Autre | **H** | BP. Delete | Alpha |
| Autre | **I** | BP. Exit | Alpha |
| Autre | **N** | L.Existe sous cat ? | Logical |
| Autre | **P** | CHG_REASON_V.ComboActive | Numeric |
| Autre | **Q** | CHG_PRV_V.ComboActive | Alpha |
| Autre | **R** | i.Catégrorie | Numeric |

</details>

## 12. EXPRESSIONS

**36 / 36 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCULATION | 2 | 0 |
| CONDITION | 4 | 2 |
| CONSTANTE | 7 | 0 |
| CAST_LOGIQUE | 6 | 0 |
| OTHER | 14 | 0 |
| NEGATION | 2 | 0 |
| REFERENCE_VG | 1 | 0 |

### 12.2 Expressions cles par type

#### CALCULATION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 31 | `BP. Create [E]+1` | - |
| CALCULATION | 18 | `Left (Trim (CHG_PRV_V.ComboActive [Q]),Len (Trim (CHG_PRV_V.ComboActive [Q]))-1)` | - |

#### CONDITION (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 26 | `IF(BP. Exit [I],110,208)` | [RM-002](#rm-RM-002) |
| CONDITION | 24 | `IF({1,2} AND {1,3}, 'O', 'A')` | [RM-001](#rm-RM-001) |
| CONDITION | 36 | `v.Existe inactif ? [C]='N'` | - |
| CONDITION | 15 | `L S/Category ? [G]<>1 AND NOT (V Gift Pass [U]) AND NOT V.Masque sans Z [K]` | - |

#### CONSTANTE (7 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 27 | `'Sub cat'` | - |
| CONSTANTE | 28 | `'VSERV'` | - |
| CONSTANTE | 29 | `'O'` | - |
| CONSTANTE | 13 | `8` | - |
| CONSTANTE | 8 | `'C'` | - |
| ... | | *+2 autres* | |

#### CAST_LOGIQUE (6 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 5 | `CndRange(v.Existe inactif ? [C]='N','TRUE'LOG)` | - |
| CAST_LOGIQUE | 10 | `'TRUE'LOG` | - |
| CAST_LOGIQUE | 12 | `'FALSE'LOG` | - |
| CAST_LOGIQUE | 1 | `INIPut ('[MAGIC_ENV]AllowCreateInModify=N','FALSE'LOG)` | - |
| CAST_LOGIQUE | 2 | `INIPut ('[MAGIC_ENV]AllowCreateInModify=Y','FALSE'LOG)` | - |
| ... | | *+1 autres* | |

#### OTHER (14 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 25 | `ExisteInactif (L S/Category ? [G])` | - |
| OTHER | 23 | `SetCrsr (1)` | - |
| OTHER | 21 | `SetCrsr (2)` | - |
| OTHER | 30 | `{1,2} AND {1,3}` | - |
| OTHER | 35 | `[AD]` | - |
| ... | | *+9 autres* | |

#### NEGATION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| NEGATION | 32 | `NOT Stat(0, 'C'MODE)` | - |
| NEGATION | 16 | `NOT (V.Masque sans Z [K])` | - |

#### REFERENCE_VG (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 22 | `VG65` | - |

### 12.3 Toutes les expressions (36)

<details>
<summary>Voir les 36 expressions</summary>

#### CALCULATION (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 18 | `Left (Trim (CHG_PRV_V.ComboActive [Q]),Len (Trim (CHG_PRV_V.ComboActive [Q]))-1)` |
| 31 | `BP. Create [E]+1` |

#### CONDITION (4)

| IDE | Expression Decodee |
|-----|-------------------|
| 24 | `IF({1,2} AND {1,3}, 'O', 'A')` |
| 26 | `IF(BP. Exit [I],110,208)` |
| 15 | `L S/Category ? [G]<>1 AND NOT (V Gift Pass [U]) AND NOT V.Masque sans Z [K]` |
| 36 | `v.Existe inactif ? [C]='N'` |

#### CONSTANTE (7)

| IDE | Expression Decodee |
|-----|-------------------|
| 8 | `'C'` |
| 9 | `'M'` |
| 11 | `9` |
| 13 | `8` |
| 27 | `'Sub cat'` |
| 28 | `'VSERV'` |
| 29 | `'O'` |

#### CAST_LOGIQUE (6)

| IDE | Expression Decodee |
|-----|-------------------|
| 1 | `INIPut ('[MAGIC_ENV]AllowCreateInModify=N','FALSE'LOG)` |
| 2 | `INIPut ('[MAGIC_ENV]AllowCreateInModify=Y','FALSE'LOG)` |
| 4 | `CndRange(v.Existe inactif ? [C]='O','TRUE'LOG)` |
| 5 | `CndRange(v.Existe inactif ? [C]='N','TRUE'LOG)` |
| 10 | `'TRUE'LOG` |
| 12 | `'FALSE'LOG` |

#### OTHER (14)

| IDE | Expression Decodee |
|-----|-------------------|
| 3 | `GetParam ('SERVICE')` |
| 6 | `v.Existe actif ? [B]` |
| 7 | `V.Eligible Credit GO -... [A]` |
| 14 | `Stat (0,'D'MODE)` |
| 17 | `GetParam ('AMOUNTFORMAT')` |
| 19 | `GetParam ('DECIMALNUMBER')` |
| 20 | `CtrlGoto('Sub cat',0,0)` |
| 21 | `SetCrsr (2)` |
| 23 | `SetCrsr (1)` |
| 25 | `ExisteInactif (L S/Category ? [G])` |
| 30 | `{1,2} AND {1,3}` |
| 33 | `{1,4}` |
| 34 | `[AC]` |
| 35 | `[AD]` |

#### NEGATION (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 16 | `NOT (V.Masque sans Z [K])` |
| 32 | `NOT Stat(0, 'C'MODE)` |

#### REFERENCE_VG (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 22 | `VG65` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

**Chemin**: (pas de callers directs)

```mermaid
graph LR
    T367[367 Package setup]
    style T367 fill:#58a6ff
    NONE[Aucun caller]
    NONE -.-> T367
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| - | (aucun) | - |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T367[367 Package setup]
    style T367 fill:#58a6ff
    C229[229 Trace Modification...]
    T367 --> C229
    style C229 fill:#3fb950
    C321[321 Concatène libellé ...]
    T367 --> C321
    style C321 fill:#3fb950
    C247[247 Choix - Classifica...]
    T367 --> C247
    style C247 fill:#3fb950
    C267[267 Choix - TVA]
    T367 --> C267
    style C267 fill:#3fb950
    C154[154 FindTreatments]
    T367 --> C154
    style C154 fill:#3fb950
    C221[221 Select - equipment...]
    T367 --> C221
    style C221 fill:#3fb950
    C222[222 Accounting articles]
    T367 --> C222
    style C222 fill:#3fb950
    C230[230 Suppression packag...]
    T367 --> C230
    style C230 fill:#3fb950
    C265[265 Choix - Selling Units]
    T367 --> C265
    style C265 fill:#3fb950
    C328[328 Choix - Products]
    T367 --> C328
    style C328 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [229](PVE-IDE-229.md) | Trace Modification package | 10 | Sous-programme |
| [321](PVE-IDE-321.md) | Concatène libellé Cat/Ss-Cat | 3 | Sous-programme |
| [247](PVE-IDE-247.md) | Choix - Classification | 2 | Selection/consultation |
| [267](PVE-IDE-267.md) | Choix - TVA | 2 | Selection/consultation |
| [154](PVE-IDE-154.md) | FindTreatments | 1 | Sous-programme |
| [221](PVE-IDE-221.md) |    Select - equipment type | 1 | Selection/consultation |
| [222](PVE-IDE-222.md) |    Accounting articles | 1 | Sous-programme |
| [230](PVE-IDE-230.md) | Suppression packages orphelins | 1 | Sous-programme |
| [265](PVE-IDE-265.md) | Choix - Selling Units | 1 | Selection/consultation |
| [328](PVE-IDE-328.md) | Choix - Products | 1 | Selection/consultation |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 1048 | Programme volumineux |
| Expressions | 36 | Peu de logique |
| Tables WRITE | 4 | Impact modere |
| Sous-programmes | 10 | Dependances moderees |
| Ecrans visibles | 9 | Interface complexe multi-ecrans |
| Code desactive | 0.4% (4 / 1048) | Code sain |
| Regles metier | 2 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (23 taches: 5 ecrans, 18 traitements)

- **Strategie** : Orchestrateur avec 5 ecrans (Razor/React) et 18 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 10 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Creation (9 taches: 4 ecrans, 5 traitements)

- **Strategie** : Repository pattern avec Entity Framework Core.
- Insertion via `IRepository<T>.CreateAsync()`

#### Consultation (2 taches: 0 ecran, 2 traitements)

- **Strategie** : Composants de recherche/selection en modales.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| pv_customer_temp | Table WRITE (Database) | 3x | Schema + repository |
| pv_cust_rentals_histo | Table WRITE (Database) | 3x | Schema + repository |
| pv_sellers | Table WRITE (Database) | 8x | Schema + repository |
| pv_tva | Table WRITE (Database) | 4x | Schema + repository |
| [Trace Modification package (IDE 229)](PVE-IDE-229.md) | Sous-programme | 10x | **CRITIQUE** - Sous-programme |
| [Concatène libellé Cat/Ss-Cat (IDE 321)](PVE-IDE-321.md) | Sous-programme | 3x | **CRITIQUE** - Sous-programme |
| [Choix - TVA (IDE 267)](PVE-IDE-267.md) | Sous-programme | 2x | Haute - Selection/consultation |
| [Choix - Classification (IDE 247)](PVE-IDE-247.md) | Sous-programme | 2x | Haute - Selection/consultation |
| [Suppression packages orphelins (IDE 230)](PVE-IDE-230.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Choix - Selling Units (IDE 265)](PVE-IDE-265.md) | Sous-programme | 1x | Normale - Selection/consultation |
| [Choix - Products (IDE 328)](PVE-IDE-328.md) | Sous-programme | 1x | Normale - Selection/consultation |
| [FindTreatments (IDE 154)](PVE-IDE-154.md) | Sous-programme | 1x | Normale - Sous-programme |
| [   Select - equipment type (IDE 221)](PVE-IDE-221.md) | Sous-programme | 1x | Normale - Selection/consultation |
| [   Accounting articles (IDE 222)](PVE-IDE-222.md) | Sous-programme | 1x | Normale - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 19:48*
