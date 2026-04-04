# PVE IDE 336 - Zoom articles code

> **Analyse**: Phases 1-4 2026-02-03 19:39 -> 19:39 (12s) | Assemblage 19:39
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PVE |
| IDE Position | 336 |
| Nom Programme | Zoom articles code |
| Fichier source | `Prg_336.xml` |
| Dossier IDE | Zoom |
| Taches | 1 (1 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 1 |

## 2. DESCRIPTION FONCTIONNELLE

**Zoom articles code** assure la gestion complete de ce processus, accessible depuis [Etiquette CAB (IDE 102)](PVE-IDE-102.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Consultation** (1 tache) : ecrans de recherche, selection et consultation

**Logique metier** : 1 regles identifiees couvrant conditions metier.

## 3. BLOCS FONCTIONNELS

### 3.1 Consultation (1 tache)

Ecrans de recherche et consultation.

---

#### <a id="t1"></a>336 - Zoom articles [[ECRAN]](#ecran-t1)

**Role** : Selection par l'operateur : Zoom articles.
**Ecran** : 758 x 153 DLU (MDI) | [Voir mockup](#ecran-t1)


## 5. REGLES METIER

1 regles identifiees:

### Autres (1 regles)

#### <a id="rm-RM-001"></a>[RM-001] Si > service village [A]>'' alors > service village [A] sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `> service village [A]>''` |
| **Si vrai** | > service village [A] |
| **Si faux** | '') |
| **Variables** | A (> service village) |
| **Expression source** | Expression 6 : `IF (> service village [A]>'',> service village [A],'')` |
| **Exemple** | Si > service village [A]>'' â†’ > service village [A]. Sinon â†’ '') |

## 6. CONTEXTE

- **Appele par**: [Etiquette CAB (IDE 102)](PVE-IDE-102.md)
- **Appelle**: 1 programmes | **Tables**: 1 (W:0 R:1 L:0) | **Taches**: 1 | **Expressions**: 16

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 1)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 336 | 336 | Zoom articles | MDI | 758 | 153 | Consultation |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>336 - Zoom articles
**Tache** : [336](#t1) | **Type** : MDI | **Dimensions** : 758 x 153 DLU
**Bloc** : Consultation | **Titre IDE** : Zoom articles

<!-- FORM-DATA:
{
    "width":  758,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  132,
                         "w":  755,
                         "fmt":  "",
                         "name":  "",
                         "h":  19,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  21,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "196",
                         "w":  722,
                         "y":  7,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  13,
                         "h":  103,
                         "cols":  [
                                      {
                                          "title":  "Numéro article",
                                          "layer":  1,
                                          "w":  150
                                      },
                                      {
                                          "title":  "Code article",
                                          "layer":  2,
                                          "w":  164
                                      },
                                      {
                                          "title":  "Prix unitaire",
                                          "layer":  3,
                                          "w":  248
                                      },
                                      {
                                          "title":  "Réduction",
                                          "layer":  4,
                                          "w":  128
                                      }
                                  ],
                         "rows":  4
                     },
                     {
                         "x":  28,
                         "type":  "edit",
                         "var":  "",
                         "y":  22,
                         "w":  142,
                         "fmt":  "",
                         "name":  "CTRL_001",
                         "h":  8,
                         "color":  "196",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  181,
                         "type":  "edit",
                         "var":  "",
                         "y":  22,
                         "w":  154,
                         "fmt":  "",
                         "name":  "CTRL_002",
                         "h":  8,
                         "color":  "196",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  339,
                         "type":  "edit",
                         "var":  "",
                         "y":  22,
                         "w":  210,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "196",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  592,
                         "type":  "button",
                         "var":  "",
                         "y":  135,
                         "w":  144,
                         "fmt":  "\u0026Quitter",
                         "name":  "Exit",
                         "h":  14,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  21,
                         "type":  "button",
                         "var":  "",
                         "y":  135,
                         "w":  144,
                         "fmt":  "\u0026Sélectionner",
                         "name":  "Select",
                         "h":  14,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  641,
                         "type":  "checkbox",
                         "var":  "",
                         "y":  21,
                         "w":  22,
                         "fmt":  "",
                         "name":  "art_remise_autorisee",
                         "h":  9,
                         "color":  "196",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  349,
                         "type":  "image",
                         "var":  "",
                         "y":  113,
                         "w":  58,
                         "fmt":  "",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "336",
    "height":  153
}
-->

<details>
<summary><strong>Champs : 4 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 28,22 | CTRL_001 | - | edit |
| 181,22 | CTRL_002 | - | edit |
| 339,22 | (sans nom) | - | edit |
| 641,21 | art_remise_autorisee | - | checkbox |

</details>

<details>
<summary><strong>Boutons : 2 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Quitter | 592,135 | Quitte le programme |
| Sélectionner | 21,135 | Bouton fonctionnel |

</details>

## 9. NAVIGATION

Ecran unique: **Zoom articles**

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **336.1** | [**Zoom articles** (336)](#t1) [mockup](#ecran-t1) | MDI | 758x153 | Consultation |

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
| 77 | articles_________art | Articles et stock | DB | R |   |   | 1 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 77 - articles_________art (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | > service village | R | Alpha |
| B | > code article | R | Numeric |
| C | < libellé article | R | Alpha |
| D | < imputation | R | Numeric |
| E | < sous imputation | R | Numeric |
| F | < prix unitaire | R | Numeric |
| G | < masque montant | R | Alpha |
| H | < numero article | R | Numeric |
| I | v. passage | R | Logical |
| J | W1 fin tâche | R | Alpha |
| K | v. titre ecran | R | Alpha |
| L | bouton quitter | R | Alpha |
| M | bouton selectionner | R | Alpha |

</details>

## 11. VARIABLES

### 11.1 Variables de session (2)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| I | v. passage | Logical | 1x session |
| K | v. titre ecran | Alpha | 1x session |

### 11.2 Autres (11)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | > service village | Alpha | 2x refs |
| B | > code article | Numeric | [336](#t1) |
| C | < libellé article | Alpha | - |
| D | < imputation | Numeric | - |
| E | < sous imputation | Numeric | - |
| F | < prix unitaire | Numeric | - |
| G | < masque montant | Alpha | - |
| H | < numero article | Numeric | - |
| J | W1 fin tâche | Alpha | 1x refs |
| L | bouton quitter | Alpha | 1x refs |
| M | bouton selectionner | Alpha | 1x refs |

## 12. EXPRESSIONS

**16 / 16 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONDITION | 3 | 5 |
| CONSTANTE | 4 | 0 |
| CAST_LOGIQUE | 1 | 0 |
| OTHER | 6 | 0 |
| NEGATION | 1 | 0 |
| STRING | 1 | 0 |

### 12.2 Expressions cles par type

#### CONDITION (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 6 | `IF (> service village [A]>'',> service village [A],'')` | [RM-001](#rm-RM-001) |
| CONDITION | 8 | `> code article [B]` | - |
| CONDITION | 7 | `> service village [A]` | - |

#### CONSTANTE (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 5 | `'&Sélectionner'` | - |
| CONSTANTE | 15 | `' '` | - |
| CONSTANTE | 3 | `'&Quitter'` | - |
| CONSTANTE | 4 | `41` | - |

#### CAST_LOGIQUE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 1 | `'TRUE'LOG` | - |

#### OTHER (6 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 12 | `bouton selectionner [M]` | - |
| OTHER | 13 | `[N]` | - |
| OTHER | 14 | `[O]` | - |
| OTHER | 9 | `W1 fin tâche [J]` | - |
| OTHER | 10 | `bouton quitter [L]` | - |
| ... | | *+1 autres* | |

#### NEGATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| NEGATION | 16 | `NOT (v. passage [I])` | - |

#### STRING (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| STRING | 2 | `Trim ([T])` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Etiquette CAB (IDE 102)](PVE-IDE-102.md) -> **Zoom articles code (IDE 336)**

```mermaid
graph LR
    T336[336 Zoom articles code]
    style T336 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC143[143 START]
    style CC143 fill:#f59e0b
    CC420[420 Menu==V4___]
    style CC420 fill:#f59e0b
    CC439[439 Menu]
    style CC439 fill:#f59e0b
    CC185[185 Menu]
    style CC185 fill:#f59e0b
    CC353[353 Menu==V4]
    style CC353 fill:#f59e0b
    CC178[178 Menu Administration]
    style CC178 fill:#f59e0b
    CC102[102 Etiquette CAB]
    style CC102 fill:#3fb950
    CC178 --> CC102
    CC185 --> CC178
    CC353 --> CC178
    CC420 --> CC178
    CC439 --> CC178
    CC143 --> CC185
    CC143 --> CC353
    CC143 --> CC420
    CC143 --> CC439
    CC1 --> CC143
    CC102 --> T336
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [102](PVE-IDE-102.md) | Etiquette CAB | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T336[336 Zoom articles code]
    style T336 fill:#58a6ff
    C118[118 Recuperation du titre]
    T336 --> C118
    style C118 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [118](PVE-IDE-118.md) | Recuperation du titre | 1 | Recuperation donnees |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 40 | Programme compact |
| Expressions | 16 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 1 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 40) | Code sain |
| Regles metier | 1 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Consultation (1 tache: 1 ecran, 0 traitement)

- **Strategie** : Composants de recherche/selection en modales.
- 1 ecran : Zoom articles

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| [Recuperation du titre (IDE 118)](PVE-IDE-118.md) | Sous-programme | 1x | Normale - Recuperation donnees |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 19:39*
