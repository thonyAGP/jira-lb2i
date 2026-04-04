# PBP IDE 171 - Imprim GM depart comptage

> **Analyse**: Phases 1-4 2026-02-03 15:36 -> 15:37 (19s) | Assemblage 15:37
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBP |
| IDE Position | 171 |
| Nom Programme | Imprim GM depart comptage |
| Fichier source | `Prg_171.xml` |
| Dossier IDE | Liste |
| Taches | 4 (1 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 1 |

## 2. DESCRIPTION FONCTIONNELLE

**Imprim GM depart comptage** assure la gestion complete de ce processus, accessible depuis [  Liste CLients depart (IDE 168)](PBP-IDE-168.md), [  Affich depart comptage GM (IDE 170)](PBP-IDE-170.md).

Le flux de traitement s'organise en **3 blocs fonctionnels** :

- **Traitement** (2 taches) : traitements metier divers
- **Impression** (1 tache) : generation de tickets et documents
- **Calcul** (1 tache) : calculs de montants, stocks ou compteurs

**Donnees modifiees** : 1 tables en ecriture (tempo_heures).

**Logique metier** : 20 regles identifiees couvrant conditions metier.

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (2 taches)

- **171** - Veuillez patienter... **[[ECRAN]](#ecran-t1)**
- **171.2** - Ligne commentaire

Delegue a : [  Suppression nationalite (IDE 166)](PBP-IDE-166.md)

#### Phase 2 : Calcul (1 tache)

- **171.1** - Calcul pied

#### Phase 3 : Impression (1 tache)

- **171.3** - Edition Nationalite

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| tempo_heures | **W**/L (2 usages) | Table temporaire ecran |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (2 taches)

Traitements internes.

---

#### <a id="t1"></a>171 - Veuillez patienter... [[ECRAN]](#ecran-t1)

**Role** : Traitement : Veuillez patienter....
**Ecran** : 422 x 56 DLU (MDI) | [Voir mockup](#ecran-t1)
**Delegue a** : [  Suppression nationalite (IDE 166)](PBP-IDE-166.md)

---

#### <a id="t3"></a>171.2 - Ligne commentaire

**Role** : Traitement : Ligne commentaire.
**Delegue a** : [  Suppression nationalite (IDE 166)](PBP-IDE-166.md)


### 3.2 Calcul (1 tache)

Calculs metier : montants, stocks, compteurs.

---

#### <a id="t2"></a>171.1 - Calcul pied

**Role** : Calcul : Calcul pied.
**Variables liees** : A (>DateCalcul), W (w0_NomPied01), X (w0_NbPied01), Y (w0_NomPied02), Z (w0_NbPied02)


### 3.3 Impression (1 tache)

Generation des documents et tickets.

---

#### <a id="t4"></a>171.3 - Edition Nationalite

**Role** : Generation du document : Edition Nationalite.
**Variables liees** : O (w0_LibelleEdition)


## 5. REGLES METIER

20 regles identifiees:

### Autres (20 regles)

#### <a id="rm-RM-001"></a>[RM-001] Si >TopListe [D]='AG' OR >TopListe [D]='BB' OR >TopListe [D]='EN' alors MlsTrans ('Naissance') sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='AG' OR >TopListe [D]='BB' OR >TopListe [D]='EN'` |
| **Si vrai** | MlsTrans ('Naissance') |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 5 : `IF (>TopListe [D]='AG' OR >TopListe [D]='BB' OR >TopListe [D` |
| **Exemple** | Si >TopListe [D]='AG' OR >TopListe [D]='BB' OR >TopListe [D]='EN' â†’ MlsTrans ('Naissance'). Sinon â†’ '') |

#### <a id="rm-RM-002"></a>[RM-002] Si >TopListe [D]='GR' alors MlsTrans ('GROUPE') sinon IF (>TopListe [D]='CA',MlsTrans ('DATE'),MlsTrans ('DATE / HEURE')))

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='GR'` |
| **Si vrai** | MlsTrans ('GROUPE') |
| **Si faux** | IF (>TopListe [D]='CA',MlsTrans ('DATE'),MlsTrans ('DATE / HEURE'))) |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 9 : `IF (>TopListe [D]='GR',MlsTrans ('GROUPE'),IF (>TopListe [D]` |
| **Exemple** | Si >TopListe [D]='GR' â†’ MlsTrans ('GROUPE') |

#### <a id="rm-RM-003"></a>[RM-003] Si >CodeListe [C]='A' alors MlsTrans ('arrivants') sinon IF (>CodeListe [C]='V',MlsTrans ('arrivees'),IF (>CodeListe [C]='P',MlsTrans ('presents'),IF (>CodeListe [C]='D',MlsTrans ('departs'),IF (>CodeListe [C]='R',MlsTrans ('partants'),MlsTrans ('absents'))))))

| Element | Detail |
|---------|--------|
| **Condition** | `>CodeListe [C]='A'` |
| **Si vrai** | MlsTrans ('arrivants') |
| **Si faux** | IF (>CodeListe [C]='V',MlsTrans ('arrivees'),IF (>CodeListe [C]='P',MlsTrans ('presents'),IF (>CodeListe [C]='D',MlsTrans ('departs'),IF (>CodeListe [C]='R',MlsTrans ('partants'),MlsTrans ('absents')))))) |
| **Variables** | C (>CodeListe) |
| **Expression source** | Expression 21 : `IF (>CodeListe [C]='A',MlsTrans ('arrivants'),IF (>CodeListe` |
| **Exemple** | Si >CodeListe [C]='A' â†’ MlsTrans ('arrivants') |

#### <a id="rm-RM-004"></a>[RM-004] Si >TopListe [D]='PL' alors 'planning' sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='PL'` |
| **Si vrai** | 'planning' |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 22 : `IF (>TopListe [D]='PL','planning','')` |
| **Exemple** | Si >TopListe [D]='PL' â†’ 'planning'. Sinon â†’ '') |

#### <a id="rm-RM-005"></a>[RM-005] Si >TopListe [D]='CA' alors MlsTrans ('caisse') sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='CA'` |
| **Si vrai** | MlsTrans ('caisse') |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 24 : `IF (>TopListe [D]='CA',MlsTrans ('caisse'),'')` |
| **Exemple** | Si >TopListe [D]='CA' â†’ MlsTrans ('caisse'). Sinon â†’ '') |

#### <a id="rm-RM-006"></a>[RM-006] Si >TopListe [D]='MI' alors MlsTrans ('millesias') sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='MI'` |
| **Si vrai** | MlsTrans ('millesias') |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 25 : `IF (>TopListe [D]='MI',MlsTrans ('millesias'),'')` |
| **Exemple** | Si >TopListe [D]='MI' â†’ MlsTrans ('millesias'). Sinon â†’ '') |

#### <a id="rm-RM-007"></a>[RM-007] Si >TopListe [D]='BB' alors MlsTrans ('bebe') sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='BB'` |
| **Si vrai** | MlsTrans ('bebe') |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 26 : `IF (>TopListe [D]='BB',MlsTrans ('bebe'),'')` |
| **Exemple** | Si >TopListe [D]='BB' â†’ MlsTrans ('bebe'). Sinon â†’ '') |

#### <a id="rm-RM-008"></a>[RM-008] Si >TopListe [D]='EN' alors MlsTrans ('enfant') sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='EN'` |
| **Si vrai** | MlsTrans ('enfant') |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 27 : `IF (>TopListe [D]='EN',MlsTrans ('enfant'),'')` |
| **Exemple** | Si >TopListe [D]='EN' â†’ MlsTrans ('enfant'). Sinon â†’ '') |

#### <a id="rm-RM-009"></a>[RM-009] Si >TopListe [D]='SI' alors 'single' sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='SI'` |
| **Si vrai** | 'single' |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 28 : `IF (>TopListe [D]='SI','single','')` |
| **Exemple** | Si >TopListe [D]='SI' â†’ 'single'. Sinon â†’ '') |

