# ADH IDE 181 - Set Listing Number

> **Analyse**: Phases 1-4 2026-02-07 03:52 -> 04:01 (24h08min) | Assemblage 04:01
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | ADH |
| IDE Position | 181 |
| Nom Programme | Set Listing Number |
| Fichier source | `Prg_181.xml` |
| Dossier IDE | General |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |
| Complexite | **BASSE** (score 0/100) |

## 2. DESCRIPTION FONCTIONNELLE

**Set Listing Number (ADH IDE 181)** est un utilitaire de configuration impression sans interface visible. Il initialise le numéro de listing courant et réinitialise les paramètres d'impression (nom imprimante, nombre copies, numéro imprimante) à leurs valeurs par défaut. Ce programme fait partie intégrante du **subsystème d'impression en chaîne** (Chained Listing) du module caisse ADH, utilisé pour orchestrer une série d'impressions de documents (factures, garanties, tickets) sur une imprimante configurée.

Le programme reçoit en paramètre un **numéro de listing** et exécute 5 appels `SetParam()` simples pour configurer les paramètres globaux du système d'impression. Aucune table n'est modifiée, aucun sous-programme n'est appelé : c'est une opération purement paramétrée qui sert de **point d'entrée de configuration** avant de lancer les chaînes d'impression. Il est appelé depuis le menu impression (ADH IDE 214) et son résultat est utilisé par tous les programmes d'impression qui lisent ces paramètres via `GetParam()`.

Avec seulement 11 lignes de logique et 0 dépendances horizontales, c'est l'un des programmes les plus simples du module ADH. La migration vers TypeScript ou C# est triviale : transformer en fonction utilitaire d'un service de configuration impression, sans aucune complexité métier à préserver.

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>181 - Set Listing Number

**Role** : Traitement : Set Listing Number.
**Variables liees** : EN (Param Listing number)


## 5. REGLES METIER

1 regles identifiees:

### Autres (1 regles)

#### <a id="rm-RM-001"></a>[RM-001] Condition: parametre SPECIFICPRINT egale 'VOID'

| Element | Detail |
|---------|--------|
| **Condition** | `GetParam ('SPECIFICPRINT')='VOID'` |
| **Si vrai** | Action si SPECIFICPRINT = 'VOID' |
| **Expression source** | Expression 5 : `GetParam ('SPECIFICPRINT')='VOID'` |
| **Exemple** | Si GetParam ('SPECIFICPRINT')='VOID' â†’ Action si SPECIFICPRINT = 'VOID' |

## 6. CONTEXTE

- **Appele par**: (aucun)
- **Appelle**: 0 programmes | **Tables**: 0 (W:0 R:0 L:0) | **Taches**: 1 | **Expressions**: 5

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **181.1** | [**Set Listing Number** (181)](#t1) | MDI | - | Traitement |

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

*(Programme sans variables locales mappees)*

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
| CONDITION | 5 | `GetParam ('SPECIFICPRINT')='VOID'` | [RM-001](#rm-RM-001) |

#### OTHER (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 3 | `SetParam ('CURRENTPRINTERNAME','VOID')` | - |
| OTHER | 4 | `SetParam ('NUMBERCOPIES',0)` | - |
| OTHER | 1 | `SetParam ('CURRENTLISTINGNUM',Param Listing number [A])` | - |
| OTHER | 2 | `SetParam ('CURRENTPRINTERNUM',0)` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

**Chemin**: (pas de callers directs)

```mermaid
graph LR
    T181[181 Set Listing Number]
    style T181 fill:#58a6ff
    NONE[Aucun caller]
    NONE -.-> T181
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| - | (aucun) | - |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T181[181 Set Listing Number]
    style T181 fill:#58a6ff
    NONE[Aucun callee]
    T181 -.-> NONE
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
| Lignes de logique | 11 | Programme compact |
| Expressions | 5 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 11) | Code sain |
| Regles metier | 1 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 0 ecran, 1 traitement)

- **Strategie** : 1 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-08 04:03*
