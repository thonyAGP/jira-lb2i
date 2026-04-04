# GES IDE 7 - Gratuites GM

> **Analyse**: Phases 1-4 2026-02-03 11:25 -> 11:25 (14s) | Assemblage 11:25
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | GES |
| IDE Position | 7 |
| Nom Programme | Gratuites GM |
| Fichier source | `Prg_7.xml` |
| Dossier IDE | Bar |
| Taches | 16 (7 ecrans visibles) |
| Tables modifiees | 2 |
| Programmes appeles | 2 |

## 2. DESCRIPTION FONCTIONNELLE

**Gratuites GM** assure la gestion complete de ce processus, accessible depuis [MENU  Club Med Pass (IDE 5)](GES-IDE-5.md).

Le flux de traitement s'organise en **2 blocs fonctionnels** :

- **Traitement** (14 taches) : traitements metier divers
- **Calcul** (2 taches) : calculs de montants, stocks ou compteurs

**Donnees modifiees** : 2 tables en ecriture (ccrejet, cc_total).

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (14 taches)

- **7** - Gratuites GM
- **7.1** - Credits de conso GM **[[ECRAN]](#ecran-t2)**
- **7.1.1** - credit conso par type **[[ECRAN]](#ecran-t3)**
- **7.1.2** - detail credit conso **[[ECRAN]](#ecran-t4)**
- **7.2** - Credit de conso **[[ECRAN]](#ecran-t5)**
- **7.2.1** - Credit de conso **[[ECRAN]](#ecran-t6)**
- **7.2.2** - CC rejet
- **7.2.3** - Gratuites bar GO **[[ECRAN]](#ecran-t10)**
- **7.2.4** - vide CC rejet
- **7.3** - Debit/Credit en groupe **[[ECRAN]](#ecran-t12)**
- **7.4** - Impression des credit de conso **[[ECRAN]](#ecran-t13)**
- **7.4.1** - Gratuites bar GM **[[ECRAN]](#ecran-t14)**
- **7.4.1.1** - Browse - CC detail
- **7.4.1.2** - Browse - CC par type

Delegue a : [Combo - type credit conso (IDE 12)](GES-IDE-12.md)

#### Phase 2 : Calcul (2 taches)

- **7.2.1.1** - CC Comptable **[[ECRAN]](#ecran-t7)**
- **7.2.1.2** - CC Comptable Intermed **[[ECRAN]](#ecran-t8)**

Delegue a : [Compte les seminaires (IDE 13)](GES-IDE-13.md)

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

#### <a id="t1"></a>7 - Gratuites GM

**Role** : Tache d'orchestration : point d'entree du programme (14 sous-taches). Coordonne l'enchainement des traitements.

<details>
<summary>13 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [7.1](#t2) | Credits de conso GM **[[ECRAN]](#ecran-t2)** | Traitement |
| [7.1.1](#t3) | credit conso par type **[[ECRAN]](#ecran-t3)** | Traitement |
| [7.1.2](#t4) | detail credit conso **[[ECRAN]](#ecran-t4)** | Traitement |
| [7.2](#t5) | Credit de conso **[[ECRAN]](#ecran-t5)** | Traitement |
| [7.2.1](#t6) | Credit de conso **[[ECRAN]](#ecran-t6)** | Traitement |
| [7.2.2](#t9) | CC rejet | Traitement |
| [7.2.3](#t10) | Gratuites bar GO **[[ECRAN]](#ecran-t10)** | Traitement |
| [7.2.4](#t11) | vide CC rejet | Traitement |
| [7.3](#t12) | Debit/Credit en groupe **[[ECRAN]](#ecran-t12)** | Traitement |
| [7.4](#t13) | Impression des credit de conso **[[ECRAN]](#ecran-t13)** | Traitement |
| [7.4.1](#t14) | Gratuites bar GM **[[ECRAN]](#ecran-t14)** | Traitement |
| [7.4.1.1](#t15) | Browse - CC detail | Traitement |
| [7.4.1.2](#t16) | Browse - CC par type | Traitement |

</details>

---

#### <a id="t2"></a>7.1 - Credits de conso GM [[ECRAN]](#ecran-t2)

**Role** : Calcul fidelite/avantage : Credits de conso GM.
**Ecran** : 1260 x 314 DLU (MDI) | [Voir mockup](#ecran-t2)

---

#### <a id="t3"></a>7.1.1 - credit conso par type [[ECRAN]](#ecran-t3)

**Role** : Calcul fidelite/avantage : credit conso par type.
**Ecran** : 251 x 73 DLU (Modal) | [Voir mockup](#ecran-t3)
**Variables liees** : K (v.type CS), P (v.List combo type CS)

---

#### <a id="t4"></a>7.1.2 - detail credit conso [[ECRAN]](#ecran-t4)

**Role** : Calcul fidelite/avantage : detail credit conso.
**Ecran** : 348 x 70 DLU (Modal) | [Voir mockup](#ecran-t4)

---

#### <a id="t5"></a>7.2 - Credit de conso [[ECRAN]](#ecran-t5)

**Role** : Calcul fidelite/avantage : Credit de conso.
**Ecran** : 423 x 56 DLU (MDI) | [Voir mockup](#ecran-t5)

---

#### <a id="t6"></a>7.2.1 - Credit de conso [[ECRAN]](#ecran-t6)

**Role** : Calcul fidelite/avantage : Credit de conso.
**Ecran** : 214 x 81 DLU (MDI) | [Voir mockup](#ecran-t6)

---

#### <a id="t9"></a>7.2.2 - CC rejet

**Role** : Traitement : CC rejet.

---

#### <a id="t10"></a>7.2.3 - Gratuites bar GO [[ECRAN]](#ecran-t10)

**Role** : Traitement : Gratuites bar GO.
**Ecran** : 424 x 57 DLU (MDI) | [Voir mockup](#ecran-t10)

---

#### <a id="t11"></a>7.2.4 - vide CC rejet

**Role** : Traitement : vide CC rejet.

---

#### <a id="t12"></a>7.3 - Debit/Credit en groupe [[ECRAN]](#ecran-t12)

**Role** : Calcul fidelite/avantage : Debit/Credit en groupe.
**Ecran** : 273 x 107 DLU (MDI) | [Voir mockup](#ecran-t12)
**Variables liees** : Q (v.confirmation groupe)

---

#### <a id="t13"></a>7.4 - Impression des credit de conso [[ECRAN]](#ecran-t13)

**Role** : Generation du document : Impression des credit de conso.
**Ecran** : 640 x 120 DLU (MDI) | [Voir mockup](#ecran-t13)

---

#### <a id="t14"></a>7.4.1 - Gratuites bar GM [[ECRAN]](#ecran-t14)

**Role** : Traitement : Gratuites bar GM.
**Ecran** : 424 x 57 DLU (MDI) | [Voir mockup](#ecran-t14)

---

#### <a id="t15"></a>7.4.1.1 - Browse - CC detail

**Role** : Traitement : Browse - CC detail.

---

#### <a id="t16"></a>7.4.1.2 - Browse - CC par type

**Role** : Traitement : Browse - CC par type.
**Variables liees** : K (v.type CS), P (v.List combo type CS)


### 3.2 Calcul (2 taches)

Calculs metier : montants, stocks, compteurs.

---

#### <a id="t7"></a>7.2.1.1 - CC Comptable [[ECRAN]](#ecran-t7)

**Role** : Traitement : CC Comptable.
**Ecran** : 128 x 52 DLU (MDI) | [Voir mockup](#ecran-t7)
**Delegue a** : [Compte les seminaires (IDE 13)](GES-IDE-13.md)

---

#### <a id="t8"></a>7.2.1.2 - CC Comptable Intermed [[ECRAN]](#ecran-t8)

**Role** : Traitement : CC Comptable Intermed.
**Ecran** : 87 x 59 DLU (MDI) | [Voir mockup](#ecran-t8)
**Delegue a** : [Compte les seminaires (IDE 13)](GES-IDE-13.md)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [MENU  Club Med Pass (IDE 5)](GES-IDE-5.md)
- **Appelle**: 2 programmes | **Tables**: 12 (W:2 R:8 L:9) | **Taches**: 16 | **Expressions**: 15

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (7 / 16)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 7.1 | 7.1 | Credits de conso GM | MDI | 1260 | 314 | Traitement |
| 2 | 7.1.1 | 7.1.1 | credit conso par type | Modal | 251 | 73 | Traitement |
| 3 | 7.1.2 | 7.1.2 | detail credit conso | Modal | 348 | 70 | Traitement |
| 4 | 7.2 | 7.2 | Credit de conso | MDI | 423 | 56 | Traitement |
| 5 | 7.3 | 7.3 | Debit/Credit en groupe | MDI | 273 | 107 | Traitement |
| 6 | 7.4 | 7.4 | Impression des credit de conso | MDI | 640 | 120 | Traitement |
| 7 | 7.4.1 | 7.4.1 | Gratuites bar GM | MDI | 424 | 57 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t2"></a>7.1 - Credits de conso GM
**Tache** : [7.1](#t2) | **Type** : MDI | **Dimensions** : 1260 x 314 DLU
**Bloc** : Traitement | **Titre IDE** : Credits de conso GM

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
                         "x":  41,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  15,
                         "color":  "6",
                         "w":  1184,
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
                                          "w":  211
                                      },
                                      {
                                          "title":  "Prénom",
                                          "layer":  2,
                                          "w":  167
                                      },
                                      {
                                          "title":  "Séminaire",
                                          "layer":  3,
                                          "w":  262
                                      },
                                      {
                                          "title":  "Date début",
                                          "layer":  4,
                                          "w":  134
                                      },
                                      {
                                          "title":  "Date fin",
                                          "layer":  5,
                                          "w":  135
                                      },
                                      {
                                          "title":  "Crédit de conso",
                                          "layer":  6,
                                          "w":  241
                                      }
                                  ],
                         "rows":  6
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
                         "y":  145,
                         "w":  328,
                         "fmt":  "",
                         "name":  "",
                         "h":  57,
                         "color":  "",
                         "text":  "Filtre",
                         "parent":  null
                     },
                     {
                         "x":  394,
                         "type":  "label",
                         "var":  "",
                         "y":  145,
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
                         "y":  145,
                         "w":  383,
                         "fmt":  "",
                         "name":  "",
                         "h":  35,
                         "color":  "",
                         "text":  "Impression",
                         "parent":  null
                     },
                     {
                         "x":  124,
                         "type":  "label",
                         "var":  "",
                         "y":  153,
                         "w":  154,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Seminaire",
                         "parent":  19
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
                         "text":  "Position par type de credit",
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
                         "x":  50,
                         "type":  "edit",
                         "var":  "",
                         "y":  42,
                         "w":  200,
                         "fmt":  "",
                         "name":  "GM nom",
                         "h":  11,
                         "color":  "6",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  266,
                         "type":  "edit",
                         "var":  "",
                         "y":  42,
                         "w":  122,
                         "fmt":  "",
                         "name":  "GM prenom",
                         "h":  11,
                         "color":  "6",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  429,
                         "type":  "edit",
                         "var":  "",
                         "y":  42,
                         "w":  252,
                         "fmt":  "",
                         "name":  "",
                         "h":  11,
                         "color":  "6",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  694,
                         "type":  "edit",
                         "var":  "",
                         "y":  42,
                         "w":  120,
                         "fmt":  "",
                         "name":  "",
                         "h":  11,
                         "color":  "6",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  824,
                         "type":  "edit",
                         "var":  "",
                         "y":  42,
                         "w":  120,
                         "fmt":  "",
                         "name":  "",
                         "h":  11,
                         "color":  "6",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  984,
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
                         "type":  "edit",
                         "var":  "",
                         "y":  163,
                         "w":  157,
                         "fmt":  "",
                         "name":  "v.Seminaire",
                         "h":  14,
                         "color":  "6",
                         "text":  "",
                         "parent":  19
                     },
                     {
                         "x":  229,
                         "type":  "edit",
                         "var":  "",
                         "y":  163,
                         "w":  130,
                         "fmt":  "",
                         "name":  "",
                         "h":  14,
                         "color":  "6",
                         "text":  "",
                         "parent":  19
                     },
                     {
                         "x":  66,
                         "type":  "combobox",
                         "var":  "",
                         "y":  181,
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
                         "x":  539,
                         "type":  "button",
                         "var":  "",
                         "y":  159,
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
                         "y":  159,
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
                         "y":  159,
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
                         "y":  159,
                         "w":  129,
                         "fmt":  "Groupe",
                         "name":  "HG",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  229,
                         "type":  "button",
                         "var":  "",
                         "y":  181,
                         "w":  130,
                         "fmt":  "Rafraichir",
                         "name":  "J",
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
    "taskId":  "7.1",
    "height":  314
}
-->

<details>
<summary><strong>Champs : 11 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 50,42 | GM nom | - | edit |
| 266,42 | GM prenom | - | edit |
| 429,42 | (sans nom) | - | edit |
| 694,42 | (sans nom) | - | edit |
| 824,42 | (sans nom) | - | edit |
| 984,42 | (sans nom) | - | edit |
| 66,163 | v.Seminaire | - | edit |
| 229,163 | (sans nom) | - | edit |
| 66,181 | v.combo type CS | - | combobox |
| 14,5 | 30 | - | edit |
| 950,5 | WWW DD MMM YYYYT | - | edit |

</details>

<details>
<summary><strong>Boutons : 6 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Individuel | 539,159 | Bouton fonctionnel |
| Groupe | 676,159 | Bouton fonctionnel |
| Individuel | 952,159 | Bouton fonctionnel |
| Groupe | 1089,159 | Bouton fonctionnel |
| Rafraichir | 229,181 | Bouton fonctionnel |
| Quitter | 1088,295 | Quitte le programme |

</details>

---

#### <a id="ecran-t3"></a>7.1.1 - credit conso par type
**Tache** : [7.1.1](#t3) | **Type** : Modal | **Dimensions** : 251 x 73 DLU
**Bloc** : Traitement | **Titre IDE** : credit conso par type

<!-- FORM-DATA:
{
    "width":  251,
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
                         "w":  240,
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
    "taskId":  "7.1.1",
    "height":  73
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

#### <a id="ecran-t4"></a>7.1.2 - detail credit conso
**Tache** : [7.1.2](#t4) | **Type** : Modal | **Dimensions** : 348 x 70 DLU
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
                         "w":  318,
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
                                          "w":  68
                                      }
                                  ],
                         "rows":  4
                     },
                     {
                         "x":  5,
                         "type":  "label",
                         "var":  "",
                         "y":  2,
                         "w":  314,
                         "fmt":  "",
                         "name":  "",
                         "h":  15,
                         "color":  "5",
                         "text":  "",
                         "parent":  null
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
    "taskId":  "7.1.2",
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

#### <a id="ecran-t5"></a>7.2 - Credit de conso
**Tache** : [7.2](#t5) | **Type** : MDI | **Dimensions** : 423 x 56 DLU
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
    "taskId":  "7.2",
    "height":  56
}
-->

---

#### <a id="ecran-t12"></a>7.3 - Debit/Credit en groupe
**Tache** : [7.3](#t12) | **Type** : MDI | **Dimensions** : 273 x 107 DLU
**Bloc** : Traitement | **Titre IDE** : Debit/Credit en groupe

<!-- FORM-DATA:
{
    "width":  273,
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
                         "y":  74,
                         "w":  271,
                         "fmt":  "",
                         "name":  "",
                         "h":  31,
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
                         "h":  14,
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
    "taskId":  "7.3",
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

#### <a id="ecran-t13"></a>7.4 - Impression des credit de conso
**Tache** : [7.4](#t13) | **Type** : MDI | **Dimensions** : 640 x 120 DLU
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
    "taskId":  "7.4",
    "height":  120
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

#### <a id="ecran-t14"></a>7.4.1 - Gratuites bar GM
**Tache** : [7.4.1](#t14) | **Type** : MDI | **Dimensions** : 424 x 57 DLU
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
    "taskId":  "7.4.1",
    "height":  57
}
-->

## 9. NAVIGATION

### 9.1 Enchainement des ecrans

```mermaid
flowchart TD
    START([Entree])
    style START fill:#3fb950
    VF2[7.1 Credits de conso GM]
    style VF2 fill:#58a6ff
    VF3[7.1.1 credit conso par type]
    style VF3 fill:#58a6ff
    VF4[7.1.2 detail credit conso]
    style VF4 fill:#58a6ff
    VF5[7.2 Credit de conso]
    style VF5 fill:#58a6ff
    VF12[7.3 DebitCredit en groupe]
    style VF12 fill:#58a6ff
    VF13[7.4 Impression des cre...]
    style VF13 fill:#58a6ff
    VF14[7.4.1 Gratuites bar GM]
    style VF14 fill:#58a6ff
    EXT12[IDE 12 Combo - type cr...]
    style EXT12 fill:#3fb950
    EXT13[IDE 13 Compte les semi...]
    style EXT13 fill:#3fb950
    FIN([Sortie])
    style FIN fill:#f85149
    START --> VF2
    VF2 -->|Sous-programme| EXT12
    VF2 -->|Sous-programme| EXT13
    EXT13 --> FIN
```

**Detail par enchainement :**

| Depuis | Action | Vers | Retour |
|--------|--------|------|--------|
| Credits de conso GM | Sous-programme | [Combo - type credit conso (IDE 12)](GES-IDE-12.md) | Retour ecran |
| Credits de conso GM | Sous-programme | [Compte les seminaires (IDE 13)](GES-IDE-13.md) | Retour ecran |

### 9.3 Structure hierarchique (16 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **7.1** | [**Gratuites GM** (7)](#t1) | MDI | - | Traitement |
| 7.1.1 | [Credits de conso GM (7.1)](#t2) [mockup](#ecran-t2) | MDI | 1260x314 | |
| 7.1.2 | [credit conso par type (7.1.1)](#t3) [mockup](#ecran-t3) | Modal | 251x73 | |
| 7.1.3 | [detail credit conso (7.1.2)](#t4) [mockup](#ecran-t4) | Modal | 348x70 | |
| 7.1.4 | [Credit de conso (7.2)](#t5) [mockup](#ecran-t5) | MDI | 423x56 | |
| 7.1.5 | [Credit de conso (7.2.1)](#t6) [mockup](#ecran-t6) | MDI | 214x81 | |
| 7.1.6 | [CC rejet (7.2.2)](#t9) | MDI | - | |
| 7.1.7 | [Gratuites bar GO (7.2.3)](#t10) [mockup](#ecran-t10) | MDI | 424x57 | |
| 7.1.8 | [vide CC rejet (7.2.4)](#t11) | MDI | - | |
| 7.1.9 | [Debit/Credit en groupe (7.3)](#t12) [mockup](#ecran-t12) | MDI | 273x107 | |
| 7.1.10 | [Impression des credit de conso (7.4)](#t13) [mockup](#ecran-t13) | MDI | 640x120 | |
| 7.1.11 | [Gratuites bar GM (7.4.1)](#t14) [mockup](#ecran-t14) | MDI | 424x57 | |
| 7.1.12 | [Browse - CC detail (7.4.1.1)](#t15) | MDI | - | |
| 7.1.13 | [Browse - CC par type (7.4.1.2)](#t16) | MDI | - | |
| **7.2** | [**CC Comptable** (7.2.1.1)](#t7) [mockup](#ecran-t7) | MDI | 128x52 | Calcul |
| 7.2.1 | [CC Comptable Intermed (7.2.1.2)](#t8) [mockup](#ecran-t8) | MDI | 87x59 | |

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

### Tables utilisees (12)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 23 | reseau_cloture___rec | Donnees reseau/cloture | DB | R |   |   | 1 |
| 31 | gm-complet_______gmc |  | DB | R |   |   | 1 |
| 36 | client_gm |  | DB | R |   | L | 3 |
| 47 | compte_gm________cgm | Comptes GM (generaux) | DB |   |   | L | 1 |
| 70 | date_comptable___dat |  | DB | R |   |   | 2 |
| 266 | cc_comptable |  | DB |   |   | L | 2 |
| 267 | cc_comptable_intermed |  | DB |   |   | L | 2 |
| 268 | cc_total_par_type |  | DB | R |   | L | 3 |
| 269 | ccrejet |  | DB | R | **W** | L | 4 |
| 271 | cc_total |  | DB |   | **W** | L | 2 |
| 272 | cc_type_detail |  | DB | R |   | L | 4 |
| 273 | cc_type |  | DB | R |   | L | 5 |

### Colonnes par table (8 / 9 tables avec colonnes identifiees)

<details>
<summary>Table 23 - reseau_cloture___rec (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | ici | R | Alpha |
| B | r.compte bloque | R | Logical |
| C | r.cloture en cours | R | Logical |
| D | r.erreur cc | R | Logical |

</details>

<details>
<summary>Table 31 - gm-complet_______gmc (R) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 36 - client_gm (R/L) - 3 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | v.Seminaire | R | Alpha |
| B | v.date seminaire | R | Date |
| C | v.combo type CS | R | Alpha |
| D | v.total depose | R | Numeric |
| E | v.nom prenom cpt | R | Alpha |

</details>

<details>
<summary>Table 70 - date_comptable___dat (R) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | v.date du | R | Date |
| B | v.date seminaire | R | Date |
| H | F.date du seminaire | R | Date |
| I | F.date au seminaire | R | Date |
| N | v.date operation | R | Date |

</details>

<details>
<summary>Table 268 - cc_total_par_type (R/L) - 3 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | v.cummul type restant | R | Numeric |
| B | v.combo type credit conso | R | Alpha |
| C | v.combo type CS | R | Alpha |
| D | v.total depose | R | Numeric |
| K | v.type CS | R | Alpha |
| P | v.List combo type CS | R | Alpha |

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
| A | v.cummul type restant | R | Numeric |
| B | v.combo type credit conso | R | Alpha |
| C | v.combo type CS | R | Alpha |
| K | v.type CS | R | Alpha |
| P | v.List combo type CS | R | Alpha |

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
| F | F.qualite | R | Alpha |
| G | F.seminaire | R | Alpha |
| H | F.date du seminaire | R | Date |
| I | F.date au seminaire | R | Date |
| J | v.montant | R | Numeric |
| K | v.type CS | R | Alpha |
| L | v.code-gm | R | Numeric |
| M | v.filiation | R | Numeric |
| N | v.date operation | R | Date |
| O | v.heure operation | R | Time |
| P | v.List combo type CS | R | Alpha |
| Q | v.confirmation groupe | R | Numeric |
| R | v.last action sur 2 | R | Alpha |
| S | v.last name | R | Alpha |

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

### 11.2 Variables de session (11)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| E | v.action | Alpha | 4x session |
| J | v.montant | Numeric | - |
| K | v.type CS | Alpha | 1x session |
| L | v.code-gm | Numeric | - |
| M | v.filiation | Numeric | - |
| N | v.date operation | Date | - |
| O | v.heure operation | Time | - |
| P | v.List combo type CS | Alpha | - |
| Q | v.confirmation groupe | Numeric | - |
| R | v.last action sur 2 | Alpha | - |
| S | v.last name | Alpha | 1x session |

### 11.3 Autres (4)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| F | F.qualite | Alpha | - |
| G | F.seminaire | Alpha | - |
| H | F.date du seminaire | Date | - |
| I | F.date au seminaire | Date | - |

<details>
<summary>Toutes les 19 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| P0 | **A** | p.societe | Alpha |
| P0 | **B** | p.masque-mtt-compte GM | Alpha |
| P0 | **C** | p.code-devise | Alpha |
| P0 | **D** | p.nom village | Alpha |
| V. | **E** | v.action | Alpha |
| V. | **J** | v.montant | Numeric |
| V. | **K** | v.type CS | Alpha |
| V. | **L** | v.code-gm | Numeric |
| V. | **M** | v.filiation | Numeric |
| V. | **N** | v.date operation | Date |
| V. | **O** | v.heure operation | Time |
| V. | **P** | v.List combo type CS | Alpha |
| V. | **Q** | v.confirmation groupe | Numeric |
| V. | **R** | v.last action sur 2 | Alpha |
| V. | **S** | v.last name | Alpha |
| Autre | **F** | F.qualite | Alpha |
| Autre | **G** | F.seminaire | Alpha |
| Autre | **H** | F.date du seminaire | Date |
| Autre | **I** | F.date au seminaire | Date |

</details>

## 12. EXPRESSIONS

**15 / 15 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONSTANTE | 2 | 0 |
| DATE | 1 | 0 |
| CONDITION | 8 | 0 |
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
| DATE | 13 | `Date ()` | - |

#### CONDITION (8 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 8 | `[T]='GG'` | - |
| CONDITION | 7 | `v.action [E]='H'` | - |
| CONDITION | 15 | `v.last name [S]=6` | - |
| CONDITION | 9 | `[T]='GI'` | - |
| CONDITION | 4 | `v.action [E]='F'` | - |
| ... | | *+3 autres* | |

#### CAST_LOGIQUE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 11 | `'TRUE'LOG` | - |
| CAST_LOGIQUE | 10 | `'FALSE'LOG` | - |

#### OTHER (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 14 | `Time ()` | - |
| OTHER | 12 | `v.type CS [K]` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [MENU  Club Med Pass (IDE 5)](GES-IDE-5.md) -> **Gratuites GM (IDE 7)**

```mermaid
graph LR
    T7[7 Gratuites GM]
    style T7 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC69[69 Menu gestion]
    style CC69 fill:#f59e0b
    CC5[5 MENU Club Med Pass]
    style CC5 fill:#3fb950
    CC69 --> CC5
    CC1 --> CC69
    CC5 --> T7
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [5](GES-IDE-5.md) | MENU  Club Med Pass | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T7[7 Gratuites GM]
    style T7 fill:#58a6ff
    C12[12 Combo - type credit...]
    T7 --> C12
    style C12 fill:#3fb950
    C13[13 Compte les seminaires]
    T7 --> C13
    style C13 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [12](GES-IDE-12.md) | Combo - type credit conso | 1 | Sous-programme |
| [13](GES-IDE-13.md) | Compte les seminaires | 1 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 323 | Taille moyenne |
| Expressions | 15 | Peu de logique |
| Tables WRITE | 2 | Impact faible |
| Sous-programmes | 2 | Peu de dependances |
| Ecrans visibles | 7 | Interface complexe multi-ecrans |
| Code desactive | 0% (0 / 323) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (14 taches: 9 ecrans, 5 traitements)

- **Strategie** : Orchestrateur avec 9 ecrans (Razor/React) et 5 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 2 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Calcul (2 taches: 2 ecrans, 0 traitement)

- **Strategie** : Services de calcul purs (Domain Services).
- Migrer la logique de calcul (stock, compteurs, montants)

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| ccrejet | Table WRITE (Database) | 1x | Schema + repository |
| cc_total | Table WRITE (Database) | 1x | Schema + repository |
| [Compte les seminaires (IDE 13)](GES-IDE-13.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Combo - type credit conso (IDE 12)](GES-IDE-12.md) | Sous-programme | 1x | Normale - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 11:26*
