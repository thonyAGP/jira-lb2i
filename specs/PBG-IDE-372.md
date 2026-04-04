# PBG IDE 372 - Module des Prestations

> **Analyse**: Phases 1-4 2026-02-03 11:29 -> 11:29 (17s) | Assemblage 11:29
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBG |
| IDE Position | 372 |
| Nom Programme | Module des Prestations |
| Fichier source | `Prg_372.xml` |
| Dossier IDE | General |
| Taches | 6 (3 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 3 |
| :warning: Statut | **ORPHELIN_POTENTIEL** |

## 2. DESCRIPTION FONCTIONNELLE

**Module des Prestations** assure la gestion complete de ce processus.

Le flux de traitement s'organise en **2 blocs fonctionnels** :

- **Consultation** (3 taches) : ecrans de recherche, selection et consultation
- **Traitement** (3 taches) : traitements metier divers

**Donnees modifiees** : 1 tables en ecriture (prestations______pre).

**Logique metier** : 2 regles identifiees couvrant valeurs par defaut.

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (3 taches)

- **372** - Module des Sejours **[[ECRAN]](#ecran-t1)**
- **372.1** - Determination Age Bebe
- **372.2** - Test Base

Delegue a : [Recuperation du titre (IDE 317)](PBG-IDE-317.md)

#### Phase 2 : Consultation (3 taches)

- **372.3** - Affichage Clients **[[ECRAN]](#ecran-t4)**
- **372.3.1** - Affichage Hebergement **[[ECRAN]](#ecran-t5)**
- **372.3.2** - Recherche **[[ECRAN]](#ecran-t7)**

Delegue a : [Recuperation du titre (IDE 317)](PBG-IDE-317.md), [Zoom prestation (IDE 353)](PBG-IDE-353.md), [Affichage Erreurs !! (IDE 180)](PBG-IDE-180.md)

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| prestations______pre | **W** (1 usages) | Prestations/services vendus |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (3 taches)

Traitements internes.

---

#### <a id="t1"></a>372 - Module des Sejours [[ECRAN]](#ecran-t1)

**Role** : Traitement : Module des Sejours.
**Ecran** : 1086 x 26 DLU (MDI) | [Voir mockup](#ecran-t1)
**Delegue a** : [Recuperation du titre (IDE 317)](PBG-IDE-317.md)

---

#### <a id="t2"></a>372.1 - Determination Age Bebe

**Role** : Traitement : Determination Age Bebe.
**Variables liees** : P (W0-Age Bebe)
**Delegue a** : [Recuperation du titre (IDE 317)](PBG-IDE-317.md)

---

#### <a id="t3"></a>372.2 - Test Base

**Role** : Verification : Test Base.
**Variables liees** : Q (W0-Base Vide)
**Delegue a** : [Recuperation du titre (IDE 317)](PBG-IDE-317.md)


### 3.2 Consultation (3 taches)

Ecrans de recherche et consultation.

---

#### <a id="t4"></a>372.3 - Affichage Clients [[ECRAN]](#ecran-t4)

**Role** : Reinitialisation : Affichage Clients.
**Ecran** : 1101 x 258 DLU (MDI) | [Voir mockup](#ecran-t4)
**Delegue a** : [Zoom prestation (IDE 353)](PBG-IDE-353.md), [Affichage Erreurs !! (IDE 180)](PBG-IDE-180.md)

---

#### <a id="t5"></a>372.3.1 - Affichage Hebergement [[ECRAN]](#ecran-t5)

**Role** : Reinitialisation : Affichage Hebergement.
**Ecran** : 710 x 64 DLU (Modal) | [Voir mockup](#ecran-t5)
**Delegue a** : [Zoom prestation (IDE 353)](PBG-IDE-353.md), [Affichage Erreurs !! (IDE 180)](PBG-IDE-180.md)

---

#### <a id="t7"></a>372.3.2 - Recherche [[ECRAN]](#ecran-t7)

**Role** : Traitement : Recherche.
**Ecran** : 531 x 109 DLU (MDI) | [Voir mockup](#ecran-t7)
**Variables liees** : N (W0-nom-recherche), O (W0-prenom-recherche)
**Delegue a** : [Zoom prestation (IDE 353)](PBG-IDE-353.md), [Affichage Erreurs !! (IDE 180)](PBG-IDE-180.md)


## 5. REGLES METIER

2 regles identifiees:

### Autres (2 regles)

#### <a id="rm-RM-001"></a>[RM-001] Valeur par defaut si P0-Code Societe [B] est vide

| Element | Detail |
|---------|--------|
| **Condition** | `P0-Code Societe [B]=''` |
| **Si vrai** | 'C' |
| **Si faux** | P0-Code Societe [B]) |
| **Variables** | B (P0-Code Societe) |
| **Expression source** | Expression 5 : `IF (P0-Code Societe [B]='','C',P0-Code Societe [B])` |
| **Exemple** | Si P0-Code Societe [B]='' â†’ 'C'. Sinon â†’ P0-Code Societe [B]) |

#### <a id="rm-RM-002"></a>[RM-002] Valeur par defaut si P0-Code Langue [C] est vide

| Element | Detail |
|---------|--------|
| **Condition** | `P0-Code Langue [C]=''` |
| **Si vrai** | 'F' |
| **Si faux** | P0-Code Langue [C]) |
| **Variables** | C (P0-Code Langue) |
| **Expression source** | Expression 6 : `IF (P0-Code Langue [C]='','F',P0-Code Langue [C])` |
| **Exemple** | Si P0-Code Langue [C]='' â†’ 'F'. Sinon â†’ P0-Code Langue [C]) |

## 6. CONTEXTE

- **Appele par**: (aucun)
- **Appelle**: 3 programmes | **Tables**: 9 (W:1 R:3 L:6) | **Taches**: 6 | **Expressions**: 18

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (3 / 6)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 372.3 | 372.3 | Affichage Clients | MDI | 1101 | 258 | Consultation |
| 2 | 372.3.1 | 372.3.1 | Affichage Hebergement | Modal | 710 | 64 | Consultation |
| 3 | 372.3.2 | 372.3.2 | Recherche | MDI | 531 | 109 | Consultation |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t4"></a>372.3 - Affichage Clients
**Tache** : [372.3](#t4) | **Type** : MDI | **Dimensions** : 1101 x 258 DLU
**Bloc** : Consultation | **Titre IDE** : Affichage Clients

<!-- FORM-DATA:
{
    "width":  1101,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  1,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  1095,
                         "fmt":  "",
                         "name":  "",
                         "h":  22,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  380,
                         "type":  "label",
                         "var":  "",
                         "y":  29,
                         "w":  716,
                         "fmt":  "",
                         "name":  "",
                         "h":  88,
                         "color":  "1",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  409,
                         "type":  "label",
                         "var":  "",
                         "y":  34,
                         "w":  79,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Nom",
                         "parent":  4
                     },
                     {
                         "x":  7,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "110",
                         "w":  371,
                         "y":  28,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  12,
                         "h":  201,
                         "cols":  [
                                      {
                                          "title":  "Nom",
                                          "layer":  1,
                                          "w":  194
                                      },
                                      {
                                          "title":  "Prénom",
                                          "layer":  2,
                                          "w":  146
                                      }
                                  ],
                         "rows":  2
                     },
                     {
                         "x":  409,
                         "type":  "label",
                         "var":  "",
                         "y":  49,
                         "w":  79,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Prénom",
                         "parent":  4
                     },
                     {
                         "x":  409,
                         "type":  "label",
                         "var":  "",
                         "y":  63,
                         "w":  79,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Titre",
                         "parent":  4
                     },
                     {
                         "x":  380,
                         "type":  "label",
                         "var":  "",
                         "y":  80,
                         "w":  716,
                         "fmt":  "",
                         "name":  "",
                         "h":  37,
                         "color":  "178",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  409,
                         "type":  "label",
                         "var":  "",
                         "y":  103,
                         "w":  79,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "178",
                         "text":  "Adhérent",
                         "parent":  14
                     },
                     {
                         "x":  722,
                         "type":  "label",
                         "var":  "",
                         "y":  103,
                         "w":  66,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "178",
                         "text":  "Filiation",
                         "parent":  14
                     },
                     {
                         "x":  380,
                         "type":  "label",
                         "var":  "",
                         "y":  117,
                         "w":  349,
                         "fmt":  "",
                         "name":  "",
                         "h":  33,
                         "color":  "195",
                         "text":  "Aller",
                         "parent":  null
                     },
                     {
                         "x":  739,
                         "type":  "label",
                         "var":  "",
                         "y":  117,
                         "w":  357,
                         "fmt":  "",
                         "name":  "",
                         "h":  33,
                         "color":  "195",
                         "text":  "Retour",
                         "parent":  null
                     },
                     {
                         "x":  380,
                         "type":  "label",
                         "var":  "",
                         "y":  150,
                         "w":  716,
                         "fmt":  "",
                         "name":  "",
                         "h":  76,
                         "color":  "195",
                         "text":  "Prestations",
                         "parent":  null
                     },
                     {
                         "x":  2,
                         "type":  "label",
                         "var":  "",
                         "y":  235,
                         "w":  1096,
                         "fmt":  "",
                         "name":  "",
                         "h":  23,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  14,
                         "type":  "edit",
                         "var":  "",
                         "y":  44,
                         "w":  176,
                         "fmt":  "",
                         "name":  "CLI Nom",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  210,
                         "type":  "edit",
                         "var":  "",
                         "y":  44,
                         "w":  120,
                         "fmt":  "",
                         "name":  "CLI Prenom",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  530,
                         "type":  "edit",
                         "var":  "",
                         "y":  63,
                         "w":  30,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  528,
                         "type":  "edit",
                         "var":  "",
                         "y":  103,
                         "w":  123,
                         "fmt":  "#10P0",
                         "name":  "",
                         "h":  9,
                         "color":  "178",
                         "text":  "",
                         "parent":  14
                     },
                     {
                         "x":  683,
                         "type":  "edit",
                         "var":  "",
                         "y":  103,
                         "w":  22,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "178",
                         "text":  "",
                         "parent":  14
                     },
                     {
                         "x":  795,
                         "type":  "edit",
                         "var":  "",
                         "y":  103,
                         "w":  24,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "178",
                         "text":  "",
                         "parent":  14
                     },
                     {
                         "x":  508,
                         "type":  "edit",
                         "var":  "",
                         "y":  126,
                         "w":  120,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  25
                     },
                     {
                         "x":  649,
                         "type":  "edit",
                         "var":  "",
                         "y":  126,
                         "w":  30,
                         "fmt":  "UUH",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  25
                     },
                     {
                         "x":  508,
                         "type":  "edit",
                         "var":  "",
                         "y":  138,
                         "w":  75,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  25
                     },
                     {
                         "x":  641,
                         "type":  "edit",
                         "var":  "",
                         "y":  138,
                         "w":  75,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  25
                     },
                     {
                         "x":  873,
                         "type":  "edit",
                         "var":  "",
                         "y":  126,
                         "w":  120,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  26
                     },
                     {
                         "x":  996,
                         "type":  "edit",
                         "var":  "",
                         "y":  126,
                         "w":  30,
                         "fmt":  "U2H",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  26
                     },
                     {
                         "x":  870,
                         "type":  "edit",
                         "var":  "",
                         "y":  138,
                         "w":  75,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  26
                     },
                     {
                         "x":  986,
                         "type":  "edit",
                         "var":  "",
                         "y":  138,
                         "w":  75,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  26
                     },
                     {
                         "x":  9,
                         "type":  "button",
                         "var":  "",
                         "y":  238,
                         "w":  154,
                         "fmt":  "\u0026Quitter",
                         "name":  "bouton quitter",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  42
                     },
                     {
                         "x":  935,
                         "type":  "button",
                         "var":  "",
                         "y":  238,
                         "w":  154,
                         "fmt":  "\u0026Recherche",
                         "name":  "bouton recherche",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  42
                     },
                     {
                         "x":  528,
                         "type":  "edit",
                         "var":  "",
                         "y":  86,
                         "w":  23,
                         "fmt":  "",
                         "name":  "V.Code fidelisation",
                         "h":  8,
                         "color":  "164",
                         "text":  "",
                         "parent":  14
                     },
                     {
                         "x":  562,
                         "type":  "edit",
                         "var":  "",
                         "y":  86,
                         "w":  200,
                         "fmt":  "",
                         "name":  "V.Libelle fidelisation",
                         "h":  8,
                         "color":  "164",
                         "text":  "",
                         "parent":  14
                     },
                     {
                         "x":  7,
                         "type":  "edit",
                         "var":  "",
                         "y":  6,
                         "w":  394,
                         "fmt":  "20",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  813,
                         "type":  "edit",
                         "var":  "",
                         "y":  6,
                         "w":  274,
                         "fmt":  "WWW DD MMM YYYYT",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  530,
                         "type":  "edit",
                         "var":  "",
                         "y":  34,
                         "w":  176,
                         "fmt":  "15",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  530,
                         "type":  "edit",
                         "var":  "",
                         "y":  49,
                         "w":  120,
                         "fmt":  "UX9",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  409,
                         "type":  "edit",
                         "var":  "",
                         "y":  85,
                         "w":  78,
                         "fmt":  "UX5",
                         "name":  "",
                         "h":  9,
                         "color":  "140",
                         "text":  "",
                         "parent":  14
                     },
                     {
                         "x":  775,
                         "type":  "edit",
                         "var":  "",
                         "y":  86,
                         "w":  53,
                         "fmt":  "UX3",
                         "name":  "",
                         "h":  8,
                         "color":  "143",
                         "text":  "",
                         "parent":  14
                     },
                     {
                         "x":  853,
                         "type":  "edit",
                         "var":  "",
                         "y":  86,
                         "w":  120,
                         "fmt":  "UX9",
                         "name":  "",
                         "h":  8,
                         "color":  "143",
                         "text":  "",
                         "parent":  14
                     },
                     {
                         "x":  759,
                         "type":  "edit",
                         "var":  "",
                         "y":  125,
                         "w":  98,
                         "fmt":  "10",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  26
                     },
                     {
                         "x":  398,
                         "type":  "edit",
                         "var":  "",
                         "y":  126,
                         "w":  98,
                         "fmt":  "10",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  25
                     },
                     {
                         "x":  400,
                         "type":  "edit",
                         "var":  "",
                         "y":  138,
                         "w":  98,
                         "fmt":  "10",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  25
                     },
                     {
                         "x":  606,
                         "type":  "edit",
                         "var":  "",
                         "y":  138,
                         "w":  22,
                         "fmt":  "1",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  25
                     },
                     {
                         "x":  760,
                         "type":  "edit",
                         "var":  "",
                         "y":  138,
                         "w":  98,
                         "fmt":  "10",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  26
                     },
                     {
                         "x":  956,
                         "type":  "edit",
                         "var":  "",
                         "y":  138,
                         "w":  22,
                         "fmt":  "1",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  26
                     },
                     {
                         "x":  390,
                         "type":  "subform",
                         "var":  "",
                         "y":  158,
                         "w":  691,
                         "fmt":  "",
                         "name":  "Prestations",
                         "h":  65,
                         "color":  "",
                         "text":  "",
                         "parent":  41
                     }
                 ],
    "taskId":  "372.3",
    "height":  258
}
-->

<details>
<summary><strong>Champs : 29 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 14,44 | CLI Nom | - | edit |
| 210,44 | CLI Prenom | - | edit |
| 530,63 | (sans nom) | - | edit |
| 528,103 | #10P0 | - | edit |
| 683,103 | (sans nom) | - | edit |
| 795,103 | (sans nom) | - | edit |
| 508,126 | (sans nom) | - | edit |
| 649,126 | UUH | - | edit |
| 508,138 | (sans nom) | - | edit |
| 641,138 | (sans nom) | - | edit |
| 873,126 | (sans nom) | - | edit |
| 996,126 | U2H | - | edit |
| 870,138 | (sans nom) | - | edit |
| 986,138 | (sans nom) | - | edit |
| 528,86 | V.Code fidelisation | - | edit |
| 562,86 | V.Libelle fidelisation | - | edit |
| 7,6 | 20 | - | edit |
| 813,6 | WWW DD MMM YYYYT | - | edit |
| 530,34 | 15 | - | edit |
| 530,49 | UX9 | - | edit |
| 409,85 | UX5 | - | edit |
| 775,86 | UX3 | - | edit |
| 853,86 | UX9 | - | edit |
| 759,125 | 10 | - | edit |
| 398,126 | 10 | - | edit |
| 400,138 | 10 | - | edit |
| 606,138 | 1 | - | edit |
| 760,138 | 10 | - | edit |
| 956,138 | 1 | - | edit |

</details>

<details>
<summary><strong>Boutons : 2 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Quitter | 9,238 | Quitte le programme |
| Recherche | 935,238 | Ouvre la selection |

</details>

---

#### <a id="ecran-t5"></a>372.3.1 - Affichage Hebergement
**Tache** : [372.3.1](#t5) | **Type** : Modal | **Dimensions** : 710 x 64 DLU
**Bloc** : Consultation | **Titre IDE** : Affichage Hebergement

<!-- FORM-DATA:
{
    "width":  710,
    "vFactor":  8,
    "type":  "Modal",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "110",
                         "w":  704,
                         "y":  1,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  12,
                         "h":  62,
                         "cols":  [
                                      {
                                          "title":  "Code Prestation",
                                          "layer":  1,
                                          "w":  151
                                      },
                                      {
                                          "title":  "Libellé",
                                          "layer":  2,
                                          "w":  247
                                      },
                                      {
                                          "title":  "Date début",
                                          "layer":  3,
                                          "w":  143
                                      },
                                      {
                                          "title":  "Date fin",
                                          "layer":  4,
                                          "w":  123
                                      }
                                  ],
                         "rows":  4
                     },
                     {
                         "x":  10,
                         "type":  "edit",
                         "var":  "",
                         "y":  15,
                         "w":  82,
                         "fmt":  "",
                         "name":  "PRE Code Circuit",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  160,
                         "type":  "edit",
                         "var":  "",
                         "y":  15,
                         "w":  232,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  120,
                         "type":  "button",
                         "var":  "",
                         "y":  15,
                         "w":  27,
                         "fmt":  "...",
                         "name":  "bouton prestation",
                         "h":  11,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  410,
                         "type":  "edit",
                         "var":  "",
                         "y":  15,
                         "w":  120,
                         "fmt":  "",
                         "name":  "PRE Date Debut",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  547,
                         "type":  "edit",
                         "var":  "",
                         "y":  15,
                         "w":  120,
                         "fmt":  "",
                         "name":  "PRE Date Fin",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     }
                 ],
    "taskId":  "372.3.1",
    "height":  64
}
-->

<details>
<summary><strong>Champs : 4 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 10,15 | PRE Code Circuit | - | edit |
| 160,15 | (sans nom) | - | edit |
| 410,15 | PRE Date Debut | - | edit |
| 547,15 | PRE Date Fin | - | edit |

</details>

<details>
<summary><strong>Boutons : 1 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| ... | 120,15 | Bouton fonctionnel |

</details>

---

#### <a id="ecran-t7"></a>372.3.2 - Recherche
**Tache** : [372.3.2](#t7) | **Type** : MDI | **Dimensions** : 531 x 109 DLU
**Bloc** : Consultation | **Titre IDE** : Recherche

<!-- FORM-DATA:
{
    "width":  531,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  1,
                         "w":  530,
                         "fmt":  "",
                         "name":  "",
                         "h":  19,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  170,
                         "type":  "label",
                         "var":  "",
                         "y":  34,
                         "w":  340,
                         "fmt":  "",
                         "name":  "",
                         "h":  37,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  173,
                         "type":  "label",
                         "var":  "",
                         "y":  35,
                         "w":  334,
                         "fmt":  "",
                         "name":  "",
                         "h":  35,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  190,
                         "type":  "label",
                         "var":  "",
                         "y":  49,
                         "w":  197,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Entrer les première lettres",
                         "parent":  6
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  85,
                         "w":  531,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  391,
                         "type":  "edit",
                         "var":  "",
                         "y":  48,
                         "w":  93,
                         "fmt":  "U7",
                         "name":  "",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  6
                     },
                     {
                         "x":  262,
                         "type":  "edit",
                         "var":  "",
                         "y":  6,
                         "w":  262,
                         "fmt":  "WWW DD MMM YYYYT",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  4,
                         "type":  "image",
                         "var":  "",
                         "y":  23,
                         "w":  154,
                         "fmt":  "",
                         "name":  "",
                         "h":  59,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  7,
                         "type":  "button",
                         "var":  "",
                         "y":  88,
                         "w":  154,
                         "fmt":  "\u0026Valider",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  368,
                         "type":  "button",
                         "var":  "",
                         "y":  88,
                         "w":  154,
                         "fmt":  "\u0026Abandonner",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
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
                         "parent":  null
                     }
                 ],
    "taskId":  "372.3.2",
    "height":  109
}
-->

<details>
<summary><strong>Champs : 3 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 391,48 | U7 | - | edit |
| 262,6 | WWW DD MMM YYYYT | - | edit |
| 5,6 | 20 | - | edit |

</details>

<details>
<summary><strong>Boutons : 2 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Valider | 7,88 | Valide la saisie et enregistre |
| Abandonner | 368,88 | Annule et retour au menu |

</details>

## 9. NAVIGATION

### 9.1 Enchainement des ecrans

```mermaid
flowchart TD
    START([Entree])
    style START fill:#3fb950
    VF4[372.3 Affichage Clients]
    style VF4 fill:#58a6ff
    VF5[372.3.1 Affichage Hebergement]
    style VF5 fill:#58a6ff
    VF7[372.3.2 Recherche]
    style VF7 fill:#58a6ff
    EXT317[IDE 317 Recuperation d...]
    style EXT317 fill:#3fb950
    EXT353[IDE 353 Zoom prestation]
    style EXT353 fill:#3fb950
    EXT180[IDE 180 Affichage Erreurs]
    style EXT180 fill:#3fb950
    FIN([Sortie])
    style FIN fill:#f85149
    START --> VF4
    VF4 -->|Recuperation donnees| EXT317
    VF4 -->|Selection/consultation| EXT353
    VF4 -->|Affichage donnees| EXT180
    EXT180 --> FIN
```

**Detail par enchainement :**

| Depuis | Action | Vers | Retour |
|--------|--------|------|--------|
| Affichage Clients | Recuperation donnees | [Recuperation du titre (IDE 317)](PBG-IDE-317.md) | Retour ecran |
| Affichage Clients | Selection/consultation | [Zoom prestation (IDE 353)](PBG-IDE-353.md) | Retour ecran |
| Affichage Clients | Affichage donnees | [Affichage Erreurs !! (IDE 180)](PBG-IDE-180.md) | Retour ecran |

### 9.3 Structure hierarchique (6 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **372.1** | [**Module des Sejours** (372)](#t1) [mockup](#ecran-t1) | MDI | 1086x26 | Traitement |
| 372.1.1 | [Determination Age Bebe (372.1)](#t2) | MDI | - | |
| 372.1.2 | [Test Base (372.2)](#t3) | MDI | - | |
| **372.2** | [**Affichage Clients** (372.3)](#t4) [mockup](#ecran-t4) | MDI | 1101x258 | Consultation |
| 372.2.1 | [Affichage Hebergement (372.3.1)](#t5) [mockup](#ecran-t5) | Modal | 710x64 | |
| 372.2.2 | [Recherche (372.3.2)](#t7) [mockup](#ecran-t7) | MDI | 531x109 | |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Affichage Clients]
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

### Tables utilisees (9)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 31 | gm-complet_______gmc |  | DB |   |   | L | 1 |
| 33 | prestations______pre | Prestations/services vendus | DB |   | **W** |   | 1 |
| 34 | hebergement______heb | Hebergement (chambres) | DB | R |   |   | 1 |
| 36 | client_gm |  | DB | R |   | L | 2 |
| 113 | tables_village |  | DB | R |   |   | 1 |
| 135 | libelle_prestation | Prestations/services vendus | DB |   |   | L | 1 |
| 358 | import_mod |  | DB |   |   | L | 1 |
| 738 | pv_selling_unit |  | DB |   |   | L | 1 |
| 846 | stat_lieu_vente | Statistiques point de vente | TMP |   |   | L | 1 |

### Colonnes par table (5 / 4 tables avec colonnes identifiees)

<details>
<summary>Table 33 - prestations______pre (**W**) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P.Num compte | W | Numeric |
| B | P.Filiation | W | Numeric |
| C | bouton prestation | W | Alpha |

</details>

<details>
<summary>Table 34 - hebergement______heb (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | W1-Fin de Tache | R | Alpha |
| B | bouton quitter | R | Alpha |
| C | bouton recherche | R | Alpha |
| D | W1-Titre | R | Alpha |
| E | V.Code fidelisation | R | Alpha |
| F | V.Libelle fidelisation | R | Alpha |
| G | V.Couleur fidelisation | R | Numeric |
| H | Column Name | R | Unicode |

</details>

<details>
<summary>Table 36 - client_gm (R/L) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | W1-Fin de Tache | R | Alpha |
| B | W1-Code Retour | R | Numeric |

</details>

<details>
<summary>Table 113 - tables_village (R) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Autres (24)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P0-Choix Programme | Alpha | - |
| B | P0-Code Societe | Alpha | 1x refs |
| C | P0-Code Langue | Alpha | 1x refs |
| D | P0-Societe | Alpha | - |
| E | P0-Numero Compte | Numeric | - |
| F | P0-Filiation Compte | Numeric | - |
| G | P0-Nom Adherent | Alpha | - |
| H | P0-Prenom Adherent | Alpha | - |
| I | P0-Nom Personne | Alpha | - |
| J | P0-Prenom Personne | Alpha | - |
| K | P0-Nom Logement | Alpha | - |
| L | W0-Fin de Tache | Alpha | 1x refs |
| M | W0-Valeur-tri | Numeric | 1x refs |
| N | W0-nom-recherche | Alpha | - |
| O | W0-prenom-recherche | Alpha | - |
| P | W0-Age Bebe | Numeric | - |
| Q | W0-Base Vide | Alpha | 3x refs |
| R | W0-Code B004 | Alpha | - |
| S | W0-Code B020 | Alpha | - |
| T | W0-Code B023 | Alpha | - |
| U | W0-Code B024 | Alpha | - |
| V | W0-Code B026 | Alpha | - |
| W | W0-Code B027 | Alpha | - |
| X | W0-Code B044 | Alpha | - |

<details>
<summary>Toutes les 24 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| Autre | **A** | P0-Choix Programme | Alpha |
| Autre | **B** | P0-Code Societe | Alpha |
| Autre | **C** | P0-Code Langue | Alpha |
| Autre | **D** | P0-Societe | Alpha |
| Autre | **E** | P0-Numero Compte | Numeric |
| Autre | **F** | P0-Filiation Compte | Numeric |
| Autre | **G** | P0-Nom Adherent | Alpha |
| Autre | **H** | P0-Prenom Adherent | Alpha |
| Autre | **I** | P0-Nom Personne | Alpha |
| Autre | **J** | P0-Prenom Personne | Alpha |
| Autre | **K** | P0-Nom Logement | Alpha |
| Autre | **L** | W0-Fin de Tache | Alpha |
| Autre | **M** | W0-Valeur-tri | Numeric |
| Autre | **N** | W0-nom-recherche | Alpha |
| Autre | **O** | W0-prenom-recherche | Alpha |
| Autre | **P** | W0-Age Bebe | Numeric |
| Autre | **Q** | W0-Base Vide | Alpha |
| Autre | **R** | W0-Code B004 | Alpha |
| Autre | **S** | W0-Code B020 | Alpha |
| Autre | **T** | W0-Code B023 | Alpha |
| Autre | **U** | W0-Code B024 | Alpha |
| Autre | **V** | W0-Code B026 | Alpha |
| Autre | **W** | W0-Code B027 | Alpha |
| Autre | **X** | W0-Code B044 | Alpha |

</details>

## 12. EXPRESSIONS

**18 / 18 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONDITION | 7 | 2 |
| CONSTANTE | 9 | 0 |
| OTHER | 2 | 0 |

### 12.2 Expressions cles par type

#### CONDITION (7 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 6 | `IF (P0-Code Langue [C]='','F',P0-Code Langue [C])` | [RM-002](#rm-RM-002) |
| CONDITION | 5 | `IF (P0-Code Societe [B]='','C',P0-Code Societe [B])` | [RM-001](#rm-RM-001) |
| CONDITION | 8 | `W0-Base Vide [Q]='O'` | - |
| CONDITION | 9 | `W0-Base Vide [Q]='N'` | - |
| CONDITION | 7 | `W0-Base Vide [Q]<>'O' OR W0-Base Vide [Q]<>'N'` | - |
| ... | | *+2 autres* | |

#### CONSTANTE (9 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 14 | `'B026'` | - |
| CONSTANTE | 13 | `'B024'` | - |
| CONSTANTE | 16 | `'B044'` | - |
| CONSTANTE | 15 | `'B027'` | - |
| CONSTANTE | 12 | `'B023'` | - |
| ... | | *+4 autres* | |

#### OTHER (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 18 | `GetParam ('PRENOM')` | - |
| OTHER | 17 | `GetParam ('NOM')` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

**Chemin**: (pas de callers directs)

```mermaid
graph LR
    T372[372 Module des Prestat...]
    style T372 fill:#58a6ff
    NONE[Aucun caller]
    NONE -.-> T372
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| - | (aucun) | - |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T372[372 Module des Prestat...]
    style T372 fill:#58a6ff
    C317[317 Recuperation du titre]
    T372 --> C317
    style C317 fill:#3fb950
    C353[353 Zoom prestation]
    T372 --> C353
    style C353 fill:#3fb950
    C180[180 Affichage Erreurs]
    T372 --> C180
    style C180 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [317](PBG-IDE-317.md) | Recuperation du titre | 2 | Recuperation donnees |
| [353](PBG-IDE-353.md) | Zoom prestation | 2 | Selection/consultation |
| [180](PBG-IDE-180.md) | Affichage Erreurs !! | 1 | Affichage donnees |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 215 | Taille moyenne |
| Expressions | 18 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 3 | Peu de dependances |
| Ecrans visibles | 3 | Quelques ecrans |
| Code desactive | 0% (0 / 215) | Code sain |
| Regles metier | 2 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (3 taches: 1 ecran, 2 traitements)

- **Strategie** : Orchestrateur avec 1 ecrans (Razor/React) et 2 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 3 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Consultation (3 taches: 3 ecrans, 0 traitement)

- **Strategie** : Composants de recherche/selection en modales.
- 3 ecrans : Affichage Clients, Affichage Hebergement, Recherche

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| prestations______pre | Table WRITE (Database) | 1x | Schema + repository |
| [Zoom prestation (IDE 353)](PBG-IDE-353.md) | Sous-programme | 2x | Haute - Selection/consultation |
| [Recuperation du titre (IDE 317)](PBG-IDE-317.md) | Sous-programme | 2x | Haute - Recuperation donnees |
| [Affichage Erreurs !! (IDE 180)](PBG-IDE-180.md) | Sous-programme | 1x | Normale - Affichage donnees |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 11:29*
