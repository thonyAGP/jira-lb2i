# PVE IDE 225 - Payments - select

> **Analyse**: Phases 1-4 2026-02-03 19:02 -> 19:02 (17s) | Assemblage 19:02
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PVE |
| IDE Position | 225 |
| Nom Programme | Payments - select |
| Fichier source | `Prg_225.xml` |
| Dossier IDE | Packages |
| Taches | 1 (1 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 2 |

## 2. DESCRIPTION FONCTIONNELLE

**Payments - select** assure la gestion complete de ce processus, accessible depuis [Main Sale ===V4 (IDE 0)](PVE-IDE-0.md), [Main Sale (IDE 186)](PVE-IDE-186.md), [Main Sale-664 (IDE 187)](PVE-IDE-187.md), [Main Sale Sale Bar Code (IDE 214)](PVE-IDE-214.md), [Main Sale ===V4 bck (IDE 352)](PVE-IDE-352.md), [Main Sale ===V4 (IDE 354)](PVE-IDE-354.md), [Main Sale ===V4 (IDE 359)](PVE-IDE-359.md), [Main Sale (IDE 363)](PVE-IDE-363.md), [Main Sale-664 (IDE 364)](PVE-IDE-364.md), [Menu Main (TPE) (IDE 403)](PVE-IDE-403.md), [Main Sale ===V4 (IDE 409)](PVE-IDE-409.md), [Main Sale ===V4 (IDE 415)](PVE-IDE-415.md), [Main Sale ===V4 Booking ACTUEL (IDE 417)](PVE-IDE-417.md), [Main Sale (IDE 440)](PVE-IDE-440.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

**Logique metier** : 2 regles identifiees couvrant conditions metier.

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>225 - Payment [[ECRAN]](#ecran-t1)

**Role** : Traitement : Payment.
**Ecran** : 471 x 373 DLU (MDI) | [Voir mockup](#ecran-t1)
**Variables liees** : A (P.i.o.Payment type)
**Delegue a** : [Search Customer (IDE 188)](PVE-IDE-188.md), [Pilotage Garantie (IDE 325)](PVE-IDE-325.md)


## 5. REGLES METIER

2 regles identifiees:

### Autres (2 regles)

#### <a id="rm-RM-001"></a>[RM-001] Condition toujours vraie (flag actif)

| Element | Detail |
|---------|--------|
| **Condition** | `v.Retour Confirmation [K] AND L Customer ? [I]<>'REFUSAL TO SELL' AND P.i.Bloquer Free ? [G]` |
| **Si vrai** | 'TRUE'LOG |
| **Si faux** | 'FALSE'LOG) |
| **Variables** | G (P.i.Bloquer Free ?), K (v.Retour Confirmation), I (L Customer ?) |
| **Expression source** | Expression 16 : `IF(v.Retour Confirmation [K] AND L Customer ? [I]<>'REFUSAL ` |
| **Exemple** | Si v.Retour Confirmation [K] AND L Customer ? [I]<>'REFUSAL TO SELL' AND P.i.Bloquer Free ? [G] â†’ 'TRUE'LOG. Sinon â†’ 'FALSE'LOG) |

#### <a id="rm-RM-002"></a>[RM-002] Condition toujours vraie (flag actif)

| Element | Detail |
|---------|--------|
| **Condition** | `VG36 OR VG33='WS'` |
| **Si vrai** | 'TRUE'LOG |
| **Si faux** | L Customer ? [I]<>'CREDIT CARD') |
| **Variables** | I (L Customer ?) |
| **Expression source** | Expression 21 : `IF(VG36 OR VG33='WS','TRUE'LOG,L Customer ? [I]<>'CREDIT CAR` |
| **Exemple** | Si VG36 OR VG33='WS' â†’ 'TRUE'LOG. Sinon â†’ L Customer ? [I]<>'CREDIT CARD') |

## 6. CONTEXTE

