# VIL IDE 201 - Print recap sessions

> **Analyse**: Phases 1-4 2026-02-03 21:02 -> 21:02 (12s) | Assemblage 21:02
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | VIL |
| IDE Position | 201 |
| Nom Programme | Print recap sessions |
| Fichier source | `Prg_201.xml` |
| Dossier IDE | Sauvegarde |
| Taches | 23 (0 ecrans visibles) |
| Tables modifiees | 2 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Print recap sessions** assure la gestion complete de ce processus, accessible depuis [    Listings cloture HTML (IDE 219)](VIL-IDE-219.md).

Le flux de traitement s'organise en **4 blocs fonctionnels** :

- **Traitement** (19 taches) : traitements metier divers
- **Impression** (2 taches) : generation de tickets et documents
- **Calcul** (1 tache) : calculs de montants, stocks ou compteurs
- **Saisie** (1 tache) : ecrans de saisie utilisateur (formulaires, champs, donnees)

**Donnees modifiees** : 2 tables en ecriture (tempo_ecran_mecano, tempo_ecr_menage).

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Impression (2 taches)

- **201** - Print etat recap sessions
- **201.10** - Edition

#### Phase 2 : Traitement (19 taches)

- **201.1** - Sessions caisses
- **201.1.1** - CAISSE v1 **[[ECRAN]](#ecran-t3)**
- **201.1.2** - Sessions
- **201.1.2.1** - Appro / Remise
- **201.2** - Lecture 18
- **201.2.1** - Upd Recap Sessions
- **201.3.1** - Upd Recap Sessions
- **201.4** - Telecollectes
- **201.4.1** - Upd Recap Sessions Boutique
- **201.5** - Recap OD
- **201.6** - Recap Change
- **201.7** - Recap Ecarts
- **201.7.1** - Upd File
- **201.9** - PC Coffre 1
- **201.10.1** - Reception
- **201.10.1.1** - Telecollecte
- **201.10.2** - Autres Services
- **201.11** - Recap Change
- **201.1.3** - CAISSE v1 **[[ECRAN]](#ecran-t33)**

#### Phase 3 : Saisie (1 tache)

- **201.3** - Lecture Ventes

#### Phase 4 : Calcul (1 tache)

- **201.8** - Comptage Reception

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| tempo_ecran_mecano | **W**/L (13 usages) | Table temporaire ecran |
| tempo_ecr_menage | **W**/L (3 usages) | Table temporaire ecran |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Impression (2 taches)

Generation des documents et tickets.

---

#### <a id="t1"></a>201 - Print etat recap sessions

**Role** : Generation du document : Print etat recap sessions.
**Variables liees** : F (v.nb sessions reception)

---

#### <a id="t18"></a>201.10 - Edition

**Role** : Generation du document : Edition.


### 3.2 Traitement (19 taches)

Traitements internes.

---

#### <a id="t2"></a>201.1 - Sessions caisses

**Role** : Traitement : Sessions caisses.
**Variables liees** : F (v.nb sessions reception)

---

#### <a id="t3"></a>201.1.1 - CAISSE v1 [[ECRAN]](#ecran-t3)

**Role** : Traitement : CAISSE v1.
**Ecran** : 205 x 89 DLU (MDI) | [Voir mockup](#ecran-t3)

---

#### <a id="t4"></a>201.1.2 - Sessions

**Role** : Traitement : Sessions.
**Variables liees** : F (v.nb sessions reception)

---

#### <a id="t5"></a>201.1.2.1 - Appro / Remise

**Role** : Calcul fidelite/avantage : Appro / Remise.
**Variables liees** : I (v.Appro Coffre 1), J (v.Remise Coffre 1)

---

#### <a id="t6"></a>201.2 - Lecture 18

**Role** : Traitement : Lecture 18.

---

#### <a id="t7"></a>201.2.1 - Upd Recap Sessions

**Role** : Traitement : Upd Recap Sessions.
**Variables liees** : F (v.nb sessions reception)

---

#### <a id="t9"></a>201.3.1 - Upd Recap Sessions

**Role** : Traitement : Upd Recap Sessions.
**Variables liees** : F (v.nb sessions reception)

---

#### <a id="t10"></a>201.4 - Telecollectes

**Role** : Traitement : Telecollectes.

---

#### <a id="t11"></a>201.4.1 - Upd Recap Sessions Boutique

**Role** : Traitement : Upd Recap Sessions Boutique.
**Variables liees** : F (v.nb sessions reception)

---

#### <a id="t12"></a>201.5 - Recap OD

**Role** : Traitement : Recap OD.

---

#### <a id="t13"></a>201.6 - Recap Change

**Role** : Traitement : Recap Change.

---

#### <a id="t14"></a>201.7 - Recap Ecarts

**Role** : Traitement : Recap Ecarts.

---

#### <a id="t15"></a>201.7.1 - Upd File

**Role** : Traitement : Upd File.

---

#### <a id="t17"></a>201.9 - PC Coffre 1

**Role** : Traitement : PC Coffre 1.
**Variables liees** : B (p.Terminal Coffre 2), C (p.Hostname Coffre 2), G (v.user coffre 2), H (v.PC Coffre 1), I (v.Appro Coffre 1)

---

#### <a id="t19"></a>201.10.1 - Reception

**Role** : Traitement : Reception.
**Variables liees** : F (v.nb sessions reception)

---

#### <a id="t20"></a>201.10.1.1 - Telecollecte

**Role** : Traitement : Telecollecte.

---

#### <a id="t21"></a>201.10.2 - Autres Services

**Role** : Traitement : Autres Services.

---

#### <a id="t30"></a>201.11 - Recap Change

**Role** : Traitement : Recap Change.

---

#### <a id="t33"></a>201.1.3 - CAISSE v1 [[ECRAN]](#ecran-t33)

**Role** : Traitement : CAISSE v1.
**Ecran** : 205 x 89 DLU (MDI) | [Voir mockup](#ecran-t33)


### 3.3 Saisie (1 tache)

Ce bloc traite la saisie des donnees de la transaction.

---

#### <a id="t8"></a>201.3 - Lecture Ventes

**Role** : Saisie des donnees : Lecture Ventes.


### 3.4 Calcul (1 tache)

Calculs metier : montants, stocks, compteurs.

---

#### <a id="t16"></a>201.8 - Comptage Reception

**Role** : Traitement : Comptage Reception.
**Variables liees** : F (v.nb sessions reception)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [    Listings cloture HTML (IDE 219)](VIL-IDE-219.md)
- **Appelle**: 0 programmes | **Tables**: 21 (W:2 R:9 L:14) | **Taches**: 23 | **Expressions**: 4

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (23 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **201.1** | [**Print etat recap sessions** (201)](#t1) | MDI | - | Impression |
| 201.1.1 | [Edition (201.10)](#t18) | MDI | - | |
| **201.2** | [**Sessions caisses** (201.1)](#t2) | MDI | - | Traitement |
| 201.2.1 | [CAISSE v1 (201.1.1)](#t3) [mockup](#ecran-t3) | MDI | 205x89 | |
| 201.2.2 | [Sessions (201.1.2)](#t4) | MDI | - | |
| 201.2.3 | [Appro / Remise (201.1.2.1)](#t5) | MDI | - | |
| 201.2.4 | [Lecture 18 (201.2)](#t6) | MDI | - | |
| 201.2.5 | [Upd Recap Sessions (201.2.1)](#t7) | MDI | - | |
| 201.2.6 | [Upd Recap Sessions (201.3.1)](#t9) | MDI | - | |
| 201.2.7 | [Telecollectes (201.4)](#t10) | MDI | - | |
| 201.2.8 | [Upd Recap Sessions Boutique (201.4.1)](#t11) | MDI | - | |
| 201.2.9 | [Recap OD (201.5)](#t12) | MDI | - | |
| 201.2.10 | [Recap Change (201.6)](#t13) | MDI | - | |
| 201.2.11 | [Recap Ecarts (201.7)](#t14) | MDI | - | |
| 201.2.12 | [Upd File (201.7.1)](#t15) | MDI | - | |
| 201.2.13 | [PC Coffre 1 (201.9)](#t17) | MDI | - | |
| 201.2.14 | [Reception (201.10.1)](#t19) | MDI | - | |
| 201.2.15 | [Telecollecte (201.10.1.1)](#t20) | MDI | - | |
| 201.2.16 | [Autres Services (201.10.2)](#t21) | MDI | - | |
| 201.2.17 | [Recap Change (201.11)](#t30) | MDI | - | |
| 201.2.18 | [CAISSE v1 (201.1.3)](#t33) [mockup](#ecran-t33) | MDI | 205x89 | |
| **201.3** | [**Lecture Ventes** (201.3)](#t8) | MDI | - | Saisie |
| **201.4** | [**Comptage Reception** (201.8)](#t16) | MDI | - | Calcul |

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

### Tables utilisees (21)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 40 | comptable________cte |  | DB | R |   |   | 1 |
| 44 | change___________chg |  | DB | R |   |   | 1 |
| 54 | pieces_caisse____pks | Sessions de caisse | DB | R |   |   | 1 |
| 66 | imputations______imp |  | DB | R |   |   | 1 |
| 67 | tables___________tab |  | DB | R |   | L | 4 |
| 69 | initialisation___ini |  | DB |   |   | L | 1 |
| 147 | change_vente_____chg | Donnees de ventes | DB | R |   |   | 1 |
| 228 | detail_coffre | Etat du coffre | DB |   |   | L | 1 |
| 234 | ecarts |  | DB | R |   |   | 1 |
| 239 | total_od |  | DB |   |   | L | 1 |
| 241 | pointage_appro_remise |  | DB |   |   | L | 1 |
| 246 | histo_sessions_caisse | Sessions de caisse | DB | R |   |   | 2 |
| 249 | histo_sessions_caisse_detail | Sessions de caisse | DB | R |   | L | 4 |
| 255 | suivi_pdc |  | DB |   |   | L | 1 |
| 263 | vente | Donnees de ventes | DB |   |   | L | 1 |
| 351 | sessions_ouvertes | Sessions de caisse | DB |   |   | L | 2 |
| 471 | comptage_coffre_devise | Etat du coffre | TMP |   |   | L | 3 |
| 554 | import_circuit___imc |  | TMP |   |   | L | 1 |
| 594 | tempo_ecran_mecano | Table temporaire ecran | TMP |   | **W** | L | 13 |
| 595 | tempo_ecr_menage | Table temporaire ecran | TMP |   | **W** | L | 3 |
| 734 | arc_pv_cust_packages |  | DB |   |   | L | 3 |

### Colonnes par table (14 / 11 tables avec colonnes identifiees)

<details>
<summary>Table 40 - comptable________cte (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | v.retour terminal IMS | R | Logical |
| B | v.is user reception | R | Logical |

</details>

<details>
<summary>Table 44 - change___________chg (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| H | v.total Change | R | Numeric |

</details>

<details>
<summary>Table 54 - pieces_caisse____pks (R) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 66 - imputations______imp (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | p.Date Comptable | R | Date |
| B | p.Terminal Coffre 2 | R | Numeric |
| C | p.Hostname Coffre 2 | R | Unicode |
| D | p.Societe | R | Alpha |
| E | p.Masque | R | Alpha |
| F | v.nb sessions reception | R | Numeric |
| G | v.user coffre 2 | R | Alpha |
| H | v.PC Coffre 1 | R | Numeric |
| I | v.Appro Coffre 1 | R | Numeric |
| J | v.Remise Coffre 1 | R | Numeric |
| K | v.Ecart Coffre 1 | R | Numeric |

</details>

<details>
<summary>Table 67 - tables___________tab (R/L) - 4 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | v.retour terminal IMS | R | Logical |
| B | v.is user reception | R | Logical |

</details>

<details>
<summary>Table 147 - change_vente_____chg (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| F | v.total Vente Cash | R | Numeric |
| H | v.total Change | R | Numeric |

</details>

<details>
<summary>Table 234 - ecarts (R) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 246 - histo_sessions_caisse (R) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| F | v.nb sessions reception | R | Numeric |

</details>

<details>
<summary>Table 249 - histo_sessions_caisse_detail (R/L) - 4 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| F | v.nb sessions reception | R | Numeric |

</details>

<details>
<summary>Table 594 - tempo_ecran_mecano (**W**/L) - 13 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | v.total Cheques | W | Numeric |
| B | v.total OD | W | Numeric |
| C | v.total FDR Init | W | Numeric |
| D | v.total FDR Final | W | Numeric |
| E | v.total Vers/Ret Cash | W | Numeric |
| F | v.total Vente Cash | W | Numeric |
| G | v.total Solde Cash | W | Numeric |
| H | v.total Change | W | Numeric |
| I | v.total Appro | W | Numeric |
| J | v.total Remise | W | Numeric |
| K | v.total Ecart | W | Numeric |
| L | v.total AMEX | W | Numeric |
| M | v.total CCAU | W | Numeric |
| N | v.total Visa | W | Numeric |
| O | v.total CC | W | Numeric |

</details>

<details>
<summary>Table 595 - tempo_ecr_menage (**W**/L) - 3 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (5)

Variables recues du programme appelant ([    Listings cloture HTML (IDE 219)](VIL-IDE-219.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | p.Date Comptable | Date | 2x parametre entrant |
| B | p.Terminal Coffre 2 | Numeric | - |
| C | p.Hostname Coffre 2 | Unicode | [201.9](#t17) |
| D | p.Societe | Alpha | - |
| E | p.Masque | Alpha | - |

### 11.2 Variables de session (10)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| F | v.nb sessions reception | Numeric | - |
| G | v.user coffre 2 | Alpha | - |
| H | v.PC Coffre 1 | Numeric | - |
| I | v.Appro Coffre 1 | Numeric | - |
| J | v.Remise Coffre 1 | Numeric | - |
| K | v.Ecart Coffre 1 | Numeric | - |
| L | v.total AMEX | Numeric | - |
| M | v.total CCAU | Numeric | - |
| N | v.total Visa | Numeric | - |
| O | v.total CC | Numeric | - |

## 12. EXPRESSIONS

**4 / 4 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCULATION | 1 | 0 |
| CONSTANTE | 1 | 0 |
| OTHER | 2 | 0 |

### 12.2 Expressions cles par type

#### CALCULATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 3 | `p.Date Comptable [A]-1` | - |

#### CONSTANTE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 2 | `'CHGE'` | - |

#### OTHER (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 4 | `p.Date Comptable [A]` | - |
| OTHER | 1 | `p.Hostname Coffre 2 [C]` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [    Listings cloture HTML (IDE 219)](VIL-IDE-219.md) -> **Print recap sessions (IDE 201)**

```mermaid
graph LR
    T201[201 Print recap sessions]
    style T201 fill:#58a6ff
    CC219[219 Listings cloture HTML]
    style CC219 fill:#8b5cf6
    CC219 --> T201
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [219](VIL-IDE-219.md) |     Listings cloture HTML | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T201[201 Print recap sessions]
    style T201 fill:#58a6ff
    NONE[Aucun callee]
    T201 -.-> NONE
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
| Lignes de logique | 537 | Programme volumineux |
| Expressions | 4 | Peu de logique |
| Tables WRITE | 2 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 537) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Impression (2 taches: 0 ecran, 2 traitements)

- **Strategie** : Templates HTML -> PDF via wkhtmltopdf ou Puppeteer.
- `PrintService` injectable avec choix imprimante

#### Traitement (19 taches: 2 ecrans, 17 traitements)

- **Strategie** : Orchestrateur avec 2 ecrans (Razor/React) et 17 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- Decomposer les taches en services unitaires testables.

#### Saisie (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Formulaire React/Blazor avec validation Zod/FluentValidation.
- Validation temps reel cote client + serveur

#### Calcul (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Services de calcul purs (Domain Services).
- Migrer la logique de calcul (stock, compteurs, montants)

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| tempo_ecran_mecano | Table WRITE (Temp) | 7x | Schema + repository |
| tempo_ecr_menage | Table WRITE (Temp) | 1x | Schema + repository |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 21:02*
