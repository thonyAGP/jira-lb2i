# REF IDE 890 - Extrait de compte GP

> **Analyse**: Phases 1-4 2026-02-03 14:56 -> 14:56 (13s) | Assemblage 14:56
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | REF |
| IDE Position | 890 |
| Nom Programme | Extrait de compte GP |
| Fichier source | `Prg_890.xml` |
| Dossier IDE | Comptabilite |
| Taches | 1 (1 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |
| :warning: Statut | **ORPHELIN_POTENTIEL** |

## 2. DESCRIPTION FONCTIONNELLE

**Extrait de compte GP** assure la gestion complete de ce processus.

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Calcul** (1 tache) : calculs de montants, stocks ou compteurs

**Logique metier** : 1 regles identifiees couvrant conditions metier.

## 3. BLOCS FONCTIONNELS

### 3.1 Calcul (1 tache)

Calculs metier : montants, stocks, compteurs.

---

#### <a id="t1"></a>890 - Extrait de compte GP >> ADH [[ECRAN]](#ecran-t1)

**Role** : Traitement : Extrait de compte GP >> ADH.
**Ecran** : 1448 x 242 DLU | [Voir mockup](#ecran-t1)
**Variables liees** : B (P.Compte)


## 5. REGLES METIER

1 regles identifiees:

### Autres (1 regles)

#### <a id="rm-RM-001"></a>[RM-001] Si P.I.Application en cours [E]='P' alors 'P.Masque [C]'FORM sinon 'P.Compte [B]'FORM)

| Element | Detail |
|---------|--------|
| **Condition** | `P.I.Application en cours [E]='P'` |
| **Si vrai** | 'P.Masque [C]'FORM |
| **Si faux** | 'P.Compte [B]'FORM) |
| **Variables** | B (P.Compte), C (P.Masque), E (P.I.Application en cours) |
| **Expression source** | Expression 7 : `IF(P.I.Application en cours [E]='P','P.Masque [C]'FORM,'P.Co` |
| **Exemple** | Si P.I.Application en cours [E]='P' â†’ 'P.Masque [C]'FORM. Sinon â†’ 'P.Compte [B]'FORM) |

## 6. CONTEXTE

