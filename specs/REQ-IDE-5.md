# REQ IDE 5 - combo MYSERVICES

> **Analyse**: Phases 1-4 2026-02-03 20:23 -> 20:23 (15s) | Assemblage 20:23
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | REQ |
| IDE Position | 5 |
| Nom Programme | combo MYSERVICES |
| Fichier source | `Prg_5.xml` |
| Dossier IDE | Combos |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**combo MYSERVICES** assure la gestion complete de ce processus, accessible depuis [  Load combos (IDE 31)](REQ-IDE-31.md), [MAJ service (IDE 38)](REQ-IDE-38.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Consultation** (1 tache) : ecrans de recherche, selection et consultation

**Donnees modifiees** : 1 tables en ecriture (req_requests).

## 3. BLOCS FONCTIONNELS

### 3.1 Consultation (1 tache)

Ecrans de recherche et consultation.

---

#### <a id="t1"></a>5 - Zoom service [[ECRAN]](#ecran-t1)

**Role** : Selection par l'operateur : Zoom service.
**Ecran** : 256 x 68 DLU (MDI) | [Voir mockup](#ecran-t1)
**Variables liees** : B (p.list services)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [  Load combos (IDE 31)](REQ-IDE-31.md), [MAJ service (IDE 38)](REQ-IDE-38.md)
- **Appelle**: 0 programmes | **Tables**: 2 (W:1 R:0 L:1) | **Taches**: 1 | **Expressions**: 7

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **5.1** | [**Zoom service** (5)](#t1) [mockup](#ecran-t1) | MDI | 256x68 | Consultation |

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
| 432 | req_type_intervenant |  | DB |   |   | L | 1 |
| 436 | req_requests |  | DB |   | **W** |   | 1 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 436 - req_requests (**W**) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | p.with names | W | Logical |
| B | p.list services | W | Alpha |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (2)

Variables recues du programme appelant ([  Load combos (IDE 31)](REQ-IDE-31.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | p.with names | Logical | 2x parametre entrant |
| B | p.list services | Alpha | 3x parametre entrant |

## 12. EXPRESSIONS

**7 / 7 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCULATION | 1 | 0 |
| OTHER | 3 | 0 |
| CONCATENATION | 1 | 0 |
| STRING | 2 | 0 |

### 12.2 Expressions cles par type

#### CALCULATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 4 | `Left (Trim (p.list services [B]),Len (Trim (p.list services [B]))-1)` | - |

#### OTHER (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 7 | `[G]` | - |
| OTHER | 2 | `[D]` | - |
| OTHER | 1 | `GetParam ('GROUP')` | - |

#### CONCATENATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 3 | `Trim (p.list services [B])&Trim ([D])&IF (p.with names [A],':'&Trim ([F]),'')&','` | - |

#### STRING (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| STRING | 6 | `SetParam ('SERVICESINIT',Trim ([D]))` | - |
| STRING | 5 | `SetParam (IF (p.with names [A],'MYFULLSERVICES','MYSERVICES'),RTrim (p.list services [B]))` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [  Load combos (IDE 31)](REQ-IDE-31.md) -> **combo MYSERVICES (IDE 5)**

Main -> ... -> [MAJ service (IDE 38)](REQ-IDE-38.md) -> **combo MYSERVICES (IDE 5)**

```mermaid
graph LR
    T5[5 combo MYSERVICES]
    style T5 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC52[52 MAIN MENU]
    style CC52 fill:#f59e0b
    CC21[21 Menu requests]
    style CC21 fill:#f59e0b
    CC40[40 MAJ parameters]
    style CC40 fill:#f59e0b
    CC35[35 MAJ locations]
    style CC35 fill:#f59e0b
    CC29[29 Init REQ]
    style CC29 fill:#f59e0b
    CC41[41 MAJ Group profiles]
    style CC41 fill:#f59e0b
    CC22[22 Menu Administration]
    style CC22 fill:#f59e0b
    CC31[31 Load combos]
    style CC31 fill:#3fb950
    CC38[38 MAJ service]
    style CC38 fill:#3fb950
    CC29 --> CC31
    CC41 --> CC31
    CC22 --> CC31
    CC35 --> CC31
    CC29 --> CC38
    CC41 --> CC38
    CC22 --> CC38
    CC35 --> CC38
    CC21 --> CC29
    CC40 --> CC29
    CC21 --> CC41
    CC40 --> CC41
    CC21 --> CC22
    CC40 --> CC22
    CC21 --> CC35
    CC40 --> CC35
    CC52 --> CC21
    CC52 --> CC40
    CC1 --> CC52
    CC31 --> T5
    CC38 --> T5
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [31](REQ-IDE-31.md) |   Load combos | 2 |
| [38](REQ-IDE-38.md) | MAJ service | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T5[5 combo MYSERVICES]
    style T5 fill:#58a6ff
    NONE[Aucun callee]
    T5 -.-> NONE
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
| Lignes de logique | 16 | Programme compact |
| Expressions | 7 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 16) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Consultation (1 tache: 1 ecran, 0 traitement)

- **Strategie** : Composants de recherche/selection en modales.
- 1 ecran : Zoom service

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| req_requests | Table WRITE (Database) | 1x | Schema + repository |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 20:23*