#### <a id="rm-RM-010"></a>[RM-010] Si >TopListe [D]='NS' alors 'non single' sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='NS'` |
| **Si vrai** | 'non single' |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 29 : `IF (>TopListe [D]='NS','non single','')` |
| **Exemple** | Si >TopListe [D]='NS' â†’ 'non single'. Sinon â†’ '') |

#### <a id="rm-RM-011"></a>[RM-011] Si >TopListe [D]='PY' alors MlsTrans ('pays') sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='PY'` |
| **Si vrai** | MlsTrans ('pays') |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 30 : `IF (>TopListe [D]='PY',MlsTrans ('pays'),'')` |
| **Exemple** | Si >TopListe [D]='PY' â†’ MlsTrans ('pays'). Sinon â†’ '') |

#### <a id="rm-RM-012"></a>[RM-012] Si >TopListe [D]='HM' alors 'honey moon' sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='HM'` |
| **Si vrai** | 'honey moon' |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 31 : `IF (>TopListe [D]='HM','honey moon','')` |
| **Exemple** | Si >TopListe [D]='HM' â†’ 'honey moon'. Sinon â†’ '') |

#### <a id="rm-RM-013"></a>[RM-013] Si >TopListe [D]='VV' alors 'Vil/Vil' sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='VV'` |
| **Si vrai** | 'Vil/Vil' |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 32 : `IF (>TopListe [D]='VV','Vil/Vil','')` |
| **Exemple** | Si >TopListe [D]='VV' â†’ 'Vil/Vil'. Sinon â†’ '') |

