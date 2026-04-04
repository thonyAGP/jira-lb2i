# EXB IDE 6 - Annulation Ventes@

> **Analyse**: Phases 1-4 2026-02-03 10:30 -> 10:30 (23s) | Assemblage 10:30
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | EXB |
| IDE Position | 6 |
| Nom Programme | Annulation Ventes@ |
| Fichier source | `Prg_6.xml` |
| Domaine metier | Ventes |
| Taches | 52 (5 ecrans visibles) |
| Tables modifiees | 12 |
| Programmes appeles | 4 |

## 2. DESCRIPTION FONCTIONNELLE

**Annulation Ventes@** assure la gestion complete de ce processus, accessible depuis [Menu general (IDE 31)](EXB-IDE-31.md).

Le flux de traitement s'organise en **4 blocs fonctionnels** :

- **Traitement** (29 taches) : traitements metier divers
- **Calcul** (16 taches) : calculs de montants, stocks ou compteurs
- **Saisie** (6 taches) : ecrans de saisie utilisateur (formulaires, champs, donnees)
- **Consultation** (1 tache) : ecrans de recherche, selection et consultation

**Donnees modifiees** : 12 tables en ecriture (reseau_cloture___rec, comptable________cte, compte_gm________cgm, date_comptable___dat, intermed_compta__ite, vente, compteur_excurs__cte, date_comptable___dat, participants_____par, excurs_planning__epl, excursions_______exc, vente____________vep).

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Saisie (6 taches)

