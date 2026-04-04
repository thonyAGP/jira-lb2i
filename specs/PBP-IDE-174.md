# PBP IDE 174 - Liste CLients AVPBDR

> **Analyse**: Phases 1-4 2026-02-03 15:38 -> 15:38 (18s) | Assemblage 15:38
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBP |
| IDE Position | 174 |
| Nom Programme | Liste CLients AVPBDR |
| Fichier source | `Prg_174.xml` |
| Dossier IDE | Liste |
| Taches | 1 (1 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 20 |

## 2. DESCRIPTION FONCTIONNELLE

**Liste CLients AVPBDR** assure la gestion complete de ce processus, accessible depuis [Liste des arrivees (IDE 160)](PBP-IDE-160.md), [Liste des partants (IDE 172)](PBP-IDE-172.md), [Liste des Absents (IDE 173)](PBP-IDE-173.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

**Logique metier** : 13 regles identifiees couvrant conditions metier, valeurs par defaut.

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>174 - Liste CLients ABPBDR [[ECRAN]](#ecran-t1)

**Role** : Traitement : Liste CLients ABPBDR.
**Ecran** : 1624 x 219 DLU (MDI) | [Voir mockup](#ecran-t1)
**Variables liees** : B (>CodeListe), F (>TypeListe), P (w0_TopListe), R (w0_Liste), T (b_Liste)
**Delegue a** : [Prepa tempo toutes GM CP SQL (IDE 327)](PBP-IDE-327.md), [Prepare tempo seminaire (IDE 328)](PBP-IDE-328.md), [Cumul synthese (IDE 333)](PBP-IDE-333.md)


## 5. REGLES METIER

13 regles identifiees:

### Autres (13 regles)

#### <a id="rm-RM-001"></a>[RM-001] Si >CodeListe [B]='D' OR >CodeListe [B]='R' alors 'R' sinon 'A')

| Element | Detail |
|---------|--------|
| **Condition** | `>CodeListe [B]='D' OR >CodeListe [B]='R'` |
| **Si vrai** | 'R' |
| **Si faux** | 'A') |
| **Variables** | B (>CodeListe) |
| **Expression source** | Expression 4 : `IF (>CodeListe [B]='D' OR >CodeListe [B]='R','R','A')` |
| **Exemple** | Si >CodeListe [B]='D' OR >CodeListe [B]='R' â†’ 'R'. Sinon â†’ 'A') |
| **Impact** | [174 - Liste CLients ABPBDR](#t1) |

#### <a id="rm-RM-002"></a>[RM-002] Si >CodeListe [B]='P' OR >CodeListe [B]='B' alors 'PL' sinon 'CP')

| Element | Detail |
|---------|--------|
| **Condition** | `>CodeListe [B]='P' OR >CodeListe [B]='B'` |
| **Si vrai** | 'PL' |
| **Si faux** | 'CP') |
| **Variables** | B (>CodeListe) |
| **Expression source** | Expression 6 : `IF (>CodeListe [B]='P' OR >CodeListe [B]='B','PL','CP')` |
| **Exemple** | Si >CodeListe [B]='P' OR >CodeListe [B]='B' â†’ 'PL'. Sinon â†’ 'CP') |
| **Impact** | [174 - Liste CLients ABPBDR](#t1) |

#### <a id="rm-RM-003"></a>[RM-003] Si VG96 AND >CodeListe [B]='V' alors 'CVC99Z' sinon 'C'&>CodeListe [B]&'C99')

| Element | Detail |
|---------|--------|
| **Condition** | `VG96 AND >CodeListe [B]='V'` |
| **Si vrai** | 'CVC99Z' |
| **Si faux** | 'C'&>CodeListe [B]&'C99') |
| **Variables** | B (>CodeListe) |
| **Expression source** | Expression 10 : `IF(VG96 AND >CodeListe [B]='V', 'CVC99Z','C'&>CodeListe [B]&` |
| **Exemple** | Si VG96 AND >CodeListe [B]='V' â†’ 'CVC99Z'. Sinon â†’ 'C'&>CodeListe [B]&'C99') |
| **Impact** | [174 - Liste CLients ABPBDR](#t1) |

#### <a id="rm-RM-004"></a>[RM-004] Traitement conditionnel si [AQ] est a zero

| Element | Detail |
|---------|--------|
| **Condition** | `[AQ]=0` |
| **Si vrai** | [AP] |
| **Si faux** | [AQ]) |
| **Expression source** | Expression 51 : `IF ([AQ]=0,[AP],[AQ])` |
| **Exemple** | Si [AQ]=0 â†’ [AP]. Sinon â†’ [AQ]) |

#### <a id="rm-RM-005"></a>[RM-005] Si >CodeListe [B]='D' alors 'R' sinon 'A')

| Element | Detail |
|---------|--------|
| **Condition** | `>CodeListe [B]='D'` |
| **Si vrai** | 'R' |
| **Si faux** | 'A') |
| **Variables** | B (>CodeListe) |
| **Expression source** | Expression 60 : `IF (>CodeListe [B]='D','R','A')` |
| **Exemple** | Si >CodeListe [B]='D' â†’ 'R'. Sinon â†’ 'A') |
| **Impact** | [174 - Liste CLients ABPBDR](#t1) |

#### <a id="rm-RM-006"></a>[RM-006] Si [AT]='VV1' alors 0 sinon IF ([AT]='VV2',13,IF ([AT]='VV3',20,[AU])))

| Element | Detail |
|---------|--------|
| **Condition** | `[AT]='VV1'` |
| **Si vrai** | 0 |
| **Si faux** | IF ([AT]='VV2',13,IF ([AT]='VV3',20,[AU]))) |
| **Expression source** | Expression 68 : `IF ([AT]='VV1',0,IF ([AT]='VV2',13,IF ([AT]='VV3',20,[AU])))` |
| **Exemple** | Si [AT]='VV1' â†’ 0. Sinon â†’ IF ([AT]='VV2',13,IF ([AT]='VV3',20,[AU]))) |

#### <a id="rm-RM-007"></a>[RM-007] Traitement si Trim(w0_LieuSejour [U]) est renseigne

| Element | Detail |
|---------|--------|
| **Condition** | `Trim(w0_LieuSejour [U])<>''` |
| **Si vrai** | b_Date [M] |
| **Si faux** | 0) |
| **Variables** | M (b_Date), U (w0_LieuSejour) |
| **Expression source** | Expression 71 : `IF (Trim(w0_LieuSejour [U])<>'',b_Date [M],0)` |
| **Exemple** | Si Trim(w0_LieuSejour [U])<>'' â†’ b_Date [M]. Sinon â†’ 0) |

