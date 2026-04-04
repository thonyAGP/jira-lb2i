# PBP IDE 230 - Imprim pres plan GO

> **Analyse**: Phases 1-4 2026-02-03 15:56 -> 15:56 (18s) | Assemblage 15:56
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBP |
| IDE Position | 230 |
| Nom Programme | Imprim pres plan GO |
| Fichier source | `Prg_230.xml` |
| Dossier IDE | Liste |
| Taches | 3 (1 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Imprim pres plan GO** assure la gestion complete de ce processus, accessible depuis [  Liste present personnel plan (IDE 227)](PBP-IDE-227.md), [  Affichage pres plans GO (IDE 229)](PBP-IDE-229.md).

Le flux de traitement s'organise en **2 blocs fonctionnels** :

- **Traitement** (2 taches) : traitements metier divers
- **Calcul** (1 tache) : calculs de montants, stocks ou compteurs

**Logique metier** : 15 regles identifiees couvrant conditions metier.

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (2 taches)

- **230** - Veuillez patienter ... **[[ECRAN]](#ecran-t1)**
- **230.2** - Ligne commentaire

#### Phase 2 : Calcul (1 tache)

- **230.1** - Calcul pied

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (2 taches)

Traitements internes.

---

#### <a id="t1"></a>230 - Veuillez patienter ... [[ECRAN]](#ecran-t1)

**Role** : Traitement : Veuillez patienter ....
**Ecran** : 426 x 58 DLU (MDI) | [Voir mockup](#ecran-t1)

---

#### <a id="t3"></a>230.2 - Ligne commentaire

**Role** : Traitement : Ligne commentaire.
**Variables liees** : M (v.LigneExcel)


### 3.2 Calcul (1 tache)

Calculs metier : montants, stocks, compteurs.

---

#### <a id="t2"></a>230.1 - Calcul pied

**Role** : Calcul : Calcul pied.
**Variables liees** : A (>DateCalcul), N (w0_NomPied01), O (w0_NbPied01), P (w0_NomPied02), Q (w0_NbPied02)


## 5. REGLES METIER

15 regles identifiees:

### Autres (15 regles)

#### <a id="rm-RM-001"></a>[RM-001] Si >CodeListe [C]='A' alors 'arrivants' sinon IF (>CodeListe [C]='V','arrivees',IF (>CodeListe [C]='P','presents',IF (>CodeListe [C]='D','departs',IF (>CodeListe [C]='R','partants','absents')))))

| Element | Detail |
|---------|--------|
| **Condition** | `>CodeListe [C]='A'` |
| **Si vrai** | 'arrivants' |
| **Si faux** | IF (>CodeListe [C]='V','arrivees',IF (>CodeListe [C]='P','presents',IF (>CodeListe [C]='D','departs',IF (>CodeListe [C]='R','partants','absents'))))) |
| **Variables** | C (>CodeListe) |
| **Expression source** | Expression 15 : `IF (>CodeListe [C]='A','arrivants',IF (>CodeListe [C]='V','a` |
| **Exemple** | Si >CodeListe [C]='A' â†’ 'arrivants' |

#### <a id="rm-RM-002"></a>[RM-002] Si >TopListe [D]='PL' alors 'planning' sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='PL'` |
| **Si vrai** | 'planning' |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 16 : `IF (>TopListe [D]='PL','planning','')` |
| **Exemple** | Si >TopListe [D]='PL' â†’ 'planning'. Sinon â†’ '') |

#### <a id="rm-RM-003"></a>[RM-003] Si >TopListe [D]='GR' alors 'groupe' sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='GR'` |
| **Si vrai** | 'groupe' |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 17 : `IF (>TopListe [D]='GR','groupe','')` |
| **Exemple** | Si >TopListe [D]='GR' â†’ 'groupe'. Sinon â†’ '') |

#### <a id="rm-RM-004"></a>[RM-004] Si >TopListe [D]='CA' alors 'caisse' sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='CA'` |
| **Si vrai** | 'caisse' |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 18 : `IF (>TopListe [D]='CA','caisse','')` |
| **Exemple** | Si >TopListe [D]='CA' â†’ 'caisse'. Sinon â†’ '') |