#### <a id="rm-RM-014"></a>[RM-014] Si >TopListe [D]='NV' alors 'non Vil/Vil' sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='NV'` |
| **Si vrai** | 'non Vil/Vil' |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 33 : `IF (>TopListe [D]='NV','non Vil/Vil','')` |
| **Exemple** | Si >TopListe [D]='NV' â†’ 'non Vil/Vil'. Sinon â†’ '') |

#### <a id="rm-RM-015"></a>[RM-015] Si >TopListe [D]='AG' alors MlsTrans ('age du')&' '&Str (>AgeMin [H] sinon '2')&' / '&Str (>AgeMax [I],'2')&' ans','')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='AG'` |
| **Si vrai** | MlsTrans ('age du')&' '&Str (>AgeMin [H] |
| **Si faux** | '2')&' / '&Str (>AgeMax [I],'2')&' ans','') |
| **Variables** | D (>TopListe), H (>AgeMin), I (>AgeMax) |
| **Expression source** | Expression 34 : `IF (>TopListe [D]='AG',MlsTrans ('age du')&' '&Str (>AgeMin ` |
| **Exemple** | Si >TopListe [D]='AG' â†’ MlsTrans ('age du')&' '&Str (>AgeMin [H]. Sinon â†’ '2')&' / '&Str (>AgeMax [I],'2')&' ans','') |

#### <a id="rm-RM-016"></a>[RM-016] Si >TopListe [D]='CO' alors MlsTrans ('commentaire') sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='CO'` |
| **Si vrai** | MlsTrans ('commentaire') |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 35 : `IF (>TopListe [D]='CO',MlsTrans ('commentaire'),'')` |
| **Exemple** | Si >TopListe [D]='CO' â†’ MlsTrans ('commentaire'). Sinon â†’ '') |

#### <a id="rm-RM-017"></a>[RM-017] Si >TopListe [D]='CP' alors MlsTrans ('comptage') sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='CP'` |
| **Si vrai** | MlsTrans ('comptage') |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 36 : `IF (>TopListe [D]='CP',MlsTrans ('comptage'),'')` |
| **Exemple** | Si >TopListe [D]='CP' â†’ MlsTrans ('comptage'). Sinon â†’ '') |

#### <a id="rm-RM-018"></a>[RM-018] Si [ER] OR [ET] OR [EZ] alors 'EA' sinon '')&IF([ER],Trim(VG61),'')&IF([ET],Trim(VG62),'')&IF([EZ],Trim(VG63),'')

| Element | Detail |
|---------|--------|
| **Condition** | `[ER] OR [ET] OR [EZ]` |
| **Si vrai** | 'EA' |
| **Si faux** | '')&IF([ER],Trim(VG61),'')&IF([ET],Trim(VG62),'')&IF([EZ],Trim(VG63),'') |
| **Expression source** | Expression 58 : `IF([ER] OR [ET] OR [EZ],'EA','')&IF([ER],Trim(VG61),'')&IF([` |
| **Exemple** | Si [ER] OR [ET] OR [EZ] â†’ 'EA' |

#### <a id="rm-RM-019"></a>[RM-019] Si [FG] alors [FI]&[FJ]&Str([AI] sinon '3P0'),W0_Libelle Logement [R]&Str([AI],'3P0'))

| Element | Detail |
|---------|--------|
| **Condition** | `[FG]` |
| **Si vrai** | [FI]&[FJ]&Str([AI] |
| **Si faux** | '3P0'),W0_Libelle Logement [R]&Str([AI],'3P0')) |
| **Variables** | R (W0_Libelle Logement) |
| **Expression source** | Expression 60 : `IF([FG],[FI]&[FJ]&Str([AI],'3P0'),W0_Libelle Logement [R]&St` |
| **Exemple** | Si [FG] â†’ [FI]&[FJ]&Str([AI]. Sinon â†’ '3P0'),W0_Libelle Logement [R]&Str([AI],'3P0')) |

