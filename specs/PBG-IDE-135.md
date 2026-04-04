# PBG IDE 135 - GM Modifies / NA non reportes

> **Analyse**: Phases 1-4 2026-02-03 09:38 -> 09:38 (17s) | Assemblage 09:38
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBG |
| IDE Position | 135 |
| Nom Programme | GM Modifies / NA non reportes |
| Fichier source | `Prg_135.xml` |
| Domaine metier | General |
| Taches | 3 (1 ecrans visibles) |
| Tables modifiees | 2 |
| Programmes appeles | 2 |

## 2. DESCRIPTION FONCTIONNELLE

**GM Modifies / NA non reportes** assure la gestion complete de ce processus, accessible depuis [Compte Rendu Arrivants (IDE 248)](PBG-IDE-248.md).

Le flux de traitement s'organise en **3 blocs fonctionnels** :

- **Consultation** (1 tache) : ecrans de recherche, selection et consultation
- **Validation** (1 tache) : controles et verifications de coherence
- **Traitement** (1 tache) : traitements metier divers

**Donnees modifiees** : 2 tables en ecriture (import_troncon___imt, seminaires).

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (1 tache)

- **135** - Avertissement Import **[[ECRAN]](#ecran-t1)**

Delegue a : [Impression Mod/NA non reportes (IDE 136)](PBG-IDE-136.md), [Recuperation du titre (IDE 317)](PBG-IDE-317.md)

#### Phase 2 : Validation (1 tache)

- **135.1** - Verification Affichage

#### Phase 3 : Consultation (1 tache)

- **135.2** - Affichage Avertissement **[[ECRAN]](#ecran-t3)**

Delegue a : [Recuperation du titre (IDE 317)](PBG-IDE-317.md)

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| seminaires | **W**/L (2 usages) |  |
| import_troncon___imt | **W** (1 usages) |  |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>135 - Avertissement Import [[ECRAN]](#ecran-t1)

**Role** : Traitement : Avertissement Import.
**Ecran** : 190 x 11 DLU (MDI) | [Voir mockup](#ecran-t1)
**Delegue a** : [Impression Mod/NA non reportes (IDE 136)](PBG-IDE-136.md), [Recuperation du titre (IDE 317)](PBG-IDE-317.md)


### 3.2 Validation (1 tache)

Controles de coherence : 1 tache verifie les donnees et conditions.

---

#### <a id="t2"></a>135.1 - Verification Affichage

**Role** : Verification : Verification Affichage.


### 3.3 Consultation (1 tache)

Ecrans de recherche et consultation.

---

#### <a id="t3"></a>135.2 - Affichage Avertissement [[ECRAN]](#ecran-t3)

**Role** : Reinitialisation : Affichage Avertissement.
**Ecran** : 1096 x 251 DLU (MDI) | [Voir mockup](#ecran-t3)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Compte Rendu Arrivants (IDE 248)](PBG-IDE-248.md)
- **Appelle**: 2 programmes | **Tables**: 3 (W:2 R:0 L:2) | **Taches**: 3 | **Expressions**: 6

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 3)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 135.2 | 135.2 | Affichage Avertissement | MDI | 1096 | 251 | Consultation |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t3"></a>135.2 - Affichage Avertissement
**Tache** : [135.2](#t3) | **Type** : MDI | **Dimensions** : 1096 x 251 DLU
**Bloc** : Consultation | **Titre IDE** : Affichage Avertissement

<!-- FORM-DATA:
{
    "width":  1096,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  1081,
                         "fmt":  "",
                         "name":  "",
                         "h":  21,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  5,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  13,
                         "color":  "110",
                         "w":  1080,
                         "y":  24,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  13,
                         "h":  194,
                         "cols":  [
                                      {
                                          "title":  "L. Sj",
                                          "layer":  1,
                                          "w":  97
                                      },
                                      {
                                          "title":  "Nom / Prénom",
                                          "layer":  2,
                                          "w":  331
                                      },
                                      {
                                          "title":  "Dossier",
                                          "layer":  3,
                                          "w":  127
                                      },
                                      {
                                          "title":  "Adhérent",
                                          "layer":  4,
                                          "w":  168
                                      },
                                      {
                                          "title":  "Type modification",
                                          "layer":  5,
                                          "w":  168
                                      },
                                      {
                                          "title":  "Chambre",
                                          "layer":  6,
                                          "w":  96
                                      },
                                      {
                                          "title":  "Valide",
                                          "layer":  7,
                                          "w":  56
                                      }
                                  ],
                         "rows":  7
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  224,
                         "w":  1081,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  11,
                         "type":  "edit",
                         "var":  "",
                         "y":  40,
                         "w":  89,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  109,
                         "type":  "edit",
                         "var":  "",
                         "y":  40,
                         "w":  320,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  438,
                         "type":  "edit",
                         "var":  "",
                         "y":  40,
                         "w":  119,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  568,
                         "type":  "edit",
                         "var":  "",
                         "y":  40,
                         "w":  106,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  682,
                         "type":  "edit",
                         "var":  "",
                         "y":  40,
                         "w":  40,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  902,
                         "type":  "edit",
                         "var":  "",
                         "y":  40,
                         "w":  84,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  733,
                         "type":  "edit",
                         "var":  "",
                         "y":  40,
                         "w":  156,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  781,
                         "type":  "edit",
                         "var":  "",
                         "y":  7,
                         "w":  296,
                         "fmt":  "WWW DD MMM YYYYT",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  997,
                         "type":  "edit",
                         "var":  "",
                         "y":  40,
                         "w":  35,
                         "fmt":  "3",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  6,
                         "type":  "button",
                         "var":  "",
                         "y":  227,
                         "w":  154,
                         "fmt":  "\u0026Quitter",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  920,
                         "type":  "button",
                         "var":  "",
                         "y":  227,
                         "w":  154,
                         "fmt":  "\u0026Impression",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  6,
                         "type":  "edit",
                         "var":  "",
                         "y":  7,
                         "w":  267,
                         "fmt":  "20",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "135.2",
    "height":  251
}
-->

<details>
<summary><strong>Champs : 10 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 11,40 | (sans nom) | - | edit |
| 109,40 | (sans nom) | - | edit |
| 438,40 | (sans nom) | - | edit |
| 568,40 | (sans nom) | - | edit |
| 682,40 | (sans nom) | - | edit |
| 902,40 | (sans nom) | - | edit |
| 733,40 | (sans nom) | - | edit |
| 781,7 | WWW DD MMM YYYYT | - | edit |
| 997,40 | 3 | - | edit |
| 6,7 | 20 | - | edit |

</details>

<details>
<summary><strong>Boutons : 2 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Quitter | 6,227 | Quitte le programme |
| Impression | 920,227 | Appel [Impression Mod/NA non reportes (IDE 136)](PBG-IDE-136.md) |

</details>

## 9. NAVIGATION

Ecran unique: **Affichage Avertissement**

### 9.3 Structure hierarchique (3 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **135.1** | [**Avertissement Import** (135)](#t1) [mockup](#ecran-t1) | MDI | 190x11 | Traitement |
| **135.2** | [**Verification Affichage** (135.1)](#t2) | MDI | - | Validation |
| **135.3** | [**Affichage Avertissement** (135.2)](#t3) [mockup](#ecran-t3) | MDI | 1096x251 | Consultation |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Affichage Avertissement]
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
| 359 | erreur_od |  | DB |   |   | L | 1 |
| 558 | import_troncon___imt |  | TMP |   | **W** |   | 1 |
| 579 | seminaires |  | TMP |   | **W** | L | 2 |

### Colonnes par table (0 / 2 tables avec colonnes identifiees)

<details>
<summary>Table 558 - import_troncon___imt (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 579 - seminaires (**W**/L) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Autres (5)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P0-Code Choix | Alpha | - |
| B | P0-Code Societe | Alpha | - |
| C | P0-Code Langue | Alpha | - |
| D | W0-Code Suite | Alpha | 2x refs |
| E | W0-Code B031 | Alpha | - |

## 12. EXPRESSIONS

**6 / 6 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONSTANTE | 2 | 0 |
| OTHER | 2 | 0 |
| CONDITION | 2 | 0 |

### 12.2 Expressions cles par type

#### CONSTANTE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 6 | `'B031'` | - |
| CONSTANTE | 3 | `''` | - |

#### OTHER (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 2 | `GetParam ('LANGUE')` | - |
| OTHER | 1 | `GetParam ('SOCIETE')` | - |

#### CONDITION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 5 | `W0-Code Suite [D]='O'` | - |
| CONDITION | 4 | `W0-Code Suite [D]='N'` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Compte Rendu Arrivants (IDE 248)](PBG-IDE-248.md) -> **GM Modifies / NA non reportes (IDE 135)**

```mermaid
graph LR
    T135[135 GM Modifies NA non...]
    style T135 fill:#58a6ff
    CC206[206 Traitement des arr...]
    style CC206 fill:#8b5cf6
    CC248[248 Compte Rendu Arriv...]
    style CC248 fill:#3fb950
    CC206 --> CC248
    CC248 --> T135
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [248](PBG-IDE-248.md) | Compte Rendu Arrivants | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T135[135 GM Modifies NA non...]
    style T135 fill:#58a6ff
    C136[136 Impression ModNA n...]
    T135 --> C136
    style C136 fill:#3fb950
    C317[317 Recuperation du titre]
    T135 --> C317
    style C317 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [136](PBG-IDE-136.md) | Impression Mod/NA non reportes | 1 | Sous-programme |
| [317](PBG-IDE-317.md) | Recuperation du titre | 1 | Recuperation donnees |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 61 | Programme compact |
| Expressions | 6 | Peu de logique |
| Tables WRITE | 2 | Impact faible |
| Sous-programmes | 2 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 61) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 1 ecran, 0 traitement)

- **Strategie** : 1 composant(s) UI (Razor/React) avec formulaires et validation.
- 2 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Validation (1 tache: 0 ecran, 1 traitement)

- **Strategie** : FluentValidation avec validators specifiques.
- Chaque tache de validation -> un validator injectable

#### Consultation (1 tache: 1 ecran, 0 traitement)

- **Strategie** : Composants de recherche/selection en modales.
- 1 ecran : Affichage Avertissement

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| import_troncon___imt | Table WRITE (Temp) | 1x | Schema + repository |
| seminaires | Table WRITE (Temp) | 1x | Schema + repository |
| [Recuperation du titre (IDE 317)](PBG-IDE-317.md) | Sous-programme | 1x | Normale - Recuperation donnees |
| [Impression Mod/NA non reportes (IDE 136)](PBG-IDE-136.md) | Sous-programme | 1x | Normale - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 09:38*
