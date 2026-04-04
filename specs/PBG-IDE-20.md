# PBG IDE 20 - Maj log affectation

> **Analyse**: Phases 1-4 2026-02-03 01:07 -> 01:08 (42s) | Assemblage 01:08
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBG |
| IDE Position | 20 |
| Nom Programme | Maj log affectation |
| Fichier source | `Prg_20.xml` |
| Domaine metier | General |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Maj log affectation** assure la gestion complete de ce processus, accessible depuis [Gestion priorite (IDE 9)](PBG-IDE-9.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

**Donnees modifiees** : 1 tables en ecriture (pv_message).

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>20 - Maj log affectation

**Role** : Traitement : Maj log affectation.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Gestion priorite (IDE 9)](PBG-IDE-9.md)
- **Appelle**: 0 programmes | **Tables**: 1 (W:1 R:0 L:0) | **Taches**: 1 | **Expressions**: 5

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **20.1** | [**Maj log affectation** (20)](#t1) | - | - | Traitement |

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
| 822 | pv_message |  | DB |   | **W** |   | 1 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 822 - pv_message (**W**) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P.Date reference | W | Date |
| B | P.Date debut sejour | W | Date |
| C | P.N° compte | W | Numeric |
| D | P.N° filiation | W | Numeric |
| E | P.Raison rejet | W | Alpha |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (5)

Variables recues du programme appelant ([Gestion priorite (IDE 9)](PBG-IDE-9.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P.Date reference | Date | 1x parametre entrant |
| B | P.Date debut sejour | Date | 1x parametre entrant |
| C | P.N° compte | Numeric | - |
| D | P.N° filiation | Numeric | - |
| E | P.Raison rejet | Alpha | - |

## 12. EXPRESSIONS

**5 / 5 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| OTHER | 5 | 0 |

### 12.2 Expressions cles par type

#### OTHER (5 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 4 | `[X]` | - |
| OTHER | 5 | `P.Date debut sejour [B]` | - |
| OTHER | 3 | `P.Date reference [A]` | - |
| OTHER | 1 | `[W]` | - |
| OTHER | 2 | `[P]` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Gestion priorite (IDE 9)](PBG-IDE-9.md) -> **Maj log affectation (IDE 20)**

```mermaid
graph LR
    T20[20 Maj log affectation]
    style T20 fill:#58a6ff
    CC5[5 Affectation auto cha...]
    style CC5 fill:#8b5cf6
    CC14[14 lancement affec aut...]
    style CC14 fill:#f59e0b
    CC21[21 Affec manuelle chambre]
    style CC21 fill:#f59e0b
    CC6[6 Affectation auto cha...]
    style CC6 fill:#f59e0b
    CC8[8 Traitement affec aut...]
    style CC8 fill:#f59e0b
    CC9[9 Gestion priorite]
    style CC9 fill:#3fb950
    CC8 --> CC9
    CC6 --> CC8
    CC14 --> CC8
    CC21 --> CC8
    CC5 --> CC6
    CC5 --> CC14
    CC5 --> CC21
    CC9 --> T20
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [9](PBG-IDE-9.md) | Gestion priorite | 2 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T20[20 Maj log affectation]
    style T20 fill:#58a6ff
    NONE[Aucun callee]
    T20 -.-> NONE
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
| Lignes de logique | 14 | Programme compact |
| Expressions | 5 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 14) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 0 ecran, 1 traitement)

- **Strategie** : 1 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| pv_message | Table WRITE (Database) | 1x | Schema + repository |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 01:08*
