# VIL IDE 19 - Print listing des comptes

> **Analyse**: Phases 1-4 2026-02-03 01:05 -> 01:06 (39s) | Assemblage 01:06
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | VIL |
| IDE Position | 19 |
| Nom Programme | Print listing des comptes |
| Fichier source | `Prg_19.xml` |
| Domaine metier | Comptabilite |
| Taches | 1 (1 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Print listing des comptes** assure la gestion complete de ce processus, accessible depuis [    Listings cloture HTML (IDE 29)](VIL-IDE-29.md), [    Listings cloture HTML (IDE 192)](VIL-IDE-192.md), [    Listings cloture HTML (IDE 219)](VIL-IDE-219.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

**Logique metier** : 5 regles identifiees couvrant conditions metier.

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>19 - Veuillez patienter ..... [[ECRAN]](#ecran-t1)

**Role** : Traitement : Veuillez patienter ......
**Ecran** : 426 x 56 DLU (MDI) | [Voir mockup](#ecran-t1)


## 5. REGLES METIER

5 regles identifiees:

### Autres (5 regles)

#### <a id="rm-RM-001"></a>[RM-001] Si [U]<=P0 date comptable [C] alors IF([AU] sinon 'Easy Check Out','INSOL'),'')

| Element | Detail |
|---------|--------|
| **Condition** | `[U]<=P0 date comptable [C]` |
| **Si vrai** | IF([AU] |
| **Si faux** | 'Easy Check Out','INSOL'),'') |
| **Variables** | C (P0 date comptable) |
| **Expression source** | Expression 12 : `IF ([U]<=P0 date comptable [C],IF([AU],'Easy Check Out','INS` |
| **Exemple** | Si [U]<=P0 date comptable [C] â†’ IF([AU]. Sinon â†’ 'Easy Check Out','INSOL'),'') |

#### <a id="rm-RM-002"></a>[RM-002] Si [T]<0 alors Str (- ([T]) sinon P0 masque cumul [B]),Fill (' ',17)&Str ([T],Left (P0 masque cumul [B],17)))

| Element | Detail |
|---------|--------|
| **Condition** | `[T]<0` |
| **Si vrai** | Str (- ([T]) |
| **Si faux** | P0 masque cumul [B]),Fill (' ',17)&Str ([T],Left (P0 masque cumul [B],17))) |
| **Variables** | B (P0 masque cumul) |
| **Expression source** | Expression 15 : `IF ([T]<0,Str (- ([T]),P0 masque cumul [B]),Fill (' ',17)&St` |
| **Exemple** | Si [T]<0 â†’ Str (- ([T]) |

#### <a id="rm-RM-003"></a>[RM-003] Si W0 cumul credit [J]+W0 cumul debit [I]<0 alors Str (- (W0 cumul credit [J]+W0 cumul debit [I]) sinon P0 masque cumul [B]),Fill (' ',17)&Str (W0 cumul credit [J]+W0 cumul debit [I],Left (P0 masque cumul [B],17)))

| Element | Detail |
|---------|--------|
| **Condition** | `W0 cumul credit [J]+W0 cumul debit [I]<0` |
| **Si vrai** | Str (- (W0 cumul credit [J]+W0 cumul debit [I]) |
| **Si faux** | P0 masque cumul [B]),Fill (' ',17)&Str (W0 cumul credit [J]+W0 cumul debit [I],Left (P0 masque cumul [B],17))) |
| **Variables** | B (P0 masque cumul), I (W0 cumul debit), J (W0 cumul credit) |
| **Expression source** | Expression 18 : `IF (W0 cumul credit [J]+W0 cumul debit [I]<0,Str (- (W0 cumu` |
| **Exemple** | Si W0 cumul credit [J]+W0 cumul debit [I]<0 â†’ Str (- (W0 cumul credit [J]+W0 cumul debit [I]) |

#### <a id="rm-RM-004"></a>[RM-004] Si W0 cumul debit [I]+W0 cumul credit [J]<0 alors MlsTrans ('debiteur') sinon MlsTrans ('crediteur'))

| Element | Detail |
|---------|--------|
| **Condition** | `W0 cumul debit [I]+W0 cumul credit [J]<0` |
| **Si vrai** | MlsTrans ('debiteur') |
| **Si faux** | MlsTrans ('crediteur')) |
| **Variables** | I (W0 cumul debit), J (W0 cumul credit) |
| **Expression source** | Expression 22 : `IF (W0 cumul debit [I]+W0 cumul credit [J]<0,MlsTrans ('debi` |
| **Exemple** | Si W0 cumul debit [I]+W0 cumul credit [J]<0 â†’ MlsTrans ('debiteur'). Sinon â†’ MlsTrans ('crediteur')) |

