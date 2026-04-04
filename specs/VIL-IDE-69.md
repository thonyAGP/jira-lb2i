# VIL IDE 69 - Print listing OD manuels

> **Analyse**: Phases 1-4 2026-02-03 09:06 -> 09:06 (21s) | Assemblage 09:06
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | VIL |
| IDE Position | 69 |
| Nom Programme | Print listing OD manuels |
| Fichier source | `Prg_69.xml` |
| Domaine metier | Impression |
| Taches | 1 (1 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Print listing OD manuels** assure la gestion complete de ce processus, accessible depuis [CV Menu Resultat comptable (IDE 37)](VIL-IDE-37.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

**Logique metier** : 8 regles identifiees couvrant conditions metier.

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>69 - (sans nom) [[ECRAN]](#ecran-t1)

**Role** : Traitement interne.
**Ecran** : 422 x 57 DLU (MDI) | [Voir mockup](#ecran-t1)


## 5. REGLES METIER

8 regles identifiees:

### Autres (8 regles)

#### <a id="rm-RM-001"></a>[RM-001] Traitement conditionnel si P0 imputation [D] est a zero

| Element | Detail |
|---------|--------|
| **Condition** | `P0 imputation [D]=0` |
| **Si vrai** | 9999999999 |
| **Si faux** | P0 imputation [D]) |
| **Variables** | D (P0 imputation) |
| **Expression source** | Expression 10 : `IF (P0 imputation [D]=0,9999999999,P0 imputation [D])` |
| **Exemple** | Si P0 imputation [D]=0 â†’ 9999999999. Sinon â†’ P0 imputation [D]) |

#### <a id="rm-RM-002"></a>[RM-002] Si [X]='A' alors MlsTrans ('annul') sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `[X]='A'` |
| **Si vrai** | MlsTrans ('annul') |
| **Si faux** | '') |
| **Expression source** | Expression 12 : `IF ([X]='A',MlsTrans ('annul'),'')` |
| **Exemple** | Si [X]='A' â†’ MlsTrans ('annul'). Sinon â†’ '') |

#### <a id="rm-RM-003"></a>[RM-003] Traitement conditionnel si [Y]> est a zero

| Element | Detail |
|---------|--------|
| **Condition** | `[Y]>=0` |
| **Si vrai** | [Y] |
| **Si faux** | 0) |
| **Expression source** | Expression 13 : `IF ([Y]>=0,[Y],0)` |
| **Exemple** | Si [Y]>=0 â†’ [Y]. Sinon â†’ 0) |

#### <a id="rm-RM-004"></a>[RM-004] Si [Y]<0 alors ABS ([Y]) sinon 0)

| Element | Detail |
|---------|--------|
| **Condition** | `[Y]<0` |
| **Si vrai** | ABS ([Y]) |
| **Si faux** | 0) |
| **Expression source** | Expression 14 : `IF ([Y]<0,ABS ([Y]),0)` |
| **Exemple** | Si [Y]<0 â†’ ABS ([Y]). Sinon â†’ 0) |

#### <a id="rm-RM-005"></a>[RM-005] Traitement conditionnel si W0 total general [M]> est a zero

| Element | Detail |
|---------|--------|
| **Condition** | `W0 total general [M]>=0` |
| **Si vrai** | W0 total general [M] |
| **Si faux** | 0) |
| **Variables** | M (W0 total general) |
| **Expression source** | Expression 27 : `IF (W0 total general [M]>=0,W0 total general [M],0)` |
| **Exemple** | Si W0 total general [M]>=0 â†’ W0 total general [M]. Sinon â†’ 0) |

#### <a id="rm-RM-006"></a>[RM-006] Si W0 total general [M]<0 alors ABS (W0 total general [M]) sinon 0)

| Element | Detail |
|---------|--------|
| **Condition** | `W0 total general [M]<0` |
| **Si vrai** | ABS (W0 total general [M]) |
| **Si faux** | 0) |
| **Variables** | M (W0 total general) |
| **Expression source** | Expression 28 : `IF (W0 total general [M]<0,ABS (W0 total general [M]),0)` |
| **Exemple** | Si W0 total general [M]<0 â†’ ABS (W0 total general [M]). Sinon â†’ 0) |

#### <a id="rm-RM-007"></a>[RM-007] Si W0 cumul cr ss-imput [I]<>0 AND W0 cumul db ss-imput [J]<>0 alors IF (W0 cumul cr ss-imput [I]+W0 cumul db ss-imput [J]<0 sinon '(DB '&LTrim (RTrim (Str (ABS (W0 cumul cr ss-imput [I]+W0 cumul db ss-imput [J]),P0 masque cumul [B])))&')','(CR '&LTrim (RTrim (Str (ABS (W0 cumul cr ss-imput [I]+W0 cumul db ss-imput [J]),P0 masque cumul [B])))&')'),Fill ('.',22))

