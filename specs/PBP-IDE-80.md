# PBP IDE 80 - Deficit MISS V3

> **Analyse**: Phases 1-4 2026-02-03 09:12 -> 09:13 (19s) | Assemblage 09:13
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBP |
| IDE Position | 80 |
| Nom Programme | Deficit MISS V3 |
| Fichier source | `Prg_80.xml` |
| Domaine metier | General |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Deficit MISS V3** assure la gestion complete de ce processus, accessible depuis [Edition effectif mensuel V3 (IDE 66)](PBP-IDE-66.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

**Logique metier** : 2 regles identifiees couvrant conditions metier.

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>80 - Deficit MISS V3

**Role** : Traitement : Deficit MISS V3.


## 5. REGLES METIER

2 regles identifiees:

### Autres (2 regles)

#### <a id="rm-RM-001"></a>[RM-001] Si [AQ]<P.Gestion crise ? [F] alors P.Gestion crise ? [F] sinon [AQ])

| Element | Detail |
|---------|--------|
| **Condition** | `[AQ]<P.Gestion crise ? [F]` |
| **Si vrai** | P.Gestion crise ? [F] |
| **Si faux** | [AQ]) |
| **Variables** | F (P.Gestion crise ?) |
| **Expression source** | Expression 18 : `IF([AQ]<P.Gestion crise ? [F],P.Gestion crise ? [F],[AQ])` |
| **Exemple** | Si [AQ]<P.Gestion crise ? [F] â†’ P.Gestion crise ? [F]. Sinon â†’ [AQ]) |

#### <a id="rm-RM-002"></a>[RM-002] Si [AS]>V.Nb JH du mois [G] alors V.Nb JH du mois [G] sinon [AS])

| Element | Detail |
|---------|--------|
| **Condition** | `[AS]>V.Nb JH du mois [G]` |
| **Si vrai** | V.Nb JH du mois [G] |
| **Si faux** | [AS]) |
| **Variables** | G (V.Nb JH du mois) |
| **Expression source** | Expression 19 : `IF([AS]>V.Nb JH du mois [G],V.Nb JH du mois [G],[AS])` |
| **Exemple** | Si [AS]>V.Nb JH du mois [G] â†’ V.Nb JH du mois [G]. Sinon â†’ [AS]) |

## 6. CONTEXTE

