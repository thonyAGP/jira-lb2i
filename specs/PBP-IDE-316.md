# PBP IDE 316 - LZM -> Tempouserlist

> **Analyse**: Phases 1-4 2026-02-03 16:22 -> 16:22 (21s) | Assemblage 16:22
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBP |
| IDE Position | 316 |
| Nom Programme | LZM -> Tempouserlist |
| Fichier source | `Prg_316.xml` |
| Dossier IDE | Remplissage |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**LZM -> Tempouserlist** assure la gestion complete de ce processus, accessible depuis [Liste occupation (IDE 136)](PBP-IDE-136.md), [Liste des previsions (IDE 253)](PBP-IDE-253.md), [Liste des arrivees (IDE 254)](PBP-IDE-254.md), [Liste des sejours (IDE 255)](PBP-IDE-255.md), [Liste des departs (IDE 256)](PBP-IDE-256.md), [Liste des menages (IDE 257)](PBP-IDE-257.md), [Liste liberation (IDE 381)](PBP-IDE-381.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

**Logique metier** : 1 regles identifiees couvrant conditions metier.

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>316 - Veuillez patienter ... [[ECRAN]](#ecran-t1)

**Role** : Traitement : Veuillez patienter ....
**Ecran** : 424 x 56 DLU (MDI) | [Voir mockup](#ecran-t1)


## 5. REGLES METIER

1 regles identifiees:

### Autres (1 regles)

#### <a id="rm-RM-001"></a>[RM-001] Si [L]>=>ValMinNbLog [E] alors VG1 sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `[L]>=>ValMinNbLog [E]` |
| **Si vrai** | VG1 |
| **Si faux** | '') |
| **Variables** | E (>ValMinNbLog) |
| **Expression source** | Expression 5 : `IF ([L]>=>ValMinNbLog [E],VG1,'')` |
| **Exemple** | Si [L]>=>ValMinNbLog [E] â†’ VG1. Sinon â†’ '') |

## 6. CONTEXTE

- **Appele par**: [Liste occupation (IDE 136)](PBP-IDE-136.md), [Liste des previsions (IDE 253)](PBP-IDE-253.md), [Liste des arrivees (IDE 254)](PBP-IDE-254.md), [Liste des sejours (IDE 255)](PBP-IDE-255.md), [Liste des departs (IDE 256)](PBP-IDE-256.md), [Liste des menages (IDE 257)](PBP-IDE-257.md), [Liste liberation (IDE 381)](PBP-IDE-381.md)
- **Appelle**: 0 programmes | **Tables**: 2 (W:0 R:1 L:1) | **Taches**: 1 | **Expressions**: 11

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **316.1** | [**Veuillez patienter ...** (316)](#t1) [mockup](#ecran-t1) | MDI | 424x56 | Traitement |

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

### Tables utilisees (2)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 107 | logement_zone_menage |  | DB | R |   |   | 1 |
| 637 | tempo_zone_secteur | Table temporaire ecran | DB |   |   | L | 1 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 107 - logement_zone_menage (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | >Categorie | R | Alpha |
| B | >NomTable | R | Alpha |
| C | >CodeMenage | R | Alpha |
| D | >CodeTri | R | Alpha |
| E | >ValMinNbLog | R | Numeric |
| F | >InitMarqueur | R | Logical |

</details>

## 11. VARIABLES

### 11.1 Autres (6)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | >Categorie | Alpha | 1x refs |
| B | >NomTable | Alpha | 1x refs |
| C | >CodeMenage | Alpha | 1x refs |
| D | >CodeTri | Alpha | 1x refs |
| E | >ValMinNbLog | Numeric | 5x refs |
| F | >InitMarqueur | Logical | 1x refs |

## 12. EXPRESSIONS

**11 / 11 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONDITION | 8 | 5 |
| OTHER | 3 | 0 |

### 12.2 Expressions cles par type

#### CONDITION (8 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 5 | `IF ([L]>=>ValMinNbLog [E],VG1,'')` | [RM-001](#rm-RM-001) |
| CONDITION | 3 | `>CodeMenage [C]` | - |
| CONDITION | 4 | `>CodeTri [D]` | - |
| CONDITION | 10 | `>InitMarqueur [F]` | - |
| CONDITION | 9 | `IF ([L]>=>ValMinNbLog [E],[I],'')` | - |
| ... | | *+3 autres* | |

#### OTHER (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 11 | `[K]` | - |
| OTHER | 2 | `GetParam ('LANGUE')` | - |
| OTHER | 1 | `GetParam ('SOCIETE')` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Liste occupation (IDE 136)](PBP-IDE-136.md) -> **LZM -> Tempouserlist (IDE 316)**

Main -> ... -> [Liste des previsions (IDE 253)](PBP-IDE-253.md) -> **LZM -> Tempouserlist (IDE 316)**

Main -> ... -> [Liste des arrivees (IDE 254)](PBP-IDE-254.md) -> **LZM -> Tempouserlist (IDE 316)**

Main -> ... -> [Liste des sejours (IDE 255)](PBP-IDE-255.md) -> **LZM -> Tempouserlist (IDE 316)**

Main -> ... -> [Liste des departs (IDE 256)](PBP-IDE-256.md) -> **LZM -> Tempouserlist (IDE 316)**

Main -> ... -> [Liste des menages (IDE 257)](PBP-IDE-257.md) -> **LZM -> Tempouserlist (IDE 316)**

Main -> ... -> [Liste liberation (IDE 381)](PBP-IDE-381.md) -> **LZM -> Tempouserlist (IDE 316)**

```mermaid
graph LR
    T316[316 LZM - Tempouserlist]
    style T316 fill:#58a6ff
    CC255[255 Liste des sejours]
    style CC255 fill:#8b5cf6
    CC256[256 Liste des departs]
    style CC256 fill:#8b5cf6
    CC254[254 Liste des arrivees]
    style CC254 fill:#8b5cf6
    CC136[136 Liste occupation]
    style CC136 fill:#8b5cf6
    CC253[253 Liste des previsions]
    style CC253 fill:#8b5cf6
    CC136 --> T316
    CC253 --> T316
    CC254 --> T316
    CC255 --> T316
    CC256 --> T316
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [136](PBP-IDE-136.md) | Liste occupation | 2 |
| [253](PBP-IDE-253.md) | Liste des previsions | 1 |
| [254](PBP-IDE-254.md) | Liste des arrivees | 1 |
| [255](PBP-IDE-255.md) | Liste des sejours | 1 |
| [256](PBP-IDE-256.md) | Liste des departs | 1 |
| [257](PBP-IDE-257.md) | Liste des menages | 1 |
| [381](PBP-IDE-381.md) | Liste liberation | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T316[316 LZM - Tempouserlist]
    style T316 fill:#58a6ff
    NONE[Aucun callee]
    T316 -.-> NONE
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
| Lignes de logique | 26 | Programme compact |
| Expressions | 11 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 26) | Code sain |
| Regles metier | 1 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 1 ecran, 0 traitement)

- **Strategie** : 1 composant(s) UI (Razor/React) avec formulaires et validation.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 16:22*
