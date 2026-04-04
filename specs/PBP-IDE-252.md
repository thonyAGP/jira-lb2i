# PBP IDE 252 - Imp GM arrivant planning TAI

> **Analyse**: Phases 1-4 2026-02-03 15:59 -> 16:00 (11s) | Assemblage 16:00
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBP |
| IDE Position | 252 |
| Nom Programme | Imp GM arrivant planning TAI |
| Fichier source | `Prg_252.xml` |
| Dossier IDE | Logement |
| Taches | 3 (1 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Imp GM arrivant planning TAI** assure la gestion complete de ce processus, accessible depuis [  Liste CLients arrivant (IDE 156)](PBP-IDE-156.md), [  Affich arrivant planning GM (IDE 158)](PBP-IDE-158.md).

Le flux de traitement s'organise en **2 blocs fonctionnels** :

- **Traitement** (2 taches) : traitements metier divers
- **Calcul** (1 tache) : calculs de montants, stocks ou compteurs

**Logique metier** : 21 regles identifiees couvrant conditions metier, valeurs par defaut.

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (2 taches)

- **252** - Veuillez patienter... **[[ECRAN]](#ecran-t1)**
- **252.2** - Ligne commentaire

#### Phase 2 : Calcul (1 tache)

- **252.1** - Calcul pied

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (2 taches)

Traitements internes.

---

#### <a id="t1"></a>252 - Veuillez patienter... [[ECRAN]](#ecran-t1)

**Role** : Traitement : Veuillez patienter....
**Ecran** : 426 x 58 DLU (MDI) | [Voir mockup](#ecran-t1)

---

#### <a id="t3"></a>252.2 - Ligne commentaire

**Role** : Traitement : Ligne commentaire.


### 3.2 Calcul (1 tache)

Calculs metier : montants, stocks, compteurs.

---

#### <a id="t2"></a>252.1 - Calcul pied

**Role** : Calcul : Calcul pied.
**Variables liees** : A (>DateCalcul), S (w0_NomPied01), T (w0_NbPied01), U (w0_NomPied02), V (w0_NbPied02)


## 5. REGLES METIER

21 regles identifiees:

### Autres (21 regles)

#### <a id="rm-RM-001"></a>[RM-001] Si >TopListe [D]='AG' OR >TopListe [D]='BB' OR >TopListe [D]='EN' alors MlsTrans ('Naissance') sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='AG' OR >TopListe [D]='BB' OR >TopListe [D]='EN'` |
| **Si vrai** | MlsTrans ('Naissance') |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 4 : `IF (>TopListe [D]='AG' OR >TopListe [D]='BB' OR >TopListe [D` |
| **Exemple** | Si >TopListe [D]='AG' OR >TopListe [D]='BB' OR >TopListe [D]='EN' â†’ MlsTrans ('Naissance'). Sinon â†’ '') |

#### <a id="rm-RM-002"></a>[RM-002] Si >TopListe [D]='GR' alors MlsTrans ('GROUPE DEPART') sinon IF (>TopListe [D]='CA',MlsTrans ('DATE FERMETURE'),MlsTrans ('DATE/HR DEPART')))

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='GR'` |
| **Si vrai** | MlsTrans ('GROUPE DEPART') |
| **Si faux** | IF (>TopListe [D]='CA',MlsTrans ('DATE FERMETURE'),MlsTrans ('DATE/HR DEPART'))) |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 8 : `IF (>TopListe [D]='GR',MlsTrans ('GROUPE DEPART'),IF (>TopLi` |
| **Exemple** | Si >TopListe [D]='GR' â†’ MlsTrans ('GROUPE DEPART') |

#### <a id="rm-RM-003"></a>[RM-003] Si >CodeListe [C]='A' alors MlsTrans ('arrivants') sinon IF (>CodeListe [C]='V',MlsTrans ('arrivees'),IF (>CodeListe [C]='P',MlsTrans ('presents'),IF (>CodeListe [C]='D',MlsTrans ('departs'),IF (>CodeListe [C]='R',MlsTrans ('partants'),MlsTrans ('absents'))))))

| Element | Detail |
|---------|--------|
| **Condition** | `>CodeListe [C]='A'` |
| **Si vrai** | MlsTrans ('arrivants') |
| **Si faux** | IF (>CodeListe [C]='V',MlsTrans ('arrivees'),IF (>CodeListe [C]='P',MlsTrans ('presents'),IF (>CodeListe [C]='D',MlsTrans ('departs'),IF (>CodeListe [C]='R',MlsTrans ('partants'),MlsTrans ('absents')))))) |
| **Variables** | C (>CodeListe) |
| **Expression source** | Expression 17 : `IF (>CodeListe [C]='A',MlsTrans ('arrivants'),IF (>CodeListe` |
| **Exemple** | Si >CodeListe [C]='A' â†’ MlsTrans ('arrivants') |

#### <a id="rm-RM-004"></a>[RM-004] Si >TopListe [D]='PL' alors 'planning' sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='PL'` |
| **Si vrai** | 'planning' |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 18 : `IF (>TopListe [D]='PL','planning','')` |
| **Exemple** | Si >TopListe [D]='PL' â†’ 'planning'. Sinon â†’ '') |

#### <a id="rm-RM-005"></a>[RM-005] Si >TopListe [D]='CA' alors MlsTrans ('caisse') sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='CA'` |
| **Si vrai** | MlsTrans ('caisse') |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 20 : `IF (>TopListe [D]='CA',MlsTrans ('caisse'),'')` |
| **Exemple** | Si >TopListe [D]='CA' â†’ MlsTrans ('caisse'). Sinon â†’ '') |

#### <a id="rm-RM-006"></a>[RM-006] Si >TopListe [D]='MI' alors MlsTrans ('millesias') sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='MI'` |
| **Si vrai** | MlsTrans ('millesias') |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 21 : `IF (>TopListe [D]='MI',MlsTrans ('millesias'),'')` |
| **Exemple** | Si >TopListe [D]='MI' â†’ MlsTrans ('millesias'). Sinon â†’ '') |

#### <a id="rm-RM-007"></a>[RM-007] Si >TopListe [D]='BB' alors MlsTrans ('bebe') sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='BB'` |
| **Si vrai** | MlsTrans ('bebe') |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 22 : `IF (>TopListe [D]='BB',MlsTrans ('bebe'),'')` |
| **Exemple** | Si >TopListe [D]='BB' â†’ MlsTrans ('bebe'). Sinon â†’ '') |

#### <a id="rm-RM-008"></a>[RM-008] Si >TopListe [D]='EN' alors MlsTrans ('enfant') sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='EN'` |
| **Si vrai** | MlsTrans ('enfant') |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 23 : `IF (>TopListe [D]='EN',MlsTrans ('enfant'),'')` |
| **Exemple** | Si >TopListe [D]='EN' â†’ MlsTrans ('enfant'). Sinon â†’ '') |

#### <a id="rm-RM-009"></a>[RM-009] Si >TopListe [D]='SI' alors 'single' sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='SI'` |
| **Si vrai** | 'single' |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 24 : `IF (>TopListe [D]='SI','single','')` |
| **Exemple** | Si >TopListe [D]='SI' â†’ 'single'. Sinon â†’ '') |

