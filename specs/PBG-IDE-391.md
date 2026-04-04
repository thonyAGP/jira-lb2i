# PBG IDE 391 - Module Sejours SubForm

> **Analyse**: Phases 1-4 2026-02-03 11:38 -> 11:38 (18s) | Assemblage 11:38
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBG |
| IDE Position | 391 |
| Nom Programme | Module Sejours SubForm |
| Fichier source | `Prg_391.xml` |
| Dossier IDE | General |
| Taches | 17 (6 ecrans visibles) |
| Tables modifiees | 4 |
| Programmes appeles | 19 |
| :warning: Statut | **ORPHELIN_POTENTIEL** |

## 2. DESCRIPTION FONCTIONNELLE

**Module Sejours SubForm** assure la gestion complete de ce processus.

Le flux de traitement s'organise en **4 blocs fonctionnels** :

- **Traitement** (8 taches) : traitements metier divers
- **Consultation** (4 taches) : ecrans de recherche, selection et consultation
- **Calcul** (3 taches) : calculs de montants, stocks ou compteurs
- **Validation** (2 taches) : controles et verifications de coherence

**Donnees modifiees** : 4 tables en ecriture (compteurs________cpt, mouchard_________mou, ez_card, fi_complet_______gm_go).

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (8 taches)

- **391** - Module des Sejours **[[ECRAN]](#ecran-t1)**
- **391.1** - Determination Age Bebe
- **391.2** - Planning sejours **[[ECRAN]](#ecran-t4)**
- **391.2.2.1** - Recuperation date d/f
- **391.2.5** - Demande de confirmation **[[ECRAN]](#ecran-t13)**
- **391.2.6** - Tracage Suppression
- **391.2.6.2** - Tracage
- **391.2.10** - Suppression carte

Delegue a : [Marquage Caisse logique (IDE 179)](PBG-IDE-179.md), [   Recodification Client (IDE 77)](PBG-IDE-77.md), [   Avancement Client (IDE 78)](PBG-IDE-78.md), [   Suppression Periode Client (IDE 79)](PBG-IDE-79.md), [   Interruption Client (IDE 80)](PBG-IDE-80.md), [   Suppression Client (IDE 82)](PBG-IDE-82.md), [   Prolongation Client (IDE 83)](PBG-IDE-83.md), [Modules clients Identite (IDE 91)](PBG-IDE-91.md), [Contrôle des informations (IDE 95)](PBG-IDE-95.md), [Demarquage Caisse (IDE 176)](PBG-IDE-176.md), [Marquage Caisse alpha (IDE 178)](PBG-IDE-178.md), [Recuperation du titre (IDE 317)](PBG-IDE-317.md)

#### Phase 2 : Consultation (4 taches)

- **391.2.1** - Recherche Nom **[[ECRAN]](#ecran-t5)**
- **391.2.2** - Affichage Periodes **[[ECRAN]](#ecran-t7)**
- **391.2.7** - Recherche **[[ECRAN]](#ecran-t18)**
- **391.2.8** - Recherche Prenom **[[ECRAN]](#ecran-t19)**

Delegue a : [   Affichage Commentaire (IDE 74)](PBG-IDE-74.md), [   Selection Interruption (IDE 81)](PBG-IDE-81.md), [Recuperation du titre (IDE 317)](PBG-IDE-317.md)

#### Phase 3 : Calcul (3 taches)

- **391.2.2.2** - Calcul Date Grecques
- **391.2.6.1** - Compteur
- **391.2.9** - Calcul Date Grecques

Delegue a : [Separation de comptes (IDE 269)](PBG-IDE-269.md)

#### Phase 4 : Validation (2 taches)

- **391.2.3** - Verification Nb Filiation
- **391.2.4** - Controle Cloture Caisse

Delegue a : [Verification Aut sans ecran (IDE 320)](PBG-IDE-320.md), [Verification Autorisation (IDE 319)](PBG-IDE-319.md), [Verification Suppression (IDE 182)](PBG-IDE-182.md)

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| fi_complet_______gm_go | **W** (2 usages) |  |
| mouchard_________mou | **W** (1 usages) |  |
| ez_card | **W** (1 usages) |  |
| compteurs________cpt | **W** (1 usages) | Comptes GM (generaux) |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (8 taches)

Traitements internes.

---

#### <a id="t1"></a>391 - Module des Sejours [[ECRAN]](#ecran-t1)

**Role** : Tache d'orchestration : point d'entree du programme (8 sous-taches). Coordonne l'enchainement des traitements.
**Ecran** : 13 x 4 DLU (MDI) | [Voir mockup](#ecran-t1)

<details>
<summary>7 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [391.1](#t2) | Determination Age Bebe | Traitement |
| [391.2](#t4) | Planning sejours **[[ECRAN]](#ecran-t4)** | Traitement |
| [391.2.2.1](#t8) | Recuperation date d/f | Traitement |
| [391.2.5](#t13) | Demande de confirmation **[[ECRAN]](#ecran-t13)** | Traitement |
| [391.2.6](#t14) | Tracage Suppression | Traitement |
| [391.2.6.2](#t16) | Tracage | Traitement |
| [391.2.10](#t21) | Suppression carte | Traitement |

</details>
**Delegue a** : [Marquage Caisse logique (IDE 179)](PBG-IDE-179.md), [   Recodification Client (IDE 77)](PBG-IDE-77.md), [   Avancement Client (IDE 78)](PBG-IDE-78.md)

---

#### <a id="t2"></a>391.1 - Determination Age Bebe

**Role** : Traitement : Determination Age Bebe.
**Variables liees** : D (W0-Age Bebe)
**Delegue a** : [Marquage Caisse logique (IDE 179)](PBG-IDE-179.md), [   Recodification Client (IDE 77)](PBG-IDE-77.md), [   Avancement Client (IDE 78)](PBG-IDE-78.md)

---

#### <a id="t4"></a>391.2 - Planning sejours [[ECRAN]](#ecran-t4)

**Role** : Traitement : Planning sejours.
**Ecran** : 1264 x 297 DLU (MDI) | [Voir mockup](#ecran-t4)
**Delegue a** : [Marquage Caisse logique (IDE 179)](PBG-IDE-179.md), [   Recodification Client (IDE 77)](PBG-IDE-77.md), [   Avancement Client (IDE 78)](PBG-IDE-78.md)

---

#### <a id="t8"></a>391.2.2.1 - Recuperation date d/f

**Role** : Consultation/chargement : Recuperation date d/f.
**Delegue a** : [Marquage Caisse logique (IDE 179)](PBG-IDE-179.md), [   Recodification Client (IDE 77)](PBG-IDE-77.md), [   Avancement Client (IDE 78)](PBG-IDE-78.md)

---

#### <a id="t13"></a>391.2.5 - Demande de confirmation [[ECRAN]](#ecran-t13)

**Role** : Traitement : Demande de confirmation.
**Ecran** : 461 x 71 DLU (Modal) | [Voir mockup](#ecran-t13)
**Delegue a** : [Marquage Caisse logique (IDE 179)](PBG-IDE-179.md), [   Recodification Client (IDE 77)](PBG-IDE-77.md), [   Avancement Client (IDE 78)](PBG-IDE-78.md)

---

#### <a id="t14"></a>391.2.6 - Tracage Suppression

**Role** : Traitement : Tracage Suppression.
**Variables liees** : K (W1 Autorisation Suppression), BB (W1 autorisation suppression)
**Delegue a** : [Marquage Caisse logique (IDE 179)](PBG-IDE-179.md), [   Recodification Client (IDE 77)](PBG-IDE-77.md), [   Avancement Client (IDE 78)](PBG-IDE-78.md)

---

#### <a id="t16"></a>391.2.6.2 - Tracage

**Role** : Traitement : Tracage.
**Delegue a** : [Marquage Caisse logique (IDE 179)](PBG-IDE-179.md), [   Recodification Client (IDE 77)](PBG-IDE-77.md), [   Avancement Client (IDE 78)](PBG-IDE-78.md)

---

#### <a id="t21"></a>391.2.10 - Suppression carte

**Role** : Traitement : Suppression carte.
**Variables liees** : K (W1 Autorisation Suppression), BB (W1 autorisation suppression)
**Delegue a** : [Marquage Caisse logique (IDE 179)](PBG-IDE-179.md), [   Recodification Client (IDE 77)](PBG-IDE-77.md), [   Avancement Client (IDE 78)](PBG-IDE-78.md)


### 3.2 Consultation (4 taches)

Ecrans de recherche et consultation.

---

#### <a id="t5"></a>391.2.1 - Recherche Nom [[ECRAN]](#ecran-t5)

**Role** : Traitement : Recherche Nom.
**Ecran** : 570 x 92 DLU (Modal) | [Voir mockup](#ecran-t5)
**Delegue a** : [   Affichage Commentaire (IDE 74)](PBG-IDE-74.md), [   Selection Interruption (IDE 81)](PBG-IDE-81.md)

---

#### <a id="t7"></a>391.2.2 - Affichage Periodes [[ECRAN]](#ecran-t7)

**Role** : Reinitialisation : Affichage Periodes.
**Ecran** : 669 x 133 DLU (Modal) | [Voir mockup](#ecran-t7)
**Variables liees** : Y (v Libelle affichage ECI)
**Delegue a** : [   Affichage Commentaire (IDE 74)](PBG-IDE-74.md), [   Selection Interruption (IDE 81)](PBG-IDE-81.md)

---

#### <a id="t18"></a>391.2.7 - Recherche [[ECRAN]](#ecran-t18)

**Role** : Traitement : Recherche.
**Ecran** : 571 x 91 DLU (Modal) | [Voir mockup](#ecran-t18)
**Delegue a** : [   Affichage Commentaire (IDE 74)](PBG-IDE-74.md), [   Selection Interruption (IDE 81)](PBG-IDE-81.md)

---

#### <a id="t19"></a>391.2.8 - Recherche Prenom [[ECRAN]](#ecran-t19)

**Role** : Traitement : Recherche Prenom.
**Ecran** : 573 x 93 DLU (Modal) | [Voir mockup](#ecran-t19)
**Delegue a** : [   Affichage Commentaire (IDE 74)](PBG-IDE-74.md), [   Selection Interruption (IDE 81)](PBG-IDE-81.md)


### 3.3 Calcul (3 taches)

Calculs metier : montants, stocks, compteurs.

---

#### <a id="t9"></a>391.2.2.2 - Calcul Date Grecques

**Role** : Calcul : Calcul Date Grecques.
**Delegue a** : [Separation de comptes (IDE 269)](PBG-IDE-269.md)

---

#### <a id="t15"></a>391.2.6.1 - Compteur

**Role** : Calcul : Compteur.
**Delegue a** : [Separation de comptes (IDE 269)](PBG-IDE-269.md)

---

#### <a id="t20"></a>391.2.9 - Calcul Date Grecques

**Role** : Calcul : Calcul Date Grecques.
**Delegue a** : [Separation de comptes (IDE 269)](PBG-IDE-269.md)


### 3.4 Validation (2 taches)

Controles de coherence : 2 taches verifient les donnees et conditions.

---

#### <a id="t10"></a>391.2.3 - Verification Nb Filiation

**Role** : Verification : Verification Nb Filiation.
**Delegue a** : [Verification Aut sans ecran (IDE 320)](PBG-IDE-320.md), [Verification Autorisation (IDE 319)](PBG-IDE-319.md), [Verification Suppression (IDE 182)](PBG-IDE-182.md)

---

#### <a id="t12"></a>391.2.4 - Controle Cloture Caisse

**Role** : Verification : Controle Cloture Caisse.
**Variables liees** : BC (W1 passe controle caisse)
**Delegue a** : [Verification Aut sans ecran (IDE 320)](PBG-IDE-320.md), [Verification Autorisation (IDE 319)](PBG-IDE-319.md), [Verification Suppression (IDE 182)](PBG-IDE-182.md)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: (aucun)
- **Appelle**: 19 programmes | **Tables**: 17 (W:4 R:5 L:10) | **Taches**: 17 | **Expressions**: 3

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (6 / 17)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 391.2 | 391.2 | Planning sejours | MDI | 1264 | 297 | Traitement |
| 2 | 391.2.1 | 391.2.1 | Recherche Nom | Modal | 570 | 92 | Consultation |
| 3 | 391.2.2 | 391.2.2 | Affichage Periodes | Modal | 669 | 133 | Consultation |
| 4 | 391.2.5 | 391.2.5 | Demande de confirmation | Modal | 461 | 71 | Traitement |
| 5 | 391.2.7 | 391.2.7 | Recherche | Modal | 571 | 91 | Consultation |
| 6 | 391.2.8 | 391.2.8 | Recherche Prenom | Modal | 573 | 93 | Consultation |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t4"></a>391.2 - Planning sejours
**Tache** : [391.2](#t4) | **Type** : MDI | **Dimensions** : 1264 x 297 DLU
**Bloc** : Traitement | **Titre IDE** : Planning sejours

<!-- FORM-DATA:
{
    "width":  1264,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  4,
                         "type":  "label",
                         "var":  "",
                         "y":  2,
                         "w":  1251,
                         "fmt":  "",
                         "name":  "",
                         "h":  19,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  589,
                         "type":  "label",
                         "var":  "",
                         "y":  22,
                         "w":  666,
                         "fmt":  "",
                         "name":  "",
                         "h":  59,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  4,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "110",
                         "w":  584,
                         "y":  30,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  13,
                         "h":  232,
                         "cols":  [
                                      {
                                          "title":  "N°Adhérent",
                                          "layer":  1,
                                          "w":  198
                                      },
                                      {
                                          "title":  "Nom",
                                          "layer":  2,
                                          "w":  224
                                      },
                                      {
                                          "title":  "Prénom",
                                          "layer":  3,
                                          "w":  129
                                      }
                                  ],
                         "rows":  3
                     },
                     {
                         "x":  726,
                         "type":  "label",
                         "var":  "",
                         "y":  31,
                         "w":  118,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "N° Adhérent",
                         "parent":  4
                     },
                     {
                         "x":  726,
                         "type":  "label",
                         "var":  "",
                         "y":  43,
                         "w":  118,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Séminaire",
                         "parent":  4
                     },
                     {
                         "x":  726,
                         "type":  "label",
                         "var":  "",
                         "y":  55,
                         "w":  118,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Dossier",
                         "parent":  4
                     },
                     {
                         "x":  726,
                         "type":  "label",
                         "var":  "",
                         "y":  68,
                         "w":  118,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Accompagnant",
                         "parent":  4
                     },
                     {
                         "x":  589,
                         "type":  "label",
                         "var":  "",
                         "y":  83,
                         "w":  666,
                         "fmt":  "",
                         "name":  "",
                         "h":  36,
                         "color":  "195",
                         "text":  "Séjour",
                         "parent":  null
                     },
                     {
                         "x":  602,
                         "type":  "label",
                         "var":  "",
                         "y":  95,
                         "w":  88,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Arrivée",
                         "parent":  27
                     },
                     {
                         "x":  909,
                         "type":  "label",
                         "var":  "",
                         "y":  95,
                         "w":  79,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Départ",
                         "parent":  27
                     },
                     {
                         "x":  602,
                         "type":  "label",
                         "var":  "",
                         "y":  106,
                         "w":  64,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Groupe",
                         "parent":  27
                     },
                     {
                         "x":  909,
                         "type":  "label",
                         "var":  "",
                         "y":  106,
                         "w":  84,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Groupe",
                         "parent":  27
                     },
                     {
                         "x":  1,
                         "type":  "label",
                         "var":  "",
                         "y":  270,
                         "w":  1256,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  208,
                         "type":  "edit",
                         "var":  "",
                         "y":  45,
                         "w":  214,
                         "fmt":  "",
                         "name":  "gm_nom",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  436,
                         "type":  "edit",
                         "var":  "",
                         "y":  45,
                         "w":  115,
                         "fmt":  "",
                         "name":  "CLI Prenom",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  11,
                         "type":  "edit",
                         "var":  "",
                         "y":  44,
                         "w":  126,
                         "fmt":  "#10P0",
                         "name":  "",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  148,
                         "type":  "edit",
                         "var":  "",
                         "y":  45,
                         "w":  42,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  848,
                         "type":  "edit",
                         "var":  "",
                         "y":  42,
                         "w":  235,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  710,
                         "type":  "edit",
                         "var":  "",
                         "y":  95,
                         "w":  122,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  27
                     },
                     {
                         "x":  844,
                         "type":  "edit",
                         "var":  "",
                         "y":  95,
                         "w":  42,
                         "fmt":  "UUh",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  27
                     },
                     {
                         "x":  1000,
                         "type":  "edit",
                         "var":  "",
                         "y":  95,
                         "w":  122,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  27
                     },
                     {
                         "x":  1134,
                         "type":  "edit",
                         "var":  "",
                         "y":  95,
                         "w":  42,
                         "fmt":  "UUh",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  27
                     },
                     {
                         "x":  1046,
                         "type":  "edit",
                         "var":  "",
                         "y":  54,
                         "w":  200,
                         "fmt":  "",
                         "name":  "V.Libelle fidelisation",
                         "h":  8,
                         "color":  "164",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  314,
                         "type":  "button",
                         "var":  "",
                         "y":  273,
                         "w":  152,
                         "fmt":  "\u0026Rechercher",
                         "name":  "bouton rech Nom",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  38
                     },
                     {
                         "x":  620,
                         "type":  "button",
                         "var":  "",
                         "y":  273,
                         "w":  152,
                         "fmt":  "\u0026Suppression",
                         "name":  "bouton supprimer",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  38
                     },
                     {
                         "x":  773,
                         "type":  "button",
                         "var":  "",
                         "y":  273,
                         "w":  152,
                         "fmt":  "\u0026Modification",
                         "name":  "bouton modification",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  38
                     },
                     {
                         "x":  926,
                         "type":  "button",
                         "var":  "",
                         "y":  273,
                         "w":  152,
                         "fmt":  "\u0026Création",
                         "name":  "bouton creation",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  38
                     },
                     {
                         "x":  10,
                         "type":  "edit",
                         "var":  "",
                         "y":  6,
                         "w":  454,
                         "fmt":  "20",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  1045,
                         "type":  "edit",
                         "var":  "",
                         "y":  7,
                         "w":  203,
                         "fmt":  "WWW DD MMM YYYYT",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  597,
                         "type":  "image",
                         "var":  "",
                         "y":  30,
                         "w":  126,
                         "fmt":  "",
                         "name":  "",
                         "h":  46,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  848,
                         "type":  "edit",
                         "var":  "",
                         "y":  31,
                         "w":  158,
                         "fmt":  "16",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  1096,
                         "type":  "edit",
                         "var":  "",
                         "y":  31,
                         "w":  151,
                         "fmt":  "10",
                         "name":  "",
                         "h":  8,
                         "color":  "168",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  1094,
                         "type":  "edit",
                         "var":  "",
                         "y":  42,
                         "w":  70,
                         "fmt":  "UX5",
                         "name":  "",
                         "h":  8,
                         "color":  "163",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  1194,
                         "type":  "edit",
                         "var":  "",
                         "y":  42,
                         "w":  53,
                         "fmt":  "4",
                         "name":  "",
                         "h":  8,
                         "color":  "168",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  848,
                         "type":  "edit",
                         "var":  "",
                         "y":  54,
                         "w":  158,
                         "fmt":  "15",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  1016,
                         "type":  "edit",
                         "var":  "",
                         "y":  54,
                         "w":  23,
                         "fmt":  "U",
                         "name":  "",
                         "h":  8,
                         "color":  "164",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  848,
                         "type":  "edit",
                         "var":  "",
                         "y":  67,
                         "w":  347,
                         "fmt":  "UX29",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  710,
                         "type":  "edit",
                         "var":  "",
                         "y":  106,
                         "w":  174,
                         "fmt":  "15",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  27
                     },
                     {
                         "x":  1000,
                         "type":  "edit",
                         "var":  "",
                         "y":  106,
                         "w":  174,
                         "fmt":  "15",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  27
                     },
                     {
                         "x":  8,
                         "type":  "button",
                         "var":  "",
                         "y":  273,
                         "w":  152,
                         "fmt":  "\u0026Quitter",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  38
                     },
                     {
                         "x":  161,
                         "type":  "button",
                         "var":  "",
                         "y":  273,
                         "w":  152,
                         "fmt":  "Import",
                         "name":  "Bt.Import",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  38
                     },
                     {
                         "x":  1085,
                         "type":  "button",
                         "var":  "",
                         "y":  273,
                         "w":  168,
                         "fmt":  "C\u0026ommentaire NA",
                         "name":  "Bt. Commentaires NA",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  38
                     },
                     {
                         "x":  595,
                         "type":  "subform",
                         "var":  "",
                         "y":  119,
                         "w":  669,
                         "fmt":  "",
                         "name":  "Affichage Periodes",
                         "h":  150,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  1010,
                         "type":  "edit",
                         "var":  "",
                         "y":  31,
                         "w":  78,
                         "fmt":  "30",
                         "name":  "",
                         "h":  10,
                         "color":  "204",
                         "text":  "",
                         "parent":  4
                     }
                 ],
    "taskId":  "391.2",
    "height":  297
}
-->

<details>
<summary><strong>Champs : 22 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 208,45 | gm_nom | - | edit |
| 436,45 | CLI Prenom | - | edit |
| 11,44 | #10P0 | - | edit |
| 148,45 | (sans nom) | - | edit |
| 848,42 | (sans nom) | - | edit |
| 710,95 | (sans nom) | - | edit |
| 844,95 | UUh | - | edit |
| 1000,95 | (sans nom) | - | edit |
| 1134,95 | UUh | - | edit |
| 1046,54 | V.Libelle fidelisation | - | edit |
| 10,6 | 20 | - | edit |
| 1045,7 | WWW DD MMM YYYYT | - | edit |
| 848,31 | 16 | - | edit |
| 1096,31 | 10 | - | edit |
| 1094,42 | UX5 | - | edit |
| 1194,42 | 4 | - | edit |
| 848,54 | 15 | - | edit |
| 1016,54 | U | - | edit |
| 848,67 | UX29 | - | edit |
| 710,106 | 15 | - | edit |
| 1000,106 | 15 | - | edit |
| 1010,31 | 30 | - | edit |

</details>

<details>
<summary><strong>Boutons : 7 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Rechercher | 314,273 | Ouvre la selection |
| Suppression | 620,273 | Appel [   Suppression Periode Client (IDE 79)](PBG-IDE-79.md) |
| Modification | 773,273 | Modifie l'element |
| Création | 926,273 | Bouton fonctionnel |
| Quitter | 8,273 | Quitte le programme |
| Import | 161,273 | Bouton fonctionnel |
| Commentaire NA | 1085,273 | Appel [   Affichage Commentaire (IDE 74)](PBG-IDE-74.md) |

</details>

---

#### <a id="ecran-t5"></a>391.2.1 - Recherche Nom
**Tache** : [391.2.1](#t5) | **Type** : Modal | **Dimensions** : 570 x 92 DLU
**Bloc** : Consultation | **Titre IDE** : Recherche Nom

<!-- FORM-DATA:
{
    "width":  570,
    "vFactor":  8,
    "type":  "Modal",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  154,
                         "type":  "label",
                         "var":  "",
                         "y":  23,
                         "w":  407,
                         "fmt":  "",
                         "name":  "",
                         "h":  27,
                         "color":  "1",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  163,
                         "type":  "label",
                         "var":  "",
                         "y":  32,
                         "w":  125,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Nom recherche",
                         "parent":  2
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  65,
                         "w":  566,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  300,
                         "type":  "edit",
                         "var":  "",
                         "y":  31,
                         "w":  238,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  2
                     },
                     {
                         "x":  8,
                         "type":  "button",
                         "var":  "",
                         "y":  68,
                         "w":  154,
                         "fmt":  "\u0026Ok",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  170,
                         "type":  "button",
                         "var":  "",
                         "y":  68,
                         "w":  154,
                         "fmt":  "A\u0026bandonner",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  5,
                         "type":  "image",
                         "var":  "",
                         "y":  1,
                         "w":  138,
                         "fmt":  "",
                         "name":  "",
                         "h":  61,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "391.2.1",
    "height":  92
}
-->

<details>
<summary><strong>Champs : 1 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 300,31 | (sans nom) | - | edit |

</details>

<details>
<summary><strong>Boutons : 2 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Ok | 8,68 | Valide la saisie et enregistre |
| Abandonner | 170,68 | Annule et retour au menu |

</details>

---

#### <a id="ecran-t7"></a>391.2.2 - Affichage Periodes
**Tache** : [391.2.2](#t7) | **Type** : Modal | **Dimensions** : 669 x 133 DLU
**Bloc** : Consultation | **Titre IDE** : Affichage Periodes

<!-- FORM-DATA:
{
    "width":  669,
    "vFactor":  8,
    "type":  "Modal",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  3,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  665,
                         "fmt":  "",
                         "name":  "",
                         "h":  128,
                         "color":  "195",
                         "text":  "Périodes",
                         "parent":  null
                     },
                     {
                         "x":  299,
                         "type":  "label",
                         "var":  "",
                         "y":  9,
                         "w":  65,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Pont",
                         "parent":  1
                     },
                     {
                         "x":  421,
                         "type":  "label",
                         "var":  "",
                         "y":  9,
                         "w":  81,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Abandon",
                         "parent":  1
                     },
                     {
                         "x":  14,
                         "type":  "label",
                         "var":  "",
                         "y":  9,
                         "w":  61,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Qualité",
                         "parent":  1
                     },
                     {
                         "x":  14,
                         "type":  "label",
                         "var":  "",
                         "y":  20,
                         "w":  113,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Logement",
                         "parent":  1
                     },
                     {
                         "x":  156,
                         "type":  "label",
                         "var":  "",
                         "y":  20,
                         "w":  13,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "-",
                         "parent":  1
                     },
                     {
                         "x":  14,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "7",
                         "w":  648,
                         "y":  32,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  13,
                         "h":  66,
                         "cols":  [
                                      {
                                          "title":  "",
                                          "layer":  1,
                                          "w":  270
                                      },
                                      {
                                          "title":  "",
                                          "layer":  2,
                                          "w":  79
                                      },
                                      {
                                          "title":  "",
                                          "layer":  3,
                                          "w":  55
                                      },
                                      {
                                          "title":  "",
                                          "layer":  4,
                                          "w":  77
                                      },
                                      {
                                          "title":  "",
                                          "layer":  5,
                                          "w":  56
                                      },
                                      {
                                          "title":  "",
                                          "layer":  6,
                                          "w":  76
                                      }
                                  ],
                         "rows":  6
                     },
                     {
                         "x":  11,
                         "type":  "label",
                         "var":  "",
                         "y":  101,
                         "w":  649,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  292,
                         "type":  "edit",
                         "var":  "",
                         "y":  35,
                         "w":  64,
                         "fmt":  "DD/MM",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  14
                     },
                     {
                         "x":  371,
                         "type":  "edit",
                         "var":  "",
                         "y":  35,
                         "w":  42,
                         "fmt":  "UUh",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  14
                     },
                     {
                         "x":  426,
                         "type":  "edit",
                         "var":  "",
                         "y":  35,
                         "w":  64,
                         "fmt":  "DD/MM",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  14
                     },
                     {
                         "x":  502,
                         "type":  "edit",
                         "var":  "",
                         "y":  35,
                         "w":  42,
                         "fmt":  "UUh",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  14
                     },
                     {
                         "x":  58,
                         "type":  "edit",
                         "var":  "",
                         "y":  35,
                         "w":  221,
                         "fmt":  "",
                         "name":  "HEB Libelle",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  14
                     },
                     {
                         "x":  559,
                         "type":  "edit",
                         "var":  "",
                         "y":  35,
                         "w":  65,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  14
                     },
                     {
                         "x":  132,
                         "type":  "edit",
                         "var":  "",
                         "y":  9,
                         "w":  75,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  216,
                         "type":  "edit",
                         "var":  "",
                         "y":  9,
                         "w":  53,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "142",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  22,
                         "type":  "edit",
                         "var":  "",
                         "y":  35,
                         "w":  30,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  14
                     },
                     {
                         "x":  132,
                         "type":  "edit",
                         "var":  "",
                         "y":  20,
                         "w":  19,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  176,
                         "type":  "edit",
                         "var":  "",
                         "y":  20,
                         "w":  75,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  263,
                         "type":  "edit",
                         "var":  "",
                         "y":  20,
                         "w":  232,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "142",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  516,
                         "type":  "edit",
                         "var":  "",
                         "y":  9,
                         "w":  126,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  373,
                         "type":  "edit",
                         "var":  "",
                         "y":  9,
                         "w":  26,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  17,
                         "type":  "button",
                         "var":  "",
                         "y":  104,
                         "w":  120,
                         "fmt":  "\u0026Prolonger",
                         "name":  "Bouton prolongation",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  146,
                         "type":  "button",
                         "var":  "",
                         "y":  104,
                         "w":  120,
                         "fmt":  "\u0026Interrompre",
                         "name":  "Bouton Interruption",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  275,
                         "type":  "button",
                         "var":  "",
                         "y":  104,
                         "w":  120,
                         "fmt":  "",
                         "name":  "Bouton avancer",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  404,
                         "type":  "button",
                         "var":  "",
                         "y":  104,
                         "w":  120,
                         "fmt":  "\u0026Recodifier",
                         "name":  "Bouton recodifier",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  534,
                         "type":  "button",
                         "var":  "",
                         "y":  104,
                         "w":  120,
                         "fmt":  "\u0026Supprimer",
                         "name":  "Bouton supprimer",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "391.2.2",
    "height":  133
}
-->

<details>
<summary><strong>Champs : 14 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 292,35 | DD/MM | - | edit |
| 371,35 | UUh | - | edit |
| 426,35 | DD/MM | - | edit |
| 502,35 | UUh | - | edit |
| 58,35 | HEB Libelle | - | edit |
| 559,35 | (sans nom) | - | edit |
| 132,9 | (sans nom) | - | edit |
| 216,9 | (sans nom) | - | edit |
| 22,35 | (sans nom) | - | edit |
| 132,20 | (sans nom) | - | edit |
| 176,20 | (sans nom) | - | edit |
| 263,20 | (sans nom) | - | edit |
| 516,9 | (sans nom) | - | edit |
| 373,9 | (sans nom) | - | edit |

</details>

<details>
<summary><strong>Boutons : 5 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Prolonger | 17,104 | Appel [   Prolongation Client (IDE 83)](PBG-IDE-83.md) |
| Interrompre | 146,104 | Appel [   Interruption Client (IDE 80)](PBG-IDE-80.md) |
| avancer | 275,104 | Appel [   Avancement Client (IDE 78)](PBG-IDE-78.md) |
| Recodifier | 404,104 | Appel [   Recodification Client (IDE 77)](PBG-IDE-77.md) |
| Supprimer | 534,104 | Appel [   Suppression Periode Client (IDE 79)](PBG-IDE-79.md) |

</details>

---

#### <a id="ecran-t13"></a>391.2.5 - Demande de confirmation
**Tache** : [391.2.5](#t13) | **Type** : Modal | **Dimensions** : 461 x 71 DLU
**Bloc** : Traitement | **Titre IDE** : Demande de confirmation

<!-- FORM-DATA:
{
    "width":  461,
    "vFactor":  8,
    "type":  "Modal",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  458,
                         "fmt":  "",
                         "name":  "",
                         "h":  69,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  86,
                         "type":  "label",
                         "var":  "",
                         "y":  12,
                         "w":  181,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Motif de la suppression",
                         "parent":  null
                     },
                     {
                         "x":  3,
                         "type":  "label",
                         "var":  "",
                         "y":  43,
                         "w":  450,
                         "fmt":  "",
                         "name":  "",
                         "h":  25,
                         "color":  "1",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  86,
                         "type":  "edit",
                         "var":  "",
                         "y":  22,
                         "w":  350,
                         "fmt":  "",
                         "name":  "W2 Motif",
                         "h":  12,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  12,
                         "type":  "button",
                         "var":  "",
                         "y":  47,
                         "w":  154,
                         "fmt":  "\u0026Ok",
                         "name":  "bouton oui",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  175,
                         "type":  "button",
                         "var":  "",
                         "y":  47,
                         "w":  154,
                         "fmt":  "A\u0026bandonner",
                         "name":  "bouton non",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  6,
                         "type":  "image",
                         "var":  "",
                         "y":  3,
                         "w":  76,
                         "fmt":  "",
                         "name":  "",
                         "h":  30,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     }
                 ],
    "taskId":  "391.2.5",
    "height":  71
}
-->

<details>
<summary><strong>Champs : 1 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 86,22 | W2 Motif | - | edit |

</details>

<details>
<summary><strong>Boutons : 2 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Ok | 12,47 | Valide la saisie et enregistre |
| Abandonner | 175,47 | Annule et retour au menu |

</details>

---

#### <a id="ecran-t18"></a>391.2.7 - Recherche
**Tache** : [391.2.7](#t18) | **Type** : Modal | **Dimensions** : 571 x 91 DLU
**Bloc** : Consultation | **Titre IDE** : Recherche

<!-- FORM-DATA:
{
    "width":  571,
    "vFactor":  8,
    "type":  "Modal",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  154,
                         "type":  "label",
                         "var":  "",
                         "y":  10,
                         "w":  407,
                         "fmt":  "",
                         "name":  "",
                         "h":  44,
                         "color":  "1",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  163,
                         "type":  "label",
                         "var":  "",
                         "y":  18,
                         "w":  125,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "Type Client",
                         "parent":  2
                     },
                     {
                         "x":  163,
                         "type":  "label",
                         "var":  "",
                         "y":  37,
                         "w":  125,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "N° Adherent",
                         "parent":  2
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  65,
                         "w":  566,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  300,
                         "type":  "edit",
                         "var":  "",
                         "y":  18,
                         "w":  34,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  2
                     },
                     {
                         "x":  300,
                         "type":  "edit",
                         "var":  "",
                         "y":  36,
                         "w":  238,
                         "fmt":  "#10P0",
                         "name":  "",
                         "h":  11,
                         "color":  "110",
                         "text":  "",
                         "parent":  2
                     },
                     {
                         "x":  8,
                         "type":  "button",
                         "var":  "",
                         "y":  69,
                         "w":  154,
                         "fmt":  "\u0026Ok",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  170,
                         "type":  "button",
                         "var":  "",
                         "y":  69,
                         "w":  154,
                         "fmt":  "A\u0026bandonner",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  5,
                         "type":  "image",
                         "var":  "",
                         "y":  1,
                         "w":  138,
                         "fmt":  "",
                         "name":  "",
                         "h":  61,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "391.2.7",
    "height":  91
}
-->

<details>
<summary><strong>Champs : 2 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 300,18 | (sans nom) | - | edit |
| 300,36 | #10P0 | - | edit |

</details>

<details>
<summary><strong>Boutons : 2 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Ok | 8,69 | Valide la saisie et enregistre |
| Abandonner | 170,69 | Annule et retour au menu |

</details>

---

#### <a id="ecran-t19"></a>391.2.8 - Recherche Prenom
**Tache** : [391.2.8](#t19) | **Type** : Modal | **Dimensions** : 573 x 93 DLU
**Bloc** : Consultation | **Titre IDE** : Recherche Prenom

<!-- FORM-DATA:
{
    "width":  573,
    "vFactor":  8,
    "type":  "Modal",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  154,
                         "type":  "label",
                         "var":  "",
                         "y":  23,
                         "w":  407,
                         "fmt":  "",
                         "name":  "",
                         "h":  27,
                         "color":  "1",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  163,
                         "type":  "label",
                         "var":  "",
                         "y":  34,
                         "w":  125,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Prénom",
                         "parent":  2
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  65,
                         "w":  566,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  300,
                         "type":  "edit",
                         "var":  "",
                         "y":  33,
                         "w":  238,
                         "fmt":  "UX15",
                         "name":  "",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  2
                     },
                     {
                         "x":  8,
                         "type":  "button",
                         "var":  "",
                         "y":  68,
                         "w":  154,
                         "fmt":  "\u0026Ok",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  170,
                         "type":  "button",
                         "var":  "",
                         "y":  68,
                         "w":  154,
                         "fmt":  "A\u0026bandonner",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  5,
                         "type":  "image",
                         "var":  "",
                         "y":  1,
                         "w":  138,
                         "fmt":  "",
                         "name":  "",
                         "h":  61,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "391.2.8",
    "height":  93
}
-->

<details>
<summary><strong>Champs : 1 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 300,33 | UX15 | - | edit |

</details>

<details>
<summary><strong>Boutons : 2 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Ok | 8,68 | Valide la saisie et enregistre |
| Abandonner | 170,68 | Annule et retour au menu |

</details>

## 9. NAVIGATION

### 9.1 Enchainement des ecrans

```mermaid
flowchart TD
    START([Entree])
    style START fill:#3fb950
    VF4[391.2 Planning sejours]
    style VF4 fill:#58a6ff
    VF5[391.2.1 Recherche Nom]
    style VF5 fill:#58a6ff
    VF7[391.2.2 Affichage Periodes]
    style VF7 fill:#58a6ff
    VF13[391.2.5 Demande de confirm...]
    style VF13 fill:#58a6ff
    VF18[391.2.7 Recherche]
    style VF18 fill:#58a6ff
    VF19[391.2.8 Recherche Prenom]
    style VF19 fill:#58a6ff
    EXT320[IDE 320 Verification A...]
    style EXT320 fill:#3fb950
    EXT179[IDE 179 Marquage Caiss...]
    style EXT179 fill:#3fb950
    EXT319[IDE 319 Verification A...]
    style EXT319 fill:#3fb950
    EXT74[IDE 74 Affichage Comme...]
    style EXT74 fill:#3fb950
    EXT77[IDE 77 Recodification ...]
    style EXT77 fill:#3fb950
    EXT78[IDE 78 Avancement Client]
    style EXT78 fill:#3fb950
    EXT79[IDE 79 Suppression Per...]
    style EXT79 fill:#3fb950
    EXT80[IDE 80 Interruption Cl...]
    style EXT80 fill:#3fb950
    EXT81[IDE 81 Selection Inter...]
    style EXT81 fill:#3fb950
    EXT82[IDE 82 Suppression Client]
    style EXT82 fill:#3fb950
    EXT83[IDE 83 Prolongation Cl...]
    style EXT83 fill:#3fb950
    EXT87[IDE 87 Creation client...]
    style EXT87 fill:#3fb950
    EXT91[IDE 91 Modules clients...]
    style EXT91 fill:#3fb950
    EXT95[IDE 95 Contrôle des in...]
    style EXT95 fill:#3fb950
    EXT176[IDE 176 Demarquage Caisse]
    style EXT176 fill:#3fb950
    EXT178[IDE 178 Marquage Caiss...]
    style EXT178 fill:#3fb950
    EXT182[IDE 182 Verification S...]
    style EXT182 fill:#3fb950
    EXT269[IDE 269 Separation de ...]
    style EXT269 fill:#3fb950
    EXT317[IDE 317 Recuperation d...]
    style EXT317 fill:#3fb950
    FIN([Sortie])
    style FIN fill:#f85149
    START --> VF4
    VF4 -->|Controle/validation| EXT320
    VF4 -->|Sous-programme| EXT179
    VF4 -->|Controle/validation| EXT319
    VF4 -->|Affichage donnees| EXT74
    VF4 -->|Sous-programme| EXT77
    VF4 -->|Sous-programme| EXT78
    VF4 -->|Sous-programme| EXT79
    VF4 -->|Sous-programme| EXT80
    EXT317 --> FIN
```

**Detail par enchainement :**

| Depuis | Action | Vers | Retour |
|--------|--------|------|--------|
| Planning sejours | Controle/validation | [Verification Aut sans ecran (IDE 320)](PBG-IDE-320.md) | Retour ecran |
| Planning sejours | Sous-programme | [Marquage Caisse logique (IDE 179)](PBG-IDE-179.md) | Retour ecran |
| Planning sejours | Controle/validation | [Verification Autorisation (IDE 319)](PBG-IDE-319.md) | Retour ecran |
| Planning sejours | Affichage donnees | [   Affichage Commentaire (IDE 74)](PBG-IDE-74.md) | Retour ecran |
| Planning sejours | Sous-programme | [   Recodification Client (IDE 77)](PBG-IDE-77.md) | Retour ecran |
| Planning sejours | Sous-programme | [   Avancement Client (IDE 78)](PBG-IDE-78.md) | Retour ecran |
| Planning sejours | Sous-programme | [   Suppression Periode Client (IDE 79)](PBG-IDE-79.md) | Retour ecran |
| Planning sejours | Sous-programme | [   Interruption Client (IDE 80)](PBG-IDE-80.md) | Retour ecran |
| Planning sejours | Selection/consultation | [   Selection Interruption (IDE 81)](PBG-IDE-81.md) | Retour ecran |
| Planning sejours | Sous-programme | [   Suppression Client (IDE 82)](PBG-IDE-82.md) | Retour ecran |
| Planning sejours | Sous-programme | [   Prolongation Client (IDE 83)](PBG-IDE-83.md) | Retour ecran |
| Planning sejours | Sous-programme | [Creation clients Identite (IDE 87)](PBG-IDE-87.md) | Retour ecran |
| Planning sejours | Sous-programme | [Modules clients Identite (IDE 91)](PBG-IDE-91.md) | Retour ecran |
| Planning sejours | Sous-programme | [Contrôle des informations (IDE 95)](PBG-IDE-95.md) | Retour ecran |
| Planning sejours | Sous-programme | [Demarquage Caisse (IDE 176)](PBG-IDE-176.md) | Retour ecran |
| Planning sejours | Sous-programme | [Marquage Caisse alpha (IDE 178)](PBG-IDE-178.md) | Retour ecran |
| Planning sejours | Controle/validation | [Verification Suppression (IDE 182)](PBG-IDE-182.md) | Retour ecran |
| Planning sejours | Sous-programme | [Separation de comptes (IDE 269)](PBG-IDE-269.md) | Retour ecran |
| Planning sejours | Recuperation donnees | [Recuperation du titre (IDE 317)](PBG-IDE-317.md) | Retour ecran |

### 9.3 Structure hierarchique (17 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **391.1** | [**Module des Sejours** (391)](#t1) [mockup](#ecran-t1) | MDI | 13x4 | Traitement |
| 391.1.1 | [Determination Age Bebe (391.1)](#t2) | MDI | - | |
| 391.1.2 | [Planning sejours (391.2)](#t4) [mockup](#ecran-t4) | MDI | 1264x297 | |
| 391.1.3 | [Recuperation date d/f (391.2.2.1)](#t8) | MDI | - | |
| 391.1.4 | [Demande de confirmation (391.2.5)](#t13) [mockup](#ecran-t13) | Modal | 461x71 | |
| 391.1.5 | [Tracage Suppression (391.2.6)](#t14) | MDI | - | |
| 391.1.6 | [Tracage (391.2.6.2)](#t16) | MDI | - | |
| 391.1.7 | [Suppression carte (391.2.10)](#t21) | MDI | - | |
| **391.2** | [**Recherche Nom** (391.2.1)](#t5) [mockup](#ecran-t5) | Modal | 570x92 | Consultation |
| 391.2.1 | [Affichage Periodes (391.2.2)](#t7) [mockup](#ecran-t7) | Modal | 669x133 | |
| 391.2.2 | [Recherche (391.2.7)](#t18) [mockup](#ecran-t18) | Modal | 571x91 | |
| 391.2.3 | [Recherche Prenom (391.2.8)](#t19) [mockup](#ecran-t19) | Modal | 573x93 | |
| **391.3** | [**Calcul Date Grecques** (391.2.2.2)](#t9) | MDI | - | Calcul |
| 391.3.1 | [Compteur (391.2.6.1)](#t15) | MDI | - | |
| 391.3.2 | [Calcul Date Grecques (391.2.9)](#t20) | MDI | - | |
| **391.4** | [**Verification Nb Filiation** (391.2.3)](#t10) | MDI | - | Validation |
| 391.4.1 | [Controle Cloture Caisse (391.2.4)](#t12) | MDI | - | |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Affichage Clients]
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

### Tables utilisees (17)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 23 | reseau_cloture___rec | Donnees reseau/cloture | DB | R |   |   | 1 |
| 30 | gm-recherche_____gmr | Index de recherche | DB | R |   |   | 2 |
| 31 | gm-complet_______gmc |  | DB |   |   | L | 1 |
| 34 | hebergement______heb | Hebergement (chambres) | DB | R |   | L | 3 |
| 36 | client_gm |  | DB | R |   | L | 2 |
| 68 | compteurs________cpt | Comptes GM (generaux) | DB |   | **W** |   | 1 |
| 84 | mouchard_________mou |  | DB |   | **W** |   | 1 |
| 108 | code_logement____clo |  | DB |   |   | L | 1 |
| 113 | tables_village |  | DB | R |   |   | 1 |
| 171 | commentaire______com |  | DB |   |   | L | 1 |
| 312 | ez_card |  | DB |   | **W** |   | 1 |
| 315 | fi_complet_______gm_go |  | DB |   | **W** |   | 2 |
| 358 | import_mod |  | DB |   |   | L | 1 |
| 689 | sous_imputation_par_service | Services / filieres | DB |   |   | L | 1 |
| 738 | pv_selling_unit |  | DB |   |   | L | 1 |
| 805 | vente_par_moyen_paiement | Donnees de ventes | DB |   |   | L | 1 |
| 846 | stat_lieu_vente | Statistiques point de vente | TMP |   |   | L | 1 |

### Colonnes par table (5 / 9 tables avec colonnes identifiees)

<details>
<summary>Table 23 - reseau_cloture___rec (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | W2 Cloture en cours | R | Numeric |

</details>

<details>
<summary>Table 30 - gm-recherche_____gmr (R) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | W1-Fin de Tache | R | Logical |
| B | W1-Accord suite | R | Alpha |
| C | W1-Date/Heure | R | Numeric |
| D | W1-Autorisation | R | Alpha |
| E | W1-Motif | R | Alpha |
| F | W1 ret lien Comment | R | Numeric |
| G | W1 N° Cas | R | Numeric |
| H | W1 type traitement | R | Alpha |
| I | W1 Autorisation creation | R | Alpha |
| J | W1 Autorisation Modification | R | Alpha |
| K | W1 Autorisation Suppression | R | Alpha |
| L | Autorisation Prolongement | R | Alpha |
| M | Autorisation Interruption | R | Alpha |
| N | Autorisation Avancement | R | Alpha |
| O | Autorisation Recodifier | R | Alpha |
| P | Autorisation supp periode | R | Alpha |
| Q | W1-Type Client | R | Alpha |
| R | W1-N° Adherent | R | Numeric |
| S | V.code fidelisation | R | Alpha |
| T | V.Libelle fidelisation | R | Alpha |
| U | V.Couleur fidelisation | R | Numeric |
| V | V.Existe ECI (Q60 Location) | R | Logical |
| W | V.Existe ECI (Q61 Cours) | R | Logical |
| X | V.Existe ECI (Q62 Enfant) | R | Logical |
| Y | v Libelle affichage ECI | R | Alpha |
| Z | bouton rech Nom | R | Alpha |
| BA | bouton Periode | R | Alpha |
| BB | W1 autorisation suppression | R | Alpha |
| BC | W1 passe controle caisse | R | Alpha |
| BD | bouton supprimer | R | Alpha |
| BE | bouton modification | R | Alpha |
| BF | bouton creation | R | Alpha |
| BG | v.titre | R | Alpha |
| BH | Column Name | R | Unicode |

</details>

<details>
<summary>Table 34 - hebergement______heb (R/L) - 3 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P.Num compte | R | Numeric |
| B | P.Filiation | R | Numeric |
| C | W3-Selection Choix | R | Alpha |
| D | W3-Autorisation | R | Alpha |
| E | W3-Qualite | R | Alpha |
| F | W3-Complement | R | Alpha |
| G | W3-Periode | R | Alpha |
| H | W3-fin tâche | R | Alpha |
| I | W3 date debut | R | Date |
| J | W3 date fin | R | Date |
| K | W3 confirmation (L) | R | Logical |
| L | Bouton prolongation | R | Alpha |
| M | Bouton Interruption | R | Alpha |
| N | Bouton avancer | R | Alpha |
| O | Bouton recodifier | R | Alpha |
| P | Bouton supprimer | R | Alpha |

</details>

<details>
<summary>Table 36 - client_gm (R/L) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | W2_Type Client | R | Alpha |
| B | W2-Rech Adherent | R | Numeric |
| C | W2_code retour | R | Logical |
| D | Bouton Ok | R | Alpha |

</details>

<details>
<summary>Table 68 - compteurs________cpt (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 84 - mouchard_________mou (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 113 - tables_village (R) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 312 - ez_card (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 315 - fi_complet_______gm_go (**W**) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (1)

Variables recues en parametre.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| B | P0 Front/Back | Alpha | - |

### 11.2 Variables de session (8)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| S | V.code fidelisation | Alpha | - |
| T | V.Libelle fidelisation | Alpha | - |
| U | V.Couleur fidelisation | Numeric | - |
| V | V.Existe ECI (Q60 Location) | Logical | - |
| W | V.Existe ECI (Q61 Cours) | Logical | - |
| X | V.Existe ECI (Q62 Enfant) | Logical | - |
| Y | v Libelle affichage ECI | Alpha | - |
| BG | v.titre | Alpha | - |

### 11.3 Autres (25)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P0-Nom Logement | Alpha | - |
| C | W0-Fin de Tache | Logical | 1x refs |
| D | W0-Age Bebe | Numeric | - |
| E | W0-Base Vide | Alpha | - |
| F | W0-Valeur tri | Numeric | - |
| G | W1 N° Cas | Numeric | - |
| H | W1 type traitement | Alpha | - |
| I | W1 Autorisation creation | Alpha | - |
| J | W1 Autorisation Modification | Alpha | - |
| K | W1 Autorisation Suppression | Alpha | - |
| L | Autorisation Prolongement | Alpha | - |
| M | Autorisation Interruption | Alpha | - |
| N | Autorisation Avancement | Alpha | - |
| O | Autorisation Recodifier | Alpha | - |
| P | Autorisation supp periode | Alpha | - |
| Q | W1-Type Client | Alpha | - |
| R | W1-N° Adherent | Numeric | - |
| Z | bouton rech Nom | Alpha | - |
| BA | bouton Periode | Alpha | - |
| BB | W1 autorisation suppression | Alpha | - |
| BC | W1 passe controle caisse | Alpha | - |
| BD | bouton supprimer | Alpha | - |
| BE | bouton modification | Alpha | - |
| BF | bouton creation | Alpha | - |
| BH | Column Name | Unicode | - |

<details>
<summary>Toutes les 34 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| P0 | **B** | P0 Front/Back | Alpha |
| V. | **S** | V.code fidelisation | Alpha |
| V. | **T** | V.Libelle fidelisation | Alpha |
| V. | **U** | V.Couleur fidelisation | Numeric |
| V. | **V** | V.Existe ECI (Q60 Location) | Logical |
| V. | **W** | V.Existe ECI (Q61 Cours) | Logical |
| V. | **X** | V.Existe ECI (Q62 Enfant) | Logical |
| V. | **Y** | v Libelle affichage ECI | Alpha |
| V. | **BG** | v.titre | Alpha |
| Autre | **A** | P0-Nom Logement | Alpha |
| Autre | **C** | W0-Fin de Tache | Logical |
| Autre | **D** | W0-Age Bebe | Numeric |
| Autre | **E** | W0-Base Vide | Alpha |
| Autre | **F** | W0-Valeur tri | Numeric |
| Autre | **G** | W1 N° Cas | Numeric |
| Autre | **H** | W1 type traitement | Alpha |
| Autre | **I** | W1 Autorisation creation | Alpha |
| Autre | **J** | W1 Autorisation Modification | Alpha |
| Autre | **K** | W1 Autorisation Suppression | Alpha |
| Autre | **L** | Autorisation Prolongement | Alpha |
| Autre | **M** | Autorisation Interruption | Alpha |
| Autre | **N** | Autorisation Avancement | Alpha |
| Autre | **O** | Autorisation Recodifier | Alpha |
| Autre | **P** | Autorisation supp periode | Alpha |
| Autre | **Q** | W1-Type Client | Alpha |
| Autre | **R** | W1-N° Adherent | Numeric |
| Autre | **Z** | bouton rech Nom | Alpha |
| Autre | **BA** | bouton Periode | Alpha |
| Autre | **BB** | W1 autorisation suppression | Alpha |
| Autre | **BC** | W1 passe controle caisse | Alpha |
| Autre | **BD** | bouton supprimer | Alpha |
| Autre | **BE** | bouton modification | Alpha |
| Autre | **BF** | bouton creation | Alpha |
| Autre | **BH** | Column Name | Unicode |

</details>

## 12. EXPRESSIONS

**3 / 3 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONSTANTE | 1 | 0 |
| OTHER | 2 | 0 |

### 12.2 Expressions cles par type

#### CONSTANTE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 1 | `1` | - |

#### OTHER (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 3 | `W0-Fin de Tache [C]` | - |
| OTHER | 2 | `GetParam ('FRONT')` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

**Chemin**: (pas de callers directs)

```mermaid
graph LR
    T391[391 Module Sejours Sub...]
    style T391 fill:#58a6ff
    NONE[Aucun caller]
    NONE -.-> T391
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| - | (aucun) | - |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T391[391 Module Sejours Sub...]
    style T391 fill:#58a6ff
    C320[320 Verification Aut s...]
    T391 --> C320
    style C320 fill:#3fb950
    C179[179 Marquage Caisse lo...]
    T391 --> C179
    style C179 fill:#3fb950
    C319[319 Verification Autor...]
    T391 --> C319
    style C319 fill:#3fb950
    C74[74 Affichage Commentaire]
    T391 --> C74
    style C74 fill:#3fb950
    C77[77 Recodification Client]
    T391 --> C77
    style C77 fill:#3fb950
    C78[78 Avancement Client]
    T391 --> C78
    style C78 fill:#3fb950
    C79[79 Suppression Periode...]
    T391 --> C79
    style C79 fill:#3fb950
    C80[80 Interruption Client]
    T391 --> C80
    style C80 fill:#3fb950
    C81[81 Selection Interruption]
    T391 --> C81
    style C81 fill:#3fb950
    C82[82 Suppression Client]
    T391 --> C82
    style C82 fill:#3fb950
    C83[83 Prolongation Client]
    T391 --> C83
    style C83 fill:#3fb950
    C87[87 Creation clients Id...]
    T391 --> C87
    style C87 fill:#3fb950
    C91[91 Modules clients Ide...]
    T391 --> C91
    style C91 fill:#3fb950
    C95[95 Contrôle des inform...]
    T391 --> C95
    style C95 fill:#3fb950
    C176[176 Demarquage Caisse]
    T391 --> C176
    style C176 fill:#3fb950
    C178[178 Marquage Caisse alpha]
    T391 --> C178
    style C178 fill:#3fb950
    C182[182 Verification Suppr...]
    T391 --> C182
    style C182 fill:#3fb950
    C269[269 Separation de comptes]
    T391 --> C269
    style C269 fill:#3fb950
    C317[317 Recuperation du titre]
    T391 --> C317
    style C317 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [320](PBG-IDE-320.md) | Verification Aut sans ecran | 8 | Controle/validation |
| [179](PBG-IDE-179.md) | Marquage Caisse logique | 5 | Sous-programme |
| [319](PBG-IDE-319.md) | Verification Autorisation | 5 | Controle/validation |
| [74](PBG-IDE-74.md) |    Affichage Commentaire | 1 | Affichage donnees |
| [77](PBG-IDE-77.md) |    Recodification Client | 1 | Sous-programme |
| [78](PBG-IDE-78.md) |    Avancement Client | 1 | Sous-programme |
| [79](PBG-IDE-79.md) |    Suppression Periode Client | 1 | Sous-programme |
| [80](PBG-IDE-80.md) |    Interruption Client | 1 | Sous-programme |
| [81](PBG-IDE-81.md) |    Selection Interruption | 1 | Selection/consultation |
| [82](PBG-IDE-82.md) |    Suppression Client | 1 | Sous-programme |
| [83](PBG-IDE-83.md) |    Prolongation Client | 1 | Sous-programme |
| [87](PBG-IDE-87.md) | Creation clients Identite | 1 | Sous-programme |
| [91](PBG-IDE-91.md) | Modules clients Identite | 1 | Sous-programme |
| [95](PBG-IDE-95.md) | Contrôle des informations | 1 | Sous-programme |
| [176](PBG-IDE-176.md) | Demarquage Caisse | 1 | Sous-programme |
| [178](PBG-IDE-178.md) | Marquage Caisse alpha | 1 | Sous-programme |
| [182](PBG-IDE-182.md) | Verification Suppression | 1 | Controle/validation |
| [269](PBG-IDE-269.md) | Separation de comptes | 1 | Sous-programme |
| [317](PBG-IDE-317.md) | Recuperation du titre | 1 | Recuperation donnees |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 569 | Programme volumineux |
| Expressions | 3 | Peu de logique |
| Tables WRITE | 4 | Impact modere |
| Sous-programmes | 19 | Forte dependance |
| Ecrans visibles | 6 | Interface complexe multi-ecrans |
| Code desactive | 0.7% (4 / 569) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (8 taches: 3 ecrans, 5 traitements)

- **Strategie** : Orchestrateur avec 3 ecrans (Razor/React) et 5 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 19 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Consultation (4 taches: 4 ecrans, 0 traitement)

- **Strategie** : Composants de recherche/selection en modales.
- 4 ecrans : Recherche Nom, Affichage Periodes, Recherche, Recherche Prenom

#### Calcul (3 taches: 0 ecran, 3 traitements)

- **Strategie** : Services de calcul purs (Domain Services).
- Migrer la logique de calcul (stock, compteurs, montants)

#### Validation (2 taches: 0 ecran, 2 traitements)

- **Strategie** : FluentValidation avec validators specifiques.
- Chaque tache de validation -> un validator injectable

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| compteurs________cpt | Table WRITE (Database) | 1x | Schema + repository |
| mouchard_________mou | Table WRITE (Database) | 1x | Schema + repository |
| ez_card | Table WRITE (Database) | 1x | Schema + repository |
| fi_complet_______gm_go | Table WRITE (Database) | 2x | Schema + repository |
| [Verification Aut sans ecran (IDE 320)](PBG-IDE-320.md) | Sous-programme | 8x | **CRITIQUE** - Controle/validation |
| [Verification Autorisation (IDE 319)](PBG-IDE-319.md) | Sous-programme | 5x | **CRITIQUE** - Controle/validation |
| [Marquage Caisse logique (IDE 179)](PBG-IDE-179.md) | Sous-programme | 5x | **CRITIQUE** - Sous-programme |
| [Contrôle des informations (IDE 95)](PBG-IDE-95.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Demarquage Caisse (IDE 176)](PBG-IDE-176.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Creation clients Identite (IDE 87)](PBG-IDE-87.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Modules clients Identite (IDE 91)](PBG-IDE-91.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Separation de comptes (IDE 269)](PBG-IDE-269.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Recuperation du titre (IDE 317)](PBG-IDE-317.md) | Sous-programme | 1x | Normale - Recuperation donnees |
| [Marquage Caisse alpha (IDE 178)](PBG-IDE-178.md) | Sous-programme | 1x | Normale - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 11:38*
