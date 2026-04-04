# PBP IDE 52 - Deficit CM2

> **Analyse**: Phases 1-4 2026-02-03 08:58 -> 08:58 (21s) | Assemblage 08:58
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBP |
| IDE Position | 52 |
| Nom Programme | Deficit CM2 |
| Fichier source | `Prg_52.xml` |
| Domaine metier | General |
| Taches | 3 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Deficit CM2** assure la gestion complete de ce processus, accessible depuis [Edition effectif mensuel (IDE 56)](PBP-IDE-56.md), [Edition et envoi effectif (IDE 64)](PBP-IDE-64.md), [Edition effectif mensuel (IDE 413)](PBP-IDE-413.md).

Le flux de traitement s'organise en **2 blocs fonctionnels** :

- **Traitement** (2 taches) : traitements metier divers
- **Calcul** (1 tache) : calculs de montants, stocks ou compteurs

**Logique metier** : 4 regles identifiees couvrant conditions metier.

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (2 taches)

- **52** - Deficit CM2
- **52.1** - Deficit CM2

#### Phase 2 : Calcul (1 tache)

- **52.2** - Calcul JH absence

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (2 taches)

Traitements internes.

---

#### <a id="t1"></a>52 - Deficit CM2

**Role** : Traitement : Deficit CM2.

---

#### <a id="t7"></a>52.1 - Deficit CM2

**Role** : Traitement : Deficit CM2.


### 3.2 Calcul (1 tache)

Calculs metier : montants, stocks, compteurs.

---

#### <a id="t10"></a>52.2 - Calcul JH absence

**Role** : Calcul : Calcul JH absence.
**Variables liees** : M (V.Nb jour d'absence)


## 5. REGLES METIER

4 regles identifiees:

### Autres (4 regles)

#### <a id="rm-RM-001"></a>[RM-001] Si [AQ]<P.Gestion crise ? [F] alors P.Gestion crise ? [F] sinon [AQ])

| Element | Detail |
|---------|--------|
| **Condition** | `[AQ]<P.Gestion crise ? [F]` |
| **Si vrai** | P.Gestion crise ? [F] |
| **Si faux** | [AQ]) |
| **Variables** | F (P.Gestion crise ?) |
| **Expression source** | Expression 21 : `IF([AQ]<P.Gestion crise ? [F],P.Gestion crise ? [F],[AQ])` |
| **Exemple** | Si [AQ]<P.Gestion crise ? [F] â†’ P.Gestion crise ? [F]. Sinon â†’ [AQ]) |

#### <a id="rm-RM-002"></a>[RM-002] Si [AS]>V.Nb JH du mois [G] alors V.Nb JH du mois [G] sinon [AS])

| Element | Detail |
|---------|--------|
| **Condition** | `[AS]>V.Nb JH du mois [G]` |
| **Si vrai** | V.Nb JH du mois [G] |
| **Si faux** | [AS]) |
| **Variables** | G (V.Nb JH du mois) |
| **Expression source** | Expression 22 : `IF([AS]>V.Nb JH du mois [G],V.Nb JH du mois [G],[AS])` |
| **Exemple** | Si [AS]>V.Nb JH du mois [G] â†’ V.Nb JH du mois [G]. Sinon â†’ [AS]) |

#### <a id="rm-RM-003"></a>[RM-003] Si P.Lieu sejour [D]<{1 alors 108} sinon {1,108},P.Lieu sejour [D])

| Element | Detail |
|---------|--------|
| **Condition** | `P.Lieu sejour [D]<{1` |
| **Si vrai** | 108} |
| **Si faux** | {1,108},P.Lieu sejour [D]) |
| **Variables** | D (P.Lieu sejour) |
| **Expression source** | Expression 64 : `IF(P.Lieu sejour [D]<{1,108},{1,108},P.Lieu sejour [D])` |
| **Exemple** | Si P.Lieu sejour [D]<{1 â†’ 108}. Sinon â†’ {1,108},P.Lieu sejour [D]) |

#### <a id="rm-RM-004"></a>[RM-004] Si P.Nom lieu sejour [E]>{1 alors 109} sinon {1,109},P.Nom lieu sejour [E])

| Element | Detail |
|---------|--------|
| **Condition** | `P.Nom lieu sejour [E]>{1` |
| **Si vrai** | 109} |
| **Si faux** | {1,109},P.Nom lieu sejour [E]) |
| **Variables** | E (P.Nom lieu sejour) |
| **Expression source** | Expression 65 : `IF(P.Nom lieu sejour [E]>{1,109},{1,109},P.Nom lieu sejour [` |
| **Exemple** | Si P.Nom lieu sejour [E]>{1 â†’ 109}. Sinon â†’ {1,109},P.Nom lieu sejour [E]) |

