# PBP IDE 49 - Deficit ANS/MISS/ARTI/DOCT

> **Analyse**: Phases 1-4 2026-02-03 08:56 -> 08:56 (22s) | Assemblage 08:56
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBP |
| IDE Position | 49 |
| Nom Programme | Deficit ANS/MISS/ARTI/DOCT |
| Fichier source | `Prg_49.xml` |
| Domaine metier | General |
| Taches | 3 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Deficit ANS/MISS/ARTI/DOCT** assure la gestion complete de ce processus, accessible depuis [Edition et envoi effectif (IDE 64)](PBP-IDE-64.md), [Edition effectif mensuel (IDE 56)](PBP-IDE-56.md), [Edition effectif mensuel (IDE 413)](PBP-IDE-413.md).

Le flux de traitement s'organise en **2 blocs fonctionnels** :

- **Calcul** (2 taches) : calculs de montants, stocks ou compteurs
- **Traitement** (1 tache) : traitements metier divers

**Logique metier** : 5 regles identifiees couvrant conditions metier.

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (1 tache)

- **49** - Deficit ANS/MISS/ARTI/DOCT

#### Phase 2 : Calcul (2 taches)

- **49.1** - Calcul JH absence
- **49.2** - Calcul regul ANS

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>49 - Deficit ANS/MISS/ARTI/DOCT

**Role** : Traitement : Deficit ANS/MISS/ARTI/DOCT.


### 3.2 Calcul (2 taches)

Calculs metier : montants, stocks, compteurs.

---

#### <a id="t2"></a>49.1 - Calcul JH absence

**Role** : Calcul : Calcul JH absence.
**Variables liees** : L (V.Nb jh absence)

---

#### <a id="t3"></a>49.2 - Calcul regul ANS

**Role** : Calcul : Calcul regul ANS.
**Variables liees** : Q (V.tot jh regul)


## 5. REGLES METIER

5 regles identifiees:

### Autres (5 regles)

#### <a id="rm-RM-001"></a>[RM-001] Si [CS] vaut 'O' alors 'FACTURABLE', sinon 'NON&nbsp;FACTURABLE'

| Element | Detail |
|---------|--------|
| **Condition** | `[CS]='O'` |
| **Si vrai** | 'FACTURABLE' |
| **Si faux** | 'NON&nbsp;FACTURABLE') |
| **Expression source** | Expression 7 : `IF([CS]='O','FACTURABLE','NON&nbsp;FACTURABLE')` |
| **Exemple** | Si [CS]='O' â†’ 'FACTURABLE'. Sinon â†’ 'NON&nbsp;FACTURABLE') |

#### <a id="rm-RM-002"></a>[RM-002] Si [AQ]<P.Nom lieu [F] alors P.Nom lieu [F] sinon [AQ])

| Element | Detail |
|---------|--------|
| **Condition** | `[AQ]<P.Nom lieu [F]` |
| **Si vrai** | P.Nom lieu [F] |
| **Si faux** | [AQ]) |
| **Variables** | F (P.Nom lieu) |
| **Expression source** | Expression 8 : `IF([AQ]<P.Nom lieu [F],P.Nom lieu [F],[AQ])` |
| **Exemple** | Si [AQ]<P.Nom lieu [F] â†’ P.Nom lieu [F]. Sinon â†’ [AQ]) |

#### <a id="rm-RM-003"></a>[RM-003] Si [AS]>P.Gestion crise ? [G] alors P.Gestion crise ? [G] sinon [AS])

| Element | Detail |
|---------|--------|
| **Condition** | `[AS]>P.Gestion crise ? [G]` |
| **Si vrai** | P.Gestion crise ? [G] |
| **Si faux** | [AS]) |
| **Variables** | G (P.Gestion crise ?) |
| **Expression source** | Expression 9 : `IF([AS]>P.Gestion crise ? [G],P.Gestion crise ? [G],[AS])` |
| **Exemple** | Si [AS]>P.Gestion crise ? [G] â†’ P.Gestion crise ? [G]. Sinon â†’ [AS]) |

