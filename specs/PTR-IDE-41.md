# PTR IDE 41 - Recuperation du titre

> **Analyse**: Phases 1-4 2026-02-03 18:22 -> 18:23 (17s) | Assemblage 18:23
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PTR |
| IDE Position | 41 |
| Nom Programme | Recuperation du titre |
| Fichier source | `Prg_41.xml` |
| Dossier IDE | Utilitaires |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Recuperation du titre** assure la gestion complete de ce processus, accessible depuis [..Liste  Clients (ClipArt)+ (IDE 17)](PTR-IDE-17.md), [...Consultation Tempo Ecran Tt (IDE 21)](PTR-IDE-21.md), [Liste Vols Journee (IDE 29)](PTR-IDE-29.md), [Liste des Prestations Arrivant (IDE 30)](PTR-IDE-30.md), [Liste des Prestations Presents (IDE 31)](PTR-IDE-31.md), [...Consultation Tempo Ecran TK (IDE 23)](PTR-IDE-23.md), [...Consultation Erreurs (IDE 27)](PTR-IDE-27.md), [Stock Prestation (IDE 32)](PTR-IDE-32.md), [Liste des Passagers (IDE 34)](PTR-IDE-34.md), [Configuration Utilisateur (IDE 6)](PTR-IDE-6.md), [Gestion des Codes Vols (IDE 8)](PTR-IDE-8.md), [Trafic (IDE 9)](PTR-IDE-9.md), [Affichage Commentaire (IDE 12)](PTR-IDE-12.md), [Affichage Troncon du Dossier (IDE 13)](PTR-IDE-13.md), [Clients arrivants (IDE 14)](PTR-IDE-14.md), [Clients depart (IDE 15)](PTR-IDE-15.md), [Clients incompatibilites (IDE 16)](PTR-IDE-16.md), [...Consultation Syntèse (IDE 25)](PTR-IDE-25.md), [...Consultation Stock (IDE 33)](PTR-IDE-33.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>41 - Recuperation du titre

**Role** : Consultation/chargement : Recuperation du titre.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [..Liste  Clients (ClipArt)+ (IDE 17)](PTR-IDE-17.md), [...Consultation Tempo Ecran Tt (IDE 21)](PTR-IDE-21.md), [Liste Vols Journee (IDE 29)](PTR-IDE-29.md), [Liste des Prestations Arrivant (IDE 30)](PTR-IDE-30.md), [Liste des Prestations Presents (IDE 31)](PTR-IDE-31.md), [...Consultation Tempo Ecran TK (IDE 23)](PTR-IDE-23.md), [...Consultation Erreurs (IDE 27)](PTR-IDE-27.md), [Stock Prestation (IDE 32)](PTR-IDE-32.md), [Liste des Passagers (IDE 34)](PTR-IDE-34.md), [Configuration Utilisateur (IDE 6)](PTR-IDE-6.md), [Gestion des Codes Vols (IDE 8)](PTR-IDE-8.md), [Trafic (IDE 9)](PTR-IDE-9.md), [Affichage Commentaire (IDE 12)](PTR-IDE-12.md), [Affichage Troncon du Dossier (IDE 13)](PTR-IDE-13.md), [Clients arrivants (IDE 14)](PTR-IDE-14.md), [Clients depart (IDE 15)](PTR-IDE-15.md), [Clients incompatibilites (IDE 16)](PTR-IDE-16.md), [...Consultation Syntèse (IDE 25)](PTR-IDE-25.md), [...Consultation Stock (IDE 33)](PTR-IDE-33.md)
- **Appelle**: 0 programmes | **Tables**: 1 (W:0 R:1 L:0) | **Taches**: 1 | **Expressions**: 4

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **41.1** | [**Recuperation du titre** (41)](#t1) | MDI | - | Traitement |

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
| 719 | arc_transac_detail_bar |  | DB | R |   |   | 1 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 719 - arc_transac_detail_bar (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | > code ecran | R | Numeric |
| B | < nom ecran | R | Alpha |

</details>

## 11. VARIABLES

### 11.1 Autres (2)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | > code ecran | Numeric | 1x refs |
| B | < nom ecran | Alpha | - |

## 12. EXPRESSIONS

**4 / 4 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONCATENATION | 1 | 0 |
| CONSTANTE | 1 | 0 |
| OTHER | 1 | 0 |
| CONDITION | 1 | 0 |

### 12.2 Expressions cles par type

#### CONCATENATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 4 | `Trim ([F])&' - '&Trim ([G])` | - |

#### CONSTANTE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 3 | `'PT'` | - |

#### OTHER (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 1 | `GetParam ('CODELANGUE')` | - |

#### CONDITION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 2 | `> code ecran [A]` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [..Liste  Clients (ClipArt)+ (IDE 17)](PTR-IDE-17.md) -> **Recuperation du titre (IDE 41)**

Main -> ... -> [...Consultation Tempo Ecran Tt (IDE 21)](PTR-IDE-21.md) -> **Recuperation du titre (IDE 41)**

Main -> ... -> [Liste Vols Journee (IDE 29)](PTR-IDE-29.md) -> **Recuperation du titre (IDE 41)**

Main -> ... -> [Liste des Prestations Arrivant (IDE 30)](PTR-IDE-30.md) -> **Recuperation du titre (IDE 41)**

Main -> ... -> [Liste des Prestations Presents (IDE 31)](PTR-IDE-31.md) -> **Recuperation du titre (IDE 41)**

Main -> ... -> [...Consultation Tempo Ecran TK (IDE 23)](PTR-IDE-23.md) -> **Recuperation du titre (IDE 41)**

Main -> ... -> [...Consultation Erreurs (IDE 27)](PTR-IDE-27.md) -> **Recuperation du titre (IDE 41)**

Main -> ... -> [Stock Prestation (IDE 32)](PTR-IDE-32.md) -> **Recuperation du titre (IDE 41)**

Main -> ... -> [Liste des Passagers (IDE 34)](PTR-IDE-34.md) -> **Recuperation du titre (IDE 41)**

Main -> ... -> [Configuration Utilisateur (IDE 6)](PTR-IDE-6.md) -> **Recuperation du titre (IDE 41)**

Main -> ... -> [Gestion des Codes Vols (IDE 8)](PTR-IDE-8.md) -> **Recuperation du titre (IDE 41)**

Main -> ... -> [Trafic (IDE 9)](PTR-IDE-9.md) -> **Recuperation du titre (IDE 41)**

Main -> ... -> [Affichage Commentaire (IDE 12)](PTR-IDE-12.md) -> **Recuperation du titre (IDE 41)**

Main -> ... -> [Affichage Troncon du Dossier (IDE 13)](PTR-IDE-13.md) -> **Recuperation du titre (IDE 41)**

Main -> ... -> [Clients arrivants (IDE 14)](PTR-IDE-14.md) -> **Recuperation du titre (IDE 41)**

Main -> ... -> [Clients depart (IDE 15)](PTR-IDE-15.md) -> **Recuperation du titre (IDE 41)**

Main -> ... -> [Clients incompatibilites (IDE 16)](PTR-IDE-16.md) -> **Recuperation du titre (IDE 41)**

Main -> ... -> [...Consultation Syntèse (IDE 25)](PTR-IDE-25.md) -> **Recuperation du titre (IDE 41)**

Main -> ... -> [...Consultation Stock (IDE 33)](PTR-IDE-33.md) -> **Recuperation du titre (IDE 41)**

```mermaid
graph LR
    T41[41 Recuperation du titre]
    style T41 fill:#58a6ff
    CC14[14 Clients arrivants]
    style CC14 fill:#8b5cf6
    CC15[15 Clients depart]
    style CC15 fill:#8b5cf6
    CC16[16 Clients incompatibi...]
    style CC16 fill:#8b5cf6
    CC17[17 ..Liste Clients Cli...]
    style CC17 fill:#f59e0b
    CC20[20 ...Lance Consultati...]
    style CC20 fill:#f59e0b
    CC23[23 ...Consultation Tem...]
    style CC23 fill:#f59e0b
    CC21[21 ...Consultation Tem...]
    style CC21 fill:#f59e0b
    CC8[8 Gestion des Codes Vols]
    style CC8 fill:#3fb950
    CC6[6 Configuration Utilis...]
    style CC6 fill:#3fb950
    CC9[9 Trafic]
    style CC9 fill:#3fb950
    CC13[13 Affichage Troncon d...]
    style CC13 fill:#3fb950
    CC12[12 Affichage Commentaire]
    style CC12 fill:#3fb950
    CC21 --> CC6
    CC23 --> CC6
    CC21 --> CC8
    CC23 --> CC8
    CC21 --> CC9
    CC23 --> CC9
    CC21 --> CC12
    CC23 --> CC12
    CC21 --> CC13
    CC23 --> CC13
    CC20 --> CC21
    CC20 --> CC23
    CC17 --> CC20
    CC14 --> CC17
    CC15 --> CC17
    CC16 --> CC17
    CC6 --> T41
    CC8 --> T41
    CC9 --> T41
    CC12 --> T41
    CC13 --> T41
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [17](PTR-IDE-17.md) | ..Liste  Clients (ClipArt)+ | 7 |
| [21](PTR-IDE-21.md) | ...Consultation Tempo Ecran Tt | 3 |
| [29](PTR-IDE-29.md) | Liste Vols Journee | 3 |
| [30](PTR-IDE-30.md) | Liste des Prestations Arrivant | 3 |
| [31](PTR-IDE-31.md) | Liste des Prestations Presents | 3 |
| [23](PTR-IDE-23.md) | ...Consultation Tempo Ecran TK | 2 |
| [27](PTR-IDE-27.md) | ...Consultation Erreurs | 2 |
| [32](PTR-IDE-32.md) | Stock Prestation | 2 |
| [34](PTR-IDE-34.md) | Liste des Passagers | 2 |
| [6](PTR-IDE-6.md) | Configuration Utilisateur | 1 |
| [8](PTR-IDE-8.md) | Gestion des Codes Vols | 1 |
| [9](PTR-IDE-9.md) | Trafic | 1 |
| [12](PTR-IDE-12.md) | Affichage Commentaire | 1 |
| [13](PTR-IDE-13.md) | Affichage Troncon du Dossier | 1 |
| [14](PTR-IDE-14.md) | Clients arrivants | 1 |
| [15](PTR-IDE-15.md) | Clients depart | 1 |
| [16](PTR-IDE-16.md) | Clients incompatibilites | 1 |
| [25](PTR-IDE-25.md) | ...Consultation Syntèse | 1 |
| [33](PTR-IDE-33.md) | ...Consultation Stock | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T41[41 Recuperation du titre]
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
| Lignes de logique | 12 | Programme compact |
| Expressions | 4 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 12) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 0 ecran, 1 traitement)

- **Strategie** : 1 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 18:23*
