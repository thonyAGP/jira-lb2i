# POO IDE 79 - Delete table SQL

> **Analyse**: Phases 1-4 2026-02-03 18:07 -> 18:07 (16s) | Assemblage 18:07
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | POO |
| IDE Position | 79 |
| Nom Programme | Delete table SQL |
| Fichier source | `Prg_79.xml` |
| Dossier IDE | Utilitaires |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Delete table SQL** assure la gestion complete de ce processus, accessible depuis [   Envoi table autocom PABX (IDE 75)](POO-IDE-75.md), [Envoi autocom PABX (IDE 76)](POO-IDE-76.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>79 - Delete table SQL

**Role** : Traitement : Delete table SQL.
**Variables liees** : A (P.Nom table)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [   Envoi table autocom PABX (IDE 75)](POO-IDE-75.md), [Envoi autocom PABX (IDE 76)](POO-IDE-76.md)
- **Appelle**: 0 programmes | **Tables**: 0 (W:0 R:0 L:0) | **Taches**: 1 | **Expressions**: 0

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **79.1** | [**Delete table SQL** (79)](#t1) | - | - | Traitement |

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

**0 / 0 expressions decodees (0%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|

### 12.2 Expressions cles par type

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [   Envoi table autocom PABX (IDE 75)](POO-IDE-75.md) -> **Delete table SQL (IDE 79)**

Main -> ... -> [Envoi autocom PABX (IDE 76)](POO-IDE-76.md) -> **Delete table SQL (IDE 79)**

```mermaid
graph LR
    T79[79 Delete table SQL]
    style T79 fill:#58a6ff
    CC78[78 ReSynch PABX]
    style CC78 fill:#8b5cf6
    CC74[74 Envoi Check Out]
    style CC74 fill:#f59e0b
    CC73[73 Envoi Check In]
    style CC73 fill:#f59e0b
    CC75[75 Envoi table autocom...]
    style CC75 fill:#3fb950
    CC76[76 Envoi autocom PABX]
    style CC76 fill:#3fb950
    CC73 --> CC75
    CC74 --> CC75
    CC73 --> CC76
    CC74 --> CC76
    CC78 --> CC73
    CC78 --> CC74
    CC75 --> T79
    CC76 --> T79
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [75](POO-IDE-75.md) |    Envoi table autocom PABX | 1 |
| [76](POO-IDE-76.md) | Envoi autocom PABX | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T79[79 Delete table SQL]
    style T79 fill:#58a6ff
    NONE[Aucun callee]
    T79 -.-> NONE
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
| Lignes de logique | 2 | Programme compact |
| Expressions | 0 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 2) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 0 ecran, 1 traitement)

- **Strategie** : 1 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 18:07*
