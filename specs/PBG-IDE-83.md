# PBG IDE 83 - Prolongation Client

> **Analyse**: Phases 1-4 2026-02-03 09:14 -> 09:14 (19s) | Assemblage 09:14
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBG |
| IDE Position | 83 |
| Nom Programme | Prolongation Client |
| Fichier source | `Prg_83.xml` |
| Domaine metier | General |
| Taches | 20 (1 ecrans visibles) |
| Tables modifiees | 7 |
| Programmes appeles | 7 |

## 2. DESCRIPTION FONCTIONNELLE

**Prolongation Client** assure la gestion complete de ce processus, accessible depuis [Module Sejours CallTask (IDE 0)](PBG-IDE-0.md), [Module Sejours CallTask (IDE 94)](PBG-IDE-94.md), [Module Sejours SubForm (IDE 391)](PBG-IDE-391.md).

Le flux de traitement s'organise en **6 blocs fonctionnels** :

- **Traitement** (10 taches) : traitements metier divers
- **Creation** (3 taches) : insertion d'enregistrements en base (mouvements, prestations)
- **Validation** (3 taches) : controles et verifications de coherence
- **Consultation** (2 taches) : ecrans de recherche, selection et consultation
- **Calcul** (1 tache) : calculs de montants, stocks ou compteurs
- **Saisie** (1 tache) : ecrans de saisie utilisateur (formulaires, champs, donnees)

**Donnees modifiees** : 7 tables en ecriture (gm-recherche_____gmr, hebergement______heb, client_gm, compte_gm________cgm, historik_station, fichier_validation, groupe_arr_dep___vol).

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (10 taches)

