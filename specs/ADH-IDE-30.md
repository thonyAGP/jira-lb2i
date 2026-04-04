# ADH IDE 30 - Read histo Fus_Sep_Det

> **Analyse**: Phases 1-4 2026-02-07 03:41 -> 01:24 (21h42min) | Assemblage 01:24
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | ADH |
| IDE Position | 30 |
| Nom Programme | Read histo Fus_Sep_Det |
| Fichier source | `Prg_30.xml` |
| Dossier IDE | General |
| Taches | 11 (0 ecrans visibles) |
| Tables modifiees | 2 |
| Programmes appeles | 0 |
| Complexite | **BASSE** (score 14/100) |

## 2. DESCRIPTION FONCTIONNELLE

**ADH IDE 30 - Read histo Fus_Sep_Det** est un programme de **revalidation et déblocage post-opération de fusion/séparation de comptes**. Appelé directement par les programmes Séparation (IDE 27) et Fusion (IDE 28), il relit l'historique détaillé écrit précédemment pour valider la cohérence des données et effectuer le déverrouillage des comptes référence. Le programme supporte différentes phases de reprise (position `1F` et `3E`) avec des tâches conditionnées (10, 20, 30, 50, 60), ce qui permet d'adapter le traitement au contexte opérationnel.

La logique métier repose sur **11 tâches organisées en deux blocs**: un bloc de traitement qui route les opérations selon la position et le numéro de tâche, et un bloc de calcul dédié au déblocage des comptes. Le programme lit les données depuis `histo_fusionseparation_detail` (9 colonnes identifiées: type F/E, société, chrono reprise, position reprise, taskNumber, compte référence, toDo, état réseau, existence) et effectue des modifications dans deux tables cibles—`compte_gm` pour le déblocage et `histo_fusionseparation_saisie` pour la journalisation.

Code **sain et sans régression** (0% désactivé, complexité basse), ce programme joue un rôle critique dans l'intégrité post-fusion en assurant que les comptes sont correctement déverrouillés et que l'historique est nettoyé selon les états de réseau et les conditions de toDo. Aucun programme externe n'est appelé directement, ce qui en fait un **maillon autonome mais dépendant** du flux Séparation/Fusion pour son activation.

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (9 taches)

Traitements internes.

---

#### <a id="t1"></a>30 - (sans nom)

**Role** : Tache d'orchestration : point d'entree du programme (9 sous-taches). Coordonne l'enchainement des traitements.

