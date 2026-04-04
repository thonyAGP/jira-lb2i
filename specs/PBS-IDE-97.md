# PBS IDE 97 - Table des Bâtiments

> **Analyse**: Phases 1-4 2026-02-03 17:34 -> 17:34 (13s) | Assemblage 17:34
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBS |
| IDE Position | 97 |
| Nom Programme | Table des Bâtiments |
| Fichier source | `Prg_97.xml` |
| Dossier IDE | Suppr |
| Taches | 2 (1 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 5 |
| :warning: Statut | **ORPHELIN_POTENTIEL** |

## 2. DESCRIPTION FONCTIONNELLE

**Table des Bâtiments** assure la gestion complete de ce processus.

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (2 taches) : traitements metier divers

**Logique metier** : 1 regles identifiees couvrant conditions metier.

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (2 taches)

Traitements internes.

---

#### <a id="t1"></a>97 - Êcran [[ECRAN]](#ecran-t1)

**Role** : Traitement : Êcran.
**Ecran** : 850 x 248 DLU (MDI) | [Voir mockup](#ecran-t1)
**Delegue a** : [Recuperation du titre (IDE 10)](PBS-IDE-10.md), [  Alimentation Combos VILLAGE (IDE 50)](PBS-IDE-50.md), [Caractères Interdits (A6) (IDE 76)](PBS-IDE-76.md)

---

#### <a id="t2"></a>97.1 - Mise à Jour Combo

**Role** : Traitement : Mise à Jour Combo.
**Variables liees** : D (v.MaJ Combo)
**Delegue a** : [Recuperation du titre (IDE 10)](PBS-IDE-10.md), [  Alimentation Combos VILLAGE (IDE 50)](PBS-IDE-50.md), [Caractères Interdits (A6) (IDE 76)](PBS-IDE-76.md)


## 5. REGLES METIER

1 regles identifiees:

### Autres (1 regles)

#### <a id="rm-RM-001"></a>[RM-001] Si Stat (0 alors 'C'MODE) sinon 'CBAT',IF (Stat (0,'M'MODE),'MBAT','ABAT'))

| Element | Detail |
|---------|--------|
| **Condition** | `Stat (0` |
| **Si vrai** | 'C'MODE) |
| **Si faux** | 'CBAT',IF (Stat (0,'M'MODE),'MBAT','ABAT')) |
| **Expression source** | Expression 2 : `IF (Stat (0,'C'MODE),'CBAT',IF (Stat (0,'M'MODE),'MBAT','ABA` |
| **Exemple** | Si Stat (0 â†’ 'C'MODE). Sinon â†’ 'CBAT',IF (Stat (0,'M'MODE),'MBAT','ABAT')) |

## 6. CONTEXTE

- **Appele par**: (aucun)
- **Appelle**: 5 programmes | **Tables**: 2 (W:0 R:1 L:1) | **Taches**: 2 | **Expressions**: 21

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 2)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 97 | 97 | Êcran | MDI | 850 | 248 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>97 - Êcran
**Tache** : [97](#t1) | **Type** : MDI | **Dimensions** : 850 x 248 DLU
**Bloc** : Traitement | **Titre IDE** : Êcran

<!-- FORM-DATA:
{
    "width":  850,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  1,
                         "w":  846,
                         "fmt":  "",
                         "name":  "",
                         "h":  20,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  23,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "110",
                         "w":  578,
                         "y":  31,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  11,
                         "h":  180,
                         "cols":  [
                                      {
                                          "title":  "Code",
                                          "layer":  1,
                                          "w":  135
                                      },
                                      {
                                          "title":  "Libellé",
                                          "layer":  2,
                                          "w":  270
                                      },
                                      {
                                          "title":  "Nombre",
                                          "layer":  3,
                                          "w":  137
                                      }
                                  ],
                         "rows":  3
                     },
                     {
                         "x":  632,
                         "type":  "label",
                         "var":  "",
                         "y":  98,
                         "w":  183,
                         "fmt":  "",
                         "name":  "",
                         "h":  112,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  1,
                         "type":  "label",
                         "var":  "",
                         "y":  221,
                         "w":  846,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  92,
                         "type":  "edit",
                         "var":  "",
                         "y":  45,
                         "w":  30,
                         "fmt":  "U2",
                         "name":  "CODE ALPHA6",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  175,
                         "type":  "edit",
                         "var":  "",
                         "y":  45,
                         "w":  232,
                         "fmt":  "",
                         "name":  "LIBELLE VINGT",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  443,
                         "type":  "edit",
                         "var":  "",
                         "y":  45,
                         "w":  64,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  5
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
                         "x":  637,
                         "type":  "edit",
                         "var":  "",
                         "y":  7,
                         "w":  203,
                         "fmt":  "WWW DD MMM YYYYT",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  626,
                         "type":  "image",
                         "var":  "",
                         "y":  27,
                         "w":  178,
                         "fmt":  "",
                         "name":  "",
                         "h":  64,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  646,
                         "type":  "button",
                         "var":  "",
                         "y":  103,
                         "w":  154,
                         "fmt":  "\u0026Visualisation",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  646,
                         "type":  "button",
                         "var":  "",
                         "y":  124,
                         "w":  154,
                         "fmt":  "\u0026Modification",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  646,
                         "type":  "button",
                         "var":  "",
                         "y":  145,
                         "w":  154,
                         "fmt":  "\u0026Creation",
                         "name":  "Création",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  646,
                         "type":  "button",
                         "var":  "",
                         "y":  166,
                         "w":  154,
                         "fmt":  "\u0026Annulation",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  646,
                         "type":  "button",
                         "var":  "",
                         "y":  187,
                         "w":  154,
                         "fmt":  "\u0026Suppression",
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
                         "y":  224,
                         "w":  154,
                         "fmt":  "\u0026Quitter",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  14
                     }
                 ],
    "taskId":  "97",
    "height":  248
}
-->