#### <a id="rm-RM-005"></a>[RM-005] Si >TopListe [D]='MI' alors 'millesias' sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='MI'` |
| **Si vrai** | 'millesias' |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 19 : `IF (>TopListe [D]='MI','millesias','')` |
| **Exemple** | Si >TopListe [D]='MI' â†’ 'millesias'. Sinon â†’ '') |

#### <a id="rm-RM-006"></a>[RM-006] Si >TopListe [D]='BB' alors 'bebe' sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='BB'` |
| **Si vrai** | 'bebe' |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 20 : `IF (>TopListe [D]='BB','bebe','')` |
| **Exemple** | Si >TopListe [D]='BB' â†’ 'bebe'. Sinon â†’ '') |

#### <a id="rm-RM-007"></a>[RM-007] Si >TopListe [D]='EN' alors 'enfant' sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='EN'` |
| **Si vrai** | 'enfant' |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 21 : `IF (>TopListe [D]='EN','enfant','')` |
| **Exemple** | Si >TopListe [D]='EN' â†’ 'enfant'. Sinon â†’ '') |

#### <a id="rm-RM-008"></a>[RM-008] Si >TopListe [D]='SI' alors 'single' sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='SI'` |
| **Si vrai** | 'single' |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 22 : `IF (>TopListe [D]='SI','single','')` |
| **Exemple** | Si >TopListe [D]='SI' â†’ 'single'. Sinon â†’ '') |

#### <a id="rm-RM-009"></a>[RM-009] Si >TopListe [D]='NS' alors 'non single' sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='NS'` |
| **Si vrai** | 'non single' |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 23 : `IF (>TopListe [D]='NS','non single','')` |
| **Exemple** | Si >TopListe [D]='NS' â†’ 'non single'. Sinon â†’ '') |

#### <a id="rm-RM-010"></a>[RM-010] Si >TopListe [D]='PY' alors 'pays' sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='PY'` |
| **Si vrai** | 'pays' |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 24 : `IF (>TopListe [D]='PY','pays','')` |
| **Exemple** | Si >TopListe [D]='PY' â†’ 'pays'. Sinon â†’ '') |

#### <a id="rm-RM-011"></a>[RM-011] Si >TopListe [D]='HM' alors 'honey moon' sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='HM'` |
| **Si vrai** | 'honey moon' |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 25 : `IF (>TopListe [D]='HM','honey moon','')` |
| **Exemple** | Si >TopListe [D]='HM' â†’ 'honey moon'. Sinon â†’ '') |

#### <a id="rm-RM-012"></a>[RM-012] Si >TopListe [D]='VV' alors 'Vil/Vil' sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='VV'` |
| **Si vrai** | 'Vil/Vil' |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 26 : `IF (>TopListe [D]='VV','Vil/Vil','')` |
| **Exemple** | Si >TopListe [D]='VV' â†’ 'Vil/Vil'. Sinon â†’ '') |

#### <a id="rm-RM-013"></a>[RM-013] Si >TopListe [D]='NV' alors 'non Vil/Vil' sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='NV'` |
| **Si vrai** | 'non Vil/Vil' |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 27 : `IF (>TopListe [D]='NV','non Vil/Vil','')` |
| **Exemple** | Si >TopListe [D]='NV' â†’ 'non Vil/Vil'. Sinon â†’ '') |

#### <a id="rm-RM-014"></a>[RM-014] Si >TopListe [D]='AG' alors 'age' sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='AG'` |
| **Si vrai** | 'age' |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 28 : `IF (>TopListe [D]='AG','age','')` |
| **Exemple** | Si >TopListe [D]='AG' â†’ 'age'. Sinon â†’ '') |

#### <a id="rm-RM-015"></a>[RM-015] Si >TopListe [D]='CO' alors 'commentaire' sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='CO'` |
| **Si vrai** | 'commentaire' |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 29 : `IF (>TopListe [D]='CO','commentaire','')` |
| **Exemple** | Si >TopListe [D]='CO' â†’ 'commentaire'. Sinon â†’ '') |