- **Appele par**: [Main Sale ===V4 (IDE 0)](PVE-IDE-0.md), [Main Sale (IDE 186)](PVE-IDE-186.md), [Main Sale-664 (IDE 187)](PVE-IDE-187.md), [Main Sale Sale Bar Code (IDE 214)](PVE-IDE-214.md), [Main Sale ===V4 bck (IDE 352)](PVE-IDE-352.md), [Main Sale ===V4 (IDE 354)](PVE-IDE-354.md), [Main Sale ===V4 (IDE 359)](PVE-IDE-359.md), [Main Sale (IDE 363)](PVE-IDE-363.md), [Main Sale-664 (IDE 364)](PVE-IDE-364.md), [Menu Main (TPE) (IDE 403)](PVE-IDE-403.md), [Main Sale ===V4 (IDE 409)](PVE-IDE-409.md), [Main Sale ===V4 (IDE 415)](PVE-IDE-415.md), [Main Sale ===V4 Booking ACTUEL (IDE 417)](PVE-IDE-417.md), [Main Sale (IDE 440)](PVE-IDE-440.md)
- **Appelle**: 2 programmes | **Tables**: 3 (W:0 R:1 L:2) | **Taches**: 1 | **Expressions**: 21

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 1)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 225 | 225 | Payment | MDI | 471 | 373 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>225 - Payment
**Tache** : [225](#t1) | **Type** : MDI | **Dimensions** : 471 x 373 DLU
**Bloc** : Traitement | **Titre IDE** : Payment

<!-- FORM-DATA:
{
    "width":  471,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  471,
                         "fmt":  "",
                         "name":  "",
                         "h":  42,
                         "color":  "182",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  16,
                         "type":  "label",
                         "var":  "",
                         "y":  15,
                         "w":  367,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "186",
                         "text":  "Select the payer and the type of payment for this sale",
                         "parent":  1
                     },
                     {
                         "x":  25,
                         "type":  "label",
                         "var":  "",
                         "y":  47,
                         "w":  423,
                         "fmt":  "",
                         "name":  "",
                         "h":  52,
                         "color":  "183",
                         "text":  "Person paying",
                         "parent":  null
                     },
                     {
                         "x":  37,
                         "type":  "label",
                         "var":  "",
                         "y":  64,
                         "w":  253,
                         "fmt":  "",
                         "name":  "",
                         "h":  28,
                         "color":  "189",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  25,
                         "type":  "label",
                         "var":  "",
                         "y":  109,
                         "w":  423,
                         "fmt":  "",
                         "name":  "",
                         "h":  224,
                         "color":  "183",
                         "text":  "Type of payment",
                         "parent":  null
                     },
                     {
                         "x":  215,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "110",
                         "w":  160,
                         "y":  126,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  28,
                         "h":  200,
                         "cols":  [
                                      {
                                          "title":  "",
                                          "layer":  1,
                                          "w":  155
                                      }
                                  ],
                         "rows":  1
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  337,
                         "w":  471,
                         "fmt":  "",
                         "name":  "",
                         "h":  34,
                         "color":  "6",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  216,
                         "type":  "button",
                         "var":  "",
                         "y":  127,
                         "w":  154,
                         "fmt":  "",
                         "name":  "PAYMENT",
                         "h":  28,
                         "color":  "",
                         "text":  "",
                         "parent":  10
                     },
                     {
                         "x":  309,
                         "type":  "button",
                         "var":  "",
                         "y":  64,
                         "w":  126,
                         "fmt":  "Different \\Account",
                         "name":  "BP. Other account",
                         "h":  28,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  422,
                         "type":  "image",
                         "var":  "",
                         "y":  4,
                         "w":  48,
                         "fmt":  "",
                         "name":  "",
                         "h":  37,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  41,
                         "type":  "edit",
                         "var":  "",
                         "y":  67,
                         "w":  245,
                         "fmt":  "30",
                         "name":  "",
                         "h":  21,
                         "color":  "191",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  375,
                         "type":  "button",
                         "var":  "",
                         "y":  126,
                         "w":  52,
                         "fmt":  "ñ",
                         "name":  "",
                         "h":  100,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  57,
                         "type":  "image",
                         "var":  "",
                         "y":  125,
                         "w":  82,
                         "fmt":  "",
                         "name":  "",
                         "h":  44,
                         "color":  "",
                         "text":  "",
                         "parent":  8
                     },
                     {
                         "x":  375,
                         "type":  "button",
                         "var":  "",
                         "y":  226,
                         "w":  52,
                         "fmt":  "ò",
                         "name":  "",
                         "h":  100,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  393,
                         "type":  "button",
                         "var":  "",
                         "y":  342,
                         "w":  77,
                         "fmt":  "\u0026Cancel",
                         "name":  "",
                         "h":  28,
                         "color":  "",
                         "text":  "",
                         "parent":  15
                     }
                 ],
    "taskId":  "225",
    "height":  373
}
-->

