# ADH IDE 295 - Menu change bilateral

> **Analyse**: Phases 1-4 2026-02-07 03:55 -> 05:12 (25h16min) | Assemblage 05:12
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | ADH |
| IDE Position | 295 |
| Nom Programme | Menu change bilateral |
| Fichier source | `Prg_295.xml` |
| Dossier IDE | Change |
| Taches | 1 (1 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 2 |
| Complexite | **BASSE** (score 5/100) |
| <span style="color:red">Statut</span> | <span style="color:red">**ORPHELIN_POTENTIEL**</span> |

## 2. DESCRIPTION FONCTIONNELLE

# ADH IDE 295 - Menu Change Bilateral

Menu de sélection pour les opérations de change bilatéral. Ce programme affiche une grille de choix permettant à l'utilisateur de naviguer vers les différentes devises disponibles. Il récupère le titre de l'écran via ADH IDE 43 (GET_TITLE) et bascule vers le programme de gestion de change spécifique (ADH IDE 44) selon la devise sélectionnée.

Structure type menu : présentation des devises avec leurs taux de change actuels, sélection par curseur, validation et branchement conditionnel. Les paramètres sont transmis au programme appelé pour maintenir le contexte de la transaction (société, compte, filiation). Tâche principale OCA (Online Call Action) gère l'interface utilisateur et les transitions entre écrans.

Le programme agit comme point d'entrée au module change bilatéral, centralisant l'accès aux opérations de conversion devises avant délégation aux programmes spécialisés de calcul et validation des équivalences.

## 3. BLOCS FONCTIONNELS

### 3.1 Calcul (1 tache)

Calculs metier : montants, stocks, compteurs.

---

#### <a id="t1"></a>295 - OCA  Menu solde d'un compte [[ECRAN]](#ecran-t1)

**Role** : Consultation/chargement : OCA  Menu solde d'un compte.
**Ecran** : 608 x 159 DLU (MDI) | [Voir mockup](#ecran-t1)
**Variables liees** : EV (P0 solde compte), EW (P0 etat compte), EX (P0 date du solde)


## 5. REGLES METIER

2 regles identifiees:

### Autres (2 regles)

#### <a id="rm-RM-001"></a>[RM-001] Condition: W0 choix action [P] egale '1'

| Element | Detail |
|---------|--------|
| **Condition** | `W0 choix action [P]='1'` |
| **Si vrai** | Action si vrai |
| **Variables** | FC (W0 choix action) |
| **Expression source** | Expression 6 : `W0 choix action [P]='1'` |
| **Exemple** | Si W0 choix action [P]='1' â†’ Action si vrai |

#### <a id="rm-RM-002"></a>[RM-002] Condition: W0 choix action [P] egale '2'

| Element | Detail |
|---------|--------|
| **Condition** | `W0 choix action [P]='2'` |
| **Si vrai** | Action si vrai |
| **Variables** | FC (W0 choix action) |
| **Expression source** | Expression 7 : `W0 choix action [P]='2'` |
| **Exemple** | Si W0 choix action [P]='2' â†’ Action si vrai |

## 6. CONTEXTE

- **Appele par**: (aucun)
- **Appelle**: 2 programmes | **Tables**: 0 (W:0 R:0 L:0) | **Taches**: 1 | **Expressions**: 7

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 1)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 295 | 295 | OCA  Menu solde d'un compte | MDI | 608 | 159 | Calcul |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>295 - OCA  Menu solde d'un compte
**Tache** : [295](#t1) | **Type** : MDI | **Dimensions** : 608 x 159 DLU
**Bloc** : Calcul | **Titre IDE** : OCA  Menu solde d'un compte

<!-- FORM-DATA:
{
    "width":  608,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  3,
                         "w":  608,
                         "fmt":  "",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  46,
                         "type":  "label",
                         "var":  "",
                         "y":  38,
                         "w":  517,
                         "fmt":  "",
                         "name":  "",
                         "h":  82,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  50,
                         "type":  "label",
                         "var":  "",
                         "y":  39,
                         "w":  510,
                         "fmt":  "",
                         "name":  "",
                         "h":  80,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  242,
                         "type":  "label",
                         "var":  "",
                         "y":  52,
                         "w":  285,
                         "fmt":  "",
                         "name":  "",
                         "h":  42,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  243,
                         "type":  "label",
                         "var":  "",
                         "y":  53,
                         "w":  50,
                         "fmt":  "",
                         "name":  "",
                         "h":  40,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  301,
                         "type":  "label",
                         "var":  "",
                         "y":  60,
                         "w":  178,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "7",
                         "text":  "Achat de devises",
                         "parent":  null
                     },
                     {
                         "x":  301,
                         "type":  "label",
                         "var":  "",
                         "y":  76,
                         "w":  178,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "7",
                         "text":  "Vente de devises",
                         "parent":  null
                     },
                     {
                         "x":  305,
                         "type":  "label",
                         "var":  "",
                         "y":  102,
                         "w":  120,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "Votre choix",
                         "parent":  null
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  135,
                         "w":  607,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  426,
                         "type":  "edit",
                         "var":  "",
                         "y":  102,
                         "w":  26,
                         "fmt":  "UA",
                         "name":  "W0 choix action",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  7,
                         "type":  "edit",
                         "var":  "",
                         "y":  8,
                         "w":  267,
                         "fmt":  "20",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  385,
                         "type":  "edit",
                         "var":  "",
                         "y":  8,
                         "w":  216,
                         "fmt":  "WWW  DD MMM YYYYT",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  65,
                         "type":  "image",
                         "var":  "",
                         "y":  56,
                         "w":  163,
                         "fmt":  "",
                         "name":  "",
                         "h":  44,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  254,
                         "type":  "button",
                         "var":  "",
                         "y":  59,
                         "w":  26,
                         "fmt":  "1",
                         "name":  "1",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  254,
                         "type":  "button",
                         "var":  "",
                         "y":  75,
                         "w":  26,
                         "fmt":  "2",
                         "name":  "2",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  5,
                         "type":  "button",
                         "var":  "",
                         "y":  138,
                         "w":  154,
                         "fmt":  "\u0026Quitter",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  13
                     }
                 ],
    "taskId":  "295",
    "height":  159
}
-->

