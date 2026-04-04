# PVE IDE 14 - Change VAT

> **Analyse**: Phases 1-4 2026-02-03 01:02 -> 01:02 (37s) | Assemblage 01:02
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PVE |
| IDE Position | 14 |
| Nom Programme | Change VAT |
| Fichier source | `Prg_14.xml` |
| Domaine metier | Change |
| Taches | 2 (1 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 2 |

## 2. DESCRIPTION FONCTIONNELLE

**Change VAT** assure la gestion complete de ce processus, accessible depuis [Global Items (IDE 6)](PVE-IDE-6.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (2 taches) : traitements metier divers

**Donnees modifiees** : 1 tables en ecriture (pv_sellers).

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (2 taches)

Traitements internes.

---

#### <a id="t1"></a>14 - Change VAT [[ECRAN]](#ecran-t1)

**Role** : Traitement : Change VAT.
**Ecran** : 786 x 130 DLU (MDI) | [Voir mockup](#ecran-t1)

---

#### <a id="t2"></a>14.1 - Update Products

**Role** : Traitement : Update Products.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Global Items (IDE 6)](PVE-IDE-6.md)
- **Appelle**: 2 programmes | **Tables**: 3 (W:1 R:1 L:1) | **Taches**: 2 | **Expressions**: 4

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 2)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 14 | 14 | Change VAT | MDI | 786 | 130 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>14 - Change VAT
**Tache** : [14](#t1) | **Type** : MDI | **Dimensions** : 786 x 130 DLU
**Bloc** : Traitement | **Titre IDE** : Change VAT

<!-- FORM-DATA:
{
    "width":  786,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  393,
                         "type":  "label",
                         "var":  "",
                         "y":  38,
                         "w":  311,
                         "fmt":  "",
                         "name":  "",
                         "h":  16,
                         "color":  "187",
                         "text":  " VAT VALUE",
                         "parent":  null
                     },
                     {
                         "x":  8,
                         "type":  "label",
                         "var":  "",
                         "y":  3,
                         "w":  378,
                         "fmt":  "",
                         "name":  "",
                         "h":  37,
                         "color":  "183",
                         "text":  "Category",
                         "parent":  null
                     },
                     {
                         "x":  8,
                         "type":  "label",
                         "var":  "",
                         "y":  47,
                         "w":  378,
                         "fmt":  "",
                         "name":  "",
                         "h":  37,
                         "color":  "183",
                         "text":  "Sub Category",
                         "parent":  null
                     },
                     {
                         "x":  6,
                         "type":  "label",
                         "var":  "",
                         "y":  96,
                         "w":  773,
                         "fmt":  "",
                         "name":  "",
                         "h":  31,
                         "color":  "182",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  16,
                         "type":  "button",
                         "var":  "",
                         "y":  14,
                         "w":  358,
                         "fmt":  "",
                         "name":  "CAT",
                         "h":  22,
                         "color":  "",
                         "text":  "",
                         "parent":  2
                     },
                     {
                         "x":  16,
                         "type":  "button",
                         "var":  "",
                         "y":  58,
                         "w":  358,
                         "fmt":  "",
                         "name":  "SUBCAT",
                         "h":  22,
                         "color":  "",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  14,
                         "type":  "button",
                         "var":  "",
                         "y":  102,
                         "w":  145,
                         "fmt":  "\u0026Exit",
                         "name":  "",
                         "h":  22,
                         "color":  "",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  621,
                         "type":  "button",
                         "var":  "",
                         "y":  102,
                         "w":  145,
                         "fmt":  "\u0026Change",
                         "name":  "CHANGE",
                         "h":  22,
                         "color":  "",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  591,
                         "type":  "combobox",
                         "var":  "",
                         "y":  40,
                         "w":  112,
                         "fmt":  "",
                         "name":  "VAT",
                         "h":  12,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  170,
                         "type":  "button",
                         "var":  "",
                         "y":  102,
                         "w":  145,
                         "fmt":  "\u0026RAZ",
                         "name":  "RAZ",
                         "h":  22,
                         "color":  "",
                         "text":  "",
                         "parent":  7
                     }
                 ],
    "taskId":  "14",
    "height":  130
}
-->

