# WEL IDE 88 - Recup nom et prenom

> **Analyse**: Phases 1-4 2026-02-03 21:40 -> 21:40 (17s) | Assemblage 21:40
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | WEL |
| IDE Position | 88 |
| Nom Programme | Recup nom et prenom |
| Fichier source | `Prg_88.xml` |
| Dossier IDE | Utilitaires |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Recup nom et prenom** assure la gestion complete de ce processus, accessible depuis [Saisie email (IDE 10)](WEL-IDE-10.md), [Open account (IDE 26)](WEL-IDE-26.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>88 - Recup nom et prenom

**Role** : Consultation/chargement : Recup nom et prenom.
**Variables liees** : B (P.Prenom)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Saisie email (IDE 10)](WEL-IDE-10.md), [Open account (IDE 26)](WEL-IDE-26.md)
- **Appelle**: 0 programmes | **Tables**: 1 (W:0 R:1 L:0) | **Taches**: 1 | **Expressions**: 5

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **88.1** | [**Recup nom et prenom** (88)](#t1) | - | - | Traitement |

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
| 131 | fichier_validation |  | DB | R |   |   | 1 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 131 - fichier_validation (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P.Nom | R | Alpha |
| B | P.Prenom | R | Unicode |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (2)

Variables recues du programme appelant ([Saisie email (IDE 10)](WEL-IDE-10.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P.Nom | Alpha | - |
| B | P.Prenom | Unicode | - |

## 12. EXPRESSIONS

**5 / 5 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| OTHER | 2 | 0 |
| REFERENCE_VG | 3 | 0 |

### 12.2 Expressions cles par type

#### OTHER (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 2 | `[G]` | - |
| OTHER | 1 | `[F]` | - |

#### REFERENCE_VG (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 5 | `VG10` | - |
| REFERENCE_VG | 4 | `VG9` | - |
| REFERENCE_VG | 3 | `VG5` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Saisie email (IDE 10)](WEL-IDE-10.md) -> **Recup nom et prenom (IDE 88)**

Main -> ... -> [Open account (IDE 26)](WEL-IDE-26.md) -> **Recup nom et prenom (IDE 88)**

```mermaid
graph LR
    T88[88 Recup nom et prenom]
    style T88 fill:#58a6ff
    CC96[96 Ventes]
    style CC96 fill:#8b5cf6
    CC55[55 Mobile Welcome]
    style CC55 fill:#8b5cf6
    CC117[117 Ventes *Sav au 040...]
    style CC117 fill:#8b5cf6
    CC116[116 Ventes *Sav au 020...]
    style CC116 fill:#8b5cf6
    CC98[98 Email workflow]
    style CC98 fill:#f59e0b
    CC83[83 Saisie Signature Va...]
    style CC83 fill:#f59e0b
    CC8[8 Identité client]
    style CC8 fill:#f59e0b
    CC9[9 Clients]
    style CC9 fill:#f59e0b
    CC82[82 Saisie Signature]
    style CC82 fill:#f59e0b
    CC10[10 Saisie email]
    style CC10 fill:#3fb950
    CC26[26 Open account]
    style CC26 fill:#3fb950
    CC8 --> CC10
    CC9 --> CC10
    CC82 --> CC10
    CC83 --> CC10
    CC98 --> CC10
    CC8 --> CC26
    CC9 --> CC26
    CC82 --> CC26
    CC83 --> CC26
    CC98 --> CC26
    CC55 --> CC8
    CC96 --> CC8
    CC116 --> CC8
    CC117 --> CC8
    CC55 --> CC9
    CC96 --> CC9
    CC116 --> CC9
    CC117 --> CC9
    CC55 --> CC82
    CC96 --> CC82
    CC116 --> CC82
    CC117 --> CC82
    CC55 --> CC83
    CC96 --> CC83
    CC116 --> CC83
    CC117 --> CC83
    CC55 --> CC98
    CC96 --> CC98
    CC116 --> CC98
    CC117 --> CC98
    CC10 --> T88
    CC26 --> T88
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [10](WEL-IDE-10.md) | Saisie email | 1 |
| [26](WEL-IDE-26.md) | Open account | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T88[88 Recup nom et prenom]
    style T88 fill:#58a6ff
    NONE[Aucun callee]
    T88 -.-> NONE
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
| Lignes de logique | 10 | Programme compact |
| Expressions | 5 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 10) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 0 ecran, 1 traitement)

- **Strategie** : 1 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 21:40*