#### <a id="rm-RM-010"></a>[RM-010] Si >TopListe [D]='NS' alors 'non single' sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='NS'` |
| **Si vrai** | 'non single' |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 25 : `IF (>TopListe [D]='NS','non single','')` |
| **Exemple** | Si >TopListe [D]='NS' â†’ 'non single'. Sinon â†’ '') |

#### <a id="rm-RM-011"></a>[RM-011] Si >TopListe [D]='PY' alors MlsTrans ('pays') sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='PY'` |
| **Si vrai** | MlsTrans ('pays') |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 26 : `IF (>TopListe [D]='PY',MlsTrans ('pays'),'')` |
| **Exemple** | Si >TopListe [D]='PY' â†’ MlsTrans ('pays'). Sinon â†’ '') |

#### <a id="rm-RM-012"></a>[RM-012] Si >TopListe [D]='HM' alors 'honey moon' sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='HM'` |
| **Si vrai** | 'honey moon' |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 27 : `IF (>TopListe [D]='HM','honey moon','')` |
| **Exemple** | Si >TopListe [D]='HM' â†’ 'honey moon'. Sinon â†’ '') |

#### <a id="rm-RM-013"></a>[RM-013] Si >TopListe [D]='VV' alors 'Vil/Vil' sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='VV'` |
| **Si vrai** | 'Vil/Vil' |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 28 : `IF (>TopListe [D]='VV','Vil/Vil','')` |
| **Exemple** | Si >TopListe [D]='VV' â†’ 'Vil/Vil'. Sinon â†’ '') |

