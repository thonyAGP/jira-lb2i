# VIL IDE 73 - Print versements/retraits

> **Analyse**: Phases 1-4 2026-02-03 09:08 -> 09:08 (23s) | Assemblage 09:08
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | VIL |
| IDE Position | 73 |
| Nom Programme | Print versements/retraits |
| Fichier source | `Prg_73.xml` |
| Domaine metier | Impression |
| Taches | 1 (1 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Print versements/retraits** assure la gestion complete de ce processus, accessible depuis [CV Menu Resultat comptable (IDE 37)](VIL-IDE-37.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

**Logique metier** : 4 regles identifiees couvrant conditions metier.

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>73 - Veuillez patienter .... [[ECRAN]](#ecran-t1)

**Role** : Traitement : Veuillez patienter .....
**Ecran** : 426 x 57 DLU (MDI) | [Voir mockup](#ecran-t1)


## 5. REGLES METIER

4 regles identifiees:

### Autres (4 regles)

#### <a id="rm-RM-001"></a>[RM-001] Si [T]='A' alors 'annul' sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `[T]='A'` |
| **Si vrai** | 'annul' |
| **Si faux** | '') |
| **Expression source** | Expression 9 : `IF ([T]='A','annul','')` |
| **Exemple** | Si [T]='A' â†’ 'annul'. Sinon â†’ '') |

#### <a id="rm-RM-002"></a>[RM-002] Traitement conditionnel si [V]> est a zero

| Element | Detail |
|---------|--------|
| **Condition** | `[V]>=0` |
| **Si vrai** | [V] |
| **Si faux** | 0) |
| **Expression source** | Expression 10 : `IF ([V]>=0,[V],0)` |
| **Exemple** | Si [V]>=0 â†’ [V]. Sinon â†’ 0) |

#### <a id="rm-RM-003"></a>[RM-003] Si [V]<0 alors ABS ([V]) sinon 0)

| Element | Detail |
|---------|--------|
| **Condition** | `[V]<0` |
| **Si vrai** | ABS ([V]) |
| **Si faux** | 0) |
| **Expression source** | Expression 11 : `IF ([V]<0,ABS ([V]),0)` |
| **Exemple** | Si [V]<0 â†’ ABS ([V]). Sinon â†’ 0) |

#### <a id="rm-RM-004"></a>[RM-004] Si P0 Uni/Bi [F]<>'B' alors [Y] sinon [AB])

| Element | Detail |
|---------|--------|
| **Condition** | `P0 Uni/Bi [F]<>'B'` |
| **Si vrai** | [Y] |
| **Si faux** | [AB]) |
| **Variables** | F (P0 Uni/Bi) |
| **Expression source** | Expression 27 : `IF(P0 Uni/Bi [F]<>'B',[Y],[AB])` |
| **Exemple** | Si P0 Uni/Bi [F]<>'B' â†’ [Y]. Sinon â†’ [AB]) |

## 6. CONTEXTE

