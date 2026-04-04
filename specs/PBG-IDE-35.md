# PBG IDE 35 - Browse - IMPORT Troncon   IMT

> **Analyse**: Phases 1-4 2026-02-03 01:21 -> 01:22 (37s) | Assemblage 01:22
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBG |
| IDE Position | 35 |
| Nom Programme | Browse - IMPORT Troncon   IMT |
| Fichier source | `Prg_35.xml` |
| Domaine metier | General |
| Taches | 1 (1 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 20 |

## 2. DESCRIPTION FONCTIONNELLE

**Browse - IMPORT Troncon   IMT** assure la gestion complete de ce processus, accessible depuis [Dispatch (IDE 96)](PBG-IDE-96.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

**Donnees modifiees** : 1 tables en ecriture (temp_recap_sessions).

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>35 - Browse - IMPORT Troncon   IMT [[ECRAN]](#ecran-t1)

**Role** : Traitement : Browse - IMPORT Troncon   IMT.
**Ecran** : 780 x 208 DLU (MDI) | [Voir mockup](#ecran-t1)
**Delegue a** : [Browse - GM Handicap (IDE 42)](PBG-IDE-42.md), [Browse - Lit Matrimoniaux (IDE 43)](PBG-IDE-43.md), [Browse - COMMENTAIRE      COM (IDE 44)](PBG-IDE-44.md)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Dispatch (IDE 96)](PBG-IDE-96.md)
- **Appelle**: 20 programmes | **Tables**: 1 (W:1 R:0 L:0) | **Taches**: 1 | **Expressions**: 2

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 1)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 35 | 35 | Browse - IMPORT Troncon   IMT | MDI | 780 | 208 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>35 - Browse - IMPORT Troncon   IMT
**Tache** : [35](#t1) | **Type** : MDI | **Dimensions** : 780 x 208 DLU
**Bloc** : Traitement | **Titre IDE** : Browse - IMPORT Troncon   IMT

<!-- FORM-DATA:
{
    "width":  780,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  3,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "110",
                         "w":  161,
                         "y":  2,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  14,
                         "h":  168,
                         "cols":  [
                                      {
                                          "title":  "IMT Username",
                                          "layer":  1,
                                          "w":  66
                                      },
                                      {
                                          "title":  "IMT N° Ressource",
                                          "layer":  2,
                                          "w":  79
                                      }
                                  ],
                         "rows":  2
                     },
                     {
                         "x":  368,
                         "type":  "label",
                         "var":  "",
                         "y":  2,
                         "w":  83,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "IMT Date Arrivee Vol",
                         "parent":  null
                     },
                     {
                         "x":  198,
                         "type":  "label",
                         "var":  "",
                         "y":  4,
                         "w":  90,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "IMT Type Prod PP/VO",
                         "parent":  null
                     },
                     {
                         "x":  368,
                         "type":  "label",
                         "var":  "",
                         "y":  16,
                         "w":  83,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "IMT Heure Arrive Vol",
                         "parent":  null
                     },
                     {
                         "x":  198,
                         "type":  "label",
                         "var":  "",
                         "y":  18,
                         "w":  90,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "IMT Code Vol Club",
                         "parent":  null
                     },
                     {
                         "x":  368,
                         "type":  "label",
                         "var":  "",
                         "y":  28,
                         "w":  83,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "IMT IATA Arrivee",
                         "parent":  null
                     },
                     {
                         "x":  198,
                         "type":  "label",
                         "var":  "",
                         "y":  32,
                         "w":  90,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "IMT Type Transport",
                         "parent":  null
                     },
                     {
                         "x":  368,
                         "type":  "label",
                         "var":  "",
                         "y":  42,
                         "w":  83,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "IMT Categorie Tarif",
                         "parent":  null
                     },
                     {
                         "x":  198,
                         "type":  "label",
                         "var":  "",
                         "y":  44,
                         "w":  90,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "IMT Code A/R/I",
                         "parent":  null
                     },
                     {
                         "x":  368,
                         "type":  "label",
                         "var":  "",
                         "y":  54,
                         "w":  83,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "IMT Classe",
                         "parent":  null
                     },
                     {
                         "x":  198,
                         "type":  "label",
                         "var":  "",
                         "y":  56,
                         "w":  90,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "IMT Date Depart Vol",
                         "parent":  null
                     },
                     {
                         "x":  198,
                         "type":  "label",
                         "var":  "",
                         "y":  70,
                         "w":  90,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "IMT Heure Depart Vol",
                         "parent":  null
                     },
                     {
                         "x":  368,
                         "type":  "label",
                         "var":  "",
                         "y":  70,
                         "w":  83,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "IMT N° PNR",
                         "parent":  null
                     },
                     {
                         "x":  198,
                         "type":  "label",
                         "var":  "",
                         "y":  84,
                         "w":  90,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "IMT N° Vol",
                         "parent":  null
                     },
                     {
                         "x":  368,
                         "type":  "label",
                         "var":  "",
                         "y":  84,
                         "w":  83,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "IMT Compagnie",
                         "parent":  null
                     },
                     {
                         "x":  198,
                         "type":  "label",
                         "var":  "",
                         "y":  98,
                         "w":  90,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "IMT IATA Depart",
                         "parent":  null
                     },
                     {
                         "x":  368,
                         "type":  "label",
                         "var":  "",
                         "y":  100,
                         "w":  83,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "IMT Affrêteur",
                         "parent":  null
                     },
                     {
                         "x":  6,
                         "type":  "edit",
                         "var":  "",
                         "y":  16,
                         "w":  52,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  72,
                         "type":  "edit",
                         "var":  "",
                         "y":  16,
                         "w":  30,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  296,
                         "type":  "edit",
                         "var":  "",
                         "y":  4,
                         "w":  13,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  296,
                         "type":  "edit",
                         "var":  "",
                         "y":  18,
                         "w":  41,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  296,
                         "type":  "edit",
                         "var":  "",
                         "y":  32,
                         "w":  18,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  296,
                         "type":  "edit",
                         "var":  "",
                         "y":  44,
                         "w":  13,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  296,
                         "type":  "edit",
                         "var":  "",
                         "y":  56,
                         "w":  63,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  296,
                         "type":  "edit",
                         "var":  "",
                         "y":  70,
                         "w":  52,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  296,
                         "type":  "edit",
                         "var":  "",
                         "y":  84,
                         "w":  63,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  296,
                         "type":  "edit",
                         "var":  "",
                         "y":  98,
                         "w":  41,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  458,
                         "type":  "edit",
                         "var":  "",
                         "y":  2,
                         "w":  63,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  458,
                         "type":  "edit",
                         "var":  "",
                         "y":  16,
                         "w":  52,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  458,
                         "type":  "edit",
                         "var":  "",
                         "y":  28,
                         "w":  41,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  458,
                         "type":  "edit",
                         "var":  "",
                         "y":  42,
                         "w":  41,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  458,
                         "type":  "edit",
                         "var":  "",
                         "y":  54,
                         "w":  24,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  458,
                         "type":  "edit",
                         "var":  "",
                         "y":  70,
                         "w":  74,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  458,
                         "type":  "edit",
                         "var":  "",
                         "y":  84,
                         "w":  58,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  458,
                         "type":  "edit",
                         "var":  "",
                         "y":  100,
                         "w":  41,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  680,
                         "type":  "button",
                         "var":  "",
                         "y":  7,
                         "w":  100,
                         "fmt":  "Voyage CAFIL007",
                         "name":  "",
                         "h":  14,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  680,
                         "type":  "button",
                         "var":  "",
                         "y":  24,
                         "w":  100,
                         "fmt":  "GM Rech CAFIL008",
                         "name":  "",
                         "h":  14,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  680,
                         "type":  "button",
                         "var":  "",
                         "y":  41,
                         "w":  100,
                         "fmt":  "GM Comp CAFIL009",
                         "name":  "",
                         "h":  14,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  680,
                         "type":  "button",
                         "var":  "",
                         "y":  58,
                         "w":  100,
                         "fmt":  "Prestation CAFIL011",
                         "name":  "",
                         "h":  14,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  680,
                         "type":  "button",
                         "var":  "",
                         "y":  75,
                         "w":  100,
                         "fmt":  "Heberg CAFIL012",
                         "name":  "",
                         "h":  14,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  680,
                         "type":  "button",
                         "var":  "",
                         "y":  92,
                         "w":  100,
                         "fmt":  "GM Client CAFIL014",
                         "name":  "",
                         "h":  14,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  680,
                         "type":  "button",
                         "var":  "",
                         "y":  109,
                         "w":  100,
                         "fmt":  "Compte CAFIL025",
                         "name":  "",
                         "h":  14,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  680,
                         "type":  "button",
                         "var":  "",
                         "y":  126,
                         "w":  100,
                         "fmt":  "Logem CAFIL086",
                         "name":  "",
                         "h":  14,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  680,
                         "type":  "button",
                         "var":  "",
                         "y":  143,
                         "w":  100,
                         "fmt":  "Ages CAFIL091",
                         "name":  "",
                         "h":  14,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  680,
                         "type":  "button",
                         "var":  "",
                         "y":  160,
                         "w":  100,
                         "fmt":  "Circuit CAFIL105",
                         "name":  "",
                         "h":  14,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  2,
                         "type":  "button",
                         "var":  "",
                         "y":  178,
                         "w":  100,
                         "fmt":  "Valid CAFIL109",
                         "name":  "",
                         "h":  14,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  115,
                         "type":  "button",
                         "var":  "",
                         "y":  178,
                         "w":  100,
                         "fmt":  "ASD CAFIL111",
                         "name":  "",
                         "h":  14,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  239,
                         "type":  "button",
                         "var":  "",
                         "y":  178,
                         "w":  100,
                         "fmt":  "Lib Prest CAFIL113",
                         "name":  "",
                         "h":  14,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  365,
                         "type":  "button",
                         "var":  "",
                         "y":  178,
                         "w":  100,
                         "fmt":  "Circuit CAFIL146",
                         "name":  "",
                         "h":  14,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  485,
                         "type":  "button",
                         "var":  "",
                         "y":  178,
                         "w":  100,
                         "fmt":  "Lit CAFIL231",
                         "name":  "",
                         "h":  14,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  2,
                         "type":  "button",
                         "var":  "",
                         "y":  192,
                         "w":  100,
                         "fmt":  "Vol CAFIL110",
                         "name":  "",
                         "h":  14,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  115,
                         "type":  "button",
                         "var":  "",
                         "y":  192,
                         "w":  100,
                         "fmt":  "Vol CAFIL112",
                         "name":  "",
                         "h":  14,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  239,
                         "type":  "button",
                         "var":  "",
                         "y":  192,
                         "w":  100,
                         "fmt":  "Tronçon CAFIL145",
                         "name":  "",
                         "h":  14,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  365,
                         "type":  "button",
                         "var":  "",
                         "y":  192,
                         "w":  100,
                         "fmt":  "Comment CAFIL149",
                         "name":  "",
                         "h":  14,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  485,
                         "type":  "button",
                         "var":  "",
                         "y":  192,
                         "w":  100,
                         "fmt":  "Handicap CAFIL237",
                         "name":  "",
                         "h":  14,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "35",
    "height":  208
}
-->

<details>
<summary><strong>Champs : 18 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 6,16 | (sans nom) | - | edit |
| 72,16 | (sans nom) | - | edit |
| 296,4 | (sans nom) | - | edit |
| 296,18 | (sans nom) | - | edit |
| 296,32 | (sans nom) | - | edit |
| 296,44 | (sans nom) | - | edit |
| 296,56 | (sans nom) | - | edit |
| 296,70 | (sans nom) | - | edit |
| 296,84 | (sans nom) | - | edit |
| 296,98 | (sans nom) | - | edit |
| 458,2 | (sans nom) | - | edit |
| 458,16 | (sans nom) | - | edit |
| 458,28 | (sans nom) | - | edit |
| 458,42 | (sans nom) | - | edit |
| 458,54 | (sans nom) | - | edit |
| 458,70 | (sans nom) | - | edit |
| 458,84 | (sans nom) | - | edit |
| 458,100 | (sans nom) | - | edit |

</details>

<details>
<summary><strong>Boutons : 20 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Voyage CAFIL007 | 680,7 | Appel [Browse - VOYAGES          VOY (IDE 61)](PBG-IDE-61.md) |
| GM Rech CAFIL008 | 680,24 | Appel [Browse - GM RECHERCHE     GMR (IDE 60)](PBG-IDE-60.md) |
| GM Comp CAFIL009 | 680,41 | Appel [Browse - GM COMPLET       GMC (IDE 59)](PBG-IDE-59.md) |
| Prestation CAFIL011 | 680,58 | Appel [Browse - Libelle Prestation (IDE 47)](PBG-IDE-47.md) |
| Heberg CAFIL012 | 680,75 | Appel [Browse - HEBERGEMENT      HEB (IDE 57)](PBG-IDE-57.md) |
| GM Client CAFIL014 | 680,92 | Identification du client |
| Compte CAFIL025 | 680,109 | Appel [Browse - Comptes (IDE 55)](PBG-IDE-55.md) |
| Logem CAFIL086 | 680,126 | Appel [Browse - LOGEMENT Codes (IDE 54)](PBG-IDE-54.md) |
| Ages CAFIL091 | 680,143 | Appel [Browse - VOYAGES          VOY (IDE 61)](PBG-IDE-61.md) |
| Circuit CAFIL105 | 680,160 | Appel [Browse - HEB CIRCUIT      HCI (IDE 45)](PBG-IDE-45.md) |
| Valid CAFIL109 | 2,178 | Appel [Browse - Validation       VAL (IDE 51)](PBG-IDE-51.md) |
| ASD CAFIL111 | 115,178 | Bouton fonctionnel |
| Lib Prest CAFIL113 | 239,178 | Bouton fonctionnel |
| Circuit CAFIL146 | 365,178 | Appel [Browse - HEB CIRCUIT      HCI (IDE 45)](PBG-IDE-45.md) |
| Lit CAFIL231 | 485,178 | Bouton fonctionnel |
| Vol CAFIL110 | 2,192 | Bouton fonctionnel |
| Vol CAFIL112 | 115,192 | Bouton fonctionnel |
| Tronçon CAFIL145 | 239,192 | Bouton fonctionnel |
| Comment CAFIL149 | 365,192 | Appel [Browse - COMMENTAIRE      COM (IDE 44)](PBG-IDE-44.md) |
| Handicap CAFIL237 | 485,192 | Appel [Browse - GM Handicap (IDE 42)](PBG-IDE-42.md) |

</details>

## 9. NAVIGATION

Ecran unique: **Browse - IMPORT Troncon   IMT**

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **35.1** | [**Browse - IMPORT Troncon   IMT** (35)](#t1) [mockup](#ecran-t1) | MDI | 780x208 | Traitement |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Traitement principal]
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

### Tables utilisees (1)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 576 | temp_recap_sessions | Sessions de caisse | TMP |   | **W** |   | 1 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 576 - temp_recap_sessions (**W**) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | ParamUserName | W | Alpha |
| B | ParamRessource | W | Numeric |

</details>

## 11. VARIABLES

### 11.1 Autres (2)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | ParamUserName | Alpha | 1x refs |
| B | ParamRessource | Numeric | 1x refs |

## 12. EXPRESSIONS

**2 / 2 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| OTHER | 2 | 0 |

### 12.2 Expressions cles par type

#### OTHER (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 2 | `ParamRessource [B]` | - |
| OTHER | 1 | `ParamUserName [A]` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Dispatch (IDE 96)](PBG-IDE-96.md) -> **Browse - IMPORT Troncon   IMT (IDE 35)**

```mermaid
graph LR
    T35[35 Browse - IMPORT Tro...]
    style T35 fill:#58a6ff
    CC94[94 Module Sejours Call...]
    style CC94 fill:#8b5cf6
    CC391[391 Module Sejours Sub...]
    style CC391 fill:#8b5cf6
    CC95[95 Contrôle des inform...]
    style CC95 fill:#f59e0b
    CC96[96 Dispatch]
    style CC96 fill:#3fb950
    CC95 --> CC96
    CC94 --> CC95
    CC391 --> CC95
    CC96 --> T35
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [96](PBG-IDE-96.md) | Dispatch | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T35[35 Browse - IMPORT Tro...]
    style T35 fill:#58a6ff
    C42[42 Browse - GM Handicap]
    T35 --> C42
    style C42 fill:#3fb950
    C43[43 Browse - Lit Matrim...]
    T35 --> C43
    style C43 fill:#3fb950
    C44[44 Browse - COMMENTAIR...]
    T35 --> C44
    style C44 fill:#3fb950
    C45[45 Browse - HEB CIRCUI...]
    T35 --> C45
    style C45 fill:#3fb950
    C46[46 Browse - TRONCON TRO]
    T35 --> C46
    style C46 fill:#3fb950
    C47[47 Browse - Libelle Pr...]
    T35 --> C47
    style C47 fill:#3fb950
    C48[48 Browse - Groupe Arr...]
    T35 --> C48
    style C48 fill:#3fb950
    C49[49 Browse - New ASD]
    T35 --> C49
    style C49 fill:#3fb950
    C50[50 Browse - Code Vol VOT]
    T35 --> C50
    style C50 fill:#3fb950
    C51[51 Browse - Validation...]
    T35 --> C51
    style C51 fill:#3fb950
    C52[52 Browse - Code Circuit]
    T35 --> C52
    style C52 fill:#3fb950
    C53[53 Browse - Tables VIL...]
    T35 --> C53
    style C53 fill:#3fb950
    C54[54 Browse - LOGEMENT C...]
    T35 --> C54
    style C54 fill:#3fb950
    C55[55 Browse - Comptes]
    T35 --> C55
    style C55 fill:#3fb950
    C56[56 Browse - CLIENT CLI]
    T35 --> C56
    style C56 fill:#3fb950
    C57[57 Browse - HEBERGEMEN...]
    T35 --> C57
    style C57 fill:#3fb950
    C58[58 Browse - PRESTATION...]
    T35 --> C58
    style C58 fill:#3fb950
    C59[59 Browse - GM COMPLET...]
    T35 --> C59
    style C59 fill:#3fb950
    C60[60 Browse - GM RECHERC...]
    T35 --> C60
    style C60 fill:#3fb950
    C61[61 Browse - VOYAGES VOY]
    T35 --> C61
    style C61 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [42](PBG-IDE-42.md) | Browse - GM Handicap | 1 | Sous-programme |
| [43](PBG-IDE-43.md) | Browse - Lit Matrimoniaux | 1 | Sous-programme |
| [44](PBG-IDE-44.md) | Browse - COMMENTAIRE      COM | 1 | Sous-programme |
| [45](PBG-IDE-45.md) | Browse - HEB CIRCUIT      HCI | 1 | Sous-programme |
| [46](PBG-IDE-46.md) | Browse - TRONCON          TRO | 1 | Sous-programme |
| [47](PBG-IDE-47.md) | Browse - Libelle Prestation | 1 | Sous-programme |
| [48](PBG-IDE-48.md) | Browse - Groupe Arr/Dep.  VOL | 1 | Sous-programme |
| [49](PBG-IDE-49.md) | Browse - New ASD | 1 | Sous-programme |
| [50](PBG-IDE-50.md) | Browse - Code Vol         VOT | 1 | Sous-programme |
| [51](PBG-IDE-51.md) | Browse - Validation       VAL | 1 | Sous-programme |
| [52](PBG-IDE-52.md) | Browse - Code Circuit | 1 | Sous-programme |
| [53](PBG-IDE-53.md) | Browse - Tables VILLAGE | 1 | Sous-programme |
| [54](PBG-IDE-54.md) | Browse - LOGEMENT Codes | 1 | Sous-programme |
| [55](PBG-IDE-55.md) | Browse - Comptes | 1 | Sous-programme |
| [56](PBG-IDE-56.md) | Browse - CLIENT           CLI | 1 | Sous-programme |
| [57](PBG-IDE-57.md) | Browse - HEBERGEMENT      HEB | 1 | Sous-programme |
| [58](PBG-IDE-58.md) | Browse - PRESTATION       PRE | 1 | Sous-programme |
| [59](PBG-IDE-59.md) | Browse - GM COMPLET       GMC | 1 | Sous-programme |
| [60](PBG-IDE-60.md) | Browse - GM RECHERCHE     GMR | 1 | Sous-programme |
| [61](PBG-IDE-61.md) | Browse - VOYAGES          VOY | 1 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 42 | Programme compact |
| Expressions | 2 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 20 | Forte dependance |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 42) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 1 ecran, 0 traitement)

- **Strategie** : 1 composant(s) UI (Razor/React) avec formulaires et validation.
- 20 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| temp_recap_sessions | Table WRITE (Temp) | 1x | Schema + repository |
| [Browse - Comptes (IDE 55)](PBG-IDE-55.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Browse - CLIENT           CLI (IDE 56)](PBG-IDE-56.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Browse - LOGEMENT Codes (IDE 54)](PBG-IDE-54.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Browse - Code Circuit (IDE 52)](PBG-IDE-52.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Browse - Tables VILLAGE (IDE 53)](PBG-IDE-53.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Browse - GM RECHERCHE     GMR (IDE 60)](PBG-IDE-60.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Browse - VOYAGES          VOY (IDE 61)](PBG-IDE-61.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Browse - GM COMPLET       GMC (IDE 59)](PBG-IDE-59.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Browse - HEBERGEMENT      HEB (IDE 57)](PBG-IDE-57.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Browse - PRESTATION       PRE (IDE 58)](PBG-IDE-58.md) | Sous-programme | 1x | Normale - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 01:22*
