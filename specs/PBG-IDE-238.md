# PBG IDE 238 - Traitement Annulation

> **Analyse**: Phases 1-4 2026-02-03 10:26 -> 10:27 (22s) | Assemblage 10:27
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBG |
| IDE Position | 238 |
| Nom Programme | Traitement Annulation |
| Fichier source | `Prg_238.xml` |
| Domaine metier | General |
| Taches | 15 (1 ecrans visibles) |
| Tables modifiees | 3 |
| Programmes appeles | 5 |

## 2. DESCRIPTION FONCTIONNELLE

**Traitement Annulation** assure la gestion complete de ce processus, accessible depuis [Traitement des arrivants (IDE 206)](PBG-IDE-206.md).

Le flux de traitement s'organise en **4 blocs fonctionnels** :

- **Traitement** (12 taches) : traitements metier divers
- **Initialisation** (1 tache) : reinitialisation d'etats et de variables de travail
- **Validation** (1 tache) : controles et verifications de coherence
- **Creation** (1 tache) : insertion d'enregistrements en base (mouvements, prestations)

**Donnees modifiees** : 3 tables en ecriture (annulation_______anu, gm_supprimes_en_modif, pv_pms_prestations_tmp).

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (12 taches)

- **238** - Veuillez patienter ... **[[ECRAN]](#ecran-t1)**
- **238.1** - Age Enfant/Bebe
- **238.2** - Chemin IDE.DAT
- **238.3** - Import IDE.DAT
- **238.3.2** - Annulation GM
- **238.3.2.1.1** - Avertissement Import
- **238.3.2.2** - Cloture Caisse en cours ?
- **238.3.2.4** - Maj ASD
- **238.3.2.5** - Avertissement Import
- **238.4** - Suppression enregistrement = 0
- **238.5** - delete ANNU
- **238.5.1** - Suppression ANU

Delegue a : [Demarquage Caisse (IDE 176)](PBG-IDE-176.md), [   Suppression Client (IDE 82)](PBG-IDE-82.md), [Marquage Caisse(S) (IDE 177)](PBG-IDE-177.md)

#### Phase 2 : Creation (1 tache)

- **238.3.1** - Creation Annulation

#### Phase 3 : Validation (1 tache)

- **238.3.2.1** - Verif. existence ?

Delegue a : [Verification Suppression (IDE 182)](PBG-IDE-182.md)

#### Phase 4 : Initialisation (1 tache)

- **238.3.2.3** - Definition N° cas

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| annulation_______anu | **W** (3 usages) |  |
| gm_supprimes_en_modif | **W** (2 usages) |  |
| pv_pms_prestations_tmp | **W** (1 usages) | Prestations/services vendus |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (12 taches)

Traitements internes.

---

#### <a id="t1"></a>238 - Veuillez patienter ... [[ECRAN]](#ecran-t1)

**Role** : Tache d'orchestration : point d'entree du programme (12 sous-taches). Coordonne l'enchainement des traitements.
**Ecran** : 427 x 68 DLU (MDI) | [Voir mockup](#ecran-t1)

<details>
<summary>11 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [238.1](#t2) | Age Enfant/Bebe | Traitement |
| [238.2](#t3) | Chemin IDE.DAT | Traitement |
| [238.3](#t4) | Import IDE.DAT | Traitement |
| [238.3.2](#t6) | Annulation GM | Traitement |
| [238.3.2.1.1](#t8) | Avertissement Import | Traitement |
| [238.3.2.2](#t9) | Cloture Caisse en cours ? | Traitement |
| [238.3.2.4](#t11) | Maj ASD | Traitement |
| [238.3.2.5](#t12) | Avertissement Import | Traitement |
| [238.4](#t13) | Suppression enregistrement = 0 | Traitement |
| [238.5](#t14) | delete ANNU | Traitement |
| [238.5.1](#t15) | Suppression ANU | Traitement |

</details>

---

#### <a id="t2"></a>238.1 - Age Enfant/Bebe

**Role** : Traitement : Age Enfant/Bebe.

---

#### <a id="t3"></a>238.2 - Chemin IDE.DAT

**Role** : Traitement : Chemin IDE.DAT.

---

#### <a id="t4"></a>238.3 - Import IDE.DAT

**Role** : Traitement : Import IDE.DAT.
**Variables liees** : D (P0 N° Import)

---

#### <a id="t6"></a>238.3.2 - Annulation GM

**Role** : Traitement : Annulation GM.
**Variables liees** : C (P0-Nb Annulation)

---

#### <a id="t8"></a>238.3.2.1.1 - Avertissement Import

**Role** : Traitement : Avertissement Import.
**Variables liees** : D (P0 N° Import)

---

#### <a id="t9"></a>238.3.2.2 - Cloture Caisse en cours ?

**Role** : Traitement : Cloture Caisse en cours ?.

---

#### <a id="t11"></a>238.3.2.4 - Maj ASD

**Role** : Traitement : Maj ASD.

---

#### <a id="t12"></a>238.3.2.5 - Avertissement Import

**Role** : Traitement : Avertissement Import.
**Variables liees** : D (P0 N° Import)

---

#### <a id="t13"></a>238.4 - Suppression enregistrement = 0

**Role** : Traitement : Suppression enregistrement = 0.

---

#### <a id="t14"></a>238.5 - delete ANNU

**Role** : Traitement : delete ANNU.
**Variables liees** : C (P0-Nb Annulation)

---

#### <a id="t15"></a>238.5.1 - Suppression ANU

**Role** : Traitement : Suppression ANU.


### 3.2 Creation (1 tache)

Insertion de nouveaux enregistrements en base.

---

#### <a id="t5"></a>238.3.1 - Creation Annulation

**Role** : Creation d'enregistrement : Creation Annulation.
**Variables liees** : C (P0-Nb Annulation)


### 3.3 Validation (1 tache)

Controles de coherence : 1 tache verifie les donnees et conditions.

---

#### <a id="t7"></a>238.3.2.1 - Verif. existence ?

**Role** : Verification : Verif. existence ?.
**Delegue a** : [Verification Suppression (IDE 182)](PBG-IDE-182.md)


### 3.4 Initialisation (1 tache)

Reinitialisation d'etats et variables de travail.

---

#### <a id="t10"></a>238.3.2.3 - Definition N° cas

**Role** : Reinitialisation : Definition N° cas.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Traitement des arrivants (IDE 206)](PBG-IDE-206.md)
- **Appelle**: 5 programmes | **Tables**: 11 (W:3 R:5 L:4) | **Taches**: 15 | **Expressions**: 6

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 15)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 238 | 238 | Veuillez patienter ... | MDI | 427 | 68 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>238 - Veuillez patienter ...
**Tache** : [238](#t1) | **Type** : MDI | **Dimensions** : 427 x 68 DLU
**Bloc** : Traitement | **Titre IDE** : Veuillez patienter ...

<!-- FORM-DATA:
{
    "width":  427,
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
                         "text":  "Traitement Annulation",
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
    "taskId":  "238",
    "height":  68
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

Ecran unique: **Veuillez patienter ...**

### 9.3 Structure hierarchique (15 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **238.1** | [**Veuillez patienter ...** (238)](#t1) [mockup](#ecran-t1) | MDI | 427x68 | Traitement |
| 238.1.1 | [Age Enfant/Bebe (238.1)](#t2) | MDI | - | |
| 238.1.2 | [Chemin IDE.DAT (238.2)](#t3) | MDI | - | |
| 238.1.3 | [Import IDE.DAT (238.3)](#t4) | MDI | - | |
| 238.1.4 | [Annulation GM (238.3.2)](#t6) | MDI | - | |
| 238.1.5 | [Avertissement Import (238.3.2.1.1)](#t8) | MDI | - | |
| 238.1.6 | [Cloture Caisse en cours ? (238.3.2.2)](#t9) | MDI | - | |
| 238.1.7 | [Maj ASD (238.3.2.4)](#t11) | MDI | - | |
| 238.1.8 | [Avertissement Import (238.3.2.5)](#t12) | MDI | - | |
| 238.1.9 | [Suppression enregistrement = 0 (238.4)](#t13) | MDI | - | |
| 238.1.10 | [delete ANNU (238.5)](#t14) | MDI | - | |
| 238.1.11 | [Suppression ANU (238.5.1)](#t15) | MDI | - | |
| **238.2** | [**Creation Annulation** (238.3.1)](#t5) | MDI | - | Creation |
| **238.3** | [**Verif. existence ?** (238.3.2.1)](#t7) | MDI | - | Validation |
| **238.4** | [**Definition N° cas** (238.3.2.3)](#t10) | MDI | - | Initialisation |

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

### Tables utilisees (11)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 23 | reseau_cloture___rec | Donnees reseau/cloture | DB | R |   |   | 1 |
| 30 | gm-recherche_____gmr | Index de recherche | DB | R |   |   | 2 |
| 31 | gm-complet_______gmc |  | DB | R |   | L | 2 |
| 34 | hebergement______heb | Hebergement (chambres) | DB |   |   | L | 1 |
| 113 | tables_village |  | DB | R |   |   | 1 |
| 118 | tables_imports |  | DB | R |   |   | 1 |
| 131 | fichier_validation |  | DB |   |   | L | 1 |
| 133 | new_asd |  | DB |   |   | L | 1 |
| 170 | annulation_______anu |  | DB |   | **W** |   | 3 |
| 549 | gm_supprimes_en_modif |  | TMP |   | **W** |   | 2 |
| 574 | pv_pms_prestations_tmp | Prestations/services vendus | TMP |   | **W** |   | 1 |

### Colonnes par table (2 / 8 tables avec colonnes identifiees)

<details>
<summary>Table 23 - reseau_cloture___rec (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | W3 Cloture en cours | R | Numeric |

</details>

<details>
<summary>Table 30 - gm-recherche_____gmr (R) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 31 - gm-complet_______gmc (R/L) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 113 - tables_village (R) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 118 - tables_imports (R) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 170 - annulation_______anu (**W**) - 3 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| C | P0-Nb Annulation | W | Numeric |

</details>

<details>
<summary>Table 549 - gm_supprimes_en_modif (**W**) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 574 - pv_pms_prestations_tmp (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (1)

Variables recues du programme appelant ([Traitement des arrivants (IDE 206)](PBG-IDE-206.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| D | P0 N° Import | Numeric | - |

### 11.2 Variables de session (1)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| R | V.Compteur | Numeric | - |

### 11.3 Variables de travail (2)

Variables internes au programme.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| P | W0 Age Bebe | Numeric | - |
| Q | W0 Age Enfant | Numeric | - |

### 11.4 Autres (14)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P0-Code Societe | Alpha | - |
| B | P0-Lieu de Sejour | Alpha | - |
| C | P0-Nb Annulation | Numeric | [238.3.1](#t5), [238.3.2](#t6) |
| E | W0-Operande | Numeric | - |
| F | W0-Operateur | Numeric | - |
| G | W0-Pourcentage | Numeric | - |
| H | W0-Calcul Pourcent | Numeric | - |
| I | W0-Ligne de Commande | Alpha | - |
| J | W0-Type Client | Alpha | 1x refs |
| K | W0-N°Adherent | Numeric | - |
| L | W0-Filiation Adh. | Numeric | - |
| M | W0-Type Accompagnant | Alpha | - |
| N | W0-N°Accompagnant | Numeric | - |
| O | W0-Filiation Acc. | Numeric | - |

<details>
<summary>Toutes les 18 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| P0 | **D** | P0 N° Import | Numeric |
| W0 | **P** | W0 Age Bebe | Numeric |
| W0 | **Q** | W0 Age Enfant | Numeric |
| V. | **R** | V.Compteur | Numeric |
| Autre | **A** | P0-Code Societe | Alpha |
| Autre | **B** | P0-Lieu de Sejour | Alpha |
| Autre | **C** | P0-Nb Annulation | Numeric |
| Autre | **E** | W0-Operande | Numeric |
| Autre | **F** | W0-Operateur | Numeric |
| Autre | **G** | W0-Pourcentage | Numeric |
| Autre | **H** | W0-Calcul Pourcent | Numeric |
| Autre | **I** | W0-Ligne de Commande | Alpha |
| Autre | **J** | W0-Type Client | Alpha |
| Autre | **K** | W0-N°Adherent | Numeric |
| Autre | **L** | W0-Filiation Adh. | Numeric |
| Autre | **M** | W0-Type Accompagnant | Alpha |
| Autre | **N** | W0-N°Accompagnant | Numeric |
| Autre | **O** | W0-Filiation Acc. | Numeric |

</details>

## 12. EXPRESSIONS

**6 / 6 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCULATION | 4 | 0 |
| CALCUL | 1 | 0 |
| CONSTANTE | 1 | 0 |

### 12.2 Expressions cles par type

#### CALCULATION (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 5 | `([AK]/VG8)*100` | - |
| CALCULATION | 6 | `([AK]/VG8)*50` | - |
| CALCULATION | 2 | `P0-Nb Annulation [C]/29` | - |
| CALCULATION | 3 | `P0-Nb Annulation [C]/98` | - |

#### CALCUL (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCUL | 4 | `Fix((FileInfo (W0-Type Client [J], 5)/40),10,0)` | - |

#### CONSTANTE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 1 | `''` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Traitement des arrivants (IDE 206)](PBG-IDE-206.md) -> **Traitement Annulation (IDE 238)**

```mermaid
graph LR
    T238[238 Traitement Annulation]
    style T238 fill:#58a6ff
    CC206[206 Traitement des arr...]
    style CC206 fill:#8b5cf6
    CC206 --> T238
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [206](PBG-IDE-206.md) | Traitement des arrivants | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T238[238 Traitement Annulation]
    style T238 fill:#58a6ff
    C176[176 Demarquage Caisse]
    T238 --> C176
    style C176 fill:#3fb950
    C82[82 Suppression Client]
    T238 --> C82
    style C82 fill:#3fb950
    C177[177 Marquage CaisseS]
    T238 --> C177
    style C177 fill:#3fb950
    C182[182 Verification Suppr...]
    T238 --> C182
    style C182 fill:#3fb950
    C269[269 Separation de comptes]
    T238 --> C269
    style C269 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [176](PBG-IDE-176.md) | Demarquage Caisse | 2 | Sous-programme |
| [82](PBG-IDE-82.md) |    Suppression Client | 1 | Sous-programme |
| [177](PBG-IDE-177.md) | Marquage Caisse(S) | 1 | Sous-programme |
| [182](PBG-IDE-182.md) | Verification Suppression | 1 | Controle/validation |
| [269](PBG-IDE-269.md) | Separation de comptes | 1 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 335 | Taille moyenne |
| Expressions | 6 | Peu de logique |
| Tables WRITE | 3 | Impact modere |
| Sous-programmes | 5 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0.6% (2 / 335) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (12 taches: 1 ecran, 11 traitements)

- **Strategie** : Orchestrateur avec 1 ecrans (Razor/React) et 11 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 5 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Creation (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Repository pattern avec Entity Framework Core.
- Insertion via `IRepository<T>.CreateAsync()`

#### Validation (1 tache: 0 ecran, 1 traitement)

- **Strategie** : FluentValidation avec validators specifiques.
- Chaque tache de validation -> un validator injectable

#### Initialisation (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Constructeur/methode `InitAsync()` dans l'orchestrateur.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| annulation_______anu | Table WRITE (Database) | 3x | Schema + repository |
| gm_supprimes_en_modif | Table WRITE (Temp) | 2x | Schema + repository |
| pv_pms_prestations_tmp | Table WRITE (Temp) | 1x | Schema + repository |
| [Demarquage Caisse (IDE 176)](PBG-IDE-176.md) | Sous-programme | 2x | Haute - Sous-programme |
| [Verification Suppression (IDE 182)](PBG-IDE-182.md) | Sous-programme | 1x | Normale - Controle/validation |
| [Separation de comptes (IDE 269)](PBG-IDE-269.md) | Sous-programme | 1x | Normale - Sous-programme |
| [   Suppression Client (IDE 82)](PBG-IDE-82.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Marquage Caisse(S) (IDE 177)](PBG-IDE-177.md) | Sous-programme | 1x | Normale - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 10:27*
