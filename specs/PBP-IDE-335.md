# PBP IDE 335 - Creation tempo toutes GO

> **Analyse**: Phases 1-4 2026-02-03 16:29 -> 16:29 (14s) | Assemblage 16:29
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBP |
| IDE Position | 335 |
| Nom Programme | Creation tempo toutes GO |
| Fichier source | `Prg_335.xml` |
| Dossier IDE | Remplissage |
| Taches | 4 (1 ecrans visibles) |
| Tables modifiees | 2 |
| Programmes appeles | 3 |

## 2. DESCRIPTION FONCTIONNELLE

**Creation tempo toutes GO** assure la gestion complete de ce processus, accessible depuis [  Liste present personnel plan (IDE 227)](PBP-IDE-227.md), [  Liste personnels AVPBDR (IDE 234)](PBP-IDE-234.md), [Pilotage Gestion de Crise (IDE 146)](PBP-IDE-146.md).

Le flux de traitement s'organise en **3 blocs fonctionnels** :

- **Creation** (2 taches) : insertion d'enregistrements en base (mouvements, prestations)
- **Consultation** (1 tache) : ecrans de recherche, selection et consultation
- **Traitement** (1 tache) : traitements metier divers

**Donnees modifiees** : 2 tables en ecriture (tempo_mecano_dossier_grou, tempo_userlist).

**Logique metier** : 7 regles identifiees couvrant conditions metier, valeurs par defaut.

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (1 tache)

- **335** - Veuillez patienter ... **[[ECRAN]](#ecran-t1)**

#### Phase 2 : Creation (2 taches)

- **335.1** - Creation Tempo gene
- **335.2** - Creation tempo bateaux police

#### Phase 3 : Consultation (1 tache)

- **335.3** - Recherche Code Village

Delegue a : [Recherche age Bebe_Enfant (IDE 307)](PBP-IDE-307.md)

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| tempo_mecano_dossier_grou | **W**/L (2 usages) | Table temporaire ecran |
| tempo_userlist | **W**/L (2 usages) | Table temporaire ecran |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>335 - Veuillez patienter ... [[ECRAN]](#ecran-t1)

**Role** : Traitement : Veuillez patienter ....
**Ecran** : 424 x 57 DLU (MDI) | [Voir mockup](#ecran-t1)


### 3.2 Creation (2 taches)

Insertion de nouveaux enregistrements en base.

---

#### <a id="t2"></a>335.1 - Creation Tempo gene

**Role** : Creation d'enregistrement : Creation Tempo gene.

---

#### <a id="t3"></a>335.2 - Creation tempo bateaux police

**Role** : Creation d'enregistrement : Creation tempo bateaux police.


### 3.3 Consultation (1 tache)

Ecrans de recherche et consultation.

---

#### <a id="t4"></a>335.3 - Recherche Code Village

**Role** : Traitement : Recherche Code Village.
**Variables liees** : BD (v.Code vol aller A), BF (v.Code vol retour Z), J (>CodeListe), N (>CodeVol), O (>DateVillage)
**Delegue a** : [Recherche age Bebe_Enfant (IDE 307)](PBP-IDE-307.md)


## 5. REGLES METIER

7 regles identifiees:

### Autres (7 regles)

#### <a id="rm-RM-001"></a>[RM-001] Si >CodeListe [J]='P' alors >DateCalcul [B] sinon >Soldé,Non_soldé,Tous [Y])

| Element | Detail |
|---------|--------|
| **Condition** | `>CodeListe [J]='P'` |
| **Si vrai** | >DateCalcul [B] |
| **Si faux** | >Soldé,Non_soldé,Tous [Y]) |
| **Variables** | B (>DateCalcul), J (>CodeListe), Y (>Soldé,Non_soldé,Tous) |
| **Expression source** | Expression 18 : `IF (>CodeListe [J]='P',>DateCalcul [B],>Soldé,Non_soldé,Tous` |
| **Exemple** | Si >CodeListe [J]='P' â†’ >DateCalcul [B]. Sinon â†’ >Soldé,Non_soldé,Tous [Y]) |

#### <a id="rm-RM-002"></a>[RM-002] Si >Index [A]=5 alors >DateMaxDebut [E]+14 sinon >DateMaxDebut [E])

| Element | Detail |
|---------|--------|
| **Condition** | `>Index [A]=5` |
| **Si vrai** | >DateMaxDebut [E]+14 |
| **Si faux** | >DateMaxDebut [E]) |
| **Variables** | A (>Index), E (>DateMaxDebut) |
| **Expression source** | Expression 30 : `IF (>Index [A]=5,>DateMaxDebut [E]+14,>DateMaxDebut [E])` |
| **Exemple** | Si >Index [A]=5 â†’ >DateMaxDebut [E]+14. Sinon â†’ >DateMaxDebut [E]) |

#### <a id="rm-RM-003"></a>[RM-003] Si >Index [A]=6 alors >DateMaxFin [G]+14 sinon >DateMaxFin [G])

| Element | Detail |
|---------|--------|
| **Condition** | `>Index [A]=6` |
| **Si vrai** | >DateMaxFin [G]+14 |
| **Si faux** | >DateMaxFin [G]) |
| **Variables** | A (>Index), G (>DateMaxFin) |
| **Expression source** | Expression 31 : `IF (>Index [A]=6,>DateMaxFin [G]+14,>DateMaxFin [G])` |
| **Exemple** | Si >Index [A]=6 â†’ >DateMaxFin [G]+14. Sinon â†’ >DateMaxFin [G]) |

#### <a id="rm-RM-004"></a>[RM-004] Si [OQ]>0 alors [OQ] sinon 0)

| Element | Detail |
|---------|--------|
| **Condition** | `[OQ]>0` |
| **Si vrai** | [OQ] |
| **Si faux** | 0) |
| **Expression source** | Expression 42 : `IF ([OQ]>0,[OQ],0)` |
| **Exemple** | Si [OQ]>0 â†’ [OQ]. Sinon â†’ 0) |

