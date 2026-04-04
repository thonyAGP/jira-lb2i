# PBP IDE 156 - Liste CLients arrivant

> **Analyse**: Phases 1-4 2026-02-03 15:31 -> 15:31 (11s) | Assemblage 15:31
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBP |
| IDE Position | 156 |
| Nom Programme | Liste CLients arrivant |
| Fichier source | `Prg_156.xml` |
| Dossier IDE | Liste |
| Taches | 1 (1 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 20 |

## 2. DESCRIPTION FONCTIONNELLE

**Liste CLients arrivant** assure la gestion complete de ce processus, accessible depuis [Liste des arrivants (IDE 155)](PBP-IDE-155.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

**Logique metier** : 10 regles identifiees couvrant conditions metier, valeurs par defaut.

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>156 - Liste CLients ABPBDR [[ECRAN]](#ecran-t1)

**Role** : Traitement : Liste CLients ABPBDR.
**Ecran** : 1610 x 206 DLU (MDI) | [Voir mockup](#ecran-t1)
**Variables liees** : B (>CodeListe), F (>TypeListe), P (w0_TopListe), R (w0_Liste), T (b_Liste)
**Delegue a** : [  Prep tempo arrivant planning (IDE 157)](PBP-IDE-157.md), [Prepa tempo toutes GM CP SQL (IDE 327)](PBP-IDE-327.md), [Prepare tempo seminaire (IDE 328)](PBP-IDE-328.md)


## 5. REGLES METIER

10 regles identifiees:

### Autres (10 regles)

#### <a id="rm-RM-001"></a>[RM-001] Si >CodeListe [B]='D' OR >CodeListe [B]='R' alors 'R' sinon 'A')

| Element | Detail |
|---------|--------|
| **Condition** | `>CodeListe [B]='D' OR >CodeListe [B]='R'` |
| **Si vrai** | 'R' |
| **Si faux** | 'A') |
| **Variables** | B (>CodeListe) |
| **Expression source** | Expression 4 : `IF (>CodeListe [B]='D' OR >CodeListe [B]='R','R','A')` |
| **Exemple** | Si >CodeListe [B]='D' OR >CodeListe [B]='R' â†’ 'R'. Sinon â†’ 'A') |
| **Impact** | [156 - Liste CLients ABPBDR](#t1) |

#### <a id="rm-RM-002"></a>[RM-002] Traitement conditionnel si [AQ] est a zero

| Element | Detail |
|---------|--------|
| **Condition** | `[AQ]=0` |
| **Si vrai** | [AP] |
| **Si faux** | [AQ]) |
| **Expression source** | Expression 48 : `IF ([AQ]=0,[AP],[AQ])` |
| **Exemple** | Si [AQ]=0 â†’ [AP]. Sinon â†’ [AQ]) |

#### <a id="rm-RM-003"></a>[RM-003] Si w0_Heure [O]='GR' alors ExpCalc ('63'EXP) sinon ExpCalc ('57'EXP))

| Element | Detail |
|---------|--------|
| **Condition** | `w0_Heure [O]='GR'` |
| **Si vrai** | ExpCalc ('63'EXP) |
| **Si faux** | ExpCalc ('57'EXP)) |
| **Variables** | O (w0_Heure) |
| **Expression source** | Expression 51 : `IF (w0_Heure [O]='GR',ExpCalc ('63'EXP),ExpCalc ('57'EXP))` |
| **Exemple** | Si w0_Heure [O]='GR' â†’ ExpCalc ('63'EXP). Sinon â†’ ExpCalc ('57'EXP)) |

#### <a id="rm-RM-004"></a>[RM-004] Si >CodeListe [B]='D' alors 'R' sinon 'A')

| Element | Detail |
|---------|--------|
| **Condition** | `>CodeListe [B]='D'` |
| **Si vrai** | 'R' |
| **Si faux** | 'A') |
| **Variables** | B (>CodeListe) |
| **Expression source** | Expression 59 : `IF (>CodeListe [B]='D','R','A')` |
| **Exemple** | Si >CodeListe [B]='D' â†’ 'R'. Sinon â†’ 'A') |
| **Impact** | [156 - Liste CLients ABPBDR](#t1) |

#### <a id="rm-RM-005"></a>[RM-005] Si [AT]='VV1' alors 0 sinon IF ([AT]='VV2',13,IF ([AT]='VV3',20,[AU])))

| Element | Detail |
|---------|--------|
| **Condition** | `[AT]='VV1'` |
| **Si vrai** | 0 |
| **Si faux** | IF ([AT]='VV2',13,IF ([AT]='VV3',20,[AU]))) |
| **Expression source** | Expression 67 : `IF ([AT]='VV1',0,IF ([AT]='VV2',13,IF ([AT]='VV3',20,[AU])))` |
| **Exemple** | Si [AT]='VV1' â†’ 0. Sinon â†’ IF ([AT]='VV2',13,IF ([AT]='VV3',20,[AU]))) |

#### <a id="rm-RM-006"></a>[RM-006] Traitement si Trim(w0_LieuSejour [U]) est renseigne

| Element | Detail |
|---------|--------|
| **Condition** | `Trim(w0_LieuSejour [U])<>''` |
| **Si vrai** | b_Date [M] |
| **Si faux** | 0) |
| **Variables** | M (b_Date), U (w0_LieuSejour) |
| **Expression source** | Expression 70 : `IF (Trim(w0_LieuSejour [U])<>'',b_Date [M],0)` |
| **Exemple** | Si Trim(w0_LieuSejour [U])<>'' â†’ b_Date [M]. Sinon â†’ 0) |

#### <a id="rm-RM-007"></a>[RM-007] Traitement conditionnel si [AU] est a zero

| Element | Detail |
|---------|--------|
| **Condition** | `[AU]=0` |
| **Si vrai** | 24 |
| **Si faux** | [AU]) |
| **Expression source** | Expression 74 : `IF ([AU]=0,24,[AU])` |
| **Exemple** | Si [AU]=0 â†’ 24. Sinon â†’ [AU]) |

#### <a id="rm-RM-008"></a>[RM-008] Si InStr ('DRP' alors >CodeListe [B])>0 sinon 0,w0_OkVol [K])

