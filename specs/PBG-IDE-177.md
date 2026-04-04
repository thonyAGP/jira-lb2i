# PBG IDE 177 - Marquage Caisse(S)

> **Analyse**: Phases 1-4 2026-02-03 09:58 -> 09:58 (21s) | Assemblage 09:58
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBG |
| IDE Position | 177 |
| Nom Programme | Marquage Caisse(S) |
| Fichier source | `Prg_177.xml` |
| Domaine metier | Caisse |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Marquage Caisse(S)** assure la gestion complete de ce processus, accessible depuis [Gestion Groupe Arr/dep pms-656 (IDE 106)](PBG-IDE-106.md), [Validation Arrivants (IDE 124)](PBG-IDE-124.md), [    Validation Auto seminaire (IDE 122)](PBG-IDE-122.md), [Traitement Annulation Existant (IDE 228)](PBG-IDE-228.md), [Traitement Annulation sur modi (IDE 234)](PBG-IDE-234.md), [Traitement Annulation/pms-682 (IDE 235)](PBG-IDE-235.md), [Traitement Annulation/pms-912 (IDE 236)](PBG-IDE-236.md), [Traitement Annulation (IDE 238)](PBG-IDE-238.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

**Donnees modifiees** : 1 tables en ecriture (compte_gm________cgm).

**Logique metier** : 1 regles identifiees couvrant conditions metier.

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>177 - Marquage Caisse

**Role** : Traitement : Marquage Caisse.


## 5. REGLES METIER

1 regles identifiees:

### Autres (1 regles)

#### <a id="rm-RM-001"></a>[RM-001] Si [F]='R' alors 'N' sinon 'O')

| Element | Detail |
|---------|--------|
| **Condition** | `[F]='R'` |
| **Si vrai** | 'N' |
| **Si faux** | 'O') |
| **Expression source** | Expression 3 : `IF ([F]='R','N','O')` |
| **Exemple** | Si [F]='R' â†’ 'N'. Sinon â†’ 'O') |

## 6. CONTEXTE

- **Appele par**: [Gestion Groupe Arr/dep pms-656 (IDE 106)](PBG-IDE-106.md), [Validation Arrivants (IDE 124)](PBG-IDE-124.md), [    Validation Auto seminaire (IDE 122)](PBG-IDE-122.md), [Traitement Annulation Existant (IDE 228)](PBG-IDE-228.md), [Traitement Annulation sur modi (IDE 234)](PBG-IDE-234.md), [Traitement Annulation/pms-682 (IDE 235)](PBG-IDE-235.md), [Traitement Annulation/pms-912 (IDE 236)](PBG-IDE-236.md), [Traitement Annulation (IDE 238)](PBG-IDE-238.md)
- **Appelle**: 0 programmes | **Tables**: 1 (W:1 R:0 L:0) | **Taches**: 1 | **Expressions**: 6

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **177.1** | [**Marquage Caisse** (177)](#t1) | MDI | - | Traitement |

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
| 47 | compte_gm________cgm | Comptes GM (generaux) | DB |   | **W** |   | 1 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 47 - compte_gm________cgm (**W**) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P0-Code Societe | W | Alpha |
| B | P0-Numero Compte | W | Numeric |
| C | P0-Autorisation | W | Alpha |

</details>

## 11. VARIABLES

### 11.1 Autres (3)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P0-Code Societe | Alpha | 1x refs |
| B | P0-Numero Compte | Numeric | 1x refs |
| C | P0-Autorisation | Alpha | 1x refs |

## 12. EXPRESSIONS

**6 / 6 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONDITION | 2 | 5 |
| CONSTANTE | 1 | 0 |
| OTHER | 3 | 0 |

### 12.2 Expressions cles par type

#### CONDITION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 3 | `IF ([F]='R','N','O')` | [RM-001](#rm-RM-001) |
| CONDITION | 6 | `P0-Autorisation [C]='O'` | - |

#### CONSTANTE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 5 | `'R'` | - |

#### OTHER (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 4 | `[F]` | - |
| OTHER | 2 | `P0-Numero Compte [B]` | - |
| OTHER | 1 | `P0-Code Societe [A]` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Gestion Groupe Arr/dep pms-656 (IDE 106)](PBG-IDE-106.md) -> **Marquage Caisse(S) (IDE 177)**

Main -> ... -> [Validation Arrivants (IDE 124)](PBG-IDE-124.md) -> **Marquage Caisse(S) (IDE 177)**

Main -> ... -> [    Validation Auto seminaire (IDE 122)](PBG-IDE-122.md) -> **Marquage Caisse(S) (IDE 177)**

Main -> ... -> [Traitement Annulation Existant (IDE 228)](PBG-IDE-228.md) -> **Marquage Caisse(S) (IDE 177)**

Main -> ... -> [Traitement Annulation sur modi (IDE 234)](PBG-IDE-234.md) -> **Marquage Caisse(S) (IDE 177)**

Main -> ... -> [Traitement Annulation/pms-682 (IDE 235)](PBG-IDE-235.md) -> **Marquage Caisse(S) (IDE 177)**

Main -> ... -> [Traitement Annulation/pms-912 (IDE 236)](PBG-IDE-236.md) -> **Marquage Caisse(S) (IDE 177)**

Main -> ... -> [Traitement Annulation (IDE 238)](PBG-IDE-238.md) -> **Marquage Caisse(S) (IDE 177)**

```mermaid
graph LR
    T177[177 Marquage CaisseS]
    style T177 fill:#58a6ff
    CC206[206 Traitement des arr...]
    style CC206 fill:#8b5cf6
    CC234[234 Traitement Annulat...]
    style CC234 fill:#3fb950
    CC106[106 Gestion Groupe Arr...]
    style CC106 fill:#3fb950
    CC228[228 Traitement Annulat...]
    style CC228 fill:#3fb950
    CC122[122 Validation Auto se...]
    style CC122 fill:#3fb950
    CC124[124 Validation Arrivants]
    style CC124 fill:#3fb950
    CC206 --> CC106
    CC206 --> CC122
    CC206 --> CC124
    CC206 --> CC228
    CC206 --> CC234
    CC106 --> T177
    CC122 --> T177
    CC124 --> T177
    CC228 --> T177
    CC234 --> T177
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [106](PBG-IDE-106.md) | Gestion Groupe Arr/dep pms-656 | 2 |
| [124](PBG-IDE-124.md) | Validation Arrivants | 2 |
| [122](PBG-IDE-122.md) |     Validation Auto seminaire | 1 |
| [228](PBG-IDE-228.md) | Traitement Annulation Existant | 1 |
| [234](PBG-IDE-234.md) | Traitement Annulation sur modi | 1 |
| [235](PBG-IDE-235.md) | Traitement Annulation/pms-682 | 1 |
| [236](PBG-IDE-236.md) | Traitement Annulation/pms-912 | 1 |
| [238](PBG-IDE-238.md) | Traitement Annulation | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T177[177 Marquage CaisseS]
    style T177 fill:#58a6ff
    NONE[Aucun callee]
    T177 -.-> NONE
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
| Lignes de logique | 13 | Programme compact |
| Expressions | 6 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 13) | Code sain |
| Regles metier | 1 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 0 ecran, 1 traitement)

- **Strategie** : 1 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| compte_gm________cgm | Table WRITE (Database) | 1x | Schema + repository |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 09:58*
