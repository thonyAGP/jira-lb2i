# VIL IDE 67 - Print Ecart

> **Analyse**: Phases 1-4 2026-02-03 09:05 -> 09:05 (21s) | Assemblage 09:05
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | VIL |
| IDE Position | 67 |
| Nom Programme | Print Ecart |
| Fichier source | `Prg_67.xml` |
| Domaine metier | Impression |
| Taches | 1 (1 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Print Ecart** assure la gestion complete de ce processus, accessible depuis [    Listings cloture HTML (IDE 29)](VIL-IDE-29.md), [CV  Verification caisse (IDE 39)](VIL-IDE-39.md), [Liste des ecarts (IDE 101)](VIL-IDE-101.md), [    Listings cloture HTML (IDE 192)](VIL-IDE-192.md), [CV  Verification caisse (IDE 216)](VIL-IDE-216.md), [    Listings cloture HTML (IDE 219)](VIL-IDE-219.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

**Logique metier** : 2 regles identifiees couvrant conditions metier.

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>67 - Veuillez patienter ....... [[ECRAN]](#ecran-t1)

**Role** : Traitement : Veuillez patienter ........
**Ecran** : 426 x 56 DLU (MDI) | [Voir mockup](#ecran-t1)


## 5. REGLES METIER

2 regles identifiees:

### Autres (2 regles)

#### <a id="rm-RM-001"></a>[RM-001] Si P0 TRI cle 2 ou 3 [D]=2 alors MlsTrans ('DATE COMPTABLE') sinon MlsTrans ('DATE GENERATION'))

| Element | Detail |
|---------|--------|
| **Condition** | `P0 TRI cle 2 ou 3 [D]=2` |
| **Si vrai** | MlsTrans ('DATE COMPTABLE') |
| **Si faux** | MlsTrans ('DATE GENERATION')) |
| **Variables** | D (P0 TRI cle 2 ou 3) |
| **Expression source** | Expression 4 : `IF (P0 TRI cle 2 ou 3 [D]=2,MlsTrans ('DATE COMPTABLE'),MlsT` |
| **Exemple** | Si P0 TRI cle 2 ou 3 [D]=2 â†’ MlsTrans ('DATE COMPTABLE'). Sinon â†’ MlsTrans ('DATE GENERATION')) |

#### <a id="rm-RM-002"></a>[RM-002] Condition toujours vraie (flag actif)

| Element | Detail |
|---------|--------|
| **Condition** | `P0 selection [H]=MlsTrans ('Reception')` |
| **Si vrai** | [S]='O' OR [S]='F' |
| **Si faux** | IF (P0 selection [H]=MlsTrans ('Coffre'),[S]='C','TRUE'LOG)) |
| **Variables** | H (P0 selection) |
| **Expression source** | Expression 17 : `IF (P0 selection [H]=MlsTrans ('Reception'),[S]='O' OR [S]='` |
| **Exemple** | Si P0 selection [H]=MlsTrans ('Reception') â†’ [S]='O' OR [S]='F' |

## 6. CONTEXTE

- **Appele par**: [    Listings cloture HTML (IDE 29)](VIL-IDE-29.md), [CV  Verification caisse (IDE 39)](VIL-IDE-39.md), [Liste des ecarts (IDE 101)](VIL-IDE-101.md), [    Listings cloture HTML (IDE 192)](VIL-IDE-192.md), [CV  Verification caisse (IDE 216)](VIL-IDE-216.md), [    Listings cloture HTML (IDE 219)](VIL-IDE-219.md)
- **Appelle**: 0 programmes | **Tables**: 1 (W:0 R:1 L:0) | **Taches**: 1 | **Expressions**: 21

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 1)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 67 | 67 | Veuillez patienter ....... | MDI | 426 | 56 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>67 - Veuillez patienter .......
**Tache** : [67](#t1) | **Type** : MDI | **Dimensions** : 426 x 56 DLU
**Bloc** : Traitement | **Titre IDE** : Veuillez patienter .......

<!-- FORM-DATA:
{
    "width":  426,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  3,
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
                         "w":  275,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "7",
                         "text":  "Impression en cours",
                         "parent":  null
                     },
                     {
                         "x":  3,
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
                         "x":  75,
                         "type":  "label",
                         "var":  "",
                         "y":  39,
                         "w":  331,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Impression listing gratuites bar GO",
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
    "taskId":  "67",
    "height":  56
}
-->

## 9. NAVIGATION

Ecran unique: **Veuillez patienter .......**

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **67.1** | [**Veuillez patienter .......** (67)](#t1) [mockup](#ecran-t1) | MDI | 426x56 | Traitement |

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
| 234 | ecarts |  | DB | R |   |   | 1 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 234 - ecarts (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P0 societe | R | Alpha |
| B | P0 masque cumul | R | Alpha |
| C | P0 nom du village | R | Alpha |
| D | P0 TRI cle 2 ou 3 | R | Numeric |
| E | P0 date 1 | R | Date |
| F | P0 date 2 | R | Date |
| G | P0 edition cloture auto | R | Logical |
| H | P0 selection | R | Alpha |
| I | W0 Total ecart | R | Numeric |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (8)

Variables recues du programme appelant ([    Listings cloture HTML (IDE 29)](VIL-IDE-29.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P0 societe | Alpha | - |
| B | P0 masque cumul | Alpha | 1x parametre entrant |
| C | P0 nom du village | Alpha | - |
| D | P0 TRI cle 2 ou 3 | Numeric | 6x parametre entrant |
| E | P0 date 1 | Date | 3x parametre entrant |
| F | P0 date 2 | Date | 2x parametre entrant |
| G | P0 edition cloture auto | Logical | 2x parametre entrant |
| H | P0 selection | Alpha | 2x parametre entrant |

### 11.2 Variables de travail (1)

Variables internes au programme.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| I | W0 Total ecart | Numeric | 1x calcul interne |

## 12. EXPRESSIONS

**21 / 21 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCULATION | 1 | 0 |
| CONCATENATION | 3 | 0 |
| CONDITION | 7 | 5 |
| CAST_LOGIQUE | 1 | 5 |
| OTHER | 9 | 0 |

### 12.2 Expressions cles par type

#### CALCULATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 9 | `W0 Total ecart [I]+[R]` | - |

#### CONCATENATION (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 19 | `Trim (INIGet ('[MAGIC_LOGICAL_NAMES]club_exportdata')&'Cloture\Editions\Ecarts'&IF (P0 edition cloture auto [G],'_'&DStr (P0 date 1 [E],'YYYYMMDD'),'')&'.htm')` | - |
| CONCATENATION | 5 | `DStr (Date (),'DD/MM/YYYY')&' - '&TStr (Time (),'HH:MM:SS')` | - |
| CONCATENATION | 11 | `'- '&Str (Page (0,1),'3P0Z0')&' -'` | - |

#### CONDITION (7 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 4 | `IF (P0 TRI cle 2 ou 3 [D]=2,MlsTrans ('DATE COMPTABLE'),MlsTrans ('DATE GENERATION'))` | [RM-001](#rm-RM-001) |
| CONDITION | 14 | `CndRange (P0 TRI cle 2 ou 3 [D]=2,P0 date 2 [F])` | - |
| CONDITION | 15 | `CndRange (P0 TRI cle 2 ou 3 [D]=3,P0 date 1 [E])` | - |
| CONDITION | 16 | `CndRange (P0 TRI cle 2 ou 3 [D]=3,P0 date 2 [F])` | - |
| CONDITION | 10 | `INIGet ('[MAGIC_LOGICAL_NAMES]preview')='O'` | - |
| ... | | *+2 autres* | |

#### CAST_LOGIQUE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 17 | `IF (P0 selection [H]=MlsTrans ('Reception'),[S]='O' OR [S]='F',IF (P0 selection [H]=MlsTrans ('Coffre'),[S]='C','TRUE'LOG))` | [RM-002](#rm-RM-002) |

#### OTHER (9 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 18 | `P0 selection [H]` | - |
| OTHER | 8 | `P0 masque cumul [B]` | - |
| OTHER | 21 | `GetParam ('DTCLOSURE')` | - |
| OTHER | 20 | `P0 edition cloture auto [G]` | - |
| OTHER | 7 | `SetCrsr (2)` | - |
| ... | | *+4 autres* | |

### 12.3 Toutes les expressions (21)

<details>
<summary>Voir les 21 expressions</summary>

#### CALCULATION (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 9 | `W0 Total ecart [I]+[R]` |

#### CONCATENATION (3)

| IDE | Expression Decodee |
|-----|-------------------|
| 11 | `'- '&Str (Page (0,1),'3P0Z0')&' -'` |
| 5 | `DStr (Date (),'DD/MM/YYYY')&' - '&TStr (Time (),'HH:MM:SS')` |
| 19 | `Trim (INIGet ('[MAGIC_LOGICAL_NAMES]club_exportdata')&'Cloture\Editions\Ecarts'&IF (P0 edition cloture auto [G],'_'&DStr (P0 date 1 [E],'YYYYMMDD'),'')&'.htm')` |

#### CONDITION (7)

| IDE | Expression Decodee |
|-----|-------------------|
| 4 | `IF (P0 TRI cle 2 ou 3 [D]=2,MlsTrans ('DATE COMPTABLE'),MlsTrans ('DATE GENERATION'))` |
| 10 | `INIGet ('[MAGIC_LOGICAL_NAMES]preview')='O'` |
| 12 | `MlsTrans (IF ([S]='C','Coffre','Reception'))` |
| 13 | `CndRange (P0 TRI cle 2 ou 3 [D]=2,P0 date 1 [E])` |
| 14 | `CndRange (P0 TRI cle 2 ou 3 [D]=2,P0 date 2 [F])` |
| 15 | `CndRange (P0 TRI cle 2 ou 3 [D]=3,P0 date 1 [E])` |
| 16 | `CndRange (P0 TRI cle 2 ou 3 [D]=3,P0 date 2 [F])` |

#### CAST_LOGIQUE (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 17 | `IF (P0 selection [H]=MlsTrans ('Reception'),[S]='O' OR [S]='F',IF (P0 selection [H]=MlsTrans ('Coffre'),[S]='C','TRUE'LOG))` |

#### OTHER (9)

| IDE | Expression Decodee |
|-----|-------------------|
| 1 | `P0 TRI cle 2 ou 3 [D]` |
| 2 | `MlsTrans ('Selection dates :')` |
| 3 | `MlsTrans ('Selection lieu :')` |
| 6 | `SetCrsr (1)` |
| 7 | `SetCrsr (2)` |
| 8 | `P0 masque cumul [B]` |
| 18 | `P0 selection [H]` |
| 20 | `P0 edition cloture auto [G]` |
| 21 | `GetParam ('DTCLOSURE')` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [    Listings cloture HTML (IDE 29)](VIL-IDE-29.md) -> **Print Ecart (IDE 67)**

Main -> ... -> [CV  Verification caisse (IDE 39)](VIL-IDE-39.md) -> **Print Ecart (IDE 67)**

Main -> ... -> [Liste des ecarts (IDE 101)](VIL-IDE-101.md) -> **Print Ecart (IDE 67)**

Main -> ... -> [    Listings cloture HTML (IDE 192)](VIL-IDE-192.md) -> **Print Ecart (IDE 67)**

Main -> ... -> [CV  Verification caisse (IDE 216)](VIL-IDE-216.md) -> **Print Ecart (IDE 67)**

Main -> ... -> [    Listings cloture HTML (IDE 219)](VIL-IDE-219.md) -> **Print Ecart (IDE 67)**

```mermaid
graph LR
    T67[67 Print Ecart]
    style T67 fill:#58a6ff
    CC9[9 Pilotage avant sessions]
    style CC9 fill:#8b5cf6
    CC148[148 CV Menu caisse vil...]
    style CC148 fill:#8b5cf6
    CC36[36 CV Menu Clôture de ...]
    style CC36 fill:#f59e0b
    CC10[10 Pilotage après sess...]
    style CC10 fill:#f59e0b
    CC86[86 Menu gestion caisse]
    style CC86 fill:#f59e0b
    CC29[29 Listings cloture HTML]
    style CC29 fill:#3fb950
    CC101[101 Liste des ecarts]
    style CC101 fill:#3fb950
    CC39[39 CV Verification caisse]
    style CC39 fill:#3fb950
    CC216[216 CV Verification ca...]
    style CC216 fill:#3fb950
    CC192[192 Listings cloture HTML]
    style CC192 fill:#3fb950
    CC10 --> CC29
    CC36 --> CC29
    CC86 --> CC29
    CC10 --> CC39
    CC36 --> CC39
    CC86 --> CC39
    CC10 --> CC101
    CC36 --> CC101
    CC86 --> CC101
    CC10 --> CC192
    CC36 --> CC192
    CC86 --> CC192
    CC10 --> CC216
    CC36 --> CC216
    CC86 --> CC216
    CC9 --> CC10
    CC148 --> CC10
    CC9 --> CC36
    CC148 --> CC36
    CC9 --> CC86
    CC148 --> CC86
    CC29 --> T67
    CC39 --> T67
    CC101 --> T67
    CC192 --> T67
    CC216 --> T67
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [29](VIL-IDE-29.md) |     Listings cloture HTML | 1 |
| [39](VIL-IDE-39.md) | CV  Verification caisse | 1 |
| [101](VIL-IDE-101.md) | Liste des ecarts | 1 |
| [192](VIL-IDE-192.md) |     Listings cloture HTML | 1 |
| [216](VIL-IDE-216.md) | CV  Verification caisse | 1 |
| [219](VIL-IDE-219.md) |     Listings cloture HTML | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T67[67 Print Ecart]
    style T67 fill:#58a6ff
    NONE[Aucun callee]
    T67 -.-> NONE
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
| Lignes de logique | 34 | Programme compact |
| Expressions | 21 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 34) | Code sain |
| Regles metier | 2 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 1 ecran, 0 traitement)

- **Strategie** : 1 composant(s) UI (Razor/React) avec formulaires et validation.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 09:05*
