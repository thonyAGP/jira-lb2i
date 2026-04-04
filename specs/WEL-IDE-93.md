# WEL IDE 93 - Suppression Carac interdit

> **Analyse**: Phases 1-4 2026-02-03 21:42 -> 21:42 (18s) | Assemblage 21:42
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | WEL |
| IDE Position | 93 |
| Nom Programme | Suppression Carac interdit |
| Fichier source | `Prg_93.xml` |
| Dossier IDE | Utilitaires |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Suppression Carac interdit** assure la gestion complete de ce processus, accessible depuis [  Alimentation Combos VILLAGE (IDE 38)](WEL-IDE-38.md), [  Alimentation Combos PARIS 1 (IDE 39)](WEL-IDE-39.md), [  Alimentation Combos PARIS 2 (IDE 40)](WEL-IDE-40.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>93 - Suppression Carac interdit

**Role** : Traitement : Suppression Carac interdit.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [  Alimentation Combos VILLAGE (IDE 38)](WEL-IDE-38.md), [  Alimentation Combos PARIS 1 (IDE 39)](WEL-IDE-39.md), [  Alimentation Combos PARIS 2 (IDE 40)](WEL-IDE-40.md)
- **Appelle**: 0 programmes | **Tables**: 0 (W:0 R:0 L:0) | **Taches**: 1 | **Expressions**: 3

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **93.1** | [**Suppression Carac interdit** (93)](#t1) | MDI | - | Traitement |

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

**3 / 3 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONDITION | 2 | 0 |
| CONCATENATION | 1 | 0 |

### 12.2 Expressions cles par type

#### CONDITION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 2 | `InStr (< v. combo [A],'-')<>0` | - |
| CONDITION | 1 | `InStr (< v. combo [A],'-')=0` | - |

#### CONCATENATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 3 | `Left (< v. combo [A],InStr (< v. combo [A],'-')-1)&'_'&Right (< v. combo [A],Len (< v. combo [A])-InStr (< v. combo [A],'-'))` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [  Alimentation Combos VILLAGE (IDE 38)](WEL-IDE-38.md) -> **Suppression Carac interdit (IDE 93)**

Main -> ... -> [  Alimentation Combos PARIS 1 (IDE 39)](WEL-IDE-39.md) -> **Suppression Carac interdit (IDE 93)**

Main -> ... -> [  Alimentation Combos PARIS 2 (IDE 40)](WEL-IDE-40.md) -> **Suppression Carac interdit (IDE 93)**

```mermaid
graph LR
    T93[93 Suppression Carac i...]
    style T93 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC34[34 Lancement]
    style CC34 fill:#f59e0b
    CC38[38 Alimentation Combos...]
    style CC38 fill:#3fb950
    CC39[39 Alimentation Combos...]
    style CC39 fill:#3fb950
    CC40[40 Alimentation Combos...]
    style CC40 fill:#3fb950
    CC34 --> CC38
    CC34 --> CC39
    CC34 --> CC40
    CC1 --> CC34
    CC38 --> T93
    CC39 --> T93
    CC40 --> T93
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [38](WEL-IDE-38.md) |   Alimentation Combos VILLAGE | 1 |
| [39](WEL-IDE-39.md) |   Alimentation Combos PARIS 1 | 1 |
| [40](WEL-IDE-40.md) |   Alimentation Combos PARIS 2 | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T93[93 Suppression Carac i...]
    style T93 fill:#58a6ff
    NONE[Aucun callee]
    T93 -.-> NONE
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
| Lignes de logique | 3 | Programme compact |
| Expressions | 3 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 3) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 0 ecran, 1 traitement)

- **Strategie** : 1 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 21:42*