#### <a id="rm-RM-004"></a>[RM-004] Si P.Qualite [D]<{1 alors 107} sinon {1,107},P.Qualite [D])

| Element | Detail |
|---------|--------|
| **Condition** | `P.Qualite [D]<{1` |
| **Si vrai** | 107} |
| **Si faux** | {1,107},P.Qualite [D]) |
| **Variables** | D (P.Qualite) |
| **Expression source** | Expression 72 : `IF(P.Qualite [D]<{1,107},{1,107},P.Qualite [D])` |
| **Exemple** | Si P.Qualite [D]<{1 â†’ 107}. Sinon â†’ {1,107},P.Qualite [D]) |

#### <a id="rm-RM-005"></a>[RM-005] Si P.Lieu sejour [E]>{1 alors 108} sinon {1,108},P.Lieu sejour [E])

| Element | Detail |
|---------|--------|
| **Condition** | `P.Lieu sejour [E]>{1` |
| **Si vrai** | 108} |
| **Si faux** | {1,108},P.Lieu sejour [E]) |
| **Variables** | E (P.Lieu sejour) |
| **Expression source** | Expression 73 : `IF(P.Lieu sejour [E]>{1,108},{1,108},P.Lieu sejour [E])` |
| **Exemple** | Si P.Lieu sejour [E]>{1 â†’ 108}. Sinon â†’ {1,108},P.Lieu sejour [E]) |

## 6. CONTEXTE