#### <a id="rm-RM-020"></a>[RM-020] Si VG88 AND [FM] alors TStr([FL] sinon 'HHhMMZ'),[AC])

| Element | Detail |
|---------|--------|
| **Condition** | `VG88 AND [FM]` |
| **Si vrai** | TStr([FL] |
| **Si faux** | 'HHhMMZ'),[AC]) |
| **Expression source** | Expression 63 : `IF(VG88 AND [FM],TStr([FL],'HHhMMZ'),[AC])` |
| **Exemple** | Si VG88 AND [FM] â†’ TStr([FL]. Sinon â†’ 'HHhMMZ'),[AC]) |

## 6. CONTEXTE

- **Appele par**: [  Liste CLients depart (IDE 168)](PBP-IDE-168.md), [  Affich depart comptage GM (IDE 170)](PBP-IDE-170.md)
- **Appelle**: 1 programmes | **Tables**: 9 (W:1 R:3 L:6) | **Taches**: 4 | **Expressions**: 67

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 4)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 171 | 171 | Veuillez patienter... | MDI | 422 | 56 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>171 - Veuillez patienter...
**Tache** : [171](#t1) | **Type** : MDI | **Dimensions** : 422 x 56 DLU
**Bloc** : Traitement | **Titre IDE** : Veuillez patienter...

<!-- FORM-DATA:
{
    "width":  422,
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
    "taskId":  "171",
    "height":  56
}
-->

## 9. NAVIGATION

Ecran unique: **Veuillez patienter...**

### 9.3 Structure hierarchique (4 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **171.1** | [**Veuillez patienter...** (171)](#t1) [mockup](#ecran-t1) | MDI | 422x56 | Traitement |
| 171.1.1 | [Ligne commentaire (171.2)](#t3) | MDI | - | |
| **171.2** | [**Calcul pied** (171.1)](#t2) | MDI | - | Calcul |
| **171.3** | [**Edition Nationalite** (171.3)](#t4) | MDI | - | Impression |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Traitement principal]
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

### Tables utilisees (9)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 31 | gm-complet_______gmc |  | DB | R |   |   | 1 |
| 119 | tables_pays_tel_ |  | DB |   |   | L | 1 |
| 121 | tables_pays_ventes | Donnees de ventes | DB |   |   | L | 1 |
| 171 | commentaire______com |  | DB | R |   |   | 1 |
| 358 | import_mod |  | DB |   |   | L | 1 |
| 598 | tempo_ecr_previsions | Table temporaire ecran | TMP | R |   |   | 1 |
| 600 | tempo_heures | Table temporaire ecran | TMP |   | **W** | L | 2 |
| 619 | tempo_userlist | Table temporaire ecran | TMP |   |   | L | 1 |
| 804 | valeur_credit_bar_defaut |  | DB |   |   | L | 1 |

### Colonnes par table (2 / 4 tables avec colonnes identifiees)

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
| K | >Libellé Sélection du Solde* | R | Unicode |
| L | >Soldé,Non_soldé,Tous | R | Unicode |
| M | > Tri Nom / Filiation | R | Logical |
| N | P.I Heure depart village | R | Logical |
| O | w0_LibelleEdition | R | Alpha |
| P | w0_f(CodeListe) | R | Alpha |
| Q | w0_g(TopListe) | R | Alpha |
| R | W0_Libelle Logement | R | Alpha |
| S | V.Existe ECI (Q60 Location) | R | Logical |
| T | V.Existe ECI (Q61 Cours) | R | Logical |
| U | V.Existe ECI (Q62 Enfant) | R | Logical |
| V | v Libelle affichage ECI | R | Alpha |
| W | w0_NomPied01 | R | Alpha |
| X | w0_NbPied01 | R | Numeric |
| Y | w0_NomPied02 | R | Alpha |
| Z | w0_NbPied02 | R | Numeric |
| BA | w0_NomPied03 | R | Alpha |
| BB | w0_NbPied03 | R | Numeric |
| BC | w0_NomPied04 | R | Alpha |
| BD | w0_NbPied04 | R | Numeric |
| BE | w0_NomPied05 | R | Alpha |
| BF | w0_NbPied05 | R | Numeric |
| BG | w0_Ordre Tri | R | Alpha |
| BH | w0_dernier n° Compte | R | Numeric |
| BI | w0_TotalSelect | R | Numeric |

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

<details>
<summary>Table 600 - tempo_heures (**W**/L) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (1)

Variables recues du programme appelant ([  Liste CLients depart (IDE 168)](PBP-IDE-168.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| N | P.I Heure depart village | Logical | - |

### 11.2 Variables de session (4)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| S | V.Existe ECI (Q60 Location) | Logical | - |
| T | V.Existe ECI (Q61 Cours) | Logical | - |
| U | V.Existe ECI (Q62 Enfant) | Logical | - |
| V | v Libelle affichage ECI | Alpha | - |

### 11.3 Autres (30)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | >DateCalcul | Date | 3x refs |
| B | >HeurePresence | Alpha | 2x refs |
| C | >CodeListe | Alpha | 5x refs |
| D | >TopListe | Alpha | 25x refs |
| E | >NomLogement | Alpha | - |
| F | >Total | Numeric | - |
| G | >NbSelect | Numeric | 1x refs |
| H | >AgeMin | Numeric | 1x refs |
| I | >AgeMax | Numeric | 1x refs |
| J | >CodeGroupe | Alpha | 4x refs |
| K | >Libellé Sélection du Solde* | Unicode | - |
| L | >Soldé,Non_soldé,Tous | Unicode | 3x refs |
| M | > Tri Nom / Filiation | Logical | 4x refs |
| O | w0_LibelleEdition | Alpha | 2x refs |
| P | w0_f(CodeListe) | Alpha | - |
| Q | w0_g(TopListe) | Alpha | - |
| R | W0_Libelle Logement | Alpha | 1x refs |
| W | w0_NomPied01 | Alpha | - |
| X | w0_NbPied01 | Numeric | 1x refs |
| Y | w0_NomPied02 | Alpha | - |
| Z | w0_NbPied02 | Numeric | 1x refs |
| BA | w0_NomPied03 | Alpha | - |
| BB | w0_NbPied03 | Numeric | - |
| BC | w0_NomPied04 | Alpha | - |
| BD | w0_NbPied04 | Numeric | 1x refs |
| BE | w0_NomPied05 | Alpha | - |
| BF | w0_NbPied05 | Numeric | - |
| BG | w0_Ordre Tri | Alpha | - |
| BH | w0_dernier n° Compte | Numeric | - |
| BI | w0_TotalSelect | Numeric | - |

<details>
<summary>Toutes les 35 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| P0 | **N** | P.I Heure depart village | Logical |
| V. | **S** | V.Existe ECI (Q60 Location) | Logical |
| V. | **T** | V.Existe ECI (Q61 Cours) | Logical |
| V. | **U** | V.Existe ECI (Q62 Enfant) | Logical |
| V. | **V** | v Libelle affichage ECI | Alpha |
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
| Autre | **K** | >Libellé Sélection du Solde* | Unicode |
| Autre | **L** | >Soldé,Non_soldé,Tous | Unicode |
| Autre | **M** | > Tri Nom / Filiation | Logical |
| Autre | **O** | w0_LibelleEdition | Alpha |
| Autre | **P** | w0_f(CodeListe) | Alpha |
| Autre | **Q** | w0_g(TopListe) | Alpha |
| Autre | **R** | W0_Libelle Logement | Alpha |
| Autre | **W** | w0_NomPied01 | Alpha |
| Autre | **X** | w0_NbPied01 | Numeric |
| Autre | **Y** | w0_NomPied02 | Alpha |
| Autre | **Z** | w0_NbPied02 | Numeric |
| Autre | **BA** | w0_NomPied03 | Alpha |
| Autre | **BB** | w0_NbPied03 | Numeric |
| Autre | **BC** | w0_NomPied04 | Alpha |
| Autre | **BD** | w0_NbPied04 | Numeric |
| Autre | **BE** | w0_NomPied05 | Alpha |
| Autre | **BF** | w0_NbPied05 | Numeric |
| Autre | **BG** | w0_Ordre Tri | Alpha |
| Autre | **BH** | w0_dernier n° Compte | Numeric |
| Autre | **BI** | w0_TotalSelect | Numeric |

</details>

## 12. EXPRESSIONS

**67 / 67 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONCATENATION | 10 | 5 |
| CALCULATION | 1 | 0 |
| CONDITION | 36 | 19 |
| CONSTANTE | 5 | 0 |
| OTHER | 11 | 0 |
| REFERENCE_VG | 4 | 0 |

### 12.2 Expressions cles par type

#### CONCATENATION (10 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 34 | `IF (>TopListe [D]='AG',MlsTrans ('age du')&' '&Str (>AgeMin [H],'2')&' / '&Str (>AgeMax [I],'2')&' ans','')` | [RM-015](#rm-RM-015) |
| CONCATENATION | 64 | `MlsTrans('Heure de fin :')&' '&MlsTrans(IF(VG88 AND [FM], 'Libération logement','Départ Village'))` | - |
| CONCATENATION | 43 | `MlsTrans ('Depart le')&' '&DStr (w0_NbPied02 [Z],'DD/MM/YYYY')&' '&MlsTrans ('à')&' '&[AA]&'  '&MlsTrans ('Retour le')&'  '&DStr ([AB],'DD/MM/YYYY')&' '&MlsTrans ('à')&' '&[AC]` | - |
| CONCATENATION | 54 | `Trim([ES])&IF(VG125 AND [FN]='O','N','')` | - |
| CONCATENATION | 41 | `Trim (>Libellé Sélection du ... [K])&' '&IF (>CodeListe [C]='P',>HeurePresence [B]&' h','')` | - |
| ... | | *+5 autres* | |

#### CALCULATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 52 | `w0_NbPied04 [BD]+1` | - |

#### CONDITION (36 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 31 | `IF (>TopListe [D]='HM','honey moon','')` | [RM-012](#rm-RM-012) |
| CONDITION | 32 | `IF (>TopListe [D]='VV','Vil/Vil','')` | [RM-013](#rm-RM-013) |
| CONDITION | 30 | `IF (>TopListe [D]='PY',MlsTrans ('pays'),'')` | [RM-011](#rm-RM-011) |
| CONDITION | 28 | `IF (>TopListe [D]='SI','single','')` | [RM-009](#rm-RM-009) |
| CONDITION | 29 | `IF (>TopListe [D]='NS','non single','')` | [RM-010](#rm-RM-010) |
| ... | | *+31 autres* | |

#### CONSTANTE (5 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 56 | `61` | - |
| CONSTANTE | 57 | `62` | - |
| CONSTANTE | 55 | `60` | - |
| CONSTANTE | 44 | `''` | - |
| CONSTANTE | 49 | `'PNT'` | - |

#### OTHER (11 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 50 | `w0_NbPied01 [X]` | - |
| OTHER | 17 | `Counter (0)` | - |
| OTHER | 51 | `[AW]` | - |
| OTHER | 61 | `[AH]` | - |
| OTHER | 53 | `w0_LibelleEdition [O]` | - |
| ... | | *+6 autres* | |

#### REFERENCE_VG (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 59 | `VG5` | - |
| REFERENCE_VG | 65 | `VG88` | - |
| REFERENCE_VG | 16 | `VG1` | - |
| REFERENCE_VG | 48 | `VG1` | - |

### 12.3 Toutes les expressions (67)

<details>
<summary>Voir les 67 expressions</summary>

#### CONCATENATION (10)

| IDE | Expression Decodee |
|-----|-------------------|
| 45 | `'- '&Str (Page (0,1),'3P0Z0')&' -'` |
| 34 | `IF (>TopListe [D]='AG',MlsTrans ('age du')&' '&Str (>AgeMin [H],'2')&' / '&Str (>AgeMax [I],'2')&' ans','')` |
| 38 | `MlsTrans ('Liste des')&' '&Trim (>Soldé,Non_soldé,Tous [L])&' '&Trim (> Tri Nom / Filiation [M])&' '&IF (>TopListe [D]='CP' OR >TopListe [D]='GR',Trim (>CodeGroupe [J]),'')&IF (>TopListe [D]='GR',' '&>HeurePresence [B]&' h','')&' '&MlsTrans ('le')&' '&DStr (>DateCalcul [A],'DD/MM/YYYY')` |
| 39 | `MlsTrans ('Liste des')&' '&Trim (>Soldé,Non_soldé,Tous [L])&' '&Trim (> Tri Nom / Filiation [M])&' '&IF (>TopListe [D]='CP' OR >TopListe [D]='GR',MlsTrans ('Toutes categories'),'')&' du '&DStr (>DateCalcul [A],'DD/MM/YYYY')` |
| 40 | `MlsTrans ('Liste des')&' '&Trim (>Soldé,Non_soldé,Tous [L])&' '&Trim (> Tri Nom / Filiation [M])&' '&IF (>TopListe [D]='CP' OR >TopListe [D]='GR',Trim (>CodeGroupe [J]),'')&' '&MlsTrans ('le')&' '&DStr (>DateCalcul [A],'DD/MM/YYYY')` |
| 42 | `MlsTrans ('Edition du')&' '&DStr (Date (),'DD/MM/YYYY')&' '&MlsTrans ('à')&' '&TStr (Time (),'HH:MM:SS')` |
| 43 | `MlsTrans ('Depart le')&' '&DStr (w0_NbPied02 [Z],'DD/MM/YYYY')&' '&MlsTrans ('à')&' '&[AA]&'  '&MlsTrans ('Retour le')&'  '&DStr ([AB],'DD/MM/YYYY')&' '&MlsTrans ('à')&' '&[AC]` |
| 64 | `MlsTrans('Heure de fin :')&' '&MlsTrans(IF(VG88 AND [FM], 'Libération logement','Départ Village'))` |
| 41 | `Trim (>Libellé Sélection du ... [K])&' '&IF (>CodeListe [C]='P',>HeurePresence [B]&' h','')` |
| 54 | `Trim([ES])&IF(VG125 AND [FN]='O','N','')` |

#### CALCULATION (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 52 | `w0_NbPied04 [BD]+1` |

#### CONDITION (36)

| IDE | Expression Decodee |
|-----|-------------------|
| 5 | `IF (>TopListe [D]='AG' OR >TopListe [D]='BB' OR >TopListe [D]='EN',MlsTrans ('Naissance'),'')` |
| 9 | `IF (>TopListe [D]='GR',MlsTrans ('GROUPE'),IF (>TopListe [D]='CA',MlsTrans ('DATE'),MlsTrans ('DATE / HEURE')))` |
| 10 | `IF (>TopListe [D]='GR',MlsTrans ('DEPART'),IF (>TopListe [D]='CA',MlsTrans ('FERMETURE'),MlsTrans ('DEPART')))` |
| 11 | `IF (>TopListe [D]='GR',MlsTrans ('GROUPE'),IF (>TopListe [D]='CA',MlsTrans ('DATE'),MlsTrans ('DATE / HEURE')))` |
| 12 | `IF (>TopListe [D]='GR',MlsTrans ('ARRIVEE'),IF (>TopListe [D]='CA',MlsTrans ('OUVERTURE'),MlsTrans ('ARRIVEE')))` |
| 21 | `IF (>CodeListe [C]='A',MlsTrans ('arrivants'),IF (>CodeListe [C]='V',MlsTrans ('arrivees'),IF (>CodeListe [C]='P',MlsTrans ('presents'),IF (>CodeListe [C]='D',MlsTrans ('departs'),IF (>CodeListe [C]='R',MlsTrans ('partants'),MlsTrans ('absents'))))))` |
| 22 | `IF (>TopListe [D]='PL','planning','')` |
| 23 | `IF (>TopListe [D]='GR',MlsTrans ('vol'),'')` |
| 24 | `IF (>TopListe [D]='CA',MlsTrans ('caisse'),'')` |
| 25 | `IF (>TopListe [D]='MI',MlsTrans ('millesias'),'')` |
| 26 | `IF (>TopListe [D]='BB',MlsTrans ('bebe'),'')` |
| 27 | `IF (>TopListe [D]='EN',MlsTrans ('enfant'),'')` |
| 28 | `IF (>TopListe [D]='SI','single','')` |
| 29 | `IF (>TopListe [D]='NS','non single','')` |
| 30 | `IF (>TopListe [D]='PY',MlsTrans ('pays'),'')` |
| 31 | `IF (>TopListe [D]='HM','honey moon','')` |
| 32 | `IF (>TopListe [D]='VV','Vil/Vil','')` |
| 33 | `IF (>TopListe [D]='NV','non Vil/Vil','')` |
| 35 | `IF (>TopListe [D]='CO',MlsTrans ('commentaire'),'')` |
| 36 | `IF (>TopListe [D]='CP',MlsTrans ('comptage'),'')` |
| 58 | `IF([ER] OR [ET] OR [EZ],'EA','')&IF([ER],Trim(VG61),'')&IF([ET],Trim(VG62),'')&IF([EZ],Trim(VG63),'')` |
| 60 | `IF([FG],[FI]&[FJ]&Str([AI],'3P0'),W0_Libelle Logement [R]&Str([AI],'3P0'))` |
| 63 | `IF(VG88 AND [FM],TStr([FL],'HHhMMZ'),[AC])` |
| 1 | `>CodeListe [C]='P'` |
| 2 | `>CodeListe [C]<>'P' AND >CodeGroupe [J]<>''` |
| 3 | `>CodeListe [C]<>'P' AND >CodeGroupe [J]=''` |
| 4 | `>TopListe [D]='AG' OR >TopListe [D]='BB' OR >TopListe [D]='EN'` |
| 18 | `[AM]=''` |
| 19 | `[AM]='' AND >TopListe [D]='CO'` |
| 20 | `[AM]='CIRCUIT'` |
| 37 | `> Tri Nom / Filiation [M]=''` |
| 46 | `INIGet ('[MAGIC_LOGICAL_NAMES]preview')='O'` |
| 47 | `>NbSelect [G]>0` |
| 62 | `[FG] AND Counter(0)>1 AND [AH]<>[FK]` |
| 66 | `[FP]='T'` |
| 67 | `CndRange(Trim([FO])<>'' AND [FP]<>'T',IF([FP]='N','X',''))` |

#### CONSTANTE (5)

| IDE | Expression Decodee |
|-----|-------------------|
| 44 | `''` |
| 49 | `'PNT'` |
| 55 | `60` |
| 56 | `61` |
| 57 | `62` |

#### OTHER (11)

| IDE | Expression Decodee |
|-----|-------------------|
| 6 | `w0_LibelleEdition [O]` |
| 7 | `[AH]` |
| 8 | `[AI]` |
| 13 | `GetParam ('SOCIETE')` |
| 14 | `'Village '&GetParam ('VILLAGE')` |
| 15 | `GetParam ('LANGUE')` |
| 17 | `Counter (0)` |
| 50 | `w0_NbPied01 [X]` |
| 51 | `[AW]` |
| 53 | `w0_LibelleEdition [O]` |
| 61 | `[AH]` |

#### REFERENCE_VG (4)

| IDE | Expression Decodee |
|-----|-------------------|
| 16 | `VG1` |
| 48 | `VG1` |
| 59 | `VG5` |
| 65 | `VG88` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [  Liste CLients depart (IDE 168)](PBP-IDE-168.md) -> **Imprim GM depart comptage (IDE 171)**

Main -> ... -> [  Affich depart comptage GM (IDE 170)](PBP-IDE-170.md) -> **Imprim GM depart comptage (IDE 171)**

```mermaid
graph LR
    T171[171 Imprim GM depart c...]
    style T171 fill:#58a6ff
    CC167[167 Liste des departs]
    style CC167 fill:#8b5cf6
    CC168[168 Liste CLients depart]
    style CC168 fill:#3fb950
    CC170[170 Affich depart comp...]
    style CC170 fill:#3fb950
    CC167 --> CC168
    CC167 --> CC170
    CC168 --> T171
    CC170 --> T171
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [168](PBP-IDE-168.md) |   Liste CLients depart | 1 |
| [170](PBP-IDE-170.md) |   Affich depart comptage GM | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T171[171 Imprim GM depart c...]
    style T171 fill:#58a6ff
    C166[166 Suppression nation...]
    T171 --> C166
    style C166 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [166](PBP-IDE-166.md) |   Suppression nationalite | 1 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 228 | Taille moyenne |
| Expressions | 67 | Logique moderee |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 1 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 228) | Code sain |
| Regles metier | 20 | Logique metier riche |

### 14.2 Plan de migration par bloc

#### Traitement (2 taches: 1 ecran, 1 traitement)

- **Strategie** : Orchestrateur avec 1 ecrans (Razor/React) et 1 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 1 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Calcul (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Services de calcul purs (Domain Services).
- Migrer la logique de calcul (stock, compteurs, montants)

#### Impression (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Templates HTML -> PDF via wkhtmltopdf ou Puppeteer.
- `PrintService` injectable avec choix imprimante

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| tempo_heures | Table WRITE (Temp) | 1x | Schema + repository |
| [  Suppression nationalite (IDE 166)](PBP-IDE-166.md) | Sous-programme | 1x | Normale - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 15:37*
