# PBP IDE 77 - Deficit ANS V3

> **Analyse**: Phases 1-4 2026-02-03 09:11 -> 09:11 (19s) | Assemblage 09:11
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBP |
| IDE Position | 77 |
| Nom Programme | Deficit ANS V3 |
| Fichier source | `Prg_77.xml` |
| Domaine metier | General |
| Taches | 2 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Deficit ANS V3** assure la gestion complete de ce processus, accessible depuis [Edition effectif mensuel V3 (IDE 66)](PBP-IDE-66.md).

Le flux de traitement s'organise en **2 blocs fonctionnels** :

- **Calcul** (1 tache) : calculs de montants, stocks ou compteurs
- **Traitement** (1 tache) : traitements metier divers

**Logique metier** : 3 regles identifiees couvrant conditions metier.

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (1 tache)

- **77** - Deficit ANS V3

#### Phase 2 : Calcul (1 tache)

- **77.1** - Calcul regul ANS

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>77 - Deficit ANS V3

**Role** : Traitement : Deficit ANS V3.


### 3.2 Calcul (1 tache)

Calculs metier : montants, stocks, compteurs.

---

#### <a id="t3"></a>77.1 - Calcul regul ANS

**Role** : Calcul : Calcul regul ANS.
**Variables liees** : P (V.tot jh regul)


## 5. REGLES METIER

3 regles identifiees:

### Autres (3 regles)

#### <a id="rm-RM-001"></a>[RM-001] Si [CS] vaut 'O' alors 'FACTURABLE', sinon 'NON&nbsp;FACTURABLE'

| Element | Detail |
|---------|--------|
| **Condition** | `[CS]='O'` |
| **Si vrai** | 'FACTURABLE' |
| **Si faux** | 'NON&nbsp;FACTURABLE') |
| **Expression source** | Expression 16 : `IF([CS]='O','FACTURABLE','NON&nbsp;FACTURABLE')` |
| **Exemple** | Si [CS]='O' â†’ 'FACTURABLE'. Sinon â†’ 'NON&nbsp;FACTURABLE') |

#### <a id="rm-RM-002"></a>[RM-002] Si [AQ]<P.Gestion crise ? [F] alors P.Gestion crise ? [F] sinon [AQ])

| Element | Detail |
|---------|--------|
| **Condition** | `[AQ]<P.Gestion crise ? [F]` |
| **Si vrai** | P.Gestion crise ? [F] |
| **Si faux** | [AQ]) |
| **Variables** | F (P.Gestion crise ?) |
| **Expression source** | Expression 17 : `IF([AQ]<P.Gestion crise ? [F],P.Gestion crise ? [F],[AQ])` |
| **Exemple** | Si [AQ]<P.Gestion crise ? [F] â†’ P.Gestion crise ? [F]. Sinon â†’ [AQ]) |

#### <a id="rm-RM-003"></a>[RM-003] Si [AS]>V.Nb JH du mois [G] alors V.Nb JH du mois [G] sinon [AS])

| Element | Detail |
|---------|--------|
| **Condition** | `[AS]>V.Nb JH du mois [G]` |
| **Si vrai** | V.Nb JH du mois [G] |
| **Si faux** | [AS]) |
| **Variables** | G (V.Nb JH du mois) |
| **Expression source** | Expression 18 : `IF([AS]>V.Nb JH du mois [G],V.Nb JH du mois [G],[AS])` |
| **Exemple** | Si [AS]>V.Nb JH du mois [G] â†’ V.Nb JH du mois [G]. Sinon â†’ [AS]) |

## 6. CONTEXTE

