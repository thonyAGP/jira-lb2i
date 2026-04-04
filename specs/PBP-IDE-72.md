# PBP IDE 72 - Deficit IGP Global CDV V3

> **Analyse**: Phases 1-4 2026-02-03 09:08 -> 09:08 (23s) | Assemblage 09:08
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBP |
| IDE Position | 72 |
| Nom Programme | Deficit IGP Global CDV V3 |
| Fichier source | `Prg_72.xml` |
| Domaine metier | General |
| Taches | 2 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Deficit IGP Global CDV V3** assure la gestion complete de ce processus, accessible depuis [Edition effectif mensuel V3 (IDE 66)](PBP-IDE-66.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (2 taches) : traitements metier divers

**Logique metier** : 4 regles identifiees couvrant conditions metier.

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (2 taches)

Traitements internes.

---

#### <a id="t1"></a>72 - Deficit IGP Global CDV V3

**Role** : Traitement : Deficit IGP Global CDV V3.

---

#### <a id="t27"></a>72.1 - Ligne IGP ou IGP

**Role** : Traitement : Ligne IGP ou IGP.


## 5. REGLES METIER

4 regles identifiees:

### Autres (4 regles)

#### <a id="rm-RM-001"></a>[RM-001] Si [EU] alors '800170385' sinon '800180385')

| Element | Detail |
|---------|--------|
| **Condition** | `[EU]` |
| **Si vrai** | '800170385' |
| **Si faux** | '800180385') |
| **Expression source** | Expression 3 : `IF([EU],'800170385','800180385')` |
| **Exemple** | Si [EU] â†’ '800170385'. Sinon â†’ '800180385') |

#### <a id="rm-RM-002"></a>[RM-002] Si ISNULL([EU]) alors [AN]+[ES] sinon IF([EU],[AN],[ES]))

| Element | Detail |
|---------|--------|
| **Condition** | `ISNULL([EU])` |
| **Si vrai** | [AN]+[ES] |
| **Si faux** | IF([EU],[AN],[ES])) |
| **Expression source** | Expression 5 : `IF(ISNULL([EU]),[AN]+[ES],IF([EU],[AN],[ES]))` |
| **Exemple** | Si ISNULL([EU]) â†’ [AN]+[ES]. Sinon â†’ IF([EU],[AN],[ES])) |

#### <a id="rm-RM-003"></a>[RM-003] Si [AQ]<P.Gestion crise ? [F] alors P.Gestion crise ? [F] sinon [AQ])

| Element | Detail |
|---------|--------|
| **Condition** | `[AQ]<P.Gestion crise ? [F]` |
| **Si vrai** | P.Gestion crise ? [F] |
| **Si faux** | [AQ]) |
| **Variables** | F (P.Gestion crise ?) |
| **Expression source** | Expression 27 : `IF([AQ]<P.Gestion crise ? [F],P.Gestion crise ? [F],[AQ])` |
| **Exemple** | Si [AQ]<P.Gestion crise ? [F] â†’ P.Gestion crise ? [F]. Sinon â†’ [AQ]) |

#### <a id="rm-RM-004"></a>[RM-004] Si [AS]>V.Avec CDV? [G] alors V.Avec CDV? [G] sinon [AS])

| Element | Detail |
|---------|--------|
| **Condition** | `[AS]>V.Avec CDV? [G]` |
| **Si vrai** | V.Avec CDV? [G] |
| **Si faux** | [AS]) |
| **Variables** | G (V.Avec CDV?) |
| **Expression source** | Expression 28 : `IF([AS]>V.Avec CDV? [G],V.Avec CDV? [G],[AS])` |
| **Exemple** | Si [AS]>V.Avec CDV? [G] â†’ V.Avec CDV? [G]. Sinon â†’ [AS]) |

## 6. CONTEXTE

