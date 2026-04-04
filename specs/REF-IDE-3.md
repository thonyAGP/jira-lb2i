# REF IDE 3 - 900 Progs - 06/01/2026

> **Analyse**: Phases 1-4 2026-02-03 00:51 -> 00:52 (50s) | Assemblage 00:52
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | REF |
| IDE Position | 3 |
| Nom Programme | 900 Progs - 06/01/2026 |
| Fichier source | `Prg_3.xml` |
| Domaine metier | General |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**900 Progs - 06/01/2026** assure la gestion complete de ce processus, accessible depuis [Log batch (IDE 829)](REF-IDE-829.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>3 - 833 Progs - 25/08/2021

**Role** : Traitement : 833 Progs - 25/08/2021.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Log batch (IDE 829)](REF-IDE-829.md)
- **Appelle**: 0 programmes | **Tables**: 0 (W:0 R:0 L:0) | **Taches**: 1 | **Expressions**: 1

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **3.1** | [**833 Progs - 25/08/2021** (3)](#t1) | - | - | Traitement |

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
| CALCULATION | 1 | 0 |

### 12.2 Expressions cles par type

#### CALCULATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 1 | `Flip(Trim(StrToken(StrToken(Flip(Trim(Prog())), 1, ';'), 1, '-')))` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Log batch (IDE 829)](REF-IDE-829.md) -> **900 Progs - 06/01/2026 (IDE 3)**

```mermaid
graph LR
    T3[3 900 Progs - 06012026]
    style T3 fill:#58a6ff
    CC635[635 Club Med API demo]
    style CC635 fill:#8b5cf6
    CC632[632 Lancement Chambre ...]
    style CC632 fill:#8b5cf6
    CC639[639 Pilotage API CM Stay]
    style CC639 fill:#8b5cf6
    CC637[637 Pilotage API CM Pa...]
    style CC637 fill:#8b5cf6
    CC636[636 Club Med API Route]
    style CC636 fill:#f59e0b
    CC616[616 Extraction biking]
    style CC616 fill:#f59e0b
    CC1[1 Main Program]
    style CC1 fill:#f59e0b
    CC633[633 Club Med API token]
    style CC633 fill:#f59e0b
    CC631[631 Passage des chambr...]
    style CC631 fill:#f59e0b
    CC829[829 Log batch]
    style CC829 fill:#3fb950
    CC1 --> CC829
    CC616 --> CC829
    CC631 --> CC829
    CC633 --> CC829
    CC636 --> CC829
    CC632 --> CC1
    CC635 --> CC1
    CC637 --> CC1
    CC639 --> CC1
    CC632 --> CC616
    CC635 --> CC616
    CC637 --> CC616
    CC639 --> CC616
    CC632 --> CC631
    CC635 --> CC631
    CC637 --> CC631
    CC639 --> CC631
    CC632 --> CC633
    CC635 --> CC633
    CC637 --> CC633
    CC639 --> CC633
    CC632 --> CC636
    CC635 --> CC636
    CC637 --> CC636
    CC639 --> CC636
    CC829 --> T3
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [829](REF-IDE-829.md) | Log batch | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T3[3 900 Progs - 06012026]
    style T3 fill:#58a6ff
    NONE[Aucun callee]
    T3 -.-> NONE
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
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 00:52*
