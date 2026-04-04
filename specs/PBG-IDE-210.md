# PBG IDE 210 - Traitement des Prestations TAI

> **Analyse**: Phases 1-4 2026-02-03 10:13 -> 10:13 (18s) | Assemblage 10:13
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBG |
| IDE Position | 210 |
| Nom Programme | Traitement des Prestations TAI |
| Fichier source | `Prg_210.xml` |
| Domaine metier | General |
| Taches | 11 (1 ecrans visibles) |
| Tables modifiees | 7 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Traitement des Prestations TAI** assure la gestion complete de ce processus, accessible depuis [Traitement des arrivants (IDE 206)](PBG-IDE-206.md).

Le flux de traitement s'organise en **2 blocs fonctionnels** :

- **Creation** (6 taches) : insertion d'enregistrements en base (mouvements, prestations)
- **Traitement** (5 taches) : traitements metier divers

**Donnees modifiees** : 7 tables en ecriture (gm-complet_______gmc, initialisation___ini, libelle_prestation, heure_de_passage, comptage_caisse, tempo_date_heure, Table_1104).

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (5 taches)

- **210** - Veuillez patienter... **[[ECRAN]](#ecran-t1)**
- **210.1** - Recuperation Honey Moon
- **210.4.1** - Nouvelle
- **210.6** - Village TAI
- **210.8** - getNbDecimalVillage

#### Phase 2 : Creation (6 taches)

- **210.2** - Creation Honey Moon
- **210.3** - Creation Circuit
- **210.4** - Creation Table Prestation
- **210.5** - Creation TAIGM
- **210.7** - Creation Circuit
- **210.9** - Creation Table Prestation

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| Table_1104 | **W**/L (2 usages) |  |
| gm-complet_______gmc | R/**W** (2 usages) |  |
| heure_de_passage | **W** (1 usages) |  |
| tempo_date_heure | **W** (1 usages) | Table temporaire ecran |
| libelle_prestation | **W** (1 usages) | Prestations/services vendus |
| initialisation___ini | **W** (1 usages) |  |
| comptage_caisse | **W** (1 usages) | Sessions de caisse |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (5 taches)

Traitements internes.

---

#### <a id="t1"></a>210 - Veuillez patienter... [[ECRAN]](#ecran-t1)

**Role** : Traitement : Veuillez patienter....
**Ecran** : 426 x 67 DLU (MDI) | [Voir mockup](#ecran-t1)

<details>
<summary>4 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [210.1](#t2) | Recuperation Honey Moon | Traitement |
| [210.4.1](#t6) | Nouvelle | Traitement |
| [210.6](#t8) | Village TAI | Traitement |
| [210.8](#t10) | getNbDecimalVillage | Traitement |

</details>

---

#### <a id="t2"></a>210.1 - Recuperation Honey Moon

**Role** : Consultation/chargement : Recuperation Honey Moon.
**Variables liees** : J (W0-Honey Moon 1), K (W0-Honey Moon 2), L (W0-Honey Moon 3), M (W0-Honey Moon 4)

---

#### <a id="t6"></a>210.4.1 - Nouvelle

**Role** : Creation d'enregistrement : Nouvelle.

---

#### <a id="t8"></a>210.6 - Village TAI

**Role** : Traitement : Village TAI.
**Variables liees** : R (V. Nombre Decimal Village), N (W0-Village TAI)

---

#### <a id="t10"></a>210.8 - getNbDecimalVillage

**Role** : Consultation/chargement : getNbDecimalVillage.


### 3.2 Creation (6 taches)

Insertion de nouveaux enregistrements en base.

---

#### <a id="t3"></a>210.2 - Creation Honey Moon

**Role** : Creation d'enregistrement : Creation Honey Moon.
**Variables liees** : J (W0-Honey Moon 1), K (W0-Honey Moon 2), L (W0-Honey Moon 3), M (W0-Honey Moon 4)

---

#### <a id="t4"></a>210.3 - Creation Circuit

**Role** : Creation d'enregistrement : Creation Circuit.
**Variables liees** : I (W0-Ret Lien Circuit)

---

#### <a id="t5"></a>210.4 - Creation Table Prestation

**Role** : Creation d'enregistrement : Creation Table Prestation.
**Variables liees** : C (P0-Nb Prestations), D (P0-New Prestation), P (e.Catégorie prestation?)

---

#### <a id="t7"></a>210.5 - Creation TAIGM

**Role** : Creation d'enregistrement : Creation TAIGM.

---

#### <a id="t9"></a>210.7 - Creation Circuit

**Role** : Creation d'enregistrement : Creation Circuit.
**Variables liees** : I (W0-Ret Lien Circuit)

---

#### <a id="t24"></a>210.9 - Creation Table Prestation

**Role** : Creation d'enregistrement : Creation Table Prestation.
**Variables liees** : C (P0-Nb Prestations), D (P0-New Prestation), P (e.Catégorie prestation?)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Traitement des arrivants (IDE 206)](PBG-IDE-206.md)
- **Appelle**: 0 programmes | **Tables**: 14 (W:7 R:4 L:5) | **Taches**: 11 | **Expressions**: 17

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 11)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 210 | 210 | Veuillez patienter... | MDI | 426 | 67 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>210 - Veuillez patienter...
**Tache** : [210](#t1) | **Type** : MDI | **Dimensions** : 426 x 67 DLU
**Bloc** : Traitement | **Titre IDE** : Veuillez patienter...

<!-- FORM-DATA:
{
    "width":  426,
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
                         "text":  "Traitement des Prestations",
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
    "taskId":  "210",
    "height":  67
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

### 9.3 Structure hierarchique (11 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **210.1** | [**Veuillez patienter...** (210)](#t1) [mockup](#ecran-t1) | MDI | 426x67 | Traitement |
| 210.1.1 | [Recuperation Honey Moon (210.1)](#t2) | MDI | - | |
| 210.1.2 | [Nouvelle (210.4.1)](#t6) | MDI | - | |
| 210.1.3 | [Village TAI (210.6)](#t8) | MDI | - | |
| 210.1.4 | [getNbDecimalVillage (210.8)](#t10) | - | - | |
| **210.2** | [**Creation Honey Moon** (210.2)](#t3) | MDI | - | Creation |
| 210.2.1 | [Creation Circuit (210.3)](#t4) | MDI | - | |
| 210.2.2 | [Creation Table Prestation (210.4)](#t5) | MDI | - | |
| 210.2.3 | [Creation TAIGM (210.5)](#t7) | MDI | - | |
| 210.2.4 | [Creation Circuit (210.7)](#t9) | MDI | - | |
| 210.2.5 | [Creation Table Prestation (210.9)](#t24) | MDI | - | |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Traitement principal]
    UPDATE[MAJ 7 tables]
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

### Tables utilisees (14)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 31 | gm-complet_______gmc |  | DB | R | **W** |   | 2 |
| 33 | prestations______pre | Prestations/services vendus | DB |   |   | L | 1 |
| 63 | parametres___par |  | DB | R |   |   | 1 |
| 69 | initialisation___ini |  | DB |   | **W** |   | 1 |
| 81 | societe__________soc |  | DB | R |   |   | 1 |
| 135 | libelle_prestation | Prestations/services vendus | DB |   | **W** |   | 1 |
| 462 | type_change___________bi |  | DB |   |   | L | 1 |
| 463 | heure_de_passage |  | DB |   | **W** |   | 1 |
| 473 | comptage_caisse | Sessions de caisse | TMP |   | **W** |   | 1 |
| 569 | pointage_articles_caution | Articles et stock | TMP | R |   |   | 1 |
| 573 | tempo_ecran_mecano | Table temporaire ecran | TMP |   |   | L | 1 |
| 590 | tempo_date_heure | Table temporaire ecran | TMP |   | **W** |   | 1 |
| 1078 | Table_1078 |  | MEM |   |   | L | 1 |
| 1104 | Table_1104 |  | MEM |   | **W** | L | 2 |

### Colonnes par table (4 / 10 tables avec colonnes identifiees)

<details>
<summary>Table 31 - gm-complet_______gmc (R/**W**) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 63 - parametres___par (R) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 69 - initialisation___ini (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 81 - societe__________soc (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P0-Code Societe | R | Alpha |

</details>

<details>
<summary>Table 135 - libelle_prestation (**W**) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | e.prestation_save? | W | Logical |
| C | P0-Nb Prestations | W | Numeric |
| D | P0-New Prestation | W | Logical |
| P | e.Catégorie prestation? | W | Logical |

</details>

<details>
<summary>Table 463 - heure_de_passage (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

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
| E | W0-Operande | R | Numeric |
| F | W0-Operateur | R | Numeric |
| G | W0-Pourcentage | R | Numeric |
| H | W0-Calcul Pourcent | R | Numeric |
| I | W0-Ret Lien Circuit | R | Numeric |
| J | W0-Honey Moon 1 | R | Alpha |
| K | W0-Honey Moon 2 | R | Alpha |
| L | W0-Honey Moon 3 | R | Alpha |
| M | W0-Honey Moon 4 | R | Alpha |
| N | W0-Village TAI | R | Alpha |
| O | Existe TAIFORFAIT | R | Logical |
| P | e.Catégorie prestation? | R | Logical |
| Q | V.Compteur | R | Numeric |
| R | V. Nombre Decimal Village | R | Numeric |

</details>

<details>
<summary>Table 590 - tempo_date_heure (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 1104 - Table_1104 (**W**/L) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Variables de session (2)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| Q | V.Compteur | Numeric | - |
| R | V. Nombre Decimal Village | Numeric | - |

