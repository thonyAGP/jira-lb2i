# PBP IDE 284 - RaZ Tempo synthese

> **Analyse**: Phases 1-4 2026-02-03 16:10 -> 16:11 (15s) | Assemblage 16:11
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBP |
| IDE Position | 284 |
| Nom Programme | RaZ Tempo synthese |
| Fichier source | `Prg_284.xml` |
| Dossier IDE | RAZ |
| Taches | 1 (1 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**RaZ Tempo synthese** assure la gestion complete de ce processus, accessible depuis [Liste des arrivants (IDE 155)](PBP-IDE-155.md), [  Prep tempo arrivant planning (IDE 157)](PBP-IDE-157.md), [Liste des arrivees (IDE 160)](PBP-IDE-160.md), [Liste des presents (IDE 161)](PBP-IDE-161.md), [  Prep tempo present planning (IDE 163)](PBP-IDE-163.md), [Liste des departs (IDE 167)](PBP-IDE-167.md), [  Prep tempo depart comptage (IDE 169)](PBP-IDE-169.md), [Liste des partants (IDE 172)](PBP-IDE-172.md), [Liste des Absents (IDE 173)](PBP-IDE-173.md), [Liste des arrivants personnel (IDE 224)](PBP-IDE-224.md), [Liste des arrivees personnel (IDE 225)](PBP-IDE-225.md), [Liste des presents personnel (IDE 226)](PBP-IDE-226.md), [  Creation tempo pres plan GO (IDE 228)](PBP-IDE-228.md), [Liste des Absents personnel (IDE 231)](PBP-IDE-231.md), [Liste des departs personnel (IDE 232)](PBP-IDE-232.md), [Liste des partants personnel (IDE 233)](PBP-IDE-233.md), [Prep tempo present planning CL (IDE 249)](PBP-IDE-249.md), [Creation synthese GM (IDE 325)](PBP-IDE-325.md), [Creation synthese present reel (IDE 326)](PBP-IDE-326.md), [Prepa tempo toutes GM CP SQL (IDE 327)](PBP-IDE-327.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>284 - Veuillez patienter [[ECRAN]](#ecran-t1)

**Role** : Traitement : Veuillez patienter.
**Ecran** : 424 x 56 DLU (MDI) | [Voir mockup](#ecran-t1)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Liste des arrivants (IDE 155)](PBP-IDE-155.md), [  Prep tempo arrivant planning (IDE 157)](PBP-IDE-157.md), [Liste des arrivees (IDE 160)](PBP-IDE-160.md), [Liste des presents (IDE 161)](PBP-IDE-161.md), [  Prep tempo present planning (IDE 163)](PBP-IDE-163.md), [Liste des departs (IDE 167)](PBP-IDE-167.md), [  Prep tempo depart comptage (IDE 169)](PBP-IDE-169.md), [Liste des partants (IDE 172)](PBP-IDE-172.md), [Liste des Absents (IDE 173)](PBP-IDE-173.md), [Liste des arrivants personnel (IDE 224)](PBP-IDE-224.md), [Liste des arrivees personnel (IDE 225)](PBP-IDE-225.md), [Liste des presents personnel (IDE 226)](PBP-IDE-226.md), [  Creation tempo pres plan GO (IDE 228)](PBP-IDE-228.md), [Liste des Absents personnel (IDE 231)](PBP-IDE-231.md), [Liste des departs personnel (IDE 232)](PBP-IDE-232.md), [Liste des partants personnel (IDE 233)](PBP-IDE-233.md), [Prep tempo present planning CL (IDE 249)](PBP-IDE-249.md), [Creation synthese GM (IDE 325)](PBP-IDE-325.md), [Creation synthese present reel (IDE 326)](PBP-IDE-326.md), [Prepa tempo toutes GM CP SQL (IDE 327)](PBP-IDE-327.md)
- **Appelle**: 0 programmes | **Tables**: 0 (W:0 R:0 L:0) | **Taches**: 1 | **Expressions**: 1

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 1)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 284 | 284 | Veuillez patienter | MDI | 424 | 56 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>284 - Veuillez patienter
**Tache** : [284](#t1) | **Type** : MDI | **Dimensions** : 424 x 56 DLU
**Bloc** : Traitement | **Titre IDE** : Veuillez patienter

<!-- FORM-DATA:
{
    "width":  424,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  423,
                         "fmt":  "",
                         "name":  "",
                         "h":  29,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  120,
                         "type":  "label",
                         "var":  "",
                         "y":  10,
                         "w":  221,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "7",
                         "text":  "Traitement en cours ...",
                         "parent":  null
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  29,
                         "w":  423,
                         "fmt":  "",
                         "name":  "",
                         "h":  27,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  72,
                         "type":  "label",
                         "var":  "",
                         "y":  38,
                         "w":  267,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Preparation table temporaire",
                         "parent":  null
                     },
                     {
                         "x":  4,
                         "type":  "image",
                         "var":  "",
                         "y":  2,
                         "w":  72,
                         "fmt":  "",
                         "name":  "",
                         "h":  25,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "284",
    "height":  56
}
-->

## 9. NAVIGATION

Ecran unique: **Veuillez patienter**

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **284.1** | [**Veuillez patienter** (284)](#t1) [mockup](#ecran-t1) | MDI | 424x56 | Traitement |

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

*(Programme sans variables locales mappees)*

## 12. EXPRESSIONS

**1 / 1 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| OTHER | 1 | 0 |

### 12.2 Expressions cles par type

#### OTHER (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 1 | `DbDel('{634,2}'DSOURCE,'')` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Liste des arrivants (IDE 155)](PBP-IDE-155.md) -> **RaZ Tempo synthese (IDE 284)**

Main -> ... -> [  Prep tempo arrivant planning (IDE 157)](PBP-IDE-157.md) -> **RaZ Tempo synthese (IDE 284)**

Main -> ... -> [Liste des arrivees (IDE 160)](PBP-IDE-160.md) -> **RaZ Tempo synthese (IDE 284)**

Main -> ... -> [Liste des presents (IDE 161)](PBP-IDE-161.md) -> **RaZ Tempo synthese (IDE 284)**

Main -> ... -> [  Prep tempo present planning (IDE 163)](PBP-IDE-163.md) -> **RaZ Tempo synthese (IDE 284)**

Main -> ... -> [Liste des departs (IDE 167)](PBP-IDE-167.md) -> **RaZ Tempo synthese (IDE 284)**

Main -> ... -> [  Prep tempo depart comptage (IDE 169)](PBP-IDE-169.md) -> **RaZ Tempo synthese (IDE 284)**

Main -> ... -> [Liste des partants (IDE 172)](PBP-IDE-172.md) -> **RaZ Tempo synthese (IDE 284)**

Main -> ... -> [Liste des Absents (IDE 173)](PBP-IDE-173.md) -> **RaZ Tempo synthese (IDE 284)**

Main -> ... -> [Liste des arrivants personnel (IDE 224)](PBP-IDE-224.md) -> **RaZ Tempo synthese (IDE 284)**

Main -> ... -> [Liste des arrivees personnel (IDE 225)](PBP-IDE-225.md) -> **RaZ Tempo synthese (IDE 284)**

Main -> ... -> [Liste des presents personnel (IDE 226)](PBP-IDE-226.md) -> **RaZ Tempo synthese (IDE 284)**

Main -> ... -> [  Creation tempo pres plan GO (IDE 228)](PBP-IDE-228.md) -> **RaZ Tempo synthese (IDE 284)**

Main -> ... -> [Liste des Absents personnel (IDE 231)](PBP-IDE-231.md) -> **RaZ Tempo synthese (IDE 284)**

Main -> ... -> [Liste des departs personnel (IDE 232)](PBP-IDE-232.md) -> **RaZ Tempo synthese (IDE 284)**

Main -> ... -> [Liste des partants personnel (IDE 233)](PBP-IDE-233.md) -> **RaZ Tempo synthese (IDE 284)**

Main -> ... -> [Prep tempo present planning CL (IDE 249)](PBP-IDE-249.md) -> **RaZ Tempo synthese (IDE 284)**

Main -> ... -> [Creation synthese GM (IDE 325)](PBP-IDE-325.md) -> **RaZ Tempo synthese (IDE 284)**

Main -> ... -> [Creation synthese present reel (IDE 326)](PBP-IDE-326.md) -> **RaZ Tempo synthese (IDE 284)**

Main -> ... -> [Prepa tempo toutes GM CP SQL (IDE 327)](PBP-IDE-327.md) -> **RaZ Tempo synthese (IDE 284)**

```mermaid
graph LR
    T284[284 RaZ Tempo synthese]
    style T284 fill:#58a6ff
    CC148[148 Liste Gestion de C...]
    style CC148 fill:#8b5cf6
    CC152[152 Start]
    style CC152 fill:#8b5cf6
    CC156[156 Liste CLients arri...]
    style CC156 fill:#f59e0b
    CC146[146 Pilotage Gestion d...]
    style CC146 fill:#f59e0b
    CC162[162 Liste Clients present]
    style CC162 fill:#f59e0b
    CC155[155 Liste des arrivants]
    style CC155 fill:#3fb950
    CC160[160 Liste des arrivees]
    style CC160 fill:#3fb950
    CC157[157 Prep tempo arrivan...]
    style CC157 fill:#3fb950
    CC163[163 Prep tempo present...]
    style CC163 fill:#3fb950
    CC161[161 Liste des presents]
    style CC161 fill:#3fb950
    CC146 --> CC155
    CC156 --> CC155
    CC162 --> CC155
    CC146 --> CC157
    CC156 --> CC157
    CC162 --> CC157
    CC146 --> CC160
    CC156 --> CC160
    CC162 --> CC160
    CC146 --> CC161
    CC156 --> CC161
    CC162 --> CC161
    CC146 --> CC163
    CC156 --> CC163
    CC162 --> CC163
    CC148 --> CC146
    CC152 --> CC146
    CC148 --> CC156
    CC152 --> CC156
    CC148 --> CC162
    CC152 --> CC162
    CC155 --> T284
    CC157 --> T284
    CC160 --> T284
    CC161 --> T284
    CC163 --> T284
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [155](PBP-IDE-155.md) | Liste des arrivants | 1 |
| [157](PBP-IDE-157.md) |   Prep tempo arrivant planning | 1 |
| [160](PBP-IDE-160.md) | Liste des arrivees | 1 |
| [161](PBP-IDE-161.md) | Liste des presents | 1 |
| [163](PBP-IDE-163.md) |   Prep tempo present planning | 1 |
| [167](PBP-IDE-167.md) | Liste des departs | 1 |
| [169](PBP-IDE-169.md) |   Prep tempo depart comptage | 1 |
| [172](PBP-IDE-172.md) | Liste des partants | 1 |
| [173](PBP-IDE-173.md) | Liste des Absents | 1 |
| [224](PBP-IDE-224.md) | Liste des arrivants personnel | 1 |
| [225](PBP-IDE-225.md) | Liste des arrivees personnel | 1 |
| [226](PBP-IDE-226.md) | Liste des presents personnel | 1 |
| [228](PBP-IDE-228.md) |   Creation tempo pres plan GO | 1 |
| [231](PBP-IDE-231.md) | Liste des Absents personnel | 1 |
| [232](PBP-IDE-232.md) | Liste des departs personnel | 1 |
| [233](PBP-IDE-233.md) | Liste des partants personnel | 1 |
| [249](PBP-IDE-249.md) | Prep tempo present planning CL | 1 |
| [325](PBP-IDE-325.md) | Creation synthese GM | 1 |
| [326](PBP-IDE-326.md) | Creation synthese present reel | 1 |
| [327](PBP-IDE-327.md) | Prepa tempo toutes GM CP SQL | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T284[284 RaZ Tempo synthese]
    style T284 fill:#58a6ff
    NONE[Aucun callee]
    T284 -.-> NONE
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
| Lignes de logique | 2 | Programme compact |
| Expressions | 1 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 2) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 1 ecran, 0 traitement)

- **Strategie** : 1 composant(s) UI (Razor/React) avec formulaires et validation.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 16:11*