<details>
<summary><strong>Champs : 1 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 41,67 | 30 | - | edit |

</details>

<details>
<summary><strong>Boutons : 5 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| PAYMENT | 216,127 | Bouton fonctionnel |
| Different \Account | 309,64 | Bouton fonctionnel |
| ñ | 375,126 | Bouton fonctionnel |
| ò | 375,226 | Bouton fonctionnel |
| Cancel | 393,342 | Annule et retour au menu |

</details>

## 9. NAVIGATION

Ecran unique: **Payment**

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **225.1** | [**Payment** (225)](#t1) [mockup](#ecran-t1) | MDI | 471x373 | Traitement |

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

### Tables utilisees (3)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 47 | compte_gm________cgm | Comptes GM (generaux) | DB | R |   |   | 1 |
| 382 | pv_discount_reasons |  | DB |   |   | L | 1 |
| 420 | req_dispatch |  | DB |   |   | L | 1 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 47 - compte_gm________cgm (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P.i.o.Payment type | R | Alpha |
| B | P.i.Customer id payer | R | Numeric |
| C | P.o.Clubmed transaction ? | R | Logical |
| D | P.o.Free ? | R | Logical |
| E | P.i.Action type | R | Alpha |
| F | P.o.Garantie Ok | R | Logical |
| G | P.i.Bloquer Free ? | R | Logical |
| H | BP. Other account | R | Alpha |
| I | L Customer ? | R | Logical |
| J | v Blocage | R | Logical |
| K | v.Retour Confirmation | R | Numeric |
| L | v.retour Garantie | R | Logical |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (7)

Variables recues du programme appelant ([Main Sale ===V4 (IDE 0)](PVE-IDE-0.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P.i.o.Payment type | Alpha | - |
| B | P.i.Customer id payer | Numeric | 1x parametre entrant |
| C | P.o.Clubmed transaction ? | Logical | - |
| D | P.o.Free ? | Logical | - |
| E | P.i.Action type | Alpha | 3x parametre entrant |
| F | P.o.Garantie Ok | Logical | 1x parametre entrant |
| G | P.i.Bloquer Free ? | Logical | 1x parametre entrant |

### 11.2 Variables de session (3)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| J | v Blocage | Logical | 3x session |
| K | v.Retour Confirmation | Numeric | 2x session |
| L | v.retour Garantie | Logical | - |

### 11.3 Autres (2)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| H | BP. Other account | Alpha | - |
| I | L Customer ? | Logical | 4x refs |

## 12. EXPRESSIONS

**21 / 21 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CAST_LOGIQUE | 4 | 2 |
| OTHER | 11 | 0 |
| CONDITION | 5 | 0 |
| CONCATENATION | 1 | 0 |

### 12.2 Expressions cles par type

#### CAST_LOGIQUE (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 21 | `IF(VG36 OR VG33='WS','TRUE'LOG,L Customer ? [I]<>'CREDIT CARD')` | [RM-002](#rm-RM-002) |
| CAST_LOGIQUE | 16 | `IF(v.Retour Confirmation [K] AND L Customer ? [I]<>'REFUSAL TO SELL' AND P.i.Bloquer Free ? [G],'TRUE'LOG,'FALSE'LOG)` | [RM-001](#rm-RM-001) |
| CAST_LOGIQUE | 15 | `[X]='FALSE'LOG` | - |
| CAST_LOGIQUE | 2 | `'FALSE'LOG` | - |

#### OTHER (11 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 13 | `Stat (0,'C'MODE)` | - |
| OTHER | 11 | `[S]` | - |
| OTHER | 17 | `NOT(VG86) OR NOT(VG87) OR NOT(VG24)` | - |
| OTHER | 20 | `NOT(P.o.Garantie Ok [F])` | - |
| OTHER | 18 | `VG86 AND VG87 AND VG24` | - |
| ... | | *+6 autres* | |

#### CONDITION (5 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 14 | `P.i.Action type [E]<>'CANCEL'` | - |
| CONDITION | 19 | `[Y]=6` | - |
| CONDITION | 12 | `L Customer ? [I]='CLUBMED PASS'` | - |
| CONDITION | 4 | `v Blocage [J] AND NOT (GetParam ('OKNOGUARANTY')) AND [W]<>'O' AND P.i.Action type [E]<>'CANCEL'` | - |
| CONDITION | 5 | `v Blocage [J] AND NOT (GetParam ('OKNOGUARANTY')) AND [W]<>'O' AND P.i.Action type [E]='CANCEL'` | - |

#### CONCATENATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 9 | `Trim ([Q])&' '&Trim ([P])` | - |

### 12.3 Toutes les expressions (21)

<details>
<summary>Voir les 21 expressions</summary>

#### CAST_LOGIQUE (4)

| IDE | Expression Decodee |
|-----|-------------------|
| 16 | `IF(v.Retour Confirmation [K] AND L Customer ? [I]<>'REFUSAL TO SELL' AND P.i.Bloquer Free ? [G],'TRUE'LOG,'FALSE'LOG)` |
| 21 | `IF(VG36 OR VG33='WS','TRUE'LOG,L Customer ? [I]<>'CREDIT CARD')` |
| 2 | `'FALSE'LOG` |
| 15 | `[X]='FALSE'LOG` |

#### OTHER (11)

| IDE | Expression Decodee |
|-----|-------------------|
| 1 | `GetParam ('SERVICE')` |
| 3 | `L Customer ? [I]` |
| 6 | `v Blocage [J]` |
| 7 | `v.Retour Confirmation [K]` |
| 8 | `P.i.Customer id payer [B]` |
| 10 | `[R]` |
| 11 | `[S]` |
| 13 | `Stat (0,'C'MODE)` |
| 17 | `NOT(VG86) OR NOT(VG87) OR NOT(VG24)` |
| 18 | `VG86 AND VG87 AND VG24` |
| 20 | `NOT(P.o.Garantie Ok [F])` |

#### CONDITION (5)

| IDE | Expression Decodee |
|-----|-------------------|
| 4 | `v Blocage [J] AND NOT (GetParam ('OKNOGUARANTY')) AND [W]<>'O' AND P.i.Action type [E]<>'CANCEL'` |
| 5 | `v Blocage [J] AND NOT (GetParam ('OKNOGUARANTY')) AND [W]<>'O' AND P.i.Action type [E]='CANCEL'` |
| 12 | `L Customer ? [I]='CLUBMED PASS'` |
| 14 | `P.i.Action type [E]<>'CANCEL'` |
| 19 | `[Y]=6` |

#### CONCATENATION (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 9 | `Trim ([Q])&' '&Trim ([P])` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Main Sale ===V4 (IDE 0)](PVE-IDE-0.md) -> **Payments - select (IDE 225)**

Main -> ... -> [Main Sale (IDE 186)](PVE-IDE-186.md) -> **Payments - select (IDE 225)**

Main -> ... -> [Main Sale-664 (IDE 187)](PVE-IDE-187.md) -> **Payments - select (IDE 225)**

Main -> ... -> [Main Sale Sale Bar Code (IDE 214)](PVE-IDE-214.md) -> **Payments - select (IDE 225)**

Main -> ... -> [Main Sale ===V4 bck (IDE 352)](PVE-IDE-352.md) -> **Payments - select (IDE 225)**

Main -> ... -> [Main Sale ===V4 (IDE 354)](PVE-IDE-354.md) -> **Payments - select (IDE 225)**

Main -> ... -> [Main Sale ===V4 (IDE 359)](PVE-IDE-359.md) -> **Payments - select (IDE 225)**

Main -> ... -> [Main Sale (IDE 363)](PVE-IDE-363.md) -> **Payments - select (IDE 225)**

Main -> ... -> [Main Sale-664 (IDE 364)](PVE-IDE-364.md) -> **Payments - select (IDE 225)**

Main -> ... -> [Menu Main (TPE) (IDE 403)](PVE-IDE-403.md) -> **Payments - select (IDE 225)**

Main -> ... -> [Main Sale ===V4 (IDE 409)](PVE-IDE-409.md) -> **Payments - select (IDE 225)**

Main -> ... -> [Main Sale ===V4 (IDE 415)](PVE-IDE-415.md) -> **Payments - select (IDE 225)**

Main -> ... -> [Main Sale ===V4 Booking ACTUEL (IDE 417)](PVE-IDE-417.md) -> **Payments - select (IDE 225)**

Main -> ... -> [Main Sale (IDE 440)](PVE-IDE-440.md) -> **Payments - select (IDE 225)**

```mermaid
graph LR
    T225[225 Payments - select]
    style T225 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC143[143 START]
    style CC143 fill:#f59e0b
    CC420[420 Menu==V4___]
    style CC420 fill:#f59e0b
    CC185[185 Menu]
    style CC185 fill:#f59e0b
    CC353[353 Menu==V4]
    style CC353 fill:#f59e0b
    CC187[187 Main Sale-664]
    style CC187 fill:#3fb950
    CC186[186 Main Sale]
    style CC186 fill:#3fb950
    CC352[352 Main Sale ===V4 bck]
    style CC352 fill:#3fb950
    CC214[214 Main Sale Sale Bar...]
    style CC214 fill:#3fb950
    CC353 --> CC186
    CC420 --> CC186
    CC185 --> CC186
    CC353 --> CC187
    CC420 --> CC187
    CC185 --> CC187
    CC353 --> CC214
    CC420 --> CC214
    CC185 --> CC214
    CC353 --> CC352
    CC420 --> CC352
    CC185 --> CC352
    CC143 --> CC353
    CC143 --> CC420
    CC143 --> CC185
    CC1 --> CC143
    CC186 --> T225
    CC187 --> T225
    CC214 --> T225
    CC352 --> T225
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [0](PVE-IDE-0.md) | Main Sale ===V4 | 1 |
| [186](PVE-IDE-186.md) | Main Sale | 1 |
| [187](PVE-IDE-187.md) | Main Sale-664 | 1 |
| [214](PVE-IDE-214.md) | Main Sale Sale Bar Code | 1 |
| [352](PVE-IDE-352.md) | Main Sale ===V4 bck | 1 |
| [354](PVE-IDE-354.md) | Main Sale ===V4 | 1 |
| [359](PVE-IDE-359.md) | Main Sale ===V4 | 1 |
| [363](PVE-IDE-363.md) | Main Sale | 1 |
| [364](PVE-IDE-364.md) | Main Sale-664 | 1 |
| [403](PVE-IDE-403.md) | Menu Main (TPE) | 1 |
| [409](PVE-IDE-409.md) | Main Sale ===V4 | 1 |
| [415](PVE-IDE-415.md) | Main Sale ===V4 | 1 |
| [417](PVE-IDE-417.md) | Main Sale ===V4 Booking ACTUEL | 1 |
| [440](PVE-IDE-440.md) | Main Sale | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T225[225 Payments - select]
    style T225 fill:#58a6ff
    C188[188 Search Customer]
    T225 --> C188
    style C188 fill:#3fb950
    C325[325 Pilotage Garantie]
    T225 --> C325
    style C325 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [188](PVE-IDE-188.md) | Search Customer | 1 | Sous-programme |
| [325](PVE-IDE-325.md) | Pilotage Garantie | 1 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 62 | Programme compact |
| Expressions | 21 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 2 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 62) | Code sain |
| Regles metier | 2 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 1 ecran, 0 traitement)

- **Strategie** : 1 composant(s) UI (Razor/React) avec formulaires et validation.
- 2 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| [Pilotage Garantie (IDE 325)](PVE-IDE-325.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Search Customer (IDE 188)](PVE-IDE-188.md) | Sous-programme | 1x | Normale - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 19:02*
