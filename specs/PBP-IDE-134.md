# PBP IDE 134 - Visu service GO

> **Analyse**: Phases 1-4 2026-02-03 15:26 -> 15:26 (20s) | Assemblage 15:26
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBP |
| IDE Position | 134 |
| Nom Programme | Visu service GO |
| Fichier source | `Prg_134.xml` |
| Dossier IDE | Gestion |
| Taches | 4 (4 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 2 |

## 2. DESCRIPTION FONCTIONNELLE

**Visu service GO** assure la gestion complete de ce processus, accessible depuis [Service GO (IDE 133)](PBP-IDE-133.md).

Le flux de traitement s'organise en **2 blocs fonctionnels** :

- **Traitement** (3 taches) : traitements metier divers
- **Consultation** (1 tache) : ecrans de recherche, selection et consultation

**Logique metier** : 1 regles identifiees couvrant conditions metier.

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (3 taches)

- **134** - Visu service GO **[[ECRAN]](#ecran-t1)**
- **134.1.1** - consultation hebergement **[[ECRAN]](#ecran-t3)**
- **134.1.2** - consult prestations **[[ECRAN]](#ecran-t4)**

Delegue a : [Recuperation du titre (IDE 389)](PBP-IDE-389.md)

#### Phase 2 : Consultation (1 tache)

- **134.1** - Affichage **[[ECRAN]](#ecran-t2)**

Delegue a : [Recuperation du titre (IDE 389)](PBP-IDE-389.md)

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (3 taches)

Traitements internes.

---

#### <a id="t1"></a>134 - Visu service GO [[ECRAN]](#ecran-t1)

**Role** : Traitement : Visu service GO.
**Ecran** : 1254 x 224 DLU (MDI) | [Voir mockup](#ecran-t1)
**Delegue a** : [Recuperation du titre (IDE 389)](PBP-IDE-389.md)

---

#### <a id="t3"></a>134.1.1 - consultation hebergement [[ECRAN]](#ecran-t3)

**Role** : Consultation/chargement : consultation hebergement.
**Ecran** : 773 x 78 DLU (Modal) | [Voir mockup](#ecran-t3)
**Variables liees** : A (>Date Consultation)
**Delegue a** : [Recuperation du titre (IDE 389)](PBP-IDE-389.md)

---

#### <a id="t4"></a>134.1.2 - consult prestations [[ECRAN]](#ecran-t4)

**Role** : Traitement : consult prestations.
**Ecran** : 759 x 38 DLU (Modal) | [Voir mockup](#ecran-t4)
**Variables liees** : A (>Date Consultation)
**Delegue a** : [Recuperation du titre (IDE 389)](PBP-IDE-389.md)


### 3.2 Consultation (1 tache)

Ecrans de recherche et consultation.

---

#### <a id="t2"></a>134.1 - Affichage [[ECRAN]](#ecran-t2)

**Role** : Reinitialisation : Affichage.
**Ecran** : 779 x 266 DLU (MDI) | [Voir mockup](#ecran-t2)


## 5. REGLES METIER

1 regles identifiees:

### Autres (1 regles)

#### <a id="rm-RM-001"></a>[RM-001] Si VG117 alors [BL] sinon [Z])

| Element | Detail |
|---------|--------|
| **Condition** | `VG117` |
| **Si vrai** | [BL] |
| **Si faux** | [Z]) |
| **Expression source** | Expression 15 : `IF(VG117,[BL],[Z])` |
| **Exemple** | Si VG117 â†’ [BL]. Sinon â†’ [Z]) |

## 6. CONTEXTE

- **Appele par**: [Service GO (IDE 133)](PBP-IDE-133.md)
- **Appelle**: 2 programmes | **Tables**: 7 (W:0 R:4 L:3) | **Taches**: 4 | **Expressions**: 17

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (4 / 4)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 134 | 134 | Visu service GO | MDI | 1254 | 224 | Traitement |
| 2 | 134.1 | 134.1 | Affichage | MDI | 779 | 266 | Consultation |
| 3 | 134.1.1 | 134.1.1 | consultation hebergement | Modal | 773 | 78 | Traitement |
| 4 | 134.1.2 | 134.1.2 | consult prestations | Modal | 759 | 38 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>134 - Visu service GO
**Tache** : [134](#t1) | **Type** : MDI | **Dimensions** : 1254 x 224 DLU
**Bloc** : Traitement | **Titre IDE** : Visu service GO

<!-- FORM-DATA:
{
    "width":  1254,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  1249,
                         "fmt":  "",
                         "name":  "",
                         "h":  19,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  1074,
                         "type":  "label",
                         "var":  "",
                         "y":  24,
                         "w":  175,
                         "fmt":  "",
                         "name":  "",
                         "h":  168,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  1,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "110",
                         "w":  1069,
                         "y":  29,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  14,
                         "h":  127,
                         "cols":  [
                                      {
                                          "title":  "Nom",
                                          "layer":  1,
                                          "w":  194
                                      },
                                      {
                                          "title":  "Prénom",
                                          "layer":  2,
                                          "w":  228
                                      },
                                      {
                                          "title":  "Sexe",
                                          "layer":  3,
                                          "w":  60
                                      },
                                      {
                                          "title":  "Qualité",
                                          "layer":  4,
                                          "w":  114
                                      },
                                      {
                                          "title":  "Age",
                                          "layer":  5,
                                          "w":  54
                                      },
                                      {
                                          "title":  "Date naissance",
                                          "layer":  6,
                                          "w":  139
                                      },
                                      {
                                          "title":  "Logement",
                                          "layer":  7,
                                          "w":  120
                                      },
                                      {
                                          "title":  "Tel",
                                          "layer":  8,
                                          "w":  74
                                      },
                                      {
                                          "title":  "Pays",
                                          "layer":  9,
                                          "w":  52
                                      }
                                  ],
                         "rows":  9
                     },
                     {
                         "x":  5,
                         "type":  "label",
                         "var":  "",
                         "y":  159,
                         "w":  640,
                         "fmt":  "",
                         "name":  "",
                         "h":  33,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  642,
                         "type":  "label",
                         "var":  "",
                         "y":  159,
                         "w":  427,
                         "fmt":  "",
                         "name":  "",
                         "h":  33,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  24,
                         "type":  "label",
                         "var":  "",
                         "y":  165,
                         "w":  291,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Service",
                         "parent":  27
                     },
                     {
                         "x":  333,
                         "type":  "label",
                         "var":  "",
                         "y":  165,
                         "w":  291,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Fonction",
                         "parent":  27
                     },
                     {
                         "x":  665,
                         "type":  "label",
                         "var":  "",
                         "y":  165,
                         "w":  154,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Arrivée",
                         "parent":  28
                     },
                     {
                         "x":  854,
                         "type":  "label",
                         "var":  "",
                         "y":  165,
                         "w":  157,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Départ",
                         "parent":  28
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  197,
                         "w":  1249,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  6,
                         "type":  "edit",
                         "var":  "",
                         "y":  43,
                         "w":  182,
                         "fmt":  "",
                         "name":  "TMP Nom",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  202,
                         "type":  "edit",
                         "var":  "",
                         "y":  43,
                         "w":  216,
                         "fmt":  "",
                         "name":  "TMP Prenom",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  429,
                         "type":  "edit",
                         "var":  "",
                         "y":  43,
                         "w":  37,
                         "fmt":  "",
                         "name":  "TMP Sexe",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  491,
                         "type":  "edit",
                         "var":  "",
                         "y":  43,
                         "w":  104,
                         "fmt":  "",
                         "name":  "TMP Qualite",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  603,
                         "type":  "edit",
                         "var":  "",
                         "y":  43,
                         "w":  37,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  659,
                         "type":  "edit",
                         "var":  "",
                         "y":  43,
                         "w":  120,
                         "fmt":  "DD/MM/YYYYZ",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  795,
                         "type":  "edit",
                         "var":  "",
                         "y":  43,
                         "w":  82,
                         "fmt":  "",
                         "name":  "TMP Logement",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  915,
                         "type":  "edit",
                         "var":  "",
                         "y":  43,
                         "w":  59,
                         "fmt":  "",
                         "name":  "TMP Tel Interieur",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  990,
                         "type":  "edit",
                         "var":  "",
                         "y":  43,
                         "w":  37,
                         "fmt":  "",
                         "name":  "TMP Pays",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  654,
                         "type":  "edit",
                         "var":  "",
                         "y":  176,
                         "w":  123,
                         "fmt":  "DD/MM/YYYYZ",
                         "name":  "TMP Date Arrivee",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  28
                     },
                     {
                         "x":  783,
                         "type":  "edit",
                         "var":  "",
                         "y":  176,
                         "w":  42,
                         "fmt":  "",
                         "name":  "TMP Heure Arrivee",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  28
                     },
                     {
                         "x":  844,
                         "type":  "edit",
                         "var":  "",
                         "y":  176,
                         "w":  123,
                         "fmt":  "DD/MM/YYYYZ",
                         "name":  "TMP Date Depart",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  28
                     },
                     {
                         "x":  976,
                         "type":  "edit",
                         "var":  "",
                         "y":  176,
                         "w":  42,
                         "fmt":  "",
                         "name":  "TMP Heure Depart",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  28
                     },
                     {
                         "x":  24,
                         "type":  "edit",
                         "var":  "",
                         "y":  175,
                         "w":  291,
                         "fmt":  "100",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  27
                     },
                     {
                         "x":  333,
                         "type":  "edit",
                         "var":  "",
                         "y":  176,
                         "w":  291,
                         "fmt":  "100",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  27
                     },
                     {
                         "x":  1086,
                         "type":  "button",
                         "var":  "",
                         "y":  124,
                         "w":  154,
                         "fmt":  "\u0026Voir",
                         "name":  "b_Voir",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  6
                     },
                     {
                         "x":  1086,
                         "type":  "button",
                         "var":  "",
                         "y":  157,
                         "w":  154,
                         "fmt":  "\u0026Impression",
                         "name":  "b_Imprimer",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  6
                     },
                     {
                         "x":  7,
                         "type":  "button",
                         "var":  "",
                         "y":  200,
                         "w":  154,
                         "fmt":  "\u0026Quitter",
                         "name":  "b_Quitter",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  39
                     },
                     {
                         "x":  5,
                         "type":  "edit",
                         "var":  "",
                         "y":  2,
                         "w":  395,
                         "fmt":  "30",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  443,
                         "type":  "edit",
                         "var":  "",
                         "y":  6,
                         "w":  344,
                         "fmt":  "30",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  940,
                         "type":  "edit",
                         "var":  "",
                         "y":  6,
                         "w":  299,
                         "fmt":  "WWW DD MMM YYYYT",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  5,
                         "type":  "edit",
                         "var":  "",
                         "y":  10,
                         "w":  267,
                         "fmt":  "20",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  1084,
                         "type":  "image",
                         "var":  "",
                         "y":  50,
                         "w":  159,
                         "fmt":  "",
                         "name":  "",
                         "h":  53,
                         "color":  "",
                         "text":  "",
                         "parent":  6
                     }
                 ],
    "taskId":  "134",
    "height":  224
}
-->

<details>
<summary><strong>Champs : 19 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 6,43 | TMP Nom | - | edit |
| 202,43 | TMP Prenom | - | edit |
| 429,43 | TMP Sexe | - | edit |
| 491,43 | TMP Qualite | - | edit |
| 603,43 | (sans nom) | - | edit |
| 659,43 | DD/MM/YYYYZ | - | edit |
| 795,43 | TMP Logement | - | edit |
| 915,43 | TMP Tel Interieur | - | edit |
| 990,43 | TMP Pays | - | edit |
| 654,176 | TMP Date Arrivee | - | edit |
| 783,176 | TMP Heure Arrivee | - | edit |
| 844,176 | TMP Date Depart | - | edit |
| 976,176 | TMP Heure Depart | - | edit |
| 24,175 | 100 | - | edit |
| 333,176 | 100 | - | edit |
| 5,2 | 30 | - | edit |
| 443,6 | 30 | - | edit |
| 940,6 | WWW DD MMM YYYYT | - | edit |
| 5,10 | 20 | - | edit |

</details>

<details>
<summary><strong>Boutons : 3 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Voir | 1086,124 | Bouton fonctionnel |
| Impression | 1086,157 | Bouton fonctionnel |
| Quitter | 7,200 | Quitte le programme |

</details>

---

#### <a id="ecran-t2"></a>134.1 - Affichage
**Tache** : [134.1](#t2) | **Type** : MDI | **Dimensions** : 779 x 266 DLU
**Bloc** : Consultation | **Titre IDE** : Affichage

<!-- FORM-DATA:
{
    "width":  779,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  10,
                         "type":  "label",
                         "var":  "",
                         "y":  16,
                         "w":  757,
                         "fmt":  "",
                         "name":  "",
                         "h":  97,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  21,
                         "type":  "label",
                         "var":  "",
                         "y":  25,
                         "w":  72,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "N° client",
                         "parent":  3
                     },
                     {
                         "x":  13,
                         "type":  "line",
                         "var":  "",
                         "y":  36,
                         "w":  752,
                         "fmt":  "",
                         "name":  "",
                         "h":  0,
                         "color":  "",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  21,
                         "type":  "label",
                         "var":  "",
                         "y":  41,
                         "w":  88,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Naissance",
                         "parent":  3
                     },
                     {
                         "x":  13,
                         "type":  "line",
                         "var":  "",
                         "y":  53,
                         "w":  752,
                         "fmt":  "",
                         "name":  "",
                         "h":  0,
                         "color":  "",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  21,
                         "type":  "label",
                         "var":  "",
                         "y":  59,
                         "w":  64,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Identité",
                         "parent":  3
                     },
                     {
                         "x":  13,
                         "type":  "line",
                         "var":  "",
                         "y":  71,
                         "w":  752,
                         "fmt":  "",
                         "name":  "",
                         "h":  0,
                         "color":  "",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  21,
                         "type":  "label",
                         "var":  "",
                         "y":  77,
                         "w":  69,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "Adresse",
                         "parent":  3
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  240,
                         "w":  771,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  69,
                         "type":  "edit",
                         "var":  "",
                         "y":  4,
                         "w":  37,
                         "fmt":  "",
                         "name":  "GMC Titre",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  114,
                         "type":  "edit",
                         "var":  "",
                         "y":  24,
                         "w":  26,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  149,
                         "type":  "edit",
                         "var":  "",
                         "y":  24,
                         "w":  123,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  286,
                         "type":  "edit",
                         "var":  "",
                         "y":  24,
                         "w":  26,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  328,
                         "type":  "edit",
                         "var":  "",
                         "y":  24,
                         "w":  48,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  117,
                         "type":  "edit",
                         "var":  "",
                         "y":  41,
                         "w":  120,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  246,
                         "type":  "edit",
                         "var":  "",
                         "y":  41,
                         "w":  403,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  661,
                         "type":  "edit",
                         "var":  "",
                         "y":  41,
                         "w":  45,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  117,
                         "type":  "edit",
                         "var":  "",
                         "y":  59,
                         "w":  22,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  144,
                         "type":  "edit",
                         "var":  "",
                         "y":  59,
                         "w":  347,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  496,
                         "type":  "edit",
                         "var":  "",
                         "y":  59,
                         "w":  123,
                         "fmt":  "DD/MM/YYYYZ",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  629,
                         "type":  "edit",
                         "var":  "",
                         "y":  59,
                         "w":  123,
                         "fmt":  "DD/MM/YYYYZ",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  117,
                         "type":  "edit",
                         "var":  "",
                         "y":  77,
                         "w":  123,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  250,
                         "type":  "edit",
                         "var":  "",
                         "y":  77,
                         "w":  347,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  117,
                         "type":  "edit",
                         "var":  "",
                         "y":  88,
                         "w":  403,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  117,
                         "type":  "edit",
                         "var":  "",
                         "y":  99,
                         "w":  123,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  250,
                         "type":  "edit",
                         "var":  "",
                         "y":  99,
                         "w":  347,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  106,
                         "type":  "edit",
                         "var":  "",
                         "y":  4,
                         "w":  597,
                         "fmt":  "50",
                         "name":  "",
                         "h":  10,
                         "color":  "7",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  8,
                         "type":  "button",
                         "var":  "",
                         "y":  243,
                         "w":  154,
                         "fmt":  "\u0026Quitter",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  27
                     },
                     {
                         "x":  0,
                         "type":  "subform",
                         "var":  "",
                         "y":  117,
                         "w":  778,
                         "fmt":  "",
                         "name":  "consultation hebergement",
                         "h":  82,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  0,
                         "type":  "subform",
                         "var":  "",
                         "y":  199,
                         "w":  779,
                         "fmt":  "",
                         "name":  "consult prestations",
                         "h":  41,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "134.1",
    "height":  266
}
-->

<details>
<summary><strong>Champs : 18 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 69,4 | GMC Titre | - | edit |
| 114,24 | (sans nom) | - | edit |
| 149,24 | (sans nom) | - | edit |
| 286,24 | (sans nom) | - | edit |
| 328,24 | (sans nom) | - | edit |
| 117,41 | (sans nom) | - | edit |
| 246,41 | (sans nom) | - | edit |
| 661,41 | (sans nom) | - | edit |
| 117,59 | (sans nom) | - | edit |
| 144,59 | (sans nom) | - | edit |
| 496,59 | DD/MM/YYYYZ | - | edit |
| 629,59 | DD/MM/YYYYZ | - | edit |
| 117,77 | (sans nom) | - | edit |
| 250,77 | (sans nom) | - | edit |
| 117,88 | (sans nom) | - | edit |
| 117,99 | (sans nom) | - | edit |
| 250,99 | (sans nom) | - | edit |
| 106,4 | 50 | - | edit |

</details>

<details>
<summary><strong>Boutons : 1 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Quitter | 8,243 | Quitte le programme |

</details>

---

#### <a id="ecran-t3"></a>134.1.1 - consultation hebergement
**Tache** : [134.1.1](#t3) | **Type** : Modal | **Dimensions** : 773 x 78 DLU
**Bloc** : Traitement | **Titre IDE** : consultation hebergement

<!-- FORM-DATA:
{
    "width":  773,
    "vFactor":  8,
    "type":  "Modal",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  8,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "110",
                         "w":  765,
                         "y":  1,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  12,
                         "h":  72,
                         "cols":  [
                                      {
                                          "title":  "Type",
                                          "layer":  1,
                                          "w":  158
                                      },
                                      {
                                          "title":  "Début",
                                          "layer":  2,
                                          "w":  165
                                      },
                                      {
                                          "title":  "Fin",
                                          "layer":  3,
                                          "w":  163
                                      },
                                      {
                                          "title":  "Détail",
                                          "layer":  4,
                                          "w":  244
                                      }
                                  ],
                         "rows":  4
                     },
                     {
                         "x":  173,
                         "type":  "edit",
                         "var":  "",
                         "y":  15,
                         "w":  120,
                         "fmt":  "DD/MM/YYYYZ",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  299,
                         "type":  "edit",
                         "var":  "",
                         "y":  15,
                         "w":  30,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  338,
                         "type":  "edit",
                         "var":  "",
                         "y":  15,
                         "w":  120,
                         "fmt":  "DD/MM/YYYYZ",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  461,
                         "type":  "edit",
                         "var":  "",
                         "y":  15,
                         "w":  30,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  501,
                         "type":  "edit",
                         "var":  "",
                         "y":  15,
                         "w":  232,
                         "fmt":  "20",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  14,
                         "type":  "edit",
                         "var":  "",
                         "y":  15,
                         "w":  142,
                         "fmt":  "12",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     }
                 ],
    "taskId":  "134.1.1",
    "height":  78
}
-->

<details>
<summary><strong>Champs : 6 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 173,15 | DD/MM/YYYYZ | - | edit |
| 299,15 | (sans nom) | - | edit |
| 338,15 | DD/MM/YYYYZ | - | edit |
| 461,15 | (sans nom) | - | edit |
| 501,15 | 20 | - | edit |
| 14,15 | 12 | - | edit |

</details>

---

#### <a id="ecran-t4"></a>134.1.2 - consult prestations
**Tache** : [134.1.2](#t4) | **Type** : Modal | **Dimensions** : 759 x 38 DLU
**Bloc** : Traitement | **Titre IDE** : consult prestations

<!-- FORM-DATA:
{
    "width":  759,
    "vFactor":  8,
    "type":  "Modal",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  163,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "110",
                         "w":  383,
                         "y":  0,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  10,
                         "h":  32,
                         "cols":  [
                                      {
                                          "title":  "Code circuit",
                                          "layer":  1,
                                          "w":  113
                                      },
                                      {
                                          "title":  "Libellé",
                                          "layer":  2,
                                          "w":  243
                                      }
                                  ],
                         "rows":  2
                     },
                     {
                         "x":  169,
                         "type":  "edit",
                         "var":  "",
                         "y":  14,
                         "w":  75,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  282,
                         "type":  "edit",
                         "var":  "",
                         "y":  14,
                         "w":  232,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     }
                 ],
    "taskId":  "134.1.2",
    "height":  38
}
-->

<details>
<summary><strong>Champs : 2 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 169,14 | (sans nom) | - | edit |
| 282,14 | (sans nom) | - | edit |

</details>

## 9. NAVIGATION

### 9.1 Enchainement des ecrans

```mermaid
flowchart TD
    START([Entree])
    style START fill:#3fb950
    VF1[134 Visu service GO]
    style VF1 fill:#58a6ff
    VF2[134.1 Affichage]
    style VF2 fill:#58a6ff
    VF3[134.1.1 consultation heberg...]
    style VF3 fill:#58a6ff
    VF4[134.1.2 consult prestations]
    style VF4 fill:#58a6ff
    EXT389[IDE 389 Recuperation d...]
    style EXT389 fill:#3fb950
    EXT135[IDE 135 Imprim service...]
    style EXT135 fill:#3fb950
    FIN([Sortie])
    style FIN fill:#f85149
    START --> VF1
    VF1 -->|Recuperation donnees| EXT389
    VF1 -->|Impression ticket/document| EXT135
    EXT135 --> FIN
```

**Detail par enchainement :**

| Depuis | Action | Vers | Retour |
|--------|--------|------|--------|
| Visu service GO | Recuperation donnees | [Recuperation du titre (IDE 389)](PBP-IDE-389.md) | Retour ecran |
| Visu service GO | Impression ticket/document | [  Imprim service GO AL (IDE 135)](PBP-IDE-135.md) | Retour ecran |

### 9.3 Structure hierarchique (4 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **134.1** | [**Visu service GO** (134)](#t1) [mockup](#ecran-t1) | MDI | 1254x224 | Traitement |
| 134.1.1 | [consultation hebergement (134.1.1)](#t3) [mockup](#ecran-t3) | Modal | 773x78 | |
| 134.1.2 | [consult prestations (134.1.2)](#t4) [mockup](#ecran-t4) | Modal | 759x38 | |
| **134.2** | [**Affichage** (134.1)](#t2) [mockup](#ecran-t2) | MDI | 779x266 | Consultation |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Affichage]
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

### Tables utilisees (7)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 31 | gm-complet_______gmc |  | DB | R |   |   | 1 |
| 33 | prestations______pre | Prestations/services vendus | DB | R |   |   | 1 |
| 34 | hebergement______heb | Hebergement (chambres) | DB | R |   |   | 1 |
| 35 | personnel_go______go |  | DB | R |   |   | 1 |
| 135 | libelle_prestation | Prestations/services vendus | DB |   |   | L | 1 |
| 620 | zip_chambre |  | TMP |   |   | L | 1 |
| 1094 | Table_1094 |  | MEM |   |   | L | 1 |

### Colonnes par table (3 / 4 tables avec colonnes identifiees)

<details>
<summary>Table 31 - gm-complet_______gmc (R) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 33 - prestations______pre (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P.Num compte | R | Numeric |
| B | P.Filiation | R | Numeric |

</details>

<details>
<summary>Table 34 - hebergement______heb (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P.Num compte | R | Numeric |
| B | P.Filiation | R | Numeric |

</details>

<details>
<summary>Table 35 - personnel_go______go (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | >Date Consultation | R | Date |
| B | >Total | R | Numeric |
| C | >Selection | R | Numeric |
| D | w0_TitreEcran | R | Alpha |
| E | b_Voir | R | Alpha |
| F | b_Imprimer | R | Alpha |
| G | b_Quitter | R | Alpha |

</details>

## 11. VARIABLES

### 11.1 Autres (7)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | >Date Consultation | Date | - |
| B | >Total | Numeric | 1x refs |
| C | >Selection | Numeric | 1x refs |
| D | w0_TitreEcran | Alpha | 1x refs |
| E | b_Voir | Alpha | - |
| F | b_Imprimer | Alpha | - |
| G | b_Quitter | Alpha | - |

## 12. EXPRESSIONS

**17 / 17 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONDITION | 2 | 5 |
| CONSTANTE | 4 | 0 |
| DATE | 1 | 0 |
| OTHER | 5 | 0 |
| REFERENCE_VG | 3 | 0 |
| STRING | 1 | 0 |
| CONCATENATION | 1 | 0 |

### 12.2 Expressions cles par type

#### CONDITION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 15 | `IF(VG117,[BL],[Z])` | [RM-001](#rm-RM-001) |
| CONDITION | 16 | `IF(VG117,[BM],[AA])` | - |

#### CONSTANTE (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 10 | `'&Imprimante'` | - |
| CONSTANTE | 11 | `'&Quitter'` | - |
| CONSTANTE | 3 | `13` | - |
| CONSTANTE | 9 | `'&Voir'` | - |

#### DATE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| DATE | 6 | `Date ()` | - |

#### OTHER (5 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 13 | `GetParam ('VILLAGE')` | - |
| OTHER | 14 | `[BK]` | - |
| OTHER | 8 | `[V]` | - |
| OTHER | 1 | `GetParam ('SOCIETE')` | - |
| OTHER | 7 | `[U]` | - |

#### REFERENCE_VG (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 17 | `VG117` | - |
| REFERENCE_VG | 5 | `VG2` | - |
| REFERENCE_VG | 2 | `VG1` | - |

#### STRING (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| STRING | 4 | `Trim (w0_TitreEcran [D])` | - |

#### CONCATENATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 12 | `'Selection '&Trim (Str (>Selection [C],'4'))&' sur '&Trim (Str (>Total [B],'4'))` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Service GO (IDE 133)](PBP-IDE-133.md) -> **Visu service GO (IDE 134)**

```mermaid
graph LR
    T134[134 Visu service GO]
    style T134 fill:#58a6ff
    CC133[133 Service GO]
    style CC133 fill:#8b5cf6
    CC133 --> T134
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [133](PBP-IDE-133.md) | Service GO | 2 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T134[134 Visu service GO]
    style T134 fill:#58a6ff
    C389[389 Recuperation du titre]
    T134 --> C389
    style C389 fill:#3fb950
    C135[135 Imprim service GO AL]
    T134 --> C135
    style C135 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [389](PBP-IDE-389.md) | Recuperation du titre | 2 | Recuperation donnees |
| [135](PBP-IDE-135.md) |   Imprim service GO AL | 1 | Impression ticket/document |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 108 | Programme compact |
| Expressions | 17 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 2 | Peu de dependances |
| Ecrans visibles | 4 | Quelques ecrans |
| Code desactive | 0% (0 / 108) | Code sain |
| Regles metier | 1 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (3 taches: 3 ecrans, 0 traitement)

- **Strategie** : 3 composant(s) UI (Razor/React) avec formulaires et validation.
- 2 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Consultation (1 tache: 1 ecran, 0 traitement)

- **Strategie** : Composants de recherche/selection en modales.
- 1 ecran : Affichage

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| [Recuperation du titre (IDE 389)](PBP-IDE-389.md) | Sous-programme | 2x | Haute - Recuperation donnees |
| [  Imprim service GO AL (IDE 135)](PBP-IDE-135.md) | Sous-programme | 1x | Normale - Impression ticket/document |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 15:26*
