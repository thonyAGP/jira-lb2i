# REF IDE 759 - suppress circuit

> **Analyse**: Phases 1-4 2026-02-03 14:12 -> 14:12 (14s) | Assemblage 14:12
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | REF |
| IDE Position | 759 |
| Nom Programme | suppress circuit |
| Fichier source | `Prg_759.xml` |
| Dossier IDE | General |
| Taches | 3 (0 ecrans visibles) |
| Tables modifiees | 3 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**suppress circuit** assure la gestion complete de ce processus, accessible depuis [lancement reparation (IDE 749)](REF-IDE-749.md).

Le flux de traitement s'organise en **3 blocs fonctionnels** :

- **Creation** (1 tache) : insertion d'enregistrements en base (mouvements, prestations)
- **Validation** (1 tache) : controles et verifications de coherence
- **Traitement** (1 tache) : traitements metier divers

**Donnees modifiees** : 3 tables en ecriture (heb_circuit______hci, Selection des noms a supprimer, Circuit supprime).

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (1 tache)

- **759** - suppress circuit

#### Phase 2 : Validation (1 tache)

- **759.1** - validation **[[ECRAN]](#ecran-t2)**

#### Phase 3 : Creation (1 tache)

- **759.1.1** - ajout dans trace

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| Circuit supprime | **W**/L (2 usages) |  |
| Selection des noms a supprimer | **W** (1 usages) |  |
| heb_circuit______hci | **W** (1 usages) | Hebergement (chambres) |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>759 - suppress circuit

**Role** : Traitement : suppress circuit.


### 3.2 Validation (1 tache)

Controles de coherence : 1 tache verifie les donnees et conditions.

---

#### <a id="t2"></a>759.1 - validation [[ECRAN]](#ecran-t2)

**Role** : Verification : validation.
**Ecran** : 375 x 23 DLU (MDI) | [Voir mockup](#ecran-t2)


### 3.3 Creation (1 tache)

Insertion de nouveaux enregistrements en base.

---

#### <a id="t3"></a>759.1.1 - ajout dans trace

**Role** : Creation d'enregistrement : ajout dans trace.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [lancement reparation (IDE 749)](REF-IDE-749.md)
- **Appelle**: 0 programmes | **Tables**: 3 (W:3 R:0 L:1) | **Taches**: 3 | **Expressions**: 1

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (3 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **759.1** | [**suppress circuit** (759)](#t1) | MDI | - | Traitement |
| **759.2** | [**validation** (759.1)](#t2) [mockup](#ecran-t2) | MDI | 375x23 | Validation |
| **759.3** | [**ajout dans trace** (759.1.1)](#t3) | MDI | - | Creation |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Traitement principal]
    UPDATE[MAJ 3 tables]
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

### Tables utilisees (3)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 168 | heb_circuit______hci | Hebergement (chambres) | DB |   | **W** |   | 1 |
| 808 | Selection des noms a supprimer |  | DB |   | **W** |   | 1 |
| 818 | Circuit supprime |  | DB |   | **W** | L | 2 |

### Colonnes par table (1 / 3 tables avec colonnes identifiees)

<details>
<summary>Table 168 - heb_circuit______hci (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 808 - Selection des noms a supprimer (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 818 - Circuit supprime (**W**/L) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | V. Nombre de gm's supprimes | W | Numeric |

</details>

## 11. VARIABLES

*(Programme sans variables locales mappees)*

## 12. EXPRESSIONS

**1 / 1 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| OTHER | 1 | 0 |

### 12.2 Expressions cles par type

#### OTHER (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 1 | `Counter (0)` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [lancement reparation (IDE 749)](REF-IDE-749.md) -> **suppress circuit (IDE 759)**

```mermaid
graph LR
    T759[759 suppress circuit]
    style T759 fill:#58a6ff
    CC749[749 lancement reparation]
    style CC749 fill:#8b5cf6
    CC749 --> T759
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [749](REF-IDE-749.md) | lancement reparation | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T759[759 suppress circuit]
    style T759 fill:#58a6ff
    NONE[Aucun callee]
    T759 -.-> NONE
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
| Lignes de logique | 15 | Programme compact |
| Expressions | 1 | Peu de logique |
| Tables WRITE | 3 | Impact modere |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 15) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 0 ecran, 1 traitement)

- **Strategie** : 1 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

#### Validation (1 tache: 1 ecran, 0 traitement)

- **Strategie** : FluentValidation avec validators specifiques.
- Chaque tache de validation -> un validator injectable

#### Creation (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Repository pattern avec Entity Framework Core.
- Insertion via `IRepository<T>.CreateAsync()`

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| heb_circuit______hci | Table WRITE (Database) | 1x | Schema + repository |
| Selection des noms a supprimer | Table WRITE (Database) | 1x | Schema + repository |
| Circuit supprime | Table WRITE (Database) | 1x | Schema + repository |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 14:12*
