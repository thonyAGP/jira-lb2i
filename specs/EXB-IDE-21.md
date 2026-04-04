# EXB IDE 21 - Imp reçu duplicata

> **Analyse**: Phases 1-4 2026-02-03 10:38 -> 10:38 (16s) | Assemblage 10:38
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | EXB |
| IDE Position | 21 |
| Nom Programme | Imp reçu duplicata |
| Fichier source | `Prg_21.xml` |
| Domaine metier | General |
| Taches | 6 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Imp reçu duplicata** assure la gestion complete de ce processus, accessible depuis [Liste ventes/N°vente (IDE 20)](EXB-IDE-20.md).

Le flux de traitement s'organise en **2 blocs fonctionnels** :

- **Traitement** (5 taches) : traitements metier divers
- **Impression** (1 tache) : generation de tickets et documents

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (5 taches)

- **21** - Veuillez patienter... **[[ECRAN]](#ecran-t1)**
- **21.2** - Impression
- **21.2.1** - Participants
- **21.3** - Impression
- **21.3.1** - Participants

#### Phase 2 : Impression (1 tache)

- **21.1** - Choix imprimante

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (5 taches)

Traitements internes.

---

#### <a id="t1"></a>21 - Veuillez patienter... [[ECRAN]](#ecran-t1)

**Role** : Traitement : Veuillez patienter....
**Ecran** : 430 x 60 DLU (MDI) | [Voir mockup](#ecran-t1)

<details>
<summary>4 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [21.2](#t3) | Impression | Traitement |
| [21.2.1](#t4) | Participants | Traitement |
| [21.3](#t5) | Impression | Traitement |
| [21.3.1](#t6) | Participants | Traitement |

</details>

---

#### <a id="t3"></a>21.2 - Impression

**Role** : Generation du document : Impression.

---

#### <a id="t4"></a>21.2.1 - Participants

**Role** : Traitement : Participants.

---

#### <a id="t5"></a>21.3 - Impression

**Role** : Generation du document : Impression.

---

#### <a id="t6"></a>21.3.1 - Participants

**Role** : Traitement : Participants.


### 3.2 Impression (1 tache)

Generation des documents et tickets.

---

#### <a id="t2"></a>21.1 - Choix imprimante

**Role** : Selection par l'operateur : Choix imprimante.
**Variables liees** : D (W0 choix imprimante)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Liste ventes/N°vente (IDE 20)](EXB-IDE-20.md)
- **Appelle**: 0 programmes | **Tables**: 5 (W:0 R:3 L:2) | **Taches**: 6 | **Expressions**: 9

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (6 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **21.1** | [**Veuillez patienter...** (21)](#t1) [mockup](#ecran-t1) | MDI | 430x60 | Traitement |
| 21.1.1 | [Impression (21.2)](#t3) | MDI | - | |
| 21.1.2 | [Participants (21.2.1)](#t4) | MDI | - | |
| 21.1.3 | [Impression (21.3)](#t5) | MDI | - | |
| 21.1.4 | [Participants (21.3.1)](#t6) | MDI | - | |
| **21.2** | [**Choix imprimante** (21.1)](#t2) | MDI | - | Impression |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Traitement principal]
    ENDOK([END OK])

    START --> INIT --> SAISIE
    SAISIE --> ENDOK

    style START fill:#3fb950,color:#000
    style ENDOK fill:#3fb950,color:#000
```

> **Legende**: Vert = START/END OK | Rouge = END KO | Bleu = Decisions
> *Algorigramme auto-genere. Utiliser `/algorigramme` pour une synthese metier detaillee.*

<!-- TAB:Donnees -->

## 10. TABLES

### Tables utilisees (5)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 24 | imprimante_______prn |  | DB | R |   |   | 1 |
| 298 | participants_____par |  | DB | R |   |   | 2 |
| 300 | excursions_______exc |  | DB |   |   | L | 2 |
| 302 | parametre_voutchers |  | DB |   |   | L | 2 |
| 309 | vente____________vep | Donnees de ventes | DB | R |   |   | 2 |

### Colonnes par table (2 / 3 tables avec colonnes identifiees)

<details>
<summary>Table 24 - imprimante_______prn (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| D | W0 choix imprimante | R | Numeric |

</details>

<details>
<summary>Table 298 - participants_____par (R) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 309 - vente____________vep (R) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| C | P0 numero vente | R | Numeric |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (3)

Variables recues du programme appelant ([Liste ventes/N°vente (IDE 20)](EXB-IDE-20.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P0 nom village | Alpha | - |
| B | P0 masque montant | Alpha | - |
| C | P0 numero vente | Numeric | - |

### 11.2 Variables de travail (1)

Variables internes au programme.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| D | W0 choix imprimante | Numeric | [21.1](#t2) |

## 12. EXPRESSIONS

**9 / 9 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONSTANTE | 2 | 0 |
| CONDITION | 2 | 0 |
| OTHER | 2 | 0 |
| NEGATION | 1 | 0 |
| REFERENCE_VG | 1 | 0 |
| CAST_LOGIQUE | 1 | 0 |

### 12.2 Expressions cles par type

#### CONSTANTE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 8 | `612` | - |
| CONSTANTE | 7 | `'EXB'` | - |

#### CONDITION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 2 | `W0 choix imprimante [D]>4` | - |
| CONDITION | 1 | `W0 choix imprimante [D]<5` | - |

#### OTHER (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 4 | `SetCrsr (1)` | - |
| OTHER | 3 | `SetCrsr (2)` | - |

#### NEGATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| NEGATION | 5 | `NOT VG5` | - |

#### REFERENCE_VG (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 6 | `VG5` | - |

#### CAST_LOGIQUE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 9 | `'TRUE'LOG` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Liste ventes/N°vente (IDE 20)](EXB-IDE-20.md) -> **Imp reçu duplicata (IDE 21)**

```mermaid
graph LR
    T21[21 Imp reçu duplicata]
    style T21 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC31[31 Menu general]
    style CC31 fill:#f59e0b
    CC19[19 Menu editions]
    style CC19 fill:#f59e0b
    CC20[20 Liste ventesN°vente]
    style CC20 fill:#3fb950
    CC19 --> CC20
    CC31 --> CC19
    CC1 --> CC31
    CC20 --> T21
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [20](EXB-IDE-20.md) | Liste ventes/N°vente | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T21[21 Imp reçu duplicata]
    style T21 fill:#58a6ff
    NONE[Aucun callee]
    T21 -.-> NONE
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
| Lignes de logique | 113 | Programme compact |
| Expressions | 9 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 113) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (5 taches: 1 ecran, 4 traitements)

- **Strategie** : Orchestrateur avec 1 ecrans (Razor/React) et 4 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- Decomposer les taches en services unitaires testables.

#### Impression (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Templates HTML -> PDF via wkhtmltopdf ou Puppeteer.
- `PrintService` injectable avec choix imprimante

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 10:38*
