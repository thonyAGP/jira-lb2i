# PBP IDE 44 - Remise à zero totaux

> **Analyse**: Phases 1-4 2026-02-03 08:53 -> 08:54 (21s) | Assemblage 08:54
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBP |
| IDE Position | 44 |
| Nom Programme | Remise à zero totaux |
| Fichier source | `Prg_44.xml` |
| Domaine metier | Change |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Remise à zero totaux** assure la gestion complete de ce processus, accessible depuis [Demande Edition GM (IDE 18)](PBP-IDE-18.md), [Demande Edition GO (IDE 28)](PBP-IDE-28.md), [Edit autorite P1 (IDE 25)](PBP-IDE-25.md), [Edit autorite C1 (IDE 38)](PBP-IDE-38.md), [Edit autorite C1 trie national (IDE 39)](PBP-IDE-39.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

**Donnees modifiees** : 1 tables en ecriture (tempo_hebergement).

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>44 - Remise à zero totaux

**Role** : Calcul : Remise à zero totaux.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Demande Edition GM (IDE 18)](PBP-IDE-18.md), [Demande Edition GO (IDE 28)](PBP-IDE-28.md), [Edit autorite P1 (IDE 25)](PBP-IDE-25.md), [Edit autorite C1 (IDE 38)](PBP-IDE-38.md), [Edit autorite C1 trie national (IDE 39)](PBP-IDE-39.md)
- **Appelle**: 0 programmes | **Tables**: 1 (W:1 R:0 L:0) | **Taches**: 1 | **Expressions**: 1

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **44.1** | [**Remise à zero totaux** (44)](#t1) | MDI | - | Traitement |

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
| 599 | tempo_hebergement | Hebergement (chambres) | DB |   | **W** |   | 1 |

### Colonnes par table (0 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 599 - tempo_hebergement (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

*(Programme sans variables locales mappees)*

## 12. EXPRESSIONS

**1 / 1 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| REFERENCE_VG | 1 | 0 |

### 12.2 Expressions cles par type

#### REFERENCE_VG (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 1 | `VG1` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Demande Edition GM (IDE 18)](PBP-IDE-18.md) -> **Remise à zero totaux (IDE 44)**

Main -> ... -> [Demande Edition GO (IDE 28)](PBP-IDE-28.md) -> **Remise à zero totaux (IDE 44)**

Main -> ... -> [Edit autorite P1 (IDE 25)](PBP-IDE-25.md) -> **Remise à zero totaux (IDE 44)**

Main -> ... -> [Edit autorite C1 (IDE 38)](PBP-IDE-38.md) -> **Remise à zero totaux (IDE 44)**

Main -> ... -> [Edit autorite C1 trie national (IDE 39)](PBP-IDE-39.md) -> **Remise à zero totaux (IDE 44)**

```mermaid
graph LR
    T44[44 Remise à zero totaux]
    style T44 fill:#58a6ff
    CC19[19 Automate Edition GM]
    style CC19 fill:#8b5cf6
    CC29[29 Automate Edition GO]
    style CC29 fill:#8b5cf6
    CC30[30 Centralisation nbre...]
    style CC30 fill:#f59e0b
    CC20[20 Centralisation nbre...]
    style CC20 fill:#f59e0b
    CC18[18 Demande Edition GM]
    style CC18 fill:#3fb950
    CC28[28 Demande Edition GO]
    style CC28 fill:#3fb950
    CC25[25 Edit autorite P1]
    style CC25 fill:#3fb950
    CC39[39 Edit autorite C1 tr...]
    style CC39 fill:#3fb950
    CC38[38 Edit autorite C1]
    style CC38 fill:#3fb950
    CC20 --> CC18
    CC30 --> CC18
    CC20 --> CC25
    CC30 --> CC25
    CC20 --> CC28
    CC30 --> CC28
    CC20 --> CC38
    CC30 --> CC38
    CC20 --> CC39
    CC30 --> CC39
    CC19 --> CC20
    CC29 --> CC20
    CC19 --> CC30
    CC29 --> CC30
    CC18 --> T44
    CC25 --> T44
    CC28 --> T44
    CC38 --> T44
    CC39 --> T44
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [18](PBP-IDE-18.md) | Demande Edition GM | 4 |
| [28](PBP-IDE-28.md) | Demande Edition GO | 4 |
| [25](PBP-IDE-25.md) | Edit autorite P1 | 1 |
| [38](PBP-IDE-38.md) | Edit autorite C1 | 1 |
| [39](PBP-IDE-39.md) | Edit autorite C1 trie national | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T44[44 Remise à zero totaux]
    style T44 fill:#58a6ff
    NONE[Aucun callee]
    T44 -.-> NONE
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
| Expressions | 1 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
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
| tempo_hebergement | Table WRITE (Database) | 1x | Schema + repository |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 08:54*