<details>
<summary><strong>Champs : 5 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 92,45 | CODE ALPHA6 | - | edit |
| 175,45 | LIBELLE VINGT | - | edit |
| 443,45 | (sans nom) | - | edit |
| 6,7 | 30 | - | edit |
| 637,7 | WWW DD MMM YYYYT | - | edit |

</details>

<details>
<summary><strong>Boutons : 6 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Visualisation | 646,103 | Bouton fonctionnel |
| Modification | 646,124 | Modifie l'element |
| Creation | 646,145 | Appel [Creation Historique (IDE 79)](PBS-IDE-79.md) |
| Annulation | 646,166 | Annule et retour au menu |
| Suppression | 646,187 | Supprime l'element selectionne |
| Quitter | 7,224 | Quitte le programme |

</details>

## 9. NAVIGATION

Ecran unique: **Êcran**

### 9.3 Structure hierarchique (2 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **97.1** | [**Êcran** (97)](#t1) [mockup](#ecran-t1) | MDI | 850x248 | Traitement |
| 97.1.1 | [Mise à Jour Combo (97.1)](#t2) | MDI | - | |

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

### Tables utilisees (2)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 102 | logement_go______lop |  | DB | R |   |   | 1 |
| 113 | tables_village |  | DB |   |   | L | 1 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 102 - logement_go______lop (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | > societe | R | Alpha |
| B | v. titre | R | Alpha |
| C | v.contrôle | R | Logical |
| D | v.MaJ Combo | R | Logical |
| E | v.Lien Chambre GO | R | Logical |

</details>

## 11. VARIABLES

### 11.1 Variables de session (4)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| B | v. titre | Alpha | 1x session |
| C | v.contrôle | Logical | - |
| D | v.MaJ Combo | Logical | [97.1](#t2) |
| E | v.Lien Chambre GO | Logical | 1x session |

### 11.2 Autres (1)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | > societe | Alpha | - |

## 12. EXPRESSIONS

**21 / 21 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONDITION | 3 | 5 |
| CONSTANTE | 3 | 0 |
| DATE | 2 | 0 |
| NEGATION | 3 | 0 |
| OTHER | 7 | 0 |
| REFERENCE_VG | 1 | 0 |
| CAST_LOGIQUE | 1 | 0 |
| STRING | 1 | 0 |

### 12.2 Expressions cles par type

#### CONDITION (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 2 | `IF (Stat (0,'C'MODE),'CBAT',IF (Stat (0,'M'MODE),'MBAT','ABAT'))` | [RM-001](#rm-RM-001) |
| CONDITION | 18 | `[K]<>''` | - |
| CONDITION | 12 | `Stat (0,'M'MODE) AND [L]=0 AND NOT ([F])` | - |

#### CONSTANTE (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 10 | `3` | - |
| CONSTANTE | 7 | `'F'` | - |
| CONSTANTE | 6 | `'VBATI'` | - |

#### DATE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| DATE | 16 | `Date ()` | - |
| DATE | 9 | `Date ()` | - |

#### NEGATION (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| NEGATION | 14 | `NOT (Stat (0,'E'MODE))` | - |
| NEGATION | 3 | `NOT (v.MaJ Combo [D])` | - |
| NEGATION | 1 | `NOT (Stat (0,'E'MODE))` | - |

#### OTHER (7 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 17 | `Time ()` | - |
| OTHER | 20 | `v.Lien Chambre GO [E]` | - |
| OTHER | 21 | `Left ([J],2)` | - |
| OTHER | 13 | `Stat (0,'E'MODE)` | - |
| OTHER | 4 | `Stat (0,'C'MODE)` | - |
| ... | | *+2 autres* | |

#### REFERENCE_VG (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 15 | `VG3` | - |

#### CAST_LOGIQUE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 19 | `'TRUE'LOG` | - |

#### STRING (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| STRING | 8 | `Trim (v. titre [B])` | - |

### 12.3 Toutes les expressions (21)

<details>
<summary>Voir les 21 expressions</summary>

#### CONDITION (3)

| IDE | Expression Decodee |
|-----|-------------------|
| 2 | `IF (Stat (0,'C'MODE),'CBAT',IF (Stat (0,'M'MODE),'MBAT','ABAT'))` |
| 12 | `Stat (0,'M'MODE) AND [L]=0 AND NOT ([F])` |
| 18 | `[K]<>''` |

#### CONSTANTE (3)

| IDE | Expression Decodee |
|-----|-------------------|
| 6 | `'VBATI'` |
| 7 | `'F'` |
| 10 | `3` |

#### DATE (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 9 | `Date ()` |
| 16 | `Date ()` |

#### NEGATION (3)

| IDE | Expression Decodee |
|-----|-------------------|
| 1 | `NOT (Stat (0,'E'MODE))` |
| 3 | `NOT (v.MaJ Combo [D])` |
| 14 | `NOT (Stat (0,'E'MODE))` |

#### OTHER (7)

| IDE | Expression Decodee |
|-----|-------------------|
| 4 | `Stat (0,'C'MODE)` |
| 5 | `GetParam ('SOCIETE')` |
| 11 | `Stat (0,'M'MODE)` |
| 13 | `Stat (0,'E'MODE)` |
| 17 | `Time ()` |
| 20 | `v.Lien Chambre GO [E]` |
| 21 | `Left ([J],2)` |

#### REFERENCE_VG (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 15 | `VG3` |

#### CAST_LOGIQUE (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 19 | `'TRUE'LOG` |

#### STRING (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 8 | `Trim (v. titre [B])` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

**Chemin**: (pas de callers directs)

```mermaid
graph LR
    T97[97 Table des Bâtiments]
    style T97 fill:#58a6ff
    NONE[Aucun caller]
    NONE -.-> T97
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| - | (aucun) | - |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T97[97 Table des Bâtiments]
    style T97 fill:#58a6ff
    C10[10 Recuperation du titre]
    T97 --> C10
    style C10 fill:#3fb950
    C50[50 Alimentation Combos...]
    T97 --> C50
    style C50 fill:#3fb950
    C76[76 Caractères Interdit...]
    T97 --> C76
    style C76 fill:#3fb950
    C79[79 Creation Historique]
    T97 --> C79
    style C79 fill:#3fb950
    C80[80 Minusculage Français]
    T97 --> C80
    style C80 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [10](PBS-IDE-10.md) | Recuperation du titre | 1 | Recuperation donnees |
| [50](PBS-IDE-50.md) |   Alimentation Combos VILLAGE | 1 | Sous-programme |
| [76](PBS-IDE-76.md) | Caractères Interdits (A6) | 1 | Validation saisie |
| [79](PBS-IDE-79.md) | Creation Historique | 1 | Historique/consultation |
| [80](PBS-IDE-80.md) | Minusculage Français | 1 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 46 | Programme compact |
| Expressions | 21 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 5 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 46) | Code sain |
| Regles metier | 1 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (2 taches: 1 ecran, 1 traitement)

- **Strategie** : Orchestrateur avec 1 ecrans (Razor/React) et 1 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 5 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| [Creation Historique (IDE 79)](PBS-IDE-79.md) | Sous-programme | 1x | Normale - Historique/consultation |
| [Minusculage Français (IDE 80)](PBS-IDE-80.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Caractères Interdits (A6) (IDE 76)](PBS-IDE-76.md) | Sous-programme | 1x | Normale - Validation saisie |
| [Recuperation du titre (IDE 10)](PBS-IDE-10.md) | Sous-programme | 1x | Normale - Recuperation donnees |
| [  Alimentation Combos VILLAGE (IDE 50)](PBS-IDE-50.md) | Sous-programme | 1x | Normale - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 17:34*
