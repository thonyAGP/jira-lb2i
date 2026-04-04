# GES IDE 8 - Gratuites GM exterieurs

> **Analyse**: Phases 1-4 2026-02-03 11:26 -> 11:26 (14s) | Assemblage 11:26
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | GES |
| IDE Position | 8 |
| Nom Programme | Gratuites GM exterieurs |
| Fichier source | `Prg_8.xml` |
| Dossier IDE | Bar |
| Taches | 16 (7 ecrans visibles) |
| Tables modifiees | 2 |
| Programmes appeles | 1 |

## 2. DESCRIPTION FONCTIONNELLE

**Gratuites GM exterieurs** assure la gestion complete de ce processus, accessible depuis [MENU  Club Med Pass (IDE 5)](GES-IDE-5.md).

Le flux de traitement s'organise en **2 blocs fonctionnels** :

- **Traitement** (14 taches) : traitements metier divers
- **Calcul** (2 taches) : calculs de montants, stocks ou compteurs

**Donnees modifiees** : 2 tables en ecriture (ccrejet, cc_total).

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (14 taches)

- **8** - Gratuites GM
- **8.1** - Credits de conso GM Exterieurs **[[ECRAN]](#ecran-t2)**
- **8.1.1** - credit conso par type **[[ECRAN]](#ecran-t3)**
- **8.1.2** - detail credit conso **[[ECRAN]](#ecran-t4)**
- **8.2** - Credit de conso **[[ECRAN]](#ecran-t5)**
- **8.2.1** - Credit de conso **[[ECRAN]](#ecran-t6)**
- **8.2.2** - CC rejet
- **8.2.3** - Gratuites bar GO **[[ECRAN]](#ecran-t10)**
- **8.2.4** - vide CC rejet
- **8.3** - Debit/Credit en groupe **[[ECRAN]](#ecran-t12)**
- **8.4** - Impression des credit de conso **[[ECRAN]](#ecran-t13)**
- **8.4.1** - Gratuites bar GM **[[ECRAN]](#ecran-t14)**
- **8.4.1.1** - Browse - CC detail
- **8.4.1.2** - Browse - CC par type

Delegue a : [Combo - type credit conso (IDE 12)](GES-IDE-12.md)

#### Phase 2 : Calcul (2 taches)

- **8.2.1.1** - CC Comptable **[[ECRAN]](#ecran-t7)**
- **8.2.1.2** - CC Comptable Intermed **[[ECRAN]](#ecran-t8)**

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| ccrejet | R/**W**/L (4 usages) |  |
| cc_total | **W**/L (2 usages) |  |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (14 taches)

Traitements internes.

---

#### <a id="t1"></a>8 - Gratuites GM

**Role** : Tache d'orchestration : point d'entree du programme (14 sous-taches). Coordonne l'enchainement des traitements.

<details>
<summary>13 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [8.1](#t2) | Credits de conso GM Exterieurs **[[ECRAN]](#ecran-t2)** | Traitement |
| [8.1.1](#t3) | credit conso par type **[[ECRAN]](#ecran-t3)** | Traitement |
| [8.1.2](#t4) | detail credit conso **[[ECRAN]](#ecran-t4)** | Traitement |
| [8.2](#t5) | Credit de conso **[[ECRAN]](#ecran-t5)** | Traitement |
| [8.2.1](#t6) | Credit de conso **[[ECRAN]](#ecran-t6)** | Traitement |
| [8.2.2](#t9) | CC rejet | Traitement |
| [8.2.3](#t10) | Gratuites bar GO **[[ECRAN]](#ecran-t10)** | Traitement |
| [8.2.4](#t11) | vide CC rejet | Traitement |
| [8.3](#t12) | Debit/Credit en groupe **[[ECRAN]](#ecran-t12)** | Traitement |
| [8.4](#t13) | Impression des credit de conso **[[ECRAN]](#ecran-t13)** | Traitement |
| [8.4.1](#t14) | Gratuites bar GM **[[ECRAN]](#ecran-t14)** | Traitement |
| [8.4.1.1](#t15) | Browse - CC detail | Traitement |
| [8.4.1.2](#t16) | Browse - CC par type | Traitement |

</details>

---

#### <a id="t2"></a>8.1 - Credits de conso GM Exterieurs [[ECRAN]](#ecran-t2)

**Role** : Calcul fidelite/avantage : Credits de conso GM Exterieurs.
**Ecran** : 1260 x 314 DLU (MDI) | [Voir mockup](#ecran-t2)

---

#### <a id="t3"></a>8.1.1 - credit conso par type [[ECRAN]](#ecran-t3)

**Role** : Calcul fidelite/avantage : credit conso par type.
**Ecran** : 254 x 72 DLU (Modal) | [Voir mockup](#ecran-t3)
**Variables liees** : G (v.type CS), L (v.List combo type CS)

---

#### <a id="t4"></a>8.1.2 - detail credit conso [[ECRAN]](#ecran-t4)

**Role** : Calcul fidelite/avantage : detail credit conso.
**Ecran** : 348 x 70 DLU (Modal) | [Voir mockup](#ecran-t4)

---

#### <a id="t5"></a>8.2 - Credit de conso [[ECRAN]](#ecran-t5)

**Role** : Calcul fidelite/avantage : Credit de conso.
**Ecran** : 423 x 56 DLU (MDI) | [Voir mockup](#ecran-t5)

---

#### <a id="t6"></a>8.2.1 - Credit de conso [[ECRAN]](#ecran-t6)

**Role** : Calcul fidelite/avantage : Credit de conso.
**Ecran** : 214 x 81 DLU (MDI) | [Voir mockup](#ecran-t6)

---

#### <a id="t9"></a>8.2.2 - CC rejet

**Role** : Traitement : CC rejet.

---

#### <a id="t10"></a>8.2.3 - Gratuites bar GO [[ECRAN]](#ecran-t10)

**Role** : Traitement : Gratuites bar GO.
**Ecran** : 424 x 57 DLU (MDI) | [Voir mockup](#ecran-t10)

---

#### <a id="t11"></a>8.2.4 - vide CC rejet

**Role** : Traitement : vide CC rejet.

---

#### <a id="t12"></a>8.3 - Debit/Credit en groupe [[ECRAN]](#ecran-t12)

**Role** : Calcul fidelite/avantage : Debit/Credit en groupe.
**Ecran** : 274 x 107 DLU (MDI) | [Voir mockup](#ecran-t12)

---

#### <a id="t13"></a>8.4 - Impression des credit de conso [[ECRAN]](#ecran-t13)

**Role** : Generation du document : Impression des credit de conso.
**Ecran** : 640 x 118 DLU (MDI) | [Voir mockup](#ecran-t13)

---

#### <a id="t14"></a>8.4.1 - Gratuites bar GM [[ECRAN]](#ecran-t14)

**Role** : Traitement : Gratuites bar GM.
**Ecran** : 424 x 57 DLU (MDI) | [Voir mockup](#ecran-t14)

---

#### <a id="t15"></a>8.4.1.1 - Browse - CC detail

**Role** : Traitement : Browse - CC detail.

---

#### <a id="t16"></a>8.4.1.2 - Browse - CC par type

**Role** : Traitement : Browse - CC par type.
**Variables liees** : G (v.type CS), L (v.List combo type CS)


### 3.2 Calcul (2 taches)

Calculs metier : montants, stocks, compteurs.

---

#### <a id="t7"></a>8.2.1.1 - CC Comptable [[ECRAN]](#ecran-t7)

**Role** : Traitement : CC Comptable.
**Ecran** : 128 x 52 DLU (MDI) | [Voir mockup](#ecran-t7)

---

#### <a id="t8"></a>8.2.1.2 - CC Comptable Intermed [[ECRAN]](#ecran-t8)

**Role** : Traitement : CC Comptable Intermed.
**Ecran** : 87 x 59 DLU (MDI) | [Voir mockup](#ecran-t8)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [MENU  Club Med Pass (IDE 5)](GES-IDE-5.md)
- **Appelle**: 1 programmes | **Tables**: 13 (W:2 R:8 L:10) | **Taches**: 16 | **Expressions**: 12

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (7 / 16)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 8.1 | 8.1 | Credits de conso GM Exterieurs | MDI | 1260 | 314 | Traitement |
| 2 | 8.1.1 | 8.1.1 | credit conso par type | Modal | 254 | 72 | Traitement |
| 3 | 8.1.2 | 8.1.2 | detail credit conso | Modal | 348 | 70 | Traitement |
| 4 | 8.2 | 8.2 | Credit de conso | MDI | 423 | 56 | Traitement |
| 5 | 8.3 | 8.3 | Debit/Credit en groupe | MDI | 274 | 107 | Traitement |
| 6 | 8.4 | 8.4 | Impression des credit de conso | MDI | 640 | 118 | Traitement |
| 7 | 8.4.1 | 8.4.1 | Gratuites bar GM | MDI | 424 | 57 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t2"></a>8.1 - Credits de conso GM Exterieurs
**Tache** : [8.1](#t2) | **Type** : MDI | **Dimensions** : 1260 x 314 DLU
**Bloc** : Traitement | **Titre IDE** : Credits de conso GM Exterieurs

<!-- FORM-DATA:
{
    "width":  1260,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  1,
                         "w":  1261,
                         "fmt":  "",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  190,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  15,
                         "color":  "6",
                         "w":  882,
                         "y":  25,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  15,
                         "h":  119,
                         "cols":  [
                                      {
                                          "title":  "Nom",
                                          "layer":  1,
                                          "w":  214
                                      },
                                      {
                                          "title":  "Prénom",
                                          "layer":  2,
                                          "w":  138
                                      },
                                      {
                                          "title":  "Date début",
                                          "layer":  3,
                                          "w":  130
                                      },
                                      {
                                          "title":  "Date fin",
                                          "layer":  4,
                                          "w":  152
                                      },
                                      {
                                          "title":  "Crédit de conso",
                                          "layer":  5,
                                          "w":  214
                                      }
                                  ],
                         "rows":  5
                     },
                     {
                         "x":  44,
                         "type":  "label",
                         "var":  "",
                         "y":  26,
                         "w":  1178,
                         "fmt":  "",
                         "name":  "",
                         "h":  14,
                         "color":  "5",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  41,
                         "type":  "label",
                         "var":  "",
                         "y":  155,
                         "w":  328,
                         "fmt":  "",
                         "name":  "",
                         "h":  35,
                         "color":  "",
                         "text":  "Filtre",
                         "parent":  null
                     },
                     {
                         "x":  394,
                         "type":  "label",
                         "var":  "",
                         "y":  155,
                         "w":  418,
                         "fmt":  "",
                         "name":  "",
                         "h":  35,
                         "color":  "",
                         "text":  "Dedit / Credit",
                         "parent":  null
                     },
                     {
                         "x":  842,
                         "type":  "label",
                         "var":  "",
                         "y":  155,
                         "w":  383,
                         "fmt":  "",
                         "name":  "",
                         "h":  35,
                         "color":  "",
                         "text":  "Impression",
                         "parent":  null
                     },
                     {
                         "x":  76,
                         "type":  "label",
                         "var":  "",
                         "y":  210,
                         "w":  462,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "142",
                         "text":  "Position par type de crédit",
                         "parent":  null
                     },
                     {
                         "x":  568,
                         "type":  "label",
                         "var":  "",
                         "y":  210,
                         "w":  624,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "142",
                         "text":  "Historique des crédits effectués",
                         "parent":  null
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  293,
                         "w":  1261,
                         "fmt":  "",
                         "name":  "",
                         "h":  21,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  198,
                         "type":  "edit",
                         "var":  "",
                         "y":  42,
                         "w":  200,
                         "fmt":  "",
                         "name":  "SPC Nom",
                         "h":  11,
                         "color":  "6",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  414,
                         "type":  "edit",
                         "var":  "",
                         "y":  42,
                         "w":  122,
                         "fmt":  "",
                         "name":  "SPC Prenom",
                         "h":  11,
                         "color":  "6",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  552,
                         "type":  "edit",
                         "var":  "",
                         "y":  42,
                         "w":  120,
                         "fmt":  "DD/MM/YYYY",
                         "name":  "",
                         "h":  11,
                         "color":  "6",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  696,
                         "type":  "edit",
                         "var":  "",
                         "y":  42,
                         "w":  120,
                         "fmt":  "DD/MM/YYYY",
                         "name":  "",
                         "h":  11,
                         "color":  "6",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  834,
                         "type":  "edit",
                         "var":  "",
                         "y":  42,
                         "w":  194,
                         "fmt":  "",
                         "name":  "",
                         "h":  11,
                         "color":  "6",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  66,
                         "type":  "combobox",
                         "var":  "",
                         "y":  169,
                         "w":  159,
                         "fmt":  "",
                         "name":  "v.combo type CS",
                         "h":  12,
                         "color":  "110",
                         "text":  "list CS",
                         "parent":  null
                     },
                     {
                         "x":  14,
                         "type":  "edit",
                         "var":  "",
                         "y":  5,
                         "w":  396,
                         "fmt":  "30",
                         "name":  "",
                         "h":  11,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  950,
                         "type":  "edit",
                         "var":  "",
                         "y":  5,
                         "w":  298,
                         "fmt":  "WWW DD MMM YYYYT",
                         "name":  "",
                         "h":  11,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  229,
                         "type":  "button",
                         "var":  "",
                         "y":  169,
                         "w":  130,
                         "fmt":  "Rafraichir",
                         "name":  "J",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  539,
                         "type":  "button",
                         "var":  "",
                         "y":  169,
                         "w":  129,
                         "fmt":  "Individuel",
                         "name":  "GI",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  676,
                         "type":  "button",
                         "var":  "",
                         "y":  169,
                         "w":  129,
                         "fmt":  "Groupe",
                         "name":  "GG",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  952,
                         "type":  "button",
                         "var":  "",
                         "y":  169,
                         "w":  129,
                         "fmt":  "Individuel",
                         "name":  "HI",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  1089,
                         "type":  "button",
                         "var":  "",
                         "y":  169,
                         "w":  129,
                         "fmt":  "Groupe",
                         "name":  "HG",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  1088,
                         "type":  "button",
                         "var":  "",
                         "y":  295,
                         "w":  168,
                         "fmt":  "Quitter",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "8.1",
    "height":  314
}
-->

<details>
<summary><strong>Champs : 8 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 198,42 | SPC Nom | - | edit |
| 414,42 | SPC Prenom | - | edit |
| 552,42 | DD/MM/YYYY | - | edit |
| 696,42 | DD/MM/YYYY | - | edit |
| 834,42 | (sans nom) | - | edit |
| 66,169 | v.combo type CS | - | combobox |
| 14,5 | 30 | - | edit |
| 950,5 | WWW DD MMM YYYYT | - | edit |

</details>

<details>
<summary><strong>Boutons : 6 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Rafraichir | 229,169 | Bouton fonctionnel |
| Individuel | 539,169 | Bouton fonctionnel |
| Groupe | 676,169 | Bouton fonctionnel |
| Individuel | 952,169 | Bouton fonctionnel |
| Groupe | 1089,169 | Bouton fonctionnel |
| Quitter | 1088,295 | Quitte le programme |

</details>

---

#### <a id="ecran-t3"></a>8.1.1 - credit conso par type
**Tache** : [8.1.1](#t3) | **Type** : Modal | **Dimensions** : 254 x 72 DLU
**Bloc** : Traitement | **Titre IDE** : credit conso par type

<!-- FORM-DATA:
{
    "width":  254,
    "vFactor":  8,
    "type":  "Modal",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  4,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  16,
                         "color":  "6",
                         "w":  237,
                         "y":  4,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  12,
                         "h":  66,
                         "cols":  [
                                      {
                                          "title":  "Type de crédit",
                                          "layer":  1,
                                          "w":  125
                                      },
                                      {
                                          "title":  "Solde",
                                          "layer":  2,
                                          "w":  97
                                      }
                                  ],
                         "rows":  2
                     },
                     {
                         "x":  5,
                         "type":  "label",
                         "var":  "",
                         "y":  5,
                         "w":  233,
                         "fmt":  "",
                         "name":  "",
                         "h":  15,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  133,
                         "type":  "edit",
                         "var":  "",
                         "y":  22,
                         "w":  87,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  9,
                         "type":  "edit",
                         "var":  "",
                         "y":  22,
                         "w":  115,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     }
                 ],
    "taskId":  "8.1.1",
    "height":  72
}
-->

<details>
<summary><strong>Champs : 2 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 133,22 | (sans nom) | - | edit |
| 9,22 | (sans nom) | - | edit |

</details>

---

#### <a id="ecran-t4"></a>8.1.2 - detail credit conso
**Tache** : [8.1.2](#t4) | **Type** : Modal | **Dimensions** : 348 x 70 DLU
**Bloc** : Traitement | **Titre IDE** : detail credit conso

<!-- FORM-DATA:
{
    "width":  348,
    "vFactor":  8,
    "type":  "Modal",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  4,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  16,
                         "color":  "6",
                         "w":  320,
                         "y":  1,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  12,
                         "h":  66,
                         "cols":  [
                                      {
                                          "title":  "Montant",
                                          "layer":  1,
                                          "w":  69
                                      },
                                      {
                                          "title":  "Type de crédit",
                                          "layer":  2,
                                          "w":  102
                                      },
                                      {
                                          "title":  "Date",
                                          "layer":  3,
                                          "w":  63
                                      },
                                      {
                                          "title":  "Utilisateur",
                                          "layer":  4,
                                          "w":  69
                                      }
                                  ],
                         "rows":  4
                     },
                     {
                         "x":  8,
                         "type":  "edit",
                         "var":  "",
                         "y":  18,
                         "w":  61,
                         "fmt":  "",
                         "name":  "",
                         "h":  11,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  179,
                         "type":  "edit",
                         "var":  "",
                         "y":  18,
                         "w":  56,
                         "fmt":  "",
                         "name":  "",
                         "h":  11,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  241,
                         "type":  "edit",
                         "var":  "",
                         "y":  18,
                         "w":  63,
                         "fmt":  "",
                         "name":  "",
                         "h":  11,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  77,
                         "type":  "edit",
                         "var":  "",
                         "y":  18,
                         "w":  94,
                         "fmt":  "",
                         "name":  "",
                         "h":  11,
                         "color":  "6",
                         "text":  "",
                         "parent":  1
                     }
                 ],
    "taskId":  "8.1.2",
    "height":  70
}
-->

<details>
<summary><strong>Champs : 4 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 8,18 | (sans nom) | - | edit |
| 179,18 | (sans nom) | - | edit |
| 241,18 | (sans nom) | - | edit |
| 77,18 | (sans nom) | - | edit |

</details>

---

#### <a id="ecran-t5"></a>8.2 - Credit de conso
**Tache** : [8.2](#t5) | **Type** : MDI | **Dimensions** : 423 x 56 DLU
**Bloc** : Traitement | **Titre IDE** : Credit de conso

<!-- FORM-DATA:
{
    "width":  423,
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
                         "x":  119,
                         "type":  "label",
                         "var":  "",
                         "y":  10,
                         "w":  266,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "142",
                         "text":  "Validation en cours ...",
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
                         "x":  35,
                         "type":  "label",
                         "var":  "",
                         "y":  38,
                         "w":  352,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Validation des credits de conso",
                         "parent":  null
                     },
                     {
                         "x":  3,
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
    "taskId":  "8.2",
    "height":  56
}
-->

---

#### <a id="ecran-t12"></a>8.3 - Debit/Credit en groupe
**Tache** : [8.3](#t12) | **Type** : MDI | **Dimensions** : 274 x 107 DLU
**Bloc** : Traitement | **Titre IDE** : Debit/Credit en groupe

<!-- FORM-DATA:
{
    "width":  274,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  62,
                         "type":  "label",
                         "var":  "",
                         "y":  18,
                         "w":  42,
                         "fmt":  "",
                         "name":  "",
                         "h":  14,
                         "color":  "",
                         "text":  "Montant",
                         "parent":  null
                     },
                     {
                         "x":  63,
                         "type":  "label",
                         "var":  "",
                         "y":  43,
                         "w":  49,
                         "fmt":  "",
                         "name":  "",
                         "h":  14,
                         "color":  "",
                         "text":  "Type",
                         "parent":  null
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  75,
                         "w":  271,
                         "fmt":  "",
                         "name":  "",
                         "h":  30,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  114,
                         "type":  "edit",
                         "var":  "",
                         "y":  18,
                         "w":  97,
                         "fmt":  "13.2C",
                         "name":  "",
                         "h":  14,
                         "color":  "6",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  114,
                         "type":  "combobox",
                         "var":  "",
                         "y":  43,
                         "w":  97,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "110",
                         "text":  "credit conso",
                         "parent":  null
                     },
                     {
                         "x":  88,
                         "type":  "button",
                         "var":  "",
                         "y":  81,
                         "w":  77,
                         "fmt":  "Débit",
                         "name":  "-",
                         "h":  21,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  189,
                         "type":  "button",
                         "var":  "",
                         "y":  82,
                         "w":  77,
                         "fmt":  "Annuler",
                         "name":  "",
                         "h":  21,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  6,
                         "type":  "button",
                         "var":  "",
                         "y":  81,
                         "w":  77,
                         "fmt":  "Crédit",
                         "name":  "+",
                         "h":  21,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "8.3",
    "height":  107
}
-->

<details>
<summary><strong>Champs : 2 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 114,18 | 13.2C | - | edit |
| 114,43 | credit conso | - | combobox |

</details>

<details>
<summary><strong>Boutons : 3 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Débit | 88,81 | Bouton fonctionnel |
| Annuler | 189,82 | Annule et retour au menu |
| Crédit | 6,81 | Bouton fonctionnel |

</details>

---

#### <a id="ecran-t13"></a>8.4 - Impression des credit de conso
**Tache** : [8.4](#t13) | **Type** : MDI | **Dimensions** : 640 x 118 DLU
**Bloc** : Traitement | **Titre IDE** : Impression des credit de conso

<!-- FORM-DATA:
{
    "width":  640,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  31,
                         "type":  "label",
                         "var":  "",
                         "y":  14,
                         "w":  578,
                         "fmt":  "",
                         "name":  "",
                         "h":  55,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  219,
                         "type":  "label",
                         "var":  "",
                         "y":  18,
                         "w":  353,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Crédit de conso deposés",
                         "parent":  null
                     },
                     {
                         "x":  299,
                         "type":  "label",
                         "var":  "",
                         "y":  37,
                         "w":  80,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Du",
                         "parent":  null
                     },
                     {
                         "x":  299,
                         "type":  "label",
                         "var":  "",
                         "y":  53,
                         "w":  80,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Au",
                         "parent":  null
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  93,
                         "w":  636,
                         "fmt":  "",
                         "name":  "",
                         "h":  23,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  405,
                         "type":  "edit",
                         "var":  "",
                         "y":  37,
                         "w":  126,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  405,
                         "type":  "edit",
                         "var":  "",
                         "y":  53,
                         "w":  126,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  314,
                         "type":  "button",
                         "var":  "",
                         "y":  96,
                         "w":  154,
                         "fmt":  "\u0026Valider",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  475,
                         "type":  "button",
                         "var":  "",
                         "y":  96,
                         "w":  154,
                         "fmt":  "\u0026Quitter",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  32,
                         "type":  "image",
                         "var":  "",
                         "y":  15,
                         "w":  157,
                         "fmt":  "",
                         "name":  "",
                         "h":  53,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "8.4",
    "height":  118
}
-->

<details>
<summary><strong>Champs : 2 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 405,37 | (sans nom) | - | edit |
| 405,53 | (sans nom) | - | edit |

</details>

<details>
<summary><strong>Boutons : 2 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Valider | 314,96 | Valide la saisie et enregistre |
| Quitter | 475,96 | Quitte le programme |

</details>

---

#### <a id="ecran-t14"></a>8.4.1 - Gratuites bar GM
**Tache** : [8.4.1](#t14) | **Type** : MDI | **Dimensions** : 424 x 57 DLU
**Bloc** : Traitement | **Titre IDE** : Gratuites bar GM

<!-- FORM-DATA:
{
    "width":  424,
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
                         "x":  119,
                         "type":  "label",
                         "var":  "",
                         "y":  10,
                         "w":  266,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "142",
                         "text":  "Impression en cours ...",
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
                         "x":  51,
                         "type":  "label",
                         "var":  "",
                         "y":  38,
                         "w":  318,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Impression gratuites Bar GM",
                         "parent":  null
                     },
                     {
                         "x":  3,
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
    "taskId":  "8.4.1",
    "height":  57
}
-->

## 9. NAVIGATION

### 9.1 Enchainement des ecrans

```mermaid
flowchart TD
    START([Entree])
    style START fill:#3fb950
    VF2[8.1 Credits de conso GM...]
    style VF2 fill:#58a6ff
    VF3[8.1.1 credit conso par type]
    style VF3 fill:#58a6ff
    VF4[8.1.2 detail credit conso]
    style VF4 fill:#58a6ff
    VF5[8.2 Credit de conso]
    style VF5 fill:#58a6ff
    VF12[8.3 DebitCredit en groupe]
    style VF12 fill:#58a6ff
    VF13[8.4 Impression des cre...]
    style VF13 fill:#58a6ff
    VF14[8.4.1 Gratuites bar GM]
    style VF14 fill:#58a6ff
    EXT12[IDE 12 Combo - type cr...]
    style EXT12 fill:#3fb950
    FIN([Sortie])
    style FIN fill:#f85149
    START --> VF2
    VF2 -->|Sous-programme| EXT12
    EXT12 --> FIN
```

**Detail par enchainement :**

| Depuis | Action | Vers | Retour |
|--------|--------|------|--------|
| Credits de conso GM Exterieurs | Sous-programme | [Combo - type credit conso (IDE 12)](GES-IDE-12.md) | Retour ecran |

### 9.3 Structure hierarchique (16 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **8.1** | [**Gratuites GM** (8)](#t1) | MDI | - | Traitement |
| 8.1.1 | [Credits de conso GM Exterieurs (8.1)](#t2) [mockup](#ecran-t2) | MDI | 1260x314 | |
| 8.1.2 | [credit conso par type (8.1.1)](#t3) [mockup](#ecran-t3) | Modal | 254x72 | |
| 8.1.3 | [detail credit conso (8.1.2)](#t4) [mockup](#ecran-t4) | Modal | 348x70 | |
| 8.1.4 | [Credit de conso (8.2)](#t5) [mockup](#ecran-t5) | MDI | 423x56 | |
| 8.1.5 | [Credit de conso (8.2.1)](#t6) [mockup](#ecran-t6) | MDI | 214x81 | |
| 8.1.6 | [CC rejet (8.2.2)](#t9) | MDI | - | |
| 8.1.7 | [Gratuites bar GO (8.2.3)](#t10) [mockup](#ecran-t10) | MDI | 424x57 | |
| 8.1.8 | [vide CC rejet (8.2.4)](#t11) | MDI | - | |
| 8.1.9 | [Debit/Credit en groupe (8.3)](#t12) [mockup](#ecran-t12) | MDI | 274x107 | |
| 8.1.10 | [Impression des credit de conso (8.4)](#t13) [mockup](#ecran-t13) | MDI | 640x118 | |
| 8.1.11 | [Gratuites bar GM (8.4.1)](#t14) [mockup](#ecran-t14) | MDI | 424x57 | |
| 8.1.12 | [Browse - CC detail (8.4.1.1)](#t15) | MDI | - | |
| 8.1.13 | [Browse - CC par type (8.4.1.2)](#t16) | MDI | - | |
| **8.2** | [**CC Comptable** (8.2.1.1)](#t7) [mockup](#ecran-t7) | MDI | 128x52 | Calcul |
| 8.2.1 | [CC Comptable Intermed (8.2.1.2)](#t8) [mockup](#ecran-t8) | MDI | 87x59 | |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Affiche GM]
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

### Tables utilisees (13)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 23 | reseau_cloture___rec | Donnees reseau/cloture | DB | R |   |   | 1 |
| 31 | gm-complet_______gmc |  | DB | R |   |   | 1 |
| 34 | hebergement______heb | Hebergement (chambres) | DB |   |   | L | 2 |
| 47 | compte_gm________cgm | Comptes GM (generaux) | DB |   |   | L | 1 |
| 70 | date_comptable___dat |  | DB | R |   |   | 2 |
| 266 | cc_comptable |  | DB |   |   | L | 1 |
| 267 | cc_comptable_intermed |  | DB |   |   | L | 1 |
| 268 | cc_total_par_type |  | DB | R |   | L | 3 |
| 269 | ccrejet |  | DB | R | **W** | L | 4 |
| 271 | cc_total |  | DB |   | **W** | L | 2 |
| 272 | cc_type_detail |  | DB | R |   | L | 4 |
| 273 | cc_type |  | DB | R |   | L | 5 |
| 786 | qualite_avant_reprise |  | DB | R |   | L | 3 |

### Colonnes par table (8 / 9 tables avec colonnes identifiees)

<details>
<summary>Table 23 - reseau_cloture___rec (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | r.compte bloque | R | Logical |
| B | r.cloture en cours | R | Logical |
| C | r.erreur cc | R | Logical |

</details>

<details>
<summary>Table 31 - gm-complet_______gmc (R) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 70 - date_comptable___dat (R) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | v.date du | R | Date |
| B | v.date au | R | Date |
| J | v.date operation | R | Date |

</details>

<details>
<summary>Table 268 - cc_total_par_type (R/L) - 3 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | v.combo type CS | R | Alpha |
| B | v.combo type credit conso | R | Alpha |
| C | v.total restant | R | Numeric |
| D | v.total depose | R | Numeric |
| G | v.type CS | R | Alpha |
| L | v.List combo type CS | R | Alpha |

</details>

<details>
<summary>Table 269 - ccrejet (R/**W**/L) - 4 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 271 - cc_total (**W**/L) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| C | v.total restant | W | Numeric |
| D | v.total depose | W | Numeric |

</details>

<details>
<summary>Table 272 - cc_type_detail (R/L) - 4 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | v.combo type CS | R | Alpha |
| B | v.combo type credit conso | R | Alpha |
| G | v.type CS | R | Alpha |
| L | v.List combo type CS | R | Alpha |

</details>

<details>
<summary>Table 273 - cc_type (R/L) - 5 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | p.societe | R | Alpha |
| B | p.masque-mtt-compte GM | R | Alpha |
| C | p.code-devise | R | Alpha |
| D | p.nom village | R | Alpha |
| E | v.action | R | Alpha |
| F | v.montant | R | Numeric |
| G | v.type CS | R | Alpha |
| H | v.code-gm | R | Numeric |
| I | v.filiation | R | Numeric |
| J | v.date operation | R | Date |
| K | v.heure operation | R | Time |
| L | v.List combo type CS | R | Alpha |
| M | v.last name | R | Alpha |
| N | v.last action sur 2 | R | Alpha |

</details>

<details>
<summary>Table 786 - qualite_avant_reprise (R/L) - 3 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | v.combo type CS | R | Alpha |
| B | v.cummul type depose | R | Numeric |
| C | v.total restant | R | Numeric |
| D | v.total depose | R | Numeric |
| E | v.nom prenom cpt | R | Alpha |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (4)

Variables recues du programme appelant ([MENU  Club Med Pass (IDE 5)](GES-IDE-5.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | p.societe | Alpha | 1x parametre entrant |
| B | p.masque-mtt-compte GM | Alpha | - |
| C | p.code-devise | Alpha | - |
| D | p.nom village | Alpha | - |

### 11.2 Variables de session (10)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| E | v.action | Alpha | 4x session |
| F | v.montant | Numeric | - |
| G | v.type CS | Alpha | 1x session |
| H | v.code-gm | Numeric | - |
| I | v.filiation | Numeric | - |
| J | v.date operation | Date | - |
| K | v.heure operation | Time | - |
| L | v.List combo type CS | Alpha | - |
| M | v.last name | Alpha | - |
| N | v.last action sur 2 | Alpha | - |

## 12. EXPRESSIONS

**12 / 12 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONSTANTE | 2 | 0 |
| DATE | 1 | 0 |
| CONDITION | 5 | 0 |
| CAST_LOGIQUE | 2 | 0 |
| OTHER | 2 | 0 |

### 12.2 Expressions cles par type

#### CONSTANTE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 3 | `'F'` | - |
| CONSTANTE | 1 | `'C'` | - |

#### DATE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| DATE | 11 | `Date ()` | - |

#### CONDITION (5 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 6 | `v.action [E]='V'` | - |
| CONDITION | 7 | `v.action [E]='H'` | - |
| CONDITION | 5 | `v.action [E]='G'` | - |
| CONDITION | 2 | `p.societe [A]=''` | - |
| CONDITION | 4 | `v.action [E]='F'` | - |

#### CAST_LOGIQUE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 9 | `'TRUE'LOG` | - |
| CAST_LOGIQUE | 8 | `'FALSE'LOG` | - |

#### OTHER (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 12 | `Time ()` | - |
| OTHER | 10 | `v.type CS [G]` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [MENU  Club Med Pass (IDE 5)](GES-IDE-5.md) -> **Gratuites GM exterieurs (IDE 8)**

```mermaid
graph LR
    T8[8 Gratuites GM exterieurs]
    style T8 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC69[69 Menu gestion]
    style CC69 fill:#f59e0b
    CC5[5 MENU Club Med Pass]
    style CC5 fill:#3fb950
    CC69 --> CC5
    CC1 --> CC69
    CC5 --> T8
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [5](GES-IDE-5.md) | MENU  Club Med Pass | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T8[8 Gratuites GM exterieurs]
    style T8 fill:#58a6ff
    C12[12 Combo - type credit...]
    T8 --> C12
    style C12 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [12](GES-IDE-12.md) | Combo - type credit conso | 1 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 309 | Taille moyenne |
| Expressions | 12 | Peu de logique |
| Tables WRITE | 2 | Impact faible |
| Sous-programmes | 1 | Peu de dependances |
| Ecrans visibles | 7 | Interface complexe multi-ecrans |
| Code desactive | 0% (0 / 309) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (14 taches: 9 ecrans, 5 traitements)

- **Strategie** : Orchestrateur avec 9 ecrans (Razor/React) et 5 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 1 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Calcul (2 taches: 2 ecrans, 0 traitement)

- **Strategie** : Services de calcul purs (Domain Services).
- Migrer la logique de calcul (stock, compteurs, montants)

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| ccrejet | Table WRITE (Database) | 1x | Schema + repository |
| cc_total | Table WRITE (Database) | 1x | Schema + repository |
| [Combo - type credit conso (IDE 12)](GES-IDE-12.md) | Sous-programme | 1x | Normale - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 11:26*