| Element | Detail |
|---------|--------|
| **Condition** | `InStr ('DRP'` |
| **Si vrai** | >CodeListe [B])>0 |
| **Si faux** | 0,w0_OkVol [K]) |
| **Variables** | B (>CodeListe), K (w0_OkVol) |
| **Expression source** | Expression 77 : `IF (InStr ('DRP',>CodeListe [B])>0,0,w0_OkVol [K])` |
| **Exemple** | Si InStr ('DRP' â†’ >CodeListe [B])>0. Sinon â†’ 0,w0_OkVol [K]) |
| **Impact** | [156 - Liste CLients ABPBDR](#t1) |

#### <a id="rm-RM-009"></a>[RM-009] Si InStr ('DR' alors >CodeListe [B])>0 sinon 0,w0_OkVol [K])

| Element | Detail |
|---------|--------|
| **Condition** | `InStr ('DR'` |
| **Si vrai** | >CodeListe [B])>0 |
| **Si faux** | 0,w0_OkVol [K]) |
| **Variables** | B (>CodeListe), K (w0_OkVol) |
| **Expression source** | Expression 78 : `IF (InStr ('DR',>CodeListe [B])>0,0,w0_OkVol [K])` |
| **Exemple** | Si InStr ('DR' â†’ >CodeListe [B])>0. Sinon â†’ 0,w0_OkVol [K]) |
| **Impact** | [156 - Liste CLients ABPBDR](#t1) |

#### <a id="rm-RM-010"></a>[RM-010] Valeur par defaut si [FT] est vide

| Element | Detail |
|---------|--------|
| **Condition** | `[FT]=''` |
| **Si vrai** | 'T' |
| **Si faux** | [FT]) |
| **Expression source** | Expression 149 : `IF([FT]='','T',[FT])` |
| **Exemple** | Si [FT]='' â†’ 'T'. Sinon â†’ [FT]) |

## 6. CONTEXTE

