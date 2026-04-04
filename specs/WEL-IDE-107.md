# WEL IDE 107 - Zoom village/village

> **Analyse**: Phases 1-4 2026-02-03 21:48 -> 21:48 (16s) | Assemblage 21:48
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | WEL |
| IDE Position | 107 |
| Nom Programme | Zoom village/village |
| Fichier source | `Prg_107.xml` |
| Dossier IDE | Zoom |
| Taches | 1 (1 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 1 |

## 2. DESCRIPTION FONCTIONNELLE

**Zoom village/village** assure la gestion complete de ce processus, accessible depuis [Affichage validation (IDE 64)](WEL-IDE-64.md), [  Avancement Personnel (IDE 66)](WEL-IDE-66.md), [  Interruption Personnel (IDE 67)](WEL-IDE-67.md), [  Prolongation Personnel (IDE 69)](WEL-IDE-69.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Consultation** (1 tache) : ecrans de recherche, selection et consultation

**Logique metier** : 1 regles identifiees couvrant conditions metier.

## 3. BLOCS FONCTIONNELS

### 3.1 Consultation (1 tache)

Ecrans de recherche et consultation.

---

#### <a id="t1"></a>107 - Zoom village/village [[ECRAN]](#ecran-t1)

**Role** : Selection par l'operateur : Zoom village/village.
**Ecran** : 1313 x 744 DLU | [Voir mockup](#ecran-t1)


## 5. REGLES METIER

1 regles identifiees:

### Autres (1 regles)

#### <a id="rm-RM-001"></a>[RM-001] Si P.Vol aller retour [A]='A' alors MlsTrans('INBOUND') sinon MlsTrans('OUTBOUND'))

| Element | Detail |
|---------|--------|
| **Condition** | `P.Vol aller retour [A]='A'` |
| **Si vrai** | MlsTrans('INBOUND') |
| **Si faux** | MlsTrans('OUTBOUND')) |
| **Variables** | A (P.Vol aller retour) |
| **Expression source** | Expression 15 : `IF(P.Vol aller retour [A]='A',MlsTrans('INBOUND'),MlsTrans('` |
| **Exemple** | Si P.Vol aller retour [A]='A' â†’ MlsTrans('INBOUND'). Sinon â†’ MlsTrans('OUTBOUND')) |

## 6. CONTEXTE

- **Appele par**: [Affichage validation (IDE 64)](WEL-IDE-64.md), [  Avancement Personnel (IDE 66)](WEL-IDE-66.md), [  Interruption Personnel (IDE 67)](WEL-IDE-67.md), [  Prolongation Personnel (IDE 69)](WEL-IDE-69.md)
- **Appelle**: 1 programmes | **Tables**: 1 (W:0 R:1 L:0) | **Taches**: 1 | **Expressions**: 15

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 1)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 107 | 107 | Zoom village/village | Type0 | 1313 | 744 | Consultation |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>107 - Zoom village/village
**Tache** : [107](#t1) | **Type** : Type0 | **Dimensions** : 1313 x 744 DLU
**Bloc** : Consultation | **Titre IDE** : Zoom village/village

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
                         "text":  "FLIGHT CODE",
                         "parent":  null
                     },
                     {
                         "x":  528,
                         "type":  "label",
                         "var":  "",
                         "y":  98,
                         "w":  120,
                         "fmt":  "",
                         "name":  "",
                         "h":  44,
                         "color":  "",
                         "text":  "INBOUND",
                         "parent":  null
                     },
                     {
                         "x":  647,
                         "type":  "label",
                         "var":  "",
                         "y":  98,
                         "w":  83,
                         "fmt":  "",
                         "name":  "",
                         "h":  44,
                         "color":  "",
                         "text":  "TIME",
                         "parent":  null
                     },
                     {
                         "x":  577,
                         "type":  "label",
                         "var":  "",
                         "y":  633,
                         "w":  173,
                         "fmt":  "",
                         "name":  "SELECT",
                         "h":  88,
                         "color":  "",
                         "text":  "SELECT",
                         "parent":  null
                     },
                     {
                         "x":  529,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "",
                         "w":  200,
                         "y":  139,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  44,
                         "h":  443,
                         "cols":  [
                                      {
                                          "title":  "vol_code_vol",
                                          "layer":  1,
                                          "w":  116
                                      },
                                      {
                                          "title":  "vol_heure",
                                          "layer":  2,
                                          "w":  80
                                      }
                                  ],
                         "rows":  2
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
                         "x":  729,
                         "type":  "button",
                         "var":  "",
                         "y":  97,
                         "w":  56,
                         "fmt":  "",
                         "name":  "",
                         "h":  243,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  532,
                         "type":  "edit",
                         "var":  "",
                         "y":  144,
                         "w":  112,
                         "fmt":  "U6",
                         "name":  "vol_code_vol",
                         "h":  36,
                         "color":  "",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  651,
                         "type":  "edit",
                         "var":  "",
                         "y":  144,
                         "w":  64,
                         "fmt":  "2P0",
                         "name":  "vol_heure",
                         "h":  36,
                         "color":  "",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  729,
                         "type":  "button",
                         "var":  "",
                         "y":  338,
                         "w":  56,
                         "fmt":  "",
                         "name":  "",
                         "h":  243,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "107",
    "height":  744
}
-->

<details>
<summary><strong>Champs : 2 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 532,144 | vol_code_vol | - | edit |
| 651,144 | vol_heure | - | edit |

</details>

<details>
<summary><strong>Boutons : 2 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| (sans nom) | 729,97 | Action declenchee |
| (sans nom) | 729,338 | Action declenchee |