#### <a id="rm-RM-014"></a>[RM-014] Si >TopListe [D]='NV' alors 'non Vil/Vil' sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='NV'` |
| **Si vrai** | 'non Vil/Vil' |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 29 : `IF (>TopListe [D]='NV','non Vil/Vil','')` |
| **Exemple** | Si >TopListe [D]='NV' â†’ 'non Vil/Vil'. Sinon â†’ '') |

#### <a id="rm-RM-015"></a>[RM-015] Si >TopListe [D]='AG' alors MlsTrans ('age du')&' '&Str (>AgeMin [H] sinon '2')&' / '&Str (>AgeMax [I],'2')&' ans','')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='AG'` |
| **Si vrai** | MlsTrans ('age du')&' '&Str (>AgeMin [H] |
| **Si faux** | '2')&' / '&Str (>AgeMax [I],'2')&' ans','') |
| **Variables** | D (>TopListe), H (>AgeMin), I (>AgeMax) |
| **Expression source** | Expression 30 : `IF (>TopListe [D]='AG',MlsTrans ('age du')&' '&Str (>AgeMin ` |
| **Exemple** | Si >TopListe [D]='AG' â†’ MlsTrans ('age du')&' '&Str (>AgeMin [H]. Sinon â†’ '2')&' / '&Str (>AgeMax [I],'2')&' ans','') |

#### <a id="rm-RM-016"></a>[RM-016] Si >TopListe [D]='CO' alors MlsTrans ('commentaire') sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='CO'` |
| **Si vrai** | MlsTrans ('commentaire') |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 31 : `IF (>TopListe [D]='CO',MlsTrans ('commentaire'),'')` |
| **Exemple** | Si >TopListe [D]='CO' â†’ MlsTrans ('commentaire'). Sinon â†’ '') |

#### <a id="rm-RM-017"></a>[RM-017] Si >TopListe [D]='CP' alors MlsTrans ('comptage') sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='CP'` |
| **Si vrai** | MlsTrans ('comptage') |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 32 : `IF (>TopListe [D]='CP',MlsTrans ('comptage'),'')` |
| **Exemple** | Si >TopListe [D]='CP' â†’ MlsTrans ('comptage'). Sinon â†’ '') |

#### <a id="rm-RM-018"></a>[RM-018] Valeur par defaut si >CodeListe [C]<>'CP' AND >CodeListe [C]<>'GR',IF (>NomLogement [E] est vide

| Element | Detail |
|---------|--------|
| **Condition** | `>CodeListe [C]<>'CP' AND >CodeListe [C]<>'GR'` |
| **Si vrai** | IF (>NomLogement [E]='' |
| **Si faux** | MlsTrans ('Tout Logement'),MlsTrans ('Logement')&' '&>NomLogement [E]),IF (>CodeGroupe [J]='','Toutes categories',>CodeGroupe [J])) |
| **Variables** | C (>CodeListe), E (>NomLogement), J (>CodeGroupe) |
| **Expression source** | Expression 39 : `IF (>CodeListe [C]<>'CP' AND >CodeListe [C]<>'GR',IF (>NomLo` |
| **Exemple** | Si >CodeListe [C]<>'CP' AND >CodeListe [C]<>'GR' â†’ IF (>NomLogement [E]='' |

#### <a id="rm-RM-019"></a>[RM-019] Traitement si VG42,IF ([EI] est renseigne

| Element | Detail |
|---------|--------|
| **Condition** | `VG42` |
| **Si vrai** | IF ([EI]<>'' |
| **Si faux** | [EI],[AF]),IF ([AY]<>'',[AY],[AF])) |
| **Expression source** | Expression 44 : `IF(VG42,IF ([EI]<>'',[EI],[AF]),IF ([AY]<>'',[AY],[AF]))` |
| **Exemple** | Si VG42 â†’ IF ([EI]<>''. Sinon â†’ [EI],[AF]),IF ([AY]<>'',[AY],[AF])) |

