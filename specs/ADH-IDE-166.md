# ADH IDE 166 - Start

> **Analyse**: Phases 1-4 2026-02-07 03:52 -> 03:48 (23h56min) | Assemblage 03:48
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | ADH |
| IDE Position | 166 |
| Nom Programme | Start |
| Fichier source | `Prg_166.xml` |
| Dossier IDE | General |
| Taches | 7 (0 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 6 |
| Complexite | **BASSE** (score 24/100) |

## 2. DESCRIPTION FONCTIONNELLE

**ADH IDE 166 - Start** est un programme d'**initialisation et de préparation d'environnement** appelé depuis 11 points d'entrée distincts (transactions de ventes, historiques, validations VAD, Main Program). Il orchestrate 4 tâches critiques : récupération des données de langue depuis IDE 45, initialisation du processus Easy Arrival (IDE 50), création des structures adresse via IDE 52, et vérification de la connectivité client/serveur (IDE 200). Ce programme établit le contexte système complet avant chaque opération métier majeure.

Le flux de données pivote autour de la variable **FROM_IMS** (stockée en variable B) que le programme lit 3 fois en parallèle pour peupler les différentes tables de référence. Il enrichit également les données avec des opérations de comptage sur les lieux de séjour (tâche 3) et une récupération des logins matriculés (tâche 4), essentielles pour configurer les combos d'interface (alimentation effectuée via IDE 224). Le programme écrit les modifications dans la table **categorie_operation_mw** (table n°878) et réinitialise systématiquement le log d'initialisation TPE pour chaque session.

Optimisé pour la performance (123 lignes seulement, 99.2% actif), ADH IDE 166 n'a pratiquement aucune branche morte. Ses 6 dépendances de sous-programmes (notamment les vérifications d'interface IDE 200 et les raisons d'utilisation ADH IDE 231) forment un **pipeline de startup minimaliste** qui garantit que l'environnement utilisateur est correct et synchronisé avant toute transaction métier critique.

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (5 taches)

Traitements internes.

---

#### <a id="t1"></a>166 - Start

**Role** : Traitement : Start.

<details>
<summary>4 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [166.1](#t2) | read FROM_IMS | Traitement |
| [166.3](#t4) | Recup Logins avec matricule | Traitement |
| [166.4](#t5) | read FROM_IMS | Traitement |
| [166.5](#t6) | read FROM_IMS | Traitement |

</details>
**Delegue a** : [Recuperation langue (IDE 45)](ADH-IDE-45.md), [Alimentation Combos LIEU SEJ (IDE 224)](ADH-IDE-224.md), [Raisons utilisation ADH (IDE 231)](ADH-IDE-231.md)

---

#### <a id="t2"></a>166.1 - read FROM_IMS

**Role** : Traitement : read FROM_IMS.
**Variables liees** : EO (FROM_IMS)
**Delegue a** : [Recuperation langue (IDE 45)](ADH-IDE-45.md), [Alimentation Combos LIEU SEJ (IDE 224)](ADH-IDE-224.md), [Raisons utilisation ADH (IDE 231)](ADH-IDE-231.md)

---

#### <a id="t4"></a>166.3 - Recup Logins avec matricule

**Role** : Consultation/chargement : Recup Logins avec matricule.
**Delegue a** : [Recuperation langue (IDE 45)](ADH-IDE-45.md), [Alimentation Combos LIEU SEJ (IDE 224)](ADH-IDE-224.md), [Raisons utilisation ADH (IDE 231)](ADH-IDE-231.md)

---

#### <a id="t5"></a>166.4 - read FROM_IMS

**Role** : Traitement : read FROM_IMS.
**Variables liees** : EO (FROM_IMS)
**Delegue a** : [Recuperation langue (IDE 45)](ADH-IDE-45.md), [Alimentation Combos LIEU SEJ (IDE 224)](ADH-IDE-224.md), [Raisons utilisation ADH (IDE 231)](ADH-IDE-231.md)

---

#### <a id="t6"></a>166.5 - read FROM_IMS

**Role** : Traitement : read FROM_IMS.
**Variables liees** : EO (FROM_IMS)
**Delegue a** : [Recuperation langue (IDE 45)](ADH-IDE-45.md), [Alimentation Combos LIEU SEJ (IDE 224)](ADH-IDE-224.md), [Raisons utilisation ADH (IDE 231)](ADH-IDE-231.md)


### 3.2 Calcul (1 tache)

Calculs metier : montants, stocks, compteurs.

---

#### <a id="t3"></a>166.2 - comptage lieu sejour

**Role** : Traitement : comptage lieu sejour.


### 3.3 Initialisation (1 tache)

Reinitialisation d'etats et variables de travail.

---

#### <a id="t7"></a>166.4.1 - reset log_initialisation_tpe

**Role** : Reinitialisation : reset log_initialisation_tpe.
**Delegue a** : [  Initialistaion Easy Arrival (IDE 50)](ADH-IDE-50.md)


## 5. REGLES METIER

7 regles identifiees:

### Autres (7 regles)

#### <a id="rm-RM-001"></a>[RM-001] Traitement si [H] est non nul

| Element | Detail |
|---------|--------|
| **Condition** | `[H]<>0` |
| **Si vrai** | 'N11.'&Trim(Str([H] |
| **Si faux** | '#'))&'CZ','N13CZ') |
| **Expression source** | Expression 3 : `IF([H]<>0,'N11.'&Trim(Str([H],'#'))&'CZ','N13CZ')` |
| **Exemple** | Si [H]<>0 â†’ 'N11.'&Trim(Str([H]. Sinon â†’ '#'))&'CZ','N13CZ') |

#### <a id="rm-RM-002"></a>[RM-002] Negation de (W0 connection ? [A]) AND NOT(IsComponent()) (condition inversee)

| Element | Detail |
|---------|--------|
| **Condition** | `NOT (W0 connection ? [A]) AND NOT(IsComponent())` |
| **Si vrai** | Action si vrai |
| **Variables** | EN (W0 connection ?) |
| **Expression source** | Expression 4 : `NOT (W0 connection ? [A]) AND NOT(IsComponent())` |
| **Exemple** | Si NOT (W0 connection ? [A]) AND NOT(IsComponent()) â†’ Action si vrai |

#### <a id="rm-RM-003"></a>[RM-003] Negation de (VG4 OR IsComponent() OR INIGet ('[MAGIC_LOGICAL_NAMES]RunMode')='B') (condition inversee)

| Element | Detail |
|---------|--------|
| **Condition** | `NOT (VG4 OR IsComponent() OR INIGet ('[MAGIC_LOGICAL_NAMES]RunMode')='B')` |
| **Si vrai** | Action si vrai |
| **Expression source** | Expression 11 : `NOT (VG4 OR IsComponent() OR INIGet ('[MAGIC_LOGICAL_NAMES]R` |
| **Exemple** | Si NOT (VG4 OR IsComponent() OR INIGet ('[MAGIC_LOGICAL_NAMES]RunMode')='B') â†’ Action si vrai |

#### <a id="rm-RM-004"></a>[RM-004] Condition: Trim(INIGet('[MAGIC_LOGICAL_NAMES]RunMode')) different de 'B'

| Element | Detail |
|---------|--------|
| **Condition** | `Trim(INIGet('[MAGIC_LOGICAL_NAMES]RunMode'))<>'B'` |
| **Si vrai** | Action si vrai |
| **Expression source** | Expression 12 : `Trim(INIGet('[MAGIC_LOGICAL_NAMES]RunMode'))<>'B'` |
| **Exemple** | Si Trim(INIGet('[MAGIC_LOGICAL_NAMES]RunMode'))<>'B' â†’ Action si vrai |

#### <a id="rm-RM-005"></a>[RM-005] Condition composite: NOT(IsComponent()) AND VG111 AND Range(Term(),430,450)

| Element | Detail |
|---------|--------|
| **Condition** | `NOT(IsComponent()) AND VG111 AND Range(Term(),430,450)` |
| **Si vrai** | Action si vrai |
| **Expression source** | Expression 20 : `NOT(IsComponent()) AND VG111 AND Range(Term(),430,450)` |
| **Exemple** | Si NOT(IsComponent()) AND VG111 AND Range(Term(),430,450) â†’ Action si vrai |

#### <a id="rm-RM-006"></a>[RM-006] Condition composite: MnuShow('ID_CMP',VG3 OR VG74)

| Element | Detail |
|---------|--------|
| **Condition** | `MnuShow('ID_CMP',VG3 OR VG74)` |
| **Si vrai** | Action si vrai |
| **Expression source** | Expression 23 : `MnuShow('ID_CMP',VG3 OR VG74)` |
| **Exemple** | Si MnuShow('ID_CMP',VG3 OR VG74) â†’ Action si vrai |

#### <a id="rm-RM-007"></a>[RM-007] Negation de VG78 (condition inversee)

| Element | Detail |
|---------|--------|
| **Condition** | `NOT VG78` |
| **Si vrai** | Action si vrai |
| **Expression source** | Expression 25 : `NOT VG78` |
| **Exemple** | Si NOT VG78 â†’ Action si vrai |

## 6. CONTEXTE

- **Appele par**: [VAD validés à imprimer (IDE 0)](ADH-IDE-0.md), [Histo ventes Gratuités (IDE 0)](ADH-IDE-0.md), [Histo ventes IGR (IDE 0)](ADH-IDE-0.md), [Histo ventes payantes /PMS-605 (IDE 0)](ADH-IDE-0.md), [Histo ventes payantes /PMS-623 (IDE 0)](ADH-IDE-0.md), [Print extrait compte /Service (IDE 0)](ADH-IDE-0.md), [Transaction Nouv vente PMS-584 (IDE 0)](ADH-IDE-0.md), [Transaction Nouv vente PMS-710 (IDE 0)](ADH-IDE-0.md), [Transaction Nouv vente PMS-721 (IDE 0)](ADH-IDE-0.md), [Transferts (IDE 0)](ADH-IDE-0.md), [Main Program (IDE 1)](ADH-IDE-1.md)
- **Appelle**: 6 programmes | **Tables**: 8 (W:1 R:5 L:3) | **Taches**: 7 | **Expressions**: 30

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (7 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **166.1** | [**Start** (166)](#t1) | MDI | - | Traitement |
| 166.1.1 | [read FROM_IMS (166.1)](#t2) | MDI | - | |
| 166.1.2 | [Recup Logins avec matricule (166.3)](#t4) | - | - | |
| 166.1.3 | [read FROM_IMS (166.4)](#t5) | MDI | - | |
| 166.1.4 | [read FROM_IMS (166.5)](#t6) | MDI | - | |
| **166.2** | [**comptage lieu sejour** (166.2)](#t3) | - | - | Calcul |
| **166.3** | [**reset log_initialisation_tpe** (166.4.1)](#t7) | - | - | Initialisation |

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

### Tables utilisees (8)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 878 | categorie_operation_mw | Operations comptables | DB | R | **W** |   | 2 |
| 740 | pv_stock_movements | Articles et stock | DB | R |   |   | 1 |
| 67 | tables___________tab |  | DB | R |   |   | 1 |
| 81 | societe__________soc |  | DB | R |   |   | 1 |
| 219 | communication_ims |  | DB | R |   |   | 1 |
| 118 | tables_imports |  | DB |   |   | L | 1 |
| 69 | initialisation___ini |  | DB |   |   | L | 1 |
| 728 | arc_cc_total |  | DB |   |   | L | 1 |

### Colonnes par table (2 / 5 tables avec colonnes identifiees)

<details>
<summary>Table 878 - categorie_operation_mw (R/**W**) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 740 - pv_stock_movements (R) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 67 - tables___________tab (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | W0 connection ? | R | Logical |
| B | FROM_IMS | R | Alpha |
| C | L Contrôle date OK | R | Logical |
| D | v.Tpt_interface ? | R | Logical |
| E | v.Code TPE | R | Unicode |

</details>

<details>
<summary>Table 81 - societe__________soc (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | V.Cpt lieu sejour | R | Numeric |
| B | v Retour Lieu sejour defaut | R | Logical |

</details>

<details>
<summary>Table 219 - communication_ims (R) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Variables de session (2)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| EQ | v.Tpt_interface ? | Logical | 1x session |
| ER | v.Code TPE | Unicode | 1x session |

### 11.2 Variables de travail (1)

Variables internes au programme.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| EN | W0 connection ? | Logical | 2x calcul interne |

### 11.3 Autres (2)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| EO | FROM_IMS | Alpha | - |
| EP | L Contrôle date OK | Logical | - |

## 12. EXPRESSIONS

**30 / 30 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONCATENATION | 1 | 0 |
| CONDITION | 4 | 4 |
| NEGATION | 3 | 3 |
| CONSTANTE | 2 | 0 |
| OTHER | 13 | 0 |
| REFERENCE_VG | 4 | 0 |
| STRING | 2 | 0 |
| FORMAT | 1 | 0 |

### 12.2 Expressions cles par type

#### CONCATENATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 21 | `'cmd /c mkdir '&Translate('%club_exportdata%')&'Easy_Check_Out'` | - |

#### CONDITION (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 20 | `NOT(IsComponent()) AND VG111 AND Range(Term(),430,450)` | [RM-005](#rm-RM-005) |
| CONDITION | 23 | `MnuShow('ID_CMP',VG3 OR VG74)` | [RM-006](#rm-RM-006) |
| CONDITION | 3 | `IF([H]<>0,'N11.'&Trim(Str([H],'#'))&'CZ','N13CZ')` | [RM-001](#rm-RM-001) |
| CONDITION | 12 | `Trim(INIGet('[MAGIC_LOGICAL_NAMES]RunMode'))<>'B'` | [RM-004](#rm-RM-004) |

#### NEGATION (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| NEGATION | 25 | `NOT VG78` | [RM-007](#rm-RM-007) |
| NEGATION | 11 | `NOT (VG4 OR IsComponent() OR INIGet ('[MAGIC_LOGICAL_NAMES]RunMode')='B')` | [RM-003](#rm-RM-003) |
| NEGATION | 4 | `NOT (W0 connection ? [A]) AND NOT(IsComponent())` | [RM-002](#rm-RM-002) |

#### CONSTANTE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 27 | `'BDEV'` | - |
| CONSTANTE | 13 | `'CA'` | - |

#### OTHER (13 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 19 | `NOT(IsComponent())` | - |
| OTHER | 16 | `v.Tpt_interface ? [D]` | - |
| OTHER | 10 | `SetParam ('CHAINEDLISTING','NO')` | - |
| OTHER | 30 | `[F]` | - |
| OTHER | 28 | `[G]` | - |
| ... | | *+8 autres* | |

#### REFERENCE_VG (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 18 | `VG8` | - |
| REFERENCE_VG | 26 | `VG78` | - |
| REFERENCE_VG | 14 | `VG17` | - |
| REFERENCE_VG | 15 | `VG23` | - |

#### STRING (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| STRING | 24 | `Val([J], '3')` | - |
| STRING | 17 | `Trim(v.Code TPE [E])` | - |

#### FORMAT (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| FORMAT | 29 | `Str([M],'3')` | - |

### 12.3 Toutes les expressions (30)

<details>
<summary>Voir les 30 expressions</summary>

#### CONCATENATION (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 21 | `'cmd /c mkdir '&Translate('%club_exportdata%')&'Easy_Check_Out'` |

#### CONDITION (4)

| IDE | Expression Decodee |
|-----|-------------------|
| 3 | `IF([H]<>0,'N11.'&Trim(Str([H],'#'))&'CZ','N13CZ')` |
| 12 | `Trim(INIGet('[MAGIC_LOGICAL_NAMES]RunMode'))<>'B'` |
| 20 | `NOT(IsComponent()) AND VG111 AND Range(Term(),430,450)` |
| 23 | `MnuShow('ID_CMP',VG3 OR VG74)` |

#### NEGATION (3)

| IDE | Expression Decodee |
|-----|-------------------|
| 4 | `NOT (W0 connection ? [A]) AND NOT(IsComponent())` |
| 11 | `NOT (VG4 OR IsComponent() OR INIGet ('[MAGIC_LOGICAL_NAMES]RunMode')='B')` |
| 25 | `NOT VG78` |

#### CONSTANTE (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 13 | `'CA'` |
| 27 | `'BDEV'` |

#### OTHER (13)

| IDE | Expression Decodee |
|-----|-------------------|
| 1 | `SetParam ('VERIF_USERB','O')` |
| 2 | `W0 connection ? [A]` |
| 5 | `SetParam ('SPECIFICPRINT','VOID')` |
| 6 | `SetParam ('CURRENTPRINTERNUM',0)` |
| 7 | `SetParam ('CURRENTPRINTERNAME','VOID')` |
| 8 | `SetParam ('NUMBERCOPIES',0)` |
| 9 | `SetParam ('LISTINGNUMPRINTERCHOICE',0)` |
| 10 | `SetParam ('CHAINEDLISTING','NO')` |
| 16 | `v.Tpt_interface ? [D]` |
| 19 | `NOT(IsComponent())` |
| 22 | `NOT(FileExist(Translate('%club_exportdata%')&'Easy_Check_Out'))` |
| 28 | `[G]` |
| 30 | `[F]` |

#### REFERENCE_VG (4)

| IDE | Expression Decodee |
|-----|-------------------|
| 14 | `VG17` |
| 15 | `VG23` |
| 18 | `VG8` |
| 26 | `VG78` |

#### STRING (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 17 | `Trim(v.Code TPE [E])` |
| 24 | `Val([J], '3')` |

#### FORMAT (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 29 | `Str([M],'3')` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [VAD validés à imprimer (IDE 0)](ADH-IDE-0.md) -> **Start (IDE 166)**

Main -> ... -> [Histo ventes Gratuités (IDE 0)](ADH-IDE-0.md) -> **Start (IDE 166)**

Main -> ... -> [Histo ventes IGR (IDE 0)](ADH-IDE-0.md) -> **Start (IDE 166)**

Main -> ... -> [Histo ventes payantes /PMS-605 (IDE 0)](ADH-IDE-0.md) -> **Start (IDE 166)**

Main -> ... -> [Histo ventes payantes /PMS-623 (IDE 0)](ADH-IDE-0.md) -> **Start (IDE 166)**

Main -> ... -> [Print extrait compte /Service (IDE 0)](ADH-IDE-0.md) -> **Start (IDE 166)**

Main -> ... -> [Transaction Nouv vente PMS-584 (IDE 0)](ADH-IDE-0.md) -> **Start (IDE 166)**

Main -> ... -> [Transaction Nouv vente PMS-710 (IDE 0)](ADH-IDE-0.md) -> **Start (IDE 166)**

Main -> ... -> [Transaction Nouv vente PMS-721 (IDE 0)](ADH-IDE-0.md) -> **Start (IDE 166)**

Main -> ... -> [Transferts (IDE 0)](ADH-IDE-0.md) -> **Start (IDE 166)**

Main -> ... -> [Main Program (IDE 1)](ADH-IDE-1.md) -> **Start (IDE 166)**

```mermaid
graph LR
    T166[166 Start]
    style T166 fill:#58a6ff
    CALLER1[1 Main Program]
    CALLER1 --> T166
    style CALLER1 fill:#3fb950
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [0](ADH-IDE-0.md) | VAD validés à imprimer | 2 |
| [0](ADH-IDE-0.md) | Histo ventes Gratuités | 1 |
| [0](ADH-IDE-0.md) | Histo ventes IGR | 1 |
| [0](ADH-IDE-0.md) | Histo ventes payantes /PMS-605 | 1 |
| [0](ADH-IDE-0.md) | Histo ventes payantes /PMS-623 | 1 |
| [0](ADH-IDE-0.md) | Print extrait compte /Service | 1 |
| [0](ADH-IDE-0.md) | Transaction Nouv vente PMS-584 | 1 |
| [0](ADH-IDE-0.md) | Transaction Nouv vente PMS-710 | 1 |
| [0](ADH-IDE-0.md) | Transaction Nouv vente PMS-721 | 1 |
| [0](ADH-IDE-0.md) | Transferts | 1 |
| [1](ADH-IDE-1.md) | Main Program | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T166[166 Start]
    style T166 fill:#58a6ff
    C45[45 Recuperation langue]
    T166 --> C45
    style C45 fill:#3fb950
    C50[50 Initialistaion Easy...]
    T166 --> C50
    style C50 fill:#3fb950
    C52[52 Creation adresse_vi...]
    T166 --> C52
    style C52 fill:#3fb950
    C200[200 Verification si cl...]
    T166 --> C200
    style C200 fill:#3fb950
    C224[224 Alimentation Combo...]
    T166 --> C224
    style C224 fill:#3fb950
    C231[231 Raisons utilisatio...]
    T166 --> C231
    style C231 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [45](ADH-IDE-45.md) | Recuperation langue | 1 | Recuperation donnees |
| [50](ADH-IDE-50.md) |   Initialistaion Easy Arrival | 1 | Reinitialisation |
| [52](ADH-IDE-52.md) | Creation adresse_village | 1 | Sous-programme |
| [200](ADH-IDE-200.md) | Verification si client/serveur | 1 | Controle/validation |
| [224](ADH-IDE-224.md) | Alimentation Combos LIEU SEJ | 1 | Sous-programme |
| [231](ADH-IDE-231.md) | Raisons utilisation ADH | 1 | Parametrage |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 123 | Programme compact |
| Expressions | 30 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 6 | Dependances moderees |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0.8% (1 / 123) | Code sain |
| Regles metier | 7 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (5 taches: 0 ecran, 5 traitements)

- **Strategie** : 5 service(s) backend injectable(s) (Domain Services).
- 6 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Calcul (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Services de calcul purs (Domain Services).
- Migrer la logique de calcul (stock, compteurs, montants)

#### Initialisation (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Constructeur/methode `InitAsync()` dans l'orchestrateur.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| categorie_operation_mw | Table WRITE (Database) | 1x | Schema + repository |
| [Verification si client/serveur (IDE 200)](ADH-IDE-200.md) | Sous-programme | 1x | Normale - Controle/validation |
| [Alimentation Combos LIEU SEJ (IDE 224)](ADH-IDE-224.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Raisons utilisation ADH (IDE 231)](ADH-IDE-231.md) | Sous-programme | 1x | Normale - Parametrage |
| [Recuperation langue (IDE 45)](ADH-IDE-45.md) | Sous-programme | 1x | Normale - Recuperation donnees |
| [  Initialistaion Easy Arrival (IDE 50)](ADH-IDE-50.md) | Sous-programme | 1x | Normale - Reinitialisation |
| [Creation adresse_village (IDE 52)](ADH-IDE-52.md) | Sous-programme | 1x | Normale - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-08 03:49*
