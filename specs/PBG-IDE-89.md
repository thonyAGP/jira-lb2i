# PBG IDE 89 - Maj Nationalite heberg

> **Analyse**: Phases 1-4 2026-02-03 09:16 -> 09:17 (19s) | Assemblage 09:17
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBG |
| IDE Position | 89 |
| Nom Programme | Maj Nationalite heberg |
| Fichier source | `Prg_89.xml` |
| Domaine metier | General |
| Taches | 2 (0 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Maj Nationalite heberg** assure la gestion complete de ce processus, accessible depuis [  Maj Passport (IDE 90)](PBG-IDE-90.md), [Modules clients Identite (IDE 91)](PBG-IDE-91.md), [Saisie des fiches de police (IDE 93)](PBG-IDE-93.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (2 taches) : traitements metier divers

**Donnees modifiees** : 1 tables en ecriture (hebergement______heb).

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (2 taches)

Traitements internes.

---

#### <a id="t1"></a>89 - Maj Nationalite heberg

**Role** : Traitement : Maj Nationalite heberg.

---

#### <a id="t2"></a>89.1 - Mise a jour fichier 12

**Role** : Traitement : Mise a jour fichier 12.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [  Maj Passport (IDE 90)](PBG-IDE-90.md), [Modules clients Identite (IDE 91)](PBG-IDE-91.md), [Saisie des fiches de police (IDE 93)](PBG-IDE-93.md)
- **Appelle**: 0 programmes | **Tables**: 1 (W:1 R:0 L:0) | **Taches**: 2 | **Expressions**: 3

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (2 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **89.1** | [**Maj Nationalite heberg** (89)](#t1) | MDI | - | Traitement |
| 89.1.1 | [Mise a jour fichier 12 (89.1)](#t2) | MDI | - | |

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
| 34 | hebergement______heb | Hebergement (chambres) | DB |   | **W** |   | 1 |

### Colonnes par table (0 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 34 - hebergement______heb (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Autres (3)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | > compte | Numeric | - |
| B | > filiation | Numeric | - |
| C | > code pays | Alpha | - |

## 12. EXPRESSIONS

**3 / 3 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONSTANTE | 3 | 0 |

### 12.2 Expressions cles par type

#### CONSTANTE (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 3 | `'H'` | - |
| CONSTANTE | 2 | `'Z'` | - |
| CONSTANTE | 1 | `'A'` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [  Maj Passport (IDE 90)](PBG-IDE-90.md) -> **Maj Nationalite heberg (IDE 89)**

Main -> ... -> [Modules clients Identite (IDE 91)](PBG-IDE-91.md) -> **Maj Nationalite heberg (IDE 89)**

Main -> ... -> [Saisie des fiches de police (IDE 93)](PBG-IDE-93.md) -> **Maj Nationalite heberg (IDE 89)**

```mermaid
graph LR
    T89[89 Maj Nationalite heberg]
    style T89 fill:#58a6ff
    CC206[206 Traitement des arr...]
    style CC206 fill:#8b5cf6
    CC222[222 lanceur]
    style CC222 fill:#8b5cf6
    CC223[223 Transferts Caisse]
    style CC223 fill:#f59e0b
    CC94[94 Module Sejours Call...]
    style CC94 fill:#f59e0b
    CC391[391 Module Sejours Sub...]
    style CC391 fill:#f59e0b
    CC86[86 Creation filiation]
    style CC86 fill:#f59e0b
    CC87[87 Creation clients Id...]
    style CC87 fill:#f59e0b
    CC90[90 Maj Passport]
    style CC90 fill:#3fb950
    CC91[91 Modules clients Ide...]
    style CC91 fill:#3fb950
    CC93[93 Saisie des fiches d...]
    style CC93 fill:#3fb950
    CC86 --> CC90
    CC87 --> CC90
    CC223 --> CC90
    CC94 --> CC90
    CC391 --> CC90
    CC86 --> CC91
    CC87 --> CC91
    CC223 --> CC91
    CC94 --> CC91
    CC391 --> CC91
    CC86 --> CC93
    CC87 --> CC93
    CC223 --> CC93
    CC94 --> CC93
    CC391 --> CC93
    CC206 --> CC86
    CC222 --> CC86
    CC206 --> CC87
    CC222 --> CC87
    CC206 --> CC223
    CC222 --> CC223
    CC206 --> CC94
    CC222 --> CC94
    CC206 --> CC391
    CC222 --> CC391
    CC90 --> T89
    CC91 --> T89
    CC93 --> T89
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [90](PBG-IDE-90.md) |   Maj Passport | 1 |
| [91](PBG-IDE-91.md) | Modules clients Identite | 1 |
| [93](PBG-IDE-93.md) | Saisie des fiches de police | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T89[89 Maj Nationalite heberg]
    style T89 fill:#58a6ff
    NONE[Aucun callee]
    T89 -.-> NONE
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
| Lignes de logique | 17 | Programme compact |
| Expressions | 3 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 17) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (2 taches: 0 ecran, 2 traitements)

- **Strategie** : 2 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| hebergement______heb | Table WRITE (Database) | 1x | Schema + repository |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 09:17*
