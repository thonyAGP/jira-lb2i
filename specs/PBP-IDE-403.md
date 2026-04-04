# PBP IDE 403 - Selection heure / Vol

> **Analyse**: Phases 1-4 2026-02-03 16:51 -> 16:51 (29s) | Assemblage 16:51
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBP |
| IDE Position | 403 |
| Nom Programme | Selection heure / Vol |
| Fichier source | `Prg_403.xml` |
| Dossier IDE | Zoom |
| Taches | 3 (2 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 1 |

## 2. DESCRIPTION FONCTIONNELLE

**Selection heure / Vol** assure la gestion complete de ce processus, accessible depuis [Liste CLients AVPBDR (IDE 174)](PBP-IDE-174.md), [  Liste present personnel plan (IDE 227)](PBP-IDE-227.md), [  Liste personnels AVPBDR (IDE 234)](PBP-IDE-234.md), [  Liste CLients arrivant (IDE 156)](PBP-IDE-156.md), [  Liste Clients present (IDE 162)](PBP-IDE-162.md), [  Liste CLients depart (IDE 168)](PBP-IDE-168.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Consultation** (3 taches) : ecrans de recherche, selection et consultation

## 3. BLOCS FONCTIONNELS

### 3.1 Consultation (3 taches)

Ecrans de recherche et consultation.

---

#### <a id="t1"></a>403 - selection lieu sejour [[ECRAN]](#ecran-t1)

**Role** : Selection par l'operateur : selection lieu sejour.
**Ecran** : 360 x 175 DLU (MDI) | [Voir mockup](#ecran-t1)
**Variables liees** : G (p.i.Selection min), H (p.i.Selection max)

---

#### <a id="t4"></a>403.1 - selection lieu sejour [[ECRAN]](#ecran-t4)

**Role** : Selection par l'operateur : selection lieu sejour.
**Ecran** : 360 x 175 DLU (MDI) | [Voir mockup](#ecran-t4)
**Variables liees** : G (p.i.Selection min), H (p.i.Selection max)

---

#### <a id="t7"></a>403.2 - selection lieu sejour [[ECRAN]](#ecran-t7)

**Role** : Selection par l'operateur : selection lieu sejour.
**Ecran** : 360 x 175 DLU (MDI) | [Voir mockup](#ecran-t7)
**Variables liees** : G (p.i.Selection min), H (p.i.Selection max)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Liste CLients AVPBDR (IDE 174)](PBP-IDE-174.md), [  Liste present personnel plan (IDE 227)](PBP-IDE-227.md), [  Liste personnels AVPBDR (IDE 234)](PBP-IDE-234.md), [  Liste CLients arrivant (IDE 156)](PBP-IDE-156.md), [  Liste Clients present (IDE 162)](PBP-IDE-162.md), [  Liste CLients depart (IDE 168)](PBP-IDE-168.md)
- **Appelle**: 1 programmes | **Tables**: 2 (W:0 R:2 L:0) | **Taches**: 3 | **Expressions**: 17

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (2 / 3)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 403.1 | 403.1 | selection lieu sejour | MDI | 360 | 175 | Consultation |
| 2 | 403.2 | 403.2 | selection lieu sejour | MDI | 360 | 175 | Consultation |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t4"></a>403.1 - selection lieu sejour
**Tache** : [403.1](#t4) | **Type** : MDI | **Dimensions** : 360 x 175 DLU
**Bloc** : Consultation | **Titre IDE** : selection lieu sejour

<!-- FORM-DATA:
{
    "width":  360,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  18,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "196",
                         "w":  323,
                         "y":  3,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  13,
                         "h":  116,
                         "cols":  [
                                      {
                                          "title":  "Date",
                                          "layer":  1,
                                          "w":  128
                                      },
                                      {
                                          "title":  "Heure",
                                          "layer":  2,
                                          "w":  74
                                      },
                                      {
                                          "title":  "Vol",
                                          "layer":  3,
                                          "w":  87
                                      }
                                  ],
                         "rows":  3
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  153,
                         "w":  353,
                         "fmt":  "",
                         "name":  "",
                         "h":  19,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  24,
                         "type":  "edit",
                         "var":  "",
                         "y":  18,
                         "w":  123,
                         "fmt":  "",
                         "name":  "VOL Date",
                         "h":  9,
                         "color":  "196",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  176,
                         "type":  "edit",
                         "var":  "",
                         "y":  18,
                         "w":  30,
                         "fmt":  "",
                         "name":  "VOL Heure",
                         "h":  9,
                         "color":  "196",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  227,
                         "type":  "edit",
                         "var":  "",
                         "y":  18,
                         "w":  75,
                         "fmt":  "",
                         "name":  "VOL Code Vol",
                         "h":  8,
                         "color":  "196",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  10,
                         "type":  "button",
                         "var":  "",
                         "y":  156,
                         "w":  154,
                         "fmt":  "\u0026Sélectionner",
                         "name":  "bouton selectionner",
                         "h":  14,
                         "color":  "",
                         "text":  "",
                         "parent":  9
                     },
                     {
                         "x":  185,
                         "type":  "button",
                         "var":  "",
                         "y":  156,
                         "w":  154,
                         "fmt":  "\u0026Quitter",
                         "name":  "bouton quitter",
                         "h":  14,
                         "color":  "",
                         "text":  "",
                         "parent":  9
                     },
                     {
                         "x":  147,
                         "type":  "image",
                         "var":  "",
                         "y":  128,
                         "w":  58,
                         "fmt":  "",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "403.1",
    "height":  175
}
-->

<details>
<summary><strong>Champs : 3 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 24,18 | VOL Date | - | edit |
| 176,18 | VOL Heure | - | edit |
| 227,18 | VOL Code Vol | - | edit |

</details>

<details>
<summary><strong>Boutons : 2 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Sélectionner | 10,156 | Bouton fonctionnel |
| Quitter | 185,156 | Quitte le programme |

</details>

---

#### <a id="ecran-t7"></a>403.2 - selection lieu sejour
**Tache** : [403.2](#t7) | **Type** : MDI | **Dimensions** : 360 x 175 DLU
**Bloc** : Consultation | **Titre IDE** : selection lieu sejour

<!-- FORM-DATA:
{
    "width":  360,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  18,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "196",
                         "w":  323,
                         "y":  3,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  13,
                         "h":  116,
                         "cols":  [
                                      {
                                          "title":  "Date",
                                          "layer":  1,
                                          "w":  128
                                      },
                                      {
                                          "title":  "Heure",
                                          "layer":  2,
                                          "w":  74
                                      },
                                      {
                                          "title":  "Vol",
                                          "layer":  3,
                                          "w":  87
                                      }
                                  ],
                         "rows":  3
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  153,
                         "w":  353,
                         "fmt":  "",
                         "name":  "",
                         "h":  19,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  24,
                         "type":  "edit",
                         "var":  "",
                         "y":  18,
                         "w":  123,
                         "fmt":  "",
                         "name":  "VOL Date",
                         "h":  9,
                         "color":  "196",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  176,
                         "type":  "edit",
                         "var":  "",
                         "y":  18,
                         "w":  30,
                         "fmt":  "",
                         "name":  "VOL Heure",
                         "h":  9,
                         "color":  "196",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  227,
                         "type":  "edit",
                         "var":  "",
                         "y":  18,
                         "w":  75,
                         "fmt":  "",
                         "name":  "VOL Code Vol",
                         "h":  8,
                         "color":  "196",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  10,
                         "type":  "button",
                         "var":  "",
                         "y":  156,
                         "w":  154,
                         "fmt":  "\u0026Sélectionner",
                         "name":  "bouton selectionner",
                         "h":  14,
                         "color":  "",
                         "text":  "",
                         "parent":  9
                     },
                     {
                         "x":  185,
                         "type":  "button",
                         "var":  "",
                         "y":  156,
                         "w":  154,
                         "fmt":  "\u0026Quitter",
                         "name":  "bouton quitter",
                         "h":  14,
                         "color":  "",
                         "text":  "",
                         "parent":  9
                     },
                     {
                         "x":  147,
                         "type":  "image",
                         "var":  "",
                         "y":  128,
                         "w":  58,
                         "fmt":  "",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "403.2",
    "height":  175
}
-->

<details>
<summary><strong>Champs : 3 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 24,18 | VOL Date | - | edit |
| 176,18 | VOL Heure | - | edit |
| 227,18 | VOL Code Vol | - | edit |

</details>

<details>
<summary><strong>Boutons : 2 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Sélectionner | 10,156 | Bouton fonctionnel |
| Quitter | 185,156 | Quitte le programme |

</details>

## 9. NAVIGATION

### 9.1 Enchainement des ecrans

```mermaid
flowchart TD
    START([Entree])
    style START fill:#3fb950
    VF4[403.1 selection lieu sejour]
    style VF4 fill:#58a6ff
    VF7[403.2 selection lieu sejour]
    style VF7 fill:#58a6ff
    EXT389[IDE 389 Recuperation d...]
    style EXT389 fill:#3fb950
    FIN([Sortie])
    style FIN fill:#f85149
    START --> VF4
    VF4 -->|Recuperation donnees| EXT389
    EXT389 --> FIN
```

**Detail par enchainement :**

| Depuis | Action | Vers | Retour |
|--------|--------|------|--------|
| selection lieu sejour | Recuperation donnees | [Recuperation du titre (IDE 389)](PBP-IDE-389.md) | Retour ecran |

### 9.3 Structure hierarchique (3 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **403.1** | [**selection lieu sejour** (403)](#t1) [mockup](#ecran-t1) | MDI | 360x175 | Consultation |
| 403.1.1 | [selection lieu sejour (403.1)](#t4) [mockup](#ecran-t4) | MDI | 360x175 | |
| 403.1.2 | [selection lieu sejour (403.2)](#t7) [mockup](#ecran-t7) | MDI | 360x175 | |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Selection heure Vol orig]
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

### Tables utilisees (2)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 134 | groupe_arr_dep___vol |  | DB | R |   |   | 1 |
| 1021 | Table_1021 |  | MEM | R |   |   | 1 |

### Colonnes par table (2 / 2 tables avec colonnes identifiees)

<details>
<summary>Table 134 - groupe_arr_dep___vol (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | w0_AutoriseQuitter | R | Logical |
| B | bouton selectionner | R | Alpha |
| C | bouton quitter | R | Alpha |

</details>

<details>
<summary>Table 1021 - Table_1021 (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | w0_AutoriseQuitter | R | Logical |
| B | bouton selectionner | R | Alpha |
| C | bouton quitter | R | Alpha |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (8)

Variables recues du programme appelant ([Liste CLients AVPBDR (IDE 174)](PBP-IDE-174.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | p.Type Vol | Alpha | - |
| B | p.i.Date | Date | - |
| C | p.o.Date village | Date | - |
| D | p.i.o.Heure village | Alpha | - |
| E | p.o.Code vol | Alpha | - |
| F | p.i.o.Code ville | Alpha | - |
| G | p.i.Selection min | Alpha | - |
| H | p.i.Selection max | Alpha | - |

### 11.2 Variables de session (1)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| I | v.Titre | Alpha | - |

## 12. EXPRESSIONS

**17 / 17 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONSTANTE | 3 | 0 |
| NEGATION | 1 | 0 |
| OTHER | 7 | 0 |
| CONDITION | 2 | 0 |
| CAST_LOGIQUE | 1 | 0 |
| STRING | 3 | 0 |

### 12.2 Expressions cles par type

#### CONSTANTE (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 16 | `''` | - |
| CONSTANTE | 15 | `0` | - |
| CONSTANTE | 1 | `71` | - |

#### NEGATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| NEGATION | 2 | `NOT VG88` | - |

#### OTHER (7 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 9 | `{1,1}` | - |
| OTHER | 10 | `{1,2}` | - |
| OTHER | 17 | `[P]` | - |
| OTHER | 8 | `GetParam ('SOCIETE')` | - |
| OTHER | 4 | `[K]` | - |
| ... | | *+2 autres* | |

#### CONDITION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 13 | `CndRange ({1,8}<>'',{1,8})` | - |
| CONDITION | 12 | `CndRange ({1,7}<>'',{1,7})` | - |

#### CAST_LOGIQUE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 14 | `'TRUE'LOG` | - |

#### STRING (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| STRING | 11 | `Val ({1,4},'2')` | - |
| STRING | 5 | `Str ([L],'2P0Z0')` | - |
| STRING | 3 | `Trim ({1,19})` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Liste CLients AVPBDR (IDE 174)](PBP-IDE-174.md) -> **Selection heure / Vol (IDE 403)**

Main -> ... -> [  Liste present personnel plan (IDE 227)](PBP-IDE-227.md) -> **Selection heure / Vol (IDE 403)**

Main -> ... -> [  Liste personnels AVPBDR (IDE 234)](PBP-IDE-234.md) -> **Selection heure / Vol (IDE 403)**

Main -> ... -> [  Liste CLients arrivant (IDE 156)](PBP-IDE-156.md) -> **Selection heure / Vol (IDE 403)**

Main -> ... -> [  Liste Clients present (IDE 162)](PBP-IDE-162.md) -> **Selection heure / Vol (IDE 403)**

Main -> ... -> [  Liste CLients depart (IDE 168)](PBP-IDE-168.md) -> **Selection heure / Vol (IDE 403)**

```mermaid
graph LR
    T403[403 Selection heure Vol]
    style T403 fill:#58a6ff
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
    CC156 --> T403
    CC162 --> T403
    CC168 --> T403
    CC174 --> T403
    CC227 --> T403
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [174](PBP-IDE-174.md) | Liste CLients AVPBDR | 6 |
| [227](PBP-IDE-227.md) |   Liste present personnel plan | 6 |
| [234](PBP-IDE-234.md) |   Liste personnels AVPBDR | 6 |
| [156](PBP-IDE-156.md) |   Liste CLients arrivant | 3 |
| [162](PBP-IDE-162.md) |   Liste Clients present | 3 |
| [168](PBP-IDE-168.md) |   Liste CLients depart | 3 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T403[403 Selection heure Vol]
    style T403 fill:#58a6ff
    C389[389 Recuperation du titre]
    T403 --> C389
    style C389 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [389](PBP-IDE-389.md) | Recuperation du titre | 1 | Recuperation donnees |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 77 | Programme compact |
| Expressions | 17 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 1 | Peu de dependances |
| Ecrans visibles | 2 | Quelques ecrans |
| Code desactive | 0% (0 / 77) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Consultation (3 taches: 3 ecrans, 0 traitement)

- **Strategie** : Composants de recherche/selection en modales.
- 3 ecrans : selection lieu sejour, selection lieu sejour, selection lieu sejour

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| [Recuperation du titre (IDE 389)](PBP-IDE-389.md) | Sous-programme | 1x | Normale - Recuperation donnees |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 16:51*
