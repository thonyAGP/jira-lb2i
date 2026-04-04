# PVE IDE 310 - Keyboard2

> **Analyse**: Phases 1-4 2026-02-03 19:31 -> 19:32 (12s) | Assemblage 19:32
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PVE |
| IDE Position | 310 |
| Nom Programme | Keyboard2 |
| Fichier source | `Prg_310.xml` |
| Dossier IDE | Utilitaires |
| Taches | 2 (1 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Keyboard2** assure la gestion complete de ce processus, accessible depuis [Recherche Adresse Mail (IDE 199)](PVE-IDE-199.md), [Recherche Adresse Mail (IDE 308)](PVE-IDE-308.md).

Le flux de traitement s'organise en **2 blocs fonctionnels** :

- **Calcul** (1 tache) : calculs de montants, stocks ou compteurs
- **Traitement** (1 tache) : traitements metier divers

**Logique metier** : 1 regles identifiees couvrant conditions metier.

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (1 tache)

- **310** - Keyboard2 **[[ECRAN]](#ecran-t1)**

#### Phase 2 : Calcul (1 tache)

- **310.1** - Calcul

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>310 - Keyboard2 [[ECRAN]](#ecran-t1)

**Role** : Traitement : Keyboard2.
**Ecran** : 577 x 282 DLU (MDI) | [Voir mockup](#ecran-t1)


### 3.2 Calcul (1 tache)

Calculs metier : montants, stocks, compteurs.

---

#### <a id="t2"></a>310.1 - Calcul

**Role** : Calcul : Calcul.


## 5. REGLES METIER

1 regles identifiees:

### Autres (1 regles)

#### <a id="rm-RM-001"></a>[RM-001] Si L Touche MAJ/Min [F] alors 'MAJ' sinon 'Min')

| Element | Detail |
|---------|--------|
| **Condition** | `L Touche MAJ/Min [F]` |
| **Si vrai** | 'MAJ' |
| **Si faux** | 'Min') |
| **Variables** | F (L Touche MAJ/Min) |
| **Expression source** | Expression 4 : `IF (L Touche MAJ/Min [F],'MAJ','Min')` |
| **Exemple** | Si L Touche MAJ/Min [F] â†’ 'MAJ'. Sinon â†’ 'Min') |

## 6. CONTEXTE

- **Appele par**: [Recherche Adresse Mail (IDE 199)](PVE-IDE-199.md), [Recherche Adresse Mail (IDE 308)](PVE-IDE-308.md)
- **Appelle**: 0 programmes | **Tables**: 0 (W:0 R:0 L:0) | **Taches**: 2 | **Expressions**: 36

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 2)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 310 | 310 | Keyboard2 | MDI | 577 | 282 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>310 - Keyboard2
**Tache** : [310](#t1) | **Type** : MDI | **Dimensions** : 577 x 282 DLU
**Bloc** : Traitement | **Titre IDE** : Keyboard2

<!-- FORM-DATA:
{
    "width":  577,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  9,
                         "type":  "label",
                         "var":  "",
                         "y":  22,
                         "w":  561,
                         "fmt":  "",
                         "name":  "",
                         "h":  32,
                         "color":  "182",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  8,
                         "type":  "edit",
                         "var":  "",
                         "y":  6,
                         "w":  565,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "144",
                         "text":  "",
                         "parent":  50
                     },
                     {
                         "x":  352,
                         "type":  "button",
                         "var":  "",
                         "y":  29,
                         "w":  82,
                         "fmt":  "\u0026Validate",
                         "name":  "VALID",
                         "h":  22,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  93,
                         "type":  "button",
                         "var":  "",
                         "y":  185,
                         "w":  44,
                         "fmt":  "A",
                         "name":  "*A",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  137,
                         "type":  "button",
                         "var":  "",
                         "y":  185,
                         "w":  44,
                         "fmt":  "Z",
                         "name":  "*Z",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  181,
                         "type":  "button",
                         "var":  "",
                         "y":  185,
                         "w":  44,
                         "fmt":  "E",
                         "name":  "*E",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  225,
                         "type":  "button",
                         "var":  "",
                         "y":  185,
                         "w":  44,
                         "fmt":  "R",
                         "name":  "*R",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  269,
                         "type":  "button",
                         "var":  "",
                         "y":  185,
                         "w":  44,
                         "fmt":  "T",
                         "name":  "*T",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  313,
                         "type":  "button",
                         "var":  "",
                         "y":  185,
                         "w":  44,
                         "fmt":  "Y",
                         "name":  "*Y",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  357,
                         "type":  "button",
                         "var":  "",
                         "y":  185,
                         "w":  44,
                         "fmt":  "U",
                         "name":  "*U",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  401,
                         "type":  "button",
                         "var":  "",
                         "y":  185,
                         "w":  44,
                         "fmt":  "I",
                         "name":  "*I",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  445,
                         "type":  "button",
                         "var":  "",
                         "y":  185,
                         "w":  44,
                         "fmt":  "O",
                         "name":  "*O",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  489,
                         "type":  "button",
                         "var":  "",
                         "y":  185,
                         "w":  44,
                         "fmt":  "P",
                         "name":  "*P",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  56,
                         "type":  "button",
                         "var":  "",
                         "y":  217,
                         "w":  52,
                         "fmt":  "MAJ",
                         "name":  "MAJ",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  108,
                         "type":  "button",
                         "var":  "",
                         "y":  217,
                         "w":  44,
                         "fmt":  "Q",
                         "name":  "*Q",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  152,
                         "type":  "button",
                         "var":  "",
                         "y":  217,
                         "w":  44,
                         "fmt":  "S",
                         "name":  "*S",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  196,
                         "type":  "button",
                         "var":  "",
                         "y":  217,
                         "w":  44,
                         "fmt":  "D",
                         "name":  "*D",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  240,
                         "type":  "button",
                         "var":  "",
                         "y":  217,
                         "w":  44,
                         "fmt":  "F",
                         "name":  "*F",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  284,
                         "type":  "button",
                         "var":  "",
                         "y":  217,
                         "w":  44,
                         "fmt":  "G",
                         "name":  "*G",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  328,
                         "type":  "button",
                         "var":  "",
                         "y":  217,
                         "w":  44,
                         "fmt":  "H",
                         "name":  "*H",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  372,
                         "type":  "button",
                         "var":  "",
                         "y":  217,
                         "w":  44,
                         "fmt":  "J",
                         "name":  "*J",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  416,
                         "type":  "button",
                         "var":  "",
                         "y":  217,
                         "w":  44,
                         "fmt":  "K",
                         "name":  "*K",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  460,
                         "type":  "button",
                         "var":  "",
                         "y":  217,
                         "w":  44,
                         "fmt":  "L",
                         "name":  "*L",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  504,
                         "type":  "button",
                         "var":  "",
                         "y":  217,
                         "w":  44,
                         "fmt":  "M",
                         "name":  "*M",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  56,
                         "type":  "button",
                         "var":  "",
                         "y":  249,
                         "w":  71,
                         "fmt":  "Clear",
                         "name":  "CLEAR",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  127,
                         "type":  "button",
                         "var":  "",
                         "y":  249,
                         "w":  44,
                         "fmt":  "W",
                         "name":  "*W",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  171,
                         "type":  "button",
                         "var":  "",
                         "y":  249,
                         "w":  44,
                         "fmt":  "X",
                         "name":  "*X",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  215,
                         "type":  "button",
                         "var":  "",
                         "y":  249,
                         "w":  44,
                         "fmt":  "C",
                         "name":  "*C",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  259,
                         "type":  "button",
                         "var":  "",
                         "y":  249,
                         "w":  44,
                         "fmt":  "V",
                         "name":  "*V",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  303,
                         "type":  "button",
                         "var":  "",
                         "y":  249,
                         "w":  44,
                         "fmt":  "B",
                         "name":  "*B",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  347,
                         "type":  "button",
                         "var":  "",
                         "y":  249,
                         "w":  44,
                         "fmt":  "N",
                         "name":  "*N",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  391,
                         "type":  "button",
                         "var":  "",
                         "y":  249,
                         "w":  40,
                         "fmt":  "-",
                         "name":  "*-",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  431,
                         "type":  "button",
                         "var":  "",
                         "y":  249,
                         "w":  40,
                         "fmt":  "\u0027",
                         "name":  "*\u0027",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  471,
                         "type":  "button",
                         "var":  "",
                         "y":  249,
                         "w":  43,
                         "fmt":  "Backspace",
                         "name":  "BACKSPACE",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  514,
                         "type":  "button",
                         "var":  "",
                         "y":  249,
                         "w":  34,
                         "fmt":  "Space",
                         "name":  "SPACE",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  486,
                         "type":  "button",
                         "var":  "",
                         "y":  29,
                         "w":  82,
                         "fmt":  "\u0026Exit",
                         "name":  "",
                         "h":  22,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  75,
                         "type":  "button",
                         "var":  "",
                         "y":  153,
                         "w":  44,
                         "fmt":  "1",
                         "name":  "*1",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  119,
                         "type":  "button",
                         "var":  "",
                         "y":  153,
                         "w":  44,
                         "fmt":  "2",
                         "name":  "*2",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  163,
                         "type":  "button",
                         "var":  "",
                         "y":  153,
                         "w":  44,
                         "fmt":  "3",
                         "name":  "*3",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  207,
                         "type":  "button",
                         "var":  "",
                         "y":  153,
                         "w":  44,
                         "fmt":  "4",
                         "name":  "*4",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  251,
                         "type":  "button",
                         "var":  "",
                         "y":  153,
                         "w":  44,
                         "fmt":  "5",
                         "name":  "*5",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  295,
                         "type":  "button",
                         "var":  "",
                         "y":  153,
                         "w":  44,
                         "fmt":  "6",
                         "name":  "*6",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  339,
                         "type":  "button",
                         "var":  "",
                         "y":  153,
                         "w":  44,
                         "fmt":  "7",
                         "name":  "*7",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  383,
                         "type":  "button",
                         "var":  "",
                         "y":  153,
                         "w":  44,
                         "fmt":  "8",
                         "name":  "*8",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  427,
                         "type":  "button",
                         "var":  "",
                         "y":  153,
                         "w":  44,
                         "fmt":  "9",
                         "name":  "*9",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  471,
                         "type":  "button",
                         "var":  "",
                         "y":  153,
                         "w":  44,
                         "fmt":  "0",
                         "name":  "*0",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  5,
                         "type":  "button",
                         "var":  "",
                         "y":  89,
                         "w":  44,
                         "fmt":  "~",
                         "name":  "*~",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  49,
                         "type":  "button",
                         "var":  "",
                         "y":  89,
                         "w":  44,
                         "fmt":  "\"",
                         "name":  "*\"",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  93,
                         "type":  "button",
                         "var":  "",
                         "y":  89,
                         "w":  44,
                         "fmt":  "{",
                         "name":  "*{",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  137,
                         "type":  "button",
                         "var":  "",
                         "y":  89,
                         "w":  44,
                         "fmt":  "\\",
                         "name":  "*\\",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  181,
                         "type":  "button",
                         "var":  "",
                         "y":  89,
                         "w":  44,
                         "fmt":  "@",
                         "name":  "*@",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  225,
                         "type":  "button",
                         "var":  "",
                         "y":  89,
                         "w":  44,
                         "fmt":  "£",
                         "name":  "*£",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  269,
                         "type":  "button",
                         "var":  "",
                         "y":  89,
                         "w":  44,
                         "fmt":  "ù",
                         "name":  "*ù",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  313,
                         "type":  "button",
                         "var":  "",
                         "y":  89,
                         "w":  44,
                         "fmt":  "%",
                         "name":  "*%",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  357,
                         "type":  "button",
                         "var":  "",
                         "y":  89,
                         "w":  44,
                         "fmt":  "*",
                         "name":  "**",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  401,
                         "type":  "button",
                         "var":  "",
                         "y":  89,
                         "w":  44,
                         "fmt":  "µ",
                         "name":  "*µ",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  445,
                         "type":  "button",
                         "var":  "",
                         "y":  89,
                         "w":  44,
                         "fmt":  "?",
                         "name":  "*?",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  489,
                         "type":  "button",
                         "var":  "",
                         "y":  89,
                         "w":  44,
                         "fmt":  ",",
                         "name":  "*,",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  533,
                         "type":  "button",
                         "var":  "",
                         "y":  89,
                         "w":  44,
                         "fmt":  "}",
                         "name":  "*}",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  401,
                         "type":  "button",
                         "var":  "",
                         "y":  57,
                         "w":  44,
                         "fmt":  ".",
                         "name":  "*.",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  313,
                         "type":  "button",
                         "var":  "",
                         "y":  57,
                         "w":  44,
                         "fmt":  "/",
                         "name":  "*/",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  5,
                         "type":  "button",
                         "var":  "",
                         "y":  121,
                         "w":  44,
                         "fmt":  "²",
                         "name":  "*²",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  49,
                         "type":  "button",
                         "var":  "",
                         "y":  121,
                         "w":  44,
                         "fmt":  "é",
                         "name":  "*é",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  93,
                         "type":  "button",
                         "var":  "",
                         "y":  121,
                         "w":  44,
                         "fmt":  "(",
                         "name":  "*(",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  137,
                         "type":  "button",
                         "var":  "",
                         "y":  121,
                         "w":  44,
                         "fmt":  "è",
                         "name":  "*è",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  181,
                         "type":  "button",
                         "var":  "",
                         "y":  121,
                         "w":  44,
                         "fmt":  "_",
                         "name":  "*_",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  225,
                         "type":  "button",
                         "var":  "",
                         "y":  121,
                         "w":  44,
                         "fmt":  "ç",
                         "name":  "*ç",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  269,
                         "type":  "button",
                         "var":  "",
                         "y":  121,
                         "w":  44,
                         "fmt":  "à",
                         "name":  "*à",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  313,
                         "type":  "button",
                         "var":  "",
                         "y":  121,
                         "w":  44,
                         "fmt":  ")",
                         "name":  "*)",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  357,
                         "type":  "button",
                         "var":  "",
                         "y":  121,
                         "w":  44,
                         "fmt":  "+",
                         "name":  "*+",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  401,
                         "type":  "button",
                         "var":  "",
                         "y":  121,
                         "w":  44,
                         "fmt":  "=",
                         "name":  "*=",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  445,
                         "type":  "button",
                         "var":  "",
                         "y":  121,
                         "w":  44,
                         "fmt":  "$",
                         "name":  "*$",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  489,
                         "type":  "button",
                         "var":  "",
                         "y":  121,
                         "w":  44,
                         "fmt":  "[",
                         "name":  "*[",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  533,
                         "type":  "button",
                         "var":  "",
                         "y":  121,
                         "w":  44,
                         "fmt":  "]",
                         "name":  "*]",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  445,
                         "type":  "button",
                         "var":  "",
                         "y":  57,
                         "w":  44,
                         "fmt":  ";",
                         "name":  "*;",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  357,
                         "type":  "button",
                         "var":  "",
                         "y":  57,
                         "w":  44,
                         "fmt":  ":",
                         "name":  "*:",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  5,
                         "type":  "button",
                         "var":  "",
                         "y":  57,
                         "w":  44,
                         "fmt":  "ë",
                         "name":  "*ë",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  49,
                         "type":  "button",
                         "var":  "",
                         "y":  57,
                         "w":  44,
                         "fmt":  "ü",
                         "name":  "*ü",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  93,
                         "type":  "button",
                         "var":  "",
                         "y":  57,
                         "w":  44,
                         "fmt":  "ï",
                         "name":  "*ï",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  137,
                         "type":  "button",
                         "var":  "",
                         "y":  57,
                         "w":  44,
                         "fmt":  "ê",
                         "name":  "*ê",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  181,
                         "type":  "button",
                         "var":  "",
                         "y":  57,
                         "w":  44,
                         "fmt":  "û",
                         "name":  "*û",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  225,
                         "type":  "button",
                         "var":  "",
                         "y":  57,
                         "w":  44,
                         "fmt":  "î",
                         "name":  "*î",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  269,
                         "type":  "button",
                         "var":  "",
                         "y":  57,
                         "w":  44,
                         "fmt":  "\u0026\u0026",
                         "name":  "*\u0026\u0026",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  489,
                         "type":  "button",
                         "var":  "",
                         "y":  57,
                         "w":  44,
                         "fmt":  "°",
                         "name":  "*°",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  533,
                         "type":  "button",
                         "var":  "",
                         "y":  57,
                         "w":  44,
                         "fmt":  "§",
                         "name":  "*§",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  8,
                         "type":  "edit",
                         "var":  "",
                         "y":  6,
                         "w":  565,
                         "fmt":  "",
                         "name":  "V Keyboard Input",
                         "h":  12,
                         "color":  "144",
                         "text":  "",
                         "parent":  50
                     }
                 ],
    "taskId":  "310",
    "height":  282
}
-->

