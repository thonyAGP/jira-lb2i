# EXF IDE 18 - Printer choice

> **Analyse**: Phases 1-4 2026-02-03 10:58 -> 10:58 (19s) | Assemblage 10:58
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | EXF |
| IDE Position | 18 |
| Nom Programme | Printer choice |
| Fichier source | `Prg_18.xml` |
| Dossier IDE | Printer |
| Taches | 5 (1 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 1 |

## 2. DESCRIPTION FONCTIONNELLE

**Printer choice** assure la gestion complete de ce processus, accessible depuis [Ventes Excursions (IDE 35)](EXF-IDE-35.md), [ Annulation Ventes (IDE 40)](EXF-IDE-40.md), [Disponibilites@ verif stat (IDE 10)](EXF-IDE-10.md), [Liste ventes /N°vente (IDE 11)](EXF-IDE-11.md), [Liste ventes/Excursion (IDE 12)](EXF-IDE-12.md).

Le flux de traitement s'organise en **2 blocs fonctionnels** :

- **Traitement** (3 taches) : traitements metier divers
- **Impression** (2 taches) : generation de tickets et documents

**Donnees modifiees** : 1 tables en ecriture (pv_accounting_date).

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Impression (2 taches)

- **18** - Printer choice **[[ECRAN]](#ecran-t1)**
- **18.2** - Printer Choice **[[ECRAN]](#ecran-t3)**

Delegue a : [Get Printer (IDE 17)](EXF-IDE-17.md)

#### Phase 2 : Traitement (3 taches)

- **18.1** - Load
- **18.1.1** - Load
- **18.1.2** - Load

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| pv_accounting_date | **W** (2 usages) |  |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Impression (2 taches)

Generation des documents et tickets.

---

#### <a id="t1"></a>18 - Printer choice [[ECRAN]](#ecran-t1)

**Role** : Generation du document : Printer choice.
**Ecran** : 366 x 0 DLU (MDI) | [Voir mockup](#ecran-t1)
**Variables liees** : A (EndprinterChoice)
**Delegue a** : [Get Printer (IDE 17)](EXF-IDE-17.md)

---

#### <a id="t3"></a>18.2 - Printer Choice [[ECRAN]](#ecran-t3)

**Role** : Generation du document : Printer Choice.
**Ecran** : 768 x 233 DLU (MDI) | [Voir mockup](#ecran-t3)
**Variables liees** : A (EndprinterChoice)
**Delegue a** : [Get Printer (IDE 17)](EXF-IDE-17.md)


### 3.2 Traitement (3 taches)

Traitements internes.

---

#### <a id="t2"></a>18.1 - Load

**Role** : Traitement : Load.

---

#### <a id="t6"></a>18.1.1 - Load

**Role** : Traitement : Load.

---

#### <a id="t9"></a>18.1.2 - Load

**Role** : Traitement : Load.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Ventes Excursions (IDE 35)](EXF-IDE-35.md), [ Annulation Ventes (IDE 40)](EXF-IDE-40.md), [Disponibilites@ verif stat (IDE 10)](EXF-IDE-10.md), [Liste ventes /N°vente (IDE 11)](EXF-IDE-11.md), [Liste ventes/Excursion (IDE 12)](EXF-IDE-12.md)
- **Appelle**: 1 programmes | **Tables**: 5 (W:1 R:1 L:3) | **Taches**: 5 | **Expressions**: 4

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 5)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 18.2 | 18.2 | Printer Choice | MDI | 768 | 233 | Impression |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t3"></a>18.2 - Printer Choice
**Tache** : [18.2](#t3) | **Type** : MDI | **Dimensions** : 768 x 233 DLU
**Bloc** : Impression | **Titre IDE** : Printer Choice

<!-- FORM-DATA:
{
    "width":  768,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  10,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "110",
                         "w":  746,
                         "y":  1,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  14,
                         "h":  161,
                         "cols":  [
                                      {
                                          "title":  "Chrono",
                                          "layer":  1,
                                          "w":  78
                                      },
                                      {
                                          "title":  "Libellé",
                                          "layer":  2,
                                          "w":  431
                                      },
                                      {
                                          "title":  "Tray",
                                          "layer":  3,
                                          "w":  49
                                      },
                                      {
                                          "title":  "Copies",
                                          "layer":  4,
                                          "w":  69
                                      },
                                      {
                                          "title":  "Choice",
                                          "layer":  5,
                                          "w":  82
                                      }
                                  ],
                         "rows":  5
                     },
                     {
                         "x":  8,
                         "type":  "label",
                         "var":  "",
                         "y":  167,
                         "w":  165,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "Default printer",
                         "parent":  null
                     },
                     {
                         "x":  8,
                         "type":  "label",
                         "var":  "",
                         "y":  181,
                         "w":  165,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "Current listing",
                         "parent":  null
                     },
                     {
                         "x":  8,
                         "type":  "label",
                         "var":  "",
                         "y":  195,
                         "w":  165,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "Current printer",
                         "parent":  null
                     },
                     {
                         "x":  8,
                         "type":  "label",
                         "var":  "",
                         "y":  209,
                         "w":  165,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "Current copies",
                         "parent":  null
                     },
                     {
                         "x":  506,
                         "type":  "button",
                         "var":  "",
                         "y":  211,
                         "w":  240,
                         "fmt":  "",
                         "name":  "NoChangeAndExitButton",
                         "h":  16,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  194,
                         "type":  "edit",
                         "var":  "",
                         "y":  167,
                         "w":  549,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "6",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  194,
                         "type":  "edit",
                         "var":  "",
                         "y":  195,
                         "w":  549,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "6",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  18,
                         "type":  "edit",
                         "var":  "",
                         "y":  15,
                         "w":  62,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  96,
                         "type":  "edit",
                         "var":  "",
                         "y":  15,
                         "w":  421,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  525,
                         "type":  "edit",
                         "var":  "",
                         "y":  15,
                         "w":  40,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  574,
                         "type":  "edit",
                         "var":  "",
                         "y":  15,
                         "w":  59,
                         "fmt":  "",
                         "name":  "Copies",
                         "h":  12,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  643,
                         "type":  "button",
                         "var":  "",
                         "y":  15,
                         "w":  72,
                         "fmt":  "",
                         "name":  "Choice",
                         "h":  12,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  194,
                         "type":  "edit",
                         "var":  "",
                         "y":  181,
                         "w":  549,
                         "fmt":  "64",
                         "name":  "",
                         "h":  12,
                         "color":  "6",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  194,
                         "type":  "edit",
                         "var":  "",
                         "y":  209,
                         "w":  56,
                         "fmt":  "4",
                         "name":  "",
                         "h":  12,
                         "color":  "6",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "18.2",
    "height":  233
}
-->

<details>
<summary><strong>Champs : 8 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 194,167 | (sans nom) | - | edit |
| 194,195 | (sans nom) | - | edit |
| 18,15 | (sans nom) | - | edit |
| 96,15 | (sans nom) | - | edit |
| 525,15 | (sans nom) | - | edit |
| 574,15 | Copies | - | edit |
| 194,181 | 64 | - | edit |
| 194,209 | 4 | - | edit |

</details>

<details>
<summary><strong>Boutons : 2 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| NoChangeAndExitButton | 506,211 | Modifie l'element Quitte le programme |
| Choice | 643,15 | Bouton fonctionnel |

</details>

## 9. NAVIGATION

Ecran unique: **Printer Choice**

### 9.3 Structure hierarchique (5 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **18.1** | [**Printer choice** (18)](#t1) [mockup](#ecran-t1) | MDI | 366x0 | Impression |
| 18.1.1 | [Printer Choice (18.2)](#t3) [mockup](#ecran-t3) | MDI | 768x233 | |
| **18.2** | [**Load** (18.1)](#t2) | MDI | - | Traitement |
| 18.2.1 | [Load (18.1.1)](#t6) | MDI | - | |
| 18.2.2 | [Load (18.1.2)](#t9) | MDI | - | |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Printer Choice]
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

### Tables utilisees (5)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 367 | pms_print_param_default |  | DB | R |   |   | 2 |
| 369 | presents_par_nationalite |  | DB |   |   | L | 2 |
| 370 | pv_accounting_date |  | DB |   | **W** |   | 2 |
| 371 | pv_binding_settings |  | DB |   |   | L | 1 |
| 584 | tempo_type_millesia | Table temporaire ecran | TMP |   |   | L | 2 |

### Colonnes par table (1 / 2 tables avec colonnes identifiees)

<details>
<summary>Table 367 - pms_print_param_default (R) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | v.For current | R | Logical |
| B | v.Copies | R | Numeric |
| C | v.For default term | R | Logical |

</details>

<details>
<summary>Table 370 - pv_accounting_date (**W**) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Variables de session (2)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| B | v.Copies | Numeric | - |
| C | v.For default term | Logical | - |

### 11.2 Autres (1)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | EndprinterChoice | Logical | 1x refs |

## 12. EXPRESSIONS

**4 / 4 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| OTHER | 2 | 0 |
| NEGATION | 1 | 0 |
| REFERENCE_VG | 1 | 0 |

### 12.2 Expressions cles par type

#### OTHER (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 2 | `DbDel ('{584,2}'DSOURCE,'')` | - |
| OTHER | 1 | `EndprinterChoice [A]` | - |

#### NEGATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| NEGATION | 3 | `NOT VG5` | - |

#### REFERENCE_VG (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 4 | `VG5` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Ventes Excursions (IDE 35)](EXF-IDE-35.md) -> **Printer choice (IDE 18)**

Main -> ... -> [ Annulation Ventes (IDE 40)](EXF-IDE-40.md) -> **Printer choice (IDE 18)**

Main -> ... -> [Disponibilites@ verif stat (IDE 10)](EXF-IDE-10.md) -> **Printer choice (IDE 18)**

Main -> ... -> [Liste ventes /N°vente (IDE 11)](EXF-IDE-11.md) -> **Printer choice (IDE 18)**

Main -> ... -> [Liste ventes/Excursion (IDE 12)](EXF-IDE-12.md) -> **Printer choice (IDE 18)**

```mermaid
graph LR
    T18[18 Printer choice]
    style T18 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC14[14 Menu listes]
    style CC14 fill:#f59e0b
    CC13[13 Menu ventes]
    style CC13 fill:#f59e0b
    CC10[10 Disponibilites@ ver...]
    style CC10 fill:#3fb950
    CC40[40 Annulation Ventes]
    style CC40 fill:#3fb950
    CC11[11 Liste ventes N°vente]
    style CC11 fill:#3fb950
    CC12[12 Liste ventesExcursion]
    style CC12 fill:#3fb950
    CC35[35 Ventes Excursions]
    style CC35 fill:#3fb950
    CC13 --> CC10
    CC14 --> CC10
    CC13 --> CC11
    CC14 --> CC11
    CC13 --> CC12
    CC14 --> CC12
    CC13 --> CC35
    CC14 --> CC35
    CC13 --> CC40
    CC14 --> CC40
    CC1 --> CC13
    CC1 --> CC14
    CC10 --> T18
    CC11 --> T18
    CC12 --> T18
    CC35 --> T18
    CC40 --> T18
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [35](EXF-IDE-35.md) | Ventes Excursions | 4 |
| [40](EXF-IDE-40.md) |  Annulation Ventes | 4 |
| [10](EXF-IDE-10.md) | Disponibilites@ verif stat | 1 |
| [11](EXF-IDE-11.md) | Liste ventes /N°vente | 1 |
| [12](EXF-IDE-12.md) | Liste ventes/Excursion | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T18[18 Printer choice]
    style T18 fill:#58a6ff
    C17[17 Get Printer]
    T18 --> C17
    style C17 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [17](EXF-IDE-17.md) | Get Printer | 1 | Impression ticket/document |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 109 | Programme compact |
| Expressions | 4 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 1 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 109) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Impression (2 taches: 2 ecrans, 0 traitement)

- **Strategie** : Templates HTML -> PDF via wkhtmltopdf ou Puppeteer.
- `PrintService` injectable avec choix imprimante

#### Traitement (3 taches: 0 ecran, 3 traitements)

- **Strategie** : 3 service(s) backend injectable(s) (Domain Services).
- 1 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| pv_accounting_date | Table WRITE (Database) | 2x | Schema + repository |
| [Get Printer (IDE 17)](EXF-IDE-17.md) | Sous-programme | 1x | Normale - Impression ticket/document |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 10:58*