- **83** - Prolongation Client **[[ECRAN]](#ecran-t1)**
- **83.1.1** - Determination Periode
- **83.2** - Recuperation Periode Debut
- **83.6** - Confirmation Prolongation **[[ECRAN]](#ecran-t10)**
- **83.7** - Prolongation Batch **[[ECRAN]](#ecran-t11)**
- **83.7.2** - Modification Package
- **83.7.3** - Modification Heure Fin circuit
- **83.7.4** - Modification Package
- **83.7.5** - Modification Sejour
- **83.7.6** - Modification Sejour

Delegue a : [Demarquage Caisse (IDE 176)](PBG-IDE-176.md)

#### Phase 2 : Consultation (2 taches)

- **83.1** - Selection Qualite
- **83.5** - Selection Logement

Delegue a : [Zoom Selection Occupation (IDE 360)](PBG-IDE-360.md), [Zoom Selection Code-Vol (IDE 363)](PBG-IDE-363.md), [Zoom Affichage Code Logement (IDE 361)](PBG-IDE-361.md), [Zoom Affichage Lieu de Sejour (IDE 362)](PBG-IDE-362.md), [Zoom Qualite (IDE 365)](PBG-IDE-365.md)

#### Phase 3 : Saisie (1 tache)

- **83.3** - Saisie Date Fin **[[ECRAN]](#ecran-t5)**

#### Phase 4 : Creation (3 taches)

- **83.4** - Creation groupe V/V Aller/Reto
- **83.7.1** - Creation Hebergement
- **83.7.9** - Creation Historique

#### Phase 5 : Validation (3 taches)

- **83.5.1** - Verification Lieu de Sejour
- **83.5.2** - Verification Logement
- **83.7.8** - Modification Validation

#### Phase 6 : Calcul (1 tache)

- **83.7.7** - Modification Compte

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| hebergement______heb | R/**W** (6 usages) | Hebergement (chambres) |
| client_gm | R/**W** (2 usages) |  |
| historik_station | **W** (1 usages) | Historique / journal |
| fichier_validation | **W** (1 usages) |  |
| compte_gm________cgm | **W** (1 usages) | Comptes GM (generaux) |
| groupe_arr_dep___vol | **W** (1 usages) |  |
| gm-recherche_____gmr | **W** (1 usages) | Index de recherche |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (10 taches)

Traitements internes.

---

#### <a id="t1"></a>83 - Prolongation Client [[ECRAN]](#ecran-t1)

**Role** : Tache d'orchestration : point d'entree du programme (10 sous-taches). Coordonne l'enchainement des traitements.
**Ecran** : 132 x 56 DLU (MDI) | [Voir mockup](#ecran-t1)

<details>
<summary>9 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [83.1.1](#t3) | Determination Periode | Traitement |
| [83.2](#t4) | Recuperation Periode Debut | Traitement |
| [83.6](#t10) | Confirmation Prolongation **[[ECRAN]](#ecran-t10)** | Traitement |
| [83.7](#t11) | Prolongation Batch **[[ECRAN]](#ecran-t11)** | Traitement |
| [83.7.2](#t13) | Modification Package | Traitement |
| [83.7.3](#t14) | Modification Heure Fin circuit | Traitement |
| [83.7.4](#t15) | Modification Package | Traitement |
| [83.7.5](#t16) | Modification Sejour | Traitement |
| [83.7.6](#t17) | Modification Sejour | Traitement |

</details>
**Delegue a** : [Demarquage Caisse (IDE 176)](PBG-IDE-176.md)

---

#### <a id="t3"></a>83.1.1 - Determination Periode

**Role** : Traitement : Determination Periode.
**Delegue a** : [Demarquage Caisse (IDE 176)](PBG-IDE-176.md)

---

#### <a id="t4"></a>83.2 - Recuperation Periode Debut

**Role** : Consultation/chargement : Recuperation Periode Debut.
**Variables liees** : N (W0-Date Debut), O (W0-Heure Debut)
**Delegue a** : [Demarquage Caisse (IDE 176)](PBG-IDE-176.md)

---

#### <a id="t10"></a>83.6 - Confirmation Prolongation [[ECRAN]](#ecran-t10)

**Role** : Traitement : Confirmation Prolongation.
**Ecran** : 240 x 115 DLU (MDI) | [Voir mockup](#ecran-t10)
**Delegue a** : [Demarquage Caisse (IDE 176)](PBG-IDE-176.md)

---

#### <a id="t11"></a>83.7 - Prolongation Batch [[ECRAN]](#ecran-t11)

**Role** : Traitement : Prolongation Batch.
**Ecran** : 132 x 32 DLU (Modal) | [Voir mockup](#ecran-t11)
**Delegue a** : [Demarquage Caisse (IDE 176)](PBG-IDE-176.md)

---

#### <a id="t13"></a>83.7.2 - Modification Package

**Role** : Traitement : Modification Package.
**Delegue a** : [Demarquage Caisse (IDE 176)](PBG-IDE-176.md)

---

#### <a id="t14"></a>83.7.3 - Modification Heure Fin circuit

**Role** : Traitement : Modification Heure Fin circuit.
**Variables liees** : B (P.I Heure libération), O (W0-Heure Debut), Q (W0-Heure Fin)
**Delegue a** : [Demarquage Caisse (IDE 176)](PBG-IDE-176.md)

---

#### <a id="t15"></a>83.7.4 - Modification Package

**Role** : Traitement : Modification Package.
**Delegue a** : [Demarquage Caisse (IDE 176)](PBG-IDE-176.md)

---

#### <a id="t16"></a>83.7.5 - Modification Sejour

**Role** : Traitement : Modification Sejour.
**Variables liees** : Z (W0-Lieu de Sejour)
**Delegue a** : [Demarquage Caisse (IDE 176)](PBG-IDE-176.md)

---

#### <a id="t17"></a>83.7.6 - Modification Sejour

**Role** : Traitement : Modification Sejour.
**Variables liees** : Z (W0-Lieu de Sejour)
**Delegue a** : [Demarquage Caisse (IDE 176)](PBG-IDE-176.md)


### 3.2 Consultation (2 taches)

Ecrans de recherche et consultation.

---

#### <a id="t2"></a>83.1 - Selection Qualite

**Role** : Selection par l'operateur : Selection Qualite.
**Variables liees** : L (W0-Qualite)
**Delegue a** : [Zoom Selection Occupation (IDE 360)](PBG-IDE-360.md), [Zoom Selection Code-Vol (IDE 363)](PBG-IDE-363.md), [Zoom Affichage Code Logement (IDE 361)](PBG-IDE-361.md)

---

#### <a id="t7"></a>83.5 - Selection Logement

**Role** : Selection par l'operateur : Selection Logement.
**Variables liees** : BA (W0-Code Logement)
**Delegue a** : [Zoom Selection Occupation (IDE 360)](PBG-IDE-360.md), [Zoom Selection Code-Vol (IDE 363)](PBG-IDE-363.md), [Zoom Affichage Code Logement (IDE 361)](PBG-IDE-361.md)


### 3.3 Saisie (1 tache)

L'operateur saisit les donnees de la transaction via 1 ecran (Saisie Date Fin).

---

#### <a id="t5"></a>83.3 - Saisie Date Fin [[ECRAN]](#ecran-t5)

**Role** : Saisie des donnees : Saisie Date Fin.
**Ecran** : 413 x 86 DLU (MDI) | [Voir mockup](#ecran-t5)
**Variables liees** : N (W0-Date Debut), P (W0-Date Fin)


### 3.4 Creation (3 taches)

Insertion de nouveaux enregistrements en base.

---

#### <a id="t6"></a>83.4 - Creation groupe V/V Aller/Reto

**Role** : Creation d'enregistrement : Creation groupe V/V Aller/Reto.
**Variables liees** : A (P0 Groupe Depart)

---

#### <a id="t12"></a>83.7.1 - Creation Hebergement

**Role** : Creation d'enregistrement : Creation Hebergement.

---

#### <a id="t20"></a>83.7.9 - Creation Historique

**Role** : Consultation/chargement : Creation Historique.


### 3.5 Validation (3 taches)

Controles de coherence : 3 taches verifient les donnees et conditions.

---

#### <a id="t8"></a>83.5.1 - Verification Lieu de Sejour

**Role** : Verification : Verification Lieu de Sejour.
**Variables liees** : Z (W0-Lieu de Sejour)

---

#### <a id="t9"></a>83.5.2 - Verification Logement

**Role** : Verification : Verification Logement.
**Variables liees** : BA (W0-Code Logement)

---

#### <a id="t19"></a>83.7.8 - Modification Validation

**Role** : Verification : Modification Validation.


### 3.6 Calcul (1 tache)

Calculs metier : montants, stocks, compteurs.

---

#### <a id="t18"></a>83.7.7 - Modification Compte

**Role** : Traitement : Modification Compte.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Module Sejours CallTask (IDE 0)](PBG-IDE-0.md), [Module Sejours CallTask (IDE 94)](PBG-IDE-94.md), [Module Sejours SubForm (IDE 391)](PBG-IDE-391.md)
- **Appelle**: 7 programmes | **Tables**: 10 (W:7 R:4 L:1) | **Taches**: 20 | **Expressions**: 16

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 20)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 83.3 | 83.3 | Saisie Date Fin | MDI | 413 | 86 | Saisie |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t5"></a>83.3 - Saisie Date Fin
**Tache** : [83.3](#t5) | **Type** : MDI | **Dimensions** : 413 x 86 DLU
**Bloc** : Saisie | **Titre IDE** : Saisie Date Fin

<!-- FORM-DATA:
{
    "width":  413,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  137,
                         "type":  "label",
                         "var":  "",
                         "y":  14,
                         "w":  266,
                         "fmt":  "",
                         "name":  "",
                         "h":  29,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  153,
                         "type":  "label",
                         "var":  "",
                         "y":  23,
                         "w":  70,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Date fin",
                         "parent":  2
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  60,
                         "w":  409,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  357,
                         "type":  "button",
                         "var":  "",
                         "y":  23,
                         "w":  27,
                         "fmt":  "...",
                         "name":  "Btn date",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  229,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  126,
                         "fmt":  "",
                         "name":  "W1-Date Fin",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  2
                     },
                     {
                         "x":  2,
                         "type":  "image",
                         "var":  "",
                         "y":  3,
                         "w":  144,
                         "fmt":  "",
                         "name":  "",
                         "h":  53,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  5,
                         "type":  "button",
                         "var":  "",
                         "y":  63,
                         "w":  154,
                         "fmt":  "\u0026Ok",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  163,
                         "type":  "button",
                         "var":  "",
                         "y":  63,
                         "w":  154,
                         "fmt":  "A\u0026bandonner",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "83.3",
    "height":  86
}
-->

<details>
<summary><strong>Champs : 1 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 229,23 | W1-Date Fin | - | edit |

</details>

<details>
<summary><strong>Boutons : 3 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| ... | 357,23 | Bouton fonctionnel |
| Ok | 5,63 | Valide la saisie et enregistre |
| Abandonner | 163,63 | Annule et retour au menu |

</details>

## 9. NAVIGATION

Ecran unique: **Saisie Date Fin**

### 9.3 Structure hierarchique (20 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **83.1** | [**Prolongation Client** (83)](#t1) [mockup](#ecran-t1) | MDI | 132x56 | Traitement |
| 83.1.1 | [Determination Periode (83.1.1)](#t3) | MDI | - | |
| 83.1.2 | [Recuperation Periode Debut (83.2)](#t4) | MDI | - | |
| 83.1.3 | [Confirmation Prolongation (83.6)](#t10) [mockup](#ecran-t10) | MDI | 240x115 | |
| 83.1.4 | [Prolongation Batch (83.7)](#t11) [mockup](#ecran-t11) | Modal | 132x32 | |
| 83.1.5 | [Modification Package (83.7.2)](#t13) | MDI | - | |
| 83.1.6 | [Modification Heure Fin circuit (83.7.3)](#t14) | MDI | - | |
| 83.1.7 | [Modification Package (83.7.4)](#t15) | MDI | - | |
| 83.1.8 | [Modification Sejour (83.7.5)](#t16) | MDI | - | |
| 83.1.9 | [Modification Sejour (83.7.6)](#t17) | MDI | - | |
| **83.2** | [**Selection Qualite** (83.1)](#t2) | MDI | - | Consultation |
| 83.2.1 | [Selection Logement (83.5)](#t7) | MDI | - | |
| **83.3** | [**Saisie Date Fin** (83.3)](#t5) [mockup](#ecran-t5) | MDI | 413x86 | Saisie |
| **83.4** | [**Creation groupe V/V Aller/Reto** (83.4)](#t6) | MDI | - | Creation |
| 83.4.1 | [Creation Hebergement (83.7.1)](#t12) | MDI | - | |
| 83.4.2 | [Creation Historique (83.7.9)](#t20) | MDI | - | |
| **83.5** | [**Verification Lieu de Sejour** (83.5.1)](#t8) | MDI | - | Validation |
| 83.5.1 | [Verification Logement (83.5.2)](#t9) | MDI | - | |
| 83.5.2 | [Modification Validation (83.7.8)](#t19) | MDI | - | |
| **83.6** | [**Modification Compte** (83.7.7)](#t18) | MDI | - | Calcul |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Saisie Date Fin]
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

### Tables utilisees (10)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 30 | gm-recherche_____gmr | Index de recherche | DB |   | **W** |   | 1 |
| 31 | gm-complet_______gmc |  | DB |   |   | L | 1 |
| 34 | hebergement______heb | Hebergement (chambres) | DB | R | **W** |   | 6 |
| 36 | client_gm |  | DB | R | **W** |   | 2 |
| 47 | compte_gm________cgm | Comptes GM (generaux) | DB |   | **W** |   | 1 |
| 88 | historik_station | Historique / journal | DB |   | **W** |   | 1 |
| 108 | code_logement____clo |  | DB | R |   |   | 1 |
| 118 | tables_imports |  | DB | R |   |   | 1 |
| 131 | fichier_validation |  | DB |   | **W** |   | 1 |
| 134 | groupe_arr_dep___vol |  | DB |   | **W** |   | 1 |

### Colonnes par table (3 / 9 tables avec colonnes identifiees)

<details>
<summary>Table 30 - gm-recherche_____gmr (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 34 - hebergement______heb (R/**W**) - 6 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 36 - client_gm (R/**W**) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 47 - compte_gm________cgm (**W**) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | W1-Compteur Lieu | W | Numeric |

</details>

<details>
<summary>Table 88 - historik_station (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 108 - code_logement____clo (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | W2-Code Retour | R | Numeric |
| BA | W0-Code Logement | R | Alpha |
| C | W0 Ancien Code Vol | R | Alpha |
| H | W0 Code Sexe | R | Alpha |
| I | W0 Code Fumeur | R | Alpha |
| R | W0 Code Vol Aller | R | Alpha |
| V | W0-Code Vol Retour | R | Alpha |

</details>

<details>
<summary>Table 118 - tables_imports (R) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 131 - fichier_validation (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 134 - groupe_arr_dep___vol (**W**) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | v.Selection A/R | W | Alpha |
| B | v.date | W | Date |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (2)

Variables recues du programme appelant ([Module Sejours CallTask (IDE 0)](PBG-IDE-0.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P0 Groupe Depart | Alpha | [83.4](#t6) |
| B | P.I Heure libération | Time | - |

### 11.2 Variables de travail (14)

Variables internes au programme.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| C | W0 Ancien Code Vol | Alpha | - |
| D | W0 Valide ? | Alpha | 1x calcul interne |
| E | W0 Heb Existe ? | Alpha | - |
| F | W0 Age | Alpha | - |
| G | W0 Nationalite | Alpha | - |
| H | W0 Code Sexe | Alpha | - |
| I | W0 Code Fumeur | Alpha | - |
| J | W0 Age num | Numeric | - |
| K | W0 Nb mois | Numeric | - |
| R | W0 Code Vol Aller | Alpha | - |
| S | W0 Transport Aller | Alpha | - |
| T | W0 Ville Aller | Alpha | - |
| U | W0 libelle Trans Ale | Alpha | - |
| Y | W0 Libelle Trans Ret | Alpha | - |

### 11.3 Autres (14)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| L | W0-Qualite | Alpha | - |
| M | W0-Complement | Alpha | - |
| N | W0-Date Debut | Date | - |
| O | W0-Heure Debut | Alpha | - |
| P | W0-Date Fin | Date | - |
| Q | W0-Heure Fin | Alpha | - |
| V | W0-Code Vol Retour | Alpha | - |
| W | W0-Transport Retour | Alpha | - |
| X | W0-Ville Retour | Alpha | - |
| Z | W0-Lieu de Sejour | Alpha | - |
| BA | W0-Code Logement | Alpha | - |
| BB | W0-Occupation | Alpha | - |
| BC | W0-Base Occupation | Alpha | - |
| BD | W0-Accord Suite | Alpha | - |

<details>
<summary>Toutes les 30 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| P0 | **A** | P0 Groupe Depart | Alpha |
| P0 | **B** | P.I Heure libération | Time |
| W0 | **C** | W0 Ancien Code Vol | Alpha |
| W0 | **D** | W0 Valide ? | Alpha |
| W0 | **E** | W0 Heb Existe ? | Alpha |
| W0 | **F** | W0 Age | Alpha |
| W0 | **G** | W0 Nationalite | Alpha |
| W0 | **H** | W0 Code Sexe | Alpha |
| W0 | **I** | W0 Code Fumeur | Alpha |
| W0 | **J** | W0 Age num | Numeric |
| W0 | **K** | W0 Nb mois | Numeric |
| W0 | **R** | W0 Code Vol Aller | Alpha |
| W0 | **S** | W0 Transport Aller | Alpha |
| W0 | **T** | W0 Ville Aller | Alpha |
| W0 | **U** | W0 libelle Trans Ale | Alpha |
| W0 | **Y** | W0 Libelle Trans Ret | Alpha |
| Autre | **L** | W0-Qualite | Alpha |
| Autre | **M** | W0-Complement | Alpha |
| Autre | **N** | W0-Date Debut | Date |
| Autre | **O** | W0-Heure Debut | Alpha |
| Autre | **P** | W0-Date Fin | Date |
| Autre | **Q** | W0-Heure Fin | Alpha |
| Autre | **V** | W0-Code Vol Retour | Alpha |
| Autre | **W** | W0-Transport Retour | Alpha |
| Autre | **X** | W0-Ville Retour | Alpha |
| Autre | **Z** | W0-Lieu de Sejour | Alpha |
| Autre | **BA** | W0-Code Logement | Alpha |
| Autre | **BB** | W0-Occupation | Alpha |
| Autre | **BC** | W0-Base Occupation | Alpha |
| Autre | **BD** | W0-Accord Suite | Alpha |

</details>

## 12. EXPRESSIONS

**16 / 16 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONSTANTE | 5 | 0 |
| OTHER | 7 | 0 |
| CONDITION | 4 | 0 |

### 12.2 Expressions cles par type

#### CONSTANTE (5 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 7 | `'A'` | - |
| CONSTANTE | 9 | `''` | - |
| CONSTANTE | 6 | `'R'` | - |
| CONSTANTE | 4 | `'TBAOC'` | - |
| CONSTANTE | 5 | `'TUP'` | - |

#### OTHER (7 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 14 | `GetParam ('SOCIETE')` | - |
| OTHER | 15 | `GetParam ('NRO_CPTE')` | - |
| OTHER | 16 | `GetParam ('FIL_CPTE')` | - |
| OTHER | 8 | `P0 Groupe Depart [A]` | - |
| OTHER | 1 | `GetParam ('NRO_CPTE')` | - |
| ... | | *+2 autres* | |

#### CONDITION (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 12 | `[AA]='E'` | - |
| CONDITION | 13 | `[AA]='E' AND VG66` | - |
| CONDITION | 10 | `[AA]='O'` | - |
| CONDITION | 11 | `[AA]='O' AND W0 Valide ? [D]<>'O'` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Module Sejours CallTask (IDE 0)](PBG-IDE-0.md) -> **Prolongation Client (IDE 83)**

Main -> ... -> [Module Sejours CallTask (IDE 94)](PBG-IDE-94.md) -> **Prolongation Client (IDE 83)**

Main -> ... -> [Module Sejours SubForm (IDE 391)](PBG-IDE-391.md) -> **Prolongation Client (IDE 83)**

```mermaid
graph LR
    T83[83 Prolongation Client]
    style T83 fill:#58a6ff
    CC391[391 Module Sejours Sub...]
    style CC391 fill:#8b5cf6
    CC94[94 Module Sejours Call...]
    style CC94 fill:#8b5cf6
    CC94 --> T83
    CC391 --> T83
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [0](PBG-IDE-0.md) | Module Sejours CallTask | 1 |
| [94](PBG-IDE-94.md) | Module Sejours CallTask | 1 |
| [391](PBG-IDE-391.md) | Module Sejours SubForm | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T83[83 Prolongation Client]
    style T83 fill:#58a6ff
    C360[360 Zoom Selection Occ...]
    T83 --> C360
    style C360 fill:#3fb950
    C363[363 Zoom Selection Cod...]
    T83 --> C363
    style C363 fill:#3fb950
    C176[176 Demarquage Caisse]
    T83 --> C176
    style C176 fill:#3fb950
    C338[338 Date fin effectift...]
    T83 --> C338
    style C338 fill:#3fb950
    C361[361 Zoom Affichage Cod...]
    T83 --> C361
    style C361 fill:#3fb950
    C362[362 Zoom Affichage Lie...]
    T83 --> C362
    style C362 fill:#3fb950
    C365[365 Zoom Qualite]
    T83 --> C365
    style C365 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [360](PBG-IDE-360.md) | Zoom Selection Occupation | 2 | Selection/consultation |
| [363](PBG-IDE-363.md) | Zoom Selection Code-Vol | 2 | Selection/consultation |
| [176](PBG-IDE-176.md) | Demarquage Caisse | 1 | Sous-programme |
| [338](PBG-IDE-338.md) | Date fin effectif/t transfert | 1 | Transfert donnees |
| [361](PBG-IDE-361.md) | Zoom Affichage Code Logement | 1 | Selection/consultation |
| [362](PBG-IDE-362.md) | Zoom Affichage Lieu de Sejour | 1 | Selection/consultation |
| [365](PBG-IDE-365.md) | Zoom Qualite | 1 | Selection/consultation |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 423 | Taille moyenne |
| Expressions | 16 | Peu de logique |
| Tables WRITE | 7 | Fort impact donnees |
| Sous-programmes | 7 | Dependances moderees |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 423) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (10 taches: 3 ecrans, 7 traitements)

- **Strategie** : Orchestrateur avec 3 ecrans (Razor/React) et 7 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 7 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Consultation (2 taches: 0 ecran, 2 traitements)

- **Strategie** : Composants de recherche/selection en modales.

#### Saisie (1 tache: 1 ecran, 0 traitement)

- **Strategie** : Formulaire React/Blazor avec validation Zod/FluentValidation.
- Reproduire 1 ecran : Saisie Date Fin
- Validation temps reel cote client + serveur

#### Creation (3 taches: 0 ecran, 3 traitements)

- **Strategie** : Repository pattern avec Entity Framework Core.
- Insertion via `IRepository<T>.CreateAsync()`

#### Validation (3 taches: 0 ecran, 3 traitements)

- **Strategie** : FluentValidation avec validators specifiques.
- Chaque tache de validation -> un validator injectable

#### Calcul (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Services de calcul purs (Domain Services).
- Migrer la logique de calcul (stock, compteurs, montants)

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| gm-recherche_____gmr | Table WRITE (Database) | 1x | Schema + repository |
| hebergement______heb | Table WRITE (Database) | 4x | Schema + repository |
| client_gm | Table WRITE (Database) | 1x | Schema + repository |
| compte_gm________cgm | Table WRITE (Database) | 1x | Schema + repository |
| historik_station | Table WRITE (Database) | 1x | Schema + repository |
| fichier_validation | Table WRITE (Database) | 1x | Schema + repository |
| groupe_arr_dep___vol | Table WRITE (Database) | 1x | Schema + repository |
| [Zoom Selection Code-Vol (IDE 363)](PBG-IDE-363.md) | Sous-programme | 2x | Haute - Selection/consultation |
| [Zoom Selection Occupation (IDE 360)](PBG-IDE-360.md) | Sous-programme | 2x | Haute - Selection/consultation |
| [Zoom Affichage Lieu de Sejour (IDE 362)](PBG-IDE-362.md) | Sous-programme | 1x | Normale - Selection/consultation |
| [Zoom Qualite (IDE 365)](PBG-IDE-365.md) | Sous-programme | 1x | Normale - Selection/consultation |
| [Zoom Affichage Code Logement (IDE 361)](PBG-IDE-361.md) | Sous-programme | 1x | Normale - Selection/consultation |
| [Demarquage Caisse (IDE 176)](PBG-IDE-176.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Date fin effectif/t transfert (IDE 338)](PBG-IDE-338.md) | Sous-programme | 1x | Normale - Transfert donnees |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 09:14*
