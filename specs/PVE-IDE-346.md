# PVE IDE 346 - Choix - Age level

> **Analyse**: Phases 1-4 2026-02-03 19:42 -> 19:42 (11s) | Assemblage 19:42
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PVE |
| IDE Position | 346 |
| Nom Programme | Choix - Age level |
| Fichier source | `Prg_346.xml` |
| Dossier IDE | Sauvegarde |
| Taches | 1 (1 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Choix - Age level** assure la gestion complete de ce processus, accessible depuis [Skier Profile (IDE 212)](PVE-IDE-212.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>346 - Age level [[ECRAN]](#ecran-t1)

**Role** : Traitement : Age level.
**Ecran** : 362 x 310 DLU (MDI) | [Voir mockup](#ecran-t1)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Skier Profile (IDE 212)](PVE-IDE-212.md)
- **Appelle**: 0 programmes | **Tables**: 1 (W:0 R:1 L:0) | **Taches**: 1 | **Expressions**: 3

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 1)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 346 | 346 | Age level | MDI | 362 | 310 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>346 - Age level
**Tache** : [346](#t1) | **Type** : MDI | **Dimensions** : 362 x 310 DLU
**Bloc** : Traitement | **Titre IDE** : Age level

<!-- FORM-DATA:
{
    "width":  362,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  44,
                         "type":  "label",
                         "var":  "",
                         "y":  47,
                         "w":  208,
                         "fmt":  "",
                         "name":  "",
                         "h":  13,
                         "color":  "183",
                         "text":  "Range",
                         "parent":  null
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  360,
                         "fmt":  "",
                         "name":  "",
                         "h":  42,
                         "color":  "182",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  14,
                         "type":  "label",
                         "var":  "",
                         "y":  15,
                         "w":  259,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "186",
                         "text":  "Select age level",
                         "parent":  2
                     },
                     {
                         "x":  30,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "110",
                         "w":  260,
                         "y":  62,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  33,
                         "h":  201,
                         "cols":  [
                                      {
                                          "title":  "",
                                          "layer":  1,
                                          "w":  256
                                      }
                                  ],
                         "rows":  1
                     },
                     {
                         "x":  1,
                         "type":  "label",
                         "var":  "",
                         "y":  274,
                         "w":  360,
                         "fmt":  "",
                         "name":  "",
                         "h":  34,
                         "color":  "6",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  310,
                         "type":  "image",
                         "var":  "",
                         "y":  4,
                         "w":  48,
                         "fmt":  "",
                         "name":  "",
                         "h":  37,
                         "color":  "",
                         "text":  "",
                         "parent":  2
                     },
                     {
                         "x":  284,
                         "type":  "button",
                         "var":  "",
                         "y":  279,
                         "w":  77,
                         "fmt":  "\u0026Exit",
                         "name":  "",
                         "h":  28,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  33,
                         "type":  "button",
                         "var":  "",
                         "y":  62,
                         "w":  256,
                         "fmt":  "128",
                         "name":  "pvg_label",
                         "h":  32,
                         "color":  "",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  289,
                         "type":  "button",
                         "var":  "",
                         "y":  63,
                         "w":  44,
                         "fmt":  "ñ",
                         "name":  "",
                         "h":  94,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  289,
                         "type":  "button",
                         "var":  "",
                         "y":  157,
                         "w":  44,
                         "fmt":  "ò",
                         "name":  "",
                         "h":  107,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "346",
    "height":  310
}
-->

<details>
<summary><strong>Boutons : 4 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Exit | 284,279 | Quitte le programme |
| 128 | 33,62 | Bouton fonctionnel |
| ñ | 289,63 | Bouton fonctionnel |
| ò | 289,157 | Bouton fonctionnel |

</details>

## 9. NAVIGATION

Ecran unique: **Age level**

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **346.1** | [**Age level** (346)](#t1) [mockup](#ecran-t1) | MDI | 362x310 | Traitement |

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

### Tables utilisees (1)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 1621 | Table_1621 |  | MEM | R |   |   | 1 |

### Colonnes par table (0 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 1621 - Table_1621 (R) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

*(Programme sans variables locales mappees)*

## 12. EXPRESSIONS

**3 / 3 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| OTHER | 3 | 0 |

### 12.2 Expressions cles par type

#### OTHER (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 3 | `GetParam('SERVICE')` | - |
| OTHER | 2 | `[C]` | - |
| OTHER | 1 | `P.i.o.Niveau age [A]` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Skier Profile (IDE 212)](PVE-IDE-212.md) -> **Choix - Age level (IDE 346)**

```mermaid
graph LR
    T346[346 Choix - Age level]
    style T346 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC143[143 START]
    style CC143 fill:#f59e0b
    CC185[185 Menu]
    style CC185 fill:#f59e0b
    CC187[187 Main Sale-664]
    style CC187 fill:#f59e0b
    CC364[364 Main Sale-664]
    style CC364 fill:#f59e0b
    CC212[212 Skier Profile]
    style CC212 fill:#3fb950
    CC187 --> CC212
    CC364 --> CC212
    CC185 --> CC187
    CC185 --> CC364
    CC143 --> CC185
    CC1 --> CC143
    CC212 --> T346
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [212](PVE-IDE-212.md) | Skier Profile | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T346[346 Choix - Age level]
    style T346 fill:#58a6ff
    NONE[Aucun callee]
    T346 -.-> NONE
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
| Lignes de logique | 7 | Programme compact |
| Expressions | 3 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 7) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 1 ecran, 0 traitement)

- **Strategie** : 1 composant(s) UI (Razor/React) avec formulaires et validation.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 19:42*
