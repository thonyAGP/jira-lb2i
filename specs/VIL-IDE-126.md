# VIL IDE 126 - Integrite personnel identites

> **Analyse**: Phases 1-4 2026-02-03 09:34 -> 09:34 (18s) | Assemblage 09:34
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | VIL |
| IDE Position | 126 |
| Nom Programme | Integrite personnel identites |
| Fichier source | `Prg_126.xml` |
| Domaine metier | General |
| Taches | 12 (1 ecrans visibles) |
| Tables modifiees | 5 |
| Programmes appeles | 1 |

## 2. DESCRIPTION FONCTIONNELLE

**Integrite personnel identites** assure la gestion complete de ce processus, accessible depuis [Traitement integrite base (IDE 124)](VIL-IDE-124.md).

Le flux de traitement s'organise en **5 blocs fonctionnels** :

- **Traitement** (6 taches) : traitements metier divers
- **Validation** (2 taches) : controles et verifications de coherence
- **Creation** (2 taches) : insertion d'enregistrements en base (mouvements, prestations)
- **Calcul** (1 tache) : calculs de montants, stocks ou compteurs
- **Consultation** (1 tache) : ecrans de recherche, selection et consultation

**Donnees modifiees** : 5 tables en ecriture (gm-recherche_____gmr, gm-complet_______gmc, hebergement______heb, compte_gm________cgm, fi_complet_______gm_go).

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (6 taches)

