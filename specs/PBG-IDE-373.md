# PBG IDE 373 - Module personnel identites

> **Analyse**: Phases 1-4 2026-02-03 11:30 -> 11:30 (17s) | Assemblage 11:30
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBG |
| IDE Position | 373 |
| Nom Programme | Module personnel identites |
| Fichier source | `Prg_373.xml` |
| Dossier IDE | General |
| Taches | 25 (3 ecrans visibles) |
| Tables modifiees | 7 |
| Programmes appeles | 12 |
| :warning: Statut | **ORPHELIN_POTENTIEL** |

## 2. DESCRIPTION FONCTIONNELLE

**Module personnel identites** assure la gestion complete de ce processus.

Le flux de traitement s'organise en **5 blocs fonctionnels** :

- **Creation** (9 taches) : insertion d'enregistrements en base (mouvements, prestations)
- **Traitement** (8 taches) : traitements metier divers
- **Consultation** (4 taches) : ecrans de recherche, selection et consultation
- **Calcul** (3 taches) : calculs de montants, stocks ou compteurs
- **Validation** (1 tache) : controles et verifications de coherence

**Donnees modifiees** : 7 tables en ecriture (gm-recherche_____gmr, gm-complet_______gmc, hebergement______heb, compte_gm________cgm, compteurs________cpt, fichier_validation, fi_complet_______gm_go).

**Logique metier** : 1 regles identifiees couvrant valeurs par defaut.

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (8 taches)

