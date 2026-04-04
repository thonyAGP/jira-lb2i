# PBG IDE 219 - Traitement Heberg. /pms-912

> **Analyse**: Phases 1-4 2026-02-03 10:18 -> 10:18 (20s) | Assemblage 10:18
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBG |
| IDE Position | 219 |
| Nom Programme | Traitement Heberg. /pms-912 |
| Fichier source | `Prg_219.xml` |
| Domaine metier | General |
| Taches | 9 (1 ecrans visibles) |
| Tables modifiees | 5 |
| Programmes appeles | 2 |

## 2. DESCRIPTION FONCTIONNELLE

**Traitement Heberg. /pms-912** assure la gestion complete de ce processus, accessible depuis [Traitement des arrivants (IDE 206)](PBG-IDE-206.md), [Call Traitement Heberg (IDE 388)](PBG-IDE-388.md).

Le flux de traitement s'organise en **2 blocs fonctionnels** :

- **Creation** (6 taches) : insertion d'enregistrements en base (mouvements, prestations)
- **Traitement** (3 taches) : traitements metier divers

**Donnees modifiees** : 5 tables en ecriture (hebergement______heb, code_logement____clo, lit_matrimoniaux, pv_pms_prestations_tmp, tempo_trafic).

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (3 taches)

- **219** - Veuillez patienter... **[[ECRAN]](#ecran-t1)**
- **219.1** - Nbre sejours
- **219.5** - Avertissement H

Delegue a : [Maj hebergement (IDE 220)](PBG-IDE-220.md), [Mise à jour Date de Séjour (IDE 267)](PBG-IDE-267.md)

#### Phase 2 : Creation (6 taches)

- **219.2** - Creation Hebergement
- **219.3** - Creation Hebergement
- **219.4** - Creation Code Logement
- **219.2.1** - Create Log PYR
- **219.6** - Creation Hebergement **[[ECRAN]](#ecran-t10)**
- **219.6.1** - Create Log PYR

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| hebergement______heb | **W** (2 usages) | Hebergement (chambres) |
| tempo_trafic | **W** (2 usages) | Table temporaire ecran |
| code_logement____clo | **W**/L (2 usages) |  |
| lit_matrimoniaux | **W** (1 usages) |  |
| pv_pms_prestations_tmp | **W** (1 usages) | Prestations/services vendus |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (3 taches)

Traitements internes.

---

#### <a id="t1"></a>219 - Veuillez patienter... [[ECRAN]](#ecran-t1)

**Role** : Traitement : Veuillez patienter....
**Ecran** : 429 x 69 DLU (MDI) | [Voir mockup](#ecran-t1)
**Delegue a** : [Maj hebergement (IDE 220)](PBG-IDE-220.md), [Mise à jour Date de Séjour (IDE 267)](PBG-IDE-267.md)

---

#### <a id="t2"></a>219.1 - Nbre sejours

**Role** : Traitement : Nbre sejours.
**Variables liees** : J (W0-Nbre sejours)
**Delegue a** : [Maj hebergement (IDE 220)](PBG-IDE-220.md), [Mise à jour Date de Séjour (IDE 267)](PBG-IDE-267.md)

---

#### <a id="t6"></a>219.5 - Avertissement H

**Role** : Traitement : Avertissement H.
**Delegue a** : [Maj hebergement (IDE 220)](PBG-IDE-220.md), [Mise à jour Date de Séjour (IDE 267)](PBG-IDE-267.md)


### 3.2 Creation (6 taches)

Insertion de nouveaux enregistrements en base.

---

#### <a id="t3"></a>219.2 - Creation Hebergement

**Role** : Creation d'enregistrement : Creation Hebergement.
**Variables liees** : C (P0-Nb Hebergements)

---

#### <a id="t4"></a>219.3 - Creation Hebergement

**Role** : Creation d'enregistrement : Creation Hebergement.
**Variables liees** : C (P0-Nb Hebergements)

---

#### <a id="t5"></a>219.4 - Creation Code Logement

**Role** : Creation d'enregistrement : Creation Code Logement.
**Variables liees** : B (P0-Code Societe), K (W0-Existe logement)

---

#### <a id="t7"></a>219.2.1 - Create Log PYR

**Role** : Traitement : Create Log PYR.

---

#### <a id="t10"></a>219.6 - Creation Hebergement [[ECRAN]](#ecran-t10)

**Role** : Creation d'enregistrement : Creation Hebergement.
**Ecran** : 520 x 137 DLU (MDI) | [Voir mockup](#ecran-t10)
**Variables liees** : C (P0-Nb Hebergements)

---

#### <a id="t11"></a>219.6.1 - Create Log PYR

**Role** : Traitement : Create Log PYR.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Traitement des arrivants (IDE 206)](PBG-IDE-206.md), [Call Traitement Heberg (IDE 388)](PBG-IDE-388.md)
- **Appelle**: 2 programmes | **Tables**: 10 (W:5 R:1 L:5) | **Taches**: 9 | **Expressions**: 28

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 9)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 219 | 219 | Veuillez patienter... | MDI | 429 | 69 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>219 - Veuillez patienter...
**Tache** : [219](#t1) | **Type** : MDI | **Dimensions** : 429 x 69 DLU
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
                         "text":  "Traitement Hebergements",
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
    "taskId":  "219",
    "height":  69
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

### 9.3 Structure hierarchique (9 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **219.1** | [**Veuillez patienter...** (219)](#t1) [mockup](#ecran-t1) | MDI | 429x69 | Traitement |
| 219.1.1 | [Nbre sejours (219.1)](#t2) | MDI | - | |
| 219.1.2 | [Avertissement H (219.5)](#t6) | MDI | - | |
| **219.2** | [**Creation Hebergement** (219.2)](#t3) | MDI | - | Creation |
| 219.2.1 | [Creation Hebergement (219.3)](#t4) | MDI | - | |
| 219.2.2 | [Creation Code Logement (219.4)](#t5) | MDI | - | |
| 219.2.3 | [Create Log PYR (219.2.1)](#t7) | - | - | |
| 219.2.4 | [Creation Hebergement (219.6)](#t10) [mockup](#ecran-t10) | MDI | 520x137 | |
| 219.2.5 | [Create Log PYR (219.6.1)](#t11) | - | - | |

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

### Tables utilisees (10)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 31 | gm-complet_______gmc |  | DB |   |   | L | 1 |
| 34 | hebergement______heb | Hebergement (chambres) | DB |   | **W** |   | 2 |
| 108 | code_logement____clo |  | DB |   | **W** | L | 2 |
| 350 | lit_matrimoniaux |  | DB |   | **W** |   | 1 |
| 558 | import_troncon___imt |  | TMP |   |   | L | 1 |
| 564 | pms_check_out |  | TMP |   |   | L | 1 |
| 569 | pointage_articles_caution | Articles et stock | TMP |   |   | L | 1 |
| 571 | inter_prestation_inp | Prestations/services vendus | TMP | R |   |   | 1 |
| 574 | pv_pms_prestations_tmp | Prestations/services vendus | TMP |   | **W** |   | 1 |
| 617 | tempo_trafic | Table temporaire ecran | TMP |   | **W** |   | 2 |

### Colonnes par table (4 / 6 tables avec colonnes identifiees)

<details>
<summary>Table 34 - hebergement______heb (**W**) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| C | P0-Nb Hebergements | W | Numeric |

</details>

<details>
<summary>Table 108 - code_logement____clo (**W**/L) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| B | P0-Code Societe | W | Alpha |
| K | W0-Existe logement | W | Logical |

</details>

<details>
<summary>Table 350 - lit_matrimoniaux (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 571 - inter_prestation_inp (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P0-Lieu de Sejour | R | Alpha |
| B | P0-Code Societe | R | Alpha |
| C | P0-Nb Hebergements | R | Numeric |
| D | P0-N° Import | R | Numeric |
| E | P0-Qualite Import | R | Alpha |
| F | W0-Operande | R | Numeric |
| G | W0-Operateur | R | Numeric |
| H | W0-Pourcentage | R | Numeric |
| I | W0-Calcul Pourcent | R | Numeric |
| J | W0-Nbre sejours | R | Numeric |
| K | W0-Existe logement | R | Logical |
| L | W0-Existe anc sejour date deb | R | Logical |
| M | V.Compteur | R | Numeric |
| N | V. Heure libérat° chambre Vill | R | Time |

</details>

<details>
<summary>Table 574 - pv_pms_prestations_tmp (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 617 - tempo_trafic (**W**) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Variables de session (2)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| M | V.Compteur | Numeric | 1x session |
| N | V. Heure libérat° chambre Vill | Time | - |

### 11.2 Autres (12)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P0-Lieu de Sejour | Alpha | [219.1](#t2) |
| B | P0-Code Societe | Alpha | 1x refs |
| C | P0-Nb Hebergements | Numeric | - |
| D | P0-N° Import | Numeric | 1x refs |
| E | P0-Qualite Import | Alpha | - |
| F | W0-Operande | Numeric | - |
| G | W0-Operateur | Numeric | - |
| H | W0-Pourcentage | Numeric | - |
| I | W0-Calcul Pourcent | Numeric | - |
| J | W0-Nbre sejours | Numeric | - |
| K | W0-Existe logement | Logical | [219.4](#t5) |
| L | W0-Existe anc sejour date deb | Logical | - |

## 12. EXPRESSIONS

**28 / 28 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCULATION | 3 | 0 |
| CONSTANTE | 1 | 0 |
| REFERENCE_VG | 1 | 0 |
| OTHER | 18 | 0 |
| CONDITION | 3 | 0 |
| NEGATION | 1 | 0 |
| STRING | 1 | 0 |

### 12.2 Expressions cles par type

#### CALCULATION (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 20 | `[DQ]+1` | - |
| CALCULATION | 3 | `([DQ]/VG13)*50` | - |
| CALCULATION | 2 | `([DQ]/VG13)*100` | - |

#### CONSTANTE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 1 | `''` | - |

#### REFERENCE_VG (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 4 | `VG20` | - |

#### OTHER (18 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 18 | `[AT]` | - |
| OTHER | 19 | `V.Compteur [M]` | - |
| OTHER | 16 | `[AR]` | - |
| OTHER | 17 | `[AS]` | - |
| OTHER | 22 | `DbDel('{616,2}'DSOURCE,'')` | - |
| ... | | *+13 autres* | |

#### CONDITION (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 24 | `[AC]>0` | - |
| CONDITION | 8 | `[AE]='H'` | - |
| CONDITION | 7 | `[AE]>'E'` | - |

#### NEGATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| NEGATION | 21 | `NOT [AU]` | - |

#### STRING (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| STRING | 27 | `Trim(VG20)` | - |

### 12.3 Toutes les expressions (28)

<details>
<summary>Voir les 28 expressions</summary>

#### CALCULATION (3)

| IDE | Expression Decodee |
|-----|-------------------|
| 2 | `([DQ]/VG13)*100` |
| 3 | `([DQ]/VG13)*50` |
| 20 | `[DQ]+1` |

#### CONSTANTE (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 1 | `''` |

#### REFERENCE_VG (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 4 | `VG20` |

#### OTHER (18)

| IDE | Expression Decodee |
|-----|-------------------|
| 5 | `W0-Existe logement [K]` |
| 6 | `W0-Existe anc sejour d... [L]` |
| 9 | `P0-Code Societe [B]` |
| 10 | `[AC]` |
| 11 | `[AD]` |
| 12 | `P0-Lieu de Sejour [A]` |
| 13 | `[Q]` |
| 14 | `[AF]` |
| 15 | `[AG]` |
| 16 | `[AR]` |
| 17 | `[AS]` |
| 18 | `[AT]` |
| 19 | `V.Compteur [M]` |
| 22 | `DbDel('{616,2}'DSOURCE,'')` |
| 23 | `NOT(ExpCalc('10'EXP))` |
| 25 | `P0-Lieu de Sejour [A]` |
| 26 | `P0-N° Import [D]` |
| 28 | `P0-Lieu de Sejour [A]` |

#### CONDITION (3)

| IDE | Expression Decodee |
|-----|-------------------|
| 7 | `[AE]>'E'` |
| 8 | `[AE]='H'` |
| 24 | `[AC]>0` |

#### NEGATION (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 21 | `NOT [AU]` |

#### STRING (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 27 | `Trim(VG20)` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Traitement des arrivants (IDE 206)](PBG-IDE-206.md) -> **Traitement Heberg. /pms-912 (IDE 219)**

Main -> ... -> [Call Traitement Heberg (IDE 388)](PBG-IDE-388.md) -> **Traitement Heberg. /pms-912 (IDE 219)**

```mermaid
graph LR
    T219[219 Traitement Heberg....]
    style T219 fill:#58a6ff
    CC388[388 Call Traitement He...]
    style CC388 fill:#8b5cf6
    CC206[206 Traitement des arr...]
    style CC206 fill:#8b5cf6
    CC206 --> T219
    CC388 --> T219
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [206](PBG-IDE-206.md) | Traitement des arrivants | 1 |
| [388](PBG-IDE-388.md) | Call Traitement Heberg | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T219[219 Traitement Heberg....]
    style T219 fill:#58a6ff
    C220[220 Maj hebergement]
    T219 --> C220
    style C220 fill:#3fb950
    C267[267 Mise à jour Date d...]
    T219 --> C267
    style C267 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [220](PBG-IDE-220.md) | Maj hebergement | 1 | Mise a jour donnees |
| [267](PBG-IDE-267.md) | Mise à jour Date de Séjour | 1 | Mise a jour donnees |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 371 | Taille moyenne |
| Expressions | 28 | Peu de logique |
| Tables WRITE | 5 | Impact modere |
| Sous-programmes | 2 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 371) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (3 taches: 1 ecran, 2 traitements)

- **Strategie** : Orchestrateur avec 1 ecrans (Razor/React) et 2 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 2 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Creation (6 taches: 1 ecran, 5 traitements)

- **Strategie** : Repository pattern avec Entity Framework Core.
- Insertion via `IRepository<T>.CreateAsync()`

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| hebergement______heb | Table WRITE (Database) | 2x | Schema + repository |
| code_logement____clo | Table WRITE (Database) | 1x | Schema + repository |
| lit_matrimoniaux | Table WRITE (Database) | 1x | Schema + repository |
| pv_pms_prestations_tmp | Table WRITE (Temp) | 1x | Schema + repository |
| tempo_trafic | Table WRITE (Temp) | 2x | Schema + repository |
| [Mise à jour Date de Séjour (IDE 267)](PBG-IDE-267.md) | Sous-programme | 1x | Normale - Mise a jour donnees |
| [Maj hebergement (IDE 220)](PBG-IDE-220.md) | Sous-programme | 1x | Normale - Mise a jour donnees |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 10:18*
