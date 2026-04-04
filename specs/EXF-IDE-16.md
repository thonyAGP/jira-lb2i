# EXF IDE 16 - Set Village Address

> **Analyse**: Phases 1-4 2026-02-03 10:57 -> 10:57 (18s) | Assemblage 10:57
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | EXF |
| IDE Position | 16 |
| Nom Programme | Set Village Address |
| Fichier source | `Prg_16.xml` |
| Dossier IDE | Printer |
| Taches | 2 (0 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Set Village Address** assure la gestion complete de ce processus, accessible depuis [Get Printer (IDE 17)](EXF-IDE-17.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (2 taches) : traitements metier divers

**Donnees modifiees** : 1 tables en ecriture (pv_budget).

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (2 taches)

Traitements internes.

---

#### <a id="t1"></a>16 - Set Village Address

**Role** : Traitement : Set Village Address.

---

#### <a id="t2"></a>16.1 - Load Buffer

**Role** : Traitement : Load Buffer.
**Variables liees** : A (Buffer)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Get Printer (IDE 17)](EXF-IDE-17.md)
- **Appelle**: 0 programmes | **Tables**: 1 (W:1 R:0 L:0) | **Taches**: 2 | **Expressions**: 20

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (2 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **16.1** | [**Set Village Address** (16)](#t1) | MDI | - | Traitement |
| 16.1.1 | [Load Buffer (16.1)](#t2) | MDI | - | |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Traitement principal]
    UPDATE[MAJ 1 tables]
    ENDOK([END OK])

    START --> INIT --> SAISIE
    SAISIE --> UPDATE --> ENDOK

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
| 372 | pv_budget |  | DB |   | **W** |   | 1 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 372 - pv_budget (**W**) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | Buffer | W | Alpha |
| B | CounterTel | W | Numeric |
| C | CounterFax | W | Numeric |

</details>

## 11. VARIABLES

### 11.1 Autres (3)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | Buffer | Alpha | [16.1](#t2) |
| B | CounterTel | Numeric | 1x refs |
| C | CounterFax | Numeric | - |

## 12. EXPRESSIONS

**20 / 20 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONCATENATION | 1 | 0 |
| CONDITION | 4 | 0 |
| CALCULATION | 1 | 0 |
| CONSTANTE | 4 | 0 |
| OTHER | 10 | 0 |

### 12.2 Expressions cles par type

#### CONCATENATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 13 | `Trim ({1,17})&Left (IF (CounterTel [B]='','',CounterTel [B])&VarCurr ('{1,1}'VAR+Counter (0)),128)&'\|'` | - |

#### CONDITION (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 16 | `VarName ('{1,1}'VAR+Counter (0))='PMS Village.FAX'` | - |
| CONDITION | 12 | `Counter (0)>=10` | - |
| CONDITION | 14 | `VarCurr ('{1,1}'VAR+Counter (0))<>''` | - |
| CONDITION | 15 | `VarName ('{1,1}'VAR+Counter (0))='PMS Village.PHONE'` | - |

#### CALCULATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 17 | `Buffer [A]+1` | - |

#### CONSTANTE (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 19 | `'Fax  '` | - |
| CONSTANTE | 20 | `''` | - |
| CONSTANTE | 11 | `'\|'` | - |
| CONSTANTE | 18 | `'Tel  '` | - |

#### OTHER (10 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 7 | `SetParam ('VI_FAXN',MID ([Q],775,128))` | - |
| OTHER | 6 | `SetParam ('VI_PHON',MID ([Q],646,128))` | - |
| OTHER | 8 | `SetParam ('VI_MAIL',MID ([Q],904,128))` | - |
| OTHER | 10 | `SetParam ('VI_VATN',MID ([Q],1162,128))` | - |
| OTHER | 9 | `SetParam ('VI_SIRE',MID ([Q],1033,128))` | - |
| ... | | *+5 autres* | |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Get Printer (IDE 17)](EXF-IDE-17.md) -> **Set Village Address (IDE 16)**

```mermaid
graph LR
    T16[16 Set Village Address]
    style T16 fill:#58a6ff
    CC14[14 Menu listes]
    style CC14 fill:#8b5cf6
    CC13[13 Menu ventes]
    style CC13 fill:#8b5cf6
    CC40[40 Annulation Ventes]
    style CC40 fill:#8b5cf6
    CC35[35 Ventes Excursions]
    style CC35 fill:#8b5cf6
    CC20[20 Raz Current Printer]
    style CC20 fill:#f59e0b
    CC11[11 Liste ventes N°vente]
    style CC11 fill:#f59e0b
    CC10[10 Disponibilites@ ver...]
    style CC10 fill:#f59e0b
    CC18[18 Printer choice]
    style CC18 fill:#f59e0b
    CC12[12 Liste ventesExcursion]
    style CC12 fill:#f59e0b
    CC17[17 Get Printer]
    style CC17 fill:#3fb950
    CC10 --> CC17
    CC11 --> CC17
    CC12 --> CC17
    CC18 --> CC17
    CC20 --> CC17
    CC13 --> CC10
    CC14 --> CC10
    CC35 --> CC10
    CC40 --> CC10
    CC13 --> CC11
    CC14 --> CC11
    CC35 --> CC11
    CC40 --> CC11
    CC13 --> CC12
    CC14 --> CC12
    CC35 --> CC12
    CC40 --> CC12
    CC13 --> CC18
    CC14 --> CC18
    CC35 --> CC18
    CC40 --> CC18
    CC13 --> CC20
    CC14 --> CC20
    CC35 --> CC20
    CC40 --> CC20
    CC17 --> T16
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [17](EXF-IDE-17.md) | Get Printer | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T16[16 Set Village Address]
    style T16 fill:#58a6ff
    NONE[Aucun callee]
    T16 -.-> NONE
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
| Lignes de logique | 49 | Programme compact |
| Expressions | 20 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 49) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (2 taches: 0 ecran, 2 traitements)

- **Strategie** : 2 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| pv_budget | Table WRITE (Database) | 1x | Schema + repository |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 10:57*