### 11.2 Autres (16)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P0-Code Societe | Alpha | - |
| B | P0-Lieu de Sejour | Alpha | - |
| C | P0-Nb Prestations | Numeric | - |
| D | P0-New Prestation | Logical | - |
| E | W0-Operande | Numeric | - |
| F | W0-Operateur | Numeric | - |
| G | W0-Pourcentage | Numeric | - |
| H | W0-Calcul Pourcent | Numeric | - |
| I | W0-Ret Lien Circuit | Numeric | - |
| J | W0-Honey Moon 1 | Alpha | [210.1](#t2), [210.2](#t3) |
| K | W0-Honey Moon 2 | Alpha | [210.1](#t2), [210.2](#t3) |
| L | W0-Honey Moon 3 | Alpha | [210.1](#t2), [210.2](#t3) |
| M | W0-Honey Moon 4 | Alpha | [210.1](#t2), [210.2](#t3) |
| N | W0-Village TAI | Alpha | 1x refs |
| O | Existe TAIFORFAIT | Logical | - |
| P | e.Catégorie prestation? | Logical | 1x refs |

<details>
<summary>Toutes les 18 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| V. | **Q** | V.Compteur | Numeric |
| V. | **R** | V. Nombre Decimal Village | Numeric |
| Autre | **A** | P0-Code Societe | Alpha |
| Autre | **B** | P0-Lieu de Sejour | Alpha |
| Autre | **C** | P0-Nb Prestations | Numeric |
| Autre | **D** | P0-New Prestation | Logical |
| Autre | **E** | W0-Operande | Numeric |
| Autre | **F** | W0-Operateur | Numeric |
| Autre | **G** | W0-Pourcentage | Numeric |
| Autre | **H** | W0-Calcul Pourcent | Numeric |
| Autre | **I** | W0-Ret Lien Circuit | Numeric |
| Autre | **J** | W0-Honey Moon 1 | Alpha |
| Autre | **K** | W0-Honey Moon 2 | Alpha |
| Autre | **L** | W0-Honey Moon 3 | Alpha |
| Autre | **M** | W0-Honey Moon 4 | Alpha |
| Autre | **N** | W0-Village TAI | Alpha |
| Autre | **O** | Existe TAIFORFAIT | Logical |
| Autre | **P** | e.Catégorie prestation? | Logical |

</details>

## 12. EXPRESSIONS

**17 / 17 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCULATION | 4 | 0 |
| CONSTANTE | 1 | 0 |
| CAST_LOGIQUE | 1 | 0 |
| REFERENCE_VG | 1 | 0 |
| OTHER | 5 | 0 |
| CONDITION | 5 | 0 |

### 12.2 Expressions cles par type

#### CALCULATION (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 11 | `CallProg('{492,-1}'PROG,DbName('{590,2}'DSOURCE))` | - |
| CALCULATION | 15 | `[BY]+1` | - |
| CALCULATION | 3 | `([BY]/VG15)*100` | - |
| CALCULATION | 4 | `([BY]/VG15)*50` | - |

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

#### OTHER (5 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 16 | `[CE]` | - |
| OTHER | 17 | `NOT([CJ])` | - |
| OTHER | 12 | `[S]` | - |
| OTHER | 6 | `e.Catégorie prestation? [P]` | - |
| OTHER | 10 | `DbDel ('{590,2}'DSOURCE,'')` | - |

#### CONDITION (5 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 13 | `W0-Village TAI [N]='O' AND [AJ]` | - |
| CONDITION | 14 | `Trim ([T])<>''` | - |
| CONDITION | 9 | `[AI]>'E' AND [AG]>0` | - |
| CONDITION | 7 | `[S]=W0-Honey Moon 1 [J] OR [S]=W0-Honey Moon 2 [K] OR [S]=W0-Honey Moon 3 [L] OR [S]=W0-Honey Moon 4 [M]` | - |
| CONDITION | 8 | `[S]<>W0-Honey Moon 1 [J] AND [S]<>W0-Honey Moon 2 [K] AND [S]<>W0-Honey Moon 3 [L] AND [S]<>W0-Honey Moon 4 [M]` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Traitement des arrivants (IDE 206)](PBG-IDE-206.md) -> **Traitement des Prestations TAI (IDE 210)**

```mermaid
graph LR
    T210[210 Traitement des Pre...]
    style T210 fill:#58a6ff
    CC206[206 Traitement des arr...]
    style CC206 fill:#8b5cf6
    CC206 --> T210
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [206](PBG-IDE-206.md) | Traitement des arrivants | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T210[210 Traitement des Pre...]
    style T210 fill:#58a6ff
    NONE[Aucun callee]
    T210 -.-> NONE
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
| Lignes de logique | 259 | Taille moyenne |
| Expressions | 17 | Peu de logique |
| Tables WRITE | 7 | Fort impact donnees |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0.4% (1 / 259) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (5 taches: 1 ecran, 4 traitements)

- **Strategie** : Orchestrateur avec 1 ecrans (Razor/React) et 4 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- Decomposer les taches en services unitaires testables.

#### Creation (6 taches: 0 ecran, 6 traitements)

- **Strategie** : Repository pattern avec Entity Framework Core.
- Insertion via `IRepository<T>.CreateAsync()`

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| gm-complet_______gmc | Table WRITE (Database) | 1x | Schema + repository |
| initialisation___ini | Table WRITE (Database) | 1x | Schema + repository |
| libelle_prestation | Table WRITE (Database) | 1x | Schema + repository |
| heure_de_passage | Table WRITE (Database) | 1x | Schema + repository |
| comptage_caisse | Table WRITE (Temp) | 1x | Schema + repository |
| tempo_date_heure | Table WRITE (Temp) | 1x | Schema + repository |
| Table_1104 | Table WRITE (Memory) | 1x | Schema + repository |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 10:13*
