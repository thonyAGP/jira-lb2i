# ADH IDE 223 - Suppression Carac interdit

> **Analyse**: Phases 1-4 2026-02-08 04:25 -> 04:25 (4s) | Assemblage 04:25
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | ADH |
| IDE Position | 223 |
| Nom Programme | Suppression Carac interdit |
| Fichier source | `Prg_223.xml` |
| Dossier IDE | General |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |
| Complexite | **BASSE** (score 0/100) |

## 2. DESCRIPTION FONCTIONNELLE

ADH IDE 223 est un programme utilitaire de nettoyage de caractères interdits, appelé depuis le combo de sélection LIEU de séjour (ADH IDE 224). Son rôle est de valider ou nettoyer les données saisies en supprimant les caractères non autorisés avant leur stockage en base de données.

Le programme traite probablement une chaîne de caractères en entrée, la parcourt pour identifier les caractères invalides (espaces, caractères spéciaux, accents selon les règles métier), et retourne la chaîne nettoyée. Il garantit que les valeurs stockées dans la table LIEU_SEJOUR respectent le format attendu, évitant les corruptions de données ou les erreurs d'affichage ultérieures.

Ce type de programme est généralement peu complexe (quelques expressions IF/CASE pour valider chaque caractère) mais critique pour la qualité des données. Il peut être appelé depuis plusieurs combos ou grilles de saisie du module ADH, ce qui en ferait un composant partagé de validation de chaînes.

## 3. BLOCS FONCTIONNELS

## 5. REGLES METIER

2 regles identifiees:

### Autres (2 regles)

#### <a id="rm-RM-001"></a>[RM-001] Condition: InStr (< v. combo [A],'-') egale 0

| Element | Detail |
|---------|--------|
| **Condition** | `InStr (< v. combo [A],'-')=0` |
| **Si vrai** | Action si vrai |
| **Variables** | EN (< v. combo) |
| **Expression source** | Expression 1 : `InStr (< v. combo [A],'-')=0` |
| **Exemple** | Si InStr (< v. combo [A],'-')=0 â†’ Action si vrai |

#### <a id="rm-RM-002"></a>[RM-002] Condition: InStr (< v. combo [A],'-') different de 0

| Element | Detail |
|---------|--------|
| **Condition** | `InStr (< v. combo [A],'-')<>0` |
| **Si vrai** | Action si vrai |
| **Variables** | EN (< v. combo) |
| **Expression source** | Expression 2 : `InStr (< v. combo [A],'-')<>0` |
| **Exemple** | Si InStr (< v. combo [A],'-')<>0 â†’ Action si vrai |

## 6. CONTEXTE

- **Appele par**: [Alimentation Combos LIEU SEJ (IDE 224)](ADH-IDE-224.md)
- **Appelle**: 0 programmes | **Tables**: 0 (W:0 R:0 L:0) | **Taches**: 1 | **Expressions**: 3

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
    DECISION{v. combo}
    PROCESS[Traitement]
    ENDOK([END OK])
    ENDKO([END KO])

    START --> INIT --> SAISIE --> DECISION
    DECISION -->|OUI| PROCESS
    DECISION -->|NON| ENDKO
    PROCESS --> ENDOK

    style START fill:#3fb950,color:#000
    style ENDOK fill:#3fb950,color:#000
    style ENDKO fill:#f85149,color:#fff
    style DECISION fill:#58a6ff,color:#000
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

**3 / 3 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONCATENATION | 1 | 0 |
| CONDITION | 2 | 2 |

### 12.2 Expressions cles par type

#### CONCATENATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 3 | `Left (< v. combo [A],InStr (< v. combo [A],'-')-1)&'_'&Right (< v. combo [A],Len (< v. combo [A])-InStr (< v. combo [A],'-'))` | - |

#### CONDITION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 2 | `InStr (< v. combo [A],'-')<>0` | [RM-002](#rm-RM-002) |
| CONDITION | 1 | `InStr (< v. combo [A],'-')=0` | [RM-001](#rm-RM-001) |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Alimentation Combos LIEU SEJ (IDE 224)](ADH-IDE-224.md) -> **Suppression Carac interdit (IDE 223)**

```mermaid
graph LR
    T223[223 Suppression Carac ...]
    style T223 fill:#58a6ff
    CC224[224 Alimentation Combo...]
    style CC224 fill:#8b5cf6
    CC224 --> T223
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [224](ADH-IDE-224.md) | Alimentation Combos LIEU SEJ | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T223[223 Suppression Carac ...]
    style T223 fill:#58a6ff
    NONE[Aucun callee]
    T223 -.-> NONE
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
| Lignes de logique | 3 | Programme compact |
| Expressions | 3 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 3) | Code sain |
| Regles metier | 2 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-08 04:26*