- **Appele par**: [Liste des arrivants (IDE 155)](PBP-IDE-155.md)
- **Appelle**: 20 programmes | **Tables**: 4 (W:0 R:1 L:3) | **Taches**: 1 | **Expressions**: 149

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 1)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 156 | 156 | Liste CLients ABPBDR | MDI | 1610 | 206 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>156 - Liste CLients ABPBDR
**Tache** : [156](#t1) | **Type** : MDI | **Dimensions** : 1610 x 206 DLU
**Bloc** : Traitement | **Titre IDE** : Liste CLients ABPBDR

<!-- FORM-DATA:
{
    "width":  1610,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  1,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  1603,
                         "fmt":  "",
                         "name":  "",
                         "h":  20,
                         "color":  "1",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  381,
                         "type":  "label",
                         "var":  "",
                         "y":  23,
                         "w":  393,
                         "fmt":  "",
                         "name":  "",
                         "h":  149,
                         "color":  "195",
                         "text":  "Paramètres",
                         "parent":  null
                     },
                     {
                         "x":  7,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "110",
                         "w":  371,
                         "y":  26,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  11,
                         "h":  145,
                         "cols":  [
                                      {
                                          "title":  "",
                                          "layer":  1,
                                          "w":  336
                                      }
                                  ],
                         "rows":  1
                     },
                     {
                         "x":  1152,
                         "type":  "label",
                         "var":  "",
                         "y":  27,
                         "w":  263,
                         "fmt":  "",
                         "name":  "",
                         "h":  145,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  1152,
                         "type":  "label",
                         "var":  "",
                         "y":  27,
                         "w":  263,
                         "fmt":  "",
                         "name":  "",
                         "h":  49,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  1152,
                         "type":  "label",
                         "var":  "",
                         "y":  27,
                         "w":  263,
                         "fmt":  "",
                         "name":  "",
                         "h":  49,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  1418,
                         "type":  "label",
                         "var":  "",
                         "y":  27,
                         "w":  178,
                         "fmt":  "",
                         "name":  "",
                         "h":  143,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  1165,
                         "type":  "label",
                         "var":  "",
                         "y":  33,
                         "w":  96,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Port Arrivee",
                         "parent":  7
                     },
                     {
                         "x":  1165,
                         "type":  "label",
                         "var":  "",
                         "y":  34,
                         "w":  82,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Seminaire",
                         "parent":  8
                     },
                     {
                         "x":  494,
                         "type":  "label",
                         "var":  "",
                         "y":  33,
                         "w":  215,
                         "fmt":  "",
                         "name":  "",
                         "h":  36,
                         "color":  "",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  1181,
                         "type":  "label",
                         "var":  "",
                         "y":  40,
                         "w":  109,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Age Minimum",
                         "parent":  9
                     },
                     {
                         "x":  524,
                         "type":  "label",
                         "var":  "",
                         "y":  39,
                         "w":  46,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "Total",
                         "parent":  14
                     },
                     {
                         "x":  1181,
                         "type":  "label",
                         "var":  "",
                         "y":  56,
                         "w":  114,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Age Maximum",
                         "parent":  9
                     },
                     {
                         "x":  524,
                         "type":  "label",
                         "var":  "",
                         "y":  54,
                         "w":  78,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "Selection",
                         "parent":  14
                     },
                     {
                         "x":  1168,
                         "type":  "label",
                         "var":  "",
                         "y":  59,
                         "w":  45,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Date",
                         "parent":  7
                     },
                     {
                         "x":  1157,
                         "type":  "line",
                         "var":  "",
                         "y":  75,
                         "w":  256,
                         "fmt":  "",
                         "name":  "",
                         "h":  0,
                         "color":  "",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  1168,
                         "type":  "label",
                         "var":  "",
                         "y":  81,
                         "w":  98,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Dernier Port",
                         "parent":  7
                     },
                     {
                         "x":  387,
                         "type":  "label",
                         "var":  "",
                         "y":  76,
                         "w":  82,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "Date",
                         "parent":  5
                     },
                     {
                         "x":  672,
                         "type":  "label",
                         "var":  "",
                         "y":  76,
                         "w":  54,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "Heure",
                         "parent":  5
                     },
                     {
                         "x":  1168,
                         "type":  "label",
                         "var":  "",
                         "y":  104,
                         "w":  45,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Date",
                         "parent":  7
                     },
                     {
                         "x":  387,
                         "type":  "label",
                         "var":  "",
                         "y":  90,
                         "w":  82,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "Liste",
                         "parent":  5
                     },
                     {
                         "x":  1157,
                         "type":  "line",
                         "var":  "",
                         "y":  119,
                         "w":  256,
                         "fmt":  "",
                         "name":  "",
                         "h":  0,
                         "color":  "",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  1168,
                         "type":  "label",
                         "var":  "",
                         "y":  126,
                         "w":  110,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Prochain Port",
                         "parent":  7
                     },
                     {
                         "x":  385,
                         "type":  "label",
                         "var":  "",
                         "y":  105,
                         "w":  82,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "2",
                         "text":  "Vol",
                         "parent":  5
                     },
                     {
                         "x":  387,
                         "type":  "label",
                         "var":  "",
                         "y":  118,
                         "w":  90,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Lieu sejour",
                         "parent":  5
                     },
                     {
                         "x":  1168,
                         "type":  "label",
                         "var":  "",
                         "y":  150,
                         "w":  45,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Date",
                         "parent":  7
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  179,
                         "w":  1603,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "1",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  387,
                         "type":  "label",
                         "var":  "",
                         "y":  158,
                         "w":  116,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "Heure Départ",
                         "parent":  5
                     },
                     {
                         "x":  508,
                         "type":  "edit",
                         "var":  "",
                         "y":  76,
                         "w":  126,
                         "fmt":  "",
                         "name":  "w0_Date",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  636,
                         "type":  "button",
                         "var":  "",
                         "y":  76,
                         "w":  25,
                         "fmt":  "...",
                         "name":  "b_Date",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  725,
                         "type":  "edit",
                         "var":  "",
                         "y":  76,
                         "w":  33,
                         "fmt":  "",
                         "name":  "w0_Heure",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  508,
                         "type":  "edit",
                         "var":  "",
                         "y":  90,
                         "w":  182,
                         "fmt":  "",
                         "name":  "w0_Liste",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  692,
                         "type":  "button",
                         "var":  "",
                         "y":  90,
                         "w":  25,
                         "fmt":  "...",
                         "name":  "b_Liste",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  508,
                         "type":  "edit",
                         "var":  "",
                         "y":  105,
                         "w":  82,
                         "fmt":  "30",
                         "name":  "w0_CategorieVol",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  508,
                         "type":  "edit",
                         "var":  "",
                         "y":  118,
                         "w":  26,
                         "fmt":  "",
                         "name":  "w0_LieuSejour",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  539,
                         "type":  "button",
                         "var":  "",
                         "y":  118,
                         "w":  25,
                         "fmt":  "...",
                         "name":  "b_LieuSejour",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  508,
                         "type":  "checkbox",
                         "var":  "",
                         "y":  133,
                         "w":  128,
                         "fmt":  "",
                         "name":  "w0_OnlyTai",
                         "h":  10,
                         "color":  "1",
                         "text":  "Only TAI",
                         "parent":  5
                     },
                     {
                         "x":  1168,
                         "type":  "edit",
                         "var":  "",
                         "y":  45,
                         "w":  238,
                         "fmt":  "",
                         "name":  "w0_PortArrive",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  1243,
                         "type":  "edit",
                         "var":  "",
                         "y":  59,
                         "w":  126,
                         "fmt":  "DD/MM/YYYY",
                         "name":  "w0_DateArr",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  1376,
                         "type":  "button",
                         "var":  "",
                         "y":  59,
                         "w":  28,
                         "fmt":  "",
                         "name":  "b_DateArr",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  1168,
                         "type":  "edit",
                         "var":  "",
                         "y":  92,
                         "w":  238,
                         "fmt":  "",
                         "name":  "w0_DernierPort",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  1243,
                         "type":  "edit",
                         "var":  "",
                         "y":  104,
                         "w":  126,
                         "fmt":  "DD/MM/YYYY",
                         "name":  "w0_DateDernier",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  1376,
                         "type":  "button",
                         "var":  "",
                         "y":  104,
                         "w":  28,
                         "fmt":  "",
                         "name":  "b_DateDern",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  1168,
                         "type":  "edit",
                         "var":  "",
                         "y":  137,
                         "w":  238,
                         "fmt":  "",
                         "name":  "w0_ProchainPort",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  1243,
                         "type":  "edit",
                         "var":  "",
                         "y":  150,
                         "w":  126,
                         "fmt":  "DD/MM/YYYY",
                         "name":  "w0_DateProchain",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  1376,
                         "type":  "button",
                         "var":  "",
                         "y":  150,
                         "w":  28,
                         "fmt":  "",
                         "name":  "b_DateProchain",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  1322,
                         "type":  "edit",
                         "var":  "",
                         "y":  40,
                         "w":  37,
                         "fmt":  "",
                         "name":  "w0_AgeMini",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  9
                     },
                     {
                         "x":  1322,
                         "type":  "edit",
                         "var":  "",
                         "y":  56,
                         "w":  37,
                         "fmt":  "",
                         "name":  "w0_AgeMaxi",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  9
                     },
                     {
                         "x":  568,
                         "type":  "edit",
                         "var":  "",
                         "y":  119,
                         "w":  221,
                         "fmt":  "19",
                         "name":  "",
                         "h":  8,
                         "color":  "142",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  49,
                         "type":  "edit",
                         "var":  "",
                         "y":  28,
                         "w":  277,
                         "fmt":  "",
                         "name":  "QUA Libelle",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  6
                     },
                     {
                         "x":  13,
                         "type":  "checkbox",
                         "var":  "",
                         "y":  28,
                         "w":  30,
                         "fmt":  "",
                         "name":  "TUL MARQUEUR",
                         "h":  9,
                         "color":  "110",
                         "text":  "",
                         "parent":  6
                     },
                     {
                         "x":  625,
                         "type":  "edit",
                         "var":  "",
                         "y":  39,
                         "w":  56,
                         "fmt":  "",
                         "name":  "w0_Total",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  14
                     },
                     {
                         "x":  625,
                         "type":  "edit",
                         "var":  "",
                         "y":  54,
                         "w":  56,
                         "fmt":  "",
                         "name":  "w0_Selection",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  14
                     },
                     {
                         "x":  1430,
                         "type":  "button",
                         "var":  "",
                         "y":  98,
                         "w":  154,
                         "fmt":  "\u0026Ecran",
                         "name":  "b_Ecran_arr",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  10
                     },
                     {
                         "x":  1430,
                         "type":  "button",
                         "var":  "",
                         "y":  123,
                         "w":  154,
                         "fmt":  "\u0026Imprimer",
                         "name":  "b_Edition",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  10
                     },
                     {
                         "x":  6,
                         "type":  "edit",
                         "var":  "",
                         "y":  2,
                         "w":  267,
                         "fmt":  "20",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  1390,
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
                         "x":  6,
                         "type":  "edit",
                         "var":  "",
                         "y":  11,
                         "w":  325,
                         "fmt":  "30",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  1427,
                         "type":  "image",
                         "var":  "",
                         "y":  34,
                         "w":  159,
                         "fmt":  "",
                         "name":  "",
                         "h":  53,
                         "color":  "",
                         "text":  "",
                         "parent":  10
                     },
                     {
                         "x":  8,
                         "type":  "button",
                         "var":  "",
                         "y":  182,
                         "w":  154,
                         "fmt":  "\u0026Quitter",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  51
                     },
                     {
                         "x":  774,
                         "type":  "subform",
                         "var":  "",
                         "y":  22,
                         "w":  376,
                         "fmt":  "",
                         "name":  "Sel Code Logements",
                         "h":  150,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  1430,
                         "type":  "button",
                         "var":  "",
                         "y":  148,
                         "w":  154,
                         "fmt":  "E\u0026xcel",
                         "name":  "b_Excel",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  10
                     },
                     {
                         "x":  508,
                         "type":  "checkbox",
                         "var":  "",
                         "y":  145,
                         "w":  209,
                         "fmt":  "",
                         "name":  "w0_OnlyTai_0001",
                         "h":  12,
                         "color":  "",
                         "text":  "Grouper par filiation",
                         "parent":  5
                     },
                     {
                         "x":  508,
                         "type":  "combobox",
                         "var":  "",
                         "y":  158,
                         "w":  197,
                         "fmt":  "",
                         "name":  "w0_Heure fin séjour /Libération",
                         "h":  12,
                         "color":  "",
                         "text":  "S,L",
                         "parent":  5
                     },
                     {
                         "x":  1165,
                         "type":  "combobox",
                         "var":  "",
                         "y":  45,
                         "w":  238,
                         "fmt":  "",
                         "name":  "w0_NomSeminaire_0001",
                         "h":  12,
                         "color":  "",
                         "text":  "",
                         "parent":  8
                     }
                 ],
    "taskId":  "156",
    "height":  206
}
-->

