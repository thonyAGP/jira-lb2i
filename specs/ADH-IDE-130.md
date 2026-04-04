# ADH IDE 130 - Ecart fermeture caisse

> **Analyse**: Phases 1-4 2026-02-07 03:50 -> 03:08 (23h18min) | Assemblage 03:08
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | ADH |
| IDE Position | 130 |
| Nom Programme | Ecart fermeture caisse |
| Fichier source | `Prg_130.xml` |
| Dossier IDE | Caisse |
| Taches | 10 (4 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 2 |
| Complexite | **BASSE** (score 12/100) |

## 2. DESCRIPTION FONCTIONNELLE

# ADH IDE 130 - Gestion des Écarts de Fermeture Caisse

ADH IDE 130 traite les discrepancies (écarts) detectés lors de la fermeture d'une session de caisse. Le programme valide l'écart total par rapport aux seuils acceptables (ForceClosureOnEcart parameter), demande à l'opérateur de saisir un commentaire explicatif, puis enregistre cet écart dans la base de données pour audit et suivi. C'est le point de contrôle critique qui empêche une fermeture erronée si l'écart dépasse les limites définies.

Le flux comporte trois phases principales: d'abord, le calcul de l'écart global (différence entre montants physiques comptés et montants attendus), ensuite la validation contre le seuil configurable (paramètre SeuilAlerte), et enfin - si l'écart est accepté - la mise à jour de la devise de la session via WS (IDE 142) et la récupération des données de titre (IDE 43) pour l'archivage. Chaque devise est traitée individuellement pour identifier précisément où réside la discrepancy.

Ce programme est appelé uniquement en cas de détection d'écart >= au seuil. Il agit comme garde-fou: force l'opérateur à documenter l'anomalie avant de valider la fermeture, créant une piste d'audit complète. Sans ce contrôle, les petits vols ou erreurs de comptage pourraient passer inaperçus.

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (2 taches)

Traitements internes.

---

#### <a id="t1"></a>130 - Ecart fermeture caisse

**Role** : Traitement : Ecart fermeture caisse.
**Variables liees** : ES (Param caisse comptee), ET (Param caisse comptee monnaie), EU (Param caisse comptee produits), EV (Param caisse comptee cartes), EW (Param caisse comptee cheques)
**Delegue a** : [Devise update session WS (IDE 142)](ADH-IDE-142.md), [Recuperation du titre (IDE 43)](ADH-IDE-43.md)

---

#### <a id="t3"></a>130.1.1 - Commentaires [[ECRAN]](#ecran-t3)

**Role** : Traitement : Commentaires.
**Ecran** : 480 x 0 DLU (MDI) | [Voir mockup](#ecran-t3)
**Delegue a** : [Devise update session WS (IDE 142)](ADH-IDE-142.md), [Recuperation du titre (IDE 43)](ADH-IDE-43.md)


### 3.2 Saisie (1 tache)

L'operateur saisit les donnees de la transaction via 1 ecran (Saisie commentaire).

---

#### <a id="t2"></a>130.1 - Saisie commentaire [[ECRAN]](#ecran-t2)

**Role** : Saisie des donnees : Saisie commentaire.
**Ecran** : 1000 x 240 DLU (MDI) | [Voir mockup](#ecran-t2)
**Variables liees** : FN (Param commentaire), FO (Param commentaire devise)


### 3.3 Calcul (3 taches)

Calculs metier : montants, stocks, compteurs.

---

#### <a id="t4"></a>130.1.2 - Calcul ecart sur devise

**Role** : Calcul : Calcul ecart sur devise.
**Variables liees** : EP (Param devise locale), EY (Param caisse comptee nb devise), EZ (Param caisse calculee), FA (Param caisse calculee monnaie), FB (Param caisse calculee produits)

---

#### <a id="t5"></a>130.1.2.1 - Calcul ecart sur devise

**Role** : Calcul : Calcul ecart sur devise.
**Variables liees** : EP (Param devise locale), EY (Param caisse comptee nb devise), EZ (Param caisse calculee), FA (Param caisse calculee monnaie), FB (Param caisse calculee produits)

---

#### <a id="t6"></a>130.1.2.2 - Calcul ecart sur devise

**Role** : Calcul : Calcul ecart sur devise.
**Variables liees** : EP (Param devise locale), EY (Param caisse comptee nb devise), EZ (Param caisse calculee), FA (Param caisse calculee monnaie), FB (Param caisse calculee produits)


### 3.4 Consultation (3 taches)

Ecrans de recherche et consultation.

---

#### <a id="t7"></a>130.1.3 - Affiche devises [[ECRAN]](#ecran-t7)

**Role** : Reinitialisation : Affiche devises.
**Ecran** : 501 x 240 DLU (MDI) | [Voir mockup](#ecran-t7)

---

#### <a id="t8"></a>130.1.3.1 - Affiche devises [[ECRAN]](#ecran-t8)

**Role** : Reinitialisation : Affiche devises.
**Ecran** : 1002 x 240 DLU (MDI) | [Voir mockup](#ecran-t8)

---

#### <a id="t9"></a>130.1.3.2 - Affiche devises [[ECRAN]](#ecran-t9)

**Role** : Reinitialisation : Affiche devises.
**Ecran** : 1002 x 240 DLU (MDI) | [Voir mockup](#ecran-t9)


### 3.5 Impression (1 tache)

Generation des documents et tickets.

---

#### <a id="t10"></a>130.1.4 - Ticket

**Role** : Generation du document : Ticket.
**Variables liees** : FP (Param editer ticket recap)


## 5. REGLES METIER

*(Programme d'impression - logique technique sans conditions metier)*

## 6. CONTEXTE

- **Appele par**: [Fermeture caisse (IDE 131)](ADH-IDE-131.md), [Fermeture caisse 144 (IDE 299)](ADH-IDE-299.md)
- **Appelle**: 2 programmes | **Tables**: 7 (W:0 R:3 L:4) | **Taches**: 10 | **Expressions**: 2

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (4 / 10)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 130.1 | 130.1 | Saisie commentaire | MDI | 1000 | 240 | Saisie |
| 2 | 130.1.1 | 130.1.1 | Commentaires | MDI | 480 | 0 | Traitement |
| 3 | 130.1.3.1 | 130.1.3.1 | Affiche devises | MDI | 1002 | 240 | Consultation |
| 4 | 130.1.3.2 | 130.1.3.2 | Affiche devises | MDI | 1002 | 240 | Consultation |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t2"></a>130.1 - Saisie commentaire
**Tache** : [130.1](#t2) | **Type** : MDI | **Dimensions** : 1000 x 240 DLU
**Bloc** : Saisie | **Titre IDE** : Saisie commentaire

<!-- FORM-DATA:
{
    "width":  1000,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  1000,
                         "fmt":  "",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  141,
                         "type":  "label",
                         "var":  "",
                         "y":  28,
                         "w":  851,
                         "fmt":  "",
                         "name":  "",
                         "h":  18,
                         "color":  "142",
                         "text":  "Validation des ecarts (fermeture caisse)",
                         "parent":  null
                     },
                     {
                         "x":  141,
                         "type":  "label",
                         "var":  "",
                         "y":  49,
                         "w":  851,
                         "fmt":  "",
                         "name":  "",
                         "h":  126,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  148,
                         "type":  "label",
                         "var":  "",
                         "y":  55,
                         "w":  112,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "7",
                         "text":  "Monnaie",
                         "parent":  null
                     },
                     {
                         "x":  267,
                         "type":  "label",
                         "var":  "",
                         "y":  55,
                         "w":  112,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "7",
                         "text":  "Cartes",
                         "parent":  null
                     },
                     {
                         "x":  385,
                         "type":  "label",
                         "var":  "",
                         "y":  55,
                         "w":  112,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "7",
                         "text":  "Chèques",
                         "parent":  null
                     },
                     {
                         "x":  504,
                         "type":  "label",
                         "var":  "",
                         "y":  55,
                         "w":  112,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "7",
                         "text":  "Produits",
                         "parent":  null
                     },
                     {
                         "x":  625,
                         "type":  "label",
                         "var":  "",
                         "y":  55,
                         "w":  144,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "7",
                         "text":  "TOTAL",
                         "parent":  null
                     },
                     {
                         "x":  769,
                         "type":  "label",
                         "var":  "",
                         "y":  55,
                         "w":  112,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "OD",
                         "parent":  null
                     },
                     {
                         "x":  888,
                         "type":  "label",
                         "var":  "",
                         "y":  55,
                         "w":  99,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "Devises",
                         "parent":  null
                     },
                     {
                         "x":  5,
                         "type":  "label",
                         "var":  "",
                         "y":  80,
                         "w":  127,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "148",
                         "text":  "Caisse comptée",
                         "parent":  null
                     },
                     {
                         "x":  5,
                         "type":  "label",
                         "var":  "",
                         "y":  102,
                         "w":  127,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "148",
                         "text":  "Caisse contrôlée",
                         "parent":  null
                     },
                     {
                         "x":  5,
                         "type":  "label",
                         "var":  "",
                         "y":  124,
                         "w":  127,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "144",
                         "text":  "Montant écart",
                         "parent":  null
                     },
                     {
                         "x":  148,
                         "type":  "label",
                         "var":  "",
                         "y":  153,
                         "w":  112,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Commentaire",
                         "parent":  null
                     },
                     {
                         "x":  148,
                         "type":  "label",
                         "var":  "",
                         "y":  187,
                         "w":  112,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Devises",
                         "parent":  null
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  216,
                         "w":  1000,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  437,
                         "type":  "label",
                         "var":  "",
                         "y":  224,
                         "w":  128,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Monnaie locale",
                         "parent":  42
                     },
                     {
                         "x":  269,
                         "type":  "edit",
                         "var":  "",
                         "y":  153,
                         "w":  715,
                         "fmt":  "",
                         "name":  "Commentaire",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  269,
                         "type":  "edit",
                         "var":  "",
                         "y":  187,
                         "w":  715,
                         "fmt":  "",
                         "name":  "Commentaire ecart devise",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  2,
                         "type":  "edit",
                         "var":  "",
                         "y":  5,
                         "w":  267,
                         "fmt":  "30",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  740,
                         "type":  "edit",
                         "var":  "",
                         "y":  5,
                         "w":  248,
                         "fmt":  "WWW  DD MMM YYYYT",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  5,
                         "type":  "image",
                         "var":  "",
                         "y":  28,
                         "w":  127,
                         "fmt":  "",
                         "name":  "",
                         "h":  47,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  148,
                         "type":  "edit",
                         "var":  "",
                         "y":  80,
                         "w":  112,
                         "fmt":  "N## ### ### ###.###Z",
                         "name":  "",
                         "h":  10,
                         "color":  "7",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  267,
                         "type":  "edit",
                         "var":  "",
                         "y":  80,
                         "w":  112,
                         "fmt":  "N## ### ### ###.###Z",
                         "name":  "",
                         "h":  10,
                         "color":  "7",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  385,
                         "type":  "edit",
                         "var":  "",
                         "y":  80,
                         "w":  112,
                         "fmt":  "N## ### ### ###.###Z",
                         "name":  "",
                         "h":  10,
                         "color":  "7",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  504,
                         "type":  "edit",
                         "var":  "",
                         "y":  80,
                         "w":  112,
                         "fmt":  "N## ### ### ###.###Z",
                         "name":  "",
                         "h":  10,
                         "color":  "7",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  625,
                         "type":  "edit",
                         "var":  "",
                         "y":  80,
                         "w":  144,
                         "fmt":  "N## ### ### ###.###Z",
                         "name":  "",
                         "h":  10,
                         "color":  "7",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  769,
                         "type":  "edit",
                         "var":  "",
                         "y":  80,
                         "w":  112,
                         "fmt":  "N## ### ### ###.###Z",
                         "name":  "",
                         "h":  10,
                         "color":  "42",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  888,
                         "type":  "edit",
                         "var":  "",
                         "y":  80,
                         "w":  99,
                         "fmt":  "6Z",
                         "name":  "",
                         "h":  10,
                         "color":  "1",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  148,
                         "type":  "edit",
                         "var":  "",
                         "y":  102,
                         "w":  112,
                         "fmt":  "N## ### ### ###.###Z",
                         "name":  "",
                         "h":  10,
                         "color":  "7",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  267,
                         "type":  "edit",
                         "var":  "",
                         "y":  102,
                         "w":  112,
                         "fmt":  "N## ### ### ###.###Z",
                         "name":  "",
                         "h":  10,
                         "color":  "7",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  385,
                         "type":  "edit",
                         "var":  "",
                         "y":  102,
                         "w":  112,
                         "fmt":  "N## ### ### ###.###Z",
                         "name":  "",
                         "h":  10,
                         "color":  "7",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  504,
                         "type":  "edit",
                         "var":  "",
                         "y":  102,
                         "w":  112,
                         "fmt":  "N## ### ### ###.###Z",
                         "name":  "",
                         "h":  10,
                         "color":  "7",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  625,
                         "type":  "edit",
                         "var":  "",
                         "y":  102,
                         "w":  144,
                         "fmt":  "N## ### ### ###.###Z",
                         "name":  "",
                         "h":  10,
                         "color":  "7",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  769,
                         "type":  "edit",
                         "var":  "",
                         "y":  102,
                         "w":  112,
                         "fmt":  "N## ### ### ###.###Z",
                         "name":  "",
                         "h":  10,
                         "color":  "42",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  888,
                         "type":  "edit",
                         "var":  "",
                         "y":  102,
                         "w":  99,
                         "fmt":  "6Z",
                         "name":  "",
                         "h":  10,
                         "color":  "1",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  148,
                         "type":  "edit",
                         "var":  "",
                         "y":  124,
                         "w":  112,
                         "fmt":  "N## ### ### ###.###Z",
                         "name":  "",
                         "h":  10,
                         "color":  "166",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  267,
                         "type":  "edit",
                         "var":  "",
                         "y":  124,
                         "w":  112,
                         "fmt":  "N## ### ### ###.###Z",
                         "name":  "",
                         "h":  10,
                         "color":  "166",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  385,
                         "type":  "edit",
                         "var":  "",
                         "y":  124,
                         "w":  112,
                         "fmt":  "N## ### ### ###.###Z",
                         "name":  "",
                         "h":  10,
                         "color":  "166",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  504,
                         "type":  "edit",
                         "var":  "",
                         "y":  124,
                         "w":  112,
                         "fmt":  "N## ### ### ###.###Z",
                         "name":  "",
                         "h":  10,
                         "color":  "166",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  625,
                         "type":  "edit",
                         "var":  "",
                         "y":  124,
                         "w":  144,
                         "fmt":  "N## ### ### ###.###Z",
                         "name":  "",
                         "h":  10,
                         "color":  "166",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  769,
                         "type":  "edit",
                         "var":  "",
                         "y":  124,
                         "w":  112,
                         "fmt":  "N## ### ### ###.###Z",
                         "name":  "",
                         "h":  10,
                         "color":  "143",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  888,
                         "type":  "edit",
                         "var":  "",
                         "y":  124,
                         "w":  99,
                         "fmt":  "6Z",
                         "name":  "",
                         "h":  10,
                         "color":  "1",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  12,
                         "type":  "button",
                         "var":  "",
                         "y":  219,
                         "w":  154,
                         "fmt":  "A\u0026bandon",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  184,
                         "type":  "button",
                         "var":  "",
                         "y":  219,
                         "w":  240,
                         "fmt":  "\u0026Ecart devises",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  637,
                         "type":  "button",
                         "var":  "",
                         "y":  219,
                         "w":  154,
                         "fmt":  "\u0026Ticket",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  834,
                         "type":  "button",
                         "var":  "",
                         "y":  219,
                         "w":  154,
                         "fmt":  "\u0026Validation",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  583,
                         "type":  "edit",
                         "var":  "",
                         "y":  224,
                         "w":  42,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "7",
                         "text":  "",
                         "parent":  42
                     }
                 ],
    "taskId":  "130.1",
    "height":  240
}
-->

<details>
<summary><strong>Champs : 26 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 269,153 | Commentaire | - | edit |
| 269,187 | Commentaire ecart devise | - | edit |
| 2,5 | 30 | - | edit |
| 740,5 | WWW  DD MMM YYYYT | - | edit |
| 148,80 | N## ### ### ###.###Z | - | edit |
| 267,80 | N## ### ### ###.###Z | - | edit |
| 385,80 | N## ### ### ###.###Z | - | edit |
| 504,80 | N## ### ### ###.###Z | - | edit |
| 625,80 | N## ### ### ###.###Z | - | edit |
| 769,80 | N## ### ### ###.###Z | - | edit |
| 888,80 | 6Z | - | edit |
| 148,102 | N## ### ### ###.###Z | - | edit |
| 267,102 | N## ### ### ###.###Z | - | edit |
| 385,102 | N## ### ### ###.###Z | - | edit |
| 504,102 | N## ### ### ###.###Z | - | edit |
| 625,102 | N## ### ### ###.###Z | - | edit |
| 769,102 | N## ### ### ###.###Z | - | edit |
| 888,102 | 6Z | - | edit |
| 148,124 | N## ### ### ###.###Z | - | edit |
| 267,124 | N## ### ### ###.###Z | - | edit |
| 385,124 | N## ### ### ###.###Z | - | edit |
| 504,124 | N## ### ### ###.###Z | - | edit |
| 625,124 | N## ### ### ###.###Z | - | edit |
| 769,124 | N## ### ### ###.###Z | - | edit |
| 888,124 | 6Z | - | edit |
| 583,224 | (sans nom) | - | edit |

</details>

<details>
<summary><strong>Boutons : 4 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Abandon | 12,219 | Annule et retour au menu |
| Ecart devises | 184,219 | Bouton fonctionnel |
| Ticket | 637,219 | Lance l'impression |
| Validation | 834,219 | Valide la saisie et enregistre |

</details>

---

#### <a id="ecran-t3"></a>130.1.1 - Commentaires
**Tache** : [130.1.1](#t3) | **Type** : MDI | **Dimensions** : 480 x 0 DLU
**Bloc** : Traitement | **Titre IDE** : Commentaires

<!-- FORM-DATA:
{
    "width":  480,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  3,
                         "type":  "label",
                         "var":  "",
                         "y":  181,
                         "w":  474,
                         "fmt":  "",
                         "name":  "",
                         "h":  19,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  99,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "196",
                         "w":  283,
                         "y":  10,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  14,
                         "h":  142,
                         "cols":  [
                                      {
                                          "title":  "Libellé",
                                          "layer":  1,
                                          "w":  250
                                      }
                                  ],
                         "rows":  1
                     },
                     {
                         "x":  106,
                         "type":  "edit",
                         "var":  "",
                         "y":  24,
                         "w":  240,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "196",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  106,
                         "type":  "edit",
                         "var":  "",
                         "y":  24,
                         "w":  240,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "196",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  13,
                         "type":  "button",
                         "var":  "",
                         "y":  184,
                         "w":  144,
                         "fmt":  "\u0026Selectionner",
                         "name":  "",
                         "h":  14,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  325,
                         "type":  "button",
                         "var":  "",
                         "y":  184,
                         "w":  144,
                         "fmt":  "\u0026Quitter",
                         "name":  "",
                         "h":  14,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  211,
                         "type":  "image",
                         "var":  "",
                         "y":  158,
                         "w":  58,
                         "fmt":  "",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "130.1.1",
    "height":  0
}
-->

<details>
<summary><strong>Champs : 2 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 106,24 | (sans nom) | - | edit |
| 106,24 | (sans nom) | - | edit |

</details>

<details>
<summary><strong>Boutons : 2 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Selectionner | 13,184 | Ouvre la selection |
| Quitter | 325,184 | Quitte le programme |

</details>

---

#### <a id="ecran-t8"></a>130.1.3.1 - Affiche devises
**Tache** : [130.1.3.1](#t8) | **Type** : MDI | **Dimensions** : 1002 x 240 DLU
**Bloc** : Consultation | **Titre IDE** : Affiche devises

<!-- FORM-DATA:
{
    "width":  1002,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  1,
                         "w":  1000,
                         "fmt":  "",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  214,
                         "w":  1000,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  437,
                         "type":  "label",
                         "var":  "",
                         "y":  222,
                         "w":  80,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Monnaie",
                         "parent":  4
                     },
                     {
                         "x":  26,
                         "type":  "label",
                         "var":  "",
                         "y":  223,
                         "w":  154,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Devises en écart",
                         "parent":  null
                     },
                     {
                         "x":  176,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "110",
                         "w":  649,
                         "y":  23,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  10,
                         "h":  190,
                         "cols":  [
                                      {
                                          "title":  "Devise",
                                          "layer":  1,
                                          "w":  152
                                      },
                                      {
                                          "title":  "Mode paiement",
                                          "layer":  2,
                                          "w":  154
                                      },
                                      {
                                          "title":  "Quantité contrôlée",
                                          "layer":  3,
                                          "w":  151
                                      },
                                      {
                                          "title":  "Quantité Comptée",
                                          "layer":  4,
                                          "w":  159
                                      }
                                  ],
                         "rows":  4
                     },
                     {
                         "x":  740,
                         "type":  "edit",
                         "var":  "",
                         "y":  6,
                         "w":  248,
                         "fmt":  "WWW  DD MMM YYYYT",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  522,
                         "type":  "edit",
                         "var":  "",
                         "y":  222,
                         "w":  42,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "7",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  185,
                         "type":  "edit",
                         "var":  "",
                         "y":  223,
                         "w":  82,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  834,
                         "type":  "button",
                         "var":  "",
                         "y":  217,
                         "w":  154,
                         "fmt":  "\u0026Quitter",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  2,
                         "type":  "edit",
                         "var":  "",
                         "y":  6,
                         "w":  267,
                         "fmt":  "30",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  182,
                         "type":  "edit",
                         "var":  "",
                         "y":  37,
                         "w":  140,
                         "fmt":  "",
                         "name":  "mor_devise",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  9
                     },
                     {
                         "x":  378,
                         "type":  "edit",
                         "var":  "",
                         "y":  37,
                         "w":  59,
                         "fmt":  "",
                         "name":  "mor_mop",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  9
                     },
                     {
                         "x":  488,
                         "type":  "edit",
                         "var":  "",
                         "y":  37,
                         "w":  142,
                         "fmt":  "",
                         "name":  "quantite",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  9
                     },
                     {
                         "x":  642,
                         "type":  "edit",
                         "var":  "",
                         "y":  37,
                         "w":  142,
                         "fmt":  "",
                         "name":  "quantite_0001",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  9
                     }
                 ],
    "taskId":  "130.1.3.1",
    "height":  240
}
-->

<details>
<summary><strong>Champs : 8 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 740,6 | WWW  DD MMM YYYYT | - | edit |
| 522,222 | (sans nom) | - | edit |
| 185,223 | (sans nom) | - | edit |
| 2,6 | 30 | - | edit |
| 182,37 | mor_devise | - | edit |
| 378,37 | mor_mop | - | edit |
| 488,37 | quantite | - | edit |
| 642,37 | quantite_0001 | - | edit |

</details>

<details>
<summary><strong>Boutons : 1 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Quitter | 834,217 | Quitte le programme |

</details>

---

#### <a id="ecran-t9"></a>130.1.3.2 - Affiche devises
**Tache** : [130.1.3.2](#t9) | **Type** : MDI | **Dimensions** : 1002 x 240 DLU
**Bloc** : Consultation | **Titre IDE** : Affiche devises

<!-- FORM-DATA:
{
    "width":  1002,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  1,
                         "w":  1000,
                         "fmt":  "",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  214,
                         "w":  1000,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  437,
                         "type":  "label",
                         "var":  "",
                         "y":  222,
                         "w":  80,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Monnaie",
                         "parent":  4
                     },
                     {
                         "x":  26,
                         "type":  "label",
                         "var":  "",
                         "y":  223,
                         "w":  154,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Devises en écart",
                         "parent":  null
                     },
                     {
                         "x":  176,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "110",
                         "w":  651,
                         "y":  24,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  10,
                         "h":  190,
                         "cols":  [
                                      {
                                          "title":  "Devise",
                                          "layer":  1,
                                          "w":  152
                                      },
                                      {
                                          "title":  "Mode paiement",
                                          "layer":  2,
                                          "w":  154
                                      },
                                      {
                                          "title":  "Quantité contrôlée",
                                          "layer":  3,
                                          "w":  151
                                      },
                                      {
                                          "title":  "Quantité Comptée",
                                          "layer":  4,
                                          "w":  159
                                      }
                                  ],
                         "rows":  4
                     },
                     {
                         "x":  740,
                         "type":  "edit",
                         "var":  "",
                         "y":  6,
                         "w":  248,
                         "fmt":  "WWW  DD MMM YYYYT",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  522,
                         "type":  "edit",
                         "var":  "",
                         "y":  222,
                         "w":  42,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "7",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  185,
                         "type":  "edit",
                         "var":  "",
                         "y":  223,
                         "w":  82,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  834,
                         "type":  "button",
                         "var":  "",
                         "y":  217,
                         "w":  154,
                         "fmt":  "\u0026Quitter",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  7,
                         "type":  "edit",
                         "var":  "",
                         "y":  6,
                         "w":  267,
                         "fmt":  "30",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  182,
                         "type":  "edit",
                         "var":  "",
                         "y":  38,
                         "w":  140,
                         "fmt":  "",
                         "name":  "mor_devise",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  9
                     },
                     {
                         "x":  378,
                         "type":  "edit",
                         "var":  "",
                         "y":  38,
                         "w":  59,
                         "fmt":  "",
                         "name":  "mor_mop",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  9
                     },
                     {
                         "x":  488,
                         "type":  "edit",
                         "var":  "",
                         "y":  38,
                         "w":  142,
                         "fmt":  "",
                         "name":  "quantite",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  9
                     },
                     {
                         "x":  642,
                         "type":  "edit",
                         "var":  "",
                         "y":  38,
                         "w":  142,
                         "fmt":  "",
                         "name":  "quantite_0001",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  9
                     }
                 ],
    "taskId":  "130.1.3.2",
    "height":  240
}
-->

<details>
<summary><strong>Champs : 8 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 740,6 | WWW  DD MMM YYYYT | - | edit |
| 522,222 | (sans nom) | - | edit |
| 185,223 | (sans nom) | - | edit |
| 7,6 | 30 | - | edit |
| 182,38 | mor_devise | - | edit |
| 378,38 | mor_mop | - | edit |
| 488,38 | quantite | - | edit |
| 642,38 | quantite_0001 | - | edit |

</details>

<details>
<summary><strong>Boutons : 1 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Quitter | 834,217 | Quitte le programme |

</details>

## 9. NAVIGATION

### 9.1 Enchainement des ecrans

```mermaid
flowchart TD
    START([Entree])
    style START fill:#3fb950
    VF2[130.1 Saisie commentaire]
    style VF2 fill:#58a6ff
    VF3[130.1.1 Commentaires]
    style VF3 fill:#58a6ff
    VF8[130.1.3.1 Affiche devises]
    style VF8 fill:#58a6ff
    VF9[130.1.3.2 Affiche devises]
    style VF9 fill:#58a6ff
    EXT142[IDE 142 Devise update ...]
    style EXT142 fill:#3fb950
    EXT43[IDE 43 Recuperation du...]
    style EXT43 fill:#3fb950
    FIN([Sortie])
    style FIN fill:#f85149
    START --> VF2
    VF2 -->|Mise a jour donnees| EXT142
    VF2 -->|Recuperation donnees| EXT43
    EXT43 --> FIN
```

**Detail par enchainement :**

| Depuis | Action | Vers | Retour |
|--------|--------|------|--------|
| Saisie commentaire | Mise a jour donnees | [Devise update session WS (IDE 142)](ADH-IDE-142.md) | Retour ecran |
| Saisie commentaire | Recuperation donnees | [Recuperation du titre (IDE 43)](ADH-IDE-43.md) | Retour ecran |

### 9.3 Structure hierarchique (10 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **130.1** | [**Ecart fermeture caisse** (130)](#t1) | MDI | - | Traitement |
| 130.1.1 | [Commentaires (130.1.1)](#t3) [mockup](#ecran-t3) | MDI | 480x0 | |
| **130.2** | [**Saisie commentaire** (130.1)](#t2) [mockup](#ecran-t2) | MDI | 1000x240 | Saisie |
| **130.3** | [**Calcul ecart sur devise** (130.1.2)](#t4) | MDI | - | Calcul |
| 130.3.1 | [Calcul ecart sur devise (130.1.2.1)](#t5) | MDI | - | |
| 130.3.2 | [Calcul ecart sur devise (130.1.2.2)](#t6) | MDI | - | |
| **130.4** | [**Affiche devises** (130.1.3)](#t7) [mockup](#ecran-t7) | MDI | 501x240 | Consultation |
| 130.4.1 | [Affiche devises (130.1.3.1)](#t8) [mockup](#ecran-t8) | MDI | 1002x240 | |
| 130.4.2 | [Affiche devises (130.1.3.2)](#t9) [mockup](#ecran-t9) | MDI | 1002x240 | |
| **130.5** | [**Ticket** (130.1.4)](#t10) | MDI | - | Impression |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Saisie commentaire]
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
| 139 | moyens_reglement_mor | Reglements / paiements | DB | R |   |   | 2 |
| 50 | moyens_reglement_mor | Reglements / paiements | DB | R |   |   | 2 |
| 706 | parametre_port_serie |  | DB | R |   |   | 1 |
| 232 | gestion_devise_session | Sessions de caisse | DB |   |   | L | 4 |
| 141 | devises__________dev | Devises / taux de change | DB |   |   | L | 2 |
| 492 | edition_tableau_recap |  | DB |   |   | L | 1 |
| 90 | devises__________dev | Devises / taux de change | DB |   |   | L | 1 |

### Colonnes par table (4 / 3 tables avec colonnes identifiees)

<details>
<summary>Table 139 - moyens_reglement_mor (R) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | ------------------ compte | R | Alpha |
| B | ------------------ controle | R | Alpha |
| C | RUPTURE_DEV_MOP | R | Alpha |

</details>

<details>
<summary>Table 50 - moyens_reglement_mor (R) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | ------------------ compte | R | Alpha |
| B | ------------------ controle | R | Alpha |

</details>

<details>
<summary>Table 706 - parametre_port_serie (R) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Autres (31)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| EN | Param societe | Alpha | - |
| EO | Param chrono session | Numeric | - |
| EP | Param devise locale | Alpha | - |
| EQ | Param masque montant | Alpha | - |
| ER | Param quand | Alpha | - |
| ES | Param caisse comptee | Numeric | - |
| ET | Param caisse comptee monnaie | Numeric | - |
| EU | Param caisse comptee produits | Numeric | - |
| EV | Param caisse comptee cartes | Numeric | - |
| EW | Param caisse comptee cheques | Numeric | - |
| EX | Param caisse comptee od | Numeric | - |
| EY | Param caisse comptee nb devise | Numeric | - |
| EZ | Param caisse calculee | Numeric | - |
| FA | Param caisse calculee monnaie | Numeric | - |
| FB | Param caisse calculee produits | Numeric | - |
| FC | Param caisse calculee cartes | Numeric | - |
| FD | Param caisse calculee cheques | Numeric | - |
| FE | Param caisse calculee od | Numeric | - |
| FF | Param caisse calculee nb devise | Numeric | - |
| FG | Param montant ecart | Numeric | - |
| FH | Param montant ecart monnaie | Numeric | - |
| FI | Param montant ecart produits | Numeric | - |
| FJ | Param montant ecart cartes | Numeric | - |
| FK | Param montant ecart cheques | Numeric | - |
| FL | Param montant ecart od | Numeric | - |
| FM | Param ecart nb devise | Numeric | - |
| FN | Param commentaire | Alpha | - |
| FO | Param commentaire devise | Alpha | - |
| FP | Param editer ticket recap | Logical | - |
| FQ | Param UNI/BI | Alpha | - |
| FR | Fin | Logical | 1x refs |

<details>
<summary>Toutes les 31 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| Autre | **EN** | Param societe | Alpha |
| Autre | **EO** | Param chrono session | Numeric |
| Autre | **EP** | Param devise locale | Alpha |
| Autre | **EQ** | Param masque montant | Alpha |
| Autre | **ER** | Param quand | Alpha |
| Autre | **ES** | Param caisse comptee | Numeric |
| Autre | **ET** | Param caisse comptee monnaie | Numeric |
| Autre | **EU** | Param caisse comptee produits | Numeric |
| Autre | **EV** | Param caisse comptee cartes | Numeric |
| Autre | **EW** | Param caisse comptee cheques | Numeric |
| Autre | **EX** | Param caisse comptee od | Numeric |
| Autre | **EY** | Param caisse comptee nb devise | Numeric |
| Autre | **EZ** | Param caisse calculee | Numeric |
| Autre | **FA** | Param caisse calculee monnaie | Numeric |
| Autre | **FB** | Param caisse calculee produits | Numeric |
| Autre | **FC** | Param caisse calculee cartes | Numeric |
| Autre | **FD** | Param caisse calculee cheques | Numeric |
| Autre | **FE** | Param caisse calculee od | Numeric |
| Autre | **FF** | Param caisse calculee nb devise | Numeric |
| Autre | **FG** | Param montant ecart | Numeric |
| Autre | **FH** | Param montant ecart monnaie | Numeric |
| Autre | **FI** | Param montant ecart produits | Numeric |
| Autre | **FJ** | Param montant ecart cartes | Numeric |
| Autre | **FK** | Param montant ecart cheques | Numeric |
| Autre | **FL** | Param montant ecart od | Numeric |
| Autre | **FM** | Param ecart nb devise | Numeric |
| Autre | **FN** | Param commentaire | Alpha |
| Autre | **FO** | Param commentaire devise | Alpha |
| Autre | **FP** | Param editer ticket recap | Logical |
| Autre | **FQ** | Param UNI/BI | Alpha |
| Autre | **FR** | Fin | Logical |

</details>

## 12. EXPRESSIONS

**2 / 2 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CAST_LOGIQUE | 1 | 0 |
| OTHER | 1 | 0 |

### 12.2 Expressions cles par type

#### CAST_LOGIQUE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 1 | `'FALSE'LOG` | - |

#### OTHER (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 2 | `Fin [BE]` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Fermeture caisse (IDE 131)](ADH-IDE-131.md) -> **Ecart fermeture caisse (IDE 130)**

Main -> ... -> [Fermeture caisse 144 (IDE 299)](ADH-IDE-299.md) -> **Ecart fermeture caisse (IDE 130)**

```mermaid
graph LR
    T130[130 Ecart fermeture ca...]
    style T130 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC163[163 Menu caisse GM - s...]
    style CC163 fill:#f59e0b
    CC281[281 Fermeture Sessions]
    style CC281 fill:#f59e0b
    CC298[298 Gestion caisse 142]
    style CC298 fill:#f59e0b
    CC121[121 Gestion caisse]
    style CC121 fill:#f59e0b
    CC131[131 Fermeture caisse]
    style CC131 fill:#3fb950
    CC299[299 Fermeture caisse 144]
    style CC299 fill:#3fb950
    CC121 --> CC131
    CC298 --> CC131
    CC121 --> CC299
    CC298 --> CC299
    CC163 --> CC121
    CC281 --> CC121
    CC163 --> CC298
    CC281 --> CC298
    CC1 --> CC163
    CC1 --> CC281
    CC131 --> T130
    CC299 --> T130
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [131](ADH-IDE-131.md) | Fermeture caisse | 1 |
| [299](ADH-IDE-299.md) | Fermeture caisse 144 | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T130[130 Ecart fermeture ca...]
    style T130 fill:#58a6ff
    C142[142 Devise update sess...]
    T130 --> C142
    style C142 fill:#3fb950
    C43[43 Recuperation du titre]
    T130 --> C43
    style C43 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [142](ADH-IDE-142.md) | Devise update session WS | 2 | Mise a jour donnees |
| [43](ADH-IDE-43.md) | Recuperation du titre | 1 | Recuperation donnees |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 260 | Taille moyenne |
| Expressions | 2 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 2 | Peu de dependances |
| Ecrans visibles | 4 | Quelques ecrans |
| Code desactive | 0% (0 / 260) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (2 taches: 1 ecran, 1 traitement)

- **Strategie** : Orchestrateur avec 1 ecrans (Razor/React) et 1 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 2 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Saisie (1 tache: 1 ecran, 0 traitement)

- **Strategie** : Formulaire React/Blazor avec validation Zod/FluentValidation.
- Reproduire 1 ecran : Saisie commentaire
- Validation temps reel cote client + serveur

#### Calcul (3 taches: 0 ecran, 3 traitements)

- **Strategie** : Services de calcul purs (Domain Services).
- Migrer la logique de calcul (stock, compteurs, montants)

#### Consultation (3 taches: 3 ecrans, 0 traitement)

- **Strategie** : Composants de recherche/selection en modales.
- 3 ecrans : Affiche devises, Affiche devises, Affiche devises

#### Impression (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Templates HTML -> PDF via wkhtmltopdf ou Puppeteer.
- `PrintService` injectable avec choix imprimante

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| [Devise update session WS (IDE 142)](ADH-IDE-142.md) | Sous-programme | 2x | Haute - Mise a jour donnees |
| [Recuperation du titre (IDE 43)](ADH-IDE-43.md) | Sous-programme | 1x | Normale - Recuperation donnees |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-08 03:08*
