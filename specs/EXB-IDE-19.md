# EXB IDE 19 - Menu editions

> **Analyse**: Phases 1-4 2026-02-03 10:37 -> 10:37 (18s) | Assemblage 10:37
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | EXB |
| IDE Position | 19 |
| Nom Programme | Menu editions |
| Fichier source | `Prg_19.xml` |
| Domaine metier | Navigation |
| Taches | 1 (1 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 6 |

## 2. DESCRIPTION FONCTIONNELLE

**Menu editions** assure la gestion complete de ce processus, accessible depuis [Menu general (IDE 31)](EXB-IDE-31.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Impression** (1 tache) : generation de tickets et documents

## 3. BLOCS FONCTIONNELS

### 3.1 Impression (1 tache)

Generation des documents et tickets.

---

#### <a id="t1"></a>19 - Menu editions [[ECRAN]](#ecran-t1)

**Role** : Generation du document : Menu editions.
**Ecran** : 702 x 201 DLU (MDI) | [Voir mockup](#ecran-t1)
**Delegue a** : [Edition des excursions (IDE 22)](EXB-IDE-22.md)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Menu general (IDE 31)](EXB-IDE-31.md)
- **Appelle**: 6 programmes | **Tables**: 0 (W:0 R:0 L:0) | **Taches**: 1 | **Expressions**: 8

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 1)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 19 | 19 | Menu editions | MDI | 702 | 201 | Impression |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>19 - Menu editions
**Tache** : [19](#t1) | **Type** : MDI | **Dimensions** : 702 x 201 DLU
**Bloc** : Impression | **Titre IDE** : Menu editions

<!-- FORM-DATA:
{
    "width":  702,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  1,
                         "w":  695,
                         "fmt":  "",
                         "name":  "",
                         "h":  17,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  239,
                         "type":  "label",
                         "var":  "",
                         "y":  23,
                         "w":  438,
                         "fmt":  "",
                         "name":  "",
                         "h":  147,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  266,
                         "type":  "label",
                         "var":  "",
                         "y":  35,
                         "w":  388,
                         "fmt":  "",
                         "name":  "",
                         "h":  105,
                         "color":  "155",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  268,
                         "type":  "label",
                         "var":  "",
                         "y":  36,
                         "w":  44,
                         "fmt":  "",
                         "name":  "",
                         "h":  103,
                         "color":  "",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  338,
                         "type":  "label",
                         "var":  "",
                         "y":  48,
                         "w":  264,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "142",
                         "text":  "Edition des Ventes",
                         "parent":  5
                     },
                     {
                         "x":  338,
                         "type":  "label",
                         "var":  "",
                         "y":  65,
                         "w":  245,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "142",
                         "text":  "Edition des Excursions",
                         "parent":  5
                     },
                     {
                         "x":  338,
                         "type":  "label",
                         "var":  "",
                         "y":  82,
                         "w":  301,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "142",
                         "text":  "Recapitulatif des Ventes saison",
                         "parent":  5
                     },
                     {
                         "x":  338,
                         "type":  "label",
                         "var":  "",
                         "y":  99,
                         "w":  210,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "142",
                         "text":  "Liste des Participants",
                         "parent":  5
                     },
                     {
                         "x":  338,
                         "type":  "label",
                         "var":  "",
                         "y":  116,
                         "w":  221,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "142",
                         "text":  "Detail Excursion",
                         "parent":  5
                     },
                     {
                         "x":  354,
                         "type":  "label",
                         "var":  "",
                         "y":  149,
                         "w":  120,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "Votre choix",
                         "parent":  4
                     },
                     {
                         "x":  2,
                         "type":  "label",
                         "var":  "",
                         "y":  176,
                         "w":  692,
                         "fmt":  "",
                         "name":  "",
                         "h":  21,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  490,
                         "type":  "edit",
                         "var":  "",
                         "y":  149,
                         "w":  26,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  3,
                         "type":  "edit",
                         "var":  "",
                         "y":  5,
                         "w":  267,
                         "fmt":  "20",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  485,
                         "type":  "edit",
                         "var":  "",
                         "y":  5,
                         "w":  203,
                         "fmt":  "WWW DD MMM YYYYT",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  11,
                         "type":  "image",
                         "var":  "",
                         "y":  62,
                         "w":  200,
                         "fmt":  "",
                         "name":  "",
                         "h":  79,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  278,
                         "type":  "button",
                         "var":  "",
                         "y":  48,
                         "w":  24,
                         "fmt":  "A",
                         "name":  "A",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  278,
                         "type":  "button",
                         "var":  "",
                         "y":  65,
                         "w":  24,
                         "fmt":  "B",
                         "name":  "B",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  278,
                         "type":  "button",
                         "var":  "",
                         "y":  82,
                         "w":  24,
                         "fmt":  "C",
                         "name":  "C",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  278,
                         "type":  "button",
                         "var":  "",
                         "y":  99,
                         "w":  24,
                         "fmt":  "E",
                         "name":  "E",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  278,
                         "type":  "button",
                         "var":  "",
                         "y":  116,
                         "w":  24,
                         "fmt":  "F",
                         "name":  "F",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  6,
                         "type":  "button",
                         "var":  "",
                         "y":  178,
                         "w":  154,
                         "fmt":  "\u0026Quitter",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  15
                     }
                 ],
    "taskId":  "19",
    "height":  201
}
-->

