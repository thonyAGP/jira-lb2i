# PBP IDE 192 - Liste Prestation arrivants

> **Analyse**: Phases 1-4 2026-02-03 15:44 -> 15:44 (18s) | Assemblage 15:44
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBP |
| IDE Position | 192 |
| Nom Programme | Liste Prestation arrivants |
| Fichier source | `Prg_192.xml` |
| Dossier IDE | Liste |
| Taches | 1 (1 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 6 |
| :warning: Statut | **ORPHELIN_POTENTIEL** |

## 2. DESCRIPTION FONCTIONNELLE

**Liste Prestation arrivants** assure la gestion complete de ce processus.

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

**Logique metier** : 1 regles identifiees couvrant valeurs par defaut.

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>192 - Liste Prestation arrivants [[ECRAN]](#ecran-t1)

**Role** : Traitement : Liste Prestation arrivants.
**Ecran** : 562 x 159 DLU (MDI) | [Voir mockup](#ecran-t1)
**Variables liees** : B (w0_CodePrestation), C (b_Prestation)
**Delegue a** : [Recuperation du titre (IDE 389)](PBP-IDE-389.md)


## 5. REGLES METIER

1 regles identifiees:

### Autres (1 regles)

#### <a id="rm-RM-001"></a>[RM-001] Valeur par defaut si w0_CodePrestation [B] est vide

| Element | Detail |
|---------|--------|
| **Condition** | `w0_CodePrestation [B]=''` |
| **Si vrai** | 'Toutes Prestations' |
| **Si faux** | 'Prestation : '&w0_CodePrestation [B]) |
| **Variables** | B (w0_CodePrestation) |
| **Expression source** | Expression 13 : `IF (w0_CodePrestation [B]='','Toutes Prestations','Prestatio` |
| **Exemple** | Si w0_CodePrestation [B]='' â†’ 'Toutes Prestations'. Sinon â†’ 'Prestation : '&w0_CodePrestation [B]) |

## 6. CONTEXTE

- **Appele par**: (aucun)
- **Appelle**: 6 programmes | **Tables**: 0 (W:0 R:0 L:0) | **Taches**: 1 | **Expressions**: 18

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 1)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 192 | 192 | Liste Prestation arrivants | MDI | 562 | 159 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>192 - Liste Prestation arrivants
**Tache** : [192](#t1) | **Type** : MDI | **Dimensions** : 562 x 159 DLU
**Bloc** : Traitement | **Titre IDE** : Liste Prestation arrivants

<!-- FORM-DATA:
{
    "width":  562,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  556,
                         "fmt":  "",
                         "name":  "",
                         "h":  19,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  52,
                         "type":  "label",
                         "var":  "",
                         "y":  26,
                         "w":  268,
                         "fmt":  "",
                         "name":  "",
                         "h":  50,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  320,
                         "type":  "label",
                         "var":  "",
                         "y":  26,
                         "w":  186,
                         "fmt":  "",
                         "name":  "",
                         "h":  101,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  103,
                         "type":  "label",
                         "var":  "",
                         "y":  32,
                         "w":  83,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Prestation",
                         "parent":  5
                     },
                     {
                         "x":  52,
                         "type":  "label",
                         "var":  "",
                         "y":  77,
                         "w":  268,
                         "fmt":  "",
                         "name":  "",
                         "h":  50,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  78,
                         "type":  "label",
                         "var":  "",
                         "y":  82,
                         "w":  30,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Du",
                         "parent":  11
                     },
                     {
                         "x":  78,
                         "type":  "label",
                         "var":  "",
                         "y":  94,
                         "w":  29,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Au",
                         "parent":  11
                     },
                     {
                         "x":  78,
                         "type":  "label",
                         "var":  "",
                         "y":  113,
                         "w":  86,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Sélections",
                         "parent":  11
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  134,
                         "w":  556,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  105,
                         "type":  "edit",
                         "var":  "",
                         "y":  44,
                         "w":  82,
                         "fmt":  "",
                         "name":  "w0_CodePrestation",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  193,
                         "type":  "button",
                         "var":  "",
                         "y":  44,
                         "w":  33,
                         "fmt":  "...",
                         "name":  "b_Prestation",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  131,
                         "type":  "edit",
                         "var":  "",
                         "y":  82,
                         "w":  126,
                         "fmt":  "DD/MM/YYYY",
                         "name":  "w0_DateMin",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  11
                     },
                     {
                         "x":  267,
                         "type":  "button",
                         "var":  "",
                         "y":  82,
                         "w":  33,
                         "fmt":  "...",
                         "name":  "b_DateMin",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  11
                     },
                     {
                         "x":  131,
                         "type":  "edit",
                         "var":  "",
                         "y":  94,
                         "w":  126,
                         "fmt":  "DD/MM/YYYY",
                         "name":  "w0_DateMax",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  11
                     },
                     {
                         "x":  267,
                         "type":  "button",
                         "var":  "",
                         "y":  94,
                         "w":  33,
                         "fmt":  "...",
                         "name":  "b_DateMax",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  11
                     },
                     {
                         "x":  198,
                         "type":  "edit",
                         "var":  "",
                         "y":  113,
                         "w":  56,
                         "fmt":  "",
                         "name":  "w0_NbSelect",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  11
                     },
                     {
                         "x":  337,
                         "type":  "button",
                         "var":  "",
                         "y":  86,
                         "w":  154,
                         "fmt":  "\u0026Ecran",
                         "name":  "b_Ecran",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  6
                     },
                     {
                         "x":  337,
                         "type":  "button",
                         "var":  "",
                         "y":  105,
                         "w":  154,
                         "fmt":  "\u0026Impression",
                         "name":  "b_Imprimer",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  6
                     },
                     {
                         "x":  8,
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
                         "x":  340,
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
                         "x":  8,
                         "type":  "edit",
                         "var":  "",
                         "y":  10,
                         "w":  331,
                         "fmt":  "25",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  357,
                         "type":  "image",
                         "var":  "",
                         "y":  29,
                         "w":  128,
                         "fmt":  "",
                         "name":  "",
                         "h":  56,
                         "color":  "",
                         "text":  "",
                         "parent":  6
                     },
                     {
                         "x":  70,
                         "type":  "edit",
                         "var":  "",
                         "y":  63,
                         "w":  242,
                         "fmt":  "20",
                         "name":  "",
                         "h":  9,
                         "color":  "142",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  9,
                         "type":  "button",
                         "var":  "",
                         "y":  137,
                         "w":  154,
                         "fmt":  "\u0026Quitter",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  18
                     }
                 ],
    "taskId":  "192",
    "height":  159
}
-->