- **6** - Ventes **[[ECRAN]](#ecran-t1)**
- **6.1** - Annulation ventes excursion **[[ECRAN]](#ecran-t2)**
- **6.1.1.2** - Annulation de vente **[[ECRAN]](#ecran-t18)**
- **6.1.1.3** - Compteur vente
- **6.1.2** - Annulation de vente **[[ECRAN]](#ecran-t26)**
- **6.1.3** - Compteur vente

#### Phase 2 : Traitement (29 taches)

- **6.1.1** - Participants **[[ECRAN]](#ecran-t3)**
- **6.1.1.1** - Annulation
- **6.1.1.1.1** - Màj Excursions
- **6.1.1.1.2** - Màj Planning
- **6.1.1.1.3** - Generation Participants
- **6.1.1.1.4.1** - Imputation
- **6.1.1.1.4.2** - Date caisse
- **6.1.1.1.4.5** - Màj solde
- **6.1.1.1.5.1** - Imputation
- **6.1.1.1.5.2** - Date caisse
- **6.1.1.5** - Test      reseau caisse
- **6.1.1.6** - Deblocage reseau caisse
- **6.1.1.7** - Test Cloture
- **6.1.1.7.1** - Blocage Cloture v1
- **6.1.1.8** - Deblocage Cloture v1
- **6.1.5** - Annulation
- **6.1.5.1** - Màj Excursions
- **6.1.5.2** - Màj Planning
- **6.1.5.3** - Generation Participants
- **6.1.5.4.1** - Imputation
- **6.1.5.4.2** - Date caisse
- **6.1.5.4.5** - Màj solde
- **6.1.5.5.1** - Imputation
- **6.1.5.5.2** - Date caisse
- **6.1.6** - Test      reseau caisse
- **6.1.7** - Deblocage reseau caisse
- **6.1.8** - Test Cloture
- **6.1.8.1** - Blocage Cloture v1
- **6.1.1.9** - Deblocage Cloture v1

Delegue a : [Recuperation du titre (IDE 16)](EXB-IDE-16.md), [  Imp reçu annulation (IDE 5)](EXB-IDE-5.md), [Appel programme (IDE 17)](EXB-IDE-17.md)

#### Phase 3 : Calcul (16 taches)

- **6.1.1.1.4** - MAJ Comptable
- **6.1.1.1.4.3** - Creation comptable v1
- **6.1.1.1.4.4** - Creation comptable
- **6.1.1.1.5** - MAJ Comptable
- **6.1.1.1.5.3** - Creation comptable
- **6.1.1.4** - Date comptable
- **6.1.4** - Date comptable
- **6.1.5.4** - MAJ Comptable
- **6.1.5.4.3** - Creation comptable v1
- **6.1.5.4.4** - Creation comptable
- **6.1.5.5** - MAJ Comptable
- **6.1.5.5.3** - Creation comptable
- **6.1.1.1.4.6** - Creation comptable v1
- **6.1.1.1.5.4** - Creation comptable
- **6.1.5.4.6** - Creation comptable v1
- **6.1.5.5.4** - Creation comptable

#### Phase 4 : Consultation (1 tache)

- **6.2** - Recherche **[[ECRAN]](#ecran-t47)**

Delegue a : [Recuperation du titre (IDE 16)](EXB-IDE-16.md), [Zoom modes de paiement (IDE 47)](EXB-IDE-47.md)

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| compte_gm________cgm | **W** (6 usages) | Comptes GM (generaux) |
| reseau_cloture___rec | **W** (6 usages) | Donnees reseau/cloture |
| comptable________cte | **W** (4 usages) |  |
| date_comptable___dat | R/**W** (4 usages) |  |
| vente | **W** (4 usages) | Donnees de ventes |
| vente____________vep | **W** (3 usages) | Donnees de ventes |
| participants_____par | **W** (3 usages) |  |
| excursions_______exc | **W**/L (3 usages) |  |
| intermed_compta__ite | **W** (2 usages) |  |
| compteur_excurs__cte | **W** (2 usages) | Comptes GM (generaux) |
| date_comptable___dat | R/**W** (2 usages) |  |
| excurs_planning__epl | **W** (2 usages) |  |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Saisie (6 taches)

L'operateur saisit les donnees de la transaction via 4 ecrans (Ventes, Annulation ventes excursion, Annulation de vente, Annulation de vente).

---

#### <a id="t1"></a>6 - Ventes [[ECRAN]](#ecran-t1)

**Role** : Tache d'orchestration : point d'entree du programme (6 sous-taches). Coordonne l'enchainement des traitements.
**Ecran** : 216 x 20 DLU (MDI) | [Voir mockup](#ecran-t1)

<details>
<summary>5 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [6.1](#t2) | Annulation ventes excursion **[[ECRAN]](#ecran-t2)** | Saisie |
| [6.1.1.2](#t18) | Annulation de vente **[[ECRAN]](#ecran-t18)** | Saisie |
| [6.1.1.3](#t19) | Compteur vente | Saisie |
| [6.1.2](#t26) | Annulation de vente **[[ECRAN]](#ecran-t26)** | Saisie |
| [6.1.3](#t27) | Compteur vente | Saisie |

</details>

---

#### <a id="t2"></a>6.1 - Annulation ventes excursion [[ECRAN]](#ecran-t2)

**Role** : Saisie des donnees : Annulation ventes excursion.
**Ecran** : 1182 x 260 DLU (MDI) | [Voir mockup](#ecran-t2)
**Delegue a** : [  Imp reçu annulation (IDE 5)](EXB-IDE-5.md)

---

#### <a id="t18"></a>6.1.1.2 - Annulation de vente [[ECRAN]](#ecran-t18)

**Role** : Saisie des donnees : Annulation de vente.
**Ecran** : 630 x 150 DLU (MDI) | [Voir mockup](#ecran-t18)
**Variables liees** : F (W0 n° vente)
**Delegue a** : [  Imp reçu annulation (IDE 5)](EXB-IDE-5.md)

---

#### <a id="t19"></a>6.1.1.3 - Compteur vente

**Role** : Saisie des donnees : Compteur vente.
**Variables liees** : F (W0 n° vente), H (W0_Compteur)

---

#### <a id="t26"></a>6.1.2 - Annulation de vente [[ECRAN]](#ecran-t26)

**Role** : Saisie des donnees : Annulation de vente.
**Ecran** : 624 x 149 DLU (MDI) | [Voir mockup](#ecran-t26)
**Variables liees** : F (W0 n° vente)
**Delegue a** : [  Imp reçu annulation (IDE 5)](EXB-IDE-5.md)

---

#### <a id="t27"></a>6.1.3 - Compteur vente

**Role** : Saisie des donnees : Compteur vente.
**Variables liees** : F (W0 n° vente), H (W0_Compteur)


### 3.2 Traitement (29 taches)

Traitements internes.

---

#### <a id="t3"></a>6.1.1 - Participants [[ECRAN]](#ecran-t3)

**Role** : Traitement : Participants.
**Ecran** : 678 x 183 DLU (MDI) | [Voir mockup](#ecran-t3)

---

#### <a id="t4"></a>6.1.1.1 - Annulation

**Role** : Traitement : Annulation.

---

#### <a id="t5"></a>6.1.1.1.1 - Màj Excursions

**Role** : Traitement : Màj Excursions.

---

#### <a id="t6"></a>6.1.1.1.2 - Màj Planning

**Role** : Traitement : Màj Planning.

---

#### <a id="t7"></a>6.1.1.1.3 - Generation Participants

**Role** : Traitement : Generation Participants.

---

#### <a id="t9"></a>6.1.1.1.4.1 - Imputation

**Role** : Traitement : Imputation.

---

#### <a id="t10"></a>6.1.1.1.4.2 - Date caisse

**Role** : Traitement : Date caisse.
**Variables liees** : G (W0_Date_comptable)

---

#### <a id="t13"></a>6.1.1.1.4.5 - Màj solde

**Role** : Consultation/chargement : Màj solde.

---

#### <a id="t15"></a>6.1.1.1.5.1 - Imputation

**Role** : Traitement : Imputation.

---

#### <a id="t16"></a>6.1.1.1.5.2 - Date caisse

**Role** : Traitement : Date caisse.
**Variables liees** : G (W0_Date_comptable)

---

#### <a id="t21"></a>6.1.1.5 - Test      reseau caisse

**Role** : Verification : Test      reseau caisse.

---

#### <a id="t22"></a>6.1.1.6 - Deblocage reseau caisse

**Role** : Traitement : Deblocage reseau caisse.

---

#### <a id="t23"></a>6.1.1.7 - Test Cloture

**Role** : Verification : Test Cloture.

---

#### <a id="t24"></a>6.1.1.7.1 - Blocage Cloture v1

**Role** : Traitement : Blocage Cloture v1.

---

#### <a id="t25"></a>6.1.1.8 - Deblocage Cloture v1

**Role** : Traitement : Deblocage Cloture v1.

---

#### <a id="t29"></a>6.1.5 - Annulation

**Role** : Traitement : Annulation.

---

#### <a id="t30"></a>6.1.5.1 - Màj Excursions

**Role** : Traitement : Màj Excursions.

---

#### <a id="t31"></a>6.1.5.2 - Màj Planning

**Role** : Traitement : Màj Planning.

---

#### <a id="t32"></a>6.1.5.3 - Generation Participants

**Role** : Traitement : Generation Participants.

---

#### <a id="t34"></a>6.1.5.4.1 - Imputation

**Role** : Traitement : Imputation.

---

#### <a id="t35"></a>6.1.5.4.2 - Date caisse

**Role** : Traitement : Date caisse.
**Variables liees** : G (W0_Date_comptable)

---

#### <a id="t38"></a>6.1.5.4.5 - Màj solde

**Role** : Consultation/chargement : Màj solde.

---

#### <a id="t40"></a>6.1.5.5.1 - Imputation

**Role** : Traitement : Imputation.

---

#### <a id="t41"></a>6.1.5.5.2 - Date caisse

**Role** : Traitement : Date caisse.
**Variables liees** : G (W0_Date_comptable)

---

#### <a id="t43"></a>6.1.6 - Test      reseau caisse

**Role** : Verification : Test      reseau caisse.

---

#### <a id="t44"></a>6.1.7 - Deblocage reseau caisse

**Role** : Traitement : Deblocage reseau caisse.

---

#### <a id="t45"></a>6.1.8 - Test Cloture

**Role** : Verification : Test Cloture.

---

#### <a id="t46"></a>6.1.8.1 - Blocage Cloture v1

**Role** : Traitement : Blocage Cloture v1.

---

#### <a id="t68"></a>6.1.1.9 - Deblocage Cloture v1

**Role** : Traitement : Deblocage Cloture v1.


### 3.3 Calcul (16 taches)

Calculs metier : montants, stocks, compteurs.

---

#### <a id="t8"></a>6.1.1.1.4 - MAJ Comptable

**Role** : Traitement : MAJ Comptable.
**Variables liees** : G (W0_Date_comptable)

---

#### <a id="t11"></a>6.1.1.1.4.3 - Creation comptable v1

**Role** : Creation d'enregistrement : Creation comptable v1.
**Variables liees** : G (W0_Date_comptable)

---

#### <a id="t12"></a>6.1.1.1.4.4 - Creation comptable

**Role** : Creation d'enregistrement : Creation comptable.
**Variables liees** : G (W0_Date_comptable)

---

#### <a id="t14"></a>6.1.1.1.5 - MAJ Comptable

**Role** : Traitement : MAJ Comptable.
**Variables liees** : G (W0_Date_comptable)

---

#### <a id="t17"></a>6.1.1.1.5.3 - Creation comptable

**Role** : Creation d'enregistrement : Creation comptable.
**Variables liees** : G (W0_Date_comptable)

---

#### <a id="t20"></a>6.1.1.4 - Date comptable

**Role** : Traitement : Date comptable.
**Variables liees** : G (W0_Date_comptable)

---

#### <a id="t28"></a>6.1.4 - Date comptable

**Role** : Traitement : Date comptable.
**Variables liees** : G (W0_Date_comptable)

---

#### <a id="t33"></a>6.1.5.4 - MAJ Comptable

**Role** : Traitement : MAJ Comptable.
**Variables liees** : G (W0_Date_comptable)

---

#### <a id="t36"></a>6.1.5.4.3 - Creation comptable v1

**Role** : Creation d'enregistrement : Creation comptable v1.
**Variables liees** : G (W0_Date_comptable)

---

#### <a id="t37"></a>6.1.5.4.4 - Creation comptable

**Role** : Creation d'enregistrement : Creation comptable.
**Variables liees** : G (W0_Date_comptable)

---

#### <a id="t39"></a>6.1.5.5 - MAJ Comptable

**Role** : Traitement : MAJ Comptable.
**Variables liees** : G (W0_Date_comptable)

---

#### <a id="t42"></a>6.1.5.5.3 - Creation comptable

**Role** : Creation d'enregistrement : Creation comptable.
**Variables liees** : G (W0_Date_comptable)

---

#### <a id="t50"></a>6.1.1.1.4.6 - Creation comptable v1

**Role** : Creation d'enregistrement : Creation comptable v1.
**Variables liees** : G (W0_Date_comptable)

---

#### <a id="t56"></a>6.1.1.1.5.4 - Creation comptable

**Role** : Creation d'enregistrement : Creation comptable.
**Variables liees** : G (W0_Date_comptable)

---

#### <a id="t59"></a>6.1.5.4.6 - Creation comptable v1

**Role** : Creation d'enregistrement : Creation comptable v1.
**Variables liees** : G (W0_Date_comptable)

---

#### <a id="t62"></a>6.1.5.5.4 - Creation comptable

**Role** : Creation d'enregistrement : Creation comptable.
**Variables liees** : G (W0_Date_comptable)


### 3.4 Consultation (1 tache)

Ecrans de recherche et consultation.

---

#### <a id="t47"></a>6.2 - Recherche [[ECRAN]](#ecran-t47)

**Role** : Traitement : Recherche.
**Ecran** : 574 x 138 DLU (MDI) | [Voir mockup](#ecran-t47)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Menu general (IDE 31)](EXB-IDE-31.md)
- **Appelle**: 4 programmes | **Tables**: 16 (W:12 R:3 L:4) | **Taches**: 52 | **Expressions**: 3

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (5 / 52)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 6.1 | 6.1 | Annulation ventes excursion | MDI | 1182 | 260 | Saisie |
| 2 | 6.1.1 | 6.1.1 | Participants | MDI | 678 | 183 | Traitement |
| 3 | 6.1.1.2 | 6.1.1.2 | Annulation de vente | MDI | 630 | 150 | Saisie |
| 4 | 6.1.2 | 6.1.2 | Annulation de vente | MDI | 624 | 149 | Saisie |
| 5 | 6.2 | 6.2 | Recherche | MDI | 574 | 138 | Consultation |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t2"></a>6.1 - Annulation ventes excursion
**Tache** : [6.1](#t2) | **Type** : MDI | **Dimensions** : 1182 x 260 DLU
**Bloc** : Saisie | **Titre IDE** : Annulation ventes excursion

<!-- FORM-DATA:
{
    "width":  1182,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  5,
                         "type":  "label",
                         "var":  "",
                         "y":  1,
                         "w":  1167,
                         "fmt":  "",
                         "name":  "",
                         "h":  17,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  20,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "110",
                         "w":  1146,
                         "y":  20,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  14,
                         "h":  104,
                         "cols":  [
                                      {
                                          "title":  "Date",
                                          "layer":  1,
                                          "w":  136
                                      },
                                      {
                                          "title":  "Numéro",
                                          "layer":  2,
                                          "w":  152
                                      },
                                      {
                                          "title":  "Montant",
                                          "layer":  3,
                                          "w":  197
                                      },
                                      {
                                          "title":  "Mode",
                                          "layer":  4,
                                          "w":  85
                                      },
                                      {
                                          "title":  "Excursion",
                                          "layer":  5,
                                          "w":  216
                                      },
                                      {
                                          "title":  "Nom",
                                          "layer":  6,
                                          "w":  158
                                      },
                                      {
                                          "title":  "Prénom",
                                          "layer":  7,
                                          "w":  167
                                      }
                                  ],
                         "rows":  7
                     },
                     {
                         "x":  82,
                         "type":  "label",
                         "var":  "",
                         "y":  133,
                         "w":  251,
                         "fmt":  "",
                         "name":  "",
                         "h":  93,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  101,
                         "type":  "label",
                         "var":  "",
                         "y":  143,
                         "w":  204,
                         "fmt":  "",
                         "name":  "",
                         "h":  60,
                         "color":  "155",
                         "text":  "",
                         "parent":  20
                     },
                     {
                         "x":  103,
                         "type":  "label",
                         "var":  "",
                         "y":  144,
                         "w":  40,
                         "fmt":  "",
                         "name":  "",
                         "h":  58,
                         "color":  "",
                         "text":  "",
                         "parent":  20
                     },
                     {
                         "x":  154,
                         "type":  "label",
                         "var":  "",
                         "y":  152,
                         "w":  125,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "142",
                         "text":  "Recherche",
                         "parent":  20
                     },
                     {
                         "x":  154,
                         "type":  "label",
                         "var":  "",
                         "y":  169,
                         "w":  125,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "142",
                         "text":  "Impression",
                         "parent":  21
                     },
                     {
                         "x":  154,
                         "type":  "label",
                         "var":  "",
                         "y":  186,
                         "w":  125,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "142",
                         "text":  "Annulation",
                         "parent":  20
                     },
                     {
                         "x":  125,
                         "type":  "label",
                         "var":  "",
                         "y":  209,
                         "w":  120,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "Votre choix",
                         "parent":  20
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  236,
                         "w":  1175,
                         "fmt":  "",
                         "name":  "",
                         "h":  21,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  170,
                         "type":  "edit",
                         "var":  "",
                         "y":  37,
                         "w":  98,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  512,
                         "type":  "edit",
                         "var":  "",
                         "y":  36,
                         "w":  75,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  814,
                         "type":  "edit",
                         "var":  "",
                         "y":  37,
                         "w":  142,
                         "fmt":  "U12",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  976,
                         "type":  "edit",
                         "var":  "",
                         "y":  37,
                         "w":  98,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  26,
                         "type":  "edit",
                         "var":  "",
                         "y":  37,
                         "w":  120,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  322,
                         "type":  "edit",
                         "var":  "",
                         "y":  36,
                         "w":  176,
                         "fmt":  "N## ### ### ###.###Z",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  597,
                         "type":  "edit",
                         "var":  "",
                         "y":  37,
                         "w":  198,
                         "fmt":  "U17",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  261,
                         "type":  "edit",
                         "var":  "",
                         "y":  209,
                         "w":  26,
                         "fmt":  "",
                         "name":  "W1 choix action",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  20
                     },
                     {
                         "x":  8,
                         "type":  "edit",
                         "var":  "",
                         "y":  6,
                         "w":  267,
                         "fmt":  "20",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  961,
                         "type":  "edit",
                         "var":  "",
                         "y":  6,
                         "w":  203,
                         "fmt":  "WWW DD MMM YYYYT",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  1085,
                         "type":  "button",
                         "var":  "",
                         "y":  33,
                         "w":  31,
                         "fmt":  "...",
                         "name":  "",
                         "h":  13,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  669,
                         "type":  "image",
                         "var":  "",
                         "y":  132,
                         "w":  182,
                         "fmt":  "",
                         "name":  "",
                         "h":  92,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  113,
                         "type":  "button",
                         "var":  "",
                         "y":  152,
                         "w":  24,
                         "fmt":  "R",
                         "name":  "R",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  20
                     },
                     {
                         "x":  113,
                         "type":  "button",
                         "var":  "",
                         "y":  169,
                         "w":  24,
                         "fmt":  "I",
                         "name":  "I",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  113,
                         "type":  "button",
                         "var":  "",
                         "y":  186,
                         "w":  24,
                         "fmt":  "A",
                         "name":  "A",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  20
                     },
                     {
                         "x":  4,
                         "type":  "button",
                         "var":  "",
                         "y":  238,
                         "w":  154,
                         "fmt":  "\u0026Quitter",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  28
                     }
                 ],
    "taskId":  "6.1",
    "height":  260
}
-->

<details>
<summary><strong>Champs : 10 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 170,37 | (sans nom) | - | edit |
| 512,36 | (sans nom) | - | edit |
| 814,37 | U12 | - | edit |
| 976,37 | (sans nom) | - | edit |
| 26,37 | (sans nom) | - | edit |
| 322,36 | N## ### ### ###.###Z | - | edit |
| 597,37 | U17 | - | edit |
| 261,209 | W1 choix action | - | edit |
| 8,6 | 20 | - | edit |
| 961,6 | WWW DD MMM YYYYT | - | edit |

</details>

<details>
<summary><strong>Boutons : 5 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| ... | 1085,33 | Bouton fonctionnel |
| R | 113,152 | Bouton fonctionnel |
| I | 113,169 | Bouton fonctionnel |
| A | 113,186 | Bouton fonctionnel |
| Quitter | 4,238 | Quitte le programme |

</details>

---

#### <a id="ecran-t3"></a>6.1.1 - Participants
**Tache** : [6.1.1](#t3) | **Type** : MDI | **Dimensions** : 678 x 183 DLU
**Bloc** : Traitement | **Titre IDE** : Participants

<!-- FORM-DATA:
{
    "width":  678,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  2,
                         "w":  673,
                         "fmt":  "",
                         "name":  "",
                         "h":  17,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  30,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "110",
                         "w":  619,
                         "y":  48,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  14,
                         "h":  105,
                         "cols":  [
                                      {
                                          "title":  "Nom",
                                          "layer":  1,
                                          "w":  184
                                      },
                                      {
                                          "title":  "Prénom",
                                          "layer":  2,
                                          "w":  117
                                      },
                                      {
                                          "title":  "Montant",
                                          "layer":  3,
                                          "w":  190
                                      },
                                      {
                                          "title":  "Anuule ?",
                                          "layer":  4,
                                          "w":  91
                                      }
                                  ],
                         "rows":  4
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  157,
                         "w":  673,
                         "fmt":  "",
                         "name":  "",
                         "h":  22,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  37,
                         "type":  "edit",
                         "var":  "",
                         "y":  64,
                         "w":  176,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  222,
                         "type":  "edit",
                         "var":  "",
                         "y":  63,
                         "w":  98,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  344,
                         "type":  "edit",
                         "var":  "",
                         "y":  64,
                         "w":  176,
                         "fmt":  "N## ### ### ###.###Z",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  514,
                         "type":  "button",
                         "var":  "",
                         "y":  159,
                         "w":  154,
                         "fmt":  "\u0026\\Annulation",
                         "name":  "btn Annulation",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  14
                     },
                     {
                         "x":  3,
                         "type":  "edit",
                         "var":  "",
                         "y":  6,
                         "w":  267,
                         "fmt":  "20",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  460,
                         "type":  "edit",
                         "var":  "",
                         "y":  6,
                         "w":  203,
                         "fmt":  "WWW DD MMM YYYYT",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  34,
                         "type":  "edit",
                         "var":  "",
                         "y":  33,
                         "w":  605,
                         "fmt":  "42",
                         "name":  "",
                         "h":  13,
                         "color":  "142",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  531,
                         "type":  "edit",
                         "var":  "",
                         "y":  64,
                         "w":  75,
                         "fmt":  "6",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  3,
                         "type":  "button",
                         "var":  "",
                         "y":  159,
                         "w":  154,
                         "fmt":  "\u0026Quitter",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  14
                     }
                 ],
    "taskId":  "6.1.1",
    "height":  183
}
-->

<details>
<summary><strong>Champs : 7 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 37,64 | (sans nom) | - | edit |
| 222,63 | (sans nom) | - | edit |
| 344,64 | N## ### ### ###.###Z | - | edit |
| 3,6 | 20 | - | edit |
| 460,6 | WWW DD MMM YYYYT | - | edit |
| 34,33 | 42 | - | edit |
| 531,64 | 6 | - | edit |

</details>

<details>
<summary><strong>Boutons : 2 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| \Annulation | 514,159 | Annule et retour au menu |
| Quitter | 3,159 | Quitte le programme |

</details>

---

#### <a id="ecran-t18"></a>6.1.1.2 - Annulation de vente
**Tache** : [6.1.1.2](#t18) | **Type** : MDI | **Dimensions** : 630 x 150 DLU
**Bloc** : Saisie | **Titre IDE** : Annulation de vente

<!-- FORM-DATA:
{
    "width":  630,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  2,
                         "w":  621,
                         "fmt":  "",
                         "name":  "",
                         "h":  17,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  15,
                         "type":  "label",
                         "var":  "",
                         "y":  45,
                         "w":  104,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Paye par",
                         "parent":  null
                     },
                     {
                         "x":  35,
                         "type":  "label",
                         "var":  "",
                         "y":  63,
                         "w":  61,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Nom",
                         "parent":  null
                     },
                     {
                         "x":  35,
                         "type":  "label",
                         "var":  "",
                         "y":  77,
                         "w":  79,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Prenom",
                         "parent":  null
                     },
                     {
                         "x":  35,
                         "type":  "label",
                         "var":  "",
                         "y":  93,
                         "w":  157,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Moyen de paiement",
                         "parent":  null
                     },
                     {
                         "x":  35,
                         "type":  "label",
                         "var":  "",
                         "y":  109,
                         "w":  189,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "143",
                         "text":  "Commission Annulation",
                         "parent":  null
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  125,
                         "w":  621,
                         "fmt":  "",
                         "name":  "",
                         "h":  22,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  231,
                         "type":  "edit",
                         "var":  "",
                         "y":  92,
                         "w":  82,
                         "fmt":  "UUUUA",
                         "name":  "W_Moyen_lib",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  231,
                         "type":  "edit",
                         "var":  "",
                         "y":  108,
                         "w":  82,
                         "fmt":  "3.2 %",
                         "name":  "W_frais annualtion",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  4,
                         "type":  "button",
                         "var":  "",
                         "y":  127,
                         "w":  154,
                         "fmt":  "\u0026Ok",
                         "name":  "btn ok",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  16
                     },
                     {
                         "x":  3,
                         "type":  "edit",
                         "var":  "",
                         "y":  7,
                         "w":  267,
                         "fmt":  "20",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  408,
                         "type":  "edit",
                         "var":  "",
                         "y":  7,
                         "w":  203,
                         "fmt":  "WWW DD MMM YYYYT",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  136,
                         "type":  "edit",
                         "var":  "",
                         "y":  25,
                         "w":  350,
                         "fmt":  "30",
                         "name":  "",
                         "h":  10,
                         "color":  "142",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  199,
                         "type":  "edit",
                         "var":  "",
                         "y":  61,
                         "w":  182,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  408,
                         "type":  "edit",
                         "var":  "",
                         "y":  61,
                         "w":  75,
                         "fmt":  "6",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  501,
                         "type":  "image",
                         "var":  "",
                         "y":  72,
                         "w":  96,
                         "fmt":  "",
                         "name":  "",
                         "h":  38,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  199,
                         "type":  "edit",
                         "var":  "",
                         "y":  76,
                         "w":  104,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  165,
                         "type":  "button",
                         "var":  "",
                         "y":  127,
                         "w":  154,
                         "fmt":  "A\u0026bandonner",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "6.1.1.2",
    "height":  150
}
-->

<details>
<summary><strong>Champs : 8 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 231,92 | W_Moyen_lib | - | edit |
| 231,108 | W_frais annualtion | - | edit |
| 3,7 | 20 | - | edit |
| 408,7 | WWW DD MMM YYYYT | - | edit |
| 136,25 | 30 | - | edit |
| 199,61 | (sans nom) | - | edit |
| 408,61 | 6 | - | edit |
| 199,76 | (sans nom) | - | edit |

</details>

<details>
<summary><strong>Boutons : 2 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Ok | 4,127 | Valide la saisie et enregistre |
| Abandonner | 165,127 | Annule et retour au menu |

</details>

---

#### <a id="ecran-t26"></a>6.1.2 - Annulation de vente
**Tache** : [6.1.2](#t26) | **Type** : MDI | **Dimensions** : 624 x 149 DLU
**Bloc** : Saisie | **Titre IDE** : Annulation de vente

<!-- FORM-DATA:
{
    "width":  624,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  2,
                         "w":  621,
                         "fmt":  "",
                         "name":  "",
                         "h":  17,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  15,
                         "type":  "label",
                         "var":  "",
                         "y":  44,
                         "w":  104,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Paye par",
                         "parent":  null
                     },
                     {
                         "x":  35,
                         "type":  "label",
                         "var":  "",
                         "y":  62,
                         "w":  61,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Nom",
                         "parent":  null
                     },
                     {
                         "x":  35,
                         "type":  "label",
                         "var":  "",
                         "y":  76,
                         "w":  79,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Prenom",
                         "parent":  null
                     },
                     {
                         "x":  35,
                         "type":  "label",
                         "var":  "",
                         "y":  92,
                         "w":  157,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Moyen de paiement",
                         "parent":  null
                     },
                     {
                         "x":  34,
                         "type":  "label",
                         "var":  "",
                         "y":  108,
                         "w":  189,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "143",
                         "text":  "Commission Annulation",
                         "parent":  null
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  125,
                         "w":  621,
                         "fmt":  "",
                         "name":  "",
                         "h":  21,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  228,
                         "type":  "edit",
                         "var":  "",
                         "y":  91,
                         "w":  82,
                         "fmt":  "",
                         "name":  "W_Moyen_lib",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  227,
                         "type":  "edit",
                         "var":  "",
                         "y":  107,
                         "w":  82,
                         "fmt":  "3.2 %",
                         "name":  "W2_Comm annulation",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  4,
                         "type":  "button",
                         "var":  "",
                         "y":  127,
                         "w":  154,
                         "fmt":  "\u0026Ok",
                         "name":  "btn ok",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  16
                     },
                     {
                         "x":  3,
                         "type":  "edit",
                         "var":  "",
                         "y":  7,
                         "w":  267,
                         "fmt":  "20",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  408,
                         "type":  "edit",
                         "var":  "",
                         "y":  7,
                         "w":  203,
                         "fmt":  "WWW DD MMM YYYYT",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  136,
                         "type":  "edit",
                         "var":  "",
                         "y":  25,
                         "w":  350,
                         "fmt":  "30",
                         "name":  "",
                         "h":  10,
                         "color":  "142",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  199,
                         "type":  "edit",
                         "var":  "",
                         "y":  60,
                         "w":  182,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  408,
                         "type":  "edit",
                         "var":  "",
                         "y":  60,
                         "w":  75,
                         "fmt":  "6",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  501,
                         "type":  "image",
                         "var":  "",
                         "y":  72,
                         "w":  96,
                         "fmt":  "",
                         "name":  "",
                         "h":  38,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  199,
                         "type":  "edit",
                         "var":  "",
                         "y":  75,
                         "w":  104,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  162,
                         "type":  "button",
                         "var":  "",
                         "y":  127,
                         "w":  154,
                         "fmt":  "A\u0026bandonner",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "6.1.2",
    "height":  149
}
-->

<details>
<summary><strong>Champs : 8 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 228,91 | W_Moyen_lib | - | edit |
| 227,107 | W2_Comm annulation | - | edit |
| 3,7 | 20 | - | edit |
| 408,7 | WWW DD MMM YYYYT | - | edit |
| 136,25 | 30 | - | edit |
| 199,60 | (sans nom) | - | edit |
| 408,60 | 6 | - | edit |
| 199,75 | (sans nom) | - | edit |

</details>

<details>
<summary><strong>Boutons : 2 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Ok | 4,127 | Valide la saisie et enregistre |
| Abandonner | 162,127 | Annule et retour au menu |

</details>

---

#### <a id="ecran-t47"></a>6.2 - Recherche
**Tache** : [6.2](#t47) | **Type** : MDI | **Dimensions** : 574 x 138 DLU
**Bloc** : Consultation | **Titre IDE** : Recherche

<!-- FORM-DATA:
{
    "width":  574,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  5,
                         "type":  "label",
                         "var":  "",
                         "y":  2,
                         "w":  565,
                         "fmt":  "",
                         "name":  "",
                         "h":  17,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  299,
                         "type":  "label",
                         "var":  "",
                         "y":  37,
                         "w":  180,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "Entrez le numero :",
                         "parent":  null
                     },
                     {
                         "x":  3,
                         "type":  "label",
                         "var":  "",
                         "y":  113,
                         "w":  567,
                         "fmt":  "",
                         "name":  "",
                         "h":  21,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  328,
                         "type":  "edit",
                         "var":  "",
                         "y":  65,
                         "w":  104,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  359,
                         "type":  "edit",
                         "var":  "",
                         "y":  6,
                         "w":  203,
                         "fmt":  "WWW DD MMM YYYYT",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  41,
                         "type":  "image",
                         "var":  "",
                         "y":  38,
                         "w":  163,
                         "fmt":  "",
                         "name":  "",
                         "h":  59,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  6,
                         "type":  "button",
                         "var":  "",
                         "y":  115,
                         "w":  168,
                         "fmt":  "\u0026Quitter",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  8,
                         "type":  "edit",
                         "var":  "",
                         "y":  6,
                         "w":  267,
                         "fmt":  "20",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     }
                 ],
    "taskId":  "6.2",
    "height":  138
}
-->

<details>
<summary><strong>Champs : 3 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 328,65 | (sans nom) | - | edit |
| 359,6 | WWW DD MMM YYYYT | - | edit |
| 8,6 | 20 | - | edit |

</details>

<details>
<summary><strong>Boutons : 1 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Quitter | 6,115 | Quitte le programme |

</details>

## 9. NAVIGATION

### 9.1 Enchainement des ecrans

```mermaid
flowchart TD
    START([Entree])
    style START fill:#3fb950
    VF2[6.1 Annulation ventes e...]
    style VF2 fill:#58a6ff
    VF3[6.1.1 Participants]
    style VF3 fill:#58a6ff
    VF18[6.1.1.2 Annulation de vente]
    style VF18 fill:#58a6ff
    VF26[6.1.2 Annulation de vente]
    style VF26 fill:#58a6ff
    VF47[6.2 Recherche]
    style VF47 fill:#58a6ff
    EXT16[IDE 16 Recuperation du...]
    style EXT16 fill:#3fb950
    EXT5[IDE 5 Imp reçu annulation]
    style EXT5 fill:#3fb950
    EXT47[IDE 47 Zoom modes de p...]
    style EXT47 fill:#3fb950
    EXT17[IDE 17 Appel programme]
    style EXT17 fill:#3fb950
    FIN([Sortie])
    style FIN fill:#f85149
    START --> VF2
    VF2 -->|Recuperation donnees| EXT16
    VF2 -->|Sous-programme| EXT5
    VF2 -->|Selection/consultation| EXT47
    VF2 -->|Sous-programme| EXT17
    EXT17 --> FIN
```

**Detail par enchainement :**

| Depuis | Action | Vers | Retour |
|--------|--------|------|--------|
| Annulation ventes excursion | Recuperation donnees | [Recuperation du titre (IDE 16)](EXB-IDE-16.md) | Retour ecran |
| Annulation ventes excursion | Sous-programme | [  Imp reçu annulation (IDE 5)](EXB-IDE-5.md) | Retour ecran |
| Annulation ventes excursion | Selection/consultation | [Zoom modes de paiement (IDE 47)](EXB-IDE-47.md) | Retour ecran |
| Annulation ventes excursion | Sous-programme | [Appel programme (IDE 17)](EXB-IDE-17.md) | Retour ecran |

### 9.3 Structure hierarchique (52 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **6.1** | [**Ventes** (6)](#t1) [mockup](#ecran-t1) | MDI | 216x20 | Saisie |
| 6.1.1 | [Annulation ventes excursion (6.1)](#t2) [mockup](#ecran-t2) | MDI | 1182x260 | |
| 6.1.2 | [Annulation de vente (6.1.1.2)](#t18) [mockup](#ecran-t18) | MDI | 630x150 | |
| 6.1.3 | [Compteur vente (6.1.1.3)](#t19) | MDI | - | |
| 6.1.4 | [Annulation de vente (6.1.2)](#t26) [mockup](#ecran-t26) | MDI | 624x149 | |
| 6.1.5 | [Compteur vente (6.1.3)](#t27) | MDI | - | |
| **6.2** | [**Participants** (6.1.1)](#t3) [mockup](#ecran-t3) | MDI | 678x183 | Traitement |
| 6.2.1 | [Annulation (6.1.1.1)](#t4) | MDI | - | |
| 6.2.2 | [Màj Excursions (6.1.1.1.1)](#t5) | MDI | - | |
| 6.2.3 | [Màj Planning (6.1.1.1.2)](#t6) | MDI | - | |
| 6.2.4 | [Generation Participants (6.1.1.1.3)](#t7) | MDI | - | |
| 6.2.5 | [Imputation (6.1.1.1.4.1)](#t9) | MDI | - | |
| 6.2.6 | [Date caisse (6.1.1.1.4.2)](#t10) | MDI | - | |
| 6.2.7 | [Màj solde (6.1.1.1.4.5)](#t13) | MDI | - | |
| 6.2.8 | [Imputation (6.1.1.1.5.1)](#t15) | MDI | - | |
| 6.2.9 | [Date caisse (6.1.1.1.5.2)](#t16) | MDI | - | |
| 6.2.10 | [Test      reseau caisse (6.1.1.5)](#t21) | MDI | - | |
| 6.2.11 | [Deblocage reseau caisse (6.1.1.6)](#t22) | MDI | - | |
| 6.2.12 | [Test Cloture (6.1.1.7)](#t23) | MDI | - | |
| 6.2.13 | [Blocage Cloture v1 (6.1.1.7.1)](#t24) | MDI | - | |
| 6.2.14 | [Deblocage Cloture v1 (6.1.1.8)](#t25) | MDI | - | |
| 6.2.15 | [Annulation (6.1.5)](#t29) | MDI | - | |
| 6.2.16 | [Màj Excursions (6.1.5.1)](#t30) | MDI | - | |
| 6.2.17 | [Màj Planning (6.1.5.2)](#t31) | MDI | - | |
| 6.2.18 | [Generation Participants (6.1.5.3)](#t32) | MDI | - | |
| 6.2.19 | [Imputation (6.1.5.4.1)](#t34) | MDI | - | |
| 6.2.20 | [Date caisse (6.1.5.4.2)](#t35) | MDI | - | |
| 6.2.21 | [Màj solde (6.1.5.4.5)](#t38) | MDI | - | |
| 6.2.22 | [Imputation (6.1.5.5.1)](#t40) | MDI | - | |
| 6.2.23 | [Date caisse (6.1.5.5.2)](#t41) | MDI | - | |
| 6.2.24 | [Test      reseau caisse (6.1.6)](#t43) | MDI | - | |
| 6.2.25 | [Deblocage reseau caisse (6.1.7)](#t44) | MDI | - | |
| 6.2.26 | [Test Cloture (6.1.8)](#t45) | MDI | - | |
| 6.2.27 | [Blocage Cloture v1 (6.1.8.1)](#t46) | MDI | - | |
| 6.2.28 | [Deblocage Cloture v1 (6.1.1.9)](#t68) | MDI | - | |
| **6.3** | [**MAJ Comptable** (6.1.1.1.4)](#t8) | MDI | - | Calcul |
| 6.3.1 | [Creation comptable v1 (6.1.1.1.4.3)](#t11) | MDI | - | |
| 6.3.2 | [Creation comptable (6.1.1.1.4.4)](#t12) | MDI | - | |
| 6.3.3 | [MAJ Comptable (6.1.1.1.5)](#t14) | MDI | - | |
| 6.3.4 | [Creation comptable (6.1.1.1.5.3)](#t17) | MDI | - | |
| 6.3.5 | [Date comptable (6.1.1.4)](#t20) | MDI | - | |
| 6.3.6 | [Date comptable (6.1.4)](#t28) | MDI | - | |
| 6.3.7 | [MAJ Comptable (6.1.5.4)](#t33) | MDI | - | |
| 6.3.8 | [Creation comptable v1 (6.1.5.4.3)](#t36) | MDI | - | |
| 6.3.9 | [Creation comptable (6.1.5.4.4)](#t37) | MDI | - | |
| 6.3.10 | [MAJ Comptable (6.1.5.5)](#t39) | MDI | - | |
| 6.3.11 | [Creation comptable (6.1.5.5.3)](#t42) | MDI | - | |
| 6.3.12 | [Creation comptable v1 (6.1.1.1.4.6)](#t50) | MDI | - | |
| 6.3.13 | [Creation comptable (6.1.1.1.5.4)](#t56) | MDI | - | |
| 6.3.14 | [Creation comptable v1 (6.1.5.4.6)](#t59) | MDI | - | |
| 6.3.15 | [Creation comptable (6.1.5.5.4)](#t62) | MDI | - | |
| **6.4** | [**Recherche** (6.2)](#t47) [mockup](#ecran-t47) | MDI | 574x138 | Consultation |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Scroll]
    UPDATE[MAJ 12 tables]
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

### Tables utilisees (16)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 23 | reseau_cloture___rec | Donnees reseau/cloture | DB |   | **W** |   | 6 |
| 40 | comptable________cte |  | DB |   | **W** |   | 4 |
| 47 | compte_gm________cgm | Comptes GM (generaux) | DB |   | **W** |   | 6 |
| 70 | date_comptable___dat |  | DB | R | **W** |   | 4 |
| 77 | articles_________art | Articles et stock | DB | R |   |   | 4 |
| 89 | moyen_paiement___mop |  | DB |   |   | L | 1 |
| 173 | intermed_compta__ite |  | DB |   | **W** |   | 2 |
| 263 | vente | Donnees de ventes | DB |   | **W** |   | 4 |
| 278 | commission |  | DB |   |   | L | 1 |
| 292 | compteur_excurs__cte | Comptes GM (generaux) | DB |   | **W** |   | 2 |
| 293 | date_comptable___dat |  | DB | R | **W** |   | 2 |
| 298 | participants_____par |  | DB |   | **W** |   | 3 |
| 299 | excurs_planning__epl |  | DB |   | **W** |   | 2 |
| 300 | excursions_______exc |  | DB |   | **W** | L | 3 |
| 309 | vente____________vep | Donnees de ventes | DB |   | **W** |   | 3 |
| 331 | reseau_cloture___rcg | Donnees reseau/cloture | DB |   |   | L | 2 |

### Colonnes par table (13 / 13 tables avec colonnes identifiees)

<details>
<summary>Table 23 - reseau_cloture___rec (**W**) - 6 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | Retour Cloture Caisse | W | Logical |
| B | Retour Cloture Excursion | W | Logical |

</details>

<details>
<summary>Table 40 - comptable________cte (**W**) - 4 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| G | W0_Date_comptable | W | Date |

</details>

<details>
<summary>Table 47 - compte_gm________cgm (**W**) - 6 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| H | W0_Compteur | W | Numeric |

</details>

<details>
<summary>Table 70 - date_comptable___dat (R/**W**) - 4 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| D | W_Date_caisse | W | Date |
| G | W0_Date_comptable | W | Date |

</details>

<details>
<summary>Table 77 - articles_________art (R) - 4 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 173 - intermed_compta__ite (**W**) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| G | W0_Date_comptable | W | Date |

</details>

<details>
<summary>Table 263 - vente (**W**) - 4 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| F | W0 n° vente | W | Numeric |

</details>

<details>
<summary>Table 292 - compteur_excurs__cte (**W**) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| B | Retour Cloture Excursion | W | Logical |
| H | W0_Compteur | W | Numeric |

</details>

<details>
<summary>Table 293 - date_comptable___dat (R/**W**) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| D | W_Date_caisse | W | Date |
| G | W0_Date_comptable | W | Date |

</details>

<details>
<summary>Table 298 - participants_____par (**W**) - 3 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | W_Action | W | Alpha |
| B | btn Annulation | W | Alpha |
| C | W creation | W | Logical |
| D | v. titre | W | Alpha |
| E | W. Cloture | W | Logical |
| F | W cloture caisse | W | Logical |

</details>

<details>
<summary>Table 299 - excurs_planning__epl (**W**) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| B | Retour Cloture Excursion | W | Logical |

</details>

<details>
<summary>Table 300 - excursions_______exc (**W**/L) - 3 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 309 - vente____________vep (**W**) - 3 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | W1 choix action | W | Alpha |
| B | W1_Comm Annulation | W | Numeric |
| C | W1_Blocage_caisse | W | Alpha |
| D | W1_Confirmation | W | Alpha |
| E | W1 fin tâche | W | Alpha |
| F | W creation ? | W | Logical |
| G | v. titre scroll | W | Alpha |
| H | W Cloture | W | Logical |
| I | W cloture caisse | W | Logical |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (4)

Variables recues du programme appelant ([Menu general (IDE 31)](EXB-IDE-31.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P0 nom village | Alpha | - |
| B | P0 masque montant | Alpha | - |
| C | P0 devise | Alpha | - |
| D | P0 nbre decimales | Numeric | - |

### 11.2 Variables de travail (3)

Variables internes au programme.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| E | W0 choix action | Alpha | 3x calcul interne |
| F | W0 n° vente | Numeric | - |
| I | W0 voucher ? | Alpha | - |

### 11.3 Autres (2)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| G | W0_Date_comptable | Date | - |
| H | W0_Compteur | Numeric | - |

## 12. EXPRESSIONS

**3 / 3 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONDITION | 3 | 0 |

### 12.2 Expressions cles par type

#### CONDITION (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 3 | `W0 choix action [E]='I'` | - |
| CONDITION | 2 | `W0 choix action [E]='R'` | - |
| CONDITION | 1 | `W0 choix action [E]='F'` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Menu general (IDE 31)](EXB-IDE-31.md) -> **Annulation Ventes@ (IDE 6)**

```mermaid
graph LR
    T6[6 Annulation Ventes@]
    style T6 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC31[31 Menu general]
    style CC31 fill:#3fb950
    CC1 --> CC31
    CC31 --> T6
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [31](EXB-IDE-31.md) | Menu general | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T6[6 Annulation Ventes@]
    style T6 fill:#58a6ff
    C16[16 Recuperation du titre]
    T6 --> C16
    style C16 fill:#3fb950
    C5[5 Imp reçu annulation]
    T6 --> C5
    style C5 fill:#3fb950
    C47[47 Zoom modes de paiement]
    T6 --> C47
    style C47 fill:#3fb950
    C17[17 Appel programme]
    T6 --> C17
    style C17 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [16](EXB-IDE-16.md) | Recuperation du titre | 5 | Recuperation donnees |
| [5](EXB-IDE-5.md) |   Imp reçu annulation | 3 | Sous-programme |
| [47](EXB-IDE-47.md) | Zoom modes de paiement | 2 | Selection/consultation |
| [17](EXB-IDE-17.md) | Appel programme | 1 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 1099 | Programme volumineux |
| Expressions | 3 | Peu de logique |
| Tables WRITE | 12 | Fort impact donnees |
| Sous-programmes | 4 | Peu de dependances |
| Ecrans visibles | 5 | Quelques ecrans |
| Code desactive | 0% (0 / 1099) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Saisie (6 taches: 4 ecrans, 2 traitements)

- **Strategie** : Formulaire React/Blazor avec validation Zod/FluentValidation.
- Reproduire 4 ecrans : Ventes, Annulation ventes excursion, Annulation de vente, Annulation de vente
- Validation temps reel cote client + serveur

#### Traitement (29 taches: 1 ecran, 28 traitements)

- **Strategie** : Orchestrateur avec 1 ecrans (Razor/React) et 28 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 4 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Calcul (16 taches: 0 ecran, 16 traitements)

- **Strategie** : Services de calcul purs (Domain Services).
- Migrer la logique de calcul (stock, compteurs, montants)

#### Consultation (1 tache: 1 ecran, 0 traitement)

- **Strategie** : Composants de recherche/selection en modales.
- 1 ecran : Recherche

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| reseau_cloture___rec | Table WRITE (Database) | 6x | Schema + repository |
| comptable________cte | Table WRITE (Database) | 4x | Schema + repository |
| compte_gm________cgm | Table WRITE (Database) | 6x | Schema + repository |
| date_comptable___dat | Table WRITE (Database) | 2x | Schema + repository |
| intermed_compta__ite | Table WRITE (Database) | 2x | Schema + repository |
| vente | Table WRITE (Database) | 4x | Schema + repository |
| compteur_excurs__cte | Table WRITE (Database) | 2x | Schema + repository |
| date_comptable___dat | Table WRITE (Database) | 1x | Schema + repository |
| participants_____par | Table WRITE (Database) | 3x | Schema + repository |
| excurs_planning__epl | Table WRITE (Database) | 2x | Schema + repository |
| excursions_______exc | Table WRITE (Database) | 2x | Schema + repository |
| vente____________vep | Table WRITE (Database) | 3x | Schema + repository |
| [Recuperation du titre (IDE 16)](EXB-IDE-16.md) | Sous-programme | 5x | **CRITIQUE** - Recuperation donnees |
| [  Imp reçu annulation (IDE 5)](EXB-IDE-5.md) | Sous-programme | 3x | **CRITIQUE** - Sous-programme |
| [Zoom modes de paiement (IDE 47)](EXB-IDE-47.md) | Sous-programme | 2x | Haute - Selection/consultation |
| [Appel programme (IDE 17)](EXB-IDE-17.md) | Sous-programme | 1x | Normale - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 10:30*
