# REF IDE 811 - Verif_Format_Mail

> **Analyse**: Phases 1-4 2026-02-03 14:30 -> 14:30 (14s) | Assemblage 14:30
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | REF |
| IDE Position | 811 |
| Nom Programme | Verif_Format_Mail |
| Fichier source | `Prg_811.xml` |
| Dossier IDE | General |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Verif_Format_Mail** assure la gestion complete de ce processus, accessible depuis [Saisie email (IDE 705)](REF-IDE-705.md), [Verification adresse mail (IDE 707)](REF-IDE-707.md), [Recherche Adresse Mail (IDE 731)](REF-IDE-731.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Validation** (1 tache) : controles et verifications de coherence

## 3. BLOCS FONCTIONNELS

### 3.1 Validation (1 tache)

Controles de coherence : 1 tache verifie les donnees et conditions.

---

#### <a id="t1"></a>811 - Verif_Format_Mail

**Role** : Verification : Verif_Format_Mail.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Saisie email (IDE 705)](REF-IDE-705.md), [Verification adresse mail (IDE 707)](REF-IDE-707.md), [Recherche Adresse Mail (IDE 731)](REF-IDE-731.md)
- **Appelle**: 0 programmes | **Tables**: 0 (W:0 R:0 L:0) | **Taches**: 1 | **Expressions**: 0

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **811.1** | [**Verif_Format_Mail** (811)](#t1) | - | - | Validation |

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

### 11.1 Variables de session (1)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | v.Mail | Unicode | - |

### 11.2 Autres (1)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| B | IsValidMail | Logical | - |

## 12. EXPRESSIONS

**0 / 0 expressions decodees (0%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|

### 12.2 Expressions cles par type

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Saisie email (IDE 705)](REF-IDE-705.md) -> **Verif_Format_Mail (IDE 811)**

Main -> ... -> [Verification adresse mail (IDE 707)](REF-IDE-707.md) -> **Verif_Format_Mail (IDE 811)**

Main -> ... -> [Recherche Adresse Mail (IDE 731)](REF-IDE-731.md) -> **Verif_Format_Mail (IDE 811)**

```mermaid
graph LR
    T811[811 Verif_Format_Mail]
    style T811 fill:#58a6ff
    CC730[730 Saisie Signature]
    style CC730 fill:#8b5cf6
    CC705[705 Saisie email]
    style CC705 fill:#3fb950
    CC731[731 Recherche Adresse ...]
    style CC731 fill:#3fb950
    CC707[707 Verification adres...]
    style CC707 fill:#3fb950
    CC730 --> CC705
    CC730 --> CC707
    CC730 --> CC731
    CC705 --> T811
    CC707 --> T811
    CC731 --> T811
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [705](REF-IDE-705.md) | Saisie email | 1 |
| [707](REF-IDE-707.md) | Verification adresse mail | 1 |
| [731](REF-IDE-731.md) | Recherche Adresse Mail | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T811[811 Verif_Format_Mail]
    style T811 fill:#58a6ff
    NONE[Aucun callee]
    T811 -.-> NONE
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
| Lignes de logique | 5 | Programme compact |
| Expressions | 0 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 5) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Validation (1 tache: 0 ecran, 1 traitement)

- **Strategie** : FluentValidation avec validators specifiques.
- Chaque tache de validation -> un validator injectable

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 14:30*