<details>
<summary><strong>Champs : 25 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 508,76 | w0_Date | - | edit |
| 725,76 | w0_Heure | - | edit |
| 508,90 | w0_Liste | - | edit |
| 508,105 | w0_CategorieVol | - | edit |
| 508,118 | w0_LieuSejour | - | edit |
| 508,133 | w0_OnlyTai | - | checkbox |
| 1168,45 | w0_PortArrive | - | edit |
| 1243,59 | w0_DateArr | - | edit |
| 1168,92 | w0_DernierPort | - | edit |
| 1243,104 | w0_DateDernier | - | edit |
| 1168,137 | w0_ProchainPort | - | edit |
| 1243,150 | w0_DateProchain | - | edit |
| 1322,40 | w0_AgeMini | - | edit |
| 1322,56 | w0_AgeMaxi | - | edit |
| 568,119 | 19 | - | edit |
| 49,28 | QUA Libelle | - | edit |
| 13,28 | TUL MARQUEUR | - | checkbox |
| 625,39 | w0_Total | - | edit |
| 625,54 | w0_Selection | - | edit |
| 6,2 | 20 | - | edit |
| 1390,6 | WWW DD MMM YYYYT | - | edit |
| 6,11 | 30 | - | edit |
| 508,145 | w0_OnlyTai_0001 | - | checkbox |
| 508,158 | w0_Heure fin séjour /Libération | - | combobox |
| 1165,45 | w0_NomSeminaire_0001 | - | combobox |

</details>

<details>
<summary><strong>Boutons : 10 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| ... | 636,76 | Bouton fonctionnel |
| ... | 692,90 | Bouton fonctionnel |
| ... | 539,118 | Bouton fonctionnel |
| b_DateArr | 1376,59 | Bouton fonctionnel |
| b_DateDern | 1376,104 | Bouton fonctionnel |
| b_DateProchain | 1376,150 | Bouton fonctionnel |
| Ecran | 1430,98 | Appel [RaZ 619 tempo liste ecran (IDE 287)](PBP-IDE-287.md) |
| Imprimer | 1430,123 | Appel [  Imprim  fiche police (IDE 182)](PBP-IDE-182.md) |
| Quitter | 8,182 | Quitte le programme |
| Excel | 1430,148 | Bouton fonctionnel |

</details>

## 9. NAVIGATION

