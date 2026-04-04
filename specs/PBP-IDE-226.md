# PBP IDE 226 - Liste des presents personnel

> **Analyse**: Phases 1-4 2026-02-03 15:55 -> 15:55 (12s) | Assemblage 15:55
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBP |
| IDE Position | 226 |
| Nom Programme | Liste des presents personnel |
| Fichier source | `Prg_226.xml` |
| Dossier IDE | Liste |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 8 |
| :warning: Statut | **ORPHELIN_POTENTIEL** |

## 2. DESCRIPTION FONCTIONNELLE

**Liste des presents personnel** assure la gestion complete de ce processus.

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>226 - Liste des presents personnel

**Role** : Traitement : Liste des presents personnel.
**Variables liees** : B (CodeListe), C (TypeListe)
**Delegue a** : [  Liste present personnel plan (IDE 227)](PBP-IDE-227.md), [Qua -> Tempo userlist (IDE 306)](PBP-IDE-306.md)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: (aucun)
- **Appelle**: 8 programmes | **Tables**: 0 (W:0 R:0 L:0) | **Taches**: 1 | **Expressions**: 9

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **226.1** | [**Liste des presents personnel** (226)](#t1) | MDI | - | Traitement |

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
| G | v.NomFicExcel | Alpha | - |

### 11.2 Autres (6)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | CodeEcran | Numeric | - |
| B | CodeListe | Alpha | - |
| C | TypeListe | Alpha | - |
| D | CodeSelect | Alpha | - |
| E | Categorie | Alpha | - |
| F | NomTable | Alpha | - |

## 12. EXPRESSIONS

**9 / 9 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONSTANTE | 7 | 0 |
| OTHER | 2 | 0 |

### 12.2 Expressions cles par type

#### CONSTANTE (7 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 5 | `''` | - |
| CONSTANTE | 6 | `'TQUGO'` | - |
| CONSTANTE | 9 | `'LISTE_DES_PRESENTS'` | - |
| CONSTANTE | 4 | `'P'` | - |
| CONSTANTE | 1 | `62` | - |
| ... | | *+2 autres* | |

#### OTHER (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 8 | `SetCrsr (1)` | - |
| OTHER | 7 | `SetCrsr (2)` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

**Chemin**: (pas de callers directs)

```mermaid
graph LR
    T226[226 Liste des presents...]
    style T226 fill:#58a6ff
    NONE[Aucun caller]
    NONE -.-> T226
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| - | (aucun) | - |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T226[226 Liste des presents...]
    style T226 fill:#58a6ff
    C227[227 Liste present pers...]
    T226 --> C227
    style C227 fill:#3fb950
    C284[284 RaZ Tempo synthese]
    T226 --> C284
    style C284 fill:#3fb950
    C286[286 RaZ 634 tempo synt...]
    T226 --> C286
    style C286 fill:#3fb950
    C287[287 RaZ 619 tempo list...]
    T226 --> C287
    style C287 fill:#3fb950
    C288[288 RaZ 609 tempo bateau]
    T226 --> C288
    style C288 fill:#3fb950
    C289[289 RaZ 610 tempo depart]
    T226 --> C289
    style C289 fill:#3fb950
    C300[300 RaZ 598 tempo comp...]
    T226 --> C300
    style C300 fill:#3fb950
    C306[306 Qua - Tempo userlist]
    T226 --> C306
    style C306 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [227](PBP-IDE-227.md) |   Liste present personnel plan | 1 | Configuration impression |
| [284](PBP-IDE-284.md) | RaZ Tempo synthese | 1 | Reinitialisation |
| [286](PBP-IDE-286.md) | RaZ  634 tempo synthese | 1 | Reinitialisation |
| [287](PBP-IDE-287.md) | RaZ 619 tempo liste ecran | 1 | Reinitialisation |
| [288](PBP-IDE-288.md) | RaZ 609 tempo bateau | 1 | Reinitialisation |
| [289](PBP-IDE-289.md) | RaZ 610 tempo depart | 1 | Reinitialisation |
| [300](PBP-IDE-300.md) | RaZ 598 tempo comptage eff | 1 | Reinitialisation |
| [306](PBP-IDE-306.md) | Qua -> Tempo userlist | 1 | Configuration impression |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 27 | Programme compact |
| Expressions | 9 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 8 | Dependances moderees |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 27) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 0 ecran, 1 traitement)

- **Strategie** : 1 service(s) backend injectable(s) (Domain Services).
- 8 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| [RaZ 610 tempo depart (IDE 289)](PBP-IDE-289.md) | Sous-programme | 1x | Normale - Reinitialisation |
| [RaZ 609 tempo bateau (IDE 288)](PBP-IDE-288.md) | Sous-programme | 1x | Normale - Reinitialisation |
| [Qua -> Tempo userlist (IDE 306)](PBP-IDE-306.md) | Sous-programme | 1x | Normale - Configuration impression |
| [RaZ 598 tempo comptage eff (IDE 300)](PBP-IDE-300.md) | Sous-programme | 1x | Normale - Reinitialisation |
| [RaZ Tempo synthese (IDE 284)](PBP-IDE-284.md) | Sous-programme | 1x | Normale - Reinitialisation |
| [  Liste present personnel plan (IDE 227)](PBP-IDE-227.md) | Sous-programme | 1x | Normale - Configuration impression |
| [RaZ 619 tempo liste ecran (IDE 287)](PBP-IDE-287.md) | Sous-programme | 1x | Normale - Reinitialisation |
| [RaZ  634 tempo synthese (IDE 286)](PBP-IDE-286.md) | Sous-programme | 1x | Normale - Reinitialisation |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 15:55*
