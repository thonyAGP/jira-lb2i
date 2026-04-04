# REQ IDE 60 - Set Listing Number

> **Analyse**: Phases 1-4 2026-02-03 20:32 -> 20:33 (16s) | Assemblage 20:33
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | REQ |
| IDE Position | 60 |
| Nom Programme | Set Listing Number |
| Fichier source | `Prg_60.xml` |
| Dossier IDE | Printer |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Set Listing Number** assure la gestion complete de ce processus, accessible depuis [Menu requests (IDE 21)](REQ-IDE-21.md), [    Print Request form new (IDE 24)](REQ-IDE-24.md), [Request Center (IDE 25)](REQ-IDE-25.md), [My Requests (IDE 26)](REQ-IDE-26.md), [Print message (IDE 55)](REQ-IDE-55.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>60 - Set Listing Number

**Role** : Traitement : Set Listing Number.
**Variables liees** : A (Param Listing number)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Menu requests (IDE 21)](REQ-IDE-21.md), [    Print Request form new (IDE 24)](REQ-IDE-24.md), [Request Center (IDE 25)](REQ-IDE-25.md), [My Requests (IDE 26)](REQ-IDE-26.md), [Print message (IDE 55)](REQ-IDE-55.md)
- **Appelle**: 0 programmes | **Tables**: 0 (W:0 R:0 L:0) | **Taches**: 1 | **Expressions**: 1

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **60.1** | [**Set Listing Number** (60)](#t1) | MDI | - | Traitement |

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

**1 / 1 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| OTHER | 1 | 0 |

### 12.2 Expressions cles par type

#### OTHER (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 1 | `SetParam ('CURRENTLISTINGNUM',Param Listing number [A])` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Menu requests (IDE 21)](REQ-IDE-21.md) -> **Set Listing Number (IDE 60)**

Main -> ... -> [    Print Request form new (IDE 24)](REQ-IDE-24.md) -> **Set Listing Number (IDE 60)**

Main -> ... -> [Request Center (IDE 25)](REQ-IDE-25.md) -> **Set Listing Number (IDE 60)**

Main -> ... -> [My Requests (IDE 26)](REQ-IDE-26.md) -> **Set Listing Number (IDE 60)**

Main -> ... -> [Print message (IDE 55)](REQ-IDE-55.md) -> **Set Listing Number (IDE 60)**

```mermaid
graph LR
    T60[60 Set Listing Number]
    style T60 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC23[23 Capture form]
    style CC23 fill:#f59e0b
    CC52[52 MAIN MENU]
    style CC52 fill:#f59e0b
    CC53[53 Message Center]
    style CC53 fill:#f59e0b
    CC54[54 Create Modify message]
    style CC54 fill:#f59e0b
    CC21[21 Menu requests]
    style CC21 fill:#3fb950
    CC25[25 Request Center]
    style CC25 fill:#3fb950
    CC24[24 Print Request form new]
    style CC24 fill:#3fb950
    CC55[55 Print message]
    style CC55 fill:#3fb950
    CC26[26 My Requests]
    style CC26 fill:#3fb950
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
    CC1 --> CC52
    CC1 --> CC23
    CC1 --> CC53
    CC1 --> CC54
    CC21 --> T60
    CC24 --> T60
    CC25 --> T60
    CC26 --> T60
    CC55 --> T60
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [21](REQ-IDE-21.md) | Menu requests | 1 |
| [24](REQ-IDE-24.md) |     Print Request form new | 1 |
| [25](REQ-IDE-25.md) | Request Center | 1 |
| [26](REQ-IDE-26.md) | My Requests | 1 |
| [55](REQ-IDE-55.md) | Print message | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T60[60 Set Listing Number]
    style T60 fill:#58a6ff
    NONE[Aucun callee]
    T60 -.-> NONE
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
| Expressions | 1 | Peu de logique |
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
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 20:33*
