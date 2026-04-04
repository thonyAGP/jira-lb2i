# PBS IDE 67 - Gestion Code Logement

> **Analyse**: Phases 1-4 2026-02-03 17:23 -> 17:23 (16s) | Assemblage 17:23
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBS |
| IDE Position | 67 |
| Nom Programme | Gestion Code Logement |
| Fichier source | `Prg_67.xml` |
| Dossier IDE | Utilitaires |
| Taches | 3 (1 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 5 |
| :warning: Statut | **ORPHELIN_POTENTIEL** |

## 2. DESCRIPTION FONCTIONNELLE

**Gestion Code Logement** assure la gestion complete de ce processus.

Le flux de traitement s'organise en **2 blocs fonctionnels** :

- **Traitement** (2 taches) : traitements metier divers
- **Consultation** (1 tache) : ecrans de recherche, selection et consultation

**Donnees modifiees** : 1 tables en ecriture (societe__________soc).

**Logique metier** : 1 regles identifiees couvrant conditions metier.

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (2 taches)

- **67** - Êcran **[[ECRAN]](#ecran-t1)**
- **67.1** - Êcran **[[ECRAN]](#ecran-t2)**

Delegue a : [Recuperation du titre (IDE 10)](PBS-IDE-10.md), [Gestion Code Logement pms-626 (IDE 68)](PBS-IDE-68.md), [Suppression Code Logement (IDE 70)](PBS-IDE-70.md)

#### Phase 2 : Consultation (1 tache)

- **67.1.1** - Selection Lieu deSejour

Delegue a : [Recuperation du titre (IDE 10)](PBS-IDE-10.md), [Zoom LIEU DE SEJOUR (IDE 92)](PBS-IDE-92.md)

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| societe__________soc | **W** (1 usages) |  |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (2 taches)

Traitements internes.

---

#### <a id="t1"></a>67 - Êcran [[ECRAN]](#ecran-t1)

**Role** : Traitement : Êcran.
**Ecran** : 166 x 22 DLU (MDI) | [Voir mockup](#ecran-t1)
**Delegue a** : [Recuperation du titre (IDE 10)](PBS-IDE-10.md), [Gestion Code Logement pms-626 (IDE 68)](PBS-IDE-68.md), [Suppression Code Logement (IDE 70)](PBS-IDE-70.md)

---

#### <a id="t2"></a>67.1 - Êcran [[ECRAN]](#ecran-t2)

**Role** : Traitement : Êcran.
**Ecran** : 1210 x 228 DLU (MDI) | [Voir mockup](#ecran-t2)
**Delegue a** : [Recuperation du titre (IDE 10)](PBS-IDE-10.md), [Gestion Code Logement pms-626 (IDE 68)](PBS-IDE-68.md), [Suppression Code Logement (IDE 70)](PBS-IDE-70.md)


### 3.2 Consultation (1 tache)

Ecrans de recherche et consultation.

---

#### <a id="t3"></a>67.1.1 - Selection Lieu deSejour

**Role** : Selection par l'operateur : Selection Lieu deSejour.
**Variables liees** : B (v.Code Lieu Sejour)
**Delegue a** : [Zoom LIEU DE SEJOUR (IDE 92)](PBS-IDE-92.md)


## 5. REGLES METIER

1 regles identifiees:

### Autres (1 regles)

#### <a id="rm-RM-001"></a>[RM-001] Traitement si VG9 est non nul

| Element | Detail |
|---------|--------|
| **Condition** | `VG9<>0` |
| **Si vrai** | 'N12.'&Trim(Str(VG9 |
| **Si faux** | '#'))&'CZ','N12CZ') |
| **Expression source** | Expression 4 : `IF(VG9<>0,'N12.'&Trim(Str(VG9,'#'))&'CZ','N12CZ')` |
| **Exemple** | Si VG9<>0 â†’ 'N12.'&Trim(Str(VG9. Sinon â†’ '#'))&'CZ','N12CZ') |

## 6. CONTEXTE

- **Appele par**: (aucun)
- **Appelle**: 5 programmes | **Tables**: 3 (W:1 R:0 L:2) | **Taches**: 3 | **Expressions**: 6

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 3)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 67.1 | 67.1 | Êcran | MDI | 1210 | 228 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t2"></a>67.1 - Êcran
**Tache** : [67.1](#t2) | **Type** : MDI | **Dimensions** : 1210 x 228 DLU
**Bloc** : Traitement | **Titre IDE** : Êcran

<!-- FORM-DATA:
{
    "width":  1210,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  1,
                         "w":  1206,
                         "fmt":  "",
                         "name":  "",
                         "h":  20,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  13,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "110",
                         "w":  774,
                         "y":  33,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  14,
                         "h":  155,
                         "cols":  [
                                      {
                                          "title":  "Code",
                                          "layer":  1,
                                          "w":  120
                                      },
                                      {
                                          "title":  "Libellé",
                                          "layer":  2,
                                          "w":  452
                                      },
                                      {
                                          "title":  "Intervalle Ménage",
                                          "layer":  3,
                                          "w":  164
                                      }
                                  ],
                         "rows":  3
                     },
                     {
                         "x":  826,
                         "type":  "label",
                         "var":  "",
                         "y":  33,
                         "w":  74,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "7",
                         "text":  "Société",
                         "parent":  null
                     },
                     {
                         "x":  826,
                         "type":  "label",
                         "var":  "",
                         "y":  47,
                         "w":  117,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "7",
                         "text":  "Lieu de Séjour",
                         "parent":  null
                     },
                     {
                         "x":  795,
                         "type":  "label",
                         "var":  "",
                         "y":  71,
                         "w":  404,
                         "fmt":  "",
                         "name":  "",
                         "h":  118,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  201,
                         "w":  1206,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  967,
                         "type":  "edit",
                         "var":  "",
                         "y":  33,
                         "w":  232,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "7",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  46,
                         "type":  "edit",
                         "var":  "",
                         "y":  48,
                         "w":  75,
                         "fmt":  "",
                         "name":  "CLO Code Logement",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  143,
                         "type":  "edit",
                         "var":  "",
                         "y":  48,
                         "w":  440,
                         "fmt":  "",
                         "name":  "CLO Libelle Logement",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  647,
                         "type":  "edit",
                         "var":  "",
                         "y":  48,
                         "w":  26,
                         "fmt":  "",
                         "name":  "Intervalle Menage",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  6,
                         "type":  "edit",
                         "var":  "",
                         "y":  7,
                         "w":  396,
                         "fmt":  "30",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  996,
                         "type":  "edit",
                         "var":  "",
                         "y":  8,
                         "w":  203,
                         "fmt":  "WWW DD MMM YYYYT",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  967,
                         "type":  "edit",
                         "var":  "",
                         "y":  47,
                         "w":  232,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "7",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  808,
                         "type":  "button",
                         "var":  "",
                         "y":  77,
                         "w":  154,
                         "fmt":  "\u0026Visualisation",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  17
                     },
                     {
                         "x":  979,
                         "type":  "image",
                         "var":  "",
                         "y":  84,
                         "w":  202,
                         "fmt":  "",
                         "name":  "",
                         "h":  95,
                         "color":  "",
                         "text":  "",
                         "parent":  16
                     },
                     {
                         "x":  808,
                         "type":  "button",
                         "var":  "",
                         "y":  99,
                         "w":  154,
                         "fmt":  "\u0026Modification",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  17
                     },
                     {
                         "x":  808,
                         "type":  "button",
                         "var":  "",
                         "y":  121,
                         "w":  154,
                         "fmt":  "\u0026Creation",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  17
                     },
                     {
                         "x":  808,
                         "type":  "button",
                         "var":  "",
                         "y":  143,
                         "w":  154,
                         "fmt":  "\u0026Annulation",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  17
                     },
                     {
                         "x":  808,
                         "type":  "button",
                         "var":  "",
                         "y":  165,
                         "w":  154,
                         "fmt":  "\u0026Suppression",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  17
                     },
                     {
                         "x":  6,
                         "type":  "button",
                         "var":  "",
                         "y":  204,
                         "w":  154,
                         "fmt":  "\u0026Quitter",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  18
                     },
                     {
                         "x":  1045,
                         "type":  "button",
                         "var":  "",
                         "y":  204,
                         "w":  154,
                         "fmt":  "\u0026Lieu de Séjour",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  18
                     }
                 ],
    "taskId":  "67.1",
    "height":  228
}
-->

<details>
<summary><strong>Champs : 7 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 967,33 | (sans nom) | - | edit |
| 46,48 | CLO Code Logement | - | edit |
| 143,48 | CLO Libelle Logement | - | edit |
| 647,48 | Intervalle Menage | - | edit |
| 6,7 | 30 | - | edit |
| 996,8 | WWW DD MMM YYYYT | - | edit |
| 967,47 | (sans nom) | - | edit |

</details>

<details>
<summary><strong>Boutons : 7 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Visualisation | 808,77 | Bouton fonctionnel |
| Modification | 808,99 | Modifie l'element |
| Creation | 808,121 | Appel [Creation Historique (IDE 79)](PBS-IDE-79.md) |
| Annulation | 808,143 | Annule et retour au menu |
| Suppression | 808,165 | Appel [Suppression Code Logement (IDE 70)](PBS-IDE-70.md) |
| Quitter | 6,204 | Quitte le programme |
| Lieu de Séjour | 1045,204 | Appel [Zoom LIEU DE SEJOUR (IDE 92)](PBS-IDE-92.md) |

</details>

## 9. NAVIGATION

Ecran unique: **Êcran**

### 9.3 Structure hierarchique (3 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **67.1** | [**Êcran** (67)](#t1) [mockup](#ecran-t1) | MDI | 166x22 | Traitement |
| 67.1.1 | [Êcran (67.1)](#t2) [mockup](#ecran-t2) | MDI | 1210x228 | |
| **67.2** | [**Selection Lieu deSejour** (67.1.1)](#t3) | MDI | - | Consultation |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Gestion Code Logement]
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
| 81 | societe__________soc |  | DB |   | **W** |   | 1 |
| 108 | code_logement____clo |  | DB |   |   | L | 1 |
| 347 | intervalle_menage |  | DB |   |   | L | 1 |

### Colonnes par table (2 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 81 - societe__________soc (**W**) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | > societe | W | Alpha |
| B | v. titre | W | Alpha |
| C | v.Nombre Lieu de Sejour | W | Numeric |
| D | v.contrôle1 | W | Logical |
| E | v.Contrôle2 | W | Logical |

</details>

## 11. VARIABLES

### 11.1 Variables de session (5)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | v.Code Operation | Alpha | 1x session |
| B | v.Code Lieu Sejour | Alpha | - |
| C | v.Nom Import | Alpha | - |
| D | V.Masque | Alpha | - |
| E | v.Contrôle2 | Logical | - |

## 12. EXPRESSIONS

**6 / 6 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONDITION | 2 | 5 |
| OTHER | 2 | 0 |
| REFERENCE_VG | 1 | 0 |
| NEGATION | 1 | 0 |

### 12.2 Expressions cles par type

#### CONDITION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 4 | `IF(VG9<>0,'N12.'&Trim(Str(VG9,'#'))&'CZ','N12CZ')` | [RM-001](#rm-RM-001) |
| CONDITION | 1 | `v.Code Operation [A]=''` | - |

#### OTHER (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 3 | `GetParam ('NOM_IMPORT')` | - |
| OTHER | 2 | `GetParam ('CODE_LIEU_SEJOUR')` | - |

#### REFERENCE_VG (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 5 | `VG28` | - |

#### NEGATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| NEGATION | 6 | `NOT VG28` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

**Chemin**: (pas de callers directs)

```mermaid
graph LR
    T67[67 Gestion Code Logement]
    style T67 fill:#58a6ff
    NONE[Aucun caller]
    NONE -.-> T67
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| - | (aucun) | - |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T67[67 Gestion Code Logement]
    style T67 fill:#58a6ff
    C10[10 Recuperation du titre]
    T67 --> C10
    style C10 fill:#3fb950
    C68[68 Gestion Code Logeme...]
    T67 --> C68
    style C68 fill:#3fb950
    C70[70 Suppression Code Lo...]
    T67 --> C70
    style C70 fill:#3fb950
    C79[79 Creation Historique]
    T67 --> C79
    style C79 fill:#3fb950
    C92[92 Zoom LIEU DE SEJOUR]
    T67 --> C92
    style C92 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [10](PBS-IDE-10.md) | Recuperation du titre | 1 | Recuperation donnees |
| [68](PBS-IDE-68.md) | Gestion Code Logement pms-626 | 1 | Gestion moyens paiement |
| [70](PBS-IDE-70.md) | Suppression Code Logement | 1 | Sous-programme |
| [79](PBS-IDE-79.md) | Creation Historique | 1 | Historique/consultation |
| [92](PBS-IDE-92.md) | Zoom LIEU DE SEJOUR | 1 | Selection/consultation |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 55 | Programme compact |
| Expressions | 6 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 5 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 55) | Code sain |
| Regles metier | 1 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (2 taches: 2 ecrans, 0 traitement)

- **Strategie** : 2 composant(s) UI (Razor/React) avec formulaires et validation.
- 5 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Consultation (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Composants de recherche/selection en modales.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| societe__________soc | Table WRITE (Database) | 1x | Schema + repository |
| [Creation Historique (IDE 79)](PBS-IDE-79.md) | Sous-programme | 1x | Normale - Historique/consultation |
| [Zoom LIEU DE SEJOUR (IDE 92)](PBS-IDE-92.md) | Sous-programme | 1x | Normale - Selection/consultation |
| [Suppression Code Logement (IDE 70)](PBS-IDE-70.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Recuperation du titre (IDE 10)](PBS-IDE-10.md) | Sous-programme | 1x | Normale - Recuperation donnees |
| [Gestion Code Logement pms-626 (IDE 68)](PBS-IDE-68.md) | Sous-programme | 1x | Normale - Gestion moyens paiement |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 17:23*
