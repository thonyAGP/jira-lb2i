# PUG IDE 20 - Vidage table SQL

> **Analyse**: Phases 1-4 2026-02-03 18:33 -> 18:33 (18s) | Assemblage 18:33
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PUG |
| IDE Position | 20 |
| Nom Programme | Vidage table SQL |
| Fichier source | `Prg_20.xml` |
| Dossier IDE | Utilitaires |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Vidage table SQL** assure la gestion complete de ce processus, accessible depuis [   Purge Point de vente (IDE 14)](PUG-IDE-14.md), [Purge Batch (IDE 18)](PUG-IDE-18.md), [Purge Batch Save (IDE 25)](PUG-IDE-25.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>20 - Vidage table SQL

**Role** : Traitement : Vidage table SQL.
**Variables liees** : A (P.Nom table)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [   Purge Point de vente (IDE 14)](PUG-IDE-14.md), [Purge Batch (IDE 18)](PUG-IDE-18.md), [Purge Batch Save (IDE 25)](PUG-IDE-25.md)
- **Appelle**: 0 programmes | **Tables**: 0 (W:0 R:0 L:0) | **Taches**: 1 | **Expressions**: 0

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **20.1** | [**Vidage table SQL** (20)](#t1) | - | - | Traitement |

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

### Tables utilisees (0)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|

### Colonnes par table (0 / 0 tables avec colonnes identifiees)

## 11. VARIABLES

*(Programme sans variables locales mappees)*

## 12. EXPRESSIONS

**0 / 0 expressions decodees (0%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|

### 12.2 Expressions cles par type

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [   Purge Point de vente (IDE 14)](PUG-IDE-14.md) -> **Vidage table SQL (IDE 20)**

Main -> ... -> [Purge Batch (IDE 18)](PUG-IDE-18.md) -> **Vidage table SQL (IDE 20)**

Main -> ... -> [Purge Batch Save (IDE 25)](PUG-IDE-25.md) -> **Vidage table SQL (IDE 20)**

```mermaid
graph LR
    T20[20 Vidage table SQL]
    style T20 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC17[17 Lancement Purge]
    style CC17 fill:#f59e0b
    CC19[19 test purge]
    style CC19 fill:#f59e0b
    CC22[22 Lancement UNITAIRE ...]
    style CC22 fill:#f59e0b
    CC24[24 Purge - NU -]
    style CC24 fill:#f59e0b
    CC14[14 Purge Point de vente]
    style CC14 fill:#3fb950
    CC18[18 Purge Batch]
    style CC18 fill:#3fb950
    CC25[25 Purge Batch Save]
    style CC25 fill:#3fb950
    CC24 --> CC14
    CC17 --> CC14
    CC19 --> CC14
    CC22 --> CC14
    CC24 --> CC18
    CC17 --> CC18
    CC19 --> CC18
    CC22 --> CC18
    CC24 --> CC25
    CC17 --> CC25
    CC19 --> CC25
    CC22 --> CC25
    CC1 --> CC24
    CC1 --> CC17
    CC1 --> CC19
    CC1 --> CC22
    CC14 --> T20
    CC18 --> T20
    CC25 --> T20
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [14](PUG-IDE-14.md) |    Purge Point de vente | 2 |
| [18](PUG-IDE-18.md) | Purge Batch | 2 |
| [25](PUG-IDE-25.md) | Purge Batch Save | 2 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T20[20 Vidage table SQL]
    style T20 fill:#58a6ff
    NONE[Aucun callee]
    T20 -.-> NONE
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
| Lignes de logique | 2 | Programme compact |
| Expressions | 0 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 2) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 0 ecran, 1 traitement)

- **Strategie** : 1 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 18:33*
