# MAI IDE 1 - Main Program

> **Analyse**: Phases 1-4 2026-02-03 14:44 -> 14:44 (9s) | Assemblage 14:44
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | MAI |
| IDE Position | 1 |
| Nom Programme | Main Program |
| Fichier source | `Prg_1.xml` |
| Dossier IDE | General |
| Taches | 1 (1 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 4 |
| :warning: Statut | **ORPHELIN_POTENTIEL** |

## 2. DESCRIPTION FONCTIONNELLE

**Main Program** assure la gestion complete de ce processus.

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>1 - Caisse Maintenance [[ECRAN]](#ecran-t1)

**Role** : Traitement : Caisse Maintenance.
**Ecran** : 320 x 200 DLU (Type11) | [Voir mockup](#ecran-t1)
**Variables liees** : C (VG.DROIT CAISSE MAINTENANCE ?)
**Delegue a** : [Recuperation langue (IDE 46)](MAI-IDE-46.md), [Abandon (IDE 49)](MAI-IDE-49.md), [Start (IDE 51)](MAI-IDE-51.md)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: (aucun)
- **Appelle**: 4 programmes | **Tables**: 0 (W:0 R:0 L:0) | **Taches**: 1 | **Expressions**: 15

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 1)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 1 | 1 | Caisse Maintenance | Type11 | 320 | 200 | Traitement |

### 8.2 Mockups Ecrans

## 9. NAVIGATION

Ecran unique: **Caisse Maintenance**

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **1.1** | [**Caisse Maintenance** (1)](#t1) [mockup](#ecran-t1) | Type11 | 320x200 | Traitement |

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

### 11.1 Variables globales (11)

Variables globales partagees entre programmes.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | VG.LOGIN | Alpha | 3x variable globale |
| B | VG.USER | Alpha | - |
| C | VG.DROIT CAISSE MAINTENANCE ? | Logical | - |
| D | VG.DROIT ACCES A TOUT ? | Logical | - |
| E | VG.USE MDR? | Logical | - |
| F | VG.INTERFACE QUADRIGA? | Logical | - |
| G | VG.VERSION | Alpha | - |
| H | VG.DATE VERSION | Alpha | - |
| I | VG.HOSTNAME AU LIEU DE TERM | Logical | - |
| J | VG.PSEUDO TERMINAL | Numeric | - |
| K | VG.DROIT ACCES IT ? | Logical | - |

## 12. EXPRESSIONS

**15 / 15 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONCATENATION | 1 | 0 |
| CONSTANTE | 5 | 0 |
| CONDITION | 1 | 0 |
| CAST_LOGIQUE | 3 | 0 |
| OTHER | 4 | 0 |
| NEGATION | 1 | 0 |

### 12.2 Expressions cles par type

#### CONCATENATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 8 | `'Caisse Maintenance - V '&Trim(ExpCalc('7'EXP))&' - '&Trim(ExpCalc('8'EXP))` | - |

#### CONSTANTE (5 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 9 | `'T2H'` | - |
| CONSTANTE | 10 | `'1.00'` | - |
| CONSTANTE | 7 | `'01/06/2021'` | - |
| CONSTANTE | 5 | `'CM'` | - |
| CONSTANTE | 6 | `'4.01'` | - |

#### CONDITION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 1 | `RunMode ()<=2` | - |

#### CAST_LOGIQUE (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 15 | `CallProg(ProgIdx('hasRight','TRUE'LOG),VG.LOGIN [A],'ACCESALL')` | - |
| CAST_LOGIQUE | 3 | `CallProg(ProgIdx('hasRight','TRUE'LOG),VG.LOGIN [A],'CAISSEMT')` | - |
| CAST_LOGIQUE | 2 | `CallProg(ProgIdx('hasRight','TRUE'LOG),VG.LOGIN [A],'ACCESALL')` | - |

#### OTHER (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 12 | `GetPseudoTerminal ()` | - |
| OTHER | 14 | `VG.HOSTNAME AU LIEU DE... [I]` | - |
| OTHER | 4 | `MnuShow('DEV',VG.DROIT CAISSE MAINTE... [C])` | - |
| OTHER | 11 | `Term ()` | - |

#### NEGATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| NEGATION | 13 | `NOT VG.HOSTNAME AU LIEU DE... [I]` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

**Chemin**: (pas de callers directs)

```mermaid
graph LR
    T1[1 Main Program]
    style T1 fill:#58a6ff
    NONE[Aucun caller]
    NONE -.-> T1
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| - | (aucun) | - |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T1[1 Main Program]
    style T1 fill:#58a6ff
    C46[46 Recuperation langue]
    T1 --> C46
    style C46 fill:#3fb950
    C49[49 Abandon]
    T1 --> C49
    style C49 fill:#3fb950
    C51[51 Start]
    T1 --> C51
    style C51 fill:#3fb950
    C52[52 CM Menu parametrage...]
    T1 --> C52
    style C52 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [46](MAI-IDE-46.md) | Recuperation langue | 1 | Recuperation donnees |
| [49](MAI-IDE-49.md) | Abandon | 1 | Sous-programme |
| [51](MAI-IDE-51.md) | Start | 1 | Sous-programme |
| [52](MAI-IDE-52.md) | CM  Menu parametrage caisse | 1 | Navigation menu |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 32 | Programme compact |
| Expressions | 15 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 4 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 32) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 1 ecran, 0 traitement)

- **Strategie** : 1 composant(s) UI (Razor/React) avec formulaires et validation.
- 4 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| [Start (IDE 51)](MAI-IDE-51.md) | Sous-programme | 1x | Normale - Sous-programme |
| [CM  Menu parametrage caisse (IDE 52)](MAI-IDE-52.md) | Sous-programme | 1x | Normale - Navigation menu |
| [Recuperation langue (IDE 46)](MAI-IDE-46.md) | Sous-programme | 1x | Normale - Recuperation donnees |
| [Abandon (IDE 49)](MAI-IDE-49.md) | Sous-programme | 1x | Normale - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 14:44*
