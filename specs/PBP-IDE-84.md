# PBP IDE 84 - Deficit Stagiaire V3

> **Analyse**: Phases 1-4 2026-02-03 09:14 -> 09:14 (19s) | Assemblage 09:14
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBP |
| IDE Position | 84 |
| Nom Programme | Deficit Stagiaire V3 |
| Fichier source | `Prg_84.xml` |
| Domaine metier | General |
| Taches | 2 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Deficit Stagiaire V3** assure la gestion complete de ce processus, accessible depuis [Edition effectif mensuel V3 (IDE 66)](PBP-IDE-66.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (2 taches) : traitements metier divers

**Logique metier** : 2 regles identifiees couvrant conditions metier.

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (2 taches)

Traitements internes.

---

#### <a id="t2"></a>84 - GO STAG

**Role** : Traitement : GO STAG.

---

#### <a id="t6"></a>84.1 - Deficit GO STAG V3 [[ECRAN]](#ecran-t6)

**Role** : Traitement : Deficit GO STAG V3.
**Ecran** : 883 x 631 DLU | [Voir mockup](#ecran-t6)


## 5. REGLES METIER

2 regles identifiees:

### Autres (2 regles)

#### <a id="rm-RM-001"></a>[RM-001] Si [AQ]<{1 alors 1} sinon {1,1},[AQ])

| Element | Detail |
|---------|--------|
| **Condition** | `[AQ]<{1` |
| **Si vrai** | 1} |
| **Si faux** | {1,1},[AQ]) |
| **Expression source** | Expression 18 : `IF([AQ]<{1,1},{1,1},[AQ])` |
| **Exemple** | Si [AQ]<{1 â†’ 1}. Sinon â†’ {1,1},[AQ]) |

#### <a id="rm-RM-002"></a>[RM-002] Si [AS]>{1 alors 2} sinon {1,2},[AS])

| Element | Detail |
|---------|--------|
| **Condition** | `[AS]>{1` |
| **Si vrai** | 2} |
| **Si faux** | {1,2},[AS]) |
| **Expression source** | Expression 19 : `IF([AS]>{1,2},{1,2},[AS])` |
| **Exemple** | Si [AS]>{1 â†’ 2}. Sinon â†’ {1,2},[AS]) |

## 6. CONTEXTE