## 6. CONTEXTE

- **Appele par**: [  Liste present personnel plan (IDE 227)](PBP-IDE-227.md), [  Affichage pres plans GO (IDE 229)](PBP-IDE-229.md)
- **Appelle**: 0 programmes | **Tables**: 4 (W:0 R:3 L:1) | **Taches**: 3 | **Expressions**: 38

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 3)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 230 | 230 | Veuillez patienter ... | MDI | 426 | 58 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>230 - Veuillez patienter ...
**Tache** : [230](#t1) | **Type** : MDI | **Dimensions** : 426 x 58 DLU
**Bloc** : Traitement | **Titre IDE** : Veuillez patienter ...

<!-- FORM-DATA:
{
    "width":  426,
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
                         "w":  267,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Impression en cours",
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
    "taskId":  "230",
    "height":  58
}
-->

## 9. NAVIGATION

Ecran unique: **Veuillez patienter ...**

### 9.3 Structure hierarchique (3 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **230.1** | [**Veuillez patienter ...** (230)](#t1) [mockup](#ecran-t1) | MDI | 426x58 | Traitement |
| 230.1.1 | [Ligne commentaire (230.2)](#t3) | MDI | - | |
| **230.2** | [**Calcul pied** (230.1)](#t2) | MDI | - | Calcul |

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

### Tables utilisees (4)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 118 | tables_imports |  | DB | R |   |   | 1 |
| 171 | commentaire______com |  | DB | R |   |   | 1 |
| 598 | tempo_ecr_previsions | Table temporaire ecran | TMP | R |   |   | 1 |
| 619 | tempo_userlist | Table temporaire ecran | TMP |   |   | L | 1 |

### Colonnes par table (2 / 3 tables avec colonnes identifiees)

<details>
<summary>Table 118 - tables_imports (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | >DateCalcul | R | Date |
| B | >HeurePresence | R | Alpha |
| C | >CodeListe | R | Alpha |
| D | >TopListe | R | Alpha |
| E | >NomLogement | R | Alpha |
| F | >Total | R | Numeric |
| G | >NbSelect | R | Numeric |
| H | >Excel | R | Logical |
| I | >NomFihierExcel | R | Alpha |
| J | w0_LibelleEdition | R | Alpha |
| K | w0_f(CodeListe) | R | Alpha |
| L | w0_g(TopListe) | R | Alpha |
| M | v.LigneExcel | R | Alpha |
| N | w0_NomPied01 | R | Alpha |
| O | w0_NbPied01 | R | Numeric |
| P | w0_NomPied02 | R | Alpha |
| Q | w0_NbPied02 | R | Numeric |
| R | w0_NomPied03 | R | Alpha |
| S | w0_NbPied03 | R | Numeric |
| T | w0_NomPied04 | R | Alpha |
| U | w0_NbPied04 | R | Numeric |
| V | w0_NomPied05 | R | Alpha |
| W | w0_NbPied05 | R | Numeric |
| X | w0_TotalSelect | R | Numeric |

</details>

<details>
<summary>Table 171 - commentaire______com (R) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 598 - tempo_ecr_previsions (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | w1_Rupture | R | Numeric |
| B | w1_TotalSelect | R | Numeric |

</details>

## 11. VARIABLES

### 11.1 Variables de session (1)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| M | v.LigneExcel | Alpha | - |

### 11.2 Autres (23)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | >DateCalcul | Date | 1x refs |
| B | >HeurePresence | Alpha | 1x refs |
| C | >CodeListe | Alpha | 2x refs |
| D | >TopListe | Alpha | 15x refs |
| E | >NomLogement | Alpha | - |
| F | >Total | Numeric | - |
| G | >NbSelect | Numeric | - |
| H | >Excel | Logical | 2x refs |
| I | >NomFihierExcel | Alpha | 1x refs |
| J | w0_LibelleEdition | Alpha | 2x refs |
| K | w0_f(CodeListe) | Alpha | - |
| L | w0_g(TopListe) | Alpha | - |
| N | w0_NomPied01 | Alpha | 1x refs |
| O | w0_NbPied01 | Numeric | 1x refs |
| P | w0_NomPied02 | Alpha | 1x refs |
| Q | w0_NbPied02 | Numeric | 1x refs |
| R | w0_NomPied03 | Alpha | - |
| S | w0_NbPied03 | Numeric | 1x refs |
| T | w0_NomPied04 | Alpha | 1x refs |
| U | w0_NbPied04 | Numeric | - |
| V | w0_NomPied05 | Alpha | 2x refs |
| W | w0_NbPied05 | Numeric | 2x refs |
| X | w0_TotalSelect | Numeric | 2x refs |

<details>
<summary>Toutes les 24 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| V. | **M** | v.LigneExcel | Alpha |
| Autre | **A** | >DateCalcul | Date |
| Autre | **B** | >HeurePresence | Alpha |
| Autre | **C** | >CodeListe | Alpha |
| Autre | **D** | >TopListe | Alpha |
| Autre | **E** | >NomLogement | Alpha |
| Autre | **F** | >Total | Numeric |
| Autre | **G** | >NbSelect | Numeric |
| Autre | **H** | >Excel | Logical |
| Autre | **I** | >NomFihierExcel | Alpha |
| Autre | **J** | w0_LibelleEdition | Alpha |
| Autre | **K** | w0_f(CodeListe) | Alpha |
| Autre | **L** | w0_g(TopListe) | Alpha |
| Autre | **N** | w0_NomPied01 | Alpha |
| Autre | **O** | w0_NbPied01 | Numeric |
| Autre | **P** | w0_NomPied02 | Alpha |
| Autre | **Q** | w0_NbPied02 | Numeric |
| Autre | **R** | w0_NomPied03 | Alpha |
| Autre | **S** | w0_NbPied03 | Numeric |
| Autre | **T** | w0_NomPied04 | Alpha |
| Autre | **U** | w0_NbPied04 | Numeric |
| Autre | **V** | w0_NomPied05 | Alpha |
| Autre | **W** | w0_NbPied05 | Numeric |
| Autre | **X** | w0_TotalSelect | Numeric |

</details>

## 12. EXPRESSIONS

**38 / 38 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONCATENATION | 6 | 0 |
| CONDITION | 22 | 15 |
| FORMAT | 1 | 0 |
| OTHER | 6 | 0 |
| REFERENCE_VG | 1 | 0 |
| NEGATION | 1 | 0 |
| STRING | 1 | 0 |

### 12.2 Expressions cles par type

#### CONCATENATION (6 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 34 | `MlsTrans ('Depart le')&' '&DStr (w0_NomPied05 [V],'DD/MM/YYYY')&' '&MlsTrans ('à')&' '&w0_NbPied05 [W]&'  '&MlsTrans ('Retour le')&'  '&DStr (w0_TotalSelect [X],'DD/MM/YYYY')&' '&MlsTrans ('à')&' '&[Y]` | - |
| CONCATENATION | 10 | `'Matricule WD'&VG36&'Nom'&VG36&'Prénom'&VG36&'Sex'&VG36&'Qualité'&VG36&'Logement'&VG36&'Pays'&VG36&'Fonction'&VG36&'Date Arrivée'&VG36&'Heure Arr'&VG36&'Date Départ'&VG36&'Heure Dept'&VG36&'B'&VG36&'F'` | - |
| CONCATENATION | 32 | `Trim (>Excel [H])&' '&IF (>CodeListe [C]='P',>HeurePresence [B]&IF (>HeurePresence [B]='','',' h'),'')` | - |
| CONCATENATION | 35 | `'- '&Str (Page (0,1),'3P0Z0')&' -'` | - |
| CONCATENATION | 31 | `MlsTrans ('Liste des')&' '&Trim (>NomFihierExcel [I])&' '&Trim (w0_LibelleEdition [J])&' '&MlsTrans ('le')&' '&DStr (>DateCalcul [A],'DD/MM/YYYY')` | - |
| ... | | *+1 autres* | |

#### CONDITION (22 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 25 | `IF (>TopListe [D]='HM','honey moon','')` | [RM-011](#rm-RM-011) |
| CONDITION | 24 | `IF (>TopListe [D]='PY','pays','')` | [RM-010](#rm-RM-010) |
| CONDITION | 23 | `IF (>TopListe [D]='NS','non single','')` | [RM-009](#rm-RM-009) |
| CONDITION | 26 | `IF (>TopListe [D]='VV','Vil/Vil','')` | [RM-012](#rm-RM-012) |
| CONDITION | 29 | `IF (>TopListe [D]='CO','commentaire','')` | [RM-015](#rm-RM-015) |
| ... | | *+17 autres* | |

#### FORMAT (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| FORMAT | 11 | `[DD]&VG36&w0_NomPied01 [N]&VG36&w0_NbPied01 [O]&VG36&w0_NomPied02 [P]&VG36&w0_NbPied02 [Q]&VG36&w0_NbPied03 [S]&VG36&w0_NomPied04 [T]&VG36&[AG]&VG36&DStr(w0_NomPied05 [V],'DD/MM/YYYY')&VG36&w0_NbPied05 [W]&VG36&DStr(w0_TotalSelect [X],'DD/MM/YYYY')&VG36&[Y]&VG36&[Z]&VG36&[AB]` | - |

#### OTHER (6 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 5 | `Counter (0)` | - |
| OTHER | 8 | `[CZ]` | - |
| OTHER | 37 | `[CU]` | - |
| OTHER | 1 | `GetParam ('SOCIETE')` | - |
| OTHER | 2 | `GetParam ('VILLAGE')` | - |
| ... | | *+1 autres* | |

#### REFERENCE_VG (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 4 | `VG1` | - |

#### NEGATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| NEGATION | 7 | `NOT [CZ]` | - |

#### STRING (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| STRING | 6 | `Trim([DA])` | - |

### 12.3 Toutes les expressions (38)

<details>
<summary>Voir les 38 expressions</summary>

#### CONCATENATION (6)

| IDE | Expression Decodee |
|-----|-------------------|
| 35 | `'- '&Str (Page (0,1),'3P0Z0')&' -'` |
| 31 | `MlsTrans ('Liste des')&' '&Trim (>NomFihierExcel [I])&' '&Trim (w0_LibelleEdition [J])&' '&MlsTrans ('le')&' '&DStr (>DateCalcul [A],'DD/MM/YYYY')` |
| 33 | `MlsTrans ('Edition du')&' '&DStr (Date (),'DD/MM/YYYY')&' '&MlsTrans ('à')&' '&TStr (Time (),'HH:MM:SS')` |
| 34 | `MlsTrans ('Depart le')&' '&DStr (w0_NomPied05 [V],'DD/MM/YYYY')&' '&MlsTrans ('à')&' '&w0_NbPied05 [W]&'  '&MlsTrans ('Retour le')&'  '&DStr (w0_TotalSelect [X],'DD/MM/YYYY')&' '&MlsTrans ('à')&' '&[Y]` |
| 10 | `'Matricule WD'&VG36&'Nom'&VG36&'Prénom'&VG36&'Sex'&VG36&'Qualité'&VG36&'Logement'&VG36&'Pays'&VG36&'Fonction'&VG36&'Date Arrivée'&VG36&'Heure Arr'&VG36&'Date Départ'&VG36&'Heure Dept'&VG36&'B'&VG36&'F'` |
| 32 | `Trim (>Excel [H])&' '&IF (>CodeListe [C]='P',>HeurePresence [B]&IF (>HeurePresence [B]='','',' h'),'')` |

#### CONDITION (22)

| IDE | Expression Decodee |
|-----|-------------------|
| 15 | `IF (>CodeListe [C]='A','arrivants',IF (>CodeListe [C]='V','arrivees',IF (>CodeListe [C]='P','presents',IF (>CodeListe [C]='D','departs',IF (>CodeListe [C]='R','partants','absents')))))` |
| 16 | `IF (>TopListe [D]='PL','planning','')` |
| 17 | `IF (>TopListe [D]='GR','groupe','')` |
| 18 | `IF (>TopListe [D]='CA','caisse','')` |
| 19 | `IF (>TopListe [D]='MI','millesias','')` |
| 20 | `IF (>TopListe [D]='BB','bebe','')` |
| 21 | `IF (>TopListe [D]='EN','enfant','')` |
| 22 | `IF (>TopListe [D]='SI','single','')` |
| 23 | `IF (>TopListe [D]='NS','non single','')` |
| 24 | `IF (>TopListe [D]='PY','pays','')` |
| 25 | `IF (>TopListe [D]='HM','honey moon','')` |
| 26 | `IF (>TopListe [D]='VV','Vil/Vil','')` |
| 27 | `IF (>TopListe [D]='NV','non Vil/Vil','')` |
| 28 | `IF (>TopListe [D]='AG','age','')` |
| 29 | `IF (>TopListe [D]='CO','commentaire','')` |
| 12 | `[AI]=''` |
| 13 | `[AI]='' AND >TopListe [D]='CO'` |
| 14 | `[AI]='CIRCUIT'` |
| 30 | `w0_LibelleEdition [J]=''` |
| 36 | `INIGet ('[MAGIC_LOGICAL_NAMES]preview')='O'` |
| 38 | `VG44>1` |
| 9 | `Trim(>Excel [H])` |

#### FORMAT (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 11 | `[DD]&VG36&w0_NomPied01 [N]&VG36&w0_NbPied01 [O]&VG36&w0_NomPied02 [P]&VG36&w0_NbPied02 [Q]&VG36&w0_NbPied03 [S]&VG36&w0_NomPied04 [T]&VG36&[AG]&VG36&DStr(w0_NomPied05 [V],'DD/MM/YYYY')&VG36&w0_NbPied05 [W]&VG36&DStr(w0_TotalSelect [X],'DD/MM/YYYY')&VG36&[Y]&VG36&[Z]&VG36&[AB]` |

#### OTHER (6)

| IDE | Expression Decodee |
|-----|-------------------|
| 1 | `GetParam ('SOCIETE')` |
| 2 | `GetParam ('VILLAGE')` |
| 3 | `IsFirstRecordCycle (0)` |
| 5 | `Counter (0)` |
| 8 | `[CZ]` |
| 37 | `[CU]` |

#### REFERENCE_VG (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 4 | `VG1` |

#### NEGATION (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 7 | `NOT [CZ]` |

#### STRING (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 6 | `Trim([DA])` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [  Liste present personnel plan (IDE 227)](PBP-IDE-227.md) -> **Imprim pres plan GO (IDE 230)**

Main -> ... -> [  Affichage pres plans GO (IDE 229)](PBP-IDE-229.md) -> **Imprim pres plan GO (IDE 230)**

```mermaid
graph LR
    T230[230 Imprim pres plan GO]
    style T230 fill:#58a6ff
    CC226[226 Liste des presents...]
    style CC226 fill:#8b5cf6
    CC227[227 Liste present pers...]
    style CC227 fill:#3fb950
    CC229[229 Affichage pres pla...]
    style CC229 fill:#3fb950
    CC226 --> CC227
    CC226 --> CC229
    CC227 --> T230
    CC229 --> T230
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [227](PBP-IDE-227.md) |   Liste present personnel plan | 2 |
| [229](PBP-IDE-229.md) |   Affichage pres plans GO | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T230[230 Imprim pres plan GO]
    style T230 fill:#58a6ff
    NONE[Aucun callee]
    T230 -.-> NONE
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
| Lignes de logique | 151 | Programme compact |
| Expressions | 38 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 151) | Code sain |
| Regles metier | 15 | Logique metier riche |

### 14.2 Plan de migration par bloc

#### Traitement (2 taches: 1 ecran, 1 traitement)

- **Strategie** : Orchestrateur avec 1 ecrans (Razor/React) et 1 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- Decomposer les taches en services unitaires testables.

#### Calcul (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Services de calcul purs (Domain Services).
- Migrer la logique de calcul (stock, compteurs, montants)

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 15:56*
