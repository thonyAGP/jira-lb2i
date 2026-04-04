# PBP IDE 206 - Liste des Easy Check-In

> **Analyse**: Phases 1-4 2026-02-03 15:48 -> 15:48 (12s) | Assemblage 15:48
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBP |
| IDE Position | 206 |
| Nom Programme | Liste des Easy Check-In |
| Fichier source | `Prg_206.xml` |
| Dossier IDE | Liste |
| Taches | 3 (1 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |
| :warning: Statut | **ORPHELIN_POTENTIEL** |

## 2. DESCRIPTION FONCTIONNELLE

**Liste des Easy Check-In** assure la gestion complete de ce processus.

Le flux de traitement s'organise en **2 blocs fonctionnels** :

- **Traitement** (2 taches) : traitements metier divers
- **Impression** (1 tache) : generation de tickets et documents

**Logique metier** : 2 regles identifiees couvrant conditions metier.

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (2 taches)

- **206** - Liste des Easy Check-In **[[ECRAN]](#ecran-t1)**
- **206.1** - Check Nbre Lignes **[[ECRAN]](#ecran-t2)**

#### Phase 2 : Impression (1 tache)

- **206.2** - Edition

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (2 taches)

Traitements internes.

---

#### <a id="t1"></a>206 - Liste des Easy Check-In [[ECRAN]](#ecran-t1)

**Role** : Traitement : Liste des Easy Check-In.
**Ecran** : 605 x 183 DLU (MDI) | [Voir mockup](#ecran-t1)

---

#### <a id="t2"></a>206.1 - Check Nbre Lignes [[ECRAN]](#ecran-t2)

**Role** : Traitement : Check Nbre Lignes.
**Ecran** : 312 x 71 DLU | [Voir mockup](#ecran-t2)


### 3.2 Impression (1 tache)

Generation des documents et tickets.

---

#### <a id="t3"></a>206.2 - Edition

**Role** : Generation du document : Edition.


## 5. REGLES METIER

2 regles identifiees:

### Autres (2 regles)

#### <a id="rm-RM-001"></a>[RM-001] Si w0_choix [D]='A' alors 'and [gmr_debut_sejour]='&''''&DStr(w0_Date [B] sinon 'YYYYMMDD')&'''', IF(w0_choix [D]='B','and [gmr_debut_sejour]<='&''''&DStr(w0_Date [B],'YYYYMMDD')&''''&' and [gmr_fin_sejour]>='&''''&DStr(w0_Date [B],'YYYYMMDD')&''''&' and [gmr_acces]='&''''&'O'&'''', IF(w0_choix [D]='C',' and [gmr_fin_sejour]='&''''&DStr(w0_Date [B],'YYYYMMDD')&''''&' and [gmr_acces]='&''''&'O'&'''','')))

| Element | Detail |
|---------|--------|
| **Condition** | `w0_choix [D]='A'` |
| **Si vrai** | 'and [gmr_debut_sejour]='&''''&DStr(w0_Date [B] |
| **Si faux** | 'YYYYMMDD')&'''', IF(w0_choix [D]='B','and [gmr_debut_sejour]<='&''''&DStr(w0_Date [B],'YYYYMMDD')&''''&' and [gmr_fin_sejour]>='&''''&DStr(w0_Date [B],'YYYYMMDD')&''''&' and [gmr_acces]='&''''&'O'&'''', IF(w0_choix [D]='C',' and [gmr_fin_sejour]='&''''&DStr(w0_Date [B],'YYYYMMDD')&''''&' and [gmr_acces]='&''''&'O'&'''',''))) |
| **Variables** | B (w0_Date), D (w0_choix) |
| **Expression source** | Expression 23 : `IF(w0_choix [D]='A','and [gmr_debut_sejour]='&''''&DStr(w0_D` |
| **Exemple** | Si w0_choix [D]='A' â†’ 'and [gmr_debut_sejour]='&''''&DStr(w0_Date [B] |

#### <a id="rm-RM-002"></a>[RM-002] Condition toujours vraie (flag actif)

| Element | Detail |
|---------|--------|
| **Condition** | `b.Filiations [G]='TRUE'LOG` |
| **Si vrai** | ' and [dga_num_dossier_na]='&''''&'''' |
| **Si faux** | '') |
| **Variables** | G (b.Filiations) |
| **Expression source** | Expression 24 : `IF(b.Filiations [G]='TRUE'LOG,' and [dga_num_dossier_na]='&'` |
| **Exemple** | Si b.Filiations [G]='TRUE'LOG â†’ ' and [dga_num_dossier_na]='&''''&''''. Sinon â†’ '') |

## 6. CONTEXTE

- **Appele par**: (aucun)
- **Appelle**: 0 programmes | **Tables**: 0 (W:0 R:0 L:0) | **Taches**: 3 | **Expressions**: 26

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 3)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 206 | 206 | Liste des Easy Check-In | MDI | 605 | 183 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>206 - Liste des Easy Check-In
**Tache** : [206](#t1) | **Type** : MDI | **Dimensions** : 605 x 183 DLU
**Bloc** : Traitement | **Titre IDE** : Liste des Easy Check-In

<!-- FORM-DATA:
{
    "width":  605,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  593,
                         "fmt":  "",
                         "name":  "",
                         "h":  19,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  4,
                         "type":  "label",
                         "var":  "",
                         "y":  156,
                         "w":  593,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  40,
                         "type":  "label",
                         "var":  "",
                         "y":  24,
                         "w":  330,
                         "fmt":  "",
                         "name":  "",
                         "h":  127,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  99,
                         "type":  "label",
                         "var":  "",
                         "y":  33,
                         "w":  30,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Le",
                         "parent":  6
                     },
                     {
                         "x":  45,
                         "type":  "line",
                         "var":  "",
                         "y":  50,
                         "w":  323,
                         "fmt":  "",
                         "name":  "",
                         "h":  0,
                         "color":  "",
                         "text":  "",
                         "parent":  6
                     },
                     {
                         "x":  45,
                         "type":  "line",
                         "var":  "",
                         "y":  127,
                         "w":  323,
                         "fmt":  "",
                         "name":  "",
                         "h":  0,
                         "color":  "",
                         "text":  "",
                         "parent":  6
                     },
                     {
                         "x":  99,
                         "type":  "label",
                         "var":  "",
                         "y":  136,
                         "w":  116,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "Sélections",
                         "parent":  6
                     },
                     {
                         "x":  378,
                         "type":  "label",
                         "var":  "",
                         "y":  24,
                         "w":  186,
                         "fmt":  "",
                         "name":  "",
                         "h":  127,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  136,
                         "type":  "edit",
                         "var":  "",
                         "y":  33,
                         "w":  126,
                         "fmt":  "DD/MM/YYYY",
                         "name":  "w0_Date",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  6
                     },
                     {
                         "x":  264,
                         "type":  "button",
                         "var":  "",
                         "y":  33,
                         "w":  27,
                         "fmt":  "...",
                         "name":  "b_Date",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  6
                     },
                     {
                         "x":  107,
                         "type":  "radio",
                         "var":  "",
                         "y":  64,
                         "w":  199,
                         "fmt":  "",
                         "name":  "w0_choix",
                         "h":  47,
                         "color":  "",
                         "text":  "A,B,C",
                         "parent":  6
                     },
                     {
                         "x":  235,
                         "type":  "edit",
                         "var":  "",
                         "y":  136,
                         "w":  56,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  6
                     },
                     {
                         "x":  394,
                         "type":  "button",
                         "var":  "",
                         "y":  88,
                         "w":  154,
                         "fmt":  "\u0026Ecran",
                         "name":  "b_Ecran",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  17
                     },
                     {
                         "x":  394,
                         "type":  "button",
                         "var":  "",
                         "y":  108,
                         "w":  154,
                         "fmt":  "\u0026Impression",
                         "name":  "b_Imprimer",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  17
                     },
                     {
                         "x":  6,
                         "type":  "edit",
                         "var":  "",
                         "y":  2,
                         "w":  267,
                         "fmt":  "30",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  383,
                         "type":  "edit",
                         "var":  "",
                         "y":  6,
                         "w":  203,
                         "fmt":  "WWW DD MMM YYYYT",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  6,
                         "type":  "edit",
                         "var":  "",
                         "y":  10,
                         "w":  358,
                         "fmt":  "50",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  402,
                         "type":  "image",
                         "var":  "",
                         "y":  29,
                         "w":  136,
                         "fmt":  "",
                         "name":  "",
                         "h":  54,
                         "color":  "",
                         "text":  "",
                         "parent":  17
                     },
                     {
                         "x":  12,
                         "type":  "button",
                         "var":  "",
                         "y":  159,
                         "w":  154,
                         "fmt":  "\u0026Quitter",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  394,
                         "type":  "button",
                         "var":  "",
                         "y":  128,
                         "w":  154,
                         "fmt":  "\u0026Excel",
                         "name":  "b_Excel",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "206",
    "height":  183
}
-->

<details>
<summary><strong>Champs : 5 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 136,33 | w0_Date | - | edit |
| 235,136 | (sans nom) | - | edit |
| 6,2 | 30 | - | edit |
| 383,6 | WWW DD MMM YYYYT | - | edit |
| 6,10 | 50 | - | edit |

</details>

<details>
<summary><strong>Boutons : 5 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| ... | 264,33 | Bouton fonctionnel |
| Ecran | 394,88 | Bouton fonctionnel |
| Impression | 394,108 | Bouton fonctionnel |
| Quitter | 12,159 | Quitte le programme |
| Excel | 394,128 | Bouton fonctionnel |

</details>

## 9. NAVIGATION

Ecran unique: **Liste des Easy Check-In**

### 9.3 Structure hierarchique (3 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **206.1** | [**Liste des Easy Check-In** (206)](#t1) [mockup](#ecran-t1) | MDI | 605x183 | Traitement |
| 206.1.1 | [Check Nbre Lignes (206.1)](#t2) [mockup](#ecran-t2) | - | 312x71 | |
| **206.2** | [**Edition** (206.2)](#t3) | MDI | - | Impression |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Traitement principal]
    DECISION{w0_Date}
    PROCESS[Traitement]
    ENDOK([END OK])
    ENDKO([END KO])

    START --> INIT --> SAISIE --> DECISION
    DECISION -->|OUI| PROCESS
    DECISION -->|NON| ENDKO
    PROCESS --> ENDOK

    style START fill:#3fb950,color:#000
    style ENDOK fill:#3fb950,color:#000
    style ENDKO fill:#f85149,color:#fff
    style DECISION fill:#58a6ff,color:#000
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

### 11.1 Variables de session (9)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| L | v.Where_Filiation | Alpha | 1x session |
| M | v.Chemin | Alpha | - |
| N | v.Fichier | Alpha | 1x session |
| O | v.heb_Code_GM | Numeric | 1x session |
| P | v.Nom_Logement | Alpha | - |
| Q | v.Code_package | Alpha | - |
| R | v.Nom_Logement | Alpha | - |
| S | v.Code_package | Alpha | - |
| T | v.Ligne | Alpha | - |

### 11.2 Autres (11)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | w0_TitreEcran | Alpha | - |
| B | w0_Date | Date | 1x refs |
| C | b_Date | Alpha | - |
| D | w0_choix | Alpha | 3x refs |
| E | w0_NbSelect | Numeric | 2x refs |
| F | w0_NbFid | Numeric | - |
| G | b.Filiations | Logical | 1x refs |
| H | b_Ecran | Alpha | - |
| I | b_Imprimer | Alpha | - |
| J | b_Excel | Alpha | - |
| K | v_Where_Sejour | Alpha | - |

<details>
<summary>Toutes les 20 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| V. | **L** | v.Where_Filiation | Alpha |
| V. | **M** | v.Chemin | Alpha |
| V. | **N** | v.Fichier | Alpha |
| V. | **O** | v.heb_Code_GM | Numeric |
| V. | **P** | v.Nom_Logement | Alpha |
| V. | **Q** | v.Code_package | Alpha |
| V. | **R** | v.Nom_Logement | Alpha |
| V. | **S** | v.Code_package | Alpha |
| V. | **T** | v.Ligne | Alpha |
| Autre | **A** | w0_TitreEcran | Alpha |
| Autre | **B** | w0_Date | Date |
| Autre | **C** | b_Date | Alpha |
| Autre | **D** | w0_choix | Alpha |
| Autre | **E** | w0_NbSelect | Numeric |
| Autre | **F** | w0_NbFid | Numeric |
| Autre | **G** | b.Filiations | Logical |
| Autre | **H** | b_Ecran | Alpha |
| Autre | **I** | b_Imprimer | Alpha |
| Autre | **J** | b_Excel | Alpha |
| Autre | **K** | v_Where_Sejour | Alpha |

</details>

## 12. EXPRESSIONS

**26 / 26 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONCATENATION | 2 | 0 |
| CONDITION | 4 | 5 |
| CAST_LOGIQUE | 5 | 5 |
| CONSTANTE | 6 | 0 |
| FORMAT | 1 | 0 |
| DATE | 1 | 0 |
| REFERENCE_VG | 1 | 0 |
| OTHER | 5 | 0 |
| STRING | 1 | 0 |

### 12.2 Expressions cles par type

#### CONCATENATION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 9 | `Trim(v.Fichier [N])&Trim(v.heb_Code_GM [O])` | - |
| CONCATENATION | 3 | `w0_choix [D]&' - '&Trim (v.Where_Filiation [L])` | - |

#### CONDITION (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 23 | `IF(w0_choix [D]='A','and [gmr_debut_sejour]='&''''&DStr(w0_Date [B],'YYYYMMDD')&'''', IF(w0_choix [D]='B','and [gmr_debut_sejour]<='&''''&DStr(w0_Date [B],'YYYYMMDD')&''''&' and [gmr_fin_sejour]>='&''''&DStr(w0_Date [B],'YYYYMMDD')&''''&' and [gmr_acces]='&''''&'O'&'''', IF(w0_choix [D]='C',' and [gmr_fin_sejour]='&''''&DStr(w0_Date [B],'YYYYMMDD')&''''&' and [gmr_acces]='&''''&'O'&'''','')))` | [RM-001](#rm-RM-001) |
| CONDITION | 25 | `w0_choix [D]<>''` | - |
| CONDITION | 19 | `w0_NbSelect [E]>0` | - |
| CONDITION | 17 | `w0_NbSelect [E]=0` | - |

#### CAST_LOGIQUE (5 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 24 | `IF(b.Filiations [G]='TRUE'LOG,' and [dga_num_dossier_na]='&''''&'''','')` | [RM-002](#rm-RM-002) |
| CAST_LOGIQUE | 21 | `'FALSE'LOG` | - |
| CAST_LOGIQUE | 22 | `'TRUE'LOG` | - |
| CAST_LOGIQUE | 1 | `'TRUE'LOG` | - |
| CAST_LOGIQUE | 2 | `'FALSE'LOG` | - |

#### CONSTANTE (6 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 7 | `'&Excel'` | - |
| CONSTANTE | 18 | `0` | - |
| CONSTANTE | 20 | `'A'` | - |
| CONSTANTE | 4 | `'...'` | - |
| CONSTANTE | 5 | `'&Ecran'` | - |
| ... | | *+1 autres* | |

#### FORMAT (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| FORMAT | 12 | `'EASY_CHECK-IN_'&DStr(Date(),'YYMMDD')&TStr(Time(),'HHMMSS')&'.pdf'` | - |

#### DATE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| DATE | 13 | `Date()` | - |

#### REFERENCE_VG (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 8 | `VG2` | - |

#### OTHER (5 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 15 | `SetCrsr (1)` | - |
| OTHER | 16 | `GetParam ('VILLAGE')` | - |
| OTHER | 14 | `SetCrsr (2)` | - |
| OTHER | 10 | `Translate('%TempDir%')&'Easy_CheckIn.csv'` | - |
| OTHER | 11 | `Translate('%TempDir%')` | - |

#### STRING (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| STRING | 26 | `Trim({1,12})` | - |

### 12.3 Toutes les expressions (26)

<details>
<summary>Voir les 26 expressions</summary>

#### CONCATENATION (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 3 | `w0_choix [D]&' - '&Trim (v.Where_Filiation [L])` |
| 9 | `Trim(v.Fichier [N])&Trim(v.heb_Code_GM [O])` |

#### CONDITION (4)

| IDE | Expression Decodee |
|-----|-------------------|
| 23 | `IF(w0_choix [D]='A','and [gmr_debut_sejour]='&''''&DStr(w0_Date [B],'YYYYMMDD')&'''', IF(w0_choix [D]='B','and [gmr_debut_sejour]<='&''''&DStr(w0_Date [B],'YYYYMMDD')&''''&' and [gmr_fin_sejour]>='&''''&DStr(w0_Date [B],'YYYYMMDD')&''''&' and [gmr_acces]='&''''&'O'&'''', IF(w0_choix [D]='C',' and [gmr_fin_sejour]='&''''&DStr(w0_Date [B],'YYYYMMDD')&''''&' and [gmr_acces]='&''''&'O'&'''','')))` |
| 17 | `w0_NbSelect [E]=0` |
| 19 | `w0_NbSelect [E]>0` |
| 25 | `w0_choix [D]<>''` |

#### CAST_LOGIQUE (5)

| IDE | Expression Decodee |
|-----|-------------------|
| 24 | `IF(b.Filiations [G]='TRUE'LOG,' and [dga_num_dossier_na]='&''''&'''','')` |
| 1 | `'TRUE'LOG` |
| 2 | `'FALSE'LOG` |
| 21 | `'FALSE'LOG` |
| 22 | `'TRUE'LOG` |

#### CONSTANTE (6)

| IDE | Expression Decodee |
|-----|-------------------|
| 4 | `'...'` |
| 5 | `'&Ecran'` |
| 6 | `'&Imprimer'` |
| 7 | `'&Excel'` |
| 18 | `0` |
| 20 | `'A'` |

#### FORMAT (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 12 | `'EASY_CHECK-IN_'&DStr(Date(),'YYMMDD')&TStr(Time(),'HHMMSS')&'.pdf'` |

#### DATE (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 13 | `Date()` |

#### REFERENCE_VG (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 8 | `VG2` |

#### OTHER (5)

| IDE | Expression Decodee |
|-----|-------------------|
| 10 | `Translate('%TempDir%')&'Easy_CheckIn.csv'` |
| 11 | `Translate('%TempDir%')` |
| 14 | `SetCrsr (2)` |
| 15 | `SetCrsr (1)` |
| 16 | `GetParam ('VILLAGE')` |

#### STRING (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 26 | `Trim({1,12})` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

**Chemin**: (pas de callers directs)

```mermaid
graph LR
    T206[206 Liste des Easy Che...]
    style T206 fill:#58a6ff
    NONE[Aucun caller]
    NONE -.-> T206
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| - | (aucun) | - |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T206[206 Liste des Easy Che...]
    style T206 fill:#58a6ff
    NONE[Aucun callee]
    T206 -.-> NONE
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
| Lignes de logique | 107 | Programme compact |
| Expressions | 26 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 4.7% (5 / 107) | Code sain |
| Regles metier | 2 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (2 taches: 2 ecrans, 0 traitement)

- **Strategie** : 2 composant(s) UI (Razor/React) avec formulaires et validation.
- Decomposer les taches en services unitaires testables.

#### Impression (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Templates HTML -> PDF via wkhtmltopdf ou Puppeteer.
- `PrintService` injectable avec choix imprimante

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 15:48*