- **373** - Module des Identites
- **373.1** - Determination Age Bebe
- **373.2.2** - Langue ?
- **373.2.5** - Lecture Qualite&Occupation
- **373.2.6** - Determination Fonction **[[ECRAN]](#ecran-t12)**
- **373.2.6.1** - Determination Service
- **373.2.7** - Veuillez patienter... **[[ECRAN]](#ecran-t15)**
- **373.2.10** - Maj base occup

Delegue a : [Redirection touches (IDE 309)](PBG-IDE-309.md), [Création Village/Village (IDE 336)](PBG-IDE-336.md), [Determination Age Debut Sejour (IDE 312)](PBG-IDE-312.md), [Recuperation du titre (IDE 317)](PBG-IDE-317.md)

#### Phase 2 : Consultation (4 taches)

- **373.2** - Affichage Personnel **[[ECRAN]](#ecran-t4)**
- **373.2.1** - Recherche **[[ECRAN]](#ecran-t5)**
- **373.2.6.2** - Selection Fonction **[[ECRAN]](#ecran-t14)**
- **373.2.7.8** - Creation Recherche

Delegue a : [Zoom nationalite (IDE 356)](PBG-IDE-356.md), [Recherche Existance Groupe A/D (IDE 337)](PBG-IDE-337.md), [Zoom langue (IDE 355)](PBG-IDE-355.md), [Zoom Qualite(C/P) (IDE 366)](PBG-IDE-366.md), [Zoom Village/Village (IDE 370)](PBG-IDE-370.md), [Recuperation du titre (IDE 317)](PBG-IDE-317.md)

#### Phase 3 : Calcul (3 taches)

- **373.2.3** - Attribution Compte
- **373.2.4** - Attribution Compte
- **373.2.7.7** - Creation Compte

#### Phase 4 : Creation (9 taches)

- **373.2.7.1** - Creation Complet
- **373.2.7.2** - Creation Hebergement
- **373.2.7.3** - Creation Hebergement
- **373.2.7.4** - Creation Hebergement
- **373.2.7.5** - Creation Package Aller
- **373.2.7.6** - Creation Package Retour
- **373.2.7.10** - Creation Complet
- **373.2.8** - Creation personnel
- **373.2.9** - Creation personnel

Delegue a : [Creation Historique (IDE 181)](PBG-IDE-181.md), [  Creation personnel identites (IDE 194)](PBG-IDE-194.md)

#### Phase 5 : Validation (1 tache)

- **373.2.7.9** - Creation Validation

Delegue a : [Verification Aut sans ecran (IDE 320)](PBG-IDE-320.md)

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| hebergement______heb | R/**W**/L (8 usages) | Hebergement (chambres) |
| compte_gm________cgm | **W**/L (2 usages) | Comptes GM (generaux) |
| gm-recherche_____gmr | **W** (2 usages) | Index de recherche |
| gm-complet_______gmc | **W**/L (2 usages) |  |
| compteurs________cpt | **W** (2 usages) | Comptes GM (generaux) |
| fichier_validation | **W** (1 usages) |  |
| fi_complet_______gm_go | **W** (1 usages) |  |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (8 taches)

Traitements internes.

---

#### <a id="t1"></a>373 - Module des Identites

**Role** : Tache d'orchestration : point d'entree du programme (8 sous-taches). Coordonne l'enchainement des traitements.

<details>
<summary>7 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [373.1](#t2) | Determination Age Bebe | Traitement |
| [373.2.2](#t8) | Langue ? | Traitement |
| [373.2.5](#t11) | Lecture Qualite&Occupation | Traitement |
| [373.2.6](#t12) | Determination Fonction **[[ECRAN]](#ecran-t12)** | Traitement |
| [373.2.6.1](#t13) | Determination Service | Traitement |
| [373.2.7](#t15) | Veuillez patienter... **[[ECRAN]](#ecran-t15)** | Traitement |
| [373.2.10](#t29) | Maj base occup | Traitement |

</details>
**Delegue a** : [Redirection touches (IDE 309)](PBG-IDE-309.md), [Création Village/Village (IDE 336)](PBG-IDE-336.md), [Determination Age Debut Sejour (IDE 312)](PBG-IDE-312.md)

---

#### <a id="t2"></a>373.1 - Determination Age Bebe

**Role** : Traitement : Determination Age Bebe.
**Variables liees** : C (W0-Age Bebe)
**Delegue a** : [Redirection touches (IDE 309)](PBG-IDE-309.md), [Création Village/Village (IDE 336)](PBG-IDE-336.md), [Determination Age Debut Sejour (IDE 312)](PBG-IDE-312.md)

---

#### <a id="t8"></a>373.2.2 - Langue ?

**Role** : Traitement : Langue ?.
**Variables liees** : M (W0-Saisie langue ?), T (W1-Select Langue), W (bouton langue)
**Delegue a** : [Redirection touches (IDE 309)](PBG-IDE-309.md), [Création Village/Village (IDE 336)](PBG-IDE-336.md), [Determination Age Debut Sejour (IDE 312)](PBG-IDE-312.md)

---

#### <a id="t11"></a>373.2.5 - Lecture Qualite&Occupation

**Role** : Traitement : Lecture Qualite&Occupation.
**Delegue a** : [Redirection touches (IDE 309)](PBG-IDE-309.md), [Création Village/Village (IDE 336)](PBG-IDE-336.md), [Determination Age Debut Sejour (IDE 312)](PBG-IDE-312.md)

---

#### <a id="t12"></a>373.2.6 - Determination Fonction [[ECRAN]](#ecran-t12)

**Role** : Traitement : Determination Fonction.
**Ecran** : 108 x 8 DLU (MDI) | [Voir mockup](#ecran-t12)
**Variables liees** : P (W0-Code fonction)
**Delegue a** : [Redirection touches (IDE 309)](PBG-IDE-309.md), [Création Village/Village (IDE 336)](PBG-IDE-336.md), [Determination Age Debut Sejour (IDE 312)](PBG-IDE-312.md)

---

#### <a id="t13"></a>373.2.6.1 - Determination Service

**Role** : Traitement : Determination Service.
**Variables liees** : O (W0-Table service)
**Delegue a** : [Redirection touches (IDE 309)](PBG-IDE-309.md), [Création Village/Village (IDE 336)](PBG-IDE-336.md), [Determination Age Debut Sejour (IDE 312)](PBG-IDE-312.md)

---

#### <a id="t15"></a>373.2.7 - Veuillez patienter... [[ECRAN]](#ecran-t15)

**Role** : Traitement : Veuillez patienter....
**Ecran** : 422 x 56 DLU (MDI) | [Voir mockup](#ecran-t15)
**Delegue a** : [Redirection touches (IDE 309)](PBG-IDE-309.md), [Création Village/Village (IDE 336)](PBG-IDE-336.md), [Determination Age Debut Sejour (IDE 312)](PBG-IDE-312.md)

---

#### <a id="t29"></a>373.2.10 - Maj base occup

**Role** : Traitement : Maj base occup.
**Variables liees** : D (W0-Base Vide), K (W0-code base occup), U (W1-Base occupation)
**Delegue a** : [Redirection touches (IDE 309)](PBG-IDE-309.md), [Création Village/Village (IDE 336)](PBG-IDE-336.md), [Determination Age Debut Sejour (IDE 312)](PBG-IDE-312.md)


### 3.2 Consultation (4 taches)

Ecrans de recherche et consultation.

---

#### <a id="t4"></a>373.2 - Affichage Personnel [[ECRAN]](#ecran-t4)

**Role** : Reinitialisation : Affichage Personnel.
**Ecran** : 1130 x 370 DLU (MDI) | [Voir mockup](#ecran-t4)
**Variables liees** : BA (v Libelle affichage ECI)
**Delegue a** : [Zoom nationalite (IDE 356)](PBG-IDE-356.md), [Recherche Existance Groupe A/D (IDE 337)](PBG-IDE-337.md), [Zoom langue (IDE 355)](PBG-IDE-355.md)

---

#### <a id="t5"></a>373.2.1 - Recherche [[ECRAN]](#ecran-t5)

**Role** : Traitement : Recherche.
**Ecran** : 578 x 101 DLU (MDI) | [Voir mockup](#ecran-t5)
**Variables liees** : BH (bouton recherche)
**Delegue a** : [Zoom nationalite (IDE 356)](PBG-IDE-356.md), [Recherche Existance Groupe A/D (IDE 337)](PBG-IDE-337.md), [Zoom langue (IDE 355)](PBG-IDE-355.md)

---

#### <a id="t14"></a>373.2.6.2 - Selection Fonction [[ECRAN]](#ecran-t14)

**Role** : Selection par l'operateur : Selection Fonction.
**Ecran** : 390 x 167 DLU (MDI) | [Voir mockup](#ecran-t14)
**Variables liees** : P (W0-Code fonction)
**Delegue a** : [Zoom nationalite (IDE 356)](PBG-IDE-356.md), [Recherche Existance Groupe A/D (IDE 337)](PBG-IDE-337.md), [Zoom langue (IDE 355)](PBG-IDE-355.md)

---

#### <a id="t23"></a>373.2.7.8 - Creation Recherche

**Role** : Creation d'enregistrement : Creation Recherche.
**Variables liees** : H (W0-autorisation creation), BH (bouton recherche)
**Delegue a** : [Zoom nationalite (IDE 356)](PBG-IDE-356.md), [Recherche Existance Groupe A/D (IDE 337)](PBG-IDE-337.md), [Zoom langue (IDE 355)](PBG-IDE-355.md)


### 3.3 Calcul (3 taches)

Calculs metier : montants, stocks, compteurs.

---

#### <a id="t9"></a>373.2.3 - Attribution Compte

**Role** : Traitement : Attribution Compte.
**Variables liees** : G (W0-numero compte memo), Q (W0-Compte)

---

#### <a id="t10"></a>373.2.4 - Attribution Compte

**Role** : Traitement : Attribution Compte.
**Variables liees** : G (W0-numero compte memo), Q (W0-Compte)

---

#### <a id="t22"></a>373.2.7.7 - Creation Compte

**Role** : Creation d'enregistrement : Creation Compte.
**Variables liees** : G (W0-numero compte memo), H (W0-autorisation creation), Q (W0-Compte)
**Delegue a** : [Creation Historique (IDE 181)](PBG-IDE-181.md), [  Creation personnel identites (IDE 194)](PBG-IDE-194.md)


### 3.4 Creation (9 taches)

Insertion de nouveaux enregistrements en base.

---

#### <a id="t16"></a>373.2.7.1 - Creation Complet

**Role** : Creation d'enregistrement : Creation Complet.
**Variables liees** : H (W0-autorisation creation)
**Delegue a** : [Creation Historique (IDE 181)](PBG-IDE-181.md), [  Creation personnel identites (IDE 194)](PBG-IDE-194.md)

---

#### <a id="t17"></a>373.2.7.2 - Creation Hebergement

**Role** : Creation d'enregistrement : Creation Hebergement.
**Variables liees** : H (W0-autorisation creation)
**Delegue a** : [Creation Historique (IDE 181)](PBG-IDE-181.md), [  Creation personnel identites (IDE 194)](PBG-IDE-194.md)

---

#### <a id="t18"></a>373.2.7.3 - Creation Hebergement

**Role** : Creation d'enregistrement : Creation Hebergement.
**Variables liees** : H (W0-autorisation creation)
**Delegue a** : [Creation Historique (IDE 181)](PBG-IDE-181.md), [  Creation personnel identites (IDE 194)](PBG-IDE-194.md)

---

#### <a id="t19"></a>373.2.7.4 - Creation Hebergement

**Role** : Creation d'enregistrement : Creation Hebergement.
**Variables liees** : H (W0-autorisation creation)
**Delegue a** : [Creation Historique (IDE 181)](PBG-IDE-181.md), [  Creation personnel identites (IDE 194)](PBG-IDE-194.md)

---

#### <a id="t20"></a>373.2.7.5 - Creation Package Aller

**Role** : Creation d'enregistrement : Creation Package Aller.
**Variables liees** : BB (v.V/V Aller), BK (v.Existe Code VV Aller), BL (v.Code VV Aller), BM (v.Heure VV Aller), H (W0-autorisation creation)
**Delegue a** : [Creation Historique (IDE 181)](PBG-IDE-181.md), [  Creation personnel identites (IDE 194)](PBG-IDE-194.md)

---

#### <a id="t21"></a>373.2.7.6 - Creation Package Retour

**Role** : Creation d'enregistrement : Creation Package Retour.
**Variables liees** : BC (v.V/V Retour), BI (v.Retour Question Bsi), BN (v.Existe Code VV Retour), BO (v.Code VV Retour), BP (v.Heure VV Retour)
**Delegue a** : [Creation Historique (IDE 181)](PBG-IDE-181.md), [  Creation personnel identites (IDE 194)](PBG-IDE-194.md)

---

#### <a id="t25"></a>373.2.7.10 - Creation Complet

**Role** : Creation d'enregistrement : Creation Complet.
**Variables liees** : H (W0-autorisation creation)
**Delegue a** : [Creation Historique (IDE 181)](PBG-IDE-181.md), [  Creation personnel identites (IDE 194)](PBG-IDE-194.md)

---

#### <a id="t27"></a>373.2.8 - Creation personnel

**Role** : Creation d'enregistrement : Creation personnel.
**Variables liees** : H (W0-autorisation creation)
**Delegue a** : [Creation Historique (IDE 181)](PBG-IDE-181.md), [  Creation personnel identites (IDE 194)](PBG-IDE-194.md)

---

#### <a id="t28"></a>373.2.9 - Creation personnel

**Role** : Creation d'enregistrement : Creation personnel.
**Variables liees** : H (W0-autorisation creation)
**Delegue a** : [Creation Historique (IDE 181)](PBG-IDE-181.md), [  Creation personnel identites (IDE 194)](PBG-IDE-194.md)


### 3.5 Validation (1 tache)

Controles de coherence : 1 tache verifie les donnees et conditions.

---

#### <a id="t24"></a>373.2.7.9 - Creation Validation

**Role** : Verification : Creation Validation.
**Variables liees** : H (W0-autorisation creation)
**Delegue a** : [Verification Aut sans ecran (IDE 320)](PBG-IDE-320.md), [Creation Historique (IDE 181)](PBG-IDE-181.md), [  Creation personnel identites (IDE 194)](PBG-IDE-194.md)


## 5. REGLES METIER

1 regles identifiees:

### Autres (1 regles)

#### <a id="rm-RM-001"></a>[RM-001] Valeur par defaut si Trim (> Mode attaque ecran [A]) est vide

| Element | Detail |
|---------|--------|
| **Condition** | `Trim (> Mode attaque ecran [A])=''` |
| **Si vrai** | 'E'MODE |
| **Si faux** | > Mode attaque ecran [A]) |
| **Variables** | A (> Mode attaque ecran) |
| **Expression source** | Expression 3 : `IF (Trim (> Mode attaque ecran [A])='','E'MODE,> Mode attaqu` |
| **Exemple** | Si Trim (> Mode attaque ecran [A])='' â†’ 'E'MODE. Sinon â†’ > Mode attaque ecran [A]) |

## 6. CONTEXTE

- **Appele par**: (aucun)
- **Appelle**: 12 programmes | **Tables**: 15 (W:7 R:4 L:9) | **Taches**: 25 | **Expressions**: 15

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (3 / 25)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 373.2 | 373.2 | Affichage Personnel | MDI | 1130 | 370 | Consultation |
| 2 | 373.2.1 | 373.2.1 | Recherche | MDI | 578 | 101 | Consultation |
| 3 | 373.2.6.2 | 373.2.6.2 | Selection Fonction | MDI | 390 | 167 | Consultation |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t4"></a>373.2 - Affichage Personnel
**Tache** : [373.2](#t4) | **Type** : MDI | **Dimensions** : 1130 x 370 DLU
**Bloc** : Consultation | **Titre IDE** : Affichage Personnel

<!-- FORM-DATA:
{
    "width":  1130,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  1,
                         "type":  "label",
                         "var":  "",
                         "y":  1,
                         "w":  1126,
                         "fmt":  "",
                         "name":  "",
                         "h":  19,
                         "color":  "1",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  262,
                         "type":  "label",
                         "var":  "",
                         "y":  5,
                         "w":  120,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "GO N° Compte",
                         "parent":  null
                     },
                     {
                         "x":  414,
                         "type":  "label",
                         "var":  "",
                         "y":  24,
                         "w":  698,
                         "fmt":  "",
                         "name":  "",
                         "h":  316,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  425,
                         "type":  "label",
                         "var":  "",
                         "y":  31,
                         "w":  106,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "Titre",
                         "parent":  5
                     },
                     {
                         "x":  12,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  14,
                         "color":  "110",
                         "w":  396,
                         "y":  26,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  14,
                         "h":  314,
                         "cols":  [
                                      {
                                          "title":  "Titre",
                                          "layer":  1,
                                          "w":  48
                                      },
                                      {
                                          "title":  "Nom",
                                          "layer":  2,
                                          "w":  192
                                      },
                                      {
                                          "title":  "Prénom",
                                          "layer":  3,
                                          "w":  122
                                      }
                                  ],
                         "rows":  3
                     },
                     {
                         "x":  425,
                         "type":  "label",
                         "var":  "",
                         "y":  47,
                         "w":  106,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "Qualité",
                         "parent":  5
                     },
                     {
                         "x":  425,
                         "type":  "label",
                         "var":  "",
                         "y":  63,
                         "w":  106,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "Service",
                         "parent":  5
                     },
                     {
                         "x":  425,
                         "type":  "label",
                         "var":  "",
                         "y":  79,
                         "w":  106,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Fonction",
                         "parent":  5
                     },
                     {
                         "x":  425,
                         "type":  "label",
                         "var":  "",
                         "y":  94,
                         "w":  106,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "Contrat",
                         "parent":  5
                     },
                     {
                         "x":  425,
                         "type":  "label",
                         "var":  "",
                         "y":  163,
                         "w":  106,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "Arrivée",
                         "parent":  5
                     },
                     {
                         "x":  425,
                         "type":  "label",
                         "var":  "",
                         "y":  179,
                         "w":  106,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "Départ",
                         "parent":  5
                     },
                     {
                         "x":  425,
                         "type":  "label",
                         "var":  "",
                         "y":  196,
                         "w":  149,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Date de Naissance",
                         "parent":  5
                     },
                     {
                         "x":  759,
                         "type":  "label",
                         "var":  "",
                         "y":  196,
                         "w":  43,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Age",
                         "parent":  5
                     },
                     {
                         "x":  425,
                         "type":  "label",
                         "var":  "",
                         "y":  211,
                         "w":  106,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Nationalité",
                         "parent":  5
                     },
                     {
                         "x":  425,
                         "type":  "label",
                         "var":  "",
                         "y":  226,
                         "w":  106,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "Occupation",
                         "parent":  5
                     },
                     {
                         "x":  425,
                         "type":  "label",
                         "var":  "",
                         "y":  243,
                         "w":  106,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Identité",
                         "parent":  5
                     },
                     {
                         "x":  425,
                         "type":  "label",
                         "var":  "",
                         "y":  259,
                         "w":  106,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "Délivré",
                         "parent":  5
                     },
                     {
                         "x":  842,
                         "type":  "label",
                         "var":  "",
                         "y":  259,
                         "w":  45,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "Date",
                         "parent":  5
                     },
                     {
                         "x":  432,
                         "type":  "label",
                         "var":  "",
                         "y":  272,
                         "w":  643,
                         "fmt":  "",
                         "name":  "",
                         "h":  49,
                         "color":  "195",
                         "text":  "Adresse",
                         "parent":  5
                     },
                     {
                         "x":  425,
                         "type":  "label",
                         "var":  "",
                         "y":  326,
                         "w":  106,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Langue",
                         "parent":  5
                     },
                     {
                         "x":  2,
                         "type":  "label",
                         "var":  "",
                         "y":  344,
                         "w":  1125,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "1",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  425,
                         "type":  "label",
                         "var":  "",
                         "y":  113,
                         "w":  106,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "Cat. d\u0027emploi",
                         "parent":  5
                     },
                     {
                         "x":  425,
                         "type":  "label",
                         "var":  "",
                         "y":  130,
                         "w":  106,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "BSI Ok ?",
                         "parent":  5
                     },
                     {
                         "x":  425,
                         "type":  "label",
                         "var":  "",
                         "y":  145,
                         "w":  107,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "Lieu de séjour",
                         "parent":  5
                     },
                     {
                         "x":  750,
                         "type":  "label",
                         "var":  "",
                         "y":  163,
                         "w":  85,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "Vol aller",
                         "parent":  5
                     },
                     {
                         "x":  747,
                         "type":  "label",
                         "var":  "",
                         "y":  179,
                         "w":  85,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "Vol retour",
                         "parent":  5
                     },
                     {
                         "x":  69,
                         "type":  "edit",
                         "var":  "",
                         "y":  44,
                         "w":  176,
                         "fmt":  "U15",
                         "name":  "GO Nom",
                         "h":  8,
                         "color":  "6",
                         "text":  "",
                         "parent":  10
                     },
                     {
                         "x":  264,
                         "type":  "edit",
                         "var":  "",
                         "y":  44,
                         "w":  98,
                         "fmt":  "UX9",
                         "name":  "GO Prenom",
                         "h":  8,
                         "color":  "6",
                         "text":  "",
                         "parent":  10
                     },
                     {
                         "x":  538,
                         "type":  "combobox",
                         "var":  "",
                         "y":  30,
                         "w":  182,
                         "fmt":  "",
                         "name":  "W1-Select titre",
                         "h":  12,
                         "color":  "110",
                         "text":  "1,2",
                         "parent":  5
                     },
                     {
                         "x":  725,
                         "type":  "button",
                         "var":  "",
                         "y":  47,
                         "w":  28,
                         "fmt":  "...",
                         "name":  "v. bouton qualite",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  538,
                         "type":  "edit",
                         "var":  "",
                         "y":  46,
                         "w":  182,
                         "fmt":  "15",
                         "name":  "W1-Select qualite",
                         "h":  12,
                         "color":  "110",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  538,
                         "type":  "combobox",
                         "var":  "",
                         "y":  61,
                         "w":  206,
                         "fmt":  "",
                         "name":  "W1-Select Service",
                         "h":  12,
                         "color":  "110",
                         "text":  "1,2",
                         "parent":  5
                     },
                     {
                         "x":  759,
                         "type":  "edit",
                         "var":  "",
                         "y":  62,
                         "w":  294,
                         "fmt":  "",
                         "name":  "GO Service",
                         "h":  12,
                         "color":  "110",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  538,
                         "type":  "edit",
                         "var":  "",
                         "y":  79,
                         "w":  294,
                         "fmt":  "",
                         "name":  "GO Fonction",
                         "h":  12,
                         "color":  "110",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  837,
                         "type":  "button",
                         "var":  "",
                         "y":  80,
                         "w":  28,
                         "fmt":  "...",
                         "name":  "v.bouton fonction",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  538,
                         "type":  "combobox",
                         "var":  "",
                         "y":  94,
                         "w":  206,
                         "fmt":  "",
                         "name":  "W1-Select Contrat",
                         "h":  12,
                         "color":  "110",
                         "text":  "1,2",
                         "parent":  5
                     },
                     {
                         "x":  538,
                         "type":  "combobox",
                         "var":  "",
                         "y":  113,
                         "w":  422,
                         "fmt":  "",
                         "name":  "Go_cat_emploi",
                         "h":  12,
                         "color":  "110",
                         "text":  "1,2,3",
                         "parent":  5
                     },
                     {
                         "x":  538,
                         "type":  "checkbox",
                         "var":  "",
                         "y":  130,
                         "w":  37,
                         "fmt":  "",
                         "name":  "go_bsi_ok",
                         "h":  12,
                         "color":  "",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  538,
                         "type":  "edit",
                         "var":  "",
                         "y":  163,
                         "w":  166,
                         "fmt":  "DD/MM/YYYYZ",
                         "name":  "GO Date Debut",
                         "h":  12,
                         "color":  "110",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  709,
                         "type":  "button",
                         "var":  "",
                         "y":  165,
                         "w":  28,
                         "fmt":  "...",
                         "name":  "bouton date debut",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  832,
                         "type":  "edit",
                         "var":  "",
                         "y":  163,
                         "w":  74,
                         "fmt":  "",
                         "name":  "heb_nom_logement",
                         "h":  12,
                         "color":  "6",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  912,
                         "type":  "edit",
                         "var":  "",
                         "y":  163,
                         "w":  34,
                         "fmt":  "",
                         "name":  "heb_heure_debut",
                         "h":  12,
                         "color":  "6",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  956,
                         "type":  "button",
                         "var":  "",
                         "y":  164,
                         "w":  28,
                         "fmt":  "...",
                         "name":  "v.V/V Aller",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  538,
                         "type":  "edit",
                         "var":  "",
                         "y":  179,
                         "w":  166,
                         "fmt":  "DD/MM/YYYYZ",
                         "name":  "GO Date Fin",
                         "h":  12,
                         "color":  "110",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  578,
                         "type":  "edit",
                         "var":  "",
                         "y":  195,
                         "w":  126,
                         "fmt":  "DD/MM/YYYYT",
                         "name":  "GO Date Naissance",
                         "h":  12,
                         "color":  "110",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  709,
                         "type":  "button",
                         "var":  "",
                         "y":  181,
                         "w":  28,
                         "fmt":  "...",
                         "name":  "bouton date fin",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  832,
                         "type":  "edit",
                         "var":  "",
                         "y":  179,
                         "w":  74,
                         "fmt":  "",
                         "name":  "heb_nom_logement_0001",
                         "h":  12,
                         "color":  "6",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  912,
                         "type":  "edit",
                         "var":  "",
                         "y":  179,
                         "w":  34,
                         "fmt":  "",
                         "name":  "heb_heure_debut_0001",
                         "h":  12,
                         "color":  "6",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  956,
                         "type":  "button",
                         "var":  "",
                         "y":  180,
                         "w":  28,
                         "fmt":  "...",
                         "name":  "v.V/V Retour",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  538,
                         "type":  "edit",
                         "var":  "",
                         "y":  211,
                         "w":  37,
                         "fmt":  "",
                         "name":  "GO Nationalite",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  585,
                         "type":  "button",
                         "var":  "",
                         "y":  211,
                         "w":  28,
                         "fmt":  "...",
                         "name":  "bouton nationalite",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  587,
                         "type":  "combobox",
                         "var":  "",
                         "y":  226,
                         "w":  110,
                         "fmt":  "",
                         "name":  "W1-Base occupation",
                         "h":  12,
                         "color":  "110",
                         "text":  "1,2",
                         "parent":  5
                     },
                     {
                         "x":  538,
                         "type":  "edit",
                         "var":  "",
                         "y":  243,
                         "w":  280,
                         "fmt":  "U18",
                         "name":  "GMC N° Pièce",
                         "h":  12,
                         "color":  "110",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  538,
                         "type":  "edit",
                         "var":  "",
                         "y":  259,
                         "w":  280,
                         "fmt":  "U18",
                         "name":  "GMC Ville Delivrance",
                         "h":  12,
                         "color":  "110",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  915,
                         "type":  "edit",
                         "var":  "",
                         "y":  259,
                         "w":  126,
                         "fmt":  "DD/MM/YYYYT",
                         "name":  "GMC Date Delivrance",
                         "h":  12,
                         "color":  "110",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  1048,
                         "type":  "button",
                         "var":  "",
                         "y":  260,
                         "w":  26,
                         "fmt":  "...",
                         "name":  "bouton date delivrance",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  538,
                         "type":  "edit",
                         "var":  "",
                         "y":  282,
                         "w":  126,
                         "fmt":  "",
                         "name":  "GMC N° dans la rue",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  45
                     },
                     {
                         "x":  667,
                         "type":  "edit",
                         "var":  "",
                         "y":  282,
                         "w":  358,
                         "fmt":  "",
                         "name":  "GMC Nom de la rue",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  45
                     },
                     {
                         "x":  538,
                         "type":  "edit",
                         "var":  "",
                         "y":  294,
                         "w":  486,
                         "fmt":  "",
                         "name":  "GMC Commune",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  45
                     },
                     {
                         "x":  538,
                         "type":  "edit",
                         "var":  "",
                         "y":  306,
                         "w":  126,
                         "fmt":  "",
                         "name":  "GMC Code Postal",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  45
                     },
                     {
                         "x":  667,
                         "type":  "edit",
                         "var":  "",
                         "y":  306,
                         "w":  358,
                         "fmt":  "",
                         "name":  "GMC Ville",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  45
                     },
                     {
                         "x":  528,
                         "type":  "edit",
                         "var":  "",
                         "y":  326,
                         "w":  37,
                         "fmt":  "",
                         "name":  "GMR Langue Parlee",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  571,
                         "type":  "button",
                         "var":  "",
                         "y":  326,
                         "w":  28,
                         "fmt":  "...",
                         "name":  "bouton langue",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  615,
                         "type":  "edit",
                         "var":  "",
                         "y":  326,
                         "w":  232,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "7",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  832,
                         "type":  "edit",
                         "var":  "",
                         "y":  196,
                         "w":  30,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  629,
                         "type":  "edit",
                         "var":  "",
                         "y":  211,
                         "w":  314,
                         "fmt":  "U20",
                         "name":  "",
                         "h":  10,
                         "color":  "7",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  957,
                         "type":  "button",
                         "var":  "",
                         "y":  347,
                         "w":  154,
                         "fmt":  "\u0026Recherche",
                         "name":  "bouton recherche",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  54
                     },
                     {
                         "x":  11,
                         "type":  "edit",
                         "var":  "",
                         "y":  6,
                         "w":  478,
                         "fmt":  "30",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  841,
                         "type":  "edit",
                         "var":  "",
                         "y":  6,
                         "w":  275,
                         "fmt":  "WWW DD MMM YYYYT",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  724,
                         "type":  "edit",
                         "var":  "",
                         "y":  31,
                         "w":  53,
                         "fmt":  "UX3",
                         "name":  "",
                         "h":  12,
                         "color":  "7",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  22,
                         "type":  "edit",
                         "var":  "",
                         "y":  44,
                         "w":  30,
                         "fmt":  "UX",
                         "name":  "",
                         "h":  7,
                         "color":  "6",
                         "text":  "",
                         "parent":  10
                     },
                     {
                         "x":  538,
                         "type":  "edit",
                         "var":  "",
                         "y":  226,
                         "w":  19,
                         "fmt":  "1",
                         "name":  "",
                         "h":  12,
                         "color":  "7",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  11,
                         "type":  "button",
                         "var":  "",
                         "y":  347,
                         "w":  154,
                         "fmt":  "\u0026Ok",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  54
                     },
                     {
                         "x":  187,
                         "type":  "button",
                         "var":  "",
                         "y":  347,
                         "w":  154,
                         "fmt":  "A\u0026bandonner",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  54
                     },
                     {
                         "x":  340,
                         "type":  "button",
                         "var":  "",
                         "y":  347,
                         "w":  154,
                         "fmt":  "\u0026Annuler",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  54
                     },
                     {
                         "x":  494,
                         "type":  "button",
                         "var":  "",
                         "y":  347,
                         "w":  154,
                         "fmt":  "\u0026Creation",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  54
                     },
                     {
                         "x":  648,
                         "type":  "button",
                         "var":  "",
                         "y":  347,
                         "w":  154,
                         "fmt":  "\u0026Modification",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  54
                     },
                     {
                         "x":  802,
                         "type":  "button",
                         "var":  "",
                         "y":  347,
                         "w":  154,
                         "fmt":  "\u0026Visualisation",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  54
                     },
                     {
                         "x":  542,
                         "type":  "combobox",
                         "var":  "",
                         "y":  144,
                         "w":  280,
                         "fmt":  "",
                         "name":  "W1-Combo Lieu Sejour",
                         "h":  12,
                         "color":  "110",
                         "text":  "1,2",
                         "parent":  5
                     },
                     {
                         "x":  786,
                         "type":  "edit",
                         "var":  "",
                         "y":  31,
                         "w":  77,
                         "fmt":  "6",
                         "name":  "",
                         "h":  12,
                         "color":  "204",
                         "text":  "",
                         "parent":  5
                     }
                 ],
    "taskId":  "373.2",
    "height":  370
}
-->

<details>
<summary><strong>Champs : 38 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 69,44 | GO Nom | - | edit |
| 264,44 | GO Prenom | - | edit |
| 538,30 | W1-Select titre | - | combobox |
| 538,46 | W1-Select qualite | - | edit |
| 538,61 | W1-Select Service | - | combobox |
| 759,62 | GO Service | - | edit |
| 538,79 | GO Fonction | - | edit |
| 538,94 | W1-Select Contrat | - | combobox |
| 538,113 | Go_cat_emploi | - | combobox |
| 538,130 | go_bsi_ok | - | checkbox |
| 538,163 | GO Date Debut | - | edit |
| 832,163 | heb_nom_logement | - | edit |
| 912,163 | heb_heure_debut | - | edit |
| 538,179 | GO Date Fin | - | edit |
| 578,195 | GO Date Naissance | - | edit |
| 832,179 | heb_nom_logement_0001 | - | edit |
| 912,179 | heb_heure_debut_0001 | - | edit |
| 538,211 | GO Nationalite | - | edit |
| 587,226 | W1-Base occupation | - | combobox |
| 538,243 | GMC N° Pièce | - | edit |
| 538,259 | GMC Ville Delivrance | - | edit |
| 915,259 | GMC Date Delivrance | - | edit |
| 538,282 | GMC N° dans la rue | - | edit |
| 667,282 | GMC Nom de la rue | - | edit |
| 538,294 | GMC Commune | - | edit |
| 538,306 | GMC Code Postal | - | edit |
| 667,306 | GMC Ville | - | edit |
| 528,326 | GMR Langue Parlee | - | edit |
| 615,326 | (sans nom) | - | edit |
| 832,196 | (sans nom) | - | edit |
| 629,211 | U20 | - | edit |
| 11,6 | 30 | - | edit |
| 841,6 | WWW DD MMM YYYYT | - | edit |
| 724,31 | UX3 | - | edit |
| 22,44 | UX | - | edit |
| 538,226 | 1 | - | edit |
| 542,144 | W1-Combo Lieu Sejour | - | combobox |
| 786,31 | 6 | - | edit |

</details>

<details>
<summary><strong>Boutons : 16 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| ... | 725,47 | Bouton fonctionnel |
| ... | 837,80 | Bouton fonctionnel |
| ... | 709,165 | Bouton fonctionnel |
| ... | 956,164 | Bouton fonctionnel |
| ... | 709,181 | Bouton fonctionnel |
| ... | 956,180 | Bouton fonctionnel |
| ... | 585,211 | Bouton fonctionnel |
| ... | 1048,260 | Bouton fonctionnel |
| ... | 571,326 | Bouton fonctionnel |
| Recherche | 957,347 | Appel [Recherche Existance Groupe A/D (IDE 337)](PBG-IDE-337.md) |
| Ok | 11,347 | Valide la saisie et enregistre |
| Abandonner | 187,347 | Annule et retour au menu |
| Annuler | 340,347 | Annule et retour au menu |
| Creation | 494,347 | Appel [Creation Historique (IDE 181)](PBG-IDE-181.md) |
| Modification | 648,347 | Modifie l'element |
| Visualisation | 802,347 | Bouton fonctionnel |

</details>

---

#### <a id="ecran-t5"></a>373.2.1 - Recherche
**Tache** : [373.2.1](#t5) | **Type** : MDI | **Dimensions** : 578 x 101 DLU
**Bloc** : Consultation | **Titre IDE** : Recherche

<!-- FORM-DATA:
{
    "width":  578,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  193,
                         "type":  "label",
                         "var":  "",
                         "y":  11,
                         "w":  375,
                         "fmt":  "",
                         "name":  "",
                         "h":  49,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  219,
                         "type":  "label",
                         "var":  "",
                         "y":  25,
                         "w":  208,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Entrez les premières lettres",
                         "parent":  2
                     },
                     {
                         "x":  1,
                         "type":  "label",
                         "var":  "",
                         "y":  75,
                         "w":  574,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  304,
                         "type":  "edit",
                         "var":  "",
                         "y":  35,
                         "w":  238,
                         "fmt":  "U20",
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
                         "y":  78,
                         "w":  154,
                         "fmt":  "\u0026Ok",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  411,
                         "type":  "button",
                         "var":  "",
                         "y":  79,
                         "w":  154,
                         "fmt":  "\u0026Abandon",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  29,
                         "type":  "image",
                         "var":  "",
                         "y":  1,
                         "w":  151,
                         "fmt":  "",
                         "name":  "",
                         "h":  67,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "373.2.1",
    "height":  101
}
-->

<details>
<summary><strong>Champs : 1 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 304,35 | U20 | - | edit |

</details>

<details>
<summary><strong>Boutons : 2 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Ok | 8,78 | Valide la saisie et enregistre |
| Abandon | 411,79 | Annule et retour au menu |

</details>

---

#### <a id="ecran-t14"></a>373.2.6.2 - Selection Fonction
**Tache** : [373.2.6.2](#t14) | **Type** : MDI | **Dimensions** : 390 x 167 DLU
**Bloc** : Consultation | **Titre IDE** : Selection Fonction

<!-- FORM-DATA:
{
    "width":  390,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  32,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "196",
                         "w":  338,
                         "y":  5,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  12,
                         "h":  106,
                         "cols":  [
                                      {
                                          "title":  "Fonction",
                                          "layer":  1,
                                          "w":  301
                                      }
                                  ],
                         "rows":  1
                     },
                     {
                         "x":  2,
                         "type":  "label",
                         "var":  "",
                         "y":  140,
                         "w":  385,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  38,
                         "type":  "edit",
                         "var":  "",
                         "y":  20,
                         "w":  288,
                         "fmt":  "U25",
                         "name":  "",
                         "h":  8,
                         "color":  "196",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  29,
                         "type":  "button",
                         "var":  "",
                         "y":  143,
                         "w":  154,
                         "fmt":  "\u0026Sélectionner",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  209,
                         "type":  "button",
                         "var":  "",
                         "y":  143,
                         "w":  154,
                         "fmt":  "\u0026Quitter",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  167,
                         "type":  "image",
                         "var":  "",
                         "y":  116,
                         "w":  58,
                         "fmt":  "",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "373.2.6.2",
    "height":  167
}
-->

<details>
<summary><strong>Champs : 1 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 38,20 | U25 | - | edit |

</details>

<details>
<summary><strong>Boutons : 2 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Sélectionner | 29,143 | Bouton fonctionnel |
| Quitter | 209,143 | Quitte le programme |

</details>

## 9. NAVIGATION

### 9.1 Enchainement des ecrans

```mermaid
flowchart TD
    START([Entree])
    style START fill:#3fb950
    VF4[373.2 Affichage Personnel]
    style VF4 fill:#58a6ff
    VF5[373.2.1 Recherche]
    style VF5 fill:#58a6ff
    VF14[373.2.6.2 Selection Fonction]
    style VF14 fill:#58a6ff
    EXT309[IDE 309 Redirection to...]
    style EXT309 fill:#3fb950
    EXT356[IDE 356 Zoom nationalite]
    style EXT356 fill:#3fb950
    EXT320[IDE 320 Verification A...]
    style EXT320 fill:#3fb950
    EXT336[IDE 336 Création Villa...]
    style EXT336 fill:#3fb950
    EXT337[IDE 337 Recherche Exis...]
    style EXT337 fill:#3fb950
    EXT355[IDE 355 Zoom langue]
    style EXT355 fill:#3fb950
    EXT366[IDE 366 Zoom QualiteCP]
    style EXT366 fill:#3fb950
    EXT370[IDE 370 Zoom VillageVi...]
    style EXT370 fill:#3fb950
    EXT181[IDE 181 Creation Histo...]
    style EXT181 fill:#3fb950
    EXT194[IDE 194 Creation perso...]
    style EXT194 fill:#3fb950
    EXT312[IDE 312 Determination ...]
    style EXT312 fill:#3fb950
    EXT317[IDE 317 Recuperation d...]
    style EXT317 fill:#3fb950
    FIN([Sortie])
    style FIN fill:#f85149
    START --> VF4
    VF4 -->|Sous-programme| EXT309
    VF4 -->|Selection/consultation| EXT356
    VF4 -->|Controle/validation| EXT320
    VF4 -->|Sous-programme| EXT336
    VF4 -->|Sous-programme| EXT337
    VF4 -->|Selection/consultation| EXT355
    VF4 -->|Selection/consultation| EXT366
    VF4 -->|Selection/consultation| EXT370
    EXT317 --> FIN
```

**Detail par enchainement :**

| Depuis | Action | Vers | Retour |
|--------|--------|------|--------|
| Affichage Personnel | Sous-programme | [Redirection touches (IDE 309)](PBG-IDE-309.md) | Retour ecran |
| Affichage Personnel | Selection/consultation | [Zoom nationalite (IDE 356)](PBG-IDE-356.md) | Retour ecran |
| Affichage Personnel | Controle/validation | [Verification Aut sans ecran (IDE 320)](PBG-IDE-320.md) | Retour ecran |
| Affichage Personnel | Sous-programme | [Création Village/Village (IDE 336)](PBG-IDE-336.md) | Retour ecran |
| Affichage Personnel | Sous-programme | [Recherche Existance Groupe A/D (IDE 337)](PBG-IDE-337.md) | Retour ecran |
| Affichage Personnel | Selection/consultation | [Zoom langue (IDE 355)](PBG-IDE-355.md) | Retour ecran |
| Affichage Personnel | Selection/consultation | [Zoom Qualite(C/P) (IDE 366)](PBG-IDE-366.md) | Retour ecran |
| Affichage Personnel | Selection/consultation | [Zoom Village/Village (IDE 370)](PBG-IDE-370.md) | Retour ecran |
| Affichage Personnel | Historique/consultation | [Creation Historique (IDE 181)](PBG-IDE-181.md) | Retour ecran |
| Affichage Personnel | Sous-programme | [  Creation personnel identites (IDE 194)](PBG-IDE-194.md) | Retour ecran |
| Affichage Personnel | Sous-programme | [Determination Age Debut Sejour (IDE 312)](PBG-IDE-312.md) | Retour ecran |
| Affichage Personnel | Recuperation donnees | [Recuperation du titre (IDE 317)](PBG-IDE-317.md) | Retour ecran |

### 9.3 Structure hierarchique (25 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **373.1** | [**Module des Identites** (373)](#t1) | MDI | - | Traitement |
| 373.1.1 | [Determination Age Bebe (373.1)](#t2) | MDI | - | |
| 373.1.2 | [Langue ? (373.2.2)](#t8) | MDI | - | |
| 373.1.3 | [Lecture Qualite&Occupation (373.2.5)](#t11) | MDI | - | |
| 373.1.4 | [Determination Fonction (373.2.6)](#t12) [mockup](#ecran-t12) | MDI | 108x8 | |
| 373.1.5 | [Determination Service (373.2.6.1)](#t13) | MDI | - | |
| 373.1.6 | [Veuillez patienter... (373.2.7)](#t15) [mockup](#ecran-t15) | MDI | 422x56 | |
| 373.1.7 | [Maj base occup (373.2.10)](#t29) | - | - | |
| **373.2** | [**Affichage Personnel** (373.2)](#t4) [mockup](#ecran-t4) | MDI | 1130x370 | Consultation |
| 373.2.1 | [Recherche (373.2.1)](#t5) [mockup](#ecran-t5) | MDI | 578x101 | |
| 373.2.2 | [Selection Fonction (373.2.6.2)](#t14) [mockup](#ecran-t14) | MDI | 390x167 | |
| 373.2.3 | [Creation Recherche (373.2.7.8)](#t23) | MDI | - | |
| **373.3** | [**Attribution Compte** (373.2.3)](#t9) | MDI | - | Calcul |
| 373.3.1 | [Attribution Compte (373.2.4)](#t10) | MDI | - | |
| 373.3.2 | [Creation Compte (373.2.7.7)](#t22) | MDI | - | |
| **373.4** | [**Creation Complet** (373.2.7.1)](#t16) | MDI | - | Creation |
| 373.4.1 | [Creation Hebergement (373.2.7.2)](#t17) | MDI | - | |
| 373.4.2 | [Creation Hebergement (373.2.7.3)](#t18) | MDI | - | |
| 373.4.3 | [Creation Hebergement (373.2.7.4)](#t19) | MDI | - | |
| 373.4.4 | [Creation Package Aller (373.2.7.5)](#t20) | MDI | - | |
| 373.4.5 | [Creation Package Retour (373.2.7.6)](#t21) | MDI | - | |
| 373.4.6 | [Creation Complet (373.2.7.10)](#t25) | MDI | - | |
| 373.4.7 | [Creation personnel (373.2.8)](#t27) | MDI | - | |
| 373.4.8 | [Creation personnel (373.2.9)](#t28) | MDI | - | |
| **373.5** | [**Creation Validation** (373.2.7.9)](#t24) | MDI | - | Validation |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Affichage Personnel Nom]
    UPDATE[MAJ 7 tables]
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

### Tables utilisees (15)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 30 | gm-recherche_____gmr | Index de recherche | DB |   | **W** |   | 2 |
| 31 | gm-complet_______gmc |  | DB |   | **W** | L | 2 |
| 34 | hebergement______heb | Hebergement (chambres) | DB | R | **W** | L | 8 |
| 35 | personnel_go______go |  | DB |   |   | L | 1 |
| 47 | compte_gm________cgm | Comptes GM (generaux) | DB |   | **W** | L | 2 |
| 63 | parametres___par |  | DB | R |   |   | 1 |
| 68 | compteurs________cpt | Comptes GM (generaux) | DB |   | **W** |   | 2 |
| 78 | param__telephone_tel |  | DB |   |   | L | 1 |
| 113 | tables_village |  | DB | R |   |   | 2 |
| 117 | tables_services | Services / filieres | DB | R |   | L | 3 |
| 119 | tables_pays_tel_ |  | DB |   |   | L | 1 |
| 130 | fichier_langue |  | DB |   |   | L | 1 |
| 131 | fichier_validation |  | DB |   | **W** |   | 1 |
| 315 | fi_complet_______gm_go |  | DB |   | **W** |   | 1 |
| 805 | vente_par_moyen_paiement | Donnees de ventes | DB |   |   | L | 1 |

### Colonnes par table (3 / 10 tables avec colonnes identifiees)

<details>
<summary>Table 30 - gm-recherche_____gmr (**W**) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | W1-Fin de Tache | W | Logical |
| B | W1-Arrêt | W | Alpha |
| C | W1-Age codifie | W | Alpha |
| D | W1-Nb mois | W | Numeric |
| E | W1-Bebe | W | Alpha |
| F | W1-Acces planning | W | Alpha |
| G | W1- Numero compte memo | W | Numeric |
| H | W1-Select qualite | W | Alpha |
| I | v. bouton qualite | W | Alpha |
| J | W1-Select titre | W | Alpha |
| K | W1-Select Service | W | Alpha |
| L | v.bouton fonction | W | Alpha |
| M | W1-Select Contrat | W | Alpha |
| N | W1-Combo Lieu Sejour | W | Alpha |
| O | bouton date debut | W | Alpha |
| P | W1-Select Vol Aller | W | Alpha |
| Q | bouton date fin | W | Alpha |
| R | bouton nationalite | W | Alpha |
| S | W1-select nationalite | W | Alpha |
| T | W1-Select Langue | W | Alpha |
| U | W1-Base occupation | W | Alpha |
| V | bouton date delivrance | W | Alpha |
| W | bouton langue | W | Alpha |
| X | V.Existe ECI (Q60 Location) | W | Logical |
| Y | V.Existe ECI (Q61 Cours) | W | Logical |
| Z | V.Existe ECI (Q62 Enfant) | W | Logical |
| BA | v Libelle affichage ECI | W | Alpha |
| BB | v.V/V Aller | W | Alpha |
| BC | v.V/V Retour | W | Alpha |
| BD | bouton annuler | W | Alpha |
| BE | bouton modifier | W | Alpha |
| BF | bouton creer | W | Alpha |
| BG | bouton visu | W | Alpha |
| BH | bouton recherche | W | Alpha |
| BI | v.Retour Question Bsi | W | Numeric |
| BJ | v.Modif Lieu Séjour ? | W | Logical |
| BK | v.Existe Code VV Aller | W | Logical |
| BL | v.Code VV Aller | W | Alpha |
| BM | v.Heure VV Aller | W | Alpha |
| BN | v.Existe Code VV Retour | W | Logical |
| BO | v.Code VV Retour | W | Alpha |
| BP | v.Heure VV Retour | W | Alpha |
| BQ | CHG_REASON_go_bsi_ok | W | Numeric |
| BR | CHG_PRV_go_bsi_ok | W | Logical |
| BS | Column Name | W | Unicode |

</details>

<details>
<summary>Table 31 - gm-complet_______gmc (**W**/L) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 34 - hebergement______heb (R/**W**/L) - 8 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 47 - compte_gm________cgm (**W**/L) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| G | W0-numero compte memo | W | Numeric |
| Q | W0-Compte | W | Numeric |

</details>

<details>
<summary>Table 63 - parametres___par (R) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 68 - compteurs________cpt (**W**) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 113 - tables_village (R) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 117 - tables_services (R/L) - 3 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 131 - fichier_validation (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 315 - fi_complet_______gm_go (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (1)

Variables recues en parametre.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| B | P0 Front/Back | Alpha | 2x parametre entrant |

### 11.2 Variables de session (15)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| F | v.ecran titre | Alpha | - |
| X | V.Existe ECI (Q60 Location) | Logical | - |
| Y | V.Existe ECI (Q61 Cours) | Logical | - |
| Z | V.Existe ECI (Q62 Enfant) | Logical | - |
| BA | v Libelle affichage ECI | Alpha | - |
| BB | v.V/V Aller | Alpha | - |
| BC | v.V/V Retour | Alpha | - |
| BI | v.Retour Question Bsi | Numeric | - |
| BJ | v.Modif Lieu Séjour ? | Logical | - |
| BK | v.Existe Code VV Aller | Logical | - |
| BL | v.Code VV Aller | Alpha | - |
| BM | v.Heure VV Aller | Alpha | - |
| BN | v.Existe Code VV Retour | Logical | - |
| BO | v.Code VV Retour | Alpha | - |
| BP | v.Heure VV Retour | Alpha | - |

### 11.3 Autres (29)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | > Mode attaque ecran | Alpha | 1x refs |
| C | W0-Age Bebe | Numeric | - |
| D | W0-Base Vide | Alpha | - |
| E | WO-Valeur tri | Numeric | 1x refs |
| G | W0-numero compte memo | Numeric | - |
| H | W0-autorisation creation | Alpha | - |
| I | W0-autorisation modif | Alpha | - |
| J | W0-autorisation | Alpha | - |
| K | W0-code base occup | Alpha | - |
| L | W0-heberg | Alpha | - |
| M | W0-Saisie langue ? | Alpha | - |
| N | W0-Bloquage effectue | Alpha | - |
| O | W0-Table service | Alpha | - |
| P | W0-Code fonction | Alpha | - |
| Q | W0-Compte | Numeric | - |
| R | W0-Adhesion | Numeric | - |
| S | WO-Fin de tache | Logical | 1x refs |
| T | W1-Select Langue | Alpha | - |
| U | W1-Base occupation | Alpha | - |
| V | bouton date delivrance | Alpha | - |
| W | bouton langue | Alpha | - |
| BD | bouton annuler | Alpha | - |
| BE | bouton modifier | Alpha | - |
| BF | bouton creer | Alpha | - |
| BG | bouton visu | Alpha | - |
| BH | bouton recherche | Alpha | - |
| BQ | CHG_REASON_go_bsi_ok | Numeric | - |
| BR | CHG_PRV_go_bsi_ok | Logical | - |
| BS | Column Name | Unicode | - |

<details>
<summary>Toutes les 45 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| P0 | **B** | P0 Front/Back | Alpha |
| V. | **F** | v.ecran titre | Alpha |
| V. | **X** | V.Existe ECI (Q60 Location) | Logical |
| V. | **Y** | V.Existe ECI (Q61 Cours) | Logical |
| V. | **Z** | V.Existe ECI (Q62 Enfant) | Logical |
| V. | **BA** | v Libelle affichage ECI | Alpha |
| V. | **BB** | v.V/V Aller | Alpha |
| V. | **BC** | v.V/V Retour | Alpha |
| V. | **BI** | v.Retour Question Bsi | Numeric |
| V. | **BJ** | v.Modif Lieu Séjour ? | Logical |
| V. | **BK** | v.Existe Code VV Aller | Logical |
| V. | **BL** | v.Code VV Aller | Alpha |
| V. | **BM** | v.Heure VV Aller | Alpha |
| V. | **BN** | v.Existe Code VV Retour | Logical |
| V. | **BO** | v.Code VV Retour | Alpha |
| V. | **BP** | v.Heure VV Retour | Alpha |
| Autre | **A** | > Mode attaque ecran | Alpha |
| Autre | **C** | W0-Age Bebe | Numeric |
| Autre | **D** | W0-Base Vide | Alpha |
| Autre | **E** | WO-Valeur tri | Numeric |
| Autre | **G** | W0-numero compte memo | Numeric |
| Autre | **H** | W0-autorisation creation | Alpha |
| Autre | **I** | W0-autorisation modif | Alpha |
| Autre | **J** | W0-autorisation | Alpha |
| Autre | **K** | W0-code base occup | Alpha |
| Autre | **L** | W0-heberg | Alpha |
| Autre | **M** | W0-Saisie langue ? | Alpha |
| Autre | **N** | W0-Bloquage effectue | Alpha |
| Autre | **O** | W0-Table service | Alpha |
| Autre | **P** | W0-Code fonction | Alpha |
| Autre | **Q** | W0-Compte | Numeric |
| Autre | **R** | W0-Adhesion | Numeric |
| Autre | **S** | WO-Fin de tache | Logical |
| Autre | **T** | W1-Select Langue | Alpha |
| Autre | **U** | W1-Base occupation | Alpha |
| Autre | **V** | bouton date delivrance | Alpha |
| Autre | **W** | bouton langue | Alpha |
| Autre | **BD** | bouton annuler | Alpha |
| Autre | **BE** | bouton modifier | Alpha |
| Autre | **BF** | bouton creer | Alpha |
| Autre | **BG** | bouton visu | Alpha |
| Autre | **BH** | bouton recherche | Alpha |
| Autre | **BQ** | CHG_REASON_go_bsi_ok | Numeric |
| Autre | **BR** | CHG_PRV_go_bsi_ok | Logical |
| Autre | **BS** | Column Name | Unicode |

</details>

## 12. EXPRESSIONS

**15 / 15 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONDITION | 5 | 5 |
| CONSTANTE | 7 | 0 |
| OTHER | 3 | 0 |

### 12.2 Expressions cles par type

#### CONDITION (5 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 3 | `IF (Trim (> Mode attaque ecran [A])='','E'MODE,> Mode attaque ecran [A])` | [RM-001](#rm-RM-001) |
| CONDITION | 13 | `P0 Front/Back [B]='B'` | - |
| CONDITION | 15 | `Level (1)<>''` | - |
| CONDITION | 5 | `WO-Valeur tri [E]=0` | - |
| CONDITION | 12 | `P0 Front/Back [B]='F'` | - |

#### CONSTANTE (7 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 10 | `'09'` | - |
| CONSTANTE | 11 | `'10'` | - |
| CONSTANTE | 14 | `'O'` | - |
| CONSTANTE | 6 | `2` | - |
| CONSTANTE | 1 | `'N'` | - |
| ... | | *+2 autres* | |

#### OTHER (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 9 | `GetParam ('SOCIETE')` | - |
| OTHER | 8 | `WO-Fin de tache [S]` | - |
| OTHER | 7 | `GetParam ('FRONT')` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

**Chemin**: (pas de callers directs)

```mermaid
graph LR
    T373[373 Module personnel i...]
    style T373 fill:#58a6ff
    NONE[Aucun caller]
    NONE -.-> T373
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| - | (aucun) | - |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T373[373 Module personnel i...]
    style T373 fill:#58a6ff
    C309[309 Redirection touches]
    T373 --> C309
    style C309 fill:#3fb950
    C356[356 Zoom nationalite]
    T373 --> C356
    style C356 fill:#3fb950
    C320[320 Verification Aut s...]
    T373 --> C320
    style C320 fill:#3fb950
    C336[336 Création VillageVi...]
    T373 --> C336
    style C336 fill:#3fb950
    C337[337 Recherche Existanc...]
    T373 --> C337
    style C337 fill:#3fb950
    C355[355 Zoom langue]
    T373 --> C355
    style C355 fill:#3fb950
    C366[366 Zoom QualiteCP]
    T373 --> C366
    style C366 fill:#3fb950
    C370[370 Zoom VillageVillage]
    T373 --> C370
    style C370 fill:#3fb950
    C181[181 Creation Historique]
    T373 --> C181
    style C181 fill:#3fb950
    C194[194 Creation personnel...]
    T373 --> C194
    style C194 fill:#3fb950
    C312[312 Determination Age ...]
    T373 --> C312
    style C312 fill:#3fb950
    C317[317 Recuperation du titre]
    T373 --> C317
    style C317 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [309](PBG-IDE-309.md) | Redirection touches | 4 | Sous-programme |
| [356](PBG-IDE-356.md) | Zoom nationalite | 3 | Selection/consultation |
| [320](PBG-IDE-320.md) | Verification Aut sans ecran | 2 | Controle/validation |
| [336](PBG-IDE-336.md) | Création Village/Village | 2 | Sous-programme |
| [337](PBG-IDE-337.md) | Recherche Existance Groupe A/D | 2 | Sous-programme |
| [355](PBG-IDE-355.md) | Zoom langue | 2 | Selection/consultation |
| [366](PBG-IDE-366.md) | Zoom Qualite(C/P) | 2 | Selection/consultation |
| [370](PBG-IDE-370.md) | Zoom Village/Village | 2 | Selection/consultation |
| [181](PBG-IDE-181.md) | Creation Historique | 1 | Historique/consultation |
| [194](PBG-IDE-194.md) |   Creation personnel identites | 1 | Sous-programme |
| [312](PBG-IDE-312.md) | Determination Age Debut Sejour | 1 | Sous-programme |
| [317](PBG-IDE-317.md) | Recuperation du titre | 1 | Recuperation donnees |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 827 | Programme volumineux |
| Expressions | 15 | Peu de logique |
| Tables WRITE | 7 | Fort impact donnees |
| Sous-programmes | 12 | Forte dependance |
| Ecrans visibles | 3 | Quelques ecrans |
| Code desactive | 0.7% (6 / 827) | Code sain |
| Regles metier | 1 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (8 taches: 2 ecrans, 6 traitements)

- **Strategie** : Orchestrateur avec 2 ecrans (Razor/React) et 6 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 12 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Consultation (4 taches: 3 ecrans, 1 traitement)

- **Strategie** : Composants de recherche/selection en modales.
- 3 ecrans : Affichage Personnel, Recherche, Selection Fonction

#### Calcul (3 taches: 0 ecran, 3 traitements)

- **Strategie** : Services de calcul purs (Domain Services).
- Migrer la logique de calcul (stock, compteurs, montants)

#### Creation (9 taches: 0 ecran, 9 traitements)

- **Strategie** : Repository pattern avec Entity Framework Core.
- Insertion via `IRepository<T>.CreateAsync()`

#### Validation (1 tache: 0 ecran, 1 traitement)

- **Strategie** : FluentValidation avec validators specifiques.
- Chaque tache de validation -> un validator injectable

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| gm-recherche_____gmr | Table WRITE (Database) | 2x | Schema + repository |
| gm-complet_______gmc | Table WRITE (Database) | 1x | Schema + repository |
| hebergement______heb | Table WRITE (Database) | 6x | Schema + repository |
| compte_gm________cgm | Table WRITE (Database) | 1x | Schema + repository |
| compteurs________cpt | Table WRITE (Database) | 2x | Schema + repository |
| fichier_validation | Table WRITE (Database) | 1x | Schema + repository |
| fi_complet_______gm_go | Table WRITE (Database) | 1x | Schema + repository |
| [Redirection touches (IDE 309)](PBG-IDE-309.md) | Sous-programme | 4x | **CRITIQUE** - Sous-programme |
| [Zoom nationalite (IDE 356)](PBG-IDE-356.md) | Sous-programme | 3x | **CRITIQUE** - Selection/consultation |
| [Zoom langue (IDE 355)](PBG-IDE-355.md) | Sous-programme | 2x | Haute - Selection/consultation |
| [Zoom Qualite(C/P) (IDE 366)](PBG-IDE-366.md) | Sous-programme | 2x | Haute - Selection/consultation |
| [Zoom Village/Village (IDE 370)](PBG-IDE-370.md) | Sous-programme | 2x | Haute - Selection/consultation |
| [Verification Aut sans ecran (IDE 320)](PBG-IDE-320.md) | Sous-programme | 2x | Haute - Controle/validation |
| [Création Village/Village (IDE 336)](PBG-IDE-336.md) | Sous-programme | 2x | Haute - Sous-programme |
| [Recherche Existance Groupe A/D (IDE 337)](PBG-IDE-337.md) | Sous-programme | 2x | Haute - Sous-programme |
| [Determination Age Debut Sejour (IDE 312)](PBG-IDE-312.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Recuperation du titre (IDE 317)](PBG-IDE-317.md) | Sous-programme | 1x | Normale - Recuperation donnees |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 11:30*
