# PBG IDE 362 - Zoom Affichage Lieu de Sejour

> **Analyse**: Phases 1-4 2026-02-03 11:25 -> 11:25 (17s) | Assemblage 11:25
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBG |
| IDE Position | 362 |
| Nom Programme | Zoom Affichage Lieu de Sejour |
| Fichier source | `Prg_362.xml` |
| Dossier IDE | Consultation |
| Taches | 1 (1 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Zoom Affichage Lieu de Sejour** assure la gestion complete de ce processus, accessible depuis [   Recodification Client (IDE 77)](PBG-IDE-77.md), [   Avancement Client (IDE 78)](PBG-IDE-78.md), [   Prolongation Client (IDE 83)](PBG-IDE-83.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Consultation** (1 tache) : ecrans de recherche, selection et consultation

**Logique metier** : 1 regles identifiees couvrant conditions metier.

## 3. BLOCS FONCTIONNELS

### 3.1 Consultation (1 tache)

Ecrans de recherche et consultation.

---

#### <a id="t1"></a>362 - Affichage Lieu de Sejour [[ECRAN]](#ecran-t1)

**Role** : Reinitialisation : Affichage Lieu de Sejour.
**Ecran** : 426 x 139 DLU (MDI) | [Voir mockup](#ecran-t1)
**Variables liees** : C (< Lieu sejour)


## 5. REGLES METIER

1 regles identifiees:

### Autres (1 regles)

#### <a id="rm-RM-001"></a>[RM-001] Si < Lieu sejour [C]<>'' alors 'O' sinon 'N')

| Element | Detail |
|---------|--------|
| **Condition** | `< Lieu sejour [C]<>''` |
| **Si vrai** | 'O' |
| **Si faux** | 'N') |
| **Variables** | C (< Lieu sejour) |
| **Expression source** | Expression 5 : `IF (< Lieu sejour [C]<>'','O','N')` |
| **Exemple** | Si < Lieu sejour [C]<>'' â†’ 'O'. Sinon â†’ 'N') |

## 6. CONTEXTE

- **Appele par**: [   Recodification Client (IDE 77)](PBG-IDE-77.md), [   Avancement Client (IDE 78)](PBG-IDE-78.md), [   Prolongation Client (IDE 83)](PBG-IDE-83.md)
- **Appelle**: 0 programmes | **Tables**: 1 (W:0 R:1 L:0) | **Taches**: 1 | **Expressions**: 6

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 1)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 362 | 362 | Affichage Lieu de Sejour | MDI | 426 | 139 | Consultation |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>362 - Affichage Lieu de Sejour
**Tache** : [362](#t1) | **Type** : MDI | **Dimensions** : 426 x 139 DLU
**Bloc** : Consultation | **Titre IDE** : Affichage Lieu de Sejour

<!-- FORM-DATA:
{
    "width":  426,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  76,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "196",
                         "w":  280,
                         "y":  3,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  12,
                         "h":  80,
                         "cols":  [
                                      {
                                          "title":  "Nom",
                                          "layer":  1,
                                          "w":  244
                                      }
                                  ],
                         "rows":  1
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  113,
                         "w":  423,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  85,
                         "type":  "edit",
                         "var":  "",
                         "y":  18,
                         "w":  232,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "196",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  7,
                         "type":  "button",
                         "var":  "",
                         "y":  117,
                         "w":  154,
                         "fmt":  "\u0026Selectionner",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  262,
                         "type":  "button",
                         "var":  "",
                         "y":  117,
                         "w":  154,
                         "fmt":  "\u0026Quitter",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  182,
                         "type":  "image",
                         "var":  "",
                         "y":  89,
                         "w":  58,
                         "fmt":  "",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "362",
    "height":  139
}
-->

<details>
<summary><strong>Champs : 1 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 85,18 | (sans nom) | - | edit |

</details>

<details>
<summary><strong>Boutons : 2 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Selectionner | 7,117 | Ouvre la selection |
| Quitter | 262,117 | Quitte le programme |

</details>

## 9. NAVIGATION

Ecran unique: **Affichage Lieu de Sejour**

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **362.1** | [**Affichage Lieu de Sejour** (362)](#t1) [mockup](#ecran-t1) | MDI | 426x139 | Consultation |

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
| 118 | tables_imports |  | DB | R |   |   | 1 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 118 - tables_imports (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | > Societe | R | Alpha |
| B | < Accord suite | R | Alpha |
| C | < Lieu sejour | R | Alpha |

</details>

## 11. VARIABLES

### 11.1 Autres (3)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | > Societe | Alpha | 1x refs |
| B | < Accord suite | Alpha | - |
| C | < Lieu sejour | Alpha | [362](#t1) |

## 12. EXPRESSIONS

**6 / 6 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONDITION | 4 | 5 |
| CONSTANTE | 1 | 0 |
| OTHER | 1 | 0 |

### 12.2 Expressions cles par type

#### CONDITION (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 5 | `IF (< Lieu sejour [C]<>'','O','N')` | [RM-001](#rm-RM-001) |
| CONDITION | 6 | `< Lieu sejour [C]` | - |
| CONDITION | 3 | `> Societe [A]` | - |
| CONDITION | 1 | `[E]<>'N' AND [E]<>'G'` | - |

#### CONSTANTE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 2 | `'N'` | - |

#### OTHER (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 4 | `[E]` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [   Recodification Client (IDE 77)](PBG-IDE-77.md) -> **Zoom Affichage Lieu de Sejour (IDE 362)**

Main -> ... -> [   Avancement Client (IDE 78)](PBG-IDE-78.md) -> **Zoom Affichage Lieu de Sejour (IDE 362)**

Main -> ... -> [   Prolongation Client (IDE 83)](PBG-IDE-83.md) -> **Zoom Affichage Lieu de Sejour (IDE 362)**

```mermaid
graph LR
    T362[362 Zoom Affichage Lie...]
    style T362 fill:#58a6ff
    CC94[94 Module Sejours Call...]
    style CC94 fill:#8b5cf6
    CC391[391 Module Sejours Sub...]
    style CC391 fill:#8b5cf6
    CC77[77 Recodification Client]
    style CC77 fill:#3fb950
    CC78[78 Avancement Client]
    style CC78 fill:#3fb950
    CC83[83 Prolongation Client]
    style CC83 fill:#3fb950
    CC94 --> CC77
    CC391 --> CC77
    CC94 --> CC78
    CC391 --> CC78
    CC94 --> CC83
    CC391 --> CC83
    CC77 --> T362
    CC78 --> T362
    CC83 --> T362
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [77](PBG-IDE-77.md) |    Recodification Client | 1 |
| [78](PBG-IDE-78.md) |    Avancement Client | 1 |
| [83](PBG-IDE-83.md) |    Prolongation Client | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T362[362 Zoom Affichage Lie...]
    style T362 fill:#58a6ff
    NONE[Aucun callee]
    T362 -.-> NONE
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
| Lignes de logique | 16 | Programme compact |
| Expressions | 6 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 16) | Code sain |
| Regles metier | 1 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Consultation (1 tache: 1 ecran, 0 traitement)

- **Strategie** : Composants de recherche/selection en modales.
- 1 ecran : Affichage Lieu de Sejour

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 11:25*
