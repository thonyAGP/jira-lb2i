# PBS IDE 45 - Gestion Qualites

> **Analyse**: Phases 1-4 2026-02-03 17:15 -> 17:15 (18s) | Assemblage 17:15
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBS |
| IDE Position | 45 |
| Nom Programme | Gestion Qualites |
| Fichier source | `Prg_45.xml` |
| Dossier IDE | Start |
| Taches | 3 (1 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 3 |
| :warning: Statut | **ORPHELIN_POTENTIEL** |

## 2. DESCRIPTION FONCTIONNELLE

**Gestion Qualites** assure la gestion complete de ce processus.

Le flux de traitement s'organise en **3 blocs fonctionnels** :

- **Creation** (1 tache) : insertion d'enregistrements en base (mouvements, prestations)
- **Consultation** (1 tache) : ecrans de recherche, selection et consultation
- **Traitement** (1 tache) : traitements metier divers

**Donnees modifiees** : 1 tables en ecriture (tables_qualites__qua).

**Logique metier** : 6 regles identifiees couvrant conditions metier.

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (1 tache)

- **45** - Êcran **[[ECRAN]](#ecran-t1)**

Delegue a : [Minusculage Français (IDE 80)](PBS-IDE-80.md), [Recuperation du titre (IDE 10)](PBS-IDE-10.md)

#### Phase 2 : Consultation (1 tache)

- **45.1** - Recherche Code Tri

Delegue a : [Recuperation du titre (IDE 10)](PBS-IDE-10.md)

#### Phase 3 : Creation (1 tache)

- **45.2** - Limite à 15 Creations

Delegue a : [Creation Historique (IDE 79)](PBS-IDE-79.md)

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| tables_qualites__qua | R/**W** (3 usages) |  |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>45 - Êcran [[ECRAN]](#ecran-t1)

**Role** : Traitement : Êcran.
**Ecran** : 893 x 201 DLU (MDI) | [Voir mockup](#ecran-t1)
**Delegue a** : [Minusculage Français (IDE 80)](PBS-IDE-80.md), [Recuperation du titre (IDE 10)](PBS-IDE-10.md)


### 3.2 Consultation (1 tache)

Ecrans de recherche et consultation.

---

#### <a id="t2"></a>45.1 - Recherche Code Tri

**Role** : Traitement : Recherche Code Tri.


### 3.3 Creation (1 tache)

Insertion de nouveaux enregistrements en base.

---

#### <a id="t3"></a>45.2 - Limite à 15 Creations

**Role** : Creation d'enregistrement : Limite à 15 Creations.
**Delegue a** : [Creation Historique (IDE 79)](PBS-IDE-79.md)


## 5. REGLES METIER

6 regles identifiees:

### Autres (6 regles)

#### <a id="rm-RM-001"></a>[RM-001] Si Stat (0 alors 'C'MODE) sinon 'CQUP','MQUP')

| Element | Detail |
|---------|--------|
| **Condition** | `Stat (0` |
| **Si vrai** | 'C'MODE) |
| **Si faux** | 'CQUP','MQUP') |
| **Expression source** | Expression 2 : `IF (Stat (0,'C'MODE),'CQUP','MQUP')` |
| **Exemple** | Si Stat (0 â†’ 'C'MODE). Sinon â†’ 'CQUP','MQUP') |

#### <a id="rm-RM-002"></a>[RM-002] Condition toujours vraie (flag actif)

| Element | Detail |
|---------|--------|
| **Condition** | `[O]='O'` |
| **Si vrai** | 'TRUE'LOG |
| **Si faux** | 'FALSE'LOG) |
| **Expression source** | Expression 21 : `IF ([O]='O','TRUE'LOG,'FALSE'LOG)` |
| **Exemple** | Si [O]='O' â†’ 'TRUE'LOG. Sinon â†’ 'FALSE'LOG) |

#### <a id="rm-RM-003"></a>[RM-003] Si [P] alors 'O' sinon 'N')

| Element | Detail |
|---------|--------|
| **Condition** | `[P]` |
| **Si vrai** | 'O' |
| **Si faux** | 'N') |
| **Expression source** | Expression 23 : `IF ([P],'O','N')` |
| **Exemple** | Si [P] â†’ 'O'. Sinon â†’ 'N') |

#### <a id="rm-RM-004"></a>[RM-004] Si ExpCalc('29'EXP) alors 85.75 sinon 62.75)

| Element | Detail |
|---------|--------|
| **Condition** | `ExpCalc('29'EXP)` |
| **Si vrai** | 85.75 |
| **Si faux** | 62.75) |
| **Expression source** | Expression 25 : `IF(ExpCalc('29'EXP),85.75,62.75)` |
| **Exemple** | Si ExpCalc('29'EXP) â†’ 85.75. Sinon â†’ 62.75) |

#### <a id="rm-RM-005"></a>[RM-005] Condition toujours vraie (flag actif)

| Element | Detail |
|---------|--------|
| **Condition** | `[M]='1'` |
| **Si vrai** | 'TRUE'LOG |
| **Si faux** | 'FALSE'LOG) |
| **Expression source** | Expression 32 : `IF ([M]='1','TRUE'LOG,'FALSE'LOG)` |
| **Exemple** | Si [M]='1' â†’ 'TRUE'LOG. Sinon â†’ 'FALSE'LOG) |

#### <a id="rm-RM-006"></a>[RM-006] Si [AH] alors '1' sinon '0')

| Element | Detail |
|---------|--------|
| **Condition** | `[AH]` |
| **Si vrai** | '1' |
| **Si faux** | '0') |
| **Expression source** | Expression 33 : `IF ([AH],'1','0')` |
| **Exemple** | Si [AH] â†’ '1'. Sinon â†’ '0') |

## 6. CONTEXTE

- **Appele par**: (aucun)
- **Appelle**: 3 programmes | **Tables**: 1 (W:1 R:1 L:0) | **Taches**: 3 | **Expressions**: 43

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 3)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 45 | 45 | Êcran | MDI | 893 | 201 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>45 - Êcran
**Tache** : [45](#t1) | **Type** : MDI | **Dimensions** : 893 x 201 DLU
**Bloc** : Traitement | **Titre IDE** : Êcran

<!-- FORM-DATA:
{
    "width":  893,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  1,
                         "w":  889,
                         "fmt":  "",
                         "name":  "",
                         "h":  20,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  12,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "110",
                         "w":  686,
                         "y":  30,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  16,
                         "h":  132,
                         "cols":  [
                                      {
                                          "title":  "Qualité",
                                          "layer":  1,
                                          "w":  176
                                      },
                                      {
                                          "title":  "Libellé",
                                          "layer":  2,
                                          "w":  290
                                      },
                                      {
                                          "title":  "Livre de Porte (Grèce)",
                                          "layer":  3,
                                          "w":  186
                                      }
                                  ],
                         "rows":  3
                     },
                     {
                         "x":  705,
                         "type":  "label",
                         "var":  "",
                         "y":  44,
                         "w":  180,
                         "fmt":  "",
                         "name":  "",
                         "h":  106,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  112,
                         "type":  "label",
                         "var":  "",
                         "y":  46,
                         "w":  21,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "-",
                         "parent":  4
                     },
                     {
                         "x":  1,
                         "type":  "label",
                         "var":  "",
                         "y":  173,
                         "w":  888,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  66,
                         "type":  "edit",
                         "var":  "",
                         "y":  46,
                         "w":  42,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  130,
                         "type":  "edit",
                         "var":  "",
                         "y":  46,
                         "w":  53,
                         "fmt":  "",
                         "name":  "QUA Compl. Qualite",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  203,
                         "type":  "edit",
                         "var":  "",
                         "y":  46,
                         "w":  277,
                         "fmt":  "",
                         "name":  "QUA Libelle",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  565,
                         "type":  "checkbox",
                         "var":  "",
                         "y":  46,
                         "w":  24,
                         "fmt":  "",
                         "name":  "v. livre de porte",
                         "h":  12,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  6,
                         "type":  "edit",
                         "var":  "",
                         "y":  7,
                         "w":  396,
                         "fmt":  "30",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  614,
                         "type":  "edit",
                         "var":  "",
                         "y":  7,
                         "w":  268,
                         "fmt":  "WWW DD MMM YYYYT",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  718,
                         "type":  "button",
                         "var":  "",
                         "y":  52,
                         "w":  154,
                         "fmt":  "\u0026Visualisation",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  718,
                         "type":  "button",
                         "var":  "",
                         "y":  76,
                         "w":  154,
                         "fmt":  "\u0026Modification",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  718,
                         "type":  "button",
                         "var":  "",
                         "y":  100,
                         "w":  154,
                         "fmt":  "\u0026Creation",
                         "name":  "Creation",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  718,
                         "type":  "button",
                         "var":  "",
                         "y":  124,
                         "w":  154,
                         "fmt":  "\u0026Annulation",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  7,
                         "type":  "button",
                         "var":  "",
                         "y":  176,
                         "w":  154,
                         "fmt":  "\u0026Quitter",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  14
                     }
                 ],
    "taskId":  "45",
    "height":  201
}
-->

<details>
<summary><strong>Champs : 6 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 66,46 | (sans nom) | - | edit |
| 130,46 | QUA Compl. Qualite | - | edit |
| 203,46 | QUA Libelle | - | edit |
| 565,46 | v. livre de porte | - | checkbox |
| 6,7 | 30 | - | edit |
| 614,7 | WWW DD MMM YYYYT | - | edit |

</details>

<details>
<summary><strong>Boutons : 5 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Visualisation | 718,52 | Bouton fonctionnel |
| Modification | 718,76 | Modifie l'element |
| Creation | 718,100 | Appel [Creation Historique (IDE 79)](PBS-IDE-79.md) |
| Annulation | 718,124 | Annule et retour au menu |
| Quitter | 7,176 | Quitte le programme |

</details>

## 9. NAVIGATION

Ecran unique: **Êcran**

### 9.3 Structure hierarchique (3 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **45.1** | [**Êcran** (45)](#t1) [mockup](#ecran-t1) | MDI | 893x201 | Traitement |
| **45.2** | [**Recherche Code Tri** (45.1)](#t2) | MDI | - | Consultation |
| **45.3** | [**Limite à 15 Creations** (45.2)](#t3) | MDI | - | Creation |

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
| 120 | tables_qualites__qua |  | DB | R | **W** |   | 3 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 120 - tables_qualites__qua (R/**W**) - 3 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | > societe | W | Alpha |
| B | v. titre | W | Alpha |
| C | v.contrôle | W | Logical |
| D | v.valeur Tri | W | Alpha |
| E | v.compteur | W | Numeric |
| F | v. livre de porte | W | Logical |
| G | v.liste mecano | W | Logical |
| H | Taille Tableau | W | Numeric |

</details>

## 11. VARIABLES

### 11.1 Variables de session (6)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| B | v. titre | Alpha | 1x session |
| C | v.contrôle | Logical | 1x session |
| D | v.valeur Tri | Alpha | 1x session |
| E | v.compteur | Numeric | 1x session |
| F | v. livre de porte | Logical | - |
| G | v.liste mecano | Logical | - |

### 11.2 Autres (2)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | > societe | Alpha | - |
| H | Taille Tableau | Numeric | - |

## 12. EXPRESSIONS

**43 / 43 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCULATION | 4 | 0 |
| CONDITION | 14 | 4 |
| CAST_LOGIQUE | 2 | 2 |
| CONSTANTE | 5 | 0 |
| DATE | 1 | 0 |
| NEGATION | 5 | 0 |
| OTHER | 6 | 0 |
| REFERENCE_VG | 4 | 0 |
| FORMAT | 1 | 0 |
| STRING | 1 | 0 |

### 12.2 Expressions cles par type

#### CALCULATION (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 42 | `[AN]+36` | - |
| CALCULATION | 43 | `[AN]+37` | - |
| CALCULATION | 38 | `22+36.25+14.5+18+
IF(VG10,14.125,0)+
IF(VG6,18.25,0)+
IF(VG8,24.25,0)+
IF(ExpCalc('29'EXP),21.625,0)+
4.5` | - |
| CALCULATION | 41 | `[AN]+10` | - |

#### CONDITION (14 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 25 | `IF(ExpCalc('29'EXP),85.75,62.75)` | [RM-004](#rm-RM-004) |
| CONDITION | 33 | `IF ([AH],'1','0')` | [RM-006](#rm-RM-006) |
| CONDITION | 2 | `IF (Stat (0,'C'MODE),'CQUP','MQUP')` | [RM-001](#rm-RM-001) |
| CONDITION | 23 | `IF ([P],'O','N')` | [RM-003](#rm-RM-003) |
| CONDITION | 15 | `Trim([AL])<>''` | - |
| ... | | *+9 autres* | |

#### CAST_LOGIQUE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 32 | `IF ([M]='1','TRUE'LOG,'FALSE'LOG)` | [RM-005](#rm-RM-005) |
| CAST_LOGIQUE | 21 | `IF ([O]='O','TRUE'LOG,'FALSE'LOG)` | [RM-002](#rm-RM-002) |

#### CONSTANTE (5 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 18 | `'0'` | - |
| CONSTANTE | 19 | `'O'` | - |
| CONSTANTE | 13 | `22` | - |
| CONSTANTE | 7 | `'P'` | - |
| CONSTANTE | 9 | `'GO'` | - |

#### DATE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| DATE | 11 | `Date ()` | - |

#### NEGATION (5 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| NEGATION | 29 | `NOT Stat(0,'E'MODE) AND NOT VG10` | - |
| NEGATION | 31 | `NOT Stat(0,'E'MODE)` | - |
| NEGATION | 27 | `NOT VG10` | - |
| NEGATION | 1 | `NOT (Stat (0,'E'MODE))` | - |
| NEGATION | 3 | `NOT (v.valeur Tri [D])` | - |

#### OTHER (6 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 24 | `ExpCalc('4'EXP)` | - |
| OTHER | 30 | `Stat(0,'E'MODE)` | - |
| OTHER | 39 | `[AN]` | - |
| OTHER | 4 | `Stat (0,'C'MODE)` | - |
| OTHER | 6 | `GetParam ('SOCIETE')` | - |
| ... | | *+1 autres* | |

#### REFERENCE_VG (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 34 | `VG6` | - |
| REFERENCE_VG | 35 | `VG8` | - |
| REFERENCE_VG | 12 | `VG4` | - |
| REFERENCE_VG | 28 | `VG10` | - |

#### FORMAT (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| FORMAT | 26 | `'v.contrôle [C]'FORM` | - |

#### STRING (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| STRING | 10 | `Trim (v. titre [B])` | - |

### 12.3 Toutes les expressions (43)

<details>
<summary>Voir les 43 expressions</summary>

#### CALCULATION (4)

| IDE | Expression Decodee |
|-----|-------------------|
| 38 | `22+36.25+14.5+18+
IF(VG10,14.125,0)+
IF(VG6,18.25,0)+
IF(VG8,24.25,0)+
IF(ExpCalc('29'EXP),21.625,0)+
4.5` |
| 41 | `[AN]+10` |
| 42 | `[AN]+36` |
| 43 | `[AN]+37` |

#### CONDITION (14)

| IDE | Expression Decodee |
|-----|-------------------|
| 2 | `IF (Stat (0,'C'MODE),'CQUP','MQUP')` |
| 23 | `IF ([P],'O','N')` |
| 25 | `IF(ExpCalc('29'EXP),85.75,62.75)` |
| 33 | `IF ([AH],'1','0')` |
| 5 | `[K]=''` |
| 20 | `[N]<>'N'` |
| 36 | `GetParam ('CODELANGUE') = 'FRA'` |
| 37 | `GetParam ('CODELANGUE') <> 'FRA'` |
| 40 | `VG3='DSIOP'` |
| 14 | `Trim([L])<>''` |
| 15 | `Trim([AL])<>''` |
| 16 | `Trim([L])=''` |
| 17 | `Trim([AL])=''` |
| 22 | `Trim (GetParam ('FISCALITEGREC'))='O'` |

#### CAST_LOGIQUE (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 21 | `IF ([O]='O','TRUE'LOG,'FALSE'LOG)` |
| 32 | `IF ([M]='1','TRUE'LOG,'FALSE'LOG)` |

#### CONSTANTE (5)

| IDE | Expression Decodee |
|-----|-------------------|
| 7 | `'P'` |
| 9 | `'GO'` |
| 13 | `22` |
| 18 | `'0'` |
| 19 | `'O'` |

#### DATE (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 11 | `Date ()` |

#### NEGATION (5)

| IDE | Expression Decodee |
|-----|-------------------|
| 1 | `NOT (Stat (0,'E'MODE))` |
| 3 | `NOT (v.valeur Tri [D])` |
| 27 | `NOT VG10` |
| 29 | `NOT Stat(0,'E'MODE) AND NOT VG10` |
| 31 | `NOT Stat(0,'E'MODE)` |

#### OTHER (6)

| IDE | Expression Decodee |
|-----|-------------------|
| 4 | `Stat (0,'C'MODE)` |
| 6 | `GetParam ('SOCIETE')` |
| 8 | `v.compteur [E]` |
| 24 | `ExpCalc('4'EXP)` |
| 30 | `Stat(0,'E'MODE)` |
| 39 | `[AN]` |

#### REFERENCE_VG (4)

| IDE | Expression Decodee |
|-----|-------------------|
| 12 | `VG4` |
| 28 | `VG10` |
| 34 | `VG6` |
| 35 | `VG8` |

#### FORMAT (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 26 | `'v.contrôle [C]'FORM` |

#### STRING (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 10 | `Trim (v. titre [B])` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

**Chemin**: (pas de callers directs)

```mermaid
graph LR
    T45[45 Gestion Qualites]
    style T45 fill:#58a6ff
    NONE[Aucun caller]
    NONE -.-> T45
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| - | (aucun) | - |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T45[45 Gestion Qualites]
    style T45 fill:#58a6ff
    C80[80 Minusculage Français]
    T45 --> C80
    style C80 fill:#3fb950
    C10[10 Recuperation du titre]
    T45 --> C10
    style C10 fill:#3fb950
    C79[79 Creation Historique]
    T45 --> C79
    style C79 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [80](PBS-IDE-80.md) | Minusculage Français | 2 | Sous-programme |
| [10](PBS-IDE-10.md) | Recuperation du titre | 1 | Recuperation donnees |
| [79](PBS-IDE-79.md) | Creation Historique | 1 | Historique/consultation |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 83 | Programme compact |
| Expressions | 43 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 3 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 83) | Code sain |
| Regles metier | 6 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 1 ecran, 0 traitement)

- **Strategie** : 1 composant(s) UI (Razor/React) avec formulaires et validation.
- 3 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Consultation (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Composants de recherche/selection en modales.

#### Creation (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Repository pattern avec Entity Framework Core.
- Insertion via `IRepository<T>.CreateAsync()`

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| tables_qualites__qua | Table WRITE (Database) | 1x | Schema + repository |
| [Minusculage Français (IDE 80)](PBS-IDE-80.md) | Sous-programme | 2x | Haute - Sous-programme |
| [Creation Historique (IDE 79)](PBS-IDE-79.md) | Sous-programme | 1x | Normale - Historique/consultation |
| [Recuperation du titre (IDE 10)](PBS-IDE-10.md) | Sous-programme | 1x | Normale - Recuperation donnees |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 17:15*