#### <a id="rm-RM-008"></a>[RM-008] Si InStr ('DRP' alors >CodeListe [B])>0 sinon 0,w0_OkVol [K])

| Element | Detail |
|---------|--------|
| **Condition** | `InStr ('DRP'` |
| **Si vrai** | >CodeListe [B])>0 |
| **Si faux** | 0,w0_OkVol [K]) |
| **Variables** | B (>CodeListe), K (w0_OkVol) |
| **Expression source** | Expression 76 : `IF (InStr ('DRP',>CodeListe [B])>0,0,w0_OkVol [K])` |
| **Exemple** | Si InStr ('DRP' â†’ >CodeListe [B])>0. Sinon â†’ 0,w0_OkVol [K]) |
| **Impact** | [174 - Liste CLients ABPBDR](#t1) |

#### <a id="rm-RM-009"></a>[RM-009] Si InStr ('DR' alors >CodeListe [B])>0 sinon 0,w0_OkVol [K])

| Element | Detail |
|---------|--------|
| **Condition** | `InStr ('DR'` |
| **Si vrai** | >CodeListe [B])>0 |
| **Si faux** | 0,w0_OkVol [K]) |
| **Variables** | B (>CodeListe), K (w0_OkVol) |
| **Expression source** | Expression 77 : `IF (InStr ('DR',>CodeListe [B])>0,0,w0_OkVol [K])` |
| **Exemple** | Si InStr ('DR' â†’ >CodeListe [B])>0. Sinon â†’ 0,w0_OkVol [K]) |
| **Impact** | [174 - Liste CLients ABPBDR](#t1) |

#### <a id="rm-RM-010"></a>[RM-010] Traitement conditionnel si [AU] est a zero

| Element | Detail |
|---------|--------|
| **Condition** | `[AU]=0` |
| **Si vrai** | 24 |
| **Si faux** | [AU]) |
| **Expression source** | Expression 137 : `IF ([AU]=0,24,[AU])` |
| **Exemple** | Si [AU]=0 â†’ 24. Sinon â†’ [AU]) |

#### <a id="rm-RM-011"></a>[RM-011] Condition toujours vraie (flag actif)

| Element | Detail |
|---------|--------|
| **Condition** | `w0_Heure [O]='CP'` |
| **Si vrai** | 'TRUE'LOG |
| **Si faux** | 'FALSE'LOG) |
| **Variables** | O (w0_Heure) |
| **Expression source** | Expression 139 : `IF (w0_Heure [O]='CP','TRUE'LOG,'FALSE'LOG)` |
| **Exemple** | Si w0_Heure [O]='CP' â†’ 'TRUE'LOG. Sinon â†’ 'FALSE'LOG) |

#### <a id="rm-RM-012"></a>[RM-012] Si >CodeListe [B]='A' alors MlsTrans ('ARRIVANTS') sinon IF (>CodeListe [B]='V',MlsTrans ('ARRIVEES'),IF (>CodeListe [B]='P',MlsTrans ('PRESENTS'),IF (>CodeListe [B]='D',MlsTrans ('DEPARTS'),IF (>CodeListe [B]='R',MlsTrans ('PARTANTS'),IF (>CodeListe [B]='B',MlsTrans ('ABSENTS'),MlsTrans ('STOCKPREST')))))))

| Element | Detail |
|---------|--------|
| **Condition** | `>CodeListe [B]='A'` |
| **Si vrai** | MlsTrans ('ARRIVANTS') |
| **Si faux** | IF (>CodeListe [B]='V',MlsTrans ('ARRIVEES'),IF (>CodeListe [B]='P',MlsTrans ('PRESENTS'),IF (>CodeListe [B]='D',MlsTrans ('DEPARTS'),IF (>CodeListe [B]='R',MlsTrans ('PARTANTS'),IF (>CodeListe [B]='B',MlsTrans ('ABSENTS'),MlsTrans ('STOCKPREST'))))))) |
| **Variables** | B (>CodeListe) |
| **Expression source** | Expression 142 : `IF (>CodeListe [B]='A',MlsTrans ('ARRIVANTS'),IF (>CodeListe` |
| **Exemple** | Si >CodeListe [B]='A' â†’ MlsTrans ('ARRIVANTS') |
| **Impact** | [174 - Liste CLients ABPBDR](#t1) |

#### <a id="rm-RM-013"></a>[RM-013] Valeur par defaut si [FV] est vide

| Element | Detail |
|---------|--------|
| **Condition** | `[FV]=''` |
| **Si vrai** | 'T' |
| **Si faux** | [FV]) |
| **Expression source** | Expression 150 : `IF([FV]='','T',[FV])` |
| **Exemple** | Si [FV]='' â†’ 'T'. Sinon â†’ [FV]) |

## 6. CONTEXTE

