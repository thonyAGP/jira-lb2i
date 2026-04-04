# PTR IDE 18 - ...Creation Tempo Ecran Toutes

> **Analyse**: Phases 1-4 2026-02-03 18:14 -> 18:14 (15s) | Assemblage 18:14
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PTR |
| IDE Position | 18 |
| Nom Programme | ...Creation Tempo Ecran Toutes |
| Fichier source | `Prg_18.xml` |
| Dossier IDE | Listes |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**...Creation Tempo Ecran Toutes** assure la gestion complete de ce processus, accessible depuis [..Liste  Clients (ClipArt)+ (IDE 17)](PTR-IDE-17.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Creation** (1 tache) : insertion d'enregistrements en base (mouvements, prestations)

**Donnees modifiees** : 1 tables en ecriture (classe_monetaire_reference).

## 3. BLOCS FONCTIONNELS

### 3.1 Creation (1 tache)

Insertion de nouveaux enregistrements en base.

---

#### <a id="t1"></a>18 - ...Creation Tempo Ecran

**Role** : Creation d'enregistrement : ...Creation Tempo Ecran.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [..Liste  Clients (ClipArt)+ (IDE 17)](PTR-IDE-17.md)
- **Appelle**: 0 programmes | **Tables**: 1 (W:1 R:0 L:0) | **Taches**: 1 | **Expressions**: 30

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **18.1** | [**...Creation Tempo Ecran** (18)](#t1) | MDI | - | Creation |

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
| 681 | classe_monetaire_reference |  | DB |   | **W** |   | 1 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 681 - classe_monetaire_reference (**W**) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P0-Societe | W | Alpha |
| B | P0-Nom | W | Alpha |
| C | P0-Prenom | W | Alpha |
| D | P0-Sexe | W | Alpha |
| E | P0-Qualite | W | Alpha |
| F | P0-Age | W | Numeric |
| G | P0-Logement | W | Alpha |
| H | P0-Pays | W | Alpha |
| I | P0-Date Arrivee | W | Date |
| J | P0-Time Arrivee | W | Time |
| K | P0-Code Vol Arrivee | W | Alpha |
| L | P0-Code Compagnie Arrivée | W | Alpha |
| M | P0-Ville Arrivee | W | Alpha |
| N | P0-Date Depart | W | Date |
| O | P0-Time Depart | W | Time |
| P | P0-Code Vol Départ | W | Alpha |
| Q | P0-Code Compagnie Départ | W | Alpha |
| R | P0-Ville Départ | W | Alpha |
| S | P0-Bebe | W | Alpha |
| T | P0-Millesia | W | Alpha |
| U | P0-Liste Blanche | W | Alpha |
| V | P0-Retour Circuit | W | Alpha |
| W | P0-Compte | W | Numeric |
| X | P0-Filiation | W | Numeric |
| Y | P0-DateDebHeb | W | Date |
| Z | P0-TimeDebHeb | W | Alpha |
| BA | P0-DateFinHeb | W | Date |
| BB | P0-TimeFinHeb | W | Alpha |
| BC | P0-Telephone | W | Alpha |

</details>

## 11. VARIABLES

### 11.1 Autres (29)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P0-Societe | Alpha | 1x refs |
| B | P0-Nom | Alpha | 1x refs |
| C | P0-Prenom | Alpha | 1x refs |
| D | P0-Sexe | Alpha | 1x refs |
| E | P0-Qualite | Alpha | 1x refs |
| F | P0-Age | Numeric | 1x refs |
| G | P0-Logement | Alpha | 1x refs |
| H | P0-Pays | Alpha | 1x refs |
| I | P0-Date Arrivee | Date | 1x refs |
| J | P0-Time Arrivee | Time | 1x refs |
| K | P0-Code Vol Arrivee | Alpha | 1x refs |
| L | P0-Code Compagnie Arrivée | Alpha | 1x refs |
| M | P0-Ville Arrivee | Alpha | 1x refs |
| N | P0-Date Depart | Date | 1x refs |
| O | P0-Time Depart | Time | 1x refs |
| P | P0-Code Vol Départ | Alpha | 1x refs |
| Q | P0-Code Compagnie Départ | Alpha | 1x refs |
| R | P0-Ville Départ | Alpha | 1x refs |
| S | P0-Bebe | Alpha | 1x refs |
| T | P0-Millesia | Alpha | 1x refs |
| U | P0-Liste Blanche | Alpha | 1x refs |
| V | P0-Retour Circuit | Alpha | 1x refs |
| W | P0-Compte | Numeric | 1x refs |
| X | P0-Filiation | Numeric | 1x refs |
| Y | P0-DateDebHeb | Date | 1x refs |
| Z | P0-TimeDebHeb | Alpha | 1x refs |
| BA | P0-DateFinHeb | Date | - |
| BB | P0-TimeFinHeb | Alpha | - |
| BC | P0-Telephone | Alpha | - |

<details>
<summary>Toutes les 29 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| Autre | **A** | P0-Societe | Alpha |
| Autre | **B** | P0-Nom | Alpha |
| Autre | **C** | P0-Prenom | Alpha |
| Autre | **D** | P0-Sexe | Alpha |
| Autre | **E** | P0-Qualite | Alpha |
| Autre | **F** | P0-Age | Numeric |
| Autre | **G** | P0-Logement | Alpha |
| Autre | **H** | P0-Pays | Alpha |
| Autre | **I** | P0-Date Arrivee | Date |
| Autre | **J** | P0-Time Arrivee | Time |
| Autre | **K** | P0-Code Vol Arrivee | Alpha |
| Autre | **L** | P0-Code Compagnie Arrivée | Alpha |
| Autre | **M** | P0-Ville Arrivee | Alpha |
| Autre | **N** | P0-Date Depart | Date |
| Autre | **O** | P0-Time Depart | Time |
| Autre | **P** | P0-Code Vol Départ | Alpha |
| Autre | **Q** | P0-Code Compagnie Départ | Alpha |
| Autre | **R** | P0-Ville Départ | Alpha |
| Autre | **S** | P0-Bebe | Alpha |
| Autre | **T** | P0-Millesia | Alpha |
| Autre | **U** | P0-Liste Blanche | Alpha |
| Autre | **V** | P0-Retour Circuit | Alpha |
| Autre | **W** | P0-Compte | Numeric |
| Autre | **X** | P0-Filiation | Numeric |
| Autre | **Y** | P0-DateDebHeb | Date |
| Autre | **Z** | P0-TimeDebHeb | Alpha |
| Autre | **BA** | P0-DateFinHeb | Date |
| Autre | **BB** | P0-TimeFinHeb | Alpha |
| Autre | **BC** | P0-Telephone | Alpha |

</details>

## 12. EXPRESSIONS

**30 / 30 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| OTHER | 29 | 0 |
| REFERENCE_VG | 1 | 0 |

### 12.2 Expressions cles par type

#### OTHER (29 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 21 | `P0-Ville Départ [R]` | - |
| OTHER | 22 | `P0-Bebe [S]` | - |
| OTHER | 23 | `P0-Millesia [T]` | - |
| OTHER | 20 | `P0-Code Compagnie Départ [Q]` | - |
| OTHER | 17 | `P0-Time Depart [O]` | - |
| ... | | *+24 autres* | |

#### REFERENCE_VG (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 2 | `VG2` | - |

### 12.3 Toutes les expressions (30)

<details>
<summary>Voir les 30 expressions</summary>

#### OTHER (29)

| IDE | Expression Decodee |
|-----|-------------------|
| 1 | `P0-Societe [A]` |
| 3 | `P0-Nom [B]` |
| 4 | `P0-Prenom [C]` |
| 5 | `P0-Sexe [D]` |
| 6 | `P0-Qualite [E]` |
| 7 | `P0-Age [F]` |
| 8 | `P0-Logement [G]` |
| 9 | `P0-Pays [H]` |
| 10 | `P0-Date Arrivee [I]` |
| 11 | `P0-Time Arrivee [J]` |
| 12 | `P0-Code Vol Arrivee [K]` |
| 13 | `[DG]` |
| 14 | `P0-Code Compagnie Arrivée [L]` |
| 15 | `P0-Ville Arrivee [M]` |
| 16 | `P0-Date Depart [N]` |
| 17 | `P0-Time Depart [O]` |
| 18 | `[DH]` |
| 19 | `P0-Code Vol Départ [P]` |
| 20 | `P0-Code Compagnie Départ [Q]` |
| 21 | `P0-Ville Départ [R]` |
| 22 | `P0-Bebe [S]` |
| 23 | `P0-Millesia [T]` |
| 24 | `P0-Liste Blanche [U]` |
| 25 | `P0-Retour Circuit [V]` |
| 26 | `P0-Compte [W]` |
| 27 | `P0-Filiation [X]` |
| 28 | `P0-DateDebHeb [Y]` |
| 29 | `P0-TimeDebHeb [Z]` |
| 30 | `[AA]` |

#### REFERENCE_VG (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 2 | `VG2` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [..Liste  Clients (ClipArt)+ (IDE 17)](PTR-IDE-17.md) -> **...Creation Tempo Ecran Toutes (IDE 18)**

```mermaid
graph LR
    T18[18 ...Creation Tempo E...]
    style T18 fill:#58a6ff
    CC15[15 Clients depart]
    style CC15 fill:#8b5cf6
    CC16[16 Clients incompatibi...]
    style CC16 fill:#8b5cf6
    CC14[14 Clients arrivants]
    style CC14 fill:#8b5cf6
    CC17[17 ..Liste Clients Cli...]
    style CC17 fill:#3fb950
    CC14 --> CC17
    CC15 --> CC17
    CC16 --> CC17
    CC17 --> T18
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [17](PTR-IDE-17.md) | ..Liste  Clients (ClipArt)+ | 16 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T18[18 ...Creation Tempo E...]
    style T18 fill:#58a6ff
    NONE[Aucun callee]
    T18 -.-> NONE
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
| Lignes de logique | 64 | Programme compact |
| Expressions | 30 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 64) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Creation (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Repository pattern avec Entity Framework Core.
- Insertion via `IRepository<T>.CreateAsync()`

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| classe_monetaire_reference | Table WRITE (Database) | 1x | Schema + repository |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 18:14*
