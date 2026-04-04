# PVE IDE 125 - Liste cloture service

> **Analyse**: Phases 1-4 2026-02-03 09:34 -> 09:34 (18s) | Assemblage 09:34
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PVE |
| IDE Position | 125 |
| Nom Programme | Liste cloture service |
| Fichier source | `Prg_125.xml` |
| Domaine metier | General |
| Taches | 32 (0 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Liste cloture service** assure la gestion complete de ce processus, accessible depuis [Fin de journée (IDE 114)](PVE-IDE-114.md), [Fin de journée(Telecollecte) (IDE 404)](PVE-IDE-404.md).

Le flux de traitement s'organise en **3 blocs fonctionnels** :

- **Saisie** (11 taches) : ecrans de saisie utilisateur (formulaires, champs, donnees)
- **Traitement** (11 taches) : traitements metier divers
- **Calcul** (10 taches) : calculs de montants, stocks ou compteurs

**Donnees modifiees** : 1 tables en ecriture (historique_pabx_restruc).

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (11 taches)

- **125** - Liste cloture service
- **125.1** - qualification du service
- **125.2** - Lecture des PC v1
- **125.2.3** - Lecture des od
- **125.2.4** - Lecture des od bout
- **125.2.5** - Lecture des TPE
- **125.3** - Lecture des PC v1
- **125.3.3** - Lecture des od
- **125.3.4** - Lecture des od bout
- **125.3.5** - Lecture des TPE
- **125.5** - impression

#### Phase 2 : Saisie (11 taches)

- **125.2.1** - Lecture saisie TPE
- **125.2.1.1** - tempo saisie
- **125.2.2** - Lecture des ventes
- **125.2.5.1** - Lecture saisie TPE
- **125.2.5.1.1** - tempo saisie
- **125.3.1** - Lecture saisie TPE
- **125.3.1.1** - tempo saisie
- **125.3.2** - Lecture des ventes
- **125.3.5.1** - Lecture saisie TPE
- **125.3.5.1.1** - tempo saisie
- **125.4** - Lecture saisie OD

#### Phase 3 : Calcul (10 taches)

- **125.2.2.1** - tempo calcul
- **125.2.3.1** - tempo calcul
- **125.2.4.1** - tempo calcul
- **125.2.6** - Comptes Boutique
- **125.2.6.1** - tempo calcul
- **125.3.2.1** - tempo calcul
- **125.3.3.1** - tempo calcul
- **125.3.4.1** - tempo calcul
- **125.3.6** - Comptes Boutique
- **125.3.6.1** - tempo calcul

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| historique_pabx_restruc | **W**/L (14 usages) | Historique / journal |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (11 taches)

Traitements internes.

---

#### <a id="t1"></a>125 - Liste cloture service

**Role** : Tache d'orchestration : point d'entree du programme (11 sous-taches). Coordonne l'enchainement des traitements.

<details>
<summary>10 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [125.1](#t2) | qualification du service | Traitement |
| [125.2](#t3) | Lecture des PC v1 | Traitement |
| [125.2.3](#t8) | Lecture des od | Traitement |
| [125.2.4](#t10) | Lecture des od bout | Traitement |
| [125.2.5](#t12) | Lecture des TPE | Traitement |
| [125.3](#t17) | Lecture des PC v1 | Traitement |
| [125.3.3](#t22) | Lecture des od | Traitement |
| [125.3.4](#t24) | Lecture des od bout | Traitement |
| [125.3.5](#t26) | Lecture des TPE | Traitement |
| [125.5](#t32) | impression | Traitement |

</details>
**Variables liees** : B (PI Service), H (V Service Sans TRS), I (V Service Avec TRS), J (V Service Boutique)

---

#### <a id="t2"></a>125.1 - qualification du service

**Role** : Traitement : qualification du service.
**Variables liees** : B (PI Service), H (V Service Sans TRS), I (V Service Avec TRS), J (V Service Boutique)

---

#### <a id="t3"></a>125.2 - Lecture des PC v1

**Role** : Traitement : Lecture des PC v1.

---

#### <a id="t8"></a>125.2.3 - Lecture des od

**Role** : Traitement : Lecture des od.

---

#### <a id="t10"></a>125.2.4 - Lecture des od bout

**Role** : Traitement : Lecture des od bout.
**Variables liees** : J (V Service Boutique), K (V imputation boutique)

---

#### <a id="t12"></a>125.2.5 - Lecture des TPE

**Role** : Traitement : Lecture des TPE.

---

#### <a id="t17"></a>125.3 - Lecture des PC v1

**Role** : Traitement : Lecture des PC v1.

---

#### <a id="t22"></a>125.3.3 - Lecture des od

**Role** : Traitement : Lecture des od.

---

#### <a id="t24"></a>125.3.4 - Lecture des od bout

**Role** : Traitement : Lecture des od bout.
**Variables liees** : J (V Service Boutique), K (V imputation boutique)

---

#### <a id="t26"></a>125.3.5 - Lecture des TPE

**Role** : Traitement : Lecture des TPE.

---

#### <a id="t32"></a>125.5 - impression

**Role** : Generation du document : impression.


### 3.2 Saisie (11 taches)

Ce bloc traite la saisie des donnees de la transaction.

---

#### <a id="t4"></a>125.2.1 - Lecture saisie TPE

**Role** : Saisie des donnees : Lecture saisie TPE.

---

#### <a id="t5"></a>125.2.1.1 - tempo saisie

**Role** : Saisie des donnees : tempo saisie.

---

#### <a id="t6"></a>125.2.2 - Lecture des ventes

**Role** : Saisie des donnees : Lecture des ventes.

---

#### <a id="t13"></a>125.2.5.1 - Lecture saisie TPE

**Role** : Saisie des donnees : Lecture saisie TPE.

---

#### <a id="t14"></a>125.2.5.1.1 - tempo saisie

**Role** : Saisie des donnees : tempo saisie.

---

#### <a id="t18"></a>125.3.1 - Lecture saisie TPE

**Role** : Saisie des donnees : Lecture saisie TPE.

---

#### <a id="t19"></a>125.3.1.1 - tempo saisie

**Role** : Saisie des donnees : tempo saisie.

---

#### <a id="t20"></a>125.3.2 - Lecture des ventes

**Role** : Saisie des donnees : Lecture des ventes.

---

#### <a id="t27"></a>125.3.5.1 - Lecture saisie TPE

**Role** : Saisie des donnees : Lecture saisie TPE.

---

#### <a id="t28"></a>125.3.5.1.1 - tempo saisie

**Role** : Saisie des donnees : tempo saisie.

---

#### <a id="t31"></a>125.4 - Lecture saisie OD

**Role** : Saisie des donnees : Lecture saisie OD.


### 3.3 Calcul (10 taches)

Calculs metier : montants, stocks, compteurs.

---

#### <a id="t7"></a>125.2.2.1 - tempo calcul

**Role** : Calcul : tempo calcul.

---

#### <a id="t9"></a>125.2.3.1 - tempo calcul

**Role** : Calcul : tempo calcul.

---

#### <a id="t11"></a>125.2.4.1 - tempo calcul

**Role** : Calcul : tempo calcul.

---

#### <a id="t15"></a>125.2.6 - Comptes Boutique

**Role** : Traitement : Comptes Boutique.
**Variables liees** : J (V Service Boutique), K (V imputation boutique)

---

#### <a id="t16"></a>125.2.6.1 - tempo calcul

**Role** : Calcul : tempo calcul.

---

#### <a id="t21"></a>125.3.2.1 - tempo calcul

**Role** : Calcul : tempo calcul.

---

#### <a id="t23"></a>125.3.3.1 - tempo calcul

**Role** : Calcul : tempo calcul.

---

#### <a id="t25"></a>125.3.4.1 - tempo calcul

**Role** : Calcul : tempo calcul.

---

#### <a id="t29"></a>125.3.6 - Comptes Boutique

**Role** : Traitement : Comptes Boutique.
**Variables liees** : J (V Service Boutique), K (V imputation boutique)

---

#### <a id="t30"></a>125.3.6.1 - tempo calcul

**Role** : Calcul : tempo calcul.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Fin de journée (IDE 114)](PVE-IDE-114.md), [Fin de journée(Telecollecte) (IDE 404)](PVE-IDE-404.md)
- **Appelle**: 0 programmes | **Tables**: 12 (W:1 R:9 L:4) | **Taches**: 32 | **Expressions**: 3

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (32 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **125.1** | [**Liste cloture service** (125)](#t1) | MDI | - | Traitement |
| 125.1.1 | [qualification du service (125.1)](#t2) | MDI | - | |
| 125.1.2 | [Lecture des PC v1 (125.2)](#t3) | MDI | - | |
| 125.1.3 | [Lecture des od (125.2.3)](#t8) | MDI | - | |
| 125.1.4 | [Lecture des od bout (125.2.4)](#t10) | MDI | - | |
| 125.1.5 | [Lecture des TPE (125.2.5)](#t12) | MDI | - | |
| 125.1.6 | [Lecture des PC v1 (125.3)](#t17) | MDI | - | |
| 125.1.7 | [Lecture des od (125.3.3)](#t22) | MDI | - | |
| 125.1.8 | [Lecture des od bout (125.3.4)](#t24) | MDI | - | |
| 125.1.9 | [Lecture des TPE (125.3.5)](#t26) | MDI | - | |
| 125.1.10 | [impression (125.5)](#t32) | MDI | - | |
| **125.2** | [**Lecture saisie TPE** (125.2.1)](#t4) | MDI | - | Saisie |
| 125.2.1 | [tempo saisie (125.2.1.1)](#t5) | MDI | - | |
| 125.2.2 | [Lecture des ventes (125.2.2)](#t6) | MDI | - | |
| 125.2.3 | [Lecture saisie TPE (125.2.5.1)](#t13) | MDI | - | |
| 125.2.4 | [tempo saisie (125.2.5.1.1)](#t14) | MDI | - | |
| 125.2.5 | [Lecture saisie TPE (125.3.1)](#t18) | MDI | - | |
| 125.2.6 | [tempo saisie (125.3.1.1)](#t19) | MDI | - | |
| 125.2.7 | [Lecture des ventes (125.3.2)](#t20) | MDI | - | |
| 125.2.8 | [Lecture saisie TPE (125.3.5.1)](#t27) | MDI | - | |
| 125.2.9 | [tempo saisie (125.3.5.1.1)](#t28) | MDI | - | |
| 125.2.10 | [Lecture saisie OD (125.4)](#t31) | MDI | - | |
| **125.3** | [**tempo calcul** (125.2.2.1)](#t7) | MDI | - | Calcul |
| 125.3.1 | [tempo calcul (125.2.3.1)](#t9) | MDI | - | |
| 125.3.2 | [tempo calcul (125.2.4.1)](#t11) | MDI | - | |
| 125.3.3 | [Comptes Boutique (125.2.6)](#t15) | MDI | - | |
| 125.3.4 | [tempo calcul (125.2.6.1)](#t16) | MDI | - | |
| 125.3.5 | [tempo calcul (125.3.2.1)](#t21) | MDI | - | |
| 125.3.6 | [tempo calcul (125.3.3.1)](#t23) | MDI | - | |
| 125.3.7 | [tempo calcul (125.3.4.1)](#t25) | MDI | - | |
| 125.3.8 | [Comptes Boutique (125.3.6)](#t29) | MDI | - | |
| 125.3.9 | [tempo calcul (125.3.6.1)](#t30) | MDI | - | |

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

### Tables utilisees (12)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 40 | comptable________cte |  | DB | R |   |   | 4 |
| 89 | moyen_paiement___mop |  | DB | R |   | L | 6 |
| 240 | saisie_pdc_boutique |  | DB | R |   |   | 2 |
| 245 | saisie_od_par_service | Services / filieres | DB | R |   |   | 1 |
| 256 | terminaux_boutique |  | DB |   |   | L | 1 |
| 259 | tpe_par_service | Services / filieres | DB | R |   |   | 2 |
| 260 | tickets_tpe |  | DB | R |   |   | 4 |
| 263 | vente | Donnees de ventes | DB |   |   | L | 2 |
| 550 | historique_pabx_restruc | Historique / journal | TMP |   | **W** | L | 14 |
| 697 | droits_applications | Droits operateur | DB | R |   |   | 1 |
| 734 | arc_pv_cust_packages |  | DB | R |   |   | 1 |
| 1464 | Table_1464 |  | MEM | R |   |   | 1 |

### Colonnes par table (8 / 10 tables avec colonnes identifiees)

<details>
<summary>Table 40 - comptable________cte (R) - 4 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| C | PI data comptable | R | Date |

</details>

<details>
<summary>Table 89 - moyen_paiement___mop (R/L) - 6 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 240 - saisie_pdc_boutique (R) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| B | total saisie | R | Numeric |
| C | v service Boutique | R | Logical |
| J | V Service Boutique | R | Logical |
| K | V imputation boutique | R | Numeric |

</details>

<details>
<summary>Table 245 - saisie_od_par_service (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | v service sans TRS_IMS | R | Logical |
| B | PI Service | R | Alpha |
| C | v service Boutique | R | Logical |
| H | V Service Sans TRS | R | Logical |
| I | V Service Avec TRS | R | Logical |
| J | V Service Boutique | R | Logical |

</details>

<details>
<summary>Table 259 - tpe_par_service (R) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | v service sans TRS_IMS | R | Logical |
| B | PI Service | R | Alpha |
| C | v service Boutique | R | Logical |
| H | V Service Sans TRS | R | Logical |
| I | V Service Avec TRS | R | Logical |
| J | V Service Boutique | R | Logical |

</details>

<details>
<summary>Table 260 - tickets_tpe (R) - 4 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 550 - historique_pabx_restruc (**W**/L) - 14 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | total calcul | W | Numeric |
| B | total saisie | W | Numeric |

</details>

<details>
<summary>Table 697 - droits_applications (R) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 734 - arc_pv_cust_packages (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | v service sans TRS_IMS | R | Logical |
| B | v service avec TRS_IMS | R | Logical |
| C | v service Boutique | R | Logical |
| D | v cumul bout comptes | R | Numeric |
| E | v cumul bout telecollecte | R | Numeric |

</details>

<details>
<summary>Table 1464 - Table_1464 (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | v service sans TRS_IMS | R | Logical |
| B | v service avec TRS_IMS | R | Logical |
| C | v service Boutique | R | Logical |
| D | v cumul bout comptes | R | Numeric |
| E | v cumul bout telecollecte | R | Numeric |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (5)

Variables recues du programme appelant ([Fin de journée (IDE 114)](PVE-IDE-114.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | PI societe | Alpha | - |
| B | PI Service | Alpha | - |
| C | PI data comptable | Date | - |
| D | PI nomvillage | Alpha | - |
| E | PI masque | Alpha | - |

### 11.2 Variables de session (6)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| F | V Class OD | Alpha | - |
| G | V Mop OD | Alpha | - |
| H | V Service Sans TRS | Logical | - |
| I | V Service Avec TRS | Logical | - |
| J | V Service Boutique | Logical | - |
| K | V imputation boutique | Numeric | - |

## 12. EXPRESSIONS

**3 / 3 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| OTHER | 1 | 0 |
| NEGATION | 1 | 0 |
| REFERENCE_VG | 1 | 0 |

### 12.2 Expressions cles par type

#### OTHER (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 1 | `DbDel ('{550,3}'DSOURCE,'')` | - |

#### NEGATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| NEGATION | 2 | `NOT VG104` | - |

#### REFERENCE_VG (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 3 | `VG104` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Fin de journée (IDE 114)](PVE-IDE-114.md) -> **Liste cloture service (IDE 125)**

Main -> ... -> [Fin de journée(Telecollecte) (IDE 404)](PVE-IDE-404.md) -> **Liste cloture service (IDE 125)**

```mermaid
graph LR
    T125[125 Liste cloture service]
    style T125 fill:#58a6ff
    CC143[143 START]
    style CC143 fill:#8b5cf6
    CC353[353 Menu==V4]
    style CC353 fill:#f59e0b
    CC185[185 Menu]
    style CC185 fill:#f59e0b
    CC439[439 Menu]
    style CC439 fill:#f59e0b
    CC420[420 Menu==V4___]
    style CC420 fill:#f59e0b
    CC180[180 Menu Cloture du se...]
    style CC180 fill:#f59e0b
    CC397[397 Menu Service clotu...]
    style CC397 fill:#f59e0b
    CC402[402 Menu Service cloture]
    style CC402 fill:#f59e0b
    CC114[114 Fin de journée]
    style CC114 fill:#3fb950
    CC404[404 Fin de journéeTele...]
    style CC404 fill:#3fb950
    CC180 --> CC114
    CC397 --> CC114
    CC402 --> CC114
    CC180 --> CC404
    CC397 --> CC404
    CC402 --> CC404
    CC185 --> CC180
    CC353 --> CC180
    CC420 --> CC180
    CC439 --> CC180
    CC185 --> CC397
    CC353 --> CC397
    CC420 --> CC397
    CC439 --> CC397
    CC185 --> CC402
    CC353 --> CC402
    CC420 --> CC402
    CC439 --> CC402
    CC143 --> CC185
    CC143 --> CC353
    CC143 --> CC420
    CC143 --> CC439
    CC114 --> T125
    CC404 --> T125
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [114](PVE-IDE-114.md) | Fin de journée | 1 |
| [404](PVE-IDE-404.md) | Fin de journée(Telecollecte) | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T125[125 Liste cloture service]
    style T125 fill:#58a6ff
    NONE[Aucun callee]
    T125 -.-> NONE
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
| Lignes de logique | 441 | Taille moyenne |
| Expressions | 3 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 441) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (11 taches: 0 ecran, 11 traitements)

- **Strategie** : 11 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

#### Saisie (11 taches: 0 ecran, 11 traitements)

- **Strategie** : Formulaire React/Blazor avec validation Zod/FluentValidation.
- Validation temps reel cote client + serveur

#### Calcul (10 taches: 0 ecran, 10 traitements)

- **Strategie** : Services de calcul purs (Domain Services).
- Migrer la logique de calcul (stock, compteurs, montants)

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| historique_pabx_restruc | Table WRITE (Temp) | 13x | Schema + repository |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 09:34*
