# EXB IDE 16 - Recuperation du titre

> **Analyse**: Phases 1-4 2026-02-03 10:36 -> 10:36 (21s) | Assemblage 10:36
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | EXB |
| IDE Position | 16 |
| Nom Programme | Recuperation du titre |
| Fichier source | `Prg_16.xml` |
| Domaine metier | General |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Recuperation du titre** assure la gestion complete de ce processus, accessible depuis [Ventes_Excursions (IDE 40)](EXB-IDE-40.md), [Definition Plannings (IDE 15)](EXB-IDE-15.md), [ Annulation Ventes@ (IDE 6)](EXB-IDE-6.md), [Definition Annexes (IDE 14)](EXB-IDE-14.md), [Definition Excursions (IDE 13)](EXB-IDE-13.md), [Liste ventes/N°vente (IDE 20)](EXB-IDE-20.md), [Liste Participant (IDE 23)](EXB-IDE-23.md), [Detail Excursion (IDE 26)](EXB-IDE-26.md), [Menu clôture (IDE 8)](EXB-IDE-8.md), [Edition des excursions (IDE 22)](EXB-IDE-22.md), [ Menu fin de saison (IDE 28)](EXB-IDE-28.md), [Menu general (IDE 31)](EXB-IDE-31.md), [Purge (IDE 34)](EXB-IDE-34.md), [  Participants general (IDE 42)](EXB-IDE-42.md), [  Participants date (IDE 43)](EXB-IDE-43.md), [Zoom article (IDE 46)](EXB-IDE-46.md), [Zoom modes de paiement (IDE 47)](EXB-IDE-47.md), [Zoom Adherents Paiement (IDE 48)](EXB-IDE-48.md), [Zoom Adherents VSP (IDE 49)](EXB-IDE-49.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>16 - Recuperation du titre

**Role** : Consultation/chargement : Recuperation du titre.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Ventes_Excursions (IDE 40)](EXB-IDE-40.md), [Definition Plannings (IDE 15)](EXB-IDE-15.md), [ Annulation Ventes@ (IDE 6)](EXB-IDE-6.md), [Definition Annexes (IDE 14)](EXB-IDE-14.md), [Definition Excursions (IDE 13)](EXB-IDE-13.md), [Liste ventes/N°vente (IDE 20)](EXB-IDE-20.md), [Liste Participant (IDE 23)](EXB-IDE-23.md), [Detail Excursion (IDE 26)](EXB-IDE-26.md), [Menu clôture (IDE 8)](EXB-IDE-8.md), [Edition des excursions (IDE 22)](EXB-IDE-22.md), [ Menu fin de saison (IDE 28)](EXB-IDE-28.md), [Menu general (IDE 31)](EXB-IDE-31.md), [Purge (IDE 34)](EXB-IDE-34.md), [  Participants general (IDE 42)](EXB-IDE-42.md), [  Participants date (IDE 43)](EXB-IDE-43.md), [Zoom article (IDE 46)](EXB-IDE-46.md), [Zoom modes de paiement (IDE 47)](EXB-IDE-47.md), [Zoom Adherents Paiement (IDE 48)](EXB-IDE-48.md), [Zoom Adherents VSP (IDE 49)](EXB-IDE-49.md)
- **Appelle**: 0 programmes | **Tables**: 1 (W:0 R:1 L:0) | **Taches**: 1 | **Expressions**: 4

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **16.1** | [**Recuperation du titre** (16)](#t1) | MDI | - | Traitement |

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
| 721 | arc_bl_detail |  | DB | R |   |   | 1 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 721 - arc_bl_detail (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | > code ecran | R | Numeric |
| B | < nom ecran | R | Alpha |
| C | code langue | R | Alpha |

</details>

## 11. VARIABLES

### 11.1 Autres (3)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | > code ecran | Numeric | 1x refs |
| B | < nom ecran | Alpha | - |
| C | code langue | Alpha | - |

## 12. EXPRESSIONS

**4 / 4 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONCATENATION | 1 | 0 |
| CONSTANTE | 1 | 0 |
| CONDITION | 1 | 0 |
| OTHER | 1 | 0 |

### 12.2 Expressions cles par type

#### CONCATENATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 3 | `Trim ([G])&' - '&Trim ([H])` | - |

#### CONSTANTE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 2 | `'EM'` | - |

#### CONDITION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 1 | `> code ecran [A]` | - |

#### OTHER (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 4 | `GetParam ('CODELANGUE')` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Ventes_Excursions (IDE 40)](EXB-IDE-40.md) -> **Recuperation du titre (IDE 16)**

Main -> ... -> [Definition Plannings (IDE 15)](EXB-IDE-15.md) -> **Recuperation du titre (IDE 16)**

Main -> ... -> [ Annulation Ventes@ (IDE 6)](EXB-IDE-6.md) -> **Recuperation du titre (IDE 16)**

Main -> ... -> [Definition Annexes (IDE 14)](EXB-IDE-14.md) -> **Recuperation du titre (IDE 16)**

Main -> ... -> [Definition Excursions (IDE 13)](EXB-IDE-13.md) -> **Recuperation du titre (IDE 16)**

Main -> ... -> [Liste ventes/N°vente (IDE 20)](EXB-IDE-20.md) -> **Recuperation du titre (IDE 16)**

Main -> ... -> [Liste Participant (IDE 23)](EXB-IDE-23.md) -> **Recuperation du titre (IDE 16)**

Main -> ... -> [Detail Excursion (IDE 26)](EXB-IDE-26.md) -> **Recuperation du titre (IDE 16)**

Main -> ... -> [Menu clôture (IDE 8)](EXB-IDE-8.md) -> **Recuperation du titre (IDE 16)**

Main -> ... -> [Edition des excursions (IDE 22)](EXB-IDE-22.md) -> **Recuperation du titre (IDE 16)**

Main -> ... -> [ Menu fin de saison (IDE 28)](EXB-IDE-28.md) -> **Recuperation du titre (IDE 16)**

Main -> ... -> [Menu general (IDE 31)](EXB-IDE-31.md) -> **Recuperation du titre (IDE 16)**

Main -> ... -> [Purge (IDE 34)](EXB-IDE-34.md) -> **Recuperation du titre (IDE 16)**

Main -> ... -> [  Participants general (IDE 42)](EXB-IDE-42.md) -> **Recuperation du titre (IDE 16)**

Main -> ... -> [  Participants date (IDE 43)](EXB-IDE-43.md) -> **Recuperation du titre (IDE 16)**

Main -> ... -> [Zoom article (IDE 46)](EXB-IDE-46.md) -> **Recuperation du titre (IDE 16)**

Main -> ... -> [Zoom modes de paiement (IDE 47)](EXB-IDE-47.md) -> **Recuperation du titre (IDE 16)**

Main -> ... -> [Zoom Adherents Paiement (IDE 48)](EXB-IDE-48.md) -> **Recuperation du titre (IDE 16)**

Main -> ... -> [Zoom Adherents VSP (IDE 49)](EXB-IDE-49.md) -> **Recuperation du titre (IDE 16)**

```mermaid
graph LR
    T16[16 Recuperation du titre]
    style T16 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC31[31 Menu general]
    style CC31 fill:#f59e0b
    CC15[15 Definition Plannings]
    style CC15 fill:#3fb950
    CC6[6 Annulation Ventes@]
    style CC6 fill:#3fb950
    CC8[8 Menu clôture]
    style CC8 fill:#3fb950
    CC13[13 Definition Excursions]
    style CC13 fill:#3fb950
    CC14[14 Definition Annexes]
    style CC14 fill:#3fb950
    CC31 --> CC6
    CC31 --> CC8
    CC31 --> CC13
    CC31 --> CC14
    CC31 --> CC15
    CC1 --> CC31
    CC6 --> T16
    CC8 --> T16
    CC13 --> T16
    CC14 --> T16
    CC15 --> T16
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [40](EXB-IDE-40.md) | Ventes_Excursions | 21 |
| [15](EXB-IDE-15.md) | Definition Plannings | 6 |
| [6](EXB-IDE-6.md) |  Annulation Ventes@ | 5 |
| [14](EXB-IDE-14.md) | Definition Annexes | 4 |
| [13](EXB-IDE-13.md) | Definition Excursions | 3 |
| [20](EXB-IDE-20.md) | Liste ventes/N°vente | 3 |
| [23](EXB-IDE-23.md) | Liste Participant | 3 |
| [26](EXB-IDE-26.md) | Detail Excursion | 3 |
| [8](EXB-IDE-8.md) | Menu clôture | 1 |
| [22](EXB-IDE-22.md) | Edition des excursions | 1 |
| [28](EXB-IDE-28.md) |  Menu fin de saison | 1 |
| [31](EXB-IDE-31.md) | Menu general | 1 |
| [34](EXB-IDE-34.md) | Purge | 1 |
| [42](EXB-IDE-42.md) |   Participants general | 1 |
| [43](EXB-IDE-43.md) |   Participants date | 1 |
| [46](EXB-IDE-46.md) | Zoom article | 1 |
| [47](EXB-IDE-47.md) | Zoom modes de paiement | 1 |
| [48](EXB-IDE-48.md) | Zoom Adherents Paiement | 1 |
| [49](EXB-IDE-49.md) | Zoom Adherents VSP | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T16[16 Recuperation du titre]
    style T16 fill:#58a6ff
    NONE[Aucun callee]
    T16 -.-> NONE
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
| Lignes de logique | 13 | Programme compact |
| Expressions | 4 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 13) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 0 ecran, 1 traitement)

- **Strategie** : 1 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 10:36*
