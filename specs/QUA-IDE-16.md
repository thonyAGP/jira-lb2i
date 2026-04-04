# QUA IDE 16 - Ecriture Simple

> **Analyse**: Phases 1-4 2026-02-03 20:18 -> 20:19 (15s) | Assemblage 20:19
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | QUA |
| IDE Position | 16 |
| Nom Programme | Ecriture Simple |
| Fichier source | `Prg_16.xml` |
| Dossier IDE | Port |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Ecriture Simple** assure la gestion complete de ce processus, accessible depuis [Sequence Complete (IDE 18)](QUA-IDE-18.md), [Sequence Complete (IDE 24)](QUA-IDE-24.md), [Boucle Lecture (IDE 15)](QUA-IDE-15.md), [Boucle Lecture (IDE 25)](QUA-IDE-25.md), [Flush Serial (IDE 19)](QUA-IDE-19.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

**Logique metier** : 1 regles identifiees couvrant conditions metier.

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>16 - Ecriture Simple

**Role** : Traitement : Ecriture Simple.


## 5. REGLES METIER

1 regles identifiees:

### Autres (1 regles)

#### <a id="rm-RM-001"></a>[RM-001] Si Len(Trim(Prm - Message [B]))<>[F] alors Trim(Prm - Message [B])&' .' sinon Trim(Prm - Message [B]))

| Element | Detail |
|---------|--------|
| **Condition** | `Len(Trim(Prm - Message [B]))<>[F]` |
| **Si vrai** | Trim(Prm - Message [B])&' .' |
| **Si faux** | Trim(Prm - Message [B])) |
| **Variables** | B (Prm - Message) |
| **Expression source** | Expression 3 : `IF(Len(Trim(Prm - Message [B]))<>[F],Trim(Prm - Message [B])` |
| **Exemple** | Si Len(Trim(Prm - Message [B]))<>[F] â†’ Trim(Prm - Message [B])&' .'. Sinon â†’ Trim(Prm - Message [B])) |

## 6. CONTEXTE

- **Appele par**: [Sequence Complete (IDE 18)](QUA-IDE-18.md), [Sequence Complete (IDE 24)](QUA-IDE-24.md), [Boucle Lecture (IDE 15)](QUA-IDE-15.md), [Boucle Lecture (IDE 25)](QUA-IDE-25.md), [Flush Serial (IDE 19)](QUA-IDE-19.md)
- **Appelle**: 0 programmes | **Tables**: 0 (W:0 R:0 L:0) | **Taches**: 1 | **Expressions**: 6

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **16.1** | [**Ecriture Simple** (16)](#t1) | MDI | - | Traitement |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Traitement principal]
    DECISION{Message}
    PROCESS[Traitement]
    ENDOK([END OK])
    ENDKO([END KO])

    START --> INIT --> SAISIE --> DECISION
    DECISION -->|OUI| PROCESS
    DECISION -->|NON| ENDKO
    PROCESS --> ENDOK

    style START fill:#3fb950,color:#000
    style ENDOK fill:#3fb950,color:#000
    style ENDKO fill:#f85149,color:#fff
    style DECISION fill:#58a6ff,color:#000
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

### 11.1 Variables de session (1)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| E | V - Statut Numerique | Numeric | - |

### 11.2 Autres (4)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | Prm - Port | Numeric | - |
| B | Prm - Message | Alpha | 1x refs |
| C | Prm - Taille Message | Numeric | 1x refs |
| D | Prm - Statut Logique | Logical | - |

## 12. EXPRESSIONS

**6 / 6 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONDITION | 2 | 5 |
| CONSTANTE | 1 | 0 |
| CONCATENATION | 1 | 0 |
| OTHER | 1 | 0 |
| CAST_LOGIQUE | 1 | 0 |

### 12.2 Expressions cles par type

#### CONDITION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 3 | `IF(Len(Trim(Prm - Message [B]))<>[F],Trim(Prm - Message [B])&' .',Trim(Prm - Message [B]))` | [RM-001](#rm-RM-001) |
| CONDITION | 6 | `Prm - Taille Message [C]=0` | - |

#### CONSTANTE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 2 | `'2A22'` | - |

#### CONCATENATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 1 | `'@'&Translate('%dll%')&'scomm.dll.sc_write'` | - |

#### OTHER (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 4 | `[F]` | - |

#### CAST_LOGIQUE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 5 | `'TRUE'LOG` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Sequence Complete (IDE 18)](QUA-IDE-18.md) -> **Ecriture Simple (IDE 16)**

Main -> ... -> [Sequence Complete (IDE 24)](QUA-IDE-24.md) -> **Ecriture Simple (IDE 16)**

Main -> ... -> [Boucle Lecture (IDE 15)](QUA-IDE-15.md) -> **Ecriture Simple (IDE 16)**

Main -> ... -> [Boucle Lecture (IDE 25)](QUA-IDE-25.md) -> **Ecriture Simple (IDE 16)**

Main -> ... -> [Flush Serial (IDE 19)](QUA-IDE-19.md) -> **Ecriture Simple (IDE 16)**

```mermaid
graph LR
    T16[16 Ecriture Simple]
    style T16 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC8[8 Check All Rooms]
    style CC8 fill:#f59e0b
    CC5[5 Interfaces]
    style CC5 fill:#f59e0b
    CC9[9 Test Check In]
    style CC9 fill:#f59e0b
    CC27[27 Test Check In]
    style CC27 fill:#f59e0b
    CC15[15 Boucle Lecture]
    style CC15 fill:#3fb950
    CC19[19 Flush Serial]
    style CC19 fill:#3fb950
    CC18[18 Sequence Complete]
    style CC18 fill:#3fb950
    CC25[25 Boucle Lecture]
    style CC25 fill:#3fb950
    CC24[24 Sequence Complete]
    style CC24 fill:#3fb950
    CC5 --> CC15
    CC8 --> CC15
    CC9 --> CC15
    CC27 --> CC15
    CC5 --> CC18
    CC8 --> CC18
    CC9 --> CC18
    CC27 --> CC18
    CC5 --> CC19
    CC8 --> CC19
    CC9 --> CC19
    CC27 --> CC19
    CC5 --> CC24
    CC8 --> CC24
    CC9 --> CC24
    CC27 --> CC24
    CC5 --> CC25
    CC8 --> CC25
    CC9 --> CC25
    CC27 --> CC25
    CC1 --> CC5
    CC1 --> CC8
    CC1 --> CC9
    CC1 --> CC27
    CC15 --> T16
    CC18 --> T16
    CC19 --> T16
    CC24 --> T16
    CC25 --> T16
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [18](QUA-IDE-18.md) | Sequence Complete | 5 |
| [24](QUA-IDE-24.md) | Sequence Complete | 5 |
| [15](QUA-IDE-15.md) | Boucle Lecture | 2 |
| [25](QUA-IDE-25.md) | Boucle Lecture | 2 |
| [19](QUA-IDE-19.md) | Flush Serial | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T16[16 Ecriture Simple]
    style T16 fill:#58a6ff
    NONE[Aucun callee]
    T16 -.-> NONE
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
| Lignes de logique | 9 | Programme compact |
| Expressions | 6 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 9) | Code sain |
| Regles metier | 1 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 0 ecran, 1 traitement)

- **Strategie** : 1 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 20:19*