- **Appele par**: [Liste des arrivees (IDE 160)](PBP-IDE-160.md), [Liste des partants (IDE 172)](PBP-IDE-172.md), [Liste des Absents (IDE 173)](PBP-IDE-173.md)
- **Appelle**: 20 programmes | **Tables**: 4 (W:0 R:1 L:3) | **Taches**: 1 | **Expressions**: 154

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 1)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 174 | 174 | Liste CLients ABPBDR | MDI | 1624 | 219 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>174 - Liste CLients ABPBDR
**Tache** : [174](#t1) | **Type** : MDI | **Dimensions** : 1624 x 219 DLU
**Bloc** : Traitement | **Titre IDE** : Liste CLients ABPBDR

<!-- FORM-DATA:
{
    "width":  1624,
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
                         "y":  18,
                         "w":  393,
                         "fmt":  "",
                         "name":  "",
                         "h":  170,
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
                         "y":  28,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  11,
                         "h":  160,
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
                         "x":  1169,
                         "type":  "label",
                         "var":  "",
                         "y":  27,
                         "w":  263,
                         "fmt":  "",
                         "name":  "",
                         "h":  161,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  1169,
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
                         "x":  1169,
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
                         "x":  1435,
                         "type":  "label",
                         "var":  "",
                         "y":  27,
                         "w":  178,
                         "fmt":  "",
                         "name":  "",
                         "h":  161,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  1182,
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
                         "x":  1182,
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
                         "y":  29,
                         "w":  215,
                         "fmt":  "",
                         "name":  "",
                         "h":  36,
                         "color":  "",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  1198,
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
                         "y":  35,
                         "w":  46,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "Total",
                         "parent":  14
                     },
                     {
                         "x":  1198,
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
                         "y":  50,
                         "w":  78,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "Sélection",
                         "parent":  14
                     },
                     {
                         "x":  1184,
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
                         "x":  1174,
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
                         "x":  1184,
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
                         "x":  394,
                         "type":  "label",
                         "var":  "",
                         "y":  72,
                         "w":  86,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "Date",
                         "parent":  5
                     },
                     {
                         "x":  394,
                         "type":  "label",
                         "var":  "",
                         "y":  86,
                         "w":  86,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Heure",
                         "parent":  5
                     },
                     {
                         "x":  1184,
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
                         "x":  394,
                         "type":  "label",
                         "var":  "",
                         "y":  100,
                         "w":  86,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "Liste",
                         "parent":  5
                     },
                     {
                         "x":  1174,
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
                         "x":  1184,
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
                         "x":  394,
                         "type":  "label",
                         "var":  "",
                         "y":  115,
                         "w":  86,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Vol",
                         "parent":  5
                     },
                     {
                         "x":  392,
                         "type":  "label",
                         "var":  "",
                         "y":  128,
                         "w":  90,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "Lieu séjour",
                         "parent":  5
                     },
                     {
                         "x":  1184,
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
                         "y":  192,
                         "w":  1616,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "1",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  392,
                         "type":  "label",
                         "var":  "",
                         "y":  158,
                         "w":  111,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "Heure départ",
                         "parent":  5
                     },
                     {
                         "x":  392,
                         "type":  "label",
                         "var":  "",
                         "y":  173,
                         "w":  114,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "Etat comptes",
                         "parent":  5
                     },
                     {
                         "x":  510,
                         "type":  "edit",
                         "var":  "",
                         "y":  72,
                         "w":  126,
                         "fmt":  "",
                         "name":  "w0_Date",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  638,
                         "type":  "button",
                         "var":  "",
                         "y":  72,
                         "w":  25,
                         "fmt":  "...",
                         "name":  "b_Date",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  510,
                         "type":  "edit",
                         "var":  "",
                         "y":  86,
                         "w":  37,
                         "fmt":  "",
                         "name":  "w0_Heure",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  510,
                         "type":  "edit",
                         "var":  "",
                         "y":  100,
                         "w":  182,
                         "fmt":  "",
                         "name":  "w0_Liste",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  694,
                         "type":  "button",
                         "var":  "",
                         "y":  100,
                         "w":  25,
                         "fmt":  "...",
                         "name":  "b_Liste",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  510,
                         "type":  "edit",
                         "var":  "",
                         "y":  128,
                         "w":  26,
                         "fmt":  "",
                         "name":  "w0_LieuSejour",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  1184,
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
                         "x":  1260,
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
                         "x":  1393,
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
                         "x":  1184,
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
                         "x":  1260,
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
                         "x":  1393,
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
                         "x":  1184,
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
                         "x":  1260,
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
                         "x":  1393,
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
                         "x":  1339,
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
                         "x":  1339,
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
                         "x":  510,
                         "type":  "edit",
                         "var":  "",
                         "y":  115,
                         "w":  82,
                         "fmt":  "",
                         "name":  "w0_CodeVV",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  570,
                         "type":  "edit",
                         "var":  "",
                         "y":  130,
                         "w":  197,
                         "fmt":  "19",
                         "name":  "",
                         "h":  8,
                         "color":  "142",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  541,
                         "type":  "button",
                         "var":  "",
                         "y":  128,
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
                         "y":  31,
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
                         "y":  31,
                         "w":  30,
                         "fmt":  "",
                         "name":  "TUL MARQUEUR",
                         "h":  9,
                         "color":  "110",
                         "text":  "",
                         "parent":  6
                     },
                     {
                         "x":  629,
                         "type":  "edit",
                         "var":  "",
                         "y":  35,
                         "w":  56,
                         "fmt":  "",
                         "name":  "w0_Total",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  14
                     },
                     {
                         "x":  629,
                         "type":  "edit",
                         "var":  "",
                         "y":  50,
                         "w":  56,
                         "fmt":  "",
                         "name":  "w0_Selection",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  14
                     },
                     {
                         "x":  1450,
                         "type":  "button",
                         "var":  "",
                         "y":  92,
                         "w":  154,
                         "fmt":  "\u0026Ecran",
                         "name":  "b_Ecran",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  10
                     },
                     {
                         "x":  1450,
                         "type":  "button",
                         "var":  "",
                         "y":  118,
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
                         "x":  1399,
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
                         "x":  1443,
                         "type":  "image",
                         "var":  "",
                         "y":  33,
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
                         "y":  195,
                         "w":  154,
                         "fmt":  "\u0026Quitter",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  51
                     },
                     {
                         "x":  784,
                         "type":  "subform",
                         "var":  "",
                         "y":  25,
                         "w":  376,
                         "fmt":  "",
                         "name":  "Sel Code Logements",
                         "h":  164,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  1450,
                         "type":  "button",
                         "var":  "",
                         "y":  144,
                         "w":  154,
                         "fmt":  "E\u0026xcel",
                         "name":  "b_Excel",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  10
                     },
                     {
                         "x":  510,
                         "type":  "checkbox",
                         "var":  "",
                         "y":  141,
                         "w":  209,
                         "fmt":  "",
                         "name":  "w0_OnlyTai_0001",
                         "h":  12,
                         "color":  "2",
                         "text":  "Grouper par filiation",
                         "parent":  5
                     },
                     {
                         "x":  510,
                         "type":  "combobox",
                         "var":  "",
                         "y":  156,
                         "w":  224,
                         "fmt":  "",
                         "name":  "w0_Heure fin Séjout/Libération",
                         "h":  12,
                         "color":  "",
                         "text":  "S,L",
                         "parent":  5
                     },
                     {
                         "x":  1182,
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
                         "x":  510,
                         "type":  "combobox",
                         "var":  "",
                         "y":  173,
                         "w":  194,
                         "fmt":  "",
                         "name":  "w0_Soldé,Insoldé,Tous",
                         "h":  12,
                         "color":  "",
                         "text":  "S,N,T",
                         "parent":  5
                     }
                 ],
    "taskId":  "174",
    "height":  219
}
-->