<details>
<summary><strong>Champs : 3 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 426,102 | W0 choix action | - | edit |
| 7,8 | 20 | - | edit |
| 385,8 | WWW  DD MMM YYYYT | - | edit |

</details>

<details>
<summary><strong>Boutons : 3 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| 1 | 254,59 | Bouton fonctionnel |
| 2 | 254,75 | Bouton fonctionnel |
| Quitter | 5,138 | Quitte le programme |

</details>

## 9. NAVIGATION

Ecran unique: **OCA  Menu solde d'un compte**

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **295.1** | [**OCA  Menu solde d'un compte** (295)](#t1) [mockup](#ecran-t1) | MDI | 608x159 | Calcul |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Traitement principal]
    DECISION{W0 choix action}
    PROCESS[Traitement]
    ENDOK([END OK])
    ENDKO([END KO])

    START --> INIT --> SAISIE --> DECISION
    DECISION -->|OUI| PROCESS
    DECISION -->|NON| ENDKO
    PROCESS --> ENDOK

    style START fill:#3fb950,color:#000
    style ENDOK fill:#3fb950,color:#000
    style ENDKO fill:#f85149,color:#fff
    style DECISION fill:#58a6ff,color:#000
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

### 11.1 Parametres entrants (15)

Variables recues en parametre.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| EN | P0 societe | Alpha | - |
| EO | P0 code GM | Numeric | - |
| EP | P0 filiation | Numeric | - |
| EQ | P0 devise locale | Alpha | - |
| ER | P0 nb decimale | Numeric | - |
| ES | P0 masque montant | Alpha | - |
| ET | P0 code retour | Alpha | - |
| EU | P0 nom du village | Alpha | - |
| EV | P0 solde compte | Numeric | - |
| EW | P0 etat compte | Alpha | - |
| EX | P0 date du solde | Date | - |
| EY | P0 garanti O/N | Alpha | - |
| EZ | P0 telephone | Alpha | - |
| FA | P0 fax | Alpha | - |
| FB | P0 nouvelle caisse | Alpha | - |

### 11.2 Variables de session (1)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| FD | v. titre ecran | Alpha | 1x session |

### 11.3 Variables de travail (1)

Variables internes au programme.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| FC | W0 choix action | Alpha | 2x calcul interne |

<details>
<summary>Toutes les 17 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| P0 | **EN** | P0 societe | Alpha |
| P0 | **EO** | P0 code GM | Numeric |
| P0 | **EP** | P0 filiation | Numeric |
| P0 | **EQ** | P0 devise locale | Alpha |
| P0 | **ER** | P0 nb decimale | Numeric |
| P0 | **ES** | P0 masque montant | Alpha |
| P0 | **ET** | P0 code retour | Alpha |
| P0 | **EU** | P0 nom du village | Alpha |
| P0 | **EV** | P0 solde compte | Numeric |
| P0 | **EW** | P0 etat compte | Alpha |
| P0 | **EX** | P0 date du solde | Date |
| P0 | **EY** | P0 garanti O/N | Alpha |
| P0 | **EZ** | P0 telephone | Alpha |
| P0 | **FA** | P0 fax | Alpha |
| P0 | **FB** | P0 nouvelle caisse | Alpha |
| W0 | **FC** | W0 choix action | Alpha |
| V. | **FD** | v. titre ecran | Alpha |

</details>

## 12. EXPRESSIONS

**7 / 7 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONDITION | 2 | 2 |
| CONSTANTE | 2 | 0 |
| DATE | 1 | 0 |
| REFERENCE_VG | 1 | 0 |
| STRING | 1 | 0 |

### 12.2 Expressions cles par type

#### CONDITION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 7 | `W0 choix action [P]='2'` | [RM-002](#rm-RM-002) |
| CONDITION | 6 | `W0 choix action [P]='1'` | [RM-001](#rm-RM-001) |

#### CONSTANTE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 5 | `''` | - |
| CONSTANTE | 4 | `38` | - |

#### DATE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| DATE | 1 | `Date ()` | - |

#### REFERENCE_VG (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 2 | `VG2` | - |

#### STRING (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| STRING | 3 | `Trim (v. titre ecran [Q])` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

**Chemin**: (pas de callers directs)

```mermaid
graph LR
    T295[295 Menu change bilateral]
    style T295 fill:#58a6ff
    NONE[Aucun caller]
    NONE -.-> T295
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| - | (aucun) | - |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T295[295 Menu change bilateral]
    style T295 fill:#58a6ff
    C43[43 Recuperation du titre]
    T295 --> C43
    style C43 fill:#3fb950
    C44[44 Appel programme]
    T295 --> C44
    style C44 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [43](ADH-IDE-43.md) | Recuperation du titre | 1 | Recuperation donnees |
| [44](ADH-IDE-44.md) | Appel programme | 1 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 26 | Programme compact |
| Expressions | 7 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 2 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 26) | Code sain |
| Regles metier | 2 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Calcul (1 tache: 1 ecran, 0 traitement)

- **Strategie** : Services de calcul purs (Domain Services).
- Migrer la logique de calcul (stock, compteurs, montants)

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| [Appel programme (IDE 44)](ADH-IDE-44.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Recuperation du titre (IDE 43)](ADH-IDE-43.md) | Sous-programme | 1x | Normale - Recuperation donnees |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-08 05:13*
