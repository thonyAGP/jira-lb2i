# WEL IDE 77 - Création Village/Village

> **Analyse**: Phases 1-4 2026-02-03 21:36 -> 21:36 (11s) | Assemblage 21:36
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | WEL |
| IDE Position | 77 |
| Nom Programme | Création Village/Village |
| Fichier source | `Prg_77.xml` |
| Dossier IDE | Utilitaires |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Création Village/Village** assure la gestion complete de ce processus, accessible depuis [  Avancement Personnel (IDE 66)](WEL-IDE-66.md), [  Interruption Personnel (IDE 67)](WEL-IDE-67.md), [  Prolongation Personnel (IDE 69)](WEL-IDE-69.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

**Donnees modifiees** : 1 tables en ecriture (groupe_arr_dep___vol).

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>77 - Création Village/Village

**Role** : Traitement : Création Village/Village.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [  Avancement Personnel (IDE 66)](WEL-IDE-66.md), [  Interruption Personnel (IDE 67)](WEL-IDE-67.md), [  Prolongation Personnel (IDE 69)](WEL-IDE-69.md)
- **Appelle**: 0 programmes | **Tables**: 1 (W:1 R:0 L:0) | **Taches**: 1 | **Expressions**: 10

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **77.1** | [**Création Village/Village** (77)](#t1) | MDI | - | Traitement |

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
| 134 | groupe_arr_dep___vol |  | DB |   | **W** |   | 1 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 134 - groupe_arr_dep___vol (**W**) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P.Date | W | Date |
| B | P.Aller/Retour | W | Alpha |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (2)

Variables recues du programme appelant ([  Avancement Personnel (IDE 66)](WEL-IDE-66.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P.Date | Date | 1x parametre entrant |
| B | P.Aller/Retour | Alpha | 1x parametre entrant |

## 12. EXPRESSIONS

**10 / 10 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONSTANTE | 7 | 0 |
| REFERENCE_VG | 1 | 0 |
| OTHER | 2 | 0 |

### 12.2 Expressions cles par type

#### CONSTANTE (7 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 8 | `'VV3'` | - |
| CONSTANTE | 9 | `18` | - |
| CONSTANTE | 10 | `23` | - |
| CONSTANTE | 7 | `'M'` | - |
| CONSTANTE | 4 | `'VV1'` | - |
| ... | | *+2 autres* | |

#### REFERENCE_VG (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 1 | `VG5` | - |

#### OTHER (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 3 | `P.Date [A]` | - |
| OTHER | 2 | `P.Aller/Retour [B]` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [  Avancement Personnel (IDE 66)](WEL-IDE-66.md) -> **Création Village/Village (IDE 77)**

Main -> ... -> [  Interruption Personnel (IDE 67)](WEL-IDE-67.md) -> **Création Village/Village (IDE 77)**

Main -> ... -> [  Prolongation Personnel (IDE 69)](WEL-IDE-69.md) -> **Création Village/Village (IDE 77)**

```mermaid
graph LR
    T77[77 Création VillageVil...]
    style T77 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC34[34 Lancement]
    style CC34 fill:#f59e0b
    CC55[55 Mobile Welcome]
    style CC55 fill:#f59e0b
    CC9[9 Clients]
    style CC9 fill:#f59e0b
    CC66[66 Avancement Personnel]
    style CC66 fill:#3fb950
    CC67[67 Interruption Personnel]
    style CC67 fill:#3fb950
    CC69[69 Prolongation Personnel]
    style CC69 fill:#3fb950
    CC9 --> CC66
    CC9 --> CC67
    CC9 --> CC69
    CC55 --> CC9
    CC34 --> CC55
    CC1 --> CC34
    CC66 --> T77
    CC67 --> T77
    CC69 --> T77
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [66](WEL-IDE-66.md) |   Avancement Personnel | 1 |
| [67](WEL-IDE-67.md) |   Interruption Personnel | 1 |
| [69](WEL-IDE-69.md) |   Prolongation Personnel | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T77[77 Création VillageVil...]
    style T77 fill:#58a6ff
    NONE[Aucun callee]
    T77 -.-> NONE
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
| Lignes de logique | 32 | Programme compact |
| Expressions | 10 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 32) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 0 ecran, 1 traitement)

- **Strategie** : 1 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| groupe_arr_dep___vol | Table WRITE (Database) | 1x | Schema + repository |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 21:36*
