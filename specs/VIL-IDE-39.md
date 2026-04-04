# VIL IDE 39 - CV  Verification caisse

> **Analyse**: Phases 1-4 2026-02-03 01:24 -> 01:24 (36s) | Assemblage 01:24
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | VIL |
| IDE Position | 39 |
| Nom Programme | CV  Verification caisse |
| Fichier source | `Prg_39.xml` |
| Domaine metier | Caisse |
| Taches | 8 (1 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 7 |

## 2. DESCRIPTION FONCTIONNELLE

**CV  Verification caisse** assure la gestion complete de ce processus, accessible depuis [CV  Menu Clôture de caisse (IDE 36)](VIL-IDE-36.md).

Le flux de traitement s'organise en **3 blocs fonctionnels** :

- **Traitement** (6 taches) : traitements metier divers
- **Validation** (1 tache) : controles et verifications de coherence
- **Consultation** (1 tache) : ecrans de recherche, selection et consultation

**Donnees modifiees** : 1 tables en ecriture (solde_caisse_____sks).

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Validation (1 tache)

- **39** - AC  Verification caisse **[[ECRAN]](#ecran-t1)**

#### Phase 2 : Consultation (1 tache)

- **39.1** - Affichage menu operations **[[ECRAN]](#ecran-t2)**

Delegue a : [Recup Classe et Lib du MOP (IDE 120)](VIL-IDE-120.md)

#### Phase 3 : Traitement (6 taches)

- **39.2** - Lecture solde veille
- **39.3** - (sans nom) **[[ECRAN]](#ecran-t4)**
- **39.4** - MAJ nouveau solde
- **39.5** - Versements/Retraits
- **39.6** - Recuperation n° pièce change
- **39.6.1** - Recup imputation chge

Delegue a : [Appel programme (IDE 42)](VIL-IDE-42.md), [Liste des telecollectes (IDE 70)](VIL-IDE-70.md)

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| solde_caisse_____sks | R/**W** (2 usages) | Sessions de caisse |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Validation (1 tache)

Controles de coherence : 1 tache verifie les donnees et conditions.

---

#### <a id="t1"></a>39 - AC  Verification caisse [[ECRAN]](#ecran-t1)

**Role** : Verification : AC  Verification caisse.
**Ecran** : 118 x 110 DLU (MDI) | [Voir mockup](#ecran-t1)
**Variables liees** : F (P0 top verif caisse)


### 3.2 Consultation (1 tache)

Ecrans de recherche et consultation.

---

#### <a id="t2"></a>39.1 - Affichage menu operations [[ECRAN]](#ecran-t2)

**Role** : Reinitialisation : Affichage menu operations.
**Ecran** : 780 x 249 DLU (MDI) | [Voir mockup](#ecran-t2)


### 3.3 Traitement (6 taches)

Traitements internes.

---

#### <a id="t3"></a>39.2 - Lecture solde veille

**Role** : Consultation/chargement : Lecture solde veille.
**Variables liees** : Q (WP0 solde veille)
**Delegue a** : [Appel programme (IDE 42)](VIL-IDE-42.md), [Liste des telecollectes (IDE 70)](VIL-IDE-70.md)

---

#### <a id="t4"></a>39.3 - (sans nom) [[ECRAN]](#ecran-t4)

**Role** : Traitement interne.
**Ecran** : 100 x 24 DLU (MDI) | [Voir mockup](#ecran-t4)
**Delegue a** : [Appel programme (IDE 42)](VIL-IDE-42.md), [Liste des telecollectes (IDE 70)](VIL-IDE-70.md)

---

#### <a id="t5"></a>39.4 - MAJ nouveau solde

**Role** : Consultation/chargement : MAJ nouveau solde.
**Variables liees** : Q (WP0 solde veille)
**Delegue a** : [Appel programme (IDE 42)](VIL-IDE-42.md), [Liste des telecollectes (IDE 70)](VIL-IDE-70.md)

---

#### <a id="t7"></a>39.5 - Versements/Retraits

**Role** : Traitement : Versements/Retraits.
**Delegue a** : [Appel programme (IDE 42)](VIL-IDE-42.md), [Liste des telecollectes (IDE 70)](VIL-IDE-70.md)

---

#### <a id="t8"></a>39.6 - Recuperation n° pièce change

**Role** : Consultation/chargement : Recuperation n° pièce change.
**Variables liees** : E (P0 n° pièce change)
**Delegue a** : [Appel programme (IDE 42)](VIL-IDE-42.md), [Liste des telecollectes (IDE 70)](VIL-IDE-70.md)

---

#### <a id="t9"></a>39.6.1 - Recup imputation chge

**Role** : Consultation/chargement : Recup imputation chge.
**Delegue a** : [Appel programme (IDE 42)](VIL-IDE-42.md), [Liste des telecollectes (IDE 70)](VIL-IDE-70.md)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [CV  Menu Clôture de caisse (IDE 36)](VIL-IDE-36.md)
- **Appelle**: 7 programmes | **Tables**: 4 (W:1 R:4 L:0) | **Taches**: 8 | **Expressions**: 18

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 8)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 39.1 | 39.1 | Affichage menu operations | MDI | 780 | 249 | Consultation |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t2"></a>39.1 - Affichage menu operations
**Tache** : [39.1](#t2) | **Type** : MDI | **Dimensions** : 780 x 249 DLU
**Bloc** : Consultation | **Titre IDE** : Affichage menu operations

<!-- FORM-DATA:
{
    "width":  780,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  1,
                         "type":  "label",
                         "var":  "",
                         "y":  2,
                         "w":  768,
                         "fmt":  "",
                         "name":  "",
                         "h":  17,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  4,
                         "type":  "label",
                         "var":  "",
                         "y":  24,
                         "w":  761,
                         "fmt":  "",
                         "name":  "",
                         "h":  195,
                         "color":  "2",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  65,
                         "type":  "label",
                         "var":  "",
                         "y":  41,
                         "w":  642,
                         "fmt":  "",
                         "name":  "",
                         "h":  46,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  70,
                         "type":  "label",
                         "var":  "",
                         "y":  47,
                         "w":  110,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "Solde veille",
                         "parent":  null
                     },
                     {
                         "x":  370,
                         "type":  "label",
                         "var":  "",
                         "y":  47,
                         "w":  133,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Pces de caisse",
                         "parent":  null
                     },
                     {
                         "x":  70,
                         "type":  "label",
                         "var":  "",
                         "y":  59,
                         "w":  103,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "Versements",
                         "parent":  null
                     },
                     {
                         "x":  370,
                         "type":  "label",
                         "var":  "",
                         "y":  59,
                         "w":  133,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Solde du jour",
                         "parent":  null
                     },
                     {
                         "x":  70,
                         "type":  "label",
                         "var":  "",
                         "y":  71,
                         "w":  78,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "Retraits",
                         "parent":  null
                     },
                     {
                         "x":  100,
                         "type":  "label",
                         "var":  "",
                         "y":  94,
                         "w":  572,
                         "fmt":  "",
                         "name":  "",
                         "h":  105,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  102,
                         "type":  "label",
                         "var":  "",
                         "y":  95,
                         "w":  568,
                         "fmt":  "",
                         "name":  "",
                         "h":  119,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  272,
                         "type":  "label",
                         "var":  "",
                         "y":  101,
                         "w":  367,
                         "fmt":  "",
                         "name":  "",
                         "h":  90,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  275,
                         "type":  "label",
                         "var":  "",
                         "y":  102,
                         "w":  42,
                         "fmt":  "",
                         "name":  "",
                         "h":  90,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  323,
                         "type":  "label",
                         "var":  "",
                         "y":  106,
                         "w":  235,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "7",
                         "text":  "Listing ventes",
                         "parent":  null
                     },
                     {
                         "x":  323,
                         "type":  "label",
                         "var":  "",
                         "y":  128,
                         "w":  235,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "7",
                         "text":  "Listing telecollectes",
                         "parent":  null
                     },
                     {
                         "x":  323,
                         "type":  "label",
                         "var":  "",
                         "y":  149,
                         "w":  235,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "7",
                         "text":  "Brouillard de caisse",
                         "parent":  null
                     },
                     {
                         "x":  323,
                         "type":  "label",
                         "var":  "",
                         "y":  170,
                         "w":  235,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "7",
                         "text":  "Clôture de caisse",
                         "parent":  null
                     },
                     {
                         "x":  373,
                         "type":  "label",
                         "var":  "",
                         "y":  197,
                         "w":  103,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Votre choix",
                         "parent":  null
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  222,
                         "w":  772,
                         "fmt":  "",
                         "name":  "",
                         "h":  23,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  489,
                         "type":  "edit",
                         "var":  "",
                         "y":  196,
                         "w":  27,
                         "fmt":  "UA",
                         "name":  "W1 choix action",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  5,
                         "type":  "edit",
                         "var":  "",
                         "y":  6,
                         "w":  223,
                         "fmt":  "20",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  593,
                         "type":  "edit",
                         "var":  "",
                         "y":  6,
                         "w":  169,
                         "fmt":  "WWW DD MMM YYYYZ",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  65,
                         "type":  "edit",
                         "var":  "",
                         "y":  26,
                         "w":  642,
                         "fmt":  "50",
                         "name":  "",
                         "h":  15,
                         "color":  "7",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  183,
                         "type":  "edit",
                         "var":  "",
                         "y":  47,
                         "w":  168,
                         "fmt":  "17",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  508,
                         "type":  "edit",
                         "var":  "",
                         "y":  47,
                         "w":  168,
                         "fmt":  "17",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  183,
                         "type":  "edit",
                         "var":  "",
                         "y":  59,
                         "w":  168,
                         "fmt":  "17",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  508,
                         "type":  "edit",
                         "var":  "",
                         "y":  59,
                         "w":  168,
                         "fmt":  "17",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  183,
                         "type":  "edit",
                         "var":  "",
                         "y":  71,
                         "w":  168,
                         "fmt":  "17",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  117,
                         "type":  "image",
                         "var":  "",
                         "y":  103,
                         "w":  133,
                         "fmt":  "",
                         "name":  "",
                         "h":  38,
                         "color":  "7",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  283,
                         "type":  "button",
                         "var":  "",
                         "y":  106,
                         "w":  22,
                         "fmt":  "1",
                         "name":  "1",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  589,
                         "type":  "edit",
                         "var":  "",
                         "y":  106,
                         "w":  38,
                         "fmt":  "2",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  283,
                         "type":  "button",
                         "var":  "",
                         "y":  127,
                         "w":  22,
                         "fmt":  "2",
                         "name":  "2",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  589,
                         "type":  "edit",
                         "var":  "",
                         "y":  128,
                         "w":  38,
                         "fmt":  "2",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  283,
                         "type":  "button",
                         "var":  "",
                         "y":  148,
                         "w":  22,
                         "fmt":  "3",
                         "name":  "3",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  589,
                         "type":  "edit",
                         "var":  "",
                         "y":  149,
                         "w":  38,
                         "fmt":  "2",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  124,
                         "type":  "image",
                         "var":  "",
                         "y":  144,
                         "w":  112,
                         "fmt":  "",
                         "name":  "",
                         "h":  50,
                         "color":  "7",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  283,
                         "type":  "button",
                         "var":  "",
                         "y":  169,
                         "w":  22,
                         "fmt":  "4",
                         "name":  "4",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  589,
                         "type":  "edit",
                         "var":  "",
                         "y":  170,
                         "w":  38,
                         "fmt":  "2",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  5,
                         "type":  "button",
                         "var":  "",
                         "y":  225,
                         "w":  137,
                         "fmt":  "\u0026Quitter",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "39.1",
    "height":  249
}
-->

<details>
<summary><strong>Champs : 13 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 489,196 | W1 choix action | - | edit |
| 5,6 | 20 | - | edit |
| 593,6 | WWW DD MMM YYYYZ | - | edit |
| 65,26 | 50 | - | edit |
| 183,47 | 17 | - | edit |
| 508,47 | 17 | - | edit |
| 183,59 | 17 | - | edit |
| 508,59 | 17 | - | edit |
| 183,71 | 17 | - | edit |
| 589,106 | 2 | - | edit |
| 589,128 | 2 | - | edit |
| 589,149 | 2 | - | edit |
| 589,170 | 2 | - | edit |

</details>

<details>
<summary><strong>Boutons : 5 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| 1 | 283,106 | Bouton fonctionnel |
| 2 | 283,127 | Bouton fonctionnel |
| 3 | 283,148 | Bouton fonctionnel |
| 4 | 283,169 | Bouton fonctionnel |
| Quitter | 5,225 | Quitte le programme |

</details>

## 9. NAVIGATION

Ecran unique: **Affichage menu operations**

### 9.3 Structure hierarchique (8 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **39.1** | [**AC  Verification caisse** (39)](#t1) [mockup](#ecran-t1) | MDI | 118x110 | Validation |
| **39.2** | [**Affichage menu operations** (39.1)](#t2) [mockup](#ecran-t2) | MDI | 780x249 | Consultation |
| **39.3** | [**Lecture solde veille** (39.2)](#t3) | MDI | - | Traitement |
| 39.3.1 | [(sans nom) (39.3)](#t4) [mockup](#ecran-t4) | MDI | 100x24 | |
| 39.3.2 | [MAJ nouveau solde (39.4)](#t5) | MDI | - | |
| 39.3.3 | [Versements/Retraits (39.5)](#t7) | MDI | - | |
| 39.3.4 | [Recuperation n° pièce change (39.6)](#t8) | MDI | - | |
| 39.3.5 | [Recup imputation chge (39.6.1)](#t9) | MDI | - | |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[saisie du choix daction]
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

### Tables utilisees (4)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 40 | comptable________cte |  | DB | R |   |   | 1 |
| 54 | pieces_caisse____pks | Sessions de caisse | DB | R |   |   | 1 |
| 55 | solde_caisse_____sks | Sessions de caisse | DB | R | **W** |   | 2 |
| 66 | imputations______imp |  | DB | R |   |   | 1 |

### Colonnes par table (3 / 4 tables avec colonnes identifiees)

<details>
<summary>Table 40 - comptable________cte (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| D | P0 date comptable | R | Date |

</details>

<details>
<summary>Table 54 - pieces_caisse____pks (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| F | P0 top verif caisse | R | Alpha |

</details>

<details>
<summary>Table 55 - solde_caisse_____sks (R/**W**) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| F | P0 top verif caisse | W | Alpha |
| Q | WP0 solde veille | W | Numeric |

</details>

<details>
<summary>Table 66 - imputations______imp (R) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (11)

Variables recues du programme appelant ([CV  Menu Clôture de caisse (IDE 36)](VIL-IDE-36.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P0 societe | Alpha | 1x parametre entrant |
| B | P0 nbre decimales | Numeric | - |
| C | P0 masque cumul | Alpha | - |
| D | P0 date comptable | Date | - |
| E | P0 n° pièce change | Numeric | - |
| F | P0 top verif caisse | Alpha | [39](#t1) |
| G | P0 devise locale | Alpha | 1x parametre entrant |
| H | P0 masque montant | Alpha | 1x parametre entrant |
| I | P0 nom village | Alpha | - |
| J | P0 uni/bilateral | Alpha | - |
| K | P0 Action Abandon | Alpha | - |

### 11.2 Variables de travail (6)

Variables internes au programme.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| L | W0 clôture/ventes | Alpha | 1x calcul interne |
| M | W0 clôture/telecollectes | Alpha | 1x calcul interne |
| N | W0 clôture/brouillar | Alpha | 1x calcul interne |
| W | W0 choix action | Alpha | 6x calcul interne |
| X | W0 message | Alpha | 2x calcul interne |
| Y | W0 resultat ventes | Numeric | - |

### 11.3 Autres (12)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| O | WP0 montant versmnt | Numeric | - |
| P | WP0 montant retrait | Numeric | - |
| Q | WP0 solde veille | Numeric | - |
| R | WP0 pkes recette | Numeric | - |
| S | WP0 pkes depense | Numeric | - |
| T | WP0 dev. local bidon | Alpha | - |
| U | WP0 masque montant | Alpha | - |
| V | WP0 appel depuis clô | Alpha | - |
| Z | WP0 Versement CASH | Numeric | - |
| BA | WP0 Versement NON CASH | Numeric | - |
| BB | WP0 Retrait CASH | Numeric | - |
| BC | WP0 Retrait NON CASH | Numeric | - |

<details>
<summary>Toutes les 29 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| P0 | **A** | P0 societe | Alpha |
| P0 | **B** | P0 nbre decimales | Numeric |
| P0 | **C** | P0 masque cumul | Alpha |
| P0 | **D** | P0 date comptable | Date |
| P0 | **E** | P0 n° pièce change | Numeric |
| P0 | **F** | P0 top verif caisse | Alpha |
| P0 | **G** | P0 devise locale | Alpha |
| P0 | **H** | P0 masque montant | Alpha |
| P0 | **I** | P0 nom village | Alpha |
| P0 | **J** | P0 uni/bilateral | Alpha |
| P0 | **K** | P0 Action Abandon | Alpha |
| W0 | **L** | W0 clôture/ventes | Alpha |
| W0 | **M** | W0 clôture/telecollectes | Alpha |
| W0 | **N** | W0 clôture/brouillar | Alpha |
| W0 | **W** | W0 choix action | Alpha |
| W0 | **X** | W0 message | Alpha |
| W0 | **Y** | W0 resultat ventes | Numeric |
| Autre | **O** | WP0 montant versmnt | Numeric |
| Autre | **P** | WP0 montant retrait | Numeric |
| Autre | **Q** | WP0 solde veille | Numeric |
| Autre | **R** | WP0 pkes recette | Numeric |
| Autre | **S** | WP0 pkes depense | Numeric |
| Autre | **T** | WP0 dev. local bidon | Alpha |
| Autre | **U** | WP0 masque montant | Alpha |
| Autre | **V** | WP0 appel depuis clô | Alpha |
| Autre | **Z** | WP0 Versement CASH | Numeric |
| Autre | **BA** | WP0 Versement NON CASH | Numeric |
| Autre | **BB** | WP0 Retrait CASH | Numeric |
| Autre | **BC** | WP0 Retrait NON CASH | Numeric |

</details>

## 12. EXPRESSIONS

**18 / 18 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONSTANTE | 7 | 0 |
| CONDITION | 8 | 0 |
| OTHER | 3 | 0 |

### 12.2 Expressions cles par type

#### CONSTANTE (7 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 15 | `''` | - |
| CONSTANTE | 16 | `0` | - |
| CONSTANTE | 17 | `'2'` | - |
| CONSTANTE | 14 | `2` | - |
| CONSTANTE | 2 | `'C'` | - |
| ... | | *+2 autres* | |

#### CONDITION (8 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 11 | `W0 choix action [W]='3' AND W0 clôture/telecollectes [M]='O' AND P0 top verif caisse [F]<>'O'` | - |
| CONDITION | 10 | `W0 choix action [W]='2' AND W0 clôture/ventes [L]='O' AND P0 top verif caisse [F]<>'O'` | - |
| CONDITION | 13 | `W0 message [X]<>''` | - |
| CONDITION | 12 | `W0 choix action [W]='4' AND W0 clôture/brouillar [N]='O' AND P0 top verif caisse [F]<>'O'` | - |
| CONDITION | 7 | `W0 choix action [W]='F'` | - |
| ... | | *+3 autres* | |

#### OTHER (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 18 | `W0 message [X]` | - |
| OTHER | 5 | `P0 masque montant [H]` | - |
| OTHER | 4 | `P0 devise locale [G]` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [CV  Menu Clôture de caisse (IDE 36)](VIL-IDE-36.md) -> **CV  Verification caisse (IDE 39)**

```mermaid
graph LR
    T39[39 CV Verification caisse]
    style T39 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC78[78 Lance correspittivi]
    style CC78 fill:#8b5cf6
    CC148[148 CV Menu caisse vil...]
    style CC148 fill:#f59e0b
    CC36[36 CV Menu Clôture de ...]
    style CC36 fill:#3fb950
    CC148 --> CC36
    CC1 --> CC148
    CC78 --> CC148
    CC36 --> T39
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [36](VIL-IDE-36.md) | CV  Menu Clôture de caisse | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T39[39 CV Verification caisse]
    style T39 fill:#58a6ff
    C66[66 Print brouillardclo...]
    T39 --> C66
    style C66 fill:#3fb950
    C42[42 Appel programme]
    T39 --> C42
    style C42 fill:#3fb950
    C58[58 CV Print pièce de c...]
    T39 --> C58
    style C58 fill:#3fb950
    C67[67 Print Ecart]
    T39 --> C67
    style C67 fill:#3fb950
    C70[70 Liste des telecolle...]
    T39 --> C70
    style C70 fill:#3fb950
    C96[96 Liste des ventes]
    T39 --> C96
    style C96 fill:#3fb950
    C120[120 Recup Classe et Li...]
    T39 --> C120
    style C120 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [66](VIL-IDE-66.md) | Print brouillard/cloture | 2 | Impression ticket/document |
| [42](VIL-IDE-42.md) | Appel programme | 1 | Sous-programme |
| [58](VIL-IDE-58.md) | CV  Print pièce de caisse | 1 | Impression ticket/document |
| [67](VIL-IDE-67.md) | Print Ecart | 1 | Impression ticket/document |
| [70](VIL-IDE-70.md) | Liste des telecollectes | 1 | Configuration impression |
| [96](VIL-IDE-96.md) | Liste des ventes | 1 | Configuration impression |
| [120](VIL-IDE-120.md) | Recup Classe et Lib du MOP | 1 | Recuperation donnees |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 162 | Programme compact |
| Expressions | 18 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 7 | Dependances moderees |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 162) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Validation (1 tache: 1 ecran, 0 traitement)

- **Strategie** : FluentValidation avec validators specifiques.
- Chaque tache de validation -> un validator injectable

#### Consultation (1 tache: 1 ecran, 0 traitement)

- **Strategie** : Composants de recherche/selection en modales.
- 1 ecran : Affichage menu operations

#### Traitement (6 taches: 1 ecran, 5 traitements)

- **Strategie** : Orchestrateur avec 1 ecrans (Razor/React) et 5 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 7 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| solde_caisse_____sks | Table WRITE (Database) | 1x | Schema + repository |
| [Print brouillard/cloture (IDE 66)](VIL-IDE-66.md) | Sous-programme | 2x | Haute - Impression ticket/document |
| [Liste des telecollectes (IDE 70)](VIL-IDE-70.md) | Sous-programme | 1x | Normale - Configuration impression |
| [Liste des ventes (IDE 96)](VIL-IDE-96.md) | Sous-programme | 1x | Normale - Configuration impression |
| [Recup Classe et Lib du MOP (IDE 120)](VIL-IDE-120.md) | Sous-programme | 1x | Normale - Recuperation donnees |
| [Appel programme (IDE 42)](VIL-IDE-42.md) | Sous-programme | 1x | Normale - Sous-programme |
| [CV  Print pièce de caisse (IDE 58)](VIL-IDE-58.md) | Sous-programme | 1x | Normale - Impression ticket/document |
| [Print Ecart (IDE 67)](VIL-IDE-67.md) | Sous-programme | 1x | Normale - Impression ticket/document |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 01:24*
