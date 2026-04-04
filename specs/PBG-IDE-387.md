# PBG IDE 387 - Creation clients Identite_sav

> **Analyse**: Phases 1-4 2026-02-03 11:36 -> 11:36 (18s) | Assemblage 11:36
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBG |
| IDE Position | 387 |
| Nom Programme | Creation clients Identite_sav |
| Fichier source | `Prg_387.xml` |
| Dossier IDE | General |
| Taches | 25 (4 ecrans visibles) |
| Tables modifiees | 8 |
| Programmes appeles | 17 |
| :warning: Statut | **ORPHELIN_POTENTIEL** |

## 2. DESCRIPTION FONCTIONNELLE

**Creation clients Identite_sav** assure la gestion complete de ce processus.

Le flux de traitement s'organise en **6 blocs fonctionnels** :

- **Traitement** (13 taches) : traitements metier divers
- **Calcul** (4 taches) : calculs de montants, stocks ou compteurs
- **Creation** (4 taches) : insertion d'enregistrements en base (mouvements, prestations)
- **Validation** (2 taches) : controles et verifications de coherence
- **Initialisation** (1 tache) : reinitialisation d'etats et de variables de travail
- **Consultation** (1 tache) : ecrans de recherche, selection et consultation

**Donnees modifiees** : 8 tables en ecriture (gm-recherche_____gmr, gm-complet_______gmc, compte_gm________cgm, compteurs________cpt, historik_station, groupe_arr_dep___vol, heb_circuit______hci, import_mod).

**Logique metier** : 2 regles identifiees couvrant conditions metier, valeurs par defaut.

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (13 taches)

