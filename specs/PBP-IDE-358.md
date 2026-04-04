# PBP IDE 358 - Màj stat quotidienne PMS-763

> **Analyse**: Phases 1-4 2026-02-03 16:37 -> 16:38 (17s) | Assemblage 16:38
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBP |
| IDE Position | 358 |
| Nom Programme | Màj stat quotidienne PMS-763 |
| Fichier source | `Prg_358.xml` |
| Dossier IDE | Statistiques |
| Taches | 5 (0 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 0 |
| :warning: Statut | **ORPHELIN_POTENTIEL** |

## 2. DESCRIPTION FONCTIONNELLE

**Màj stat quotidienne PMS-763** assure la gestion complete de ce processus.

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (5 taches) : traitements metier divers

**Donnees modifiees** : 1 tables en ecriture (##_pv_customer_dat).

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (5 taches)

- **358** - Mise à jour stat quotidienne-N
- **358.1** - Realise
- **358.1.1** - Mise a jour stat
- **358.2** - suppression statistique
- **358.3** - Maj Lieu de sejour Statistique

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| ##_pv_customer_dat | **W**/L (2 usages) |  |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (5 taches)

Traitements internes.

---

#### <a id="t1"></a>358 - Mise à jour stat quotidienne-N

**Role** : Traitement : Mise à jour stat quotidienne-N.

<details>
<summary>4 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [358.1](#t45) | Realise | Traitement |
| [358.1.1](#t58) | Mise a jour stat | Traitement |
| [358.2](#t61) | suppression statistique | Traitement |
| [358.3](#t62) | Maj Lieu de sejour Statistique | Traitement |

</details>
**Variables liees** : B (P.Nb lieu sejour)

---

#### <a id="t45"></a>358.1 - Realise

**Role** : Traitement : Realise.

---

#### <a id="t58"></a>358.1.1 - Mise a jour stat

**Role** : Traitement : Mise a jour stat.
**Variables liees** : B (P.Nb lieu sejour)

---

#### <a id="t61"></a>358.2 - suppression statistique

**Role** : Traitement : suppression statistique.

---

#### <a id="t62"></a>358.3 - Maj Lieu de sejour Statistique

**Role** : Traitement : Maj Lieu de sejour Statistique.
**Variables liees** : B (P.Nb lieu sejour)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: (aucun)
- **Appelle**: 0 programmes | **Tables**: 9 (W:1 R:3 L:7) | **Taches**: 5 | **Expressions**: 3

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (5 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **358.1** | [**Mise à jour stat quotidienne-N** (358)](#t1) | - | - | Traitement |
| 358.1.1 | [Realise (358.1)](#t45) | MDI | - | |
| 358.1.2 | [Mise a jour stat (358.1.1)](#t58) | - | - | |
| 358.1.3 | [suppression statistique (358.2)](#t61) | - | - | |
| 358.1.4 | [Maj Lieu de sejour Statistique (358.3)](#t62) | - | - | |

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

### Tables utilisees (9)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 30 | gm-recherche_____gmr | Index de recherche | DB | R |   |   | 1 |
| 31 | gm-complet_______gmc |  | DB |   |   | L | 1 |
| 34 | hebergement______heb | Hebergement (chambres) | DB | R |   | L | 2 |
| 36 | client_gm |  | DB |   |   | L | 1 |
| 81 | societe__________soc |  | DB |   |   | L | 2 |
| 120 | tables_qualites__qua |  | DB | R |   |   | 1 |
| 131 | fichier_validation |  | DB |   |   | L | 1 |
| 325 | gm_handicap |  | DB |   |   | L | 1 |
| 837 | ##_pv_customer_dat |  | DB |   | **W** | L | 2 |

### Colonnes par table (4 / 4 tables avec colonnes identifiees)

<details>
<summary>Table 30 - gm-recherche_____gmr (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | V.Existe handicap ? | R | Logical |
| B | V.Jour | R | Date |

</details>

<details>
<summary>Table 34 - hebergement______heb (R/L) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | v lien hebergement | R | Logical |

</details>

<details>
<summary>Table 120 - tables_qualites__qua (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P.Date | R | Date |
| B | P.Nb lieu sejour | R | Numeric |

</details>

<details>
<summary>Table 837 - ##_pv_customer_dat (**W**/L) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (2)

Variables recues en parametre.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P.Date | Date | - |
| B | P.Nb lieu sejour | Numeric | - |

## 12. EXPRESSIONS

**3 / 3 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| OTHER | 1 | 0 |
| CAST_LOGIQUE | 1 | 0 |
| CONDITION | 1 | 0 |

### 12.2 Expressions cles par type

#### OTHER (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 1 | `GetParam('SOCIETE')` | - |

#### CAST_LOGIQUE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 2 | `'TRUE'LOG` | - |

#### CONDITION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 3 | `[I]>1` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

**Chemin**: (pas de callers directs)

```mermaid
graph LR
    T358[358 Màj stat quotidien...]
    style T358 fill:#58a6ff
    NONE[Aucun caller]
    NONE -.-> T358
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| - | (aucun) | - |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T358[358 Màj stat quotidien...]
    style T358 fill:#58a6ff
    NONE[Aucun callee]
    T358 -.-> NONE
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
| Lignes de logique | 218 | Taille moyenne |
| Expressions | 3 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 218) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (5 taches: 0 ecran, 5 traitements)

- **Strategie** : 5 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| ##_pv_customer_dat | Table WRITE (Database) | 1x | Schema + repository |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 16:38*
