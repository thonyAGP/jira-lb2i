# WEL IDE 83 - Saisie Signature Validation

> **Analyse**: Phases 1-4 2026-02-03 21:37 -> 21:38 (19s) | Assemblage 21:38
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | WEL |
| IDE Position | 83 |
| Nom Programme | Saisie Signature Validation |
| Fichier source | `Prg_83.xml` |
| Dossier IDE | Utilitaires |
| Taches | 2 (2 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 1 |

## 2. DESCRIPTION FONCTIONNELLE

**Saisie Signature Validation** assure la gestion complete de ce processus, accessible depuis [Ventes (IDE 96)](WEL-IDE-96.md), [Ventes *Sav au 02/07/2018 (IDE 116)](WEL-IDE-116.md), [Ventes *Sav au 04/07/2018 (IDE 117)](WEL-IDE-117.md).

Le flux de traitement s'organise en **2 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers
- **Saisie** (1 tache) : ecrans de saisie utilisateur (formulaires, champs, donnees)

**Logique metier** : 1 regles identifiees couvrant conditions metier.

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Saisie (1 tache)

- **83** - Saisie Signature Validation **[[ECRAN]](#ecran-t1)**

Delegue a : [Saisie email (IDE 10)](WEL-IDE-10.md)

#### Phase 2 : Traitement (1 tache)

- **83.1** - Confirmation **[[ECRAN]](#ecran-t9)**

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Saisie (1 tache)

L'operateur saisit les donnees de la transaction via 1 ecran (Saisie Signature Validation).

---

#### <a id="t1"></a>83 - Saisie Signature Validation [[ECRAN]](#ecran-t1)

**Role** : Saisie des donnees : Saisie Signature Validation.
**Ecran** : 1313 x 744 DLU (MDI) | [Voir mockup](#ecran-t1)
**Delegue a** : [Saisie email (IDE 10)](WEL-IDE-10.md)


### 3.2 Traitement (1 tache)

Traitements internes.

---

#### <a id="t9"></a>83.1 - Confirmation [[ECRAN]](#ecran-t9)

**Role** : Traitement : Confirmation.
**Ecran** : 598 x 220 DLU (Type6) | [Voir mockup](#ecran-t9)
**Variables liees** : U (confirmationRetour)


## 5. REGLES METIER

1 regles identifiees:

### Autres (1 regles)

#### <a id="rm-RM-001"></a>[RM-001] Condition toujours vraie (flag actif)

| Element | Detail |
|---------|--------|
| **Condition** | `p.Receive-Recept ? [F]='TRUE'LOG` |
| **Si vrai** | '√' |
| **Si faux** | ' ') |
| **Variables** | F (p.Receive-Recept ?) |
| **Expression source** | Expression 7 : `IF(p.Receive-Recept ? [F]='TRUE'LOG,'√',' ')` |
| **Exemple** | Si p.Receive-Recept ? [F]='TRUE'LOG â†’ '√'. Sinon â†’ ' ') |

## 6. CONTEXTE

- **Appele par**: [Ventes (IDE 96)](WEL-IDE-96.md), [Ventes *Sav au 02/07/2018 (IDE 116)](WEL-IDE-116.md), [Ventes *Sav au 04/07/2018 (IDE 117)](WEL-IDE-117.md)
- **Appelle**: 1 programmes | **Tables**: 0 (W:0 R:0 L:0) | **Taches**: 2 | **Expressions**: 39

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (2 / 2)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 83 | 83 | Saisie Signature Validation | MDI | 1313 | 744 | Saisie |
| 2 | 83.1 | 83.1 | Confirmation | Type6 | 598 | 220 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>83 - Saisie Signature Validation
**Tache** : [83](#t1) | **Type** : MDI | **Dimensions** : 1313 x 744 DLU
**Bloc** : Saisie | **Titre IDE** : Saisie Signature Validation

<!-- FORM-DATA:
{
    "width":  1313,
    "vFactor":  100,
    "type":  "MDI",
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
                         "text":  "SIGNATURE",
                         "parent":  null
                     },
                     {
                         "x":  34,
                         "type":  "label",
                         "var":  "",
                         "y":  189,
                         "w":  1245,
                         "fmt":  "",
                         "name":  "",
                         "h":  44,
                         "color":  "220",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  229,
                         "type":  "label",
                         "var":  "",
                         "y":  189,
                         "w":  181,
                         "fmt":  "",
                         "name":  "",
                         "h":  44,
                         "color":  "220",
                         "text":  "DECLINE E-Receipt",
                         "parent":  null
                     },
                     {
                         "x":  34,
                         "type":  "label",
                         "var":  "",
                         "y":  233,
                         "w":  1245,
                         "fmt":  "",
                         "name":  "",
                         "h":  32,
                         "color":  "",
                         "text":  "Signature  required  to validate purchase",
                         "parent":  null
                     },
                     {
                         "x":  39,
                         "type":  "label",
                         "var":  "",
                         "y":  189,
                         "w":  181,
                         "fmt":  "",
                         "name":  "",
                         "h":  44,
                         "color":  "220",
                         "text":  "RECEIPT SIGNATURE",
                         "parent":  4
                     },
                     {
                         "x":  433,
                         "type":  "label",
                         "var":  "",
                         "y":  111,
                         "w":  446,
                         "fmt":  "",
                         "name":  "",
                         "h":  44,
                         "color":  "227",
                         "text":  "you have to sign before entering an email !",
                         "parent":  null
                     },
                     {
                         "x":  34,
                         "type":  "edit",
                         "var":  "",
                         "y":  267,
                         "w":  1245,
                         "fmt":  "",
                         "name":  "Signature",
                         "h":  286,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  470,
                         "type":  "combobox",
                         "var":  "",
                         "y":  194,
                         "w":  740,
                         "fmt":  "",
                         "name":  "p.Email address",
                         "h":  30,
                         "color":  "219",
                         "text":  "",
                         "parent":  null
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
                         "x":  418,
                         "type":  "checkbox",
                         "var":  "",
                         "y":  189,
                         "w":  46,
                         "fmt":  "",
                         "name":  "v.Receive-Recept ?",
                         "h":  44,
                         "color":  "219",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  1218,
                         "type":  "edit",
                         "var":  "",
                         "y":  189,
                         "w":  46,
                         "fmt":  "+",
                         "name":  "B Change",
                         "h":  44,
                         "color":  "214",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  462,
                         "type":  "edit",
                         "var":  "",
                         "y":  562,
                         "w":  173,
                         "fmt":  "30",
                         "name":  "ERASE",
                         "h":  79,
                         "color":  "214",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  693,
                         "type":  "edit",
                         "var":  "",
                         "y":  562,
                         "w":  173,
                         "fmt":  "30",
                         "name":  "BtnValider",
                         "h":  79,
                         "color":  "214",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "83",
    "height":  744
}
-->

<details>
<summary><strong>Champs : 6 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 34,267 | Signature | - | edit |
| 470,194 | p.Email address | - | combobox |
| 418,189 | v.Receive-Recept ? | - | checkbox |
| 1218,189 | B Change | - | edit |
| 462,562 | ERASE | - | edit |
| 693,562 | BtnValider | - | edit |

</details>

---

#### <a id="ecran-t9"></a>83.1 - Confirmation
**Tache** : [83.1](#t9) | **Type** : Type6 | **Dimensions** : 598 x 220 DLU
**Bloc** : Traitement | **Titre IDE** : Confirmation

<!-- FORM-DATA:
{
    "width":  598,
    "vFactor":  100,
    "type":  "Type6",
    "hFactor":  100,
    "controls":  [
                     {
                         "x":  78,
                         "type":  "label",
                         "var":  "",
                         "y":  45,
                         "w":  441,
                         "fmt":  "",
                         "name":  "",
                         "h":  47,
                         "color":  "181",
                         "text":  "you are leaving without signing. do you want to continue ?",
                         "parent":  null
                     },
                     {
                         "x":  310,
                         "type":  "edit",
                         "var":  "",
                         "y":  114,
                         "w":  148,
                         "fmt":  "Yes",
                         "name":  "Yes",
                         "h":  57,
                         "color":  "214",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  127,
                         "type":  "edit",
                         "var":  "",
                         "y":  114,
                         "w":  148,
                         "fmt":  "No",
                         "name":  "No",
                         "h":  57,
                         "color":  "214",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "83.1",
    "height":  220
}
-->

<details>
<summary><strong>Champs : 2 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 310,114 | Yes | - | edit |
| 127,114 | No | - | edit |

</details>

## 9. NAVIGATION

### 9.1 Enchainement des ecrans

```mermaid
flowchart TD
    START([Entree])
    style START fill:#3fb950
    VF1[83 Saisie Signature Va...]
    style VF1 fill:#58a6ff
    VF9[83.1 Confirmation]
    style VF9 fill:#58a6ff
    EXT10[IDE 10 Saisie email]
    style EXT10 fill:#3fb950
    FIN([Sortie])
    style FIN fill:#f85149
    START --> VF1
    VF1 -->|Sous-programme| EXT10
    EXT10 --> FIN
```

**Detail par enchainement :**

| Depuis | Action | Vers | Retour |
|--------|--------|------|--------|
| Saisie Signature Validation | Sous-programme | [Saisie email (IDE 10)](WEL-IDE-10.md) | Retour ecran |

### 9.3 Structure hierarchique (2 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **83.1** | [**Saisie Signature Validation** (83)](#t1) [mockup](#ecran-t1) | MDI | 1313x744 | Saisie |
| **83.2** | [**Confirmation** (83.1)](#t9) [mockup](#ecran-t9) | Type6 | 598x220 | Traitement |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Retour confirmation]
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

### Tables utilisees (0)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|

### Colonnes par table (0 / 0 tables avec colonnes identifiees)

## 11. VARIABLES

### 11.1 Parametres entrants (9)

Variables recues du programme appelant ([Ventes (IDE 96)](WEL-IDE-96.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | p.Ste | Alpha | 1x parametre entrant |
| B | p.Compte | Numeric | 1x parametre entrant |
| C | p.Filiation | Numeric | 1x parametre entrant |
| D | p.Filename | Alpha | 1x parametre entrant |
| E | p.Email address | Alpha | 2x parametre entrant |
| F | p.Receive-Recept ? | Logical | 3x parametre entrant |
| G | p.Continue | Logical | 2x parametre entrant |
| H | p.nb strokes | Alpha | 1x parametre entrant |
| I | p.Valider? | Logical | - |

### 11.2 Variables de session (11)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| J | v.Ste | Alpha | 3x session |
| K | v.Compte | Numeric | - |
| L | v.Filiation | Numeric | - |
| M | v.Filename | Alpha | 1x session |
| N | v.Email address | Alpha | - |
| O | v.Receive-Recept ? | Logical | - |
| P | v.Continue | Logical | - |
| Q | v.nb strokes | Alpha | 1x session |
| R | v.Decline Receive_Mail | Logical | 1x session |
| S | v.InkPicture1 | Blob | 1x session |
| T | v.Envoi | Logical | 1x session |

### 11.3 Autres (1)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| U | confirmationRetour | Logical | 1x refs |

<details>
<summary>Toutes les 21 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| P0 | **A** | p.Ste | Alpha |
| P0 | **B** | p.Compte | Numeric |
| P0 | **C** | p.Filiation | Numeric |
| P0 | **D** | p.Filename | Alpha |
| P0 | **E** | p.Email address | Alpha |
| P0 | **F** | p.Receive-Recept ? | Logical |
| P0 | **G** | p.Continue | Logical |
| P0 | **H** | p.nb strokes | Alpha |
| P0 | **I** | p.Valider? | Logical |
| V. | **J** | v.Ste | Alpha |
| V. | **K** | v.Compte | Numeric |
| V. | **L** | v.Filiation | Numeric |
| V. | **M** | v.Filename | Alpha |
| V. | **N** | v.Email address | Alpha |
| V. | **O** | v.Receive-Recept ? | Logical |
| V. | **P** | v.Continue | Logical |
| V. | **Q** | v.nb strokes | Alpha |
| V. | **R** | v.Decline Receive_Mail | Logical |
| V. | **S** | v.InkPicture1 | Blob |
| V. | **T** | v.Envoi | Logical |
| Autre | **U** | confirmationRetour | Logical |

</details>

## 12. EXPRESSIONS

**39 / 39 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONCATENATION | 1 | 0 |
| CALCULATION | 1 | 0 |
| CAST_LOGIQUE | 5 | 5 |
| CONSTANTE | 1 | 0 |
| OTHER | 25 | 0 |
| NEGATION | 1 | 0 |
| REFERENCE_VG | 2 | 0 |
| CONDITION | 3 | 0 |

### 12.2 Expressions cles par type

#### CONCATENATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 3 | `'cmd /c mkdir '&Translate ('%club_exportdata%')&'Welcome\images\'` | - |

#### CALCULATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 14 | `MlsTrans('+')` | - |

#### CAST_LOGIQUE (5 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 7 | `IF(p.Receive-Recept ? [F]='TRUE'LOG,'√',' ')` | [RM-001](#rm-RM-001) |
| CAST_LOGIQUE | 21 | `'FALSE'LOG` | - |
| CAST_LOGIQUE | 22 | `'TRUE'LOG` | - |
| CAST_LOGIQUE | 5 | `'FALSE'LOG` | - |
| CAST_LOGIQUE | 17 | `'TRUE'LOG` | - |

#### CONSTANTE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 9 | `''` | - |

#### OTHER (25 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 31 | `[X]` | - |
| OTHER | 32 | `p.Ste [A]` | - |
| OTHER | 33 | `p.Compte [B]` | - |
| OTHER | 28 | `confirmationRetour [U]` | - |
| OTHER | 29 | `[V]` | - |
| ... | | *+20 autres* | |

#### NEGATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| NEGATION | 8 | `NOT p.Receive-Recept ? [F]` | - |

#### REFERENCE_VG (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 12 | `VG9` | - |
| REFERENCE_VG | 11 | `VG5` | - |

#### CONDITION (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 19 | `Trim(p.Email address [E]) = ''` | - |
| CONDITION | 18 | `v.Ste [J].Ink.Strokes.Count > 0` | - |
| CONDITION | 16 | `v.Ste [J].Ink.Strokes.Count = 0` | - |

### 12.3 Toutes les expressions (39)

<details>
<summary>Voir les 39 expressions</summary>

#### CONCATENATION (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 3 | `'cmd /c mkdir '&Translate ('%club_exportdata%')&'Welcome\images\'` |

#### CALCULATION (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 14 | `MlsTrans('+')` |

#### CAST_LOGIQUE (5)

| IDE | Expression Decodee |
|-----|-------------------|
| 7 | `IF(p.Receive-Recept ? [F]='TRUE'LOG,'√',' ')` |
| 5 | `'FALSE'LOG` |
| 17 | `'TRUE'LOG` |
| 21 | `'FALSE'LOG` |
| 22 | `'TRUE'LOG` |

#### CONSTANTE (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 9 | `''` |

#### OTHER (25)

| IDE | Expression Decodee |
|-----|-------------------|
| 1 | `p.Continue [G]` |
| 2 | `SetCrsr(1)` |
| 4 | `NOT(FileExist(Translate ('%club_exportdata%')&'Welcome\images\'))` |
| 6 | `SetCrsr(2)` |
| 10 | `v.Ste [J].Ink.Strokes.Count.ToString()` |
| 13 | `ASCIIChr(13)&MlsTrans('ERASE SIGNATURE')` |
| 15 | `MlsTrans('you have to sign before entering an email !')` |
| 20 | `ASCIIChr(13)&MlsTrans('VALIDATE')` |
| 23 | `v.Filename [M]` |
| 24 | `v.nb strokes [Q]` |
| 25 | `v.Decline Receive_Mail [R]` |
| 26 | `v.InkPicture1 [S]` |
| 27 | `v.Envoi [T]` |
| 28 | `confirmationRetour [U]` |
| 29 | `[V]` |
| 30 | `[W]` |
| 31 | `[X]` |
| 32 | `p.Ste [A]` |
| 33 | `p.Compte [B]` |
| 34 | `p.Filiation [C]` |
| 35 | `p.Filename [D]` |
| 36 | `p.Email address [E]` |
| 37 | `p.Receive-Recept ? [F]` |
| 38 | `p.Continue [G]` |
| 39 | `p.nb strokes [H]` |

#### NEGATION (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 8 | `NOT p.Receive-Recept ? [F]` |

#### REFERENCE_VG (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 11 | `VG5` |
| 12 | `VG9` |

#### CONDITION (3)

| IDE | Expression Decodee |
|-----|-------------------|
| 16 | `v.Ste [J].Ink.Strokes.Count = 0` |
| 18 | `v.Ste [J].Ink.Strokes.Count > 0` |
| 19 | `Trim(p.Email address [E]) = ''` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Ventes (IDE 96)](WEL-IDE-96.md) -> **Saisie Signature Validation (IDE 83)**

Main -> ... -> [Ventes *Sav au 02/07/2018 (IDE 116)](WEL-IDE-116.md) -> **Saisie Signature Validation (IDE 83)**

Main -> ... -> [Ventes *Sav au 04/07/2018 (IDE 117)](WEL-IDE-117.md) -> **Saisie Signature Validation (IDE 83)**

```mermaid
graph LR
    T83[83 Saisie Signature Va...]
    style T83 fill:#58a6ff
    CC95[95 Lancement ventes]
    style CC95 fill:#8b5cf6
    CC96[96 Ventes]
    style CC96 fill:#3fb950
    CC117[117 Ventes *Sav au 040...]
    style CC117 fill:#3fb950
    CC116[116 Ventes *Sav au 020...]
    style CC116 fill:#3fb950
    CC95 --> CC96
    CC95 --> CC116
    CC95 --> CC117
    CC96 --> T83
    CC116 --> T83
    CC117 --> T83
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [96](WEL-IDE-96.md) | Ventes | 1 |
| [116](WEL-IDE-116.md) | Ventes *Sav au 02/07/2018 | 1 |
| [117](WEL-IDE-117.md) | Ventes *Sav au 04/07/2018 | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T83[83 Saisie Signature Va...]
    style T83 fill:#58a6ff
    C10[10 Saisie email]
    T83 --> C10
    style C10 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [10](WEL-IDE-10.md) | Saisie email | 1 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 77 | Programme compact |
| Expressions | 39 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 1 | Peu de dependances |
| Ecrans visibles | 2 | Quelques ecrans |
| Code desactive | 1.3% (1 / 77) | Code sain |
| Regles metier | 1 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Saisie (1 tache: 1 ecran, 0 traitement)

- **Strategie** : Formulaire React/Blazor avec validation Zod/FluentValidation.
- Reproduire 1 ecran : Saisie Signature Validation
- Validation temps reel cote client + serveur

#### Traitement (1 tache: 1 ecran, 0 traitement)

- **Strategie** : 1 composant(s) UI (Razor/React) avec formulaires et validation.
- 1 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| [Saisie email (IDE 10)](WEL-IDE-10.md) | Sous-programme | 1x | Normale - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 21:38*
