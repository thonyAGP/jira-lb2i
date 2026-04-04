# PBG IDE 85 - Delete GMR adh=0

> **Analyse**: Phases 1-4 2026-02-03 09:14 -> 09:15 (19s) | Assemblage 09:15
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBG |
| IDE Position | 85 |
| Nom Programme | Delete GMR adh=0 |
| Fichier source | `Prg_85.xml` |
| Domaine metier | General |
| Taches | 3 (0 ecrans visibles) |
| Tables modifiees | 3 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Delete GMR adh=0** assure la gestion complete de ce processus, accessible depuis [Creation filiation (IDE 86)](PBG-IDE-86.md), [Creation clients Identite (IDE 87)](PBG-IDE-87.md), [Creation clients Identite SAV (IDE 379)](PBG-IDE-379.md), [Creation clients Identite P185 (IDE 382)](PBG-IDE-382.md), [Creation clients Identite PROD (IDE 383)](PBG-IDE-383.md), [Creation clients Identite en c (IDE 384)](PBG-IDE-384.md), [Creation clients Identite SAV* (IDE 386)](PBG-IDE-386.md), [Creation clients Identite_sav (IDE 387)](PBG-IDE-387.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (3 taches) : traitements metier divers

**Donnees modifiees** : 3 tables en ecriture (gm-recherche_____gmr, gm-complet_______gmc, client_gm).

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (3 taches)

Traitements internes.

---

#### <a id="t1"></a>85 - Delete GMR adh=0 [[ECRAN]](#ecran-t1)

**Role** : Traitement : Delete GMR adh=0.
**Ecran** : 235 x 47 DLU (MDI) | [Voir mockup](#ecran-t1)

---

#### <a id="t2"></a>85.1 - GM 14

**Role** : Traitement : GM 14.

---

#### <a id="t3"></a>85.2 - GM 9

**Role** : Traitement : GM 9.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Creation filiation (IDE 86)](PBG-IDE-86.md), [Creation clients Identite (IDE 87)](PBG-IDE-87.md), [Creation clients Identite SAV (IDE 379)](PBG-IDE-379.md), [Creation clients Identite P185 (IDE 382)](PBG-IDE-382.md), [Creation clients Identite PROD (IDE 383)](PBG-IDE-383.md), [Creation clients Identite en c (IDE 384)](PBG-IDE-384.md), [Creation clients Identite SAV* (IDE 386)](PBG-IDE-386.md), [Creation clients Identite_sav (IDE 387)](PBG-IDE-387.md)
- **Appelle**: 0 programmes | **Tables**: 3 (W:3 R:0 L:0) | **Taches**: 3 | **Expressions**: 1

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (3 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **85.1** | [**Delete GMR adh=0** (85)](#t1) [mockup](#ecran-t1) | MDI | 235x47 | Traitement |
| 85.1.1 | [GM 14 (85.1)](#t2) | MDI | - | |
| 85.1.2 | [GM 9 (85.2)](#t3) | MDI | - | |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Traitement principal]
    UPDATE[MAJ 3 tables]
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

### Tables utilisees (3)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 30 | gm-recherche_____gmr | Index de recherche | DB |   | **W** |   | 1 |
| 31 | gm-complet_______gmc |  | DB |   | **W** |   | 1 |
| 36 | client_gm |  | DB |   | **W** |   | 1 |

### Colonnes par table (0 / 3 tables avec colonnes identifiees)

<details>
<summary>Table 30 - gm-recherche_____gmr (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 31 - gm-complet_______gmc (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 36 - client_gm (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

*(Programme sans variables locales mappees)*

## 12. EXPRESSIONS

**1 / 1 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONSTANTE | 1 | 0 |

### 12.2 Expressions cles par type

#### CONSTANTE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 1 | `0` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Creation filiation (IDE 86)](PBG-IDE-86.md) -> **Delete GMR adh=0 (IDE 85)**

Main -> ... -> [Creation clients Identite (IDE 87)](PBG-IDE-87.md) -> **Delete GMR adh=0 (IDE 85)**

Main -> ... -> [Creation clients Identite SAV (IDE 379)](PBG-IDE-379.md) -> **Delete GMR adh=0 (IDE 85)**

Main -> ... -> [Creation clients Identite P185 (IDE 382)](PBG-IDE-382.md) -> **Delete GMR adh=0 (IDE 85)**

Main -> ... -> [Creation clients Identite PROD (IDE 383)](PBG-IDE-383.md) -> **Delete GMR adh=0 (IDE 85)**

Main -> ... -> [Creation clients Identite en c (IDE 384)](PBG-IDE-384.md) -> **Delete GMR adh=0 (IDE 85)**

Main -> ... -> [Creation clients Identite SAV* (IDE 386)](PBG-IDE-386.md) -> **Delete GMR adh=0 (IDE 85)**

Main -> ... -> [Creation clients Identite_sav (IDE 387)](PBG-IDE-387.md) -> **Delete GMR adh=0 (IDE 85)**

```mermaid
graph LR
    T85[85 Delete GMR adh=0]
    style T85 fill:#58a6ff
    CC94[94 Module Sejours Call...]
    style CC94 fill:#8b5cf6
    CC91[91 Modules clients Ide...]
    style CC91 fill:#8b5cf6
    CC391[391 Module Sejours Sub...]
    style CC391 fill:#8b5cf6
    CC86[86 Creation filiation]
    style CC86 fill:#3fb950
    CC383[383 Creation clients I...]
    style CC383 fill:#3fb950
    CC87[87 Creation clients Id...]
    style CC87 fill:#3fb950
    CC379[379 Creation clients I...]
    style CC379 fill:#3fb950
    CC382[382 Creation clients I...]
    style CC382 fill:#3fb950
    CC91 --> CC86
    CC94 --> CC86
    CC391 --> CC86
    CC91 --> CC87
    CC94 --> CC87
    CC391 --> CC87
    CC91 --> CC379
    CC94 --> CC379
    CC391 --> CC379
    CC91 --> CC382
    CC94 --> CC382
    CC391 --> CC382
    CC91 --> CC383
    CC94 --> CC383
    CC391 --> CC383
    CC86 --> T85
    CC87 --> T85
    CC379 --> T85
    CC382 --> T85
    CC383 --> T85
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [86](PBG-IDE-86.md) | Creation filiation | 2 |
| [87](PBG-IDE-87.md) | Creation clients Identite | 2 |
| [379](PBG-IDE-379.md) | Creation clients Identite SAV | 2 |
| [382](PBG-IDE-382.md) | Creation clients Identite P185 | 2 |
| [383](PBG-IDE-383.md) | Creation clients Identite PROD | 2 |
| [384](PBG-IDE-384.md) | Creation clients Identite en c | 2 |
| [386](PBG-IDE-386.md) | Creation clients Identite SAV* | 2 |
| [387](PBG-IDE-387.md) | Creation clients Identite_sav | 2 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T85[85 Delete GMR adh=0]
    style T85 fill:#58a6ff
    NONE[Aucun callee]
    T85 -.-> NONE
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
| Lignes de logique | 30 | Programme compact |
| Expressions | 1 | Peu de logique |
| Tables WRITE | 3 | Impact modere |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 30) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (3 taches: 1 ecran, 2 traitements)

- **Strategie** : Orchestrateur avec 1 ecrans (Razor/React) et 2 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| gm-recherche_____gmr | Table WRITE (Database) | 1x | Schema + repository |
| gm-complet_______gmc | Table WRITE (Database) | 1x | Schema + repository |
| client_gm | Table WRITE (Database) | 1x | Schema + repository |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 09:15*
