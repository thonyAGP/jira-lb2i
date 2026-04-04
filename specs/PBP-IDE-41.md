# PBP IDE 41 - Recherche personnel Valider

> **Analyse**: Phases 1-4 2026-02-03 08:51 -> 08:52 (34s) | Assemblage 08:52
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBP |
| IDE Position | 41 |
| Nom Programme | Recherche personnel Valider |
| Fichier source | `Prg_41.xml` |
| Domaine metier | Consultation |
| Taches | 3 (0 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Recherche personnel Valider** assure la gestion complete de ce processus, accessible depuis [Demande Edition GO (IDE 28)](PBP-IDE-28.md), [lanceur (IDE 101)](PBP-IDE-101.md).

Le flux de traitement s'organise en **3 blocs fonctionnels** :

- **Consultation** (1 tache) : ecrans de recherche, selection et consultation
- **Traitement** (1 tache) : traitements metier divers
- **Validation** (1 tache) : controles et verifications de coherence

**Donnees modifiees** : 1 tables en ecriture (tempo_selection).

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Validation (1 tache)

- **41** - Recherche personnel Valider

#### Phase 2 : Traitement (1 tache)

- **41.1** - Complete

#### Phase 3 : Consultation (1 tache)

- **41.2** - Recherche Cabine

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| tempo_selection | **W**/L (2 usages) | Table temporaire ecran |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Validation (1 tache)

Controles de coherence : 1 tache verifie les donnees et conditions.

---

#### <a id="t1"></a>41 - Recherche personnel Valider

**Role** : Verification : Recherche personnel Valider.


### 3.2 Traitement (1 tache)

Traitements internes.

---

#### <a id="t3"></a>41.1 - Complete

**Role** : Traitement : Complete.


### 3.3 Consultation (1 tache)

Ecrans de recherche et consultation.

---

#### <a id="t4"></a>41.2 - Recherche Cabine

**Role** : Traitement : Recherche Cabine.
**Variables liees** : B (v.numero cabine)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Demande Edition GO (IDE 28)](PBP-IDE-28.md), [lanceur (IDE 101)](PBP-IDE-101.md)
- **Appelle**: 0 programmes | **Tables**: 9 (W:1 R:2 L:8) | **Taches**: 3 | **Expressions**: 7

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (3 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **41.1** | [**Recherche personnel Valider** (41)](#t1) | MDI | - | Validation |
| **41.2** | [**Complete** (41.1)](#t3) | MDI | - | Traitement |
| **41.3** | [**Recherche Cabine** (41.2)](#t4) | MDI | - | Consultation |

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

### Tables utilisees (9)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 31 | gm-complet_______gmc |  | DB | R |   |   | 1 |
| 34 | hebergement______heb | Hebergement (chambres) | DB | R |   | L | 2 |
| 35 | personnel_go______go |  | DB |   |   | L | 1 |
| 131 | fichier_validation |  | DB |   |   | L | 1 |
| 281 | crew |  | DB |   |   | L | 1 |
| 364 | pms_footer_comment |  | DB |   |   | L | 1 |
| 599 | tempo_hebergement | Hebergement (chambres) | DB |   |   | L | 1 |
| 632 | tempo_selection | Table temporaire ecran | DB |   | **W** | L | 2 |
| 730 | arc_ez_card |  | DB |   |   | L | 1 |

### Colonnes par table (1 / 3 tables avec colonnes identifiees)

<details>
<summary>Table 31 - gm-complet_______gmc (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | > Date | R | Date |
| B | v.numero cabine | R | Alpha |

</details>

<details>
<summary>Table 34 - hebergement______heb (R/L) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 632 - tempo_selection (**W**/L) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Variables de session (1)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| B | v.numero cabine | Alpha | [41.2](#t4) |

### 11.2 Autres (1)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | > Date | Date | 1x refs |

## 12. EXPRESSIONS

**7 / 7 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| OTHER | 6 | 0 |
| CONDITION | 1 | 0 |

### 12.2 Expressions cles par type

#### OTHER (6 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 5 | `GetParam ('SOCIETE')` | - |
| OTHER | 6 | `[L]` | - |
| OTHER | 7 | `GetParam ('LANGUE')` | - |
| OTHER | 1 | `[E]` | - |
| OTHER | 2 | `[F]` | - |
| ... | | *+1 autres* | |

#### CONDITION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 4 | `Range (> Date [A],v.numero cabine [B],[C]) AND [AA]='O'` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Demande Edition GO (IDE 28)](PBP-IDE-28.md) -> **Recherche personnel Valider (IDE 41)**

Main -> ... -> [lanceur (IDE 101)](PBP-IDE-101.md) -> **Recherche personnel Valider (IDE 41)**

```mermaid
graph LR
    T41[41 Recherche personnel...]
    style T41 fill:#58a6ff
    CC101[101 lanceur]
    style CC101 fill:#8b5cf6
    CC28[28 Demande Edition GO]
    style CC28 fill:#8b5cf6
    CC28 --> T41
    CC101 --> T41
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [28](PBP-IDE-28.md) | Demande Edition GO | 4 |
| [101](PBP-IDE-101.md) | lanceur | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T41[41 Recherche personnel...]
    style T41 fill:#58a6ff
    NONE[Aucun callee]
    T41 -.-> NONE
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
| Lignes de logique | 123 | Programme compact |
| Expressions | 7 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 123) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Validation (1 tache: 0 ecran, 1 traitement)

- **Strategie** : FluentValidation avec validators specifiques.
- Chaque tache de validation -> un validator injectable

#### Traitement (1 tache: 0 ecran, 1 traitement)

- **Strategie** : 1 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

#### Consultation (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Composants de recherche/selection en modales.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| tempo_selection | Table WRITE (Database) | 1x | Schema + repository |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 08:52*
