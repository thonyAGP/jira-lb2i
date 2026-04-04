# PBG IDE 129 - GM supprimes en modif 2

> **Analyse**: Phases 1-4 2026-02-03 09:35 -> 09:36 (17s) | Assemblage 09:36
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBG |
| IDE Position | 129 |
| Nom Programme | GM supprimes en modif 2 |
| Fichier source | `Prg_129.xml` |
| Domaine metier | General |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**GM supprimes en modif 2** assure la gestion complete de ce processus, accessible depuis [   Suppression Client (IDE 82)](PBG-IDE-82.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

**Donnees modifiees** : 1 tables en ecriture (pms_printer_dispo).

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>129 - GM supprimes en modif 2

**Role** : Traitement : GM supprimes en modif 2.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [   Suppression Client (IDE 82)](PBG-IDE-82.md)
- **Appelle**: 0 programmes | **Tables**: 1 (W:1 R:0 L:0) | **Taches**: 1 | **Expressions**: 7

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **129.1** | [**GM supprimes en modif 2** (129)](#t1) | MDI | - | Traitement |

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
| 567 | pms_printer_dispo |  | TMP |   | **W** |   | 1 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 567 - pms_printer_dispo (**W**) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | PARAM Societe | W | Alpha |
| B | PARAM Type | W | Alpha |
| C | PARAM Adherent | W | Numeric |
| D | PARAM Filiation club | W | Numeric |
| E | PARAM compte | W | Numeric |
| F | PARAM filiation | W | Numeric |

</details>

## 11. VARIABLES

### 11.1 Autres (6)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | PARAM Societe | Alpha | 1x refs |
| B | PARAM Type | Alpha | 1x refs |
| C | PARAM Adherent | Numeric | 1x refs |
| D | PARAM Filiation club | Numeric | 1x refs |
| E | PARAM compte | Numeric | 1x refs |
| F | PARAM filiation | Numeric | 2x refs |

## 12. EXPRESSIONS

**7 / 7 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| OTHER | 6 | 0 |
| CAST_LOGIQUE | 1 | 0 |

### 12.2 Expressions cles par type

#### OTHER (6 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 4 | `PARAM Filiation club [D]` | - |
| OTHER | 5 | `PARAM compte [E]` | - |
| OTHER | 6 | `PARAM filiation [F]` | - |
| OTHER | 1 | `PARAM Societe [A]` | - |
| OTHER | 2 | `PARAM Type [B]` | - |
| ... | | *+1 autres* | |

#### CAST_LOGIQUE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 7 | `'TRUE'LOG` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [   Suppression Client (IDE 82)](PBG-IDE-82.md) -> **GM supprimes en modif 2 (IDE 129)**

```mermaid
graph LR
    T129[129 GM supprimes en mo...]
    style T129 fill:#58a6ff
    CC234[234 Traitement Annulat...]
    style CC234 fill:#8b5cf6
    CC228[228 Traitement Annulat...]
    style CC228 fill:#8b5cf6
    CC206[206 Traitement des arr...]
    style CC206 fill:#8b5cf6
    CC94[94 Module Sejours Call...]
    style CC94 fill:#8b5cf6
    CC82[82 Suppression Client]
    style CC82 fill:#3fb950
    CC94 --> CC82
    CC206 --> CC82
    CC228 --> CC82
    CC234 --> CC82
    CC82 --> T129
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [82](PBG-IDE-82.md) |    Suppression Client | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T129[129 GM supprimes en mo...]
    style T129 fill:#58a6ff
    NONE[Aucun callee]
    T129 -.-> NONE
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
| Expressions | 7 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 22) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 0 ecran, 1 traitement)

- **Strategie** : 1 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| pms_printer_dispo | Table WRITE (Temp) | 1x | Schema + repository |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 09:36*
