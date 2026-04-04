# ADH IDE 296 - Print versement/retrait bi

> **Analyse**: Phases 1-4 2026-02-07 03:55 -> 03:55 (33s) | Assemblage 05:13
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | ADH |
| IDE Position | 296 |
| Nom Programme | Print versement/retrait bi |
| Fichier source | `Prg_296.xml` |
| Dossier IDE | Impression |
| Taches | 13 (1 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 1 |
| Complexite | **BASSE** (score 12/100) |
| <span style="color:red">Statut</span> | <span style="color:red">**ORPHELIN_POTENTIEL**</span> |

## 2. DESCRIPTION FONCTIONNELLE

**ADH IDE 296 - Print versement/retrait bi** gère l'impression des reçus de versement et retrait bilatéraux dans le système de caisse. Le programme initialise l'imprimante via un appel à ADH IDE 182 (Raz Current Printer), puis structure le flux d'impression sur plusieurs tâches organisées pour afficher l'état d'avancement à l'utilisateur.

La logique d'impression suit un pattern standardisé avec six tâches distinctes. La première tâche affiche un message "Veuillez patienter" pendant le traitement. Les quatre tâches intermédiaires (Printer 1, Impression reçu, etc.) gèrent les différentes étapes d'impression du reçu de versement/retrait, avec une tâche répétée deux fois pour traiter les deux volets du document bilatéral. La dernière tâche (Printer 4) finalise le processus d'impression.

Ce programme fait partie des utilitaires de caisse ADH.ecf, exploités par les modules d'opérations de change et de gestion des dépôts pour produire les preuves imprimées des transactions de trésorerie. Le pattern structuré en tâches séquentielles garantit que chaque étape d'impression (initialisation, mise en forme, impression volet 1, volet 2, finalization) s'exécute dans l'ordre correct.

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (8 taches)

Traitements internes.

---

#### <a id="t1"></a>T1 - Veuillez patienter ... [ECRAN]

**Role** : Tache d'orchestration : point d'entree du programme (8 sous-taches). Coordonne l'enchainement des traitements.
**Ecran** : 424 x 56 DLU (MDI) | [Voir mockup](#ecran-t1)

<details>
<summary>7 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [T3](#t3) | Impression reçu verst/retrait **[ECRAN]** | Traitement |
| [T4](#t4) | Impression reçu verst/retrait **[ECRAN]** | Traitement |
| [T6](#t6) | Impression reçu verst/retrait **[ECRAN]** | Traitement |
| [T7](#t7) | Impression reçu verst/retrait **[ECRAN]** | Traitement |
| [T9](#t9) | Impression reçu verst/retrait **[ECRAN]** | Traitement |
| [T11](#t11) | Impression reçu verst/retrait **[ECRAN]** | Traitement |
| [T13](#t13) | Impression reçu verst/retrait **[ECRAN]** | Traitement |

</details>

---

#### <a id="t3"></a>T3 - Impression reçu verst/retrait [ECRAN]

**Role** : Generation du document : Impression reçu verst/retrait.
**Ecran** : 1058 x 791 DLU (MDI) | [Voir mockup](#ecran-t3)

---

#### <a id="t4"></a>T4 - Impression reçu verst/retrait [ECRAN]

**Role** : Generation du document : Impression reçu verst/retrait.
**Ecran** : 1058 x 791 DLU (MDI) | [Voir mockup](#ecran-t4)

---

#### <a id="t6"></a>T6 - Impression reçu verst/retrait [ECRAN]

**Role** : Generation du document : Impression reçu verst/retrait.
**Ecran** : 1058 x 791 DLU (MDI) | [Voir mockup](#ecran-t6)

---

#### <a id="t7"></a>T7 - Impression reçu verst/retrait [ECRAN]

**Role** : Generation du document : Impression reçu verst/retrait.
**Ecran** : 1058 x 791 DLU (MDI) | [Voir mockup](#ecran-t7)

---

#### <a id="t9"></a>T9 - Impression reçu verst/retrait [ECRAN]

**Role** : Generation du document : Impression reçu verst/retrait.
**Ecran** : 357 x 103 DLU (MDI) | [Voir mockup](#ecran-t9)

---

#### <a id="t11"></a>T11 - Impression reçu verst/retrait [ECRAN]

**Role** : Generation du document : Impression reçu verst/retrait.
**Ecran** : 1058 x 791 DLU (MDI) | [Voir mockup](#ecran-t11)

---

#### <a id="t13"></a>T13 - Impression reçu verst/retrait [ECRAN]

**Role** : Generation du document : Impression reçu verst/retrait.
**Ecran** : 1058 x 791 DLU (MDI) | [Voir mockup](#ecran-t13)


### 3.2 Impression (5 taches)

Generation des documents et tickets.

---

#### <a id="t2"></a>T2 - Printer 1 [ECRAN]

**Role** : Generation du document : Printer 1.
**Ecran** : 1058 x 791 DLU (MDI) | [Voir mockup](#ecran-t2)
**Delegue a** : [Raz Current Printer (IDE 182)](ADH-IDE-182.md)

---

#### <a id="t5"></a>T5 - Printer 4 [ECRAN]

**Role** : Generation du document : Printer 4.
**Ecran** : 1058 x 791 DLU (MDI) | [Voir mockup](#ecran-t5)
**Delegue a** : [Raz Current Printer (IDE 182)](ADH-IDE-182.md)

---

#### <a id="t8"></a>T8 - Printer 5 [ECRAN]

**Role** : Generation du document : Printer 5.
**Ecran** : 357 x 103 DLU (MDI) | [Voir mockup](#ecran-t8)
**Delegue a** : [Raz Current Printer (IDE 182)](ADH-IDE-182.md)

---

#### <a id="t10"></a>T10 - Printer 8 [ECRAN]

**Role** : Generation du document : Printer 8.
**Ecran** : 1058 x 791 DLU (MDI) | [Voir mockup](#ecran-t10)
**Delegue a** : [Raz Current Printer (IDE 182)](ADH-IDE-182.md)

---

#### <a id="t12"></a>T12 - Printer 9 [ECRAN]

**Role** : Generation du document : Printer 9.
**Ecran** : 1058 x 791 DLU (MDI) | [Voir mockup](#ecran-t12)
**Delegue a** : [Raz Current Printer (IDE 182)](ADH-IDE-182.md)


## 5. REGLES METIER

5 regles identifiees:

### Impression (5 regles)

#### <a id="rm-RM-001"></a>[RM-001] Verification que l'imprimante courante est la n1

| Element | Detail |
|---------|--------|
| **Condition** | `GetParam ('CURRENTPRINTERNUM')=1` |
| **Si vrai** | Action conditionnelle |
| **Expression source** | Expression 3 : `GetParam ('CURRENTPRINTERNUM')=1` |
| **Exemple** | Si GetParam ('CURRENTPRINTERNUM')=1 â†’ Action conditionnelle |
| **Impact** | [T2 - Printer 1](#t2) |

#### <a id="rm-RM-002"></a>[RM-002] Verification que l'imprimante courante est la n4

| Element | Detail |
|---------|--------|
| **Condition** | `GetParam ('CURRENTPRINTERNUM')=4` |
| **Si vrai** | Action conditionnelle |
| **Expression source** | Expression 4 : `GetParam ('CURRENTPRINTERNUM')=4` |
| **Exemple** | Si GetParam ('CURRENTPRINTERNUM')=4 â†’ Action conditionnelle |
| **Impact** | [T2 - Printer 1](#t2) |

#### <a id="rm-RM-003"></a>[RM-003] Verification que l'imprimante courante est la n5

| Element | Detail |
|---------|--------|
| **Condition** | `GetParam ('CURRENTPRINTERNUM')=5` |
| **Si vrai** | Action conditionnelle |
| **Expression source** | Expression 5 : `GetParam ('CURRENTPRINTERNUM')=5` |
| **Exemple** | Si GetParam ('CURRENTPRINTERNUM')=5 â†’ Action conditionnelle |
| **Impact** | [T2 - Printer 1](#t2) |

#### <a id="rm-RM-004"></a>[RM-004] Verification que l'imprimante courante est la n8

| Element | Detail |
|---------|--------|
| **Condition** | `GetParam ('CURRENTPRINTERNUM')=8` |
| **Si vrai** | Action conditionnelle |
| **Expression source** | Expression 6 : `GetParam ('CURRENTPRINTERNUM')=8` |
| **Exemple** | Si GetParam ('CURRENTPRINTERNUM')=8 â†’ Action conditionnelle |
| **Impact** | [T2 - Printer 1](#t2) |

#### <a id="rm-RM-005"></a>[RM-005] Verification que l'imprimante courante est la n9

| Element | Detail |
|---------|--------|
| **Condition** | `GetParam ('CURRENTPRINTERNUM')=9` |
| **Si vrai** | Action conditionnelle |
| **Expression source** | Expression 7 : `GetParam ('CURRENTPRINTERNUM')=9` |
| **Exemple** | Si GetParam ('CURRENTPRINTERNUM')=9 â†’ Action conditionnelle |
| **Impact** | [T2 - Printer 1](#t2) |

## 6. CONTEXTE

- **Appele par**: (aucun)
- **Appelle**: 1 programmes | **Tables**: 2 (W:0 R:1 L:1) | **Taches**: 13 | **Expressions**: 7

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 13)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 296 | T1 | Veuillez patienter ... | MDI | 424 | 56 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>296 - Veuillez patienter ...
**Tache** : [T1](#t1) | **Type** : MDI | **Dimensions** : 424 x 56 DLU
**Bloc** : Traitement | **Titre IDE** : Veuillez patienter ...

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
                         "text":  "Impression en cours ...",
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
                         "x":  55,
                         "type":  "label",
                         "var":  "",
                         "y":  38,
                         "w":  315,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Edition des versements / retraits",
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
    "taskId":  "296",
    "height":  56
}
-->

## 9. NAVIGATION

Ecran unique: **Veuillez patienter ...**

### 9.3 Structure hierarchique (13 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **296.1** | [**Veuillez patienter ...** (T1)](#t1) [mockup](#ecran-t1) | MDI | 424x56 | Traitement |
| 296.1.1 | [Impression reçu verst/retrait (T3)](#t3) [mockup](#ecran-t3) | MDI | 1058x791 | |
| 296.1.2 | [Impression reçu verst/retrait (T4)](#t4) [mockup](#ecran-t4) | MDI | 1058x791 | |
| 296.1.3 | [Impression reçu verst/retrait (T6)](#t6) [mockup](#ecran-t6) | MDI | 1058x791 | |
| 296.1.4 | [Impression reçu verst/retrait (T7)](#t7) [mockup](#ecran-t7) | MDI | 1058x791 | |
| 296.1.5 | [Impression reçu verst/retrait (T9)](#t9) [mockup](#ecran-t9) | MDI | 357x103 | |
| 296.1.6 | [Impression reçu verst/retrait (T11)](#t11) [mockup](#ecran-t11) | MDI | 1058x791 | |
| 296.1.7 | [Impression reçu verst/retrait (T13)](#t13) [mockup](#ecran-t13) | MDI | 1058x791 | |
| **296.2** | [**Printer 1** (T2)](#t2) [mockup](#ecran-t2) | MDI | 1058x791 | Impression |
| 296.2.1 | [Printer 4 (T5)](#t5) [mockup](#ecran-t5) | MDI | 1058x791 | |
| 296.2.2 | [Printer 5 (T8)](#t8) [mockup](#ecran-t8) | MDI | 357x103 | |
| 296.2.3 | [Printer 8 (T10)](#t10) [mockup](#ecran-t10) | MDI | 1058x791 | |
| 296.2.4 | [Printer 9 (T12)](#t12) [mockup](#ecran-t12) | MDI | 1058x791 | |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    START --> INIT
    B1[Traitement (8t)]
    INIT --> B1
    B2[Impression (5t)]
    B1 --> B2
    ENDOK([END OK])
    B2 --> ENDOK

    style START fill:#3fb950,color:#000
    style ENDOK fill:#3fb950,color:#000
```

> **Legende**: Vert = START/END OK | Rouge = END KO | Bleu = Decisions
> *Algorigramme genere depuis les expressions CONDITION. Utiliser `/algorigramme` pour une synthese metier detaillee.*

<!-- TAB:Donnees -->

## 10. TABLES

### Tables utilisees (2)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 40 | comptable________cte |  | DB | R |   |   | 7 |
| 30 | gm-recherche_____gmr | Index de recherche | DB |   |   | L | 7 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 40 - comptable________cte (R) - 7 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | W1 imprimante | R | Alpha |
| B | W1 large | R | Alpha |
| C | W1 normal | R | Alpha |
| D | W1 condense | R | Alpha |
| E | W1 detection papier | R | Alpha |
| F | W1 inhibe panel | R | Alpha |
| G | W1 massicot | R | Alpha |
| H | W1 selection feuille | R | Alpha |
| I | W1 selection rouleau | R | Alpha |
| J | W1 ejection | R | Alpha |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (9)

Variables recues en parametre.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P0 societe | Alpha | - |
| B | P0 code adherent | Numeric | - |
| C | P0 date | Date | - |
| D | P0 heure | Time | - |
| E | P0 devise locale | Alpha | - |
| F | P0 masque montant | Alpha | - |
| G | P0 nom village | Alpha | - |
| H | P0 telephone | Alpha | - |
| I | P0 fax | Alpha | - |

### 11.2 Variables de travail (1)

Variables internes au programme.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| J | W0 entête ? | Alpha | - |

## 12. EXPRESSIONS

**7 / 7 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| OTHER | 2 | 0 |
| CONDITION | 5 | 0 |

### 12.2 Expressions cles par type

#### OTHER (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 2 | `SetCrsr (1)` | - |
| OTHER | 1 | `SetCrsr (2)` | - |

#### CONDITION (5 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 6 | `GetParam ('CURRENTPRINTERNUM')=8` | - |
| CONDITION | 7 | `GetParam ('CURRENTPRINTERNUM')=9` | - |
| CONDITION | 5 | `GetParam ('CURRENTPRINTERNUM')=5` | - |
| CONDITION | 3 | `GetParam ('CURRENTPRINTERNUM')=1` | - |
| CONDITION | 4 | `GetParam ('CURRENTPRINTERNUM')=4` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

**Chemin**: (pas de callers directs)

```mermaid
graph LR
    T296[296 Print versementret...]
    style T296 fill:#58a6ff
    NONE[Aucun caller]
    NONE -.-> T296
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| - | (aucun) | - |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T296[296 Print versementret...]
    style T296 fill:#58a6ff
    C182[182 Raz Current Printer]
    T296 --> C182
    style C182 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [182](ADH-IDE-182.md) | Raz Current Printer | 1 | Impression ticket/document |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 233 | Taille moyenne |
| Expressions | 7 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 1 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 233) | Code sain |
| Regles metier | 5 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (8 taches: 8 ecrans, 0 traitement)

- **Strategie** : 8 composant(s) UI (Razor/React) avec formulaires et validation.
- 1 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Impression (5 taches: 5 ecrans, 0 traitement)

- **Strategie** : Templates HTML -> PDF via wkhtmltopdf ou Puppeteer.
- `PrintService` injectable avec choix imprimante

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| [Raz Current Printer (IDE 182)](ADH-IDE-182.md) | Sous-programme | 1x | Normale - Impression ticket/document |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-08 05:13*
