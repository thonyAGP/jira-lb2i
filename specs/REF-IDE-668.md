# REF IDE 668 - Lance saisie TPE

> **Analyse**: Phases 1-4 2026-02-03 13:32 -> 13:32 (15s) | Assemblage 13:32
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | REF |
| IDE Position | 668 |
| Nom Programme | Lance saisie TPE |
| Fichier source | `Prg_668.xml` |
| Dossier IDE | General |
| Taches | 3 (0 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 2 |

## 2. DESCRIPTION FONCTIONNELLE

**Lance saisie TPE** assure la gestion complete de ce processus, accessible depuis [lance tpe (IDE 660)](REF-IDE-660.md), [TEST TPE et REGUL (IDE 672)](REF-IDE-672.md).

Le flux de traitement s'organise en **2 blocs fonctionnels** :

- **Traitement** (2 taches) : traitements metier divers
- **Saisie** (1 tache) : ecrans de saisie utilisateur (formulaires, champs, donnees)

**Donnees modifiees** : 1 tables en ecriture (tickets_tpe).

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Saisie (1 tache)

- **668** - Lance saisie TPE **[[ECRAN]](#ecran-t1)**

Delegue a : [Saisie des tickets TPE (IDE 670)](REF-IDE-670.md), [Saisie tickets TPE Interfacés (IDE 671)](REF-IDE-671.md)

#### Phase 2 : Traitement (2 taches)

- **668.1** - Sauvegarde des données
- **668.2** - Test Interfaces

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| tickets_tpe | **W** (1 usages) |  |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Saisie (1 tache)

L'operateur saisit les donnees de la transaction via 1 ecran (Lance saisie TPE).

---

#### <a id="t1"></a>668 - Lance saisie TPE [[ECRAN]](#ecran-t1)

**Role** : Saisie des donnees : Lance saisie TPE.
**Ecran** : 413 x 275 DLU (MDI) | [Voir mockup](#ecran-t1)
**Delegue a** : [Saisie des tickets TPE (IDE 670)](REF-IDE-670.md), [Saisie tickets TPE Interfacés (IDE 671)](REF-IDE-671.md)


### 3.2 Traitement (2 taches)

Traitements internes.

---

#### <a id="t2"></a>668.1 - Sauvegarde des données

**Role** : Traitement : Sauvegarde des données.

---

#### <a id="t3"></a>668.2 - Test Interfaces

**Role** : Verification : Test Interfaces.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [lance tpe (IDE 660)](REF-IDE-660.md), [TEST TPE et REGUL (IDE 672)](REF-IDE-672.md)
- **Appelle**: 2 programmes | **Tables**: 2 (W:1 R:0 L:1) | **Taches**: 3 | **Expressions**: 9

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (3 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **668.1** | [**Lance saisie TPE** (668)](#t1) [mockup](#ecran-t1) | MDI | 413x275 | Saisie |
| **668.2** | [**Sauvegarde des données** (668.1)](#t2) | - | - | Traitement |
| 668.2.1 | [Test Interfaces (668.2)](#t3) | - | - | |

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
| 260 | tickets_tpe |  | DB |   | **W** |   | 1 |
| 538 | tickets_tpe |  | TMP |   |   | L | 1 |

### Colonnes par table (0 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 260 - tickets_tpe (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (10)

Variables recues du programme appelant ([lance tpe (IDE 660)](REF-IDE-660.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P.Param societe | Alpha | - |
| B | P.Date comptable | Date | - |
| C | P.Param masque | Alpha | - |
| D | P.Ecart TPE corrige | Logical | 2x parametre entrant |
| E | P.Appel PVE | Logical | 3x parametre entrant |
| F | P.Cloture auto | Logical | - |
| G | P.Activite de la boutique | Numeric | - |
| H | P.Est un terminal boutique | Logical | - |
| I | P.VG.TPE ACTIF | Logical | 3x parametre entrant |
| J | P.Service | Alpha | - |

### 11.2 Variables de session (2)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| L | v.abandon demandé | Logical | 2x session |
| M | v.Existe TPE Interfacé | Logical | - |

### 11.3 Autres (1)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| K | DATE COMPTABLE DEMANDEE | Date | - |

## 12. EXPRESSIONS

**9 / 9 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| OTHER | 5 | 0 |
| CAST_LOGIQUE | 2 | 0 |
| NEGATION | 2 | 0 |

### 12.2 Expressions cles par type

#### OTHER (5 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 7 | `P.Est un terminal bout... [H]` | - |
| OTHER | 8 | `NOT(v.abandon demandé [L])` | - |
| OTHER | 4 | `P.Ecart TPE corrige [D] OR v.abandon demandé [L]` | - |
| OTHER | 1 | `P.VG.TPE ACTIF [I] AND P.Appel PVE [E]` | - |
| OTHER | 2 | `NOT(P.VG.TPE ACTIF [I]) OR (P.VG.TPE ACTIF [I] AND P.Appel PVE [E] AND NOT([P]))` | - |

#### CAST_LOGIQUE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 9 | `'FALSE'LOG` | - |
| CAST_LOGIQUE | 3 | `P.VG.TPE ACTIF [I] AND IF(P.Appel PVE [E],[P],'TRUE'LOG)` | - |

#### NEGATION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| NEGATION | 6 | `NOT P.Est un terminal bout... [H]` | - |
| NEGATION | 5 | `NOT (P.Ecart TPE corrige [D])` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [lance tpe (IDE 660)](REF-IDE-660.md) -> **Lance saisie TPE (IDE 668)**

Main -> ... -> [TEST TPE et REGUL (IDE 672)](REF-IDE-672.md) -> **Lance saisie TPE (IDE 668)**

```mermaid
graph LR
    T668[668 Lance saisie TPE]
    style T668 fill:#58a6ff
    CC672[672 TEST TPE et REGUL]
    style CC672 fill:#8b5cf6
    CC660[660 lance tpe]
    style CC660 fill:#8b5cf6
    CC660 --> T668
    CC672 --> T668
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [660](REF-IDE-660.md) | lance tpe | 1 |
| [672](REF-IDE-672.md) | TEST TPE et REGUL | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T668[668 Lance saisie TPE]
    style T668 fill:#58a6ff
    C670[670 Saisie des tickets...]
    T668 --> C670
    style C670 fill:#3fb950
    C671[671 Saisie tickets TPE...]
    T668 --> C671
    style C671 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [670](REF-IDE-670.md) | Saisie des tickets TPE | 1 | Impression ticket/document |
| [671](REF-IDE-671.md) | Saisie tickets TPE Interfacés | 1 | Impression ticket/document |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 83 | Programme compact |
| Expressions | 9 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 2 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 83) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Saisie (1 tache: 1 ecran, 0 traitement)

- **Strategie** : Formulaire React/Blazor avec validation Zod/FluentValidation.
- Reproduire 1 ecran : Lance saisie TPE
- Validation temps reel cote client + serveur

#### Traitement (2 taches: 0 ecran, 2 traitements)

- **Strategie** : 2 service(s) backend injectable(s) (Domain Services).
- 2 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| tickets_tpe | Table WRITE (Database) | 1x | Schema + repository |
| [Saisie tickets TPE Interfacés (IDE 671)](REF-IDE-671.md) | Sous-programme | 1x | Normale - Impression ticket/document |
| [Saisie des tickets TPE (IDE 670)](REF-IDE-670.md) | Sous-programme | 1x | Normale - Impression ticket/document |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 13:32*
