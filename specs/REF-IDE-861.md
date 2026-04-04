# REF IDE 861 - Set Open Bravo VGs

> **Analyse**: Phases 1-4 2026-02-03 14:47 -> 14:47 (13s) | Assemblage 14:47
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | REF |
| IDE Position | 861 |
| Nom Programme | Set Open Bravo VGs |
| Fichier source | `Prg_861.xml` |
| Dossier IDE | General |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Set Open Bravo VGs** assure la gestion complete de ce processus, accessible depuis [OpenBravo Params (IDE 862)](REF-IDE-862.md), [Main Program (IDE 1)](REF-IDE-1.md), [Get CashUp (IDE 864)](REF-IDE-864.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

**Donnees modifiees** : 1 tables en ecriture (pms_village).

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>861 - Set Open Bravo VGs

**Role** : Traitement : Set Open Bravo VGs.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [OpenBravo Params (IDE 862)](REF-IDE-862.md), [Main Program (IDE 1)](REF-IDE-1.md), [Get CashUp (IDE 864)](REF-IDE-864.md)
- **Appelle**: 0 programmes | **Tables**: 2 (W:1 R:0 L:1) | **Taches**: 1 | **Expressions**: 7

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **861.1** | [**Set Open Bravo VGs** (861)](#t1) | - | - | Traitement |

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

### Tables utilisees (2)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 368 | pms_village |  | DB |   | **W** |   | 1 |
| 919 | Table_919 |  | MEM |   |   | L | 1 |

### Colonnes par table (0 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 368 - pms_village (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

*(Programme sans variables locales mappees)*

## 12. EXPRESSIONS

**7 / 7 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| OTHER | 7 | 0 |

### 12.2 Expressions cles par type

#### OTHER (7 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 5 | `[F]` | - |
| OTHER | 6 | `[G]` | - |
| OTHER | 7 | `[H]` | - |
| OTHER | 4 | `[E]` | - |
| OTHER | 1 | `[A]` | - |
| ... | | *+2 autres* | |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [OpenBravo Params (IDE 862)](REF-IDE-862.md) -> **Set Open Bravo VGs (IDE 861)**

Main -> ... -> [Main Program (IDE 1)](REF-IDE-1.md) -> **Set Open Bravo VGs (IDE 861)**

Main -> ... -> [Get CashUp (IDE 864)](REF-IDE-864.md) -> **Set Open Bravo VGs (IDE 861)**

```mermaid
graph LR
    T861[861 Set Open Bravo VGs]
    style T861 fill:#58a6ff
    CC621[621 Cloture OB]
    style CC621 fill:#8b5cf6
    CC1[1 Main Program]
    style CC1 fill:#3fb950
    CC864[864 Get CashUp]
    style CC864 fill:#3fb950
    CC862[862 OpenBravo Params]
    style CC862 fill:#3fb950
    CC621 --> CC1
    CC621 --> CC862
    CC621 --> CC864
    CC1 --> T861
    CC862 --> T861
    CC864 --> T861
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [862](REF-IDE-862.md) | OpenBravo Params | 2 |
| [1](REF-IDE-1.md) | Main Program | 1 |
| [864](REF-IDE-864.md) | Get CashUp | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T861[861 Set Open Bravo VGs]
    style T861 fill:#58a6ff
    NONE[Aucun callee]
    T861 -.-> NONE
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
| Lignes de logique | 18 | Programme compact |
| Expressions | 7 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 18) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 0 ecran, 1 traitement)

- **Strategie** : 1 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| pms_village | Table WRITE (Database) | 1x | Schema + repository |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 14:47*
