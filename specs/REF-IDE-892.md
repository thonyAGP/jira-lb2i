# REF IDE 892 - Gestion Statut Location *cours

> **Analyse**: Phases 1-4 2026-02-03 14:57 -> 14:57 (13s) | Assemblage 14:57
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | REF |
| IDE Position | 892 |
| Nom Programme | Gestion Statut Location *cours |
| Fichier source | `Prg_892.xml` |
| Dossier IDE | General |
| Taches | 10 (3 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |
| :warning: Statut | **ORPHELIN_POTENTIEL** |

## 2. DESCRIPTION FONCTIONNELLE

**Gestion Statut Location *cours** assure la gestion complete de ce processus.

Le flux de traitement s'organise en **3 blocs fonctionnels** :

- **Traitement** (7 taches) : traitements metier divers
- **Impression** (2 taches) : generation de tickets et documents
- **Calcul** (1 tache) : calculs de montants, stocks ou compteurs

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Calcul (1 tache)

- **892** - Rental Status Calculation **[[ECRAN]](#ecran-t1)**

#### Phase 2 : Traitement (7 taches)

- **892.1** - Rentals "Out" Date Due dépassé **[[ECRAN]](#ecran-t2)**
- **892.1.1** - Update Lignes cochées. **[[ECRAN]](#ecran-t3)**
- **892.1.3** - Ligne en statut OUT
- **892.1.3.2** - Maj OUT > IN Sauf dernier/Equi
- **892.1.4** - Liste Gm purgés Status à Out **[[ECRAN]](#ecran-t8)**
- **892.1.4.1** - Mise à jour Status à IN Locat
- **892.1.4.2** - Mise à jour Statut à IN Equip

#### Phase 3 : Impression (2 taches)

- **892.1.2** - Print/Update Status Out **[[ECRAN]](#ecran-t4)**
- **892.1.3.1** - Edition des anc lignes Out>In **[[ECRAN]](#ecran-t6)**

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Calcul (1 tache)

Calculs metier : montants, stocks, compteurs.

---

#### <a id="t1"></a>892 - Rental Status Calculation [[ECRAN]](#ecran-t1)

**Role** : Calcul : Rental Status Calculation.
**Ecran** : 313 x 174 DLU | [Voir mockup](#ecran-t1)
**Variables liees** : I (status_loc), J (status_equi)


### 3.2 Traitement (7 taches)

Traitements internes.

---

#### <a id="t2"></a>892.1 - Rentals "Out" Date Due dépassé [[ECRAN]](#ecran-t2)

**Role** : Traitement : Rentals "Out" Date Due dépassé.
**Ecran** : 997 x 429 DLU | [Voir mockup](#ecran-t2)
**Variables liees** : A (V.Nombre de jours après date du), N (V.Date OUT PDF), O (V.Date IN PDF), P (V.Date OUT CSV), Q (V.Date IN CSV)

---

#### <a id="t3"></a>892.1.1 - Update Lignes cochées. [[ECRAN]](#ecran-t3)

**Role** : Traitement : Update Lignes cochées..
**Ecran** : 992 x 429 DLU | [Voir mockup](#ecran-t3)

---

#### <a id="t5"></a>892.1.3 - Ligne en statut OUT

**Role** : Traitement : Ligne en statut OUT.
**Variables liees** : M (V_Anc_ligne à Out)

---

#### <a id="t7"></a>892.1.3.2 - Maj OUT > IN Sauf dernier/Equi

**Role** : Traitement : Maj OUT > IN Sauf dernier/Equi.

---

#### <a id="t8"></a>892.1.4 - Liste Gm purgés Status à Out [[ECRAN]](#ecran-t8)

**Role** : Traitement : Liste Gm purgés Status à Out.
**Ecran** : 743 x 331 DLU | [Voir mockup](#ecran-t8)
**Variables liees** : I (status_loc), J (status_equi)

---

#### <a id="t9"></a>892.1.4.1 - Mise à jour Status à IN Locat

**Role** : Traitement : Mise à jour Status à IN Locat.
**Variables liees** : A (V.Nombre de jours après date du), I (status_loc), J (status_equi)

---

#### <a id="t10"></a>892.1.4.2 - Mise à jour Statut à IN Equip

**Role** : Traitement : Mise à jour Statut à IN Equip.
**Variables liees** : A (V.Nombre de jours après date du)


### 3.3 Impression (2 taches)

Generation des documents et tickets.

---

#### <a id="t4"></a>892.1.2 - Print/Update Status Out [[ECRAN]](#ecran-t4)

**Role** : Generation du document : Print/Update Status Out.
**Ecran** : 992 x 429 DLU | [Voir mockup](#ecran-t4)
**Variables liees** : I (status_loc), J (status_equi)

---

#### <a id="t6"></a>892.1.3.1 - Edition des anc lignes Out>In [[ECRAN]](#ecran-t6)

**Role** : Generation du document : Edition des anc lignes Out>In.
**Ecran** : 879 x 195 DLU | [Voir mockup](#ecran-t6)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: (aucun)
- **Appelle**: 0 programmes | **Tables**: 9 (W:0 R:3 L:8) | **Taches**: 10 | **Expressions**: 7

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (3 / 10)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 892 | 892 | Rental Status Calculation | Type0 | 313 | 174 | Calcul |
| 2 | 892.1 | 892.1 | Rentals "Out" Date Due dépassé | Type0 | 997 | 429 | Traitement |
| 3 | 892.1.3.1 | 892.1.3.1 | Edition des anc lignes Out>In | Type0 | 879 | 195 | Impression |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>892 - Rental Status Calculation
**Tache** : [892](#t1) | **Type** : Type0 | **Dimensions** : 313 x 174 DLU
**Bloc** : Calcul | **Titre IDE** : Rental Status Calculation

<!-- FORM-DATA:
{
    "width":  313,
    "vFactor":  8,
    "type":  "Type0",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  207,
                         "type":  "label",
                         "var":  "",
                         "y":  76,
                         "w":  25,
                         "fmt":  "",
                         "name":  "",
                         "h":  11,
                         "color":  "183",
                         "text":  "jours",
                         "parent":  null
                     },
                     {
                         "x":  48,
                         "type":  "label",
                         "var":  "",
                         "y":  77,
                         "w":  133,
                         "fmt":  "",
                         "name":  "",
                         "h":  11,
                         "color":  "183",
                         "text":  "Date due dépassée depuis",
                         "parent":  null
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  312,
                         "fmt":  "",
                         "name":  "",
                         "h":  42,
                         "color":  "182",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  12,
                         "type":  "label",
                         "var":  "",
                         "y":  16,
                         "w":  243,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "186",
                         "text":  "Rental Status Calculation",
                         "parent":  4
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  139,
                         "w":  312,
                         "fmt":  "",
                         "name":  "",
                         "h":  34,
                         "color":  "6",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  262,
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
                         "x":  185,
                         "type":  "edit",
                         "var":  "",
                         "y":  77,
                         "w":  18,
                         "fmt":  "",
                         "name":  "V.Nombre de jours après date du",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  174,
                         "type":  "button",
                         "var":  "",
                         "y":  144,
                         "w":  68,
                         "fmt":  "\u0026GO",
                         "name":  "",
                         "h":  28,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  242,
                         "type":  "button",
                         "var":  "",
                         "y":  144,
                         "w":  68,
                         "fmt":  "\u0026Exit",
                         "name":  "",
                         "h":  28,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "892",
    "height":  174
}
-->

<details>
<summary><strong>Champs : 1 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 185,77 | V.Nombre de jours après date du | - | edit |

</details>

<details>
<summary><strong>Boutons : 2 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| GO | 174,144 | Bouton fonctionnel |
| Exit | 242,144 | Quitte le programme |

</details>

---

#### <a id="ecran-t2"></a>892.1 - Rentals "Out" Date Due dépassé
**Tache** : [892.1](#t2) | **Type** : Type0 | **Dimensions** : 997 x 429 DLU
**Bloc** : Traitement | **Titre IDE** : Rentals "Out" Date Due dépassé

<!-- FORM-DATA:
{
    "width":  997,
    "vFactor":  8,
    "type":  "Type0",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  991,
                         "fmt":  "",
                         "name":  "",
                         "h":  42,
                         "color":  "189",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  177,
                         "type":  "label",
                         "var":  "",
                         "y":  13,
                         "w":  301,
                         "fmt":  "",
                         "name":  "",
                         "h":  18,
                         "color":  "188",
                         "text":  "RENTAL STATUS CALCULATION",
                         "parent":  1
                     },
                     {
                         "x":  90,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  24,
                         "color":  "110",
                         "w":  792,
                         "y":  50,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  28,
                         "h":  290,
                         "cols":  [
                                      {
                                          "title":  "Equipment Id",
                                          "layer":  1,
                                          "w":  84
                                      },
                                      {
                                          "title":  "Manufacturer",
                                          "layer":  2,
                                          "w":  85
                                      },
                                      {
                                          "title":  "Model",
                                          "layer":  3,
                                          "w":  107
                                      },
                                      {
                                          "title":  "Name",
                                          "layer":  4,
                                          "w":  120
                                      },
                                      {
                                          "title":  "Room number",
                                          "layer":  5,
                                          "w":  80
                                      },
                                      {
                                          "title":  "Rental status",
                                          "layer":  6,
                                          "w":  72
                                      },
                                      {
                                          "title":  "Equipment status",
                                          "layer":  7,
                                          "w":  72
                                      },
                                      {
                                          "title":  "Date In",
                                          "layer":  8,
                                          "w":  72
                                      },
                                      {
                                          "title":  "Date Out",
                                          "layer":  9,
                                          "w":  72
                                      },
                                      {
                                          "title":  "",
                                          "layer":  10,
                                          "w":  23
                                      }
                                  ],
                         "rows":  10
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  396,
                         "w":  991,
                         "fmt":  "",
                         "name":  "",
                         "h":  33,
                         "color":  "189",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  944,
                         "type":  "image",
                         "var":  "",
                         "y":  6,
                         "w":  48,
                         "fmt":  "",
                         "name":  "",
                         "h":  35,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  480,
                         "type":  "edit",
                         "var":  "",
                         "y":  13,
                         "w":  245,
                         "fmt":  "30",
                         "name":  "",
                         "h":  18,
                         "color":  "174",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  93,
                         "type":  "edit",
                         "var":  "",
                         "y":  78,
                         "w":  78,
                         "fmt":  "U8",
                         "name":  "equipment_id",
                         "h":  20,
                         "color":  "110",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  182,
                         "type":  "edit",
                         "var":  "",
                         "y":  77,
                         "w":  71,
                         "fmt":  "",
                         "name":  "manufacturer_name",
                         "h":  20,
                         "color":  "110",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  262,
                         "type":  "edit",
                         "var":  "",
                         "y":  77,
                         "w":  102,
                         "fmt":  "",
                         "name":  "model_name",
                         "h":  20,
                         "color":  "110",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  370,
                         "type":  "edit",
                         "var":  "",
                         "y":  77,
                         "w":  112,
                         "fmt":  "30",
                         "name":  "gm_prenom",
                         "h":  20,
                         "color":  "110",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  490,
                         "type":  "edit",
                         "var":  "",
                         "y":  77,
                         "w":  72,
                         "fmt":  "",
                         "name":  "heb_nom_logement",
                         "h":  20,
                         "color":  "110",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  570,
                         "type":  "combobox",
                         "var":  "",
                         "y":  82,
                         "w":  36,
                         "fmt":  "",
                         "name":  "status_loc",
                         "h":  12,
                         "color":  "110",
                         "text":  "Out, In",
                         "parent":  5
                     },
                     {
                         "x":  643,
                         "type":  "combobox",
                         "var":  "",
                         "y":  82,
                         "w":  67,
                         "fmt":  "",
                         "name":  "status_equip",
                         "h":  12,
                         "color":  "110",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  717,
                         "type":  "edit",
                         "var":  "",
                         "y":  77,
                         "w":  61,
                         "fmt":  "",
                         "name":  "date_in",
                         "h":  20,
                         "color":  "110",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  788,
                         "type":  "edit",
                         "var":  "",
                         "y":  77,
                         "w":  61,
                         "fmt":  "",
                         "name":  "date_out",
                         "h":  20,
                         "color":  "110",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  861,
                         "type":  "checkbox",
                         "var":  "",
                         "y":  83,
                         "w":  16,
                         "fmt":  "",
                         "name":  "Case à cocher",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  882,
                         "type":  "button",
                         "var":  "",
                         "y":  50,
                         "w":  45,
                         "fmt":  "ñ",
                         "name":  "",
                         "h":  146,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  861,
                         "type":  "checkbox",
                         "var":  "",
                         "y":  58,
                         "w":  13,
                         "fmt":  "",
                         "name":  "V.Select All/None",
                         "h":  12,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  882,
                         "type":  "button",
                         "var":  "",
                         "y":  196,
                         "w":  45,
                         "fmt":  "ò",
                         "name":  "",
                         "h":  145,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  574,
                         "type":  "button",
                         "var":  "",
                         "y":  354,
                         "w":  140,
                         "fmt":  "\u0026Change Selected statuts to IN",
                         "name":  "",
                         "h":  28,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  716,
                         "type":  "button",
                         "var":  "",
                         "y":  354,
                         "w":  140,
                         "fmt":  "\u0026Edit displayed rows",
                         "name":  "",
                         "h":  28,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  694,
                         "type":  "button",
                         "var":  "",
                         "y":  401,
                         "w":  99,
                         "fmt":  "\u0026Cancel",
                         "name":  "",
                         "h":  28,
                         "color":  "",
                         "text":  "",
                         "parent":  31
                     },
                     {
                         "x":  792,
                         "type":  "button",
                         "var":  "",
                         "y":  401,
                         "w":  100,
                         "fmt":  "\u0026Validate",
                         "name":  "",
                         "h":  28,
                         "color":  "",
                         "text":  "",
                         "parent":  31
                     },
                     {
                         "x":  891,
                         "type":  "button",
                         "var":  "",
                         "y":  401,
                         "w":  99,
                         "fmt":  "\u0026Exit",
                         "name":  "",
                         "h":  28,
                         "color":  "",
                         "text":  "",
                         "parent":  31
                     }
                 ],
    "taskId":  "892.1",
    "height":  429
}
-->

<details>
<summary><strong>Champs : 12 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 480,13 | 30 | - | edit |
| 93,78 | equipment_id | - | edit |
| 182,77 | manufacturer_name | - | edit |
| 262,77 | model_name | - | edit |
| 370,77 | gm_prenom | - | edit |
| 490,77 | heb_nom_logement | - | edit |
| 570,82 | status_loc | - | combobox |
| 643,82 | status_equip | - | combobox |
| 717,77 | date_in | - | edit |
| 788,77 | date_out | - | edit |
| 861,83 | Case à cocher | - | checkbox |
| 861,58 | V.Select All/None | - | checkbox |

</details>

<details>
<summary><strong>Boutons : 7 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| ñ | 882,50 | Bouton fonctionnel |
| ò | 882,196 | Bouton fonctionnel |
| Change Selected statuts to IN | 574,354 | Ouvre la selection Modifie l'element |
| Edit displayed rows | 716,354 | Modifie l'element |
| Cancel | 694,401 | Annule et retour au menu |
| Validate | 792,401 | Valide la saisie et enregistre |
| Exit | 891,401 | Quitte le programme |

</details>

---

#### <a id="ecran-t6"></a>892.1.3.1 - Edition des anc lignes Out>In
**Tache** : [892.1.3.1](#t6) | **Type** : Type0 | **Dimensions** : 879 x 195 DLU
**Bloc** : Impression | **Titre IDE** : Edition des anc lignes Out>In

<!-- FORM-DATA:
{
    "width":  879,
    "vFactor":  8,
    "type":  "Type0",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  8,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "",
                         "w":  857,
                         "y":  8,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  13,
                         "h":  182,
                         "cols":  [
                                      {
                                          "title":  "equipment_id",
                                          "layer":  1,
                                          "w":  66
                                      },
                                      {
                                          "title":  "description",
                                          "layer":  2,
                                          "w":  178
                                      },
                                      {
                                          "title":  "manufacturer_name",
                                          "layer":  3,
                                          "w":  122
                                      },
                                      {
                                          "title":  "model_name",
                                          "layer":  4,
                                          "w":  122
                                      },
                                      {
                                          "title":  "status",
                                          "layer":  5,
                                          "w":  66
                                      },
                                      {
                                          "title":  "status",
                                          "layer":  6,
                                          "w":  66
                                      },
                                      {
                                          "title":  "date_in",
                                          "layer":  7,
                                          "w":  55
                                      },
                                      {
                                          "title":  "date_out",
                                          "layer":  8,
                                          "w":  55
                                      }
                                  ],
                         "rows":  8
                     },
                     {
                         "x":  12,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  59,
                         "fmt":  "",
                         "name":  "equipment_id",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  78,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  171,
                         "fmt":  "",
                         "name":  "description",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  256,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  115,
                         "fmt":  "",
                         "name":  "manufacturer_name",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  378,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  115,
                         "fmt":  "",
                         "name":  "model_name",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  500,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  59,
                         "fmt":  "",
                         "name":  "status_0001",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  566,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  59,
                         "fmt":  "",
                         "name":  "status_0002",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  632,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  48,
                         "fmt":  "",
                         "name":  "date_in",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  687,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  48,
                         "fmt":  "",
                         "name":  "date_out",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     }
                 ],
    "taskId":  "892.1.3.1",
    "height":  195
}
-->

<details>
<summary><strong>Champs : 8 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 12,23 | equipment_id | - | edit |
| 78,23 | description | - | edit |
| 256,23 | manufacturer_name | - | edit |
| 378,23 | model_name | - | edit |
| 500,23 | status_0001 | - | edit |
| 566,23 | status_0002 | - | edit |
| 632,23 | date_in | - | edit |
| 687,23 | date_out | - | edit |

</details>

## 9. NAVIGATION

### 9.1 Enchainement des ecrans

```mermaid
flowchart TD
    START([Entree])
    style START fill:#3fb950
    VF1[892 Rental Status Calcu...]
    style VF1 fill:#58a6ff
    VF2[892.1 Rentals Out Date Du...]
    style VF2 fill:#58a6ff
    VF6[892.1.3.1 Edition des anc lig...]
    style VF6 fill:#58a6ff
    FIN([Sortie])
    style FIN fill:#f85149
    START --> VF1
    VF1 --> FIN
```

**Detail par enchainement :**

| Depuis | Action | Vers | Retour |
|--------|--------|------|--------|

### 9.3 Structure hierarchique (10 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **892.1** | [**Rental Status Calculation** (892)](#t1) [mockup](#ecran-t1) | - | 313x174 | Calcul |
| **892.2** | [**Rentals "Out" Date Due dépassé** (892.1)](#t2) [mockup](#ecran-t2) | - | 997x429 | Traitement |
| 892.2.1 | [Update Lignes cochées. (892.1.1)](#t3) [mockup](#ecran-t3) | - | 992x429 | |
| 892.2.2 | [Ligne en statut OUT (892.1.3)](#t5) | - | - | |
| 892.2.3 | [Maj OUT > IN Sauf dernier/Equi (892.1.3.2)](#t7) | - | - | |
| 892.2.4 | [Liste Gm purgés Status à Out (892.1.4)](#t8) [mockup](#ecran-t8) | - | 743x331 | |
| 892.2.5 | [Mise à jour Status à IN Locat (892.1.4.1)](#t9) | - | - | |
| 892.2.6 | [Mise à jour Statut à IN Equip (892.1.4.2)](#t10) | - | - | |
| **892.3** | [**Print/Update Status Out** (892.1.2)](#t4) [mockup](#ecran-t4) | - | 992x429 | Impression |
| 892.3.1 | [Edition des anc lignes Out>In (892.1.3.1)](#t6) [mockup](#ecran-t6) | - | 879x195 | |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Rentals Out Date Due d...]
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

### Tables utilisees (9)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 30 | gm-recherche_____gmr | Index de recherche | DB | R |   |   | 1 |
| 34 | hebergement______heb | Hebergement (chambres) | DB | R |   | L | 4 |
| 376 | pv_classification |  | DB |   |   | L | 3 |
| 378 | pv_customer |  | DB | R |   | L | 4 |
| 384 | pv_equipment_models |  | DB |   |   | L | 3 |
| 385 | pv_equipment |  | DB |   |   | L | 3 |
| 394 | pv_manufacturers |  | DB |   |   | L | 3 |
| 400 | pv_cust_rentals |  | DB |   |   | L | 3 |
| 888 | Prestation_Multi | Prestations/services vendus | DB |   |   | L | 3 |

### Colonnes par table (6 / 3 tables avec colonnes identifiees)

<details>
<summary>Table 30 - gm-recherche_____gmr (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | Verif existence GM ds PV_Custom | R | Logical |
| B | Verif existence Gm ds cafil008 | R | Logical |
| C | V_Nom Fichier | R | Unicode |
| D | V_Ancien Statut loc | R | Unicode |
| E | V_Ancien Statut Equip | R | Unicode |
| F | V_Ligne CSV OUt 7j | R | Unicode |
| G | V.Select All/None | R | Logical |

</details>

<details>
<summary>Table 34 - hebergement______heb (R/L) - 4 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | PI.Edite écran/Update Auto/Coch | R | Alpha |
| B | V_Ancien Statut "Upd Cochées" | R | Unicode |
| C | V_Ancien Statut "Upd Cochées" | R | Unicode |
| D | V_Ligne CSV ECRAN  "Upd Cochées | R | Unicode |

</details>

<details>
<summary>Table 378 - pv_customer (R/L) - 4 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | pv_service | R | Unicode |
| B | xcust_id | R | Numeric |
| C | package_id | R | Numeric |
| D | type_matos | R | Numeric |
| E | date_in | R | Alpha |
| F | date_out | R | Alpha |
| G | time_out | R | Alpha |
| H | equipment_id | R | Unicode |
| I | description | R | Unicode |
| J | manufacturer_name | R | Unicode |
| K | model_name | R | Unicode |
| L | status_loc | R | Unicode |
| M | status_equip | R | Unicode |
| N | V_Ligne GM purgé CSV | R | Unicode |
| O | V.Date IN CSV | R | Alpha |
| P | V.Date OUT CSV | R | Alpha |
| Q | V.Date IN PDF | R | Date |
| R | V.Date OUT PDF | R | Date |

</details>

## 11. VARIABLES

### 11.1 Variables de session (9)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | V.Nombre de jours après date du | Numeric | - |
| E | V.Nom du fichier | Alpha | - |
| F | V.Entête déjà éditée | Logical | - |
| G | V.Select All/None | Logical | - |
| N | V.Date OUT PDF | Date | - |
| O | V.Date IN PDF | Date | - |
| P | V.Date OUT CSV | Alpha | - |
| Q | V.Date IN CSV | Alpha | - |
| R | V.Date OUT PDF | Date | - |

### 11.2 Autres (9)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| B | V_format recapitulatif | Unicode | - |
| C | V_Entête_CSV | Unicode | - |
| D | V_Club_Excel_separator | Unicode | - |
| H | N° de chambre | Unicode | - |
| I | status_loc | Unicode | - |
| J | status_equi | Unicode | - |
| K | date_in | Alpha | - |
| L | date_out | Alpha | - |
| M | V_Anc_ligne à Out | Unicode | - |

<details>
<summary>Toutes les 18 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| V. | **A** | V.Nombre de jours après date du | Numeric |
| V. | **E** | V.Nom du fichier | Alpha |
| V. | **F** | V.Entête déjà éditée | Logical |
| V. | **G** | V.Select All/None | Logical |
| V. | **N** | V.Date OUT PDF | Date |
| V. | **O** | V.Date IN PDF | Date |
| V. | **P** | V.Date OUT CSV | Alpha |
| V. | **Q** | V.Date IN CSV | Alpha |
| V. | **R** | V.Date OUT PDF | Date |
| Autre | **B** | V_format recapitulatif | Unicode |
| Autre | **C** | V_Entête_CSV | Unicode |
| Autre | **D** | V_Club_Excel_separator | Unicode |
| Autre | **H** | N° de chambre | Unicode |
| Autre | **I** | status_loc | Unicode |
| Autre | **J** | status_equi | Unicode |
| Autre | **K** | date_in | Alpha |
| Autre | **L** | date_out | Alpha |
| Autre | **M** | V_Anc_ligne à Out | Unicode |

</details>

## 12. EXPRESSIONS

**7 / 7 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCULATION | 1 | 0 |
| CONSTANTE | 2 | 0 |
| OTHER | 1 | 0 |
| CAST_LOGIQUE | 2 | 0 |
| CONCATENATION | 1 | 0 |

### 12.2 Expressions cles par type

#### CALCULATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 7 | `DbDel('{888,-1}'DSOURCE,'')` | - |

#### CONSTANTE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 6 | `1` | - |
| CONSTANTE | 1 | `'PDF'` | - |

#### OTHER (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 2 | `Translate ('%club_excel_separator%')` | - |

#### CAST_LOGIQUE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 5 | `'FALSE'LOG` | - |
| CAST_LOGIQUE | 4 | `INIPut ('[MAGIC_ENV]IOTiming = O','TRUE'LOG)` | - |

#### CONCATENATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 3 | `Trim(Translate('%club_exportdata%'))&'Gestion_Statut_Location'` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

**Chemin**: (pas de callers directs)

```mermaid
graph LR
    T892[892 Gestion Statut Loc...]
    style T892 fill:#58a6ff
    NONE[Aucun caller]
    NONE -.-> T892
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| - | (aucun) | - |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T892[892 Gestion Statut Loc...]
    style T892 fill:#58a6ff
    NONE[Aucun callee]
    T892 -.-> NONE
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| - | (aucun) | - | - |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 445 | Taille moyenne |
| Expressions | 7 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 3 | Quelques ecrans |
| Code desactive | 0% (0 / 445) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Calcul (1 tache: 1 ecran, 0 traitement)

- **Strategie** : Services de calcul purs (Domain Services).
- Migrer la logique de calcul (stock, compteurs, montants)

#### Traitement (7 taches: 3 ecrans, 4 traitements)

- **Strategie** : Orchestrateur avec 3 ecrans (Razor/React) et 4 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- Decomposer les taches en services unitaires testables.

#### Impression (2 taches: 2 ecrans, 0 traitement)

- **Strategie** : Templates HTML -> PDF via wkhtmltopdf ou Puppeteer.
- `PrintService` injectable avec choix imprimante

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 14:57*
