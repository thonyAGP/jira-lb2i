# PBP IDE 301 - controle categorie

> **Analyse**: Phases 1-4 2026-02-03 16:17 -> 16:17 (14s) | Assemblage 16:17
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBP |
| IDE Position | 301 |
| Nom Programme | controle categorie |
| Fichier source | `Prg_301.xml` |
| Dossier IDE | Recup |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**controle categorie** assure la gestion complete de ce processus, accessible depuis [Liste CLients AVPBDR (IDE 174)](PBP-IDE-174.md), [  Liste CLients arrivant (IDE 156)](PBP-IDE-156.md), [  Liste Clients present (IDE 162)](PBP-IDE-162.md), [  Liste CLients depart (IDE 168)](PBP-IDE-168.md), [  Liste present personnel plan (IDE 227)](PBP-IDE-227.md), [  Liste personnels AVPBDR (IDE 234)](PBP-IDE-234.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Validation** (1 tache) : controles et verifications de coherence

## 3. BLOCS FONCTIONNELS

### 3.1 Validation (1 tache)

Controles de coherence : 1 tache verifie les donnees et conditions.

---

#### <a id="t1"></a>301 - controle categorie [[ECRAN]](#ecran-t1)

**Role** : Verification : controle categorie.
**Ecran** : 371 x 160 DLU (MDI) | [Voir mockup](#ecran-t1)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Liste CLients AVPBDR (IDE 174)](PBP-IDE-174.md), [  Liste CLients arrivant (IDE 156)](PBP-IDE-156.md), [  Liste Clients present (IDE 162)](PBP-IDE-162.md), [  Liste CLients depart (IDE 168)](PBP-IDE-168.md), [  Liste present personnel plan (IDE 227)](PBP-IDE-227.md), [  Liste personnels AVPBDR (IDE 234)](PBP-IDE-234.md)
- **Appelle**: 0 programmes | **Tables**: 1 (W:0 R:1 L:0) | **Taches**: 1 | **Expressions**: 5

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **301.1** | [**controle categorie** (301)](#t1) [mockup](#ecran-t1) | MDI | 371x160 | Validation |

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
| 134 | groupe_arr_dep___vol |  | DB | R |   |   | 1 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 134 - groupe_arr_dep___vol (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | >Date | R | Date |
| B | >TypeVol | R | Alpha |
| C | <CodeRetour | R | Logical |

</details>

## 11. VARIABLES

### 11.1 Autres (3)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | >Date | Date | 1x refs |
| B | >TypeVol | Alpha | 1x refs |
| C | <CodeRetour | Logical | - |

## 12. EXPRESSIONS

**5 / 5 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CAST_LOGIQUE | 2 | 0 |
| OTHER | 1 | 0 |
| CONDITION | 2 | 0 |

### 12.2 Expressions cles par type

#### CAST_LOGIQUE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 2 | `'TRUE'LOG` | - |
| CAST_LOGIQUE | 1 | `'FALSE'LOG` | - |

#### OTHER (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 3 | `GetParam ('SOCIETE')` | - |

#### CONDITION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 5 | `>Date [A]` | - |
| CONDITION | 4 | `>TypeVol [B]` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Liste CLients AVPBDR (IDE 174)](PBP-IDE-174.md) -> **controle categorie (IDE 301)**

Main -> ... -> [  Liste CLients arrivant (IDE 156)](PBP-IDE-156.md) -> **controle categorie (IDE 301)**

Main -> ... -> [  Liste Clients present (IDE 162)](PBP-IDE-162.md) -> **controle categorie (IDE 301)**

Main -> ... -> [  Liste CLients depart (IDE 168)](PBP-IDE-168.md) -> **controle categorie (IDE 301)**

Main -> ... -> [  Liste present personnel plan (IDE 227)](PBP-IDE-227.md) -> **controle categorie (IDE 301)**

Main -> ... -> [  Liste personnels AVPBDR (IDE 234)](PBP-IDE-234.md) -> **controle categorie (IDE 301)**

```mermaid
graph LR
    T301[301 controle categorie]
    style T301 fill:#58a6ff
    CC161[161 Liste des presents]
    style CC161 fill:#8b5cf6
    CC173[173 Liste des Absents]
    style CC173 fill:#8b5cf6
    CC167[167 Liste des departs]
    style CC167 fill:#8b5cf6
    CC172[172 Liste des partants]
    style CC172 fill:#8b5cf6
    CC160[160 Liste des arrivees]
    style CC160 fill:#8b5cf6
    CC155[155 Liste des arrivants]
    style CC155 fill:#8b5cf6
    CC162[162 Liste Clients present]
    style CC162 fill:#3fb950
    CC156[156 Liste CLients arri...]
    style CC156 fill:#3fb950
    CC227[227 Liste present pers...]
    style CC227 fill:#3fb950
    CC174[174 Liste CLients AVPBDR]
    style CC174 fill:#3fb950
    CC168[168 Liste CLients depart]
    style CC168 fill:#3fb950
    CC155 --> CC156
    CC161 --> CC156
    CC167 --> CC156
    CC160 --> CC156
    CC172 --> CC156
    CC173 --> CC156
    CC155 --> CC162
    CC161 --> CC162
    CC167 --> CC162
    CC160 --> CC162
    CC172 --> CC162
    CC173 --> CC162
    CC155 --> CC168
    CC161 --> CC168
    CC167 --> CC168
    CC160 --> CC168
    CC172 --> CC168
    CC173 --> CC168
    CC155 --> CC174
    CC161 --> CC174
    CC167 --> CC174
    CC160 --> CC174
    CC172 --> CC174
    CC173 --> CC174
    CC155 --> CC227
    CC161 --> CC227
    CC167 --> CC227
    CC160 --> CC227
    CC172 --> CC227
    CC173 --> CC227
    CC156 --> T301
    CC162 --> T301
    CC168 --> T301
    CC174 --> T301
    CC227 --> T301
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [174](PBP-IDE-174.md) | Liste CLients AVPBDR | 2 |
| [156](PBP-IDE-156.md) |   Liste CLients arrivant | 1 |
| [162](PBP-IDE-162.md) |   Liste Clients present | 1 |
| [168](PBP-IDE-168.md) |   Liste CLients depart | 1 |
| [227](PBP-IDE-227.md) |   Liste present personnel plan | 1 |
| [234](PBP-IDE-234.md) |   Liste personnels AVPBDR | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T301[301 controle categorie]
    style T301 fill:#58a6ff
    NONE[Aucun callee]
    T301 -.-> NONE
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
| Expressions | 5 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 12) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Validation (1 tache: 1 ecran, 0 traitement)

- **Strategie** : FluentValidation avec validators specifiques.
- Chaque tache de validation -> un validator injectable

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 16:17*
