# PBG IDE 63 - Calcul JH

> **Analyse**: Phases 1-4 2026-02-03 09:03 -> 09:03 (20s) | Assemblage 09:03
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBG |
| IDE Position | 63 |
| Nom Programme | Calcul JH |
| Fichier source | `Prg_63.xml` |
| Domaine metier | General |
| Taches | 12 (0 ecrans visibles) |
| Tables modifiees | 2 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Calcul JH** assure la gestion complete de ce processus, accessible depuis [Ecriture log valid devalid (IDE 64)](PBG-IDE-64.md), [Choix prog repas non encaissée (IDE 66)](PBG-IDE-66.md), [Repas non encaissés (IDE 67)](PBG-IDE-67.md), [Gestion Groupe Arr/dep pms-656 (IDE 106)](PBG-IDE-106.md), [Repas non encaissés au villNEW (IDE 381)](PBG-IDE-381.md).

Le flux de traitement s'organise en **4 blocs fonctionnels** :

- **Traitement** (5 taches) : traitements metier divers
- **Validation** (4 taches) : controles et verifications de coherence
- **Creation** (2 taches) : insertion d'enregistrements en base (mouvements, prestations)
- **Calcul** (1 tache) : calculs de montants, stocks ou compteurs

**Donnees modifiees** : 2 tables en ecriture (initialisation___ini, pv_invoicehistoline).

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Calcul (1 tache)

- **63** - Calcul JH

#### Phase 2 : Traitement (5 taches)

- **63.1** - recup village
- **63.2** - Ecriture PV
- **63.3** - ecriture jh ecomat quotidienne
- **63.3.3.2** - update SQL
- **63.3.4.2** - update SQL

#### Phase 3 : Validation (4 taches)

