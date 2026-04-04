# PBG IDE 214 - Traitement des Sejours reprise

> **Analyse**: Phases 1-4 2026-02-03 10:15 -> 10:15 (20s) | Assemblage 10:15
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBG |
| IDE Position | 214 |
| Nom Programme | Traitement des Sejours reprise |
| Fichier source | `Prg_214.xml` |
| Domaine metier | General |
| Taches | 7 (1 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 1 |
| :warning: Statut | **ORPHELIN_POTENTIEL** |

## 2. DESCRIPTION FONCTIONNELLE

**Traitement des Sejours reprise** assure la gestion complete de ce processus.

Le flux de traitement s'organise en **2 blocs fonctionnels** :

- **Creation** (4 taches) : insertion d'enregistrements en base (mouvements, prestations)
- **Traitement** (3 taches) : traitements metier divers

**Donnees modifiees** : 1 tables en ecriture (voyages__________voy).

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (3 taches)

- **214** - Veuillez patienter... **[[ECRAN]](#ecran-t1)**
- **214.1** - Heure Diff
- **214.2** - Determination Periodes

Delegue a : [Suppression vol doublons (IDE 339)](PBG-IDE-339.md)

#### Phase 2 : Creation (4 taches)

- **214.2.1** - Creation Voyage Aller
- **214.2.2** - Creation Voyage Aller
- **214.2.3** - Creation Voyage Aller
- **214.2.4** - Creation Voyage Aller

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| voyages__________voy | **W** (4 usages) |  |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (3 taches)

Traitements internes.

---

#### <a id="t1"></a>214 - Veuillez patienter... [[ECRAN]](#ecran-t1)

**Role** : Traitement : Veuillez patienter....
**Ecran** : 429 x 70 DLU (MDI) | [Voir mockup](#ecran-t1)
**Delegue a** : [Suppression vol doublons (IDE 339)](PBG-IDE-339.md)

---

#### <a id="t2"></a>214.1 - Heure Diff

**Role** : Traitement : Heure Diff.
**Variables liees** : H (W0 Heure diff aller -1), I (W0 Heure diff retour)
**Delegue a** : [Suppression vol doublons (IDE 339)](PBG-IDE-339.md)

---

#### <a id="t3"></a>214.2 - Determination Periodes

**Role** : Traitement : Determination Periodes.
**Delegue a** : [Suppression vol doublons (IDE 339)](PBG-IDE-339.md)


### 3.2 Creation (4 taches)

Insertion de nouveaux enregistrements en base.

---

#### <a id="t4"></a>214.2.1 - Creation Voyage Aller

**Role** : Creation d'enregistrement : Creation Voyage Aller.
**Variables liees** : H (W0 Heure diff aller -1)

---

#### <a id="t5"></a>214.2.2 - Creation Voyage Aller

**Role** : Creation d'enregistrement : Creation Voyage Aller.
**Variables liees** : H (W0 Heure diff aller -1)

---

#### <a id="t6"></a>214.2.3 - Creation Voyage Aller

**Role** : Creation d'enregistrement : Creation Voyage Aller.
**Variables liees** : H (W0 Heure diff aller -1)

---

#### <a id="t7"></a>214.2.4 - Creation Voyage Aller

**Role** : Creation d'enregistrement : Creation Voyage Aller.
**Variables liees** : H (W0 Heure diff aller -1)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: (aucun)
- **Appelle**: 1 programmes | **Tables**: 7 (W:1 R:3 L:3) | **Taches**: 7 | **Expressions**: 14

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 7)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 214 | 214 | Veuillez patienter... | MDI | 429 | 70 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>214 - Veuillez patienter...
**Tache** : [214](#t1) | **Type** : MDI | **Dimensions** : 429 x 70 DLU
**Bloc** : Traitement | **Titre IDE** : Veuillez patienter...

<!-- FORM-DATA:
{
    "width":  429,
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
                         "text":  "Reprise des vols",
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
                         "h":  37,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  9,
                         "type":  "label",
                         "var":  "",
                         "y":  41,
                         "w":  405,
                         "fmt":  "",
                         "name":  "",
                         "h":  19,
                         "color":  "",
                         "text":  "",
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
                     },
                     {
                         "x":  12,
                         "type":  "edit",
                         "var":  "",
                         "y":  42,
                         "w":  400,
                         "fmt":  "30",
                         "name":  "",
                         "h":  17,
                         "color":  "159",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  177,
                         "type":  "edit",
                         "var":  "",
                         "y":  46,
                         "w":  64,
                         "fmt":  "3 %",
                         "name":  "",
                         "h":  8,
                         "color":  "143",
                         "text":  "",
                         "parent":  1
                     }
                 ],
    "taskId":  "214",
    "height":  70
}
-->

<details>
<summary><strong>Champs : 2 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 12,42 | 30 | - | edit |
| 177,46 | 3 % | - | edit |

</details>

## 9. NAVIGATION

Ecran unique: **Veuillez patienter...**

### 9.3 Structure hierarchique (7 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **214.1** | [**Veuillez patienter...** (214)](#t1) [mockup](#ecran-t1) | MDI | 429x70 | Traitement |
| 214.1.1 | [Heure Diff (214.1)](#t2) | MDI | - | |
| 214.1.2 | [Determination Periodes (214.2)](#t3) | MDI | - | |
| **214.2** | [**Creation Voyage Aller** (214.2.1)](#t4) | MDI | - | Creation |
| 214.2.1 | [Creation Voyage Aller (214.2.2)](#t5) | MDI | - | |
| 214.2.2 | [Creation Voyage Aller (214.2.3)](#t6) | MDI | - | |
| 214.2.3 | [Creation Voyage Aller (214.2.4)](#t7) | MDI | - | |

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

### Tables utilisees (7)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 29 | voyages__________voy |  | DB |   | **W** |   | 4 |
| 34 | hebergement______heb | Hebergement (chambres) | DB | R |   |   | 1 |
| 113 | tables_village |  | DB | R |   |   | 1 |
| 132 | code_vol_________vot |  | DB |   |   | L | 4 |
| 569 | pointage_articles_caution | Articles et stock | TMP | R |   |   | 1 |
| 571 | inter_prestation_inp | Prestations/services vendus | TMP |   |   | L | 1 |
| 576 | temp_recap_sessions | Sessions de caisse | TMP |   |   | L | 1 |

### Colonnes par table (3 / 4 tables avec colonnes identifiees)

<details>
<summary>Table 29 - voyages__________voy (**W**) - 4 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 34 - hebergement______heb (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | v.compagnie Aller | R | Unicode |
| B | v.compagnie Aller Differe -1 | R | Unicode |
| C | v.compagnie Aller Differe +1 | R | Unicode |
| D | W1 Vol Retour ? | R | Numeric |
| E | v.compagnie Retour | R | Unicode |
| F | v.compagnie Depart Differe +1 | R | Unicode |
| G | W1 Vol Aller ? | R | Numeric |
| H | W1 Vol Aller Dif -1? | R | Numeric |
| I | W1 Vol Aller Dif +1? | R | Numeric |
| J | W1 Vol Retour Dif ? | R | Numeric |

</details>

<details>
<summary>Table 113 - tables_village (R) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 569 - pointage_articles_caution (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P0-Code Societe | R | Alpha |
| B | P0-Lieu de Sejour | R | Alpha |
| C | P0-Nb Arrivants | R | Numeric |
| D | W0-Operande | R | Numeric |
| E | W0-Operateur | R | Numeric |
| F | W0-Pourcentage | R | Numeric |
| G | W0-Calcul Pourcent | R | Numeric |
| H | W0 Heure diff aller -1 | R | Numeric |
| I | W0 Heure diff retour | R | Numeric |
| J | W0-Alerte | R | Alpha |

</details>

## 11. VARIABLES

### 11.1 Variables de travail (2)

Variables internes au programme.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| H | W0 Heure diff aller -1 | Numeric | - |
| I | W0 Heure diff retour | Numeric | - |

### 11.2 Autres (8)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P0-Code Societe | Alpha | 1x refs |
| B | P0-Lieu de Sejour | Alpha | - |
| C | P0-Nb Arrivants | Numeric | 3x refs |
| D | W0-Operande | Numeric | - |
| E | W0-Operateur | Numeric | 2x refs |
| F | W0-Pourcentage | Numeric | 2x refs |
| G | W0-Calcul Pourcent | Numeric | 1x refs |
| J | W0-Alerte | Alpha | - |

## 12. EXPRESSIONS

**14 / 14 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCULATION | 5 | 0 |
| CONSTANTE | 3 | 0 |
| CONDITION | 2 | 0 |
| OTHER | 3 | 0 |
| REFERENCE_VG | 1 | 0 |

### 12.2 Expressions cles par type

#### CALCULATION (5 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 9 | `W0-Operateur [E]/W0-Calcul Pourcent [G]` | - |
| CALCULATION | 10 | `W0-Operateur [E]+1` | - |
| CALCULATION | 8 | `P0-Nb Arrivants [C]/98` | - |
| CALCULATION | 5 | `W0-Pourcentage [F]/2` | - |
| CALCULATION | 7 | `P0-Nb Arrivants [C]/29` | - |

#### CONSTANTE (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 14 | `1` | - |
| CONSTANTE | 12 | `'C'` | - |
| CONSTANTE | 3 | `''` | - |

#### CONDITION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 2 | `P0-Nb Arrivants [C]=0` | - |
| CONDITION | 1 | `P0-Code Societe [A]=''` | - |

#### OTHER (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 13 | `DbRecs ('{569,2}'DSOURCE,'')` | - |
| OTHER | 11 | `[M]` | - |
| OTHER | 4 | `W0-Pourcentage [F]` | - |

#### REFERENCE_VG (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 6 | `VG20` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

**Chemin**: (pas de callers directs)

```mermaid
graph LR
    T214[214 Traitement des Sej...]
    style T214 fill:#58a6ff
    NONE[Aucun caller]
    NONE -.-> T214
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| - | (aucun) | - |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T214[214 Traitement des Sej...]
    style T214 fill:#58a6ff
    C339[339 Suppression vol do...]
    T214 --> C339
    style C339 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [339](PBG-IDE-339.md) | Suppression vol doublons | 1 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 260 | Taille moyenne |
| Expressions | 14 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 1 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 260) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (3 taches: 1 ecran, 2 traitements)

- **Strategie** : Orchestrateur avec 1 ecrans (Razor/React) et 2 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 1 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Creation (4 taches: 0 ecran, 4 traitements)

- **Strategie** : Repository pattern avec Entity Framework Core.
- Insertion via `IRepository<T>.CreateAsync()`

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| voyages__________voy | Table WRITE (Database) | 4x | Schema + repository |
| [Suppression vol doublons (IDE 339)](PBG-IDE-339.md) | Sous-programme | 1x | Normale - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 10:15*
