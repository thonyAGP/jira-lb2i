# REF IDE 704 - Export niveau menu

> **Analyse**: Phases 1-4 2026-02-03 13:48 -> 13:49 (27s) | Assemblage 13:49
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | REF |
| IDE Position | 704 |
| Nom Programme | Export niveau menu |
| Fichier source | `Prg_704.xml` |
| Dossier IDE | Navigation |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 1 |

## 2. DESCRIPTION FONCTIONNELLE

**Export niveau menu** assure la gestion complete de ce processus, accessible depuis [Export csv menu (IDE 703)](REF-IDE-703.md), [Export niveau menu (IDE 704)](REF-IDE-704.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>704 - niveau menu

**Role** : Traitement : niveau menu.
**Variables liees** : A (P.Niveau)
**Delegue a** : [Export niveau menu (IDE 704)](REF-IDE-704.md)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Export csv menu (IDE 703)](REF-IDE-703.md), [Export niveau menu (IDE 704)](REF-IDE-704.md)
- **Appelle**: 1 programmes | **Tables**: 2 (W:0 R:1 L:1) | **Taches**: 1 | **Expressions**: 5

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **704.1** | [**niveau menu** (704)](#t1) | - | - | Traitement |

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
| 741 | Table_741 |  | MEM | R |   |   | 1 |
| 750 | Table_750 |  | MEM |   |   | L | 1 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 741 - Table_741 (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P.Niveau | R | Numeric |
| B | P.id | R | Numeric |
| C | P.Profondeur | R | Numeric |
| D | V.Ligne | R | Alpha |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (3)

Variables recues du programme appelant ([Export csv menu (IDE 703)](REF-IDE-703.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P.Niveau | Numeric | 1x parametre entrant |
| B | P.id | Numeric | 2x parametre entrant |
| C | P.Profondeur | Numeric | 2x parametre entrant |

### 11.2 Variables de session (1)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| D | V.Ligne | Alpha | - |

## 12. EXPRESSIONS

**5 / 5 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCULATION | 2 | 0 |
| OTHER | 2 | 0 |
| CONCATENATION | 1 | 0 |

### 12.2 Expressions cles par type

#### CALCULATION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 5 | `P.Profondeur [C]+1` | - |
| CALCULATION | 1 | `P.id [B]+1` | - |

#### OTHER (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 4 | `P.id [B]` | - |
| OTHER | 2 | `P.Niveau [A]` | - |

#### CONCATENATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 3 | `Fill('" ";',P.Profondeur [C])&'"'&Trim([F])&'"'&';'&'"'&Trim([G])&'"'` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Export csv menu (IDE 703)](REF-IDE-703.md) -> **Export niveau menu (IDE 704)**

Main -> ... -> [Export niveau menu (IDE 704)](REF-IDE-704.md) -> **Export niveau menu (IDE 704)**

```mermaid
graph LR
    T704[704 Export niveau menu]
    style T704 fill:#58a6ff
    CC703[703 Export csv menu]
    style CC703 fill:#8b5cf6
    CC703 --> T704
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [703](REF-IDE-703.md) | Export csv menu | 1 |
| [704](REF-IDE-704.md) | Export niveau menu | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T704[704 Export niveau menu]
    style T704 fill:#58a6ff
    C704[704 Export niveau menu]
    T704 --> C704
    style C704 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [704](REF-IDE-704.md) | Export niveau menu | 1 | Navigation menu |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 17 | Programme compact |
| Expressions | 5 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 1 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 17) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 0 ecran, 1 traitement)

- **Strategie** : 1 service(s) backend injectable(s) (Domain Services).
- 1 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| [Export niveau menu (IDE 704)](REF-IDE-704.md) | Sous-programme | 1x | Normale - Navigation menu |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 13:49*
