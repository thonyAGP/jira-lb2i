# WEL IDE 14 - Circuits

> **Analyse**: Phases 1-4 2026-02-03 21:15 -> 21:15 (18s) | Assemblage 21:15
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | WEL |
| IDE Position | 14 |
| Nom Programme | Circuits |
| Fichier source | `Prg_14.xml` |
| Dossier IDE | Clients |
| Taches | 1 (1 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 1 |
| :warning: Statut | **ORPHELIN_POTENTIEL** |

## 2. DESCRIPTION FONCTIONNELLE

**Circuits** assure la gestion complete de ce processus.

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>14 - Circuits [[ECRAN]](#ecran-t1)

**Role** : Traitement : Circuits.
**Ecran** : 1313 x 744 DLU | [Voir mockup](#ecran-t1)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: (aucun)
- **Appelle**: 1 programmes | **Tables**: 2 (W:0 R:1 L:1) | **Taches**: 1 | **Expressions**: 11

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 1)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 14 | 14 | Circuits | Type0 | 1313 | 744 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>14 - Circuits
**Tache** : [14](#t1) | **Type** : Type0 | **Dimensions** : 1313 x 744 DLU
**Bloc** : Traitement | **Titre IDE** : Circuits

<!-- FORM-DATA:
{
    "width":  1313,
    "vFactor":  100,
    "type":  "Type0",
    "hFactor":  100,
    "controls":  [
                     {
                         "x":  182,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  1130,
                         "fmt":  "",
                         "name":  "",
                         "h":  66,
                         "color":  "212",
                         "text":  "TOUR",
                         "parent":  null
                     },
                     {
                         "x":  295,
                         "type":  "label",
                         "var":  "",
                         "y":  133,
                         "w":  361,
                         "fmt":  "",
                         "name":  "",
                         "h":  44,
                         "color":  "",
                         "text":  "TOUR CODE",
                         "parent":  null
                     },
                     {
                         "x":  655,
                         "type":  "label",
                         "var":  "",
                         "y":  133,
                         "w":  155,
                         "fmt":  "",
                         "name":  "",
                         "h":  44,
                         "color":  "",
                         "text":  "START DATE",
                         "parent":  null
                     },
                     {
                         "x":  809,
                         "type":  "label",
                         "var":  "",
                         "y":  133,
                         "w":  154,
                         "fmt":  "",
                         "name":  "",
                         "h":  44,
                         "color":  "",
                         "text":  "END DATE",
                         "parent":  null
                     },
                     {
                         "x":  295,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "",
                         "w":  668,
                         "y":  176,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  44,
                         "h":  484,
                         "cols":  [
                                      {
                                          "title":  "TOUR CODE",
                                          "layer":  1,
                                          "w":  358
                                      },
                                      {
                                          "title":  "",
                                          "layer":  2,
                                          "w":  154
                                      },
                                      {
                                          "title":  "",
                                          "layer":  3,
                                          "w":  150
                                      }
                                  ],
                         "rows":  3
                     },
                     {
                         "x":  0,
                         "type":  "image",
                         "var":  "",
                         "y":  0,
                         "w":  173,
                         "fmt":  "",
                         "name":  "RETOUR",
                         "h":  66,
                         "color":  "226",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  962,
                         "type":  "button",
                         "var":  "",
                         "y":  133,
                         "w":  56,
                         "fmt":  "",
                         "name":  "",
                         "h":  264,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  300,
                         "type":  "edit",
                         "var":  "",
                         "y":  181,
                         "w":  38,
                         "fmt":  "",
                         "name":  "hci__u_p__nb_occup_",
                         "h":  36,
                         "color":  "220",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  358,
                         "type":  "edit",
                         "var":  "",
                         "y":  181,
                         "w":  289,
                         "fmt":  "",
                         "name":  "libelle",
                         "h":  36,
                         "color":  "220",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  660,
                         "type":  "edit",
                         "var":  "",
                         "y":  181,
                         "w":  102,
                         "fmt":  "##/##/####Z",
                         "name":  "pre_date_debut",
                         "h":  36,
                         "color":  "220",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  771,
                         "type":  "edit",
                         "var":  "",
                         "y":  181,
                         "w":  33,
                         "fmt":  "",
                         "name":  "hci_heure_debut",
                         "h":  36,
                         "color":  "",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  811,
                         "type":  "edit",
                         "var":  "",
                         "y":  181,
                         "w":  102,
                         "fmt":  "##/##/####Z",
                         "name":  "pre_date_fin",
                         "h":  36,
                         "color":  "220",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  920,
                         "type":  "edit",
                         "var":  "",
                         "y":  181,
                         "w":  33,
                         "fmt":  "",
                         "name":  "hci_heure_fin",
                         "h":  36,
                         "color":  "",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  962,
                         "type":  "button",
                         "var":  "",
                         "y":  397,
                         "w":  56,
                         "fmt":  "",
                         "name":  "",
                         "h":  264,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "14",
    "height":  744
}
-->

<details>
<summary><strong>Champs : 6 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 300,181 | hci__u_p__nb_occup_ | - | edit |
| 358,181 | libelle | - | edit |
| 660,181 | pre_date_debut | - | edit |
| 771,181 | hci_heure_debut | - | edit |
| 811,181 | pre_date_fin | - | edit |
| 920,181 | hci_heure_fin | - | edit |

</details>

<details>
<summary><strong>Boutons : 2 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| (sans nom) | 962,133 | Action declenchee |
| (sans nom) | 962,397 | Action declenchee |

</details>

## 9. NAVIGATION

Ecran unique: **Circuits**

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **14.1** | [**Circuits** (14)](#t1) [mockup](#ecran-t1) | - | 1313x744 | Traitement |

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

### Tables utilisees (2)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 131 | fichier_validation |  | DB |   |   | L | 1 |
| 168 | heb_circuit______hci | Hebergement (chambres) | DB | R |   |   | 1 |

### Colonnes par table (0 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 168 - heb_circuit______hci (R) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

*(Programme sans variables locales mappees)*

## 12. EXPRESSIONS

**11 / 11 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONCATENATION | 1 | 0 |
| CONSTANTE | 3 | 0 |
| REFERENCE_VG | 3 | 0 |
| OTHER | 4 | 0 |

### 12.2 Expressions cles par type

#### CONCATENATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 1 | `'TOUR - '&Trim([P])&' '&Trim([Q])` | - |

#### CONSTANTE (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 11 | `'Y'` | - |
| CONSTANTE | 10 | `'B'` | - |
| CONSTANTE | 3 | `'TOUR'` | - |

#### REFERENCE_VG (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 6 | `VG10` | - |
| REFERENCE_VG | 5 | `VG9` | - |
| REFERENCE_VG | 2 | `VG5` | - |

#### OTHER (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 8 | `[B]` | - |
| OTHER | 9 | `[C]` | - |
| OTHER | 4 | `MlsTrans('Call Tour')` | - |
| OTHER | 7 | `[A]` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

**Chemin**: (pas de callers directs)

```mermaid
graph LR
    T14[14 Circuits]
    style T14 fill:#58a6ff
    NONE[Aucun caller]
    NONE -.-> T14
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| - | (aucun) | - |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T14[14 Circuits]
    style T14 fill:#58a6ff
    C81[81 Create logbook]
    T14 --> C81
    style C81 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [81](WEL-IDE-81.md) | Create logbook | 1 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 22 | Programme compact |
| Expressions | 11 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 1 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 22) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 1 ecran, 0 traitement)

- **Strategie** : 1 composant(s) UI (Razor/React) avec formulaires et validation.
- 1 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| [Create logbook (IDE 81)](WEL-IDE-81.md) | Sous-programme | 1x | Normale - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 21:15*