<details>
<summary><strong>Champs : 2 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 8,6 | (sans nom) | - | edit |
| 8,6 | V Keyboard Input | - | edit |

</details>

<details>
<summary><strong>Boutons : 83 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Validate | 352,29 | Valide la saisie et enregistre |
| A | 93,185 | Bouton fonctionnel |
| Z | 137,185 | Bouton fonctionnel |
| E | 181,185 | Bouton fonctionnel |
| R | 225,185 | Bouton fonctionnel |
| T | 269,185 | Bouton fonctionnel |
| Y | 313,185 | Bouton fonctionnel |
| U | 357,185 | Bouton fonctionnel |
| I | 401,185 | Bouton fonctionnel |
| O | 445,185 | Bouton fonctionnel |
| P | 489,185 | Bouton fonctionnel |
| MAJ | 56,217 | Bouton fonctionnel |
| Q | 108,217 | Bouton fonctionnel |
| S | 152,217 | Bouton fonctionnel |
| D | 196,217 | Bouton fonctionnel |
| F | 240,217 | Bouton fonctionnel |
| G | 284,217 | Bouton fonctionnel |
| H | 328,217 | Bouton fonctionnel |
| J | 372,217 | Bouton fonctionnel |
| K | 416,217 | Bouton fonctionnel |
| L | 460,217 | Bouton fonctionnel |
| M | 504,217 | Bouton fonctionnel |
| Clear | 56,249 | Bouton fonctionnel |
| W | 127,249 | Bouton fonctionnel |
| X | 171,249 | Bouton fonctionnel |
| C | 215,249 | Bouton fonctionnel |
| V | 259,249 | Bouton fonctionnel |
| B | 303,249 | Bouton fonctionnel |
| N | 347,249 | Bouton fonctionnel |
| - | 391,249 | Bouton fonctionnel |
| ' | 431,249 | Bouton fonctionnel |
| Backspace | 471,249 | Bouton fonctionnel |
| Space | 514,249 | Bouton fonctionnel |
| Exit | 486,29 | Quitte le programme |
| 1 | 75,153 | Bouton fonctionnel |
| 2 | 119,153 | Bouton fonctionnel |
| 3 | 163,153 | Bouton fonctionnel |
| 4 | 207,153 | Bouton fonctionnel |
| 5 | 251,153 | Bouton fonctionnel |
| 6 | 295,153 | Bouton fonctionnel |
| 7 | 339,153 | Bouton fonctionnel |
| 8 | 383,153 | Bouton fonctionnel |
| 9 | 427,153 | Bouton fonctionnel |
| 0 | 471,153 | Bouton fonctionnel |
| ~ | 5,89 | Bouton fonctionnel |
| " | 49,89 | Bouton fonctionnel |
| { | 93,89 | Bouton fonctionnel |
| \ | 137,89 | Bouton fonctionnel |
| @ | 181,89 | Bouton fonctionnel |
| £ | 225,89 | Bouton fonctionnel |
| ù | 269,89 | Bouton fonctionnel |
| % | 313,89 | Bouton fonctionnel |
| * | 357,89 | Bouton fonctionnel |
| µ | 401,89 | Bouton fonctionnel |
| ? | 445,89 | Bouton fonctionnel |
| , | 489,89 | Bouton fonctionnel |
| } | 533,89 | Bouton fonctionnel |
| . | 401,57 | Bouton fonctionnel |
| / | 313,57 | Bouton fonctionnel |
| ² | 5,121 | Bouton fonctionnel |
| é | 49,121 | Bouton fonctionnel |
| ( | 93,121 | Bouton fonctionnel |
| è | 137,121 | Bouton fonctionnel |
| _ | 181,121 | Bouton fonctionnel |
| ç | 225,121 | Bouton fonctionnel |
| à | 269,121 | Bouton fonctionnel |
| ) | 313,121 | Bouton fonctionnel |
| + | 357,121 | Bouton fonctionnel |
| = | 401,121 | Bouton fonctionnel |
| $ | 445,121 | Bouton fonctionnel |
| [ | 489,121 | Bouton fonctionnel |
| ] | 533,121 | Bouton fonctionnel |
| ; | 445,57 | Bouton fonctionnel |
| : | 357,57 | Bouton fonctionnel |
| ë | 5,57 | Bouton fonctionnel |
| ü | 49,57 | Bouton fonctionnel |
| ï | 93,57 | Bouton fonctionnel |
| ê | 137,57 | Bouton fonctionnel |
| û | 181,57 | Bouton fonctionnel |
| î | 225,57 | Bouton fonctionnel |
| (sans nom) | 269,57 | Action declenchee |
| ° | 489,57 | Bouton fonctionnel |
| § | 533,57 | Bouton fonctionnel |

