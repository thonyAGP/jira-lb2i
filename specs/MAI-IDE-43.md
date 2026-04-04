# MAI IDE 43 - Visualisation pooling

> **Analyse**: Phases 1-4 2026-02-03 14:54 -> 14:54 (9s) | Assemblage 14:54
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | MAI |
| IDE Position | 43 |
| Nom Programme | Visualisation pooling |
| Fichier source | `Prg_43.xml` |
| Dossier IDE | Controle |
| Taches | 3 (2 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Visualisation pooling** assure la gestion complete de ce processus, accessible depuis [Verification pooling (IDE 42)](MAI-IDE-42.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Validation** (3 taches) : controles et verifications de coherence

**Logique metier** : 2 regles identifiees couvrant conditions metier.

## 3. BLOCS FONCTIONNELS

### 3.1 Validation (3 taches)

Controles de coherence : 3 taches verifient les donnees et conditions.

---

#### <a id="t1"></a>43 - Verification Pooling [[ECRAN]](#ecran-t1)

**Role** : Verification : Verification Pooling.
**Ecran** : 883 x 170 DLU (MDI) | [Voir mockup](#ecran-t1)
**Variables liees** : A (v. type de pooling)

---

#### <a id="t4"></a>43.1 - Verification Pooling [[ECRAN]](#ecran-t4)

**Role** : Verification : Verification Pooling.
**Ecran** : 883 x 170 DLU (MDI) | [Voir mockup](#ecran-t4)
**Variables liees** : A (v. type de pooling)

---

#### <a id="t7"></a>43.2 - Verification Pooling [[ECRAN]](#ecran-t7)

**Role** : Verification : Verification Pooling.
**Ecran** : 883 x 170 DLU (MDI) | [Voir mockup](#ecran-t7)
**Variables liees** : A (v. type de pooling)


## 5. REGLES METIER

2 regles identifiees:

### Autres (2 regles)

#### <a id="rm-RM-001"></a>[RM-001] Si [B]='COM' alors 'TELEPHONE' sinon 'MONETIQUE')

| Element | Detail |
|---------|--------|
| **Condition** | `[B]='COM'` |
| **Si vrai** | 'TELEPHONE' |
| **Si faux** | 'MONETIQUE') |
| **Expression source** | Expression 6 : `IF ([B]='COM','TELEPHONE','MONETIQUE')` |
| **Exemple** | Si [B]='COM' â†’ 'TELEPHONE'. Sinon â†’ 'MONETIQUE') |

#### <a id="rm-RM-002"></a>[RM-002] Si [D] alors 'Probleme sur le pooling' sinon 'Ok')

| Element | Detail |
|---------|--------|
| **Condition** | `[D]` |
| **Si vrai** | 'Probleme sur le pooling' |
| **Si faux** | 'Ok') |
| **Expression source** | Expression 7 : `IF ([D],'Probleme sur le pooling','Ok')` |
| **Exemple** | Si [D] â†’ 'Probleme sur le pooling'. Sinon â†’ 'Ok') |

## 6. CONTEXTE

- **Appele par**: [Verification pooling (IDE 42)](MAI-IDE-42.md)
- **Appelle**: 0 programmes | **Tables**: 1 (W:0 R:1 L:0) | **Taches**: 3 | **Expressions**: 8

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (2 / 3)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 43.2 | 43.1 | Verification Pooling | MDI | 883 | 170 | Validation |
| 2 | 43.1 | 43.2 | Verification Pooling | MDI | 883 | 170 | Validation |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t4"></a>43.2 - Verification Pooling
**Tache** : [43.1](#t4) | **Type** : MDI | **Dimensions** : 883 x 170 DLU
**Bloc** : Validation | **Titre IDE** : Verification Pooling

<!-- FORM-DATA:
{
    "width":  883,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  875,
                         "fmt":  "",
                         "name":  "",
                         "h":  19,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  85,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "110",
                         "w":  707,
                         "y":  25,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  12,
                         "h":  111,
                         "cols":  [
                                      {
                                          "title":  "Pooling",
                                          "layer":  1,
                                          "w":  245
                                      },
                                      {
                                          "title":  "Etat",
                                          "layer":  2,
                                          "w":  253
                                      },
                                      {
                                          "title":  "Heure de Verification",
                                          "layer":  3,
                                          "w":  171
                                      }
                                  ],
                         "rows":  3
                     },
                     {
                         "x":  2,
                         "type":  "label",
                         "var":  "",
                         "y":  140,
                         "w":  875,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  98,
                         "type":  "edit",
                         "var":  "",
                         "y":  41,
                         "w":  232,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "146",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  624,
                         "type":  "edit",
                         "var":  "",
                         "y":  41,
                         "w":  98,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  502,
                         "type":  "edit",
                         "var":  "",
                         "y":  5,
                         "w":  365,
                         "fmt":  "WWW DD MMM YYYYT",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  342,
                         "type":  "edit",
                         "var":  "",
                         "y":  41,
                         "w":  232,
                         "fmt":  "30",
                         "name":  "",
                         "h":  8,
                         "color":  "146",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  8,
                         "type":  "button",
                         "var":  "",
                         "y":  143,
                         "w":  154,
                         "fmt":  "\u0026Quitter",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  14
                     },
                     {
                         "x":  10,
                         "type":  "edit",
                         "var":  "",
                         "y":  5,
                         "w":  267,
                         "fmt":  "20",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     }
                 ],
    "taskId":  "43.2",
    "height":  170
}
-->

<details>
<summary><strong>Champs : 5 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 98,41 | (sans nom) | - | edit |
| 624,41 | (sans nom) | - | edit |
| 502,5 | WWW DD MMM YYYYT | - | edit |
| 342,41 | 30 | - | edit |
| 10,5 | 20 | - | edit |

