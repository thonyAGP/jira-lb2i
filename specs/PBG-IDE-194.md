# PBG IDE 194 - Creation personnel identites

> **Analyse**: Phases 1-4 2026-02-03 10:06 -> 10:06 (19s) | Assemblage 10:06
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBG |
| IDE Position | 194 |
| Nom Programme | Creation personnel identites |
| Fichier source | `Prg_194.xml` |
| Domaine metier | General |
| Taches | 17 (4 ecrans visibles) |
| Tables modifiees | 6 |
| Programmes appeles | 11 |

## 2. DESCRIPTION FONCTIONNELLE

**Creation personnel identites** assure la gestion complete de ce processus, accessible depuis [Sejours personnel SubForm (IDE 0)](PBG-IDE-0.md), [Personnel Identites (IDE 195)](PBG-IDE-195.md), [Sejours personnel CallTask (IDE 196)](PBG-IDE-196.md), [Module personnel identites (IDE 373)](PBG-IDE-373.md).

Le flux de traitement s'organise en **5 blocs fonctionnels** :

- **Traitement** (8 taches) : traitements metier divers
- **Creation** (3 taches) : insertion d'enregistrements en base (mouvements, prestations)
- **Calcul** (2 taches) : calculs de montants, stocks ou compteurs
- **Validation** (2 taches) : controles et verifications de coherence
- **Consultation** (2 taches) : ecrans de recherche, selection et consultation

**Donnees modifiees** : 6 tables en ecriture (gm-recherche_____gmr, hebergement______heb, compte_gm________cgm, compteurs________cpt, fichier_validation, Table_1092).

**Logique metier** : 1 regles identifiees couvrant valeurs par defaut.

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (8 taches)

