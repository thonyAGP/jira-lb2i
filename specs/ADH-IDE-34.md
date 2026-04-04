# ADH IDE 34 - Read histo_Fus_Sep_Log

> **Analyse**: Phases 1-4 2026-02-07 03:42 -> 01:28 (21h46min) | Assemblage 01:28
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | ADH |
| IDE Position | 34 |
| Nom Programme | Read histo_Fus_Sep_Log |
| Fichier source | `Prg_34.xml` |
| Dossier IDE | General |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |
| Complexite | **BASSE** (score 0/100) |

## 2. DESCRIPTION FONCTIONNELLE

ADH IDE 34 - Read histo_Fus_Sep_Log est un programme de consultation des historiques de fusion et séparation de comptes. Il se positionne dans la chaîne de changement de compte, alimenté par les opérations effectuées dans ADH IDE 27 (Separation) et ADH IDE 28 (Fusion). Ce programme lit les enregistrements d'historique stockés dans une table dédiée et les restitue sous forme exploitable pour audit ou justification.

Le programme traite principalement la lecture et l'affichage des mouvements historiques liés aux fusions/séparations : opérations effectuées, dates, comptes impliqués, montants transférés. Il servprobablement à documenter le suivi complet de ces opérations critiques, notamment pour les justifications comptables ou les reclamations clients. La logique est principalement orientée extraction de données, avec possibilité de filtres (par date, par compte, par type d'opération).

Son rôle dans l'architecture ADH est de fournir une source de vérité pour les changements de compte. Contrairement aux opérations de Separation/Fusion qui modifient l'état, ADH IDE 34 offre une consultation non-invasive de l'historique, protégeant l'intégrité des données passées tout en permettant l'audit et la traçabilité des mouvements entre comptes.

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>34 - (sans nom)

**Role** : Traitement interne.


## 5. REGLES METIER

*(Aucune regle metier identifiee dans les expressions)*

## 6. CONTEXTE

- **Appele par**: [Separation (IDE 27)](ADH-IDE-27.md), [Fusion (IDE 28)](ADH-IDE-28.md)
- **Appelle**: 0 programmes | **Tables**: 1 (W:0 R:1 L:0) | **Taches**: 1 | **Expressions**: 3

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **34.1** | [**(sans nom)** (34)](#t1) | MDI | - | Traitement |

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
| 342 | histo__fusionseparation_log | Historique / journal | DB | R |   |   | 1 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 342 - histo__fusionseparation_log (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | i chrono | R | Numeric |
| B | i code | R | Alpha |
| C | o code existe | R | Logical |

</details>

## 11. VARIABLES

### 11.1 Autres (3)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| EN | i chrono | Numeric | 1x refs |
| EO | i code | Alpha | 1x refs |
| EP | o code existe | Logical | - |

## 12. EXPRESSIONS

**3 / 3 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONSTANTE | 1 | 0 |
| OTHER | 2 | 0 |

### 12.2 Expressions cles par type

#### CONSTANTE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 2 | `0` | - |

#### OTHER (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 3 | `i code [B]` | - |
| OTHER | 1 | `i chrono [A]` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Separation (IDE 27)](ADH-IDE-27.md) -> **Read histo_Fus_Sep_Log (IDE 34)**

Main -> ... -> [Fusion (IDE 28)](ADH-IDE-28.md) -> **Read histo_Fus_Sep_Log (IDE 34)**

```mermaid
graph LR
    T34[34 Read histo_Fus_Sep_Log]
    style T34 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC163[163 Menu caisse GM - s...]
    style CC163 fill:#f59e0b
    CC37[37 Menu changement compte]
    style CC37 fill:#f59e0b
    CC27[27 Separation]
    style CC27 fill:#3fb950
    CC28[28 Fusion]
    style CC28 fill:#3fb950
    CC37 --> CC27
    CC37 --> CC28
    CC163 --> CC37
    CC1 --> CC163
    CC27 --> T34
    CC28 --> T34
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [27](ADH-IDE-27.md) | Separation | 1 |
| [28](ADH-IDE-28.md) | Fusion | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T34[34 Read histo_Fus_Sep_Log]
    style T34 fill:#58a6ff
    NONE[Aucun callee]
    T34 -.-> NONE
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
| Lignes de logique | 12 | Programme compact |
| Expressions | 3 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 12) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 0 ecran, 1 traitement)

- **Strategie** : 1 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-08 01:29*
