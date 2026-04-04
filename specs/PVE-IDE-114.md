# PVE IDE 114 - Fin de journée

> **Analyse**: Phases 1-4 2026-02-03 09:29 -> 09:29 (19s) | Assemblage 09:29
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PVE |
| IDE Position | 114 |
| Nom Programme | Fin de journée |
| Fichier source | `Prg_114.xml` |
| Domaine metier | General |
| Taches | 20 (4 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 8 |

## 2. DESCRIPTION FONCTIONNELLE

**Fin de journée** assure la gestion complete de ce processus, accessible depuis [Menu Cloture du service (IDE 180)](PVE-IDE-180.md), [Menu Service cloture v2 (IDE 397)](PVE-IDE-397.md), [Menu Service cloture (IDE 402)](PVE-IDE-402.md).

Le flux de traitement s'organise en **4 blocs fonctionnels** :

- **Traitement** (16 taches) : traitements metier divers
- **Saisie** (2 taches) : ecrans de saisie utilisateur (formulaires, champs, donnees)
- **Initialisation** (1 tache) : reinitialisation d'etats et de variables de travail
- **Calcul** (1 tache) : calculs de montants, stocks ou compteurs

**Donnees modifiees** : 1 tables en ecriture (communication_ims).

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (16 taches)

- **114** - Menu **[[ECRAN]](#ecran-t1)**
- **114.1** - Est un term BOUT
- **114.2** - Est un term BOUT
- **114.4** - Paramètres PAR
- **114.6** - Param caisse
- **114.7** - CV  Autres tables **[[ECRAN]](#ecran-t8)**
- **114.7.1** - End of day Menu **[[ECRAN]](#ecran-t9)**
- **114.7.2** - Liste transac histo **[[ECRAN]](#ecran-t10)**
- **114.7.5** - Liste transac **[[ECRAN]](#ecran-t13)**
- **114.7.6** - Closure Report **[[ECRAN]](#ecran-t14)**
- **114.8** - read FROM_ADH
- **114.9** - read FROM_SKI
- **114.10** - read FROM_VIL sa
- **114.11** - write FROM_ADH
- **114.12** - write FROM_SKI
- **114.13** - write FROM_VIL sa

Delegue a : [Lecture session ouverte (IDE 116)](PVE-IDE-116.md), [Extrait - Sélection d'un GM (IDE 120)](PVE-IDE-120.md), [Liste cloture service (IDE 125)](PVE-IDE-125.md)

#### Phase 2 : Initialisation (1 tache)

- **114.3** - Initialisation

#### Phase 3 : Calcul (1 tache)

- **114.5** - Date comptable

#### Phase 4 : Saisie (2 taches)

- **114.7.3** - Lance saisie TPE
- **114.7.4** - lance saisie OD

Delegue a : [Liste des transactions imprim (IDE 123)](PVE-IDE-123.md), [Vidage Transactions en attente (IDE 115)](PVE-IDE-115.md), [Saisie des OD (IDE 119)](PVE-IDE-119.md), [Liste des transactions écran (IDE 124)](PVE-IDE-124.md)

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| communication_ims | R/**W** (6 usages) |  |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (16 taches)

Traitements internes.

---

#### <a id="t1"></a>114 - Menu [[ECRAN]](#ecran-t1)

**Role** : Tache d'orchestration : point d'entree du programme (16 sous-taches). Coordonne l'enchainement des traitements.
**Ecran** : 875 x 209 DLU (MDI) | [Voir mockup](#ecran-t1)

<details>
<summary>15 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [114.1](#t2) | Est un term BOUT | Traitement |
| [114.2](#t3) | Est un term BOUT | Traitement |
| [114.4](#t5) | Paramètres PAR | Traitement |
| [114.6](#t7) | Param caisse | Traitement |
| [114.7](#t8) | CV  Autres tables **[[ECRAN]](#ecran-t8)** | Traitement |
| [114.7.1](#t9) | End of day Menu **[[ECRAN]](#ecran-t9)** | Traitement |
| [114.7.2](#t10) | Liste transac histo **[[ECRAN]](#ecran-t10)** | Traitement |
| [114.7.5](#t13) | Liste transac **[[ECRAN]](#ecran-t13)** | Traitement |
| [114.7.6](#t14) | Closure Report **[[ECRAN]](#ecran-t14)** | Traitement |
| [114.8](#t15) | read FROM_ADH | Traitement |
| [114.9](#t16) | read FROM_SKI | Traitement |
| [114.10](#t17) | read FROM_VIL sa | Traitement |
| [114.11](#t18) | write FROM_ADH | Traitement |
| [114.12](#t19) | write FROM_SKI | Traitement |
| [114.13](#t20) | write FROM_VIL sa | Traitement |

</details>

---

#### <a id="t2"></a>114.1 - Est un term BOUT

**Role** : Traitement : Est un term BOUT.
**Variables liees** : N (V Utilisation bouti), BK (V Activité boutique), BL (V est un term boutique)

---

#### <a id="t3"></a>114.2 - Est un term BOUT

**Role** : Traitement : Est un term BOUT.
**Variables liees** : N (V Utilisation bouti), BK (V Activité boutique), BL (V est un term boutique)

---

#### <a id="t5"></a>114.4 - Paramètres PAR

**Role** : Traitement : Paramètres PAR.

---

#### <a id="t7"></a>114.6 - Param caisse

**Role** : Traitement : Param caisse.
**Variables liees** : P (V Village nouvelle caisse), R (V autorisation parametre caiss)

---

#### <a id="t8"></a>114.7 - CV  Autres tables [[ECRAN]](#ecran-t8)

**Role** : Traitement : CV  Autres tables.
**Ecran** : 2 x 1 DLU (MDI) | [Voir mockup](#ecran-t8)

---

#### <a id="t9"></a>114.7.1 - End of day Menu [[ECRAN]](#ecran-t9)

**Role** : Traitement : End of day Menu.
**Ecran** : 1018 x 280 DLU (Type6) | [Voir mockup](#ecran-t9)

---

#### <a id="t10"></a>114.7.2 - Liste transac histo [[ECRAN]](#ecran-t10)

**Role** : Traitement : Liste transac histo.
**Ecran** : 478 x 122 DLU (MDI) | [Voir mockup](#ecran-t10)
**Variables liees** : V (V Total transaction)

---

#### <a id="t13"></a>114.7.5 - Liste transac [[ECRAN]](#ecran-t13)

**Role** : Traitement : Liste transac.
**Ecran** : 483 x 172 DLU (MDI) | [Voir mockup](#ecran-t13)
**Variables liees** : V (V Total transaction)

---

#### <a id="t14"></a>114.7.6 - Closure Report [[ECRAN]](#ecran-t14)

**Role** : Traitement : Closure Report.
**Ecran** : 475 x 122 DLU (MDI) | [Voir mockup](#ecran-t14)

---

#### <a id="t15"></a>114.8 - read FROM_ADH

**Role** : Traitement : read FROM_ADH.
**Variables liees** : Z (V FROM_ADH)

---

#### <a id="t16"></a>114.9 - read FROM_SKI

**Role** : Traitement : read FROM_SKI.
**Variables liees** : BA (V FROM_SKI)

---

#### <a id="t17"></a>114.10 - read FROM_VIL sa

**Role** : Traitement : read FROM_VIL sa.
**Variables liees** : BB (V FROM_VIL saisie articles)

---

#### <a id="t18"></a>114.11 - write FROM_ADH

**Role** : Traitement : write FROM_ADH.
**Variables liees** : Z (V FROM_ADH)

---

#### <a id="t19"></a>114.12 - write FROM_SKI

**Role** : Traitement : write FROM_SKI.
**Variables liees** : BA (V FROM_SKI)

---

#### <a id="t20"></a>114.13 - write FROM_VIL sa

**Role** : Traitement : write FROM_VIL sa.
**Variables liees** : BB (V FROM_VIL saisie articles)


### 3.2 Initialisation (1 tache)

Reinitialisation d'etats et variables de travail.

---

#### <a id="t4"></a>114.3 - Initialisation

**Role** : Reinitialisation : Initialisation.


### 3.3 Calcul (1 tache)

Calculs metier : montants, stocks, compteurs.

---

#### <a id="t6"></a>114.5 - Date comptable

**Role** : Traitement : Date comptable.
**Variables liees** : T (V Date comptable), X (V Date ouverture)


### 3.4 Saisie (2 taches)

Ce bloc traite la saisie des donnees de la transaction.

---

#### <a id="t11"></a>114.7.3 - Lance saisie TPE

**Role** : Saisie des donnees : Lance saisie TPE.
**Variables liees** : BB (V FROM_VIL saisie articles)
**Delegue a** : [Liste des transactions imprim (IDE 123)](PVE-IDE-123.md), [Vidage Transactions en attente (IDE 115)](PVE-IDE-115.md), [Saisie des OD (IDE 119)](PVE-IDE-119.md)

---

#### <a id="t12"></a>114.7.4 - lance saisie OD

**Role** : Saisie des donnees : lance saisie OD.
**Variables liees** : BB (V FROM_VIL saisie articles)
**Delegue a** : [Liste des transactions imprim (IDE 123)](PVE-IDE-123.md), [Vidage Transactions en attente (IDE 115)](PVE-IDE-115.md), [Saisie des OD (IDE 119)](PVE-IDE-119.md)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Menu Cloture du service (IDE 180)](PVE-IDE-180.md), [Menu Service cloture v2 (IDE 397)](PVE-IDE-397.md), [Menu Service cloture (IDE 402)](PVE-IDE-402.md)
- **Appelle**: 8 programmes | **Tables**: 8 (W:1 R:7 L:1) | **Taches**: 20 | **Expressions**: 10

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (4 / 20)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 114.7.1 | 114.7.1 | End of day Menu | Type6 | 1018 | 280 | Traitement |
| 2 | 114.7.2 | 114.7.2 | Liste transac histo | MDI | 478 | 122 | Traitement |
| 3 | 114.7.5 | 114.7.5 | Liste transac | MDI | 483 | 172 | Traitement |
| 4 | 114.7.6 | 114.7.6 | Closure Report | MDI | 475 | 122 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t9"></a>114.7.1 - End of day Menu
**Tache** : [114.7.1](#t9) | **Type** : Type6 | **Dimensions** : 1018 x 280 DLU
**Bloc** : Traitement | **Titre IDE** : End of day Menu

<!-- FORM-DATA:
{
    "width":  1018,
    "vFactor":  8,
    "type":  "Type6",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  6,
                         "type":  "label",
                         "var":  "",
                         "y":  5,
                         "w":  1002,
                         "fmt":  "",
                         "name":  "",
                         "h":  26,
                         "color":  "188",
                         "text":  "END OF DAY MENU",
                         "parent":  null
                     },
                     {
                         "x":  8,
                         "type":  "label",
                         "var":  "",
                         "y":  33,
                         "w":  1001,
                         "fmt":  "",
                         "name":  "",
                         "h":  31,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  96,
                         "type":  "label",
                         "var":  "",
                         "y":  43,
                         "w":  232,
                         "fmt":  "",
                         "name":  "",
                         "h":  14,
                         "color":  "110",
                         "text":  "Accounting date",
                         "parent":  3
                     },
                     {
                         "x":  343,
                         "type":  "edit",
                         "var":  "",
                         "y":  43,
                         "w":  192,
                         "fmt":  "",
                         "name":  "",
                         "h":  14,
                         "color":  "110",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  846,
                         "type":  "image",
                         "var":  "",
                         "y":  74,
                         "w":  160,
                         "fmt":  "",
                         "name":  "",
                         "h":  62,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  44,
                         "type":  "button",
                         "var":  "",
                         "y":  89,
                         "w":  324,
                         "fmt":  "\u0026Statement of \\Account",
                         "name":  "EXTRAIT",
                         "h":  31,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  416,
                         "type":  "button",
                         "var":  "",
                         "y":  89,
                         "w":  324,
                         "fmt":  "Input telecollection \u0026TPE",
                         "name":  "TPE",
                         "h":  31,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  44,
                         "type":  "button",
                         "var":  "",
                         "y":  129,
                         "w":  324,
                         "fmt":  "Input \u0026OD",
                         "name":  "OD",
                         "h":  31,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  416,
                         "type":  "button",
                         "var":  "",
                         "y":  129,
                         "w":  324,
                         "fmt":  "Input Cash \u0026documents",
                         "name":  "CAISSE",
                         "h":  31,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  44,
                         "type":  "button",
                         "var":  "",
                         "y":  170,
                         "w":  324,
                         "fmt":  "Transactions \u0026\\List",
                         "name":  "TRANSLIST",
                         "h":  31,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  416,
                         "type":  "button",
                         "var":  "",
                         "y":  170,
                         "w":  324,
                         "fmt":  "Transactions \u0026\\History",
                         "name":  "TRANSHISTO",
                         "h":  31,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  44,
                         "type":  "button",
                         "var":  "",
                         "y":  210,
                         "w":  324,
                         "fmt":  "\u0026Closure \\List",
                         "name":  "CLOTURE",
                         "h":  31,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  821,
                         "type":  "button",
                         "var":  "",
                         "y":  246,
                         "w":  179,
                         "fmt":  "\u0026Exit",
                         "name":  "EXIT",
                         "h":  30,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  416,
                         "type":  "button",
                         "var":  "",
                         "y":  210,
                         "w":  324,
                         "fmt":  "T\u0026PE Diary",
                         "name":  "Diary",
                         "h":  31,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "114.7.1",
    "height":  280
}
-->

<details>
<summary><strong>Champs : 1 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 343,43 | (sans nom) | - | edit |

</details>

<details>
<summary><strong>Boutons : 9 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Statement of \Account | 44,89 | Bouton fonctionnel |
| Input telecollection TPE | 416,89 | Bouton fonctionnel |
| Input OD | 44,129 | Bouton fonctionnel |
| Input Cash documents | 416,129 | Bouton fonctionnel |
| Transactions \List | 44,170 | Appel [Liste des transactions imprim (IDE 123)](PVE-IDE-123.md) |
| Transactions \History | 416,170 | Appel [Liste des transactions imprim (IDE 123)](PVE-IDE-123.md) |
| Closure \List | 44,210 | Bouton fonctionnel |
| Exit | 821,246 | Quitte le programme |
| TPE Diary | 416,210 | Bouton fonctionnel |

</details>

---

#### <a id="ecran-t10"></a>114.7.2 - Liste transac histo
**Tache** : [114.7.2](#t10) | **Type** : MDI | **Dimensions** : 478 x 122 DLU
**Bloc** : Traitement | **Titre IDE** : Liste transac histo

<!-- FORM-DATA:
{
    "width":  478,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  472,
                         "fmt":  "",
                         "name":  "",
                         "h":  19,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  293,
                         "type":  "label",
                         "var":  "",
                         "y":  47,
                         "w":  149,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "date comptable",
                         "parent":  null
                     },
                     {
                         "x":  2,
                         "type":  "label",
                         "var":  "",
                         "y":  96,
                         "w":  472,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  8,
                         "type":  "button",
                         "var":  "",
                         "y":  100,
                         "w":  154,
                         "fmt":  "",
                         "name":  "bouton quitter",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  293,
                         "type":  "edit",
                         "var":  "",
                         "y":  63,
                         "w":  149,
                         "fmt":  "",
                         "name":  "v date comptable",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  309,
                         "type":  "button",
                         "var":  "",
                         "y":  100,
                         "w":  154,
                         "fmt":  "",
                         "name":  "bouton imprimer",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  7,
                         "type":  "edit",
                         "var":  "",
                         "y":  5,
                         "w":  192,
                         "fmt":  "30",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  244,
                         "type":  "edit",
                         "var":  "",
                         "y":  5,
                         "w":  219,
                         "fmt":  "WWW DD MMM YYYYT",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  59,
                         "type":  "image",
                         "var":  "",
                         "y":  35,
                         "w":  160,
                         "fmt":  "",
                         "name":  "",
                         "h":  50,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "114.7.2",
    "height":  122
}
-->

<details>
<summary><strong>Champs : 3 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 293,63 | v date comptable | - | edit |
| 7,5 | 30 | - | edit |
| 244,5 | WWW DD MMM YYYYT | - | edit |

</details>

<details>
<summary><strong>Boutons : 2 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| quitter | 8,100 | Quitte le programme |
| imprimer | 309,100 | Appel [Liste des transactions imprim (IDE 123)](PVE-IDE-123.md) |

</details>

---

#### <a id="ecran-t13"></a>114.7.5 - Liste transac
**Tache** : [114.7.5](#t13) | **Type** : MDI | **Dimensions** : 483 x 172 DLU
**Bloc** : Traitement | **Titre IDE** : Liste transac

<!-- FORM-DATA:
{
    "width":  483,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  472,
                         "fmt":  "",
                         "name":  "",
                         "h":  19,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  4,
                         "type":  "label",
                         "var":  "",
                         "y":  144,
                         "w":  472,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  163,
                         "type":  "button",
                         "var":  "",
                         "y":  148,
                         "w":  154,
                         "fmt":  "\u0026Exit",
                         "name":  "bouton quitter",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  163,
                         "type":  "combobox",
                         "var":  "",
                         "y":  49,
                         "w":  154,
                         "fmt":  "",
                         "name":  "TOUT OD VENTES",
                         "h":  12,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  50,
                         "type":  "button",
                         "var":  "",
                         "y":  96,
                         "w":  154,
                         "fmt":  "\u0026Screen",
                         "name":  "bouton écran",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  277,
                         "type":  "button",
                         "var":  "",
                         "y":  96,
                         "w":  154,
                         "fmt":  "\u0026Print",
                         "name":  "bouton imprimer",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  7,
                         "type":  "edit",
                         "var":  "",
                         "y":  5,
                         "w":  192,
                         "fmt":  "30",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  244,
                         "type":  "edit",
                         "var":  "",
                         "y":  5,
                         "w":  219,
                         "fmt":  "WWW DD MMM YYYYT",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     }
                 ],
    "taskId":  "114.7.5",
    "height":  172
}
-->

<details>
<summary><strong>Champs : 3 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 163,49 | TOUT OD VENTES | - | combobox |
| 7,5 | 30 | - | edit |
| 244,5 | WWW DD MMM YYYYT | - | edit |

</details>

<details>
<summary><strong>Boutons : 3 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Exit | 163,148 | Quitte le programme |
| Screen | 50,96 | Bouton fonctionnel |
| Print | 277,96 | Lance l'impression |

</details>

---

#### <a id="ecran-t14"></a>114.7.6 - Closure Report
**Tache** : [114.7.6](#t14) | **Type** : MDI | **Dimensions** : 475 x 122 DLU
**Bloc** : Traitement | **Titre IDE** : Closure Report

<!-- FORM-DATA:
{
    "width":  475,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  472,
                         "fmt":  "",
                         "name":  "",
                         "h":  19,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  293,
                         "type":  "label",
                         "var":  "",
                         "y":  47,
                         "w":  149,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "accounting date",
                         "parent":  null
                     },
                     {
                         "x":  2,
                         "type":  "label",
                         "var":  "",
                         "y":  96,
                         "w":  472,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  8,
                         "type":  "button",
                         "var":  "",
                         "y":  100,
                         "w":  154,
                         "fmt":  "\u0026Exit",
                         "name":  "BP. Exit",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  293,
                         "type":  "edit",
                         "var":  "",
                         "y":  63,
                         "w":  149,
                         "fmt":  "",
                         "name":  "v date comptable",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  309,
                         "type":  "button",
                         "var":  "",
                         "y":  100,
                         "w":  154,
                         "fmt":  "\u0026Print",
                         "name":  "BP. Print",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  7,
                         "type":  "edit",
                         "var":  "",
                         "y":  5,
                         "w":  192,
                         "fmt":  "30",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  244,
                         "type":  "edit",
                         "var":  "",
                         "y":  5,
                         "w":  219,
                         "fmt":  "WWW DD MMM YYYYT",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  59,
                         "type":  "image",
                         "var":  "",
                         "y":  35,
                         "w":  160,
                         "fmt":  "",
                         "name":  "",
                         "h":  50,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "114.7.6",
    "height":  122
}
-->

<details>
<summary><strong>Champs : 3 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 293,63 | v date comptable | - | edit |
| 7,5 | 30 | - | edit |
| 244,5 | WWW DD MMM YYYYT | - | edit |

</details>

<details>
<summary><strong>Boutons : 2 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Exit | 8,100 | Quitte le programme |
| Print | 309,100 | Lance l'impression |

</details>

## 9. NAVIGATION

### 9.1 Enchainement des ecrans

```mermaid
flowchart TD
    START([Entree])
    style START fill:#3fb950
    VF9[114.7.1 End of day Menu]
    style VF9 fill:#58a6ff
    VF10[114.7.2 Liste transac histo]
    style VF10 fill:#58a6ff
    VF13[114.7.5 Liste transac]
    style VF13 fill:#58a6ff
    VF14[114.7.6 Closure Report]
    style VF14 fill:#58a6ff
    EXT123[IDE 123 Liste des tran...]
    style EXT123 fill:#3fb950
    EXT115[IDE 115 Vidage Transac...]
    style EXT115 fill:#3fb950
    EXT116[IDE 116 Lecture sessio...]
    style EXT116 fill:#3fb950
    EXT117[IDE 117 Controle sessi...]
    style EXT117 fill:#3fb950
    EXT119[IDE 119 Saisie des OD]
    style EXT119 fill:#3fb950
    EXT120[IDE 120 Extrait - Séle...]
    style EXT120 fill:#3fb950
    EXT124[IDE 124 Liste des tran...]
    style EXT124 fill:#3fb950
    EXT125[IDE 125 Liste cloture ...]
    style EXT125 fill:#3fb950
    FIN([Sortie])
    style FIN fill:#f85149
    START --> VF9
    VF9 -->|Impression ticket/document| EXT123
    VF9 -->|Sous-programme| EXT115
    VF9 -->|Gestion session| EXT116
    VF9 -->|Controle/validation| EXT117
    VF9 -->|Sous-programme| EXT119
    VF9 -->|Sous-programme| EXT120
    VF9 -->|Configuration impression| EXT124
    VF9 -->|Configuration impression| EXT125
    EXT125 --> FIN
```

**Detail par enchainement :**

| Depuis | Action | Vers | Retour |
|--------|--------|------|--------|
| End of day Menu | Impression ticket/document | [Liste des transactions imprim (IDE 123)](PVE-IDE-123.md) | Retour ecran |
| End of day Menu | Sous-programme | [Vidage Transactions en attente (IDE 115)](PVE-IDE-115.md) | Retour ecran |
| End of day Menu | Gestion session | [Lecture session ouverte (IDE 116)](PVE-IDE-116.md) | Retour ecran |
| End of day Menu | Controle/validation | [Controle session caisse (IDE 117)](PVE-IDE-117.md) | Retour ecran |
| End of day Menu | Sous-programme | [Saisie des OD (IDE 119)](PVE-IDE-119.md) | Retour ecran |
| End of day Menu | Sous-programme | [Extrait - Sélection d'un GM (IDE 120)](PVE-IDE-120.md) | Retour ecran |
| End of day Menu | Configuration impression | [Liste des transactions écran (IDE 124)](PVE-IDE-124.md) | Retour ecran |
| End of day Menu | Configuration impression | [Liste cloture service (IDE 125)](PVE-IDE-125.md) | Retour ecran |

### 9.3 Structure hierarchique (20 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **114.1** | [**Menu** (114)](#t1) [mockup](#ecran-t1) | MDI | 875x209 | Traitement |
| 114.1.1 | [Est un term BOUT (114.1)](#t2) | MDI | - | |
| 114.1.2 | [Est un term BOUT (114.2)](#t3) | MDI | - | |
| 114.1.3 | [Paramètres PAR (114.4)](#t5) | MDI | - | |
| 114.1.4 | [Param caisse (114.6)](#t7) | MDI | - | |
| 114.1.5 | [CV  Autres tables (114.7)](#t8) [mockup](#ecran-t8) | MDI | 2x1 | |
| 114.1.6 | [End of day Menu (114.7.1)](#t9) [mockup](#ecran-t9) | Type6 | 1018x280 | |
| 114.1.7 | [Liste transac histo (114.7.2)](#t10) [mockup](#ecran-t10) | MDI | 478x122 | |
| 114.1.8 | [Liste transac (114.7.5)](#t13) [mockup](#ecran-t13) | MDI | 483x172 | |
| 114.1.9 | [Closure Report (114.7.6)](#t14) [mockup](#ecran-t14) | MDI | 475x122 | |
| 114.1.10 | [read FROM_ADH (114.8)](#t15) | MDI | - | |
| 114.1.11 | [read FROM_SKI (114.9)](#t16) | MDI | - | |
| 114.1.12 | [read FROM_VIL sa (114.10)](#t17) | MDI | - | |
| 114.1.13 | [write FROM_ADH (114.11)](#t18) | MDI | - | |
| 114.1.14 | [write FROM_SKI (114.12)](#t19) | MDI | - | |
| 114.1.15 | [write FROM_VIL sa (114.13)](#t20) | MDI | - | |
| **114.2** | [**Initialisation** (114.3)](#t4) | MDI | - | Initialisation |
| **114.3** | [**Date comptable** (114.5)](#t6) | MDI | - | Calcul |
| **114.4** | [**Lance saisie TPE** (114.7.3)](#t11) | MDI | - | Saisie |
| 114.4.1 | [lance saisie OD (114.7.4)](#t12) | MDI | - | |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Traitement principal]
    UPDATE[MAJ 1 tables]
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

### Tables utilisees (8)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 63 | parametres___par |  | DB | R |   |   | 1 |
| 69 | initialisation___ini |  | DB | R |   |   | 1 |
| 70 | date_comptable___dat |  | DB | R |   |   | 1 |
| 71 | derniere_purge___pur |  | DB | R |   |   | 1 |
| 219 | communication_ims |  | DB | R | **W** |   | 6 |
| 256 | terminaux_boutique |  | DB | R |   |   | 2 |
| 697 | droits_applications | Droits operateur | DB | R |   |   | 1 |
| 728 | arc_cc_total |  | DB |   |   | L | 1 |

### Colonnes par table (5 / 7 tables avec colonnes identifiees)

<details>
<summary>Table 63 - parametres___par (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| D | Autorisation parametres | R | Logical |

</details>

<details>
<summary>Table 69 - initialisation___ini (R) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 70 - date_comptable___dat (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | DATE DEMANDEE | R | Date |
| B | v date comptable | R | Date |
| T | V Date comptable | R | Date |
| X | V Date ouverture | R | Date |

</details>

<details>
<summary>Table 71 - derniere_purge___pur (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | bouton quitter | R | Alpha |
| B | v date comptable | R | Date |
| C | bouton imprimer | R | Alpha |

</details>

<details>
<summary>Table 219 - communication_ims (R/**W**) - 6 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 256 - terminaux_boutique (R) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| BK | V Activité boutique | R | Numeric |
| BL | V est un term boutique | R | Logical |

</details>

<details>
<summary>Table 697 - droits_applications (R) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Variables de session (38)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | V Société | Alpha | - |
| B | V Service | Alpha | - |
| C | V Service Libellé | Alpha | - |
| D | V Village CAM | Alpha | - |
| E | V Village TEL | Alpha | - |
| F | V Village BIBOP | Alpha | - |
| G | V Nb décimales | Numeric | - |
| H | V Devise locale | Alpha | - |
| I | V Code village | Alpha | - |
| J | V Nom village | Alpha | - |
| K | V Masque montant | Alpha | - |
| L | V Choix action | Alpha | 1x session |
| M | V Utilisation caiss | Alpha | - |
| N | V Utilisation bouti | Alpha | - |
| O | V Village PME | Alpha | - |
| P | V Village nouvelle caisse | Alpha | - |
| Q | V Fin tache | Alpha | 1x session |
| R | V autorisation parametre caiss | Logical | - |
| S | V uniBi | Alpha | - |
| T | V Date comptable | Date | - |
| U | V Masque cumul | Alpha | - |
| V | V Total transaction | Numeric | - |
| W | V Chrono session | Numeric | - |
| X | V Date ouverture | Date | - |
| Y | V Time ouverture | Time | - |
| Z | V FROM_ADH | Alpha | [114.8](#t15), [114.11](#t18) |
| BA | V FROM_SKI | Alpha | - |
| BB | V FROM_VIL saisie articles | Alpha | - |
| BC | V user déjà connecté | Logical | - |
| BD | V Service IMS sans session 1 | Alpha | - |
| BE | V Service IMS sans session 2 | Alpha | - |
| BF | V Service IMS sans session 3 | Alpha | - |
| BG | V Service IMS sans session 4 | Alpha | - |
| BH | V Service IMS sans session 5 | Alpha | - |
| BI | V Cloture auto | Logical | - |
| BJ | V est un service BarSpaSkiBou | Logical | - |
| BK | V Activité boutique | Numeric | - |
| BL | V est un term boutique | Logical | - |

<details>
<summary>Toutes les 38 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| V. | **A** | V Société | Alpha |
| V. | **B** | V Service | Alpha |
| V. | **C** | V Service Libellé | Alpha |
| V. | **D** | V Village CAM | Alpha |
| V. | **E** | V Village TEL | Alpha |
| V. | **F** | V Village BIBOP | Alpha |
| V. | **G** | V Nb décimales | Numeric |
| V. | **H** | V Devise locale | Alpha |
| V. | **I** | V Code village | Alpha |
| V. | **J** | V Nom village | Alpha |
| V. | **K** | V Masque montant | Alpha |
| V. | **L** | V Choix action | Alpha |
| V. | **M** | V Utilisation caiss | Alpha |
| V. | **N** | V Utilisation bouti | Alpha |
| V. | **O** | V Village PME | Alpha |
| V. | **P** | V Village nouvelle caisse | Alpha |
| V. | **Q** | V Fin tache | Alpha |
| V. | **R** | V autorisation parametre caiss | Logical |
| V. | **S** | V uniBi | Alpha |
| V. | **T** | V Date comptable | Date |
| V. | **U** | V Masque cumul | Alpha |
| V. | **V** | V Total transaction | Numeric |
| V. | **W** | V Chrono session | Numeric |
| V. | **X** | V Date ouverture | Date |
| V. | **Y** | V Time ouverture | Time |
| V. | **Z** | V FROM_ADH | Alpha |
| V. | **BA** | V FROM_SKI | Alpha |
| V. | **BB** | V FROM_VIL saisie articles | Alpha |
| V. | **BC** | V user déjà connecté | Logical |
| V. | **BD** | V Service IMS sans session 1 | Alpha |
| V. | **BE** | V Service IMS sans session 2 | Alpha |
| V. | **BF** | V Service IMS sans session 3 | Alpha |
| V. | **BG** | V Service IMS sans session 4 | Alpha |
| V. | **BH** | V Service IMS sans session 5 | Alpha |
| V. | **BI** | V Cloture auto | Logical |
| V. | **BJ** | V est un service BarSpaSkiBou | Logical |
| V. | **BK** | V Activité boutique | Numeric |
| V. | **BL** | V est un term boutique | Logical |

</details>

## 12. EXPRESSIONS

**10 / 10 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONSTANTE | 3 | 0 |
| OTHER | 2 | 0 |
| CONDITION | 3 | 0 |
| NEGATION | 1 | 0 |
| REFERENCE_VG | 1 | 0 |

### 12.2 Expressions cles par type

#### CONSTANTE (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 8 | `''` | - |
| CONSTANTE | 7 | `'B'` | - |
| CONSTANTE | 1 | `'C'` | - |

#### OTHER (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 3 | `GetParam ('SERVICELIB')` | - |
| OTHER | 2 | `GetParam ('SERVICE')` | - |

#### CONDITION (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 6 | `V FROM_ADH [Z]='O'` | - |
| CONDITION | 5 | `V Choix action [L]='B'` | - |
| CONDITION | 4 | `V Fin tache [Q]='F'` | - |

#### NEGATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| NEGATION | 9 | `NOT VG104` | - |

#### REFERENCE_VG (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 10 | `VG104` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Menu Cloture du service (IDE 180)](PVE-IDE-180.md) -> **Fin de journée (IDE 114)**

Main -> ... -> [Menu Service cloture v2 (IDE 397)](PVE-IDE-397.md) -> **Fin de journée (IDE 114)**

Main -> ... -> [Menu Service cloture (IDE 402)](PVE-IDE-402.md) -> **Fin de journée (IDE 114)**

```mermaid
graph LR
    T114[114 Fin de journée]
    style T114 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC143[143 START]
    style CC143 fill:#f59e0b
    CC420[420 Menu==V4___]
    style CC420 fill:#f59e0b
    CC439[439 Menu]
    style CC439 fill:#f59e0b
    CC353[353 Menu==V4]
    style CC353 fill:#f59e0b
    CC185[185 Menu]
    style CC185 fill:#f59e0b
    CC180[180 Menu Cloture du se...]
    style CC180 fill:#3fb950
    CC397[397 Menu Service clotu...]
    style CC397 fill:#3fb950
    CC402[402 Menu Service cloture]
    style CC402 fill:#3fb950
    CC185 --> CC180
    CC353 --> CC180
    CC420 --> CC180
    CC439 --> CC180
    CC185 --> CC397
    CC353 --> CC397
    CC420 --> CC397
    CC439 --> CC397
    CC185 --> CC402
    CC353 --> CC402
    CC420 --> CC402
    CC439 --> CC402
    CC143 --> CC185
    CC143 --> CC353
    CC143 --> CC420
    CC143 --> CC439
    CC1 --> CC143
    CC180 --> T114
    CC397 --> T114
    CC402 --> T114
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [180](PVE-IDE-180.md) | Menu Cloture du service | 1 |
| [397](PVE-IDE-397.md) | Menu Service cloture v2 | 1 |
| [402](PVE-IDE-402.md) | Menu Service cloture | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T114[114 Fin de journée]
    style T114 fill:#58a6ff
    C123[123 Liste des transact...]
    T114 --> C123
    style C123 fill:#3fb950
    C115[115 Vidage Transaction...]
    T114 --> C115
    style C115 fill:#3fb950
    C116[116 Lecture session ou...]
    T114 --> C116
    style C116 fill:#3fb950
    C117[117 Controle session c...]
    T114 --> C117
    style C117 fill:#3fb950
    C119[119 Saisie des OD]
    T114 --> C119
    style C119 fill:#3fb950
    C120[120 Extrait - Sélectio...]
    T114 --> C120
    style C120 fill:#3fb950
    C124[124 Liste des transact...]
    T114 --> C124
    style C124 fill:#3fb950
    C125[125 Liste cloture service]
    T114 --> C125
    style C125 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [123](PVE-IDE-123.md) | Liste des transactions imprim | 2 | Impression ticket/document |
| [115](PVE-IDE-115.md) | Vidage Transactions en attente | 1 | Sous-programme |
| [116](PVE-IDE-116.md) | Lecture session ouverte | 1 | Gestion session |
| [117](PVE-IDE-117.md) | Controle session caisse | 1 | Controle/validation |
| [119](PVE-IDE-119.md) | Saisie des OD | 1 | Sous-programme |
| [120](PVE-IDE-120.md) | Extrait - Sélection d'un GM | 1 | Sous-programme |
| [124](PVE-IDE-124.md) | Liste des transactions écran | 1 | Configuration impression |
| [125](PVE-IDE-125.md) | Liste cloture service | 1 | Configuration impression |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 346 | Taille moyenne |
| Expressions | 10 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 8 | Dependances moderees |
| Ecrans visibles | 4 | Quelques ecrans |
| Code desactive | 1.2% (4 / 346) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (16 taches: 6 ecrans, 10 traitements)

- **Strategie** : Orchestrateur avec 6 ecrans (Razor/React) et 10 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 8 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Initialisation (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Constructeur/methode `InitAsync()` dans l'orchestrateur.

#### Calcul (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Services de calcul purs (Domain Services).
- Migrer la logique de calcul (stock, compteurs, montants)

#### Saisie (2 taches: 0 ecran, 2 traitements)

- **Strategie** : Formulaire React/Blazor avec validation Zod/FluentValidation.
- Validation temps reel cote client + serveur

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| communication_ims | Table WRITE (Database) | 3x | Schema + repository |
| [Liste des transactions imprim (IDE 123)](PVE-IDE-123.md) | Sous-programme | 2x | Haute - Impression ticket/document |
| [Extrait - Sélection d'un GM (IDE 120)](PVE-IDE-120.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Liste des transactions écran (IDE 124)](PVE-IDE-124.md) | Sous-programme | 1x | Normale - Configuration impression |
| [Liste cloture service (IDE 125)](PVE-IDE-125.md) | Sous-programme | 1x | Normale - Configuration impression |
| [Saisie des OD (IDE 119)](PVE-IDE-119.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Vidage Transactions en attente (IDE 115)](PVE-IDE-115.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Lecture session ouverte (IDE 116)](PVE-IDE-116.md) | Sous-programme | 1x | Normale - Gestion session |
| [Controle session caisse (IDE 117)](PVE-IDE-117.md) | Sous-programme | 1x | Normale - Controle/validation |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 09:29*
