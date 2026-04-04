# VIL IDE 111 - Prep. list. comptable avec GP

> **Analyse**: Phases 1-4 2026-02-03 09:27 -> 09:27 (20s) | Assemblage 09:27
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | VIL |
| IDE Position | 111 |
| Nom Programme | Prep. list. comptable avec GP |
| Fichier source | `Prg_111.xml` |
| Domaine metier | General |
| Taches | 6 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Prep. list. comptable avec GP** assure la gestion complete de ce processus, accessible depuis [    Listings cloture HTML (IDE 29)](VIL-IDE-29.md), [Tableau Excel - Cloture Manuel (IDE 113)](VIL-IDE-113.md), [Tableau Excel - Cloture Auto (IDE 114)](VIL-IDE-114.md), [Lancement (IDE 193)](VIL-IDE-193.md).

Le flux de traitement s'organise en **2 blocs fonctionnels** :

- **Traitement** (5 taches) : traitements metier divers
- **Calcul** (1 tache) : calculs de montants, stocks ou compteurs

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Calcul (1 tache)

- **111** - Prep. list. comptable avec GP

#### Phase 2 : Traitement (5 taches)

- **111.1** - Cpte versement retrait
- **111.2** - Load ecritures
- **111.2.1** - Load ecritures
- **111.3** - Load ecritures
- **111.3.1** - Load ecritures

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Calcul (1 tache)

Calculs metier : montants, stocks, compteurs.

---

#### <a id="t1"></a>111 - Prep. list. comptable avec GP

**Role** : Traitement : Prep. list. comptable avec GP.
**Variables liees** : B (Param date comptable), C (Param Comptable C / Vente V)


### 3.2 Traitement (5 taches)

Traitements internes.

---

#### <a id="t2"></a>111.1 - Cpte versement retrait

**Role** : Traitement : Cpte versement retrait.
**Variables liees** : D (Cpte versement retrait NON CASH), E (Cpte versement retrait CASH)

---

#### <a id="t3"></a>111.2 - Load ecritures

**Role** : Traitement : Load ecritures.

---

#### <a id="t6"></a>111.2.1 - Load ecritures

**Role** : Traitement : Load ecritures.

---

#### <a id="t9"></a>111.3 - Load ecritures

**Role** : Traitement : Load ecritures.

---

#### <a id="t10"></a>111.3.1 - Load ecritures

