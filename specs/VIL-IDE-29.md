# VIL IDE 29 - Listings cloture HTML

> **Analyse**: Phases 1-4 2026-02-03 01:15 -> 01:15 (35s) | Assemblage 01:15
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | VIL |
| IDE Position | 29 |
| Nom Programme | Listings cloture HTML |
| Fichier source | `Prg_29.xml` |
| Domaine metier | General |
| Taches | 5 (0 ecrans visibles) |
| Tables modifiees | 2 |
| Programmes appeles | 20 |

## 2. DESCRIPTION FONCTIONNELLE

**Listings cloture HTML** assure la gestion complete de ce processus, accessible depuis [Pilotage après sessions (IDE 10)](VIL-IDE-10.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (5 taches) : traitements metier divers

**Donnees modifiees** : 2 tables en ecriture (comptage_coffre_devise, pv_customer).

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (5 taches)

- **29** - CV  Menu listings complement. **[[ECRAN]](#ecran-t1)**
- **29.1** - Versements/Retraits
- **29.2** - Lecture solde veille
- **29.3** - Gen 341
- **29.4** - Gen 341

Delegue a : [Correspittivi (IDE 75)](VIL-IDE-75.md), [Truncate table SQL (IDE 48)](VIL-IDE-48.md), [Liste des telecollectes (IDE 70)](VIL-IDE-70.md)

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| pv_customer | **W** (1 usages) |  |
| comptage_coffre_devise | **W** (1 usages) | Etat du coffre |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (5 taches)

Traitements internes.

---

#### <a id="t1"></a>29 - CV  Menu listings complement. [[ECRAN]](#ecran-t1)

**Role** : Traitement : CV  Menu listings complement..
**Ecran** : 342 x 17 DLU (MDI) | [Voir mockup](#ecran-t1)

<details>
<summary>4 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [29.1](#t2) | Versements/Retraits | Traitement |
| [29.2](#t3) | Lecture solde veille | Traitement |
| [29.3](#t4) | Gen 341 | Traitement |
| [29.4](#t5) | Gen 341 | Traitement |

</details>
**Delegue a** : [Correspittivi (IDE 75)](VIL-IDE-75.md), [Truncate table SQL (IDE 48)](VIL-IDE-48.md), [Liste des telecollectes (IDE 70)](VIL-IDE-70.md)

---

#### <a id="t2"></a>29.1 - Versements/Retraits

**Role** : Traitement : Versements/Retraits.
**Delegue a** : [Correspittivi (IDE 75)](VIL-IDE-75.md), [Truncate table SQL (IDE 48)](VIL-IDE-48.md), [Liste des telecollectes (IDE 70)](VIL-IDE-70.md)

---

#### <a id="t3"></a>29.2 - Lecture solde veille

**Role** : Consultation/chargement : Lecture solde veille.
**Variables liees** : M (W0 solde veille)
**Delegue a** : [Correspittivi (IDE 75)](VIL-IDE-75.md), [Truncate table SQL (IDE 48)](VIL-IDE-48.md), [Liste des telecollectes (IDE 70)](VIL-IDE-70.md)

---

#### <a id="t4"></a>29.3 - Gen 341

**Role** : Traitement : Gen 341.
**Delegue a** : [Correspittivi (IDE 75)](VIL-IDE-75.md), [Truncate table SQL (IDE 48)](VIL-IDE-48.md), [Liste des telecollectes (IDE 70)](VIL-IDE-70.md)

---

#### <a id="t5"></a>29.4 - Gen 341

**Role** : Traitement : Gen 341.
**Delegue a** : [Correspittivi (IDE 75)](VIL-IDE-75.md), [Truncate table SQL (IDE 48)](VIL-IDE-48.md), [Liste des telecollectes (IDE 70)](VIL-IDE-70.md)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Pilotage après sessions (IDE 10)](VIL-IDE-10.md)
- **Appelle**: 20 programmes | **Tables**: 6 (W:2 R:2 L:2) | **Taches**: 5 | **Expressions**: 29

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (5 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **29.1** | [**CV  Menu listings complement.** (29)](#t1) [mockup](#ecran-t1) | MDI | 342x17 | Traitement |
| 29.1.1 | [Versements/Retraits (29.1)](#t2) | MDI | - | |
| 29.1.2 | [Lecture solde veille (29.2)](#t3) | MDI | - | |
| 29.1.3 | [Gen 341 (29.3)](#t4) | MDI | - | |
| 29.1.4 | [Gen 341 (29.4)](#t5) | MDI | - | |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Traitement principal]
    UPDATE[MAJ 2 tables]
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

### Tables utilisees (6)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 17 | backup_devises_caisse | Sessions de caisse | DB |   |   | L | 1 |
| 18 | backup_histo_sessions_caisse | Sessions de caisse | DB |   |   | L | 1 |
| 40 | comptable________cte |  | DB | R |   |   | 1 |
| 55 | solde_caisse_____sks | Sessions de caisse | DB | R |   |   | 1 |
| 471 | comptage_coffre_devise | Etat du coffre | TMP |   | **W** |   | 1 |
| 508 | pv_customer |  | TMP |   | **W** |   | 1 |

### Colonnes par table (3 / 4 tables avec colonnes identifiees)

<details>
<summary>Table 40 - comptable________cte (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| D | P0 date comptable | R | Date |

</details>

<details>
<summary>Table 55 - solde_caisse_____sks (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| M | W0 solde veille | R | Numeric |

</details>

<details>
<summary>Table 471 - comptage_coffre_devise (**W**) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| G | P0 Devise Locale | W | Alpha |
| H | P0 Terminal Coffre 2 | W | Numeric |
| I | P0 Hostname Coffre 2 | W | Unicode |

</details>

<details>
<summary>Table 508 - pv_customer (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (10)

Variables recues du programme appelant ([Pilotage après sessions (IDE 10)](VIL-IDE-10.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P0 societe | Alpha | - |
| B | P0 picture montant | Alpha | 1x parametre entrant |
| C | P0 nbre decimales | Numeric | 1x parametre entrant |
| D | P0 date comptable | Date | 4x parametre entrant |
| E | P0 nom village | Alpha | 1x parametre entrant |
| F | P0 Uni / Bi | Alpha | 1x parametre entrant |
| G | P0 Devise Locale | Alpha | - |
| H | P0 Terminal Coffre 2 | Numeric | - |
| I | P0 Hostname Coffre 2 | Unicode | - |
| J | P.i.delai expiration | Numeric | - |

### 11.2 Variables de travail (10)

Variables internes au programme.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| L | W0 param bidon | Numeric | - |
| M | W0 solde veille | Numeric | - |
| N | W0 montant versmnt | Numeric | - |
| O | W0 montant retrait | Numeric | - |
| P | W0 pkes recettes | Numeric | - |
| Q | W0 pkes depenses | Numeric | - |
| R | W0 Versement CASH | Numeric | - |
| S | W0 Versement NON CASH | Numeric | - |
| T | W0 Retrait CASH | Numeric | - |
| U | W0 Retrait NON CASH | Numeric | [29.1](#t2) |

### 11.3 Autres (1)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| K | WP0 masque cumul | Alpha | - |

<details>
<summary>Toutes les 21 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| P0 | **A** | P0 societe | Alpha |
| P0 | **B** | P0 picture montant | Alpha |
| P0 | **C** | P0 nbre decimales | Numeric |
| P0 | **D** | P0 date comptable | Date |
| P0 | **E** | P0 nom village | Alpha |
| P0 | **F** | P0 Uni / Bi | Alpha |
| P0 | **G** | P0 Devise Locale | Alpha |
| P0 | **H** | P0 Terminal Coffre 2 | Numeric |
| P0 | **I** | P0 Hostname Coffre 2 | Unicode |
| P0 | **J** | P.i.delai expiration | Numeric |
| W0 | **L** | W0 param bidon | Numeric |
| W0 | **M** | W0 solde veille | Numeric |
| W0 | **N** | W0 montant versmnt | Numeric |
| W0 | **O** | W0 montant retrait | Numeric |
| W0 | **P** | W0 pkes recettes | Numeric |
| W0 | **Q** | W0 pkes depenses | Numeric |
| W0 | **R** | W0 Versement CASH | Numeric |
| W0 | **S** | W0 Versement NON CASH | Numeric |
| W0 | **T** | W0 Retrait CASH | Numeric |
| W0 | **U** | W0 Retrait NON CASH | Numeric |
| Autre | **K** | WP0 masque cumul | Alpha |

</details>

## 12. EXPRESSIONS

**29 / 29 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONSTANTE | 9 | 0 |
| CAST_LOGIQUE | 1 | 0 |
| CONCATENATION | 1 | 0 |
| CONDITION | 2 | 0 |
| OTHER | 11 | 0 |
| REFERENCE_VG | 5 | 0 |

### 12.2 Expressions cles par type

#### CONSTANTE (9 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 19 | `'M'` | - |
| CONSTANTE | 16 | `'J'` | - |
| CONSTANTE | 29 | `'V'` | - |
| CONSTANTE | 28 | `'C'` | - |
| CONSTANTE | 12 | `2` | - |
| ... | | *+4 autres* | |

#### CAST_LOGIQUE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 2 | `'TRUE'LOG` | - |

#### CONCATENATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 3 | `'N'&Right (' ### ### ### ###'&Left ('.',P0 nbre decimales [C])&Left ('###',P0 nbre decimales [C]),16)&'Z'` | - |

#### CONDITION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 15 | `P0 date comptable [D]=EOM(P0 date comptable [D])` | - |
| CONDITION | 4 | `P0 Uni / Bi [F]='B'` | - |

#### OTHER (11 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 24 | `P0 date comptable [D]` | - |
| OTHER | 20 | `NOT(VG24)` | - |
| OTHER | 25 | `P0 nom village [E]` | - |
| OTHER | 27 | `P0 picture montant [B]` | - |
| OTHER | 26 | `W0 Retrait NON CASH [U]` | - |
| ... | | *+6 autres* | |

#### REFERENCE_VG (5 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 22 | `VG25` | - |
| REFERENCE_VG | 23 | `VG41` | - |
| REFERENCE_VG | 21 | `VG24` | - |
| REFERENCE_VG | 13 | `VG14` | - |
| REFERENCE_VG | 14 | `VG23` | - |

### 12.3 Toutes les expressions (29)

<details>
<summary>Voir les 29 expressions</summary>

#### CONSTANTE (9)

| IDE | Expression Decodee |
|-----|-------------------|
| 1 | `''` |
| 5 | `'O'` |
| 6 | `0` |
| 9 | `'2'` |
| 12 | `2` |
| 16 | `'J'` |
| 19 | `'M'` |
| 28 | `'C'` |
| 29 | `'V'` |

#### CAST_LOGIQUE (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 2 | `'TRUE'LOG` |

#### CONCATENATION (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 3 | `'N'&Right (' ### ### ### ###'&Left ('.',P0 nbre decimales [C])&Left ('###',P0 nbre decimales [C]),16)&'Z'` |

#### CONDITION (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 4 | `P0 Uni / Bi [F]='B'` |
| 15 | `P0 date comptable [D]=EOM(P0 date comptable [D])` |

#### OTHER (11)

| IDE | Expression Decodee |
|-----|-------------------|
| 7 | `DbDel ('{508,2}'DSOURCE,'')` |
| 8 | `DbName ('{471,2}'DSOURCE)` |
| 10 | `DbDel ('{594,2}'DSOURCE,'')` |
| 11 | `DbDel ('{595,2}'DSOURCE,'')` |
| 17 | `BOM(P0 date comptable [D])` |
| 18 | `EOM(P0 date comptable [D])` |
| 20 | `NOT(VG24)` |
| 24 | `P0 date comptable [D]` |
| 25 | `P0 nom village [E]` |
| 26 | `W0 Retrait NON CASH [U]` |
| 27 | `P0 picture montant [B]` |

#### REFERENCE_VG (5)

| IDE | Expression Decodee |
|-----|-------------------|
| 13 | `VG14` |
| 14 | `VG23` |
| 21 | `VG24` |
| 22 | `VG25` |
| 23 | `VG41` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Pilotage après sessions (IDE 10)](VIL-IDE-10.md) -> **Listings cloture HTML (IDE 29)**

```mermaid
graph LR
    T29[29 Listings cloture HTML]
    style T29 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC149[149 Start]
    style CC149 fill:#f59e0b
    CC9[9 Pilotage avant sessions]
    style CC9 fill:#f59e0b
    CC10[10 Pilotage après sess...]
    style CC10 fill:#3fb950
    CC9 --> CC10
    CC149 --> CC9
    CC1 --> CC149
    CC10 --> T29
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [10](VIL-IDE-10.md) | Pilotage après sessions | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T29[29 Listings cloture HTML]
    style T29 fill:#58a6ff
    C20[20 Print listing des c...]
    T29 --> C20
    style C20 fill:#3fb950
    C68[68 Print listing compt...]
    T29 --> C68
    style C68 fill:#3fb950
    C75[75 Correspittivi]
    T29 --> C75
    style C75 fill:#3fb950
    C111[111 Prep. list. compta...]
    T29 --> C111
    style C111 fill:#3fb950
    C19[19 Print listing des c...]
    T29 --> C19
    style C19 fill:#3fb950
    C21[21 Print recap devises]
    T29 --> C21
    style C21 fill:#3fb950
    C22[22 Print recap sessions]
    T29 --> C22
    style C22 fill:#3fb950
    C48[48 Truncate table SQL]
    T29 --> C48
    style C48 fill:#3fb950
    C61[61 CV Print change Achat]
    T29 --> C61
    style C61 fill:#3fb950
    C63[63 CV Print change Vente]
    T29 --> C63
    style C63 fill:#3fb950
    C65[65 CV Print listing gr...]
    T29 --> C65
    style C65 fill:#3fb950
    C66[66 Print brouillardclo...]
    T29 --> C66
    style C66 fill:#3fb950
    C67[67 Print Ecart]
    T29 --> C67
    style C67 fill:#3fb950
    C70[70 Liste des telecolle...]
    T29 --> C70
    style C70 fill:#3fb950
    C71[71 Print listing compt...]
    T29 --> C71
    style C71 fill:#3fb950
    C76[76 Genere tempo vente ...]
    T29 --> C76
    style C76 fill:#3fb950
    C77[77 Edition HTML Ventes...]
    T29 --> C77
    style C77 fill:#3fb950
    C79[79 Liste des paiements...]
    T29 --> C79
    style C79 fill:#3fb950
    C96[96 Liste des ventes]
    T29 --> C96
    style C96 fill:#3fb950
    C120[120 Recup Classe et Li...]
    T29 --> C120
    style C120 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [20](VIL-IDE-20.md) | Print listing des comptes (PME | 2 | Impression ticket/document |
| [68](VIL-IDE-68.md) | Print listing comptable | 2 | Impression ticket/document |
| [75](VIL-IDE-75.md) | Correspittivi | 2 | Sous-programme |
| [111](VIL-IDE-111.md) | Prep. list. comptable avec GP | 2 | Configuration impression |
| [19](VIL-IDE-19.md) |     Print listing des comptes | 1 | Impression ticket/document |
| [21](VIL-IDE-21.md) |     Print recap devises | 1 | Impression ticket/document |
| [22](VIL-IDE-22.md) |     Print recap sessions | 1 | Impression ticket/document |
| [48](VIL-IDE-48.md) | Truncate table SQL | 1 | Sous-programme |
| [61](VIL-IDE-61.md) | CV  Print change Achat | 1 | Impression ticket/document |
| [63](VIL-IDE-63.md) | CV  Print change Vente | 1 | Impression ticket/document |
| [65](VIL-IDE-65.md) | CV  Print listing gratuites | 1 | Impression ticket/document |
| [66](VIL-IDE-66.md) | Print brouillard/cloture | 1 | Impression ticket/document |
| [67](VIL-IDE-67.md) | Print Ecart | 1 | Impression ticket/document |
| [70](VIL-IDE-70.md) | Liste des telecollectes | 1 | Configuration impression |
| [71](VIL-IDE-71.md) | Print listing compte cash | 1 | Impression ticket/document |
| [76](VIL-IDE-76.md) | Genere tempo vente telecollec | 1 | Sous-programme |
| [77](VIL-IDE-77.md) | Edition HTML Ventes TPE | 1 | Impression ticket/document |
| [79](VIL-IDE-79.md) | Liste des paiements en attente | 1 | Configuration impression |
| [96](VIL-IDE-96.md) | Liste des ventes | 1 | Configuration impression |
| [120](VIL-IDE-120.md) | Recup Classe et Lib du MOP | 1 | Recuperation donnees |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 160 | Programme compact |
| Expressions | 29 | Peu de logique |
| Tables WRITE | 2 | Impact faible |
| Sous-programmes | 20 | Forte dependance |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 1.2% (2 / 160) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (5 taches: 1 ecran, 4 traitements)

- **Strategie** : Orchestrateur avec 1 ecrans (Razor/React) et 4 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 20 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| comptage_coffre_devise | Table WRITE (Temp) | 1x | Schema + repository |
| pv_customer | Table WRITE (Temp) | 1x | Schema + repository |
| [Correspittivi (IDE 75)](VIL-IDE-75.md) | Sous-programme | 2x | Haute - Sous-programme |
| [Prep. list. comptable avec GP (IDE 111)](VIL-IDE-111.md) | Sous-programme | 2x | Haute - Configuration impression |
| [Print listing des comptes (PME (IDE 20)](VIL-IDE-20.md) | Sous-programme | 2x | Haute - Impression ticket/document |
| [Print listing comptable (IDE 68)](VIL-IDE-68.md) | Sous-programme | 2x | Haute - Impression ticket/document |
| [Print listing compte cash (IDE 71)](VIL-IDE-71.md) | Sous-programme | 1x | Normale - Impression ticket/document |
| [Genere tempo vente telecollec (IDE 76)](VIL-IDE-76.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Print Ecart (IDE 67)](VIL-IDE-67.md) | Sous-programme | 1x | Normale - Impression ticket/document |
| [Liste des telecollectes (IDE 70)](VIL-IDE-70.md) | Sous-programme | 1x | Normale - Configuration impression |
| [Liste des ventes (IDE 96)](VIL-IDE-96.md) | Sous-programme | 1x | Normale - Configuration impression |
| [Recup Classe et Lib du MOP (IDE 120)](VIL-IDE-120.md) | Sous-programme | 1x | Normale - Recuperation donnees |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 01:15*
