# ADH IDE 33 - Delete histo_Fus_Sep_Saisie

> **Analyse**: Phases 1-4 2026-02-07 03:42 -> 01:28 (21h45min) | Assemblage 01:28
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | ADH |
| IDE Position | 33 |
| Nom Programme | Delete histo_Fus_Sep_Saisie |
| Fichier source | `Prg_33.xml` |
| Dossier IDE | General |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 0 |
| Complexite | **BASSE** (score 7/100) |

## 2. DESCRIPTION FONCTIONNELLE

Ce programme gère la suppression des enregistrements historiques de saisie lors des opérations de fusion/séparation de comptes. Il intervient dans le flux de gestion des comptes (IDE 28 - Fusion) et nettoie la table `histo_fusionseparation_saisie` après traitement des données de fusion.

Le programme effectue une suppression simple mais critique : il purge tous les enregistrements historiques relatifs à une opération de fusion/séparation identifiée. Cette opération s'inscrit dans un processus de maintenance des données, permettant de récupérer l'espace disque et de maintenir l'intégrité historique après que les données pertinentes ont été traitées et archivées ailleurs.

L'absence de paramètres visibles suggère une suppression basée sur des critères implicites (probablement une clé de session ou d'opération passée en contexte global). Le programme est généralement appelé en fin de flux, une fois que les étapes de validation et de fusion sont complétées, assurant qu'aucune donnée critique n'est supprimée avant son traitement.

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>33 - (sans nom)

**Role** : Traitement interne.


## 5. REGLES METIER

*(Aucune regle metier identifiee dans les expressions)*

## 6. CONTEXTE

- **Appele par**: [Fusion (IDE 28)](ADH-IDE-28.md)
- **Appelle**: 0 programmes | **Tables**: 1 (W:1 R:0 L:0) | **Taches**: 1 | **Expressions**: 6

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **33.1** | [**(sans nom)** (33)](#t1) | MDI | - | Traitement |

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
| 343 | histo_fusionseparation_saisie | Historique / journal | DB |   | **W** |   | 1 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 343 - histo_fusionseparation_saisie (**W**) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | i chrono E/F | W | Numeric |
| B | i societe | W | Alpha |
| C | i compte reference | W | Numeric |
| D | i filiation reference | W | Numeric |
| E | i compte pointe old | W | Numeric |
| F | i filiation pointe old | W | Numeric |

</details>

## 11. VARIABLES

### 11.1 Autres (6)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| EN | i chrono E/F | Numeric | 1x refs |
| EO | i societe | Alpha | 1x refs |
| EP | i compte reference | Numeric | 1x refs |
| EQ | i filiation reference | Numeric | 1x refs |
| ER | i compte pointe old | Numeric | 1x refs |
| ES | i filiation pointe old | Numeric | 1x refs |

## 12. EXPRESSIONS

**6 / 6 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| OTHER | 6 | 0 |

### 12.2 Expressions cles par type

#### OTHER (6 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 4 | `i filiation reference [D]` | - |
| OTHER | 5 | `i compte pointe old [E]` | - |
| OTHER | 6 | `i filiation pointe old [F]` | - |
| OTHER | 1 | `i chrono E/F [A]` | - |
| OTHER | 2 | `i societe [B]` | - |
| ... | | *+1 autres* | |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Fusion (IDE 28)](ADH-IDE-28.md) -> **Delete histo_Fus_Sep_Saisie (IDE 33)**

```mermaid
graph LR
    T33[33 Delete histo_Fus_Se...]
    style T33 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC163[163 Menu caisse GM - s...]
    style CC163 fill:#f59e0b
    CC37[37 Menu changement compte]
    style CC37 fill:#f59e0b
    CC28[28 Fusion]
    style CC28 fill:#3fb950
    CC37 --> CC28
    CC163 --> CC37
    CC1 --> CC163
    CC28 --> T33
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [28](ADH-IDE-28.md) | Fusion | 2 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T33[33 Delete histo_Fus_Se...]
    style T33 fill:#58a6ff
    NONE[Aucun callee]
    T33 -.-> NONE
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
| Expressions | 6 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 14) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 0 ecran, 1 traitement)

- **Strategie** : 1 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| histo_fusionseparation_saisie | Table WRITE (Database) | 1x | Schema + repository |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-08 01:28*