- **Appele par**: [Edition et envoi effectif (IDE 64)](PBP-IDE-64.md), [Edition effectif mensuel (IDE 56)](PBP-IDE-56.md), [Edition effectif mensuel (IDE 413)](PBP-IDE-413.md)
- **Appelle**: 0 programmes | **Tables**: 4 (W:0 R:3 L:1) | **Taches**: 3 | **Expressions**: 76

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (3 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **49.1** | [**Deficit ANS/MISS/ARTI/DOCT** (49)](#t1) | - | - | Traitement |
| **49.2** | [**Calcul JH absence** (49.1)](#t2) | - | - | Calcul |
| 49.2.1 | [Calcul regul ANS (49.2)](#t3) | - | - | |

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
| 366 | pms_print_param |  | DB | R |   |   | 1 |
| 825 | fac_hebergement_pro | Hebergement (chambres) | DB |   |   | L | 1 |
| 826 | wording_mention_legal |  | DB | R |   |   | 1 |
| 834 | tpe_par_terminal |  | DB | R |   |   | 1 |

### Colonnes par table (2 / 3 tables avec colonnes identifiees)

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

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 834 - tpe_par_terminal (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P.Date debut | R | Date |
| B | P.Date fin | R | Date |
| C | P.Code village | R | Alpha |
| D | P.Qualite | R | Alpha |
| E | P.Lieu sejour | R | Alpha |
| F | P.Nom lieu | R | Alpha |
| G | P.Gestion crise ? | R | Logical |
| H | V.Nb JH du mois | R | Numeric |
| I | V.Total JH | R | Numeric |
| J | V.Date debut | R | Date |
| K | V.Date fin | R | Date |
| L | V.Nb jh absence | R | Numeric |
| M | V.Date debut premiere periode | R | Date |
| N | V.Date fin derniere periode | R | Date |
| O | V.Date debut sej | R | Date |
| P | V.Date fin sej | R | Date |
| Q | V.tot jh regul | R | Numeric |
| R | V.Heure debut premiere periode | R | Alpha |
| S | V.Heure fin derniere periode | R | Alpha |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (7)

Variables recues du programme appelant ([Edition et envoi effectif (IDE 64)](PBP-IDE-64.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P.Date debut | Date | - |
| B | P.Date fin | Date | - |
| C | P.Code village | Alpha | - |
| D | P.Qualite | Alpha | 1x parametre entrant |
| E | P.Lieu sejour | Alpha | 1x parametre entrant |
| F | P.Nom lieu | Alpha | 5x parametre entrant |
| G | P.Gestion crise ? | Logical | 3x parametre entrant |

### 11.2 Variables de session (12)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| H | V.Nb JH du mois | Numeric | 1x session |
| I | V.Total JH | Numeric | 1x session |
| J | V.Date debut | Date | - |
| K | V.Date fin | Date | - |
| L | V.Nb jh absence | Numeric | - |
| M | V.Date debut premiere periode | Date | - |
| N | V.Date fin derniere periode | Date | - |
| O | V.Date debut sej | Date | - |
| P | V.Date fin sej | Date | - |
| Q | V.tot jh regul | Numeric | - |
| R | V.Heure debut premiere periode | Alpha | - |
| S | V.Heure fin derniere periode | Alpha | - |

<details>
<summary>Toutes les 19 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| P0 | **A** | P.Date debut | Date |
| P0 | **B** | P.Date fin | Date |
| P0 | **C** | P.Code village | Alpha |
| P0 | **D** | P.Qualite | Alpha |
| P0 | **E** | P.Lieu sejour | Alpha |
| P0 | **F** | P.Nom lieu | Alpha |
| P0 | **G** | P.Gestion crise ? | Logical |
| V. | **H** | V.Nb JH du mois | Numeric |
| V. | **I** | V.Total JH | Numeric |
| V. | **J** | V.Date debut | Date |
| V. | **K** | V.Date fin | Date |
| V. | **L** | V.Nb jh absence | Numeric |
| V. | **M** | V.Date debut premiere periode | Date |
| V. | **N** | V.Date fin derniere periode | Date |
| V. | **O** | V.Date debut sej | Date |
| V. | **P** | V.Date fin sej | Date |
| V. | **Q** | V.tot jh regul | Numeric |
| V. | **R** | V.Heure debut premiere periode | Alpha |
| V. | **S** | V.Heure fin derniere periode | Alpha |

</details>

## 12. EXPRESSIONS

**76 / 76 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCULATION | 8 | 0 |
| CONDITION | 23 | 5 |
| CONSTANTE | 4 | 0 |
| FORMAT | 1 | 0 |
| OTHER | 37 | 0 |
| NEGATION | 2 | 0 |
| STRING | 1 | 0 |

### 12.2 Expressions cles par type

#### CALCULATION (8 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 45 | `[AO]+([DD]-[DC]-1)` | - |
| CALCULATION | 35 | `[AN]+[DI]` | - |
| CALCULATION | 76 | `{1,88}+V.Total JH [I]` | - |
| CALCULATION | 75 | `(V.Nb JH du mois [H]-P.Gestion crise ? [G])+1` | - |
| CALCULATION | 12 | `[AN]+[AO]` | - |
| ... | | *+3 autres* | |

#### CONDITION (23 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 72 | `IF(P.Qualite [D]<{1,107},{1,107},P.Qualite [D])` | [RM-004](#rm-RM-004) |
| CONDITION | 73 | `IF(P.Lieu sejour [E]>{1,108},{1,108},P.Lieu sejour [E])` | [RM-005](#rm-RM-005) |
| CONDITION | 9 | `IF([AS]>P.Gestion crise ? [G],P.Gestion crise ? [G],[AS])` | [RM-003](#rm-RM-003) |
| CONDITION | 7 | `IF([CS]='O','FACTURABLE','NON&nbsp;FACTURABLE')` | [RM-001](#rm-RM-001) |
| CONDITION | 8 | `IF([AQ]<P.Nom lieu [F],P.Nom lieu [F],[AQ])` | [RM-002](#rm-RM-002) |
| ... | | *+18 autres* | |

#### CONSTANTE (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 42 | `''` | - |
| CONSTANTE | 74 | `0` | - |
| CONSTANTE | 6 | `'O'` | - |
| CONSTANTE | 24 | `0` | - |

#### FORMAT (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| FORMAT | 1 | `Trim(Translate('%club_exportdata%'))&'trsft\'&Trim([CA])&IF([CW]<>'','_'&Trim([CW])&'_','_')&'EFF_Deficit_'&Trim([CU])&'_'&IF([DE],Trim(DStr(Date()-2,'YYYYMM')),Trim(DStr(Date(),'YYYYMM')))&'.htm'` | - |

#### OTHER (37 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 60 | `MlsTrans('Début de séjour')` | - |
| OTHER | 59 | `MlsTrans('Lien de parenté')` | - |
| OTHER | 62 | `MlsTrans('Gratuité ou Facturation')` | - |
| OTHER | 61 | `MlsTrans('Fin de séjour')` | - |
| OTHER | 58 | `MlsTrans('Date de naissance')` | - |
| ... | | *+32 autres* | |

#### NEGATION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| NEGATION | 37 | `NOT ExpCalc('72'EXP)` | - |
| NEGATION | 36 | `NOT ExpCalc('70'EXP)` | - |

#### STRING (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| STRING | 3 | `Trim(VG37)` | - |

### 12.3 Toutes les expressions (76)

<details>
<summary>Voir les 76 expressions</summary>

#### CALCULATION (8)

| IDE | Expression Decodee |
|-----|-------------------|
| 11 | `[AO]-[CJ]` |
| 12 | `[AN]+[AO]` |
| 28 | `[AO]+1` |
| 29 | `[AO]+0.5` |
| 35 | `[AN]+[DI]` |
| 45 | `[AO]+([DD]-[DC]-1)` |
| 75 | `(V.Nb JH du mois [H]-P.Gestion crise ? [G])+1` |
| 76 | `{1,88}+V.Total JH [I]` |

#### CONDITION (23)

| IDE | Expression Decodee |
|-----|-------------------|
| 7 | `IF([CS]='O','FACTURABLE','NON&nbsp;FACTURABLE')` |
| 8 | `IF([AQ]<P.Nom lieu [F],P.Nom lieu [F],[AQ])` |
| 9 | `IF([AS]>P.Gestion crise ? [G],P.Gestion crise ? [G],[AS])` |
| 72 | `IF(P.Qualite [D]<{1,107},{1,107},P.Qualite [D])` |
| 73 | `IF(P.Lieu sejour [E]>{1,108},{1,108},P.Lieu sejour [E])` |
| 10 | `[CL]='GO' AND [CM]=[CU]` |
| 14 | `[CU]='ANS'` |
| 15 | `[CU]='MISS'` |
| 16 | `[CU]='ARTI'` |
| 17 | `[CU]='DOCT'` |
| 18 | `CndRange([CW]<>'',[CW])` |
| 19 | `[CW]<>''` |
| 22 | `[CB]<[DC] OR [DC]=0` |
| 23 | `[CC]>[DD] OR [DD]=0` |
| 27 | `[DG]<[DC]` |
| 30 | `[DH]>[DD]` |
| 33 | `[AQ]<[DG] OR [DG]=0` |
| 34 | `[AS]>[DH] OR [DH]=0` |
| 46 | `[AO]<>0` |
| 38 | `Val([DJ],'2')<=15` |
| 39 | `Val([DJ],'2')<23` |
| 40 | `Val([DK],'2')>=12` |
| 41 | `Val([DK],'2')>=20` |

#### CONSTANTE (4)

| IDE | Expression Decodee |
|-----|-------------------|
| 6 | `'O'` |
| 24 | `0` |
| 42 | `''` |
| 74 | `0` |

#### FORMAT (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 1 | `Trim(Translate('%club_exportdata%'))&'trsft\'&Trim([CA])&IF([CW]<>'','_'&Trim([CW])&'_','_')&'EFF_Deficit_'&Trim([CU])&'_'&IF([DE],Trim(DStr(Date()-2,'YYYYMM')),Trim(DStr(Date(),'YYYYMM')))&'.htm'` |

#### OTHER (37)

| IDE | Expression Decodee |
|-----|-------------------|
| 2 | `GetParam('SOCIETE')` |
| 4 | `Day(EOM(P.Nom lieu [F]))` |
| 5 | `CMonth(P.Nom lieu [F])` |
| 13 | `EOM(P.Nom lieu [F])` |
| 20 | `[CB]` |
| 21 | `[CC]` |
| 25 | `P.Gestion crise ? [G]` |
| 26 | `P.Nom lieu [F]` |
| 31 | `[AQ]` |
| 32 | `[AS]` |
| 43 | `[DL]` |
| 44 | `[DM]` |
| 47 | `MlsTrans('Nom du Chef de Village')` |
| 48 | `MlsTrans('Signature du Chef de Village')` |
| 49 | `MlsTrans('Village')` |
| 50 | `MlsTrans('PAS INSCRITS EN NA')` |
| 51 | `MlsTrans('Mois')` |
| 52 | `MlsTrans('Lieu de séjour')` |
| 53 | `MlsTrans('Nombre de jours du mois')` |
| 54 | `MlsTrans('Total JH et montant total facturé du mois')` |
| 55 | `MlsTrans('Total régularisation du mois')` |
| 56 | `MlsTrans('Nom')` |
| 57 | `MlsTrans('Prénom')` |
| 58 | `MlsTrans('Date de naissance')` |
| 59 | `MlsTrans('Lien de parenté')` |
| 60 | `MlsTrans('Début de séjour')` |
| 61 | `MlsTrans('Fin de séjour')` |
| 62 | `MlsTrans('Gratuité ou Facturation')` |
| 63 | `MlsTrans('Nombre de JH')` |
| 64 | `MlsTrans('Dossier')` |
| 65 | `MlsTrans('Accompagnants non salariés')` |
| 66 | `MlsTrans('GO Docteur')` |
| 67 | `MlsTrans('GO Mission')` |
| 68 | `MlsTrans('GO Artistes')` |
| 69 | `{1,1}` |
| 70 | `{1,2}` |
| 71 | `{1,3}` |

#### NEGATION (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 36 | `NOT ExpCalc('70'EXP)` |
| 37 | `NOT ExpCalc('72'EXP)` |

#### STRING (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 3 | `Trim(VG37)` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Edition et envoi effectif (IDE 64)](PBP-IDE-64.md) -> **Deficit ANS/MISS/ARTI/DOCT (IDE 49)**

Main -> ... -> [Edition effectif mensuel (IDE 56)](PBP-IDE-56.md) -> **Deficit ANS/MISS/ARTI/DOCT (IDE 49)**

Main -> ... -> [Edition effectif mensuel (IDE 413)](PBP-IDE-413.md) -> **Deficit ANS/MISS/ARTI/DOCT (IDE 49)**

```mermaid
graph LR
    T49[49 Deficit ANSMISSARTI...]
    style T49 fill:#58a6ff
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
    CC56 --> T49
    CC64 --> T49
    CC413 --> T49
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [64](PBP-IDE-64.md) | Edition et envoi effectif | 8 |
| [56](PBP-IDE-56.md) | Edition effectif mensuel | 4 |
| [413](PBP-IDE-413.md) | Edition effectif mensuel | 2 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T49[49 Deficit ANSMISSARTI...]
    style T49 fill:#58a6ff
    NONE[Aucun callee]
    T49 -.-> NONE
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
| Lignes de logique | 123 | Programme compact |
| Expressions | 76 | Logique moderee |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 123) | Code sain |
| Regles metier | 5 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 0 ecran, 1 traitement)

- **Strategie** : 1 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

#### Calcul (2 taches: 0 ecran, 2 traitements)

- **Strategie** : Services de calcul purs (Domain Services).
- Migrer la logique de calcul (stock, compteurs, montants)

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 08:56*
