# REF IDE 879 - Calcul effectif quotidien(SVG)

> **Analyse**: Phases 1-4 2026-02-03 14:53 -> 14:53 (15s) | Assemblage 14:53
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | REF |
| IDE Position | 879 |
| Nom Programme | Calcul effectif quotidien(SVG) |
| Fichier source | `Prg_879.xml` |
| Dossier IDE | General |
| Taches | 24 (0 ecrans visibles) |
| Tables modifiees | 3 |
| Programmes appeles | 1 |
| :warning: Statut | **ORPHELIN_POTENTIEL** |

## 2. DESCRIPTION FONCTIONNELLE

**Calcul effectif quotidien(SVG)** assure la gestion complete de ce processus.

Le flux de traitement s'organise en **3 blocs fonctionnels** :

- **Traitement** (20 taches) : traitements metier divers
- **Calcul** (2 taches) : calculs de montants, stocks ou compteurs
- **Initialisation** (2 taches) : reinitialisation d'etats et de variables de travail

**Donnees modifiees** : 3 tables en ecriture (societe__________soc, absences_personnel, vrl_hp).

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Calcul (2 taches)

- **879** - Calcul effectif quotidien(SVG) **[[ECRAN]](#ecran-t1)**
- **879.2.2.3** - Calcul JH absence

Delegue a : [recalcul JH vente (IDE 625)](REF-IDE-625.md)

#### Phase 2 : Initialisation (2 taches)

- **879.1** - Initialisation lieu sejour
- **879.3** - Initialisation heures

#### Phase 3 : Traitement (20 taches)

- **879.1.1** - Mise à jour effectif quotidien
- **879.1.2** - Mise à jour effectif quotidien
- **879.1.3** - Mise à jour effectif quotidien
- **879.2** - Parcours qualité **[[ECRAN]](#ecran-t6)**
- **879.2.1** - Vrl
- **879.2.2** - Traitement deval val diff
- **879.2.2.1** - Del effectif personnes inexist
- **879.2.2.2** - Maj personnes
- **879.2.3** - Vrl
- **879.2.4** - Vrl
- **879.2.5** - Vrl
- **879.2.6** - Vrl
- **879.2.7** - Realise
- **879.2.7.1** - Maj personnes
- **879.2.7.2** - Del effectif personnes inexist
- **879.2.7.2.1** - Maj personnes
- **879.2.8** - Previsionnel
- **879.2.9** - Vrl
- **879.2.10** - Correctif repas hors village
- **879.2.11** - delete eff quotidien SQL

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| vrl_hp | R/**W**/L (5 usages) |  |
| absences_personnel | **W**/L (3 usages) |  |
| societe__________soc | R/**W** (3 usages) |  |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Calcul (2 taches)

Calculs metier : montants, stocks, compteurs.

---

#### <a id="t1"></a>879 - Calcul effectif quotidien(SVG) [[ECRAN]](#ecran-t1)

**Role** : Calcul : Calcul effectif quotidien(SVG).
**Ecran** : 310 x 145 DLU | [Voir mockup](#ecran-t1)

---

#### <a id="t11"></a>879.2.2.3 - Calcul JH absence

**Role** : Calcul : Calcul JH absence.
**Delegue a** : [recalcul JH vente (IDE 625)](REF-IDE-625.md)


### 3.2 Initialisation (2 taches)

Reinitialisation d'etats et variables de travail.

---

#### <a id="t2"></a>879.1 - Initialisation lieu sejour

**Role** : Reinitialisation : Initialisation lieu sejour.
**Variables liees** : C (P.Nb Lieu sejour)

---

#### <a id="t24"></a>879.3 - Initialisation heures

**Role** : Reinitialisation : Initialisation heures.


### 3.3 Traitement (20 taches)

Traitements internes.

---

#### <a id="t3"></a>879.1.1 - Mise à jour effectif quotidien

**Role** : Traitement : Mise à jour effectif quotidien.
**Variables liees** : C (P.Nb Lieu sejour)

---

#### <a id="t4"></a>879.1.2 - Mise à jour effectif quotidien

**Role** : Traitement : Mise à jour effectif quotidien.
**Variables liees** : C (P.Nb Lieu sejour)

---

#### <a id="t5"></a>879.1.3 - Mise à jour effectif quotidien

**Role** : Traitement : Mise à jour effectif quotidien.
**Variables liees** : C (P.Nb Lieu sejour)

---

#### <a id="t6"></a>879.2 - Parcours qualité [[ECRAN]](#ecran-t6)

**Role** : Traitement : Parcours qualité.
**Ecran** : 667 x 153 DLU (MDI) | [Voir mockup](#ecran-t6)

---

#### <a id="t7"></a>879.2.1 - Vrl

**Role** : Traitement interne.

---

#### <a id="t8"></a>879.2.2 - Traitement deval val diff

**Role** : Traitement : Traitement deval val diff.

---

#### <a id="t9"></a>879.2.2.1 - Del effectif personnes inexist

**Role** : Traitement : Del effectif personnes inexist.

---

#### <a id="t10"></a>879.2.2.2 - Maj personnes

**Role** : Traitement : Maj personnes.

---

#### <a id="t12"></a>879.2.3 - Vrl

**Role** : Traitement interne.

---

#### <a id="t13"></a>879.2.4 - Vrl

**Role** : Traitement interne.

---

#### <a id="t14"></a>879.2.5 - Vrl

**Role** : Traitement interne.

---

#### <a id="t15"></a>879.2.6 - Vrl

**Role** : Traitement interne.

---

#### <a id="t16"></a>879.2.7 - Realise

**Role** : Traitement : Realise.

---

#### <a id="t17"></a>879.2.7.1 - Maj personnes

**Role** : Traitement : Maj personnes.

---

#### <a id="t18"></a>879.2.7.2 - Del effectif personnes inexist

**Role** : Traitement : Del effectif personnes inexist.

---

#### <a id="t19"></a>879.2.7.2.1 - Maj personnes

**Role** : Traitement : Maj personnes.

---

#### <a id="t20"></a>879.2.8 - Previsionnel

**Role** : Traitement : Previsionnel.

---

#### <a id="t21"></a>879.2.9 - Vrl

**Role** : Traitement interne.

---

#### <a id="t22"></a>879.2.10 - Correctif repas hors village

**Role** : Traitement : Correctif repas hors village.

---

#### <a id="t23"></a>879.2.11 - delete eff quotidien SQL

**Role** : Traitement : delete eff quotidien SQL.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: (aucun)
- **Appelle**: 1 programmes | **Tables**: 14 (W:3 R:5 L:12) | **Taches**: 24 | **Expressions**: 6

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (24 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **879.1** | [**Calcul effectif quotidien(SVG)** (879)](#t1) [mockup](#ecran-t1) | - | 310x145 | Calcul |
| 879.1.1 | [Calcul JH absence (879.2.2.3)](#t11) | - | - | |
| **879.2** | [**Initialisation lieu sejour** (879.1)](#t2) | - | - | Initialisation |
| 879.2.1 | [Initialisation heures (879.3)](#t24) | - | - | |
| **879.3** | [**Mise à jour effectif quotidien** (879.1.1)](#t3) | - | - | Traitement |
| 879.3.1 | [Mise à jour effectif quotidien (879.1.2)](#t4) | - | - | |
| 879.3.2 | [Mise à jour effectif quotidien (879.1.3)](#t5) | - | - | |
| 879.3.3 | [Parcours qualité (879.2)](#t6) [mockup](#ecran-t6) | MDI | 667x153 | |
| 879.3.4 | [Vrl (879.2.1)](#t7) | - | - | |
| 879.3.5 | [Traitement deval val diff (879.2.2)](#t8) | - | - | |
| 879.3.6 | [Del effectif personnes inexist (879.2.2.1)](#t9) | - | - | |
| 879.3.7 | [Maj personnes (879.2.2.2)](#t10) | - | - | |
| 879.3.8 | [Vrl (879.2.3)](#t12) | - | - | |
| 879.3.9 | [Vrl (879.2.4)](#t13) | - | - | |
| 879.3.10 | [Vrl (879.2.5)](#t14) | - | - | |
| 879.3.11 | [Vrl (879.2.6)](#t15) | - | - | |
| 879.3.12 | [Realise (879.2.7)](#t16) | MDI | - | |
| 879.3.13 | [Maj personnes (879.2.7.1)](#t17) | - | - | |
| 879.3.14 | [Del effectif personnes inexist (879.2.7.2)](#t18) | - | - | |
| 879.3.15 | [Maj personnes (879.2.7.2.1)](#t19) | - | - | |
| 879.3.16 | [Previsionnel (879.2.8)](#t20) | MDI | - | |
| 879.3.17 | [Vrl (879.2.9)](#t21) | - | - | |
| 879.3.18 | [Correctif repas hors village (879.2.10)](#t22) | - | - | |
| 879.3.19 | [delete eff quotidien SQL (879.2.11)](#t23) | - | - | |

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

### Tables utilisees (14)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 30 | gm-recherche_____gmr | Index de recherche | DB | R |   |   | 5 |
| 31 | gm-complet_______gmc |  | DB |   |   | L | 2 |
| 34 | hebergement______heb | Hebergement (chambres) | DB | R |   | L | 12 |
| 35 | personnel_go______go |  | DB |   |   | L | 2 |
| 81 | societe__________soc |  | DB | R | **W** |   | 3 |
| 118 | tables_imports |  | DB |   |   | L | 1 |
| 120 | tables_qualites__qua |  | DB |   |   | L | 1 |
| 362 | absences_personnel |  | DB |   | **W** | L | 3 |
| 770 | vente_vrl_vsl | Donnees de ventes | DB |   |   | L | 2 |
| 783 | vrl_hp |  | DB | R | **W** | L | 5 |
| 784 | type_repas_nenc_vill |  | DB | R |   | L | 5 |
| 785 | effectif_quotidien |  | DB |   |   | L | 10 |
| 790 | log_valid_devalid |  | DB |   |   | L | 1 |
| 793 | effectif_personnes |  | DB |   |   | L | 7 |

### Colonnes par table (5 / 6 tables avec colonnes identifiees)

<details>
<summary>Table 30 - gm-recherche_____gmr (R) - 5 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | V.Nb real correction | R | Numeric |
| B | V.Date operation | R | Date |
| C | V.Nb absence | R | Numeric |
| D | V.heure fin sejour | R | Alpha |
| E | V.Heure fin periode prec midi | R | Alpha |
| F | V.Heure fin periode prec soir | R | Alpha |

</details>

<details>
<summary>Table 34 - hebergement______heb (R/L) - 12 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | V.Existe hebergement ? | R | Logical |

</details>

<details>
<summary>Table 81 - societe__________soc (R/**W**) - 3 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P.Date | W | Date |
| B | P.From PBP | W | Logical |
| C | P.Nb Lieu sejour | W | Numeric |
| D | P.From gestion crise | W | Logical |
| E | V.Date | W | Alpha |
| F | V.Where clause | W | Alpha |

</details>

<details>
<summary>Table 362 - absences_personnel (**W**/L) - 3 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | V.Date debut absence | W | Date |
| B | V.Date fin absence | W | Date |
| C | V.J absence | W | Numeric |

</details>

<details>
<summary>Table 783 - vrl_hp (R/**W**/L) - 5 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | V.qualite | W | Alpha |
| B | V.qualite_compl IGR | W | Alpha |
| C | V.Qualite compl GO | W | Alpha |
| D | V.Ancienne regul midi | W | Numeric |
| E | V.Ancienne regul soir | W | Numeric |

</details>

<details>
<summary>Table 784 - type_repas_nenc_vill (R/L) - 5 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (4)

Variables recues en parametre.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P.Date | Date | 2x parametre entrant |
| B | P.From PBP | Logical | 1x parametre entrant |
| C | P.Nb Lieu sejour | Numeric | [879.1](#t2) |
| D | P.From gestion crise | Logical | - |

### 11.2 Variables de session (2)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| E | V.Date | Alpha | - |
| F | V.Where clause | Alpha | - |

## 12. EXPRESSIONS

**6 / 6 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCULATION | 2 | 0 |
| CONSTANTE | 1 | 0 |
| CONDITION | 1 | 0 |
| OTHER | 1 | 0 |
| CAST_LOGIQUE | 1 | 0 |

### 12.2 Expressions cles par type

#### CALCULATION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 4 | `P.Date [A]-1` | - |
| CALCULATION | 3 | `BOM(P.Date [A]-1)` | - |

#### CONSTANTE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 2 | `'C'` | - |

#### CONDITION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 1 | `VG8 AND P.Nb Lieu sejour [C]>1` | - |

#### OTHER (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 5 | `P.From PBP [B]` | - |

#### CAST_LOGIQUE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 6 | `'FALSE'LOG` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

**Chemin**: (pas de callers directs)

```mermaid
graph LR
    T879[879 Calcul effectif qu...]
    style T879 fill:#58a6ff
    NONE[Aucun caller]
    NONE -.-> T879
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| - | (aucun) | - |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T879[879 Calcul effectif qu...]
    style T879 fill:#58a6ff
    C625[625 recalcul JH vente]
    T879 --> C625
    style C625 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [625](REF-IDE-625.md) | recalcul JH vente | 1 | Calcul de donnees |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 1235 | Programme volumineux |
| Expressions | 6 | Peu de logique |
| Tables WRITE | 3 | Impact modere |
| Sous-programmes | 1 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 1235) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Calcul (2 taches: 1 ecran, 1 traitement)

- **Strategie** : Services de calcul purs (Domain Services).
- Migrer la logique de calcul (stock, compteurs, montants)

#### Initialisation (2 taches: 0 ecran, 2 traitements)

- **Strategie** : Constructeur/methode `InitAsync()` dans l'orchestrateur.

#### Traitement (20 taches: 1 ecran, 19 traitements)

- **Strategie** : Orchestrateur avec 1 ecrans (Razor/React) et 19 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 1 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| societe__________soc | Table WRITE (Database) | 2x | Schema + repository |
| absences_personnel | Table WRITE (Database) | 1x | Schema + repository |
| vrl_hp | Table WRITE (Database) | 3x | Schema + repository |
| [recalcul JH vente (IDE 625)](REF-IDE-625.md) | Sous-programme | 1x | Normale - Calcul de donnees |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 14:53*