- **Appele par**: [Edition effectif mensuel V3 (IDE 66)](PBP-IDE-66.md)
- **Appelle**: 0 programmes | **Tables**: 2 (W:0 R:1 L:1) | **Taches**: 1 | **Expressions**: 41

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **80.1** | [**Deficit MISS V3** (80)](#t1) | - | - | Traitement |

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
| E | P.Nom lieu | R | Alpha |
| F | P.Gestion crise ? | R | Logical |
| G | V.Nb JH du mois | R | Numeric |
| H | V.Nb repas | R | Numeric |
| I | V.Total JH | R | Numeric |
| J | V.Date debut | R | Date |
| K | V.Date fin | R | Date |
| L | V.Nb jh absence | R | Numeric |
| M | V.Date debut premiere periode | R | Date |
| N | V.Date fin derniere periode | R | Date |
| O | V.Date debut sej | R | Date |
| P | V.Date fin sej | R | Date |
| Q | V.Heure debut premiere periode | R | Alpha |
| R | V.Heure fin derniere periode | R | Alpha |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (6)

Variables recues du programme appelant ([Edition effectif mensuel V3 (IDE 66)](PBP-IDE-66.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P.Date debut | Date | - |
| B | P.Date fin | Date | - |
| C | P.Code village | Alpha | - |
| D | P.Lieu sejour | Alpha | - |
| E | P.Nom lieu | Alpha | - |
| F | P.Gestion crise ? | Logical | 5x parametre entrant |

### 11.2 Variables de session (12)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| G | V.Nb JH du mois | Numeric | 3x session |
| H | V.Nb repas | Numeric | - |
| I | V.Total JH | Numeric | - |
| J | V.Date debut | Date | - |
| K | V.Date fin | Date | - |
| L | V.Nb jh absence | Numeric | - |
| M | V.Date debut premiere periode | Date | - |
| N | V.Date fin derniere periode | Date | - |
| O | V.Date debut sej | Date | - |
| P | V.Date fin sej | Date | - |
| Q | V.Heure debut premiere periode | Alpha | - |
| R | V.Heure fin derniere periode | Alpha | - |

<details>
<summary>Toutes les 18 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| P0 | **A** | P.Date debut | Date |
| P0 | **B** | P.Date fin | Date |
| P0 | **C** | P.Code village | Alpha |
| P0 | **D** | P.Lieu sejour | Alpha |
| P0 | **E** | P.Nom lieu | Alpha |
| P0 | **F** | P.Gestion crise ? | Logical |
| V. | **G** | V.Nb JH du mois | Numeric |
| V. | **H** | V.Nb repas | Numeric |
| V. | **I** | V.Total JH | Numeric |
| V. | **J** | V.Date debut | Date |
| V. | **K** | V.Date fin | Date |
| V. | **L** | V.Nb jh absence | Numeric |
| V. | **M** | V.Date debut premiere periode | Date |
| V. | **N** | V.Date fin derniere periode | Date |
| V. | **O** | V.Date debut sej | Date |
| V. | **P** | V.Date fin sej | Date |
| V. | **Q** | V.Heure debut premiere periode | Alpha |
| V. | **R** | V.Heure fin derniere periode | Alpha |

</details>

## 12. EXPRESSIONS

**41 / 41 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCULATION | 3 | 0 |
| CONDITION | 10 | 2 |
| CONSTANTE | 9 | 0 |
| FORMAT | 1 | 0 |
| OTHER | 17 | 0 |
| STRING | 1 | 0 |

### 12.2 Expressions cles par type

#### CALCULATION (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 41 | `[ER]+([EH]+[EL])` | - |
| CALCULATION | 40 | `[AO]+([EH]+[EL])/2` | - |
| CALCULATION | 20 | `[AN]+[AO]` | - |

#### CONDITION (10 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 19 | `IF([AS]>V.Nb JH du mois [G],V.Nb JH du mois [G],[AS])` | [RM-002](#rm-RM-002) |
| CONDITION | 18 | `IF([AQ]<P.Gestion crise ? [F],P.Gestion crise ? [F],[AQ])` | [RM-001](#rm-RM-001) |
| CONDITION | 30 | `[AQ]<[DG] OR [DG]=0` | - |
| CONDITION | 26 | `[CC]>[DD] OR [DD]=0` | - |
| CONDITION | 35 | `[AO]<>0` | - |
| ... | | *+5 autres* | |

#### CONSTANTE (9 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 36 | `'GO'` | - |
| CONSTANTE | 32 | `''` | - |
| CONSTANTE | 39 | `0` | - |
| CONSTANTE | 37 | `'MISS'` | - |
| CONSTANTE | 27 | `0` | - |
| ... | | *+4 autres* | |

#### FORMAT (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| FORMAT | 5 | `Trim(Translate('%club_exportdata%'))&'trsft\'&Trim([CA])&IF([CW]<>'','_'&Trim([CW])&'_','_')&'EFF_Deficit_MISS'&'_'&IF([DE],Trim(DStr(Date()-2,'YYYYMM')),Trim(DStr(Date(),'YYYYMM')))&'.htm'` | - |

#### OTHER (17 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 24 | `[CC]` | - |
| OTHER | 28 | `[AQ]` | - |
| OTHER | 17 | `CMonth(P.Gestion crise ? [F])` | - |
| OTHER | 23 | `[CB]` | - |
| OTHER | 34 | `[DM]` | - |
| ... | | *+12 autres* | |

#### STRING (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| STRING | 15 | `Trim(VG37)` | - |

### 12.3 Toutes les expressions (41)

<details>
<summary>Voir les 41 expressions</summary>

#### CALCULATION (3)

| IDE | Expression Decodee |
|-----|-------------------|
| 20 | `[AN]+[AO]` |
| 40 | `[AO]+([EH]+[EL])/2` |
| 41 | `[ER]+([EH]+[EL])` |

#### CONDITION (10)

| IDE | Expression Decodee |
|-----|-------------------|
| 18 | `IF([AQ]<P.Gestion crise ? [F],P.Gestion crise ? [F],[AQ])` |
| 19 | `IF([AS]>V.Nb JH du mois [G],V.Nb JH du mois [G],[AS])` |
| 6 | `[EA]=''` |
| 21 | `CndRange([CW]<>'',[CW])` |
| 22 | `[CW]<>''` |
| 25 | `[CB]<[DC] OR [DC]=0` |
| 26 | `[CC]>[DD] OR [DD]=0` |
| 30 | `[AQ]<[DG] OR [DG]=0` |
| 31 | `[AS]>[DH] OR [DH]=0` |
| 35 | `[AO]<>0` |

#### CONSTANTE (9)

| IDE | Expression Decodee |
|-----|-------------------|
| 1 | `'Activité'` |
| 2 | `'GO Mission (Sejour + Repas)'` |
| 3 | `'REPAS'` |
| 4 | `'800200385'` |
| 27 | `0` |
| 32 | `''` |
| 36 | `'GO'` |
| 37 | `'MISS'` |
| 39 | `0` |

#### FORMAT (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 5 | `Trim(Translate('%club_exportdata%'))&'trsft\'&Trim([CA])&IF([CW]<>'','_'&Trim([CW])&'_','_')&'EFF_Deficit_MISS'&'_'&IF([DE],Trim(DStr(Date()-2,'YYYYMM')),Trim(DStr(Date(),'YYYYMM')))&'.htm'` |

#### OTHER (17)

| IDE | Expression Decodee |
|-----|-------------------|
| 7 | `P.Gestion crise ? [F]` |
| 8 | `V.Nb JH du mois [G]` |
| 9 | `[EC]` |
| 10 | `[ED]` |
| 11 | `[EE]` |
| 12 | `V.Nb JH du mois [G]` |
| 13 | `P.Gestion crise ? [F]` |
| 14 | `[DY]` |
| 16 | `Day(EOM(P.Gestion crise ? [F]))` |
| 17 | `CMonth(P.Gestion crise ? [F])` |
| 23 | `[CB]` |
| 24 | `[CC]` |
| 28 | `[AQ]` |
| 29 | `[AS]` |
| 33 | `[DL]` |
| 34 | `[DM]` |
| 38 | `[DZ]` |

#### STRING (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 15 | `Trim(VG37)` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Edition effectif mensuel V3 (IDE 66)](PBP-IDE-66.md) -> **Deficit MISS V3 (IDE 80)**

```mermaid
graph LR
    T80[80 Deficit MISS V3]
    style T80 fill:#58a6ff
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
    CC66 --> T80
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [66](PBP-IDE-66.md) | Edition effectif mensuel V3 | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T80[80 Deficit MISS V3]
    style T80 fill:#58a6ff
    NONE[Aucun callee]
    T80 -.-> NONE
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
| Lignes de logique | 90 | Programme compact |
| Expressions | 41 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 90) | Code sain |
| Regles metier | 2 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 0 ecran, 1 traitement)

- **Strategie** : 1 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 09:13*
