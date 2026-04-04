# QUA IDE 14 - Ouv/Ferm Port Com

> **Analyse**: Phases 1-4 2026-02-03 20:18 -> 20:18 (15s) | Assemblage 20:18
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | QUA |
| IDE Position | 14 |
| Nom Programme | Ouv/Ferm Port Com |
| Fichier source | `Prg_14.xml` |
| Dossier IDE | Port |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Ouv/Ferm Port Com** assure la gestion complete de ce processus, accessible depuis [Sequence Complete (IDE 18)](QUA-IDE-18.md), [Flush Serial (IDE 19)](QUA-IDE-19.md), [Sequence Complete (IDE 24)](QUA-IDE-24.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>14 - Ouv/Ferm Port Com

**Role** : Traitement : Ouv/Ferm Port Com.
**Variables liees** : B (Prm - p.Port)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Sequence Complete (IDE 18)](QUA-IDE-18.md), [Flush Serial (IDE 19)](QUA-IDE-19.md), [Sequence Complete (IDE 24)](QUA-IDE-24.md)
- **Appelle**: 0 programmes | **Tables**: 0 (W:0 R:0 L:0) | **Taches**: 1 | **Expressions**: 7

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **14.1** | [**Ouv/Ferm Port Com** (14)](#t1) | MDI | - | Traitement |

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

### 11.1 Autres (7)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | Prm - Action | Alpha | 2x refs |
| B | Prm - p.Port | Numeric | - |
| C | Prm - Vitesse | Numeric | - |
| D | Prm - Parite | Alpha | - |
| E | Prm - Bit Arret | Alpha | - |
| F | Prm - Bit Donnees | Alpha | - |
| G | Prm - Statut | Numeric | - |

## 12. EXPRESSIONS

**7 / 7 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONSTANTE | 3 | 0 |
| CONCATENATION | 2 | 0 |
| CONDITION | 2 | 0 |

### 12.2 Expressions cles par type

#### CONSTANTE (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 6 | `'22'` | - |
| CONSTANTE | 3 | `0` | - |
| CONSTANTE | 2 | `'24AAA22222'` | - |

#### CONCATENATION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 5 | `'@'&Translate('%dll%')&'scomm.dll.sc_close'` | - |
| CONCATENATION | 1 | `'@'&Translate('%dll%')&'scomm.dll.sc_open'` | - |

#### CONDITION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 7 | `Prm - Action [A]='F'` | - |
| CONDITION | 4 | `Prm - Action [A]='O'` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Sequence Complete (IDE 18)](QUA-IDE-18.md) -> **Ouv/Ferm Port Com (IDE 14)**

Main -> ... -> [Flush Serial (IDE 19)](QUA-IDE-19.md) -> **Ouv/Ferm Port Com (IDE 14)**

Main -> ... -> [Sequence Complete (IDE 24)](QUA-IDE-24.md) -> **Ouv/Ferm Port Com (IDE 14)**

```mermaid
graph LR
    T14[14 OuvFerm Port Com]
    style T14 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC8[8 Check All Rooms]
    style CC8 fill:#f59e0b
    CC9[9 Test Check In]
    style CC9 fill:#f59e0b
    CC27[27 Test Check In]
    style CC27 fill:#f59e0b
    CC5[5 Interfaces]
    style CC5 fill:#f59e0b
    CC18[18 Sequence Complete]
    style CC18 fill:#3fb950
    CC19[19 Flush Serial]
    style CC19 fill:#3fb950
    CC24[24 Sequence Complete]
    style CC24 fill:#3fb950
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
    CC1 --> CC5
    CC1 --> CC8
    CC1 --> CC9
    CC1 --> CC27
    CC18 --> T14
    CC19 --> T14
    CC24 --> T14
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [18](QUA-IDE-18.md) | Sequence Complete | 3 |
| [19](QUA-IDE-19.md) | Flush Serial | 3 |
| [24](QUA-IDE-24.md) | Sequence Complete | 3 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T14[14 OuvFerm Port Com]
    style T14 fill:#58a6ff
    NONE[Aucun callee]
    T14 -.-> NONE
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
| Lignes de logique | 11 | Programme compact |
| Expressions | 7 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 11) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 0 ecran, 1 traitement)

- **Strategie** : 1 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 20:18*