<details>
<summary><strong>Champs : 3 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 490,149 | (sans nom) | - | edit |
| 3,5 | 20 | - | edit |
| 485,5 | WWW DD MMM YYYYT | - | edit |

</details>

<details>
<summary><strong>Boutons : 6 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| A | 278,48 | Bouton fonctionnel |
| B | 278,65 | Bouton fonctionnel |
| C | 278,82 | Bouton fonctionnel |
| E | 278,99 | Bouton fonctionnel |
| F | 278,116 | Bouton fonctionnel |
| Quitter | 6,178 | Quitte le programme |

</details>

## 9. NAVIGATION

Ecran unique: **Menu editions**

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **19.1** | [**Menu editions** (19)](#t1) [mockup](#ecran-t1) | MDI | 702x201 | Impression |

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

### 11.1 Parametres entrants (3)

Variables recues du programme appelant ([Menu general (IDE 31)](EXB-IDE-31.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P0 masque montant | Alpha | - |
| B | P0 date comptable | Date | - |
| C | P0 nom village | Alpha | - |

### 11.2 Variables de travail (1)

Variables internes au programme.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| D | W0 choix action | Alpha | 5x calcul interne |

## 12. EXPRESSIONS

**8 / 8 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONSTANTE | 1 | 0 |
| DATE | 1 | 0 |
| CONDITION | 5 | 0 |
| REFERENCE_VG | 1 | 0 |

### 12.2 Expressions cles par type

#### CONSTANTE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 1 | `''` | - |

#### DATE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| DATE | 8 | `Date ()` | - |

#### CONDITION (5 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 5 | `W0 choix action [D]='E'` | - |
| CONDITION | 6 | `W0 choix action [D]='F'` | - |
| CONDITION | 4 | `W0 choix action [D]='C'` | - |
| CONDITION | 2 | `W0 choix action [D]='A'` | - |
| CONDITION | 3 | `W0 choix action [D]='B'` | - |

#### REFERENCE_VG (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 7 | `VG2` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Menu general (IDE 31)](EXB-IDE-31.md) -> **Menu editions (IDE 19)**

```mermaid
graph LR
    T19[19 Menu editions]
    style T19 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC31[31 Menu general]
    style CC31 fill:#3fb950
    CC1 --> CC31
    CC31 --> T19
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [31](EXB-IDE-31.md) | Menu general | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T19[19 Menu editions]
    style T19 fill:#58a6ff
    C17[17 Appel programme]
    T19 --> C17
    style C17 fill:#3fb950
    C20[20 Liste ventesN°vente]
    T19 --> C20
    style C20 fill:#3fb950
    C22[22 Edition des excursions]
    T19 --> C22
    style C22 fill:#3fb950
    C23[23 Liste Participant]
    T19 --> C23
    style C23 fill:#3fb950
    C25[25 Ventes saison]
    T19 --> C25
    style C25 fill:#3fb950
    C26[26 Detail Excursion]
    T19 --> C26
    style C26 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [17](EXB-IDE-17.md) | Appel programme | 1 | Sous-programme |
| [20](EXB-IDE-20.md) | Liste ventes/N°vente | 1 | Configuration impression |
| [22](EXB-IDE-22.md) | Edition des excursions | 1 | Impression ticket/document |
| [23](EXB-IDE-23.md) | Liste Participant | 1 | Configuration impression |
| [25](EXB-IDE-25.md) | Ventes saison | 1 | Sous-programme |
| [26](EXB-IDE-26.md) | Detail Excursion | 1 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 11 | Programme compact |
| Expressions | 8 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 6 | Dependances moderees |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 11) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Impression (1 tache: 1 ecran, 0 traitement)

- **Strategie** : Templates HTML -> PDF via wkhtmltopdf ou Puppeteer.
- `PrintService` injectable avec choix imprimante

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| [Liste Participant (IDE 23)](EXB-IDE-23.md) | Sous-programme | 1x | Normale - Configuration impression |
| [Ventes saison (IDE 25)](EXB-IDE-25.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Detail Excursion (IDE 26)](EXB-IDE-26.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Appel programme (IDE 17)](EXB-IDE-17.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Liste ventes/N°vente (IDE 20)](EXB-IDE-20.md) | Sous-programme | 1x | Normale - Configuration impression |
| [Edition des excursions (IDE 22)](EXB-IDE-22.md) | Sous-programme | 1x | Normale - Impression ticket/document |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 10:37*