- **Appele par**: [Edition effectif mensuel V3 (IDE 66)](PBP-IDE-66.md)
- **Appelle**: 0 programmes | **Tables**: 3 (W:0 R:1 L:2) | **Taches**: 2 | **Expressions**: 43

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (2 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **72.1** | [**Deficit IGP Global CDV V3** (72)](#t1) | - | - | Traitement |
| 72.1.1 | [Ligne IGP ou IGP (72.1)](#t27) | - | - | |

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

### Tables utilisees (3)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 802 | type_prestation | Prestations/services vendus | DB |   |   | L | 1 |
| 834 | tpe_par_terminal |  | DB | R |   |   | 1 |
| 949 | Table_949 |  | MEM |   |   | L | 1 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 834 - tpe_par_terminal (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P.Date debut | R | Date |
| B | P.Date fin | R | Date |
| C | P.Code village | R | Alpha |
| D | P.Lieu sejour | R | Alpha |
| E | P.Nom lieu sejour | R | Alpha |
| F | P.Gestion crise ? | R | Logical |
| G | P.Avec CDV? | R | Logical |
| H | P.Nb JH du mois | R | Numeric |
| I | P.Total JH | R | Numeric |
| J | V.Date debut | R | Date |
| K | V.Date fin | R | Date |
| L | V.Date debut premiere periode | R | Date |
| M | V.Date fin derniere periode | R | Date |
| N | V.Date debut sej | R | Date |
| O | V.Date fin sej | R | Date |
| P | V.Heure debut premiere periode | R | Alpha |
| Q | V.Heure fin derniere periode | R | Alpha |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (6)

Variables recues du programme appelant ([Edition effectif mensuel V3 (IDE 66)](PBP-IDE-66.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P.Date debut | Date | 1x parametre entrant |
| B | P.Date fin | Date | 1x parametre entrant |
| C | P.Code village | Alpha | 1x parametre entrant |
| D | P.Lieu sejour | Alpha | - |
| E | P.Nom lieu sejour | Alpha | - |
| F | P.Gestion crise ? | Logical | 4x parametre entrant |

### 11.2 Variables de session (11)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| G | V.Avec CDV? | Logical | 2x session |
| H | v.Condition SQL CDV | Unicode | - |
| I | V.Nb JH avec CDV du mois | Numeric | - |
| J | V.Total avec CDV JH | Numeric | - |
| K | V.Nb JH sans CDV du mois | Numeric | - |
| L | V.Total sans CDV JH | Numeric | - |
| M | V.Date fin derniere periode | Date | - |
| N | V.Date debut sej | Date | - |
| O | V.Date fin sej | Date | - |
| P | V.Heure debut premiere periode | Alpha | - |
| Q | V.Heure fin derniere periode | Alpha | - |

<details>
<summary>Toutes les 17 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| P0 | **A** | P.Date debut | Date |
| P0 | **B** | P.Date fin | Date |
| P0 | **C** | P.Code village | Alpha |
| P0 | **D** | P.Lieu sejour | Alpha |
| P0 | **E** | P.Nom lieu sejour | Alpha |
| P0 | **F** | P.Gestion crise ? | Logical |
| V. | **G** | V.Avec CDV? | Logical |
| V. | **H** | v.Condition SQL CDV | Unicode |
| V. | **I** | V.Nb JH avec CDV du mois | Numeric |
| V. | **J** | V.Total avec CDV JH | Numeric |
| V. | **K** | V.Nb JH sans CDV du mois | Numeric |
| V. | **L** | V.Total sans CDV JH | Numeric |
| V. | **M** | V.Date fin derniere periode | Date |
| V. | **N** | V.Date debut sej | Date |
| V. | **O** | V.Date fin sej | Date |
| V. | **P** | V.Heure debut premiere periode | Alpha |
| V. | **Q** | V.Heure fin derniere periode | Alpha |

</details>

## 12. EXPRESSIONS

**43 / 43 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCULATION | 2 | 0 |
| CONDITION | 14 | 4 |
| CONSTANTE | 4 | 0 |
| FORMAT | 1 | 0 |
| OTHER | 19 | 0 |
| CAST_LOGIQUE | 2 | 0 |
| STRING | 1 | 0 |

### 12.2 Expressions cles par type

#### CALCULATION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 43 | `[AO]+(([EF]+[EJ])/2)` | - |
| CALCULATION | 22 | `[AN]+[AO]` | - |

#### CONDITION (14 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 27 | `IF([AQ]<P.Gestion crise ? [F],P.Gestion crise ? [F],[AQ])` | [RM-003](#rm-RM-003) |
| CONDITION | 28 | `IF([AS]>V.Avec CDV? [G],V.Avec CDV? [G],[AS])` | [RM-004](#rm-RM-004) |
| CONDITION | 5 | `IF(ISNULL([EU]),[AN]+[ES],IF([EU],[AN],[ES]))` | [RM-002](#rm-RM-002) |
| CONDITION | 3 | `IF([EU],'800170385','800180385')` | [RM-001](#rm-RM-001) |
| CONDITION | 35 | `[AQ]<[DG] OR [DG]=0` | - |
| ... | | *+9 autres* | |

#### CONSTANTE (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 26 | `0` | - |
| CONSTANTE | 37 | `''` | - |
| CONSTANTE | 1 | `'Invitant'` | - |
| CONSTANTE | 2 | `'Invités gratuits pensions Hors Chef de village'` | - |

#### FORMAT (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| FORMAT | 6 | `Trim(Translate('%club_exportdata%'))&'trsft\'&Trim([BU])&IF([CT]<>'','_'&Trim([CT])&'_','_')&'EFF_Deficit_IGP_'&IF([DF],Trim(DStr(Date()-2,'YYYYMM')),Trim(DStr(Date(),'YYYYMM')))&'.htm'` | - |

#### OTHER (19 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 30 | `[BW]` | - |
| OTHER | 33 | `[AQ]` | - |
| OTHER | 24 | `V.Avec CDV? [G]` | - |
| OTHER | 29 | `[BV]` | - |
| OTHER | 34 | `[AS]` | - |
| ... | | *+14 autres* | |

#### CAST_LOGIQUE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 12 | `'FALSE'LOG` | - |
| CAST_LOGIQUE | 11 | `'TRUE'LOG` | - |

#### STRING (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| STRING | 7 | `Trim(VG37)` | - |

### 12.3 Toutes les expressions (43)

<details>
<summary>Voir les 43 expressions</summary>

#### CALCULATION (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 22 | `[AN]+[AO]` |
| 43 | `[AO]+(([EF]+[EJ])/2)` |

#### CONDITION (14)

| IDE | Expression Decodee |
|-----|-------------------|
| 3 | `IF([EU],'800170385','800180385')` |
| 4 | `IF([EU],'CDV','IGP Hors CDV')` |
| 5 | `IF(ISNULL([EU]),[AN]+[ES],IF([EU],[AN],[ES]))` |
| 14 | `IF([EU],'IGP','IGP2')` |
| 27 | `IF([AQ]<P.Gestion crise ? [F],P.Gestion crise ? [F],[AQ])` |
| 28 | `IF([AS]>V.Avec CDV? [G],V.Avec CDV? [G],[AS])` |
| 10 | `[CT]<>''` |
| 25 | `CndRange([CT]<>'',[CT])` |
| 31 | `[BV]<[DD] OR [DD]=0` |
| 32 | `[BW]>[DE] OR [DE]=0` |
| 35 | `[AQ]<[DG] OR [DG]=0` |
| 36 | `[AS]>[DH] OR [DH]=0` |
| 38 | `[AO]<>0` |
| 15 | `[DW]='GM' AND [DX]=Trim({1,152})` |

#### CONSTANTE (4)

| IDE | Expression Decodee |
|-----|-------------------|
| 1 | `'Invitant'` |
| 2 | `'Invités gratuits pensions Hors Chef de village'` |
| 26 | `0` |
| 37 | `''` |

#### FORMAT (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 6 | `Trim(Translate('%club_exportdata%'))&'trsft\'&Trim([BU])&IF([CT]<>'','_'&Trim([CT])&'_','_')&'EFF_Deficit_IGP_'&IF([DF],Trim(DStr(Date()-2,'YYYYMM')),Trim(DStr(Date(),'YYYYMM')))&'.htm'` |

#### OTHER (19)

| IDE | Expression Decodee |
|-----|-------------------|
| 8 | `Day(EOM(P.Gestion crise ? [F]))` |
| 9 | `CMonth(P.Gestion crise ? [F])` |
| 13 | `NULL()` |
| 16 | `P.Date debut [A]` |
| 17 | `P.Date fin [B]` |
| 18 | `P.Code village [C]` |
| 19 | `GetParam('SOCIETE')` |
| 20 | `[EB]` |
| 21 | `[EC]` |
| 23 | `P.Gestion crise ? [F]` |
| 24 | `V.Avec CDV? [G]` |
| 29 | `[BV]` |
| 30 | `[BW]` |
| 33 | `[AQ]` |
| 34 | `[AS]` |
| 39 | `[DK]` |
| 40 | `[DL]` |
| 41 | `[DW]` |
| 42 | `[DX]` |

#### CAST_LOGIQUE (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 11 | `'TRUE'LOG` |
| 12 | `'FALSE'LOG` |

#### STRING (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 7 | `Trim(VG37)` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Edition effectif mensuel V3 (IDE 66)](PBP-IDE-66.md) -> **Deficit IGP Global CDV V3 (IDE 72)**

```mermaid
graph LR
    T72[72 Deficit IGP Global ...]
    style T72 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC148[148 Liste Gestion de C...]
    style CC148 fill:#f59e0b
    CC152[152 Start]
    style CC152 fill:#f59e0b
    CC414[414 Call Extraction]
    style CC414 fill:#f59e0b
    CC146[146 Pilotage Gestion d...]
    style CC146 fill:#f59e0b
    CC63[63 Cloture saison effe...]
    style CC63 fill:#f59e0b
    CC54[54 Effectif mensuel la...]
    style CC54 fill:#f59e0b
    CC64[64 Edition et envoi ef...]
    style CC64 fill:#f59e0b
    CC66[66 Edition effectif me...]
    style CC66 fill:#3fb950
    CC54 --> CC66
    CC64 --> CC66
    CC63 --> CC54
    CC146 --> CC54
    CC414 --> CC54
    CC63 --> CC64
    CC146 --> CC64
    CC414 --> CC64
    CC148 --> CC63
    CC152 --> CC63
    CC148 --> CC146
    CC152 --> CC146
    CC148 --> CC414
    CC152 --> CC414
    CC1 --> CC148
    CC1 --> CC152
    CC66 --> T72
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [66](PBP-IDE-66.md) | Edition effectif mensuel V3 | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T72[72 Deficit IGP Global ...]
    style T72 fill:#58a6ff
    NONE[Aucun callee]
    T72 -.-> NONE
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
| Lignes de logique | 121 | Programme compact |
| Expressions | 43 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 121) | Code sain |
| Regles metier | 4 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (2 taches: 0 ecran, 2 traitements)

- **Strategie** : 2 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 09:08*
