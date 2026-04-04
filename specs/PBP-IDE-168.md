# PBP IDE 168 - Liste CLients depart

> **Analyse**: Phases 1-4 2026-02-03 15:35 -> 15:35 (15s) | Assemblage 15:35
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBP |
| IDE Position | 168 |
| Nom Programme | Liste CLients depart |
| Fichier source | `Prg_168.xml` |
| Dossier IDE | Liste |
| Taches | 1 (1 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 20 |

## 2. DESCRIPTION FONCTIONNELLE

**Liste CLients depart** assure la gestion complete de ce processus, accessible depuis [Liste des departs (IDE 167)](PBP-IDE-167.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

**Logique metier** : 9 regles identifiees couvrant conditions metier, valeurs par defaut.

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>168 - Liste CLients ABPBDR [[ECRAN]](#ecran-t1)

**Role** : Traitement : Liste CLients ABPBDR.
**Ecran** : 1627 x 218 DLU (MDI) | [Voir mockup](#ecran-t1)
**Variables liees** : B (>CodeListe), F (>TypeListe), P (w0_TopListe), R (w0_Liste), T (b_Liste)
**Delegue a** : [Prepa tempo toutes GM CP SQL (IDE 327)](PBP-IDE-327.md), [Prepare tempo seminaire (IDE 328)](PBP-IDE-328.md), [Cumul synthese (IDE 333)](PBP-IDE-333.md)


## 5. REGLES METIER

9 regles identifiees:

### Autres (9 regles)

#### <a id="rm-RM-001"></a>[RM-001] Si >CodeListe [B]='D' OR >CodeListe [B]='R' alors 'R' sinon 'A')

| Element | Detail |
|---------|--------|
| **Condition** | `>CodeListe [B]='D' OR >CodeListe [B]='R'` |
| **Si vrai** | 'R' |
| **Si faux** | 'A') |
| **Variables** | B (>CodeListe) |
| **Expression source** | Expression 4 : `IF (>CodeListe [B]='D' OR >CodeListe [B]='R','R','A')` |
| **Exemple** | Si >CodeListe [B]='D' OR >CodeListe [B]='R' â†’ 'R'. Sinon â†’ 'A') |
| **Impact** | [168 - Liste CLients ABPBDR](#t1) |

#### <a id="rm-RM-002"></a>[RM-002] Traitement conditionnel si [AQ] est a zero

| Element | Detail |
|---------|--------|
| **Condition** | `[AQ]=0` |
| **Si vrai** | [AP] |
| **Si faux** | [AQ]) |
| **Expression source** | Expression 40 : `IF ([AQ]=0,[AP],[AQ])` |
| **Exemple** | Si [AQ]=0 â†’ [AP]. Sinon â†’ [AQ]) |

#### <a id="rm-RM-003"></a>[RM-003] Si >CodeListe [B]='D' alors 'R' sinon 'A')

| Element | Detail |
|---------|--------|
| **Condition** | `>CodeListe [B]='D'` |
| **Si vrai** | 'R' |
| **Si faux** | 'A') |
| **Variables** | B (>CodeListe) |
| **Expression source** | Expression 52 : `IF (>CodeListe [B]='D','R','A')` |
| **Exemple** | Si >CodeListe [B]='D' â†’ 'R'. Sinon â†’ 'A') |
| **Impact** | [168 - Liste CLients ABPBDR](#t1) |

#### <a id="rm-RM-004"></a>[RM-004] Si [AT]='VV1' alors 0 sinon IF ([AT]='VV2',13,IF ([AT]='VV3',20,[AU])))

| Element | Detail |
|---------|--------|
| **Condition** | `[AT]='VV1'` |
| **Si vrai** | 0 |
| **Si faux** | IF ([AT]='VV2',13,IF ([AT]='VV3',20,[AU]))) |
| **Expression source** | Expression 60 : `IF ([AT]='VV1',0,IF ([AT]='VV2',13,IF ([AT]='VV3',20,[AU])))` |
| **Exemple** | Si [AT]='VV1' â†’ 0. Sinon â†’ IF ([AT]='VV2',13,IF ([AT]='VV3',20,[AU]))) |

#### <a id="rm-RM-005"></a>[RM-005] Traitement si w0_LieuSejour [U] est renseigne

| Element | Detail |
|---------|--------|
| **Condition** | `w0_LieuSejour [U]<>''` |
| **Si vrai** | b_Date [M] |
| **Si faux** | 0) |
| **Variables** | M (b_Date), U (w0_LieuSejour) |
| **Expression source** | Expression 63 : `IF (w0_LieuSejour [U]<>'',b_Date [M],0)` |
| **Exemple** | Si w0_LieuSejour [U]<>'' â†’ b_Date [M]. Sinon â†’ 0) |

#### <a id="rm-RM-006"></a>[RM-006] Valeur par defaut si b_DateVillageAV [X] est vide

| Element | Detail |
|---------|--------|
| **Condition** | `b_DateVillageAV [X]=''` |
| **Si vrai** | 24 |
| **Si faux** | [AU]) |
| **Variables** | M (b_Date), X (b_DateVillageAV) |
| **Expression source** | Expression 66 : `IF (b_DateVillageAV [X]='',24,[AU])` |
| **Exemple** | Si b_DateVillageAV [X]='' â†’ 24. Sinon â†’ [AU]) |

#### <a id="rm-RM-007"></a>[RM-007] Si InStr ('DRP' alors >CodeListe [B])>0 sinon 0,w0_OkVol [K])

