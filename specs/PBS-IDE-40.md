# PBS IDE 40 - Suppression Logement Exterieur

> **Analyse**: Phases 1-4 2026-02-03 17:13 -> 17:13 (13s) | Assemblage 17:13
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBS |
| IDE Position | 40 |
| Nom Programme | Suppression Logement Exterieur |
| Fichier source | `Prg_40.xml` |
| Dossier IDE | Logement |
| Taches | 9 (1 ecrans visibles) |
| Tables modifiees | 6 |
| Programmes appeles | 1 |

## 2. DESCRIPTION FONCTIONNELLE

**Suppression Logement Exterieur** assure la gestion complete de ce processus, accessible depuis [Logement exterieur (IDE 38)](PBS-IDE-38.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (9 taches) : traitements metier divers

**Donnees modifiees** : 6 tables en ecriture (fichier_menage, logement_complement, logement_exterieurs, logement_zone_menage, tables_village, nb_code__poste).

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (9 taches)

- **40** - Suppression Logement Exterieur **[[ECRAN]](#ecran-t1)**
- **40.1** - Suppression Logement Batch **[[ECRAN]](#ecran-t2)**
- **40.1.1** - Suppression Logement **[[ECRAN]](#ecran-t3)**
- **40.1.1.1** - Decrementations Tables
- **40.1.1.2** - Suppression Telephone
- **40.1.1.3** - Suppression Complements
- **40.1.1.3.1** - Suppression Complements lies
- **40.1.2** - Suppression Menage
- **40.1.2.1** - Decrementations Tables

Delegue a : [ Logement Libre ? (IDE 25)](PBS-IDE-25.md)

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| logement_complement | **W** (2 usages) |  |
| logement_exterieurs | **W** (1 usages) |  |
| logement_zone_menage | **W** (1 usages) |  |
| nb_code__poste | **W** (1 usages) |  |
| tables_village | **W** (1 usages) |  |
| fichier_menage | **W** (1 usages) |  |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (9 taches)

Traitements internes.

---

#### <a id="t1"></a>40 - Suppression Logement Exterieur [[ECRAN]](#ecran-t1)

**Role** : Tache d'orchestration : point d'entree du programme (9 sous-taches). Coordonne l'enchainement des traitements.
**Ecran** : 166 x 23 DLU (MDI) | [Voir mockup](#ecran-t1)

<details>
<summary>8 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [40.1](#t2) | Suppression Logement Batch **[[ECRAN]](#ecran-t2)** | Traitement |
| [40.1.1](#t3) | Suppression Logement **[[ECRAN]](#ecran-t3)** | Traitement |
| [40.1.1.1](#t4) | Decrementations Tables | Traitement |
| [40.1.1.2](#t5) | Suppression Telephone | Traitement |
| [40.1.1.3](#t6) | Suppression Complements | Traitement |
| [40.1.1.3.1](#t7) | Suppression Complements lies | Traitement |
| [40.1.2](#t9) | Suppression Menage | Traitement |
| [40.1.2.1](#t10) | Decrementations Tables | Traitement |

</details>
**Delegue a** : [ Logement Libre ? (IDE 25)](PBS-IDE-25.md)

---

#### <a id="t2"></a>40.1 - Suppression Logement Batch [[ECRAN]](#ecran-t2)

**Role** : Traitement : Suppression Logement Batch.
**Ecran** : 424 x 56 DLU (MDI) | [Voir mockup](#ecran-t2)
**Delegue a** : [ Logement Libre ? (IDE 25)](PBS-IDE-25.md)

---

#### <a id="t3"></a>40.1.1 - Suppression Logement [[ECRAN]](#ecran-t3)

**Role** : Traitement : Suppression Logement.
**Ecran** : 821 x 181 DLU (MDI) | [Voir mockup](#ecran-t3)
**Delegue a** : [ Logement Libre ? (IDE 25)](PBS-IDE-25.md)

---

#### <a id="t4"></a>40.1.1.1 - Decrementations Tables

**Role** : Traitement : Decrementations Tables.
**Delegue a** : [ Logement Libre ? (IDE 25)](PBS-IDE-25.md)

---

#### <a id="t5"></a>40.1.1.2 - Suppression Telephone

**Role** : Traitement : Suppression Telephone.
**Delegue a** : [ Logement Libre ? (IDE 25)](PBS-IDE-25.md)

---

#### <a id="t6"></a>40.1.1.3 - Suppression Complements

**Role** : Traitement : Suppression Complements.
**Delegue a** : [ Logement Libre ? (IDE 25)](PBS-IDE-25.md)

---

#### <a id="t7"></a>40.1.1.3.1 - Suppression Complements lies

**Role** : Traitement : Suppression Complements lies.
**Delegue a** : [ Logement Libre ? (IDE 25)](PBS-IDE-25.md)

---

#### <a id="t9"></a>40.1.2 - Suppression Menage

**Role** : Traitement : Suppression Menage.
**Delegue a** : [ Logement Libre ? (IDE 25)](PBS-IDE-25.md)

---

#### <a id="t10"></a>40.1.2.1 - Decrementations Tables

**Role** : Traitement : Decrementations Tables.
**Delegue a** : [ Logement Libre ? (IDE 25)](PBS-IDE-25.md)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Logement exterieur (IDE 38)](PBS-IDE-38.md)
- **Appelle**: 1 programmes | **Tables**: 6 (W:6 R:0 L:0) | **Taches**: 9 | **Expressions**: 5

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 9)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 40.1 | 40.1 | Suppression Logement Batch | MDI | 424 | 56 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t2"></a>40.1 - Suppression Logement Batch
**Tache** : [40.1](#t2) | **Type** : MDI | **Dimensions** : 424 x 56 DLU
**Bloc** : Traitement | **Titre IDE** : Suppression Logement Batch

<!-- FORM-DATA:
{
    "width":  424,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  1,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  423,
                         "fmt":  "",
                         "name":  "",
                         "h":  29,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  99,
                         "type":  "label",
                         "var":  "",
                         "y":  10,
                         "w":  275,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "7",
                         "text":  "Logement Exterieur",
                         "parent":  null
                     },
                     {
                         "x":  1,
                         "type":  "label",
                         "var":  "",
                         "y":  29,
                         "w":  423,
                         "fmt":  "",
                         "name":  "",
                         "h":  27,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  55,
                         "type":  "label",
                         "var":  "",
                         "y":  39,
                         "w":  316,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Suppression Logement en cours",
                         "parent":  null
                     },
                     {
                         "x":  2,
                         "type":  "image",
                         "var":  "",
                         "y":  2,
                         "w":  72,
                         "fmt":  "",
                         "name":  "",
                         "h":  25,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "40.1",
    "height":  56
}
-->

## 9. NAVIGATION

Ecran unique: **Suppression Logement Batch**

### 9.3 Structure hierarchique (9 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **40.1** | [**Suppression Logement Exterieur** (40)](#t1) [mockup](#ecran-t1) | MDI | 166x23 | Traitement |
| 40.1.1 | [Suppression Logement Batch (40.1)](#t2) [mockup](#ecran-t2) | MDI | 424x56 | |
| 40.1.2 | [Suppression Logement (40.1.1)](#t3) [mockup](#ecran-t3) | MDI | 821x181 | |
| 40.1.3 | [Decrementations Tables (40.1.1.1)](#t4) | MDI | - | |
| 40.1.4 | [Suppression Telephone (40.1.1.2)](#t5) | MDI | - | |
| 40.1.5 | [Suppression Complements (40.1.1.3)](#t6) | MDI | - | |
| 40.1.6 | [Suppression Complements lies (40.1.1.3.1)](#t7) | MDI | - | |
| 40.1.7 | [Suppression Menage (40.1.2)](#t9) | MDI | - | |
| 40.1.8 | [Decrementations Tables (40.1.2.1)](#t10) | MDI | - | |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Suppression Logement B...]
    UPDATE[MAJ 6 tables]
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

### Tables utilisees (6)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 104 | fichier_menage |  | DB |   | **W** |   | 1 |
| 105 | logement_complement |  | DB |   | **W** |   | 2 |
| 106 | logement_exterieurs |  | DB |   | **W** |   | 1 |
| 107 | logement_zone_menage |  | DB |   | **W** |   | 1 |
| 113 | tables_village |  | DB |   | **W** |   | 1 |
| 151 | nb_code__poste |  | DB |   | **W** |   | 1 |

### Colonnes par table (4 / 6 tables avec colonnes identifiees)

<details>
<summary>Table 104 - fichier_menage (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 105 - logement_complement (**W**) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | > Code Complement | W | Alpha |

</details>

<details>
<summary>Table 106 - logement_exterieurs (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 107 - logement_zone_menage (**W**) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | > Zone/Secteur | W | Alpha |

</details>

<details>
<summary>Table 113 - tables_village (**W**) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | > nom table | W | Alpha |
| B | > Code Alpha6 | W | Alpha |

</details>

<details>
<summary>Table 151 - nb_code__poste (**W**) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | > Code Complement | W | Alpha |
| B | > Code Alpha6 | W | Alpha |

</details>

## 11. VARIABLES

### 11.1 Variables de session (2)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| B | v.Contrôle | Logical | 1x session |
| C | v.Reponse | Numeric | 1x session |

### 11.2 Autres (1)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | > Nom Standard | Alpha | - |

## 12. EXPRESSIONS

**5 / 5 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| OTHER | 4 | 0 |
| CONDITION | 1 | 0 |

### 12.2 Expressions cles par type

#### OTHER (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 4 | `SetCrsr (1)` | - |
| OTHER | 5 | `SetCrsr (1)` | - |
| OTHER | 1 | `v.Contrôle [B]` | - |
| OTHER | 3 | `SetCrsr (2)` | - |

#### CONDITION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 2 | `v.Reponse [C]=6` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Logement exterieur (IDE 38)](PBS-IDE-38.md) -> **Suppression Logement Exterieur (IDE 40)**

```mermaid
graph LR
    T40[40 Suppression Logemen...]
    style T40 fill:#58a6ff
    CC38[38 Logement exterieur]
    style CC38 fill:#8b5cf6
    CC38 --> T40
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [38](PBS-IDE-38.md) | Logement exterieur | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T40[40 Suppression Logemen...]
    style T40 fill:#58a6ff
    C25[25 Logement Libre]
    T40 --> C25
    style C25 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [25](PBS-IDE-25.md) |  Logement Libre ? | 1 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 79 | Programme compact |
| Expressions | 5 | Peu de logique |
| Tables WRITE | 6 | Fort impact donnees |
| Sous-programmes | 1 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 79) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (9 taches: 3 ecrans, 6 traitements)

- **Strategie** : Orchestrateur avec 3 ecrans (Razor/React) et 6 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 1 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| fichier_menage | Table WRITE (Database) | 1x | Schema + repository |
| logement_complement | Table WRITE (Database) | 2x | Schema + repository |
| logement_exterieurs | Table WRITE (Database) | 1x | Schema + repository |
| logement_zone_menage | Table WRITE (Database) | 1x | Schema + repository |
| tables_village | Table WRITE (Database) | 1x | Schema + repository |
| nb_code__poste | Table WRITE (Database) | 1x | Schema + repository |
| [ Logement Libre ? (IDE 25)](PBS-IDE-25.md) | Sous-programme | 1x | Normale - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 17:13*