<details>
<summary><strong>Champs : 8 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 105,44 | w0_CodePrestation | - | edit |
| 131,82 | w0_DateMin | - | edit |
| 131,94 | w0_DateMax | - | edit |
| 198,113 | w0_NbSelect | - | edit |
| 8,2 | 20 | - | edit |
| 340,6 | WWW DD MMM YYYYT | - | edit |
| 8,10 | 25 | - | edit |
| 70,63 | 20 | - | edit |

</details>

<details>
<summary><strong>Boutons : 6 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| ... | 193,44 | Bouton fonctionnel |
| ... | 267,82 | Bouton fonctionnel |
| ... | 267,94 | Bouton fonctionnel |
| Ecran | 337,86 | Bouton fonctionnel |
| Impression | 337,105 | Bouton fonctionnel |
| Quitter | 9,137 | Quitte le programme |

</details>

## 9. NAVIGATION

Ecran unique: **Liste Prestation arrivants**

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **192.1** | [**Liste Prestation arrivants** (192)](#t1) [mockup](#ecran-t1) | MDI | 562x159 | Traitement |

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

### 11.1 Autres (11)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | w0_TitreEcran | Alpha | 1x refs |
| B | w0_CodePrestation | Alpha | 1x refs |
| C | b_Prestation | Alpha | - |
| D | w0_DateMin | Date | 2x refs |
| E | b_DateMin | Alpha | - |
| F | w0_DateMax | Date | 1x refs |
| G | b_DateMax | Alpha | - |
| H | w0_Total | Numeric | - |
| I | w0_NbSelect | Numeric | 2x refs |
| J | b_Ecran | Alpha | - |
| K | b_Imprimer | Alpha | - |

## 12. EXPRESSIONS

**18 / 18 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONDITION | 4 | 5 |
| CONSTANTE | 7 | 0 |
| DATE | 1 | 0 |
| OTHER | 4 | 0 |
| REFERENCE_VG | 1 | 0 |
| STRING | 1 | 0 |

### 12.2 Expressions cles par type

#### CONDITION (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 13 | `IF (w0_CodePrestation [B]='','Toutes Prestations','Prestation : '&w0_CodePrestation [B])` | [RM-001](#rm-RM-001) |
| CONDITION | 18 | `w0_DateMin [D]>w0_DateMax [F]` | - |
| CONDITION | 16 | `w0_NbSelect [I]=0` | - |
| CONDITION | 15 | `w0_NbSelect [I]>0` | - |

#### CONSTANTE (7 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 9 | `'&Ecran'` | - |
| CONSTANTE | 10 | `'&Imprimer'` | - |
| CONSTANTE | 17 | `0` | - |
| CONSTANTE | 8 | `'...'` | - |
| CONSTANTE | 1 | `147` | - |
| ... | | *+2 autres* | |

#### DATE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| DATE | 4 | `Date ()` | - |

#### OTHER (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 12 | `w0_DateMin [D]` | - |
| OTHER | 14 | `GetParam ('VILLAGE')` | - |
| OTHER | 6 | `SetCrsr (2)` | - |
| OTHER | 7 | `SetCrsr (1)` | - |

#### REFERENCE_VG (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 11 | `VG2` | - |

#### STRING (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| STRING | 3 | `Trim (w0_TitreEcran [A])` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

**Chemin**: (pas de callers directs)

```mermaid
graph LR
    T192[192 Liste Prestation a...]
    style T192 fill:#58a6ff
    NONE[Aucun caller]
    NONE -.-> T192
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| - | (aucun) | - |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T192[192 Liste Prestation a...]
    style T192 fill:#58a6ff
    C290[290 RaZ 589 tempo pres...]
    T192 --> C290
    style C290 fill:#3fb950
    C330[330 Creat 589 634 temp...]
    T192 --> C330
    style C330 fill:#3fb950
    C405[405 Selection prestation]
    T192 --> C405
    style C405 fill:#3fb950
    C185[185 Affiche Prestation]
    T192 --> C185
    style C185 fill:#3fb950
    C186[186 Imprime prestation]
    T192 --> C186
    style C186 fill:#3fb950
    C389[389 Recuperation du titre]
    T192 --> C389
    style C389 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [290](PBP-IDE-290.md) | RaZ 589 tempo prestattion | 2 | Reinitialisation |
| [330](PBP-IDE-330.md) | Creat 589 634 tempo prestation | 2 | Sous-programme |
| [405](PBP-IDE-405.md) | Selection prestation | 2 | Selection/consultation |
| [185](PBP-IDE-185.md) |   Affiche Prestation | 1 | Affichage donnees |
| [186](PBP-IDE-186.md) |   Imprime prestation | 1 | Impression ticket/document |
| [389](PBP-IDE-389.md) | Recuperation du titre | 1 | Recuperation donnees |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 52 | Programme compact |
| Expressions | 18 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 6 | Dependances moderees |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 52) | Code sain |
| Regles metier | 1 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 1 ecran, 0 traitement)

- **Strategie** : 1 composant(s) UI (Razor/React) avec formulaires et validation.
- 6 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| [Selection prestation (IDE 405)](PBP-IDE-405.md) | Sous-programme | 2x | Haute - Selection/consultation |
| [Creat 589 634 tempo prestation (IDE 330)](PBP-IDE-330.md) | Sous-programme | 2x | Haute - Sous-programme |
| [RaZ 589 tempo prestattion (IDE 290)](PBP-IDE-290.md) | Sous-programme | 2x | Haute - Reinitialisation |
| [Recuperation du titre (IDE 389)](PBP-IDE-389.md) | Sous-programme | 1x | Normale - Recuperation donnees |
| [  Imprime prestation (IDE 186)](PBP-IDE-186.md) | Sous-programme | 1x | Normale - Impression ticket/document |
| [  Affiche Prestation (IDE 185)](PBP-IDE-185.md) | Sous-programme | 1x | Normale - Affichage donnees |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 15:44*