</details>

<details>
<summary><strong>Boutons : 1 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Quitter | 8,143 | Quitte le programme |

</details>

---

#### <a id="ecran-t7"></a>43.1 - Verification Pooling
**Tache** : [43.2](#t7) | **Type** : MDI | **Dimensions** : 883 x 170 DLU
**Bloc** : Validation | **Titre IDE** : Verification Pooling

<!-- FORM-DATA:
{
    "width":  883,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  875,
                         "fmt":  "",
                         "name":  "",
                         "h":  19,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  85,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "110",
                         "w":  707,
                         "y":  25,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  12,
                         "h":  111,
                         "cols":  [
                                      {
                                          "title":  "Pooling",
                                          "layer":  1,
                                          "w":  245
                                      },
                                      {
                                          "title":  "Etat",
                                          "layer":  2,
                                          "w":  253
                                      },
                                      {
                                          "title":  "Heure de Verification",
                                          "layer":  3,
                                          "w":  171
                                      }
                                  ],
                         "rows":  3
                     },
                     {
                         "x":  2,
                         "type":  "label",
                         "var":  "",
                         "y":  140,
                         "w":  875,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  98,
                         "type":  "edit",
                         "var":  "",
                         "y":  41,
                         "w":  232,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "146",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  624,
                         "type":  "edit",
                         "var":  "",
                         "y":  41,
                         "w":  98,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  502,
                         "type":  "edit",
                         "var":  "",
                         "y":  5,
                         "w":  365,
                         "fmt":  "WWW DD MMM YYYYT",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  342,
                         "type":  "edit",
                         "var":  "",
                         "y":  41,
                         "w":  232,
                         "fmt":  "30",
                         "name":  "",
                         "h":  8,
                         "color":  "146",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  8,
                         "type":  "button",
                         "var":  "",
                         "y":  143,
                         "w":  154,
                         "fmt":  "\u0026Quitter",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  14
                     },
                     {
                         "x":  10,
                         "type":  "edit",
                         "var":  "",
                         "y":  5,
                         "w":  267,
                         "fmt":  "20",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     }
                 ],
    "taskId":  "43.1",
    "height":  170
}
-->

<details>
<summary><strong>Champs : 5 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 98,41 | (sans nom) | - | edit |
| 624,41 | (sans nom) | - | edit |
| 502,5 | WWW DD MMM YYYYT | - | edit |
| 342,41 | 30 | - | edit |
| 10,5 | 20 | - | edit |

</details>

<details>
<summary><strong>Boutons : 1 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Quitter | 8,143 | Quitte le programme |

</details>

## 9. NAVIGATION

### 9.1 Enchainement des ecrans

```mermaid
flowchart TD
    START([Entree])
    style START fill:#3fb950
    VF4[43.1 Verification Pooling]
    style VF4 fill:#58a6ff
    VF7[43.2 Verification Pooling]
    style VF7 fill:#58a6ff
    FIN([Sortie])
    style FIN fill:#f85149
    START --> VF4
    VF4 --> FIN
```

**Detail par enchainement :**

| Depuis | Action | Vers | Retour |
|--------|--------|------|--------|

### 9.3 Structure hierarchique (3 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **43.1** | [**Verification Pooling** (43)](#t1) [mockup](#ecran-t1) | MDI | 883x170 | Validation |
| 43.1.1 | [Verification Pooling (43.1)](#t4) [mockup](#ecran-t4) | MDI | 883x170 | |
| 43.1.2 | [Verification Pooling (43.2)](#t7) [mockup](#ecran-t7) | MDI | 883x170 | |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Visualisation pooling T2H]
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

### Tables utilisees (1)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 476 | comptes_pour_changer_activite | Comptes GM (generaux) | TMP | R |   |   | 2 |

### Colonnes par table (0 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 476 - comptes_pour_changer_activite (R) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

*(Programme sans variables locales mappees)*

## 12. EXPRESSIONS

**8 / 8 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONDITION | 3 | 2 |
| DATE | 1 | 0 |
| NEGATION | 1 | 0 |
| REFERENCE_VG | 3 | 0 |

### 12.2 Expressions cles par type

#### CONDITION (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 7 | `IF ([D],'Probleme sur le pooling','Ok')` | [RM-002](#rm-RM-002) |
| CONDITION | 6 | `IF ([B]='COM','TELEPHONE','MONETIQUE')` | [RM-001](#rm-RM-001) |
| CONDITION | 8 | `IF ([D],11,1)` | - |

#### DATE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| DATE | 4 | `Date ()` | - |

#### NEGATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| NEGATION | 1 | `NOT VG9` | - |

#### REFERENCE_VG (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 5 | `VG2` | - |
| REFERENCE_VG | 3 | `VG10` | - |
| REFERENCE_VG | 2 | `VG9` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Verification pooling (IDE 42)](MAI-IDE-42.md) -> **Visualisation pooling (IDE 43)**

```mermaid
graph LR
    T43[43 Visualisation pooling]
    style T43 fill:#58a6ff
    CC42[42 Verification pooling]
    style CC42 fill:#8b5cf6
    CC42 --> T43
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [42](MAI-IDE-42.md) | Verification pooling | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T43[43 Visualisation pooling]
    style T43 fill:#58a6ff
    NONE[Aucun callee]
    T43 -.-> NONE
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
| Lignes de logique | 19 | Programme compact |
| Expressions | 8 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 2 | Quelques ecrans |
| Code desactive | 0% (0 / 19) | Code sain |
| Regles metier | 2 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Validation (3 taches: 3 ecrans, 0 traitement)

- **Strategie** : FluentValidation avec validators specifiques.
- Chaque tache de validation -> un validator injectable

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 14:54*