#### <a id="rm-RM-020"></a>[RM-020] Si [EJ] alors [EK]&[EL]&Str([AJ] sinon '3P0'),[BF]&w0_NomPied01 [S]&Str([AJ],'3P0'))

| Element | Detail |
|---------|--------|
| **Condition** | `[EJ]` |
| **Si vrai** | [EK]&[EL]&Str([AJ] |
| **Si faux** | '3P0'),[BF]&w0_NomPied01 [S]&Str([AJ],'3P0')) |
| **Variables** | S (w0_NomPied01) |
| **Expression source** | Expression 51 : `IF([EJ],[EK]&[EL]&Str([AJ],'3P0'),[BF]&w0_NomPied01 [S]&Str(` |
| **Exemple** | Si [EJ] â†’ [EK]&[EL]&Str([AJ]. Sinon â†’ '3P0'),[BF]&w0_NomPied01 [S]&Str([AJ],'3P0')) |

#### <a id="rm-RM-021"></a>[RM-021] Si VG88 AND [EP] alors TStr([EO] sinon 'HHhMMZ'),[AD])

| Element | Detail |
|---------|--------|
| **Condition** | `VG88 AND [EP]` |
| **Si vrai** | TStr([EO] |
| **Si faux** | 'HHhMMZ'),[AD]) |
| **Expression source** | Expression 54 : `IF(VG88 AND [EP],TStr([EO],'HHhMMZ'),[AD])` |
| **Exemple** | Si VG88 AND [EP] â†’ TStr([EO]. Sinon â†’ 'HHhMMZ'),[AD]) |

## 6. CONTEXTE

- **Appele par**: [  Liste CLients arrivant (IDE 156)](PBP-IDE-156.md), [  Affich arrivant planning GM (IDE 158)](PBP-IDE-158.md)
- **Appelle**: 0 programmes | **Tables**: 6 (W:0 R:3 L:3) | **Taches**: 3 | **Expressions**: 55

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 3)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 252 | 252 | Veuillez patienter... | MDI | 426 | 58 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>252 - Veuillez patienter...
**Tache** : [252](#t1) | **Type** : MDI | **Dimensions** : 426 x 58 DLU
**Bloc** : Traitement | **Titre IDE** : Veuillez patienter...

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
                         "text":  "Impression en cours ...",
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
                         "w":  280,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Edition AVPBDR",
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
    "taskId":  "252",
    "height":  58
}
-->

## 9. NAVIGATION

Ecran unique: **Veuillez patienter...**

