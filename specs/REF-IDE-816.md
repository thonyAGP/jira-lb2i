# REF IDE 816 - Converti csv en xlsx

> **Analyse**: Phases 1-4 2026-02-03 14:32 -> 14:32 (15s) | Assemblage 14:32
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | REF |
| IDE Position | 816 |
| Nom Programme | Converti csv en xlsx |
| Fichier source | `Prg_816.xml` |
| Dossier IDE | General |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 3 |
| :warning: Statut | **ORPHELIN_POTENTIEL** |

## 2. DESCRIPTION FONCTIONNELLE

**Converti csv en xlsx** assure la gestion complete de ce processus.

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>816 - Converti csv en xlsx

**Role** : Traitement : Converti csv en xlsx.
**Variables liees** : B (p.io.Destination xlsx)
**Delegue a** : [Converti csv en xlsx / Exe (IDE 817)](REF-IDE-817.md), [Converti csv en xlsx / Excel (IDE 818)](REF-IDE-818.md), [IsExcelInstalled (IDE 820)](REF-IDE-820.md)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: (aucun)
- **Appelle**: 3 programmes | **Tables**: 0 (W:0 R:0 L:0) | **Taches**: 1 | **Expressions**: 3

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **816.1** | [**Converti csv en xlsx** (816)](#t1) | - | - | Traitement |

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

### 11.1 Parametres entrants (4)

Variables recues en parametre.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | p.i.Source csv | Unicode | 1x parametre entrant |
| B | p.io.Destination xlsx | Unicode | - |
| C | p.i.Séparateur csv | Unicode | 1x parametre entrant |
| D | p.o.Statut (blanc pour OK) | Unicode | - |

### 11.2 Variables de session (1)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| E | v.Excel installé ? | Logical | 1x session |

## 12. EXPRESSIONS

**3 / 3 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| OTHER | 3 | 0 |

### 12.2 Expressions cles par type

#### OTHER (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 3 | `p.i.Séparateur csv [C]` | - |
| OTHER | 2 | `p.i.Source csv [A]` | - |
| OTHER | 1 | `v.Excel installé ? [E]` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

**Chemin**: (pas de callers directs)

```mermaid
graph LR
    T816[816 Converti csv en xlsx]
    style T816 fill:#58a6ff
    NONE[Aucun caller]
    NONE -.-> T816
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| - | (aucun) | - |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T816[816 Converti csv en xlsx]
    style T816 fill:#58a6ff
    C817[817 Converti csv en xl...]
    T816 --> C817
    style C817 fill:#3fb950
    C818[818 Converti csv en xl...]
    T816 --> C818
    style C818 fill:#3fb950
    C820[820 IsExcelInstalled]
    T816 --> C820
    style C820 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [817](REF-IDE-817.md) | Converti csv en xlsx / Exe | 1 | Sous-programme |
| [818](REF-IDE-818.md) | Converti csv en xlsx / Excel | 1 | Sous-programme |
| [820](REF-IDE-820.md) | IsExcelInstalled | 1 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 17 | Programme compact |
| Expressions | 3 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 3 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 17) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 0 ecran, 1 traitement)

- **Strategie** : 1 service(s) backend injectable(s) (Domain Services).
- 3 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| [IsExcelInstalled (IDE 820)](REF-IDE-820.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Converti csv en xlsx / Excel (IDE 818)](REF-IDE-818.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Converti csv en xlsx / Exe (IDE 817)](REF-IDE-817.md) | Sous-programme | 1x | Normale - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 14:32*
