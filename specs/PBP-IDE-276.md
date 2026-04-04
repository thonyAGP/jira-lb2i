# PBP IDE 276 - Regroupement Accompagnant

> **Analyse**: Phases 1-4 2026-02-03 16:07 -> 16:07 (17s) | Assemblage 16:07
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBP |
| IDE Position | 276 |
| Nom Programme | Regroupement Accompagnant |
| Fichier source | `Prg_276.xml` |
| Dossier IDE | Mecano |
| Taches | 4 (1 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Regroupement Accompagnant** assure la gestion complete de ce processus, accessible depuis [Groupage Mecano (IDE 275)](PBP-IDE-275.md).

Le flux de traitement s'organise en **2 blocs fonctionnels** :

- **Traitement** (3 taches) : traitements metier divers
- **Creation** (1 tache) : insertion d'enregistrements en base (mouvements, prestations)

**Donnees modifiees** : 1 tables en ecriture (tempo_livre_de_porte_bresil).

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (3 taches)

- **276** - Veuillez patienter ... **[[ECRAN]](#ecran-t1)**
- **276.1** - Groupage Adherent
- **276.1.2** - Groupage Adherent

#### Phase 2 : Creation (1 tache)

- **276.1.1** - Creation Sous-Groupage **[[ECRAN]](#ecran-t3)**

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| tempo_livre_de_porte_bresil | **W**/L (2 usages) | Table temporaire ecran |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (3 taches)

Traitements internes.

---

#### <a id="t1"></a>276 - Veuillez patienter ... [[ECRAN]](#ecran-t1)

**Role** : Traitement : Veuillez patienter ....
**Ecran** : 427 x 58 DLU (MDI) | [Voir mockup](#ecran-t1)

---

#### <a id="t2"></a>276.1 - Groupage Adherent

**Role** : Traitement : Groupage Adherent.
**Variables liees** : B (W1-Sous-Groupe adherent)

---

#### <a id="t4"></a>276.1.2 - Groupage Adherent

**Role** : Traitement : Groupage Adherent.
**Variables liees** : B (W1-Sous-Groupe adherent)


### 3.2 Creation (1 tache)

Insertion de nouveaux enregistrements en base.

---

#### <a id="t3"></a>276.1.1 - Creation Sous-Groupage [[ECRAN]](#ecran-t3)

**Role** : Creation d'enregistrement : Creation Sous-Groupage.
**Ecran** : 248 x 206 DLU (MDI) | [Voir mockup](#ecran-t3)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Groupage Mecano (IDE 275)](PBP-IDE-275.md)
- **Appelle**: 0 programmes | **Tables**: 3 (W:1 R:1 L:2) | **Taches**: 4 | **Expressions**: 1

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 4)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 276 | 276 | Veuillez patienter ... | MDI | 427 | 58 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>276 - Veuillez patienter ...
**Tache** : [276](#t1) | **Type** : MDI | **Dimensions** : 427 x 58 DLU
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
                         "x":  69,
                         "type":  "label",
                         "var":  "",
                         "y":  38,
                         "w":  286,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Groupement accompagnants",
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
    "taskId":  "276",
    "height":  58
}
-->

## 9. NAVIGATION

Ecran unique: **Veuillez patienter ...**

### 9.3 Structure hierarchique (4 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **276.1** | [**Veuillez patienter ...** (276)](#t1) [mockup](#ecran-t1) | MDI | 427x58 | Traitement |
| 276.1.1 | [Groupage Adherent (276.1)](#t2) | MDI | - | |
| 276.1.2 | [Groupage Adherent (276.1.2)](#t4) | MDI | - | |
| **276.2** | [**Creation Sous-Groupage** (276.1.1)](#t3) [mockup](#ecran-t3) | MDI | 248x206 | Creation |

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

### Tables utilisees (3)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 622 | tempo_zone_secteur | Table temporaire ecran | TMP | R |   |   | 2 |
| 623 | tempo_facturation | Table temporaire ecran | TMP |   |   | L | 1 |
| 624 | tempo_livre_de_porte_bresil | Table temporaire ecran | TMP |   | **W** | L | 2 |

### Colonnes par table (1 / 2 tables avec colonnes identifiees)

<details>
<summary>Table 622 - tempo_zone_secteur (R) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | W1-N°Groupe adherent | R | Numeric |
| B | W1-Sous-Groupe adherent | R | Numeric |
| C | W1-N°Groupe accompagnant | R | Numeric |
| D | W1-Sous-Groupe accompagnat | R | Numeric |

</details>

<details>
<summary>Table 624 - tempo_livre_de_porte_bresil (**W**/L) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Autres (4)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | W0-Fin de Tache | Alpha | - |
| B | W1-Sous-Groupe adherent | Numeric | - |
| C | W1-N°Groupe accompagnant | Numeric | - |
| D | W1-Sous-Groupe accompagnat | Numeric | - |

## 12. EXPRESSIONS

**1 / 1 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONSTANTE | 1 | 0 |

### 12.2 Expressions cles par type

#### CONSTANTE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 1 | `'F'` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Groupage Mecano (IDE 275)](PBP-IDE-275.md) -> **Regroupement Accompagnant (IDE 276)**

```mermaid
graph LR
    T276[276 Regroupement Accom...]
    style T276 fill:#58a6ff
    CC108[108 Edition Forfait Ski]
    style CC108 fill:#8b5cf6
    CC127[127 Liste Mecanographique]
    style CC127 fill:#f59e0b
    CC114[114 Liste Mec benef fo...]
    style CC114 fill:#f59e0b
    CC269[269 Preparation Mecano]
    style CC269 fill:#f59e0b
    CC275[275 Groupage Mecano]
    style CC275 fill:#3fb950
    CC269 --> CC275
    CC114 --> CC269
    CC127 --> CC269
    CC108 --> CC114
    CC108 --> CC127
    CC275 --> T276
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [275](PBP-IDE-275.md) | Groupage Mecano | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T276[276 Regroupement Accom...]
    style T276 fill:#58a6ff
    NONE[Aucun callee]
    T276 -.-> NONE
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
| Lignes de logique | 64 | Programme compact |
| Expressions | 1 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 64) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (3 taches: 1 ecran, 2 traitements)

- **Strategie** : Orchestrateur avec 1 ecrans (Razor/React) et 2 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- Decomposer les taches en services unitaires testables.

#### Creation (1 tache: 1 ecran, 0 traitement)

- **Strategie** : Repository pattern avec Entity Framework Core.
- Insertion via `IRepository<T>.CreateAsync()`

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| tempo_livre_de_porte_bresil | Table WRITE (Temp) | 1x | Schema + repository |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 16:07*