<details>
<summary><strong>Champs : 25 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 510,72 | w0_Date | - | edit |
| 510,86 | w0_Heure | - | edit |
| 510,100 | w0_Liste | - | edit |
| 510,128 | w0_LieuSejour | - | edit |
| 1184,45 | w0_PortArrive | - | edit |
| 1260,59 | w0_DateArr | - | edit |
| 1184,92 | w0_DernierPort | - | edit |
| 1260,104 | w0_DateDernier | - | edit |
| 1184,137 | w0_ProchainPort | - | edit |
| 1260,150 | w0_DateProchain | - | edit |
| 1339,40 | w0_AgeMini | - | edit |
| 1339,56 | w0_AgeMaxi | - | edit |
| 510,115 | w0_CodeVV | - | edit |
| 570,130 | 19 | - | edit |
| 50,31 | QUA Libelle | - | edit |
| 13,31 | TUL MARQUEUR | - | checkbox |
| 629,35 | w0_Total | - | edit |
| 629,50 | w0_Selection | - | edit |
| 6,2 | 20 | - | edit |
| 1399,6 | WWW DD MMM YYYYT | - | edit |
| 6,11 | 30 | - | edit |
| 510,141 | w0_OnlyTai_0001 | - | checkbox |
| 510,156 | w0_Heure fin Séjout/Libération | - | combobox |
| 1182,45 | w0_NomSeminaire_0001 | - | combobox |
| 510,173 | w0_Soldé,Insoldé,Tous | - | combobox |

</details>

<details>
<summary><strong>Boutons : 10 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| ... | 638,72 | Bouton fonctionnel |
| ... | 694,100 | Bouton fonctionnel |
| b_DateArr | 1393,59 | Bouton fonctionnel |
| b_DateDern | 1393,104 | Bouton fonctionnel |
| b_DateProchain | 1393,150 | Bouton fonctionnel |
| ... | 541,128 | Bouton fonctionnel |
| Ecran | 1450,92 | Appel [RaZ 619 tempo liste ecran (IDE 287)](PBP-IDE-287.md) |
| Imprimer | 1450,118 | Appel [  Imprim  fiche police (IDE 182)](PBP-IDE-182.md) |
| Quitter | 8,195 | Quitte le programme |
| Excel | 1450,144 | Bouton fonctionnel |

</details>

## 9. NAVIGATION