- **194** - Module des Identites
- **194.1** - Determination Age Bebe
- **194.2.1** - Langue ?
- **194.2.2** - Lecture Qualite&Occupation
- **194.2.3** - Determination Fonction **[[ECRAN]](#ecran-t7)**
- **194.2.3.1** - Determination Service
- **194.2.4** - Veuillez patienter... **[[ECRAN]](#ecran-t10)**
- **194.2.5.1** - (sans nom) **[[ECRAN]](#ecran-t40)**

Delegue a : [Création Village/Village (IDE 336)](PBG-IDE-336.md), [Determination Age Debut Sejour (IDE 312)](PBG-IDE-312.md), [Recuperation du titre (IDE 317)](PBG-IDE-317.md)

#### Phase 2 : Creation (3 taches)

- **194.2** - Creation personnel **[[ECRAN]](#ecran-t4)**
- **194.2.4.2** - Creation Package Aller
- **194.2.4.3** - Creation Package Retour

Delegue a : [Creation Historique (IDE 181)](PBG-IDE-181.md)

#### Phase 3 : Consultation (2 taches)

- **194.2.3.2** - Selection Fonction **[[ECRAN]](#ecran-t9)**
- **194.2.5** - Selection Fonction **[[ECRAN]](#ecran-t39)**

Delegue a : [Zoom nationalite (IDE 356)](PBG-IDE-356.md), [Recherche Existance Groupe A/D (IDE 337)](PBG-IDE-337.md), [Zoom langue (IDE 355)](PBG-IDE-355.md), [Zoom Qualite(C/P) (IDE 366)](PBG-IDE-366.md), [Zoom Village/Village (IDE 370)](PBG-IDE-370.md), [Recuperation du titre (IDE 317)](PBG-IDE-317.md)

#### Phase 4 : Validation (2 taches)

- **194.2.4.1** - Verification Planning
- **194.2.4.5** - Creation Validation

Delegue a : [Verification Aut sans ecran (IDE 320)](PBG-IDE-320.md)

#### Phase 5 : Calcul (2 taches)

- **194.2.4.4** - Creation Compte
- **194.3** - Attribution Compte

Delegue a : [Vérification compteur compte (IDE 351)](PBG-IDE-351.md)

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| hebergement______heb | R/**W**/L (4 usages) | Hebergement (chambres) |
| Table_1092 | **W**/L (2 usages) |  |
| gm-recherche_____gmr | **W** (1 usages) | Index de recherche |
| fichier_validation | **W** (1 usages) |  |
| compteurs________cpt | **W** (1 usages) | Comptes GM (generaux) |
| compte_gm________cgm | **W** (1 usages) | Comptes GM (generaux) |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (8 taches)

Traitements internes.

---

#### <a id="t1"></a>194 - Module des Identites

**Role** : Tache d'orchestration : point d'entree du programme (8 sous-taches). Coordonne l'enchainement des traitements.

<details>
<summary>7 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [194.1](#t2) | Determination Age Bebe | Traitement |
| [194.2.1](#t5) | Langue ? | Traitement |
| [194.2.2](#t6) | Lecture Qualite&Occupation | Traitement |
| [194.2.3](#t7) | Determination Fonction **[[ECRAN]](#ecran-t7)** | Traitement |
| [194.2.3.1](#t8) | Determination Service | Traitement |
| [194.2.4](#t10) | Veuillez patienter... **[[ECRAN]](#ecran-t10)** | Traitement |
| [194.2.5.1](#t40) | (sans nom) **[[ECRAN]](#ecran-t40)** | Traitement |

</details>
**Delegue a** : [Création Village/Village (IDE 336)](PBG-IDE-336.md), [Determination Age Debut Sejour (IDE 312)](PBG-IDE-312.md), [Recuperation du titre (IDE 317)](PBG-IDE-317.md)

---

#### <a id="t2"></a>194.1 - Determination Age Bebe

**Role** : Traitement : Determination Age Bebe.
**Variables liees** : C (W0-Age Bebe)
**Delegue a** : [Création Village/Village (IDE 336)](PBG-IDE-336.md), [Determination Age Debut Sejour (IDE 312)](PBG-IDE-312.md), [Recuperation du titre (IDE 317)](PBG-IDE-317.md)

---

#### <a id="t5"></a>194.2.1 - Langue ?

**Role** : Traitement : Langue ?.
**Variables liees** : T (v. bouton langue), L (W0-Saisie langue ?)
**Delegue a** : [Création Village/Village (IDE 336)](PBG-IDE-336.md), [Determination Age Debut Sejour (IDE 312)](PBG-IDE-312.md), [Recuperation du titre (IDE 317)](PBG-IDE-317.md)

---

#### <a id="t6"></a>194.2.2 - Lecture Qualite&Occupation

**Role** : Traitement : Lecture Qualite&Occupation.
**Delegue a** : [Création Village/Village (IDE 336)](PBG-IDE-336.md), [Determination Age Debut Sejour (IDE 312)](PBG-IDE-312.md), [Recuperation du titre (IDE 317)](PBG-IDE-317.md)

---

#### <a id="t7"></a>194.2.3 - Determination Fonction [[ECRAN]](#ecran-t7)

**Role** : Traitement : Determination Fonction.
**Ecran** : 108 x 8 DLU (MDI) | [Voir mockup](#ecran-t7)
**Variables liees** : O (W0-Code fonction)
**Delegue a** : [Création Village/Village (IDE 336)](PBG-IDE-336.md), [Determination Age Debut Sejour (IDE 312)](PBG-IDE-312.md), [Recuperation du titre (IDE 317)](PBG-IDE-317.md)

---

#### <a id="t8"></a>194.2.3.1 - Determination Service

**Role** : Traitement : Determination Service.
**Variables liees** : N (W0-Table service)
**Delegue a** : [Création Village/Village (IDE 336)](PBG-IDE-336.md), [Determination Age Debut Sejour (IDE 312)](PBG-IDE-312.md), [Recuperation du titre (IDE 317)](PBG-IDE-317.md)

---

#### <a id="t10"></a>194.2.4 - Veuillez patienter... [[ECRAN]](#ecran-t10)

**Role** : Traitement : Veuillez patienter....
**Ecran** : 422 x 56 DLU (MDI) | [Voir mockup](#ecran-t10)
**Delegue a** : [Création Village/Village (IDE 336)](PBG-IDE-336.md), [Determination Age Debut Sejour (IDE 312)](PBG-IDE-312.md), [Recuperation du titre (IDE 317)](PBG-IDE-317.md)

---

#### <a id="t40"></a>194.2.5.1 - (sans nom) [[ECRAN]](#ecran-t40)

**Role** : Traitement interne.
**Ecran** : 180 x 120 DLU | [Voir mockup](#ecran-t40)
**Delegue a** : [Création Village/Village (IDE 336)](PBG-IDE-336.md), [Determination Age Debut Sejour (IDE 312)](PBG-IDE-312.md), [Recuperation du titre (IDE 317)](PBG-IDE-317.md)


### 3.2 Creation (3 taches)

Insertion de nouveaux enregistrements en base.

---

#### <a id="t4"></a>194.2 - Creation personnel [[ECRAN]](#ecran-t4)

**Role** : Creation d'enregistrement : Creation personnel.
**Ecran** : 734 x 383 DLU (MDI) | [Voir mockup](#ecran-t4)
**Variables liees** : BE (v Suite Creation), G (W0-autorisation creation)
**Delegue a** : [Creation Historique (IDE 181)](PBG-IDE-181.md)

---

#### <a id="t12"></a>194.2.4.2 - Creation Package Aller

**Role** : Creation d'enregistrement : Creation Package Aller.
**Variables liees** : U (v.bouton.V/VAller), Y (v Existe Code VV Aller), Z (v Code VV Aller), BA (v Heure VV Aller), BE (v Suite Creation)
**Delegue a** : [Creation Historique (IDE 181)](PBG-IDE-181.md)

---

#### <a id="t13"></a>194.2.4.3 - Creation Package Retour

**Role** : Creation d'enregistrement : Creation Package Retour.
**Variables liees** : V (v.bouton V/V Retour), X (v.Retour Question Bsi), BB (v Existe Code VV Retour), BC (v Code VV Retour), BD (v Heure VV Retour)
**Delegue a** : [Creation Historique (IDE 181)](PBG-IDE-181.md)


### 3.3 Consultation (2 taches)

Ecrans de recherche et consultation.

---

#### <a id="t9"></a>194.2.3.2 - Selection Fonction [[ECRAN]](#ecran-t9)

**Role** : Selection par l'operateur : Selection Fonction.
**Ecran** : 392 x 167 DLU (MDI) | [Voir mockup](#ecran-t9)
**Variables liees** : O (W0-Code fonction)
**Delegue a** : [Zoom nationalite (IDE 356)](PBG-IDE-356.md), [Recherche Existance Groupe A/D (IDE 337)](PBG-IDE-337.md), [Zoom langue (IDE 355)](PBG-IDE-355.md)

---

#### <a id="t39"></a>194.2.5 - Selection Fonction [[ECRAN]](#ecran-t39)

**Role** : Selection par l'operateur : Selection Fonction.
**Ecran** : 758 x 183 DLU (MDI) | [Voir mockup](#ecran-t39)
**Variables liees** : O (W0-Code fonction)
**Delegue a** : [Zoom nationalite (IDE 356)](PBG-IDE-356.md), [Recherche Existance Groupe A/D (IDE 337)](PBG-IDE-337.md), [Zoom langue (IDE 355)](PBG-IDE-355.md)


### 3.4 Validation (2 taches)

Controles de coherence : 2 taches verifient les donnees et conditions.

---

#### <a id="t11"></a>194.2.4.1 - Verification Planning

**Role** : Verification : Verification Planning.
**Delegue a** : [Verification Aut sans ecran (IDE 320)](PBG-IDE-320.md)

---

#### <a id="t15"></a>194.2.4.5 - Creation Validation

**Role** : Verification : Creation Validation.
**Variables liees** : BE (v Suite Creation), G (W0-autorisation creation)
**Delegue a** : [Verification Aut sans ecran (IDE 320)](PBG-IDE-320.md), [Creation Historique (IDE 181)](PBG-IDE-181.md)


### 3.5 Calcul (2 taches)

Calculs metier : montants, stocks, compteurs.

---

#### <a id="t14"></a>194.2.4.4 - Creation Compte

**Role** : Creation d'enregistrement : Creation Compte.
**Variables liees** : BE (v Suite Creation), F (W0-numero compte memo), G (W0-autorisation creation), P (W0-Compte)
**Delegue a** : [Creation Historique (IDE 181)](PBG-IDE-181.md), [Vérification compteur compte (IDE 351)](PBG-IDE-351.md)

---

#### <a id="t16"></a>194.3 - Attribution Compte

**Role** : Traitement : Attribution Compte.
**Variables liees** : F (W0-numero compte memo), P (W0-Compte)
**Delegue a** : [Vérification compteur compte (IDE 351)](PBG-IDE-351.md)


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

- **Appele par**: [Sejours personnel SubForm (IDE 0)](PBG-IDE-0.md), [Personnel Identites (IDE 195)](PBG-IDE-195.md), [Sejours personnel CallTask (IDE 196)](PBG-IDE-196.md), [Module personnel identites (IDE 373)](PBG-IDE-373.md)
- **Appelle**: 11 programmes | **Tables**: 14 (W:6 R:4 L:8) | **Taches**: 17 | **Expressions**: 12

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (4 / 17)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 194.2 | 194.2 | Creation personnel | MDI | 734 | 383 | Creation |
| 2 | 194.2.4.2 | 194.2.3.2 | Selection Fonction | MDI | 392 | 167 | Consultation |
| 3 | 194.2.1 | 194.2.5 | Selection Fonction | MDI | 758 | 183 | Consultation |
| 4 | 194.2.1.1 | 194.2.5.1 | (sans nom) | Type0 | 180 | 120 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t4"></a>194.2 - Creation personnel
**Tache** : [194.2](#t4) | **Type** : MDI | **Dimensions** : 734 x 383 DLU
**Bloc** : Creation | **Titre IDE** : Creation personnel

<!-- FORM-DATA:
{
    "width":  734,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  1,
                         "type":  "label",
                         "var":  "",
                         "y":  1,
                         "w":  724,
                         "fmt":  "",
                         "name":  "",
                         "h":  19,
                         "color":  "1",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  12,
                         "type":  "label",
                         "var":  "",
                         "y":  23,
                         "w":  716,
                         "fmt":  "",
                         "name":  "",
                         "h":  328,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  21,
                         "type":  "label",
                         "var":  "",
                         "y":  31,
                         "w":  83,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "Nom",
                         "parent":  4
                     },
                     {
                         "x":  358,
                         "type":  "label",
                         "var":  "",
                         "y":  31,
                         "w":  42,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "Titre",
                         "parent":  4
                     },
                     {
                         "x":  21,
                         "type":  "label",
                         "var":  "",
                         "y":  47,
                         "w":  82,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "Prénom",
                         "parent":  4
                     },
                     {
                         "x":  358,
                         "type":  "label",
                         "var":  "",
                         "y":  47,
                         "w":  71,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "Qualité",
                         "parent":  4
                     },
                     {
                         "x":  21,
                         "type":  "label",
                         "var":  "",
                         "y":  78,
                         "w":  66,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "Service",
                         "parent":  4
                     },
                     {
                         "x":  21,
                         "type":  "label",
                         "var":  "",
                         "y":  96,
                         "w":  82,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Fonction",
                         "parent":  4
                     },
                     {
                         "x":  21,
                         "type":  "label",
                         "var":  "",
                         "y":  112,
                         "w":  75,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "Contrat",
                         "parent":  4
                     },
                     {
                         "x":  21,
                         "type":  "label",
                         "var":  "",
                         "y":  179,
                         "w":  67,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Arrivée",
                         "parent":  4
                     },
                     {
                         "x":  21,
                         "type":  "label",
                         "var":  "",
                         "y":  193,
                         "w":  75,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Départ",
                         "parent":  4
                     },
                     {
                         "x":  21,
                         "type":  "label",
                         "var":  "",
                         "y":  208,
                         "w":  154,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Date de Naissance",
                         "parent":  4
                     },
                     {
                         "x":  358,
                         "type":  "label",
                         "var":  "",
                         "y":  208,
                         "w":  43,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Age",
                         "parent":  4
                     },
                     {
                         "x":  21,
                         "type":  "label",
                         "var":  "",
                         "y":  222,
                         "w":  93,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Nationalité",
                         "parent":  4
                     },
                     {
                         "x":  21,
                         "type":  "label",
                         "var":  "",
                         "y":  237,
                         "w":  96,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "Occupation",
                         "parent":  4
                     },
                     {
                         "x":  21,
                         "type":  "label",
                         "var":  "",
                         "y":  254,
                         "w":  64,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Identité",
                         "parent":  4
                     },
                     {
                         "x":  21,
                         "type":  "label",
                         "var":  "",
                         "y":  268,
                         "w":  77,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Délivré",
                         "parent":  4
                     },
                     {
                         "x":  358,
                         "type":  "label",
                         "var":  "",
                         "y":  270,
                         "w":  45,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Date",
                         "parent":  4
                     },
                     {
                         "x":  25,
                         "type":  "label",
                         "var":  "",
                         "y":  283,
                         "w":  643,
                         "fmt":  "",
                         "name":  "",
                         "h":  49,
                         "color":  "195",
                         "text":  "Adresse",
                         "parent":  null
                     },
                     {
                         "x":  18,
                         "type":  "label",
                         "var":  "",
                         "y":  337,
                         "w":  82,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Langue",
                         "parent":  4
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  357,
                         "w":  725,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "1",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  614,
                         "type":  "label",
                         "var":  "",
                         "y":  31,
                         "w":  57,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "7",
                         "text":  "Bébé",
                         "parent":  4
                     },
                     {
                         "x":  21,
                         "type":  "label",
                         "var":  "",
                         "y":  130,
                         "w":  91,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "Cat.Emploi",
                         "parent":  4
                     },
                     {
                         "x":  21,
                         "type":  "label",
                         "var":  "",
                         "y":  145,
                         "w":  75,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "BSI Ok ?",
                         "parent":  4
                     },
                     {
                         "x":  21,
                         "type":  "label",
                         "var":  "",
                         "y":  160,
                         "w":  115,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "Lieu de séjour",
                         "parent":  4
                     },
                     {
                         "x":  360,
                         "type":  "label",
                         "var":  "",
                         "y":  179,
                         "w":  91,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Vol aller",
                         "parent":  4
                     },
                     {
                         "x":  360,
                         "type":  "label",
                         "var":  "",
                         "y":  194,
                         "w":  91,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Vol Retour",
                         "parent":  4
                     },
                     {
                         "x":  21,
                         "type":  "label",
                         "var":  "",
                         "y":  63,
                         "w":  109,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "Matricule WD",
                         "parent":  4
                     },
                     {
                         "x":  133,
                         "type":  "edit",
                         "var":  "",
                         "y":  31,
                         "w":  182,
                         "fmt":  "",
                         "name":  "GO Nom",
                         "h":  12,
                         "color":  "6",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  426,
                         "type":  "combobox",
                         "var":  "",
                         "y":  31,
                         "w":  182,
                         "fmt":  "",
                         "name":  "W1-Select titre",
                         "h":  12,
                         "color":  "",
                         "text":  "1,2",
                         "parent":  4
                     },
                     {
                         "x":  133,
                         "type":  "edit",
                         "var":  "",
                         "y":  47,
                         "w":  182,
                         "fmt":  "",
                         "name":  "GO Prenom",
                         "h":  12,
                         "color":  "6",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  614,
                         "type":  "button",
                         "var":  "",
                         "y":  47,
                         "w":  28,
                         "fmt":  "...",
                         "name":  "v. bouton qualite",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  426,
                         "type":  "edit",
                         "var":  "",
                         "y":  47,
                         "w":  182,
                         "fmt":  "15",
                         "name":  "W1-Select qualite",
                         "h":  12,
                         "color":  "6",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  133,
                         "type":  "edit",
                         "var":  "",
                         "y":  63,
                         "w":  532,
                         "fmt":  "",
                         "name":  "go_matricule_wd",
                         "h":  12,
                         "color":  "6",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  133,
                         "type":  "combobox",
                         "var":  "",
                         "y":  78,
                         "w":  403,
                         "fmt":  "",
                         "name":  "go_code_service",
                         "h":  12,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  134,
                         "type":  "edit",
                         "var":  "",
                         "y":  96,
                         "w":  286,
                         "fmt":  "",
                         "name":  "go_fonction",
                         "h":  12,
                         "color":  "6",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  426,
                         "type":  "button",
                         "var":  "",
                         "y":  96,
                         "w":  28,
                         "fmt":  "...",
                         "name":  "v.bouton fonction",
                         "h":  12,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  133,
                         "type":  "combobox",
                         "var":  "",
                         "y":  112,
                         "w":  206,
                         "fmt":  "",
                         "name":  "W1-Select Contrat",
                         "h":  12,
                         "color":  "",
                         "text":  "1,2",
                         "parent":  4
                     },
                     {
                         "x":  133,
                         "type":  "combobox",
                         "var":  "",
                         "y":  129,
                         "w":  403,
                         "fmt":  "",
                         "name":  "Go_cat_emploi",
                         "h":  12,
                         "color":  "6",
                         "text":  "1,2,3",
                         "parent":  4
                     },
                     {
                         "x":  133,
                         "type":  "checkbox",
                         "var":  "",
                         "y":  145,
                         "w":  34,
                         "fmt":  "",
                         "name":  "GO_bsi ok",
                         "h":  12,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  135,
                         "type":  "combobox",
                         "var":  "",
                         "y":  160,
                         "w":  280,
                         "fmt":  "",
                         "name":  "W1-Lieu de séjour",
                         "h":  12,
                         "color":  "",
                         "text":  "1,2",
                         "parent":  4
                     },
                     {
                         "x":  133,
                         "type":  "edit",
                         "var":  "",
                         "y":  179,
                         "w":  169,
                         "fmt":  "DD/MM/YYYYZ",
                         "name":  "GO Date Debut",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  309,
                         "type":  "button",
                         "var":  "",
                         "y":  179,
                         "w":  28,
                         "fmt":  "...",
                         "name":  "v.bouton date debut",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  452,
                         "type":  "edit",
                         "var":  "",
                         "y":  179,
                         "w":  74,
                         "fmt":  "",
                         "name":  "heb_nom_logement",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  533,
                         "type":  "edit",
                         "var":  "",
                         "y":  179,
                         "w":  37,
                         "fmt":  "",
                         "name":  "heb_heure_debut_0001",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  574,
                         "type":  "button",
                         "var":  "",
                         "y":  179,
                         "w":  28,
                         "fmt":  "...",
                         "name":  "v.bouton.V/VAller",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  133,
                         "type":  "edit",
                         "var":  "",
                         "y":  193,
                         "w":  169,
                         "fmt":  "DD/MM/YYYYZ",
                         "name":  "GO Date Fin",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  309,
                         "type":  "button",
                         "var":  "",
                         "y":  193,
                         "w":  28,
                         "fmt":  "...",
                         "name":  "v.bouton date fin",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  452,
                         "type":  "edit",
                         "var":  "",
                         "y":  194,
                         "w":  74,
                         "fmt":  "",
                         "name":  "heb_nom_logement_0001",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  533,
                         "type":  "edit",
                         "var":  "",
                         "y":  194,
                         "w":  37,
                         "fmt":  "",
                         "name":  "heb_heure_debut_0002",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  574,
                         "type":  "button",
                         "var":  "",
                         "y":  194,
                         "w":  28,
                         "fmt":  "...",
                         "name":  "v.bouton V/V Retour",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  174,
                         "type":  "edit",
                         "var":  "",
                         "y":  208,
                         "w":  126,
                         "fmt":  "DD/MM/YYYYT",
                         "name":  "GO Date Naissance",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  181,
                         "type":  "button",
                         "var":  "",
                         "y":  222,
                         "w":  28,
                         "fmt":  "...",
                         "name":  "v. bouton nationalite",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  133,
                         "type":  "edit",
                         "var":  "",
                         "y":  222,
                         "w":  37,
                         "fmt":  "",
                         "name":  "GO Nationalite",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  224,
                         "type":  "edit",
                         "var":  "",
                         "y":  222,
                         "w":  344,
                         "fmt":  "U20",
                         "name":  "",
                         "h":  10,
                         "color":  "7",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  182,
                         "type":  "combobox",
                         "var":  "",
                         "y":  237,
                         "w":  110,
                         "fmt":  "",
                         "name":  "W1-Base occupation",
                         "h":  12,
                         "color":  "",
                         "text":  "1,2",
                         "parent":  4
                     },
                     {
                         "x":  134,
                         "type":  "edit",
                         "var":  "",
                         "y":  254,
                         "w":  216,
                         "fmt":  "U18",
                         "name":  "GMC N° Pièce",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  133,
                         "type":  "edit",
                         "var":  "",
                         "y":  270,
                         "w":  216,
                         "fmt":  "U18",
                         "name":  "GMC Ville Delivrance",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  574,
                         "type":  "button",
                         "var":  "",
                         "y":  270,
                         "w":  26,
                         "fmt":  "...",
                         "name":  "v.bouton date delivrance",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  426,
                         "type":  "edit",
                         "var":  "",
                         "y":  270,
                         "w":  144,
                         "fmt":  "DD/MM/YYYYT",
                         "name":  "GMC Date Delivrance",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  133,
                         "type":  "edit",
                         "var":  "",
                         "y":  293,
                         "w":  126,
                         "fmt":  "",
                         "name":  "GMC N° dans la rue",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  39
                     },
                     {
                         "x":  267,
                         "type":  "edit",
                         "var":  "",
                         "y":  293,
                         "w":  356,
                         "fmt":  "",
                         "name":  "GMC Nom de la rue",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  39
                     },
                     {
                         "x":  133,
                         "type":  "edit",
                         "var":  "",
                         "y":  305,
                         "w":  488,
                         "fmt":  "",
                         "name":  "GMC Commune",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  39
                     },
                     {
                         "x":  133,
                         "type":  "edit",
                         "var":  "",
                         "y":  317,
                         "w":  126,
                         "fmt":  "",
                         "name":  "GMC Code Postal",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  39
                     },
                     {
                         "x":  267,
                         "type":  "edit",
                         "var":  "",
                         "y":  317,
                         "w":  356,
                         "fmt":  "",
                         "name":  "GMC Ville",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  39
                     },
                     {
                         "x":  180,
                         "type":  "button",
                         "var":  "",
                         "y":  337,
                         "w":  28,
                         "fmt":  "...",
                         "name":  "v. bouton langue",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  133,
                         "type":  "edit",
                         "var":  "",
                         "y":  337,
                         "w":  37,
                         "fmt":  "",
                         "name":  "GMR Langue Parlee",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  218,
                         "type":  "edit",
                         "var":  "",
                         "y":  337,
                         "w":  232,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "7",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  398,
                         "type":  "edit",
                         "var":  "",
                         "y":  208,
                         "w":  30,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  9,
                         "type":  "button",
                         "var":  "",
                         "y":  362,
                         "w":  154,
                         "fmt":  "\u0026Ok",
                         "name":  "v. bouton quitter",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  9,
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
                         "x":  444,
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
                         "x":  133,
                         "type":  "edit",
                         "var":  "",
                         "y":  237,
                         "w":  19,
                         "fmt":  "1",
                         "name":  "",
                         "h":  12,
                         "color":  "7",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  187,
                         "type":  "button",
                         "var":  "",
                         "y":  362,
                         "w":  154,
                         "fmt":  "A\u0026bandonner",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  133,
                         "type":  "edit",
                         "var":  "",
                         "y":  78,
                         "w":  532,
                         "fmt":  "",
                         "name":  "goj_job_family",
                         "h":  12,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  134,
                         "type":  "edit",
                         "var":  "",
                         "y":  96,
                         "w":  532,
                         "fmt":  "",
                         "name":  "goj_job_title",
                         "h":  12,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  675,
                         "type":  "button",
                         "var":  "",
                         "y":  88,
                         "w":  28,
                         "fmt":  "...",
                         "name":  "v. btn fx",
                         "h":  12,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     }
                 ],
    "taskId":  "194.2",
    "height":  383
}
-->

<details>
<summary><strong>Champs : 37 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 133,31 | GO Nom | - | edit |
| 426,31 | W1-Select titre | - | combobox |
| 133,47 | GO Prenom | - | edit |
| 426,47 | W1-Select qualite | - | edit |
| 133,63 | go_matricule_wd | - | edit |
| 133,78 | go_code_service | - | combobox |
| 134,96 | go_fonction | - | edit |
| 133,112 | W1-Select Contrat | - | combobox |
| 133,129 | Go_cat_emploi | - | combobox |
| 133,145 | GO_bsi ok | - | checkbox |
| 135,160 | W1-Lieu de séjour | - | combobox |
| 133,179 | GO Date Debut | - | edit |
| 452,179 | heb_nom_logement | - | edit |
| 533,179 | heb_heure_debut_0001 | - | edit |
| 133,193 | GO Date Fin | - | edit |
| 452,194 | heb_nom_logement_0001 | - | edit |
| 533,194 | heb_heure_debut_0002 | - | edit |
| 174,208 | GO Date Naissance | - | edit |
| 133,222 | GO Nationalite | - | edit |
| 224,222 | U20 | - | edit |
| 182,237 | W1-Base occupation | - | combobox |
| 134,254 | GMC N° Pièce | - | edit |
| 133,270 | GMC Ville Delivrance | - | edit |
| 426,270 | GMC Date Delivrance | - | edit |
| 133,293 | GMC N° dans la rue | - | edit |
| 267,293 | GMC Nom de la rue | - | edit |
| 133,305 | GMC Commune | - | edit |
| 133,317 | GMC Code Postal | - | edit |
| 267,317 | GMC Ville | - | edit |
| 133,337 | GMR Langue Parlee | - | edit |
| 218,337 | (sans nom) | - | edit |
| 398,208 | (sans nom) | - | edit |
| 9,6 | 30 | - | edit |
| 444,6 | WWW DD MMM YYYYT | - | edit |
| 133,237 | 1 | - | edit |
| 133,78 | goj_job_family | - | edit |
| 134,96 | goj_job_title | - | edit |

</details>

<details>
<summary><strong>Boutons : 12 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| ... | 614,47 | Bouton fonctionnel |
| ... | 426,96 | Bouton fonctionnel |
| ... | 309,179 | Bouton fonctionnel |
| ... | 574,179 | Bouton fonctionnel |
| ... | 309,193 | Bouton fonctionnel |
| ... | 574,194 | Bouton fonctionnel |
| ... | 181,222 | Bouton fonctionnel |
| ... | 574,270 | Bouton fonctionnel |
| ... | 180,337 | Bouton fonctionnel |
| Ok | 9,362 | Valide la saisie et enregistre |
| Abandonner | 187,362 | Annule et retour au menu |
| ... | 675,88 | Bouton fonctionnel |

</details>

---

#### <a id="ecran-t9"></a>194.2.4.2 - Selection Fonction
**Tache** : [194.2.3.2](#t9) | **Type** : MDI | **Dimensions** : 392 x 167 DLU
**Bloc** : Consultation | **Titre IDE** : Selection Fonction

<!-- FORM-DATA:
{
    "width":  392,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  34,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "196",
                         "w":  336,
                         "y":  7,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  12,
                         "h":  104,
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
                         "x":  40,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
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
    "taskId":  "194.2.4.2",
    "height":  167
}
-->

<details>
<summary><strong>Champs : 1 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 40,23 | U25 | - | edit |

</details>

<details>
<summary><strong>Boutons : 2 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Sélectionner | 29,143 | Bouton fonctionnel |
| Quitter | 209,143 | Quitte le programme |

</details>

---

#### <a id="ecran-t39"></a>194.2.1 - Selection Fonction
**Tache** : [194.2.5](#t39) | **Type** : MDI | **Dimensions** : 758 x 183 DLU
**Bloc** : Consultation | **Titre IDE** : Selection Fonction

<!-- FORM-DATA:
{
    "width":  758,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  16,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "196",
                         "w":  360,
                         "y":  5,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  12,
                         "h":  112,
                         "cols":  [
                                      {
                                          "title":  "Service",
                                          "layer":  1,
                                          "w":  324
                                      }
                                  ],
                         "rows":  1
                     },
                     {
                         "x":  2,
                         "type":  "label",
                         "var":  "",
                         "y":  158,
                         "w":  753,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  22,
                         "type":  "edit",
                         "var":  "",
                         "y":  20,
                         "w":  288,
                         "fmt":  "100",
                         "name":  "v. goj_job_family",
                         "h":  8,
                         "color":  "196",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  14,
                         "type":  "button",
                         "var":  "",
                         "y":  161,
                         "w":  154,
                         "fmt":  "\u0026Sélectionner",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  591,
                         "type":  "button",
                         "var":  "",
                         "y":  161,
                         "w":  154,
                         "fmt":  "\u0026Quitter",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  350,
                         "type":  "image",
                         "var":  "",
                         "y":  131,
                         "w":  58,
                         "fmt":  "",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  384,
                         "type":  "subform",
                         "var":  "",
                         "y":  5,
                         "w":  360,
                         "fmt":  "",
                         "name":  "st1",
                         "h":  120,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "194.2.1",
    "height":  183
}
-->

<details>
<summary><strong>Champs : 1 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 22,20 | v. goj_job_family | - | edit |

</details>

<details>
<summary><strong>Boutons : 2 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Sélectionner | 14,161 | Bouton fonctionnel |
| Quitter | 591,161 | Quitte le programme |

</details>

---

#### <a id="ecran-t40"></a>194.2.1.1 - (sans nom)
**Tache** : [194.2.5.1](#t40) | **Type** : Type0 | **Dimensions** : 180 x 120 DLU
**Bloc** : Traitement | **Titre IDE** : (sans nom)

<!-- FORM-DATA:
{
    "width":  180,
    "vFactor":  8,
    "type":  "Type0",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "196",
                         "w":  180,
                         "y":  0,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  13,
                         "h":  112,
                         "cols":  [
                                      {
                                          "title":  "Fonction",
                                          "layer":  1,
                                          "w":  162
                                      }
                                  ],
                         "rows":  1
                     },
                     {
                         "x":  4,
                         "type":  "edit",
                         "var":  "",
                         "y":  15,
                         "w":  160,
                         "fmt":  "",
                         "name":  "goj_job_title",
                         "h":  10,
                         "color":  "196",
                         "text":  "",
                         "parent":  2
                     }
                 ],
    "taskId":  "194.2.1.1",
    "height":  120
}
-->

<details>
<summary><strong>Champs : 1 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 4,15 | goj_job_title | - | edit |

</details>

## 9. NAVIGATION

### 9.1 Enchainement des ecrans

```mermaid
flowchart TD
    START([Entree])
    style START fill:#3fb950
    VF4[194.2 Creation personnel]
    style VF4 fill:#58a6ff
    VF9[194.2.3.2 Selection Fonction]
    style VF9 fill:#58a6ff
    VF39[194.2.5 Selection Fonction]
    style VF39 fill:#58a6ff
    VF40[194.2.5.1 sans nom]
    style VF40 fill:#58a6ff
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
    EXT312[IDE 312 Determination ...]
    style EXT312 fill:#3fb950
    EXT317[IDE 317 Recuperation d...]
    style EXT317 fill:#3fb950
    EXT351[IDE 351 Vérification c...]
    style EXT351 fill:#3fb950
    FIN([Sortie])
    style FIN fill:#f85149
    START --> VF4
    VF4 -->|Selection/consultation| EXT356
    VF4 -->|Controle/validation| EXT320
    VF4 -->|Sous-programme| EXT336
    VF4 -->|Sous-programme| EXT337
    VF4 -->|Selection/consultation| EXT355
    VF4 -->|Selection/consultation| EXT366
    VF4 -->|Selection/consultation| EXT370
    VF4 -->|Historique/consultation| EXT181
    EXT351 --> FIN
```

**Detail par enchainement :**

| Depuis | Action | Vers | Retour |
|--------|--------|------|--------|
| Creation personnel | Selection/consultation | [Zoom nationalite (IDE 356)](PBG-IDE-356.md) | Retour ecran |
| Creation personnel | Controle/validation | [Verification Aut sans ecran (IDE 320)](PBG-IDE-320.md) | Retour ecran |
| Creation personnel | Sous-programme | [Création Village/Village (IDE 336)](PBG-IDE-336.md) | Retour ecran |
| Creation personnel | Sous-programme | [Recherche Existance Groupe A/D (IDE 337)](PBG-IDE-337.md) | Retour ecran |
| Creation personnel | Selection/consultation | [Zoom langue (IDE 355)](PBG-IDE-355.md) | Retour ecran |
| Creation personnel | Selection/consultation | [Zoom Qualite(C/P) (IDE 366)](PBG-IDE-366.md) | Retour ecran |
| Creation personnel | Selection/consultation | [Zoom Village/Village (IDE 370)](PBG-IDE-370.md) | Retour ecran |
| Creation personnel | Historique/consultation | [Creation Historique (IDE 181)](PBG-IDE-181.md) | Retour ecran |
| Creation personnel | Sous-programme | [Determination Age Debut Sejour (IDE 312)](PBG-IDE-312.md) | Retour ecran |
| Creation personnel | Recuperation donnees | [Recuperation du titre (IDE 317)](PBG-IDE-317.md) | Retour ecran |
| Creation personnel | Sous-programme | [Vérification compteur compte (IDE 351)](PBG-IDE-351.md) | Retour ecran |

### 9.3 Structure hierarchique (17 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **194.1** | [**Module des Identites** (194)](#t1) | MDI | - | Traitement |
| 194.1.1 | [Determination Age Bebe (194.1)](#t2) | MDI | - | |
| 194.1.2 | [Langue ? (194.2.1)](#t5) | MDI | - | |
| 194.1.3 | [Lecture Qualite&Occupation (194.2.2)](#t6) | MDI | - | |
| 194.1.4 | [Determination Fonction (194.2.3)](#t7) [mockup](#ecran-t7) | MDI | 108x8 | |
| 194.1.5 | [Determination Service (194.2.3.1)](#t8) | MDI | - | |
| 194.1.6 | [Veuillez patienter... (194.2.4)](#t10) [mockup](#ecran-t10) | MDI | 422x56 | |
| 194.1.7 | [(sans nom) (194.2.5.1)](#t40) [mockup](#ecran-t40) | - | 180x120 | |
| **194.2** | [**Creation personnel** (194.2)](#t4) [mockup](#ecran-t4) | MDI | 734x383 | Creation |
| 194.2.1 | [Creation Package Aller (194.2.4.2)](#t12) | MDI | - | |
| 194.2.2 | [Creation Package Retour (194.2.4.3)](#t13) | MDI | - | |
| **194.3** | [**Selection Fonction** (194.2.3.2)](#t9) [mockup](#ecran-t9) | MDI | 392x167 | Consultation |
| 194.3.1 | [Selection Fonction (194.2.5)](#t39) [mockup](#ecran-t39) | MDI | 758x183 | |
| **194.4** | [**Verification Planning** (194.2.4.1)](#t11) | MDI | - | Validation |
| 194.4.1 | [Creation Validation (194.2.4.5)](#t15) | MDI | - | |
| **194.5** | [**Creation Compte** (194.2.4.4)](#t14) | MDI | - | Calcul |
| 194.5.1 | [Attribution Compte (194.3)](#t16) | MDI | - | |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Affichage Personnel Nom]
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

### Tables utilisees (14)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 30 | gm-recherche_____gmr | Index de recherche | DB |   | **W** |   | 1 |
| 31 | gm-complet_______gmc |  | DB |   |   | L | 1 |
| 34 | hebergement______heb | Hebergement (chambres) | DB | R | **W** | L | 4 |
| 35 | personnel_go______go |  | DB |   |   | L | 1 |
| 47 | compte_gm________cgm | Comptes GM (generaux) | DB |   | **W** |   | 1 |
| 63 | parametres___par |  | DB | R |   |   | 2 |
| 68 | compteurs________cpt | Comptes GM (generaux) | DB |   | **W** |   | 1 |
| 78 | param__telephone_tel |  | DB |   |   | L | 1 |
| 113 | tables_village |  | DB | R |   |   | 2 |
| 117 | tables_services | Services / filieres | DB | R |   | L | 3 |
| 119 | tables_pays_tel_ |  | DB |   |   | L | 1 |
| 130 | fichier_langue |  | DB |   |   | L | 1 |
| 131 | fichier_validation |  | DB |   | **W** |   | 1 |
| 1092 | Table_1092 |  | MEM |   | **W** | L | 2 |

### Colonnes par table (4 / 9 tables avec colonnes identifiees)

<details>
<summary>Table 30 - gm-recherche_____gmr (**W**) - 1 usages</summary>

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
| J | v. btn fx | W | Alpha |
| K | W1-Select titre | W | Alpha |
| L | v.bouton fonction | W | Alpha |
| M | W1-Select Contrat | W | Alpha |
| N | W1-Lieu de séjour | W | Alpha |
| O | v.bouton date debut | W | Alpha |
| P | v.bouton date fin | W | Alpha |
| Q | v. bouton nationalite | W | Alpha |
| R | W1-Base occupation | W | Alpha |
| S | v.bouton date delivrance | W | Alpha |
| T | v. bouton langue | W | Alpha |
| U | v.bouton.V/VAller | W | Alpha |
| V | v.bouton V/V Retour | W | Alpha |
| W | v. bouton quitter | W | Alpha |
| X | v.Retour Question Bsi | W | Numeric |
| Y | v Existe Code VV Aller | W | Logical |
| Z | v Code VV Aller | W | Alpha |
| BA | v Heure VV Aller | W | Alpha |
| BB | v Existe Code VV Retour | W | Logical |
| BC | v Code VV Retour | W | Alpha |
| BD | v Heure VV Retour | W | Alpha |
| BE | v Suite Creation | W | Alpha |
| BF | v Bt | W | Alpha |
| BG | CHG_REASON_go_bsi_ok | W | Numeric |
| BH | CHG_PRV_go_bsi_ok | W | Logical |

</details>

<details>
<summary>Table 34 - hebergement______heb (R/**W**/L) - 4 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 47 - compte_gm________cgm (**W**) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| F | W0-numero compte memo | W | Numeric |
| G | W1- Numero compte memo | W | Numeric |
| P | W0-Compte | W | Numeric |

</details>

<details>
<summary>Table 63 - parametres___par (R) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 68 - compteurs________cpt (**W**) - 1 usages</summary>

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
<summary>Table 1092 - Table_1092 (**W**/L) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | W1-Table Service | W | Alpha |
| N | W0-Table service | W | Alpha |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (1)

Variables recues du programme appelant ([Sejours personnel SubForm (IDE 0)](PBG-IDE-0.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| B | P0 Front/Back | Alpha | 2x parametre entrant |

### 11.2 Variables de session (15)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| E | v.ecran titre | Alpha | - |
| S | v.bouton date delivrance | Alpha | - |
| T | v. bouton langue | Alpha | - |
| U | v.bouton.V/VAller | Alpha | - |
| V | v.bouton V/V Retour | Alpha | - |
| W | v. bouton quitter | Alpha | - |
| X | v.Retour Question Bsi | Numeric | - |
| Y | v Existe Code VV Aller | Logical | - |
| Z | v Code VV Aller | Alpha | - |
| BA | v Heure VV Aller | Alpha | - |
| BB | v Existe Code VV Retour | Logical | - |
| BC | v Code VV Retour | Alpha | - |
| BD | v Heure VV Retour | Alpha | - |
| BE | v Suite Creation | Alpha | - |
| BF | v Bt | Alpha | - |

### 11.3 Autres (18)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | > Mode attaque ecran | Alpha | 1x refs |
| C | W0-Age Bebe | Numeric | - |
| D | W0-Base Vide | Alpha | - |
| F | W0-numero compte memo | Numeric | - |
| G | W0-autorisation creation | Alpha | - |
| H | W0-autorisation modif | Alpha | - |
| I | W0-autorisation | Alpha | - |
| J | W0-code base occup | Alpha | - |
| K | W0-heberg | Alpha | - |
| L | W0-Saisie langue ? | Alpha | - |
| M | W0-Bloquage effectue | Alpha | - |
| N | W0-Table service | Alpha | - |
| O | W0-Code fonction | Alpha | - |
| P | W0-Compte | Numeric | - |
| Q | W0-Adhesion | Numeric | - |
| R | W1-Base occupation | Alpha | - |
| BG | CHG_REASON_go_bsi_ok | Numeric | - |
| BH | CHG_PRV_go_bsi_ok | Logical | - |

<details>
<summary>Toutes les 34 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| P0 | **B** | P0 Front/Back | Alpha |
| V. | **E** | v.ecran titre | Alpha |
| V. | **S** | v.bouton date delivrance | Alpha |
| V. | **T** | v. bouton langue | Alpha |
| V. | **U** | v.bouton.V/VAller | Alpha |
| V. | **V** | v.bouton V/V Retour | Alpha |
| V. | **W** | v. bouton quitter | Alpha |
| V. | **X** | v.Retour Question Bsi | Numeric |
| V. | **Y** | v Existe Code VV Aller | Logical |
| V. | **Z** | v Code VV Aller | Alpha |
| V. | **BA** | v Heure VV Aller | Alpha |
| V. | **BB** | v Existe Code VV Retour | Logical |
| V. | **BC** | v Code VV Retour | Alpha |
| V. | **BD** | v Heure VV Retour | Alpha |
| V. | **BE** | v Suite Creation | Alpha |
| V. | **BF** | v Bt | Alpha |
| Autre | **A** | > Mode attaque ecran | Alpha |
| Autre | **C** | W0-Age Bebe | Numeric |
| Autre | **D** | W0-Base Vide | Alpha |
| Autre | **F** | W0-numero compte memo | Numeric |
| Autre | **G** | W0-autorisation creation | Alpha |
| Autre | **H** | W0-autorisation modif | Alpha |
| Autre | **I** | W0-autorisation | Alpha |
| Autre | **J** | W0-code base occup | Alpha |
| Autre | **K** | W0-heberg | Alpha |
| Autre | **L** | W0-Saisie langue ? | Alpha |
| Autre | **M** | W0-Bloquage effectue | Alpha |
| Autre | **N** | W0-Table service | Alpha |
| Autre | **O** | W0-Code fonction | Alpha |
| Autre | **P** | W0-Compte | Numeric |
| Autre | **Q** | W0-Adhesion | Numeric |
| Autre | **R** | W1-Base occupation | Alpha |
| Autre | **BG** | CHG_REASON_go_bsi_ok | Numeric |
| Autre | **BH** | CHG_PRV_go_bsi_ok | Logical |

</details>

## 12. EXPRESSIONS

**12 / 12 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONDITION | 3 | 5 |
| CONSTANTE | 7 | 0 |
| OTHER | 2 | 0 |

### 12.2 Expressions cles par type

#### CONDITION (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 3 | `IF (Trim (> Mode attaque ecran [A])='','E'MODE,> Mode attaque ecran [A])` | [RM-001](#rm-RM-001) |
| CONDITION | 10 | `P0 Front/Back [B]='B'` | - |
| CONDITION | 9 | `P0 Front/Back [B]='F'` | - |

#### CONSTANTE (7 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 8 | `'10'` | - |
| CONSTANTE | 11 | `'O'` | - |
| CONSTANTE | 12 | `'CCREA'` | - |
| CONSTANTE | 7 | `'09'` | - |
| CONSTANTE | 1 | `'N'` | - |
| ... | | *+2 autres* | |

#### OTHER (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 6 | `GetParam ('SOCIETE')` | - |
| OTHER | 5 | `GetParam ('FRONT')` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Sejours personnel SubForm (IDE 0)](PBG-IDE-0.md) -> **Creation personnel identites (IDE 194)**

Main -> ... -> [Personnel Identites (IDE 195)](PBG-IDE-195.md) -> **Creation personnel identites (IDE 194)**

Main -> ... -> [Sejours personnel CallTask (IDE 196)](PBG-IDE-196.md) -> **Creation personnel identites (IDE 194)**

Main -> ... -> [Module personnel identites (IDE 373)](PBG-IDE-373.md) -> **Creation personnel identites (IDE 194)**

```mermaid
graph LR
    T194[194 Creation personnel...]
    style T194 fill:#58a6ff
    CC373[373 Module personnel i...]
    style CC373 fill:#8b5cf6
    CC196[196 Sejours personnel ...]
    style CC196 fill:#8b5cf6
    CC195[195 Personnel Identites]
    style CC195 fill:#8b5cf6
    CC195 --> T194
    CC196 --> T194
    CC373 --> T194
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [0](PBG-IDE-0.md) | Sejours personnel SubForm | 1 |
| [195](PBG-IDE-195.md) | Personnel Identites | 1 |
| [196](PBG-IDE-196.md) | Sejours personnel CallTask | 1 |
| [373](PBG-IDE-373.md) | Module personnel identites | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T194[194 Creation personnel...]
    style T194 fill:#58a6ff
    C356[356 Zoom nationalite]
    T194 --> C356
    style C356 fill:#3fb950
    C320[320 Verification Aut s...]
    T194 --> C320
    style C320 fill:#3fb950
    C336[336 Création VillageVi...]
    T194 --> C336
    style C336 fill:#3fb950
    C337[337 Recherche Existanc...]
    T194 --> C337
    style C337 fill:#3fb950
    C355[355 Zoom langue]
    T194 --> C355
    style C355 fill:#3fb950
    C366[366 Zoom QualiteCP]
    T194 --> C366
    style C366 fill:#3fb950
    C370[370 Zoom VillageVillage]
    T194 --> C370
    style C370 fill:#3fb950
    C181[181 Creation Historique]
    T194 --> C181
    style C181 fill:#3fb950
    C312[312 Determination Age ...]
    T194 --> C312
    style C312 fill:#3fb950
    C317[317 Recuperation du titre]
    T194 --> C317
    style C317 fill:#3fb950
    C351[351 Vérification compt...]
    T194 --> C351
    style C351 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [356](PBG-IDE-356.md) | Zoom nationalite | 3 | Selection/consultation |
| [320](PBG-IDE-320.md) | Verification Aut sans ecran | 2 | Controle/validation |
| [336](PBG-IDE-336.md) | Création Village/Village | 2 | Sous-programme |
| [337](PBG-IDE-337.md) | Recherche Existance Groupe A/D | 2 | Sous-programme |
| [355](PBG-IDE-355.md) | Zoom langue | 2 | Selection/consultation |
| [366](PBG-IDE-366.md) | Zoom Qualite(C/P) | 2 | Selection/consultation |
| [370](PBG-IDE-370.md) | Zoom Village/Village | 2 | Selection/consultation |
| [181](PBG-IDE-181.md) | Creation Historique | 1 | Historique/consultation |
| [312](PBG-IDE-312.md) | Determination Age Debut Sejour | 1 | Sous-programme |
| [317](PBG-IDE-317.md) | Recuperation du titre | 1 | Recuperation donnees |
| [351](PBG-IDE-351.md) | Vérification compteur compte | 1 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 600 | Programme volumineux |
| Expressions | 12 | Peu de logique |
| Tables WRITE | 6 | Fort impact donnees |
| Sous-programmes | 11 | Forte dependance |
| Ecrans visibles | 4 | Quelques ecrans |
| Code desactive | 0.5% (3 / 600) | Code sain |
| Regles metier | 1 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (8 taches: 3 ecrans, 5 traitements)

- **Strategie** : Orchestrateur avec 3 ecrans (Razor/React) et 5 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 11 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Creation (3 taches: 1 ecran, 2 traitements)

- **Strategie** : Repository pattern avec Entity Framework Core.
- Insertion via `IRepository<T>.CreateAsync()`

#### Consultation (2 taches: 2 ecrans, 0 traitement)

- **Strategie** : Composants de recherche/selection en modales.
- 2 ecrans : Selection Fonction, Selection Fonction

#### Validation (2 taches: 0 ecran, 2 traitements)

- **Strategie** : FluentValidation avec validators specifiques.
- Chaque tache de validation -> un validator injectable

#### Calcul (2 taches: 0 ecran, 2 traitements)

- **Strategie** : Services de calcul purs (Domain Services).
- Migrer la logique de calcul (stock, compteurs, montants)

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| gm-recherche_____gmr | Table WRITE (Database) | 1x | Schema + repository |
| hebergement______heb | Table WRITE (Database) | 2x | Schema + repository |
| compte_gm________cgm | Table WRITE (Database) | 1x | Schema + repository |
| compteurs________cpt | Table WRITE (Database) | 1x | Schema + repository |
| fichier_validation | Table WRITE (Database) | 1x | Schema + repository |
| Table_1092 | Table WRITE (Memory) | 1x | Schema + repository |
| [Zoom nationalite (IDE 356)](PBG-IDE-356.md) | Sous-programme | 3x | **CRITIQUE** - Selection/consultation |
| [Zoom langue (IDE 355)](PBG-IDE-355.md) | Sous-programme | 2x | Haute - Selection/consultation |
| [Zoom Qualite(C/P) (IDE 366)](PBG-IDE-366.md) | Sous-programme | 2x | Haute - Selection/consultation |
| [Zoom Village/Village (IDE 370)](PBG-IDE-370.md) | Sous-programme | 2x | Haute - Selection/consultation |
| [Verification Aut sans ecran (IDE 320)](PBG-IDE-320.md) | Sous-programme | 2x | Haute - Controle/validation |
| [Création Village/Village (IDE 336)](PBG-IDE-336.md) | Sous-programme | 2x | Haute - Sous-programme |
| [Recherche Existance Groupe A/D (IDE 337)](PBG-IDE-337.md) | Sous-programme | 2x | Haute - Sous-programme |
| [Recuperation du titre (IDE 317)](PBG-IDE-317.md) | Sous-programme | 1x | Normale - Recuperation donnees |
| [Vérification compteur compte (IDE 351)](PBG-IDE-351.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Creation Historique (IDE 181)](PBG-IDE-181.md) | Sous-programme | 1x | Normale - Historique/consultation |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 10:06*
