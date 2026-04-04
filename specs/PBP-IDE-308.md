# PBP IDE 308 - Recup code zone/secteur

> **Analyse**: Phases 1-4 2026-02-03 16:19 -> 16:19 (12s) | Assemblage 16:19
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBP |
| IDE Position | 308 |
| Nom Programme | Recup code zone/secteur |
| Fichier source | `Prg_308.xml` |
| Dossier IDE | Recup |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Recup code zone/secteur** assure la gestion complete de ce processus, accessible depuis [Liste des previsions (IDE 253)](PBP-IDE-253.md), [Liste des arrivees (IDE 254)](PBP-IDE-254.md), [Liste des sejours (IDE 255)](PBP-IDE-255.md), [Liste des departs (IDE 256)](PBP-IDE-256.md), [Liste des menages (IDE 257)](PBP-IDE-257.md), [Liste liberation (IDE 381)](PBP-IDE-381.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>308 - Recup code zone/secteur

**Role** : Consultation/chargement : Recup code zone/secteur.
**Variables liees** : A (<Code zone/secteur)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Liste des previsions (IDE 253)](PBP-IDE-253.md), [Liste des arrivees (IDE 254)](PBP-IDE-254.md), [Liste des sejours (IDE 255)](PBP-IDE-255.md), [Liste des departs (IDE 256)](PBP-IDE-256.md), [Liste des menages (IDE 257)](PBP-IDE-257.md), [Liste liberation (IDE 381)](PBP-IDE-381.md)
- **Appelle**: 0 programmes | **Tables**: 1 (W:0 R:1 L:0) | **Taches**: 1 | **Expressions**: 2

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **308.1** | [**Recup code zone/secteur** (308)](#t1) | MDI | - | Traitement |

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
| 109 | table_utilisateurs |  | DB | R |   |   | 1 |

### Colonnes par table (0 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 109 - table_utilisateurs (R) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

*(Programme sans variables locales mappees)*

## 12. EXPRESSIONS

**2 / 2 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| REFERENCE_VG | 1 | 0 |
| OTHER | 1 | 0 |

### 12.2 Expressions cles par type

#### REFERENCE_VG (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 1 | `VG1` | - |

#### OTHER (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 2 | `[C]` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Liste des previsions (IDE 253)](PBP-IDE-253.md) -> **Recup code zone/secteur (IDE 308)**

Main -> ... -> [Liste des arrivees (IDE 254)](PBP-IDE-254.md) -> **Recup code zone/secteur (IDE 308)**

Main -> ... -> [Liste des sejours (IDE 255)](PBP-IDE-255.md) -> **Recup code zone/secteur (IDE 308)**

Main -> ... -> [Liste des departs (IDE 256)](PBP-IDE-256.md) -> **Recup code zone/secteur (IDE 308)**

Main -> ... -> [Liste des menages (IDE 257)](PBP-IDE-257.md) -> **Recup code zone/secteur (IDE 308)**

Main -> ... -> [Liste liberation (IDE 381)](PBP-IDE-381.md) -> **Recup code zone/secteur (IDE 308)**

```mermaid
graph LR
    T308[308 Recup code zonesec...]
    style T308 fill:#58a6ff
    CC256[256 Liste des departs]
    style CC256 fill:#8b5cf6
    CC257[257 Liste des menages]
    style CC257 fill:#8b5cf6
    CC255[255 Liste des sejours]
    style CC255 fill:#8b5cf6
    CC253[253 Liste des previsions]
    style CC253 fill:#8b5cf6
    CC254[254 Liste des arrivees]
    style CC254 fill:#8b5cf6
    CC253 --> T308
    CC254 --> T308
    CC255 --> T308
    CC256 --> T308
    CC257 --> T308
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [253](PBP-IDE-253.md) | Liste des previsions | 1 |
| [254](PBP-IDE-254.md) | Liste des arrivees | 1 |
| [255](PBP-IDE-255.md) | Liste des sejours | 1 |
| [256](PBP-IDE-256.md) | Liste des departs | 1 |
| [257](PBP-IDE-257.md) | Liste des menages | 1 |
| [381](PBP-IDE-381.md) | Liste liberation | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T308[308 Recup code zonesec...]
    style T308 fill:#58a6ff
    NONE[Aucun callee]
    T308 -.-> NONE
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
| Lignes de logique | 6 | Programme compact |
| Expressions | 2 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 6) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 0 ecran, 1 traitement)

- **Strategie** : 1 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 16:19*
