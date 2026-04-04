# REQ IDE 57 - Set Village Address

> **Analyse**: Phases 1-4 2026-02-03 20:31 -> 20:32 (14s) | Assemblage 20:32
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | REQ |
| IDE Position | 57 |
| Nom Programme | Set Village Address |
| Fichier source | `Prg_57.xml` |
| Dossier IDE | Printer |
| Taches | 2 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Set Village Address** assure la gestion complete de ce processus, accessible depuis [Get Printer (IDE 58)](REQ-IDE-58.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (2 taches) : traitements metier divers

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (2 taches)

Traitements internes.

---

#### <a id="t1"></a>57 - Set Village Address

**Role** : Traitement : Set Village Address.

---

#### <a id="t2"></a>57.1 - Load Buffer

**Role** : Traitement : Load Buffer.
**Variables liees** : A (Buffer)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Get Printer (IDE 58)](REQ-IDE-58.md)
- **Appelle**: 0 programmes | **Tables**: 1 (W:0 R:1 L:0) | **Taches**: 2 | **Expressions**: 10

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (2 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **57.1** | [**Set Village Address** (57)](#t1) | MDI | - | Traitement |
| 57.1.1 | [Load Buffer (57.1)](#t2) | MDI | - | |

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
| 372 | pv_budget |  | DB | R |   |   | 1 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 372 - pv_budget (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | Buffer | R | Alpha |
| B | CounterTel | R | Numeric |
| C | CounterFax | R | Numeric |

</details>

## 11. VARIABLES

### 11.1 Autres (3)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | Buffer | Alpha | - |
| B | CounterTel | Numeric | - |
| C | CounterFax | Numeric | - |

## 12. EXPRESSIONS

**10 / 10 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| OTHER | 10 | 0 |

### 12.2 Expressions cles par type

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

Main -> ... -> [Get Printer (IDE 58)](REQ-IDE-58.md) -> **Set Village Address (IDE 57)**

```mermaid
graph LR
    T57[57 Set Village Address]
    style T57 fill:#58a6ff
    CC23[23 Capture form]
    style CC23 fill:#8b5cf6
    CC52[52 MAIN MENU]
    style CC52 fill:#8b5cf6
    CC54[54 Create Modify message]
    style CC54 fill:#8b5cf6
    CC53[53 Message Center]
    style CC53 fill:#8b5cf6
    CC55[55 Print message]
    style CC55 fill:#f59e0b
    CC24[24 Print Request form new]
    style CC24 fill:#f59e0b
    CC21[21 Menu requests]
    style CC21 fill:#f59e0b
    CC26[26 My Requests]
    style CC26 fill:#f59e0b
    CC25[25 Request Center]
    style CC25 fill:#f59e0b
    CC58[58 Get Printer]
    style CC58 fill:#3fb950
    CC21 --> CC58
    CC24 --> CC58
    CC25 --> CC58
    CC26 --> CC58
    CC55 --> CC58
    CC52 --> CC21
    CC23 --> CC21
    CC53 --> CC21
    CC54 --> CC21
    CC52 --> CC24
    CC23 --> CC24
    CC53 --> CC24
    CC54 --> CC24
    CC52 --> CC25
    CC23 --> CC25
    CC53 --> CC25
    CC54 --> CC25
    CC52 --> CC26
    CC23 --> CC26
    CC53 --> CC26
    CC54 --> CC26
    CC52 --> CC55
    CC23 --> CC55
    CC53 --> CC55
    CC54 --> CC55
    CC58 --> T57
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [58](REQ-IDE-58.md) | Get Printer | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T57[57 Set Village Address]
    style T57 fill:#58a6ff
    NONE[Aucun callee]
    T57 -.-> NONE
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
| Lignes de logique | 46 | Programme compact |
| Expressions | 10 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 46) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (2 taches: 0 ecran, 2 traitements)

- **Strategie** : 2 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 20:32*