- **63.3.1** - verif exist jh quotidienne **[[ECRAN]](#ecran-t5)**
- **63.3.2** - verif exist jh quotidienne **[[ECRAN]](#ecran-t6)**
- **63.3.3** - verif exist jh quotidienne **[[ECRAN]](#ecran-t7)**
- **63.3.4** - verif exist jh quotidienne **[[ECRAN]](#ecran-t10)**

#### Phase 4 : Creation (2 taches)

- **63.3.3.1** - insert SQL
- **63.3.4.1** - insert SQL

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| initialisation___ini | R/**W** (2 usages) |  |
| pv_invoicehistoline | **W** (1 usages) | Historique / journal |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Calcul (1 tache)

Calculs metier : montants, stocks, compteurs.

---

#### <a id="t1"></a>63 - Calcul JH

**Role** : Calcul : Calcul JH.


### 3.2 Traitement (5 taches)

Traitements internes.

---

#### <a id="t2"></a>63.1 - recup village

**Role** : Consultation/chargement : recup village.
**Variables liees** : F (V.Village)

---

#### <a id="t3"></a>63.2 - Ecriture PV

**Role** : Traitement : Ecriture PV.

---

#### <a id="t4"></a>63.3 - ecriture jh ecomat quotidienne

**Role** : Traitement : ecriture jh ecomat quotidienne.

---

#### <a id="t9"></a>63.3.3.2 - update SQL

**Role** : Traitement : update SQL.

---

#### <a id="t12"></a>63.3.4.2 - update SQL

**Role** : Traitement : update SQL.


### 3.3 Validation (4 taches)

Controles de coherence : 4 taches verifient les donnees et conditions.

---

#### <a id="t5"></a>63.3.1 - verif exist jh quotidienne [[ECRAN]](#ecran-t5)

**Role** : Verification : verif exist jh quotidienne.
**Ecran** : 171 x 195 DLU | [Voir mockup](#ecran-t5)
**Variables liees** : B (V.Existe qualite ?)

---

#### <a id="t6"></a>63.3.2 - verif exist jh quotidienne [[ECRAN]](#ecran-t6)

**Role** : Verification : verif exist jh quotidienne.
**Ecran** : 171 x 195 DLU | [Voir mockup](#ecran-t6)
**Variables liees** : B (V.Existe qualite ?)

---

#### <a id="t7"></a>63.3.3 - verif exist jh quotidienne [[ECRAN]](#ecran-t7)

**Role** : Verification : verif exist jh quotidienne.
**Ecran** : 171 x 195 DLU | [Voir mockup](#ecran-t7)
**Variables liees** : B (V.Existe qualite ?)

---

#### <a id="t10"></a>63.3.4 - verif exist jh quotidienne [[ECRAN]](#ecran-t10)

**Role** : Verification : verif exist jh quotidienne.
**Ecran** : 171 x 195 DLU | [Voir mockup](#ecran-t10)
**Variables liees** : B (V.Existe qualite ?)


### 3.4 Creation (2 taches)

Insertion de nouveaux enregistrements en base.

---

#### <a id="t8"></a>63.3.3.1 - insert SQL

**Role** : Creation d'enregistrement : insert SQL.

---

#### <a id="t11"></a>63.3.4.1 - insert SQL

**Role** : Creation d'enregistrement : insert SQL.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Ecriture log valid devalid (IDE 64)](PBG-IDE-64.md), [Choix prog repas non encaissée (IDE 66)](PBG-IDE-66.md), [Repas non encaissés (IDE 67)](PBG-IDE-67.md), [Gestion Groupe Arr/dep pms-656 (IDE 106)](PBG-IDE-106.md), [Repas non encaissés au villNEW (IDE 381)](PBG-IDE-381.md)
- **Appelle**: 0 programmes | **Tables**: 4 (W:2 R:1 L:2) | **Taches**: 12 | **Expressions**: 17

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (12 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **63.1** | [**Calcul JH** (63)](#t1) | - | - | Calcul |
| **63.2** | [**recup village** (63.1)](#t2) | - | - | Traitement |
| 63.2.1 | [Ecriture PV (63.2)](#t3) | - | - | |
| 63.2.2 | [ecriture jh ecomat quotidienne (63.3)](#t4) | - | - | |
| 63.2.3 | [update SQL (63.3.3.2)](#t9) | - | - | |
| 63.2.4 | [update SQL (63.3.4.2)](#t12) | - | - | |
| **63.3** | [**verif exist jh quotidienne** (63.3.1)](#t5) [mockup](#ecran-t5) | - | 171x195 | Validation |
| 63.3.1 | [verif exist jh quotidienne (63.3.2)](#t6) [mockup](#ecran-t6) | - | 171x195 | |
| 63.3.2 | [verif exist jh quotidienne (63.3.3)](#t7) [mockup](#ecran-t7) | - | 171x195 | |
| 63.3.3 | [verif exist jh quotidienne (63.3.4)](#t10) [mockup](#ecran-t10) | - | 171x195 | |
| **63.4** | [**insert SQL** (63.3.3.1)](#t8) | - | - | Creation |
| 63.4.1 | [insert SQL (63.3.4.1)](#t11) | - | - | |

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

### Tables utilisees (4)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 69 | initialisation___ini |  | DB | R | **W** |   | 2 |
| 120 | tables_qualites__qua |  | DB |   |   | L | 1 |
| 392 | pv_invoicehistoline | Historique / journal | DB |   | **W** |   | 1 |
| 825 | fac_hebergement_pro | Hebergement (chambres) | DB |   |   | L | 1 |

### Colonnes par table (1 / 2 tables avec colonnes identifiees)

<details>
<summary>Table 69 - initialisation___ini (R/**W**) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P.Date | W | Date |
| B | V.Existe qualite ? | W | Logical |
| C | V.JHP jour | W | Numeric |
| D | V.JHD jour | W | Numeric |
| E | V.JHE jour | W | Numeric |
| F | V.Village | W | Alpha |
| G | V.JHP mensuel | W | Numeric |
| H | V.JHP total | W | Numeric |
| I | V.JHD mensuel | W | Numeric |
| J | V.JHD Total | W | Numeric |
| K | V.JHE total | W | Numeric |
| L | V.JHE mensuel | W | Numeric |

</details>

<details>
<summary>Table 392 - pv_invoicehistoline (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (1)

Variables recues du programme appelant ([Ecriture log valid devalid (IDE 64)](PBG-IDE-64.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P.Date | Date | 2x parametre entrant |

### 11.2 Variables de session (11)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| B | V.Existe qualite ? | Logical | 1x session |
| C | V.JHP jour | Numeric | 2x session |
| D | V.JHD jour | Numeric | 2x session |
| E | V.JHE jour | Numeric | 4x session |
| F | V.Village | Alpha | 4x session |
| G | V.JHP mensuel | Numeric | - |
| H | V.JHP total | Numeric | - |
| I | V.JHD mensuel | Numeric | - |
| J | V.JHD Total | Numeric | - |
| K | V.JHE total | Numeric | - |
| L | V.JHE mensuel | Numeric | - |

## 12. EXPRESSIONS

**17 / 17 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCULATION | 6 | 0 |
| CONSTANTE | 5 | 0 |
| OTHER | 3 | 0 |
| CONDITION | 3 | 0 |

### 12.2 Expressions cles par type

#### CALCULATION (6 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 9 | `[P]+(V.JHE jour [E]+V.Village [F]+[Y]+[Z])/2` | - |
| CALCULATION | 10 | `[O]+[P]` | - |
| CALCULATION | 17 | `[S]+[U]` | - |
| CALCULATION | 5 | `[O]+(V.JHE jour [E]+V.Village [F]+[Y]+[Z])/2` | - |
| CALCULATION | 6 | `[S]+(V.JHE jour [E]+V.Village [F]+[Y]+[Z])/2` | - |
| ... | | *+1 autres* | |

#### CONSTANTE (5 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 14 | `'maint2'` | - |
| CONSTANTE | 15 | `'maint3'` | - |
| CONSTANTE | 13 | `'maint1'` | - |
| CONSTANTE | 1 | `'C'` | - |
| CONSTANTE | 12 | `'economat'` | - |

#### OTHER (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 4 | `V.JHD jour [D]` | - |
| OTHER | 3 | `V.JHP jour [C]` | - |
| OTHER | 2 | `BOM(P.Date [A])` | - |

#### CONDITION (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 16 | `V.Existe qualite ? [B]=P.Date [A]` | - |
| CONDITION | 11 | `[M]='JHD' OR (V.JHP jour [C]='IGR' AND V.JHD jour [D]<>'HCMB') OR V.JHD jour [D]='AVDJ' OR V.JHP jour [C]='VRL'` | - |
| CONDITION | 8 | `[M]='JHP'` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Ecriture log valid devalid (IDE 64)](PBG-IDE-64.md) -> **Calcul JH (IDE 63)**

Main -> ... -> [Choix prog repas non encaissée (IDE 66)](PBG-IDE-66.md) -> **Calcul JH (IDE 63)**

Main -> ... -> [Repas non encaissés (IDE 67)](PBG-IDE-67.md) -> **Calcul JH (IDE 63)**

Main -> ... -> [Gestion Groupe Arr/dep pms-656 (IDE 106)](PBG-IDE-106.md) -> **Calcul JH (IDE 63)**

Main -> ... -> [Repas non encaissés au villNEW (IDE 381)](PBG-IDE-381.md) -> **Calcul JH (IDE 63)**

```mermaid
graph LR
    T63[63 Calcul JH]
    style T63 fill:#58a6ff
    CC122[122 Validation Auto se...]
    style CC122 fill:#8b5cf6
    CC121[121 Validation Auto fi...]
    style CC121 fill:#8b5cf6
    CC124[124 Validation Arrivants]
    style CC124 fill:#8b5cf6
    CC64[64 Ecriture log valid ...]
    style CC64 fill:#3fb950
    CC381[381 Repas non encaissé...]
    style CC381 fill:#3fb950
    CC66[66 Choix prog repas no...]
    style CC66 fill:#3fb950
    CC67[67 Repas non encaissés]
    style CC67 fill:#3fb950
    CC106[106 Gestion Groupe Arr...]
    style CC106 fill:#3fb950
    CC121 --> CC64
    CC122 --> CC64
    CC124 --> CC64
    CC121 --> CC66
    CC122 --> CC66
    CC124 --> CC66
    CC121 --> CC67
    CC122 --> CC67
    CC124 --> CC67
    CC121 --> CC106
    CC122 --> CC106
    CC124 --> CC106
    CC121 --> CC381
    CC122 --> CC381
    CC124 --> CC381
    CC64 --> T63
    CC66 --> T63
    CC67 --> T63
    CC106 --> T63
    CC381 --> T63
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [64](PBG-IDE-64.md) | Ecriture log valid devalid | 1 |
| [66](PBG-IDE-66.md) | Choix prog repas non encaissée | 1 |
| [67](PBG-IDE-67.md) | Repas non encaissés | 1 |
| [106](PBG-IDE-106.md) | Gestion Groupe Arr/dep pms-656 | 1 |
| [381](PBG-IDE-381.md) | Repas non encaissés au villNEW | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T63[63 Calcul JH]
    style T63 fill:#58a6ff
    NONE[Aucun callee]
    T63 -.-> NONE
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
| Lignes de logique | 111 | Programme compact |
| Expressions | 17 | Peu de logique |
| Tables WRITE | 2 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 111) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Calcul (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Services de calcul purs (Domain Services).
- Migrer la logique de calcul (stock, compteurs, montants)

#### Traitement (5 taches: 0 ecran, 5 traitements)

- **Strategie** : 5 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

#### Validation (4 taches: 4 ecrans, 0 traitement)

- **Strategie** : FluentValidation avec validators specifiques.
- Chaque tache de validation -> un validator injectable

#### Creation (2 taches: 0 ecran, 2 traitements)

- **Strategie** : Repository pattern avec Entity Framework Core.
- Insertion via `IRepository<T>.CreateAsync()`

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| initialisation___ini | Table WRITE (Database) | 1x | Schema + repository |
| pv_invoicehistoline | Table WRITE (Database) | 1x | Schema + repository |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 09:03*