### 9.3 Structure hierarchique (3 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **252.1** | [**Veuillez patienter...** (252)](#t1) [mockup](#ecran-t1) | MDI | 426x58 | Traitement |
| 252.1.1 | [Ligne commentaire (252.2)](#t3) | MDI | - | |
| **252.2** | [**Calcul pied** (252.1)](#t2) | MDI | - | Calcul |

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

### Tables utilisees (6)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 31 | gm-complet_______gmc |  | DB | R |   |   | 1 |
| 171 | commentaire______com |  | DB | R |   |   | 1 |
| 358 | import_mod |  | DB |   |   | L | 1 |
| 463 | heure_de_passage |  | DB |   |   | L | 1 |
| 598 | tempo_ecr_previsions | Table temporaire ecran | TMP | R |   |   | 1 |
| 619 | tempo_userlist | Table temporaire ecran | TMP |   |   | L | 1 |

### Colonnes par table (3 / 3 tables avec colonnes identifiees)

<details>
<summary>Table 31 - gm-complet_______gmc (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | >DateCalcul | R | Date |
| B | >HeurePresence | R | Alpha |
| C | >CodeListe | R | Alpha |
| D | >TopListe | R | Alpha |
| E | >NomLogement | R | Alpha |
| F | >Total | R | Numeric |
| G | >NbSelect | R | Numeric |
| H | >AgeMin | R | Numeric |
| I | >AgeMax | R | Numeric |
| J | >CodeGroupe | R | Alpha |
| K | >OnlyTAI | R | Logical |
| L | >Tri Nom/Filiation | R | Logical |
| M | P.I Heure depart village | R | Logical |
| N | w0_LibelleEdition | R | Alpha |
| O | w0_f(CodeListe) | R | Alpha |
| P | w0_g(TopListe) | R | Alpha |
| Q | W0_Libelle Logement | R | Alpha |
| R | Existe TAI | R | Logical |
| S | w0_NomPied01 | R | Alpha |
| T | w0_NbPied01 | R | Numeric |
| U | w0_NomPied02 | R | Alpha |
| V | w0_NbPied02 | R | Numeric |
| W | w0_NomPied03 | R | Alpha |
| X | w0_NbPied03 | R | Numeric |
| Y | w0_NomPied04 | R | Alpha |
| Z | w0_NbPied04 | R | Numeric |
| BA | w0_NomPied05 | R | Alpha |
| BB | w0_NbPied05 | R | Numeric |
| BC | w0_TotalSelect | R | Numeric |
| BD | w0_Ordre tri | R | Alpha |
| BE | w0_Dernier n° compte | R | Numeric |

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

### 11.1 Parametres entrants (1)

Variables recues du programme appelant ([  Liste CLients arrivant (IDE 156)](PBP-IDE-156.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| M | P.I Heure depart village | Logical | 2x parametre entrant |

### 11.2 Autres (30)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | >DateCalcul | Date | 2x refs |
| B | >HeurePresence | Alpha | 2x refs |
| C | >CodeListe | Alpha | 5x refs |
| D | >TopListe | Alpha | 22x refs |
| E | >NomLogement | Alpha | 1x refs |
| F | >Total | Numeric | - |
| G | >NbSelect | Numeric | 1x refs |
| H | >AgeMin | Numeric | 1x refs |
| I | >AgeMax | Numeric | 1x refs |
| J | >CodeGroupe | Alpha | 3x refs |
| K | >OnlyTAI | Logical | 2x refs |
| L | >Tri Nom/Filiation | Logical | 1x refs |
| N | w0_LibelleEdition | Alpha | 3x refs |
| O | w0_f(CodeListe) | Alpha | - |
| P | w0_g(TopListe) | Alpha | 2x refs |
| Q | W0_Libelle Logement | Alpha | - |
| R | Existe TAI | Logical | - |
| S | w0_NomPied01 | Alpha | 1x refs |
| T | w0_NbPied01 | Numeric | - |
| U | w0_NomPied02 | Alpha | - |
| V | w0_NbPied02 | Numeric | - |
| W | w0_NomPied03 | Alpha | - |
| X | w0_NbPied03 | Numeric | - |
| Y | w0_NomPied04 | Alpha | - |
| Z | w0_NbPied04 | Numeric | - |
| BA | w0_NomPied05 | Alpha | - |
| BB | w0_NbPied05 | Numeric | - |
| BC | w0_TotalSelect | Numeric | - |
| BD | w0_Ordre tri | Alpha | 1x refs |
| BE | w0_Dernier n° compte | Numeric | 1x refs |

<details>
<summary>Toutes les 31 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| P0 | **M** | P.I Heure depart village | Logical |
| Autre | **A** | >DateCalcul | Date |
| Autre | **B** | >HeurePresence | Alpha |
| Autre | **C** | >CodeListe | Alpha |
| Autre | **D** | >TopListe | Alpha |
| Autre | **E** | >NomLogement | Alpha |
| Autre | **F** | >Total | Numeric |
| Autre | **G** | >NbSelect | Numeric |
| Autre | **H** | >AgeMin | Numeric |
| Autre | **I** | >AgeMax | Numeric |
| Autre | **J** | >CodeGroupe | Alpha |
| Autre | **K** | >OnlyTAI | Logical |
| Autre | **L** | >Tri Nom/Filiation | Logical |
| Autre | **N** | w0_LibelleEdition | Alpha |
| Autre | **O** | w0_f(CodeListe) | Alpha |
| Autre | **P** | w0_g(TopListe) | Alpha |
| Autre | **Q** | W0_Libelle Logement | Alpha |
| Autre | **R** | Existe TAI | Logical |
| Autre | **S** | w0_NomPied01 | Alpha |
| Autre | **T** | w0_NbPied01 | Numeric |
| Autre | **U** | w0_NomPied02 | Alpha |
| Autre | **V** | w0_NbPied02 | Numeric |
| Autre | **W** | w0_NomPied03 | Alpha |
| Autre | **X** | w0_NbPied03 | Numeric |
| Autre | **Y** | w0_NomPied04 | Alpha |
| Autre | **Z** | w0_NbPied04 | Numeric |
| Autre | **BA** | w0_NomPied05 | Alpha |
| Autre | **BB** | w0_NbPied05 | Numeric |
| Autre | **BC** | w0_TotalSelect | Numeric |
| Autre | **BD** | w0_Ordre tri | Alpha |
| Autre | **BE** | w0_Dernier n° compte | Numeric |

</details>

## 12. EXPRESSIONS

**55 / 55 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONCATENATION | 10 | 2 |
| CONDITION | 34 | 19 |
| OTHER | 10 | 0 |
| REFERENCE_VG | 1 | 0 |

### 12.2 Expressions cles par type

#### CONCATENATION (10 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 30 | `IF (>TopListe [D]='AG',MlsTrans ('age du')&' '&Str (>AgeMin [H],'2')&' / '&Str (>AgeMax [I],'2')&' ans','')` | [RM-015](#rm-RM-015) |
| CONCATENATION | 39 | `IF (>CodeListe [C]<>'CP' AND >CodeListe [C]<>'GR',IF (>NomLogement [E]='',MlsTrans ('Tout Logement'),MlsTrans ('Logement')&' '&>NomLogement [E]),IF (>CodeGroupe [J]='','Toutes categories',>CodeGroupe [J]))` | [RM-018](#rm-RM-018) |
| CONCATENATION | 49 | `'TAI from '&DStr (w0_Ordre tri [BD],'DD/MM/YYYY')&' to '&DStr (w0_Dernier n° compte [BE],'DD/MM/YYYY')` | - |
| CONCATENATION | 38 | `MlsTrans ('Depart le')&' '&DStr ([AA],'DD/MM/YYYY')&' '` | - |
| CONCATENATION | 36 | `Trim (>Tri Nom/Filiation [L])&' '&IF (>CodeListe [C]='P',>HeurePresence [B]&' h','')` | - |
| ... | | *+5 autres* | |

#### CONDITION (34 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 28 | `IF (>TopListe [D]='VV','Vil/Vil','')` | [RM-013](#rm-RM-013) |
| CONDITION | 29 | `IF (>TopListe [D]='NV','non Vil/Vil','')` | [RM-014](#rm-RM-014) |
| CONDITION | 27 | `IF (>TopListe [D]='HM','honey moon','')` | [RM-012](#rm-RM-012) |
| CONDITION | 25 | `IF (>TopListe [D]='NS','non single','')` | [RM-010](#rm-RM-010) |
| CONDITION | 26 | `IF (>TopListe [D]='PY',MlsTrans ('pays'),'')` | [RM-011](#rm-RM-011) |
| ... | | *+29 autres* | |

#### OTHER (10 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 45 | `w0_g(TopListe) [P]` | - |
| OTHER | 13 | `Counter (0)` | - |
| OTHER | 46 | `[AI]` | - |
| OTHER | 52 | `[AI]` | - |
| OTHER | 47 | `[AJ]` | - |
| ... | | *+5 autres* | |

#### REFERENCE_VG (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 12 | `VG1` | - |

### 12.3 Toutes les expressions (55)

<details>
<summary>Voir les 55 expressions</summary>

#### CONCATENATION (10)

| IDE | Expression Decodee |
|-----|-------------------|
| 40 | `'- '&Str (Page (0,1),'3P0Z0')&' -'` |
| 30 | `IF (>TopListe [D]='AG',MlsTrans ('age du')&' '&Str (>AgeMin [H],'2')&' / '&Str (>AgeMax [I],'2')&' ans','')` |
| 39 | `IF (>CodeListe [C]<>'CP' AND >CodeListe [C]<>'GR',IF (>NomLogement [E]='',MlsTrans ('Tout Logement'),MlsTrans ('Logement')&' '&>NomLogement [E]),IF (>CodeGroupe [J]='','Toutes categories',>CodeGroupe [J]))` |
| 34 | `MlsTrans ('Liste des')&' '&' '&Trim (P.I Heure depart village [M])&' '&Trim (w0_LibelleEdition [N])&IF (>TopListe [D]='CP' OR >TopListe [D]='GR',' '&Trim (>CodeGroupe [J])&' '&>HeurePresence [B]&' h','')&' '&MlsTrans ('le')&' '&DStr (>DateCalcul [A],'DD/MM/YYYY')` |
| 35 | `MlsTrans ('Liste des')&' '&' '&Trim (P.I Heure depart village [M])&' '&Trim (w0_LibelleEdition [N])&IF (>TopListe [D]='CP' OR >TopListe [D]='GR',' '&Trim (>CodeGroupe [J]),'')&' '&MlsTrans ('le')&' '&DStr (>DateCalcul [A],'DD/MM/YYYY')` |
| 37 | `MlsTrans ('Edition du')&' '&DStr (Date (),'DD/MM/YYYY')&' '&MlsTrans ('à')&' '&TStr (Time (),'HH:MM:SS')` |
| 38 | `MlsTrans ('Depart le')&' '&DStr ([AA],'DD/MM/YYYY')&' '` |
| 49 | `'TAI from '&DStr (w0_Ordre tri [BD],'DD/MM/YYYY')&' to '&DStr (w0_Dernier n° compte [BE],'DD/MM/YYYY')` |
| 55 | `MlsTrans('Heure de fin :')&' '&MlsTrans(IF(VG88 AND [EP], 'Libération logement','Départ Village'))` |
| 36 | `Trim (>Tri Nom/Filiation [L])&' '&IF (>CodeListe [C]='P',>HeurePresence [B]&' h','')` |

#### CONDITION (34)

| IDE | Expression Decodee |
|-----|-------------------|
| 4 | `IF (>TopListe [D]='AG' OR >TopListe [D]='BB' OR >TopListe [D]='EN',MlsTrans ('Naissance'),'')` |
| 8 | `IF (>TopListe [D]='GR',MlsTrans ('GROUPE DEPART'),IF (>TopListe [D]='CA',MlsTrans ('DATE FERMETURE'),MlsTrans ('DATE/HR DEPART')))` |
| 9 | `IF (>TopListe [D]='GR',MlsTrans ('GROUPE ARRIVEE'),IF (>TopListe [D]='CA',MlsTrans ('DATE OUVERTURE'),MlsTrans ('DATE/HR ARRIVEE')))` |
| 17 | `IF (>CodeListe [C]='A',MlsTrans ('arrivants'),IF (>CodeListe [C]='V',MlsTrans ('arrivees'),IF (>CodeListe [C]='P',MlsTrans ('presents'),IF (>CodeListe [C]='D',MlsTrans ('departs'),IF (>CodeListe [C]='R',MlsTrans ('partants'),MlsTrans ('absents'))))))` |
| 18 | `IF (>TopListe [D]='PL','planning','')` |
| 19 | `IF (>TopListe [D]='GR',MlsTrans ('groupe'),'')` |
| 20 | `IF (>TopListe [D]='CA',MlsTrans ('caisse'),'')` |
| 21 | `IF (>TopListe [D]='MI',MlsTrans ('millesias'),'')` |
| 22 | `IF (>TopListe [D]='BB',MlsTrans ('bebe'),'')` |
| 23 | `IF (>TopListe [D]='EN',MlsTrans ('enfant'),'')` |
| 24 | `IF (>TopListe [D]='SI','single','')` |
| 25 | `IF (>TopListe [D]='NS','non single','')` |
| 26 | `IF (>TopListe [D]='PY',MlsTrans ('pays'),'')` |
| 27 | `IF (>TopListe [D]='HM','honey moon','')` |
| 28 | `IF (>TopListe [D]='VV','Vil/Vil','')` |
| 29 | `IF (>TopListe [D]='NV','non Vil/Vil','')` |
| 31 | `IF (>TopListe [D]='CO',MlsTrans ('commentaire'),'')` |
| 32 | `IF (>TopListe [D]='CP',MlsTrans ('comptage'),'')` |
| 44 | `IF(VG42,IF ([EI]<>'',[EI],[AF]),IF ([AY]<>'',[AY],[AF]))` |
| 51 | `IF([EJ],[EK]&[EL]&Str([AJ],'3P0'),[BF]&w0_NomPied01 [S]&Str([AJ],'3P0'))` |
| 54 | `IF(VG88 AND [EP],TStr([EO],'HHhMMZ'),[AD])` |
| 1 | `>CodeListe [C]='P'` |
| 2 | `>CodeListe [C]<>'P'` |
| 3 | `>TopListe [D]='AG' OR >TopListe [D]='BB' OR >TopListe [D]='EN'` |
| 14 | `[AN]=''` |
| 15 | `[AN]='' AND >TopListe [D]='CO'` |
| 16 | `[AN]='CIRCUIT'` |
| 33 | `w0_LibelleEdition [N]=''` |
| 41 | `INIGet ('[MAGIC_LOGICAL_NAMES]preview')='O'` |
| 42 | `>NbSelect [G]>0` |
| 43 | `[AH]<>'H'` |
| 48 | `>OnlyTAI [K]` |
| 50 | `[AZ] AND >OnlyTAI [K]` |
| 53 | `[EJ] AND [AI]<>[EN] AND Counter(0)>1` |

#### OTHER (10)

| IDE | Expression Decodee |
|-----|-------------------|
| 5 | `w0_g(TopListe) [P]` |
| 6 | `[AI]` |
| 7 | `[AJ]` |
| 10 | `GetParam ('SOCIETE')` |
| 11 | `'Village '&GetParam ('VILLAGE')` |
| 13 | `Counter (0)` |
| 45 | `w0_g(TopListe) [P]` |
| 46 | `[AI]` |
| 47 | `[AJ]` |
| 52 | `[AI]` |

#### REFERENCE_VG (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 12 | `VG1` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [  Liste CLients arrivant (IDE 156)](PBP-IDE-156.md) -> **Imp GM arrivant planning TAI (IDE 252)**

Main -> ... -> [  Affich arrivant planning GM (IDE 158)](PBP-IDE-158.md) -> **Imp GM arrivant planning TAI (IDE 252)**

```mermaid
graph LR
    T252[252 Imp GM arrivant pl...]
    style T252 fill:#58a6ff
    CC155[155 Liste des arrivants]
    style CC155 fill:#8b5cf6
    CC156[156 Liste CLients arri...]
    style CC156 fill:#3fb950
    CC158[158 Affich arrivant pl...]
    style CC158 fill:#3fb950
    CC155 --> CC156
    CC155 --> CC158
    CC156 --> T252
    CC158 --> T252
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [156](PBP-IDE-156.md) |   Liste CLients arrivant | 1 |
| [158](PBP-IDE-158.md) |   Affich arrivant planning GM | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T252[252 Imp GM arrivant pl...]
    style T252 fill:#58a6ff
    NONE[Aucun callee]
    T252 -.-> NONE
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
| Lignes de logique | 179 | Programme compact |
| Expressions | 55 | Logique moderee |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 179) | Code sain |
| Regles metier | 21 | Logique metier riche |

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
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 16:00*