- **387** - Module des Clients
- **387.1** - Determination Age Bebe
- **387.2.1** - Modification Hebergement
- **387.2.3** - Demarquage Caisse
- **387.2.6** - personne existante **[[ECRAN]](#ecran-t10)**
- **387.2.7** - determination periode
- **387.2.8** - Reiteration **[[ECRAN]](#ecran-t12)**
- **387.2.8.1** - Clients **[[ECRAN]](#ecran-t13)**
- **387.2.8.1.1** - Modification Hebergement
- **387.2.8.1.3** - recup filiation club
- **387.2.8.1.4** - recup filiation
- **387.2.9** - MAJ immigration **[[ECRAN]](#ecran-t21)**
- **387.2.10** - Clients **[[ECRAN]](#ecran-t22)**

Delegue a : [Redirection touches (IDE 309)](PBG-IDE-309.md), [Determination Age Debut Sejour (IDE 312)](PBG-IDE-312.md), [Recuperation du titre (IDE 317)](PBG-IDE-317.md), [   Delete GMR cpte=0 (IDE 84)](PBG-IDE-84.md), [   Delete GMR adh=0 (IDE 85)](PBG-IDE-85.md), [  Maj Passport (IDE 90)](PBG-IDE-90.md), [Langue ? (IDE 311)](PBG-IDE-311.md), [Caractères Interdits (A20) - L (IDE 313)](PBG-IDE-313.md), [Caractères Interdits (A20) - A (IDE 314)](PBG-IDE-314.md)

#### Phase 2 : Creation (4 taches)

- **387.2** - Creation client **[[ECRAN]](#ecran-t4)**
- **387.2.2** - Creation Historique
- **387.2.4** - creation V/V
- **387.2.8.1.2** - Creation Historique

Delegue a : [   Creation Fidelisation (IDE 72)](PBG-IDE-72.md), [Create TAI GM (IDE 97)](PBG-IDE-97.md)

#### Phase 3 : Validation (2 taches)

- **387.2.5** - Verification Algorythme
- **387.2.13** - verif logements

Delegue a : [Caractères Interdits (A20) - L (IDE 313)](PBG-IDE-313.md), [Caractères Interdits (A20) - A (IDE 314)](PBG-IDE-314.md), [Verification Aut sans ecran (IDE 320)](PBG-IDE-320.md)

#### Phase 4 : Calcul (4 taches)

- **387.2.8.1.5** - Calcul flag
- **387.2.8.1.6** - Calcul Millesia
- **387.2.12** - Mise a jour compteur
- **387.2.14** - Calcul Millesia

#### Phase 5 : Consultation (1 tache)

- **387.2.11** - Modif recherche

Delegue a : [Zoom VOL (IDE 359)](PBG-IDE-359.md), [Recuperation du titre (IDE 317)](PBG-IDE-317.md), [Zoom inscription (IDE 354)](PBG-IDE-354.md), [Zoom logement (IDE 357)](PBG-IDE-357.md), [Zoom Qualite(C/P) (IDE 366)](PBG-IDE-366.md), [Zoom langue (IDE 355)](PBG-IDE-355.md)

#### Phase 6 : Initialisation (1 tache)

- **387.3** - Initialisation paramètres

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| gm-recherche_____gmr | R/**W**/L (4 usages) | Index de recherche |
| gm-complet_______gmc | **W** (3 usages) |  |
| historik_station | **W** (2 usages) | Historique / journal |
| import_mod | **W** (2 usages) |  |
| compte_gm________cgm | **W**/L (2 usages) | Comptes GM (generaux) |
| groupe_arr_dep___vol | **W**/L (2 usages) |  |
| compteurs________cpt | **W**/L (2 usages) | Comptes GM (generaux) |
| heb_circuit______hci | **W** (2 usages) | Hebergement (chambres) |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (13 taches)

Traitements internes.

---

#### <a id="t1"></a>387 - Module des Clients

**Role** : Tache d'orchestration : point d'entree du programme (13 sous-taches). Coordonne l'enchainement des traitements.

<details>
<summary>12 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [387.1](#t2) | Determination Age Bebe | Traitement |
| [387.2.1](#t5) | Modification Hebergement | Traitement |
| [387.2.3](#t7) | Demarquage Caisse | Traitement |
| [387.2.6](#t10) | personne existante **[[ECRAN]](#ecran-t10)** | Traitement |
| [387.2.7](#t11) | determination periode | Traitement |
| [387.2.8](#t12) | Reiteration **[[ECRAN]](#ecran-t12)** | Traitement |
| [387.2.8.1](#t13) | Clients **[[ECRAN]](#ecran-t13)** | Traitement |
| [387.2.8.1.1](#t14) | Modification Hebergement | Traitement |
| [387.2.8.1.3](#t17) | recup filiation club | Traitement |
| [387.2.8.1.4](#t18) | recup filiation | Traitement |
| [387.2.9](#t21) | MAJ immigration **[[ECRAN]](#ecran-t21)** | Traitement |
| [387.2.10](#t22) | Clients **[[ECRAN]](#ecran-t22)** | Traitement |

</details>

---

#### <a id="t2"></a>387.1 - Determination Age Bebe

**Role** : Traitement : Determination Age Bebe.
**Variables liees** : L (W0-Age Bebe)

---

#### <a id="t5"></a>387.2.1 - Modification Hebergement

**Role** : Traitement : Modification Hebergement.
**Variables liees** : CK (v. Hebergement)

---

#### <a id="t7"></a>387.2.3 - Demarquage Caisse

**Role** : Traitement : Demarquage Caisse.

---

#### <a id="t10"></a>387.2.6 - personne existante [[ECRAN]](#ecran-t10)

**Role** : Traitement : personne existante.
**Ecran** : 776 x 145 DLU (MDI) | [Voir mockup](#ecran-t10)

---

#### <a id="t11"></a>387.2.7 - determination periode

**Role** : Traitement : determination periode.

---

#### <a id="t12"></a>387.2.8 - Reiteration [[ECRAN]](#ecran-t12)

**Role** : Traitement : Reiteration.
**Ecran** : 706 x 147 DLU (MDI) | [Voir mockup](#ecran-t12)

---

#### <a id="t13"></a>387.2.8.1 - Clients [[ECRAN]](#ecran-t13)

**Role** : Traitement : Clients.
**Ecran** : 710 x 150 DLU (MDI) | [Voir mockup](#ecran-t13)

---

#### <a id="t14"></a>387.2.8.1.1 - Modification Hebergement

**Role** : Traitement : Modification Hebergement.
**Variables liees** : CK (v. Hebergement)

---

#### <a id="t17"></a>387.2.8.1.3 - recup filiation club

**Role** : Consultation/chargement : recup filiation club.
**Variables liees** : Z (W0 filiation club1), BA (W0 filiation club2), CO (v. ok filiation), C (>Filiation Compte), J (W0-Filiation)

---

#### <a id="t18"></a>387.2.8.1.4 - recup filiation

**Role** : Consultation/chargement : recup filiation.
**Variables liees** : Z (W0 filiation club1), BA (W0 filiation club2), CO (v. ok filiation), C (>Filiation Compte), J (W0-Filiation)

---

#### <a id="t21"></a>387.2.9 - MAJ immigration [[ECRAN]](#ecran-t21)

**Role** : Traitement : MAJ immigration.
**Ecran** : 638 x 168 DLU (MDI) | [Voir mockup](#ecran-t21)

---

#### <a id="t22"></a>387.2.10 - Clients [[ECRAN]](#ecran-t22)

**Role** : Traitement : Clients.
**Ecran** : 216 x 52 DLU (MDI) | [Voir mockup](#ecran-t22)


### 3.2 Creation (4 taches)

Insertion de nouveaux enregistrements en base.

---

#### <a id="t4"></a>387.2 - Creation client [[ECRAN]](#ecran-t4)

**Role** : Creation d'enregistrement : Creation client.
**Ecran** : 920 x 311 DLU (MDI) | [Voir mockup](#ecran-t4)
**Variables liees** : H (W0-Type Client), O (W0-autorisation creation)
**Delegue a** : [   Creation Fidelisation (IDE 72)](PBG-IDE-72.md), [Create TAI GM (IDE 97)](PBG-IDE-97.md)

---

#### <a id="t6"></a>387.2.2 - Creation Historique

**Role** : Consultation/chargement : Creation Historique.
**Variables liees** : O (W0-autorisation creation)
**Delegue a** : [   Creation Fidelisation (IDE 72)](PBG-IDE-72.md), [Create TAI GM (IDE 97)](PBG-IDE-97.md)

---

#### <a id="t8"></a>387.2.4 - creation V/V

**Role** : Creation d'enregistrement : creation V/V.
**Variables liees** : O (W0-autorisation creation)
**Delegue a** : [   Creation Fidelisation (IDE 72)](PBG-IDE-72.md), [Create TAI GM (IDE 97)](PBG-IDE-97.md)

---

#### <a id="t15"></a>387.2.8.1.2 - Creation Historique

**Role** : Consultation/chargement : Creation Historique.
**Variables liees** : O (W0-autorisation creation)
**Delegue a** : [   Creation Fidelisation (IDE 72)](PBG-IDE-72.md), [Create TAI GM (IDE 97)](PBG-IDE-97.md)


### 3.3 Validation (2 taches)

Controles de coherence : 2 taches verifient les donnees et conditions.

---

#### <a id="t9"></a>387.2.5 - Verification Algorythme

**Role** : Verification : Verification Algorythme.
**Delegue a** : [Verification Aut sans ecran (IDE 320)](PBG-IDE-320.md)

---

#### <a id="t25"></a>387.2.13 - verif logements

**Role** : Verification : verif logements.
**Delegue a** : [Verification Aut sans ecran (IDE 320)](PBG-IDE-320.md)


### 3.4 Calcul (4 taches)

Calculs metier : montants, stocks, compteurs.

---

#### <a id="t19"></a>387.2.8.1.5 - Calcul flag

**Role** : Calcul : Calcul flag.

---

#### <a id="t20"></a>387.2.8.1.6 - Calcul Millesia

**Role** : Calcul : Calcul Millesia.

---

#### <a id="t24"></a>387.2.12 - Mise a jour compteur

**Role** : Calcul : Mise a jour compteur.
**Variables liees** : V (W0-lieu sejour general), W (W0-compteur lieu), X (W0-lieu sejour), BT (W1-lieu sejour), BU (W1-select lieu sejour)

---

#### <a id="t26"></a>387.2.14 - Calcul Millesia

**Role** : Calcul : Calcul Millesia.


### 3.5 Consultation (1 tache)

Ecrans de recherche et consultation.

---

#### <a id="t23"></a>387.2.11 - Modif recherche

**Role** : Traitement : Modif recherche.
**Variables liees** : BB (W0 modif langue), P (W0- autorisation modif)
**Delegue a** : [Zoom VOL (IDE 359)](PBG-IDE-359.md), [Zoom inscription (IDE 354)](PBG-IDE-354.md), [Zoom logement (IDE 357)](PBG-IDE-357.md)


### 3.6 Initialisation (1 tache)

Reinitialisation d'etats et variables de travail.

---

#### <a id="t27"></a>387.3 - Initialisation paramètres

**Role** : Reinitialisation : Initialisation paramètres.


## 5. REGLES METIER

2 regles identifiees:

### Autres (2 regles)

#### <a id="rm-RM-001"></a>[RM-001] Traitement conditionnel si GetParam ('NB_LIEU_SEJOUR') est a zero

| Element | Detail |
|---------|--------|
| **Condition** | `GetParam ('NB_LIEU_SEJOUR')=0` |
| **Si vrai** | 'G' |
| **Si faux** | IF (GetParam ('NB_LIEU_SEJOUR')=1,GetParam ('CODE_LIEU_SEJOUR'),'')) |
| **Expression source** | Expression 1 : `IF (GetParam ('NB_LIEU_SEJOUR')=0,'G',IF (GetParam ('NB_LIEU` |
| **Exemple** | Si GetParam ('NB_LIEU_SEJOUR')=0 â†’ 'G' |

#### <a id="rm-RM-002"></a>[RM-002] Valeur par defaut si > Mode attaque ecran [A] est vide

| Element | Detail |
|---------|--------|
| **Condition** | `> Mode attaque ecran [A]=''` |
| **Si vrai** | 'E'MODE |
| **Si faux** | > Mode attaque ecran [A]) |
| **Variables** | A (> Mode attaque ecran) |
| **Expression source** | Expression 6 : `IF (> Mode attaque ecran [A]='','E'MODE,> Mode attaque ecran` |
| **Exemple** | Si > Mode attaque ecran [A]='' â†’ 'E'MODE. Sinon â†’ > Mode attaque ecran [A]) |

## 6. CONTEXTE

- **Appele par**: (aucun)
- **Appelle**: 17 programmes | **Tables**: 22 (W:8 R:6 L:17) | **Taches**: 25 | **Expressions**: 17

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (4 / 25)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 387.2 | 387.2 | Creation client | MDI | 920 | 311 | Creation |
| 2 | 387.2.6 | 387.2.6 | personne existante | MDI | 776 | 145 | Traitement |
| 3 | 387.2.8.1 | 387.2.8.1 | Clients | MDI | 710 | 150 | Traitement |
| 4 | 387.2.9 | 387.2.9 | MAJ immigration | MDI | 638 | 168 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t4"></a>387.2 - Creation client
**Tache** : [387.2](#t4) | **Type** : MDI | **Dimensions** : 920 x 311 DLU
**Bloc** : Creation | **Titre IDE** : Creation client

<!-- FORM-DATA:
{
    "width":  920,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  913,
                         "fmt":  "",
                         "name":  "",
                         "h":  21,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  30,
                         "type":  "label",
                         "var":  "",
                         "y":  24,
                         "w":  854,
                         "fmt":  "",
                         "name":  "",
                         "h":  206,
                         "color":  "1",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  48,
                         "type":  "label",
                         "var":  "",
                         "y":  31,
                         "w":  85,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Nom",
                         "parent":  4
                     },
                     {
                         "x":  373,
                         "type":  "label",
                         "var":  "",
                         "y":  31,
                         "w":  89,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Prénom",
                         "parent":  4
                     },
                     {
                         "x":  612,
                         "type":  "label",
                         "var":  "",
                         "y":  31,
                         "w":  42,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Titre",
                         "parent":  4
                     },
                     {
                         "x":  48,
                         "type":  "label",
                         "var":  "",
                         "y":  47,
                         "w":  61,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Qualité",
                         "parent":  4
                     },
                     {
                         "x":  48,
                         "type":  "label",
                         "var":  "",
                         "y":  63,
                         "w":  106,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Honey Moon",
                         "parent":  4
                     },
                     {
                         "x":  357,
                         "type":  "label",
                         "var":  "",
                         "y":  63,
                         "w":  53,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Fleurs",
                         "parent":  4
                     },
                     {
                         "x":  46,
                         "type":  "label",
                         "var":  "",
                         "y":  79,
                         "w":  62,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Fidel.",
                         "parent":  4
                     },
                     {
                         "x":  357,
                         "type":  "label",
                         "var":  "",
                         "y":  79,
                         "w":  107,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Type Fidel.",
                         "parent":  4
                     },
                     {
                         "x":  48,
                         "type":  "label",
                         "var":  "",
                         "y":  95,
                         "w":  104,
                         "fmt":  "",
                         "name":  "",
                         "h":  11,
                         "color":  "",
                         "text":  "Date Début",
                         "parent":  4
                     },
                     {
                         "x":  380,
                         "type":  "label",
                         "var":  "",
                         "y":  95,
                         "w":  109,
                         "fmt":  "",
                         "name":  "",
                         "h":  11,
                         "color":  "",
                         "text":  "Vol aller",
                         "parent":  4
                     },
                     {
                         "x":  48,
                         "type":  "label",
                         "var":  "",
                         "y":  112,
                         "w":  96,
                         "fmt":  "",
                         "name":  "",
                         "h":  11,
                         "color":  "",
                         "text":  "Date Fin",
                         "parent":  4
                     },
                     {
                         "x":  380,
                         "type":  "label",
                         "var":  "",
                         "y":  112,
                         "w":  117,
                         "fmt":  "",
                         "name":  "",
                         "h":  11,
                         "color":  "",
                         "text":  "Vol retour",
                         "parent":  4
                     },
                     {
                         "x":  48,
                         "type":  "label",
                         "var":  "",
                         "y":  129,
                         "w":  96,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "N° Adhérent",
                         "parent":  4
                     },
                     {
                         "x":  315,
                         "type":  "label",
                         "var":  "",
                         "y":  129,
                         "w":  69,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Filiation",
                         "parent":  4
                     },
                     {
                         "x":  442,
                         "type":  "label",
                         "var":  "",
                         "y":  129,
                         "w":  94,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Date Naiss",
                         "parent":  4
                     },
                     {
                         "x":  693,
                         "type":  "label",
                         "var":  "",
                         "y":  129,
                         "w":  38,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Age",
                         "parent":  4
                     },
                     {
                         "x":  48,
                         "type":  "label",
                         "var":  "",
                         "y":  145,
                         "w":  85,
                         "fmt":  "",
                         "name":  "",
                         "h":  11,
                         "color":  "",
                         "text":  "Inscription",
                         "parent":  4
                     },
                     {
                         "x":  48,
                         "type":  "label",
                         "var":  "",
                         "y":  162,
                         "w":  83,
                         "fmt":  "",
                         "name":  "",
                         "h":  11,
                         "color":  "",
                         "text":  "Fumeur",
                         "parent":  4
                     },
                     {
                         "x":  48,
                         "type":  "label",
                         "var":  "",
                         "y":  179,
                         "w":  100,
                         "fmt":  "",
                         "name":  "",
                         "h":  11,
                         "color":  "",
                         "text":  "Lieu séjour",
                         "parent":  4
                     },
                     {
                         "x":  425,
                         "type":  "label",
                         "var":  "",
                         "y":  179,
                         "w":  115,
                         "fmt":  "",
                         "name":  "",
                         "h":  11,
                         "color":  "",
                         "text":  "Logement",
                         "parent":  4
                     },
                     {
                         "x":  425,
                         "type":  "label",
                         "var":  "",
                         "y":  196,
                         "w":  83,
                         "fmt":  "",
                         "name":  "",
                         "h":  11,
                         "color":  "",
                         "text":  "Base Occ",
                         "parent":  4
                     },
                     {
                         "x":  48,
                         "type":  "label",
                         "var":  "",
                         "y":  196,
                         "w":  106,
                         "fmt":  "",
                         "name":  "",
                         "h":  11,
                         "color":  "",
                         "text":  "Occup (U/P)",
                         "parent":  4
                     },
                     {
                         "x":  48,
                         "type":  "label",
                         "var":  "",
                         "y":  216,
                         "w":  90,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Langue",
                         "parent":  4
                     },
                     {
                         "x":  30,
                         "type":  "label",
                         "var":  "",
                         "y":  237,
                         "w":  611,
                         "fmt":  "",
                         "name":  "",
                         "h":  45,
                         "color":  "195",
                         "text":  "Adresse",
                         "parent":  null
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  286,
                         "w":  914,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  33,
                         "type":  "line",
                         "var":  "",
                         "y":  211,
                         "w":  850,
                         "fmt":  "",
                         "name":  "",
                         "h":  0,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  33,
                         "type":  "line",
                         "var":  "",
                         "y":  57,
                         "w":  850,
                         "fmt":  "",
                         "name":  "",
                         "h":  0,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  33,
                         "type":  "line",
                         "var":  "",
                         "y":  92,
                         "w":  850,
                         "fmt":  "",
                         "name":  "",
                         "h":  0,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  33,
                         "type":  "line",
                         "var":  "",
                         "y":  123,
                         "w":  850,
                         "fmt":  "",
                         "name":  "",
                         "h":  0,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  33,
                         "type":  "line",
                         "var":  "",
                         "y":  156,
                         "w":  850,
                         "fmt":  "",
                         "name":  "",
                         "h":  0,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  156,
                         "type":  "edit",
                         "var":  "",
                         "y":  31,
                         "w":  182,
                         "fmt":  "",
                         "name":  "CLI Nom",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  466,
                         "type":  "edit",
                         "var":  "",
                         "y":  31,
                         "w":  126,
                         "fmt":  "",
                         "name":  "CLI Prenom",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  660,
                         "type":  "combobox",
                         "var":  "",
                         "y":  31,
                         "w":  191,
                         "fmt":  "",
                         "name":  "W1-select titre",
                         "h":  10,
                         "color":  "110",
                         "text":  "1,2",
                         "parent":  4
                     },
                     {
                         "x":  339,
                         "type":  "button",
                         "var":  "",
                         "y":  47,
                         "w":  27,
                         "fmt":  "...",
                         "name":  "v. bouton qualite",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  156,
                         "type":  "edit",
                         "var":  "",
                         "y":  47,
                         "w":  182,
                         "fmt":  "30",
                         "name":  "W1-select qualite",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  154,
                         "type":  "combobox",
                         "var":  "",
                         "y":  63,
                         "w":  188,
                         "fmt":  "",
                         "name":  "W1-select honey moon",
                         "h":  11,
                         "color":  "110",
                         "text":  "1,2",
                         "parent":  4
                     },
                     {
                         "x":  480,
                         "type":  "combobox",
                         "var":  "",
                         "y":  63,
                         "w":  122,
                         "fmt":  "",
                         "name":  "W1-select fleurs",
                         "h":  11,
                         "color":  "110",
                         "text":  "1,2",
                         "parent":  4
                     },
                     {
                         "x":  154,
                         "type":  "combobox",
                         "var":  "",
                         "y":  78,
                         "w":  188,
                         "fmt":  "",
                         "name":  "W1-select millesia",
                         "h":  11,
                         "color":  "110",
                         "text":  "1,2",
                         "parent":  4
                     },
                     {
                         "x":  480,
                         "type":  "combobox",
                         "var":  "",
                         "y":  78,
                         "w":  188,
                         "fmt":  "",
                         "name":  "W1-type de milesia",
                         "h":  11,
                         "color":  "110",
                         "text":  "Ami,Proche,Intime,Top top,GO Vacance",
                         "parent":  4
                     },
                     {
                         "x":  157,
                         "type":  "edit",
                         "var":  "",
                         "y":  95,
                         "w":  133,
                         "fmt":  "",
                         "name":  "CLI Date Debut",
                         "h":  11,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  292,
                         "type":  "button",
                         "var":  "",
                         "y":  95,
                         "w":  27,
                         "fmt":  "...",
                         "name":  "W1-bouton date debut",
                         "h":  11,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  504,
                         "type":  "edit",
                         "var":  "",
                         "y":  95,
                         "w":  93,
                         "fmt":  "6U",
                         "name":  "W1-select vol aller",
                         "h":  11,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  598,
                         "type":  "button",
                         "var":  "",
                         "y":  95,
                         "w":  27,
                         "fmt":  "...",
                         "name":  "v. bouton vol aller",
                         "h":  11,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  157,
                         "type":  "edit",
                         "var":  "",
                         "y":  112,
                         "w":  133,
                         "fmt":  "",
                         "name":  "CLI Date Fin",
                         "h":  11,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  292,
                         "type":  "button",
                         "var":  "",
                         "y":  112,
                         "w":  27,
                         "fmt":  "...",
                         "name":  "W1-bouton date fin",
                         "h":  11,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  504,
                         "type":  "edit",
                         "var":  "",
                         "y":  112,
                         "w":  93,
                         "fmt":  "6U",
                         "name":  "W1-select vol dep",
                         "h":  11,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  598,
                         "type":  "button",
                         "var":  "",
                         "y":  112,
                         "w":  27,
                         "fmt":  "...",
                         "name":  "v. bouton vol retour",
                         "h":  11,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  157,
                         "type":  "edit",
                         "var":  "",
                         "y":  129,
                         "w":  133,
                         "fmt":  "9P0Z",
                         "name":  "CLI N° Adherent",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  386,
                         "type":  "edit",
                         "var":  "",
                         "y":  129,
                         "w":  48,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  552,
                         "type":  "edit",
                         "var":  "",
                         "y":  129,
                         "w":  126,
                         "fmt":  "",
                         "name":  "CLI Date Naissance",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  157,
                         "type":  "edit",
                         "var":  "",
                         "y":  146,
                         "w":  48,
                         "fmt":  "",
                         "name":  "W1-select inscription",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  206,
                         "type":  "button",
                         "var":  "",
                         "y":  146,
                         "w":  27,
                         "fmt":  "...",
                         "name":  "v. bouton inscription",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  242,
                         "type":  "edit",
                         "var":  "",
                         "y":  148,
                         "w":  288,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "142",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  157,
                         "type":  "combobox",
                         "var":  "",
                         "y":  162,
                         "w":  166,
                         "fmt":  "",
                         "name":  "W1-select fumeur",
                         "h":  11,
                         "color":  "110",
                         "text":  "1,2",
                         "parent":  4
                     },
                     {
                         "x":  157,
                         "type":  "combobox",
                         "var":  "",
                         "y":  179,
                         "w":  238,
                         "fmt":  "",
                         "name":  "W1-select lieu sejour",
                         "h":  11,
                         "color":  "110",
                         "text":  "1,2",
                         "parent":  4
                     },
                     {
                         "x":  601,
                         "type":  "button",
                         "var":  "",
                         "y":  179,
                         "w":  27,
                         "fmt":  "...",
                         "name":  "v. bouton logement",
                         "h":  11,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  539,
                         "type":  "edit",
                         "var":  "",
                         "y":  179,
                         "w":  60,
                         "fmt":  "10",
                         "name":  "W1-select logement",
                         "h":  11,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  157,
                         "type":  "combobox",
                         "var":  "",
                         "y":  196,
                         "w":  238,
                         "fmt":  "",
                         "name":  "W1-select TUP",
                         "h":  11,
                         "color":  "110",
                         "text":  "1,2",
                         "parent":  4
                     },
                     {
                         "x":  539,
                         "type":  "combobox",
                         "var":  "",
                         "y":  196,
                         "w":  89,
                         "fmt":  "",
                         "name":  "W1-select Base OCC",
                         "h":  11,
                         "color":  "110",
                         "text":  "1,2",
                         "parent":  4
                     },
                     {
                         "x":  733,
                         "type":  "edit",
                         "var":  "",
                         "y":  129,
                         "w":  30,
                         "fmt":  "",
                         "name":  "CLI Age",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  195,
                         "type":  "button",
                         "var":  "",
                         "y":  216,
                         "w":  27,
                         "fmt":  "...",
                         "name":  "v. bouton langue",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  157,
                         "type":  "edit",
                         "var":  "",
                         "y":  216,
                         "w":  37,
                         "fmt":  "",
                         "name":  "GMR Langue Parlee",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  101,
                         "type":  "edit",
                         "var":  "",
                         "y":  247,
                         "w":  126,
                         "fmt":  "",
                         "name":  "W1 n dans la rue",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  50
                     },
                     {
                         "x":  229,
                         "type":  "edit",
                         "var":  "",
                         "y":  247,
                         "w":  356,
                         "fmt":  "",
                         "name":  "W1 Nom de la rue",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  50
                     },
                     {
                         "x":  101,
                         "type":  "edit",
                         "var":  "",
                         "y":  257,
                         "w":  483,
                         "fmt":  "",
                         "name":  "W1 Commune",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  50
                     },
                     {
                         "x":  101,
                         "type":  "edit",
                         "var":  "",
                         "y":  267,
                         "w":  126,
                         "fmt":  "",
                         "name":  "W1 Code postal",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  50
                     },
                     {
                         "x":  229,
                         "type":  "edit",
                         "var":  "",
                         "y":  267,
                         "w":  356,
                         "fmt":  "",
                         "name":  "W1 Ville",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  50
                     },
                     {
                         "x":  234,
                         "type":  "edit",
                         "var":  "",
                         "y":  216,
                         "w":  238,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "142",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  373,
                         "type":  "edit",
                         "var":  "",
                         "y":  47,
                         "w":  277,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "142",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  8,
                         "type":  "button",
                         "var":  "",
                         "y":  289,
                         "w":  154,
                         "fmt":  "\u0026Ok",
                         "name":  "Bouton Ok",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  56
                     },
                     {
                         "x":  169,
                         "type":  "button",
                         "var":  "",
                         "y":  289,
                         "w":  154,
                         "fmt":  "\u0026Filiation",
                         "name":  "Filiation",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  56
                     },
                     {
                         "x":  6,
                         "type":  "edit",
                         "var":  "",
                         "y":  6,
                         "w":  267,
                         "fmt":  "30",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  635,
                         "type":  "edit",
                         "var":  "",
                         "y":  6,
                         "w":  267,
                         "fmt":  "WWW DD MMM YYYYT",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  157,
                         "type":  "edit",
                         "var":  "",
                         "y":  179,
                         "w":  48,
                         "fmt":  "",
                         "name":  "",
                         "h":  11,
                         "color":  "6",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  714,
                         "type":  "image",
                         "var":  "",
                         "y":  235,
                         "w":  102,
                         "fmt":  "",
                         "name":  "",
                         "h":  48,
                         "color":  "7",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  752,
                         "type":  "button",
                         "var":  "",
                         "y":  290,
                         "w":  154,
                         "fmt":  "A\u0026bandonner",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  56
                     }
                 ],
    "taskId":  "387.2",
    "height":  311
}
-->

<details>
<summary><strong>Champs : 34 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 156,31 | CLI Nom | - | edit |
| 466,31 | CLI Prenom | - | edit |
| 660,31 | W1-select titre | - | combobox |
| 156,47 | W1-select qualite | - | edit |
| 154,63 | W1-select honey moon | - | combobox |
| 480,63 | W1-select fleurs | - | combobox |
| 154,78 | W1-select millesia | - | combobox |
| 480,78 | W1-type de milesia | - | combobox |
| 157,95 | CLI Date Debut | - | edit |
| 504,95 | W1-select vol aller | - | edit |
| 157,112 | CLI Date Fin | - | edit |
| 504,112 | W1-select vol dep | - | edit |
| 157,129 | CLI N° Adherent | - | edit |
| 386,129 | (sans nom) | - | edit |
| 552,129 | CLI Date Naissance | - | edit |
| 157,146 | W1-select inscription | - | edit |
| 242,148 | (sans nom) | - | edit |
| 157,162 | W1-select fumeur | - | combobox |
| 157,179 | W1-select lieu sejour | - | combobox |
| 539,179 | W1-select logement | - | edit |
| 157,196 | W1-select TUP | - | combobox |
| 539,196 | W1-select Base OCC | - | combobox |
| 733,129 | CLI Age | - | edit |
| 157,216 | GMR Langue Parlee | - | edit |
| 101,247 | W1 n dans la rue | - | edit |
| 229,247 | W1 Nom de la rue | - | edit |
| 101,257 | W1 Commune | - | edit |
| 101,267 | W1 Code postal | - | edit |
| 229,267 | W1 Ville | - | edit |
| 234,216 | (sans nom) | - | edit |
| 373,47 | (sans nom) | - | edit |
| 6,6 | 30 | - | edit |
| 635,6 | WWW DD MMM YYYYT | - | edit |
| 157,179 | (sans nom) | - | edit |

</details>

<details>
<summary><strong>Boutons : 11 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| ... | 339,47 | Bouton fonctionnel |
| ... | 292,95 | Bouton fonctionnel |
| ... | 598,95 | Bouton fonctionnel |
| ... | 292,112 | Bouton fonctionnel |
| ... | 598,112 | Bouton fonctionnel |
| ... | 206,146 | Bouton fonctionnel |
| ... | 601,179 | Bouton fonctionnel |
| ... | 195,216 | Bouton fonctionnel |
| Ok | 8,289 | Valide la saisie et enregistre |
| Filiation | 169,289 | Bouton fonctionnel |
| Abandonner | 752,290 | Annule et retour au menu |

</details>

---

#### <a id="ecran-t10"></a>387.2.6 - personne existante
**Tache** : [387.2.6](#t10) | **Type** : MDI | **Dimensions** : 776 x 145 DLU
**Bloc** : Traitement | **Titre IDE** : personne existante

<!-- FORM-DATA:
{
    "width":  776,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  1,
                         "w":  771,
                         "fmt":  "",
                         "name":  "",
                         "h":  21,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  258,
                         "type":  "label",
                         "var":  "",
                         "y":  26,
                         "w":  513,
                         "fmt":  "",
                         "name":  "",
                         "h":  89,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  261,
                         "type":  "label",
                         "var":  "",
                         "y":  27,
                         "w":  508,
                         "fmt":  "",
                         "name":  "",
                         "h":  87,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  293,
                         "type":  "label",
                         "var":  "",
                         "y":  35,
                         "w":  107,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "N° Adhérent",
                         "parent":  5
                     },
                     {
                         "x":  293,
                         "type":  "label",
                         "var":  "",
                         "y":  50,
                         "w":  107,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Nom",
                         "parent":  5
                     },
                     {
                         "x":  293,
                         "type":  "label",
                         "var":  "",
                         "y":  65,
                         "w":  107,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Prénom",
                         "parent":  null
                     },
                     {
                         "x":  293,
                         "type":  "label",
                         "var":  "",
                         "y":  80,
                         "w":  107,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Début Séjour",
                         "parent":  5
                     },
                     {
                         "x":  293,
                         "type":  "label",
                         "var":  "",
                         "y":  95,
                         "w":  107,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Fin Séjour",
                         "parent":  5
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  119,
                         "w":  771,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  406,
                         "type":  "edit",
                         "var":  "",
                         "y":  50,
                         "w":  344,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  406,
                         "type":  "edit",
                         "var":  "",
                         "y":  65,
                         "w":  98,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  406,
                         "type":  "edit",
                         "var":  "",
                         "y":  80,
                         "w":  120,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  406,
                         "type":  "edit",
                         "var":  "",
                         "y":  95,
                         "w":  120,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  480,
                         "type":  "edit",
                         "var":  "",
                         "y":  7,
                         "w":  283,
                         "fmt":  "WWW DD MMM YYYYT",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  0,
                         "type":  "image",
                         "var":  "",
                         "y":  33,
                         "w":  249,
                         "fmt":  "",
                         "name":  "",
                         "h":  81,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  406,
                         "type":  "edit",
                         "var":  "",
                         "y":  35,
                         "w":  187,
                         "fmt":  "16",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  10,
                         "type":  "button",
                         "var":  "",
                         "y":  121,
                         "w":  154,
                         "fmt":  "\u0026OK",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  6,
                         "type":  "edit",
                         "var":  "",
                         "y":  7,
                         "w":  267,
                         "fmt":  "20",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "387.2.6",
    "height":  145
}
-->

<details>
<summary><strong>Champs : 7 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 406,50 | (sans nom) | - | edit |
| 406,65 | (sans nom) | - | edit |
| 406,80 | (sans nom) | - | edit |
| 406,95 | (sans nom) | - | edit |
| 480,7 | WWW DD MMM YYYYT | - | edit |
| 406,35 | 16 | - | edit |
| 6,7 | 20 | - | edit |

</details>

<details>
<summary><strong>Boutons : 1 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| OK | 10,121 | Valide la saisie et enregistre |

</details>

---

#### <a id="ecran-t13"></a>387.2.8.1 - Clients
**Tache** : [387.2.8.1](#t13) | **Type** : MDI | **Dimensions** : 710 x 150 DLU
**Bloc** : Traitement | **Titre IDE** : Clients

<!-- FORM-DATA:
{
    "width":  710,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  706,
                         "fmt":  "",
                         "name":  "",
                         "h":  21,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  175,
                         "type":  "label",
                         "var":  "",
                         "y":  24,
                         "w":  531,
                         "fmt":  "",
                         "name":  "",
                         "h":  52,
                         "color":  "1",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  189,
                         "type":  "label",
                         "var":  "",
                         "y":  31,
                         "w":  96,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "N°Adherent",
                         "parent":  4
                     },
                     {
                         "x":  478,
                         "type":  "label",
                         "var":  "",
                         "y":  31,
                         "w":  80,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "Filiation",
                         "parent":  4
                     },
                     {
                         "x":  189,
                         "type":  "label",
                         "var":  "",
                         "y":  45,
                         "w":  80,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "Nom",
                         "parent":  4
                     },
                     {
                         "x":  478,
                         "type":  "label",
                         "var":  "",
                         "y":  45,
                         "w":  82,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "Prenom",
                         "parent":  4
                     },
                     {
                         "x":  189,
                         "type":  "label",
                         "var":  "",
                         "y":  60,
                         "w":  42,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "Titre",
                         "parent":  4
                     },
                     {
                         "x":  175,
                         "type":  "label",
                         "var":  "",
                         "y":  79,
                         "w":  531,
                         "fmt":  "",
                         "name":  "",
                         "h":  36,
                         "color":  "1",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  202,
                         "type":  "label",
                         "var":  "",
                         "y":  84,
                         "w":  133,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "Date Naissance",
                         "parent":  15
                     },
                     {
                         "x":  497,
                         "type":  "label",
                         "var":  "",
                         "y":  84,
                         "w":  38,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "Age",
                         "parent":  15
                     },
                     {
                         "x":  202,
                         "type":  "label",
                         "var":  "",
                         "y":  100,
                         "w":  74,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "Fumeur",
                         "parent":  15
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  125,
                         "w":  706,
                         "fmt":  "",
                         "name":  "",
                         "h":  22,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  563,
                         "type":  "edit",
                         "var":  "",
                         "y":  31,
                         "w":  48,
                         "fmt":  "",
                         "name":  "CLI Filiation Club",
                         "h":  12,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  288,
                         "type":  "edit",
                         "var":  "",
                         "y":  45,
                         "w":  182,
                         "fmt":  "",
                         "name":  "CLI Nom",
                         "h":  12,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  563,
                         "type":  "edit",
                         "var":  "",
                         "y":  45,
                         "w":  126,
                         "fmt":  "UL9",
                         "name":  "CLI Prenom",
                         "h":  12,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  290,
                         "type":  "combobox",
                         "var":  "",
                         "y":  60,
                         "w":  182,
                         "fmt":  "",
                         "name":  "W2-select titre",
                         "h":  12,
                         "color":  "110",
                         "text":  "1,2",
                         "parent":  4
                     },
                     {
                         "x":  565,
                         "type":  "edit",
                         "var":  "",
                         "y":  84,
                         "w":  38,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "",
                         "parent":  15
                     },
                     {
                         "x":  337,
                         "type":  "edit",
                         "var":  "",
                         "y":  84,
                         "w":  126,
                         "fmt":  "",
                         "name":  "CLI Date Naissance",
                         "h":  12,
                         "color":  "110",
                         "text":  "",
                         "parent":  15
                     },
                     {
                         "x":  337,
                         "type":  "combobox",
                         "var":  "",
                         "y":  99,
                         "w":  182,
                         "fmt":  "",
                         "name":  "W2-select fumeur",
                         "h":  12,
                         "color":  "110",
                         "text":  "1,2",
                         "parent":  15
                     },
                     {
                         "x":  8,
                         "type":  "button",
                         "var":  "",
                         "y":  127,
                         "w":  154,
                         "fmt":  "\u0026Ok",
                         "name":  "Bouton Ok",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  6,
                         "type":  "edit",
                         "var":  "",
                         "y":  6,
                         "w":  267,
                         "fmt":  "30",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  411,
                         "type":  "edit",
                         "var":  "",
                         "y":  6,
                         "w":  283,
                         "fmt":  "WWW DD MMM YYYYT",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  293,
                         "type":  "edit",
                         "var":  "",
                         "y":  31,
                         "w":  120,
                         "fmt":  "10",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  10,
                         "type":  "image",
                         "var":  "",
                         "y":  37,
                         "w":  159,
                         "fmt":  "",
                         "name":  "",
                         "h":  59,
                         "color":  "7",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  171,
                         "type":  "button",
                         "var":  "",
                         "y":  127,
                         "w":  154,
                         "fmt":  "\u0026Abandonner",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "387.2.8.1",
    "height":  150
}
-->

<details>
<summary><strong>Champs : 10 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 563,31 | CLI Filiation Club | - | edit |
| 288,45 | CLI Nom | - | edit |
| 563,45 | CLI Prenom | - | edit |
| 290,60 | W2-select titre | - | combobox |
| 565,84 | (sans nom) | - | edit |
| 337,84 | CLI Date Naissance | - | edit |
| 337,99 | W2-select fumeur | - | combobox |
| 6,6 | 30 | - | edit |
| 411,6 | WWW DD MMM YYYYT | - | edit |
| 293,31 | 10 | - | edit |

</details>

<details>
<summary><strong>Boutons : 2 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Ok | 8,127 | Valide la saisie et enregistre |
| Abandonner | 171,127 | Annule et retour au menu |

</details>

---

#### <a id="ecran-t21"></a>387.2.9 - MAJ immigration
**Tache** : [387.2.9](#t21) | **Type** : MDI | **Dimensions** : 638 x 168 DLU
**Bloc** : Traitement | **Titre IDE** : MAJ immigration

<!-- FORM-DATA:
{
    "width":  638,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  633,
                         "fmt":  "",
                         "name":  "",
                         "h":  21,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  205,
                         "type":  "label",
                         "var":  "",
                         "y":  29,
                         "w":  415,
                         "fmt":  "",
                         "name":  "",
                         "h":  100,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  219,
                         "type":  "label",
                         "var":  "",
                         "y":  35,
                         "w":  130,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Date Naissance",
                         "parent":  4
                     },
                     {
                         "x":  219,
                         "type":  "label",
                         "var":  "",
                         "y":  51,
                         "w":  118,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Nationalite",
                         "parent":  4
                     },
                     {
                         "x":  219,
                         "type":  "label",
                         "var":  "",
                         "y":  67,
                         "w":  75,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Identite",
                         "parent":  4
                     },
                     {
                         "x":  219,
                         "type":  "label",
                         "var":  "",
                         "y":  83,
                         "w":  125,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Ville Delivrance",
                         "parent":  4
                     },
                     {
                         "x":  219,
                         "type":  "label",
                         "var":  "",
                         "y":  99,
                         "w":  131,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Date Delivrance",
                         "parent":  4
                     },
                     {
                         "x":  219,
                         "type":  "label",
                         "var":  "",
                         "y":  115,
                         "w":  118,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Profession",
                         "parent":  4
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  142,
                         "w":  633,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  368,
                         "type":  "edit",
                         "var":  "",
                         "y":  35,
                         "w":  126,
                         "fmt":  "",
                         "name":  "W2-Date naissance",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  368,
                         "type":  "combobox",
                         "var":  "",
                         "y":  51,
                         "w":  238,
                         "fmt":  "",
                         "name":  "W2-select nationalite",
                         "h":  12,
                         "color":  "110",
                         "text":  "1,2",
                         "parent":  4
                     },
                     {
                         "x":  368,
                         "type":  "edit",
                         "var":  "",
                         "y":  67,
                         "w":  238,
                         "fmt":  "",
                         "name":  "W2-Identite",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  368,
                         "type":  "edit",
                         "var":  "",
                         "y":  83,
                         "w":  238,
                         "fmt":  "",
                         "name":  "W2-Ville delivrance",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  368,
                         "type":  "edit",
                         "var":  "",
                         "y":  99,
                         "w":  126,
                         "fmt":  "",
                         "name":  "W2-Date delivrance",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  368,
                         "type":  "edit",
                         "var":  "",
                         "y":  114,
                         "w":  238,
                         "fmt":  "",
                         "name":  "W2-Profession",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  9,
                         "type":  "button",
                         "var":  "",
                         "y":  145,
                         "w":  154,
                         "fmt":  "\u0026Ok",
                         "name":  "bouton quitter",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  17
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
                         "parent":  null
                     },
                     {
                         "x":  345,
                         "type":  "edit",
                         "var":  "",
                         "y":  6,
                         "w":  283,
                         "fmt":  "WWW DD MMM YYYYT",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  21,
                         "type":  "image",
                         "var":  "",
                         "y":  55,
                         "w":  155,
                         "fmt":  "",
                         "name":  "",
                         "h":  56,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  176,
                         "type":  "button",
                         "var":  "",
                         "y":  145,
                         "w":  154,
                         "fmt":  "\u0026Abandonner",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  17
                     }
                 ],
    "taskId":  "387.2.9",
    "height":  168
}
-->

<details>
<summary><strong>Champs : 8 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 368,35 | W2-Date naissance | - | edit |
| 368,51 | W2-select nationalite | - | combobox |
| 368,67 | W2-Identite | - | edit |
| 368,83 | W2-Ville delivrance | - | edit |
| 368,99 | W2-Date delivrance | - | edit |
| 368,114 | W2-Profession | - | edit |
| 8,6 | 20 | - | edit |
| 345,6 | WWW DD MMM YYYYT | - | edit |

</details>

<details>
<summary><strong>Boutons : 2 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Ok | 9,145 | Valide la saisie et enregistre |
| Abandonner | 176,145 | Annule et retour au menu |

</details>

## 9. NAVIGATION

### 9.1 Enchainement des ecrans

```mermaid
flowchart TD
    START([Entree])
    style START fill:#3fb950
    VF4[387.2 Creation client]
    style VF4 fill:#58a6ff
    VF10[387.2.6 personne existante]
    style VF10 fill:#58a6ff
    VF13[387.2.8.1 Clients]
    style VF13 fill:#58a6ff
    VF21[387.2.9 MAJ immigration]
    style VF21 fill:#58a6ff
    EXT359[IDE 359 Zoom VOL]
    style EXT359 fill:#3fb950
    EXT309[IDE 309 Redirection to...]
    style EXT309 fill:#3fb950
    EXT312[IDE 312 Determination ...]
    style EXT312 fill:#3fb950
    EXT317[IDE 317 Recuperation d...]
    style EXT317 fill:#3fb950
    EXT354[IDE 354 Zoom inscription]
    style EXT354 fill:#3fb950
    EXT357[IDE 357 Zoom logement]
    style EXT357 fill:#3fb950
    EXT366[IDE 366 Zoom QualiteCP]
    style EXT366 fill:#3fb950
    EXT72[IDE 72 Creation Fideli...]
    style EXT72 fill:#3fb950
    EXT84[IDE 84 Delete GMR cpte=0]
    style EXT84 fill:#3fb950
    EXT85[IDE 85 Delete GMR adh=0]
    style EXT85 fill:#3fb950
    EXT90[IDE 90 Maj Passport]
    style EXT90 fill:#3fb950
    EXT97[IDE 97 Create TAI GM]
    style EXT97 fill:#3fb950
    EXT355[IDE 355 Zoom langue]
    style EXT355 fill:#3fb950
    EXT311[IDE 311 Langue]
    style EXT311 fill:#3fb950
    EXT313[IDE 313 Caractères Int...]
    style EXT313 fill:#3fb950
    EXT314[IDE 314 Caractères Int...]
    style EXT314 fill:#3fb950
    EXT320[IDE 320 Verification A...]
    style EXT320 fill:#3fb950
    FIN([Sortie])
    style FIN fill:#f85149
    START --> VF4
    VF4 -->|Selection/consultation| EXT359
    VF4 -->|Sous-programme| EXT309
    VF4 -->|Sous-programme| EXT312
    VF4 -->|Recuperation donnees| EXT317
    VF4 -->|Selection/consultation| EXT354
    VF4 -->|Selection/consultation| EXT357
    VF4 -->|Selection/consultation| EXT366
    VF4 -->|Programme fidelite| EXT72
    EXT320 --> FIN
```

**Detail par enchainement :**

| Depuis | Action | Vers | Retour |
|--------|--------|------|--------|
| Creation client | Selection/consultation | [Zoom VOL (IDE 359)](PBG-IDE-359.md) | Retour ecran |
| Creation client | Sous-programme | [Redirection touches (IDE 309)](PBG-IDE-309.md) | Retour ecran |
| Creation client | Sous-programme | [Determination Age Debut Sejour (IDE 312)](PBG-IDE-312.md) | Retour ecran |
| Creation client | Recuperation donnees | [Recuperation du titre (IDE 317)](PBG-IDE-317.md) | Retour ecran |
| Creation client | Selection/consultation | [Zoom inscription (IDE 354)](PBG-IDE-354.md) | Retour ecran |
| Creation client | Selection/consultation | [Zoom logement (IDE 357)](PBG-IDE-357.md) | Retour ecran |
| Creation client | Selection/consultation | [Zoom Qualite(C/P) (IDE 366)](PBG-IDE-366.md) | Retour ecran |
| Creation client | Programme fidelite | [   Creation Fidelisation (IDE 72)](PBG-IDE-72.md) | Retour ecran |
| Creation client | Sous-programme | [   Delete GMR cpte=0 (IDE 84)](PBG-IDE-84.md) | Retour ecran |
| Creation client | Sous-programme | [   Delete GMR adh=0 (IDE 85)](PBG-IDE-85.md) | Retour ecran |
| Creation client | Mise a jour donnees | [  Maj Passport (IDE 90)](PBG-IDE-90.md) | Retour ecran |
| Creation client | Sous-programme | [Create TAI GM (IDE 97)](PBG-IDE-97.md) | Retour ecran |
| Creation client | Selection/consultation | [Zoom langue (IDE 355)](PBG-IDE-355.md) | Retour ecran |
| Creation client | Sous-programme | [Langue ? (IDE 311)](PBG-IDE-311.md) | Retour ecran |
| Creation client | Validation saisie | [Caractères Interdits (A20) - L (IDE 313)](PBG-IDE-313.md) | Retour ecran |
| Creation client | Validation saisie | [Caractères Interdits (A20) - A (IDE 314)](PBG-IDE-314.md) | Retour ecran |
| Creation client | Controle/validation | [Verification Aut sans ecran (IDE 320)](PBG-IDE-320.md) | Retour ecran |

### 9.3 Structure hierarchique (25 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **387.1** | [**Module des Clients** (387)](#t1) | MDI | - | Traitement |
| 387.1.1 | [Determination Age Bebe (387.1)](#t2) | MDI | - | |
| 387.1.2 | [Modification Hebergement (387.2.1)](#t5) | MDI | - | |
| 387.1.3 | [Demarquage Caisse (387.2.3)](#t7) | MDI | - | |
| 387.1.4 | [personne existante (387.2.6)](#t10) [mockup](#ecran-t10) | MDI | 776x145 | |
| 387.1.5 | [determination periode (387.2.7)](#t11) | MDI | - | |
| 387.1.6 | [Reiteration (387.2.8)](#t12) [mockup](#ecran-t12) | MDI | 706x147 | |
| 387.1.7 | [Clients (387.2.8.1)](#t13) [mockup](#ecran-t13) | MDI | 710x150 | |
| 387.1.8 | [Modification Hebergement (387.2.8.1.1)](#t14) | MDI | - | |
| 387.1.9 | [recup filiation club (387.2.8.1.3)](#t17) | MDI | - | |
| 387.1.10 | [recup filiation (387.2.8.1.4)](#t18) | MDI | - | |
| 387.1.11 | [MAJ immigration (387.2.9)](#t21) [mockup](#ecran-t21) | MDI | 638x168 | |
| 387.1.12 | [Clients (387.2.10)](#t22) [mockup](#ecran-t22) | MDI | 216x52 | |
| **387.2** | [**Creation client** (387.2)](#t4) [mockup](#ecran-t4) | MDI | 920x311 | Creation |
| 387.2.1 | [Creation Historique (387.2.2)](#t6) | MDI | - | |
| 387.2.2 | [creation V/V (387.2.4)](#t8) | MDI | - | |
| 387.2.3 | [Creation Historique (387.2.8.1.2)](#t15) | MDI | - | |
| **387.3** | [**Verification Algorythme** (387.2.5)](#t9) | MDI | - | Validation |
| 387.3.1 | [verif logements (387.2.13)](#t25) | MDI | - | |
| **387.4** | [**Calcul flag** (387.2.8.1.5)](#t19) | MDI | - | Calcul |
| 387.4.1 | [Calcul Millesia (387.2.8.1.6)](#t20) | MDI | - | |
| 387.4.2 | [Mise a jour compteur (387.2.12)](#t24) | MDI | - | |
| 387.4.3 | [Calcul Millesia (387.2.14)](#t26) | MDI | - | |
| **387.5** | [**Modif recherche** (387.2.11)](#t23) | MDI | - | Consultation |
| **387.6** | [**Initialisation paramètres** (387.3)](#t27) | MDI | - | Initialisation |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Creation]
    UPDATE[MAJ 8 tables]
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

### Tables utilisees (22)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 30 | gm-recherche_____gmr | Index de recherche | DB | R | **W** | L | 4 |
| 31 | gm-complet_______gmc |  | DB |   | **W** |   | 3 |
| 34 | hebergement______heb | Hebergement (chambres) | DB | R |   | L | 3 |
| 36 | client_gm |  | DB | R |   | L | 4 |
| 47 | compte_gm________cgm | Comptes GM (generaux) | DB |   | **W** | L | 2 |
| 63 | parametres___par |  | DB | R |   | L | 2 |
| 68 | compteurs________cpt | Comptes GM (generaux) | DB |   | **W** | L | 2 |
| 69 | initialisation___ini |  | DB |   |   | L | 1 |
| 78 | param__telephone_tel |  | DB |   |   | L | 1 |
| 88 | historik_station | Historique / journal | DB |   | **W** |   | 2 |
| 108 | code_logement____clo |  | DB | R |   |   | 1 |
| 113 | tables_village |  | DB | R |   | L | 3 |
| 119 | tables_pays_tel_ |  | DB |   |   | L | 2 |
| 120 | tables_qualites__qua |  | DB |   |   | L | 1 |
| 121 | tables_pays_ventes | Donnees de ventes | DB |   |   | L | 1 |
| 130 | fichier_langue |  | DB |   |   | L | 1 |
| 131 | fichier_validation |  | DB |   |   | L | 2 |
| 134 | groupe_arr_dep___vol |  | DB |   | **W** | L | 2 |
| 168 | heb_circuit______hci | Hebergement (chambres) | DB |   | **W** |   | 2 |
| 171 | commentaire______com |  | DB |   |   | L | 1 |
| 358 | import_mod |  | DB |   | **W** |   | 2 |
| 728 | arc_cc_total |  | DB |   |   | L | 1 |

### Colonnes par table (9 / 13 tables avec colonnes identifiees)

<details>
<summary>Table 30 - gm-recherche_____gmr (R/**W**/L) - 4 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 31 - gm-complet_______gmc (**W**) - 3 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | W1-autorisation | W | Alpha |
| B | W1-fin tache | W | Logical |
| C | W1 ret lien comment | W | Numeric |
| D | W1-age codifie | W | Alpha |
| E | W1-Nb mois | W | Numeric |
| F | W1-fin compte | W | Date |
| G | W1-Numero compte memo | W | Numeric |
| H | W1-Filliation | W | Numeric |
| I | W1-Creation TAI | W | Logical |
| J | W1-planning | W | Logical |
| K | W1-saisie langue ? | W | Logical |
| L | W1-validation nom | W | Logical |
| M | W1-validation prenom | W | Alpha |
| N | W1-select titre | W | Alpha |
| O | v cdr | W | Logical |
| P | v. bouton qualite | W | Alpha |
| Q | W1-select qualite | W | Alpha |
| R | W1-select honey moon | W | Alpha |
| S | W1-select fleurs | W | Alpha |
| T | W1-select millesia | W | Alpha |
| U | W1-type de milesia | W | Alpha |
| V | W1-Actionnaire | W | Alpha |
| W | W1-Donateur | W | Alpha |
| X | W1-TOP VIP | W | Alpha |
| Y | W1-Ambassadeur | W | Alpha |
| Z | W1-Report | W | Alpha |
| BA | W1-anc date deb | W | Date |
| BB | W1-bouton date debut | W | Alpha |
| BC | W1-retour vol aller | W | Logical |
| BD | W1-select vol aller | W | Alpha |
| BE | v. bouton vol aller | W | Alpha |
| BF | W1-anc date fin | W | Date |
| BG | W1-bouton date fin | W | Alpha |
| BH | W1-retour vol retour | W | Logical |
| BI | W1-select vol dep | W | Alpha |
| BJ | v. bouton vol retour | W | Alpha |
| BK | W1-accord filiation | W | Logical |
| BL | W1 codrt adherent | W | Logical |
| BM | W1-retour filiation | W | Logical |
| BN | W1-retour famille | W | Logical |
| BO | W1 libelle nationalite | W | Alpha |
| BP | W1 langue parler | W | Alpha |
| BQ | W1-select inscription | W | Alpha |
| BR | v. bouton inscription | W | Alpha |
| BS | W1-select fumeur | W | Alpha |
| BT | W1-lieu sejour | W | Alpha |
| BU | W1-select lieu sejour | W | Alpha |
| BV | W1-retour logement | W | Logical |
| BW | W1-select logement | W | Alpha |
| BX | v. bouton logement | W | Alpha |
| BY | W1-select TUP | W | Alpha |
| BZ | W1-select Base OCC | W | Alpha |
| CA | W1 N° Piece | W | Alpha |
| CB | W1 Date de delivrance | W | Date |
| CC | W1 Ville delivrance | W | Alpha |
| CD | W1 Proffession | W | Alpha |
| CE | v. bouton langue | W | Alpha |
| CF | W1 n dans la rue | W | Alpha |
| CG | W1 Nom de la rue | W | Alpha |
| CH | W1 Commune | W | Alpha |
| CI | W1 Code postal | W | Alpha |
| CJ | W1 Ville | W | Alpha |
| CK | v. Hebergement | W | Alpha |
| CL | v. aller | W | Alpha |
| CM | v. retour | W | Alpha |
| CN | Bouton Ok | W | Alpha |
| CO | v. ok filiation | W | Logical |
| CP | W1-bouton creer une filiation | W | Alpha |

</details>

<details>
<summary>Table 34 - hebergement______heb (R/L) - 3 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| CK | v. Hebergement | R | Alpha |

</details>

<details>
<summary>Table 36 - client_gm (R/L) - 4 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| G | W2 cdrt client | R | Logical |
| H | W0-Type Client | R | Alpha |

</details>

<details>
<summary>Table 47 - compte_gm________cgm (**W**/L) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| B | >Numero Compte | W | Numeric |
| C | >Filiation Compte | W | Numeric |
| E | W2-fin compte | W | Date |
| F | W1-fin compte | W | Date |
| G | W1-Numero compte memo | W | Numeric |
| W | W0-compteur lieu | W | Numeric |

</details>

<details>
<summary>Table 63 - parametres___par (R/L) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 68 - compteurs________cpt (**W**/L) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 88 - historik_station (**W**) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 108 - code_logement____clo (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| BV | W1-retour logement | R | Logical |
| BW | W1-select logement | R | Alpha |
| BX | v. bouton logement | R | Alpha |
| CI | W1 Code postal | R | Alpha |

</details>

<details>
<summary>Table 113 - tables_village (R/L) - 3 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| BG | W0 NomVillage | R | Alpha |
| BK | W0 VILLAGE TAI | R | Alpha |

</details>

<details>
<summary>Table 134 - groupe_arr_dep___vol (**W**/L) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | Aller/Retour | W | Alpha |
| B | Date | W | Date |

</details>

<details>
<summary>Table 168 - heb_circuit______hci (**W**) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 358 - import_mod (**W**) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (1)

Variables recues en parametre.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| G | P0 Front/Back | Alpha | 1x parametre entrant |

### 11.2 Variables de session (8)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| BL | v. Nom Adherent | Alpha | - |
| BR | v. bouton inscription | Alpha | - |
| BX | v. bouton logement | Alpha | - |
| CE | v. bouton langue | Alpha | - |
| CK | v. Hebergement | Alpha | - |
| CL | v. aller | Alpha | - |
| CM | v. retour | Alpha | - |
| CO | v. ok filiation | Logical | - |

### 11.3 Variables de travail (19)

Variables internes au programme.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| F | W0 active menu | Logical | 6x calcul interne |
| N | W0 combo nationalite | Alpha | - |
| R | W0 vol arrive | Alpha | - |
| S | W0 vol depart | Alpha | - |
| T | W0 titre | Alpha | - |
| U | W0 titre 2 | Alpha | - |
| Y | W0 libelle nationalite | Alpha | - |
| Z | W0 filiation club1 | Numeric | - |
| BA | W0 filiation club2 | Numeric | - |
| BB | W0 modif langue | Alpha | - |
| BC | W0 Societe | Alpha | - |
| BD | W0 Devise | Alpha | - |
| BE | W0 Decimales | Numeric | - |
| BF | W0 Masque | Alpha | - |
| BG | W0 NomVillage | Alpha | - |
| BH | W0 TAI Obligatoire | Alpha | - |
| BI | W0 SAISIR TAI | Numeric | - |
| BJ | W0 TAI FAIT POUR FIL ZERO | Logical | - |
| BK | W0 VILLAGE TAI | Alpha | - |

### 11.4 Autres (40)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | > Mode attaque ecran | Alpha | 1x refs |
| B | >Numero Compte | Numeric | - |
| C | >Filiation Compte | Numeric | - |
| D | >Nom Adherent | Alpha | - |
| E | >Prenom Adherent | Alpha | - |
| H | W0-Type Client | Alpha | - |
| I | W0-N°Adherent | Numeric | - |
| J | W0-Filiation | Numeric | - |
| K | W0-Fin de Tache | Logical | 1x refs |
| L | W0-Age Bebe | Numeric | - |
| M | W0-Base Vide | Alpha | - |
| O | W0-autorisation creation | Alpha | [387.2](#t4), [387.2.2](#t6), [387.2.4](#t8) |
| P | W0- autorisation modif | Alpha | - |
| Q | W0- Blocage effectue | Alpha | - |
| V | W0-lieu sejour general | Alpha | - |
| W | W0-compteur lieu | Numeric | - |
| X | W0-lieu sejour | Alpha | - |
| BM | W1-retour filiation | Logical | - |
| BN | W1-retour famille | Logical | - |
| BO | W1 libelle nationalite | Alpha | - |
| BP | W1 langue parler | Alpha | - |
| BQ | W1-select inscription | Alpha | - |
| BS | W1-select fumeur | Alpha | - |
| BT | W1-lieu sejour | Alpha | - |
| BU | W1-select lieu sejour | Alpha | - |
| BV | W1-retour logement | Logical | - |
| BW | W1-select logement | Alpha | - |
| BY | W1-select TUP | Alpha | - |
| BZ | W1-select Base OCC | Alpha | - |
| CA | W1 N° Piece | Alpha | - |
| CB | W1 Date de delivrance | Date | - |
| CC | W1 Ville delivrance | Alpha | - |
| CD | W1 Proffession | Alpha | - |
| CF | W1 n dans la rue | Alpha | - |
| CG | W1 Nom de la rue | Alpha | - |
| CH | W1 Commune | Alpha | - |
| CI | W1 Code postal | Alpha | - |
| CJ | W1 Ville | Alpha | - |
| CN | Bouton Ok | Alpha | - |
| CP | W1-bouton creer une filiation | Alpha | - |

<details>
<summary>Toutes les 68 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| P0 | **G** | P0 Front/Back | Alpha |
| W0 | **F** | W0 active menu | Logical |
| W0 | **N** | W0 combo nationalite | Alpha |
| W0 | **R** | W0 vol arrive | Alpha |
| W0 | **S** | W0 vol depart | Alpha |
| W0 | **T** | W0 titre | Alpha |
| W0 | **U** | W0 titre 2 | Alpha |
| W0 | **Y** | W0 libelle nationalite | Alpha |
| W0 | **Z** | W0 filiation club1 | Numeric |
| W0 | **BA** | W0 filiation club2 | Numeric |
| W0 | **BB** | W0 modif langue | Alpha |
| W0 | **BC** | W0 Societe | Alpha |
| W0 | **BD** | W0 Devise | Alpha |
| W0 | **BE** | W0 Decimales | Numeric |
| W0 | **BF** | W0 Masque | Alpha |
| W0 | **BG** | W0 NomVillage | Alpha |
| W0 | **BH** | W0 TAI Obligatoire | Alpha |
| W0 | **BI** | W0 SAISIR TAI | Numeric |
| W0 | **BJ** | W0 TAI FAIT POUR FIL ZERO | Logical |
| W0 | **BK** | W0 VILLAGE TAI | Alpha |
| V. | **BL** | v. Nom Adherent | Alpha |
| V. | **BR** | v. bouton inscription | Alpha |
| V. | **BX** | v. bouton logement | Alpha |
| V. | **CE** | v. bouton langue | Alpha |
| V. | **CK** | v. Hebergement | Alpha |
| V. | **CL** | v. aller | Alpha |
| V. | **CM** | v. retour | Alpha |
| V. | **CO** | v. ok filiation | Logical |
| Autre | **A** | > Mode attaque ecran | Alpha |
| Autre | **B** | >Numero Compte | Numeric |
| Autre | **C** | >Filiation Compte | Numeric |
| Autre | **D** | >Nom Adherent | Alpha |
| Autre | **E** | >Prenom Adherent | Alpha |
| Autre | **H** | W0-Type Client | Alpha |
| Autre | **I** | W0-N°Adherent | Numeric |
| Autre | **J** | W0-Filiation | Numeric |
| Autre | **K** | W0-Fin de Tache | Logical |
| Autre | **L** | W0-Age Bebe | Numeric |
| Autre | **M** | W0-Base Vide | Alpha |
| Autre | **O** | W0-autorisation creation | Alpha |
| Autre | **P** | W0- autorisation modif | Alpha |
| Autre | **Q** | W0- Blocage effectue | Alpha |
| Autre | **V** | W0-lieu sejour general | Alpha |
| Autre | **W** | W0-compteur lieu | Numeric |
| Autre | **X** | W0-lieu sejour | Alpha |
| Autre | **BM** | W1-retour filiation | Logical |
| Autre | **BN** | W1-retour famille | Logical |
| Autre | **BO** | W1 libelle nationalite | Alpha |
| Autre | **BP** | W1 langue parler | Alpha |
| Autre | **BQ** | W1-select inscription | Alpha |
| Autre | **BS** | W1-select fumeur | Alpha |
| Autre | **BT** | W1-lieu sejour | Alpha |
| Autre | **BU** | W1-select lieu sejour | Alpha |
| Autre | **BV** | W1-retour logement | Logical |
| Autre | **BW** | W1-select logement | Alpha |
| Autre | **BY** | W1-select TUP | Alpha |
| Autre | **BZ** | W1-select Base OCC | Alpha |
| Autre | **CA** | W1 N° Piece | Alpha |
| Autre | **CB** | W1 Date de delivrance | Date |
| Autre | **CC** | W1 Ville delivrance | Alpha |
| Autre | **CD** | W1 Proffession | Alpha |
| Autre | **CF** | W1 n dans la rue | Alpha |
| Autre | **CG** | W1 Nom de la rue | Alpha |
| Autre | **CH** | W1 Commune | Alpha |
| Autre | **CI** | W1 Code postal | Alpha |
| Autre | **CJ** | W1 Ville | Alpha |
| Autre | **CN** | Bouton Ok | Alpha |
| Autre | **CP** | W1-bouton creer une filiation | Alpha |

</details>

## 12. EXPRESSIONS

**17 / 17 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONDITION | 3 | 2 |
| CONSTANTE | 3 | 0 |
| OTHER | 9 | 0 |
| CAST_LOGIQUE | 2 | 0 |

### 12.2 Expressions cles par type

#### CONDITION (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 6 | `IF (> Mode attaque ecran [A]='','E'MODE,> Mode attaque ecran [A])` | [RM-002](#rm-RM-002) |
| CONDITION | 1 | `IF (GetParam ('NB_LIEU_SEJOUR')=0,'G',IF (GetParam ('NB_LIEU_SEJOUR')=1,GetParam ('CODE_LIEU_SEJOUR'),''))` | [RM-001](#rm-RM-001) |
| CONDITION | 9 | `W0-autorisation creation [O]='O' OR P0 Front/Back [G]='B'` | - |

#### CONSTANTE (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 8 | `'09'` | - |
| CONSTANTE | 5 | `51` | - |
| CONSTANTE | 4 | `55` | - |

#### OTHER (9 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 13 | `MnuShow ('Suivant',W0 active menu [F])` | - |
| OTHER | 12 | `MnuShow ('Precedent',W0 active menu [F])` | - |
| OTHER | 15 | `MnuShow ('Enr Suivant',W0 active menu [F])` | - |
| OTHER | 14 | `MnuShow ('Enr Precedent',W0 active menu [F])` | - |
| OTHER | 11 | `MnuShow ('Fin',W0 active menu [F])` | - |
| ... | | *+4 autres* | |

#### CAST_LOGIQUE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 17 | `'FALSE'LOG` | - |
| CAST_LOGIQUE | 16 | `'TRUE'LOG` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

**Chemin**: (pas de callers directs)

```mermaid
graph LR
    T387[387 Creation clients I...]
    style T387 fill:#58a6ff
    NONE[Aucun caller]
    NONE -.-> T387
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| - | (aucun) | - |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T387[387 Creation clients I...]
    style T387 fill:#58a6ff
    C359[359 Zoom VOL]
    T387 --> C359
    style C359 fill:#3fb950
    C309[309 Redirection touches]
    T387 --> C309
    style C309 fill:#3fb950
    C312[312 Determination Age ...]
    T387 --> C312
    style C312 fill:#3fb950
    C317[317 Recuperation du titre]
    T387 --> C317
    style C317 fill:#3fb950
    C354[354 Zoom inscription]
    T387 --> C354
    style C354 fill:#3fb950
    C357[357 Zoom logement]
    T387 --> C357
    style C357 fill:#3fb950
    C366[366 Zoom QualiteCP]
    T387 --> C366
    style C366 fill:#3fb950
    C72[72 Creation Fidelisation]
    T387 --> C72
    style C72 fill:#3fb950
    C84[84 Delete GMR cpte=0]
    T387 --> C84
    style C84 fill:#3fb950
    C85[85 Delete GMR adh=0]
    T387 --> C85
    style C85 fill:#3fb950
    C90[90 Maj Passport]
    T387 --> C90
    style C90 fill:#3fb950
    C97[97 Create TAI GM]
    T387 --> C97
    style C97 fill:#3fb950
    C355[355 Zoom langue]
    T387 --> C355
    style C355 fill:#3fb950
    C311[311 Langue]
    T387 --> C311
    style C311 fill:#3fb950
    C313[313 Caractères Interdi...]
    T387 --> C313
    style C313 fill:#3fb950
    C314[314 Caractères Interdi...]
    T387 --> C314
    style C314 fill:#3fb950
    C320[320 Verification Aut s...]
    T387 --> C320
    style C320 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [359](PBG-IDE-359.md) | Zoom VOL | 6 | Selection/consultation |
| [309](PBG-IDE-309.md) | Redirection touches | 4 | Sous-programme |
| [312](PBG-IDE-312.md) | Determination Age Debut Sejour | 4 | Sous-programme |
| [317](PBG-IDE-317.md) | Recuperation du titre | 3 | Recuperation donnees |
| [354](PBG-IDE-354.md) | Zoom inscription | 3 | Selection/consultation |
| [357](PBG-IDE-357.md) | Zoom logement | 3 | Selection/consultation |
| [366](PBG-IDE-366.md) | Zoom Qualite(C/P) | 3 | Selection/consultation |
| [72](PBG-IDE-72.md) |    Creation Fidelisation | 2 | Programme fidelite |
| [84](PBG-IDE-84.md) |    Delete GMR cpte=0 | 2 | Sous-programme |
| [85](PBG-IDE-85.md) |    Delete GMR adh=0 | 2 | Sous-programme |
| [90](PBG-IDE-90.md) |   Maj Passport | 2 | Mise a jour donnees |
| [97](PBG-IDE-97.md) | Create TAI GM | 2 | Sous-programme |
| [355](PBG-IDE-355.md) | Zoom langue | 2 | Selection/consultation |
| [311](PBG-IDE-311.md) | Langue ? | 1 | Sous-programme |
| [313](PBG-IDE-313.md) | Caractères Interdits (A20) - L | 1 | Validation saisie |
| [314](PBG-IDE-314.md) | Caractères Interdits (A20) - A | 1 | Validation saisie |
| [320](PBG-IDE-320.md) | Verification Aut sans ecran | 1 | Controle/validation |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 1361 | Programme volumineux |
| Expressions | 17 | Peu de logique |
| Tables WRITE | 8 | Fort impact donnees |
| Sous-programmes | 17 | Forte dependance |
| Ecrans visibles | 4 | Quelques ecrans |
| Code desactive | 0.4% (5 / 1361) | Code sain |
| Regles metier | 2 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (13 taches: 5 ecrans, 8 traitements)

- **Strategie** : Orchestrateur avec 5 ecrans (Razor/React) et 8 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 17 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Creation (4 taches: 1 ecran, 3 traitements)

- **Strategie** : Repository pattern avec Entity Framework Core.
- Insertion via `IRepository<T>.CreateAsync()`

#### Validation (2 taches: 0 ecran, 2 traitements)

- **Strategie** : FluentValidation avec validators specifiques.
- Chaque tache de validation -> un validator injectable

#### Calcul (4 taches: 0 ecran, 4 traitements)

- **Strategie** : Services de calcul purs (Domain Services).
- Migrer la logique de calcul (stock, compteurs, montants)

#### Consultation (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Composants de recherche/selection en modales.

#### Initialisation (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Constructeur/methode `InitAsync()` dans l'orchestrateur.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| gm-recherche_____gmr | Table WRITE (Database) | 1x | Schema + repository |
| gm-complet_______gmc | Table WRITE (Database) | 3x | Schema + repository |
| compte_gm________cgm | Table WRITE (Database) | 1x | Schema + repository |
| compteurs________cpt | Table WRITE (Database) | 1x | Schema + repository |
| historik_station | Table WRITE (Database) | 2x | Schema + repository |
| groupe_arr_dep___vol | Table WRITE (Database) | 1x | Schema + repository |
| heb_circuit______hci | Table WRITE (Database) | 2x | Schema + repository |
| import_mod | Table WRITE (Database) | 2x | Schema + repository |
| [Zoom VOL (IDE 359)](PBG-IDE-359.md) | Sous-programme | 6x | **CRITIQUE** - Selection/consultation |
| [Determination Age Debut Sejour (IDE 312)](PBG-IDE-312.md) | Sous-programme | 4x | **CRITIQUE** - Sous-programme |
| [Redirection touches (IDE 309)](PBG-IDE-309.md) | Sous-programme | 4x | **CRITIQUE** - Sous-programme |
| [Zoom logement (IDE 357)](PBG-IDE-357.md) | Sous-programme | 3x | **CRITIQUE** - Selection/consultation |
| [Zoom Qualite(C/P) (IDE 366)](PBG-IDE-366.md) | Sous-programme | 3x | **CRITIQUE** - Selection/consultation |
| [Recuperation du titre (IDE 317)](PBG-IDE-317.md) | Sous-programme | 3x | **CRITIQUE** - Recuperation donnees |
| [Zoom inscription (IDE 354)](PBG-IDE-354.md) | Sous-programme | 3x | **CRITIQUE** - Selection/consultation |
| [  Maj Passport (IDE 90)](PBG-IDE-90.md) | Sous-programme | 2x | Haute - Mise a jour donnees |
| [Create TAI GM (IDE 97)](PBG-IDE-97.md) | Sous-programme | 2x | Haute - Sous-programme |
| [Zoom langue (IDE 355)](PBG-IDE-355.md) | Sous-programme | 2x | Haute - Selection/consultation |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 11:36*
