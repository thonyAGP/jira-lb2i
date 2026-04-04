# PBP IDE 163 - Prep tempo present planning

> **Analyse**: Phases 1-4 2026-02-03 15:33 -> 15:33 (21s) | Assemblage 15:33
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBP |
| IDE Position | 163 |
| Nom Programme | Prep tempo present planning |
| Fichier source | `Prg_163.xml` |
| Dossier IDE | Liste |
| Taches | 6 (1 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 4 |

## 2. DESCRIPTION FONCTIONNELLE

**Prep tempo present planning** assure la gestion complete de ce processus, accessible depuis [  Liste Clients present (IDE 162)](PBP-IDE-162.md), [Pilotage Gestion de Crise (IDE 146)](PBP-IDE-146.md).

Le flux de traitement s'organise en **3 blocs fonctionnels** :

- **Traitement** (3 taches) : traitements metier divers
- **Creation** (2 taches) : insertion d'enregistrements en base (mouvements, prestations)
- **Consultation** (1 tache) : ecrans de recherche, selection et consultation

**Donnees modifiees** : 1 tables en ecriture (tempo_mecano_dossier_grou).

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (3 taches)

- **163** - Veuillez patienter ... **[[ECRAN]](#ecran-t1)**
- **163.1** - Veuillez patienter ... **[[ECRAN]](#ecran-t2)**
- **163.1.1.1** - Tronçons

#### Phase 2 : Creation (2 taches)

- **163.1.1** - Creation Tempo gene
- **163.1.2** - Creation tempo bateaux police

Delegue a : [Creation tempo total qualite (IDE 205)](PBP-IDE-205.md)

#### Phase 3 : Consultation (1 tache)

- **163.2** - Recherche Code Village

Delegue a : [Recherche age Bebe_Enfant (IDE 307)](PBP-IDE-307.md)

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| tempo_mecano_dossier_grou | **W**/L (2 usages) | Table temporaire ecran |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (3 taches)

Traitements internes.

---

#### <a id="t1"></a>163 - Veuillez patienter ... [[ECRAN]](#ecran-t1)

**Role** : Traitement : Veuillez patienter ....
**Ecran** : 426 x 58 DLU (MDI) | [Voir mockup](#ecran-t1)

---

#### <a id="t2"></a>163.1 - Veuillez patienter ... [[ECRAN]](#ecran-t2)

**Role** : Traitement : Veuillez patienter ....
**Ecran** : 424 x 56 DLU (MDI) | [Voir mockup](#ecran-t2)

---

#### <a id="t5"></a>163.1.1.1 - Tronçons

**Role** : Traitement : Tronçons.


### 3.2 Creation (2 taches)

Insertion de nouveaux enregistrements en base.

---

#### <a id="t3"></a>163.1.1 - Creation Tempo gene

**Role** : Creation d'enregistrement : Creation Tempo gene.
**Delegue a** : [Creation tempo total qualite (IDE 205)](PBP-IDE-205.md)

---

#### <a id="t6"></a>163.1.2 - Creation tempo bateaux police

**Role** : Creation d'enregistrement : Creation tempo bateaux police.
**Delegue a** : [Creation tempo total qualite (IDE 205)](PBP-IDE-205.md)


### 3.3 Consultation (1 tache)

Ecrans de recherche et consultation.

---

#### <a id="t7"></a>163.2 - Recherche Code Village

**Role** : Traitement : Recherche Code Village.
**Variables liees** : J (>CodeListe), N (>CodeVol), O (>DateVillage), P (>HeureVillage), BC (w0_CodeVillage)
**Delegue a** : [Recherche age Bebe_Enfant (IDE 307)](PBP-IDE-307.md)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [  Liste Clients present (IDE 162)](PBP-IDE-162.md), [Pilotage Gestion de Crise (IDE 146)](PBP-IDE-146.md)
- **Appelle**: 4 programmes | **Tables**: 20 (W:1 R:5 L:16) | **Taches**: 6 | **Expressions**: 25

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 6)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 163 | 163 | Veuillez patienter ... | MDI | 426 | 58 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>163 - Veuillez patienter ...
**Tache** : [163](#t1) | **Type** : MDI | **Dimensions** : 426 x 58 DLU
**Bloc** : Traitement | **Titre IDE** : Veuillez patienter ...

<!-- FORM-DATA:
{
    "width":  426,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  0,
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
                         "x":  120,
                         "type":  "label",
                         "var":  "",
                         "y":  10,
                         "w":  256,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "7",
                         "text":  "Traitement GM en cours ...",
                         "parent":  null
                     },
                     {
                         "x":  0,
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
                         "x":  103,
                         "type":  "label",
                         "var":  "",
                         "y":  33,
                         "w":  114,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Analysés :",
                         "parent":  4
                     },
                     {
                         "x":  103,
                         "type":  "label",
                         "var":  "",
                         "y":  44,
                         "w":  150,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Selectionnés :",
                         "parent":  4
                     },
                     {
                         "x":  4,
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
                         "x":  265,
                         "type":  "edit",
                         "var":  "",
                         "y":  31,
                         "w":  56,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  265,
                         "type":  "edit",
                         "var":  "",
                         "y":  43,
                         "w":  56,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     }
                 ],
    "taskId":  "163",
    "height":  58
}
-->

<details>
<summary><strong>Champs : 2 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 265,31 | (sans nom) | - | edit |
| 265,43 | (sans nom) | - | edit |

</details>

## 9. NAVIGATION

Ecran unique: **Veuillez patienter ...**

### 9.3 Structure hierarchique (6 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **163.1** | [**Veuillez patienter ...** (163)](#t1) [mockup](#ecran-t1) | MDI | 426x58 | Traitement |
| 163.1.1 | [Veuillez patienter ... (163.1)](#t2) [mockup](#ecran-t2) | MDI | 424x56 | |
| 163.1.2 | [Tronçons (163.1.1.1)](#t5) | MDI | - | |
| **163.2** | [**Creation Tempo gene** (163.1.1)](#t3) | MDI | - | Creation |
| 163.2.1 | [Creation tempo bateaux police (163.1.2)](#t6) | MDI | - | |
| **163.3** | [**Recherche Code Village** (163.2)](#t7) | - | - | Consultation |

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

### Tables utilisees (20)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 31 | gm-complet_______gmc |  | DB | R |   |   | 1 |
| 34 | hebergement______heb | Hebergement (chambres) | DB | R |   |   | 1 |
| 36 | client_gm |  | DB | R |   | L | 2 |
| 81 | societe__________soc |  | DB |   |   | L | 1 |
| 104 | fichier_menage |  | DB |   |   | L | 1 |
| 118 | tables_imports |  | DB |   |   | L | 1 |
| 119 | tables_pays_tel_ |  | DB |   |   | L | 1 |
| 121 | tables_pays_ventes | Donnees de ventes | DB |   |   | L | 1 |
| 167 | troncon__________tro |  | DB | R |   |   | 1 |
| 168 | heb_circuit______hci | Hebergement (chambres) | DB |   |   | L | 1 |
| 171 | commentaire______com |  | DB |   |   | L | 1 |
| 285 | email |  | DB |   |   | L | 1 |
| 358 | import_mod |  | DB |   |   | L | 1 |
| 366 | pms_print_param |  | DB |   |   | L | 1 |
| 372 | pv_budget |  | DB | R |   |   | 1 |
| 609 | tempo_mecano_dossier_grou | Table temporaire ecran | TMP |   | **W** | L | 2 |
| 619 | tempo_userlist | Table temporaire ecran | TMP |   |   | L | 2 |
| 637 | tempo_zone_secteur | Table temporaire ecran | DB |   |   | L | 2 |
| 738 | pv_selling_unit |  | DB |   |   | L | 1 |
| 845 | stat_vendeur_date |  | TMP |   |   | L | 1 |

### Colonnes par table (7 / 6 tables avec colonnes identifiees)

<details>
<summary>Table 31 - gm-complet_______gmc (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | >Index | R | Numeric |
| B | >DateCalcul | R | Date |
| C | >HeureCalcul | R | Alpha |
| D | >DateMinDebut | R | Date |
| E | >DateMaxDebut | R | Date |
| F | >DateMinFin | R | Date |
| G | >DateMaxFin | R | Date |
| H | >w0_HeureMin | R | Numeric |
| I | >w0_HeureMax | R | Numeric |
| J | >CodeListe | R | Alpha |
| K | >Logement | R | Alpha |
| L | >TypeHebergement | R | Alpha |
| M | >TopListe | R | Alpha |
| N | >CodeVol | R | Alpha |
| O | >DateVillage | R | Date |
| P | >HeureVillage | R | Alpha |
| Q | >AgeMini | R | Numeric |
| R | >AgeMaxi | R | Numeric |
| S | <Total | R | Numeric |
| T | <NbSelect | R | Numeric |
| U | >TULCategorie | R | Alpha |
| V | >TULNomTable | R | Alpha |
| W | > sejour | R | Alpha |
| X | > gestion crise | R | Logical |
| Y | w0_RetCommentaire | R | Logical |
| Z | w0_NationSelect | R | Alpha |
| BA | w0_AgeBebe | R | Numeric |
| BB | w0_AgeEnfant | R | Numeric |
| BC | w0_CodeVillage | R | Alpha |

</details>

<details>
<summary>Table 34 - hebergement______heb (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | w0_Age------------------------- | R | Alpha |
| B | w0_Arrivee--------------------- | R | Alpha |
| C | v.Code vol aller A | R | Unicode |
| D | w0_Depart---------------------- | R | Alpha |
| E | v.Code vol retour Z | R | Unicode |
| F | w0_RetSelect | R | Logical |
| G | w0_Circuit--------------------- | R | Logical |
| H | w0_DepCircuit------------------ | R | Logical |
| I | w0_RetCircuit------------------ | R | Logical |
| J | W0_PresenceAv------------------ | R | Logical |
| K | w0_RetHebPreced---------------- | R | Logical |
| L | w0_RetHebSuiv------------------ | R | Logical |
| M | W0 Lien Table Import | R | Logical |
| N | v. retour absence | R | Logical |
| O | w0_Type | R | Alpha |
| P | w0_DateMaxDebut | R | Date |
| Q | w0_DateMaxFin | R | Date |
| R | w0_Total | R | Numeric |
| S | w0_NbSelect | R | Numeric |
| T | w0_RetCtlHeb | R | Logical |
| U | w0_TelInt | R | Numeric |
| V | w0_TelExt_Commune | R | Alpha |
| W | w0_FaxVille | R | Alpha |
| X | w0_TypeEcran | R | Alpha |
| Y | w0_NumAdherent | R | Alpha |
| Z | w0_Age | R | Numeric |
| BA | w0_Cabine | R | Alpha |
| BB | W0_RetourCircuit | R | Alpha |
| BC | w0_CondArrivant | R | Logical |
| BD | w0_CondArrive | R | Logical |
| BE | W0_CondPresent | R | Logical |
| BF | w0_CondDepart | R | Logical |
| BG | w0_CondAbsent | R | Logical |
| BH | w0_CondPartant | R | Logical |

</details>

<details>
<summary>Table 36 - client_gm (R/L) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | w1_RetCreat | R | Logical |
| B | Ret. Link 36 | R | Logical |

</details>

<details>
<summary>Table 167 - troncon__________tro (R) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 372 - pv_budget (R) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 609 - tempo_mecano_dossier_grou (**W**/L) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Autres (34)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | >Index | Numeric | 1x refs |
| B | >DateCalcul | Date | - |
| C | >HeureCalcul | Alpha | - |
| D | >DateMinDebut | Date | 1x refs |
| E | >DateMaxDebut | Date | 1x refs |
| F | >DateMinFin | Date | 1x refs |
| G | >DateMaxFin | Date | 1x refs |
| H | >w0_HeureMin | Numeric | - |
| I | >w0_HeureMax | Numeric | - |
| J | >CodeListe | Alpha | - |
| K | >Logement | Alpha | - |
| L | >TypeHebergement | Alpha | - |
| M | >TopListe | Alpha | 2x refs |
| N | >CodeVol | Alpha | - |
| O | >DateVillage | Date | - |
| P | >HeureVillage | Alpha | - |
| Q | >AgeMini | Numeric | - |
| R | >AgeMaxi | Numeric | - |
| S | <Total | Numeric | - |
| T | <NbSelect | Numeric | - |
| U | >TULCategorie | Alpha | - |
| V | >TULNomTable | Alpha | - |
| W | > sejour | Alpha | - |
| X | > gestion crise | Logical | - |
| Y | w0_RetCommentaire | Logical | 2x refs |
| Z | w0_NationSelect | Alpha | - |
| BA | w0_AgeBebe | Numeric | - |
| BB | w0_AgeEnfant | Numeric | - |
| BC | w0_CodeVillage | Alpha | - |
| BD | w0_CondArrive | Logical | - |
| BE | W0_CondPresent | Logical | 1x refs |
| BF | w0_CondDepart | Logical | - |
| BG | w0_CondAbsent | Logical | - |
| BH | w0_CondPartant | Logical | - |

<details>
<summary>Toutes les 34 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| Autre | **A** | >Index | Numeric |
| Autre | **B** | >DateCalcul | Date |
| Autre | **C** | >HeureCalcul | Alpha |
| Autre | **D** | >DateMinDebut | Date |
| Autre | **E** | >DateMaxDebut | Date |
| Autre | **F** | >DateMinFin | Date |
| Autre | **G** | >DateMaxFin | Date |
| Autre | **H** | >w0_HeureMin | Numeric |
| Autre | **I** | >w0_HeureMax | Numeric |
| Autre | **J** | >CodeListe | Alpha |
| Autre | **K** | >Logement | Alpha |
| Autre | **L** | >TypeHebergement | Alpha |
| Autre | **M** | >TopListe | Alpha |
| Autre | **N** | >CodeVol | Alpha |
| Autre | **O** | >DateVillage | Date |
| Autre | **P** | >HeureVillage | Alpha |
| Autre | **Q** | >AgeMini | Numeric |
| Autre | **R** | >AgeMaxi | Numeric |
| Autre | **S** | <Total | Numeric |
| Autre | **T** | <NbSelect | Numeric |
| Autre | **U** | >TULCategorie | Alpha |
| Autre | **V** | >TULNomTable | Alpha |
| Autre | **W** | > sejour | Alpha |
| Autre | **X** | > gestion crise | Logical |
| Autre | **Y** | w0_RetCommentaire | Logical |
| Autre | **Z** | w0_NationSelect | Alpha |
| Autre | **BA** | w0_AgeBebe | Numeric |
| Autre | **BB** | w0_AgeEnfant | Numeric |
| Autre | **BC** | w0_CodeVillage | Alpha |
| Autre | **BD** | w0_CondArrive | Logical |
| Autre | **BE** | W0_CondPresent | Logical |
| Autre | **BF** | w0_CondDepart | Logical |
| Autre | **BG** | w0_CondAbsent | Logical |
| Autre | **BH** | w0_CondPartant | Logical |

</details>

## 12. EXPRESSIONS

**25 / 25 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONSTANTE | 6 | 0 |
| CONDITION | 7 | 0 |
| OTHER | 11 | 0 |
| REFERENCE_VG | 1 | 0 |

### 12.2 Expressions cles par type

#### CONSTANTE (6 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 18 | `'TNATI'` | - |
| CONSTANTE | 19 | `0` | - |
| CONSTANTE | 23 | `'FRA'` | - |
| CONSTANTE | 2 | `'VBEBE'` | - |
| CONSTANTE | 3 | `'VENFA'` | - |
| ... | | *+1 autres* | |

#### CONDITION (7 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 10 | `CndRange (>DateMaxFin [G]>0,>DateMaxFin [G])` | - |
| CONDITION | 21 | `>TopListe [M]='CO'` | - |
| CONDITION | 22 | `>TopListe [M]='ST'` | - |
| CONDITION | 9 | `CndRange (>DateMinFin [F]>0,>DateMinFin [F])` | - |
| CONDITION | 1 | `>Index [A]` | - |
| ... | | *+2 autres* | |

#### OTHER (11 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 15 | `W0_CondPresent [BE]` | - |
| OTHER | 14 | `[AS]` | - |
| OTHER | 20 | `w0_RetCommentaire [Y]` | - |
| OTHER | 25 | `[GG]` | - |
| OTHER | 24 | `[CJ]` | - |
| ... | | *+6 autres* | |

#### REFERENCE_VG (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 16 | `VG1` | - |

### 12.3 Toutes les expressions (25)

<details>
<summary>Voir les 25 expressions</summary>

#### CONSTANTE (6)

| IDE | Expression Decodee |
|-----|-------------------|
| 2 | `'VBEBE'` |
| 3 | `'VENFA'` |
| 17 | `'M'` |
| 18 | `'TNATI'` |
| 19 | `0` |
| 23 | `'FRA'` |

#### CONDITION (7)

| IDE | Expression Decodee |
|-----|-------------------|
| 1 | `>Index [A]` |
| 7 | `CndRange (>DateMinDebut [D]>0,>DateMinDebut [D])` |
| 8 | `CndRange (>DateMaxDebut [E]>0,>DateMaxDebut [E])` |
| 9 | `CndRange (>DateMinFin [F]>0,>DateMinFin [F])` |
| 10 | `CndRange (>DateMaxFin [G]>0,>DateMaxFin [G])` |
| 21 | `>TopListe [M]='CO'` |
| 22 | `>TopListe [M]='ST'` |

#### OTHER (11)

| IDE | Expression Decodee |
|-----|-------------------|
| 4 | `[AS]` |
| 5 | `GetParam('SOCIETE')` |
| 6 | `w0_RetCommentaire [Y]` |
| 11 | `[AN]` |
| 12 | `[AO]` |
| 13 | `GetParam ('LANGUE')` |
| 14 | `[AS]` |
| 15 | `W0_CondPresent [BE]` |
| 20 | `w0_RetCommentaire [Y]` |
| 24 | `[CJ]` |
| 25 | `[GG]` |

#### REFERENCE_VG (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 16 | `VG1` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [  Liste Clients present (IDE 162)](PBP-IDE-162.md) -> **Prep tempo present planning (IDE 163)**

Main -> ... -> [Pilotage Gestion de Crise (IDE 146)](PBP-IDE-146.md) -> **Prep tempo present planning (IDE 163)**

```mermaid
graph LR
    T163[163 Prep tempo present...]
    style T163 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC152[152 Start]
    style CC152 fill:#f59e0b
    CC161[161 Liste des presents]
    style CC161 fill:#f59e0b
    CC148[148 Liste Gestion de C...]
    style CC148 fill:#f59e0b
    CC146[146 Pilotage Gestion d...]
    style CC146 fill:#3fb950
    CC162[162 Liste Clients present]
    style CC162 fill:#3fb950
    CC148 --> CC146
    CC152 --> CC146
    CC161 --> CC146
    CC148 --> CC162
    CC152 --> CC162
    CC161 --> CC162
    CC1 --> CC148
    CC1 --> CC152
    CC1 --> CC161
    CC146 --> T163
    CC162 --> T163
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [162](PBP-IDE-162.md) |   Liste Clients present | 3 |
| [146](PBP-IDE-146.md) | Pilotage Gestion de Crise | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T163[163 Prep tempo present...]
    style T163 fill:#58a6ff
    C307[307 Recherche age Bebe...]
    T163 --> C307
    style C307 fill:#3fb950
    C205[205 Creation tempo tot...]
    T163 --> C205
    style C205 fill:#3fb950
    C284[284 RaZ Tempo synthese]
    T163 --> C284
    style C284 fill:#3fb950
    C302[302 Controle presence ...]
    T163 --> C302
    style C302 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [307](PBP-IDE-307.md) | Recherche age Bebe_Enfant | 2 | Sous-programme |
| [205](PBP-IDE-205.md) | Creation tempo total qualite | 1 | Sous-programme |
| [284](PBP-IDE-284.md) | RaZ Tempo synthese | 1 | Reinitialisation |
| [302](PBP-IDE-302.md) | Controle presence heberg | 1 | Controle/validation |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 850 | Programme volumineux |
| Expressions | 25 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 4 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 850) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (3 taches: 2 ecrans, 1 traitement)

- **Strategie** : Orchestrateur avec 2 ecrans (Razor/React) et 1 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 4 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Creation (2 taches: 0 ecran, 2 traitements)

- **Strategie** : Repository pattern avec Entity Framework Core.
- Insertion via `IRepository<T>.CreateAsync()`

#### Consultation (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Composants de recherche/selection en modales.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| tempo_mecano_dossier_grou | Table WRITE (Temp) | 1x | Schema + repository |
| [Recherche age Bebe_Enfant (IDE 307)](PBP-IDE-307.md) | Sous-programme | 2x | Haute - Sous-programme |
| [Controle presence heberg (IDE 302)](PBP-IDE-302.md) | Sous-programme | 1x | Normale - Controle/validation |
| [RaZ Tempo synthese (IDE 284)](PBP-IDE-284.md) | Sous-programme | 1x | Normale - Reinitialisation |
| [Creation tempo total qualite (IDE 205)](PBP-IDE-205.md) | Sous-programme | 1x | Normale - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 15:34*