</details>

## 9. NAVIGATION

Ecran unique: **Zoom village/village**

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **107.1** | [**Zoom village/village** (107)](#t1) [mockup](#ecran-t1) | - | 1313x744 | Consultation |

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

### Tables utilisees (1)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 134 | groupe_arr_dep___vol |  | DB | R |   |   | 1 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 134 - groupe_arr_dep___vol (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P.Vol aller retour | R | Alpha |
| B | P.Vol date | R | Date |
| C | P.Code vol | R | Alpha |
| D | P.Vol heure | R | Alpha |
| E | P.Accord suite | R | Alpha |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (5)

Variables recues du programme appelant ([Affichage validation (IDE 64)](WEL-IDE-64.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P.Vol aller retour | Alpha | 3x parametre entrant |
| B | P.Vol date | Date | 1x parametre entrant |
| C | P.Code vol | Alpha | 1x parametre entrant |
| D | P.Vol heure | Alpha | 1x parametre entrant |
| E | P.Accord suite | Alpha | - |

## 12. EXPRESSIONS

**15 / 15 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCULATION | 1 | 0 |
| CONDITION | 1 | 5 |
| CONSTANTE | 5 | 0 |
| REFERENCE_VG | 1 | 0 |
| OTHER | 3 | 0 |
| CONCATENATION | 2 | 0 |
| NEGATION | 1 | 0 |
| STRING | 1 | 0 |

### 12.2 Expressions cles par type

#### CALCULATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 6 | `MlsTrans('Call - Flight code list')` | - |

#### CONDITION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 15 | `IF(P.Vol aller retour [A]='A',MlsTrans('INBOUND'),MlsTrans('OUTBOUND'))` | [RM-001](#rm-RM-001) |

#### CONSTANTE (5 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 10 | `'N'` | - |
| CONSTANTE | 11 | `'O'` | - |
| CONSTANTE | 8 | `'M'` | - |
| CONSTANTE | 4 | `'ZOOM_FLIGHT'` | - |
| CONSTANTE | 5 | `'SEL_FLIGHT'` | - |

#### REFERENCE_VG (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 1 | `VG5` | - |

#### OTHER (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 13 | `[J]` | - |
| OTHER | 3 | `P.Vol date [B]` | - |
| OTHER | 2 | `P.Vol aller retour [A]` | - |

#### CONCATENATION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 7 | `MlsTrans('Select flight : Flight code')&' '&Trim(P.Code vol [C])&' '&MlsTrans('Flight time')&' '&Trim(P.Vol heure [D])` | - |
| CONCATENATION | 9 | `MlsTrans('FLIGHT')&' '&IF(P.Vol aller retour [A]='A',MlsTrans('INBOUND'),MlsTrans('OUTBOUND'))` | - |

#### NEGATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| NEGATION | 14 | `NOT EmptyDataview(0)` | - |

#### STRING (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| STRING | 12 | `Str ([K],'2P0')&':00'` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Affichage validation (IDE 64)](WEL-IDE-64.md) -> **Zoom village/village (IDE 107)**

Main -> ... -> [  Avancement Personnel (IDE 66)](WEL-IDE-66.md) -> **Zoom village/village (IDE 107)**

Main -> ... -> [  Interruption Personnel (IDE 67)](WEL-IDE-67.md) -> **Zoom village/village (IDE 107)**

Main -> ... -> [  Prolongation Personnel (IDE 69)](WEL-IDE-69.md) -> **Zoom village/village (IDE 107)**

```mermaid
graph LR
    T107[107 Zoom villagevillage]
    style T107 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC34[34 Lancement]
    style CC34 fill:#f59e0b
    CC55[55 Mobile Welcome]
    style CC55 fill:#f59e0b
    CC9[9 Clients]
    style CC9 fill:#f59e0b
    CC63[63 Validation sejour]
    style CC63 fill:#f59e0b
    CC66[66 Avancement Personnel]
    style CC66 fill:#3fb950
    CC64[64 Affichage validation]
    style CC64 fill:#3fb950
    CC69[69 Prolongation Personnel]
    style CC69 fill:#3fb950
    CC67[67 Interruption Personnel]
    style CC67 fill:#3fb950
    CC63 --> CC64
    CC9 --> CC64
    CC63 --> CC66
    CC9 --> CC66
    CC63 --> CC67
    CC9 --> CC67
    CC63 --> CC69
    CC9 --> CC69
    CC55 --> CC63
    CC55 --> CC9
    CC34 --> CC55
    CC1 --> CC34
    CC64 --> T107
    CC66 --> T107
    CC67 --> T107
    CC69 --> T107
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [64](WEL-IDE-64.md) | Affichage validation | 2 |
| [66](WEL-IDE-66.md) |   Avancement Personnel | 1 |
| [67](WEL-IDE-67.md) |   Interruption Personnel | 1 |
| [69](WEL-IDE-69.md) |   Prolongation Personnel | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T107[107 Zoom villagevillage]
    style T107 fill:#58a6ff
    C81[81 Create logbook]
    T107 --> C81
    style C81 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [81](WEL-IDE-81.md) | Create logbook | 2 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 20 | Programme compact |
| Expressions | 15 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 1 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 20) | Code sain |
| Regles metier | 1 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Consultation (1 tache: 1 ecran, 0 traitement)

- **Strategie** : Composants de recherche/selection en modales.
- 1 ecran : Zoom village/village

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| [Create logbook (IDE 81)](WEL-IDE-81.md) | Sous-programme | 2x | Haute - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 21:48*
