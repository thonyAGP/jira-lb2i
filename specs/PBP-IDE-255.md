# PBP IDE 255 - Liste des sejours

> **Analyse**: Phases 1-4 2026-02-03 16:00 -> 16:00 (10s) | Assemblage 16:00
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBP |
| IDE Position | 255 |
| Nom Programme | Liste des sejours |
| Fichier source | `Prg_255.xml` |
| Dossier IDE | Logement |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 4 |
| :warning: Statut | **ORPHELIN_POTENTIEL** |

## 2. DESCRIPTION FONCTIONNELLE

**Liste des sejours** assure la gestion complete de ce processus.

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>255 - Liste des sejours

**Role** : Traitement : Liste des sejours.
**Variables liees** : B (CodeListe)
**Delegue a** : [  Liste logement PASDL (IDE 258)](PBP-IDE-258.md), [Recup code zone/secteur (IDE 308)](PBP-IDE-308.md), [LZM -> Tempouserlist (IDE 316)](PBP-IDE-316.md)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: (aucun)
- **Appelle**: 4 programmes | **Tables**: 0 (W:0 R:0 L:0) | **Taches**: 1 | **Expressions**: 8

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **255.1** | [**Liste des sejours** (255)](#t1) | MDI | - | Traitement |

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

### 11.1 Autres (8)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | CodeEcran | Numeric | - |
| B | CodeListe | Alpha | - |
| C | Categorie | Alpha | - |
| D | NomTable | Alpha | - |
| E | CodeZoneSecteur | Alpha | 1x refs |
| F | CodeTri | Alpha | - |
| G | NbLogMini | Numeric | - |
| H | Titre edition | Alpha | - |

## 12. EXPRESSIONS

**8 / 8 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONSTANTE | 6 | 0 |
| CAST_LOGIQUE | 1 | 0 |
| CONCATENATION | 1 | 0 |

### 12.2 Expressions cles par type

#### CONSTANTE (6 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 4 | `'ELOGE'` | - |
| CONSTANTE | 5 | `'01'` | - |
| CONSTANTE | 6 | `0` | - |
| CONSTANTE | 1 | `47` | - |
| CONSTANTE | 2 | `'S'` | - |
| ... | | *+1 autres* | |

#### CAST_LOGIQUE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 7 | `'FALSE'LOG` | - |

#### CONCATENATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 8 | `MlsTrans ('Liste des sejours par')&' '&IF (CodeZoneSecteur [E]='Z','Zone',MlsTrans ('Secteur'))` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

**Chemin**: (pas de callers directs)

```mermaid
graph LR
    T255[255 Liste des sejours]
    style T255 fill:#58a6ff
    NONE[Aucun caller]
    NONE -.-> T255
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| - | (aucun) | - |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T255[255 Liste des sejours]
    style T255 fill:#58a6ff
    C258[258 Liste logement PASDL]
    T255 --> C258
    style C258 fill:#3fb950
    C280[280 RaZ 637 TempoUserList]
    T255 --> C280
    style C280 fill:#3fb950
    C308[308 Recup code zonesec...]
    T255 --> C308
    style C308 fill:#3fb950
    C316[316 LZM - Tempouserlist]
    T255 --> C316
    style C316 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [258](PBP-IDE-258.md) |   Liste logement PASDL | 1 | Configuration impression |
| [280](PBP-IDE-280.md) | RaZ 637 TempoUserList | 1 | Reinitialisation |
| [308](PBP-IDE-308.md) | Recup code zone/secteur | 1 | Recuperation donnees |
| [316](PBP-IDE-316.md) | LZM -> Tempouserlist | 1 | Configuration impression |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 20 | Programme compact |
| Expressions | 8 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 4 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 20) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 0 ecran, 1 traitement)

- **Strategie** : 1 service(s) backend injectable(s) (Domain Services).
- 4 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| [Recup code zone/secteur (IDE 308)](PBP-IDE-308.md) | Sous-programme | 1x | Normale - Recuperation donnees |
| [LZM -> Tempouserlist (IDE 316)](PBP-IDE-316.md) | Sous-programme | 1x | Normale - Configuration impression |
| [  Liste logement PASDL (IDE 258)](PBP-IDE-258.md) | Sous-programme | 1x | Normale - Configuration impression |
| [RaZ 637 TempoUserList (IDE 280)](PBP-IDE-280.md) | Sous-programme | 1x | Normale - Reinitialisation |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 16:00*