- **Appele par**: [CV Menu Resultat comptable (IDE 37)](VIL-IDE-37.md)
- **Appelle**: 0 programmes | **Tables**: 4 (W:0 R:1 L:3) | **Taches**: 1 | **Expressions**: 27

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 1)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 73 | 73 | Veuillez patienter .... | MDI | 426 | 57 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>73 - Veuillez patienter ....
**Tache** : [73](#t1) | **Type** : MDI | **Dimensions** : 426 x 57 DLU
**Bloc** : Traitement | **Titre IDE** : Veuillez patienter ....

<!-- FORM-DATA:
{
    "width":  426,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  1,
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
                         "x":  118,
                         "type":  "label",
                         "var":  "",
                         "y":  10,
                         "w":  275,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "7",
                         "text":  "Impression en cours",
                         "parent":  null
                     },
                     {
                         "x":  1,
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
                         "x":  73,
                         "type":  "label",
                         "var":  "",
                         "y":  39,
                         "w":  285,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Impression  versement/retrait",
                         "parent":  null
                     },
                     {
                         "x":  2,
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
    "taskId":  "73",
    "height":  57
}
-->

## 9. NAVIGATION

Ecran unique: **Veuillez patienter ....**

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **73.1** | [**Veuillez patienter ....** (73)](#t1) [mockup](#ecran-t1) | MDI | 426x57 | Traitement |

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

### Tables utilisees (4)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 30 | gm-recherche_____gmr | Index de recherche | DB | R |   |   | 1 |
| 40 | comptable________cte |  | DB |   |   | L | 1 |
| 89 | moyen_paiement___mop |  | DB |   |   | L | 1 |
| 140 | moyen_paiement___mop |  | DB |   |   | L | 1 |

### Colonnes par table (2 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 30 - gm-recherche_____gmr (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P0 societe | R | Alpha |
| B | P0 masque cumul | R | Alpha |
| C | P0 date comptable | R | Date |
| D | P0 top exec V/R | R | Alpha |
| E | P0 nom village | R | Alpha |
| F | P0 Uni/Bi | R | Alpha |
| G | W0 montant credit | R | Numeric |
| H | W0 montant debit | R | Numeric |
| I | W0 date listing | R | Date |
| J | W0 heure listing | R | Time |
| K | W0 nom village | R | Alpha |
| L | W0 config imp | R | Alpha |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (6)

Variables recues du programme appelant ([CV Menu Resultat comptable (IDE 37)](VIL-IDE-37.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P0 societe | Alpha | 1x parametre entrant |
| B | P0 masque cumul | Alpha | 1x parametre entrant |
| C | P0 date comptable | Date | 2x parametre entrant |
| D | P0 top exec V/R | Alpha | - |
| E | P0 nom village | Alpha | - |
| F | P0 Uni/Bi | Alpha | 3x parametre entrant |

### 11.2 Variables de travail (6)

Variables internes au programme.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| G | W0 montant credit | Numeric | 1x calcul interne |
| H | W0 montant debit | Numeric | 2x calcul interne |
| I | W0 date listing | Date | - |
| J | W0 heure listing | Time | - |
| K | W0 nom village | Alpha | - |
| L | W0 config imp | Alpha | - |

## 12. EXPRESSIONS

**27 / 27 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCULATION | 2 | 0 |
| CONCATENATION | 2 | 0 |
| CONDITION | 10 | 4 |
| CONSTANTE | 1 | 0 |
| DATE | 1 | 0 |
| OTHER | 11 | 0 |

### 12.2 Expressions cles par type

#### CALCULATION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 14 | `W0 montant debit [H]+[V]` | - |
| CALCULATION | 13 | `W0 montant credit [G]+[V]` | - |

#### CONCATENATION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 23 | `MlsTrans ('LISTING VERSEMENTS / RETRAITS DU')&' '&DStr (P0 date comptable [C],'DD/MM/YYYY')` | - |
| CONCATENATION | 21 | `'- '&Str (Page (0,1),'3P0Z0')&' -'` | - |

#### CONDITION (10 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 11 | `IF ([V]<0,ABS ([V]),0)` | [RM-003](#rm-RM-003) |
| CONDITION | 27 | `IF(P0 Uni/Bi [F]<>'B',[Y],[AB])` | [RM-004](#rm-RM-004) |
| CONDITION | 9 | `IF ([T]='A','annul','')` | [RM-001](#rm-RM-001) |
| CONDITION | 10 | `IF ([V]>=0,[V],0)` | [RM-002](#rm-RM-002) |
| CONDITION | 24 | `[N]='S' AND [Z]='$CASH' OR [N]='V' AND ([Z]='$CASH' OR [Z]='$PAPER' OR [Z]='$CARD')` | - |
| ... | | *+5 autres* | |

#### CONSTANTE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 19 | `'O'` | - |

#### DATE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| DATE | 17 | `Date ()` | - |

#### OTHER (11 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 8 | `[Q]` | - |
| OTHER | 7 | `[P]` | - |
| OTHER | 12 | `ABS (W0 montant debit [H])` | - |
| OTHER | 20 | `[U]` | - |
| OTHER | 18 | `Time ()` | - |
| ... | | *+6 autres* | |

### 12.3 Toutes les expressions (27)

<details>
<summary>Voir les 27 expressions</summary>

#### CALCULATION (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 13 | `W0 montant credit [G]+[V]` |
| 14 | `W0 montant debit [H]+[V]` |

#### CONCATENATION (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 21 | `'- '&Str (Page (0,1),'3P0Z0')&' -'` |
| 23 | `MlsTrans ('LISTING VERSEMENTS / RETRAITS DU')&' '&DStr (P0 date comptable [C],'DD/MM/YYYY')` |

#### CONDITION (10)

| IDE | Expression Decodee |
|-----|-------------------|
| 9 | `IF ([T]='A','annul','')` |
| 10 | `IF ([V]>=0,[V],0)` |
| 11 | `IF ([V]<0,ABS ([V]),0)` |
| 27 | `IF(P0 Uni/Bi [F]<>'B',[Y],[AB])` |
| 15 | `[V]>=0` |
| 16 | `[V]<0` |
| 22 | `INIGet ('[MAGIC_LOGICAL_NAMES]preview')='O'` |
| 24 | `[N]='S' AND [Z]='$CASH' OR [N]='V' AND ([Z]='$CASH' OR [Z]='$PAPER' OR [Z]='$CARD')` |
| 25 | `P0 Uni/Bi [F]<>'B'` |
| 26 | `P0 Uni/Bi [F]='B'` |

#### CONSTANTE (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 19 | `'O'` |

#### DATE (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 17 | `Date ()` |

#### OTHER (11)

| IDE | Expression Decodee |
|-----|-------------------|
| 1 | `GetParam ('DTCLOSURE')` |
| 2 | `SetCrsr (1)` |
| 3 | `SetCrsr (2)` |
| 4 | `P0 societe [A]` |
| 5 | `P0 masque cumul [B]` |
| 6 | `P0 date comptable [C]` |
| 7 | `[P]` |
| 8 | `[Q]` |
| 12 | `ABS (W0 montant debit [H])` |
| 18 | `Time ()` |
| 20 | `[U]` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [CV Menu Resultat comptable (IDE 37)](VIL-IDE-37.md) -> **Print versements/retraits (IDE 73)**

```mermaid
graph LR
    T73[73 Print versementsret...]
    style T73 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC78[78 Lance correspittivi]
    style CC78 fill:#8b5cf6
    CC148[148 CV Menu caisse vil...]
    style CC148 fill:#f59e0b
    CC36[36 CV Menu Clôture de ...]
    style CC36 fill:#f59e0b
    CC37[37 CV Menu Resultat co...]
    style CC37 fill:#3fb950
    CC36 --> CC37
    CC148 --> CC36
    CC1 --> CC148
    CC78 --> CC148
    CC37 --> T73
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [37](VIL-IDE-37.md) | CV Menu Resultat comptable | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T73[73 Print versementsret...]
    style T73 fill:#58a6ff
    NONE[Aucun callee]
    T73 -.-> NONE
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
| Lignes de logique | 59 | Programme compact |
| Expressions | 27 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 59) | Code sain |
| Regles metier | 4 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 1 ecran, 0 traitement)

- **Strategie** : 1 composant(s) UI (Razor/React) avec formulaires et validation.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 09:08*
