# EXF IDE 12 - Liste ventes/Excursion

> **Analyse**: Phases 1-4 2026-02-03 10:55 -> 10:56 (16s) | Assemblage 10:56
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | EXF |
| IDE Position | 12 |
| Nom Programme | Liste ventes/Excursion |
| Fichier source | `Prg_12.xml` |
| Dossier IDE | Menu |
| Taches | 4 (3 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 7 |

## 2. DESCRIPTION FONCTIONNELLE

**Liste ventes/Excursion** assure la gestion complete de ce processus, accessible depuis [   Menu listes (IDE 14)](EXF-IDE-14.md).

Le flux de traitement s'organise en **3 blocs fonctionnels** :

- **Saisie** (2 taches) : ecrans de saisie utilisateur (formulaires, champs, donnees)
- **Consultation** (1 tache) : ecrans de recherche, selection et consultation
- **Traitement** (1 tache) : traitements metier divers

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Saisie (2 taches)

- **12** - Ventes **[[ECRAN]](#ecran-t1)**
- **12.1** - Liste ventes par exc **[[ECRAN]](#ecran-t2)**

#### Phase 2 : Traitement (1 tache)

- **12.1.1** - Participants **[[ECRAN]](#ecran-t3)**

Delegue a : [Recuperation du titre (IDE 31)](EXF-IDE-31.md), [Set Listing Number (IDE 19)](EXF-IDE-19.md), [Reçu duplicata new (IDE 25)](EXF-IDE-25.md), [Appel programme (IDE 33)](EXF-IDE-33.md)

#### Phase 3 : Consultation (1 tache)

- **12.2** - Recherche **[[ECRAN]](#ecran-t4)**

Delegue a : [Recuperation du titre (IDE 31)](EXF-IDE-31.md)

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Saisie (2 taches)

L'operateur saisit les donnees de la transaction via 2 ecrans (Ventes, Liste ventes par exc).

---

#### <a id="t1"></a>12 - Ventes [[ECRAN]](#ecran-t1)

**Role** : Saisie des donnees : Ventes.
**Ecran** : 166 x 12 DLU (MDI) | [Voir mockup](#ecran-t1)

---

#### <a id="t2"></a>12.1 - Liste ventes par exc [[ECRAN]](#ecran-t2)

**Role** : Saisie des donnees : Liste ventes par exc.
**Ecran** : 1229 x 257 DLU (MDI) | [Voir mockup](#ecran-t2)


### 3.2 Traitement (1 tache)

Traitements internes.

---

#### <a id="t3"></a>12.1.1 - Participants [[ECRAN]](#ecran-t3)

**Role** : Traitement : Participants.
**Ecran** : 566 x 228 DLU (MDI) | [Voir mockup](#ecran-t3)
**Delegue a** : [Recuperation du titre (IDE 31)](EXF-IDE-31.md), [Set Listing Number (IDE 19)](EXF-IDE-19.md), [Reçu duplicata new (IDE 25)](EXF-IDE-25.md)


### 3.3 Consultation (1 tache)

Ecrans de recherche et consultation.

---

#### <a id="t4"></a>12.2 - Recherche [[ECRAN]](#ecran-t4)

**Role** : Traitement : Recherche.
**Ecran** : 523 x 89 DLU (MDI) | [Voir mockup](#ecran-t4)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [   Menu listes (IDE 14)](EXF-IDE-14.md)
- **Appelle**: 7 programmes | **Tables**: 3 (W:0 R:2 L:1) | **Taches**: 4 | **Expressions**: 4

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (3 / 4)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 12.1 | 12.1 | Liste ventes par exc | MDI | 1229 | 257 | Saisie |
| 2 | 12.1.1 | 12.1.1 | Participants | MDI | 566 | 228 | Traitement |
| 3 | 12.2 | 12.2 | Recherche | MDI | 523 | 89 | Consultation |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t2"></a>12.1 - Liste ventes par exc
**Tache** : [12.1](#t2) | **Type** : MDI | **Dimensions** : 1229 x 257 DLU
**Bloc** : Saisie | **Titre IDE** : Liste ventes par exc

<!-- FORM-DATA:
{
    "width":  1229,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  2,
                         "type":  "label",
                         "var":  "",
                         "y":  1,
                         "w":  1218,
                         "fmt":  "",
                         "name":  "",
                         "h":  17,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  17,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "110",
                         "w":  1197,
                         "y":  22,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  14,
                         "h":  110,
                         "cols":  [
                                      {
                                          "title":  "Date Comptable",
                                          "layer":  1,
                                          "w":  130
                                      },
                                      {
                                          "title":  "Code Excursion / Vente",
                                          "layer":  2,
                                          "w":  212
                                      },
                                      {
                                          "title":  "Montant",
                                          "layer":  3,
                                          "w":  159
                                      },
                                      {
                                          "title":  "Paiement",
                                          "layer":  4,
                                          "w":  86
                                      },
                                      {
                                          "title":  "Excursion",
                                          "layer":  5,
                                          "w":  239
                                      },
                                      {
                                          "title":  "Payé par",
                                          "layer":  6,
                                          "w":  335
                                      }
                                  ],
                         "rows":  6
                     },
                     {
                         "x":  49,
                         "type":  "label",
                         "var":  "",
                         "y":  151,
                         "w":  251,
                         "fmt":  "",
                         "name":  "",
                         "h":  69,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  79,
                         "type":  "label",
                         "var":  "",
                         "y":  156,
                         "w":  196,
                         "fmt":  "",
                         "name":  "",
                         "h":  40,
                         "color":  "",
                         "text":  "",
                         "parent":  20
                     },
                     {
                         "x":  80,
                         "type":  "label",
                         "var":  "",
                         "y":  162,
                         "w":  34,
                         "fmt":  "",
                         "name":  "",
                         "h":  33,
                         "color":  "",
                         "text":  "",
                         "parent":  21
                     },
                     {
                         "x":  122,
                         "type":  "label",
                         "var":  "",
                         "y":  166,
                         "w":  125,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "142",
                         "text":  "Recherche",
                         "parent":  21
                     },
                     {
                         "x":  122,
                         "type":  "label",
                         "var":  "",
                         "y":  181,
                         "w":  125,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "142",
                         "text":  "Impression",
                         "parent":  21
                     },
                     {
                         "x":  92,
                         "type":  "label",
                         "var":  "",
                         "y":  201,
                         "w":  120,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "Votre choix",
                         "parent":  20
                     },
                     {
                         "x":  2,
                         "type":  "label",
                         "var":  "",
                         "y":  231,
                         "w":  1220,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  258,
                         "type":  "edit",
                         "var":  "",
                         "y":  38,
                         "w":  98,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  525,
                         "type":  "edit",
                         "var":  "",
                         "y":  38,
                         "w":  75,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  861,
                         "type":  "edit",
                         "var":  "",
                         "y":  38,
                         "w":  176,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  1045,
                         "type":  "edit",
                         "var":  "",
                         "y":  38,
                         "w":  98,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  22,
                         "type":  "edit",
                         "var":  "",
                         "y":  38,
                         "w":  117,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  370,
                         "type":  "edit",
                         "var":  "",
                         "y":  38,
                         "w":  146,
                         "fmt":  "N## ### ### ###.###Z",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  154,
                         "type":  "edit",
                         "var":  "",
                         "y":  38,
                         "w":  98,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  610,
                         "type":  "edit",
                         "var":  "",
                         "y":  38,
                         "w":  232,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  228,
                         "type":  "edit",
                         "var":  "",
                         "y":  201,
                         "w":  26,
                         "fmt":  "",
                         "name":  "W1 choix action",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  20
                     },
                     {
                         "x":  5,
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
                         "x":  1009,
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
                         "x":  1150,
                         "type":  "button",
                         "var":  "",
                         "y":  35,
                         "w":  28,
                         "fmt":  "...",
                         "name":  "",
                         "h":  13,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  654,
                         "type":  "image",
                         "var":  "",
                         "y":  139,
                         "w":  174,
                         "fmt":  "",
                         "name":  "",
                         "h":  87,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  83,
                         "type":  "button",
                         "var":  "",
                         "y":  166,
                         "w":  24,
                         "fmt":  "R",
                         "name":  "R",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  21
                     },
                     {
                         "x":  83,
                         "type":  "button",
                         "var":  "",
                         "y":  181,
                         "w":  24,
                         "fmt":  "I",
                         "name":  "I",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  21
                     },
                     {
                         "x":  9,
                         "type":  "button",
                         "var":  "",
                         "y":  234,
                         "w":  154,
                         "fmt":  "\u0026Quitter",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  27
                     },
                     {
                         "x":  1045,
                         "type":  "button",
                         "var":  "",
                         "y":  234,
                         "w":  168,
                         "fmt":  "Printer",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "12.1",
    "height":  257
}
-->

<details>
<summary><strong>Champs : 11 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 258,38 | (sans nom) | - | edit |
| 525,38 | (sans nom) | - | edit |
| 861,38 | (sans nom) | - | edit |
| 1045,38 | (sans nom) | - | edit |
| 22,38 | (sans nom) | - | edit |
| 370,38 | N## ### ### ###.###Z | - | edit |
| 154,38 | (sans nom) | - | edit |
| 610,38 | (sans nom) | - | edit |
| 228,201 | W1 choix action | - | edit |
| 5,6 | 20 | - | edit |
| 1009,6 | WWW DD MMM YYYYT | - | edit |

</details>

<details>
<summary><strong>Boutons : 5 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| ... | 1150,35 | Bouton fonctionnel |
| R | 83,166 | Bouton fonctionnel |
| I | 83,181 | Bouton fonctionnel |
| Quitter | 9,234 | Quitte le programme |
| Printer | 1045,234 | Appel [Get Printer (IDE 17)](EXF-IDE-17.md) |

</details>

---

#### <a id="ecran-t3"></a>12.1.1 - Participants
**Tache** : [12.1.1](#t3) | **Type** : MDI | **Dimensions** : 566 x 228 DLU
**Bloc** : Traitement | **Titre IDE** : Participants

<!-- FORM-DATA:
{
    "width":  566,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  2,
                         "type":  "label",
                         "var":  "",
                         "y":  1,
                         "w":  559,
                         "fmt":  "",
                         "name":  "",
                         "h":  19,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  28,
                         "type":  "label",
                         "var":  "",
                         "y":  27,
                         "w":  82,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Excursion",
                         "parent":  null
                     },
                     {
                         "x":  371,
                         "type":  "label",
                         "var":  "",
                         "y":  27,
                         "w":  27,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "du",
                         "parent":  null
                     },
                     {
                         "x":  107,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "110",
                         "w":  354,
                         "y":  44,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  14,
                         "h":  153,
                         "cols":  [
                                      {
                                          "title":  "Participants",
                                          "layer":  1,
                                          "w":  319
                                      }
                                  ],
                         "rows":  1
                     },
                     {
                         "x":  2,
                         "type":  "label",
                         "var":  "",
                         "y":  205,
                         "w":  559,
                         "fmt":  "",
                         "name":  "",
                         "h":  21,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  114,
                         "type":  "edit",
                         "var":  "",
                         "y":  58,
                         "w":  176,
                         "fmt":  "",
                         "name":  "",
                         "h":  11,
                         "color":  "148",
                         "text":  "",
                         "parent":  8
                     },
                     {
                         "x":  309,
                         "type":  "edit",
                         "var":  "",
                         "y":  58,
                         "w":  98,
                         "fmt":  "",
                         "name":  "",
                         "h":  11,
                         "color":  "148",
                         "text":  "",
                         "parent":  8
                     },
                     {
                         "x":  342,
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
                         "x":  122,
                         "type":  "edit",
                         "var":  "",
                         "y":  27,
                         "w":  238,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  410,
                         "type":  "edit",
                         "var":  "",
                         "y":  27,
                         "w":  126,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  5,
                         "type":  "button",
                         "var":  "",
                         "y":  207,
                         "w":  154,
                         "fmt":  "\u0026Quitter",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  12
                     },
                     {
                         "x":  5,
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
    "taskId":  "12.1.1",
    "height":  228
}
-->

<details>
<summary><strong>Champs : 6 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 114,58 | (sans nom) | - | edit |
| 309,58 | (sans nom) | - | edit |
| 342,6 | WWW DD MMM YYYYT | - | edit |
| 122,27 | (sans nom) | - | edit |
| 410,27 | (sans nom) | - | edit |
| 5,6 | 20 | - | edit |

</details>

<details>
<summary><strong>Boutons : 1 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Quitter | 5,207 | Quitte le programme |

</details>

---

#### <a id="ecran-t4"></a>12.2 - Recherche
**Tache** : [12.2](#t4) | **Type** : MDI | **Dimensions** : 523 x 89 DLU
**Bloc** : Consultation | **Titre IDE** : Recherche

<!-- FORM-DATA:
{
    "width":  523,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  149,
                         "type":  "label",
                         "var":  "",
                         "y":  16,
                         "w":  344,
                         "fmt":  "",
                         "name":  "",
                         "h":  33,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  167,
                         "type":  "label",
                         "var":  "",
                         "y":  27,
                         "w":  209,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Entrez le code excursion",
                         "parent":  2
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  64,
                         "w":  518,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  389,
                         "type":  "edit",
                         "var":  "",
                         "y":  26,
                         "w":  86,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  2
                     },
                     {
                         "x":  169,
                         "type":  "button",
                         "var":  "",
                         "y":  66,
                         "w":  154,
                         "fmt":  "\u0026Abandonner",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  7,
                         "type":  "button",
                         "var":  "",
                         "y":  67,
                         "w":  154,
                         "fmt":  "\u0026Ok",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  2,
                         "type":  "image",
                         "var":  "",
                         "y":  5,
                         "w":  127,
                         "fmt":  "",
                         "name":  "",
                         "h":  54,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "12.2",
    "height":  89
}
-->

<details>
<summary><strong>Champs : 1 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 389,26 | (sans nom) | - | edit |

</details>

<details>
<summary><strong>Boutons : 2 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Abandonner | 169,66 | Annule et retour au menu |
| Ok | 7,67 | Valide la saisie et enregistre |

</details>

## 9. NAVIGATION

### 9.1 Enchainement des ecrans

```mermaid
flowchart TD
    START([Entree])
    style START fill:#3fb950
    VF2[12.1 Liste ventes par exc]
    style VF2 fill:#58a6ff
    VF3[12.1.1 Participants]
    style VF3 fill:#58a6ff
    VF4[12.2 Recherche]
    style VF4 fill:#58a6ff
    EXT31[IDE 31 Recuperation du...]
    style EXT31 fill:#3fb950
    EXT17[IDE 17 Get Printer]
    style EXT17 fill:#3fb950
    EXT18[IDE 18 Printer choice]
    style EXT18 fill:#3fb950
    EXT19[IDE 19 Set Listing Number]
    style EXT19 fill:#3fb950
    EXT20[IDE 20 Raz Current Pri...]
    style EXT20 fill:#3fb950
    EXT25[IDE 25 Reçu duplicata new]
    style EXT25 fill:#3fb950
    EXT33[IDE 33 Appel programme]
    style EXT33 fill:#3fb950
    FIN([Sortie])
    style FIN fill:#f85149
    START --> VF2
    VF2 -->|Recuperation donnees| EXT31
    VF2 -->|Impression ticket/document| EXT17
    VF2 -->|Impression ticket/document| EXT18
    VF2 -->|Configuration impression| EXT19
    VF2 -->|Impression ticket/document| EXT20
    VF2 -->|Sous-programme| EXT25
    VF2 -->|Sous-programme| EXT33
    EXT33 --> FIN
```

**Detail par enchainement :**

| Depuis | Action | Vers | Retour |
|--------|--------|------|--------|
| Liste ventes par exc | Recuperation donnees | [Recuperation du titre (IDE 31)](EXF-IDE-31.md) | Retour ecran |
| Liste ventes par exc | Impression ticket/document | [Get Printer (IDE 17)](EXF-IDE-17.md) | Retour ecran |
| Liste ventes par exc | Impression ticket/document | [Printer choice (IDE 18)](EXF-IDE-18.md) | Retour ecran |
| Liste ventes par exc | Configuration impression | [Set Listing Number (IDE 19)](EXF-IDE-19.md) | Retour ecran |
| Liste ventes par exc | Impression ticket/document | [Raz Current Printer (IDE 20)](EXF-IDE-20.md) | Retour ecran |
| Liste ventes par exc | Sous-programme | [Reçu duplicata new (IDE 25)](EXF-IDE-25.md) | Retour ecran |
| Liste ventes par exc | Sous-programme | [Appel programme (IDE 33)](EXF-IDE-33.md) | Retour ecran |

### 9.3 Structure hierarchique (4 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **12.1** | [**Ventes** (12)](#t1) [mockup](#ecran-t1) | MDI | 166x12 | Saisie |
| 12.1.1 | [Liste ventes par exc (12.1)](#t2) [mockup](#ecran-t2) | MDI | 1229x257 | |
| **12.2** | [**Participants** (12.1.1)](#t3) [mockup](#ecran-t3) | MDI | 566x228 | Traitement |
| **12.3** | [**Recherche** (12.2)](#t4) [mockup](#ecran-t4) | MDI | 523x89 | Consultation |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Scroll]
    ENDOK([END OK])

    START --> INIT --> SAISIE
    SAISIE --> ENDOK

    style START fill:#3fb950,color:#000
    style ENDOK fill:#3fb950,color:#000
```

> **Legende**: Vert = START/END OK | Rouge = END KO | Bleu = Decisions
> *Algorigramme auto-genere. Utiliser `/algorigramme` pour une synthese metier detaillee.*

<!-- TAB:Donnees -->

## 10. TABLES

### Tables utilisees (3)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 298 | participants_____par |  | DB | R |   |   | 1 |
| 300 | excursions_______exc |  | DB |   |   | L | 1 |
| 309 | vente____________vep | Donnees de ventes | DB | R |   |   | 1 |

### Colonnes par table (2 / 2 tables avec colonnes identifiees)

<details>
<summary>Table 298 - participants_____par (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | W creation | R | Logical |
| B | v. titre | R | Alpha |

</details>

<details>
<summary>Table 309 - vente____________vep (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | W1 choix action | R | Alpha |
| B | W1 fin tâche | R | Alpha |
| C | v. titre scroll | R | Alpha |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (2)

Variables recues du programme appelant ([   Menu listes (IDE 14)](EXF-IDE-14.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P0 nom village | Alpha | - |
| B | P0 masque montant | Alpha | - |

### 11.2 Variables de travail (3)

Variables internes au programme.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| C | W0 choix action | Alpha | 3x calcul interne |
| D | W0 n° excursion | Numeric | - |
| E | W0 voucher ? | Alpha | - |

## 12. EXPRESSIONS

**4 / 4 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONSTANTE | 1 | 0 |
| CONDITION | 3 | 0 |

### 12.2 Expressions cles par type

#### CONSTANTE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 4 | `104` | - |

#### CONDITION (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 3 | `W0 choix action [C]='I'` | - |
| CONDITION | 2 | `W0 choix action [C]='R'` | - |
| CONDITION | 1 | `W0 choix action [C]='F'` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [   Menu listes (IDE 14)](EXF-IDE-14.md) -> **Liste ventes/Excursion (IDE 12)**

```mermaid
graph LR
    T12[12 Liste ventesExcursion]
    style T12 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC13[13 Menu ventes]
    style CC13 fill:#f59e0b
    CC14[14 Menu listes]
    style CC14 fill:#3fb950
    CC13 --> CC14
    CC1 --> CC13
    CC14 --> T12
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [14](EXF-IDE-14.md) |    Menu listes | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T12[12 Liste ventesExcursion]
    style T12 fill:#58a6ff
    C31[31 Recuperation du titre]
    T12 --> C31
    style C31 fill:#3fb950
    C17[17 Get Printer]
    T12 --> C17
    style C17 fill:#3fb950
    C18[18 Printer choice]
    T12 --> C18
    style C18 fill:#3fb950
    C19[19 Set Listing Number]
    T12 --> C19
    style C19 fill:#3fb950
    C20[20 Raz Current Printer]
    T12 --> C20
    style C20 fill:#3fb950
    C25[25 Reçu duplicata new]
    T12 --> C25
    style C25 fill:#3fb950
    C33[33 Appel programme]
    T12 --> C33
    style C33 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [31](EXF-IDE-31.md) | Recuperation du titre | 3 | Recuperation donnees |
| [17](EXF-IDE-17.md) | Get Printer | 1 | Impression ticket/document |
| [18](EXF-IDE-18.md) | Printer choice | 1 | Impression ticket/document |
| [19](EXF-IDE-19.md) | Set Listing Number | 1 | Configuration impression |
| [20](EXF-IDE-20.md) | Raz Current Printer | 1 | Impression ticket/document |
| [25](EXF-IDE-25.md) | Reçu duplicata new | 1 | Sous-programme |
| [33](EXF-IDE-33.md) | Appel programme | 1 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 86 | Programme compact |
| Expressions | 4 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 7 | Dependances moderees |
| Ecrans visibles | 3 | Quelques ecrans |
| Code desactive | 0% (0 / 86) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Saisie (2 taches: 2 ecrans, 0 traitement)

- **Strategie** : Formulaire React/Blazor avec validation Zod/FluentValidation.
- Reproduire 2 ecrans : Ventes, Liste ventes par exc
- Validation temps reel cote client + serveur

#### Traitement (1 tache: 1 ecran, 0 traitement)

- **Strategie** : 1 composant(s) UI (Razor/React) avec formulaires et validation.
- 7 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Consultation (1 tache: 1 ecran, 0 traitement)

- **Strategie** : Composants de recherche/selection en modales.
- 1 ecran : Recherche

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| [Recuperation du titre (IDE 31)](EXF-IDE-31.md) | Sous-programme | 3x | **CRITIQUE** - Recuperation donnees |
| [Raz Current Printer (IDE 20)](EXF-IDE-20.md) | Sous-programme | 1x | Normale - Impression ticket/document |
| [Reçu duplicata new (IDE 25)](EXF-IDE-25.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Appel programme (IDE 33)](EXF-IDE-33.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Get Printer (IDE 17)](EXF-IDE-17.md) | Sous-programme | 1x | Normale - Impression ticket/document |
| [Printer choice (IDE 18)](EXF-IDE-18.md) | Sous-programme | 1x | Normale - Impression ticket/document |
| [Set Listing Number (IDE 19)](EXF-IDE-19.md) | Sous-programme | 1x | Normale - Configuration impression |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 10:56*