| Element | Detail |
|---------|--------|
| **Condition** | `InStr ('DRP'` |
| **Si vrai** | >CodeListe [B])>0 |
| **Si faux** | 0,w0_OkVol [K]) |
| **Variables** | B (>CodeListe), K (w0_OkVol) |
| **Expression source** | Expression 69 : `IF (InStr ('DRP',>CodeListe [B])>0,0,w0_OkVol [K])` |
| **Exemple** | Si InStr ('DRP' â†’ >CodeListe [B])>0. Sinon â†’ 0,w0_OkVol [K]) |
| **Impact** | [168 - Liste CLients ABPBDR](#t1) |

#### <a id="rm-RM-008"></a>[RM-008] Si InStr ('DR' alors >CodeListe [B])>0 sinon 0,w0_OkVol [K])

| Element | Detail |
|---------|--------|
| **Condition** | `InStr ('DR'` |
| **Si vrai** | >CodeListe [B])>0 |
| **Si faux** | 0,w0_OkVol [K]) |
| **Variables** | B (>CodeListe), K (w0_OkVol) |
| **Expression source** | Expression 70 : `IF (InStr ('DR',>CodeListe [B])>0,0,w0_OkVol [K])` |
| **Exemple** | Si InStr ('DR' â†’ >CodeListe [B])>0. Sinon â†’ 0,w0_OkVol [K]) |
| **Impact** | [168 - Liste CLients ABPBDR](#t1) |

#### <a id="rm-RM-009"></a>[RM-009] Valeur par defaut si [FP] est vide

| Element | Detail |
|---------|--------|
| **Condition** | `[FP]=''` |
| **Si vrai** | 'T' |
| **Si faux** | [FP]) |
| **Expression source** | Expression 113 : `IF([FP]='','T',[FP])` |
| **Exemple** | Si [FP]='' â†’ 'T'. Sinon â†’ [FP]) |

## 6. CONTEXTE

- **Appele par**: [Liste des departs (IDE 167)](PBP-IDE-167.md)
- **Appelle**: 20 programmes | **Tables**: 4 (W:0 R:1 L:3) | **Taches**: 1 | **Expressions**: 120

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 1)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 168 | 168 | Liste CLients ABPBDR | MDI | 1627 | 218 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>168 - Liste CLients ABPBDR
**Tache** : [168](#t1) | **Type** : MDI | **Dimensions** : 1627 x 218 DLU
**Bloc** : Traitement | **Titre IDE** : Liste CLients ABPBDR

<!-- FORM-DATA:
{
    "width":  1627,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  1,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  1616,
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
                         "y":  24,
                         "w":  401,
                         "fmt":  "",
                         "name":  "",
                         "h":  164,
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
                         "y":  24,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  11,
                         "h":  162,
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
                         "x":  1175,
                         "type":  "label",
                         "var":  "",
                         "y":  27,
                         "w":  263,
                         "fmt":  "",
                         "name":  "",
                         "h":  164,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  1175,
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
                         "x":  1175,
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
                         "x":  1441,
                         "type":  "label",
                         "var":  "",
                         "y":  24,
                         "w":  178,
                         "fmt":  "",
                         "name":  "",
                         "h":  164,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  1187,
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
                         "x":  1187,
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
                         "x":  496,
                         "type":  "label",
                         "var":  "",
                         "y":  32,
                         "w":  215,
                         "fmt":  "",
                         "name":  "",
                         "h":  31,
                         "color":  "",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  1203,
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
                         "x":  526,
                         "type":  "label",
                         "var":  "",
                         "y":  38,
                         "w":  46,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "Total",
                         "parent":  14
                     },
                     {
                         "x":  1203,
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
                         "x":  526,
                         "type":  "label",
                         "var":  "",
                         "y":  51,
                         "w":  78,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "Selection",
                         "parent":  14
                     },
                     {
                         "x":  1189,
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
                         "x":  1179,
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
                         "x":  1189,
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
                         "y":  69,
                         "w":  86,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "Date",
                         "parent":  5
                     },
                     {
                         "x":  387,
                         "type":  "label",
                         "var":  "",
                         "y":  83,
                         "w":  86,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Heure",
                         "parent":  5
                     },
                     {
                         "x":  1189,
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
                         "y":  97,
                         "w":  86,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "Liste",
                         "parent":  5
                     },
                     {
                         "x":  1179,
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
                         "x":  1189,
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
                         "x":  387,
                         "type":  "label",
                         "var":  "",
                         "y":  111,
                         "w":  86,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Vol",
                         "parent":  5
                     },
                     {
                         "x":  387,
                         "type":  "label",
                         "var":  "",
                         "y":  126,
                         "w":  90,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "Lieu séjour",
                         "parent":  5
                     },
                     {
                         "x":  1189,
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
                         "y":  191,
                         "w":  1616,
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
                         "y":  156,
                         "w":  114,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "Heure départ",
                         "parent":  5
                     },
                     {
                         "x":  387,
                         "type":  "label",
                         "var":  "",
                         "y":  172,
                         "w":  114,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "Etat comptes",
                         "parent":  5
                     },
                     {
                         "x":  511,
                         "type":  "edit",
                         "var":  "",
                         "y":  69,
                         "w":  126,
                         "fmt":  "",
                         "name":  "w0_Date",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  639,
                         "type":  "button",
                         "var":  "",
                         "y":  69,
                         "w":  25,
                         "fmt":  "...",
                         "name":  "b_Date",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  511,
                         "type":  "edit",
                         "var":  "",
                         "y":  83,
                         "w":  37,
                         "fmt":  "",
                         "name":  "w0_Heure",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  511,
                         "type":  "edit",
                         "var":  "",
                         "y":  97,
                         "w":  182,
                         "fmt":  "",
                         "name":  "w0_Liste",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  694,
                         "type":  "button",
                         "var":  "",
                         "y":  97,
                         "w":  25,
                         "fmt":  "...",
                         "name":  "b_Liste",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  511,
                         "type":  "edit",
                         "var":  "",
                         "y":  126,
                         "w":  26,
                         "fmt":  "",
                         "name":  "w0_LieuSejour",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  1189,
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
                         "x":  1266,
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
                         "x":  1399,
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
                         "x":  1189,
                         "type":  "edit",
                         "var":  "",
                         "y":  92,
                         "w":  238,
                         "fmt":  "",
                         "name":  "w0_DernierPort",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  1266,
                         "type":  "edit",
                         "var":  "",
                         "y":  104,
                         "w":  126,
                         "fmt":  "DD/MM/YYYY",
                         "name":  "w0_DateDernier",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  1399,
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
                         "x":  1189,
                         "type":  "edit",
                         "var":  "",
                         "y":  137,
                         "w":  238,
                         "fmt":  "",
                         "name":  "w0_ProchainPort",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  1266,
                         "type":  "edit",
                         "var":  "",
                         "y":  150,
                         "w":  126,
                         "fmt":  "DD/MM/YYYY",
                         "name":  "w0_DateProchain",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  1399,
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
                         "x":  1346,
                         "type":  "edit",
                         "var":  "",
                         "y":  40,
                         "w":  37,
                         "fmt":  "",
                         "name":  "w0_AgeMini",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  9
                     },
                     {
                         "x":  1346,
                         "type":  "edit",
                         "var":  "",
                         "y":  56,
                         "w":  37,
                         "fmt":  "",
                         "name":  "w0_AgeMaxi",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  9
                     },
                     {
                         "x":  511,
                         "type":  "edit",
                         "var":  "",
                         "y":  111,
                         "w":  82,
                         "fmt":  "",
                         "name":  "w0_CodeVV",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  570,
                         "type":  "edit",
                         "var":  "",
                         "y":  127,
                         "w":  205,
                         "fmt":  "19",
                         "name":  "",
                         "h":  8,
                         "color":  "142",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  540,
                         "type":  "button",
                         "var":  "",
                         "y":  126,
                         "w":  25,
                         "fmt":  "...",
                         "name":  "b_LieuSejour",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  50,
                         "type":  "edit",
                         "var":  "",
                         "y":  26,
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
                         "y":  26,
                         "w":  30,
                         "fmt":  "",
                         "name":  "TUL MARQUEUR",
                         "h":  9,
                         "color":  "110",
                         "text":  "",
                         "parent":  6
                     },
                     {
                         "x":  627,
                         "type":  "edit",
                         "var":  "",
                         "y":  38,
                         "w":  56,
                         "fmt":  "",
                         "name":  "w0_Total",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  14
                     },
                     {
                         "x":  627,
                         "type":  "edit",
                         "var":  "",
                         "y":  51,
                         "w":  56,
                         "fmt":  "",
                         "name":  "w0_Selection",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  14
                     },
                     {
                         "x":  1456,
                         "type":  "button",
                         "var":  "",
                         "y":  95,
                         "w":  154,
                         "fmt":  "\u0026Ecran",
                         "name":  "b_Ecran",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  10
                     },
                     {
                         "x":  1456,
                         "type":  "button",
                         "var":  "",
                         "y":  120,
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
                         "x":  1396,
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
                         "x":  1453,
                         "type":  "image",
                         "var":  "",
                         "y":  35,
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
                         "y":  194,
                         "w":  154,
                         "fmt":  "\u0026Quitter",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  51
                     },
                     {
                         "x":  787,
                         "type":  "subform",
                         "var":  "",
                         "y":  24,
                         "w":  376,
                         "fmt":  "",
                         "name":  "Sel Code Logements",
                         "h":  164,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  1456,
                         "type":  "button",
                         "var":  "",
                         "y":  145,
                         "w":  154,
                         "fmt":  "E\u0026xcel",
                         "name":  "b_Excel",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  10
                     },
                     {
                         "x":  511,
                         "type":  "checkbox",
                         "var":  "",
                         "y":  143,
                         "w":  209,
                         "fmt":  "",
                         "name":  "w0_OnlyTai_0001",
                         "h":  12,
                         "color":  "",
                         "text":  "Grouper par filiation",
                         "parent":  5
                     },
                     {
                         "x":  511,
                         "type":  "combobox",
                         "var":  "",
                         "y":  156,
                         "w":  194,
                         "fmt":  "",
                         "name":  "w0_Heure depart village",
                         "h":  12,
                         "color":  "",
                         "text":  "S,L",
                         "parent":  5
                     },
                     {
                         "x":  1187,
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
                     },
                     {
                         "x":  511,
                         "type":  "combobox",
                         "var":  "",
                         "y":  172,
                         "w":  194,
                         "fmt":  "",
                         "name":  "w0_Soldé,Insoldé,Tous",
                         "h":  12,
                         "color":  "",
                         "text":  "S,N,T",
                         "parent":  5
                     }
                 ],
    "taskId":  "168",
    "height":  218
}
-->