Ecran unique: **Liste CLients ABPBDR**

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **174.1** | [**Liste CLients ABPBDR** (174)](#t1) [mockup](#ecran-t1) | MDI | 1624x219 | Traitement |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Traitement principal]
    DECISION{CodeListe}
    PROCESS[Traitement]
    ENDOK([END OK])
    ENDKO([END KO])

    START --> INIT --> SAISIE --> DECISION
    DECISION -->|OUI| PROCESS
    DECISION -->|NON| ENDKO
    PROCESS --> ENDOK

    style START fill:#3fb950,color:#000
    style ENDOK fill:#3fb950,color:#000
    style ENDKO fill:#f85149,color:#fff
    style DECISION fill:#58a6ff,color:#000
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
| BG | w0_DateSeminaire | R | Date |
| BH | b_DateSeminaire | R | Alpha |
| BI | w0_PortArrive | R | Alpha |
| BJ | w0_DateArr | R | Date |
| BK | b_DateArr | R | Alpha |
| BL | w0_DernierPort | R | Alpha |
| BM | w0_DateDernier | R | Date |
| BN | b_DateDern | R | Alpha |
| BO | w0_ProchainPort | R | Alpha |
| BP | w0_DateProchain | R | Date |
| BQ | b_DateProchain | R | Alpha |
| BR | w0_AgeMini | R | Numeric |
| BS | w0_AgeMaxi | R | Numeric |
| BT | w0_CodeVol | R | Alpha |
| BU | w0_CodeVille | R | Alpha |
| BV | w0_CodeVV | R | Alpha |
| BW | w0_HeureMin | R | Numeric |
| BX | w0_HeureMax | R | Numeric |
| BY | w0_DateDebMin | R | Date |
| BZ | w0_DateDebMax | R | Date |
| CA | w0_DateFinMin | R | Date |
| CB | w0_DateFinMax | R | Date |
| CC | w0_Soldé,Insoldé,Tous | R | Unicode |
| CD | w0_Libellé pour écrans/Edition | R | Unicode |
| CE | b_LieuSejour | R | Alpha |
| CF | b_Sejour | R | Alpha |
| CG | w0_Grouper par filiation | R | Logical |
| CH | w0_Heure fin Séjout/Libération | R | Alpha |
| CI | w0_Total | R | Numeric |
| CJ | w0_Selection | R | Numeric |
| CK | v. titre | R | Alpha |
| CL | W0 nom societe | R | Alpha |
| CM | W0 date minimum | R | Date |
| CN | b_DateMini | R | Alpha |
| CO | w0_SejourMulti | R | Logical |
| CP | w0_AgeBebe | R | Numeric |
| CQ | w0_AgeEnfant | R | Numeric |
| CR | b_Ecran | R | Alpha |
| CS | b_Edition | R | Alpha |
| CT | w0_Excel | R | Logical |
| CU | w0_Code_liste_excel | R | Alpha |
| CV | w0_Nom Fichier Excel | R | Alpha |
| CW | CHG_REASON_w0_Soldé,Insoldé,To | R | Numeric |
| CX | CHG_PRV_w0_Soldé,Insoldé,Tous | R | Unicode |

</details>

## 11. VARIABLES

### 11.1 Variables de session (1)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| CK | v. titre | Alpha | - |

### 11.2 Variables de travail (2)

Variables internes au programme.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| CL | W0 nom societe | Alpha | - |
| CM | W0 date minimum | Date | - |

### 11.3 Autres (73)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | >CodeEcran | Numeric | - |
| B | >CodeListe | Alpha | 21x refs |
| C | >CodeSelect | Alpha | - |
| D | >Categorie | Alpha | 1x refs |
| E | >NomTable | Alpha | 1x refs |
| F | >TypeListe | Alpha | 1x refs |
| G | >Soldé,Non_soldé,Tous | Unicode | - |
| H | w0_CodeEcranFille | Numeric | - |
| I | w0_IndexGene | Numeric | - |
| J | w0_TypeVol | Alpha | - |
| K | w0_OkVol | Logical | 9x refs |
| L | w0_Date | Date | 4x refs |
| M | b_Date | Alpha | 6x refs |
| N | w0_HeureNum | Numeric | 1x refs |
| O | w0_Heure | Alpha | 41x refs |
| P | w0_TopListe | Alpha | - |
| Q | w0_NbSelect | Numeric | 2x refs |
| R | w0_Liste | Alpha | - |
| S | w0_Pays | Alpha | - |
| T | b_Liste | Alpha | 2x refs |
| U | w0_LieuSejour | Alpha | 2x refs |
| V | w0_CategorieVol | Alpha | 1x refs |
| W | w0_Compagnie | Alpha | - |
| X | w0_DateVillageAV | Date | 1x refs |
| Y | b_DateVillageAV | Alpha | 1x refs |
| Z | w0_HeureVillageAV | Alpha | - |
| BA | w0_DateVillageDR | Date | - |
| BB | b_DateVillageDR | Alpha | - |
| BC | w0_HeureVillageDR | Alpha | - |
| BD | w0_Logement | Alpha | - |
| BE | w0_HeurePresent | Alpha | - |
| BF | w0_NomSeminaire | Alpha | - |
| BG | w0_DateSeminaire | Date | 1x refs |
| BH | b_DateSeminaire | Alpha | 1x refs |
| BI | w0_PortArrive | Alpha | - |
| BJ | w0_DateArr | Date | - |
| BK | b_DateArr | Alpha | - |
| BL | w0_DernierPort | Alpha | - |
| BM | w0_DateDernier | Date | - |
| BN | b_DateDern | Alpha | - |
| BO | w0_ProchainPort | Alpha | - |
| BP | w0_DateProchain | Date | - |
| BQ | b_DateProchain | Alpha | - |
| BR | w0_AgeMini | Numeric | - |
| BS | w0_AgeMaxi | Numeric | - |
| BT | w0_CodeVol | Alpha | 2x refs |
| BU | w0_CodeVille | Alpha | 1x refs |
| BV | w0_CodeVV | Alpha | - |
| BW | w0_HeureMin | Numeric | - |
| BX | w0_HeureMax | Numeric | 1x refs |
| BY | w0_DateDebMin | Date | 1x refs |
| BZ | w0_DateDebMax | Date | - |
| CA | w0_DateFinMin | Date | 1x refs |
| CB | w0_DateFinMax | Date | - |
| CC | w0_Soldé,Insoldé,Tous | Unicode | - |
| CD | w0_Libellé pour écrans/Edition | Unicode | - |
| CE | b_LieuSejour | Alpha | - |
| CF | b_Sejour | Alpha | - |
| CG | w0_Grouper par filiation | Logical | - |
| CH | w0_Heure fin Séjout/Libération | Alpha | - |
| CI | w0_Total | Numeric | - |
| CJ | w0_Selection | Numeric | - |
| CN | b_DateMini | Alpha | - |
| CO | w0_SejourMulti | Logical | - |
| CP | w0_AgeBebe | Numeric | - |
| CQ | w0_AgeEnfant | Numeric | - |
| CR | b_Ecran | Alpha | - |
| CS | b_Edition | Alpha | - |
| CT | w0_Excel | Logical | - |
| CU | w0_Code_liste_excel | Alpha | - |
| CV | w0_Nom Fichier Excel | Alpha | - |
| CW | CHG_REASON_w0_Soldé,Insoldé,To | Numeric | - |
| CX | CHG_PRV_w0_Soldé,Insoldé,Tous | Unicode | - |

<details>
<summary>Toutes les 76 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| W0 | **CL** | W0 nom societe | Alpha |
| W0 | **CM** | W0 date minimum | Date |
| V. | **CK** | v. titre | Alpha |
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
| Autre | **BG** | w0_DateSeminaire | Date |
| Autre | **BH** | b_DateSeminaire | Alpha |
| Autre | **BI** | w0_PortArrive | Alpha |
| Autre | **BJ** | w0_DateArr | Date |
| Autre | **BK** | b_DateArr | Alpha |
| Autre | **BL** | w0_DernierPort | Alpha |
| Autre | **BM** | w0_DateDernier | Date |
| Autre | **BN** | b_DateDern | Alpha |
| Autre | **BO** | w0_ProchainPort | Alpha |
| Autre | **BP** | w0_DateProchain | Date |
| Autre | **BQ** | b_DateProchain | Alpha |
| Autre | **BR** | w0_AgeMini | Numeric |
| Autre | **BS** | w0_AgeMaxi | Numeric |
| Autre | **BT** | w0_CodeVol | Alpha |
| Autre | **BU** | w0_CodeVille | Alpha |
| Autre | **BV** | w0_CodeVV | Alpha |
| Autre | **BW** | w0_HeureMin | Numeric |
| Autre | **BX** | w0_HeureMax | Numeric |
| Autre | **BY** | w0_DateDebMin | Date |
| Autre | **BZ** | w0_DateDebMax | Date |
| Autre | **CA** | w0_DateFinMin | Date |
| Autre | **CB** | w0_DateFinMax | Date |
| Autre | **CC** | w0_Soldé,Insoldé,Tous | Unicode |
| Autre | **CD** | w0_Libellé pour écrans/Edition | Unicode |
| Autre | **CE** | b_LieuSejour | Alpha |
| Autre | **CF** | b_Sejour | Alpha |
| Autre | **CG** | w0_Grouper par filiation | Logical |
| Autre | **CH** | w0_Heure fin Séjout/Libération | Alpha |
| Autre | **CI** | w0_Total | Numeric |
| Autre | **CJ** | w0_Selection | Numeric |
| Autre | **CN** | b_DateMini | Alpha |
| Autre | **CO** | w0_SejourMulti | Logical |
| Autre | **CP** | w0_AgeBebe | Numeric |
| Autre | **CQ** | w0_AgeEnfant | Numeric |
| Autre | **CR** | b_Ecran | Alpha |
| Autre | **CS** | b_Edition | Alpha |
| Autre | **CT** | w0_Excel | Logical |
| Autre | **CU** | w0_Code_liste_excel | Alpha |
| Autre | **CV** | w0_Nom Fichier Excel | Alpha |
| Autre | **CW** | CHG_REASON_w0_Soldé,Insoldé,To | Numeric |
| Autre | **CX** | CHG_PRV_w0_Soldé,Insoldé,Tous | Unicode |

</details>

## 12. EXPRESSIONS

**154 / 154 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONDITION | 77 | 12 |
| CAST_LOGIQUE | 4 | 5 |
| CONSTANTE | 46 | 0 |
| DATE | 1 | 0 |
| FORMAT | 1 | 0 |
| OTHER | 16 | 0 |
| CONCATENATION | 2 | 0 |
| REFERENCE_VG | 3 | 0 |
| STRING | 4 | 0 |

### 12.2 Expressions cles par type

#### CONDITION (77 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 76 | `IF (InStr ('DRP',>CodeListe [B])>0,0,w0_OkVol [K])` | [RM-008](#rm-RM-008) |
| CONDITION | 71 | `IF (Trim(w0_LieuSejour [U])<>'',b_Date [M],0)` | [RM-007](#rm-RM-007) |
| CONDITION | 68 | `IF ([AT]='VV1',0,IF ([AT]='VV2',13,IF ([AT]='VV3',20,[AU])))` | [RM-006](#rm-RM-006) |
| CONDITION | 77 | `IF (InStr ('DR',>CodeListe [B])>0,0,w0_OkVol [K])` | [RM-009](#rm-RM-009) |
| CONDITION | 150 | `IF([FV]='','T',[FV])` | [RM-013](#rm-RM-013) |
| ... | | *+72 autres* | |

#### CAST_LOGIQUE (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 139 | `IF (w0_Heure [O]='CP','TRUE'LOG,'FALSE'LOG)` | [RM-011](#rm-RM-011) |
| CAST_LOGIQUE | 141 | `'TRUE'LOG` | - |
| CAST_LOGIQUE | 55 | `'FALSE'LOG` | - |
| CAST_LOGIQUE | 151 | `CASE('TRUE'LOG,
[FY]='T',MlsTrans('Tous les comptes'),
[FY]='S',MlsTrans('Seuls les comptes soldés'),
[FY]='N',MlsTrans('Seuls les comptes non soldés'),
'')` | - |

#### CONSTANTE (46 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 103 | `92` | - |
| CONSTANTE | 102 | `91` | - |
| CONSTANTE | 104 | `93` | - |
| CONSTANTE | 106 | `95` | - |
| CONSTANTE | 105 | `94` | - |
| ... | | *+41 autres* | |

#### DATE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| DATE | 17 | `Date ()` | - |

#### FORMAT (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| FORMAT | 140 | `('%club_exportdata%')&Trim(GetParam('VILLAGE'))&'_'&Trim([FM])&'_'&
Trim(w0_NbSelect [Q])&'_'&DStr(w0_OkVol [K],'YYYYMMDD')&IF([FS]='L','LIBCH','DEPVIL')&'.csv'` | - |

#### OTHER (16 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 90 | `IN(w0_Heure [O], 'BA', 'PO', 'PT')` | - |
| OTHER | 114 | `w0_DateFinMin [CA]` | - |
| OTHER | 82 | `SetCrsr (2)` | - |
| OTHER | 83 | `SetCrsr (1)` | - |
| OTHER | 143 | `[FL]` | - |
| ... | | *+11 autres* | |

#### CONCATENATION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 9 | `'C'&>CodeListe [B]&'C99'` | - |
| CONCATENATION | 8 | `'C'&>CodeListe [B]&'60'` | - |

#### REFERENCE_VG (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 145 | `VG88` | - |
| REFERENCE_VG | 21 | `VG1` | - |
| REFERENCE_VG | 16 | `VG2` | - |

#### STRING (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| STRING | 74 | `Val (w0_HeureNum [N],'2')` | - |
| STRING | 136 | `Val (w0_DateVillageAV [X],'2')` | - |
| STRING | 14 | `Str (b_Date [M],'2P0Z0')` | - |
| STRING | 15 | `Trim (w0_CodeVille [BU])` | - |

### 12.3 Toutes les expressions (154)

<details>
<summary>Voir les 154 expressions</summary>

#### CONDITION (77)

| IDE | Expression Decodee |
|-----|-------------------|
| 4 | `IF (>CodeListe [B]='D' OR >CodeListe [B]='R','R','A')` |
| 5 | `IF (>CodeListe [B]='D' OR >CodeListe [B]='R',6,IF (InStr ('AVB',>CodeListe [B])>0,5,1))` |
| 6 | `IF (>CodeListe [B]='P' OR >CodeListe [B]='B','PL','CP')` |
| 10 | `IF(VG96 AND >CodeListe [B]='V', 'CVC99Z','C'&>CodeListe [B]&'C99')` |
| 18 | `IF (>CodeListe [B]='P' OR >CodeListe [B]='B','Planning','Comptage')` |
| 51 | `IF ([AQ]=0,[AP],[AQ])` |
| 60 | `IF (>CodeListe [B]='D','R','A')` |
| 68 | `IF ([AT]='VV1',0,IF ([AT]='VV2',13,IF ([AT]='VV3',20,[AU])))` |
| 69 | `IF ([AT]='VV1',13,IF ([AT]='VV2',20,IF ([AT]='VV3',24,[AU])))` |
| 71 | `IF (Trim(w0_LieuSejour [U])<>'',b_Date [M],0)` |
| 72 | `IF (Trim(w0_LieuSejour [U])<>'',b_Date [M],24)` |
| 76 | `IF (InStr ('DRP',>CodeListe [B])>0,0,w0_OkVol [K])` |
| 77 | `IF (InStr ('DR',>CodeListe [B])>0,0,w0_OkVol [K])` |
| 78 | `IF (InStr ('DRP',>CodeListe [B])>0,w0_OkVol [K],0)` |
| 79 | `IF (InStr ('DR',>CodeListe [B])>0,w0_OkVol [K],0)` |
| 137 | `IF ([AU]=0,24,[AU])` |
| 142 | `IF (>CodeListe [B]='A',MlsTrans ('ARRIVANTS'),IF (>CodeListe [B]='V',MlsTrans ('ARRIVEES'),IF (>CodeListe [B]='P',MlsTrans ('PRESENTS'),IF (>CodeListe [B]='D',MlsTrans ('DEPARTS'),IF (>CodeListe [B]='R',MlsTrans ('PARTANTS'),IF (>CodeListe [B]='B',MlsTrans ('ABSENTS'),MlsTrans ('STOCKPREST')))))))` |
| 144 | `CASE(>CodeListe [B],'D','D','R','D','P','P','B','P','A','A','V','A','P')` |
| 150 | `IF([FV]='','T',[FV])` |
| 22 | `>Categorie [D]` |
| 23 | `>NomTable [E]` |
| 26 | `w0_Heure [O]='PL'` |
| 27 | `w0_Heure [O]='GR'` |
| 28 | `w0_Heure [O]='GR' OR w0_Heure [O]='CP'` |
| 29 | `w0_Heure [O]='RE'` |
| 30 | `w0_Heure [O]='CA'` |
| 31 | `w0_Heure [O]='MI'` |
| 32 | `w0_Heure [O]='BB'` |
| 33 | `w0_Heure [O]='SI'` |
| 34 | `w0_Heure [O]='NS'` |
| 35 | `w0_Heure [O]='PY'` |
| 36 | `w0_Heure [O]='HM'` |
| 37 | `w0_Heure [O]='VV'` |
| 38 | `w0_Heure [O]='NV'` |
| 39 | `w0_Heure [O]='AG'` |
| 40 | `w0_Heure [O]='CO'` |
| 41 | `w0_Heure [O]='PO'` |
| 42 | `w0_Heure [O]='BA'` |
| 43 | `w0_Heure [O]='SM'` |
| 44 | `w0_Heure [O]='ST'` |
| 45 | `w0_Heure [O]='SE'` |
| 46 | `w0_Heure [O]='AF'` |
| 47 | `w0_Heure [O]='CP'` |
| 48 | `w0_Heure [O]='EN'` |
| 49 | `w0_Heure [O]='PT'` |
| 50 | `w0_Heure [O]<>'CP' AND w0_Heure [O]<>'CP'` |
| 52 | `w0_Heure [O]='AG' OR w0_Heure [O]='SA'` |
| 56 | `w0_Heure [O]='RE' AND (>CodeListe [B]='A' OR >CodeListe [B]='V')` |
| 57 | `w0_Heure [O]='RE' AND (>CodeListe [B]='D' OR >CodeListe [B]='R')` |
| 81 | `>CodeListe [B]='P'` |
| 84 | `NOT(w0_Heure [O]='SY' OR w0_Heure [O]='SA')` |
| 85 | `w0_Heure [O]='SY' OR w0_Heure [O]='SA'` |
| 86 | `w0_Heure [O]='SY' AND >CodeListe [B]<>'P'` |
| 87 | `w0_Heure [O]='SA' OR >CodeListe [B]='P' AND w0_Heure [O]='SY'` |
| 88 | `w0_Heure [O]<>'SY' AND w0_Heure [O]<>'SA'` |
| 89 | `w0_Heure [O]<>'SM' AND w0_Heure [O]<>'AF'` |
| 117 | `w0_NbSelect [Q]=''` |
| 118 | `w0_OkVol [K]=0` |
| 119 | `b_Date [M]=0` |
| 120 | `w0_Heure [O]=''` |
| 121 | `w0_CategorieVol [V]=0` |
| 122 | `b_DateVillageAV [Y]=0` |
| 123 | `[AE]=0` |
| 124 | `[AH]=0` |
| 125 | `[AK]=0` |
| 126 | `[AN]=0` |
| 129 | `w0_CodeVol [BT]>0` |
| 130 | `w0_CodeVol [BT]=0` |
| 132 | `w0_DateDebMin [BY]>w0_OkVol [K]` |
| 134 | `[AV]=0` |
| 135 | `b_Liste [T]=''` |
| 138 | `w0_Heure [O]='AF' OR w0_Heure [O]='RE'` |
| 146 | `[FS]='L'` |
| 148 | `VG114 AND >CodeListe [B]='V'` |
| 153 | `[GA]=0` |
| 131 | `w0_Heure [O]='SM' AND InStr ('AVB',>CodeListe [B])>0 AND w0_OkVol [K]<>[AE]` |
| 154 | `Trim(>TypeListe [F])='PARTANTS'` |

#### CAST_LOGIQUE (4)

| IDE | Expression Decodee |
|-----|-------------------|
| 139 | `IF (w0_Heure [O]='CP','TRUE'LOG,'FALSE'LOG)` |
| 151 | `CASE('TRUE'LOG,
[FY]='T',MlsTrans('Tous les comptes'),
[FY]='S',MlsTrans('Seuls les comptes soldés'),
[FY]='N',MlsTrans('Seuls les comptes non soldés'),
'')` |
| 55 | `'FALSE'LOG` |
| 141 | `'TRUE'LOG` |

#### CONSTANTE (46)

| IDE | Expression Decodee |
|-----|-------------------|
| 2 | `'VBEBE'` |
| 3 | `'VENFA'` |
| 11 | `'Se&jour'` |
| 13 | `'...'` |
| 20 | `'C'` |
| 53 | `'M'` |
| 54 | `'TNATI'` |
| 58 | `'A'` |
| 59 | `'R'` |
| 61 | `'VV1'` |
| 62 | `'VV2'` |
| 63 | `'VV3'` |
| 64 | `10` |
| 65 | `18` |
| 66 | `23` |
| 67 | `'23'` |
| 75 | `0` |
| 80 | `'GM'` |
| 91 | `80` |
| 92 | `81` |
| 93 | `82` |
| 94 | `83` |
| 95 | `84` |
| 96 | `85` |
| 97 | `86` |
| 98 | `87` |
| 99 | `88` |
| 100 | `89` |
| 101 | `90` |
| 102 | `91` |
| 103 | `92` |
| 104 | `93` |
| 105 | `94` |
| 106 | `95` |
| 107 | `96` |
| 108 | `97` |
| 109 | `98` |
| 110 | `99` |
| 111 | `100` |
| 112 | `101` |
| 113 | `102` |
| 115 | `'&Ecran'` |
| 116 | `'&Imprimer'` |
| 133 | `24` |
| 147 | `'S'` |
| 149 | `'AVP'` |

#### DATE (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 17 | `Date ()` |

#### FORMAT (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 140 | `('%club_exportdata%')&Trim(GetParam('VILLAGE'))&'_'&Trim([FM])&'_'&
Trim(w0_NbSelect [Q])&'_'&DStr(w0_OkVol [K],'YYYYMMDD')&IF([FS]='L','LIBCH','DEPVIL')&'.csv'` |

#### OTHER (16)

| IDE | Expression Decodee |
|-----|-------------------|
| 1 | `GetParam ('LIEU_SEJOUR')` |
| 7 | `w0_HeureMax [BX]` |
| 12 | `b_Liste [T]` |
| 19 | `GetParam ('SOCIETE')` |
| 24 | `w0_DateSeminaire [BG]` |
| 25 | `b_DateSeminaire [BH]` |
| 70 | `[AU]` |
| 73 | `w0_OkVol [K]` |
| 82 | `SetCrsr (2)` |
| 83 | `SetCrsr (1)` |
| 90 | `IN(w0_Heure [O], 'BA', 'PO', 'PT')` |
| 114 | `w0_DateFinMin [CA]` |
| 127 | `[AT]` |
| 128 | `GetParam ('VILLAGE')` |
| 143 | `[FL]` |
| 152 | `[FY]` |

#### CONCATENATION (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 8 | `'C'&>CodeListe [B]&'60'` |
| 9 | `'C'&>CodeListe [B]&'C99'` |

#### REFERENCE_VG (3)

| IDE | Expression Decodee |
|-----|-------------------|
| 16 | `VG2` |
| 21 | `VG1` |
| 145 | `VG88` |

#### STRING (4)

| IDE | Expression Decodee |
|-----|-------------------|
| 14 | `Str (b_Date [M],'2P0Z0')` |
| 15 | `Trim (w0_CodeVille [BU])` |
| 74 | `Val (w0_HeureNum [N],'2')` |
| 136 | `Val (w0_DateVillageAV [X],'2')` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Liste des arrivees (IDE 160)](PBP-IDE-160.md) -> **Liste CLients AVPBDR (IDE 174)**

Main -> ... -> [Liste des partants (IDE 172)](PBP-IDE-172.md) -> **Liste CLients AVPBDR (IDE 174)**

Main -> ... -> [Liste des Absents (IDE 173)](PBP-IDE-173.md) -> **Liste CLients AVPBDR (IDE 174)**

```mermaid
graph LR
    T174[174 Liste CLients AVPBDR]
    style T174 fill:#58a6ff
    CC173[173 Liste des Absents]
    style CC173 fill:#8b5cf6
    CC172[172 Liste des partants]
    style CC172 fill:#8b5cf6
    CC160[160 Liste des arrivees]
    style CC160 fill:#8b5cf6
    CC160 --> T174
    CC172 --> T174
    CC173 --> T174
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [160](PBP-IDE-160.md) | Liste des arrivees | 1 |
| [172](PBP-IDE-172.md) | Liste des partants | 1 |
| [173](PBP-IDE-173.md) | Liste des Absents | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T174[174 Liste CLients AVPBDR]
    style T174 fill:#58a6ff
    C324[324 Creation categorie...]
    T174 --> C324
    style C324 fill:#3fb950
    C400[400 Selection Vols]
    T174 --> C400
    style C400 fill:#3fb950
    C403[403 Selection heure Vol]
    T174 --> C403
    style C403 fill:#3fb950
    C285[285 RaZ 604 tempo depart]
    T174 --> C285
    style C285 fill:#3fb950
    C286[286 RaZ 634 tempo synt...]
    T174 --> C286
    style C286 fill:#3fb950
    C287[287 RaZ 619 tempo list...]
    T174 --> C287
    style C287 fill:#3fb950
    C288[288 RaZ 609 tempo bateau]
    T174 --> C288
    style C288 fill:#3fb950
    C299[299 RaZ 598 tempo comp...]
    T174 --> C299
    style C299 fill:#3fb950
    C325[325 Creation synthese GM]
    T174 --> C325
    style C325 fill:#3fb950
    C326[326 Creation synthese ...]
    T174 --> C326
    style C326 fill:#3fb950
    C327[327 Prepa tempo toutes...]
    T174 --> C327
    style C327 fill:#3fb950
    C328[328 Prepare tempo semi...]
    T174 --> C328
    style C328 fill:#3fb950
    C332[332 Preparation affich...]
    T174 --> C332
    style C332 fill:#3fb950
    C333[333 Cumul synthese]
    T174 --> C333
    style C333 fill:#3fb950
    C182[182 Imprim fiche police]
    T174 --> C182
    style C182 fill:#3fb950
    C188[188 Imprime Synthese]
    T174 --> C188
    style C188 fill:#3fb950
    C280[280 RaZ 637 TempoUserList]
    T174 --> C280
    style C280 fill:#3fb950
    C301[301 controle categorie]
    T174 --> C301
    style C301 fill:#3fb950
    C307[307 Recherche age Bebe...]
    T174 --> C307
    style C307 fill:#3fb950
    C321[321 PVE - Tempo userlist]
    T174 --> C321
    style C321 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [324](PBP-IDE-324.md) | Creation categorie comptage | 6 | Sous-programme |
| [400](PBP-IDE-400.md) | Selection Vols | 6 | Selection/consultation |
| [403](PBP-IDE-403.md) | Selection heure / Vol | 6 | Selection/consultation |
| [285](PBP-IDE-285.md) | RaZ 604 tempo depart | 3 | Reinitialisation |
| [286](PBP-IDE-286.md) | RaZ  634 tempo synthese | 3 | Reinitialisation |
| [287](PBP-IDE-287.md) | RaZ 619 tempo liste ecran | 3 | Reinitialisation |
| [288](PBP-IDE-288.md) | RaZ 609 tempo bateau | 3 | Reinitialisation |
| [299](PBP-IDE-299.md) | RaZ 598 tempo comptage | 3 | Reinitialisation |
| [325](PBP-IDE-325.md) | Creation synthese GM | 3 | Sous-programme |
| [326](PBP-IDE-326.md) | Creation synthese present reel | 3 | Sous-programme |
| [327](PBP-IDE-327.md) | Prepa tempo toutes GM CP SQL | 3 | Sous-programme |
| [328](PBP-IDE-328.md) | Prepare tempo seminaire | 3 | Sous-programme |
| [332](PBP-IDE-332.md) | Preparation affichage depart | 3 | Affichage donnees |
| [333](PBP-IDE-333.md) | Cumul synthese | 3 | Sous-programme |
| [182](PBP-IDE-182.md) |   Imprim  fiche police | 2 | Impression ticket/document |
| [188](PBP-IDE-188.md) |   Imprime Synthese | 2 | Impression ticket/document |
| [280](PBP-IDE-280.md) | RaZ 637 TempoUserList | 2 | Reinitialisation |
| [301](PBP-IDE-301.md) | controle categorie | 2 | Controle/validation |
| [307](PBP-IDE-307.md) | Recherche age Bebe_Enfant | 2 | Sous-programme |
| [321](PBP-IDE-321.md) | PVE -> Tempo userlist | 2 | Configuration impression |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 442 | Taille moyenne |
| Expressions | 154 | Logique moderee |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 20 | Forte dependance |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 442) | Code sain |
| Regles metier | 13 | Logique metier riche |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 1 ecran, 0 traitement)

- **Strategie** : 1 composant(s) UI (Razor/React) avec formulaires et validation.
- 20 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| [Selection heure / Vol (IDE 403)](PBP-IDE-403.md) | Sous-programme | 6x | **CRITIQUE** - Selection/consultation |
| [Selection Vols (IDE 400)](PBP-IDE-400.md) | Sous-programme | 6x | **CRITIQUE** - Selection/consultation |
| [Creation categorie comptage (IDE 324)](PBP-IDE-324.md) | Sous-programme | 6x | **CRITIQUE** - Sous-programme |
| [Prepa tempo toutes GM CP SQL (IDE 327)](PBP-IDE-327.md) | Sous-programme | 3x | **CRITIQUE** - Sous-programme |
| [Creation synthese present reel (IDE 326)](PBP-IDE-326.md) | Sous-programme | 3x | **CRITIQUE** - Sous-programme |
| [Prepare tempo seminaire (IDE 328)](PBP-IDE-328.md) | Sous-programme | 3x | **CRITIQUE** - Sous-programme |
| [Cumul synthese (IDE 333)](PBP-IDE-333.md) | Sous-programme | 3x | **CRITIQUE** - Sous-programme |
| [Preparation affichage depart (IDE 332)](PBP-IDE-332.md) | Sous-programme | 3x | **CRITIQUE** - Affichage donnees |
| [Creation synthese GM (IDE 325)](PBP-IDE-325.md) | Sous-programme | 3x | **CRITIQUE** - Sous-programme |
| [RaZ  634 tempo synthese (IDE 286)](PBP-IDE-286.md) | Sous-programme | 3x | **CRITIQUE** - Reinitialisation |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 15:38*