#### <a id="rm-RM-005"></a>[RM-005] Si >CodeListe [J]<>'P' alors w0_NumAdherent [CA]=>TypeHebergement [L] AND Trim(MID (w0_TypeEcran [BZ] sinon 2,2))='1',[EL]=>TypeHebergement [L] AND Trim(MID ([EQ],2,2))='1')

| Element | Detail |
|---------|--------|
| **Condition** | `>CodeListe [J]<>'P'` |
| **Si vrai** | w0_NumAdherent [CA]=>TypeHebergement [L] AND Trim(MID (w0_TypeEcran [BZ] |
| **Si faux** | 2,2))='1',[EL]=>TypeHebergement [L] AND Trim(MID ([EQ],2,2))='1') |
| **Variables** | J (>CodeListe), L (>TypeHebergement), BO (w0_Type), BZ (w0_TypeEcran), CA (w0_NumAdherent) |
| **Expression source** | Expression 75 : `IF (>CodeListe [J]<>'P',w0_NumAdherent [CA]=>TypeHebergement` |
| **Exemple** | Si >CodeListe [J]<>'P' â†’ w0_NumAdherent [CA]=>TypeHebergement [L] AND Trim(MID (w0_TypeEcran [BZ] |

#### <a id="rm-RM-006"></a>[RM-006] Valeur par defaut si w0_CondArrive [CE] est vide

| Element | Detail |
|---------|--------|
| **Condition** | `w0_CondArrive [CE]='' OR w0_CondArrive [CE]='*'` |
| **Si vrai** | [PH] |
| **Si faux** | w0_CondArrive [CE]) |
| **Variables** | CE (w0_CondArrive) |
| **Expression source** | Expression 127 : `IF(w0_CondArrive [CE]='' OR w0_CondArrive [CE]='*',[PH],w0_C` |
| **Exemple** | Si w0_CondArrive [CE]='' OR w0_CondArrive [CE]='*' â†’ [PH]. Sinon â†’ w0_CondArrive [CE]) |

#### <a id="rm-RM-007"></a>[RM-007] Si VG88 alors CodeVolAller([AA] sinon [AB]), [PN])

| Element | Detail |
|---------|--------|
| **Condition** | `VG88` |
| **Si vrai** | CodeVolAller([AA] |
| **Si faux** | [AB]), [PN]) |
| **Expression source** | Expression 128 : `IF(VG88, CodeVolAller([AA], [AB]), [PN])` |
| **Exemple** | Si VG88 â†’ CodeVolAller([AA]. Sinon â†’ [AB]), [PN]) |

## 6. CONTEXTE

- **Appele par**: [  Liste present personnel plan (IDE 227)](PBP-IDE-227.md), [  Liste personnels AVPBDR (IDE 234)](PBP-IDE-234.md), [Pilotage Gestion de Crise (IDE 146)](PBP-IDE-146.md)
- **Appelle**: 3 programmes | **Tables**: 16 (W:2 R:2 L:14) | **Taches**: 4 | **Expressions**: 138

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 4)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 335 | 335 | Veuillez patienter ... | MDI | 424 | 57 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>335 - Veuillez patienter ...
**Tache** : [335](#t1) | **Type** : MDI | **Dimensions** : 424 x 57 DLU
**Bloc** : Traitement | **Titre IDE** : Veuillez patienter ...

<!-- FORM-DATA:
{
    "width":  424,
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
                         "x":  101,
                         "type":  "label",
                         "var":  "",
                         "y":  10,
                         "w":  277,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "7",
                         "text":  "Traitement GO en cours ...",
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
                         "x":  103,
                         "type":  "label",
                         "var":  "",
                         "y":  33,
                         "w":  114,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Analyses :",
                         "parent":  4
                     },
                     {
                         "x":  103,
                         "type":  "label",
                         "var":  "",
                         "y":  44,
                         "w":  150,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Selectionnes :",
                         "parent":  4
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
                     },
                     {
                         "x":  265,
                         "type":  "edit",
                         "var":  "",
                         "y":  31,
                         "w":  56,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  265,
                         "type":  "edit",
                         "var":  "",
                         "y":  43,
                         "w":  56,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     }
                 ],
    "taskId":  "335",
    "height":  57
}
-->

<details>
<summary><strong>Champs : 2 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 265,31 | (sans nom) | - | edit |
| 265,43 | (sans nom) | - | edit |

</details>

## 9. NAVIGATION

Ecran unique: **Veuillez patienter ...**