## 6. CONTEXTE

- **Appele par**: [Edition effectif mensuel (IDE 56)](PBP-IDE-56.md), [Edition et envoi effectif (IDE 64)](PBP-IDE-64.md), [Edition effectif mensuel (IDE 413)](PBP-IDE-413.md)
- **Appelle**: 0 programmes | **Tables**: 5 (W:0 R:3 L:2) | **Taches**: 3 | **Expressions**: 65

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (3 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **52.1** | [**Deficit CM2** (52)](#t1) | - | - | Traitement |
| 52.1.1 | [Deficit CM2 (52.1)](#t7) | - | - | |
| **52.2** | [**Calcul JH absence** (52.2)](#t10) | - | - | Calcul |

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

### Tables utilisees (5)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 366 | pms_print_param |  | DB | R |   |   | 1 |
| 802 | type_prestation | Prestations/services vendus | DB |   |   | L | 1 |
| 825 | fac_hebergement_pro | Hebergement (chambres) | DB |   |   | L | 1 |
| 826 | wording_mention_legal |  | DB | R |   |   | 1 |
| 834 | tpe_par_terminal |  | DB | R |   |   | 1 |

### Colonnes par table (3 / 3 tables avec colonnes identifiees)

<details>
<summary>Table 366 - pms_print_param (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | V.Date debut absence | R | Date |
| B | V.Date fin absence | R | Date |
| C | V.J absence | R | Numeric |

</details>

<details>
<summary>Table 826 - wording_mention_legal (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | V.Nb repas midi | R | Numeric |
| B | V.Nb repas soir | R | Numeric |
| C | V.Nb jh midi | R | Numeric |
| D | V.Nb jh soir | R | Numeric |

</details>

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
| G | V.Nb JH du mois | R | Numeric |
| H | V.Total JH | R | Numeric |
| I | V.Date debut | R | Date |
| J | V.Date fin | R | Date |
| K | V.Date debut premiere periode | R | Date |
| L | V.Date fin derniere periode | R | Date |
| M | V.Nb jour d'absence | R | Numeric |
| N | V.Date debut sej | R | Date |
| O | V.Date fin sej | R | Date |
| P | V.Heure debut premiere periode | R | Alpha |
| Q | V.Heure fin derniere periode | R | Alpha |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (6)

Variables recues du programme appelant ([Edition effectif mensuel (IDE 56)](PBP-IDE-56.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P.Date debut | Date | 1x parametre entrant |
| B | P.Date fin | Date | 1x parametre entrant |
| C | P.Code village | Alpha | 1x parametre entrant |
| D | P.Lieu sejour | Alpha | 1x parametre entrant |
| E | P.Nom lieu sejour | Alpha | 1x parametre entrant |
| F | P.Gestion crise ? | Logical | 5x parametre entrant |

### 11.2 Variables de session (11)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| G | V.Nb JH du mois | Numeric | 2x session |
| H | V.Total JH | Numeric | - |
| I | V.Date debut | Date | - |
| J | V.Date fin | Date | - |
| K | V.Date debut premiere periode | Date | - |
| L | V.Date fin derniere periode | Date | - |
| M | V.Nb jour d'absence | Numeric | - |
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
| V. | **G** | V.Nb JH du mois | Numeric |
| V. | **H** | V.Total JH | Numeric |
| V. | **I** | V.Date debut | Date |
| V. | **J** | V.Date fin | Date |
| V. | **K** | V.Date debut premiere periode | Date |
| V. | **L** | V.Date fin derniere periode | Date |
| V. | **M** | V.Nb jour d'absence | Numeric |
| V. | **N** | V.Date debut sej | Date |
| V. | **O** | V.Date fin sej | Date |
| V. | **P** | V.Heure debut premiere periode | Alpha |
| V. | **Q** | V.Heure fin derniere periode | Alpha |

</details>

## 12. EXPRESSIONS

**65 / 65 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCULATION | 7 | 0 |
| CONDITION | 18 | 4 |
| CONSTANTE | 3 | 0 |
| FORMAT | 1 | 0 |
| OTHER | 33 | 0 |
| NEGATION | 2 | 0 |
| STRING | 1 | 0 |

### 12.2 Expressions cles par type

#### CALCULATION (7 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 35 | `[AO]+([DE]-[DD]-1)` | - |
| CALCULATION | 36 | `[AO]-[DF]` | - |
| CALCULATION | 39 | `[AO]+0.5` | - |
| CALCULATION | 27 | `[AO]+1` | - |
| CALCULATION | 15 | `Fill('-',30)` | - |
| ... | | *+2 autres* | |

#### CONDITION (18 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 22 | `IF([AS]>V.Nb JH du mois [G],V.Nb JH du mois [G],[AS])` | [RM-002](#rm-RM-002) |
| CONDITION | 65 | `IF(P.Nom lieu sejour [E]>{1,109},{1,109},P.Nom lieu sejour [E])` | [RM-004](#rm-RM-004) |
| CONDITION | 64 | `IF(P.Lieu sejour [D]<{1,108},{1,108},P.Lieu sejour [D])` | [RM-003](#rm-RM-003) |
| CONDITION | 21 | `IF([AQ]<P.Gestion crise ? [F],P.Gestion crise ? [F],[AQ])` | [RM-001](#rm-RM-001) |
| CONDITION | 37 | `[AO]<>0` | - |
| ... | | *+13 autres* | |

#### CONSTANTE (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 34 | `''` | - |
| CONSTANTE | 17 | `0` | - |
| CONSTANTE | 10 | `'O'` | - |

#### FORMAT (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| FORMAT | 1 | `Trim(Translate('%club_exportdata%'))&'trsft\'&Trim([BU])&IF([CT]<>'','_'&Trim([CT])&'_','_')&'EFF_Deficit_CM2_'&IF([DG],Trim(DStr(Date()-2,'YYYYMM')),Trim(DStr(Date(),'YYYYMM')))&'.htm'` | - |

#### OTHER (33 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 53 | `MlsTrans('Total JH')` | - |
| OTHER | 52 | `MlsTrans('Lieu de séjour')` | - |
| OTHER | 55 | `MlsTrans('Prénom')` | - |
| OTHER | 54 | `MlsTrans('Nom')` | - |
| OTHER | 49 | `MlsTrans('Village')` | - |
| ... | | *+28 autres* | |

#### NEGATION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| NEGATION | 40 | `NOT ExpCalc('65'EXP)` | - |
| NEGATION | 38 | `NOT ExpCalc('64'EXP)` | - |

#### STRING (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| STRING | 7 | `Trim(VG37)` | - |

### 12.3 Toutes les expressions (65)

<details>
<summary>Voir les 65 expressions</summary>

#### CALCULATION (7)

| IDE | Expression Decodee |
|-----|-------------------|
| 15 | `Fill('-',30)` |
| 16 | `Fill('-',20)` |
| 18 | `[AN]+[AO]` |
| 27 | `[AO]+1` |
| 35 | `[AO]+([DE]-[DD]-1)` |
| 36 | `[AO]-[DF]` |
| 39 | `[AO]+0.5` |

#### CONDITION (18)

| IDE | Expression Decodee |
|-----|-------------------|
| 14 | `CASE([CJ],'IGPV','IGP CCS','OFFI','Officiers','MARI','Marins','')` |
| 21 | `IF([AQ]<P.Gestion crise ? [F],P.Gestion crise ? [F],[AQ])` |
| 22 | `IF([AS]>V.Nb JH du mois [G],V.Nb JH du mois [G],[AS])` |
| 64 | `IF(P.Lieu sejour [D]<{1,108},{1,108},P.Lieu sejour [D])` |
| 65 | `IF(P.Nom lieu sejour [E]>{1,109},{1,109},P.Nom lieu sejour [E])` |
| 12 | `CndRange([CT]<>'',[CT])` |
| 13 | `[CT]<>''` |
| 23 | `[BV]<[DD] OR [DD]=0` |
| 24 | `[BW]>[DE] OR [DE]=0` |
| 28 | `[DH]<[DD]` |
| 29 | `[DI]>[DE]` |
| 31 | `[AQ]<[DH] OR [DH]=0` |
| 33 | `[AS]>[DI] OR [DI]=0` |
| 37 | `[AO]<>0` |
| 41 | `Val([DJ],'2')<=15` |
| 42 | `Val([DJ],'2')<23` |
| 43 | `Val([DK],'2')>=12` |
| 44 | `Val([DK],'2')>=20` |

#### CONSTANTE (3)

| IDE | Expression Decodee |
|-----|-------------------|
| 10 | `'O'` |
| 17 | `0` |
| 34 | `''` |

#### FORMAT (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 1 | `Trim(Translate('%club_exportdata%'))&'trsft\'&Trim([BU])&IF([CT]<>'','_'&Trim([CT])&'_','_')&'EFF_Deficit_CM2_'&IF([DG],Trim(DStr(Date()-2,'YYYYMM')),Trim(DStr(Date(),'YYYYMM')))&'.htm'` |

#### OTHER (33)

| IDE | Expression Decodee |
|-----|-------------------|
| 2 | `IN([CJ],'IGPV','OFFI','MARI')` |
| 3 | `P.Date debut [A]` |
| 4 | `P.Date fin [B]` |
| 5 | `P.Code village [C]` |
| 6 | `GetParam('SOCIETE')` |
| 8 | `Day(EOM(P.Gestion crise ? [F]))` |
| 9 | `CMonth(P.Gestion crise ? [F])` |
| 11 | `EOM(P.Gestion crise ? [F])` |
| 19 | `[BV]` |
| 20 | `[BW]` |
| 25 | `V.Nb JH du mois [G]` |
| 26 | `P.Gestion crise ? [F]` |
| 30 | `[AQ]` |
| 32 | `[AS]` |
| 45 | `[DL]` |
| 46 | `[DM]` |
| 47 | `MlsTrans('Nom du Chef de Village')` |
| 48 | `MlsTrans('Signature du Chef de Village')` |
| 49 | `MlsTrans('Village')` |
| 50 | `MlsTrans('Mois')` |
| 51 | `MlsTrans('Nombre de jours du mois')` |
| 52 | `MlsTrans('Lieu de séjour')` |
| 53 | `MlsTrans('Total JH')` |
| 54 | `MlsTrans('Nom')` |
| 55 | `MlsTrans('Prénom')` |
| 56 | `MlsTrans('Motif')` |
| 57 | `MlsTrans('Début de séjour')` |
| 58 | `MlsTrans('Fin de séjour')` |
| 59 | `MlsTrans('Nombre de JH')` |
| 60 | `MlsTrans('CCS')` |
| 61 | `{1,1}` |
| 62 | `{1,2}` |
| 63 | `{1,3}` |

#### NEGATION (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 38 | `NOT ExpCalc('64'EXP)` |
| 40 | `NOT ExpCalc('65'EXP)` |

#### STRING (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 7 | `Trim(VG37)` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Edition effectif mensuel (IDE 56)](PBP-IDE-56.md) -> **Deficit CM2 (IDE 52)**

Main -> ... -> [Edition et envoi effectif (IDE 64)](PBP-IDE-64.md) -> **Deficit CM2 (IDE 52)**

Main -> ... -> [Edition effectif mensuel (IDE 413)](PBP-IDE-413.md) -> **Deficit CM2 (IDE 52)**

```mermaid
graph LR
    T52[52 Deficit CM2]
    style T52 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC148[148 Liste Gestion de C...]
    style CC148 fill:#f59e0b
    CC152[152 Start]
    style CC152 fill:#f59e0b
    CC146[146 Pilotage Gestion d...]
    style CC146 fill:#f59e0b
    CC414[414 Call Extraction]
    style CC414 fill:#f59e0b
    CC54[54 Effectif mensuel la...]
    style CC54 fill:#f59e0b
    CC63[63 Cloture saison effe...]
    style CC63 fill:#f59e0b
    CC56[56 Edition effectif me...]
    style CC56 fill:#3fb950
    CC64[64 Edition et envoi ef...]
    style CC64 fill:#3fb950
    CC413[413 Edition effectif m...]
    style CC413 fill:#3fb950
    CC54 --> CC56
    CC63 --> CC56
    CC146 --> CC56
    CC414 --> CC56
    CC54 --> CC64
    CC63 --> CC64
    CC146 --> CC64
    CC414 --> CC64
    CC54 --> CC413
    CC63 --> CC413
    CC146 --> CC413
    CC414 --> CC413
    CC148 --> CC54
    CC152 --> CC54
    CC148 --> CC63
    CC152 --> CC63
    CC148 --> CC146
    CC152 --> CC146
    CC148 --> CC414
    CC152 --> CC414
    CC1 --> CC148
    CC1 --> CC152
    CC56 --> T52
    CC64 --> T52
    CC413 --> T52
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [56](PBP-IDE-56.md) | Edition effectif mensuel | 1 |
| [64](PBP-IDE-64.md) | Edition et envoi effectif | 1 |
| [413](PBP-IDE-413.md) | Edition effectif mensuel | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T52[52 Deficit CM2]
    style T52 fill:#58a6ff
    NONE[Aucun callee]
    T52 -.-> NONE
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
| Lignes de logique | 140 | Programme compact |
| Expressions | 65 | Logique moderee |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 140) | Code sain |
| Regles metier | 4 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (2 taches: 0 ecran, 2 traitements)

- **Strategie** : 2 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

#### Calcul (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Services de calcul purs (Domain Services).
- Migrer la logique de calcul (stock, compteurs, montants)

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 08:58*
