# ADH IDE 161 - Get Club Med Pass

> **Analyse**: Phases 1-4 2026-02-07 07:19 -> 03:43 (20h24min) | Assemblage 03:43
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | ADH |
| IDE Position | 161 |
| Nom Programme | Get Club Med Pass |
| Fichier source | `Prg_161.xml` |
| Dossier IDE | General |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 0 |
| Complexite | **BASSE** (score 7/100) |
| <span style="color:red">Statut</span> | <span style="color:red">**ORPHELIN_POTENTIEL**</span> |

## 2. DESCRIPTION FONCTIONNELLE

ADH IDE 161 - Get Club Med Pass est un programme très simple de récupération d'informations de carte Club Med Pass. Il reçoit trois paramètres (société, compte, filiation) et effectue une mise à jour directe sur la table ez_card sans logique métier complexe. Le programme comporte une seule condition qui teste si le statut n'est pas 'O' (opposition/bloqué) avant de continuer le traitement.

Ce programme s'intègre dans l'écosystème Club Med Pass qui comprend plusieurs utilitaires (Menu principal 77, Gestion filiations 114, Création de cartes 81, etc.). Cependant, il est actuellement orphelin - aucun caller direct n'a pu être détecté dans la base de connaissances, ce qui suggère qu'il pourrait être appelé via ProgIdx() avec un nom public ou être un utilitaire de batch non référencé directement.

Pour la migration vers C#, le programme est un excellent candidat pour une simple API REST donnée sa structure basse complexité (22 lignes, zéro sous-programmes, aucune dépendance interne). Il devrait être consolidé avec ADH IDE 114 (Club Med Pass Filiations) ou transformé en endpoint spécialisé `POST /api/club-med-pass/get` si sa fonction est distincte.

## 3. BLOCS FONCTIONNELS

## 5. REGLES METIER

1 regles identifiees:

### Autres (1 regles)

#### <a id="rm-RM-001"></a>[RM-001] Condition: [H] different de 'O'

| Element | Detail |
|---------|--------|
| **Condition** | `[H]<>'O'` |
| **Si vrai** | Action si vrai |
| **Expression source** | Expression 4 : `[H]<>'O'` |
| **Exemple** | Si [H]<>'O' â†’ Action si vrai |

## 6. CONTEXTE

- **Appele par**: (aucun)
- **Appelle**: 0 programmes | **Tables**: 1 (W:1 R:0 L:0) | **Taches**: 1 | **Expressions**: 5

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (0 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|

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
| 312 | ez_card |  | DB |   | **W** |   | 1 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 312 - ez_card (**W**) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P0 societe | W | Unicode |
| B | P0 compte | W | Numeric |
| C | P0 filiation | W | Numeric |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (3)

Variables recues en parametre.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| EN | P0 societe | Unicode | 1x parametre entrant |
| EO | P0 compte | Numeric | 1x parametre entrant |
| EP | P0 filiation | Numeric | 1x parametre entrant |

## 12. EXPRESSIONS

**5 / 5 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONDITION | 1 | 5 |
| OTHER | 4 | 0 |

### 12.2 Expressions cles par type

#### CONDITION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 4 | `[H]<>'O'` | [RM-001](#rm-RM-001) |

#### OTHER (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 3 | `P0 filiation [C]` | - |
| OTHER | 5 | `[G]` | - |
| OTHER | 1 | `P0 societe [A]` | - |
| OTHER | 2 | `P0 compte [B]` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

**Chemin**: (pas de callers directs)

```mermaid
graph LR
    T161[161 Get Club Med Pass]
    style T161 fill:#58a6ff
    NONE[Aucun caller]
    NONE -.-> T161
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| - | (aucun) | - |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T161[161 Get Club Med Pass]
    style T161 fill:#58a6ff
    NONE[Aucun callee]
    T161 -.-> NONE
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
| Expressions | 5 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 22) | Code sain |
| Regles metier | 1 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| ez_card | Table WRITE (Database) | 1x | Schema + repository |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-08 03:45*
