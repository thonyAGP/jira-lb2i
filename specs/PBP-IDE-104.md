# PBP IDE 104 - Export - GO

> **Analyse**: Phases 1-4 2026-02-03 09:24 -> 09:24 (20s) | Assemblage 09:24
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBP |
| IDE Position | 104 |
| Nom Programme | Export - GO |
| Fichier source | `Prg_104.xml` |
| Domaine metier | General |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Export - GO** assure la gestion complete de ce processus, accessible depuis [Demande Edition GO (IDE 28)](PBP-IDE-28.md), [lanceur (IDE 101)](PBP-IDE-101.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

**Logique metier** : 1 regles identifiees couvrant conditions metier.

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>104 - Export - GO [[ECRAN]](#ecran-t1)

**Role** : Traitement : Export - GO.
**Ecran** : 228 x 76 DLU (MDI) | [Voir mockup](#ecran-t1)


## 5. REGLES METIER

1 regles identifiees:

### Autres (1 regles)

#### <a id="rm-RM-001"></a>[RM-001] Si p.eapis [A] alors INIGet ('[MAGIC_LOGICAL_NAMES]club_exportdata')&'CREW.CSV' sinon '%club_env%tmp_crew.txt')

| Element | Detail |
|---------|--------|
| **Condition** | `p.eapis [A]` |
| **Si vrai** | INIGet ('[MAGIC_LOGICAL_NAMES]club_exportdata')&'CREW.CSV' |
| **Si faux** | '%club_env%tmp_crew.txt') |
| **Variables** | A (p.eapis) |
| **Expression source** | Expression 2 : `IF (p.eapis [A],INIGet ('[MAGIC_LOGICAL_NAMES]club_exportdat` |
| **Exemple** | Si p.eapis [A] â†’ INIGet ('[MAGIC_LOGICAL_NAMES]club_exportdata')&'CREW.CSV'. Sinon â†’ '%club_env%tmp_crew.txt') |
| **Impact** | [104 - Export - GO](#t1) |

## 6. CONTEXTE

- **Appele par**: [Demande Edition GO (IDE 28)](PBP-IDE-28.md), [lanceur (IDE 101)](PBP-IDE-101.md)
- **Appelle**: 0 programmes | **Tables**: 3 (W:0 R:1 L:2) | **Taches**: 1 | **Expressions**: 11

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **104.1** | [**Export - GO** (104)](#t1) [mockup](#ecran-t1) | MDI | 228x76 | Traitement |

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

### Tables utilisees (3)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 35 | personnel_go______go |  | DB | R |   |   | 1 |
| 281 | crew |  | DB |   |   | L | 1 |
| 632 | tempo_selection | Table temporaire ecran | DB |   |   | L | 1 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 35 - personnel_go______go (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | p.eapis | R | Logical |
| B | v.Delimiter | R | Alpha |
| C | v.line | R | Alpha |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (1)

Variables recues du programme appelant ([Demande Edition GO (IDE 28)](PBP-IDE-28.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | p.eapis | Logical | 4x parametre entrant |

### 11.2 Variables de session (2)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| B | v.Delimiter | Alpha | 1x session |
| C | v.line | Alpha | 1x session |

## 12. EXPRESSIONS

**11 / 11 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONDITION | 2 | 5 |
| CONCATENATION | 2 | 0 |
| OTHER | 6 | 0 |
| NEGATION | 1 | 0 |

### 12.2 Expressions cles par type

#### CONDITION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 2 | `IF (p.eapis [A],INIGet ('[MAGIC_LOGICAL_NAMES]club_exportdata')&'CREW.CSV','%club_env%tmp_crew.txt')` | [RM-001](#rm-RM-001) |
| CONDITION | 11 | `IF (p.eapis [A],'3'INDEX,'1'INDEX)` | - |

#### CONCATENATION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 8 | `'Last Name'&Trim ([T])&'First Name'&Trim ([T])&'Middle Name'&Trim ([T])&'Nationality'&Trim ([T])&'Sex'&Trim ([T])&'Date of Birth'&Trim ([T])&'Passport Number'&Trim ([T])&'Country of Issue'&Trim ([T])&'Date of Expiry'` | - |
| CONCATENATION | 10 | `Trim (v.line [C])&Trim ([T])&Trim ([D])&Trim ([T])&Trim ([T])&Trim ([E])&Trim ([T])&Trim ([K])&Trim ([T])&DStr ([F],'YYYY-MM-DD')&Trim ([T])&Trim ([G])&Trim ([T])&Trim ([I])&Trim ([T])&DStr ([J],'YYYY-MM-DD')` | - |

#### OTHER (6 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 5 | `[O]` | - |
| OTHER | 6 | `p.eapis [A]` | - |
| OTHER | 7 | `INIGet ('[MAGIC_LOGICAL_NAMES]club_excel_separator')` | - |
| OTHER | 1 | `v.Delimiter [B]` | - |
| OTHER | 3 | `[M]` | - |
| ... | | *+1 autres* | |

#### NEGATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| NEGATION | 9 | `NOT (p.eapis [A])` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Demande Edition GO (IDE 28)](PBP-IDE-28.md) -> **Export - GO (IDE 104)**

Main -> ... -> [lanceur (IDE 101)](PBP-IDE-101.md) -> **Export - GO (IDE 104)**

```mermaid
graph LR
    T104[104 Export - GO]
    style T104 fill:#58a6ff
    CC101[101 lanceur]
    style CC101 fill:#8b5cf6
    CC28[28 Demande Edition GO]
    style CC28 fill:#8b5cf6
    CC28 --> T104
    CC101 --> T104
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [28](PBP-IDE-28.md) | Demande Edition GO | 3 |
| [101](PBP-IDE-101.md) | lanceur | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T104[104 Export - GO]
    style T104 fill:#58a6ff
    NONE[Aucun callee]
    T104 -.-> NONE
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
| Lignes de logique | 44 | Programme compact |
| Expressions | 11 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 44) | Code sain |
| Regles metier | 1 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 1 ecran, 0 traitement)

- **Strategie** : 1 composant(s) UI (Razor/React) avec formulaires et validation.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 09:24*