- **Appele par**: (aucun)
- **Appelle**: 0 programmes | **Tables**: 0 (W:0 R:0 L:0) | **Taches**: 1 | **Expressions**: 7

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 1)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 890 | 890 | Extrait de compte GP >> ADH | Type0 | 1448 | 242 | Calcul |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>890 - Extrait de compte GP >> ADH
**Tache** : [890](#t1) | **Type** : Type0 | **Dimensions** : 1448 x 242 DLU
**Bloc** : Calcul | **Titre IDE** : Extrait de compte GP >> ADH

<!-- FORM-DATA:
{
    "width":  1448,
    "vFactor":  8,
    "type":  "Type0",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  8,
                         "type":  "label",
                         "var":  "",
                         "y":  1,
                         "w":  1437,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  8,
                         "type":  "label",
                         "var":  "",
                         "y":  212,
                         "w":  1437,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  66,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "110",
                         "w":  1315,
                         "y":  30,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  13,
                         "h":  156,
                         "cols":  [
                                      {
                                          "title":  "Crédit/Débit",
                                          "layer":  1,
                                          "w":  122
                                      },
                                      {
                                          "title":  "Date",
                                          "layer":  2,
                                          "w":  124
                                      },
                                      {
                                          "title":  "Heure",
                                          "layer":  3,
                                          "w":  86
                                      },
                                      {
                                          "title":  "Libellé",
                                          "layer":  4,
                                          "w":  247
                                      },
                                      {
                                          "title":  "Libellé Supplementaire",
                                          "layer":  5,
                                          "w":  210
                                      },
                                      {
                                          "title":  "Montant",
                                          "layer":  6,
                                          "w":  192
                                      },
                                      {
                                          "title":  "Paiement",
                                          "layer":  7,
                                          "w":  101
                                      },
                                      {
                                          "title":  "Gift Pass",
                                          "layer":  8,
                                          "w":  201
                                      }
                                  ],
                         "rows":  8
                     },
                     {
                         "x":  66,
                         "type":  "label",
                         "var":  "",
                         "y":  188,
                         "w":  596,
                         "fmt":  "",
                         "name":  "",
                         "h":  19,
                         "color":  "42",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  785,
                         "type":  "label",
                         "var":  "",
                         "y":  188,
                         "w":  596,
                         "fmt":  "",
                         "name":  "",
                         "h":  19,
                         "color":  "42",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  794,
                         "type":  "label",
                         "var":  "",
                         "y":  195,
                         "w":  83,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "42",
                         "text":  "Operateur",
                         "parent":  24
                     },
                     {
                         "x":  18,
                         "type":  "edit",
                         "var":  "",
                         "y":  10,
                         "w":  398,
                         "fmt":  "30",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  1229,
                         "type":  "edit",
                         "var":  "",
                         "y":  10,
                         "w":  203,
                         "fmt":  "WWW DD MMM YYYYT",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  78,
                         "type":  "edit",
                         "var":  "",
                         "y":  46,
                         "w":  30,
                         "fmt":  "UX",
                         "name":  "cd",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  194,
                         "type":  "edit",
                         "var":  "",
                         "y":  46,
                         "w":  112,
                         "fmt":  "##/##/####",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  317,
                         "type":  "edit",
                         "var":  "",
                         "y":  46,
                         "w":  74,
                         "fmt":  "HH:MM",
                         "name":  "heure_op",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  438,
                         "type":  "edit",
                         "var":  "",
                         "y":  46,
                         "w":  176,
                         "fmt":  "",
                         "name":  "label",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  659,
                         "type":  "edit",
                         "var":  "",
                         "y":  46,
                         "w":  176,
                         "fmt":  "U15",
                         "name":  "CTE libelle Supplem.",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  862,
                         "type":  "edit",
                         "var":  "",
                         "y":  46,
                         "w":  176,
                         "fmt":  "15",
                         "name":  "montant",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  1058,
                         "type":  "edit",
                         "var":  "",
                         "y":  46,
                         "w":  77,
                         "fmt":  "",
                         "name":  "paiement",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  1154,
                         "type":  "edit",
                         "var":  "",
                         "y":  46,
                         "w":  176,
                         "fmt":  "15",
                         "name":  "cte_montant_free_extra",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  72,
                         "type":  "edit",
                         "var":  "",
                         "y":  195,
                         "w":  578,
                         "fmt":  "40",
                         "name":  "",
                         "h":  8,
                         "color":  "42",
                         "text":  "",
                         "parent":  22
                     },
                     {
                         "x":  930,
                         "type":  "edit",
                         "var":  "",
                         "y":  195,
                         "w":  101,
                         "fmt":  "",
                         "name":  "operateur",
                         "h":  10,
                         "color":  "42",
                         "text":  "",
                         "parent":  24
                     },
                     {
                         "x":  17,
                         "type":  "button",
                         "var":  "",
                         "y":  215,
                         "w":  168,
                         "fmt":  "\u0026Quitter",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "890",
    "height":  242
}
-->

<details>
<summary><strong>Champs : 12 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 18,10 | 30 | - | edit |
| 1229,10 | WWW DD MMM YYYYT | - | edit |
| 78,46 | cd | - | edit |
| 194,46 | ##/##/#### | - | edit |
| 317,46 | heure_op | - | edit |
| 438,46 | label | - | edit |
| 659,46 | CTE libelle Supplem. | - | edit |
| 862,46 | montant | - | edit |
| 1058,46 | paiement | - | edit |
| 1154,46 | cte_montant_free_extra | - | edit |
| 72,195 | 40 | - | edit |
| 930,195 | operateur | - | edit |

</details>

<details>
<summary><strong>Boutons : 1 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Quitter | 17,215 | Quitte le programme |

</details>

## 9. NAVIGATION

Ecran unique: **Extrait de compte GP >> ADH**

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **890.1** | [**Extrait de compte GP >> ADH** (890)](#t1) [mockup](#ecran-t1) | - | 1448x242 | Calcul |

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

### 11.1 Parametres entrants (5)

Variables recues en parametre.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P.Societe | Alpha | - |
| B | P.Compte | Numeric | 1x parametre entrant |
| C | P.Masque | Alpha | 2x parametre entrant |
| D | P.Village | Alpha | - |
| E | P.I.Application en cours | Alpha | 1x parametre entrant |

### 11.2 Autres (18)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| F | cte_montant_free_extra | Numeric | - |
| G | imputation | Numeric | - |
| H | sousimp | Numeric | - |
| I | CPTE | Numeric | - |
| J | FIL | Numeric | - |
| K | DEB | Alpha | - |
| L | FIN | Alpha | - |
| M | nom | Unicode | 1x refs |
| N | prenom | Unicode | 1x refs |
| O | cd | Unicode | - |
| P | comptable | Alpha | - |
| Q | date_op | Alpha | 1x refs |
| R | heure_op | Alpha | 1x refs |
| S | operateur | Unicode | - |
| T | paiement | Unicode | - |
| U | montant | Numeric | - |
| V | label | Unicode | - |
| W | label2 | Unicode | - |

<details>
<summary>Toutes les 23 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| P0 | **A** | P.Societe | Alpha |
| P0 | **B** | P.Compte | Numeric |
| P0 | **C** | P.Masque | Alpha |
| P0 | **D** | P.Village | Alpha |
| P0 | **E** | P.I.Application en cours | Alpha |
| Autre | **F** | cte_montant_free_extra | Numeric |
| Autre | **G** | imputation | Numeric |
| Autre | **H** | sousimp | Numeric |
| Autre | **I** | CPTE | Numeric |
| Autre | **J** | FIL | Numeric |
| Autre | **K** | DEB | Alpha |
| Autre | **L** | FIN | Alpha |
| Autre | **M** | nom | Unicode |
| Autre | **N** | prenom | Unicode |
| Autre | **O** | cd | Unicode |
| Autre | **P** | comptable | Alpha |
| Autre | **Q** | date_op | Alpha |
| Autre | **R** | heure_op | Alpha |
| Autre | **S** | operateur | Unicode |
| Autre | **T** | paiement | Unicode |
| Autre | **U** | montant | Numeric |
| Autre | **V** | label | Unicode |
| Autre | **W** | label2 | Unicode |

</details>

## 12. EXPRESSIONS

**7 / 7 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONDITION | 1 | 5 |
| DATE | 2 | 0 |
| STRING | 2 | 0 |
| CONCATENATION | 2 | 0 |

### 12.2 Expressions cles par type

#### CONDITION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 7 | `IF(P.I.Application en cours [E]='P','P.Masque [C]'FORM,'P.Compte [B]'FORM)` | [RM-001](#rm-RM-001) |

#### DATE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| DATE | 4 | `Date()` | - |
| DATE | 1 | `DVal(date_op [Q],'YYYYMMDD')` | - |

#### STRING (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| STRING | 3 | `Trim(P.Masque [C])` | - |
| STRING | 2 | `TVal(heure_op [R],'HHMMSS')` | - |

#### CONCATENATION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 6 | `Trim(prenom [N])&' '&Trim(nom [M])` | - |
| CONCATENATION | 5 | `VG2&' '&'('&Trim (Str (VG31,'3'))&') '` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

**Chemin**: (pas de callers directs)

```mermaid
graph LR
    T890[890 Extrait de compte GP]
    style T890 fill:#58a6ff
    NONE[Aucun caller]
    NONE -.-> T890
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| - | (aucun) | - |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T890[890 Extrait de compte GP]
    style T890 fill:#58a6ff
    NONE[Aucun callee]
    T890 -.-> NONE
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
| Lignes de logique | 27 | Programme compact |
| Expressions | 7 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 27) | Code sain |
| Regles metier | 1 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Calcul (1 tache: 1 ecran, 0 traitement)

- **Strategie** : Services de calcul purs (Domain Services).
- Migrer la logique de calcul (stock, compteurs, montants)

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 14:56*