**Role** : Traitement : Load ecritures.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [    Listings cloture HTML (IDE 29)](VIL-IDE-29.md), [Tableau Excel - Cloture Manuel (IDE 113)](VIL-IDE-113.md), [Tableau Excel - Cloture Auto (IDE 114)](VIL-IDE-114.md), [Lancement (IDE 193)](VIL-IDE-193.md)
- **Appelle**: 0 programmes | **Tables**: 6 (W:0 R:5 L:1) | **Taches**: 6 | **Expressions**: 5

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (6 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **111.1** | [**Prep. list. comptable avec GP** (111)](#t1) | MDI | - | Calcul |
| **111.2** | [**Cpte versement retrait** (111.1)](#t2) | MDI | - | Traitement |
| 111.2.1 | [Load ecritures (111.2)](#t3) | MDI | - | |
| 111.2.2 | [Load ecritures (111.2.1)](#t6) | MDI | - | |
| 111.2.3 | [Load ecritures (111.3)](#t9) | MDI | - | |
| 111.2.4 | [Load ecritures (111.3.1)](#t10) | MDI | - | |

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

### Tables utilisees (6)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 40 | comptable________cte |  | DB | R |   |   | 1 |
| 65 | comptes_recette__cre | Comptes GM (generaux) | DB | R |   |   | 2 |
| 263 | vente | Donnees de ventes | DB | R |   |   | 1 |
| 553 | import_logement__iml |  | DB |   |   | L | 4 |
| 697 | droits_applications | Droits operateur | DB | R |   |   | 1 |
| 925 | vente_complement_commun | Donnees de ventes | DB | R |   |   | 1 |

### Colonnes par table (4 / 5 tables avec colonnes identifiees)

<details>
<summary>Table 40 - comptable________cte (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| B | Param date comptable | R | Date |
| C | Param Comptable C / Vente V | R | Alpha |

</details>

<details>
<summary>Table 65 - comptes_recette__cre (R) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | v.compte debit | R | Numeric |
| B | v.compte credit | R | Numeric |

</details>

<details>
<summary>Table 263 - vente (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| C | Param Comptable C / Vente V | R | Alpha |

</details>

<details>
<summary>Table 697 - droits_applications (R) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 925 - vente_complement_commun (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | Param societe | R | Alpha |
| B | Param date comptable | R | Date |
| C | Param Comptable C / Vente V | R | Alpha |
| D | Cpte versement retrait NON CASH | R | Numeric |
| E | Cpte versement retrait CASH | R | Numeric |

</details>

## 11. VARIABLES

### 11.1 Autres (5)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | Param societe | Alpha | - |
| B | Param date comptable | Date | - |
| C | Param Comptable C / Vente V | Alpha | - |
| D | Cpte versement retrait NON CASH | Numeric | - |
| E | Cpte versement retrait CASH | Numeric | - |

## 12. EXPRESSIONS

**5 / 5 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONSTANTE | 2 | 0 |
| OTHER | 1 | 0 |
| CONDITION | 2 | 0 |

### 12.2 Expressions cles par type

#### CONSTANTE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 3 | `7` | - |
| CONSTANTE | 2 | `4` | - |

#### OTHER (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 1 | `DbDel ('{553,2}'DSOURCE,'')` | - |

#### CONDITION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 5 | `[Q]='V'` | - |
| CONDITION | 4 | `[Q]='C'` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [    Listings cloture HTML (IDE 29)](VIL-IDE-29.md) -> **Prep. list. comptable avec GP (IDE 111)**

Main -> ... -> [Tableau Excel - Cloture Manuel (IDE 113)](VIL-IDE-113.md) -> **Prep. list. comptable avec GP (IDE 111)**

Main -> ... -> [Tableau Excel - Cloture Auto (IDE 114)](VIL-IDE-114.md) -> **Prep. list. comptable avec GP (IDE 111)**

Main -> ... -> [Lancement (IDE 193)](VIL-IDE-193.md) -> **Prep. list. comptable avec GP (IDE 111)**

```mermaid
graph LR
    T111[111 Prep. list. compta...]
    style T111 fill:#58a6ff
    CC149[149 Start]
    style CC149 fill:#8b5cf6
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC78[78 Lance correspittivi]
    style CC78 fill:#8b5cf6
    CC9[9 Pilotage avant sessions]
    style CC9 fill:#f59e0b
    CC148[148 CV Menu caisse vil...]
    style CC148 fill:#f59e0b
    CC36[36 CV Menu Clôture de ...]
    style CC36 fill:#f59e0b
    CC10[10 Pilotage après sess...]
    style CC10 fill:#f59e0b
    CC113[113 Tableau Excel - Cl...]
    style CC113 fill:#3fb950
    CC29[29 Listings cloture HTML]
    style CC29 fill:#3fb950
    CC193[193 Lancement]
    style CC193 fill:#3fb950
    CC114[114 Tableau Excel - Cl...]
    style CC114 fill:#3fb950
    CC10 --> CC29
    CC36 --> CC29
    CC10 --> CC113
    CC36 --> CC113
    CC10 --> CC114
    CC36 --> CC114
    CC10 --> CC193
    CC36 --> CC193
    CC9 --> CC10
    CC148 --> CC10
    CC9 --> CC36
    CC148 --> CC36
    CC149 --> CC9
    CC1 --> CC9
    CC78 --> CC9
    CC149 --> CC148
    CC1 --> CC148
    CC78 --> CC148
    CC29 --> T111
    CC113 --> T111
    CC114 --> T111
    CC193 --> T111
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [29](VIL-IDE-29.md) |     Listings cloture HTML | 2 |
| [113](VIL-IDE-113.md) | Tableau Excel - Cloture Manuel | 1 |
| [114](VIL-IDE-114.md) | Tableau Excel - Cloture Auto | 1 |
| [193](VIL-IDE-193.md) | Lancement | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T111[111 Prep. list. compta...]
    style T111 fill:#58a6ff
    NONE[Aucun callee]
    T111 -.-> NONE
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
| Lignes de logique | 325 | Taille moyenne |
| Expressions | 5 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 325) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Calcul (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Services de calcul purs (Domain Services).
- Migrer la logique de calcul (stock, compteurs, montants)

#### Traitement (5 taches: 0 ecran, 5 traitements)

- **Strategie** : 5 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 09:27*
