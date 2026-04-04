# PBP IDE 158 - Affich arrivant planning GM

> **Analyse**: Phases 1-4 2026-02-03 15:32 -> 15:32 (11s) | Assemblage 15:32
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBP |
| IDE Position | 158 |
| Nom Programme | Affich arrivant planning GM |
| Fichier source | `Prg_158.xml` |
| Dossier IDE | Liste |
| Taches | 4 (4 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 4 |

## 2. DESCRIPTION FONCTIONNELLE

**Affich arrivant planning GM** assure la gestion complete de ce processus, accessible depuis [  Liste CLients arrivant (IDE 156)](PBP-IDE-156.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (4 taches) : traitements metier divers

**Logique metier** : 2 regles identifiees couvrant conditions metier.

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (4 taches)

- **158** - Toutes **[[ECRAN]](#ecran-t1)**
- **158.1** - Detail **[[ECRAN]](#ecran-t2)**
- **158.1.1** - consultation hebergement **[[ECRAN]](#ecran-t3)**
- **158.1.2** - consult prestations **[[ECRAN]](#ecran-t4)**

Delegue a : [Recuperation du titre (IDE 389)](PBP-IDE-389.md), [Imp GM arrivant planning TAI (IDE 252)](PBP-IDE-252.md)

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (4 taches)

Traitements internes.

---

#### <a id="t1"></a>158 - Toutes [[ECRAN]](#ecran-t1)

**Role** : Traitement : Toutes.
**Ecran** : 1237 x 225 DLU (MDI) | [Voir mockup](#ecran-t1)

<details>
<summary>3 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [158.1](#t2) | Detail **[[ECRAN]](#ecran-t2)** | Traitement |
| [158.1.1](#t3) | consultation hebergement **[[ECRAN]](#ecran-t3)** | Traitement |
| [158.1.2](#t4) | consult prestations **[[ECRAN]](#ecran-t4)** | Traitement |

</details>
**Delegue a** : [Recuperation du titre (IDE 389)](PBP-IDE-389.md), [Imp GM arrivant planning TAI (IDE 252)](PBP-IDE-252.md)

---

#### <a id="t2"></a>158.1 - Detail [[ECRAN]](#ecran-t2)

**Role** : Traitement : Detail.
**Ecran** : 774 x 267 DLU (MDI) | [Voir mockup](#ecran-t2)
**Delegue a** : [Recuperation du titre (IDE 389)](PBP-IDE-389.md), [Imp GM arrivant planning TAI (IDE 252)](PBP-IDE-252.md)

---

#### <a id="t3"></a>158.1.1 - consultation hebergement [[ECRAN]](#ecran-t3)

**Role** : Consultation/chargement : consultation hebergement.
**Ecran** : 763 x 78 DLU (Modal) | [Voir mockup](#ecran-t3)
**Delegue a** : [Recuperation du titre (IDE 389)](PBP-IDE-389.md), [Imp GM arrivant planning TAI (IDE 252)](PBP-IDE-252.md)

---

#### <a id="t4"></a>158.1.2 - consult prestations [[ECRAN]](#ecran-t4)

**Role** : Traitement : consult prestations.
**Ecran** : 759 x 40 DLU (Modal) | [Voir mockup](#ecran-t4)
**Delegue a** : [Recuperation du titre (IDE 389)](PBP-IDE-389.md), [Imp GM arrivant planning TAI (IDE 252)](PBP-IDE-252.md)


## 5. REGLES METIER

2 regles identifiees:

### Autres (2 regles)

#### <a id="rm-RM-001"></a>[RM-001] Si [EB] alors Trim([EC])&Trim([ED])&Str([AI] sinon '3P0'),Trim(Existe TAI [R])&Str([AI],'3P0'))

| Element | Detail |
|---------|--------|
| **Condition** | `[EB]` |
| **Si vrai** | Trim([EC])&Trim([ED])&Str([AI] |
| **Si faux** | '3P0'),Trim(Existe TAI [R])&Str([AI],'3P0')) |
| **Variables** | R (Existe TAI) |
| **Expression source** | Expression 34 : `IF([EB],Trim([EC])&Trim([ED])&Str([AI],'3P0'),Trim(Existe TA` |
| **Exemple** | Si [EB] â†’ Trim([EC])&Trim([ED])&Str([AI]. Sinon â†’ '3P0'),Trim(Existe TAI [R])&Str([AI],'3P0')) |

#### <a id="rm-RM-002"></a>[RM-002] Si VG88 AND [EI] alors TStr([EF] sinon 'HHhMMZ'), [AC])

| Element | Detail |
|---------|--------|
| **Condition** | `VG88 AND [EI]` |
| **Si vrai** | TStr([EF] |
| **Si faux** | 'HHhMMZ'), [AC]) |
| **Expression source** | Expression 35 : `IF(VG88 AND [EI],TStr([EF],'HHhMMZ'), [AC])` |
| **Exemple** | Si VG88 AND [EI] â†’ TStr([EF]. Sinon â†’ 'HHhMMZ'), [AC]) |

## 6. CONTEXTE

- **Appele par**: [  Liste CLients arrivant (IDE 156)](PBP-IDE-156.md)
- **Appelle**: 4 programmes | **Tables**: 10 (W:0 R:4 L:6) | **Taches**: 4 | **Expressions**: 36

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (4 / 4)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 158 | 158 | Toutes | MDI | 1237 | 225 | Traitement |
| 2 | 158.1 | 158.1 | Detail | MDI | 774 | 267 | Traitement |
| 3 | 158.1.1 | 158.1.1 | consultation hebergement | Modal | 763 | 78 | Traitement |
| 4 | 158.1.2 | 158.1.2 | consult prestations | Modal | 759 | 40 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>158 - Toutes
**Tache** : [158](#t1) | **Type** : MDI | **Dimensions** : 1237 x 225 DLU
**Bloc** : Traitement | **Titre IDE** : Toutes

<!-- FORM-DATA:
{
    "width":  1237,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  1234,
                         "fmt":  "",
                         "name":  "",
                         "h":  19,
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
                         "w":  1046,
                         "y":  23,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  14,
                         "h":  110,
                         "cols":  [
                                      {
                                          "title":  "Nom",
                                          "layer":  1,
                                          "w":  188
                                      },
                                      {
                                          "title":  "Prénom",
                                          "layer":  2,
                                          "w":  130
                                      },
                                      {
                                          "title":  "Sexe",
                                          "layer":  3,
                                          "w":  55
                                      },
                                      {
                                          "title":  "Qualité",
                                          "layer":  4,
                                          "w":  116
                                      },
                                      {
                                          "title":  "Age",
                                          "layer":  5,
                                          "w":  52
                                      },
                                      {
                                          "title":  "Logement",
                                          "layer":  6,
                                          "w":  183
                                      },
                                      {
                                          "title":  "Pays",
                                          "layer":  7,
                                          "w":  55
                                      },
                                      {
                                          "title":  "Numéro Adhérent",
                                          "layer":  8,
                                          "w":  232
                                      }
                                  ],
                         "rows":  8
                     },
                     {
                         "x":  1050,
                         "type":  "label",
                         "var":  "",
                         "y":  21,
                         "w":  175,
                         "fmt":  "",
                         "name":  "",
                         "h":  175,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  1059,
                         "type":  "label",
                         "var":  "",
                         "y":  23,
                         "w":  154,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "144",
                         "text":  "Only TAI",
                         "parent":  7
                     },
                     {
                         "x":  7,
                         "type":  "label",
                         "var":  "",
                         "y":  145,
                         "w":  1035,
                         "fmt":  "",
                         "name":  "",
                         "h":  52,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  18,
                         "type":  "label",
                         "var":  "",
                         "y":  150,
                         "w":  245,
                         "fmt":  "",
                         "name":  "",
                         "h":  42,
                         "color":  "195",
                         "text":  "Arrivée",
                         "parent":  27
                     },
                     {
                         "x":  275,
                         "type":  "label",
                         "var":  "",
                         "y":  150,
                         "w":  245,
                         "fmt":  "",
                         "name":  "",
                         "h":  42,
                         "color":  "195",
                         "text":  "Départ",
                         "parent":  27
                     },
                     {
                         "x":  529,
                         "type":  "label",
                         "var":  "",
                         "y":  154,
                         "w":  499,
                         "fmt":  "",
                         "name":  "",
                         "h":  38,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  29,
                         "type":  "label",
                         "var":  "",
                         "y":  162,
                         "w":  120,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Date",
                         "parent":  28
                     },
                     {
                         "x":  158,
                         "type":  "label",
                         "var":  "",
                         "y":  162,
                         "w":  82,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Heure",
                         "parent":  28
                     },
                     {
                         "x":  288,
                         "type":  "label",
                         "var":  "",
                         "y":  162,
                         "w":  88,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Date",
                         "parent":  29
                     },
                     {
                         "x":  384,
                         "type":  "label",
                         "var":  "",
                         "y":  162,
                         "w":  133,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Heure",
                         "parent":  29
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  199,
                         "w":  1234,
                         "fmt":  "",
                         "name":  "",
                         "h":  23,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  11,
                         "type":  "edit",
                         "var":  "",
                         "y":  38,
                         "w":  176,
                         "fmt":  "",
                         "name":  "TLE Nom",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  6
                     },
                     {
                         "x":  197,
                         "type":  "edit",
                         "var":  "",
                         "y":  38,
                         "w":  120,
                         "fmt":  "",
                         "name":  "TLE Prenom",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  6
                     },
                     {
                         "x":  326,
                         "type":  "edit",
                         "var":  "",
                         "y":  37,
                         "w":  37,
                         "fmt":  "",
                         "name":  "TLE Sexe",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  6
                     },
                     {
                         "x":  381,
                         "type":  "edit",
                         "var":  "",
                         "y":  37,
                         "w":  104,
                         "fmt":  "",
                         "name":  "TLE Qualite",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  6
                     },
                     {
                         "x":  498,
                         "type":  "edit",
                         "var":  "",
                         "y":  37,
                         "w":  37,
                         "fmt":  "",
                         "name":  "TLE Age",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  6
                     },
                     {
                         "x":  549,
                         "type":  "edit",
                         "var":  "",
                         "y":  37,
                         "w":  171,
                         "fmt":  "",
                         "name":  "TLE Logement",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  6
                     },
                     {
                         "x":  733,
                         "type":  "edit",
                         "var":  "",
                         "y":  37,
                         "w":  37,
                         "fmt":  "",
                         "name":  "TLE Pays",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  6
                     },
                     {
                         "x":  789,
                         "type":  "edit",
                         "var":  "",
                         "y":  37,
                         "w":  216,
                         "fmt":  "",
                         "name":  "TLE Numero Adherent",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  6
                     },
                     {
                         "x":  29,
                         "type":  "edit",
                         "var":  "",
                         "y":  176,
                         "w":  120,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  28
                     },
                     {
                         "x":  158,
                         "type":  "edit",
                         "var":  "",
                         "y":  176,
                         "w":  82,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  28
                     },
                     {
                         "x":  288,
                         "type":  "edit",
                         "var":  "",
                         "y":  176,
                         "w":  120,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  29
                     },
                     {
                         "x":  419,
                         "type":  "edit",
                         "var":  "",
                         "y":  176,
                         "w":  82,
                         "fmt":  "6",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  29
                     },
                     {
                         "x":  947,
                         "type":  "edit",
                         "var":  "",
                         "y":  176,
                         "w":  56,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  30
                     },
                     {
                         "x":  1059,
                         "type":  "button",
                         "var":  "",
                         "y":  114,
                         "w":  154,
                         "fmt":  "\u0026Commentaire",
                         "name":  "b_Commentaire",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  1059,
                         "type":  "button",
                         "var":  "",
                         "y":  139,
                         "w":  154,
                         "fmt":  "\u0026Voir",
                         "name":  "b_Ecran",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  1059,
                         "type":  "button",
                         "var":  "",
                         "y":  162,
                         "w":  154,
                         "fmt":  "\u0026Impression",
                         "name":  "b_Imprim",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  8,
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
                         "x":  472,
                         "type":  "edit",
                         "var":  "",
                         "y":  6,
                         "w":  288,
                         "fmt":  "25",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  915,
                         "type":  "edit",
                         "var":  "",
                         "y":  6,
                         "w":  310,
                         "fmt":  "WWW DD MMM YYYYT",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  8,
                         "type":  "edit",
                         "var":  "",
                         "y":  10,
                         "w":  154,
                         "fmt":  "30",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  1054,
                         "type":  "image",
                         "var":  "",
                         "y":  43,
                         "w":  165,
                         "fmt":  "",
                         "name":  "",
                         "h":  50,
                         "color":  "",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  7,
                         "type":  "edit",
                         "var":  "",
                         "y":  135,
                         "w":  1035,
                         "fmt":  "100",
                         "name":  "",
                         "h":  10,
                         "color":  "144",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  561,
                         "type":  "edit",
                         "var":  "",
                         "y":  160,
                         "w":  56,
                         "fmt":  "4",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  30
                     },
                     {
                         "x":  835,
                         "type":  "edit",
                         "var":  "",
                         "y":  160,
                         "w":  168,
                         "fmt":  "14",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  30
                     },
                     {
                         "x":  561,
                         "type":  "edit",
                         "var":  "",
                         "y":  176,
                         "w":  194,
                         "fmt":  "30",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  30
                     },
                     {
                         "x":  773,
                         "type":  "edit",
                         "var":  "",
                         "y":  176,
                         "w":  157,
                         "fmt":  "13",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  30
                     },
                     {
                         "x":  7,
                         "type":  "button",
                         "var":  "",
                         "y":  202,
                         "w":  154,
                         "fmt":  "\u0026Quitter",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  44
                     },
                     {
                         "x":  640,
                         "type":  "edit",
                         "var":  "",
                         "y":  160,
                         "w":  181,
                         "fmt":  "20",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  30
                     }
                 ],
    "taskId":  "158",
    "height":  225
}
-->

<details>
<summary><strong>Champs : 23 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 11,38 | TLE Nom | - | edit |
| 197,38 | TLE Prenom | - | edit |
| 326,37 | TLE Sexe | - | edit |
| 381,37 | TLE Qualite | - | edit |
| 498,37 | TLE Age | - | edit |
| 549,37 | TLE Logement | - | edit |
| 733,37 | TLE Pays | - | edit |
| 789,37 | TLE Numero Adherent | - | edit |
| 29,176 | (sans nom) | - | edit |
| 158,176 | (sans nom) | - | edit |
| 288,176 | (sans nom) | - | edit |
| 419,176 | 6 | - | edit |
| 947,176 | (sans nom) | - | edit |
| 8,2 | 30 | - | edit |
| 472,6 | 25 | - | edit |
| 915,6 | WWW DD MMM YYYYT | - | edit |
| 8,10 | 30 | - | edit |
| 7,135 | 100 | - | edit |
| 561,160 | 4 | - | edit |
| 835,160 | 14 | - | edit |
| 561,176 | 30 | - | edit |
| 773,176 | 13 | - | edit |
| 640,160 | 20 | - | edit |

</details>

<details>
<summary><strong>Boutons : 4 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Commentaire | 1059,114 | Appel [Affichage Commentaire (IDE 198)](PBP-IDE-198.md) |
| Voir | 1059,139 | Bouton fonctionnel |
| Impression | 1059,162 | Bouton fonctionnel |
| Quitter | 7,202 | Quitte le programme |

</details>

---

#### <a id="ecran-t2"></a>158.1 - Detail
**Tache** : [158.1](#t2) | **Type** : MDI | **Dimensions** : 774 x 267 DLU
**Bloc** : Traitement | **Titre IDE** : Detail

<!-- FORM-DATA:
{
    "width":  774,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  3,
                         "type":  "label",
                         "var":  "",
                         "y":  15,
                         "w":  757,
                         "fmt":  "",
                         "name":  "",
                         "h":  98,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  11,
                         "type":  "label",
                         "var":  "",
                         "y":  23,
                         "w":  94,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "N° adhérent",
                         "parent":  3
                     },
                     {
                         "x":  5,
                         "type":  "line",
                         "var":  "",
                         "y":  34,
                         "w":  752,
                         "fmt":  "",
                         "name":  "",
                         "h":  0,
                         "color":  "",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  11,
                         "type":  "label",
                         "var":  "",
                         "y":  39,
                         "w":  88,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Naissance",
                         "parent":  3
                     },
                     {
                         "x":  5,
                         "type":  "line",
                         "var":  "",
                         "y":  51,
                         "w":  752,
                         "fmt":  "",
                         "name":  "",
                         "h":  0,
                         "color":  "",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  11,
                         "type":  "label",
                         "var":  "",
                         "y":  57,
                         "w":  64,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Identité",
                         "parent":  3
                     },
                     {
                         "x":  5,
                         "type":  "line",
                         "var":  "",
                         "y":  70,
                         "w":  752,
                         "fmt":  "",
                         "name":  "",
                         "h":  0,
                         "color":  "",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  11,
                         "type":  "label",
                         "var":  "",
                         "y":  75,
                         "w":  69,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "Adresse",
                         "parent":  3
                     },
                     {
                         "x":  2,
                         "type":  "label",
                         "var":  "",
                         "y":  238,
                         "w":  762,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  64,
                         "type":  "edit",
                         "var":  "",
                         "y":  5,
                         "w":  37,
                         "fmt":  "",
                         "name":  "GMC Titre",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  125,
                         "type":  "edit",
                         "var":  "",
                         "y":  22,
                         "w":  26,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  158,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  123,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  290,
                         "type":  "edit",
                         "var":  "",
                         "y":  22,
                         "w":  26,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  325,
                         "type":  "edit",
                         "var":  "",
                         "y":  22,
                         "w":  48,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  109,
                         "type":  "edit",
                         "var":  "",
                         "y":  39,
                         "w":  132,
                         "fmt":  "DD/MM/YYYYZ",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  248,
                         "type":  "edit",
                         "var":  "",
                         "y":  39,
                         "w":  440,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  694,
                         "type":  "edit",
                         "var":  "",
                         "y":  39,
                         "w":  45,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  109,
                         "type":  "edit",
                         "var":  "",
                         "y":  57,
                         "w":  22,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  136,
                         "type":  "edit",
                         "var":  "",
                         "y":  57,
                         "w":  347,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  488,
                         "type":  "edit",
                         "var":  "",
                         "y":  57,
                         "w":  123,
                         "fmt":  "DD/MM/YYYYZ",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  618,
                         "type":  "edit",
                         "var":  "",
                         "y":  57,
                         "w":  123,
                         "fmt":  "DD/MM/YYYYZ",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  109,
                         "type":  "edit",
                         "var":  "",
                         "y":  86,
                         "w":  403,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  109,
                         "type":  "edit",
                         "var":  "",
                         "y":  97,
                         "w":  123,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  242,
                         "type":  "edit",
                         "var":  "",
                         "y":  97,
                         "w":  347,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  109,
                         "type":  "edit",
                         "var":  "",
                         "y":  75,
                         "w":  123,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  242,
                         "type":  "edit",
                         "var":  "",
                         "y":  75,
                         "w":  347,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  101,
                         "type":  "edit",
                         "var":  "",
                         "y":  5,
                         "w":  597,
                         "fmt":  "55",
                         "name":  "",
                         "h":  10,
                         "color":  "7",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  10,
                         "type":  "button",
                         "var":  "",
                         "y":  241,
                         "w":  154,
                         "fmt":  "\u0026Quitter",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  27
                     },
                     {
                         "x":  1,
                         "type":  "subform",
                         "var":  "",
                         "y":  113,
                         "w":  767,
                         "fmt":  "",
                         "name":  "consultation hebergement",
                         "h":  80,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  0,
                         "type":  "subform",
                         "var":  "",
                         "y":  194,
                         "w":  768,
                         "fmt":  "",
                         "name":  "consult prestations",
                         "h":  44,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "158.1",
    "height":  267
}
-->

<details>
<summary><strong>Champs : 18 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 64,5 | GMC Titre | - | edit |
| 125,22 | (sans nom) | - | edit |
| 158,23 | (sans nom) | - | edit |
| 290,22 | (sans nom) | - | edit |
| 325,22 | (sans nom) | - | edit |
| 109,39 | DD/MM/YYYYZ | - | edit |
| 248,39 | (sans nom) | - | edit |
| 694,39 | (sans nom) | - | edit |
| 109,57 | (sans nom) | - | edit |
| 136,57 | (sans nom) | - | edit |
| 488,57 | DD/MM/YYYYZ | - | edit |
| 618,57 | DD/MM/YYYYZ | - | edit |
| 109,86 | (sans nom) | - | edit |
| 109,97 | (sans nom) | - | edit |
| 242,97 | (sans nom) | - | edit |
| 109,75 | (sans nom) | - | edit |
| 242,75 | (sans nom) | - | edit |
| 101,5 | 55 | - | edit |

</details>

<details>
<summary><strong>Boutons : 1 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Quitter | 10,241 | Quitte le programme |

</details>

---

#### <a id="ecran-t3"></a>158.1.1 - consultation hebergement
**Tache** : [158.1.1](#t3) | **Type** : Modal | **Dimensions** : 763 x 78 DLU
**Bloc** : Traitement | **Titre IDE** : consultation hebergement

<!-- FORM-DATA:
{
    "width":  763,
    "vFactor":  8,
    "type":  "Modal",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  1,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "110",
                         "w":  762,
                         "y":  13,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  12,
                         "h":  62,
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
                                          "w":  242
                                      }
                                  ],
                         "rows":  4
                     },
                     {
                         "x":  165,
                         "type":  "edit",
                         "var":  "",
                         "y":  27,
                         "w":  120,
                         "fmt":  "DD/MM/YYYYZ",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  293,
                         "type":  "edit",
                         "var":  "",
                         "y":  27,
                         "w":  30,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  330,
                         "type":  "edit",
                         "var":  "",
                         "y":  27,
                         "w":  120,
                         "fmt":  "DD/MM/YYYYZ",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  454,
                         "type":  "edit",
                         "var":  "",
                         "y":  27,
                         "w":  30,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  493,
                         "type":  "edit",
                         "var":  "",
                         "y":  27,
                         "w":  232,
                         "fmt":  "20",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  6,
                         "type":  "edit",
                         "var":  "",
                         "y":  27,
                         "w":  142,
                         "fmt":  "12",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     }
                 ],
    "taskId":  "158.1.1",
    "height":  78
}
-->

<details>
<summary><strong>Champs : 6 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 165,27 | DD/MM/YYYYZ | - | edit |
| 293,27 | (sans nom) | - | edit |
| 330,27 | DD/MM/YYYYZ | - | edit |
| 454,27 | (sans nom) | - | edit |
| 493,27 | 20 | - | edit |
| 6,27 | 12 | - | edit |

</details>

---

#### <a id="ecran-t4"></a>158.1.2 - consult prestations
**Tache** : [158.1.2](#t4) | **Type** : Modal | **Dimensions** : 759 x 40 DLU
**Bloc** : Traitement | **Titre IDE** : consult prestations

<!-- FORM-DATA:
{
    "width":  759,
    "vFactor":  8,
    "type":  "Modal",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  187,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "110",
                         "w":  397,
                         "y":  0,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  11,
                         "h":  36,
                         "cols":  [
                                      {
                                          "title":  "Code circuit",
                                          "layer":  1,
                                          "w":  111
                                      },
                                      {
                                          "title":  "Libellé ",
                                          "layer":  2,
                                          "w":  254
                                      }
                                  ],
                         "rows":  2
                     },
                     {
                         "x":  193,
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
                         "x":  304,
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
    "taskId":  "158.1.2",
    "height":  40
}
-->

<details>
<summary><strong>Champs : 2 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 193,14 | (sans nom) | - | edit |
| 304,14 | (sans nom) | - | edit |

</details>

## 9. NAVIGATION

### 9.1 Enchainement des ecrans

```mermaid
flowchart TD
    START([Entree])
    style START fill:#3fb950
    VF1[158 Toutes]
    style VF1 fill:#58a6ff
    VF2[158.1 Detail]
    style VF2 fill:#58a6ff
    VF3[158.1.1 consultation heberg...]
    style VF3 fill:#58a6ff
    VF4[158.1.2 consult prestations]
    style VF4 fill:#58a6ff
    EXT389[IDE 389 Recuperation d...]
    style EXT389 fill:#3fb950
    EXT159[IDE 159 Imprim GM arri...]
    style EXT159 fill:#3fb950
    EXT198[IDE 198 Affichage Comm...]
    style EXT198 fill:#3fb950
    EXT252[IDE 252 Imp GM arrivan...]
    style EXT252 fill:#3fb950
    FIN([Sortie])
    style FIN fill:#f85149
    START --> VF1
    VF1 -->|Recuperation donnees| EXT389
    VF1 -->|Impression ticket/document| EXT159
    VF1 -->|Affichage donnees| EXT198
    VF1 -->|Sous-programme| EXT252
    EXT252 --> FIN
```

**Detail par enchainement :**

| Depuis | Action | Vers | Retour |
|--------|--------|------|--------|
| Toutes | Recuperation donnees | [Recuperation du titre (IDE 389)](PBP-IDE-389.md) | Retour ecran |
| Toutes | Impression ticket/document | [  Imprim GM arrivant planning (IDE 159)](PBP-IDE-159.md) | Retour ecran |
| Toutes | Affichage donnees | [Affichage Commentaire (IDE 198)](PBP-IDE-198.md) | Retour ecran |
| Toutes | Sous-programme | [Imp GM arrivant planning TAI (IDE 252)](PBP-IDE-252.md) | Retour ecran |

### 9.3 Structure hierarchique (4 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **158.1** | [**Toutes** (158)](#t1) [mockup](#ecran-t1) | MDI | 1237x225 | Traitement |
| 158.1.1 | [Detail (158.1)](#t2) [mockup](#ecran-t2) | MDI | 774x267 | |
| 158.1.2 | [consultation hebergement (158.1.1)](#t3) [mockup](#ecran-t3) | Modal | 763x78 | |
| 158.1.3 | [consult prestations (158.1.2)](#t4) [mockup](#ecran-t4) | Modal | 759x40 | |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Detail]
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

### Tables utilisees (10)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 31 | gm-complet_______gmc |  | DB | R |   |   | 1 |
| 33 | prestations______pre | Prestations/services vendus | DB | R |   |   | 1 |
| 34 | hebergement______heb | Hebergement (chambres) | DB | R |   |   | 1 |
| 135 | libelle_prestation | Prestations/services vendus | DB |   |   | L | 1 |
| 171 | commentaire______com |  | DB | R |   |   | 1 |
| 358 | import_mod |  | DB |   |   | L | 1 |
| 463 | heure_de_passage |  | DB |   |   | L | 1 |
| 619 | tempo_userlist | Table temporaire ecran | TMP |   |   | L | 1 |
| 738 | pv_selling_unit |  | DB |   |   | L | 1 |
| 845 | stat_vendeur_date |  | TMP |   |   | L | 1 |

### Colonnes par table (5 / 4 tables avec colonnes identifiees)

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
<summary>Table 171 - commentaire______com (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | >CodeEcran | R | Numeric |
| B | >Date | R | Date |
| C | >Heure | R | Alpha |
| D | >CodeListe | R | Alpha |
| E | >TopListe | R | Alpha |
| F | >Logement | R | Alpha |
| G | >TitreMaman | R | Alpha |
| H | >Total | R | Numeric |
| I | >NbSelect | R | Numeric |
| J | >AgeMin | R | Numeric |
| K | >AgeMax | R | Numeric |
| L | >CodeGroupe | R | Alpha |
| M | >OnlyTAI | R | Logical |
| N | >Tri Nom / Affiliation | R | Logical |
| O | > Départ village | R | Logical |
| P | w0_TitreEcran | R | Alpha |
| Q | w0_RetCommentaire | R | Logical |
| R | Existe TAI | R | Logical |
| S | Ordre Tri | R | Alpha |
| T | b_Commentaire | R | Alpha |
| U | b_Ecran | R | Alpha |
| V | b_Imprim | R | Alpha |

</details>

## 11. VARIABLES

### 11.1 Autres (22)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | >CodeEcran | Numeric | - |
| B | >Date | Date | - |
| C | >Heure | Alpha | - |
| D | >CodeListe | Alpha | - |
| E | >TopListe | Alpha | - |
| F | >Logement | Alpha | - |
| G | >TitreMaman | Alpha | 1x refs |
| H | >Total | Numeric | 1x refs |
| I | >NbSelect | Numeric | 1x refs |
| J | >AgeMin | Numeric | - |
| K | >AgeMax | Numeric | - |
| L | >CodeGroupe | Alpha | - |
| M | >OnlyTAI | Logical | 3x refs |
| N | >Tri Nom / Affiliation | Logical | 1x refs |
| O | > Départ village | Logical | 1x refs |
| P | w0_TitreEcran | Alpha | - |
| Q | w0_RetCommentaire | Logical | - |
| R | Existe TAI | Logical | 1x refs |
| S | Ordre Tri | Alpha | - |
| T | b_Commentaire | Alpha | - |
| U | b_Ecran | Alpha | - |
| V | b_Imprim | Alpha | - |

<details>
<summary>Toutes les 22 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| Autre | **A** | >CodeEcran | Numeric |
| Autre | **B** | >Date | Date |
| Autre | **C** | >Heure | Alpha |
| Autre | **D** | >CodeListe | Alpha |
| Autre | **E** | >TopListe | Alpha |
| Autre | **F** | >Logement | Alpha |
| Autre | **G** | >TitreMaman | Alpha |
| Autre | **H** | >Total | Numeric |
| Autre | **I** | >NbSelect | Numeric |
| Autre | **J** | >AgeMin | Numeric |
| Autre | **K** | >AgeMax | Numeric |
| Autre | **L** | >CodeGroupe | Alpha |
| Autre | **M** | >OnlyTAI | Logical |
| Autre | **N** | >Tri Nom / Affiliation | Logical |
| Autre | **O** | > Départ village | Logical |
| Autre | **P** | w0_TitreEcran | Alpha |
| Autre | **Q** | w0_RetCommentaire | Logical |
| Autre | **R** | Existe TAI | Logical |
| Autre | **S** | Ordre Tri | Alpha |
| Autre | **T** | b_Commentaire | Alpha |
| Autre | **U** | b_Ecran | Alpha |
| Autre | **V** | b_Imprim | Alpha |

</details>

## 12. EXPRESSIONS

**36 / 36 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONDITION | 10 | 2 |
| CONSTANTE | 3 | 0 |
| DATE | 1 | 0 |
| CONCATENATION | 4 | 0 |
| OTHER | 15 | 0 |
| REFERENCE_VG | 2 | 0 |
| NEGATION | 1 | 0 |

### 12.2 Expressions cles par type

#### CONDITION (10 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 35 | `IF(VG88 AND [EI],TStr([EF],'HHhMMZ'), [AC])` | [RM-002](#rm-RM-002) |
| CONDITION | 34 | `IF([EB],Trim([EC])&Trim([ED])&Str([AI],'3P0'),Trim(Existe TAI [R])&Str([AI],'3P0'))` | [RM-001](#rm-RM-001) |
| CONDITION | 26 | `> Départ village [O]` | - |
| CONDITION | 18 | `[AF]<>''` | - |
| CONDITION | 32 | `>OnlyTAI [M]` | - |
| ... | | *+5 autres* | |

#### CONSTANTE (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 21 | `'&Commentaire'` | - |
| CONSTANTE | 20 | `'&Imprimante'` | - |
| CONSTANTE | 19 | `'&Ecran'` | - |

#### DATE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| DATE | 9 | `Date ()` | - |

#### CONCATENATION (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 15 | `Trim([DZ])&IF(VG125 AND [EK]='O',' NGM','')` | - |
| CONCATENATION | 23 | `Str (>NbSelect [I],'4')&' '&MlsTrans ('selectionne sur')&' '&Str (>Total [H],'4')` | - |
| CONCATENATION | 29 | `'TAI from '&DStr ([BG],'DD/MM/YYYY')&' to '&DStr ([BH],'DD/MM/YYYY')` | - |
| CONCATENATION | 4 | `Trim (>TitreMaman [G])&' '&Trim (>Tri Nom / Affiliation [N])` | - |

#### OTHER (15 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 24 | `GetParam ('VILLAGE')` | - |
| OTHER | 22 | `[AQ]` | - |
| OTHER | 17 | `MlsTrans ('Liste Blanche')` | - |
| OTHER | 25 | `[AY]` | - |
| OTHER | 33 | `[DW]` | - |
| ... | | *+10 autres* | |

#### REFERENCE_VG (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 8 | `VG2` | - |
| REFERENCE_VG | 3 | `VG1` | - |

#### NEGATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| NEGATION | 31 | `NOT (>OnlyTAI [M])` | - |

### 12.3 Toutes les expressions (36)

<details>
<summary>Voir les 36 expressions</summary>

#### CONDITION (10)

| IDE | Expression Decodee |
|-----|-------------------|
| 34 | `IF([EB],Trim([EC])&Trim([ED])&Str([AI],'3P0'),Trim(Existe TAI [R])&Str([AI],'3P0'))` |
| 35 | `IF(VG88 AND [EI],TStr([EF],'HHhMMZ'), [AC])` |
| 36 | `IF(VG88 AND [EI],'Libération logement','Départ village')` |
| 12 | `[AD]='B'` |
| 14 | `[AG]='R'` |
| 16 | `[AE]<>''` |
| 18 | `[AF]<>''` |
| 26 | `> Départ village [O]` |
| 30 | `[BC] AND >OnlyTAI [M]` |
| 32 | `>OnlyTAI [M]` |

#### CONSTANTE (3)

| IDE | Expression Decodee |
|-----|-------------------|
| 19 | `'&Ecran'` |
| 20 | `'&Imprimante'` |
| 21 | `'&Commentaire'` |

#### DATE (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 9 | `Date ()` |

#### CONCATENATION (4)

| IDE | Expression Decodee |
|-----|-------------------|
| 29 | `'TAI from '&DStr ([BG],'DD/MM/YYYY')&' to '&DStr ([BH],'DD/MM/YYYY')` |
| 4 | `Trim (>TitreMaman [G])&' '&Trim (>Tri Nom / Affiliation [N])` |
| 15 | `Trim([DZ])&IF(VG125 AND [EK]='O',' NGM','')` |
| 23 | `Str (>NbSelect [I],'4')&' '&MlsTrans ('selectionne sur')&' '&Str (>Total [H],'4')` |

#### OTHER (15)

| IDE | Expression Decodee |
|-----|-------------------|
| 1 | `GetParam ('SOCIETE')` |
| 2 | `GetParam ('CODELANGUE')` |
| 5 | `VG126 AND [EL]` |
| 6 | `[AH]` |
| 7 | `[AI]` |
| 10 | `MlsTrans ('Bebe')` |
| 11 | `MlsTrans ('Fiche police complétée')` |
| 13 | `MlsTrans ('Retour Circuit')` |
| 17 | `MlsTrans ('Liste Blanche')` |
| 22 | `[AQ]` |
| 24 | `GetParam ('VILLAGE')` |
| 25 | `[AY]` |
| 27 | `[AH]` |
| 28 | `[AI]` |
| 33 | `[DW]` |

#### REFERENCE_VG (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 3 | `VG1` |
| 8 | `VG2` |

#### NEGATION (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 31 | `NOT (>OnlyTAI [M])` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [  Liste CLients arrivant (IDE 156)](PBP-IDE-156.md) -> **Affich arrivant planning GM (IDE 158)**

```mermaid
graph LR
    T158[158 Affich arrivant pl...]
    style T158 fill:#58a6ff
    CC155[155 Liste des arrivants]
    style CC155 fill:#8b5cf6
    CC156[156 Liste CLients arri...]
    style CC156 fill:#3fb950
    CC155 --> CC156
    CC156 --> T158
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [156](PBP-IDE-156.md) |   Liste CLients arrivant | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T158[158 Affich arrivant pl...]
    style T158 fill:#58a6ff
    C389[389 Recuperation du titre]
    T158 --> C389
    style C389 fill:#3fb950
    C159[159 Imprim GM arrivant...]
    T158 --> C159
    style C159 fill:#3fb950
    C198[198 Affichage Commentaire]
    T158 --> C198
    style C198 fill:#3fb950
    C252[252 Imp GM arrivant pl...]
    T158 --> C252
    style C252 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [389](PBP-IDE-389.md) | Recuperation du titre | 2 | Recuperation donnees |
| [159](PBP-IDE-159.md) |   Imprim GM arrivant planning | 1 | Impression ticket/document |
| [198](PBP-IDE-198.md) | Affichage Commentaire | 1 | Affichage donnees |
| [252](PBP-IDE-252.md) | Imp GM arrivant planning TAI | 1 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 186 | Programme compact |
| Expressions | 36 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 4 | Peu de dependances |
| Ecrans visibles | 4 | Quelques ecrans |
| Code desactive | 0% (0 / 186) | Code sain |
| Regles metier | 2 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (4 taches: 4 ecrans, 0 traitement)

- **Strategie** : 4 composant(s) UI (Razor/React) avec formulaires et validation.
- 4 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| [Recuperation du titre (IDE 389)](PBP-IDE-389.md) | Sous-programme | 2x | Haute - Recuperation donnees |
| [Imp GM arrivant planning TAI (IDE 252)](PBP-IDE-252.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Affichage Commentaire (IDE 198)](PBP-IDE-198.md) | Sous-programme | 1x | Normale - Affichage donnees |
| [  Imprim GM arrivant planning (IDE 159)](PBP-IDE-159.md) | Sous-programme | 1x | Normale - Impression ticket/document |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 15:32*
