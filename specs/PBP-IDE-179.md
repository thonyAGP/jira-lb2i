# PBP IDE 179 - Affichage AVPBDR secretaire

> **Analyse**: Phases 1-4 2026-02-03 15:39 -> 15:40 (11s) | Assemblage 15:40
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBP |
| IDE Position | 179 |
| Nom Programme | Affichage AVPBDR secretaire |
| Fichier source | `Prg_179.xml` |
| Dossier IDE | Liste |
| Taches | 4 (4 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 2 |

## 2. DESCRIPTION FONCTIONNELLE

**Affichage AVPBDR secretaire** assure la gestion complete de ce processus, accessible depuis [  Liste CLients arrivant (IDE 156)](PBP-IDE-156.md), [  Liste Clients present (IDE 162)](PBP-IDE-162.md), [  Liste CLients depart (IDE 168)](PBP-IDE-168.md), [Liste CLients AVPBDR (IDE 174)](PBP-IDE-174.md), [  Liste present personnel plan (IDE 227)](PBP-IDE-227.md), [  Liste personnels AVPBDR (IDE 234)](PBP-IDE-234.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (4 taches) : traitements metier divers

**Logique metier** : 3 regles identifiees couvrant conditions metier.

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (4 taches)

- **179** - Secretaire **[[ECRAN]](#ecran-t1)**
- **179.1** - Detail **[[ECRAN]](#ecran-t2)**
- **179.1.1** - consultation hebergement **[[ECRAN]](#ecran-t3)**
- **179.1.2** - consult prestations **[[ECRAN]](#ecran-t4)**

Delegue a : [Recuperation du titre (IDE 389)](PBP-IDE-389.md)

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (4 taches)

Traitements internes.

---

#### <a id="t1"></a>179 - Secretaire [[ECRAN]](#ecran-t1)

**Role** : Traitement : Secretaire.
**Ecran** : 1162 x 281 DLU (MDI) | [Voir mockup](#ecran-t1)

<details>
<summary>3 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [179.1](#t2) | Detail **[[ECRAN]](#ecran-t2)** | Traitement |
| [179.1.1](#t3) | consultation hebergement **[[ECRAN]](#ecran-t3)** | Traitement |
| [179.1.2](#t4) | consult prestations **[[ECRAN]](#ecran-t4)** | Traitement |

</details>
**Delegue a** : [Recuperation du titre (IDE 389)](PBP-IDE-389.md), [  Imprim AVPBDR secretaire (IDE 180)](PBP-IDE-180.md)

---

#### <a id="t2"></a>179.1 - Detail [[ECRAN]](#ecran-t2)

**Role** : Traitement : Detail.
**Ecran** : 768 x 262 DLU (MDI) | [Voir mockup](#ecran-t2)
**Delegue a** : [Recuperation du titre (IDE 389)](PBP-IDE-389.md)

---

#### <a id="t3"></a>179.1.1 - consultation hebergement [[ECRAN]](#ecran-t3)

**Role** : Consultation/chargement : consultation hebergement.
**Ecran** : 768 x 78 DLU (Modal) | [Voir mockup](#ecran-t3)
**Delegue a** : [Recuperation du titre (IDE 389)](PBP-IDE-389.md)

---

#### <a id="t4"></a>179.1.2 - consult prestations [[ECRAN]](#ecran-t4)

**Role** : Traitement : consult prestations.
**Ecran** : 759 x 37 DLU (Modal) | [Voir mockup](#ecran-t4)
**Delegue a** : [Recuperation du titre (IDE 389)](PBP-IDE-389.md)


## 5. REGLES METIER

3 regles identifiees:

### Autres (3 regles)

#### <a id="rm-RM-001"></a>[RM-001] Si [CH] alors [CI]&[CJ]&Str([AE] sinon '3P0'),w0_TitreEcran [N]&Str([AE],'3P0'))

| Element | Detail |
|---------|--------|
| **Condition** | `[CH]` |
| **Si vrai** | [CI]&[CJ]&Str([AE] |
| **Si faux** | '3P0'),w0_TitreEcran [N]&Str([AE],'3P0')) |
| **Variables** | N (w0_TitreEcran) |
| **Expression source** | Expression 21 : `IF([CH],[CI]&[CJ]&Str([AE],'3P0'),w0_TitreEcran [N]&Str([AE]` |
| **Exemple** | Si [CH] â†’ [CI]&[CJ]&Str([AE]. Sinon â†’ '3P0'),w0_TitreEcran [N]&Str([AE],'3P0')) |

#### <a id="rm-RM-002"></a>[RM-002] Si VG88 AND [CN] alors TStr([CL] sinon 'HHhMMZ'),[Y])

| Element | Detail |
|---------|--------|
| **Condition** | `VG88 AND [CN]` |
| **Si vrai** | TStr([CL] |
| **Si faux** | 'HHhMMZ'),[Y]) |
| **Expression source** | Expression 22 : `IF(VG88 AND [CN],TStr([CL],'HHhMMZ'),[Y])` |
| **Exemple** | Si VG88 AND [CN] â†’ TStr([CL]. Sinon â†’ 'HHhMMZ'),[Y]) |

#### <a id="rm-RM-003"></a>[RM-003] Si [CO]<>'T' alors 29.75 sinon 25.75)

| Element | Detail |
|---------|--------|
| **Condition** | `[CO]<>'T'` |
| **Si vrai** | 29.75 |
| **Si faux** | 25.75) |
| **Expression source** | Expression 25 : `IF([CO]<>'T',29.75,25.75)` |
| **Exemple** | Si [CO]<>'T' â†’ 29.75. Sinon â†’ 25.75) |

## 6. CONTEXTE

- **Appele par**: [  Liste CLients arrivant (IDE 156)](PBP-IDE-156.md), [  Liste Clients present (IDE 162)](PBP-IDE-162.md), [  Liste CLients depart (IDE 168)](PBP-IDE-168.md), [Liste CLients AVPBDR (IDE 174)](PBP-IDE-174.md), [  Liste present personnel plan (IDE 227)](PBP-IDE-227.md), [  Liste personnels AVPBDR (IDE 234)](PBP-IDE-234.md)
- **Appelle**: 2 programmes | **Tables**: 6 (W:0 R:4 L:2) | **Taches**: 4 | **Expressions**: 27

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (4 / 4)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 179 | 179 | Secretaire | MDI | 1162 | 281 | Traitement |
| 2 | 179.1 | 179.1 | Detail | MDI | 768 | 262 | Traitement |
| 3 | 179.1.1 | 179.1.1 | consultation hebergement | Modal | 768 | 78 | Traitement |
| 4 | 179.1.2 | 179.1.2 | consult prestations | Modal | 759 | 37 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>179 - Secretaire
**Tache** : [179](#t1) | **Type** : MDI | **Dimensions** : 1162 x 281 DLU
**Bloc** : Traitement | **Titre IDE** : Secretaire

<!-- FORM-DATA:
{
    "width":  1162,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  1156,
                         "fmt":  "",
                         "name":  "",
                         "h":  19,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  962,
                         "type":  "label",
                         "var":  "",
                         "y":  41,
                         "w":  187,
                         "fmt":  "",
                         "name":  "",
                         "h":  205,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  0,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "110",
                         "w":  987,
                         "y":  44,
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
                                          "title":  "Age",
                                          "layer":  4,
                                          "w":  52
                                      },
                                      {
                                          "title":  "Pays",
                                          "layer":  5,
                                          "w":  65
                                      },
                                      {
                                          "title":  "Logement",
                                          "layer":  6,
                                          "w":  183
                                      },
                                      {
                                          "title":  "Commune",
                                          "layer":  7,
                                          "w":  249
                                      },
                                      {
                                          "title":  "S",
                                          "layer":  8,
                                          "w":  32
                                      }
                                  ],
                         "rows":  8
                     },
                     {
                         "x":  16,
                         "type":  "label",
                         "var":  "",
                         "y":  157,
                         "w":  941,
                         "fmt":  "",
                         "name":  "",
                         "h":  89,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  34,
                         "type":  "label",
                         "var":  "",
                         "y":  162,
                         "w":  245,
                         "fmt":  "",
                         "name":  "",
                         "h":  42,
                         "color":  "195",
                         "text":  "Arrivée",
                         "parent":  23
                     },
                     {
                         "x":  291,
                         "type":  "label",
                         "var":  "",
                         "y":  162,
                         "w":  245,
                         "fmt":  "",
                         "name":  "",
                         "h":  42,
                         "color":  "195",
                         "text":  "Départ",
                         "parent":  23
                     },
                     {
                         "x":  544,
                         "type":  "label",
                         "var":  "",
                         "y":  162,
                         "w":  397,
                         "fmt":  "",
                         "name":  "",
                         "h":  79,
                         "color":  "195",
                         "text":  "",
                         "parent":  23
                     },
                     {
                         "x":  43,
                         "type":  "label",
                         "var":  "",
                         "y":  173,
                         "w":  120,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Date",
                         "parent":  24
                     },
                     {
                         "x":  173,
                         "type":  "label",
                         "var":  "",
                         "y":  173,
                         "w":  82,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Heure",
                         "parent":  24
                     },
                     {
                         "x":  301,
                         "type":  "label",
                         "var":  "",
                         "y":  173,
                         "w":  120,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Date",
                         "parent":  25
                     },
                     {
                         "x":  432,
                         "type":  "label",
                         "var":  "",
                         "y":  173,
                         "w":  54,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Heure",
                         "parent":  25
                     },
                     {
                         "x":  34,
                         "type":  "label",
                         "var":  "",
                         "y":  205,
                         "w":  503,
                         "fmt":  "",
                         "name":  "",
                         "h":  36,
                         "color":  "195",
                         "text":  "",
                         "parent":  23
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  250,
                         "w":  1157,
                         "fmt":  "",
                         "name":  "",
                         "h":  23,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  21,
                         "w":  1156,
                         "fmt":  "",
                         "name":  "",
                         "h":  19,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  8,
                         "type":  "label",
                         "var":  "",
                         "y":  26,
                         "w":  131,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "Lieu de séjour",
                         "parent":  115
                     },
                     {
                         "x":  8,
                         "type":  "edit",
                         "var":  "",
                         "y":  57,
                         "w":  176,
                         "fmt":  "",
                         "name":  "TLE Nom",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  194,
                         "type":  "edit",
                         "var":  "",
                         "y":  57,
                         "w":  120,
                         "fmt":  "",
                         "name":  "TLE Prenom",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  323,
                         "type":  "edit",
                         "var":  "",
                         "y":  57,
                         "w":  37,
                         "fmt":  "",
                         "name":  "TLE Sexe",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  379,
                         "type":  "edit",
                         "var":  "",
                         "y":  57,
                         "w":  37,
                         "fmt":  "",
                         "name":  "TLE Age",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  496,
                         "type":  "edit",
                         "var":  "",
                         "y":  57,
                         "w":  171,
                         "fmt":  "",
                         "name":  "TLE Logement",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  430,
                         "type":  "edit",
                         "var":  "",
                         "y":  57,
                         "w":  37,
                         "fmt":  "",
                         "name":  "TLE Pays",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  43,
                         "type":  "edit",
                         "var":  "",
                         "y":  187,
                         "w":  120,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  24
                     },
                     {
                         "x":  173,
                         "type":  "edit",
                         "var":  "",
                         "y":  186,
                         "w":  82,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  24
                     },
                     {
                         "x":  301,
                         "type":  "edit",
                         "var":  "",
                         "y":  187,
                         "w":  120,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  25
                     },
                     {
                         "x":  432,
                         "type":  "edit",
                         "var":  "",
                         "y":  186,
                         "w":  82,
                         "fmt":  "6",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  25
                     },
                     {
                         "x":  454,
                         "type":  "edit",
                         "var":  "",
                         "y":  226,
                         "w":  56,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  38
                     },
                     {
                         "x":  678,
                         "type":  "edit",
                         "var":  "",
                         "y":  57,
                         "w":  238,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  693,
                         "type":  "edit",
                         "var":  "",
                         "y":  211,
                         "w":  238,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  26
                     },
                     {
                         "x":  558,
                         "type":  "edit",
                         "var":  "",
                         "y":  211,
                         "w":  123,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  26
                     },
                     {
                         "x":  558,
                         "type":  "edit",
                         "var":  "",
                         "y":  224,
                         "w":  126,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  26
                     },
                     {
                         "x":  558,
                         "type":  "edit",
                         "var":  "",
                         "y":  172,
                         "w":  126,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  26
                     },
                     {
                         "x":  558,
                         "type":  "edit",
                         "var":  "",
                         "y":  185,
                         "w":  350,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  26
                     },
                     {
                         "x":  978,
                         "type":  "button",
                         "var":  "",
                         "y":  177,
                         "w":  154,
                         "fmt":  "\u0026Voir",
                         "name":  "b_Ecran",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  6
                     },
                     {
                         "x":  978,
                         "type":  "button",
                         "var":  "",
                         "y":  204,
                         "w":  154,
                         "fmt":  "\u0026Impression",
                         "name":  "b_Imprim",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  6
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
                         "x":  278,
                         "type":  "edit",
                         "var":  "",
                         "y":  6,
                         "w":  605,
                         "fmt":  "100",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  939,
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
                         "x":  8,
                         "type":  "edit",
                         "var":  "",
                         "y":  10,
                         "w":  395,
                         "fmt":  "30",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  973,
                         "type":  "image",
                         "var":  "",
                         "y":  69,
                         "w":  165,
                         "fmt":  "",
                         "name":  "",
                         "h":  50,
                         "color":  "",
                         "text":  "",
                         "parent":  6
                     },
                     {
                         "x":  558,
                         "type":  "edit",
                         "var":  "",
                         "y":  198,
                         "w":  238,
                         "fmt":  "20",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  26
                     },
                     {
                         "x":  69,
                         "type":  "edit",
                         "var":  "",
                         "y":  212,
                         "w":  154,
                         "fmt":  "4",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  38
                     },
                     {
                         "x":  286,
                         "type":  "edit",
                         "var":  "",
                         "y":  212,
                         "w":  224,
                         "fmt":  "14",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  38
                     },
                     {
                         "x":  69,
                         "type":  "edit",
                         "var":  "",
                         "y":  226,
                         "w":  154,
                         "fmt":  "8",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  38
                     },
                     {
                         "x":  280,
                         "type":  "edit",
                         "var":  "",
                         "y":  226,
                         "w":  157,
                         "fmt":  "13",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  38
                     },
                     {
                         "x":  7,
                         "type":  "button",
                         "var":  "",
                         "y":  253,
                         "w":  154,
                         "fmt":  "\u0026Quitter",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  47
                     },
                     {
                         "x":  194,
                         "type":  "edit",
                         "var":  "",
                         "y":  26,
                         "w":  224,
                         "fmt":  "",
                         "name":  "nom_import",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  115
                     },
                     {
                         "x":  928,
                         "type":  "edit",
                         "var":  "",
                         "y":  57,
                         "w":  18,
                         "fmt":  "",
                         "name":  "tle_compte_solde",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  7
                     }
                 ],
    "taskId":  "179",
    "height":  281
}
-->

<details>
<summary><strong>Champs : 28 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 8,57 | TLE Nom | - | edit |
| 194,57 | TLE Prenom | - | edit |
| 323,57 | TLE Sexe | - | edit |
| 379,57 | TLE Age | - | edit |
| 496,57 | TLE Logement | - | edit |
| 430,57 | TLE Pays | - | edit |
| 43,187 | (sans nom) | - | edit |
| 173,186 | (sans nom) | - | edit |
| 301,187 | (sans nom) | - | edit |
| 432,186 | 6 | - | edit |
| 454,226 | (sans nom) | - | edit |
| 678,57 | (sans nom) | - | edit |
| 693,211 | (sans nom) | - | edit |
| 558,211 | (sans nom) | - | edit |
| 558,224 | (sans nom) | - | edit |
| 558,172 | (sans nom) | - | edit |
| 558,185 | (sans nom) | - | edit |
| 8,2 | 30 | - | edit |
| 278,6 | 100 | - | edit |
| 939,6 | WWW DD MMM YYYYT | - | edit |
| 8,10 | 30 | - | edit |
| 558,198 | 20 | - | edit |
| 69,212 | 4 | - | edit |
| 286,212 | 14 | - | edit |
| 69,226 | 8 | - | edit |
| 280,226 | 13 | - | edit |
| 194,26 | nom_import | - | edit |
| 928,57 | tle_compte_solde | - | edit |

</details>

<details>
<summary><strong>Boutons : 3 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Voir | 978,177 | Bouton fonctionnel |
| Impression | 978,204 | Bouton fonctionnel |
| Quitter | 7,253 | Quitte le programme |

</details>

---

#### <a id="ecran-t2"></a>179.1 - Detail
**Tache** : [179.1](#t2) | **Type** : MDI | **Dimensions** : 768 x 262 DLU
**Bloc** : Traitement | **Titre IDE** : Detail

<!-- FORM-DATA:
{
    "width":  768,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  7,
                         "type":  "label",
                         "var":  "",
                         "y":  24,
                         "w":  757,
                         "fmt":  "",
                         "name":  "",
                         "h":  95,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  18,
                         "type":  "label",
                         "var":  "",
                         "y":  31,
                         "w":  94,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "N° adhérent",
                         "parent":  3
                     },
                     {
                         "x":  8,
                         "type":  "line",
                         "var":  "",
                         "y":  41,
                         "w":  752,
                         "fmt":  "",
                         "name":  "",
                         "h":  0,
                         "color":  "",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  18,
                         "type":  "label",
                         "var":  "",
                         "y":  47,
                         "w":  88,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Naissance",
                         "parent":  3
                     },
                     {
                         "x":  18,
                         "type":  "label",
                         "var":  "",
                         "y":  65,
                         "w":  64,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Identité",
                         "parent":  3
                     },
                     {
                         "x":  8,
                         "type":  "line",
                         "var":  "",
                         "y":  76,
                         "w":  752,
                         "fmt":  "",
                         "name":  "",
                         "h":  0,
                         "color":  "",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  18,
                         "type":  "label",
                         "var":  "",
                         "y":  83,
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
                         "y":  236,
                         "w":  766,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  79,
                         "type":  "edit",
                         "var":  "",
                         "y":  8,
                         "w":  37,
                         "fmt":  "",
                         "name":  "GMC Titre",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  131,
                         "type":  "edit",
                         "var":  "",
                         "y":  30,
                         "w":  26,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  166,
                         "type":  "edit",
                         "var":  "",
                         "y":  30,
                         "w":  123,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  298,
                         "type":  "edit",
                         "var":  "",
                         "y":  29,
                         "w":  26,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  333,
                         "type":  "edit",
                         "var":  "",
                         "y":  29,
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
                         "y":  47,
                         "w":  132,
                         "fmt":  "DD/MM/YYYYZ",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  254,
                         "type":  "edit",
                         "var":  "",
                         "y":  47,
                         "w":  440,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  701,
                         "type":  "edit",
                         "var":  "",
                         "y":  47,
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
                         "y":  65,
                         "w":  22,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  142,
                         "type":  "edit",
                         "var":  "",
                         "y":  65,
                         "w":  347,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  494,
                         "type":  "edit",
                         "var":  "",
                         "y":  65,
                         "w":  120,
                         "fmt":  "DD/MM/YYYYZ",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  624,
                         "type":  "edit",
                         "var":  "",
                         "y":  65,
                         "w":  120,
                         "fmt":  "DD/MM/YYYYZ",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  117,
                         "type":  "edit",
                         "var":  "",
                         "y":  94,
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
                         "y":  105,
                         "w":  123,
                         "fmt":  "",
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
                         "y":  105,
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
                         "y":  83,
                         "w":  123,
                         "fmt":  "",
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
                         "y":  83,
                         "w":  347,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  116,
                         "type":  "edit",
                         "var":  "",
                         "y":  8,
                         "w":  597,
                         "fmt":  "55",
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
                         "y":  239,
                         "w":  154,
                         "fmt":  "\u0026Quitter",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  26
                     },
                     {
                         "x":  0,
                         "type":  "subform",
                         "var":  "",
                         "y":  119,
                         "w":  768,
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
                         "y":  199,
                         "w":  768,
                         "fmt":  "",
                         "name":  "consult prestations",
                         "h":  38,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "179.1",
    "height":  262
}
-->

<details>
<summary><strong>Champs : 18 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 79,8 | GMC Titre | - | edit |
| 131,30 | (sans nom) | - | edit |
| 166,30 | (sans nom) | - | edit |
| 298,29 | (sans nom) | - | edit |
| 333,29 | (sans nom) | - | edit |
| 117,47 | DD/MM/YYYYZ | - | edit |
| 254,47 | (sans nom) | - | edit |
| 701,47 | (sans nom) | - | edit |
| 117,65 | (sans nom) | - | edit |
| 142,65 | (sans nom) | - | edit |
| 494,65 | DD/MM/YYYYZ | - | edit |
| 624,65 | DD/MM/YYYYZ | - | edit |
| 117,94 | (sans nom) | - | edit |
| 117,105 | (sans nom) | - | edit |
| 248,105 | (sans nom) | - | edit |
| 117,83 | (sans nom) | - | edit |
| 248,83 | (sans nom) | - | edit |
| 116,8 | 55 | - | edit |

</details>

<details>
<summary><strong>Boutons : 1 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Quitter | 8,239 | Quitte le programme |

</details>

---

#### <a id="ecran-t3"></a>179.1.1 - consultation hebergement
**Tache** : [179.1.1](#t3) | **Type** : Modal | **Dimensions** : 768 x 78 DLU
**Bloc** : Traitement | **Titre IDE** : consultation hebergement

<!-- FORM-DATA:
{
    "width":  768,
    "vFactor":  8,
    "type":  "Modal",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  6,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "110",
                         "w":  762,
                         "y":  0,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  12,
                         "h":  73,
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
                         "x":  170,
                         "type":  "edit",
                         "var":  "",
                         "y":  14,
                         "w":  120,
                         "fmt":  "DD/MM/YYYYZ",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  298,
                         "type":  "edit",
                         "var":  "",
                         "y":  14,
                         "w":  30,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  334,
                         "type":  "edit",
                         "var":  "",
                         "y":  14,
                         "w":  120,
                         "fmt":  "DD/MM/YYYYZ",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  459,
                         "type":  "edit",
                         "var":  "",
                         "y":  14,
                         "w":  30,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  498,
                         "type":  "edit",
                         "var":  "",
                         "y":  14,
                         "w":  232,
                         "fmt":  "20",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  13,
                         "type":  "edit",
                         "var":  "",
                         "y":  14,
                         "w":  142,
                         "fmt":  "12",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     }
                 ],
    "taskId":  "179.1.1",
    "height":  78
}
-->

<details>
<summary><strong>Champs : 6 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 170,14 | DD/MM/YYYYZ | - | edit |
| 298,14 | (sans nom) | - | edit |
| 334,14 | DD/MM/YYYYZ | - | edit |
| 459,14 | (sans nom) | - | edit |
| 498,14 | 20 | - | edit |
| 13,14 | 12 | - | edit |

</details>

---

#### <a id="ecran-t4"></a>179.1.2 - consult prestations
**Tache** : [179.1.2](#t4) | **Type** : Modal | **Dimensions** : 759 x 37 DLU
**Bloc** : Traitement | **Titre IDE** : consult prestations

<!-- FORM-DATA:
{
    "width":  759,
    "vFactor":  8,
    "type":  "Modal",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  189,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "110",
                         "w":  391,
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
                                          "w":  111
                                      },
                                      {
                                          "title":  "Libellé",
                                          "layer":  2,
                                          "w":  245
                                      }
                                  ],
                         "rows":  2
                     },
                     {
                         "x":  221,
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
                         "x":  306,
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
    "taskId":  "179.1.2",
    "height":  37
}
-->

<details>
<summary><strong>Champs : 2 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 221,14 | (sans nom) | - | edit |
| 306,14 | (sans nom) | - | edit |

</details>

## 9. NAVIGATION

### 9.1 Enchainement des ecrans

```mermaid
flowchart TD
    START([Entree])
    style START fill:#3fb950
    VF1[179 Secretaire]
    style VF1 fill:#58a6ff
    VF2[179.1 Detail]
    style VF2 fill:#58a6ff
    VF3[179.1.1 consultation heberg...]
    style VF3 fill:#58a6ff
    VF4[179.1.2 consult prestations]
    style VF4 fill:#58a6ff
    EXT389[IDE 389 Recuperation d...]
    style EXT389 fill:#3fb950
    EXT180[IDE 180 Imprim AVPBDR ...]
    style EXT180 fill:#3fb950
    FIN([Sortie])
    style FIN fill:#f85149
    START --> VF1
    VF1 -->|Recuperation donnees| EXT389
    VF1 -->|Impression ticket/document| EXT180
    EXT180 --> FIN
```

**Detail par enchainement :**

| Depuis | Action | Vers | Retour |
|--------|--------|------|--------|
| Secretaire | Recuperation donnees | [Recuperation du titre (IDE 389)](PBP-IDE-389.md) | Retour ecran |
| Secretaire | Impression ticket/document | [  Imprim AVPBDR secretaire (IDE 180)](PBP-IDE-180.md) | Retour ecran |

### 9.3 Structure hierarchique (4 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **179.1** | [**Secretaire** (179)](#t1) [mockup](#ecran-t1) | MDI | 1162x281 | Traitement |
| 179.1.1 | [Detail (179.1)](#t2) [mockup](#ecran-t2) | MDI | 768x262 | |
| 179.1.2 | [consultation hebergement (179.1.1)](#t3) [mockup](#ecran-t3) | Modal | 768x78 | |
| 179.1.3 | [consult prestations (179.1.2)](#t4) [mockup](#ecran-t4) | Modal | 759x37 | |

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

### Tables utilisees (6)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 31 | gm-complet_______gmc |  | DB | R |   |   | 1 |
| 33 | prestations______pre | Prestations/services vendus | DB | R |   |   | 1 |
| 34 | hebergement______heb | Hebergement (chambres) | DB | R |   |   | 1 |
| 118 | tables_imports |  | DB | R |   |   | 1 |
| 135 | libelle_prestation | Prestations/services vendus | DB |   |   | L | 1 |
| 619 | tempo_userlist | Table temporaire ecran | TMP |   |   | L | 1 |

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
<summary>Table 118 - tables_imports (R) - 1 usages</summary>

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
| J | >Libellé Sélection du Solde* | R | Unicode |
| K | >Soldé,Non_soldé,Tous | R | Unicode |
| L | >Tri Nom/Filiation | R | Logical |
| M | P.I Heure depart Village | R | Logical |
| N | w0_TitreEcran | R | Alpha |
| O | v.Ordre Tri | R | Alpha |
| P | b_Ecran | R | Alpha |
| Q | b_Imprim | R | Alpha |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (1)

Variables recues du programme appelant ([  Liste CLients arrivant (IDE 156)](PBP-IDE-156.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| M | P.I Heure depart Village | Logical | - |

### 11.2 Variables de session (1)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| O | v.Ordre Tri | Alpha | - |

### 11.3 Autres (15)

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
| J | >Libellé Sélection du Solde* | Unicode | - |
| K | >Soldé,Non_soldé,Tous | Unicode | - |
| L | >Tri Nom/Filiation | Logical | - |
| N | w0_TitreEcran | Alpha | 1x refs |
| P | b_Ecran | Alpha | - |
| Q | b_Imprim | Alpha | - |

<details>
<summary>Toutes les 17 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| P0 | **M** | P.I Heure depart Village | Logical |
| V. | **O** | v.Ordre Tri | Alpha |
| Autre | **A** | >CodeEcran | Numeric |
| Autre | **B** | >Date | Date |
| Autre | **C** | >Heure | Alpha |
| Autre | **D** | >CodeListe | Alpha |
| Autre | **E** | >TopListe | Alpha |
| Autre | **F** | >Logement | Alpha |
| Autre | **G** | >TitreMaman | Alpha |
| Autre | **H** | >Total | Numeric |
| Autre | **I** | >NbSelect | Numeric |
| Autre | **J** | >Libellé Sélection du Solde* | Unicode |
| Autre | **K** | >Soldé,Non_soldé,Tous | Unicode |
| Autre | **L** | >Tri Nom/Filiation | Logical |
| Autre | **N** | w0_TitreEcran | Alpha |
| Autre | **P** | b_Ecran | Alpha |
| Autre | **Q** | b_Imprim | Alpha |

</details>

## 12. EXPRESSIONS

**27 / 27 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONCATENATION | 2 | 0 |
| CONDITION | 12 | 3 |
| CONSTANTE | 2 | 0 |
| DATE | 1 | 0 |
| OTHER | 8 | 0 |
| REFERENCE_VG | 2 | 0 |

### 12.2 Expressions cles par type

#### CONCATENATION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 3 | `Trim (>TitreMaman [G])&' '&Trim (>Libellé Sélection du ... [J])` | - |
| CONCATENATION | 17 | `Str (>NbSelect [I],'4')&' '&MlsTrans ('selectionnes sur')&' '&Str (>Total [H],'4')&' - '&Trim([CQ])` | - |

#### CONDITION (12 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 25 | `IF([CO]<>'T',29.75,25.75)` | [RM-003](#rm-RM-003) |
| CONDITION | 22 | `IF(VG88 AND [CN],TStr([CL],'HHhMMZ'),[Y])` | [RM-002](#rm-RM-002) |
| CONDITION | 21 | `IF([CH],[CI]&[CJ]&Str([AE],'3P0'),w0_TitreEcran [N]&Str([AE],'3P0'))` | [RM-001](#rm-RM-001) |
| CONDITION | 20 | `VG44>1` | - |
| CONDITION | 13 | `[AB]<>''` | - |
| ... | | *+7 autres* | |

#### CONSTANTE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 15 | `'&Imprimante'` | - |
| CONSTANTE | 14 | `'&Ecran'` | - |

#### DATE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| DATE | 5 | `Date ()` | - |

#### OTHER (8 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 16 | `[AG]` | - |
| OTHER | 12 | `MlsTrans ('Liste Blanche')` | - |
| OTHER | 19 | `[CC]` | - |
| OTHER | 18 | `GetParam ('VILLAGE')` | - |
| OTHER | 6 | `MlsTrans ('Bebe')` | - |
| ... | | *+3 autres* | |

#### REFERENCE_VG (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 4 | `VG2` | - |
| REFERENCE_VG | 2 | `VG1` | - |

### 12.3 Toutes les expressions (27)

<details>
<summary>Voir les 27 expressions</summary>

#### CONCATENATION (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 17 | `Str (>NbSelect [I],'4')&' '&MlsTrans ('selectionnes sur')&' '&Str (>Total [H],'4')&' - '&Trim([CQ])` |
| 3 | `Trim (>TitreMaman [G])&' '&Trim (>Libellé Sélection du ... [J])` |

#### CONDITION (12)

| IDE | Expression Decodee |
|-----|-------------------|
| 21 | `IF([CH],[CI]&[CJ]&Str([AE],'3P0'),w0_TitreEcran [N]&Str([AE],'3P0'))` |
| 22 | `IF(VG88 AND [CN],TStr([CL],'HHhMMZ'),[Y])` |
| 23 | `IF(VG88 AND [CN],'Libération logement','Départ village')` |
| 25 | `IF([CO]<>'T',29.75,25.75)` |
| 26 | `IF([CO]<>'T',31.125,27.125)` |
| 7 | `[Z]='B'` |
| 9 | `[AC]='R'` |
| 11 | `[AA]<>''` |
| 13 | `[AB]<>''` |
| 20 | `VG44>1` |
| 27 | `[CO]='T'` |
| 24 | `CndRange(Trim([CQ])<>'' AND [CO]<>'T',IF([CO]='N','X',''))` |

#### CONSTANTE (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 14 | `'&Ecran'` |
| 15 | `'&Imprimante'` |

#### DATE (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 5 | `Date ()` |

#### OTHER (8)

| IDE | Expression Decodee |
|-----|-------------------|
| 1 | `GetParam ('SOCIETE')` |
| 6 | `MlsTrans ('Bebe')` |
| 8 | `MlsTrans ('Retour Circuit')` |
| 10 | `MlsTrans ('Millesia')` |
| 12 | `MlsTrans ('Liste Blanche')` |
| 16 | `[AG]` |
| 18 | `GetParam ('VILLAGE')` |
| 19 | `[CC]` |

#### REFERENCE_VG (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 2 | `VG1` |
| 4 | `VG2` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [  Liste CLients arrivant (IDE 156)](PBP-IDE-156.md) -> **Affichage AVPBDR secretaire (IDE 179)**

Main -> ... -> [  Liste Clients present (IDE 162)](PBP-IDE-162.md) -> **Affichage AVPBDR secretaire (IDE 179)**

Main -> ... -> [  Liste CLients depart (IDE 168)](PBP-IDE-168.md) -> **Affichage AVPBDR secretaire (IDE 179)**

Main -> ... -> [Liste CLients AVPBDR (IDE 174)](PBP-IDE-174.md) -> **Affichage AVPBDR secretaire (IDE 179)**

Main -> ... -> [  Liste present personnel plan (IDE 227)](PBP-IDE-227.md) -> **Affichage AVPBDR secretaire (IDE 179)**

Main -> ... -> [  Liste personnels AVPBDR (IDE 234)](PBP-IDE-234.md) -> **Affichage AVPBDR secretaire (IDE 179)**

```mermaid
graph LR
    T179[179 Affichage AVPBDR s...]
    style T179 fill:#58a6ff
    CC161[161 Liste des presents]
    style CC161 fill:#8b5cf6
    CC173[173 Liste des Absents]
    style CC173 fill:#8b5cf6
    CC167[167 Liste des departs]
    style CC167 fill:#8b5cf6
    CC172[172 Liste des partants]
    style CC172 fill:#8b5cf6
    CC160[160 Liste des arrivees]
    style CC160 fill:#8b5cf6
    CC155[155 Liste des arrivants]
    style CC155 fill:#8b5cf6
    CC162[162 Liste Clients present]
    style CC162 fill:#3fb950
    CC156[156 Liste CLients arri...]
    style CC156 fill:#3fb950
    CC227[227 Liste present pers...]
    style CC227 fill:#3fb950
    CC174[174 Liste CLients AVPBDR]
    style CC174 fill:#3fb950
    CC168[168 Liste CLients depart]
    style CC168 fill:#3fb950
    CC155 --> CC156
    CC161 --> CC156
    CC167 --> CC156
    CC160 --> CC156
    CC172 --> CC156
    CC173 --> CC156
    CC155 --> CC162
    CC161 --> CC162
    CC167 --> CC162
    CC160 --> CC162
    CC172 --> CC162
    CC173 --> CC162
    CC155 --> CC168
    CC161 --> CC168
    CC167 --> CC168
    CC160 --> CC168
    CC172 --> CC168
    CC173 --> CC168
    CC155 --> CC174
    CC161 --> CC174
    CC167 --> CC174
    CC160 --> CC174
    CC172 --> CC174
    CC173 --> CC174
    CC155 --> CC227
    CC161 --> CC227
    CC167 --> CC227
    CC160 --> CC227
    CC172 --> CC227
    CC173 --> CC227
    CC156 --> T179
    CC162 --> T179
    CC168 --> T179
    CC174 --> T179
    CC227 --> T179
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [156](PBP-IDE-156.md) |   Liste CLients arrivant | 1 |
| [162](PBP-IDE-162.md) |   Liste Clients present | 1 |
| [168](PBP-IDE-168.md) |   Liste CLients depart | 1 |
| [174](PBP-IDE-174.md) | Liste CLients AVPBDR | 1 |
| [227](PBP-IDE-227.md) |   Liste present personnel plan | 1 |
| [234](PBP-IDE-234.md) |   Liste personnels AVPBDR | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T179[179 Affichage AVPBDR s...]
    style T179 fill:#58a6ff
    C389[389 Recuperation du titre]
    T179 --> C389
    style C389 fill:#3fb950
    C180[180 Imprim AVPBDR secr...]
    T179 --> C180
    style C180 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [389](PBP-IDE-389.md) | Recuperation du titre | 2 | Recuperation donnees |
| [180](PBP-IDE-180.md) |   Imprim AVPBDR secretaire | 1 | Impression ticket/document |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 144 | Programme compact |
| Expressions | 27 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 2 | Peu de dependances |
| Ecrans visibles | 4 | Quelques ecrans |
| Code desactive | 0% (0 / 144) | Code sain |
| Regles metier | 3 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (4 taches: 4 ecrans, 0 traitement)

- **Strategie** : 4 composant(s) UI (Razor/React) avec formulaires et validation.
- 2 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| [Recuperation du titre (IDE 389)](PBP-IDE-389.md) | Sous-programme | 2x | Haute - Recuperation donnees |
| [  Imprim AVPBDR secretaire (IDE 180)](PBP-IDE-180.md) | Sous-programme | 1x | Normale - Impression ticket/document |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 15:40*
