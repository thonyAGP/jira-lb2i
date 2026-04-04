# VIL IDE 209 - Uni Print sortie devises

> **Analyse**: Phases 1-4 2026-02-03 21:05 -> 21:05 (13s) | Assemblage 21:05
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | VIL |
| IDE Position | 209 |
| Nom Programme | Uni Print sortie devises |
| Fichier source | `Prg_209.xml` |
| Dossier IDE | Suppr |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Uni Print sortie devises** assure la gestion complete de ce processus, accessible depuis [Uni Sortie de devises (IDE 211)](VIL-IDE-211.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

**Logique metier** : 1 regles identifiees couvrant conditions metier.

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>209 - Veuillez patienter ..... [[ECRAN]](#ecran-t1)

**Role** : Traitement : Veuillez patienter ......
**Ecran** : 427 x 57 DLU (MDI) | [Voir mockup](#ecran-t1)


## 5. REGLES METIER

1 regles identifiees:

### Autres (1 regles)

#### <a id="rm-RM-001"></a>[RM-001] Si P0 validation [E]='O' alors '' sinon '    Duplicata')

| Element | Detail |
|---------|--------|
| **Condition** | `P0 validation [E]='O'` |
| **Si vrai** | '' |
| **Si faux** | '    Duplicata') |
| **Variables** | E (P0 validation) |
| **Expression source** | Expression 7 : `IF (P0 validation [E]='O','','    Duplicata')` |
| **Exemple** | Si P0 validation [E]='O' â†’ ''. Sinon â†’ '    Duplicata') |

## 6. CONTEXTE

- **Appele par**: [Uni Sortie de devises (IDE 211)](VIL-IDE-211.md)
- **Appelle**: 0 programmes | **Tables**: 1 (W:0 R:1 L:0) | **Taches**: 1 | **Expressions**: 9

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **209.1** | [**Veuillez patienter .....** (209)](#t1) [mockup](#ecran-t1) | MDI | 427x57 | Traitement |

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
| 59 | lign_sortie_dev__ldk |  | DB | R |   |   | 1 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 59 - lign_sortie_dev__ldk (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P0 societe | R | Alpha |
| B | P0 date comptable | R | Date |
| C | P0 date sortie | R | Date |
| D | P0 heure sortie | R | Time |
| E | P0 validation | R | Alpha |
| F | P0 nom village | R | Alpha |
| G | W0 config imp. | R | Alpha |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (6)

Variables recues du programme appelant ([Uni Sortie de devises (IDE 211)](VIL-IDE-211.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P0 societe | Alpha | 1x parametre entrant |
| B | P0 date comptable | Date | 1x parametre entrant |
| C | P0 date sortie | Date | 1x parametre entrant |
| D | P0 heure sortie | Time | 1x parametre entrant |
| E | P0 validation | Alpha | 1x parametre entrant |
| F | P0 nom village | Alpha | - |

### 11.2 Variables de travail (1)

Variables internes au programme.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| G | W0 config imp. | Alpha | - |

## 12. EXPRESSIONS

**9 / 9 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONCATENATION | 1 | 0 |
| CONDITION | 2 | 5 |
| OTHER | 6 | 0 |

### 12.2 Expressions cles par type

#### CONCATENATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 8 | `'- '&Str (Page (0,1),'3P0Z0')&' -'` | - |

#### CONDITION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 7 | `IF (P0 validation [E]='O','','    Duplicata')` | [RM-001](#rm-RM-001) |
| CONDITION | 9 | `INIGet ('[MAGIC_LOGICAL_NAMES]preview')='O'` | - |

#### OTHER (6 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 4 | `P0 date comptable [B]` | - |
| OTHER | 5 | `P0 date sortie [C]` | - |
| OTHER | 6 | `P0 heure sortie [D]` | - |
| OTHER | 1 | `SetCrsr (1)` | - |
| OTHER | 2 | `SetCrsr (2)` | - |
| ... | | *+1 autres* | |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Uni Sortie de devises (IDE 211)](VIL-IDE-211.md) -> **Uni Print sortie devises (IDE 209)**

```mermaid
graph LR
    T209[209 Uni Print sortie d...]
    style T209 fill:#58a6ff
    CC211[211 Uni Sortie de devises]
    style CC211 fill:#8b5cf6
    CC211 --> T209
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [211](VIL-IDE-211.md) | Uni Sortie de devises | 2 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T209[209 Uni Print sortie d...]
    style T209 fill:#58a6ff
    NONE[Aucun callee]
    T209 -.-> NONE
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
| Lignes de logique | 22 | Programme compact |
| Expressions | 9 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 22) | Code sain |
| Regles metier | 1 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 1 ecran, 0 traitement)

- **Strategie** : 1 composant(s) UI (Razor/React) avec formulaires et validation.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 21:05*
