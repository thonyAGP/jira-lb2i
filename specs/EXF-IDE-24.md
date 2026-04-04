# EXF IDE 24 - Reçu annulation new

> **Analyse**: Phases 1-4 2026-02-03 11:01 -> 11:01 (19s) | Assemblage 11:01
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | EXF |
| IDE Position | 24 |
| Nom Programme | Reçu annulation new |
| Fichier source | `Prg_24.xml` |
| Dossier IDE | Recu |
| Taches | 20 (0 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 1 |

## 2. DESCRIPTION FONCTIONNELLE

**Reçu annulation new** assure la gestion complete de ce processus, accessible depuis [ Annulation Ventes (IDE 40)](EXF-IDE-40.md).

Le flux de traitement s'organise en **2 blocs fonctionnels** :

- **Traitement** (15 taches) : traitements metier divers
- **Impression** (5 taches) : generation de tickets et documents

**Donnees modifiees** : 1 tables en ecriture (participants_____par).

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (15 taches)

- **24** - Veuillez patienter... **[[ECRAN]](#ecran-t1)**
- **24.1.1** - Impression
- **24.1.1.1** - Participants
- **24.1.2** - Impression
- **24.1.2.1** - Participants
- **24.2.1** - Impression
- **24.2.1.1** - Participants
- **24.2.2** - Impression
- **24.2.2.1** - Participants
- **24.3.1** - Impression
- **24.3.1.1** - Participants
- **24.4.1** - Impression
- **24.4.1.1** - Participants
- **24.5.1** - Impression
- **24.5.1.1** - Participants

#### Phase 2 : Impression (5 taches)

- **24.1** - Printer 1
- **24.2** - Printer 4
- **24.3** - Printer 6
- **24.4** - Printer 8
- **24.5** - Printer 9

Delegue a : [Raz Current Printer (IDE 20)](EXF-IDE-20.md)

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| participants_____par | **W** (7 usages) |  |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (15 taches)

Traitements internes.

---

#### <a id="t1"></a>24 - Veuillez patienter... [[ECRAN]](#ecran-t1)

**Role** : Tache d'orchestration : point d'entree du programme (15 sous-taches). Coordonne l'enchainement des traitements.
**Ecran** : 427 x 62 DLU (MDI) | [Voir mockup](#ecran-t1)

<details>
<summary>14 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [24.1.1](#t4) | Impression | Traitement |
| [24.1.1.1](#t5) | Participants | Traitement |
| [24.1.2](#t6) | Impression | Traitement |
| [24.1.2.1](#t7) | Participants | Traitement |
| [24.2.1](#t9) | Impression | Traitement |
| [24.2.1.1](#t10) | Participants | Traitement |
| [24.2.2](#t11) | Impression | Traitement |
| [24.2.2.1](#t12) | Participants | Traitement |
| [24.3.1](#t14) | Impression | Traitement |
| [24.3.1.1](#t15) | Participants | Traitement |
| [24.4.1](#t17) | Impression | Traitement |
| [24.4.1.1](#t18) | Participants | Traitement |
| [24.5.1](#t20) | Impression | Traitement |
| [24.5.1.1](#t21) | Participants | Traitement |

</details>

---

#### <a id="t4"></a>24.1.1 - Impression

**Role** : Generation du document : Impression.

---

#### <a id="t5"></a>24.1.1.1 - Participants

**Role** : Traitement : Participants.

---

#### <a id="t6"></a>24.1.2 - Impression

**Role** : Generation du document : Impression.

---

#### <a id="t7"></a>24.1.2.1 - Participants

**Role** : Traitement : Participants.

---

#### <a id="t9"></a>24.2.1 - Impression

**Role** : Generation du document : Impression.

---

#### <a id="t10"></a>24.2.1.1 - Participants

**Role** : Traitement : Participants.

---

#### <a id="t11"></a>24.2.2 - Impression

**Role** : Generation du document : Impression.

---

#### <a id="t12"></a>24.2.2.1 - Participants

**Role** : Traitement : Participants.

---

#### <a id="t14"></a>24.3.1 - Impression

**Role** : Generation du document : Impression.

---

#### <a id="t15"></a>24.3.1.1 - Participants

**Role** : Traitement : Participants.

---

#### <a id="t17"></a>24.4.1 - Impression

**Role** : Generation du document : Impression.

---

#### <a id="t18"></a>24.4.1.1 - Participants

**Role** : Traitement : Participants.

---

#### <a id="t20"></a>24.5.1 - Impression

**Role** : Generation du document : Impression.

---

#### <a id="t21"></a>24.5.1.1 - Participants

**Role** : Traitement : Participants.


### 3.2 Impression (5 taches)

Generation des documents et tickets.

---

#### <a id="t3"></a>24.1 - Printer 1

**Role** : Generation du document : Printer 1.
**Delegue a** : [Raz Current Printer (IDE 20)](EXF-IDE-20.md)

---

#### <a id="t8"></a>24.2 - Printer 4

**Role** : Generation du document : Printer 4.
**Delegue a** : [Raz Current Printer (IDE 20)](EXF-IDE-20.md)

---

#### <a id="t13"></a>24.3 - Printer 6

**Role** : Generation du document : Printer 6.
**Delegue a** : [Raz Current Printer (IDE 20)](EXF-IDE-20.md)

---

#### <a id="t16"></a>24.4 - Printer 8

**Role** : Generation du document : Printer 8.
**Delegue a** : [Raz Current Printer (IDE 20)](EXF-IDE-20.md)

---

#### <a id="t19"></a>24.5 - Printer 9

**Role** : Generation du document : Printer 9.
**Delegue a** : [Raz Current Printer (IDE 20)](EXF-IDE-20.md)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [ Annulation Ventes (IDE 40)](EXF-IDE-40.md)
- **Appelle**: 1 programmes | **Tables**: 6 (W:1 R:2 L:4) | **Taches**: 20 | **Expressions**: 10

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (20 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **24.1** | [**Veuillez patienter...** (24)](#t1) [mockup](#ecran-t1) | MDI | 427x62 | Traitement |
| 24.1.1 | [Impression (24.1.1)](#t4) | MDI | - | |
| 24.1.2 | [Participants (24.1.1.1)](#t5) | MDI | - | |
| 24.1.3 | [Impression (24.1.2)](#t6) | MDI | - | |
| 24.1.4 | [Participants (24.1.2.1)](#t7) | MDI | - | |
| 24.1.5 | [Impression (24.2.1)](#t9) | MDI | - | |
| 24.1.6 | [Participants (24.2.1.1)](#t10) | MDI | - | |
| 24.1.7 | [Impression (24.2.2)](#t11) | MDI | - | |
| 24.1.8 | [Participants (24.2.2.1)](#t12) | MDI | - | |
| 24.1.9 | [Impression (24.3.1)](#t14) | MDI | - | |
| 24.1.10 | [Participants (24.3.1.1)](#t15) | MDI | - | |
| 24.1.11 | [Impression (24.4.1)](#t17) | MDI | - | |
| 24.1.12 | [Participants (24.4.1.1)](#t18) | MDI | - | |
| 24.1.13 | [Impression (24.5.1)](#t20) | MDI | - | |
| 24.1.14 | [Participants (24.5.1.1)](#t21) | MDI | - | |
| **24.2** | [**Printer 1** (24.1)](#t3) | MDI | - | Impression |
| 24.2.1 | [Printer 4 (24.2)](#t8) | MDI | - | |
| 24.2.2 | [Printer 6 (24.3)](#t13) | MDI | - | |
| 24.2.3 | [Printer 8 (24.4)](#t16) | MDI | - | |
| 24.2.4 | [Printer 9 (24.5)](#t19) | MDI | - | |

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

### Tables utilisees (6)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 30 | gm-recherche_____gmr | Index de recherche | DB | R |   |   | 2 |
| 277 | vendeur |  | DB |   |   | L | 7 |
| 298 | participants_____par |  | DB |   | **W** |   | 7 |
| 300 | excursions_______exc |  | DB |   |   | L | 7 |
| 302 | parametre_voutchers |  | DB |   |   | L | 7 |
| 309 | vente____________vep | Donnees de ventes | DB | R |   | L | 7 |

### Colonnes par table (1 / 3 tables avec colonnes identifiees)

<details>
<summary>Table 30 - gm-recherche_____gmr (R) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 298 - participants_____par (**W**) - 7 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 309 - vente____________vep (R/L) - 7 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| C | P0 numero vente | R | Numeric |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (4)

Variables recues du programme appelant ([ Annulation Ventes (IDE 40)](EXF-IDE-40.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P0 nom village | Alpha | - |
| B | P0 masque montant | Alpha | - |
| C | P0 numero vente | Numeric | - |
| D | P0 frais annulation | Numeric | - |

## 12. EXPRESSIONS

**10 / 10 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| OTHER | 3 | 0 |
| CONDITION | 6 | 0 |
| CAST_LOGIQUE | 1 | 0 |

### 12.2 Expressions cles par type

#### OTHER (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 10 | `SetParam ('CURRENTPAGENUMBER',0)` | - |
| OTHER | 2 | `SetCrsr (1)` | - |
| OTHER | 1 | `SetCrsr (2)` | - |

#### CONDITION (6 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 6 | `GetParam ('CURRENTPRINTERNUM')=8` | - |
| CONDITION | 7 | `GetParam ('CURRENTPRINTERNUM')=9` | - |
| CONDITION | 9 | `Counter (0)>=GetParam ('NUMBERCOPIES')` | - |
| CONDITION | 3 | `GetParam ('CURRENTPRINTERNUM')=1` | - |
| CONDITION | 4 | `GetParam ('CURRENTPRINTERNUM')=4` | - |
| ... | | *+1 autres* | |

#### CAST_LOGIQUE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 8 | `'TRUE'LOG` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [ Annulation Ventes (IDE 40)](EXF-IDE-40.md) -> **Reçu annulation new (IDE 24)**

```mermaid
graph LR
    T24[24 Reçu annulation new]
    style T24 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC13[13 Menu ventes]
    style CC13 fill:#f59e0b
    CC40[40 Annulation Ventes]
    style CC40 fill:#3fb950
    CC13 --> CC40
    CC1 --> CC13
    CC40 --> T24
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [40](EXF-IDE-40.md) |  Annulation Ventes | 3 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T24[24 Reçu annulation new]
    style T24 fill:#58a6ff
    C20[20 Raz Current Printer]
    T24 --> C20
    style C20 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [20](EXF-IDE-20.md) | Raz Current Printer | 1 | Impression ticket/document |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 438 | Taille moyenne |
| Expressions | 10 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 1 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 438) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (15 taches: 1 ecran, 14 traitements)

- **Strategie** : Orchestrateur avec 1 ecrans (Razor/React) et 14 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 1 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Impression (5 taches: 0 ecran, 5 traitements)

- **Strategie** : Templates HTML -> PDF via wkhtmltopdf ou Puppeteer.
- `PrintService` injectable avec choix imprimante

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| participants_____par | Table WRITE (Database) | 7x | Schema + repository |
| [Raz Current Printer (IDE 20)](EXF-IDE-20.md) | Sous-programme | 1x | Normale - Impression ticket/document |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 11:01*