| Element | Detail |
|---------|--------|
| **Condition** | `W0 cumul cr ss-imput [I]<>0 AND W0 cumul db ss-imput [J]<>0` |
| **Si vrai** | IF (W0 cumul cr ss-imput [I]+W0 cumul db ss-imput [J]<0 |
| **Si faux** | '(DB '&LTrim (RTrim (Str (ABS (W0 cumul cr ss-imput [I]+W0 cumul db ss-imput [J]),P0 masque cumul [B])))&')','(CR '&LTrim (RTrim (Str (ABS (W0 cumul cr ss-imput [I]+W0 cumul db ss-imput [J]),P0 masque cumul [B])))&')'),Fill ('.',22)) |
| **Variables** | B (P0 masque cumul), I (W0 cumul cr ss-imput), J (W0 cumul db ss-imput) |
| **Expression source** | Expression 29 : `IF (W0 cumul cr ss-imput [I]<>0 AND W0 cumul db ss-imput [J]` |
| **Exemple** | Si W0 cumul cr ss-imput [I]<>0 AND W0 cumul db ss-imput [J]<>0 â†’ IF (W0 cumul cr ss-imput [I]+W0 cumul db ss-imput [J]<0 |

#### <a id="rm-RM-008"></a>[RM-008] Si W0 cumul cr imput [K]<>0 AND W0 cumul db imput [L]<>0 alors IF (W0 cumul cr imput [K]+W0 cumul db imput [L]<0 sinon '(DB '&LTrim (RTrim (Str (ABS (W0 cumul cr imput [K]+W0 cumul db imput [L]),P0 masque cumul [B])))&')','(CR '&LTrim (RTrim (Str (ABS (W0 cumul cr imput [K]+W0 cumul db imput [L]),P0 masque cumul [B])))&')'),Fill ('.',22))

| Element | Detail |
|---------|--------|
| **Condition** | `W0 cumul cr imput [K]<>0 AND W0 cumul db imput [L]<>0` |
| **Si vrai** | IF (W0 cumul cr imput [K]+W0 cumul db imput [L]<0 |
| **Si faux** | '(DB '&LTrim (RTrim (Str (ABS (W0 cumul cr imput [K]+W0 cumul db imput [L]),P0 masque cumul [B])))&')','(CR '&LTrim (RTrim (Str (ABS (W0 cumul cr imput [K]+W0 cumul db imput [L]),P0 masque cumul [B])))&')'),Fill ('.',22)) |
| **Variables** | B (P0 masque cumul), K (W0 cumul cr imput), L (W0 cumul db imput) |
| **Expression source** | Expression 30 : `IF (W0 cumul cr imput [K]<>0 AND W0 cumul db imput [L]<>0,IF` |
| **Exemple** | Si W0 cumul cr imput [K]<>0 AND W0 cumul db imput [L]<>0 â†’ IF (W0 cumul cr imput [K]+W0 cumul db imput [L]<0 |

## 6. CONTEXTE

- **Appele par**: [CV Menu Resultat comptable (IDE 37)](VIL-IDE-37.md)
- **Appelle**: 0 programmes | **Tables**: 2 (W:0 R:1 L:1) | **Taches**: 1 | **Expressions**: 32

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 1)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 69 | 69 | (sans nom) | MDI | 422 | 57 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>69 - (sans nom)
**Tache** : [69](#t1) | **Type** : MDI | **Dimensions** : 422 x 57 DLU
**Bloc** : Traitement | **Titre IDE** : (sans nom)

<!-- FORM-DATA:
{
    "width":  422,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  1,
                         "w":  423,
                         "fmt":  "",
                         "name":  "",
                         "h":  29,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  117,
                         "type":  "label",
                         "var":  "",
                         "y":  11,
                         "w":  275,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "7",
                         "text":  "Impression en cours",
                         "parent":  null
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  30,
                         "w":  423,
                         "fmt":  "",
                         "name":  "",
                         "h":  27,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  62,
                         "type":  "label",
                         "var":  "",
                         "y":  40,
                         "w":  298,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Impression listing OD manuels",
                         "parent":  null
                     },
                     {
                         "x":  1,
                         "type":  "image",
                         "var":  "",
                         "y":  3,
                         "w":  72,
                         "fmt":  "",
                         "name":  "",
                         "h":  25,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "69",
    "height":  57
}
-->

## 9. NAVIGATION

Ecran unique: ****

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **69.1** | [**(sans nom)** (69)](#t1) [mockup](#ecran-t1) | MDI | 422x57 | Traitement |

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

### Tables utilisees (2)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 30 | gm-recherche_____gmr | Index de recherche | DB | R |   |   | 1 |
| 40 | comptable________cte |  | DB |   |   | L | 1 |

### Colonnes par table (2 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 30 - gm-recherche_____gmr (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P0 societe | R | Alpha |
| B | P0 masque cumul | R | Alpha |
| C | P0 date comptable | R | Date |
| D | P0 imputation | R | Numeric |
| E | P0 nom village | R | Alpha |
| F | W0 config imp. | R | Alpha |
| G | W0 date listing | R | Date |
| H | W0 heure listing | R | Time |
| I | W0 cumul cr ss-imput | R | Numeric |
| J | W0 cumul db ss-imput | R | Numeric |
| K | W0 cumul cr imput | R | Numeric |
| L | W0 cumul db imput | R | Numeric |
| M | W0 total general | R | Numeric |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (5)

Variables recues du programme appelant ([CV Menu Resultat comptable (IDE 37)](VIL-IDE-37.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P0 societe | Alpha | 1x parametre entrant |
| B | P0 masque cumul | Alpha | 3x parametre entrant |
| C | P0 date comptable | Date | 1x parametre entrant |
| D | P0 imputation | Numeric | 2x parametre entrant |
| E | P0 nom village | Alpha | - |

### 11.2 Variables de travail (8)

Variables internes au programme.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| F | W0 config imp. | Alpha | - |
| G | W0 date listing | Date | - |
| H | W0 heure listing | Time | - |
| I | W0 cumul cr ss-imput | Numeric | 2x calcul interne |
| J | W0 cumul db ss-imput | Numeric | 3x calcul interne |
| K | W0 cumul cr imput | Numeric | 2x calcul interne |
| L | W0 cumul db imput | Numeric | 3x calcul interne |
| M | W0 total general | Numeric | 3x calcul interne |

## 12. EXPRESSIONS

**32 / 32 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCULATION | 5 | 0 |
| CONCATENATION | 3 | 2 |
| CONDITION | 9 | 6 |
| CONSTANTE | 2 | 0 |
| DATE | 1 | 0 |
| OTHER | 12 | 0 |

### 12.2 Expressions cles par type

#### CALCULATION (5 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 25 | `W0 cumul db imput [L]+[Y]` | - |
| CALCULATION | 26 | `W0 total general [M]+[Y]` | - |
| CALCULATION | 24 | `W0 cumul cr imput [K]+[Y]` | - |
| CALCULATION | 20 | `W0 cumul cr ss-imput [I]+[Y]` | - |
| CALCULATION | 22 | `W0 cumul db ss-imput [J]+[Y]` | - |

#### CONCATENATION (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 30 | `IF (W0 cumul cr imput [K]<>0 AND W0 cumul db imput [L]<>0,IF (W0 cumul cr imput [K]+W0 cumul db imput [L]<0,'(DB '&LTrim (RTrim (Str (ABS (W0 cumul cr imput [K]+W0 cumul db imput [L]),P0 masque cumul [B])))&')','(CR '&LTrim (RTrim (Str (ABS (W0 cumul cr imput [K]+W0 cumul db imput [L]),P0 masque cumul [B])))&')'),Fill ('.',22))` | [RM-008](#rm-RM-008) |
| CONCATENATION | 29 | `IF (W0 cumul cr ss-imput [I]<>0 AND W0 cumul db ss-imput [J]<>0,IF (W0 cumul cr ss-imput [I]+W0 cumul db ss-imput [J]<0,'(DB '&LTrim (RTrim (Str (ABS (W0 cumul cr ss-imput [I]+W0 cumul db ss-imput [J]),P0 masque cumul [B])))&')','(CR '&LTrim (RTrim (Str (ABS (W0 cumul cr ss-imput [I]+W0 cumul db ss-imput [J]),P0 masque cumul [B])))&')'),Fill ('.',22))` | [RM-007](#rm-RM-007) |
| CONCATENATION | 32 | `'- '&Str (Page (0,1),'3P0Z0')&' -'` | - |

#### CONDITION (9 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 14 | `IF ([Y]<0,ABS ([Y]),0)` | [RM-004](#rm-RM-004) |
| CONDITION | 27 | `IF (W0 total general [M]>=0,W0 total general [M],0)` | [RM-005](#rm-RM-005) |
| CONDITION | 28 | `IF (W0 total general [M]<0,ABS (W0 total general [M]),0)` | [RM-006](#rm-RM-006) |
| CONDITION | 10 | `IF (P0 imputation [D]=0,9999999999,P0 imputation [D])` | [RM-001](#rm-RM-001) |
| CONDITION | 12 | `IF ([X]='A',MlsTrans ('annul'),'')` | [RM-002](#rm-RM-002) |
| ... | | *+4 autres* | |

#### CONSTANTE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 19 | `0` | - |
| CONSTANTE | 8 | `'M'` | - |

#### DATE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| DATE | 5 | `Date ()` | - |

#### OTHER (12 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 15 | `ABS (W0 cumul db ss-imput [J])` | - |
| OTHER | 11 | `P0 masque cumul [B]` | - |
| OTHER | 9 | `P0 imputation [D]` | - |
| OTHER | 18 | `[R]` | - |
| OTHER | 17 | `[Q]` | - |
| ... | | *+7 autres* | |

### 12.3 Toutes les expressions (32)

<details>
<summary>Voir les 32 expressions</summary>

#### CALCULATION (5)

| IDE | Expression Decodee |
|-----|-------------------|
| 20 | `W0 cumul cr ss-imput [I]+[Y]` |
| 22 | `W0 cumul db ss-imput [J]+[Y]` |
| 24 | `W0 cumul cr imput [K]+[Y]` |
| 25 | `W0 cumul db imput [L]+[Y]` |
| 26 | `W0 total general [M]+[Y]` |

#### CONCATENATION (3)

| IDE | Expression Decodee |
|-----|-------------------|
| 32 | `'- '&Str (Page (0,1),'3P0Z0')&' -'` |
| 29 | `IF (W0 cumul cr ss-imput [I]<>0 AND W0 cumul db ss-imput [J]<>0,IF (W0 cumul cr ss-imput [I]+W0 cumul db ss-imput [J]<0,'(DB '&LTrim (RTrim (Str (ABS (W0 cumul cr ss-imput [I]+W0 cumul db ss-imput [J]),P0 masque cumul [B])))&')','(CR '&LTrim (RTrim (Str (ABS (W0 cumul cr ss-imput [I]+W0 cumul db ss-imput [J]),P0 masque cumul [B])))&')'),Fill ('.',22))` |
| 30 | `IF (W0 cumul cr imput [K]<>0 AND W0 cumul db imput [L]<>0,IF (W0 cumul cr imput [K]+W0 cumul db imput [L]<0,'(DB '&LTrim (RTrim (Str (ABS (W0 cumul cr imput [K]+W0 cumul db imput [L]),P0 masque cumul [B])))&')','(CR '&LTrim (RTrim (Str (ABS (W0 cumul cr imput [K]+W0 cumul db imput [L]),P0 masque cumul [B])))&')'),Fill ('.',22))` |

#### CONDITION (9)

| IDE | Expression Decodee |
|-----|-------------------|
| 10 | `IF (P0 imputation [D]=0,9999999999,P0 imputation [D])` |
| 12 | `IF ([X]='A',MlsTrans ('annul'),'')` |
| 13 | `IF ([Y]>=0,[Y],0)` |
| 14 | `IF ([Y]<0,ABS ([Y]),0)` |
| 27 | `IF (W0 total general [M]>=0,W0 total general [M],0)` |
| 28 | `IF (W0 total general [M]<0,ABS (W0 total general [M]),0)` |
| 21 | `[Y]>=0` |
| 23 | `[Y]<0` |
| 31 | `INIGet ('[MAGIC_LOGICAL_NAMES]preview')='O'` |

#### CONSTANTE (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 8 | `'M'` |
| 19 | `0` |

#### DATE (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 5 | `Date ()` |

#### OTHER (12)

| IDE | Expression Decodee |
|-----|-------------------|
| 1 | `GetParam ('DTCLOSURE')` |
| 2 | `SetCrsr (1)` |
| 3 | `SetCrsr (2)` |
| 4 | `P0 societe [A]` |
| 6 | `Time ()` |
| 7 | `P0 date comptable [C]` |
| 9 | `P0 imputation [D]` |
| 11 | `P0 masque cumul [B]` |
| 15 | `ABS (W0 cumul db ss-imput [J])` |
| 16 | `ABS (W0 cumul db imput [L])` |
| 17 | `[Q]` |
| 18 | `[R]` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [CV Menu Resultat comptable (IDE 37)](VIL-IDE-37.md) -> **Print listing OD manuels (IDE 69)**

```mermaid
graph LR
    T69[69 Print listing OD ma...]
    style T69 fill:#58a6ff
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
    CC37 --> T69
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [37](VIL-IDE-37.md) | CV Menu Resultat comptable | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T69[69 Print listing OD ma...]
    style T69 fill:#58a6ff
    NONE[Aucun callee]
    T69 -.-> NONE
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
| Lignes de logique | 62 | Programme compact |
| Expressions | 32 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 62) | Code sain |
| Regles metier | 8 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 1 ecran, 0 traitement)

- **Strategie** : 1 composant(s) UI (Razor/React) avec formulaires et validation.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 09:06*