<details>
<summary><strong>Champs : 25 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 511,69 | w0_Date | - | edit |
| 511,83 | w0_Heure | - | edit |
| 511,97 | w0_Liste | - | edit |
| 511,126 | w0_LieuSejour | - | edit |
| 1189,45 | w0_PortArrive | - | edit |
| 1266,59 | w0_DateArr | - | edit |
| 1189,92 | w0_DernierPort | - | edit |
| 1266,104 | w0_DateDernier | - | edit |
| 1189,137 | w0_ProchainPort | - | edit |
| 1266,150 | w0_DateProchain | - | edit |
| 1346,40 | w0_AgeMini | - | edit |
| 1346,56 | w0_AgeMaxi | - | edit |
| 511,111 | w0_CodeVV | - | edit |
| 570,127 | 19 | - | edit |
| 50,26 | QUA Libelle | - | edit |
| 13,26 | TUL MARQUEUR | - | checkbox |
| 627,38 | w0_Total | - | edit |
| 627,51 | w0_Selection | - | edit |
| 6,2 | 20 | - | edit |
| 1396,6 | WWW DD MMM YYYYT | - | edit |
| 6,11 | 30 | - | edit |
| 511,143 | w0_OnlyTai_0001 | - | checkbox |
| 511,156 | w0_Heure depart village | - | combobox |
| 1187,45 | w0_NomSeminaire_0001 | - | combobox |
| 511,172 | w0_Soldé,Insoldé,Tous | - | combobox |

</details>