#### <a id="rm-RM-005"></a>[RM-005] Si [T]>0 alors [T] sinon 0)

| Element | Detail |
|---------|--------|
| **Condition** | `[T]>0` |
| **Si vrai** | [T] |
| **Si faux** | 0) |
| **Expression source** | Expression 32 : `IF ([T]>0,[T],0)` |
| **Exemple** | Si [T]>0 â†’ [T]. Sinon â†’ 0) |

## 6. CONTEXTE

- **Appele par**: [    Listings cloture HTML (IDE 29)](VIL-IDE-29.md), [    Listings cloture HTML (IDE 192)](VIL-IDE-192.md), [    Listings cloture HTML (IDE 219)](VIL-IDE-219.md)
- **Appelle**: 0 programmes | **Tables**: 2 (W:0 R:1 L:1) | **Taches**: 1 | **Expressions**: 32

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 1)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 19 | 19 | Veuillez patienter ..... | MDI | 426 | 56 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>19 - Veuillez patienter .....
**Tache** : [19](#t1) | **Type** : MDI | **Dimensions** : 426 x 56 DLU
**Bloc** : Traitement | **Titre IDE** : Veuillez patienter .....

<!-- FORM-DATA:
{
    "width":  426,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  2,
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
                         "x":  119,
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
                         "x":  2,
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
                         "x":  74,
                         "type":  "label",
                         "var":  "",
                         "y":  39,
                         "w":  302,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Impression  listing des comptes",
                         "parent":  null
                     },
                     {
                         "x":  3,
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
    "taskId":  "19",
    "height":  56
}
-->

## 9. NAVIGATION

Ecran unique: **Veuillez patienter .....**

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **19.1** | [**Veuillez patienter .....** (19)](#t1) [mockup](#ecran-t1) | MDI | 426x56 | Traitement |

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
| 16 | backup_compte_gm__cgm | Comptes GM (generaux) | DB | R |   |   | 1 |
| 31 | gm-complet_______gmc |  | DB |   |   | L | 1 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 16 - backup_compte_gm__cgm (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P0 societe | R | Alpha |
| B | P0 masque cumul | R | Alpha |
| C | P0 date comptable | R | Date |
| D | P0 nom village | R | Alpha |
| E | P0 edition html | R | Logical |
| F | W0 config imp | R | Alpha |
| G | W0 date listing | R | Date |
| H | W0 heure listing | R | Time |
| I | W0 cumul debit | R | Numeric |
| J | W0 cumul credit | R | Numeric |
| K | W0 string-solde | R | Alpha |
| L | W0 string-solde | R | Alpha |
| M | W0 Retour Easy Check Out | R | Logical |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (5)

Variables recues du programme appelant ([    Listings cloture HTML (IDE 29)](VIL-IDE-29.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P0 societe | Alpha | 1x parametre entrant |
| B | P0 masque cumul | Alpha | 4x parametre entrant |
| C | P0 date comptable | Date | 3x parametre entrant |
| D | P0 nom village | Alpha | - |
| E | P0 edition html | Logical | 2x parametre entrant |

### 11.2 Variables de travail (8)

Variables internes au programme.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| F | W0 config imp | Alpha | - |
| G | W0 date listing | Date | - |
| H | W0 heure listing | Time | - |
| I | W0 cumul debit | Numeric | 6x calcul interne |
| J | W0 cumul credit | Numeric | 6x calcul interne |
| K | W0 string-solde | Alpha | - |
| L | W0 string-solde | Alpha | - |
| M | W0 Retour Easy Check Out | Logical | - |

## 12. EXPRESSIONS

**32 / 32 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCULATION | 3 | 0 |
| CONDITION | 14 | 5 |
| CONCATENATION | 2 | 0 |
| CONSTANTE | 1 | 0 |
| DATE | 1 | 0 |
| OTHER | 10 | 0 |
| CAST_LOGIQUE | 1 | 0 |

### 12.2 Expressions cles par type

#### CALCULATION (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 24 | `W0 cumul credit [J]+[T]` | - |
| CALCULATION | 23 | `W0 cumul debit [I]+[T]` | - |
| CALCULATION | 19 | `W0 cumul credit [J]+W0 cumul debit [I]` | - |

#### CONDITION (14 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 15 | `IF ([T]<0,Str (- ([T]),P0 masque cumul [B]),Fill (' ',17)&Str ([T],Left (P0 masque cumul [B],17)))` | [RM-002](#rm-RM-002) |
| CONDITION | 32 | `IF ([T]>0,[T],0)` | [RM-005](#rm-RM-005) |
| CONDITION | 22 | `IF (W0 cumul debit [I]+W0 cumul credit [J]<0,MlsTrans ('debiteur'),MlsTrans ('crediteur'))` | [RM-004](#rm-RM-004) |
| CONDITION | 18 | `IF (W0 cumul credit [J]+W0 cumul debit [I]<0,Str (- (W0 cumul credit [J]+W0 cumul debit [I]),P0 masque cumul [B]),Fill (' ',17)&Str (W0 cumul credit [J]+W0 cumul debit [I],Left (P0 masque cumul [B],17)))` | [RM-003](#rm-RM-003) |
| CONDITION | 12 | `IF ([U]<=P0 date comptable [C],IF([AU],'Easy Check Out','INSOL'),'')` | [RM-001](#rm-RM-001) |
| ... | | *+9 autres* | |

#### CONCATENATION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 29 | `Trim (INIGet ('[MAGIC_LOGICAL_NAMES]club_exportdata')&'Cloture\Editions\Adherent'&IF (P0 edition html [E],'_'&DStr (P0 date comptable [C],'YYYYMMDD'),'')&'.htm')` | - |
| CONCATENATION | 28 | `'- '&Str (Page (0,1),'3P0Z0')&' -'` | - |

#### CONSTANTE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 26 | `''` | - |

#### DATE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| DATE | 10 | `Date ()` | - |

#### OTHER (10 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 8 | `Left (P0 masque cumul [B],17)` | - |
| OTHER | 6 | `[P]` | - |
| OTHER | 9 | `Left (Right (P0 masque cumul [B],17),16)` | - |
| OTHER | 30 | `P0 edition html [E]` | - |
| OTHER | 11 | `Time ()` | - |
| ... | | *+5 autres* | |

#### CAST_LOGIQUE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 7 | `'TRUE'LOG` | - |

### 12.3 Toutes les expressions (32)

<details>
<summary>Voir les 32 expressions</summary>

#### CALCULATION (3)

| IDE | Expression Decodee |
|-----|-------------------|
| 19 | `W0 cumul credit [J]+W0 cumul debit [I]` |
| 23 | `W0 cumul debit [I]+[T]` |
| 24 | `W0 cumul credit [J]+[T]` |

#### CONDITION (14)

| IDE | Expression Decodee |
|-----|-------------------|
| 20 | `W0 cumul credit [J]+W0 cumul debit [I]<0` |
| 21 | `W0 cumul credit [J]+W0 cumul debit [I]>=0` |
| 12 | `IF ([U]<=P0 date comptable [C],IF([AU],'Easy Check Out','INSOL'),'')` |
| 15 | `IF ([T]<0,Str (- ([T]),P0 masque cumul [B]),Fill (' ',17)&Str ([T],Left (P0 masque cumul [B],17)))` |
| 18 | `IF (W0 cumul credit [J]+W0 cumul debit [I]<0,Str (- (W0 cumul credit [J]+W0 cumul debit [I]),P0 masque cumul [B]),Fill (' ',17)&Str (W0 cumul credit [J]+W0 cumul debit [I],Left (P0 masque cumul [B],17)))` |
| 22 | `IF (W0 cumul debit [I]+W0 cumul credit [J]<0,MlsTrans ('debiteur'),MlsTrans ('crediteur'))` |
| 31 | `IF ([T]<0,[T],0)` |
| 32 | `IF ([T]>0,[T],0)` |
| 13 | `[T]<0` |
| 14 | `[T]>0` |
| 16 | `[T]>=0` |
| 17 | `[T]<0` |
| 25 | `[T]<>0` |
| 27 | `INIGet ('[MAGIC_LOGICAL_NAMES]preview')='O'` |

#### CONCATENATION (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 28 | `'- '&Str (Page (0,1),'3P0Z0')&' -'` |
| 29 | `Trim (INIGet ('[MAGIC_LOGICAL_NAMES]club_exportdata')&'Cloture\Editions\Adherent'&IF (P0 edition html [E],'_'&DStr (P0 date comptable [C],'YYYYMMDD'),'')&'.htm')` |

#### CONSTANTE (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 26 | `''` |

#### DATE (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 10 | `Date ()` |

#### OTHER (10)

| IDE | Expression Decodee |
|-----|-------------------|
| 1 | `GetParam ('DTCLOSURE')` |
| 2 | `SetCrsr (1)` |
| 3 | `SetCrsr (2)` |
| 4 | `P0 date comptable [C]` |
| 5 | `P0 societe [A]` |
| 6 | `[P]` |
| 8 | `Left (P0 masque cumul [B],17)` |
| 9 | `Left (Right (P0 masque cumul [B],17),16)` |
| 11 | `Time ()` |
| 30 | `P0 edition html [E]` |

#### CAST_LOGIQUE (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 7 | `'TRUE'LOG` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [    Listings cloture HTML (IDE 29)](VIL-IDE-29.md) -> **Print listing des comptes (IDE 19)**

Main -> ... -> [    Listings cloture HTML (IDE 192)](VIL-IDE-192.md) -> **Print listing des comptes (IDE 19)**

Main -> ... -> [    Listings cloture HTML (IDE 219)](VIL-IDE-219.md) -> **Print listing des comptes (IDE 19)**

```mermaid
graph LR
    T19[19 Print listing des c...]
    style T19 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC149[149 Start]
    style CC149 fill:#f59e0b
    CC9[9 Pilotage avant sessions]
    style CC9 fill:#f59e0b
    CC10[10 Pilotage après sess...]
    style CC10 fill:#f59e0b
    CC29[29 Listings cloture HTML]
    style CC29 fill:#3fb950
    CC192[192 Listings cloture HTML]
    style CC192 fill:#3fb950
    CC219[219 Listings cloture HTML]
    style CC219 fill:#3fb950
    CC10 --> CC29
    CC10 --> CC192
    CC10 --> CC219
    CC9 --> CC10
    CC149 --> CC9
    CC1 --> CC149
    CC29 --> T19
    CC192 --> T19
    CC219 --> T19
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [29](VIL-IDE-29.md) |     Listings cloture HTML | 1 |
| [192](VIL-IDE-192.md) |     Listings cloture HTML | 1 |
| [219](VIL-IDE-219.md) |     Listings cloture HTML | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T19[19 Print listing des c...]
    style T19 fill:#58a6ff
    NONE[Aucun callee]
    T19 -.-> NONE
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
| Lignes de logique | 50 | Programme compact |
| Expressions | 32 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 50) | Code sain |
| Regles metier | 5 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 1 ecran, 0 traitement)

- **Strategie** : 1 composant(s) UI (Razor/React) avec formulaires et validation.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 01:06*