- **Appele par**: [Edition effectif mensuel V3 (IDE 66)](PBP-IDE-66.md)
- **Appelle**: 0 programmes | **Tables**: 2 (W:0 R:1 L:1) | **Taches**: 2 | **Expressions**: 39

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (2 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **84.1** | [**GO STAG** (84)](#t2) | - | - | Traitement |
| 84.1.1 | [Deficit GO STAG V3 (84.1)](#t6) [mockup](#ecran-t6) | - | 883x631 | |

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
| A | V.Nb repas | R | Numeric |
| B | V.Date debut | R | Date |
| C | V.Date fin | R | Date |
| D | V.Nb jh absence | R | Numeric |
| E | V.Date debut premiere periode | R | Date |
| F | V.Date fin derniere periode | R | Date |
| G | V.Date debut sej | R | Date |
| H | V.Date fin sej | R | Date |
| I | V.Heure debut premiere periode | R | Alpha |
| J | V.Heure fin derniere periode | R | Alpha |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (6)

Variables recues du programme appelant ([Edition effectif mensuel V3 (IDE 66)](PBP-IDE-66.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P.Date debut | Date | 2x parametre entrant |
| B | P.Date fin | Date | - |
| C | P.Code village | Alpha | - |
| D | P.Lieu sejour | Alpha | 1x parametre entrant |
| E | P.Nom lieu | Alpha | 2x parametre entrant |
| F | P.Gestion crise ? | Logical | - |

### 11.2 Variables de session (4)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| G | V.Total nb jh | Numeric | - |
| H | V.Total jh | Numeric | - |
| I | V.Heure debut premiere periode | Alpha | - |
| J | V.Heure fin derniere periode | Alpha | - |

## 12. EXPRESSIONS

**39 / 39 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCULATION | 3 | 0 |
| CONDITION | 9 | 2 |
| CONSTANTE | 7 | 0 |
| FORMAT | 1 | 0 |
| OTHER | 18 | 0 |
| STRING | 1 | 0 |

### 12.2 Expressions cles par type

#### CALCULATION (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 39 | `[ER]+([EH]+[EL])` | - |
| CALCULATION | 38 | `{1,3}+([EH]+[EL])/2` | - |
| CALCULATION | 20 | `{1,12}+{1,3}` | - |

#### CONDITION (9 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 19 | `IF([AS]>{1,2},{1,2},[AS])` | [RM-002](#rm-RM-002) |
| CONDITION | 18 | `IF([AQ]<{1,1},{1,1},[AQ])` | [RM-001](#rm-RM-001) |
| CONDITION | 29 | `[AQ]<[DG] OR [DG]=0` | - |
| CONDITION | 30 | `[AS]>[DH] OR [DH]=0` | - |
| CONDITION | 34 | `[ER]<>0` | - |
| ... | | *+4 autres* | |

#### CONSTANTE (7 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 31 | `''` | - |
| CONSTANTE | 35 | `'GO'` | - |
| CONSTANTE | 36 | `'STAG'` | - |
| CONSTANTE | 26 | `0` | - |
| CONSTANTE | 1 | `'Activité'` | - |
| ... | | *+2 autres* | |

#### FORMAT (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| FORMAT | 4 | `Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(P.Lieu sejour [D])&IF(P.Nom lieu [E]<>'','_'&Trim(P.Nom lieu [E])&'_','_')&'EFF_Deficit_STAG_'&IF([K],Trim(DStr(Date()-2,'YYYYMM')),Trim(DStr(Date(),'YYYYMM')))&'.htm'` | - |

#### OTHER (18 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 22 | `[CB]` | - |
| OTHER | 23 | `[CC]` | - |
| OTHER | 16 | `{1,1}` | - |
| OTHER | 17 | `[DY]` | - |
| OTHER | 27 | `[AQ]` | - |
| ... | | *+13 autres* | |

#### STRING (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| STRING | 5 | `Trim(VG37)` | - |

### 12.3 Toutes les expressions (39)

<details>
<summary>Voir les 39 expressions</summary>

#### CALCULATION (3)

| IDE | Expression Decodee |
|-----|-------------------|
| 20 | `{1,12}+{1,3}` |
| 38 | `{1,3}+([EH]+[EL])/2` |
| 39 | `[ER]+([EH]+[EL])` |

#### CONDITION (9)

| IDE | Expression Decodee |
|-----|-------------------|
| 18 | `IF([AQ]<{1,1},{1,1},[AQ])` |
| 19 | `IF([AS]>{1,2},{1,2},[AS])` |
| 8 | `P.Nom lieu [E]<>''` |
| 21 | `CndRange({1,5}<>'',{1,5})` |
| 24 | `[CB]<[DC] OR [DC]=0` |
| 25 | `[CC]>[DD] OR [DD]=0` |
| 29 | `[AQ]<[DG] OR [DG]=0` |
| 30 | `[AS]>[DH] OR [DH]=0` |
| 34 | `[ER]<>0` |

#### CONSTANTE (7)

| IDE | Expression Decodee |
|-----|-------------------|
| 1 | `'Activité'` |
| 2 | `'GO Stagiaires'` |
| 3 | `'800200385'` |
| 26 | `0` |
| 31 | `''` |
| 35 | `'GO'` |
| 36 | `'STAG'` |

#### FORMAT (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 4 | `Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(P.Lieu sejour [D])&IF(P.Nom lieu [E]<>'','_'&Trim(P.Nom lieu [E])&'_','_')&'EFF_Deficit_STAG_'&IF([K],Trim(DStr(Date()-2,'YYYYMM')),Trim(DStr(Date(),'YYYYMM')))&'.htm'` |

#### OTHER (18)

| IDE | Expression Decodee |
|-----|-------------------|
| 6 | `CMonth(P.Date debut [A])` |
| 7 | `Day(EOM(P.Date debut [A]))` |
| 9 | `{1,1}` |
| 10 | `{1,2}` |
| 11 | `GetParam('SOCIETE')` |
| 12 | `[EC]` |
| 13 | `[ED]` |
| 14 | `[EE]` |
| 15 | `{1,2}` |
| 16 | `{1,1}` |
| 17 | `[DY]` |
| 22 | `[CB]` |
| 23 | `[CC]` |
| 27 | `[AQ]` |
| 28 | `[AS]` |
| 32 | `[DL]` |
| 33 | `[DM]` |
| 37 | `[DZ]` |

#### STRING (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 5 | `Trim(VG37)` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Edition effectif mensuel V3 (IDE 66)](PBP-IDE-66.md) -> **Deficit Stagiaire V3 (IDE 84)**

```mermaid
graph LR
    T84[84 Deficit Stagiaire V3]
    style T84 fill:#58a6ff
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
    CC66 --> T84
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [66](PBP-IDE-66.md) | Edition effectif mensuel V3 | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T84[84 Deficit Stagiaire V3]
    style T84 fill:#58a6ff
    NONE[Aucun callee]
    T84 -.-> NONE
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
| Lignes de logique | 91 | Programme compact |
| Expressions | 39 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 91) | Code sain |
| Regles metier | 2 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (2 taches: 1 ecran, 1 traitement)

- **Strategie** : Orchestrateur avec 1 ecrans (Razor/React) et 1 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 09:14*