### 9.3 Structure hierarchique (4 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **335.1** | [**Veuillez patienter ...** (335)](#t1) [mockup](#ecran-t1) | MDI | 424x57 | Traitement |
| **335.2** | [**Creation Tempo gene** (335.1)](#t2) | MDI | - | Creation |
| 335.2.1 | [Creation tempo bateaux police (335.2)](#t3) | MDI | - | |
| **335.3** | [**Recherche Code Village** (335.3)](#t4) | - | - | Consultation |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Traitement principal]
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

### Tables utilisees (16)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 31 | gm-complet_______gmc |  | DB | R |   |   | 1 |
| 34 | hebergement______heb | Hebergement (chambres) | DB |   |   | L | 1 |
| 35 | personnel_go______go |  | DB |   |   | L | 1 |
| 47 | compte_gm________cgm | Comptes GM (generaux) | DB |   |   | L | 1 |
| 81 | societe__________soc |  | DB |   |   | L | 1 |
| 104 | fichier_menage |  | DB |   |   | L | 1 |
| 118 | tables_imports |  | DB |   |   | L | 1 |
| 119 | tables_pays_tel_ |  | DB |   |   | L | 1 |
| 171 | commentaire______com |  | DB |   |   | L | 1 |
| 285 | email |  | DB |   |   | L | 1 |
| 366 | pms_print_param |  | DB |   |   | L | 1 |
| 372 | pv_budget |  | DB | R |   |   | 1 |
| 598 | tempo_ecr_previsions | Table temporaire ecran | TMP |   |   | L | 3 |
| 609 | tempo_mecano_dossier_grou | Table temporaire ecran | TMP |   | **W** | L | 2 |
| 619 | tempo_userlist | Table temporaire ecran | TMP |   | **W** | L | 2 |
| 637 | tempo_zone_secteur | Table temporaire ecran | DB |   |   | L | 1 |

### Colonnes par table (4 / 4 tables avec colonnes identifiees)

<details>
<summary>Table 31 - gm-complet_______gmc (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | >Index | R | Numeric |
| B | >DateCalcul | R | Date |
| C | >HeureCalcul | R | Alpha |
| D | >DateMinDebut | R | Date |
| E | >DateMaxDebut | R | Date |
| F | >DateMinFin | R | Date |
| G | >DateMaxFin | R | Date |
| H | >w0_HeureMin | R | Numeric |
| I | >w0_HeureMax | R | Numeric |
| J | >CodeListe | R | Alpha |
| K | >Logement | R | Alpha |
| L | >TypeHebergement | R | Alpha |
| M | >TopListe | R | Alpha |
| N | >CodeVol | R | Alpha |
| O | >DateVillage | R | Date |
| P | >HeureVillage | R | Alpha |
| Q | >AgeMini | R | Numeric |
| R | >AgeMaxi | R | Numeric |
| S | <Total | R | Numeric |
| T | <NbSelect | R | Numeric |
| U | >TULCategorie | R | Alpha |
| V | >TULNomTable | R | Alpha |
| W | >Gestion Crise | R | Logical |
| X | >Lieu Séjour | R | Alpha |
| Y | >Soldé,Non_soldé,Tous | R | Unicode |
| Z | P.I.Enlever les absents | R | Logical |
| BA | w0_RetCommentaire | R | Logical |
| BB | w0_Age------------------------- | R | Alpha |
| BC | w0_Arrivee--------------------- | R | Alpha |
| BD | v.Code vol aller A | R | Unicode |
| BE | w0_Depart---------------------- | R | Alpha |
| BF | v.Code vol retour Z | R | Unicode |
| BG | w0_RetSelect | R | Logical |
| BH | w0_Circuit--------------------- | R | Logical |
| BI | W0_PresenceAv------------------ | R | Logical |
| BJ | w0_NationSelect | R | Alpha |
| BK | w0_RetHebPreced---------------- | R | Logical |
| BL | w0_RetHebSuiv------------------ | R | Logical |
| BM | v.Date début | R | Date |
| BN | v.Retour abs personnel | R | Logical |
| BO | w0_Type | R | Alpha |
| BP | w0_DateMaxDebut | R | Date |
| BQ | w0_DateMaxFin | R | Date |
| BR | w0_Total | R | Numeric |
| BS | w0_NbSelect | R | Numeric |
| BT | w0_AgeBebe | R | Numeric |
| BU | w0_AgeEnfant | R | Numeric |
| BV | w0_RetCtlHeb | R | Logical |
| BW | w0_TelInt | R | Numeric |
| BX | w0_TelExt_Commune | R | Alpha |
| BY | w0_FaxVille | R | Alpha |
| BZ | w0_TypeEcran | R | Alpha |
| CA | w0_NumAdherent | R | Alpha |
| CB | w0_Age | R | Numeric |
| CC | w0_Cabine | R | Alpha |
| CD | w0_CondArrivant | R | Logical |
| CE | w0_CondArrive | R | Logical |
| CF | W0_CondPresent | R | Logical |
| CG | w0_CondDepart | R | Logical |
| CH | w0_CondAbsent | R | Logical |
| CI | w0_CondPartant | R | Logical |
| CJ | w0_Code_Village | R | Alpha |
| CK | v.Date/Heure début | R | Numeric |
| CL | v.Date/Heure fin | R | Numeric |
| CM | v.Date/heure abs départ | R | Numeric |
| CN | v.Date/heure abs retour | R | Numeric |

</details>

<details>
<summary>Table 372 - pv_budget (R) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 609 - tempo_mecano_dossier_grou (**W**/L) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 619 - tempo_userlist (**W**/L) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (1)

Variables recues du programme appelant ([  Liste present personnel plan (IDE 227)](PBP-IDE-227.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| Z | P.I.Enlever les absents | Logical | - |

### 11.2 Variables de session (8)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| BD | v.Code vol aller A | Unicode | - |
| BF | v.Code vol retour Z | Unicode | - |
| BM | v.Date début | Date | - |
| BN | v.Retour abs personnel | Logical | - |
| CK | v.Date/Heure début | Numeric | - |
| CL | v.Date/Heure fin | Numeric | - |
| CM | v.Date/heure abs départ | Numeric | - |
| CN | v.Date/heure abs retour | Numeric | - |

### 11.3 Autres (57)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | >Index | Numeric | 3x refs |
| B | >DateCalcul | Date | 3x refs |
| C | >HeureCalcul | Alpha | - |
| D | >DateMinDebut | Date | 4x refs |
| E | >DateMaxDebut | Date | 5x refs |
| F | >DateMinFin | Date | 1x refs |
| G | >DateMaxFin | Date | 2x refs |
| H | >w0_HeureMin | Numeric | 9x refs |
| I | >w0_HeureMax | Numeric | 9x refs |
| J | >CodeListe | Alpha | 31x refs |
| K | >Logement | Alpha | 1x refs |
| L | >TypeHebergement | Alpha | 17x refs |
| M | >TopListe | Alpha | 22x refs |
| N | >CodeVol | Alpha | 14x refs |
| O | >DateVillage | Date | 1x refs |
| P | >HeureVillage | Alpha | 1x refs |
| Q | >AgeMini | Numeric | 1x refs |
| R | >AgeMaxi | Numeric | 1x refs |
| S | <Total | Numeric | 1x refs |
| T | <NbSelect | Numeric | - |
| U | >TULCategorie | Alpha | 1x refs |
| V | >TULNomTable | Alpha | 1x refs |
| W | >Gestion Crise | Logical | 2x refs |
| X | >Lieu Séjour | Alpha | 1x refs |
| Y | >Soldé,Non_soldé,Tous | Unicode | 5x refs |
| BA | w0_RetCommentaire | Logical | 1x refs |
| BB | w0_Age------------------------- | Alpha | - |
| BC | w0_Arrivee--------------------- | Alpha | - |
| BE | w0_Depart---------------------- | Alpha | - |
| BG | w0_RetSelect | Logical | - |
| BH | w0_Circuit--------------------- | Logical | - |
| BI | W0_PresenceAv------------------ | Logical | - |
| BJ | w0_NationSelect | Alpha | - |
| BK | w0_RetHebPreced---------------- | Logical | - |
| BL | w0_RetHebSuiv------------------ | Logical | - |
| BO | w0_Type | Alpha | 2x refs |
| BP | w0_DateMaxDebut | Date | - |
| BQ | w0_DateMaxFin | Date | - |
| BR | w0_Total | Numeric | - |
| BS | w0_NbSelect | Numeric | - |
| BT | w0_AgeBebe | Numeric | 6x refs |
| BU | w0_AgeEnfant | Numeric | - |
| BV | w0_RetCtlHeb | Logical | 5x refs |
| BW | w0_TelInt | Numeric | 5x refs |
| BX | w0_TelExt_Commune | Alpha | 4x refs |
| BY | w0_FaxVille | Alpha | 4x refs |
| BZ | w0_TypeEcran | Alpha | 2x refs |
| CA | w0_NumAdherent | Alpha | 22x refs |
| CB | w0_Age | Numeric | 11x refs |
| CC | w0_Cabine | Alpha | - |
| CD | w0_CondArrivant | Logical | 1x refs |
| CE | w0_CondArrive | Logical | 2x refs |
| CF | W0_CondPresent | Logical | 2x refs |
| CG | w0_CondDepart | Logical | - |
| CH | w0_CondAbsent | Logical | - |
| CI | w0_CondPartant | Logical | - |
| CJ | w0_Code_Village | Alpha | - |

<details>
<summary>Toutes les 66 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| P0 | **Z** | P.I.Enlever les absents | Logical |
| V. | **BD** | v.Code vol aller A | Unicode |
| V. | **BF** | v.Code vol retour Z | Unicode |
| V. | **BM** | v.Date début | Date |
| V. | **BN** | v.Retour abs personnel | Logical |
| V. | **CK** | v.Date/Heure début | Numeric |
| V. | **CL** | v.Date/Heure fin | Numeric |
| V. | **CM** | v.Date/heure abs départ | Numeric |
| V. | **CN** | v.Date/heure abs retour | Numeric |
| Autre | **A** | >Index | Numeric |
| Autre | **B** | >DateCalcul | Date |
| Autre | **C** | >HeureCalcul | Alpha |
| Autre | **D** | >DateMinDebut | Date |
| Autre | **E** | >DateMaxDebut | Date |
| Autre | **F** | >DateMinFin | Date |
| Autre | **G** | >DateMaxFin | Date |
| Autre | **H** | >w0_HeureMin | Numeric |
| Autre | **I** | >w0_HeureMax | Numeric |
| Autre | **J** | >CodeListe | Alpha |
| Autre | **K** | >Logement | Alpha |
| Autre | **L** | >TypeHebergement | Alpha |
| Autre | **M** | >TopListe | Alpha |
| Autre | **N** | >CodeVol | Alpha |
| Autre | **O** | >DateVillage | Date |
| Autre | **P** | >HeureVillage | Alpha |
| Autre | **Q** | >AgeMini | Numeric |
| Autre | **R** | >AgeMaxi | Numeric |
| Autre | **S** | <Total | Numeric |
| Autre | **T** | <NbSelect | Numeric |
| Autre | **U** | >TULCategorie | Alpha |
| Autre | **V** | >TULNomTable | Alpha |
| Autre | **W** | >Gestion Crise | Logical |
| Autre | **X** | >Lieu Séjour | Alpha |
| Autre | **Y** | >Soldé,Non_soldé,Tous | Unicode |
| Autre | **BA** | w0_RetCommentaire | Logical |
| Autre | **BB** | w0_Age------------------------- | Alpha |
| Autre | **BC** | w0_Arrivee--------------------- | Alpha |
| Autre | **BE** | w0_Depart---------------------- | Alpha |
| Autre | **BG** | w0_RetSelect | Logical |
| Autre | **BH** | w0_Circuit--------------------- | Logical |
| Autre | **BI** | W0_PresenceAv------------------ | Logical |
| Autre | **BJ** | w0_NationSelect | Alpha |
| Autre | **BK** | w0_RetHebPreced---------------- | Logical |
| Autre | **BL** | w0_RetHebSuiv------------------ | Logical |
| Autre | **BO** | w0_Type | Alpha |
| Autre | **BP** | w0_DateMaxDebut | Date |
| Autre | **BQ** | w0_DateMaxFin | Date |
| Autre | **BR** | w0_Total | Numeric |
| Autre | **BS** | w0_NbSelect | Numeric |
| Autre | **BT** | w0_AgeBebe | Numeric |
| Autre | **BU** | w0_AgeEnfant | Numeric |
| Autre | **BV** | w0_RetCtlHeb | Logical |
| Autre | **BW** | w0_TelInt | Numeric |
| Autre | **BX** | w0_TelExt_Commune | Alpha |
| Autre | **BY** | w0_FaxVille | Alpha |
| Autre | **BZ** | w0_TypeEcran | Alpha |
| Autre | **CA** | w0_NumAdherent | Alpha |
| Autre | **CB** | w0_Age | Numeric |
| Autre | **CC** | w0_Cabine | Alpha |
| Autre | **CD** | w0_CondArrivant | Logical |
| Autre | **CE** | w0_CondArrive | Logical |
| Autre | **CF** | W0_CondPresent | Logical |
| Autre | **CG** | w0_CondDepart | Logical |
| Autre | **CH** | w0_CondAbsent | Logical |
| Autre | **CI** | w0_CondPartant | Logical |
| Autre | **CJ** | w0_Code_Village | Alpha |

</details>

## 12. EXPRESSIONS

**138 / 138 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONDITION | 91 | 7 |
| CONSTANTE | 13 | 0 |
| OTHER | 23 | 0 |
| REFERENCE_VG | 1 | 0 |
| CAST_LOGIQUE | 2 | 0 |
| NEGATION | 2 | 0 |
| CONCATENATION | 6 | 0 |

### 12.2 Expressions cles par type

#### CONDITION (91 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 127 | `IF(w0_CondArrive [CE]='' OR w0_CondArrive [CE]='*',[PH],w0_CondArrive [CE])` | [RM-006](#rm-RM-006) |
| CONDITION | 30 | `IF (>Index [A]=5,>DateMaxDebut [E]+14,>DateMaxDebut [E])` | [RM-002](#rm-RM-002) |
| CONDITION | 75 | `IF (>CodeListe [J]<>'P',w0_NumAdherent [CA]=>TypeHebergement [L] AND Trim(MID (w0_TypeEcran [BZ],2,2))='1',[EL]=>TypeHebergement [L] AND Trim(MID ([EQ],2,2))='1')` | [RM-005](#rm-RM-005) |
| CONDITION | 42 | `IF ([OQ]>0,[OQ],0)` | [RM-004](#rm-RM-004) |
| CONDITION | 31 | `IF (>Index [A]=6,>DateMaxFin [G]+14,>DateMaxFin [G])` | [RM-003](#rm-RM-003) |
| ... | | *+86 autres* | |

#### CONSTANTE (13 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 87 | `0` | - |
| CONSTANTE | 36 | `'P'` | - |
| CONSTANTE | 35 | `'C'` | - |
| CONSTANTE | 123 | `'TCLME'` | - |
| CONSTANTE | 122 | `'D'` | - |
| ... | | *+8 autres* | |

#### OTHER (23 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 86 | `[FY]` | - |
| OTHER | 88 | `[AY]` | - |
| OTHER | 85 | `[FX]` | - |
| OTHER | 66 | `[GO] OR [GP] OR [GQ] OR [GR] OR [GS] OR [GT]` | - |
| OTHER | 84 | `[FW]` | - |
| ... | | *+18 autres* | |

#### REFERENCE_VG (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 22 | `VG1` | - |

#### CAST_LOGIQUE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 43 | `[DM] AND (IF(NOT >Gestion Crise [W],[PA] OR W0_CondPresent [CF]='','TRUE'LOG))` | - |
| CAST_LOGIQUE | 29 | `'TRUE'LOG` | - |

#### NEGATION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| NEGATION | 137 | `NOT [PO] OR NOT [PT] OR
([QA]<[QC] AND [QB]<[QC]) OR ([QA]>[QD] AND [QB]>[QC])` | - |
| NEGATION | 126 | `NOT >Gestion Crise [W]` | - |

#### CONCATENATION (6 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 104 | `[GP] OR >CodeListe [J]='A' AND Trim (w0_NumAdherent [CA])&w0_Age [CB]<>Trim ([FH])&[FI] AND [EY] OR >CodeListe [J]='A' AND NOT ([EY]) AND w0_FaxVille [BY]='P'` | - |
| CONCATENATION | 105 | `[GR] OR >CodeListe [J]='D' AND Trim (w0_NumAdherent [CA])&w0_Age [CB]<>Trim ([FS])&[FT] AND [FJ] OR >CodeListe [J]='D' AND NOT ([FJ]) AND w0_FaxVille [BY]='P'` | - |
| CONCATENATION | 106 | `[GT] OR >CodeListe [J]='R' AND Trim (w0_NumAdherent [CA])&w0_Age [CB]<>Trim ([FS])&[FT] AND [FJ] OR >CodeListe [J]='R' AND NOT ([FJ])` | - |
| CONCATENATION | 38 | `[AK]&Str ([AL],'10P0Z0')&[AM]&Str ([AN],'3L')` | - |
| CONCATENATION | 39 | `[AK]&Str ([AL],'10P0Z0')&' '&Str ([AN],'3L')` | - |
| ... | | *+1 autres* | |

### 12.3 Toutes les expressions (138)

<details>
<summary>Voir les 138 expressions</summary>

#### CONDITION (91)

| IDE | Expression Decodee |
|-----|-------------------|
| 37 | `<Total [S]+1` |
| 133 | `>DateMinDebut [D]*86400+>w0_HeureMin [H]*3600` |
| 134 | `>DateMaxDebut [E]*86400 + IF( >w0_HeureMax [I]=0,24,>w0_HeureMax [I])*3600` |
| 18 | `IF (>CodeListe [J]='P',>DateCalcul [B],>Soldé,Non_soldé,Tous [Y])` |
| 30 | `IF (>Index [A]=5,>DateMaxDebut [E]+14,>DateMaxDebut [E])` |
| 31 | `IF (>Index [A]=6,>DateMaxFin [G]+14,>DateMaxFin [G])` |
| 42 | `IF ([OQ]>0,[OQ],0)` |
| 75 | `IF (>CodeListe [J]<>'P',w0_NumAdherent [CA]=>TypeHebergement [L] AND Trim(MID (w0_TypeEcran [BZ],2,2))='1',[EL]=>TypeHebergement [L] AND Trim(MID ([EQ],2,2))='1')` |
| 76 | `IF (>CodeListe [J]<>'P',w0_NumAdherent [CA]=>TypeHebergement [L] AND Trim(MID(w0_TypeEcran [BZ],2,2))<>'1',[EL]=>TypeHebergement [L] AND Trim(MID ([EQ],2,2))<>'1')` |
| 127 | `IF(w0_CondArrive [CE]='' OR w0_CondArrive [CE]='*',[PH],w0_CondArrive [CE])` |
| 128 | `IF(VG88, CodeVolAller([AA], [AB]), [PN])` |
| 129 | `IF(VG88, CodeVolRetour([AA], [AB]), [PM])` |
| 135 | `[PP]*86400+(CASE([PV],1,12,3,18,0)*3600)` |
| 136 | `[PU]*86400+(CASE([PW],1,14,2,23,6)*3600)` |
| 1 | `>Index [A]` |
| 6 | `>Lieu Séjour [X]` |
| 7 | `CndRange (>DateMinDebut [D]>0,>DateMinDebut [D])` |
| 8 | `CndRange (>DateMaxDebut [E]>0,>DateMaxDebut [E])` |
| 9 | `CndRange (>DateMinFin [F]>0,>DateMinFin [F])` |
| 10 | `CndRange (>DateMaxFin [G]>0,>DateMaxFin [G])` |
| 17 | `CndRange (>CodeListe [J]='P',>Soldé,Non_soldé,Tous [Y])` |
| 23 | `>TULCategorie [U]` |
| 24 | `>TULNomTable [V]` |
| 34 | `>Soldé,Non_soldé,Tous [Y]` |
| 44 | `>CodeListe [J]='P'` |
| 45 | `>Logement [K]=w0_CondArrive [CE] OR >Logement [K]=''` |
| 46 | `>TopListe [M]='PL'` |
| 47 | `>TopListe [M]='GR'` |
| 48 | `>TopListe [M]='RE'` |
| 49 | `>TopListe [M]='CA'` |
| 50 | `>TopListe [M]='MI'` |
| 51 | `>TopListe [M]='BB'` |
| 52 | `>TopListe [M]='EN'` |
| 53 | `>TopListe [M]='SI'` |
| 54 | `>TopListe [M]='NS'` |
| 55 | `>TopListe [M]='PY'` |
| 56 | `>TopListe [M]='HM'` |
| 57 | `>TopListe [M]='VV'` |
| 58 | `>TopListe [M]='NV'` |
| 59 | `>TopListe [M]='ST'` |
| 60 | `>TopListe [M]='SE'` |
| 61 | `>TopListe [M]='AG'` |
| 62 | `>TopListe [M]='CO'` |
| 63 | `>TopListe [M]='PO'` |
| 64 | `>TopListe [M]='BA'` |
| 65 | `>TopListe [M]='CP'` |
| 67 | `>TypeHebergement [L]=IF (>CodeListe [J]='P',[EL],w0_NumAdherent [CA])` |
| 68 | `>TypeHebergement [L]=IF (>CodeListe [J]='P',[EL],w0_NumAdherent [CA]) AND [AB]=0` |
| 69 | `>TypeHebergement [L]=IF (>CodeListe [J]='P',[EL],w0_NumAdherent [CA]) AND [AN]=0 AND [AX]='O'` |
| 70 | `>CodeVol [N]='' OR >CodeVol [N]=IF (>CodeListe [J]='D' OR >CodeListe [J]='R',[DL],[DD]) AND >TypeHebergement [L]=IF (>CodeListe [J]='P',[EL],w0_NumAdherent [CA])` |
| 71 | `(w0_AgeBebe [BT]=>DateCalcul [B] AND w0_AgeBebe [BT]=>DateVillage [O] AND w0_RetCtlHeb [BV]=>HeureVillage [P] OR w0_AgeBebe [BT]=0 AND w0_RetCtlHeb [BV]='') AND >TypeHebergement [L]=IF (>CodeListe [J]<>'P',[EL],w0_NumAdherent [CA])` |
| 72 | `>TypeHebergement [L]=IF (>CodeListe [J]='P',[EL],w0_NumAdherent [CA]) AND [AH]='M'` |
| 73 | `>TypeHebergement [L]=IF (>CodeListe [J]='P',[EL],w0_NumAdherent [CA]) AND ([AG]<=[GE] AND ([OO])>0 OR [OP]>0)` |
| 74 | `>TypeHebergement [L]=IF (>CodeListe [J]='P',[EL],w0_NumAdherent [CA]) AND ([AG]<=[GF] AND [AG]>[GE])` |
| 77 | `>TypeHebergement [L]=IF (>CodeListe [J]='P',[EL],w0_NumAdherent [CA]) AND [EX]` |
| 80 | `w0_NumAdherent [CA]=>TypeHebergement [L] AND [EB] AND [GG] AND >CodeListe [J]='P' AND [EH]='P'` |
| 81 | `w0_NumAdherent [CA]=>TypeHebergement [L] AND [EB] AND [GG]` |
| 82 | `>AgeMini [Q]>0 AND [OQ]<=>AgeMaxi [R] AND [OQ]>=>AgeMini [Q] OR >AgeMini [Q]=0 AND [OQ]<=>AgeMaxi [R] AND ([OQ]>0 OR [OR]>0) AND >TypeHebergement [L]=IF (>CodeListe [J]='P',[EL],w0_NumAdherent [CA])` |
| 83 | `w0_NumAdherent [CA]=>TypeHebergement [L]` |
| 93 | `>CodeListe [J]='A'` |
| 94 | `>CodeListe [J]='V' AND w0_FaxVille [BY]='P'` |
| 95 | `>CodeListe [J]='P' AND [EH]='P' AND [GG]` |
| 96 | `>CodeListe [J]='D' AND w0_FaxVille [BY]='P'` |
| 97 | `>CodeListe [J]='B' AND [EH]<>'P'` |
| 98 | `>CodeListe [J]='R'` |
| 100 | `>CodeListe [J]='P' AND [EH]='P'` |
| 102 | `>CodeVol [N]=''` |
| 108 | `[GO] OR >CodeVol [N]<>'' AND NOT ([EY]) AND w0_AgeBebe [BT]<>[DA] AND [DD]=>CodeVol [N]` |
| 111 | `[GP] OR >CodeVol [N]<>'' AND NOT ([EY]) AND w0_AgeBebe [BT]<>[DA] AND [DD]=>CodeVol [N]` |
| 114 | `[GR] OR >CodeVol [N]<>'' AND NOT ([FJ]) AND w0_TelInt [BW]<>[DI] AND [DL]=>CodeVol [N]` |
| 117 | `[GT] OR >CodeVol [N]<>'' AND NOT ([FJ]) AND w0_TelInt [BW]<>[DI] AND [DL]=>CodeVol [N]` |
| 119 | `CndRange([OS]<>'',[OS])` |
| 120 | `>TopListe [M]='CO'` |
| 121 | `>TopListe [M]='ST'` |
| 124 | `CndRange([OS]<>'',[OS])` |
| 130 | `MIN(>DateMinDebut [D],>DateMaxDebut [E])` |
| 131 | `>DateMaxDebut [E]` |
| 132 | `>DateMinDebut [D]` |
| 138 | `([QH]='S' AND [QG]=0)
OR 
([QH]='N' AND [QG]<>0) 
OR 
[QH]='T' 
OR 
[QH]=''` |
| 15 | `CndRange (InStr ('PDR',>CodeListe [J])=0,>Soldé,Non_soldé,Tous [Y])` |
| 16 | `CndRange (InStr ('PAVB',>CodeListe [J])>0,IF (>CodeListe [J]='P',>DateCalcul [B],>Soldé,Non_soldé,Tous [Y]))` |
| 78 | `>TypeHebergement [L]=IF (>CodeListe [J]='P',[EL],w0_NumAdherent [CA]) AND InStr ('VV',IF (>CodeListe [J]='D' OR >CodeListe [J]='R',Left ([DL],2),Left ([DD],2)))>0` |
| 79 | `>TypeHebergement [L]=IF (>CodeListe [J]='P',[EL],w0_NumAdherent [CA]) AND InStr ('VV',IF (>CodeListe [J]='D' OR >CodeListe [J]='R',Left ([DL],2),Left ([DD],2)))=0` |
| 107 | `[GO] OR >CodeVol [N]<>'' AND [EY] AND >w0_HeureMin [H]<Val (w0_RetCtlHeb [BV],'2') AND >w0_HeureMax [I]>=Val (w0_RetCtlHeb [BV],'2')` |
| 109 | `[GO] OR >CodeVol [N]<>'' AND NOT ([EY]) AND w0_AgeBebe [BT]<>[DA] AND >w0_HeureMin [H]<Val (w0_RetCtlHeb [BV],'2') AND >w0_HeureMax [I]>=Val (w0_RetCtlHeb [BV],'2')` |
| 110 | `[GP] OR >CodeVol [N]<>'' AND [EY] AND >w0_HeureMin [H]<Val (w0_RetCtlHeb [BV],'2') AND >w0_HeureMax [I]>=Val (w0_RetCtlHeb [BV],'2')` |
| 112 | `[GP] OR >CodeVol [N]<>'' AND NOT ([EY]) AND w0_AgeBebe [BT]<>[DA] AND >w0_HeureMin [H]<Val (w0_RetCtlHeb [BV],'2') AND >w0_HeureMax [I]>=Val (w0_RetCtlHeb [BV],'2')` |
| 113 | `[GR] OR >CodeVol [N]<>'' AND [FJ] AND >w0_HeureMin [H]<Val (w0_TelExt_Commune [BX],'2') AND >w0_HeureMax [I]>=Val (w0_TelExt_Commune [BX],'2')` |
| 115 | `[GR] OR >CodeVol [N]<>'' AND NOT ([FJ]) AND w0_TelInt [BW]<>[DI] AND >w0_HeureMin [H]<Val (w0_TelExt_Commune [BX],'2') AND >w0_HeureMax [I]>=Val (w0_TelExt_Commune [BX],'2')` |
| 116 | `[GT] OR >CodeVol [N]<>'' AND [FJ] AND >w0_HeureMin [H]<Val (w0_TelExt_Commune [BX],'2') AND >w0_HeureMax [I]>=Val (w0_TelExt_Commune [BX],'2')` |
| 118 | `[GT] OR >CodeVol [N]<>'' AND NOT ([FJ]) AND w0_TelInt [BW]<>[DI] AND >w0_HeureMin [H]<Val (w0_TelExt_Commune [BX],'2') AND >w0_HeureMax [I]>=Val (w0_TelExt_Commune [BX],'2')` |

#### CONSTANTE (13)

| IDE | Expression Decodee |
|-----|-------------------|
| 2 | `'VBEBE'` |
| 3 | `'VENFA'` |
| 21 | `'H'` |
| 25 | `'M'` |
| 26 | `'TNATI'` |
| 32 | `'A'` |
| 33 | `'Z'` |
| 35 | `'C'` |
| 36 | `'P'` |
| 87 | `0` |
| 91 | `''` |
| 122 | `'D'` |
| 123 | `'TCLME'` |

#### OTHER (23)

| IDE | Expression Decodee |
|-----|-------------------|
| 4 | `[AS]` |
| 5 | `GetParam('SOCIETE')` |
| 11 | `[AA]` |
| 12 | `[AB]` |
| 13 | `GetParam ('LANGUE')` |
| 14 | `[AS]` |
| 19 | `w0_AgeBebe [BT]` |
| 20 | `w0_TelInt [BW]` |
| 27 | `Left (w0_NumAdherent [CA],3)` |
| 28 | `w0_Age [CB]` |
| 40 | `[AG]` |
| 41 | `[AO]` |
| 66 | `[GO] OR [GP] OR [GQ] OR [GR] OR [GS] OR [GT]` |
| 84 | `[FW]` |
| 85 | `[FX]` |
| 86 | `[FY]` |
| 88 | `[AY]` |
| 89 | `[AZ]` |
| 90 | `w0_RetCommentaire [BA]` |
| 92 | `w0_CondArrivant [CD]` |
| 99 | `[GQ] AND [GG]` |
| 101 | `W0_PresenceAv---------... [BI]` |
| 125 | `W0_CondPresent [CF]` |

#### REFERENCE_VG (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 22 | `VG1` |

#### CAST_LOGIQUE (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 29 | `'TRUE'LOG` |
| 43 | `[DM] AND (IF(NOT >Gestion Crise [W],[PA] OR W0_CondPresent [CF]='','TRUE'LOG))` |

#### NEGATION (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 126 | `NOT >Gestion Crise [W]` |
| 137 | `NOT [PO] OR NOT [PT] OR
([QA]<[QC] AND [QB]<[QC]) OR ([QA]>[QD] AND [QB]>[QC])` |

#### CONCATENATION (6)

| IDE | Expression Decodee |
|-----|-------------------|
| 38 | `[AK]&Str ([AL],'10P0Z0')&[AM]&Str ([AN],'3L')` |
| 39 | `[AK]&Str ([AL],'10P0Z0')&' '&Str ([AN],'3L')` |
| 103 | `[GO] OR >CodeListe [J]='V' AND Trim (w0_NumAdherent [CA])&w0_Age [CB]<>Trim ([FH])&[FI] AND [EY] OR >CodeListe [J]='V' AND NOT ([EY])` |
| 104 | `[GP] OR >CodeListe [J]='A' AND Trim (w0_NumAdherent [CA])&w0_Age [CB]<>Trim ([FH])&[FI] AND [EY] OR >CodeListe [J]='A' AND NOT ([EY]) AND w0_FaxVille [BY]='P'` |
| 105 | `[GR] OR >CodeListe [J]='D' AND Trim (w0_NumAdherent [CA])&w0_Age [CB]<>Trim ([FS])&[FT] AND [FJ] OR >CodeListe [J]='D' AND NOT ([FJ]) AND w0_FaxVille [BY]='P'` |
| 106 | `[GT] OR >CodeListe [J]='R' AND Trim (w0_NumAdherent [CA])&w0_Age [CB]<>Trim ([FS])&[FT] AND [FJ] OR >CodeListe [J]='R' AND NOT ([FJ])` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [  Liste present personnel plan (IDE 227)](PBP-IDE-227.md) -> **Creation tempo toutes GO (IDE 335)**

Main -> ... -> [  Liste personnels AVPBDR (IDE 234)](PBP-IDE-234.md) -> **Creation tempo toutes GO (IDE 335)**

Main -> ... -> [Pilotage Gestion de Crise (IDE 146)](PBP-IDE-146.md) -> **Creation tempo toutes GO (IDE 335)**

```mermaid
graph LR
    T335[335 Creation tempo tou...]
    style T335 fill:#58a6ff
    CC224[224 Liste des arrivant...]
    style CC224 fill:#8b5cf6
    CC233[233 Liste des partants...]
    style CC233 fill:#8b5cf6
    CC225[225 Liste des arrivees...]
    style CC225 fill:#8b5cf6
    CC232[232 Liste des departs ...]
    style CC232 fill:#8b5cf6
    CC231[231 Liste des Absents ...]
    style CC231 fill:#8b5cf6
    CC226[226 Liste des presents...]
    style CC226 fill:#8b5cf6
    CC148[148 Liste Gestion de C...]
    style CC148 fill:#8b5cf6
    CC152[152 Start]
    style CC152 fill:#8b5cf6
    CC146[146 Pilotage Gestion d...]
    style CC146 fill:#3fb950
    CC234[234 Liste personnels A...]
    style CC234 fill:#3fb950
    CC227[227 Liste present pers...]
    style CC227 fill:#3fb950
    CC148 --> CC146
    CC152 --> CC146
    CC226 --> CC146
    CC224 --> CC146
    CC225 --> CC146
    CC231 --> CC146
    CC232 --> CC146
    CC233 --> CC146
    CC148 --> CC227
    CC152 --> CC227
    CC226 --> CC227
    CC224 --> CC227
    CC225 --> CC227
    CC231 --> CC227
    CC232 --> CC227
    CC233 --> CC227
    CC148 --> CC234
    CC152 --> CC234
    CC226 --> CC234
    CC224 --> CC234
    CC225 --> CC234
    CC231 --> CC234
    CC232 --> CC234
    CC233 --> CC234
    CC146 --> T335
    CC227 --> T335
    CC234 --> T335
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [227](PBP-IDE-227.md) |   Liste present personnel plan | 3 |
| [234](PBP-IDE-234.md) |   Liste personnels AVPBDR | 3 |
| [146](PBP-IDE-146.md) | Pilotage Gestion de Crise | 2 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T335[335 Creation tempo tou...]
    style T335 fill:#58a6ff
    C307[307 Recherche age Bebe...]
    T335 --> C307
    style C307 fill:#3fb950
    C284[284 RaZ Tempo synthese]
    T335 --> C284
    style C284 fill:#3fb950
    C302[302 Controle presence ...]
    T335 --> C302
    style C302 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [307](PBP-IDE-307.md) | Recherche age Bebe_Enfant | 2 | Sous-programme |
| [284](PBP-IDE-284.md) | RaZ Tempo synthese | 1 | Reinitialisation |
| [302](PBP-IDE-302.md) | Controle presence heberg | 1 | Controle/validation |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 620 | Programme volumineux |
| Expressions | 138 | Logique moderee |
| Tables WRITE | 2 | Impact faible |
| Sous-programmes | 3 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 620) | Code sain |
| Regles metier | 7 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 1 ecran, 0 traitement)

- **Strategie** : 1 composant(s) UI (Razor/React) avec formulaires et validation.
- 3 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Creation (2 taches: 0 ecran, 2 traitements)

- **Strategie** : Repository pattern avec Entity Framework Core.
- Insertion via `IRepository<T>.CreateAsync()`

#### Consultation (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Composants de recherche/selection en modales.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| tempo_mecano_dossier_grou | Table WRITE (Temp) | 1x | Schema + repository |
| tempo_userlist | Table WRITE (Temp) | 1x | Schema + repository |
| [Recherche age Bebe_Enfant (IDE 307)](PBP-IDE-307.md) | Sous-programme | 2x | Haute - Sous-programme |
| [Controle presence heberg (IDE 302)](PBP-IDE-302.md) | Sous-programme | 1x | Normale - Controle/validation |
| [RaZ Tempo synthese (IDE 284)](PBP-IDE-284.md) | Sous-programme | 1x | Normale - Reinitialisation |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 16:29*
