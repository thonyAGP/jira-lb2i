# PBP IDE 140 - Calcul recherche logement

> **Analyse**: Phases 1-4 2026-02-03 15:28 -> 15:29 (13s) | Assemblage 15:29
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBP |
| IDE Position | 140 |
| Nom Programme | Calcul recherche logement |
| Fichier source | `Prg_140.xml` |
| Dossier IDE | Gestion |
| Taches | 13 (1 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Calcul recherche logement** assure la gestion complete de ce processus, accessible depuis [Liste occupation (IDE 136)](PBP-IDE-136.md).

Le flux de traitement s'organise en **4 blocs fonctionnels** :

- **Traitement** (6 taches) : traitements metier divers
- **Validation** (3 taches) : controles et verifications de coherence
- **Consultation** (3 taches) : ecrans de recherche, selection et consultation
- **Creation** (1 tache) : insertion d'enregistrements en base (mouvements, prestations)

**Donnees modifiees** : 1 tables en ecriture (tempo_ecran_mecano).

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (6 taches)

- **140** - Veuillez Patienter ... **[[ECRAN]](#ecran-t1)**
- **140.1.1** - Analyse hebergement
- **140.1.2** - Communicante
- **140.1.2.1** - Analyse hebergement
- **140.1.3** - Recuperation variable
- **140.1.4** - Analyse hebergement

#### Phase 2 : Consultation (3 taches)

- **140.1** - Affiche **[[ECRAN]](#ecran-t2)**
- **140.1.6** - Exist select
- **140.1.7** - Exist select

#### Phase 3 : Validation (3 taches)

- **140.1.1.1** - Verif
- **140.1.2.1.1** - Verif
- **140.1.3.1** - Verif

#### Phase 4 : Creation (1 tache)

- **140.1.5** - Creation

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| tempo_ecran_mecano | **W**/L (3 usages) | Table temporaire ecran |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (6 taches)

Traitements internes.

---

#### <a id="t1"></a>140 - Veuillez Patienter ... [[ECRAN]](#ecran-t1)

**Role** : Tache d'orchestration : point d'entree du programme (6 sous-taches). Coordonne l'enchainement des traitements.
**Ecran** : 426 x 58 DLU (MDI) | [Voir mockup](#ecran-t1)

<details>
<summary>5 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [140.1.1](#t3) | Analyse hebergement | Traitement |
| [140.1.2](#t5) | Communicante | Traitement |
| [140.1.2.1](#t6) | Analyse hebergement | Traitement |
| [140.1.3](#t8) | Recuperation variable | Traitement |
| [140.1.4](#t10) | Analyse hebergement | Traitement |

</details>

---

#### <a id="t3"></a>140.1.1 - Analyse hebergement

**Role** : Traitement : Analyse hebergement.

---

#### <a id="t5"></a>140.1.2 - Communicante

**Role** : Traitement : Communicante.

---

#### <a id="t6"></a>140.1.2.1 - Analyse hebergement

**Role** : Traitement : Analyse hebergement.

---

#### <a id="t8"></a>140.1.3 - Recuperation variable

**Role** : Consultation/chargement : Recuperation variable.

---

#### <a id="t10"></a>140.1.4 - Analyse hebergement

**Role** : Traitement : Analyse hebergement.


### 3.2 Consultation (3 taches)

Ecrans de recherche et consultation.

---

#### <a id="t2"></a>140.1 - Affiche [[ECRAN]](#ecran-t2)

**Role** : Reinitialisation : Affiche.
**Ecran** : 858 x 184 DLU (MDI) | [Voir mockup](#ecran-t2)

---

#### <a id="t12"></a>140.1.6 - Exist select

**Role** : Traitement : Exist select.
**Variables liees** : F (<NbSelect)

---

#### <a id="t15"></a>140.1.7 - Exist select

**Role** : Traitement : Exist select.
**Variables liees** : F (<NbSelect)


### 3.3 Validation (3 taches)

Controles de coherence : 3 taches verifient les donnees et conditions.

---

#### <a id="t4"></a>140.1.1.1 - Verif

**Role** : Verification : Verif.

---

#### <a id="t7"></a>140.1.2.1.1 - Verif

**Role** : Verification : Verif.

---

#### <a id="t9"></a>140.1.3.1 - Verif

**Role** : Verification : Verif.


### 3.4 Creation (1 tache)

Insertion de nouveaux enregistrements en base.

---

#### <a id="t11"></a>140.1.5 - Creation

**Role** : Creation d'enregistrement : Creation.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Liste occupation (IDE 136)](PBP-IDE-136.md)
- **Appelle**: 0 programmes | **Tables**: 5 (W:1 R:4 L:3) | **Taches**: 13 | **Expressions**: 16

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 13)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 140 | 140 | Veuillez Patienter ... | MDI | 426 | 58 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>140 - Veuillez Patienter ...
**Tache** : [140](#t1) | **Type** : MDI | **Dimensions** : 426 x 58 DLU
**Bloc** : Traitement | **Titre IDE** : Veuillez Patienter ...

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
                         "w":  221,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "7",
                         "text":  "Traitement en cours ...",
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
                         "x":  110,
                         "type":  "label",
                         "var":  "",
                         "y":  32,
                         "w":  114,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Analyses",
                         "parent":  4
                     },
                     {
                         "x":  110,
                         "type":  "label",
                         "var":  "",
                         "y":  44,
                         "w":  139,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Selectiones",
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
                         "x":  259,
                         "type":  "edit",
                         "var":  "",
                         "y":  32,
                         "w":  56,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  259,
                         "type":  "edit",
                         "var":  "",
                         "y":  44,
                         "w":  56,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     }
                 ],
    "taskId":  "140",
    "height":  58
}
-->

<details>
<summary><strong>Champs : 2 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 259,32 | (sans nom) | - | edit |
| 259,44 | (sans nom) | - | edit |

</details>

## 9. NAVIGATION

Ecran unique: **Veuillez Patienter ...**

### 9.3 Structure hierarchique (13 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **140.1** | [**Veuillez Patienter ...** (140)](#t1) [mockup](#ecran-t1) | MDI | 426x58 | Traitement |
| 140.1.1 | [Analyse hebergement (140.1.1)](#t3) | MDI | - | |
| 140.1.2 | [Communicante (140.1.2)](#t5) | MDI | - | |
| 140.1.3 | [Analyse hebergement (140.1.2.1)](#t6) | MDI | - | |
| 140.1.4 | [Recuperation variable (140.1.3)](#t8) | MDI | - | |
| 140.1.5 | [Analyse hebergement (140.1.4)](#t10) | MDI | - | |
| **140.2** | [**Affiche** (140.1)](#t2) [mockup](#ecran-t2) | MDI | 858x184 | Consultation |
| 140.2.1 | [Exist select (140.1.6)](#t12) | MDI | - | |
| 140.2.2 | [Exist select (140.1.7)](#t15) | MDI | - | |
| **140.3** | [**Verif** (140.1.1.1)](#t4) | MDI | - | Validation |
| 140.3.1 | [Verif (140.1.2.1.1)](#t7) | MDI | - | |
| 140.3.2 | [Verif (140.1.3.1)](#t9) | MDI | - | |
| **140.4** | [**Creation** (140.1.5)](#t11) | MDI | - | Creation |

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

### Tables utilisees (5)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 34 | hebergement______heb | Hebergement (chambres) | DB | R |   |   | 3 |
| 103 | logement_client__loc |  | DB | R |   |   | 1 |
| 105 | logement_complement |  | DB | R |   | L | 2 |
| 621 | tempo_ecran_mecano | Table temporaire ecran | TMP |   | **W** | L | 3 |
| 637 | tempo_zone_secteur | Table temporaire ecran | DB | R |   | L | 7 |

### Colonnes par table (5 / 5 tables avec colonnes identifiees)

<details>
<summary>Table 34 - hebergement______heb (R) - 3 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | NB_Concerne | R | Numeric |
| B | w2_BlocageConstaté | R | Logical |
| C | w2_ReservationConstaté | R | Logical |
| D | w2_CodeAcces | R | Alpha |

</details>

<details>
<summary>Table 103 - logement_client__loc (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | w1_CondDate | R | Logical |
| B | w1_Selectionne | R | Logical |
| C | w1_Rattachement | R | Alpha |
| D | w1_ExistEns | R | Logical |
| E | w1_ExistLoge | R | Logical |
| F | w1_ExistBati | R | Logical |
| G | w1_ExistEtag | R | Logical |
| H | w1_ExistVue | R | Logical |
| I | w1_ExistComm | R | Logical |
| J | w1_ExistAtt | R | Logical |
| K | w1_ExistHand | R | Logical |
| L | w1_ExistSta | R | Logical |
| M | w1_ExistLieu | R | Logical |
| N | w1_ExistClog | R | Logical |
| O | w1_ExistZone | R | Logical |
| P | w1_ExistSect | R | Logical |
| Q | w1_ExistOccu | R | Logical |
| R | w1_FaitEns | R | Logical |
| S | w1_FaitLoge | R | Logical |
| T | w1_FaitBati | R | Logical |
| U | w1_FaitEtag | R | Logical |
| V | w1_FaitVue | R | Logical |
| W | w1_FaitComm | R | Logical |
| X | w1_FaitAtt | R | Logical |
| Y | w1_FaitHand | R | Logical |
| Z | w1_FaitSta | R | Logical |
| BA | w1_FaitLieu | R | Logical |
| BB | w1_FaitClog | R | Logical |
| BC | w1_FaitZone | R | Logical |
| BD | w1_FaitSect | R | Logical |
| BE | w1_FaitOccu | R | Logical |
| BF | v. TOCCU OCC Complet | R | Logical |
| BG | v. TOCCU BLK Bloqué | R | Logical |
| BH | v. TOCCU RES Reservé | R | Logical |
| BI | v. TOCCU TTL Totalement Libre | R | Logical |

</details>

<details>
<summary>Table 105 - logement_complement (R/L) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| J | RetLogement-------------------- | R | Logical |

</details>

<details>
<summary>Table 621 - tempo_ecran_mecano (**W**/L) - 3 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | >DateDebut | W | Date |
| B | >HeureDebut | W | Alpha |
| C | >DateFin | W | Date |
| D | >HeureFin | W | Alpha |
| E | <Total | W | Numeric |
| F | <NbSelect | W | Numeric |
| G | RetBatiment-------------------- | W | Logical |
| H | w0_BatiMin | W | Alpha |
| I | w0_BatiMax | W | Alpha |
| J | RetLogement-------------------- | W | Logical |
| K | w0_LogMin | W | Alpha |
| L | w0_LogMax | W | Alpha |
| M | RetEnsemble-------------------- | W | Logical |
| N | w0_EnsMin | W | Alpha |
| O | w0_EnsMax | W | Alpha |
| P | RetEtage----------------------- | W | Logical |
| Q | w0_EtageMin | W | Alpha |
| R | w0_EtageMax | W | Alpha |

</details>

<details>
<summary>Table 637 - tempo_zone_secteur (R/L) - 7 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | >Categorie | R | Alpha |
| B | >NomTable | R | Alpha |
| C | <CodeRetour | R | Logical |
| D | w1_TousVrai | R | Logical |

</details>

## 11. VARIABLES

### 11.1 Variables de session (4)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| BF | v. TOCCU OCC Complet | Logical | - |
| BG | v. TOCCU BLK Bloqué | Logical | - |
| BH | v. TOCCU RES Reservé | Logical | - |
| BI | v. TOCCU TTL Totalement Libre | Logical | - |

### 11.2 Autres (31)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | >DateDebut | Date | - |
| B | >HeureDebut | Alpha | - |
| C | >DateFin | Date | - |
| D | >HeureFin | Alpha | - |
| E | <Total | Numeric | - |
| F | <NbSelect | Numeric | - |
| G | RetBatiment-------------------- | Logical | - |
| H | w0_BatiMin | Alpha | - |
| I | w0_BatiMax | Alpha | - |
| J | RetLogement-------------------- | Logical | - |
| K | w0_LogMin | Alpha | 1x refs |
| L | w0_LogMax | Alpha | - |
| M | RetEnsemble-------------------- | Logical | - |
| N | w0_EnsMin | Alpha | - |
| O | w0_EnsMax | Alpha | - |
| P | RetEtage----------------------- | Logical | - |
| Q | w0_EtageMin | Alpha | 1x refs |
| R | w0_EtageMax | Alpha | - |
| S | w1_FaitLoge | Logical | - |
| T | w1_FaitBati | Logical | - |
| U | w1_FaitEtag | Logical | - |
| V | w1_FaitVue | Logical | - |
| W | w1_FaitComm | Logical | - |
| X | w1_FaitAtt | Logical | - |
| Y | w1_FaitHand | Logical | - |
| Z | w1_FaitSta | Logical | 1x refs |
| BA | w1_FaitLieu | Logical | - |
| BB | w1_FaitClog | Logical | - |
| BC | w1_FaitZone | Logical | - |
| BD | w1_FaitSect | Logical | 1x refs |
| BE | w1_FaitOccu | Logical | - |

<details>
<summary>Toutes les 35 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| V. | **BF** | v. TOCCU OCC Complet | Logical |
| V. | **BG** | v. TOCCU BLK Bloqué | Logical |
| V. | **BH** | v. TOCCU RES Reservé | Logical |
| V. | **BI** | v. TOCCU TTL Totalement Libre | Logical |
| Autre | **A** | >DateDebut | Date |
| Autre | **B** | >HeureDebut | Alpha |
| Autre | **C** | >DateFin | Date |
| Autre | **D** | >HeureFin | Alpha |
| Autre | **E** | <Total | Numeric |
| Autre | **F** | <NbSelect | Numeric |
| Autre | **G** | RetBatiment-------------------- | Logical |
| Autre | **H** | w0_BatiMin | Alpha |
| Autre | **I** | w0_BatiMax | Alpha |
| Autre | **J** | RetLogement-------------------- | Logical |
| Autre | **K** | w0_LogMin | Alpha |
| Autre | **L** | w0_LogMax | Alpha |
| Autre | **M** | RetEnsemble-------------------- | Logical |
| Autre | **N** | w0_EnsMin | Alpha |
| Autre | **O** | w0_EnsMax | Alpha |
| Autre | **P** | RetEtage----------------------- | Logical |
| Autre | **Q** | w0_EtageMin | Alpha |
| Autre | **R** | w0_EtageMax | Alpha |
| Autre | **S** | w1_FaitLoge | Logical |
| Autre | **T** | w1_FaitBati | Logical |
| Autre | **U** | w1_FaitEtag | Logical |
| Autre | **V** | w1_FaitVue | Logical |
| Autre | **W** | w1_FaitComm | Logical |
| Autre | **X** | w1_FaitAtt | Logical |
| Autre | **Y** | w1_FaitHand | Logical |
| Autre | **Z** | w1_FaitSta | Logical |
| Autre | **BA** | w1_FaitLieu | Logical |
| Autre | **BB** | w1_FaitClog | Logical |
| Autre | **BC** | w1_FaitZone | Logical |
| Autre | **BD** | w1_FaitSect | Logical |
| Autre | **BE** | w1_FaitOccu | Logical |

</details>

## 12. EXPRESSIONS

**16 / 16 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONSTANTE | 6 | 0 |
| REFERENCE_VG | 1 | 0 |
| CAST_LOGIQUE | 1 | 0 |
| OTHER | 8 | 0 |

### 12.2 Expressions cles par type

#### CONSTANTE (6 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 5 | `'VENSE'` | - |
| CONSTANTE | 6 | `'TETAG'` | - |
| CONSTANTE | 16 | `0` | - |
| CONSTANTE | 2 | `'L'` | - |
| CONSTANTE | 3 | `'VBATI'` | - |
| ... | | *+1 autres* | |

#### REFERENCE_VG (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 1 | `VG1` | - |

#### CAST_LOGIQUE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 7 | `'TRUE'LOG` | - |

#### OTHER (8 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 13 | `[AU]` | - |
| OTHER | 12 | `[AO]` | - |
| OTHER | 15 | `[BJ]` | - |
| OTHER | 14 | `w1_FaitSect [BD]` | - |
| OTHER | 9 | `w0_EtageMin [Q]` | - |
| ... | | *+3 autres* | |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Liste occupation (IDE 136)](PBP-IDE-136.md) -> **Calcul recherche logement (IDE 140)**

```mermaid
graph LR
    T140[140 Calcul recherche l...]
    style T140 fill:#58a6ff
    CC136[136 Liste occupation]
    style CC136 fill:#8b5cf6
    CC136 --> T140
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [136](PBP-IDE-136.md) | Liste occupation | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T140[140 Calcul recherche l...]
    style T140 fill:#58a6ff
    NONE[Aucun callee]
    T140 -.-> NONE
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
| Lignes de logique | 392 | Taille moyenne |
| Expressions | 16 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0.5% (2 / 392) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (6 taches: 1 ecran, 5 traitements)

- **Strategie** : Orchestrateur avec 1 ecrans (Razor/React) et 5 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- Decomposer les taches en services unitaires testables.

#### Consultation (3 taches: 1 ecran, 2 traitements)

- **Strategie** : Composants de recherche/selection en modales.
- 1 ecran : Affiche

#### Validation (3 taches: 0 ecran, 3 traitements)

- **Strategie** : FluentValidation avec validators specifiques.
- Chaque tache de validation -> un validator injectable

#### Creation (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Repository pattern avec Entity Framework Core.
- Insertion via `IRepository<T>.CreateAsync()`

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| tempo_ecran_mecano | Table WRITE (Temp) | 2x | Schema + repository |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 15:29*
