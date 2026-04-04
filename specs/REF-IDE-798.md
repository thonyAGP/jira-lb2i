# REF IDE 798 - DateTimeToUnixTimeStamp

> **Analyse**: Phases 1-4 2026-02-03 14:26 -> 14:26 (14s) | Assemblage 14:26
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | REF |
| IDE Position | 798 |
| Nom Programme | DateTimeToUnixTimeStamp |
| Fichier source | `Prg_798.xml` |
| Dossier IDE | General |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**DateTimeToUnixTimeStamp** assure la gestion complete de ce processus, accessible depuis [Appel Curl API (IDE 634)](REF-IDE-634.md), [Appel Curl ETIS (IDE 856)](REF-IDE-856.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>798 - DateTimeToUnixTimeStamp

**Role** : Traitement : DateTimeToUnixTimeStamp.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Appel Curl API (IDE 634)](REF-IDE-634.md), [Appel Curl ETIS (IDE 856)](REF-IDE-856.md)
- **Appelle**: 0 programmes | **Tables**: 0 (W:0 R:0 L:0) | **Taches**: 1 | **Expressions**: 0

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **798.1** | [**DateTimeToUnixTimeStamp** (798)](#t1) | - | - | Traitement |

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

### 11.1 Parametres entrants (4)

Variables recues du programme appelant ([Appel Curl API (IDE 634)](REF-IDE-634.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P.DateTime | Date | - |
| B | P.Time | Time | - |
| C | P.DecalageHoraire | Numeric | - |
| D | P.TimeStamp | Unicode | - |

### 11.2 Autres (2)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| E | IsSuccess | Logical | - |
| F | ErrorMassage | Alpha | - |

## 12. EXPRESSIONS

**0 / 0 expressions decodees (0%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|

### 12.2 Expressions cles par type

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Appel Curl API (IDE 634)](REF-IDE-634.md) -> **DateTimeToUnixTimeStamp (IDE 798)**

Main -> ... -> [Appel Curl ETIS (IDE 856)](REF-IDE-856.md) -> **DateTimeToUnixTimeStamp (IDE 798)**

```mermaid
graph LR
    T798[798 DateTimeToUnixTime...]
    style T798 fill:#58a6ff
    CC638[638 Controle Presence ...]
    style CC638 fill:#8b5cf6
    CC712[712 Gestion TPE Axis O...]
    style CC712 fill:#8b5cf6
    CC884[884 Appel Routes]
    style CC884 fill:#8b5cf6
    CC852[852 Récupère màj des c...]
    style CC852 fill:#f59e0b
    CC853[853 Test connexion Etis]
    style CC853 fill:#f59e0b
    CC851[851 Chambre à faire]
    style CC851 fill:#f59e0b
    CC635[635 Club Med API demo]
    style CC635 fill:#f59e0b
    CC637[637 Pilotage API CM Pa...]
    style CC637 fill:#f59e0b
    CC639[639 Pilotage API CM Stay]
    style CC639 fill:#f59e0b
    CC634[634 Appel Curl API]
    style CC634 fill:#3fb950
    CC856[856 Appel Curl ETIS]
    style CC856 fill:#3fb950
    CC635 --> CC634
    CC637 --> CC634
    CC639 --> CC634
    CC851 --> CC634
    CC852 --> CC634
    CC853 --> CC634
    CC635 --> CC856
    CC637 --> CC856
    CC639 --> CC856
    CC851 --> CC856
    CC852 --> CC856
    CC853 --> CC856
    CC638 --> CC635
    CC712 --> CC635
    CC884 --> CC635
    CC638 --> CC637
    CC712 --> CC637
    CC884 --> CC637
    CC638 --> CC639
    CC712 --> CC639
    CC884 --> CC639
    CC638 --> CC851
    CC712 --> CC851
    CC884 --> CC851
    CC638 --> CC852
    CC712 --> CC852
    CC884 --> CC852
    CC638 --> CC853
    CC712 --> CC853
    CC884 --> CC853
    CC634 --> T798
    CC856 --> T798
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [634](REF-IDE-634.md) | Appel Curl API | 1 |
| [856](REF-IDE-856.md) | Appel Curl ETIS | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T798[798 DateTimeToUnixTime...]
    style T798 fill:#58a6ff
    NONE[Aucun callee]
    T798 -.-> NONE
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
| Expressions | 0 | Peu de logique |
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
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 14:26*
