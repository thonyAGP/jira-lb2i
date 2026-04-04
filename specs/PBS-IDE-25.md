# PBS IDE 25 - Logement Libre ?

> **Analyse**: Phases 1-4 2026-02-03 17:08 -> 17:08 (17s) | Assemblage 17:08
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBS |
| IDE Position | 25 |
| Nom Programme | Logement Libre ? |
| Fichier source | `Prg_25.xml` |
| Dossier IDE | Logement |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Logement Libre ?** assure la gestion complete de ce processus, accessible depuis [ Suppression Logement Client (IDE 31)](PBS-IDE-31.md), [ Suppression Logement Perso (IDE 36)](PBS-IDE-36.md), [Suppression Logement Exterieur (IDE 40)](PBS-IDE-40.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Validation** (1 tache) : controles et verifications de coherence

## 3. BLOCS FONCTIONNELS

### 3.1 Validation (1 tache)

Controles de coherence : 1 tache verifie les donnees et conditions.

---

#### <a id="t1"></a>25 - Verification Existant Nom [[ECRAN]](#ecran-t1)

**Role** : Verification : Verification Existant Nom.
**Ecran** : 170 x 108 DLU (MDI) | [Voir mockup](#ecran-t1)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [ Suppression Logement Client (IDE 31)](PBS-IDE-31.md), [ Suppression Logement Perso (IDE 36)](PBS-IDE-36.md), [Suppression Logement Exterieur (IDE 40)](PBS-IDE-40.md)
- **Appelle**: 0 programmes | **Tables**: 1 (W:0 R:1 L:0) | **Taches**: 1 | **Expressions**: 7

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **25.1** | [**Verification Existant Nom** (25)](#t1) [mockup](#ecran-t1) | MDI | 170x108 | Validation |

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
| 34 | hebergement______heb | Hebergement (chambres) | DB | R |   |   | 1 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 34 - hebergement______heb (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | >Nom Standard | R | Alpha |
| B | < Validation | R | Logical |
| C | v.Lien Existe | R | Logical |

</details>

## 11. VARIABLES

### 11.1 Variables de session (1)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| C | v.Lien Existe | Logical | 1x session |

### 11.2 Autres (2)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | >Nom Standard | Alpha | 1x refs |
| B | < Validation | Logical | 1x refs |

## 12. EXPRESSIONS

**7 / 7 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONSTANTE | 1 | 0 |
| OTHER | 2 | 0 |
| CONDITION | 1 | 0 |
| CAST_LOGIQUE | 2 | 0 |
| NEGATION | 1 | 0 |

### 12.2 Expressions cles par type

#### CONSTANTE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 2 | `'H'` | - |

#### OTHER (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 6 | `v.Lien Existe [C]` | - |
| OTHER | 1 | `GetParam ('SOCIETE')` | - |

#### CONDITION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 3 | `>Nom Standard [A]` | - |

#### CAST_LOGIQUE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 5 | `'FALSE'LOG` | - |
| CAST_LOGIQUE | 4 | `'TRUE'LOG` | - |

#### NEGATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| NEGATION | 7 | `NOT < Validation [B]` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [ Suppression Logement Client (IDE 31)](PBS-IDE-31.md) -> **Logement Libre ? (IDE 25)**

Main -> ... -> [ Suppression Logement Perso (IDE 36)](PBS-IDE-36.md) -> **Logement Libre ? (IDE 25)**

Main -> ... -> [Suppression Logement Exterieur (IDE 40)](PBS-IDE-40.md) -> **Logement Libre ? (IDE 25)**

```mermaid
graph LR
    T25[25 Logement Libre]
    style T25 fill:#58a6ff
    CC23[23 Logement client pms...]
    style CC23 fill:#8b5cf6
    CC99[99 Logement client pms...]
    style CC99 fill:#8b5cf6
    CC34[34 Logement personnel]
    style CC34 fill:#8b5cf6
    CC38[38 Logement exterieur]
    style CC38 fill:#8b5cf6
    CC22[22 Logement client]
    style CC22 fill:#8b5cf6
    CC31[31 Suppression Logemen...]
    style CC31 fill:#3fb950
    CC40[40 Suppression Logemen...]
    style CC40 fill:#3fb950
    CC36[36 Suppression Logemen...]
    style CC36 fill:#3fb950
    CC22 --> CC31
    CC23 --> CC31
    CC99 --> CC31
    CC34 --> CC31
    CC38 --> CC31
    CC22 --> CC36
    CC23 --> CC36
    CC99 --> CC36
    CC34 --> CC36
    CC38 --> CC36
    CC22 --> CC40
    CC23 --> CC40
    CC99 --> CC40
    CC34 --> CC40
    CC38 --> CC40
    CC31 --> T25
    CC36 --> T25
    CC40 --> T25
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [31](PBS-IDE-31.md) |  Suppression Logement Client | 1 |
| [36](PBS-IDE-36.md) |  Suppression Logement Perso | 1 |
| [40](PBS-IDE-40.md) | Suppression Logement Exterieur | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T25[25 Logement Libre]
    style T25 fill:#58a6ff
    NONE[Aucun callee]
    T25 -.-> NONE
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
| Lignes de logique | 14 | Programme compact |
| Expressions | 7 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 14) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Validation (1 tache: 1 ecran, 0 traitement)

- **Strategie** : FluentValidation avec validators specifiques.
- Chaque tache de validation -> un validator injectable

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 17:08*