- **Appele par**: [Edition effectif mensuel V3 (IDE 66)](PBP-IDE-66.md)
- **Appelle**: 0 programmes | **Tables**: 2 (W:0 R:2 L:1) | **Taches**: 2 | **Expressions**: 46

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (2 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **77.1** | [**Deficit ANS V3** (77)](#t1) | - | - | Traitement |
| **77.2** | [**Calcul regul ANS** (77.1)](#t3) | - | - | Calcul |

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
| 949 | Table_949 |  | MEM | R |   | L | 2 |

### Colonnes par table (1 / 2 tables avec colonnes identifiees)

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
| H | V.Total JH | R | Numeric |
| I | V.Date debut | R | Date |
| J | V.Date fin | R | Date |
| K | V.Nb jh absence | R | Numeric |
| L | V.Date debut premiere periode | R | Date |
| M | V.Date fin derniere periode | R | Date |
| N | V.Date debut sej | R | Date |
| O | V.Date fin sej | R | Date |
| P | V.tot jh regul | R | Numeric |
| Q | V.Heure debut premiere periode | R | Alpha |
| R | V.Heure fin derniere periode | R | Alpha |

</details>

<details>
<summary>Table 949 - Table_949 (R/L) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

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
| H | V.Total JH | Numeric | - |
| I | V.Date debut | Date | - |
| J | V.Date fin | Date | - |
| K | V.Nb jh absence | Numeric | - |
| L | V.Date debut premiere periode | Date | - |
| M | V.Date fin derniere periode | Date | - |
| N | V.Date debut sej | Date | - |
| O | V.Date fin sej | Date | - |
| P | V.tot jh regul | Numeric | - |
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
| V. | **H** | V.Total JH | Numeric |
| V. | **I** | V.Date debut | Date |
| V. | **J** | V.Date fin | Date |
| V. | **K** | V.Nb jh absence | Numeric |
| V. | **L** | V.Date debut premiere periode | Date |
| V. | **M** | V.Date fin derniere periode | Date |
| V. | **N** | V.Date debut sej | Date |
| V. | **O** | V.Date fin sej | Date |
| V. | **P** | V.tot jh regul | Numeric |
| V. | **Q** | V.Heure debut premiere periode | Alpha |
| V. | **R** | V.Heure fin derniere periode | Alpha |

</details>

## 12. EXPRESSIONS

**46 / 46 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCULATION | 4 | 0 |
| CONDITION | 13 | 3 |
| CONSTANTE | 7 | 0 |
| FORMAT | 1 | 0 |
| OTHER | 20 | 0 |
| STRING | 1 | 0 |

### 12.2 Expressions cles par type

#### CALCULATION (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 40 | `[AO]+(([EH]+[EL])/2)` | - |
| CALCULATION | 44 | `{1,113}+(([Y]+[AC])*0.5)` | - |
| CALCULATION | 19 | `[AN]+[AO]` | - |
| CALCULATION | 31 | `[AN]+[DI]` | - |

#### CONDITION (13 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 18 | `IF([AS]>V.Nb JH du mois [G],V.Nb JH du mois [G],[AS])` | [RM-003](#rm-RM-003) |
| CONDITION | 17 | `IF([AQ]<P.Gestion crise ? [F],P.Gestion crise ? [F],[AQ])` | [RM-002](#rm-RM-002) |
| CONDITION | 16 | `IF([CS]='O','FACTURABLE','NON&nbsp;FACTURABLE')` | [RM-001](#rm-RM-001) |
| CONDITION | 30 | `[AS]>[DH] OR [DH]=0` | - |
| CONDITION | 29 | `[AQ]<[DG] OR [DG]=0` | - |
| ... | | *+8 autres* | |

#### CONSTANTE (7 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 37 | `'ANS'` | - |
| CONSTANTE | 39 | `0` | - |
| CONSTANTE | 41 | `'REGANS'` | - |
| CONSTANTE | 36 | `'GO'` | - |
| CONSTANTE | 1 | `'800210385'` | - |
| ... | | *+2 autres* | |

#### FORMAT (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| FORMAT | 3 | `Trim(Translate('%club_exportdata%'))&'trsft\'&Trim([CA])&IF([CW]<>'','_'&Trim([CW])&'_','_')&'EFF_Deficit_ANS'&'_'&IF([DE],Trim(DStr(Date()-2,'YYYYMM')),Trim(DStr(Date(),'YYYYMM')))&'.htm'` | - |

#### OTHER (20 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 27 | `[AQ]` | - |
| OTHER | 28 | `[AS]` | - |
| OTHER | 23 | `[CC]` | - |
| OTHER | 15 | `CMonth(P.Gestion crise ? [F])` | - |
| OTHER | 22 | `[CB]` | - |
| ... | | *+15 autres* | |

#### STRING (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| STRING | 13 | `Trim(VG37)` | - |

### 12.3 Toutes les expressions (46)

<details>
<summary>Voir les 46 expressions</summary>

#### CALCULATION (4)

| IDE | Expression Decodee |
|-----|-------------------|
| 19 | `[AN]+[AO]` |
| 31 | `[AN]+[DI]` |
| 40 | `[AO]+(([EH]+[EL])/2)` |
| 44 | `{1,113}+(([Y]+[AC])*0.5)` |

#### CONDITION (13)

| IDE | Expression Decodee |
|-----|-------------------|
| 16 | `IF([CS]='O','FACTURABLE','NON&nbsp;FACTURABLE')` |
| 17 | `IF([AQ]<P.Gestion crise ? [F],P.Gestion crise ? [F],[AQ])` |
| 18 | `IF([AS]>V.Nb JH du mois [G],V.Nb JH du mois [G],[AS])` |
| 4 | `[EA]=''` |
| 20 | `CndRange([CW]<>'',[CW])` |
| 21 | `[CW]<>''` |
| 24 | `[CB]<[DC] OR [DC]=0` |
| 25 | `[CC]>[DD] OR [DD]=0` |
| 29 | `[AQ]<[DG] OR [DG]=0` |
| 30 | `[AS]>[DH] OR [DH]=0` |
| 35 | `[AO]<>0` |
| 45 | `[W]='DEJ' OR [W]='DDE'` |
| 46 | `[W]='DIN' OR [W]='DDE'` |

#### CONSTANTE (7)

| IDE | Expression Decodee |
|-----|-------------------|
| 1 | `'800210385'` |
| 26 | `0` |
| 32 | `''` |
| 36 | `'GO'` |
| 37 | `'ANS'` |
| 39 | `0` |
| 41 | `'REGANS'` |

#### FORMAT (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 3 | `Trim(Translate('%club_exportdata%'))&'trsft\'&Trim([CA])&IF([CW]<>'','_'&Trim([CW])&'_','_')&'EFF_Deficit_ANS'&'_'&IF([DE],Trim(DStr(Date()-2,'YYYYMM')),Trim(DStr(Date(),'YYYYMM')))&'.htm'` |

#### OTHER (20)

| IDE | Expression Decodee |
|-----|-------------------|
| 2 | `GetParam('SOCIETE')` |
| 5 | `P.Gestion crise ? [F]` |
| 6 | `V.Nb JH du mois [G]` |
| 7 | `[EC]` |
| 8 | `[ED]` |
| 9 | `[EE]` |
| 10 | `V.Nb JH du mois [G]` |
| 11 | `P.Gestion crise ? [F]` |
| 12 | `[DY]` |
| 14 | `Day(EOM(P.Gestion crise ? [F]))` |
| 15 | `CMonth(P.Gestion crise ? [F])` |
| 22 | `[CB]` |
| 23 | `[CC]` |
| 27 | `[AQ]` |
| 28 | `[AS]` |
| 33 | `[DL]` |
| 34 | `[DM]` |
| 38 | `[DZ]` |
| 42 | `{1,6}` |
| 43 | `{1,7}` |

#### STRING (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 13 | `Trim(VG37)` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Edition effectif mensuel V3 (IDE 66)](PBP-IDE-66.md) -> **Deficit ANS V3 (IDE 77)**

```mermaid
graph LR
    T77[77 Deficit ANS V3]
    style T77 fill:#58a6ff
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
    CC66 --> T77
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [66](PBP-IDE-66.md) | Edition effectif mensuel V3 | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T77[77 Deficit ANS V3]
    style T77 fill:#58a6ff
    NONE[Aucun callee]
    T77 -.-> NONE
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
| Lignes de logique | 113 | Programme compact |
| Expressions | 46 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 113) | Code sain |
| Regles metier | 3 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 0 ecran, 1 traitement)

- **Strategie** : 1 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

#### Calcul (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Services de calcul purs (Domain Services).
- Migrer la logique de calcul (stock, compteurs, montants)

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 09:11*