Ecran unique: **Liste CLients ABPBDR**

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **156.1** | [**Liste CLients ABPBDR** (156)](#t1) [mockup](#ecran-t1) | MDI | 1610x206 | Traitement |

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

### Tables utilisees (4)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 81 | societe__________soc |  | DB | R |   |   | 1 |
| 118 | tables_imports |  | DB |   |   | L | 1 |
| 120 | tables_qualites__qua |  | DB |   |   | L | 1 |
| 637 | tempo_zone_secteur | Table temporaire ecran | DB |   |   | L | 1 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 81 - societe__________soc (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | >CodeEcran | R | Numeric |
| B | >CodeListe | R | Alpha |
| C | >CodeSelect | R | Alpha |
| D | >Categorie | R | Alpha |
| E | >NomTable | R | Alpha |
| F | >TypeListe | R | Alpha |
| G | >Soldé,Non_soldé,Tous | R | Unicode |
| H | w0_CodeEcranFille | R | Numeric |
| I | w0_IndexGene | R | Numeric |
| J | w0_TypeVol | R | Alpha |
| K | w0_OkVol | R | Logical |
| L | w0_Date | R | Date |
| M | b_Date | R | Alpha |
| N | w0_HeureNumerique | R | Numeric |
| O | w0_Heure | R | Alpha |
| P | w0_TopListe | R | Alpha |
| Q | w0_NbSelect | R | Numeric |
| R | w0_Liste | R | Alpha |
| S | w0_Pays | R | Alpha |
| T | b_Liste | R | Alpha |
| U | w0_LieuSejour | R | Alpha |
| V | w0_CodeVol | R | Alpha |
| W | w0_Compagnie | R | Alpha |
| X | w0_DateVillageAV | R | Date |
| Y | b_DateVillageAV | R | Alpha |
| Z | w0_HeureVillageAV | R | Alpha |
| BA | w0_DateVillageDR | R | Date |
| BB | b_DateVillageDR | R | Alpha |
| BC | w0_HeureVillageDR | R | Alpha |
| BD | w0_Logement | R | Alpha |
| BE | w0_HeurePresent | R | Alpha |
| BF | w0_NomSeminaire | R | Alpha |
| BG | w0_PortArrive | R | Alpha |
| BH | w0_DateArr | R | Date |
| BI | b_DateArr | R | Alpha |
| BJ | w0_DernierPort | R | Alpha |
| BK | w0_DateDernier | R | Date |
| BL | b_DateDern | R | Alpha |
| BM | w0_ProchainPort | R | Alpha |
| BN | w0_DateProchain | R | Date |
| BO | b_DateProchain | R | Alpha |
| BP | w0_AgeMini | R | Numeric |
| BQ | w0_AgeMaxi | R | Numeric |
| BR | w0_CodeVol | R | Alpha |
| BS | w0_CodeVille | R | Alpha |
| BT | w0_CodeVV | R | Alpha |
| BU | w0_CompagnieVV | R | Alpha |
| BV | w0_HeureMin | R | Numeric |
| BW | w0_HeureMax | R | Numeric |
| BX | w0_DateDebMin | R | Date |
| BY | w0_DateDebMax | R | Date |
| BZ | w0_DateFinMin | R | Date |
| CA | w0_DateFinMax | R | Date |
| CB | w0_Soldé,Non_soldé,Tous | R | Unicode |
| CC | b_LieuSejour | R | Alpha |
| CD | w0_OnlyTai | R | Logical |
| CE | w0_grouper par filiation | R | Logical |
| CF | w0_Heure fin séjour /Libération | R | Alpha |
| CG | b_Sejour | R | Alpha |
| CH | w0_Total | R | Numeric |
| CI | w0_Selection | R | Numeric |
| CJ | v. titre | R | Alpha |
| CK | W0 nom societe | R | Alpha |
| CL | W0 date minimum | R | Date |
| CM | b_DateMini | R | Alpha |
| CN | w0_SejourMulti | R | Logical |
| CO | w0_AgeBebe | R | Numeric |
| CP | w0_AgeEnfant | R | Numeric |
| CQ | b_Ecran | R | Alpha |
| CR | b_Edition | R | Alpha |
| CS | v.Nom Fichier Excel | R | Alpha |
| CT | w0_CategorieVol | R | Alpha |

</details>

## 11. VARIABLES

### 11.1 Variables de session (2)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| CJ | v. titre | Alpha | - |
| CS | v.Nom Fichier Excel | Alpha | - |

### 11.2 Variables de travail (2)

Variables internes au programme.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| CK | W0 nom societe | Alpha | - |
| CL | W0 date minimum | Date | - |

### 11.3 Autres (68)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | >CodeEcran | Numeric | - |
| B | >CodeListe | Alpha | 14x refs |
| C | >CodeSelect | Alpha | - |
| D | >Categorie | Alpha | 1x refs |
| E | >NomTable | Alpha | 1x refs |
| F | >TypeListe | Alpha | - |
| G | >Soldé,Non_soldé,Tous | Unicode | - |
| H | w0_CodeEcranFille | Numeric | - |
| I | w0_IndexGene | Numeric | - |
| J | w0_TypeVol | Alpha | - |
| K | w0_OkVol | Logical | 8x refs |
| L | w0_Date | Date | 4x refs |
| M | b_Date | Alpha | 6x refs |
| N | w0_HeureNumerique | Numeric | 1x refs |
| O | w0_Heure | Alpha | 42x refs |
| P | w0_TopListe | Alpha | - |
| Q | w0_NbSelect | Numeric | 2x refs |
| R | w0_Liste | Alpha | - |
| S | w0_Pays | Alpha | - |
| T | b_Liste | Alpha | 2x refs |
| U | w0_LieuSejour | Alpha | 4x refs |
| V | w0_CodeVol | Alpha | 1x refs |
| W | w0_Compagnie | Alpha | 2x refs |
| X | w0_DateVillageAV | Date | 1x refs |
| Y | b_DateVillageAV | Alpha | 1x refs |
| Z | w0_HeureVillageAV | Alpha | - |
| BA | w0_DateVillageDR | Date | - |
| BB | b_DateVillageDR | Alpha | - |
| BC | w0_HeureVillageDR | Alpha | - |
| BD | w0_Logement | Alpha | - |
| BE | w0_HeurePresent | Alpha | 2x refs |
| BF | w0_NomSeminaire | Alpha | - |
| BG | w0_PortArrive | Alpha | - |
| BH | w0_DateArr | Date | 1x refs |
| BI | b_DateArr | Alpha | 1x refs |
| BJ | w0_DernierPort | Alpha | - |
| BK | w0_DateDernier | Date | - |
| BL | b_DateDern | Alpha | - |
| BM | w0_ProchainPort | Alpha | - |
| BN | w0_DateProchain | Date | - |
| BO | b_DateProchain | Alpha | - |
| BP | w0_AgeMini | Numeric | - |
| BQ | w0_AgeMaxi | Numeric | - |
| BR | w0_CodeVol | Alpha | 1x refs |
| BS | w0_CodeVille | Alpha | - |
| BT | w0_CodeVV | Alpha | - |
| BU | w0_CompagnieVV | Alpha | 2x refs |
| BV | w0_HeureMin | Numeric | 1x refs |
| BW | w0_HeureMax | Numeric | - |
| BX | w0_DateDebMin | Date | - |
| BY | w0_DateDebMax | Date | 1x refs |
| BZ | w0_DateFinMin | Date | 1x refs |
| CA | w0_DateFinMax | Date | - |
| CB | w0_Soldé,Non_soldé,Tous | Unicode | 1x refs |
| CC | b_LieuSejour | Alpha | - |
| CD | w0_OnlyTai | Logical | - |
| CE | w0_grouper par filiation | Logical | - |
| CF | w0_Heure fin séjour /Libération | Alpha | - |
| CG | b_Sejour | Alpha | - |
| CH | w0_Total | Numeric | - |
| CI | w0_Selection | Numeric | - |
| CM | b_DateMini | Alpha | - |
| CN | w0_SejourMulti | Logical | - |
| CO | w0_AgeBebe | Numeric | - |
| CP | w0_AgeEnfant | Numeric | - |
| CQ | b_Ecran | Alpha | - |
| CR | b_Edition | Alpha | - |
| CT | w0_CategorieVol | Alpha | - |

<details>
<summary>Toutes les 72 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| W0 | **CK** | W0 nom societe | Alpha |
| W0 | **CL** | W0 date minimum | Date |
| V. | **CJ** | v. titre | Alpha |
| V. | **CS** | v.Nom Fichier Excel | Alpha |
| Autre | **A** | >CodeEcran | Numeric |
| Autre | **B** | >CodeListe | Alpha |
| Autre | **C** | >CodeSelect | Alpha |
| Autre | **D** | >Categorie | Alpha |
| Autre | **E** | >NomTable | Alpha |
| Autre | **F** | >TypeListe | Alpha |
| Autre | **G** | >Soldé,Non_soldé,Tous | Unicode |
| Autre | **H** | w0_CodeEcranFille | Numeric |
| Autre | **I** | w0_IndexGene | Numeric |
| Autre | **J** | w0_TypeVol | Alpha |
| Autre | **K** | w0_OkVol | Logical |
| Autre | **L** | w0_Date | Date |
| Autre | **M** | b_Date | Alpha |
| Autre | **N** | w0_HeureNumerique | Numeric |
| Autre | **O** | w0_Heure | Alpha |
| Autre | **P** | w0_TopListe | Alpha |
| Autre | **Q** | w0_NbSelect | Numeric |
| Autre | **R** | w0_Liste | Alpha |
| Autre | **S** | w0_Pays | Alpha |
| Autre | **T** | b_Liste | Alpha |
| Autre | **U** | w0_LieuSejour | Alpha |
| Autre | **V** | w0_CodeVol | Alpha |
| Autre | **W** | w0_Compagnie | Alpha |
| Autre | **X** | w0_DateVillageAV | Date |
| Autre | **Y** | b_DateVillageAV | Alpha |
| Autre | **Z** | w0_HeureVillageAV | Alpha |
| Autre | **BA** | w0_DateVillageDR | Date |
| Autre | **BB** | b_DateVillageDR | Alpha |
| Autre | **BC** | w0_HeureVillageDR | Alpha |
| Autre | **BD** | w0_Logement | Alpha |
| Autre | **BE** | w0_HeurePresent | Alpha |
| Autre | **BF** | w0_NomSeminaire | Alpha |
| Autre | **BG** | w0_PortArrive | Alpha |
| Autre | **BH** | w0_DateArr | Date |
| Autre | **BI** | b_DateArr | Alpha |
| Autre | **BJ** | w0_DernierPort | Alpha |
| Autre | **BK** | w0_DateDernier | Date |
| Autre | **BL** | b_DateDern | Alpha |
| Autre | **BM** | w0_ProchainPort | Alpha |
| Autre | **BN** | w0_DateProchain | Date |
| Autre | **BO** | b_DateProchain | Alpha |
| Autre | **BP** | w0_AgeMini | Numeric |
| Autre | **BQ** | w0_AgeMaxi | Numeric |
| Autre | **BR** | w0_CodeVol | Alpha |
| Autre | **BS** | w0_CodeVille | Alpha |
| Autre | **BT** | w0_CodeVV | Alpha |
| Autre | **BU** | w0_CompagnieVV | Alpha |
| Autre | **BV** | w0_HeureMin | Numeric |
| Autre | **BW** | w0_HeureMax | Numeric |
| Autre | **BX** | w0_DateDebMin | Date |
| Autre | **BY** | w0_DateDebMax | Date |
| Autre | **BZ** | w0_DateFinMin | Date |
| Autre | **CA** | w0_DateFinMax | Date |
| Autre | **CB** | w0_Soldé,Non_soldé,Tous | Unicode |
| Autre | **CC** | b_LieuSejour | Alpha |
| Autre | **CD** | w0_OnlyTai | Logical |
| Autre | **CE** | w0_grouper par filiation | Logical |
| Autre | **CF** | w0_Heure fin séjour /Libération | Alpha |
| Autre | **CG** | b_Sejour | Alpha |
| Autre | **CH** | w0_Total | Numeric |
| Autre | **CI** | w0_Selection | Numeric |
| Autre | **CM** | b_DateMini | Alpha |
| Autre | **CN** | w0_SejourMulti | Logical |
| Autre | **CO** | w0_AgeBebe | Numeric |
| Autre | **CP** | w0_AgeEnfant | Numeric |
| Autre | **CQ** | b_Ecran | Alpha |
| Autre | **CR** | b_Edition | Alpha |
| Autre | **CT** | w0_CategorieVol | Alpha |

</details>

## 12. EXPRESSIONS

**149 / 149 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONDITION | 70 | 10 |
| CAST_LOGIQUE | 3 | 0 |
| CONSTANTE | 47 | 0 |
| DATE | 1 | 0 |
| FORMAT | 1 | 0 |
| OTHER | 14 | 0 |
| CONCATENATION | 3 | 0 |
| REFERENCE_VG | 4 | 0 |
| NEGATION | 1 | 0 |
| STRING | 5 | 0 |

### 12.2 Expressions cles par type

#### CONDITION (70 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 70 | `IF (Trim(w0_LieuSejour [U])<>'',b_Date [M],0)` | [RM-006](#rm-RM-006) |
| CONDITION | 78 | `IF (InStr ('DR',>CodeListe [B])>0,0,w0_OkVol [K])` | [RM-009](#rm-RM-009) |
| CONDITION | 149 | `IF([FT]='','T',[FT])` | [RM-010](#rm-RM-010) |
| CONDITION | 77 | `IF (InStr ('DRP',>CodeListe [B])>0,0,w0_OkVol [K])` | [RM-008](#rm-RM-008) |
| CONDITION | 74 | `IF ([AU]=0,24,[AU])` | [RM-007](#rm-RM-007) |
| ... | | *+65 autres* | |

#### CAST_LOGIQUE (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 140 | `'TRUE'LOG` | - |
| CAST_LOGIQUE | 53 | `'FALSE'LOG` | - |
| CAST_LOGIQUE | 137 | `IF (w0_Heure [O]='GR','FALSE'LOG,'TRUE'LOG)` | - |

#### CONSTANTE (47 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 105 | `91` | - |
| CONSTANTE | 104 | `90` | - |
| CONSTANTE | 106 | `92` | - |
| CONSTANTE | 108 | `94` | - |
| CONSTANTE | 107 | `93` | - |
| ... | | *+42 autres* | |

#### DATE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| DATE | 16 | `Date ()` | - |

#### FORMAT (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| FORMAT | 139 | `Translate('%club_exportdata%')&Trim(GetParam('VILLAGE'))&
'_ARR_'&Trim(w0_NbSelect [Q])&'_'&
DStr(w0_OkVol [K],'YYYYMMDD')& IF([FP]='L','_LIBCH','_DEPVIL')&'.csv'` | - |

#### OTHER (14 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 84 | `SetCrsr (1)` | - |
| OTHER | 83 | `SetCrsr (2)` | - |
| OTHER | 72 | `w0_OkVol [K]` | - |
| OTHER | 115 | `w0_Soldé,Non_soldé,Tous [CB]` | - |
| OTHER | 141 | `[FN]` | - |
| ... | | *+9 autres* | |

#### CONCATENATION (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 146 | `Trim([FR])&Trim(w0_LieuSejour [U])` | - |
| CONCATENATION | 9 | `'C'&>CodeListe [B]&'C99'` | - |
| CONCATENATION | 8 | `'C'&>CodeListe [B]&'60'` | - |

#### REFERENCE_VG (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 143 | `VG88` | - |
| REFERENCE_VG | 147 | `VG114` | - |
| REFERENCE_VG | 15 | `VG2` | - |
| REFERENCE_VG | 20 | `VG1` | - |

#### NEGATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| NEGATION | 135 | `NOT (w0_HeurePresent [BE])` | - |

#### STRING (5 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| STRING | 75 | `Val (w0_HeureNumerique [N],'2')` | - |
| STRING | 138 | `Trim(w0_LieuSejour [U])` | - |
| STRING | 73 | `Val (w0_DateVillageAV [X],'2')` | - |
| STRING | 13 | `Str (b_Date [M],'2P0Z0')` | - |
| STRING | 14 | `Trim (w0_HeureMin [BV])` | - |

### 12.3 Toutes les expressions (149)

<details>
<summary>Voir les 149 expressions</summary>

#### CONDITION (70)

| IDE | Expression Decodee |
|-----|-------------------|
| 4 | `IF (>CodeListe [B]='D' OR >CodeListe [B]='R','R','A')` |
| 5 | `IF (>CodeListe [B]='D' OR >CodeListe [B]='R',6,IF (InStr ('AVB',>CodeListe [B])>0,5,1))` |
| 48 | `IF ([AQ]=0,[AP],[AQ])` |
| 51 | `IF (w0_Heure [O]='GR',ExpCalc ('63'EXP),ExpCalc ('57'EXP))` |
| 59 | `IF (>CodeListe [B]='D','R','A')` |
| 67 | `IF ([AT]='VV1',0,IF ([AT]='VV2',13,IF ([AT]='VV3',20,[AU])))` |
| 68 | `IF ([AT]='VV1',13,IF ([AT]='VV2',20,IF ([AT]='VV3',24,[AU])))` |
| 70 | `IF (Trim(w0_LieuSejour [U])<>'',b_Date [M],0)` |
| 71 | `IF (Trim(w0_LieuSejour [U])<>'',b_Date [M],24)` |
| 74 | `IF ([AU]=0,24,[AU])` |
| 77 | `IF (InStr ('DRP',>CodeListe [B])>0,0,w0_OkVol [K])` |
| 78 | `IF (InStr ('DR',>CodeListe [B])>0,0,w0_OkVol [K])` |
| 79 | `IF (InStr ('DRP',>CodeListe [B])>0,w0_OkVol [K],0)` |
| 80 | `IF (InStr ('DR',>CodeListe [B])>0,w0_OkVol [K],0)` |
| 149 | `IF([FT]='','T',[FT])` |
| 21 | `>Categorie [D]` |
| 22 | `>NomTable [E]` |
| 25 | `w0_Heure [O]='PL'` |
| 26 | `w0_Heure [O]='GR'` |
| 27 | `w0_Heure [O]='GR' OR w0_Heure [O]='CP'` |
| 28 | `w0_Heure [O]='RE'` |
| 29 | `w0_Heure [O]='CA'` |
| 30 | `w0_Heure [O]='MI'` |
| 31 | `w0_Heure [O]='BB'` |
| 32 | `w0_Heure [O]='SI'` |
| 33 | `w0_Heure [O]='NS'` |
| 34 | `w0_Heure [O]='PY'` |
| 35 | `w0_Heure [O]='HM'` |
| 36 | `w0_Heure [O]='VV'` |
| 37 | `w0_Heure [O]='NV'` |
| 38 | `w0_Heure [O]='AG'` |
| 39 | `w0_Heure [O]='CO'` |
| 40 | `w0_Heure [O]='PO'` |
| 41 | `w0_Heure [O]='BA'` |
| 42 | `w0_Heure [O]='SM'` |
| 43 | `w0_Heure [O]='ST'` |
| 44 | `w0_Heure [O]='SE'` |
| 45 | `w0_Heure [O]='AF'` |
| 46 | `w0_Heure [O]='CP'` |
| 47 | `w0_Heure [O]<>'CP' AND w0_Heure [O]<>'GR'` |
| 49 | `w0_Heure [O]='AG' OR w0_Heure [O]='SA'` |
| 54 | `w0_Heure [O]='RE'` |
| 55 | `>CodeListe [B]='A' OR >CodeListe [B]='V'` |
| 56 | `>CodeListe [B]='D' OR >CodeListe [B]='R'` |
| 82 | `>CodeListe [B]='P'` |
| 85 | `w0_Heure [O]='SY' OR w0_Heure [O]='SA'` |
| 86 | `NOT(w0_Heure [O]='SY' OR w0_Heure [O]='SA')` |
| 87 | `w0_Heure [O]='SY' AND >CodeListe [B]<>'P'` |
| 88 | `w0_Heure [O]='SA' OR >CodeListe [B]='P' AND w0_Heure [O]='SY'` |
| 89 | `w0_Heure [O]<>'SY' AND w0_Heure [O]<>'SA'` |
| 90 | `w0_Heure [O]='PL'` |
| 91 | `w0_Heure [O]<>'PL' AND w0_Heure [O]<>'ST' AND w0_Heure [O]<>'SE' AND w0_Heure [O]<>'PO' AND w0_Heure [O]<>'BA' AND w0_Heure [O]<>'AF'` |
| 92 | `w0_Heure [O]<>'PL' AND w0_Heure [O]<>'AF' AND w0_Heure [O]<>'SM'` |
| 93 | `w0_Heure [O]='BA' OR w0_Heure [O]='PO'` |
| 118 | `w0_NbSelect [Q]=''` |
| 119 | `w0_OkVol [K]=0` |
| 120 | `b_Date [M]=0` |
| 121 | `w0_Heure [O]=''` |
| 122 | `w0_CodeVol [V]=0` |
| 123 | `b_DateVillageAV [Y]=0` |
| 124 | `[AH]=0` |
| 125 | `[AK]=0` |
| 126 | `[AN]=0` |
| 128 | `w0_CompagnieVV [BU]>0` |
| 129 | `w0_CompagnieVV [BU]=0` |
| 130 | `w0_DateFinMin [BZ]>w0_OkVol [K]` |
| 132 | `[AV]=0` |
| 133 | `b_Liste [T]=''` |
| 134 | `w0_Heure [O]='AF' OR w0_Heure [O]='RE'` |
| 144 | `[FP]='L'` |

#### CAST_LOGIQUE (3)

| IDE | Expression Decodee |
|-----|-------------------|
| 137 | `IF (w0_Heure [O]='GR','FALSE'LOG,'TRUE'LOG)` |
| 53 | `'FALSE'LOG` |
| 140 | `'TRUE'LOG` |

#### CONSTANTE (47)

| IDE | Expression Decodee |
|-----|-------------------|
| 2 | `'VBEBE'` |
| 3 | `'VENFA'` |
| 6 | `'CP'` |
| 10 | `'Se&jour'` |
| 12 | `'...'` |
| 17 | `'Comptage'` |
| 19 | `'C'` |
| 50 | `'M'` |
| 52 | `'TNATI'` |
| 57 | `'A'` |
| 58 | `'R'` |
| 60 | `'VV1'` |
| 61 | `'VV2'` |
| 62 | `'VV3'` |
| 63 | `10` |
| 64 | `18` |
| 65 | `23` |
| 66 | `'23'` |
| 76 | `0` |
| 81 | `'GM'` |
| 94 | `80` |
| 95 | `81` |
| 96 | `82` |
| 97 | `83` |
| 98 | `84` |
| 99 | `85` |
| 100 | `86` |
| 101 | `87` |
| 102 | `88` |
| 103 | `89` |
| 104 | `90` |
| 105 | `91` |
| 106 | `92` |
| 107 | `93` |
| 108 | `94` |
| 109 | `95` |
| 110 | `96` |
| 111 | `97` |
| 112 | `98` |
| 113 | `99` |
| 114 | `100` |
| 116 | `'&Ecran'` |
| 117 | `'&Imprimer'` |
| 131 | `24` |
| 142 | `'A'` |
| 145 | `'S'` |
| 148 | `'ARR'` |

#### DATE (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 16 | `Date ()` |

#### FORMAT (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 139 | `Translate('%club_exportdata%')&Trim(GetParam('VILLAGE'))&
'_ARR_'&Trim(w0_NbSelect [Q])&'_'&
DStr(w0_OkVol [K],'YYYYMMDD')& IF([FP]='L','_LIBCH','_DEPVIL')&'.csv'` |

#### OTHER (14)

| IDE | Expression Decodee |
|-----|-------------------|
| 1 | `GetParam ('LIEU_SEJOUR')` |
| 7 | `w0_DateDebMax [BY]` |
| 11 | `b_Liste [T]` |
| 18 | `GetParam ('SOCIETE')` |
| 23 | `w0_DateArr [BH]` |
| 24 | `b_DateArr [BI]` |
| 69 | `[AU]` |
| 72 | `w0_OkVol [K]` |
| 83 | `SetCrsr (2)` |
| 84 | `SetCrsr (1)` |
| 115 | `w0_Soldé,Non_soldé,Tous [CB]` |
| 127 | `GetParam ('VILLAGE')` |
| 136 | `w0_HeurePresent [BE]` |
| 141 | `[FN]` |

#### CONCATENATION (3)

| IDE | Expression Decodee |
|-----|-------------------|
| 8 | `'C'&>CodeListe [B]&'60'` |
| 9 | `'C'&>CodeListe [B]&'C99'` |
| 146 | `Trim([FR])&Trim(w0_LieuSejour [U])` |

#### REFERENCE_VG (4)

| IDE | Expression Decodee |
|-----|-------------------|
| 15 | `VG2` |
| 20 | `VG1` |
| 143 | `VG88` |
| 147 | `VG114` |

#### NEGATION (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 135 | `NOT (w0_HeurePresent [BE])` |

#### STRING (5)

| IDE | Expression Decodee |
|-----|-------------------|
| 13 | `Str (b_Date [M],'2P0Z0')` |
| 14 | `Trim (w0_HeureMin [BV])` |
| 73 | `Val (w0_DateVillageAV [X],'2')` |
| 75 | `Val (w0_HeureNumerique [N],'2')` |
| 138 | `Trim(w0_LieuSejour [U])` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Liste des arrivants (IDE 155)](PBP-IDE-155.md) -> **Liste CLients arrivant (IDE 156)**

```mermaid
graph LR
    T156[156 Liste CLients arri...]
    style T156 fill:#58a6ff
    CC155[155 Liste des arrivants]
    style CC155 fill:#8b5cf6
    CC155 --> T156
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [155](PBP-IDE-155.md) | Liste des arrivants | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T156[156 Liste CLients arri...]
    style T156 fill:#58a6ff
    C324[324 Creation categorie...]
    T156 --> C324
    style C324 fill:#3fb950
    C400[400 Selection Vols]
    T156 --> C400
    style C400 fill:#3fb950
    C403[403 Selection heure Vol]
    T156 --> C403
    style C403 fill:#3fb950
    C157[157 Prep tempo arrivan...]
    T156 --> C157
    style C157 fill:#3fb950
    C182[182 Imprim fiche police]
    T156 --> C182
    style C182 fill:#3fb950
    C188[188 Imprime Synthese]
    T156 --> C188
    style C188 fill:#3fb950
    C220[220 Calcul Facilitate ...]
    T156 --> C220
    style C220 fill:#3fb950
    C285[285 RaZ 604 tempo depart]
    T156 --> C285
    style C285 fill:#3fb950
    C286[286 RaZ 634 tempo synt...]
    T156 --> C286
    style C286 fill:#3fb950
    C287[287 RaZ 619 tempo list...]
    T156 --> C287
    style C287 fill:#3fb950
    C299[299 RaZ 598 tempo comp...]
    T156 --> C299
    style C299 fill:#3fb950
    C307[307 Recherche age Bebe...]
    T156 --> C307
    style C307 fill:#3fb950
    C325[325 Creation synthese GM]
    T156 --> C325
    style C325 fill:#3fb950
    C326[326 Creation synthese ...]
    T156 --> C326
    style C326 fill:#3fb950
    C327[327 Prepa tempo toutes...]
    T156 --> C327
    style C327 fill:#3fb950
    C328[328 Prepare tempo semi...]
    T156 --> C328
    style C328 fill:#3fb950
    C332[332 Preparation affich...]
    T156 --> C332
    style C332 fill:#3fb950
    C333[333 Cumul synthese]
    T156 --> C333
    style C333 fill:#3fb950
    C399[399 Selection lieu sejour]
    T156 --> C399
    style C399 fill:#3fb950
    C158[158 Affich arrivant pl...]
    T156 --> C158
    style C158 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [324](PBP-IDE-324.md) | Creation categorie comptage | 3 | Sous-programme |
| [400](PBP-IDE-400.md) | Selection Vols | 3 | Selection/consultation |
| [403](PBP-IDE-403.md) | Selection heure / Vol | 3 | Selection/consultation |
| [157](PBP-IDE-157.md) |   Prep tempo arrivant planning | 2 | Sous-programme |
| [182](PBP-IDE-182.md) |   Imprim  fiche police | 2 | Impression ticket/document |
| [188](PBP-IDE-188.md) |   Imprime Synthese | 2 | Impression ticket/document |
| [220](PBP-IDE-220.md) | Calcul Facilitate Your Arrival | 2 | Calcul de donnees |
| [285](PBP-IDE-285.md) | RaZ 604 tempo depart | 2 | Reinitialisation |
| [286](PBP-IDE-286.md) | RaZ  634 tempo synthese | 2 | Reinitialisation |
| [287](PBP-IDE-287.md) | RaZ 619 tempo liste ecran | 2 | Reinitialisation |
| [299](PBP-IDE-299.md) | RaZ 598 tempo comptage | 2 | Reinitialisation |
| [307](PBP-IDE-307.md) | Recherche age Bebe_Enfant | 2 | Sous-programme |
| [325](PBP-IDE-325.md) | Creation synthese GM | 2 | Sous-programme |
| [326](PBP-IDE-326.md) | Creation synthese present reel | 2 | Sous-programme |
| [327](PBP-IDE-327.md) | Prepa tempo toutes GM CP SQL | 2 | Sous-programme |
| [328](PBP-IDE-328.md) | Prepare tempo seminaire | 2 | Sous-programme |
| [332](PBP-IDE-332.md) | Preparation affichage depart | 2 | Affichage donnees |
| [333](PBP-IDE-333.md) | Cumul synthese | 2 | Sous-programme |
| [399](PBP-IDE-399.md) | Selection lieu sejour | 2 | Selection/consultation |
| [158](PBP-IDE-158.md) |   Affich arrivant planning GM | 1 | Affichage donnees |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 353 | Taille moyenne |
| Expressions | 149 | Logique moderee |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 20 | Forte dependance |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 353) | Code sain |
| Regles metier | 10 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 1 ecran, 0 traitement)

- **Strategie** : 1 composant(s) UI (Razor/React) avec formulaires et validation.
- 20 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| [Selection heure / Vol (IDE 403)](PBP-IDE-403.md) | Sous-programme | 3x | **CRITIQUE** - Selection/consultation |
| [Selection Vols (IDE 400)](PBP-IDE-400.md) | Sous-programme | 3x | **CRITIQUE** - Selection/consultation |
| [Creation categorie comptage (IDE 324)](PBP-IDE-324.md) | Sous-programme | 3x | **CRITIQUE** - Sous-programme |
| [Creation synthese present reel (IDE 326)](PBP-IDE-326.md) | Sous-programme | 2x | Haute - Sous-programme |
| [Prepa tempo toutes GM CP SQL (IDE 327)](PBP-IDE-327.md) | Sous-programme | 2x | Haute - Sous-programme |
| [Recherche age Bebe_Enfant (IDE 307)](PBP-IDE-307.md) | Sous-programme | 2x | Haute - Sous-programme |
| [Creation synthese GM (IDE 325)](PBP-IDE-325.md) | Sous-programme | 2x | Haute - Sous-programme |
| [Cumul synthese (IDE 333)](PBP-IDE-333.md) | Sous-programme | 2x | Haute - Sous-programme |
| [Selection lieu sejour (IDE 399)](PBP-IDE-399.md) | Sous-programme | 2x | Haute - Selection/consultation |
| [Prepare tempo seminaire (IDE 328)](PBP-IDE-328.md) | Sous-programme | 2x | Haute - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 15:31*