</details>

## 9. NAVIGATION

Ecran unique: **Keyboard2**

### 9.3 Structure hierarchique (2 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **310.1** | [**Keyboard2** (310)](#t1) [mockup](#ecran-t1) | MDI | 577x282 | Traitement |
| **310.2** | [**Calcul** (310.1)](#t2) | MDI | - | Calcul |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Traitement principal]
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

### Tables utilisees (0)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|

### Colonnes par table (0 / 0 tables avec colonnes identifiees)

## 11. VARIABLES

### 11.1 Parametres entrants (3)

Variables recues du programme appelant ([Recherche Adresse Mail (IDE 199)](PVE-IDE-199.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P. Saisie keyboard | Alpha | [310](#t1) |
| B | P. vient de M(ain) | Alpha | - |
| C | P.Password | Logical | 2x parametre entrant |

### 11.2 Variables de session (2)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| D | V Keyboard Input | Alpha | [310](#t1) |
| E | V.Keyboard pwd | Alpha | 1x session |

### 11.3 Autres (2)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| F | L Touche MAJ/Min | Logical | 27x refs |
| G | BP. Validate | Alpha | - |

## 12. EXPRESSIONS

**36 / 36 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONDITION | 27 | 5 |
| CONSTANTE | 2 | 0 |
| CAST_LOGIQUE | 1 | 0 |
| OTHER | 2 | 0 |
| NEGATION | 1 | 0 |
| STRING | 3 | 0 |

### 12.2 Expressions cles par type

#### CONDITION (27 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 4 | `IF (L Touche MAJ/Min [F],'MAJ','Min')` | [RM-001](#rm-RM-001) |
| CONDITION | 21 | `IF (L Touche MAJ/Min [F],'J','j')` | - |
| CONDITION | 22 | `IF (L Touche MAJ/Min [F],'K','k')` | - |
| CONDITION | 23 | `IF (L Touche MAJ/Min [F],'L','l')` | - |
| CONDITION | 18 | `IF (L Touche MAJ/Min [F],'F','f')` | - |
| ... | | *+22 autres* | |

#### CONSTANTE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 3 | `'&Validate'` | - |
| CONSTANTE | 1 | `''` | - |

#### CAST_LOGIQUE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 2 | `'TRUE'LOG` | - |

#### OTHER (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 34 | `P.Password [C]` | - |
| OTHER | 33 | `ASCIIChr(38)` | - |

#### NEGATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| NEGATION | 35 | `NOT P.Password [C]` | - |

#### STRING (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| STRING | 36 | `Trim(P. Saisie keyboard [A])` | - |
| STRING | 32 | `Trim(V.Keyboard pwd [E])` | - |
| STRING | 31 | `Trim(V Keyboard Input [D])` | - |

### 12.3 Toutes les expressions (36)

<details>
<summary>Voir les 36 expressions</summary>

#### CONDITION (27)

| IDE | Expression Decodee |
|-----|-------------------|
| 4 | `IF (L Touche MAJ/Min [F],'MAJ','Min')` |
| 5 | `IF (L Touche MAJ/Min [F],'A','a')` |
| 6 | `IF (L Touche MAJ/Min [F],'Z','z')` |
| 7 | `IF (L Touche MAJ/Min [F],'E','e')` |
| 8 | `IF (L Touche MAJ/Min [F],'R','r')` |
| 9 | `IF (L Touche MAJ/Min [F],'T','t')` |
| 10 | `IF (L Touche MAJ/Min [F],'Y','y')` |
| 11 | `IF (L Touche MAJ/Min [F],'U','u')` |
| 12 | `IF (L Touche MAJ/Min [F],'I','i')` |
| 13 | `IF (L Touche MAJ/Min [F],'O','o')` |
| 14 | `IF (L Touche MAJ/Min [F],'P','p')` |
| 15 | `IF (L Touche MAJ/Min [F],'Q','q')` |
| 16 | `IF (L Touche MAJ/Min [F],'S','s')` |
| 17 | `IF (L Touche MAJ/Min [F],'D','d')` |
| 18 | `IF (L Touche MAJ/Min [F],'F','f')` |
| 19 | `IF (L Touche MAJ/Min [F],'G','g')` |
| 20 | `IF (L Touche MAJ/Min [F],'H','h')` |
| 21 | `IF (L Touche MAJ/Min [F],'J','j')` |
| 22 | `IF (L Touche MAJ/Min [F],'K','k')` |
| 23 | `IF (L Touche MAJ/Min [F],'L','l')` |
| 24 | `IF (L Touche MAJ/Min [F],'M','m')` |
| 25 | `IF (L Touche MAJ/Min [F],'W','w')` |
| 26 | `IF (L Touche MAJ/Min [F],'X','x')` |
| 27 | `IF (L Touche MAJ/Min [F],'C','c')` |
| 28 | `IF (L Touche MAJ/Min [F],'V','v')` |
| 29 | `IF (L Touche MAJ/Min [F],'B','b')` |
| 30 | `IF (L Touche MAJ/Min [F],'N','n')` |

#### CONSTANTE (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 1 | `''` |
| 3 | `'&Validate'` |

#### CAST_LOGIQUE (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 2 | `'TRUE'LOG` |

#### OTHER (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 33 | `ASCIIChr(38)` |
| 34 | `P.Password [C]` |

#### NEGATION (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 35 | `NOT P.Password [C]` |

#### STRING (3)

| IDE | Expression Decodee |
|-----|-------------------|
| 31 | `Trim(V Keyboard Input [D])` |
| 32 | `Trim(V.Keyboard pwd [E])` |
| 36 | `Trim(P. Saisie keyboard [A])` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Recherche Adresse Mail (IDE 199)](PVE-IDE-199.md) -> **Keyboard2 (IDE 310)**

Main -> ... -> [Recherche Adresse Mail (IDE 308)](PVE-IDE-308.md) -> **Keyboard2 (IDE 310)**

```mermaid
graph LR
    T310[310 Keyboard2]
    style T310 fill:#58a6ff
    CC204[204 Choice Re_Print In...]
    style CC204 fill:#8b5cf6
    CC438[438 Print Invoice or T...]
    style CC438 fill:#8b5cf6
    CC403[403 Menu Main TPE]
    style CC403 fill:#8b5cf6
    CC429[429 Print Invoice or T...]
    style CC429 fill:#8b5cf6
    CC414[414 Print Invoice or T...]
    style CC414 fill:#8b5cf6
    CC186[186 Main Sale]
    style CC186 fill:#8b5cf6
    CC197[197 Saisie Signature]
    style CC197 fill:#8b5cf6
    CC189[189 Generate Preview P...]
    style CC189 fill:#8b5cf6
    CC187[187 Main Sale-664]
    style CC187 fill:#8b5cf6
    CC199[199 Recherche Adresse ...]
    style CC199 fill:#3fb950
    CC308[308 Recherche Adresse ...]
    style CC308 fill:#3fb950
    CC186 --> CC199
    CC187 --> CC199
    CC189 --> CC199
    CC197 --> CC199
    CC204 --> CC199
    CC403 --> CC199
    CC414 --> CC199
    CC429 --> CC199
    CC438 --> CC199
    CC186 --> CC308
    CC187 --> CC308
    CC189 --> CC308
    CC197 --> CC308
    CC204 --> CC308
    CC403 --> CC308
    CC414 --> CC308
    CC429 --> CC308
    CC438 --> CC308
    CC199 --> T310
    CC308 --> T310
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [199](PVE-IDE-199.md) | Recherche Adresse Mail | 1 |
| [308](PVE-IDE-308.md) | Recherche Adresse Mail | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T310[310 Keyboard2]
    style T310 fill:#58a6ff
    NONE[Aucun callee]
    T310 -.-> NONE
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| - | (aucun) | - | - |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 37 | Programme compact |
| Expressions | 36 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 2.7% (1 / 37) | Code sain |
| Regles metier | 1 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 1 ecran, 0 traitement)

- **Strategie** : 1 composant(s) UI (Razor/React) avec formulaires et validation.
- Decomposer les taches en services unitaires testables.

#### Calcul (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Services de calcul purs (Domain Services).
- Migrer la logique de calcul (stock, compteurs, montants)

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 19:32*
