# REF IDE 647 - Comptes speciaux

> **Analyse**: Phases 1-4 2026-02-03 13:23 -> 13:24 (17s) | Assemblage 13:24
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | REF |
| IDE Position | 647 |
| Nom Programme | Comptes speciaux |
| Fichier source | `Prg_647.xml` |
| Dossier IDE | Comptabilite |
| Taches | 18 (4 ecrans visibles) |
| Tables modifiees | 6 |
| Programmes appeles | 8 |
| :warning: Statut | **ORPHELIN_POTENTIEL** |

## 2. DESCRIPTION FONCTIONNELLE

**Comptes speciaux** assure la gestion complete de ce processus.

Le flux de traitement s'organise en **4 blocs fonctionnels** :

- **Traitement** (11 taches) : traitements metier divers
- **Creation** (5 taches) : insertion d'enregistrements en base (mouvements, prestations)
- **Validation** (1 tache) : controles et verifications de coherence
- **Consultation** (1 tache) : ecrans de recherche, selection et consultation

**Donnees modifiees** : 6 tables en ecriture (gm-recherche_____gmr, gm-complet_______gmc, hebergement______heb, compte_gm________cgm, compteurs________cpt, comptes_speciaux_spc_cash).

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (11 taches)

- **647** - (sans nom) **[[ECRAN]](#ecran-t1)**
- **647.1** - Recup Age Bebe
- **647.2** - (sans nom) **[[ECRAN]](#ecran-t3)**
- **647.4** - (sans nom) **[[ECRAN]](#ecran-t5)**
- **647.4.1** - Affectation des virtuelles
- **647.4.2** - Minusculage
- **647.4.3** - Minusculage
- **647.4.4** - (sans nom) **[[ECRAN]](#ecran-t9)**
- **647.4.5** - Veuillez patienter ... **[[ECRAN]](#ecran-t10)**
- **647.4.5.1** - Attribution N° Adherent Club
- **647.4.6** - (sans nom) **[[ECRAN]](#ecran-t17)**

Delegue a : [Recuperation du titre (IDE 658)](REF-IDE-658.md), [SP Caractères Interdits (IDE 780)](REF-IDE-780.md), [Determination Age Debut Sejou (IDE 659)](REF-IDE-659.md), [Appel programme (IDE 779)](REF-IDE-779.md)

#### Phase 2 : Consultation (1 tache)

- **647.3** - Recherche par nom **[[ECRAN]](#ecran-t4)**

Delegue a : [Recuperation du titre (IDE 658)](REF-IDE-658.md), [Zoom nationalite (IDE 649)](REF-IDE-649.md)

#### Phase 3 : Creation (5 taches)

- **647.4.5.2** - Creation Hebergement
- **647.4.5.3** - Creation Hebergement
- **647.4.5.4** - Creation Hebergement
- **647.4.5.5** - Creation Hebergement
- **647.4.5.6** - Creation Hebergement

#### Phase 4 : Validation (1 tache)

- **647.4.7** - verif date

Delegue a : [SP Caractères Interdits (IDE 780)](REF-IDE-780.md)

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| comptes_speciaux_spc_cash | R/**W**/L (5 usages) | Comptes GM (generaux) |
| gm-recherche_____gmr | R/**W**/L (4 usages) | Index de recherche |
| hebergement______heb | **W**/L (3 usages) | Hebergement (chambres) |
| gm-complet_______gmc | **W**/L (3 usages) |  |
| compte_gm________cgm | **W** (1 usages) | Comptes GM (generaux) |
| compteurs________cpt | **W** (1 usages) | Comptes GM (generaux) |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (11 taches)

Traitements internes.

---

#### <a id="t1"></a>647 - (sans nom) [[ECRAN]](#ecran-t1)

**Role** : Tache d'orchestration : point d'entree du programme (11 sous-taches). Coordonne l'enchainement des traitements.
**Ecran** : 183 x 29 DLU (MDI) | [Voir mockup](#ecran-t1)

<details>
<summary>10 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [647.1](#t2) | Recup Age Bebe | Traitement |
| [647.2](#t3) | (sans nom) **[[ECRAN]](#ecran-t3)** | Traitement |
| [647.4](#t5) | (sans nom) **[[ECRAN]](#ecran-t5)** | Traitement |
| [647.4.1](#t6) | Affectation des virtuelles | Traitement |
| [647.4.2](#t7) | Minusculage | Traitement |
| [647.4.3](#t8) | Minusculage | Traitement |
| [647.4.4](#t9) | (sans nom) **[[ECRAN]](#ecran-t9)** | Traitement |
| [647.4.5](#t10) | Veuillez patienter ... **[[ECRAN]](#ecran-t10)** | Traitement |
| [647.4.5.1](#t11) | Attribution N° Adherent Club | Traitement |
| [647.4.6](#t17) | (sans nom) **[[ECRAN]](#ecran-t17)** | Traitement |

</details>

---

#### <a id="t2"></a>647.1 - Recup Age Bebe

**Role** : Consultation/chargement : Recup Age Bebe.
**Variables liees** : S (W0 Age Bebe)

---

#### <a id="t3"></a>647.2 - (sans nom) [[ECRAN]](#ecran-t3)

**Role** : Traitement interne.
**Ecran** : 955 x 297 DLU (MDI) | [Voir mockup](#ecran-t3)

---

#### <a id="t5"></a>647.4 - (sans nom) [[ECRAN]](#ecran-t5)

**Role** : Traitement interne.
**Ecran** : 539 x 259 DLU (MDI) | [Voir mockup](#ecran-t5)

---

#### <a id="t6"></a>647.4.1 - Affectation des virtuelles

**Role** : Traitement : Affectation des virtuelles.

---

#### <a id="t7"></a>647.4.2 - Minusculage

**Role** : Traitement : Minusculage.

---

#### <a id="t8"></a>647.4.3 - Minusculage

**Role** : Traitement : Minusculage.

---

#### <a id="t9"></a>647.4.4 - (sans nom) [[ECRAN]](#ecran-t9)

**Role** : Traitement interne.
**Ecran** : 104 x 24 DLU (MDI) | [Voir mockup](#ecran-t9)

---

#### <a id="t10"></a>647.4.5 - Veuillez patienter ... [[ECRAN]](#ecran-t10)

**Role** : Traitement : Veuillez patienter ....
**Ecran** : 427 x 56 DLU (MDI) | [Voir mockup](#ecran-t10)

---

#### <a id="t11"></a>647.4.5.1 - Attribution N° Adherent Club

**Role** : Traitement : Attribution N° Adherent Club.

---

#### <a id="t17"></a>647.4.6 - (sans nom) [[ECRAN]](#ecran-t17)

**Role** : Traitement interne.
**Ecran** : 116 x 24 DLU (MDI) | [Voir mockup](#ecran-t17)


### 3.2 Consultation (1 tache)

Ecrans de recherche et consultation.

---

#### <a id="t4"></a>647.3 - Recherche par nom [[ECRAN]](#ecran-t4)

**Role** : Traitement : Recherche par nom.
**Ecran** : 562 x 90 DLU (MDI) | [Voir mockup](#ecran-t4)
**Variables liees** : O (W0 Recherche)
**Delegue a** : [Zoom nationalite (IDE 649)](REF-IDE-649.md)


### 3.3 Creation (5 taches)

Insertion de nouveaux enregistrements en base.

---

#### <a id="t12"></a>647.4.5.2 - Creation Hebergement

**Role** : Creation d'enregistrement : Creation Hebergement.

---

#### <a id="t13"></a>647.4.5.3 - Creation Hebergement

**Role** : Creation d'enregistrement : Creation Hebergement.

---

#### <a id="t14"></a>647.4.5.4 - Creation Hebergement

**Role** : Creation d'enregistrement : Creation Hebergement.

---

#### <a id="t15"></a>647.4.5.5 - Creation Hebergement

**Role** : Creation d'enregistrement : Creation Hebergement.

---

#### <a id="t16"></a>647.4.5.6 - Creation Hebergement

**Role** : Creation d'enregistrement : Creation Hebergement.


### 3.4 Validation (1 tache)

Controles de coherence : 1 tache verifie les donnees et conditions.

---

#### <a id="t18"></a>647.4.7 - verif date

**Role** : Verification : verif date.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: (aucun)
- **Appelle**: 8 programmes | **Tables**: 9 (W:6 R:4 L:5) | **Taches**: 18 | **Expressions**: 12

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (4 / 18)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 647.2 | 647.2 | (sans nom) | MDI | 955 | 297 | Traitement |
| 2 | 647.3 | 647.3 | Recherche par nom | MDI | 562 | 90 | Consultation |
| 3 | 647.4 | 647.4 | (sans nom) | MDI | 539 | 259 | Traitement |
| 4 | 647.4.5 | 647.4.5 | Veuillez patienter ... | MDI | 427 | 56 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t3"></a>647.2 - (sans nom)
**Tache** : [647.2](#t3) | **Type** : MDI | **Dimensions** : 955 x 297 DLU
**Bloc** : Traitement | **Titre IDE** : (sans nom)

<!-- FORM-DATA:
{
    "width":  955,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  3,
                         "type":  "label",
                         "var":  "",
                         "y":  2,
                         "w":  950,
                         "fmt":  "",
                         "name":  "",
                         "h":  19,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  6,
                         "type":  "label",
                         "var":  "",
                         "y":  23,
                         "w":  940,
                         "fmt":  "",
                         "name":  "",
                         "h":  245,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  644,
                         "type":  "label",
                         "var":  "",
                         "y":  187,
                         "w":  290,
                         "fmt":  "",
                         "name":  "",
                         "h":  62,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  647,
                         "type":  "label",
                         "var":  "",
                         "y":  188,
                         "w":  284,
                         "fmt":  "",
                         "name":  "",
                         "h":  75,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  685,
                         "type":  "label",
                         "var":  "",
                         "y":  193,
                         "w":  196,
                         "fmt":  "",
                         "name":  "",
                         "h":  48,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  688,
                         "type":  "label",
                         "var":  "",
                         "y":  194,
                         "w":  43,
                         "fmt":  "",
                         "name":  "",
                         "h":  46,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  733,
                         "type":  "label",
                         "var":  "",
                         "y":  196,
                         "w":  139,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "7",
                         "text":  "Création",
                         "parent":  null
                     },
                     {
                         "x":  733,
                         "type":  "label",
                         "var":  "",
                         "y":  207,
                         "w":  139,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "7",
                         "text":  "Modification",
                         "parent":  null
                     },
                     {
                         "x":  733,
                         "type":  "label",
                         "var":  "",
                         "y":  218,
                         "w":  139,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "7",
                         "text":  "Recherche",
                         "parent":  null
                     },
                     {
                         "x":  733,
                         "type":  "label",
                         "var":  "",
                         "y":  229,
                         "w":  139,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "7",
                         "text":  "Création Cash",
                         "parent":  null
                     },
                     {
                         "x":  704,
                         "type":  "label",
                         "var":  "",
                         "y":  249,
                         "w":  120,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "Votre choix",
                         "parent":  null
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  270,
                         "w":  953,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  394,
                         "type":  "label",
                         "var":  "",
                         "y":  25,
                         "w":  540,
                         "fmt":  "",
                         "name":  "",
                         "h":  159,
                         "color":  "195",
                         "text":  "Fiche adherent",
                         "parent":  null
                     },
                     {
                         "x":  419,
                         "type":  "label",
                         "var":  "",
                         "y":  36,
                         "w":  80,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Nom",
                         "parent":  17
                     },
                     {
                         "x":  419,
                         "type":  "label",
                         "var":  "",
                         "y":  49,
                         "w":  78,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Prénom",
                         "parent":  17
                     },
                     {
                         "x":  751,
                         "type":  "label",
                         "var":  "",
                         "y":  51,
                         "w":  61,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Qualité",
                         "parent":  17
                     },
                     {
                         "x":  419,
                         "type":  "label",
                         "var":  "",
                         "y":  62,
                         "w":  53,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Titre",
                         "parent":  17
                     },
                     {
                         "x":  667,
                         "type":  "label",
                         "var":  "",
                         "y":  62,
                         "w":  77,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "Crédit bar",
                         "parent":  17
                     },
                     {
                         "x":  419,
                         "type":  "label",
                         "var":  "",
                         "y":  76,
                         "w":  98,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Séjour du",
                         "parent":  17
                     },
                     {
                         "x":  667,
                         "type":  "label",
                         "var":  "",
                         "y":  76,
                         "w":  77,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "au",
                         "parent":  17
                     },
                     {
                         "x":  419,
                         "type":  "label",
                         "var":  "",
                         "y":  92,
                         "w":  122,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "N° Adhérent",
                         "parent":  17
                     },
                     {
                         "x":  787,
                         "type":  "label",
                         "var":  "",
                         "y":  92,
                         "w":  35,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Fil",
                         "parent":  17
                     },
                     {
                         "x":  419,
                         "type":  "label",
                         "var":  "",
                         "y":  106,
                         "w":  184,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Date de Naissance",
                         "parent":  17
                     },
                     {
                         "x":  419,
                         "type":  "label",
                         "var":  "",
                         "y":  120,
                         "w":  109,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Nationalité",
                         "parent":  17
                     },
                     {
                         "x":  607,
                         "type":  "label",
                         "var":  "",
                         "y":  120,
                         "w":  203,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Group Meetings \u0026 Events",
                         "parent":  17
                     },
                     {
                         "x":  24,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "110",
                         "w":  350,
                         "y":  27,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  11,
                         "h":  215,
                         "cols":  [
                                      {
                                          "title":  "Nom",
                                          "layer":  1,
                                          "w":  187
                                      },
                                      {
                                          "title":  "Prénom",
                                          "layer":  2,
                                          "w":  132
                                      }
                                  ],
                         "rows":  2
                     },
                     {
                         "x":  413,
                         "type":  "label",
                         "var":  "",
                         "y":  133,
                         "w":  442,
                         "fmt":  "",
                         "name":  "",
                         "h":  45,
                         "color":  "195",
                         "text":  "Adresse",
                         "parent":  null
                     },
                     {
                         "x":  30,
                         "type":  "edit",
                         "var":  "",
                         "y":  41,
                         "w":  176,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  42
                     },
                     {
                         "x":  218,
                         "type":  "edit",
                         "var":  "",
                         "y":  41,
                         "w":  120,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  42
                     },
                     {
                         "x":  529,
                         "type":  "edit",
                         "var":  "",
                         "y":  62,
                         "w":  40,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  17
                     },
                     {
                         "x":  832,
                         "type":  "edit",
                         "var":  "",
                         "y":  93,
                         "w":  54,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  17
                     },
                     {
                         "x":  844,
                         "type":  "edit",
                         "var":  "",
                         "y":  49,
                         "w":  40,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  17
                     },
                     {
                         "x":  613,
                         "type":  "edit",
                         "var":  "",
                         "y":  106,
                         "w":  133,
                         "fmt":  "##/##/####Z",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  17
                     },
                     {
                         "x":  529,
                         "type":  "edit",
                         "var":  "",
                         "y":  120,
                         "w":  43,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  17
                     },
                     {
                         "x":  437,
                         "type":  "edit",
                         "var":  "",
                         "y":  144,
                         "w":  410,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  47
                     },
                     {
                         "x":  437,
                         "type":  "edit",
                         "var":  "",
                         "y":  154,
                         "w":  410,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  47
                     },
                     {
                         "x":  437,
                         "type":  "edit",
                         "var":  "",
                         "y":  163,
                         "w":  410,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  47
                     },
                     {
                         "x":  529,
                         "type":  "edit",
                         "var":  "",
                         "y":  76,
                         "w":  133,
                         "fmt":  "##/##/####Z",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  17
                     },
                     {
                         "x":  751,
                         "type":  "edit",
                         "var":  "",
                         "y":  76,
                         "w":  133,
                         "fmt":  "##/##/####Z",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  17
                     },
                     {
                         "x":  838,
                         "type":  "edit",
                         "var":  "",
                         "y":  248,
                         "w":  26,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  10,
                         "type":  "edit",
                         "var":  "",
                         "y":  6,
                         "w":  274,
                         "fmt":  "20",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  669,
                         "type":  "edit",
                         "var":  "",
                         "y":  6,
                         "w":  274,
                         "fmt":  "WWW DD MMM YYYYT",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  529,
                         "type":  "edit",
                         "var":  "",
                         "y":  36,
                         "w":  186,
                         "fmt":  "U15",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  17
                     },
                     {
                         "x":  529,
                         "type":  "edit",
                         "var":  "",
                         "y":  49,
                         "w":  186,
                         "fmt":  "UX9",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  17
                     },
                     {
                         "x":  529,
                         "type":  "edit",
                         "var":  "",
                         "y":  92,
                         "w":  222,
                         "fmt":  "18",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  17
                     },
                     {
                         "x":  409,
                         "type":  "image",
                         "var":  "",
                         "y":  184,
                         "w":  173,
                         "fmt":  "",
                         "name":  "",
                         "h":  68,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  693,
                         "type":  "button",
                         "var":  "",
                         "y":  196,
                         "w":  30,
                         "fmt":  "C",
                         "name":  "C",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  693,
                         "type":  "button",
                         "var":  "",
                         "y":  207,
                         "w":  30,
                         "fmt":  "M",
                         "name":  "M",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  693,
                         "type":  "button",
                         "var":  "",
                         "y":  218,
                         "w":  30,
                         "fmt":  "R",
                         "name":  "R",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  6,
                         "type":  "button",
                         "var":  "",
                         "y":  273,
                         "w":  154,
                         "fmt":  "\u0026Quitter",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  16
                     },
                     {
                         "x":  173,
                         "type":  "button",
                         "var":  "",
                         "y":  274,
                         "w":  154,
                         "fmt":  "\u0026Selectionner",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  693,
                         "type":  "button",
                         "var":  "",
                         "y":  229,
                         "w":  30,
                         "fmt":  "A",
                         "name":  "A",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  832,
                         "type":  "checkbox",
                         "var":  "",
                         "y":  120,
                         "w":  26,
                         "fmt":  "",
                         "name":  "spc_vente_hors_place",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  17
                     },
                     {
                         "x":  751,
                         "type":  "edit",
                         "var":  "",
                         "y":  62,
                         "w":  133,
                         "fmt":  "N12.3",
                         "name":  "spc_credit_bar",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  17
                     }
                 ],
    "taskId":  "647.2",
    "height":  297
}
-->

<details>
<summary><strong>Champs : 20 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 30,41 | (sans nom) | - | edit |
| 218,41 | (sans nom) | - | edit |
| 529,62 | (sans nom) | - | edit |
| 832,93 | (sans nom) | - | edit |
| 844,49 | (sans nom) | - | edit |
| 613,106 | ##/##/####Z | - | edit |
| 529,120 | (sans nom) | - | edit |
| 437,144 | (sans nom) | - | edit |
| 437,154 | (sans nom) | - | edit |
| 437,163 | (sans nom) | - | edit |
| 529,76 | ##/##/####Z | - | edit |
| 751,76 | ##/##/####Z | - | edit |
| 838,248 | (sans nom) | - | edit |
| 10,6 | 20 | - | edit |
| 669,6 | WWW DD MMM YYYYT | - | edit |
| 529,36 | U15 | - | edit |
| 529,49 | UX9 | - | edit |
| 529,92 | 18 | - | edit |
| 832,120 | spc_vente_hors_place | - | checkbox |
| 751,62 | spc_credit_bar | - | edit |

</details>

<details>
<summary><strong>Boutons : 6 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| C | 693,196 | Bouton fonctionnel |
| M | 693,207 | Bouton fonctionnel |
| R | 693,218 | Bouton fonctionnel |
| Quitter | 6,273 | Quitte le programme |
| Selectionner | 173,274 | Ouvre la selection |
| A | 693,229 | Bouton fonctionnel |

</details>

---

#### <a id="ecran-t4"></a>647.3 - Recherche par nom
**Tache** : [647.3](#t4) | **Type** : MDI | **Dimensions** : 562 x 90 DLU
**Bloc** : Consultation | **Titre IDE** : Recherche par nom

<!-- FORM-DATA:
{
    "width":  562,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  60,
                         "type":  "label",
                         "var":  "",
                         "y":  14,
                         "w":  441,
                         "fmt":  "",
                         "name":  "",
                         "h":  40,
                         "color":  "4",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  62,
                         "type":  "label",
                         "var":  "",
                         "y":  15,
                         "w":  437,
                         "fmt":  "",
                         "name":  "",
                         "h":  38,
                         "color":  "4",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  126,
                         "type":  "label",
                         "var":  "",
                         "y":  28,
                         "w":  123,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "4",
                         "text":  "Recherche",
                         "parent":  null
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  66,
                         "w":  558,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  252,
                         "type":  "edit",
                         "var":  "",
                         "y":  28,
                         "w":  182,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  171,
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
                         "x":  6,
                         "type":  "button",
                         "var":  "",
                         "y":  69,
                         "w":  154,
                         "fmt":  "\u0026Rechercher",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "647.3",
    "height":  90
}
-->

<details>
<summary><strong>Champs : 1 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 252,28 | (sans nom) | - | edit |

</details>

<details>
<summary><strong>Boutons : 2 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Abandonner | 171,69 | Annule et retour au menu |
| Rechercher | 6,69 | Ouvre la selection |

</details>

---

#### <a id="ecran-t5"></a>647.4 - (sans nom)
**Tache** : [647.4](#t5) | **Type** : MDI | **Dimensions** : 539 x 259 DLU
**Bloc** : Traitement | **Titre IDE** : (sans nom)

<!-- FORM-DATA:
{
    "width":  539,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  1,
                         "type":  "label",
                         "var":  "",
                         "y":  1,
                         "w":  535,
                         "fmt":  "",
                         "name":  "",
                         "h":  19,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  232,
                         "w":  538,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  32,
                         "type":  "label",
                         "var":  "",
                         "y":  26,
                         "w":  474,
                         "fmt":  "",
                         "name":  "",
                         "h":  202,
                         "color":  "195",
                         "text":  "Modification",
                         "parent":  null
                     },
                     {
                         "x":  55,
                         "type":  "label",
                         "var":  "",
                         "y":  37,
                         "w":  78,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Nom",
                         "parent":  5
                     },
                     {
                         "x":  55,
                         "type":  "label",
                         "var":  "",
                         "y":  51,
                         "w":  78,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Prénom",
                         "parent":  5
                     },
                     {
                         "x":  55,
                         "type":  "label",
                         "var":  "",
                         "y":  63,
                         "w":  53,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Titre",
                         "parent":  5
                     },
                     {
                         "x":  285,
                         "type":  "label",
                         "var":  "",
                         "y":  64,
                         "w":  61,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Qualité",
                         "parent":  5
                     },
                     {
                         "x":  55,
                         "type":  "label",
                         "var":  "",
                         "y":  82,
                         "w":  98,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Crédit Bar",
                         "parent":  5
                     },
                     {
                         "x":  55,
                         "type":  "label",
                         "var":  "",
                         "y":  100,
                         "w":  98,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Séjour du",
                         "parent":  5
                     },
                     {
                         "x":  319,
                         "type":  "label",
                         "var":  "",
                         "y":  101,
                         "w":  27,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "au",
                         "parent":  5
                     },
                     {
                         "x":  55,
                         "type":  "label",
                         "var":  "",
                         "y":  115,
                         "w":  122,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "N° Adhérent",
                         "parent":  5
                     },
                     {
                         "x":  401,
                         "type":  "label",
                         "var":  "",
                         "y":  115,
                         "w":  24,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Fil",
                         "parent":  5
                     },
                     {
                         "x":  55,
                         "type":  "label",
                         "var":  "",
                         "y":  129,
                         "w":  184,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Date de Naissance",
                         "parent":  5
                     },
                     {
                         "x":  55,
                         "type":  "label",
                         "var":  "",
                         "y":  145,
                         "w":  109,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Nationalité",
                         "parent":  5
                     },
                     {
                         "x":  230,
                         "type":  "label",
                         "var":  "",
                         "y":  145,
                         "w":  203,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Group Meetings \u0026 Events",
                         "parent":  5
                     },
                     {
                         "x":  48,
                         "type":  "label",
                         "var":  "",
                         "y":  169,
                         "w":  442,
                         "fmt":  "",
                         "name":  "",
                         "h":  55,
                         "color":  "195",
                         "text":  "Adresse",
                         "parent":  null
                     },
                     {
                         "x":  177,
                         "type":  "edit",
                         "var":  "",
                         "y":  37,
                         "w":  182,
                         "fmt":  "",
                         "name":  "W1 nom",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  177,
                         "type":  "edit",
                         "var":  "",
                         "y":  51,
                         "w":  126,
                         "fmt":  "",
                         "name":  "W1 prenom",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  177,
                         "type":  "combobox",
                         "var":  "",
                         "y":  63,
                         "w":  67,
                         "fmt":  "",
                         "name":  "W1 titre",
                         "h":  12,
                         "color":  "",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  361,
                         "type":  "combobox",
                         "var":  "",
                         "y":  63,
                         "w":  67,
                         "fmt":  "",
                         "name":  "W1 qualite",
                         "h":  12,
                         "color":  "",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  181,
                         "type":  "edit",
                         "var":  "",
                         "y":  82,
                         "w":  126,
                         "fmt":  "N12.3",
                         "name":  "W1 Credit Bar",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  177,
                         "type":  "edit",
                         "var":  "",
                         "y":  100,
                         "w":  126,
                         "fmt":  "##/##/####",
                         "name":  "",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  361,
                         "type":  "edit",
                         "var":  "",
                         "y":  100,
                         "w":  126,
                         "fmt":  "##/##/####Z",
                         "name":  "W1 date fin",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  177,
                         "type":  "edit",
                         "var":  "",
                         "y":  115,
                         "w":  126,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  324,
                         "type":  "edit",
                         "var":  "",
                         "y":  115,
                         "w":  26,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  439,
                         "type":  "edit",
                         "var":  "",
                         "y":  115,
                         "w":  48,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  224,
                         "type":  "edit",
                         "var":  "",
                         "y":  129,
                         "w":  126,
                         "fmt":  "##/##/####Z",
                         "name":  "W1 date de naissance",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  177,
                         "type":  "edit",
                         "var":  "",
                         "y":  145,
                         "w":  37,
                         "fmt":  "",
                         "name":  "W1 nationnalite",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  93,
                         "type":  "edit",
                         "var":  "",
                         "y":  184,
                         "w":  350,
                         "fmt":  "",
                         "name":  "W1 rue",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  31
                     },
                     {
                         "x":  93,
                         "type":  "edit",
                         "var":  "",
                         "y":  197,
                         "w":  350,
                         "fmt":  "",
                         "name":  "W1 commune",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  31
                     },
                     {
                         "x":  93,
                         "type":  "edit",
                         "var":  "",
                         "y":  210,
                         "w":  350,
                         "fmt":  "",
                         "name":  "W1 ville/bureau dist",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  31
                     },
                     {
                         "x":  12,
                         "type":  "button",
                         "var":  "",
                         "y":  235,
                         "w":  154,
                         "fmt":  "\u0026Ok",
                         "name":  "Bouton Ok",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  8,
                         "type":  "edit",
                         "var":  "",
                         "y":  5,
                         "w":  274,
                         "fmt":  "20",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  329,
                         "type":  "edit",
                         "var":  "",
                         "y":  5,
                         "w":  203,
                         "fmt":  "WWW DD MMM YYYYT",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  170,
                         "type":  "button",
                         "var":  "",
                         "y":  235,
                         "w":  154,
                         "fmt":  "A\u0026bandonner",
                         "name":  "B_Abandonner",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  455,
                         "type":  "checkbox",
                         "var":  "",
                         "y":  145,
                         "w":  26,
                         "fmt":  "",
                         "name":  "spc_vente_hors_place",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  5
                     }
                 ],
    "taskId":  "647.4",
    "height":  259
}
-->

<details>
<summary><strong>Champs : 18 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 177,37 | W1 nom | - | edit |
| 177,51 | W1 prenom | - | edit |
| 177,63 | W1 titre | - | combobox |
| 361,63 | W1 qualite | - | combobox |
| 181,82 | W1 Credit Bar | - | edit |
| 177,100 | ##/##/#### | - | edit |
| 361,100 | W1 date fin | - | edit |
| 177,115 | (sans nom) | - | edit |
| 324,115 | (sans nom) | - | edit |
| 439,115 | (sans nom) | - | edit |
| 224,129 | W1 date de naissance | - | edit |
| 177,145 | W1 nationnalite | - | edit |
| 93,184 | W1 rue | - | edit |
| 93,197 | W1 commune | - | edit |
| 93,210 | W1 ville/bureau dist | - | edit |
| 8,5 | 20 | - | edit |
| 329,5 | WWW DD MMM YYYYT | - | edit |
| 455,145 | spc_vente_hors_place | - | checkbox |

</details>

<details>
<summary><strong>Boutons : 2 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Ok | 12,235 | Valide la saisie et enregistre |
| Abandonner | 170,235 | Annule et retour au menu |

</details>

---

#### <a id="ecran-t10"></a>647.4.5 - Veuillez patienter ...
**Tache** : [647.4.5](#t10) | **Type** : MDI | **Dimensions** : 427 x 56 DLU
**Bloc** : Traitement | **Titre IDE** : Veuillez patienter ...

<!-- FORM-DATA:
{
    "width":  427,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  3,
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
                         "x":  120,
                         "type":  "label",
                         "var":  "",
                         "y":  10,
                         "w":  275,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "7",
                         "text":  "Traitement en cours ...",
                         "parent":  null
                     },
                     {
                         "x":  3,
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
                         "x":  88,
                         "type":  "label",
                         "var":  "",
                         "y":  39,
                         "w":  240,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Enregistrement en cours",
                         "parent":  null
                     },
                     {
                         "x":  4,
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
    "taskId":  "647.4.5",
    "height":  56
}
-->

## 9. NAVIGATION

### 9.1 Enchainement des ecrans

```mermaid
flowchart TD
    START([Entree])
    style START fill:#3fb950
    VF3[647.2 sans nom]
    style VF3 fill:#58a6ff
    VF4[647.3 Recherche par nom]
    style VF4 fill:#58a6ff
    VF5[647.4 sans nom]
    style VF5 fill:#58a6ff
    VF10[647.4.5 Veuillez patienter...]
    style VF10 fill:#58a6ff
    EXT658[IDE 658 Recuperation d...]
    style EXT658 fill:#3fb950
    EXT780[IDE 780 SP Caractères ...]
    style EXT780 fill:#3fb950
    EXT646[IDE 646 Création compt...]
    style EXT646 fill:#3fb950
    EXT648[IDE 648 Create TAI Com...]
    style EXT648 fill:#3fb950
    EXT649[IDE 649 Zoom nationalite]
    style EXT649 fill:#3fb950
    EXT659[IDE 659 Determination ...]
    style EXT659 fill:#3fb950
    EXT779[IDE 779 Appel programme]
    style EXT779 fill:#3fb950
    EXT825[IDE 825 Incrémentation...]
    style EXT825 fill:#3fb950
    FIN([Sortie])
    style FIN fill:#f85149
    START --> VF3
    VF3 -->|Recuperation donnees| EXT658
    VF3 -->|Validation saisie| EXT780
    VF3 -->|Sous-programme| EXT646
    VF3 -->|Sous-programme| EXT648
    VF3 -->|Selection/consultation| EXT649
    VF3 -->|Sous-programme| EXT659
    VF3 -->|Sous-programme| EXT779
    VF3 -->|Sous-programme| EXT825
    EXT825 --> FIN
```

**Detail par enchainement :**

| Depuis | Action | Vers | Retour |
|--------|--------|------|--------|
|  | Recuperation donnees | [Recuperation du titre (IDE 658)](REF-IDE-658.md) | Retour ecran |
|  | Validation saisie | [SP Caractères Interdits (IDE 780)](REF-IDE-780.md) | Retour ecran |
|  | Sous-programme | [Création compte cash (IDE 646)](REF-IDE-646.md) | Retour ecran |
|  | Sous-programme | [Create TAI Comptes speciaux (IDE 648)](REF-IDE-648.md) | Retour ecran |
|  | Selection/consultation | [Zoom nationalite (IDE 649)](REF-IDE-649.md) | Retour ecran |
|  | Sous-programme | [Determination Age Debut Sejou (IDE 659)](REF-IDE-659.md) | Retour ecran |
|  | Sous-programme | [Appel programme (IDE 779)](REF-IDE-779.md) | Retour ecran |
|  | Sous-programme | [Incrémentation compteur num (IDE 825)](REF-IDE-825.md) | Retour ecran |

### 9.3 Structure hierarchique (18 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **647.1** | [**(sans nom)** (647)](#t1) [mockup](#ecran-t1) | MDI | 183x29 | Traitement |
| 647.1.1 | [Recup Age Bebe (647.1)](#t2) | MDI | - | |
| 647.1.2 | [(sans nom) (647.2)](#t3) [mockup](#ecran-t3) | MDI | 955x297 | |
| 647.1.3 | [(sans nom) (647.4)](#t5) [mockup](#ecran-t5) | MDI | 539x259 | |
| 647.1.4 | [Affectation des virtuelles (647.4.1)](#t6) | MDI | - | |
| 647.1.5 | [Minusculage (647.4.2)](#t7) | MDI | - | |
| 647.1.6 | [Minusculage (647.4.3)](#t8) | MDI | - | |
| 647.1.7 | [(sans nom) (647.4.4)](#t9) [mockup](#ecran-t9) | MDI | 104x24 | |
| 647.1.8 | [Veuillez patienter ... (647.4.5)](#t10) [mockup](#ecran-t10) | MDI | 427x56 | |
| 647.1.9 | [Attribution N° Adherent Club (647.4.5.1)](#t11) | MDI | - | |
| 647.1.10 | [(sans nom) (647.4.6)](#t17) [mockup](#ecran-t17) | MDI | 116x24 | |
| **647.2** | [**Recherche par nom** (647.3)](#t4) [mockup](#ecran-t4) | MDI | 562x90 | Consultation |
| **647.3** | [**Creation Hebergement** (647.4.5.2)](#t12) | MDI | - | Creation |
| 647.3.1 | [Creation Hebergement (647.4.5.3)](#t13) | MDI | - | |
| 647.3.2 | [Creation Hebergement (647.4.5.4)](#t14) | MDI | - | |
| 647.3.3 | [Creation Hebergement (647.4.5.5)](#t15) | MDI | - | |
| 647.3.4 | [Creation Hebergement (647.4.5.6)](#t16) | MDI | - | |
| **647.4** | [**verif date** (647.4.7)](#t18) | - | - | Validation |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Scroll]
    UPDATE[MAJ 6 tables]
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

### Tables utilisees (9)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 30 | gm-recherche_____gmr | Index de recherche | DB | R | **W** | L | 4 |
| 31 | gm-complet_______gmc |  | DB |   | **W** | L | 3 |
| 34 | hebergement______heb | Hebergement (chambres) | DB |   | **W** | L | 3 |
| 47 | compte_gm________cgm | Comptes GM (generaux) | DB |   | **W** |   | 1 |
| 68 | compteurs________cpt | Comptes GM (generaux) | DB |   | **W** |   | 1 |
| 113 | tables_village |  | DB | R |   |   | 1 |
| 119 | tables_pays_tel_ |  | DB |   |   | L | 1 |
| 718 | utilisateur______uti |  | DB | R |   |   | 1 |
| 758 | comptes_speciaux_spc_cash | Comptes GM (generaux) | DB | R | **W** | L | 5 |

### Colonnes par table (4 / 8 tables avec colonnes identifiees)

<details>
<summary>Table 30 - gm-recherche_____gmr (R/**W**/L) - 4 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 31 - gm-complet_______gmc (**W**/L) - 3 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 34 - hebergement______heb (**W**/L) - 3 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 47 - compte_gm________cgm (**W**) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | W3 ret.lien compte | W | Numeric |
| B | W2 n° compte | W | Numeric |
| BF | V.Existe autre compte ? | W | Logical |
| H | < compte | W | Numeric |
| N | W1 compte fictif | W | Logical |
| R | W1 n° compte | W | Numeric |

</details>

<details>
<summary>Table 68 - compteurs________cpt (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 113 - tables_village (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| E | > nom village | R | Alpha |
| F | > village TAI | R | Alpha |

</details>

<details>
<summary>Table 718 - utilisateur______uti (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | > societe | R | Alpha |
| B | > Decimales | R | Numeric |
| C | > masque | R | Alpha |
| D | > code devise | R | Alpha |
| E | > nom village | R | Alpha |
| F | > village TAI | R | Alpha |
| G | > TAI Obligatoire | R | Alpha |
| H | < compte | R | Numeric |
| I | < filiation | R | Numeric |
| J | < detecte | R | Alpha |
| K | < chaine | R | Alpha |
| L | < cpte spec select | R | Logical |
| M | W0 Choix Action | R | Alpha |
| N | W0 pas d'enreg | R | Alpha |
| O | W0 Recherche | R | Alpha |
| P | W0 societe | R | Alpha |
| Q | W0 Controle Nom | R | Alpha |
| R | W0 Controle Prenom | R | Alpha |
| S | W0 Age Bebe | R | Numeric |

</details>

<details>
<summary>Table 758 - comptes_speciaux_spc_cash (R/**W**/L) - 5 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | W1 choix action | W | Alpha |
| B | W1 fin tache | W | Alpha |
| C | v. titre | W | Alpha |
| D | W1 qualite | W | Alpha |
| E | W1 date debut | W | Date |
| F | W1 date fin | W | Date |
| G | W1 n° adherent | W | Numeric |
| H | W1 lettre controle | W | Alpha |
| I | W1 filiation | W | Numeric |
| J | W1 date de naissance | W | Date |
| K | W1 nationnalite | W | Alpha |
| L | W1 Group Meeting | W | Logical |
| M | W1 Credit Bar | W | Numeric |
| N | W1 compte fictif | W | Logical |
| O | W1 rue | W | Alpha |
| P | W1 commune | W | Alpha |
| Q | W1 ville/bureau dist | W | Alpha |
| R | W1 n° compte | W | Numeric |
| S | W1 filiation | W | Numeric |
| T | W1 choix action | W | Alpha |
| U | W1 confirmation | W | Logical |
| V | W1 autre filiation | W | Alpha |
| W | W1 Age | W | Numeric |
| X | W1 Age Codifie | W | Alpha |
| Y | W1 Nb mois | W | Numeric |
| Z | W1 langue parlee | W | Alpha |
| BA | W1 ret lien national | W | Numeric |
| BB | W1 chaine correcte | W | Alpha |
| BC | v. titre | W | Alpha |
| BD | v. Saisir Forfait TAI | W | Numeric |
| BE | Bouton Ok | W | Alpha |
| BF | V.Existe autre compte ? | W | Logical |

</details>

## 11. VARIABLES

### 11.1 Variables de session (3)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| BC | v. titre | Alpha | - |
| BD | v. Saisir Forfait TAI | Numeric | - |
| BF | V.Existe autre compte ? | Logical | - |

### 11.2 Variables de travail (7)

Variables internes au programme.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| M | W0 Choix Action | Alpha | 5x calcul interne |
| N | W0 pas d'enreg | Alpha | - |
| O | W0 Recherche | Alpha | - |
| P | W0 societe | Alpha | - |
| Q | W0 Controle Nom | Alpha | - |
| R | W0 Controle Prenom | Alpha | - |
| S | W0 Age Bebe | Numeric | - |

### 11.3 Autres (22)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | > societe | Alpha | 1x refs |
| B | > Decimales | Numeric | - |
| C | > masque | Alpha | - |
| D | > code devise | Alpha | - |
| E | > nom village | Alpha | - |
| F | > village TAI | Alpha | - |
| G | > TAI Obligatoire | Alpha | - |
| H | < compte | Numeric | - |
| I | < filiation | Numeric | - |
| J | < detecte | Alpha | - |
| K | < chaine | Alpha | - |
| L | < cpte spec select | Logical | 1x refs |
| T | W1 choix action | Alpha | - |
| U | W1 confirmation | Logical | - |
| V | W1 autre filiation | Alpha | - |
| W | W1 Age | Numeric | - |
| X | W1 Age Codifie | Alpha | - |
| Y | W1 Nb mois | Numeric | - |
| Z | W1 langue parlee | Alpha | - |
| BA | W1 ret lien national | Numeric | - |
| BB | W1 chaine correcte | Alpha | - |
| BE | Bouton Ok | Alpha | - |

<details>
<summary>Toutes les 32 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| W0 | **M** | W0 Choix Action | Alpha |
| W0 | **N** | W0 pas d'enreg | Alpha |
| W0 | **O** | W0 Recherche | Alpha |
| W0 | **P** | W0 societe | Alpha |
| W0 | **Q** | W0 Controle Nom | Alpha |
| W0 | **R** | W0 Controle Prenom | Alpha |
| W0 | **S** | W0 Age Bebe | Numeric |
| V. | **BC** | v. titre | Alpha |
| V. | **BD** | v. Saisir Forfait TAI | Numeric |
| V. | **BF** | V.Existe autre compte ? | Logical |
| Autre | **A** | > societe | Alpha |
| Autre | **B** | > Decimales | Numeric |
| Autre | **C** | > masque | Alpha |
| Autre | **D** | > code devise | Alpha |
| Autre | **E** | > nom village | Alpha |
| Autre | **F** | > village TAI | Alpha |
| Autre | **G** | > TAI Obligatoire | Alpha |
| Autre | **H** | < compte | Numeric |
| Autre | **I** | < filiation | Numeric |
| Autre | **J** | < detecte | Alpha |
| Autre | **K** | < chaine | Alpha |
| Autre | **L** | < cpte spec select | Logical |
| Autre | **T** | W1 choix action | Alpha |
| Autre | **U** | W1 confirmation | Logical |
| Autre | **V** | W1 autre filiation | Alpha |
| Autre | **W** | W1 Age | Numeric |
| Autre | **X** | W1 Age Codifie | Alpha |
| Autre | **Y** | W1 Nb mois | Numeric |
| Autre | **Z** | W1 langue parlee | Alpha |
| Autre | **BA** | W1 ret lien national | Numeric |
| Autre | **BB** | W1 chaine correcte | Alpha |
| Autre | **BE** | Bouton Ok | Alpha |

</details>

## 12. EXPRESSIONS

**12 / 12 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONSTANTE | 4 | 0 |
| CONDITION | 7 | 0 |
| REFERENCE_VG | 1 | 0 |

### 12.2 Expressions cles par type

#### CONSTANTE (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 7 | `'P'` | - |
| CONSTANTE | 9 | `'S'` | - |
| CONSTANTE | 1 | `'S'` | - |
| CONSTANTE | 6 | `'N'` | - |

#### CONDITION (7 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 8 | `< cpte spec select [L]` | - |
| CONDITION | 10 | `W0 Choix Action [M]='A'` | - |
| CONDITION | 11 | `> societe [A]` | - |
| CONDITION | 5 | `W0 Choix Action [M]='M' OR W0 Choix Action [M]='C'` | - |
| CONDITION | 2 | `W0 Choix Action [M]='F'` | - |
| ... | | *+2 autres* | |

#### REFERENCE_VG (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 12 | `VG1` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

**Chemin**: (pas de callers directs)

```mermaid
graph LR
    T647[647 Comptes speciaux]
    style T647 fill:#58a6ff
    NONE[Aucun caller]
    NONE -.-> T647
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| - | (aucun) | - |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T647[647 Comptes speciaux]
    style T647 fill:#58a6ff
    C658[658 Recuperation du titre]
    T647 --> C658
    style C658 fill:#3fb950
    C780[780 SP Caractères Inte...]
    T647 --> C780
    style C780 fill:#3fb950
    C646[646 Création compte cash]
    T647 --> C646
    style C646 fill:#3fb950
    C648[648 Create TAI Comptes...]
    T647 --> C648
    style C648 fill:#3fb950
    C649[649 Zoom nationalite]
    T647 --> C649
    style C649 fill:#3fb950
    C659[659 Determination Age ...]
    T647 --> C659
    style C659 fill:#3fb950
    C779[779 Appel programme]
    T647 --> C779
    style C779 fill:#3fb950
    C825[825 Incrémentation com...]
    T647 --> C825
    style C825 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [658](REF-IDE-658.md) | Recuperation du titre | 2 | Recuperation donnees |
| [780](REF-IDE-780.md) | SP Caractères Interdits | 2 | Validation saisie |
| [646](REF-IDE-646.md) | Création compte cash | 1 | Sous-programme |
| [648](REF-IDE-648.md) | Create TAI Comptes speciaux | 1 | Sous-programme |
| [649](REF-IDE-649.md) | Zoom nationalite | 1 | Selection/consultation |
| [659](REF-IDE-659.md) | Determination Age Debut Sejou | 1 | Sous-programme |
| [779](REF-IDE-779.md) | Appel programme | 1 | Sous-programme |
| [825](REF-IDE-825.md) | Incrémentation compteur num | 1 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 532 | Programme volumineux |
| Expressions | 12 | Peu de logique |
| Tables WRITE | 6 | Fort impact donnees |
| Sous-programmes | 8 | Dependances moderees |
| Ecrans visibles | 4 | Quelques ecrans |
| Code desactive | 0.8% (4 / 532) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (11 taches: 6 ecrans, 5 traitements)

- **Strategie** : Orchestrateur avec 6 ecrans (Razor/React) et 5 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 8 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Consultation (1 tache: 1 ecran, 0 traitement)

- **Strategie** : Composants de recherche/selection en modales.
- 1 ecran : Recherche par nom

#### Creation (5 taches: 0 ecran, 5 traitements)

- **Strategie** : Repository pattern avec Entity Framework Core.
- Insertion via `IRepository<T>.CreateAsync()`

#### Validation (1 tache: 0 ecran, 1 traitement)

- **Strategie** : FluentValidation avec validators specifiques.
- Chaque tache de validation -> un validator injectable

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| gm-recherche_____gmr | Table WRITE (Database) | 1x | Schema + repository |
| gm-complet_______gmc | Table WRITE (Database) | 1x | Schema + repository |
| hebergement______heb | Table WRITE (Database) | 1x | Schema + repository |
| compte_gm________cgm | Table WRITE (Database) | 1x | Schema + repository |
| compteurs________cpt | Table WRITE (Database) | 1x | Schema + repository |
| comptes_speciaux_spc_cash | Table WRITE (Database) | 1x | Schema + repository |
| [SP Caractères Interdits (IDE 780)](REF-IDE-780.md) | Sous-programme | 2x | Haute - Validation saisie |
| [Recuperation du titre (IDE 658)](REF-IDE-658.md) | Sous-programme | 2x | Haute - Recuperation donnees |
| [Determination Age Debut Sejou (IDE 659)](REF-IDE-659.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Appel programme (IDE 779)](REF-IDE-779.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Incrémentation compteur num (IDE 825)](REF-IDE-825.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Création compte cash (IDE 646)](REF-IDE-646.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Create TAI Comptes speciaux (IDE 648)](REF-IDE-648.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Zoom nationalite (IDE 649)](REF-IDE-649.md) | Sous-programme | 1x | Normale - Selection/consultation |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 13:24*