- **126** - Module des Identites
- **126.1** - Determination Age Bebe
- **126.2** - Test Base Personnel
- **126.3** - Veuillez patienter ... **[[ECRAN]](#ecran-t4)**
- **126.3.1** - Veuillez patienter... **[[ECRAN]](#ecran-t5)**
- **126.3.1.7** - Modif Hebergement

#### Phase 2 : Creation (2 taches)

- **126.3.1.1** - Creation Complet
- **126.3.1.5** - Creation Complet

#### Phase 3 : Calcul (1 tache)

- **126.3.1.2** - Creation Compte

#### Phase 4 : Consultation (1 tache)

- **126.3.1.3** - Creation Recherche

Delegue a : [   Rech. Age Debut Sejour (IDE 129)](VIL-IDE-129.md)

#### Phase 5 : Validation (2 taches)

- **126.3.1.4** - Creation Validation
- **126.3.1.6** - Verif si Greek

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| gm-recherche_____gmr | **W** (3 usages) | Index de recherche |
| hebergement______heb | R/**W** (2 usages) | Hebergement (chambres) |
| gm-complet_______gmc | **W**/L (2 usages) |  |
| compte_gm________cgm | **W** (1 usages) | Comptes GM (generaux) |
| fi_complet_______gm_go | **W** (1 usages) |  |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (6 taches)

Traitements internes.

---

#### <a id="t1"></a>126 - Module des Identites

**Role** : Tache d'orchestration : point d'entree du programme (6 sous-taches). Coordonne l'enchainement des traitements.

<details>
<summary>5 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [126.1](#t2) | Determination Age Bebe | Traitement |
| [126.2](#t3) | Test Base Personnel | Traitement |
| [126.3](#t4) | Veuillez patienter ... **[[ECRAN]](#ecran-t4)** | Traitement |
| [126.3.1](#t5) | Veuillez patienter... **[[ECRAN]](#ecran-t5)** | Traitement |
| [126.3.1.7](#t12) | Modif Hebergement | Traitement |

</details>

---

#### <a id="t2"></a>126.1 - Determination Age Bebe

**Role** : Traitement : Determination Age Bebe.
**Variables liees** : A (W0-Age Bebe)

---

#### <a id="t3"></a>126.2 - Test Base Personnel

**Role** : Verification : Test Base Personnel.
**Variables liees** : B (W0-Base Vide), I (W0-code base occup)

---

#### <a id="t4"></a>126.3 - Veuillez patienter ... [[ECRAN]](#ecran-t4)

**Role** : Traitement : Veuillez patienter ....
**Ecran** : 424 x 56 DLU (MDI) | [Voir mockup](#ecran-t4)

---

#### <a id="t5"></a>126.3.1 - Veuillez patienter... [[ECRAN]](#ecran-t5)

**Role** : Traitement : Veuillez patienter....
**Ecran** : 422 x 56 DLU (MDI) | [Voir mockup](#ecran-t5)

---

#### <a id="t12"></a>126.3.1.7 - Modif Hebergement

**Role** : Traitement : Modif Hebergement.
**Variables liees** : G (W0-autorisation modif)


### 3.2 Creation (2 taches)

Insertion de nouveaux enregistrements en base.

---

#### <a id="t6"></a>126.3.1.1 - Creation Complet

**Role** : Creation d'enregistrement : Creation Complet.
**Variables liees** : F (W0-autorisation creation)

---

#### <a id="t10"></a>126.3.1.5 - Creation Complet

**Role** : Creation d'enregistrement : Creation Complet.
**Variables liees** : F (W0-autorisation creation)


### 3.3 Calcul (1 tache)

Calculs metier : montants, stocks, compteurs.

---

#### <a id="t7"></a>126.3.1.2 - Creation Compte

**Role** : Creation d'enregistrement : Creation Compte.
**Variables liees** : E (W0-numero compte memo), F (W0-autorisation creation), O (W0-Compte)


### 3.4 Consultation (1 tache)

Ecrans de recherche et consultation.

---

#### <a id="t8"></a>126.3.1.3 - Creation Recherche

**Role** : Creation d'enregistrement : Creation Recherche.
**Variables liees** : F (W0-autorisation creation)
**Delegue a** : [   Rech. Age Debut Sejour (IDE 129)](VIL-IDE-129.md)


### 3.5 Validation (2 taches)

Controles de coherence : 2 taches verifient les donnees et conditions.

---

#### <a id="t9"></a>126.3.1.4 - Creation Validation

**Role** : Verification : Creation Validation.
**Variables liees** : F (W0-autorisation creation)

---

#### <a id="t11"></a>126.3.1.6 - Verif si Greek

**Role** : Verification : Verif si Greek.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Traitement integrite base (IDE 124)](VIL-IDE-124.md)
- **Appelle**: 1 programmes | **Tables**: 12 (W:5 R:4 L:7) | **Taches**: 12 | **Expressions**: 4

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 12)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 126.3 | 126.3 | Veuillez patienter ... | MDI | 424 | 56 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t4"></a>126.3 - Veuillez patienter ...
**Tache** : [126.3](#t4) | **Type** : MDI | **Dimensions** : 424 x 56 DLU
**Bloc** : Traitement | **Titre IDE** : Veuillez patienter ...

<!-- FORM-DATA:
{
    "width":  424,
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
                         "x":  117,
                         "type":  "label",
                         "var":  "",
                         "y":  10,
                         "w":  275,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "7",
                         "text":  "Integrite de la base",
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
                         "x":  38,
                         "type":  "label",
                         "var":  "",
                         "y":  39,
                         "w":  347,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Verification des GO",
                         "parent":  null
                     },
                     {
                         "x":  1,
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
    "taskId":  "126.3",
    "height":  56
}
-->

## 9. NAVIGATION

Ecran unique: **Veuillez patienter ...**

### 9.3 Structure hierarchique (12 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **126.1** | [**Module des Identites** (126)](#t1) | MDI | - | Traitement |
| 126.1.1 | [Determination Age Bebe (126.1)](#t2) | MDI | - | |
| 126.1.2 | [Test Base Personnel (126.2)](#t3) | MDI | - | |
| 126.1.3 | [Veuillez patienter ... (126.3)](#t4) [mockup](#ecran-t4) | MDI | 424x56 | |
| 126.1.4 | [Veuillez patienter... (126.3.1)](#t5) [mockup](#ecran-t5) | MDI | 422x56 | |
| 126.1.5 | [Modif Hebergement (126.3.1.7)](#t12) | - | - | |
| **126.2** | [**Creation Complet** (126.3.1.1)](#t6) | MDI | - | Creation |
| 126.2.1 | [Creation Complet (126.3.1.5)](#t10) | MDI | - | |
| **126.3** | [**Creation Compte** (126.3.1.2)](#t7) | MDI | - | Calcul |
| **126.4** | [**Creation Recherche** (126.3.1.3)](#t8) | MDI | - | Consultation |
| **126.5** | [**Creation Validation** (126.3.1.4)](#t9) | MDI | - | Validation |
| 126.5.1 | [Verif si Greek (126.3.1.6)](#t11) | MDI | - | |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Affichage Personnel Nom]
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

### Tables utilisees (12)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 30 | gm-recherche_____gmr | Index de recherche | DB |   | **W** |   | 3 |
| 31 | gm-complet_______gmc |  | DB |   | **W** | L | 2 |
| 34 | hebergement______heb | Hebergement (chambres) | DB | R | **W** |   | 2 |
| 35 | personnel_go______go |  | DB | R |   | L | 2 |
| 47 | compte_gm________cgm | Comptes GM (generaux) | DB |   | **W** |   | 1 |
| 79 | gratuites________gra |  | DB |   |   | L | 1 |
| 113 | tables_village |  | DB | R |   | L | 2 |
| 117 | tables_services | Services / filieres | DB |   |   | L | 1 |
| 119 | tables_pays_tel_ |  | DB |   |   | L | 1 |
| 120 | tables_qualites__qua |  | DB | R |   |   | 1 |
| 131 | fichier_validation |  | DB |   |   | L | 1 |
| 315 | fi_complet_______gm_go |  | DB |   | **W** |   | 1 |

### Colonnes par table (2 / 8 tables avec colonnes identifiees)

<details>
<summary>Table 30 - gm-recherche_____gmr (**W**) - 3 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | W1-Fin de Tache | W | Logical |
| B | W1-Arrêt | W | Alpha |
| C | W1-Age codifie | W | Alpha |
| D | W1-Bebe | W | Alpha |
| E | W1-Acces planning | W | Alpha |
| F | W1-NB mois | W | Numeric |
| G | W1- Numero compte memo | W | Numeric |
| H | W1-Select qualite | W | Alpha |
| I | W1-Select titre | W | Alpha |
| J | W1-Select Service | W | Alpha |
| K | W1-Select Contrat | W | Alpha |
| L | W1-select nationalite | W | Alpha |
| M | W1-Select Langue | W | Alpha |
| N | v.retour gratuités | W | Logical |

</details>

<details>
<summary>Table 31 - gm-complet_______gmc (**W**/L) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 34 - hebergement______heb (R/**W**) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 35 - personnel_go______go (R/L) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 47 - compte_gm________cgm (**W**) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | v. prise en compte greek | W | Logical |
| E | W0-numero compte memo | W | Numeric |
| G | W1- Numero compte memo | W | Numeric |
| O | W0-Compte | W | Numeric |

</details>

<details>
<summary>Table 113 - tables_village (R/L) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 120 - tables_qualites__qua (R) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 315 - fi_complet_______gm_go (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Variables de session (1)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| D | v.ecran titre | Alpha | - |

### 11.2 Autres (16)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | W0-Age Bebe | Numeric | - |
| B | W0-Base Vide | Alpha | - |
| C | WO-Valeur tri | Numeric | - |
| E | W0-numero compte memo | Numeric | [126.3.1.2](#t7) |
| F | W0-autorisation creation | Alpha | - |
| G | W0-autorisation modif | Alpha | - |
| H | W0-autorisation | Alpha | - |
| I | W0-code base occup | Alpha | - |
| J | W0-heberg | Alpha | - |
| K | W0-Saisie langue ? | Alpha | - |
| L | W0-Bloquage effectue | Alpha | - |
| M | W0-Table service | Alpha | - |
| N | W0-Code fonction | Alpha | - |
| O | W0-Compte | Numeric | - |
| P | W0-Adhesion | Numeric | - |
| Q | WO-Fin de tache | Logical | - |

<details>
<summary>Toutes les 17 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| V. | **D** | v.ecran titre | Alpha |
| Autre | **A** | W0-Age Bebe | Numeric |
| Autre | **B** | W0-Base Vide | Alpha |
| Autre | **C** | WO-Valeur tri | Numeric |
| Autre | **E** | W0-numero compte memo | Numeric |
| Autre | **F** | W0-autorisation creation | Alpha |
| Autre | **G** | W0-autorisation modif | Alpha |
| Autre | **H** | W0-autorisation | Alpha |
| Autre | **I** | W0-code base occup | Alpha |
| Autre | **J** | W0-heberg | Alpha |
| Autre | **K** | W0-Saisie langue ? | Alpha |
| Autre | **L** | W0-Bloquage effectue | Alpha |
| Autre | **M** | W0-Table service | Alpha |
| Autre | **N** | W0-Code fonction | Alpha |
| Autre | **O** | W0-Compte | Numeric |
| Autre | **P** | W0-Adhesion | Numeric |
| Autre | **Q** | WO-Fin de tache | Logical |

</details>

## 12. EXPRESSIONS

**4 / 4 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONSTANTE | 3 | 0 |
| CONDITION | 1 | 0 |

### 12.2 Expressions cles par type

#### CONSTANTE (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 4 | `2` | - |
| CONSTANTE | 2 | `''` | - |
| CONSTANTE | 1 | `'N'` | - |

#### CONDITION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 3 | `W0-numero compte memo [E]=0` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Traitement integrite base (IDE 124)](VIL-IDE-124.md) -> **Integrite personnel identites (IDE 126)**

```mermaid
graph LR
    T126[126 Integrite personne...]
    style T126 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC149[149 Start]
    style CC149 fill:#f59e0b
    CC9[9 Pilotage avant sessions]
    style CC9 fill:#f59e0b
    CC124[124 Traitement integri...]
    style CC124 fill:#3fb950
    CC9 --> CC124
    CC149 --> CC9
    CC1 --> CC149
    CC124 --> T126
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [124](VIL-IDE-124.md) | Traitement integrite base | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T126[126 Integrite personne...]
    style T126 fill:#58a6ff
    C129[129 Rech. Age Debut Se...]
    T126 --> C129
    style C129 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [129](VIL-IDE-129.md) |    Rech. Age Debut Sejour | 1 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 414 | Taille moyenne |
| Expressions | 4 | Peu de logique |
| Tables WRITE | 5 | Impact modere |
| Sous-programmes | 1 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0.2% (1 / 414) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (6 taches: 2 ecrans, 4 traitements)

- **Strategie** : Orchestrateur avec 2 ecrans (Razor/React) et 4 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 1 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Creation (2 taches: 0 ecran, 2 traitements)

- **Strategie** : Repository pattern avec Entity Framework Core.
- Insertion via `IRepository<T>.CreateAsync()`

#### Calcul (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Services de calcul purs (Domain Services).
- Migrer la logique de calcul (stock, compteurs, montants)

#### Consultation (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Composants de recherche/selection en modales.

#### Validation (2 taches: 0 ecran, 2 traitements)

- **Strategie** : FluentValidation avec validators specifiques.
- Chaque tache de validation -> un validator injectable

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| gm-recherche_____gmr | Table WRITE (Database) | 3x | Schema + repository |
| gm-complet_______gmc | Table WRITE (Database) | 1x | Schema + repository |
| hebergement______heb | Table WRITE (Database) | 1x | Schema + repository |
| compte_gm________cgm | Table WRITE (Database) | 1x | Schema + repository |
| fi_complet_______gm_go | Table WRITE (Database) | 1x | Schema + repository |
| [   Rech. Age Debut Sejour (IDE 129)](VIL-IDE-129.md) | Sous-programme | 1x | Normale - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 09:34*