<details>
<summary><strong>Boutons : 10 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| ... | 639,69 | Bouton fonctionnel |
| ... | 694,97 | Bouton fonctionnel |
| b_DateArr | 1399,59 | Bouton fonctionnel |
| b_DateDern | 1399,104 | Bouton fonctionnel |
| b_DateProchain | 1399,150 | Bouton fonctionnel |
| ... | 540,126 | Bouton fonctionnel |
| Ecran | 1456,95 | Bouton fonctionnel |
| Imprimer | 1456,120 | Appel [  Imprim  fiche police (IDE 182)](PBP-IDE-182.md) |
| Quitter | 8,194 | Quitte le programme |
| Excel | 1456,145 | Bouton fonctionnel |

</details>

## 9. NAVIGATION

Ecran unique: **Liste CLients ABPBDR**

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **168.1** | [**Liste CLients ABPBDR** (168)](#t1) [mockup](#ecran-t1) | MDI | 1627x218 | Traitement |

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
| N | w0_HeureNum | R | Numeric |
| O | w0_Heure | R | Alpha |
| P | w0_TopListe | R | Alpha |
| Q | w0_NbSelect | R | Numeric |
| R | w0_Liste | R | Alpha |
| S | w0_Pays | R | Alpha |
| T | b_Liste | R | Alpha |
| U | w0_LieuSejour | R | Alpha |
| V | w0_CategorieVol | R | Alpha |
| W | w0_DateVillageAV | R | Date |
| X | b_DateVillageAV | R | Alpha |
| Y | w0_HeureVillageAV | R | Alpha |
| Z | w0_DateVillageDR | R | Date |
| BA | b_DateVillageDR | R | Alpha |
| BB | w0_HeureVillageDR | R | Alpha |
| BC | w0_Logement | R | Alpha |
| BD | w0_HeurePresent | R | Alpha |
| BE | w0_NomSeminaire | R | Alpha |
| BF | w0_PortArrive | R | Alpha |
| BG | w0_DateArr | R | Date |
| BH | b_DateArr | R | Alpha |
| BI | w0_DernierPort | R | Alpha |
| BJ | w0_DateDernier | R | Date |
| BK | b_DateDern | R | Alpha |
| BL | w0_ProchainPort | R | Alpha |
| BM | w0_DateProchain | R | Date |
| BN | b_DateProchain | R | Alpha |
| BO | w0_AgeMini | R | Numeric |
| BP | w0_AgeMaxi | R | Numeric |
| BQ | w0_CodeVol | R | Alpha |
| BR | w0_CodeVille | R | Alpha |
| BS | w0_CodeVV | R | Alpha |
| BT | w0_HeureMin | R | Numeric |
| BU | w0_HeureMax | R | Numeric |
| BV | w0_DateDebMin | R | Date |
| BW | w0_DateDebMax | R | Date |
| BX | w0_DateFinMin | R | Date |
| BY | w0_DateFinMax | R | Date |
| BZ | b_LieuSejour | R | Alpha |
| CA | b_Sejour | R | Alpha |
| CB | w0_Grouper par filiation | R | Logical |
| CC | w0_Heure depart village | R | Alpha |
| CD | w0_Total | R | Numeric |
| CE | w0_Soldé,Non soldé,Tous | R | Unicode |
| CF | w0_Libellé pour écrans/Edition | R | Unicode |
| CG | w0_Selection | R | Numeric |
| CH | v. titre | R | Alpha |
| CI | W0 nom societe | R | Alpha |
| CJ | W0 date minimum | R | Date |
| CK | b_DateMini | R | Alpha |
| CL | w0_SejourMulti | R | Logical |
| CM | w0_AgeBebe | R | Numeric |
| CN | w0_AgeEnfant | R | Numeric |
| CO | b_Ecran | R | Alpha |
| CP | b_Edition | R | Alpha |
| CQ | w0_Excel ? | R | Logical |
| CR | w0_Nom_Fichier_Excel | R | Alpha |
| CS | CHG_REASON_w0_Soldé,Insoldé,To | R | Numeric |
| CT | CHG_PRV_w0_Soldé,Insoldé,Tous | R | Unicode |

</details>

## 11. VARIABLES

### 11.1 Variables de session (1)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| CH | v. titre | Alpha | - |

### 11.2 Variables de travail (2)

Variables internes au programme.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| CI | W0 nom societe | Alpha | - |
| CJ | W0 date minimum | Date | - |

### 11.3 Autres (69)

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
| L | w0_Date | Date | 3x refs |
| M | b_Date | Alpha | 7x refs |
| N | w0_HeureNum | Numeric | 1x refs |
| O | w0_Heure | Alpha | 33x refs |
| P | w0_TopListe | Alpha | - |
| Q | w0_NbSelect | Numeric | 2x refs |
| R | w0_Liste | Alpha | - |
| S | w0_Pays | Alpha | - |
| T | b_Liste | Alpha | 2x refs |
| U | w0_LieuSejour | Alpha | 2x refs |
| V | w0_CategorieVol | Alpha | 1x refs |
| W | w0_DateVillageAV | Date | - |
| X | b_DateVillageAV | Alpha | 2x refs |
| Y | w0_HeureVillageAV | Alpha | 1x refs |
| Z | w0_DateVillageDR | Date | - |
| BA | b_DateVillageDR | Alpha | - |
| BB | w0_HeureVillageDR | Alpha | - |
| BC | w0_Logement | Alpha | - |
| BD | w0_HeurePresent | Alpha | - |
| BE | w0_NomSeminaire | Alpha | - |
| BF | w0_PortArrive | Alpha | - |
| BG | w0_DateArr | Date | 1x refs |
| BH | b_DateArr | Alpha | 1x refs |
| BI | w0_DernierPort | Alpha | - |
| BJ | w0_DateDernier | Date | - |
| BK | b_DateDern | Alpha | - |
| BL | w0_ProchainPort | Alpha | - |
| BM | w0_DateProchain | Date | - |
| BN | b_DateProchain | Alpha | - |
| BO | w0_AgeMini | Numeric | - |
| BP | w0_AgeMaxi | Numeric | - |
| BQ | w0_CodeVol | Alpha | - |
| BR | w0_CodeVille | Alpha | - |
| BS | w0_CodeVV | Alpha | - |
| BT | w0_HeureMin | Numeric | 2x refs |
| BU | w0_HeureMax | Numeric | 1x refs |
| BV | w0_DateDebMin | Date | - |
| BW | w0_DateDebMax | Date | - |
| BX | w0_DateFinMin | Date | 1x refs |
| BY | w0_DateFinMax | Date | 1x refs |
| BZ | b_LieuSejour | Alpha | - |
| CA | b_Sejour | Alpha | 1x refs |
| CB | w0_Grouper par filiation | Logical | - |
| CC | w0_Heure depart village | Alpha | - |
| CD | w0_Total | Numeric | - |
| CE | w0_Soldé,Non soldé,Tous | Unicode | - |
| CF | w0_Libellé pour écrans/Edition | Unicode | - |
| CG | w0_Selection | Numeric | - |
| CK | b_DateMini | Alpha | - |
| CL | w0_SejourMulti | Logical | - |
| CM | w0_AgeBebe | Numeric | - |
| CN | w0_AgeEnfant | Numeric | - |
| CO | b_Ecran | Alpha | - |
| CP | b_Edition | Alpha | - |
| CQ | w0_Excel ? | Logical | - |
| CR | w0_Nom_Fichier_Excel | Alpha | - |
| CS | CHG_REASON_w0_Soldé,Insoldé,To | Numeric | - |
| CT | CHG_PRV_w0_Soldé,Insoldé,Tous | Unicode | - |

<details>
<summary>Toutes les 72 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| W0 | **CI** | W0 nom societe | Alpha |
| W0 | **CJ** | W0 date minimum | Date |
| V. | **CH** | v. titre | Alpha |
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
| Autre | **N** | w0_HeureNum | Numeric |
| Autre | **O** | w0_Heure | Alpha |
| Autre | **P** | w0_TopListe | Alpha |
| Autre | **Q** | w0_NbSelect | Numeric |
| Autre | **R** | w0_Liste | Alpha |
| Autre | **S** | w0_Pays | Alpha |
| Autre | **T** | b_Liste | Alpha |
| Autre | **U** | w0_LieuSejour | Alpha |
| Autre | **V** | w0_CategorieVol | Alpha |
| Autre | **W** | w0_DateVillageAV | Date |
| Autre | **X** | b_DateVillageAV | Alpha |
| Autre | **Y** | w0_HeureVillageAV | Alpha |
| Autre | **Z** | w0_DateVillageDR | Date |
| Autre | **BA** | b_DateVillageDR | Alpha |
| Autre | **BB** | w0_HeureVillageDR | Alpha |
| Autre | **BC** | w0_Logement | Alpha |
| Autre | **BD** | w0_HeurePresent | Alpha |
| Autre | **BE** | w0_NomSeminaire | Alpha |
| Autre | **BF** | w0_PortArrive | Alpha |
| Autre | **BG** | w0_DateArr | Date |
| Autre | **BH** | b_DateArr | Alpha |
| Autre | **BI** | w0_DernierPort | Alpha |
| Autre | **BJ** | w0_DateDernier | Date |
| Autre | **BK** | b_DateDern | Alpha |
| Autre | **BL** | w0_ProchainPort | Alpha |
| Autre | **BM** | w0_DateProchain | Date |
| Autre | **BN** | b_DateProchain | Alpha |
| Autre | **BO** | w0_AgeMini | Numeric |
| Autre | **BP** | w0_AgeMaxi | Numeric |
| Autre | **BQ** | w0_CodeVol | Alpha |
| Autre | **BR** | w0_CodeVille | Alpha |
| Autre | **BS** | w0_CodeVV | Alpha |
| Autre | **BT** | w0_HeureMin | Numeric |
| Autre | **BU** | w0_HeureMax | Numeric |
| Autre | **BV** | w0_DateDebMin | Date |
| Autre | **BW** | w0_DateDebMax | Date |
| Autre | **BX** | w0_DateFinMin | Date |
| Autre | **BY** | w0_DateFinMax | Date |
| Autre | **BZ** | b_LieuSejour | Alpha |
| Autre | **CA** | b_Sejour | Alpha |
| Autre | **CB** | w0_Grouper par filiation | Logical |
| Autre | **CC** | w0_Heure depart village | Alpha |
| Autre | **CD** | w0_Total | Numeric |
| Autre | **CE** | w0_Soldé,Non soldé,Tous | Unicode |
| Autre | **CF** | w0_Libellé pour écrans/Edition | Unicode |
| Autre | **CG** | w0_Selection | Numeric |
| Autre | **CK** | b_DateMini | Alpha |
| Autre | **CL** | w0_SejourMulti | Logical |
| Autre | **CM** | w0_AgeBebe | Numeric |
| Autre | **CN** | w0_AgeEnfant | Numeric |
| Autre | **CO** | b_Ecran | Alpha |
| Autre | **CP** | b_Edition | Alpha |
| Autre | **CQ** | w0_Excel ? | Logical |
| Autre | **CR** | w0_Nom_Fichier_Excel | Alpha |
| Autre | **CS** | CHG_REASON_w0_Soldé,Insoldé,To | Numeric |
| Autre | **CT** | CHG_PRV_w0_Soldé,Insoldé,Tous | Unicode |

</details>

## 12. EXPRESSIONS

**120 / 120 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONDITION | 61 | 9 |
| CAST_LOGIQUE | 3 | 0 |
| CONSTANTE | 28 | 0 |
| DATE | 1 | 0 |
| FORMAT | 1 | 0 |
| OTHER | 16 | 0 |
| CONCATENATION | 2 | 0 |
| REFERENCE_VG | 3 | 0 |
| NEGATION | 1 | 0 |
| STRING | 4 | 0 |

### 12.2 Expressions cles par type

#### CONDITION (61 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 66 | `IF (b_DateVillageAV [X]='',24,[AU])` | [RM-006](#rm-RM-006) |
| CONDITION | 63 | `IF (w0_LieuSejour [U]<>'',b_Date [M],0)` | [RM-005](#rm-RM-005) |
| CONDITION | 69 | `IF (InStr ('DRP',>CodeListe [B])>0,0,w0_OkVol [K])` | [RM-007](#rm-RM-007) |
| CONDITION | 113 | `IF([FP]='','T',[FP])` | [RM-009](#rm-RM-009) |
| CONDITION | 70 | `IF (InStr ('DR',>CodeListe [B])>0,0,w0_OkVol [K])` | [RM-008](#rm-RM-008) |
| ... | | *+56 autres* | |

#### CAST_LOGIQUE (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 104 | `'TRUE'LOG` | - |
| CAST_LOGIQUE | 45 | `'FALSE'LOG` | - |
| CAST_LOGIQUE | 114 | `CASE('TRUE'LOG,
[FS]='T',MlsTrans('Tous les comptes'),
[FS]='S',MlsTrans('Seuls les comptes soldés'),
[FS]='N',MlsTrans('Seuls les comptes non soldés'),
'')` | - |

#### CONSTANTE (28 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 59 | `'23'` | - |
| CONSTANTE | 68 | `0` | - |
| CONSTANTE | 73 | `'GM'` | - |
| CONSTANTE | 58 | `23` | - |
| CONSTANTE | 55 | `'VV3'` | - |
| ... | | *+23 autres* | |

#### DATE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| DATE | 16 | `Date ()` | - |

#### FORMAT (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| FORMAT | 103 | `('%club_exportdata%')&Trim(GetParam('VILLAGE'))&'_DEPARTS_'&
Trim(w0_NbSelect [Q])&'_'&
DStr(w0_OkVol [K],'YYYYMMDD')&'_'&IF([FO]='L','LIBCH','DEPVIL')&IF([FS]='I','NOT_SOLDED',IF([FS]='S','SOLDED',''))&'.csv'` | - |

#### OTHER (16 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 94 | `[AT]` | - |
| OTHER | 95 | `GetParam ('VILLAGE')` | - |
| OTHER | 76 | `SetCrsr (1)` | - |
| OTHER | 82 | `b_Sejour [CA]` | - |
| OTHER | 116 | `[FS]` | - |
| ... | | *+11 autres* | |

#### CONCATENATION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 9 | `'C'&>CodeListe [B]&'C99'` | - |
| CONCATENATION | 8 | `'C'&>CodeListe [B]&'60'` | - |

#### REFERENCE_VG (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 109 | `VG88` | - |
| REFERENCE_VG | 20 | `VG1` | - |
| REFERENCE_VG | 15 | `VG2` | - |

#### NEGATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| NEGATION | 119 | `NOT ExpCalc('176'EXP)` | - |

#### STRING (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| STRING | 65 | `Val (b_DateVillageAV [X],'2')` | - |
| STRING | 67 | `Val (w0_HeureNum [N],'2')` | - |
| STRING | 13 | `Str (b_Date [M],'2P0Z0')` | - |
| STRING | 14 | `Trim (w0_HeureMax [BU])` | - |

### 12.3 Toutes les expressions (120)

<details>
<summary>Voir les 120 expressions</summary>

#### CONDITION (61)

| IDE | Expression Decodee |
|-----|-------------------|
| 4 | `IF (>CodeListe [B]='D' OR >CodeListe [B]='R','R','A')` |
| 5 | `IF (>CodeListe [B]='D' OR >CodeListe [B]='R',6,IF (InStr ('AVB',>CodeListe [B])>0,5,1))` |
| 40 | `IF ([AQ]=0,[AP],[AQ])` |
| 52 | `IF (>CodeListe [B]='D','R','A')` |
| 60 | `IF ([AT]='VV1',0,IF ([AT]='VV2',13,IF ([AT]='VV3',20,[AU])))` |
| 61 | `IF ([AT]='VV1',13,IF ([AT]='VV2',20,IF ([AT]='VV3',24,[AU])))` |
| 63 | `IF (w0_LieuSejour [U]<>'',b_Date [M],0)` |
| 64 | `IF (w0_LieuSejour [U]<>'',b_Date [M],24)` |
| 66 | `IF (b_DateVillageAV [X]='',24,[AU])` |
| 69 | `IF (InStr ('DRP',>CodeListe [B])>0,0,w0_OkVol [K])` |
| 70 | `IF (InStr ('DR',>CodeListe [B])>0,0,w0_OkVol [K])` |
| 71 | `IF (InStr ('DRP',>CodeListe [B])>0,w0_OkVol [K],0)` |
| 72 | `IF (InStr ('DR',>CodeListe [B])>0,w0_OkVol [K],0)` |
| 113 | `IF([FP]='','T',[FP])` |
| 115 | `CASE(w0_Heure [O],'PL',80,
        'GR',81,
        'RE',82,
        'CA',83,
        'MI',84,
        'BB',85,
        'SI',86,
        'NS',87,
        'PY',88,
        'HM',89,
        'VV',90,
        'NV',91,
        'AG',92,
        'CO',93,
CASE(w0_Heure [O],'PO',94,
        'BA',95,
        'SM',96,
        'ST',97,
        'SE',98,
        'AF',99,
        'CP',100,
            0))` |
| 21 | `>Categorie [D]` |
| 22 | `>NomTable [E]` |
| 25 | `w0_Heure [O]='GR'` |
| 26 | `w0_Heure [O]='GR' OR w0_Heure [O]='CP'` |
| 27 | `w0_Heure [O]='PY'` |
| 28 | `w0_Heure [O]='BA'` |
| 29 | `w0_Heure [O]='SM'` |
| 30 | `w0_Heure [O]='ST'` |
| 31 | `w0_Heure [O]='SE'` |
| 32 | `w0_Heure [O]='AF'` |
| 33 | `w0_Heure [O]='CP'` |
| 34 | `w0_Heure [O]<>'CP'` |
| 35 | `w0_Heure [O]='CP' AND IN([AT],'VV1','VV2','VV3','')` |
| 36 | `w0_Heure [O]<>'CP' AND w0_Heure [O]<>'ST' AND w0_Heure [O]<>'SE' AND w0_Heure [O]<>'PO' AND w0_Heure [O]<>'BA' AND w0_Heure [O]<>'AF'` |
| 37 | `w0_Heure [O]<>'CP' AND w0_Heure [O]<>'SM' AND w0_Heure [O]<>'AF'` |
| 38 | `w0_Heure [O]<>'SM' AND w0_Heure [O]<>'AF'` |
| 39 | `w0_Heure [O]<>'CP' AND w0_Heure [O]<>'GR'` |
| 41 | `w0_Heure [O]='AG' OR w0_Heure [O]='SA'` |
| 43 | `w0_Heure [O]='CP'` |
| 47 | `w0_Heure [O]='RE'` |
| 48 | `>CodeListe [B]='A' OR >CodeListe [B]='V'` |
| 49 | `>CodeListe [B]='D' OR >CodeListe [B]='R'` |
| 74 | `>CodeListe [B]='P'` |
| 77 | `w0_Heure [O]='SY' OR w0_Heure [O]='SA'` |
| 78 | `w0_Heure [O]='SY' AND >CodeListe [B]<>'P'` |
| 79 | `w0_Heure [O]='SA' OR >CodeListe [B]='P' AND w0_Heure [O]='SY'` |
| 80 | `w0_Heure [O]<>'SY' AND w0_Heure [O]<>'SA'` |
| 81 | `w0_Heure [O]='BA' OR w0_Heure [O]='PO'` |
| 85 | `w0_NbSelect [Q]=''` |
| 86 | `w0_OkVol [K]=0` |
| 87 | `b_Date [M]=0` |
| 88 | `w0_Heure [O]=''` |
| 89 | `w0_CategorieVol [V]=0` |
| 90 | `w0_HeureVillageAV [Y]=0` |
| 91 | `[AH]=0` |
| 92 | `[AK]=0` |
| 93 | `[AN]=0` |
| 96 | `w0_HeureMin [BT]>0` |
| 97 | `w0_HeureMin [BT]=0` |
| 98 | `w0_DateFinMax [BY]>w0_OkVol [K]` |
| 100 | `[AV]=0` |
| 101 | `b_Liste [T]=''` |
| 102 | `w0_Heure [O]='RE' OR w0_Heure [O]='AF'` |
| 106 | `NOT(w0_Heure [O]='SY' OR w0_Heure [O]='SA')` |
| 110 | `[FO]='L'` |
| 117 | `[FU]=0` |

#### CAST_LOGIQUE (3)

| IDE | Expression Decodee |
|-----|-------------------|
| 114 | `CASE('TRUE'LOG,
[FS]='T',MlsTrans('Tous les comptes'),
[FS]='S',MlsTrans('Seuls les comptes soldés'),
[FS]='N',MlsTrans('Seuls les comptes non soldés'),
'')` |
| 45 | `'FALSE'LOG` |
| 104 | `'TRUE'LOG` |

#### CONSTANTE (28)

| IDE | Expression Decodee |
|-----|-------------------|
| 2 | `'VBEBE'` |
| 3 | `'VENFA'` |
| 6 | `'CP'` |
| 10 | `'Se&jour'` |
| 12 | `'...'` |
| 17 | `'Comptage'` |
| 19 | `'C'` |
| 42 | `'M'` |
| 44 | `'TNATI'` |
| 46 | `'DEP'` |
| 50 | `'A'` |
| 51 | `'R'` |
| 53 | `'VV1'` |
| 54 | `'VV2'` |
| 55 | `'VV3'` |
| 56 | `10` |
| 57 | `18` |
| 58 | `23` |
| 59 | `'23'` |
| 68 | `0` |
| 73 | `'GM'` |
| 83 | `'&Ecran'` |
| 84 | `'&Imprimer'` |
| 99 | `24` |
| 105 | `'S'` |
| 108 | `'D'` |
| 112 | `'GR'` |
| 120 | `'T'` |

#### DATE (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 16 | `Date ()` |

#### FORMAT (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 103 | `('%club_exportdata%')&Trim(GetParam('VILLAGE'))&'_DEPARTS_'&
Trim(w0_NbSelect [Q])&'_'&
DStr(w0_OkVol [K],'YYYYMMDD')&'_'&IF([FO]='L','LIBCH','DEPVIL')&IF([FS]='I','NOT_SOLDED',IF([FS]='S','SOLDED',''))&'.csv'` |

#### OTHER (16)

| IDE | Expression Decodee |
|-----|-------------------|
| 1 | `GetParam ('LIEU_SEJOUR')` |
| 7 | `w0_DateFinMin [BX]` |
| 11 | `b_Liste [T]` |
| 18 | `GetParam ('SOCIETE')` |
| 23 | `w0_DateArr [BG]` |
| 24 | `b_DateArr [BH]` |
| 62 | `[AU]` |
| 75 | `SetCrsr (2)` |
| 76 | `SetCrsr (1)` |
| 82 | `b_Sejour [CA]` |
| 94 | `[AT]` |
| 95 | `GetParam ('VILLAGE')` |
| 107 | `[FL]` |
| 111 | `w0_OkVol [K]` |
| 116 | `[FS]` |
| 118 | `IN(w0_Heure [O],'SY','AG')` |

#### CONCATENATION (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 8 | `'C'&>CodeListe [B]&'60'` |
| 9 | `'C'&>CodeListe [B]&'C99'` |

#### REFERENCE_VG (3)

| IDE | Expression Decodee |
|-----|-------------------|
| 15 | `VG2` |
| 20 | `VG1` |
| 109 | `VG88` |

#### NEGATION (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 119 | `NOT ExpCalc('176'EXP)` |

#### STRING (4)

| IDE | Expression Decodee |
|-----|-------------------|
| 13 | `Str (b_Date [M],'2P0Z0')` |
| 14 | `Trim (w0_HeureMax [BU])` |
| 65 | `Val (b_DateVillageAV [X],'2')` |
| 67 | `Val (w0_HeureNum [N],'2')` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Liste des departs (IDE 167)](PBP-IDE-167.md) -> **Liste CLients depart (IDE 168)**

```mermaid
graph LR
    T168[168 Liste CLients depart]
    style T168 fill:#58a6ff
    CC167[167 Liste des departs]
    style CC167 fill:#8b5cf6
    CC167 --> T168
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [167](PBP-IDE-167.md) | Liste des departs | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T168[168 Liste CLients depart]
    style T168 fill:#58a6ff
    C324[324 Creation categorie...]
    T168 --> C324
    style C324 fill:#3fb950
    C327[327 Prepa tempo toutes...]
    T168 --> C327
    style C327 fill:#3fb950
    C328[328 Prepare tempo semi...]
    T168 --> C328
    style C328 fill:#3fb950
    C332[332 Preparation affich...]
    T168 --> C332
    style C332 fill:#3fb950
    C400[400 Selection Vols]
    T168 --> C400
    style C400 fill:#3fb950
    C403[403 Selection heure Vol]
    T168 --> C403
    style C403 fill:#3fb950
    C169[169 Prep tempo depart ...]
    T168 --> C169
    style C169 fill:#3fb950
    C182[182 Imprim fiche police]
    T168 --> C182
    style C182 fill:#3fb950
    C188[188 Imprime Synthese]
    T168 --> C188
    style C188 fill:#3fb950
    C286[286 RaZ 634 tempo synt...]
    T168 --> C286
    style C286 fill:#3fb950
    C307[307 Recherche age Bebe...]
    T168 --> C307
    style C307 fill:#3fb950
    C325[325 Creation synthese GM]
    T168 --> C325
    style C325 fill:#3fb950
    C326[326 Creation synthese ...]
    T168 --> C326
    style C326 fill:#3fb950
    C333[333 Cumul synthese]
    T168 --> C333
    style C333 fill:#3fb950
    C399[399 Selection lieu sejour]
    T168 --> C399
    style C399 fill:#3fb950
    C170[170 Affich depart comp...]
    T168 --> C170
    style C170 fill:#3fb950
    C171[171 Imprim GM depart c...]
    T168 --> C171
    style C171 fill:#3fb950
    C175[175 Affichage AVPBDR t...]
    T168 --> C175
    style C175 fill:#3fb950
    C176[176 Imprim AVPBDR tout...]
    T168 --> C176
    style C176 fill:#3fb950
    C177[177 Affichage AVPBDR S...]
    T168 --> C177
    style C177 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [324](PBP-IDE-324.md) | Creation categorie comptage | 3 | Sous-programme |
| [327](PBP-IDE-327.md) | Prepa tempo toutes GM CP SQL | 3 | Sous-programme |
| [328](PBP-IDE-328.md) | Prepare tempo seminaire | 3 | Sous-programme |
| [332](PBP-IDE-332.md) | Preparation affichage depart | 3 | Affichage donnees |
| [400](PBP-IDE-400.md) | Selection Vols | 3 | Selection/consultation |
| [403](PBP-IDE-403.md) | Selection heure / Vol | 3 | Selection/consultation |
| [169](PBP-IDE-169.md) |   Prep tempo depart comptage | 2 | Sous-programme |
| [182](PBP-IDE-182.md) |   Imprim  fiche police | 2 | Impression ticket/document |
| [188](PBP-IDE-188.md) |   Imprime Synthese | 2 | Impression ticket/document |
| [286](PBP-IDE-286.md) | RaZ  634 tempo synthese | 2 | Reinitialisation |
| [307](PBP-IDE-307.md) | Recherche age Bebe_Enfant | 2 | Sous-programme |
| [325](PBP-IDE-325.md) | Creation synthese GM | 2 | Sous-programme |
| [326](PBP-IDE-326.md) | Creation synthese present reel | 2 | Sous-programme |
| [333](PBP-IDE-333.md) | Cumul synthese | 2 | Sous-programme |
| [399](PBP-IDE-399.md) | Selection lieu sejour | 2 | Selection/consultation |
| [170](PBP-IDE-170.md) |   Affich depart comptage GM | 1 | Affichage donnees |
| [171](PBP-IDE-171.md) |   Imprim GM depart comptage | 1 | Impression ticket/document |
| [175](PBP-IDE-175.md) |   Affichage AVPBDR toutes GM | 1 | Affichage donnees |
| [176](PBP-IDE-176.md) |   Imprim AVPBDR toutes GM | 1 | Impression ticket/document |
| [177](PBP-IDE-177.md) |   Affichage AVPBDR Standard | 1 | Affichage donnees |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 345 | Taille moyenne |
| Expressions | 120 | Logique moderee |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 20 | Forte dependance |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 2.6% (9 / 345) | Code sain |
| Regles metier | 9 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 1 ecran, 0 traitement)

- **Strategie** : 1 composant(s) UI (Razor/React) avec formulaires et validation.
- 20 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| [Preparation affichage depart (IDE 332)](PBP-IDE-332.md) | Sous-programme | 3x | **CRITIQUE** - Affichage donnees |
| [Selection Vols (IDE 400)](PBP-IDE-400.md) | Sous-programme | 3x | **CRITIQUE** - Selection/consultation |
| [Selection heure / Vol (IDE 403)](PBP-IDE-403.md) | Sous-programme | 3x | **CRITIQUE** - Selection/consultation |
| [Creation categorie comptage (IDE 324)](PBP-IDE-324.md) | Sous-programme | 3x | **CRITIQUE** - Sous-programme |
| [Prepa tempo toutes GM CP SQL (IDE 327)](PBP-IDE-327.md) | Sous-programme | 3x | **CRITIQUE** - Sous-programme |
| [Prepare tempo seminaire (IDE 328)](PBP-IDE-328.md) | Sous-programme | 3x | **CRITIQUE** - Sous-programme |
| [Creation synthese present reel (IDE 326)](PBP-IDE-326.md) | Sous-programme | 2x | Haute - Sous-programme |
| [Creation synthese GM (IDE 325)](PBP-IDE-325.md) | Sous-programme | 2x | Haute - Sous-programme |
| [Selection lieu sejour (IDE 399)](PBP-IDE-399.md) | Sous-programme | 2x | Haute - Selection/consultation |
| [Cumul synthese (IDE 333)](PBP-IDE-333.md) | Sous-programme | 2x | Haute - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 15:35*
