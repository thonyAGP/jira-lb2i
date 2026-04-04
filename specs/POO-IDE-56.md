# POO IDE 56 - Boucle Suppr. RETOUR.LIT

> **Analyse**: Phases 1-4 2026-02-03 17:56 -> 17:57 (14s) | Assemblage 17:57
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | POO |
| IDE Position | 56 |
| Nom Programme | Boucle Suppr. RETOUR.LIT |
| Fichier source | `Prg_56.xml` |
| Dossier IDE | Pooling |
| Taches | 2 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Boucle Suppr. RETOUR.LIT** assure la gestion complete de ce processus, accessible depuis [Execution RETOUR TXT (IDE 51)](POO-IDE-51.md), [ Retour transfert fichier (IDE 52)](POO-IDE-52.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (2 taches) : traitements metier divers

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (2 taches)

Traitements internes.

---

#### <a id="t1"></a>56 - Suppression POOLR.LIT

**Role** : Traitement : Suppression POOLR.LIT.

---

#### <a id="t2"></a>56.1 - Suppression POOLM.ECR

**Role** : Traitement : Suppression POOLM.ECR.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Execution RETOUR TXT (IDE 51)](POO-IDE-51.md), [ Retour transfert fichier (IDE 52)](POO-IDE-52.md)
- **Appelle**: 0 programmes | **Tables**: 0 (W:0 R:0 L:0) | **Taches**: 2 | **Expressions**: 4

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (2 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **56.1** | [**Suppression POOLR.LIT** (56)](#t1) | MDI | - | Traitement |
| 56.1.1 | [Suppression POOLM.ECR (56.1)](#t2) | MDI | - | |

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

**4 / 4 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CAST_LOGIQUE | 1 | 0 |
| OTHER | 1 | 0 |
| NEGATION | 1 | 0 |
| STRING | 1 | 0 |

### 12.2 Expressions cles par type

#### CAST_LOGIQUE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 1 | `'TRUE'LOG` | - |

#### OTHER (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 4 | `v. fin [A]` | - |

#### NEGATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| NEGATION | 2 | `NOT (FileExist (Trim (INIGet ('[MAGIC_LOGICAL_NAMES]club_tf_pabx'))&'RETOUR.LIT'))` | - |

#### STRING (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| STRING | 3 | `FileExist (Trim (INIGet ('[MAGIC_LOGICAL_NAMES]club_tf_pabx'))&'RETOUR.LIT')` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Execution RETOUR TXT (IDE 51)](POO-IDE-51.md) -> **Boucle Suppr. RETOUR.LIT (IDE 56)**

Main -> ... -> [ Retour transfert fichier (IDE 52)](POO-IDE-52.md) -> **Boucle Suppr. RETOUR.LIT (IDE 56)**

```mermaid
graph LR
    T56[56 Boucle Suppr. RETOU...]
    style T56 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC19[19 lancement retail OD]
    style CC19 fill:#8b5cf6
    CC16[16 Transfert ODS Boutique]
    style CC16 fill:#f59e0b
    CC24[24 Batch sur PABX]
    style CC24 fill:#f59e0b
    CC51[51 Execution RETOUR TXT]
    style CC51 fill:#3fb950
    CC52[52 Retour transfert fi...]
    style CC52 fill:#3fb950
    CC24 --> CC51
    CC16 --> CC51
    CC24 --> CC52
    CC16 --> CC52
    CC1 --> CC24
    CC19 --> CC24
    CC1 --> CC16
    CC19 --> CC16
    CC51 --> T56
    CC52 --> T56
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [51](POO-IDE-51.md) | Execution RETOUR TXT | 1 |
| [52](POO-IDE-52.md) |  Retour transfert fichier | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T56[56 Boucle Suppr. RETOU...]
    style T56 fill:#58a6ff
    NONE[Aucun callee]
    T56 -.-> NONE
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
| Lignes de logique | 7 | Programme compact |
| Expressions | 4 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 7) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (2 taches: 0 ecran, 2 traitements)

- **Strategie** : 2 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 17:57*
