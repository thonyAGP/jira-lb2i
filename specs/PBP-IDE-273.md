# PBP IDE 273 - Traitement Mecano 2

> **Analyse**: Phases 1-4 2026-02-03 16:06 -> 16:06 (18s) | Assemblage 16:06
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBP |
| IDE Position | 273 |
| Nom Programme | Traitement Mecano 2 |
| Fichier source | `Prg_273.xml` |
| Dossier IDE | Mecano |
| Taches | 9 (1 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Traitement Mecano 2** assure la gestion complete de ce processus, accessible depuis [Preparation Mecano (IDE 269)](PBP-IDE-269.md).

Le flux de traitement s'organise en **2 blocs fonctionnels** :

- **Traitement** (8 taches) : traitements metier divers
- **Calcul** (1 tache) : calculs de montants, stocks ou compteurs

**Donnees modifiees** : 1 tables en ecriture (tempo_facturation).

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (8 taches)

- **273** - Veuillez patienter ... **[[ECRAN]](#ecran-t1)**
- **273.1** - Traitement Mecano
- **273.1.1** - Traitement Accompagnant
- **273.1.1.1** - Modification Accompagnant
- **273.1.1.2** - Effacage Accompagnant
- **273.1.1.3** - Modification Accompagne
- **273.1.1.4** - Effacage Accompagnant
- **273.1.2** - Retraitement Accompagnant

#### Phase 2 : Calcul (1 tache)

- **273.2** - Comptage Mecano

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| tempo_facturation | R/**W** (8 usages) | Table temporaire ecran |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (8 taches)

Traitements internes.

---

#### <a id="t1"></a>273 - Veuillez patienter ... [[ECRAN]](#ecran-t1)

**Role** : Tache d'orchestration : point d'entree du programme (8 sous-taches). Coordonne l'enchainement des traitements.
**Ecran** : 427 x 57 DLU (MDI) | [Voir mockup](#ecran-t1)

<details>
<summary>7 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [273.1](#t2) | Traitement Mecano | Traitement |
| [273.1.1](#t3) | Traitement Accompagnant | Traitement |
| [273.1.1.1](#t4) | Modification Accompagnant | Traitement |
| [273.1.1.2](#t5) | Effacage Accompagnant | Traitement |
| [273.1.1.3](#t6) | Modification Accompagne | Traitement |
| [273.1.1.4](#t7) | Effacage Accompagnant | Traitement |
| [273.1.2](#t8) | Retraitement Accompagnant | Traitement |

</details>

---

#### <a id="t2"></a>273.1 - Traitement Mecano

**Role** : Traitement : Traitement Mecano.
**Variables liees** : B (P0-Traitement 2)

---

#### <a id="t3"></a>273.1.1 - Traitement Accompagnant

**Role** : Traitement : Traitement Accompagnant.
**Variables liees** : B (P0-Traitement 2)

---

#### <a id="t4"></a>273.1.1.1 - Modification Accompagnant

**Role** : Traitement : Modification Accompagnant.

---

#### <a id="t5"></a>273.1.1.2 - Effacage Accompagnant

**Role** : Traitement : Effacage Accompagnant.

---

#### <a id="t6"></a>273.1.1.3 - Modification Accompagne

**Role** : Traitement : Modification Accompagne.

---

#### <a id="t7"></a>273.1.1.4 - Effacage Accompagnant

**Role** : Traitement : Effacage Accompagnant.

---

#### <a id="t8"></a>273.1.2 - Retraitement Accompagnant

**Role** : Traitement : Retraitement Accompagnant.


### 3.2 Calcul (1 tache)

Calculs metier : montants, stocks, compteurs.

---

#### <a id="t9"></a>273.2 - Comptage Mecano

**Role** : Traitement : Comptage Mecano.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Preparation Mecano (IDE 269)](PBP-IDE-269.md)
- **Appelle**: 0 programmes | **Tables**: 1 (W:1 R:1 L:0) | **Taches**: 9 | **Expressions**: 3

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 9)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 273 | 273 | Veuillez patienter ... | MDI | 427 | 57 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>273 - Veuillez patienter ...
**Tache** : [273](#t1) | **Type** : MDI | **Dimensions** : 427 x 57 DLU
**Bloc** : Traitement | **Titre IDE** : Veuillez patienter ...

<!-- FORM-DATA:
{
    "width":  427,
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
                         "x":  120,
                         "type":  "label",
                         "var":  "",
                         "y":  10,
                         "w":  221,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "7",
                         "text":  "Traitement en cours ...",
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
                         "x":  72,
                         "type":  "label",
                         "var":  "",
                         "y":  38,
                         "w":  280,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Liste mecanographique 2",
                         "parent":  null
                     },
                     {
                         "x":  4,
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
    "taskId":  "273",
    "height":  57
}
-->

## 9. NAVIGATION

Ecran unique: **Veuillez patienter ...**

### 9.3 Structure hierarchique (9 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **273.1** | [**Veuillez patienter ...** (273)](#t1) [mockup](#ecran-t1) | MDI | 427x57 | Traitement |
| 273.1.1 | [Traitement Mecano (273.1)](#t2) | MDI | - | |
| 273.1.2 | [Traitement Accompagnant (273.1.1)](#t3) | MDI | - | |
| 273.1.3 | [Modification Accompagnant (273.1.1.1)](#t4) | MDI | - | |
| 273.1.4 | [Effacage Accompagnant (273.1.1.2)](#t5) | MDI | - | |
| 273.1.5 | [Modification Accompagne (273.1.1.3)](#t6) | MDI | - | |
| 273.1.6 | [Effacage Accompagnant (273.1.1.4)](#t7) | MDI | - | |
| 273.1.7 | [Retraitement Accompagnant (273.1.2)](#t8) | MDI | - | |
| **273.2** | [**Comptage Mecano** (273.2)](#t9) | MDI | - | Calcul |

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

### Tables utilisees (1)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 623 | tempo_facturation | Table temporaire ecran | TMP | R | **W** |   | 8 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 623 - tempo_facturation (R/**W**) - 8 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | W2-Fin de Tache | W | Alpha |
| B | W2-Code Retour | W | Numeric |

</details>

## 11. VARIABLES

### 11.1 Autres (5)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P0-Passe | Numeric | - |
| B | P0-Traitement 2 | Numeric | - |
| C | W0-Fin de Tache | Alpha | - |
| D | W0-Controle Avant | Numeric | 1x refs |
| E | W0-Controle Apres | Numeric | 2x refs |

## 12. EXPRESSIONS

**3 / 3 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONSTANTE | 1 | 0 |
| CONDITION | 1 | 0 |
| OTHER | 1 | 0 |

### 12.2 Expressions cles par type

#### CONSTANTE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 1 | `'F'` | - |

#### CONDITION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 2 | `W0-Controle Avant [D]=W0-Controle Apres [E]` | - |

#### OTHER (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 3 | `W0-Controle Apres [E]` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Preparation Mecano (IDE 269)](PBP-IDE-269.md) -> **Traitement Mecano 2 (IDE 273)**

```mermaid
graph LR
    T273[273 Traitement Mecano 2]
    style T273 fill:#58a6ff
    CC108[108 Edition Forfait Ski]
    style CC108 fill:#8b5cf6
    CC127[127 Liste Mecanographique]
    style CC127 fill:#f59e0b
    CC114[114 Liste Mec benef fo...]
    style CC114 fill:#f59e0b
    CC269[269 Preparation Mecano]
    style CC269 fill:#3fb950
    CC114 --> CC269
    CC127 --> CC269
    CC108 --> CC114
    CC108 --> CC127
    CC269 --> T273
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [269](PBP-IDE-269.md) | Preparation Mecano | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T273[273 Traitement Mecano 2]
    style T273 fill:#58a6ff
    NONE[Aucun callee]
    T273 -.-> NONE
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
| Lignes de logique | 117 | Programme compact |
| Expressions | 3 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 117) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (8 taches: 1 ecran, 7 traitements)

- **Strategie** : Orchestrateur avec 1 ecrans (Razor/React) et 7 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- Decomposer les taches en services unitaires testables.

#### Calcul (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Services de calcul purs (Domain Services).
- Migrer la logique de calcul (stock, compteurs, montants)

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| tempo_facturation | Table WRITE (Temp) | 7x | Schema + repository |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 16:06*
