# PTR IDE 24 - .....Impression TK

> **Analyse**: Phases 1-4 2026-02-03 18:16 -> 18:16 (15s) | Assemblage 18:16
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PTR |
| IDE Position | 24 |
| Nom Programme | .....Impression TK |
| Fichier source | `Prg_24.xml` |
| Dossier IDE | Listes |
| Taches | 4 (1 ecrans visibles) |
| Tables modifiees | 2 |
| Programmes appeles | 1 |

## 2. DESCRIPTION FONCTIONNELLE

**.....Impression TK** assure la gestion complete de ce processus, accessible depuis [...Consultation Tempo Ecran TK (IDE 23)](PTR-IDE-23.md).

Le flux de traitement s'organise en **2 blocs fonctionnels** :

- **Traitement** (3 taches) : traitements metier divers
- **Initialisation** (1 tache) : reinitialisation d'etats et de variables de travail

**Donnees modifiees** : 2 tables en ecriture (activite_plan_comptable_tempo, libelle_ecart_reference).

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (3 taches)

- **24** - .....Impression TK **[[ECRAN]](#ecran-t1)**
- **24.1** - Un instant SVP... **[[ECRAN]](#ecran-t2)**
- **24.1.1** - Lecture Totaux qualites

Delegue a : [LIST - Redirection d'un Etat (IDE 38)](PTR-IDE-38.md)

#### Phase 2 : Initialisation (1 tache)

- **24.2** - RAZ Tempo Qualites

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| activite_plan_comptable_tempo | **W**/L (3 usages) | Table temporaire ecran |
| libelle_ecart_reference | **W** (1 usages) |  |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (3 taches)

Traitements internes.

---

#### <a id="t1"></a>24 - .....Impression TK [[ECRAN]](#ecran-t1)

**Role** : Generation du document : .....Impression TK.
**Ecran** : 160 x 32 DLU (MDI) | [Voir mockup](#ecran-t1)
**Delegue a** : [LIST - Redirection d'un Etat (IDE 38)](PTR-IDE-38.md)

---

#### <a id="t2"></a>24.1 - Un instant SVP... [[ECRAN]](#ecran-t2)

**Role** : Traitement : Un instant SVP....
**Ecran** : 429 x 58 DLU (MDI) | [Voir mockup](#ecran-t2)
**Delegue a** : [LIST - Redirection d'un Etat (IDE 38)](PTR-IDE-38.md)

---

#### <a id="t3"></a>24.1.1 - Lecture Totaux qualites

**Role** : Calcul : Lecture Totaux qualites.
**Delegue a** : [LIST - Redirection d'un Etat (IDE 38)](PTR-IDE-38.md)


### 3.2 Initialisation (1 tache)

Reinitialisation d'etats et variables de travail.

---

#### <a id="t4"></a>24.2 - RAZ Tempo Qualites

**Role** : Reinitialisation : RAZ Tempo Qualites.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [...Consultation Tempo Ecran TK (IDE 23)](PTR-IDE-23.md)
- **Appelle**: 1 programmes | **Tables**: 3 (W:2 R:0 L:2) | **Taches**: 4 | **Expressions**: 3

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 4)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 24.1 | 24.1 | Un instant SVP... | MDI | 429 | 58 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t2"></a>24.1 - Un instant SVP...
**Tache** : [24.1](#t2) | **Type** : MDI | **Dimensions** : 429 x 58 DLU
**Bloc** : Traitement | **Titre IDE** : Un instant SVP...

<!-- FORM-DATA:
{
    "width":  429,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  12,
                         "type":  "label",
                         "var":  "",
                         "y":  4,
                         "w":  400,
                         "fmt":  "",
                         "name":  "",
                         "h":  48,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  161,
                         "type":  "label",
                         "var":  "",
                         "y":  18,
                         "w":  221,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "7",
                         "text":  "Impression en cours ...",
                         "parent":  1
                     },
                     {
                         "x":  226,
                         "type":  "edit",
                         "var":  "",
                         "y":  29,
                         "w":  37,
                         "fmt":  "",
                         "name":  "",
                         "h":  15,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  22,
                         "type":  "image",
                         "var":  "",
                         "y":  8,
                         "w":  106,
                         "fmt":  "",
                         "name":  "",
                         "h":  40,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "24.1",
    "height":  58
}
-->

<details>
<summary><strong>Champs : 1 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 226,29 | (sans nom) | - | edit |

</details>

## 9. NAVIGATION

Ecran unique: **Un instant SVP...**

### 9.3 Structure hierarchique (4 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **24.1** | [**.....Impression TK** (24)](#t1) [mockup](#ecran-t1) | MDI | 160x32 | Traitement |
| 24.1.1 | [Un instant SVP... (24.1)](#t2) [mockup](#ecran-t2) | MDI | 429x58 | |
| 24.1.2 | [Lecture Totaux qualites (24.1.1)](#t3) | MDI | - | |
| **24.2** | [**RAZ Tempo Qualites** (24.2)](#t4) | MDI | - | Initialisation |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[....Impression TK]
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

### Tables utilisees (3)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 132 | code_vol_________vot |  | DB |   |   | L | 1 |
| 468 | activite_plan_comptable_tempo | Table temporaire ecran | TMP |   | **W** | L | 3 |
| 686 | libelle_ecart_reference |  | DB |   | **W** |   | 1 |

### Colonnes par table (2 / 2 tables avec colonnes identifiees)

<details>
<summary>Table 468 - activite_plan_comptable_tempo (**W**/L) - 3 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | V_Qualite 1 | W | Alpha |
| B | V_Qualite 2 | W | Alpha |
| C | V_Qualite 3 | W | Alpha |
| D | V_Qualite 4 | W | Alpha |
| E | V_Qualite 5 | W | Alpha |
| F | V_Qualite 6 | W | Alpha |
| G | V_Qualite 7 | W | Alpha |
| H | V_Qualite 8 | W | Alpha |
| I | V_Qualite 9 | W | Alpha |
| J | V_Qualite 10 | W | Alpha |
| K | V_Qualite 11 | W | Alpha |
| L | V_Qualite 12 | W | Alpha |
| M | V_Qualite 13 | W | Alpha |
| N | V_Qualite 14 | W | Alpha |
| O | V_Qualite 15 | W | Alpha |
| P | V_Qte 1 | W | Numeric |
| Q | V_Qte 2 | W | Numeric |
| R | V_Qte 3 | W | Numeric |
| S | V_Qte 4 | W | Numeric |
| T | V_Qte 5 | W | Numeric |
| U | V_Qte 6 | W | Numeric |
| V | V_Qte 7 | W | Numeric |
| W | V_Qte 8 | W | Numeric |
| X | V_Qte 9 | W | Numeric |
| Y | V_Qte 10 | W | Numeric |
| Z | V_Qte 11 | W | Numeric |
| BA | V_Qte 12 | W | Numeric |
| BB | V_Qte 13 | W | Numeric |
| BC | V_Qte 14 | W | Numeric |
| BD | V_Qte 15 | W | Numeric |

</details>

<details>
<summary>Table 686 - libelle_ecart_reference (**W**) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P_Societe | W | Alpha |
| B | P_Liste Cpt | W | Alpha |
| C | P_Date | W | Date |
| D | P_Village | W | Alpha |
| E | P_Libelle Liste | W | Alpha |
| F | P_Liste | W | Alpha |
| G | P_Libelle Total selection | W | Alpha |
| H | P_Aperçu | W | Logical |
| I | P_Dialogue | W | Logical |
| J | W1-Boucle | W | Alpha |
| K | W1-Titre Edition | W | Alpha |
| L | W1-TOTAL SELECTION | W | Numeric |
| M | V_Libelle Rupture | W | Alpha |

</details>

## 11. VARIABLES

### 11.1 Autres (30)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P_Societe | Alpha | - |
| B | P_Liste Cpt | Alpha | - |
| C | P_Date | Date | - |
| D | P_Village | Alpha | - |
| E | P_Libelle Liste | Alpha | - |
| F | P_Liste | Alpha | - |
| G | P_Libelle Total Selection | Alpha | - |
| H | V_Aperçu | Logical | - |
| I | V_Dialogue | Logical | - |
| J | V_Impression | Logical | 1x refs |
| K | W1-Titre Edition | Alpha | - |
| L | W1-TOTAL SELECTION | Numeric | - |
| M | V_Libelle Rupture | Alpha | - |
| N | V_Qualite 14 | Alpha | - |
| O | V_Qualite 15 | Alpha | - |
| P | V_Qte 1 | Numeric | - |
| Q | V_Qte 2 | Numeric | - |
| R | V_Qte 3 | Numeric | - |
| S | V_Qte 4 | Numeric | - |
| T | V_Qte 5 | Numeric | - |
| U | V_Qte 6 | Numeric | - |
| V | V_Qte 7 | Numeric | - |
| W | V_Qte 8 | Numeric | - |
| X | V_Qte 9 | Numeric | - |
| Y | V_Qte 10 | Numeric | - |
| Z | V_Qte 11 | Numeric | - |
| BA | V_Qte 12 | Numeric | - |
| BB | V_Qte 13 | Numeric | - |
| BC | V_Qte 14 | Numeric | - |
| BD | V_Qte 15 | Numeric | - |

<details>
<summary>Toutes les 30 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| Autre | **A** | P_Societe | Alpha |
| Autre | **B** | P_Liste Cpt | Alpha |
| Autre | **C** | P_Date | Date |
| Autre | **D** | P_Village | Alpha |
| Autre | **E** | P_Libelle Liste | Alpha |
| Autre | **F** | P_Liste | Alpha |
| Autre | **G** | P_Libelle Total Selection | Alpha |
| Autre | **H** | V_Aperçu | Logical |
| Autre | **I** | V_Dialogue | Logical |
| Autre | **J** | V_Impression | Logical |
| Autre | **K** | W1-Titre Edition | Alpha |
| Autre | **L** | W1-TOTAL SELECTION | Numeric |
| Autre | **M** | V_Libelle Rupture | Alpha |
| Autre | **N** | V_Qualite 14 | Alpha |
| Autre | **O** | V_Qualite 15 | Alpha |
| Autre | **P** | V_Qte 1 | Numeric |
| Autre | **Q** | V_Qte 2 | Numeric |
| Autre | **R** | V_Qte 3 | Numeric |
| Autre | **S** | V_Qte 4 | Numeric |
| Autre | **T** | V_Qte 5 | Numeric |
| Autre | **U** | V_Qte 6 | Numeric |
| Autre | **V** | V_Qte 7 | Numeric |
| Autre | **W** | V_Qte 8 | Numeric |
| Autre | **X** | V_Qte 9 | Numeric |
| Autre | **Y** | V_Qte 10 | Numeric |
| Autre | **Z** | V_Qte 11 | Numeric |
| Autre | **BA** | V_Qte 12 | Numeric |
| Autre | **BB** | V_Qte 13 | Numeric |
| Autre | **BC** | V_Qte 14 | Numeric |
| Autre | **BD** | V_Qte 15 | Numeric |

</details>

## 12. EXPRESSIONS

**3 / 3 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| OTHER | 3 | 0 |

### 12.2 Expressions cles par type

#### OTHER (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 3 | `V_Impression [J]` | - |
| OTHER | 2 | `SetCrsr (2)` | - |
| OTHER | 1 | `SetCrsr (1)` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [...Consultation Tempo Ecran TK (IDE 23)](PTR-IDE-23.md) -> **.....Impression TK (IDE 24)**

```mermaid
graph LR
    T24[24 .....Impression TK]
    style T24 fill:#58a6ff
    CC14[14 Clients arrivants]
    style CC14 fill:#8b5cf6
    CC15[15 Clients depart]
    style CC15 fill:#8b5cf6
    CC16[16 Clients incompatibi...]
    style CC16 fill:#8b5cf6
    CC17[17 ..Liste Clients Cli...]
    style CC17 fill:#f59e0b
    CC20[20 ...Lance Consultati...]
    style CC20 fill:#f59e0b
    CC23[23 ...Consultation Tem...]
    style CC23 fill:#3fb950
    CC20 --> CC23
    CC17 --> CC20
    CC14 --> CC17
    CC15 --> CC17
    CC16 --> CC17
    CC23 --> T24
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [23](PTR-IDE-23.md) | ...Consultation Tempo Ecran TK | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T24[24 .....Impression TK]
    style T24 fill:#58a6ff
    C38[38 LIST - Redirection ...]
    T24 --> C38
    style C38 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [38](PTR-IDE-38.md) | LIST - Redirection d'un Etat | 1 | Configuration impression |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 246 | Taille moyenne |
| Expressions | 3 | Peu de logique |
| Tables WRITE | 2 | Impact faible |
| Sous-programmes | 1 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 246) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (3 taches: 2 ecrans, 1 traitement)

- **Strategie** : Orchestrateur avec 2 ecrans (Razor/React) et 1 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 1 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Initialisation (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Constructeur/methode `InitAsync()` dans l'orchestrateur.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| activite_plan_comptable_tempo | Table WRITE (Temp) | 2x | Schema + repository |
| libelle_ecart_reference | Table WRITE (Database) | 1x | Schema + repository |
| [LIST - Redirection d'un Etat (IDE 38)](PTR-IDE-38.md) | Sous-programme | 1x | Normale - Configuration impression |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 18:16*