<details>
<summary><strong>Champs : 1 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 591,40 | VAT | - | combobox |

</details>

<details>
<summary><strong>Boutons : 5 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| CAT | 16,14 | Appel [Choix - Category (IDE 333)](PVE-IDE-333.md) |
| SUBCAT | 16,58 | Bouton fonctionnel |
| Exit | 14,102 | Quitte le programme |
| Change | 621,102 | Modifie l'element |
| RAZ | 170,102 | Bouton fonctionnel |

</details>

## 9. NAVIGATION

Ecran unique: **Change VAT**

### 9.3 Structure hierarchique (2 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **14.1** | [**Change VAT** (14)](#t1) [mockup](#ecran-t1) | MDI | 786x130 | Traitement |
| 14.1.1 | [Update Products (14.1)](#t2) | - | - | |

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

### Tables utilisees (3)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 379 | pv_customer_temp |  | DB | R |   |   | 1 |
| 403 | pv_sellers |  | DB |   | **W** |   | 1 |
| 413 | pv_tva |  | DB |   |   | L | 1 |

### Colonnes par table (1 / 2 tables avec colonnes identifiees)

<details>
<summary>Table 379 - pv_customer_temp (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P. Category | R | Numeric |
| B | P.Sub Category | R | Numeric |
| C | VAT | R | Numeric |

</details>

<details>
<summary>Table 403 - pv_sellers (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (2)

Variables recues du programme appelant ([Global Items (IDE 6)](PVE-IDE-6.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P. Category | Numeric | 1x parametre entrant |
| B | P.Sub Category | Numeric | 1x parametre entrant |

### 11.2 Autres (1)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| C | VAT | Numeric | - |

## 12. EXPRESSIONS

**4 / 4 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONSTANTE | 1 | 0 |
| OTHER | 2 | 0 |
| CONDITION | 1 | 0 |

### 12.2 Expressions cles par type

#### CONSTANTE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 4 | `0` | - |

#### OTHER (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 2 | `P. Category [A]` | - |
| OTHER | 1 | `GetParam ('SERVICE')` | - |

#### CONDITION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 3 | `CndRange(P.Sub Category [B]>0,P.Sub Category [B])` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Global Items (IDE 6)](PVE-IDE-6.md) -> **Change VAT (IDE 14)**

```mermaid
graph LR
    T14[14 Change VAT]
    style T14 fill:#58a6ff
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
    CC6[6 Global Items]
    style CC6 fill:#3fb950
    CC178 --> CC6
    CC185 --> CC178
    CC353 --> CC178
    CC420 --> CC178
    CC439 --> CC178
    CC143 --> CC185
    CC143 --> CC353
    CC143 --> CC420
    CC143 --> CC439
    CC1 --> CC143
    CC6 --> T14
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [6](PVE-IDE-6.md) | Global Items | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T14[14 Change VAT]
    style T14 fill:#58a6ff
    C333[333 Choix - Category]
    T14 --> C333
    style C333 fill:#3fb950
    C334[334 Choix - Sub Category]
    T14 --> C334
    style C334 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [333](PVE-IDE-333.md) | Choix - Category | 1 | Selection/consultation |
| [334](PVE-IDE-334.md) | Choix - Sub Category | 1 | Selection/consultation |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 38 | Programme compact |
| Expressions | 4 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 2 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 38) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (2 taches: 1 ecran, 1 traitement)

- **Strategie** : Orchestrateur avec 1 ecrans (Razor/React) et 1 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 2 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| pv_sellers | Table WRITE (Database) | 1x | Schema + repository |
| [Choix - Sub Category (IDE 334)](PVE-IDE-334.md) | Sous-programme | 1x | Normale - Selection/consultation |
| [Choix - Category (IDE 333)](PVE-IDE-333.md) | Sous-programme | 1x | Normale - Selection/consultation |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 01:02*