<details>
<summary>8 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [30.1](#t2) | 1F/10 v1 | Traitement |
| [30.2](#t3) | 1F/10 v1 | Traitement |
| [30.3](#t4) | 1F/20 | Traitement |
| [30.4](#t6) | 1F/30 | Traitement |
| [30.4.2](#t8) | suppression histo | Traitement |
| [30.5](#t9) | 3E/50 | Traitement |
| [30.6](#t10) | 3E/60 v1 | Traitement |
| [30.7](#t11) | 3E/60 v1 | Traitement |

</details>

---

#### <a id="t2"></a>30.1 - 1F/10 v1

**Role** : Traitement : 1F/10 v1.

---

#### <a id="t3"></a>30.2 - 1F/10 v1

**Role** : Traitement : 1F/10 v1.

---

#### <a id="t4"></a>30.3 - 1F/20

**Role** : Traitement : 1F/20.

---

#### <a id="t6"></a>30.4 - 1F/30

**Role** : Traitement : 1F/30.

---

#### <a id="t8"></a>30.4.2 - suppression histo

**Role** : Traitement : suppression histo.

---

#### <a id="t9"></a>30.5 - 3E/50

**Role** : Traitement : 3E/50.

---

#### <a id="t10"></a>30.6 - 3E/60 v1

**Role** : Traitement : 3E/60 v1.

---

#### <a id="t11"></a>30.7 - 3E/60 v1

**Role** : Traitement : 3E/60 v1.


### 3.2 Calcul (2 taches)

Calculs metier : montants, stocks, compteurs.

---

#### <a id="t5"></a>30.3.1 - deblocage compte

**Role** : Traitement : deblocage compte.
**Variables liees** : ES (i compte reference)

---

#### <a id="t7"></a>30.4.1 - deblocage comptes

**Role** : Traitement : deblocage comptes.


## 5. REGLES METIER

6 regles identifiees:

### Autres (6 regles)

#### <a id="rm-RM-001"></a>[RM-001] Condition: i position reprise [D]='1F' AND i taskNumber [E] egale 10

| Element | Detail |
|---------|--------|
| **Condition** | `i position reprise [D]='1F' AND i taskNumber [E]=10` |
| **Si vrai** | Action si vrai |
| **Variables** | EQ (i position reprise), ER (i taskNumber) |
| **Expression source** | Expression 8 : `i position reprise [D]='1F' AND i taskNumber [E]=10` |
| **Exemple** | Si i position reprise [D]='1F' AND i taskNumber [E]=10 â†’ Action si vrai |

#### <a id="rm-RM-002"></a>[RM-002] Condition: i position reprise [D]='1F' AND i taskNumber [E] egale 20

| Element | Detail |
|---------|--------|
| **Condition** | `i position reprise [D]='1F' AND i taskNumber [E]=20` |
| **Si vrai** | Action si vrai |
| **Variables** | EQ (i position reprise), ER (i taskNumber) |
| **Expression source** | Expression 9 : `i position reprise [D]='1F' AND i taskNumber [E]=20` |
| **Exemple** | Si i position reprise [D]='1F' AND i taskNumber [E]=20 â†’ Action si vrai |

#### <a id="rm-RM-003"></a>[RM-003] Condition: i position reprise [D]='1F' AND i taskNumber [E] egale 30

| Element | Detail |
|---------|--------|
| **Condition** | `i position reprise [D]='1F' AND i taskNumber [E]=30` |
| **Si vrai** | Action si vrai |
| **Variables** | EQ (i position reprise), ER (i taskNumber) |
| **Expression source** | Expression 10 : `i position reprise [D]='1F' AND i taskNumber [E]=30` |
| **Exemple** | Si i position reprise [D]='1F' AND i taskNumber [E]=30 â†’ Action si vrai |

#### <a id="rm-RM-004"></a>[RM-004] Condition: i position reprise [D]='3E' AND i taskNumber [E] egale 50

| Element | Detail |
|---------|--------|
| **Condition** | `i position reprise [D]='3E' AND i taskNumber [E]=50` |
| **Si vrai** | Action si vrai |
| **Variables** | EQ (i position reprise), ER (i taskNumber) |
| **Expression source** | Expression 11 : `i position reprise [D]='3E' AND i taskNumber [E]=50` |
| **Exemple** | Si i position reprise [D]='3E' AND i taskNumber [E]=50 â†’ Action si vrai |

#### <a id="rm-RM-005"></a>[RM-005] Condition: i position reprise [D]='3E' AND i taskNumber [E] egale 60

| Element | Detail |
|---------|--------|
| **Condition** | `i position reprise [D]='3E' AND i taskNumber [E]=60` |
| **Si vrai** | Action si vrai |
| **Variables** | EQ (i position reprise), ER (i taskNumber) |
| **Expression source** | Expression 12 : `i position reprise [D]='3E' AND i taskNumber [E]=60` |
| **Exemple** | Si i position reprise [D]='3E' AND i taskNumber [E]=60 â†’ Action si vrai |

#### <a id="rm-RM-006"></a>[RM-006] Negation de VG78 (condition inversee)

| Element | Detail |
|---------|--------|
| **Condition** | `NOT VG78` |
| **Si vrai** | Action si vrai |
| **Expression source** | Expression 13 : `NOT VG78` |
| **Exemple** | Si NOT VG78 â†’ Action si vrai |

## 6. CONTEXTE

- **Appele par**: [Separation (IDE 27)](ADH-IDE-27.md), [Fusion (IDE 28)](ADH-IDE-28.md)
- **Appelle**: 0 programmes | **Tables**: 5 (W:2 R:3 L:1) | **Taches**: 11 | **Expressions**: 14

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (11 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **30.1** | [**(sans nom)** (30)](#t1) | MDI | - | Traitement |
| 30.1.1 | [1F/10 v1 (30.1)](#t2) | MDI | - | |
| 30.1.2 | [1F/10 v1 (30.2)](#t3) | MDI | - | |
| 30.1.3 | [1F/20 (30.3)](#t4) | MDI | - | |
| 30.1.4 | [1F/30 (30.4)](#t6) | MDI | - | |
| 30.1.5 | [suppression histo (30.4.2)](#t8) | MDI | - | |
| 30.1.6 | [3E/50 (30.5)](#t9) | MDI | - | |
| 30.1.7 | [3E/60 v1 (30.6)](#t10) | MDI | - | |
| 30.1.8 | [3E/60 v1 (30.7)](#t11) | MDI | - | |
| **30.2** | [**deblocage compte** (30.3.1)](#t5) | MDI | - | Calcul |
| 30.2.1 | [deblocage comptes (30.4.1)](#t7) | MDI | - | |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Traitement principal]
    DECISION{i position reprise}
    PROCESS[Traitement]
    UPDATE[MAJ 2 tables]
    ENDOK([END OK])
    ENDKO([END KO])

    START --> INIT --> SAISIE --> DECISION
    DECISION -->|OUI| PROCESS
    DECISION -->|NON| ENDKO
    PROCESS --> UPDATE --> ENDOK

    style START fill:#3fb950,color:#000
    style ENDOK fill:#3fb950,color:#000
    style ENDKO fill:#f85149,color:#fff
    style DECISION fill:#58a6ff,color:#000
```

> **Legende**: Vert = START/END OK | Rouge = END KO | Bleu = Decisions
> *Algorigramme auto-genere. Utiliser `/algorigramme` pour une synthese metier detaillee.*

<!-- TAB:Donnees -->

## 10. TABLES

### Tables utilisees (5)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 343 | histo_fusionseparation_saisie | Historique / journal | DB |   | **W** | L | 2 |
| 47 | compte_gm________cgm | Comptes GM (generaux) | DB |   | **W** |   | 2 |
| 23 | reseau_cloture___rec | Donnees reseau/cloture | DB | R |   |   | 4 |
| 341 | histo_fusionseparation_detail | Historique / journal | DB | R |   |   | 1 |
| 340 | histo_fusionseparation | Historique / journal | DB | R |   |   | 1 |

### Colonnes par table (3 / 5 tables avec colonnes identifiees)

<details>
<summary>Table 343 - histo_fusionseparation_saisie (**W**/L) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 47 - compte_gm________cgm (**W**) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| ES | i compte reference | W | Numeric |

</details>

<details>
<summary>Table 23 - reseau_cloture___rec (R) - 4 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| EN | v.Existe cloture ? | R | Logical |
| EU | o etat reseau | R | Alpha |

</details>

<details>
<summary>Table 341 - histo_fusionseparation_detail (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | i type F/E | R | Alpha |
| B | i societe | R | Alpha |
| C | i chrono reprise | R | Numeric |
| D | i position reprise | R | Alpha |
| E | i taskNumber | R | Numeric |
| F | i compte reference | R | Numeric |
| G | o toDo | R | Logical |
| H | o etat reseau | R | Alpha |
| I | exist | R | Logical |

</details>

<details>
<summary>Table 340 - histo_fusionseparation (R) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Autres (9)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| EN | i type F/E | Alpha | - |
| EO | i societe | Alpha | - |
| EP | i chrono reprise | Numeric | 1x refs |
| EQ | i position reprise | Alpha | 6x refs |
| ER | i taskNumber | Numeric | 6x refs |
| ES | i compte reference | Numeric | - |
| ET | o toDo | Logical | 1x refs |
| EU | o etat reseau | Alpha | - |
| EV | exist | Logical | 1x refs |

## 12. EXPRESSIONS

**14 / 14 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONDITION | 5 | 5 |
| NEGATION | 1 | 5 |
| CAST_LOGIQUE | 2 | 0 |
| OTHER | 5 | 0 |
| REFERENCE_VG | 1 | 0 |

### 12.2 Expressions cles par type

#### CONDITION (5 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 11 | `i position reprise [D]='3E' AND i taskNumber [E]=50` | [RM-004](#rm-RM-004) |
| CONDITION | 12 | `i position reprise [D]='3E' AND i taskNumber [E]=60` | [RM-005](#rm-RM-005) |
| CONDITION | 10 | `i position reprise [D]='1F' AND i taskNumber [E]=30` | [RM-003](#rm-RM-003) |
| CONDITION | 8 | `i position reprise [D]='1F' AND i taskNumber [E]=10` | [RM-001](#rm-RM-001) |
| CONDITION | 9 | `i position reprise [D]='1F' AND i taskNumber [E]=20` | [RM-002](#rm-RM-002) |

#### NEGATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| NEGATION | 13 | `NOT VG78` | [RM-006](#rm-RM-006) |

#### CAST_LOGIQUE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 5 | `'FALSE'LOG` | - |
| CAST_LOGIQUE | 1 | `'TRUE'LOG` | - |

#### OTHER (5 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 6 | `exist [I]` | - |
| OTHER | 7 | `o toDo [G]` | - |
| OTHER | 4 | `i taskNumber [E]` | - |
| OTHER | 2 | `i chrono reprise [C]` | - |
| OTHER | 3 | `i position reprise [D]` | - |

#### REFERENCE_VG (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 14 | `VG78` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Separation (IDE 27)](ADH-IDE-27.md) -> **Read histo Fus_Sep_Det (IDE 30)**

Main -> ... -> [Fusion (IDE 28)](ADH-IDE-28.md) -> **Read histo Fus_Sep_Det (IDE 30)**

```mermaid
graph LR
    T30[30 Read histo Fus_Sep_Det]
    style T30 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC163[163 Menu caisse GM - s...]
    style CC163 fill:#f59e0b
    CC37[37 Menu changement compte]
    style CC37 fill:#f59e0b
    CC27[27 Separation]
    style CC27 fill:#3fb950
    CC28[28 Fusion]
    style CC28 fill:#3fb950
    CC37 --> CC27
    CC37 --> CC28
    CC163 --> CC37
    CC1 --> CC163
    CC27 --> T30
    CC28 --> T30
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [27](ADH-IDE-27.md) | Separation | 11 |
| [28](ADH-IDE-28.md) | Fusion | 10 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T30[30 Read histo Fus_Sep_Det]
    style T30 fill:#58a6ff
    NONE[Aucun callee]
    T30 -.-> NONE
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
| Lignes de logique | 116 | Programme compact |
| Expressions | 14 | Peu de logique |
| Tables WRITE | 2 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 116) | Code sain |
| Regles metier | 6 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (9 taches: 0 ecran, 9 traitements)

- **Strategie** : 9 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

#### Calcul (2 taches: 0 ecran, 2 traitements)

- **Strategie** : Services de calcul purs (Domain Services).
- Migrer la logique de calcul (stock, compteurs, montants)

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| compte_gm________cgm | Table WRITE (Database) | 2x | Schema + repository |
| histo_fusionseparation_saisie | Table WRITE (Database) | 1x | Schema + repository |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-08 01:26*
