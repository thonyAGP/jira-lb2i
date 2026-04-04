# VIL IDE 51 - Mise à jour tronçons erronés

> **Analyse**: Phases 1-4 2026-02-03 08:56 -> 08:57 (32s) | Assemblage 08:57
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | VIL |
| IDE Position | 51 |
| Nom Programme | Mise à jour tronçons erronés |
| Fichier source | `Prg_51.xml` |
| Domaine metier | General |
| Taches | 4 (0 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Mise à jour tronçons erronés** assure la gestion complete de ce processus, accessible depuis [Pilotage avant sessions (IDE 9)](VIL-IDE-9.md), [CV  Menu Clôture de caisse (IDE 36)](VIL-IDE-36.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (4 taches) : traitements metier divers

**Donnees modifiees** : 1 tables en ecriture (code_vol_________vot).

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (4 taches)

- **51** - Suppression vol doublons
- **51.1** - Suppresion du vol à NULL
- **51.2** - Suppresion du vol à NULL
- **51.3** - Suppresion du vol à NULL

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| code_vol_________vot | **W** (1 usages) |  |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (4 taches)

Traitements internes.

---

#### <a id="t1"></a>51 - Suppression vol doublons

**Role** : Selection par l'operateur : Suppression vol doublons.

<details>
<summary>3 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [51.1](#t2) | Suppresion du vol à NULL | Traitement |
| [51.2](#t3) | Suppresion du vol à NULL | Traitement |
| [51.3](#t6) | Suppresion du vol à NULL | Traitement |

</details>

---

#### <a id="t2"></a>51.1 - Suppresion du vol à NULL

**Role** : Selection par l'operateur : Suppresion du vol à NULL.

---

#### <a id="t3"></a>51.2 - Suppresion du vol à NULL

**Role** : Selection par l'operateur : Suppresion du vol à NULL.

---

#### <a id="t6"></a>51.3 - Suppresion du vol à NULL

**Role** : Selection par l'operateur : Suppresion du vol à NULL.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Pilotage avant sessions (IDE 9)](VIL-IDE-9.md), [CV  Menu Clôture de caisse (IDE 36)](VIL-IDE-36.md)
- **Appelle**: 0 programmes | **Tables**: 2 (W:1 R:0 L:1) | **Taches**: 4 | **Expressions**: 2

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (4 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **51.1** | [**Suppression vol doublons** (51)](#t1) | - | - | Traitement |
| 51.1.1 | [Suppresion du vol à NULL (51.1)](#t2) | - | - | |
| 51.1.2 | [Suppresion du vol à NULL (51.2)](#t3) | - | - | |
| 51.1.3 | [Suppresion du vol à NULL (51.3)](#t6) | - | - | |

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

### Tables utilisees (2)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 132 | code_vol_________vot |  | DB |   | **W** |   | 1 |
| 167 | troncon__________tro |  | DB |   |   | L | 1 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 132 - code_vol_________vot (**W**) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| E | v.code_vol | W | Unicode |

</details>

## 11. VARIABLES

### 11.1 Variables de session (7)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | v.nombre enreg | Numeric | - |
| B | v.societe | Unicode | - |
| C | v.aller_div_retour | Unicode | - |
| D | v.date | Unicode | - |
| E | v.code_vol | Unicode | - |
| F | V.compagnie à retenir | Unicode | 1x session |
| G | V.Plusieurs Compagnie possibl? | Logical | - |

## 12. EXPRESSIONS

**2 / 2 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| OTHER | 1 | 0 |
| CONDITION | 1 | 0 |

### 12.2 Expressions cles par type

#### OTHER (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 2 | `NOT(V.Plusieurs Compagnie ... [G])` | - |

#### CONDITION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 1 | `Trim(V.compagnie à retenir [F])=''` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Pilotage avant sessions (IDE 9)](VIL-IDE-9.md) -> **Mise à jour tronçons erronés (IDE 51)**

Main -> ... -> [CV  Menu Clôture de caisse (IDE 36)](VIL-IDE-36.md) -> **Mise à jour tronçons erronés (IDE 51)**

```mermaid
graph LR
    T51[51 Mise à jour tronçon...]
    style T51 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC78[78 Lance correspittivi]
    style CC78 fill:#8b5cf6
    CC148[148 CV Menu caisse vil...]
    style CC148 fill:#f59e0b
    CC149[149 Start]
    style CC149 fill:#f59e0b
    CC9[9 Pilotage avant sessions]
    style CC9 fill:#3fb950
    CC36[36 CV Menu Clôture de ...]
    style CC36 fill:#3fb950
    CC149 --> CC9
    CC148 --> CC9
    CC149 --> CC36
    CC148 --> CC36
    CC1 --> CC149
    CC78 --> CC149
    CC1 --> CC148
    CC78 --> CC148
    CC9 --> T51
    CC36 --> T51
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [9](VIL-IDE-9.md) | Pilotage avant sessions | 1 |
| [36](VIL-IDE-36.md) | CV  Menu Clôture de caisse | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T51[51 Mise à jour tronçon...]
    style T51 fill:#58a6ff
    NONE[Aucun callee]
    T51 -.-> NONE
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
| Lignes de logique | 66 | Programme compact |
| Expressions | 2 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 66) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (4 taches: 0 ecran, 4 traitements)

- **Strategie** : 4 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| code_vol_________vot | Table WRITE (Database) | 1x | Schema + repository |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 08:57*
