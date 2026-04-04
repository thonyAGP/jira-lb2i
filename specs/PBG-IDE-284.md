# PBG IDE 284 - Traitement Prestations new

> **Analyse**: Phases 1-4 2026-02-03 10:50 -> 10:50 (19s) | Assemblage 10:50
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBG |
| IDE Position | 284 |
| Nom Programme | Traitement Prestations new |
| Fichier source | `Prg_284.xml` |
| Domaine metier | General |
| Taches | 6 (0 ecrans visibles) |
| Tables modifiees | 5 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Traitement Prestations new** assure la gestion complete de ce processus, accessible depuis [Traitement des arrivants (IDE 206)](PBG-IDE-206.md).

Le flux de traitement s'organise en **2 blocs fonctionnels** :

- **Creation** (4 taches) : insertion d'enregistrements en base (mouvements, prestations)
- **Traitement** (2 taches) : traitements metier divers

**Donnees modifiees** : 5 tables en ecriture (gm-complet_______gmc, prestations______pre, libelle_prestation, comptage_caisse, tempo_date_heure).

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (2 taches)

- **284** - Veuillez patienter... **[[ECRAN]](#ecran-t1)**
- **284.4.1** - Nouvelle

#### Phase 2 : Creation (4 taches)

- **284.1** - Creation Honey Moon
- **284.2** - Creation Circuit
- **284.3** - Creation Circuit
- **284.4** - Creation Table Prestation

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| tempo_date_heure | **W** (1 usages) | Table temporaire ecran |
| prestations______pre | **W** (1 usages) | Prestations/services vendus |
| libelle_prestation | **W** (1 usages) | Prestations/services vendus |
| gm-complet_______gmc | **W** (1 usages) |  |
| comptage_caisse | **W** (1 usages) | Sessions de caisse |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (2 taches)

Traitements internes.

---

#### <a id="t1"></a>284 - Veuillez patienter... [[ECRAN]](#ecran-t1)

**Role** : Traitement : Veuillez patienter....
**Ecran** : 429 x 68 DLU (MDI) | [Voir mockup](#ecran-t1)

---

#### <a id="t7"></a>284.4.1 - Nouvelle

**Role** : Creation d'enregistrement : Nouvelle.


### 3.2 Creation (4 taches)

Insertion de nouveaux enregistrements en base.

---

#### <a id="t3"></a>284.1 - Creation Honey Moon

**Role** : Creation d'enregistrement : Creation Honey Moon.
**Variables liees** : F (P0-Honey Moon 1), G (P0-Honey Moon 2), H (P0-Honey Moon 3), I (P0-Honey Moon 4)

---

#### <a id="t4"></a>284.2 - Creation Circuit

**Role** : Creation d'enregistrement : Creation Circuit.
**Variables liees** : N (W0-Ret Lien Circuit)

---

#### <a id="t5"></a>284.3 - Creation Circuit

**Role** : Creation d'enregistrement : Creation Circuit.
**Variables liees** : N (W0-Ret Lien Circuit)

---

#### <a id="t6"></a>284.4 - Creation Table Prestation

**Role** : Creation d'enregistrement : Creation Table Prestation.
**Variables liees** : C (P0-Nb Prestations), D (P0-New Prestation)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Traitement des arrivants (IDE 206)](PBG-IDE-206.md)
- **Appelle**: 0 programmes | **Tables**: 7 (W:5 R:1 L:1) | **Taches**: 6 | **Expressions**: 16

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (6 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **284.1** | [**Veuillez patienter...** (284)](#t1) [mockup](#ecran-t1) | MDI | 429x68 | Traitement |
| 284.1.1 | [Nouvelle (284.4.1)](#t7) | MDI | - | |
| **284.2** | [**Creation Honey Moon** (284.1)](#t3) | MDI | - | Creation |
| 284.2.1 | [Creation Circuit (284.2)](#t4) | MDI | - | |
| 284.2.2 | [Creation Circuit (284.3)](#t5) | MDI | - | |
| 284.2.3 | [Creation Table Prestation (284.4)](#t6) | MDI | - | |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Traitement principal]
    UPDATE[MAJ 5 tables]
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

### Tables utilisees (7)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 31 | gm-complet_______gmc |  | DB |   | **W** |   | 1 |
| 33 | prestations______pre | Prestations/services vendus | DB |   | **W** |   | 1 |
| 135 | libelle_prestation | Prestations/services vendus | DB |   | **W** |   | 1 |
| 473 | comptage_caisse | Sessions de caisse | TMP |   | **W** |   | 1 |
| 569 | pointage_articles_caution | Articles et stock | TMP | R |   |   | 1 |
| 573 | tempo_ecran_mecano | Table temporaire ecran | TMP |   |   | L | 1 |
| 590 | tempo_date_heure | Table temporaire ecran | TMP |   | **W** |   | 1 |

### Colonnes par table (3 / 6 tables avec colonnes identifiees)

<details>
<summary>Table 31 - gm-complet_______gmc (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 33 - prestations______pre (**W**) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| C | P0-Nb Prestations | W | Numeric |

</details>

<details>
<summary>Table 135 - libelle_prestation (**W**) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | V Existe prestation | W | Logical |
| C | P0-Nb Prestations | W | Numeric |
| D | P0-New Prestation | W | Logical |

</details>

<details>
<summary>Table 473 - comptage_caisse (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 569 - pointage_articles_caution (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P0-Code Societe | R | Alpha |
| B | P0-Lieu de Sejour | R | Alpha |
| C | P0-Nb Prestations | R | Numeric |
| D | P0-New Prestation | R | Logical |
| E | P0-Num ressource | R | Numeric |
| F | P0-Honey Moon 1 | R | Alpha |
| G | P0-Honey Moon 2 | R | Alpha |
| H | P0-Honey Moon 3 | R | Alpha |
| I | P0-Honey Moon 4 | R | Alpha |
| J | W0-Operande | R | Numeric |
| K | W0-Operateur | R | Numeric |
| L | W0-Pourcentage | R | Numeric |
| M | W0-Calcul Pourcent | R | Numeric |
| N | W0-Ret Lien Circuit | R | Numeric |
| O | V.Compteur | R | Numeric |

</details>

<details>
<summary>Table 590 - tempo_date_heure (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Variables de session (1)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| O | V.Compteur | Numeric | 1x session |

### 11.2 Autres (14)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P0-Code Societe | Alpha | - |
| B | P0-Lieu de Sejour | Alpha | - |
| C | P0-Nb Prestations | Numeric | 2x refs |
| D | P0-New Prestation | Logical | - |
| E | P0-Num ressource | Numeric | - |
| F | P0-Honey Moon 1 | Alpha | [284.1](#t3) |
| G | P0-Honey Moon 2 | Alpha | - |
| H | P0-Honey Moon 3 | Alpha | [284.1](#t3) |
| I | P0-Honey Moon 4 | Alpha | - |
| J | W0-Operande | Numeric | - |
| K | W0-Operateur | Numeric | - |
| L | W0-Pourcentage | Numeric | - |
| M | W0-Calcul Pourcent | Numeric | - |
| N | W0-Ret Lien Circuit | Numeric | - |

## 12. EXPRESSIONS

**16 / 16 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCULATION | 7 | 0 |
| CONSTANTE | 1 | 0 |
| CAST_LOGIQUE | 1 | 0 |
| REFERENCE_VG | 1 | 0 |
| OTHER | 2 | 0 |
| CONDITION | 4 | 0 |

### 12.2 Expressions cles par type

#### CALCULATION (7 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 8 | `P0-Honey Moon 1 [F]/P0-Honey Moon 3 [H]` | - |
| CALCULATION | 10 | `P0-Honey Moon 1 [F]+1` | - |
| CALCULATION | 15 | `[BQ]+1` | - |
| CALCULATION | 7 | `P0-Nb Prestations [C]/98` | - |
| CALCULATION | 3 | `([BQ]/VG15)*100` | - |
| ... | | *+2 autres* | |

#### CONSTANTE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 2 | `''` | - |

#### CAST_LOGIQUE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 1 | `'FALSE'LOG` | - |

#### REFERENCE_VG (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 5 | `VG20` | - |

#### OTHER (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 16 | `[BR]` | - |
| OTHER | 9 | `V.Compteur [O]` | - |

#### CONDITION (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 14 | `[AH]>'E'` | - |
| CONDITION | 13 | `Trim ([S])<>''` | - |
| CONDITION | 11 | `[R]=[BS] OR [R]=[BT] OR [R]=[BU] OR [R]=[BV]` | - |
| CONDITION | 12 | `[R]<>[BS] AND [R]<>[BT] AND [R]<>[BU] AND [R]<>[BV]
` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Traitement des arrivants (IDE 206)](PBG-IDE-206.md) -> **Traitement Prestations new (IDE 284)**

```mermaid
graph LR
    T284[284 Traitement Prestat...]
    style T284 fill:#58a6ff
    CC206[206 Traitement des arr...]
    style CC206 fill:#8b5cf6
    CC206 --> T284
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [206](PBG-IDE-206.md) | Traitement des arrivants | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T284[284 Traitement Prestat...]
    style T284 fill:#58a6ff
    NONE[Aucun callee]
    T284 -.-> NONE
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
| Lignes de logique | 126 | Programme compact |
| Expressions | 16 | Peu de logique |
| Tables WRITE | 5 | Impact modere |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 126) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (2 taches: 1 ecran, 1 traitement)

- **Strategie** : Orchestrateur avec 1 ecrans (Razor/React) et 1 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- Decomposer les taches en services unitaires testables.

#### Creation (4 taches: 0 ecran, 4 traitements)

- **Strategie** : Repository pattern avec Entity Framework Core.
- Insertion via `IRepository<T>.CreateAsync()`

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| gm-complet_______gmc | Table WRITE (Database) | 1x | Schema + repository |
| prestations______pre | Table WRITE (Database) | 1x | Schema + repository |
| libelle_prestation | Table WRITE (Database) | 1x | Schema + repository |
| comptage_caisse | Table WRITE (Temp) | 1x | Schema + repository |
| tempo_date_heure | Table WRITE (Temp) | 1x | Schema + repository |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 10:51*
