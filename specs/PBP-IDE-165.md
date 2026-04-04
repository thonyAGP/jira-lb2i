# PBP IDE 165 - Imprim GM present planning

> **Analyse**: Phases 1-4 2026-02-03 15:34 -> 15:34 (17s) | Assemblage 15:34
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBP |
| IDE Position | 165 |
| Nom Programme | Imprim GM present planning |
| Fichier source | `Prg_165.xml` |
| Dossier IDE | Liste |
| Taches | 4 (0 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 1 |

## 2. DESCRIPTION FONCTIONNELLE

**Imprim GM present planning** assure la gestion complete de ce processus, accessible depuis [  Liste Clients present (IDE 162)](PBP-IDE-162.md), [  Affich present planning GM (IDE 164)](PBP-IDE-164.md).

Le flux de traitement s'organise en **3 blocs fonctionnels** :

- **Traitement** (2 taches) : traitements metier divers
- **Impression** (1 tache) : generation de tickets et documents
- **Calcul** (1 tache) : calculs de montants, stocks ou compteurs

**Donnees modifiees** : 1 tables en ecriture (tempo_heures).

**Logique metier** : 20 regles identifiees couvrant conditions metier.

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (2 taches)

- **165** - Veuillez patienter... **[[ECRAN]](#ecran-t1)**
- **165.2** - Ligne commentaire

Delegue a : [  Suppression nationalite (IDE 166)](PBP-IDE-166.md)

#### Phase 2 : Calcul (1 tache)

- **165.1** - Calcul pied

#### Phase 3 : Impression (1 tache)

- **165.3** - Edition Nationalite

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| tempo_heures | **W**/L (2 usages) | Table temporaire ecran |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (2 taches)

Traitements internes.

---

#### <a id="t1"></a>165 - Veuillez patienter... [[ECRAN]](#ecran-t1)

**Role** : Traitement : Veuillez patienter....
**Ecran** : 426 x 59 DLU (MDI) | [Voir mockup](#ecran-t1)
**Delegue a** : [  Suppression nationalite (IDE 166)](PBP-IDE-166.md)

---

#### <a id="t3"></a>165.2 - Ligne commentaire

**Role** : Traitement : Ligne commentaire.
**Delegue a** : [  Suppression nationalite (IDE 166)](PBP-IDE-166.md)


### 3.2 Calcul (1 tache)

Calculs metier : montants, stocks, compteurs.

---

#### <a id="t2"></a>165.1 - Calcul pied

**Role** : Calcul : Calcul pied.
**Variables liees** : A (>DateCalcul), U (w0_NomPied01), V (w0_NbPied01), W (w0_NomPied02), X (w0_NbPied02)


### 3.3 Impression (1 tache)

Generation des documents et tickets.

---

#### <a id="t4"></a>165.3 - Edition Nationalite

**Role** : Generation du document : Edition Nationalite.
**Variables liees** : L (w0_LibelleEdition)


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
| **Expression source** | Expression 4 : `IF (>TopListe [D]='AG' OR >TopListe [D]='BB' OR >TopListe [D` |
| **Exemple** | Si >TopListe [D]='AG' OR >TopListe [D]='BB' OR >TopListe [D]='EN' â†’ MlsTrans ('Naissance'). Sinon â†’ '') |

#### <a id="rm-RM-002"></a>[RM-002] Si >TopListe [D]='GR' alors MlsTrans ('GROUPE') sinon IF (>TopListe [D]='CA',MlsTrans ('DATE'),MlsTrans ('DATE/HR')))

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='GR'` |
| **Si vrai** | MlsTrans ('GROUPE') |
| **Si faux** | IF (>TopListe [D]='CA',MlsTrans ('DATE'),MlsTrans ('DATE/HR'))) |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 8 : `IF (>TopListe [D]='GR',MlsTrans ('GROUPE'),IF (>TopListe [D]` |
| **Exemple** | Si >TopListe [D]='GR' â†’ MlsTrans ('GROUPE') |

#### <a id="rm-RM-003"></a>[RM-003] Si >CodeListe [C]='A' alors MlsTrans ('arrivants') sinon IF (>CodeListe [C]='V',MlsTrans ('arrivees'),IF (>CodeListe [C]='P',MlsTrans ('presents'),IF (>CodeListe [C]='D',MlsTrans ('departs'),IF (>CodeListe [C]='R',MlsTrans ('partants'),MlsTrans ('absents'))))))

| Element | Detail |
|---------|--------|
| **Condition** | `>CodeListe [C]='A'` |
| **Si vrai** | MlsTrans ('arrivants') |
| **Si faux** | IF (>CodeListe [C]='V',MlsTrans ('arrivees'),IF (>CodeListe [C]='P',MlsTrans ('presents'),IF (>CodeListe [C]='D',MlsTrans ('departs'),IF (>CodeListe [C]='R',MlsTrans ('partants'),MlsTrans ('absents')))))) |
| **Variables** | C (>CodeListe) |
| **Expression source** | Expression 20 : `IF (>CodeListe [C]='A',MlsTrans ('arrivants'),IF (>CodeListe` |
| **Exemple** | Si >CodeListe [C]='A' â†’ MlsTrans ('arrivants') |

#### <a id="rm-RM-004"></a>[RM-004] Si >TopListe [D]='PL' alors 'planning' sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='PL'` |
| **Si vrai** | 'planning' |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 21 : `IF (>TopListe [D]='PL','planning','')` |
| **Exemple** | Si >TopListe [D]='PL' â†’ 'planning'. Sinon â†’ '') |

#### <a id="rm-RM-005"></a>[RM-005] Si >TopListe [D]='CA' alors MlsTrans ('caisse') sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='CA'` |
| **Si vrai** | MlsTrans ('caisse') |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 23 : `IF (>TopListe [D]='CA',MlsTrans ('caisse'),'')` |
| **Exemple** | Si >TopListe [D]='CA' â†’ MlsTrans ('caisse'). Sinon â†’ '') |

#### <a id="rm-RM-006"></a>[RM-006] Si >TopListe [D]='MI' alors MlsTrans ('millesias') sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='MI'` |
| **Si vrai** | MlsTrans ('millesias') |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 24 : `IF (>TopListe [D]='MI',MlsTrans ('millesias'),'')` |
| **Exemple** | Si >TopListe [D]='MI' â†’ MlsTrans ('millesias'). Sinon â†’ '') |

#### <a id="rm-RM-007"></a>[RM-007] Si >TopListe [D]='BB' alors MlsTrans ('bebe') sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='BB'` |
| **Si vrai** | MlsTrans ('bebe') |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 25 : `IF (>TopListe [D]='BB',MlsTrans ('bebe'),'')` |
| **Exemple** | Si >TopListe [D]='BB' â†’ MlsTrans ('bebe'). Sinon â†’ '') |

#### <a id="rm-RM-008"></a>[RM-008] Si >TopListe [D]='EN' alors MlsTrans ('enfant') sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='EN'` |
| **Si vrai** | MlsTrans ('enfant') |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 26 : `IF (>TopListe [D]='EN',MlsTrans ('enfant'),'')` |
| **Exemple** | Si >TopListe [D]='EN' â†’ MlsTrans ('enfant'). Sinon â†’ '') |

#### <a id="rm-RM-009"></a>[RM-009] Si >TopListe [D]='SI' alors 'single' sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='SI'` |
| **Si vrai** | 'single' |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 27 : `IF (>TopListe [D]='SI','single','')` |
| **Exemple** | Si >TopListe [D]='SI' â†’ 'single'. Sinon â†’ '') |

#### <a id="rm-RM-010"></a>[RM-010] Si >TopListe [D]='NS' alors 'non single' sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='NS'` |
| **Si vrai** | 'non single' |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 28 : `IF (>TopListe [D]='NS','non single','')` |
| **Exemple** | Si >TopListe [D]='NS' â†’ 'non single'. Sinon â†’ '') |

#### <a id="rm-RM-011"></a>[RM-011] Si >TopListe [D]='PY' alors MlsTrans ('pays') sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='PY'` |
| **Si vrai** | MlsTrans ('pays') |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 29 : `IF (>TopListe [D]='PY',MlsTrans ('pays'),'')` |
| **Exemple** | Si >TopListe [D]='PY' â†’ MlsTrans ('pays'). Sinon â†’ '') |

#### <a id="rm-RM-012"></a>[RM-012] Si >TopListe [D]='HM' alors 'honey moon' sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='HM'` |
| **Si vrai** | 'honey moon' |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 30 : `IF (>TopListe [D]='HM','honey moon','')` |
| **Exemple** | Si >TopListe [D]='HM' â†’ 'honey moon'. Sinon â†’ '') |

#### <a id="rm-RM-013"></a>[RM-013] Si >TopListe [D]='VV' alors 'Vil/Vil' sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='VV'` |
| **Si vrai** | 'Vil/Vil' |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 31 : `IF (>TopListe [D]='VV','Vil/Vil','')` |
| **Exemple** | Si >TopListe [D]='VV' â†’ 'Vil/Vil'. Sinon â†’ '') |

#### <a id="rm-RM-014"></a>[RM-014] Si >TopListe [D]='NV' alors 'non Vil/Vil' sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='NV'` |
| **Si vrai** | 'non Vil/Vil' |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 32 : `IF (>TopListe [D]='NV','non Vil/Vil','')` |
| **Exemple** | Si >TopListe [D]='NV' â†’ 'non Vil/Vil'. Sinon â†’ '') |

#### <a id="rm-RM-015"></a>[RM-015] Si >TopListe [D]='AG' alors MlsTrans ('age du')&' '&Str (>AgeMin [H] sinon '2')&' ans / '&Str (>AgeMax [I],'2')&' ans','')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='AG'` |
| **Si vrai** | MlsTrans ('age du')&' '&Str (>AgeMin [H] |
| **Si faux** | '2')&' ans / '&Str (>AgeMax [I],'2')&' ans','') |
| **Variables** | D (>TopListe), H (>AgeMin), I (>AgeMax) |
| **Expression source** | Expression 33 : `IF (>TopListe [D]='AG',MlsTrans ('age du')&' '&Str (>AgeMin ` |
| **Exemple** | Si >TopListe [D]='AG' â†’ MlsTrans ('age du')&' '&Str (>AgeMin [H]. Sinon â†’ '2')&' ans / '&Str (>AgeMax [I],'2')&' ans','') |

#### <a id="rm-RM-016"></a>[RM-016] Si >TopListe [D]='CO' alors MlsTrans ('commentaire') sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='CO'` |
| **Si vrai** | MlsTrans ('commentaire') |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 34 : `IF (>TopListe [D]='CO',MlsTrans ('commentaire'),'')` |
| **Exemple** | Si >TopListe [D]='CO' â†’ MlsTrans ('commentaire'). Sinon â†’ '') |

#### <a id="rm-RM-017"></a>[RM-017] Si >TopListe [D]='CP' alors MlsTrans ('comptage') sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='CP'` |
| **Si vrai** | MlsTrans ('comptage') |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 35 : `IF (>TopListe [D]='CP',MlsTrans ('comptage'),'')` |
| **Exemple** | Si >TopListe [D]='CP' â†’ MlsTrans ('comptage'). Sinon â†’ '') |

#### <a id="rm-RM-018"></a>[RM-018] Si [BH] OR [BN] OR [BT] alors 'EA'&Trim([BZ]) sinon '')&IF(VG29,CASE([AU],'C',' CRE','D',' DEB','S',' SET',''),'')

| Element | Detail |
|---------|--------|
| **Condition** | `[BH] OR [BN] OR [BT]` |
| **Si vrai** | 'EA'&Trim([BZ]) |
| **Si faux** | '')&IF(VG29,CASE([AU],'C',' CRE','D',' DEB','S',' SET',''),'') |
| **Expression source** | Expression 52 : `IF([BH] OR [BN] OR [BT],'EA'&Trim([BZ]),'')&IF(VG29,CASE([AU` |
| **Exemple** | Si [BH] OR [BN] OR [BT] â†’ 'EA'&Trim([BZ]) |

#### <a id="rm-RM-019"></a>[RM-019] Si [BH] alors Trim(VG61) sinon '')&IF([BN],Trim(VG62),'')&IF([BT],Trim(VG63),'')

| Element | Detail |
|---------|--------|
| **Condition** | `[BH]` |
| **Si vrai** | Trim(VG61) |
| **Si faux** | '')&IF([BN],Trim(VG62),'')&IF([BT],Trim(VG63),'') |
| **Expression source** | Expression 56 : `IF([BH],Trim(VG61),'')&IF([BN],Trim(VG62),'')&IF([BT],Trim(V` |
| **Exemple** | Si [BH] â†’ Trim(VG61). Sinon â†’ '')&IF([BN],Trim(VG62),'')&IF([BT],Trim(VG63),'') |

#### <a id="rm-RM-020"></a>[RM-020] Si VG88 AND [CM] alors TStr([CL] sinon 'HHhMMZ'), [AC])

| Element | Detail |
|---------|--------|
| **Condition** | `VG88 AND [CM]` |
| **Si vrai** | TStr([CL] |
| **Si faux** | 'HHhMMZ'), [AC]) |
| **Expression source** | Expression 58 : `IF(VG88 AND [CM],TStr([CL],'HHhMMZ'), [AC])` |
| **Exemple** | Si VG88 AND [CM] â†’ TStr([CL]. Sinon â†’ 'HHhMMZ'), [AC]) |

## 6. CONTEXTE

- **Appele par**: [  Liste Clients present (IDE 162)](PBP-IDE-162.md), [  Affich present planning GM (IDE 164)](PBP-IDE-164.md)
- **Appelle**: 1 programmes | **Tables**: 9 (W:1 R:3 L:6) | **Taches**: 4 | **Expressions**: 63

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (4 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **165.1** | [**Veuillez patienter...** (165)](#t1) [mockup](#ecran-t1) | MDI | 426x59 | Traitement |
| 165.1.1 | [Ligne commentaire (165.2)](#t3) | MDI | - | |
| **165.2** | [**Calcul pied** (165.1)](#t2) | MDI | - | Calcul |
| **165.3** | [**Edition Nationalite** (165.3)](#t4) | MDI | - | Impression |

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
| 171 | commentaire______com |  | DB | R |   |   | 1 |
| 358 | import_mod |  | DB |   |   | L | 1 |
| 366 | pms_print_param |  | DB |   |   | L | 1 |
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
| K | P.I Heure depart village | R | Logical |
| L | w0_LibelleEdition | R | Alpha |
| M | w0_f(CodeListe) | R | Alpha |
| N | w0_g(TopListe) | R | Alpha |
| O | W0_Libelle Logement | R | Alpha |
| P | V.Existe ECI (Q60 Location) | R | Logical |
| Q | V.Existe ECI (Q61 Cours) | R | Logical |
| R | V.Existe ECI (Q62 Enfant) | R | Logical |
| S | v.absence? | R | Logical |
| T | v Libelle affichage ECI | R | Alpha |
| U | w0_NomPied01 | R | Alpha |
| V | w0_NbPied01 | R | Numeric |
| W | w0_NomPied02 | R | Alpha |
| X | w0_NbPied02 | R | Numeric |
| Y | w0_NomPied03 | R | Alpha |
| Z | w0_NbPied03 | R | Numeric |
| BA | w0_NomPied04 | R | Alpha |
| BB | w0_NbPied04 | R | Numeric |
| BC | w0_NomPied05 | R | Alpha |
| BD | w0_NbPied05 | R | Numeric |
| BE | w0_TotalSelect | R | Numeric |
| BF | v. nb absent | R | Numeric |

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

Variables recues du programme appelant ([  Liste Clients present (IDE 162)](PBP-IDE-162.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| K | P.I Heure depart village | Logical | 1x parametre entrant |

### 11.2 Variables de session (6)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| P | V.Existe ECI (Q60 Location) | Logical | - |
| Q | V.Existe ECI (Q61 Cours) | Logical | - |
| R | V.Existe ECI (Q62 Enfant) | Logical | - |
| S | v.absence? | Logical | - |
| T | v Libelle affichage ECI | Alpha | - |
| BF | v. nb absent | Numeric | - |

### 11.3 Autres (25)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | >DateCalcul | Date | 3x refs |
| B | >HeurePresence | Alpha | 2x refs |
| C | >CodeListe | Alpha | 4x refs |
| D | >TopListe | Alpha | 24x refs |
| E | >NomLogement | Alpha | - |
| F | >Total | Numeric | - |
| G | >NbSelect | Numeric | 1x refs |
| H | >AgeMin | Numeric | 1x refs |
| I | >AgeMax | Numeric | 1x refs |
| J | >CodeGroupe | Alpha | 2x refs |
| L | w0_LibelleEdition | Alpha | 2x refs |
| M | w0_f(CodeListe) | Alpha | 3x refs |
| N | w0_g(TopListe) | Alpha | - |
| O | W0_Libelle Logement | Alpha | 1x refs |
| U | w0_NomPied01 | Alpha | - |
| V | w0_NbPied01 | Numeric | - |
| W | w0_NomPied02 | Alpha | - |
| X | w0_NbPied02 | Numeric | 2x refs |
| Y | w0_NomPied03 | Alpha | - |
| Z | w0_NbPied03 | Numeric | 1x refs |
| BA | w0_NomPied04 | Alpha | - |
| BB | w0_NbPied04 | Numeric | 1x refs |
| BC | w0_NomPied05 | Alpha | - |
| BD | w0_NbPied05 | Numeric | - |
| BE | w0_TotalSelect | Numeric | - |

<details>
<summary>Toutes les 32 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| P0 | **K** | P.I Heure depart village | Logical |
| V. | **P** | V.Existe ECI (Q60 Location) | Logical |
| V. | **Q** | V.Existe ECI (Q61 Cours) | Logical |
| V. | **R** | V.Existe ECI (Q62 Enfant) | Logical |
| V. | **S** | v.absence? | Logical |
| V. | **T** | v Libelle affichage ECI | Alpha |
| V. | **BF** | v. nb absent | Numeric |
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
| Autre | **L** | w0_LibelleEdition | Alpha |
| Autre | **M** | w0_f(CodeListe) | Alpha |
| Autre | **N** | w0_g(TopListe) | Alpha |
| Autre | **O** | W0_Libelle Logement | Alpha |
| Autre | **U** | w0_NomPied01 | Alpha |
| Autre | **V** | w0_NbPied01 | Numeric |
| Autre | **W** | w0_NomPied02 | Alpha |
| Autre | **X** | w0_NbPied02 | Numeric |
| Autre | **Y** | w0_NomPied03 | Alpha |
| Autre | **Z** | w0_NbPied03 | Numeric |
| Autre | **BA** | w0_NomPied04 | Alpha |
| Autre | **BB** | w0_NbPied04 | Numeric |
| Autre | **BC** | w0_NomPied05 | Alpha |
| Autre | **BD** | w0_NbPied05 | Numeric |
| Autre | **BE** | w0_TotalSelect | Numeric |

</details>

## 12. EXPRESSIONS

**63 / 63 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONCATENATION | 10 | 5 |
| CALCULATION | 2 | 0 |
| CONDITION | 33 | 19 |
| CONSTANTE | 5 | 0 |
| OTHER | 9 | 0 |
| REFERENCE_VG | 4 | 0 |

### 12.2 Expressions cles par type

#### CONCATENATION (10 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 33 | `IF (>TopListe [D]='AG',MlsTrans ('age du')&' '&Str (>AgeMin [H],'2')&' ans / '&Str (>AgeMax [I],'2')&' ans','')` | [RM-015](#rm-RM-015) |
| CONCATENATION | 59 | `MlsTrans('Heure de fin :')&' '&MlsTrans(IF(VG88 AND [CM], 'Libération logement','Départ Village'))` | - |
| CONCATENATION | 50 | `w0_NbPied02 [X]&'  '&[AX]` | - |
| CONCATENATION | 51 | `Trim([BG])&IF(VG125 AND [CU]='O','N','')` | - |
| CONCATENATION | 39 | `Trim (P.I Heure depart village [K])&' '&IF (>CodeListe [C]='P',>HeurePresence [B]&' h','')` | - |
| ... | | *+5 autres* | |

#### CALCULATION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 63 | `[CT]+1` | - |
| CALCULATION | 49 | `w0_NbPied04 [BB]+1` | - |

#### CONDITION (33 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 30 | `IF (>TopListe [D]='HM','honey moon','')` | [RM-012](#rm-RM-012) |
| CONDITION | 31 | `IF (>TopListe [D]='VV','Vil/Vil','')` | [RM-013](#rm-RM-013) |
| CONDITION | 29 | `IF (>TopListe [D]='PY',MlsTrans ('pays'),'')` | [RM-011](#rm-RM-011) |
| CONDITION | 27 | `IF (>TopListe [D]='SI','single','')` | [RM-009](#rm-RM-009) |
| CONDITION | 28 | `IF (>TopListe [D]='NS','non single','')` | [RM-010](#rm-RM-010) |
| ... | | *+28 autres* | |

#### CONSTANTE (5 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 54 | `61` | - |
| CONSTANTE | 55 | `62` | - |
| CONSTANTE | 53 | `60` | - |
| CONSTANTE | 42 | `''` | - |
| CONSTANTE | 47 | `'PNT'` | - |

#### OTHER (9 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 16 | `Counter (0)` | - |
| OTHER | 14 | `'Village '&GetParam ('VILLAGE')` | - |
| OTHER | 62 | `ExpCalc('1'EXP) AND [CS]` | - |
| OTHER | 48 | `w0_NbPied02 [X]` | - |
| OTHER | 13 | `GetParam ('LANGUE')` | - |
| ... | | *+4 autres* | |

#### REFERENCE_VG (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 57 | `VG5` | - |
| REFERENCE_VG | 60 | `VG88` | - |
| REFERENCE_VG | 15 | `VG1` | - |
| REFERENCE_VG | 46 | `VG1` | - |

### 12.3 Toutes les expressions (63)

<details>
<summary>Voir les 63 expressions</summary>

#### CONCATENATION (10)

| IDE | Expression Decodee |
|-----|-------------------|
| 43 | `'- '&Str (Page (0,1),'3P0Z0')&' -'` |
| 33 | `IF (>TopListe [D]='AG',MlsTrans ('age du')&' '&Str (>AgeMin [H],'2')&' ans / '&Str (>AgeMax [I],'2')&' ans','')` |
| 37 | `MlsTrans ('Liste des')&' '&' '&Trim (w0_LibelleEdition [L])&' '&Trim (w0_f(CodeListe) [M])&IF (>TopListe [D]='CP' OR >TopListe [D]='GR',' '&Trim (>CodeGroupe [J])&' '&Trim (>HeurePresence [B])&' h','')&' '&MlsTrans ('le')&' '&DStr (>DateCalcul [A],'DD/MM/YYYY')` |
| 38 | `MlsTrans ('Liste des')&' '&' '&Trim (w0_LibelleEdition [L])&' '&Trim (w0_f(CodeListe) [M])&IF (>TopListe [D]='CP' OR >TopListe [D]='GR',' '&Trim (>CodeGroupe [J]),'')&' '&MlsTrans ('le')&' '&DStr (>DateCalcul [A],'DD/MM/YYYY')` |
| 40 | `MlsTrans ('Edition du')&' '&DStr (Date (),'DD/MM/YYYY')&' '&MlsTrans ('à')&' '&TStr (Time (),'HH:MM:SS')` |
| 41 | `MlsTrans ('Depart le')&' '&DStr (w0_NbPied03 [Z],'DD/MM/YYYY')&' '&MlsTrans ('à')&' '&[AA]&'  '&MlsTrans ('Retour le')&'  '&DStr ([AB],'DD/MM/YYYY')&' '&MlsTrans ('à')&' '&[AC]` |
| 50 | `w0_NbPied02 [X]&'  '&[AX]` |
| 59 | `MlsTrans('Heure de fin :')&' '&MlsTrans(IF(VG88 AND [CM], 'Libération logement','Départ Village'))` |
| 39 | `Trim (P.I Heure depart village [K])&' '&IF (>CodeListe [C]='P',>HeurePresence [B]&' h','')` |
| 51 | `Trim([BG])&IF(VG125 AND [CU]='O','N','')` |

#### CALCULATION (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 49 | `w0_NbPied04 [BB]+1` |
| 63 | `[CT]+1` |

#### CONDITION (33)

| IDE | Expression Decodee |
|-----|-------------------|
| 4 | `IF (>TopListe [D]='AG' OR >TopListe [D]='BB' OR >TopListe [D]='EN',MlsTrans ('Naissance'),'')` |
| 8 | `IF (>TopListe [D]='GR',MlsTrans ('GROUPE'),IF (>TopListe [D]='CA',MlsTrans ('DATE'),MlsTrans ('DATE/HR')))` |
| 9 | `IF (>TopListe [D]='GR',MlsTrans ('DEPART'),IF (>TopListe [D]='CA',MlsTrans ('FERMETURE'),MlsTrans ('DEPART')))` |
| 10 | `IF (>TopListe [D]='GR',MlsTrans ('GROUPE'),IF (>TopListe [D]='CA',MlsTrans ('DATE'),MlsTrans ('DATE/HR')))` |
| 11 | `IF (>TopListe [D]='GR',MlsTrans ('ARRIVEE'),IF (>TopListe [D]='CA',MlsTrans ('OUVERTURE'),MlsTrans ('ARRIVEE')))` |
| 20 | `IF (>CodeListe [C]='A',MlsTrans ('arrivants'),IF (>CodeListe [C]='V',MlsTrans ('arrivees'),IF (>CodeListe [C]='P',MlsTrans ('presents'),IF (>CodeListe [C]='D',MlsTrans ('departs'),IF (>CodeListe [C]='R',MlsTrans ('partants'),MlsTrans ('absents'))))))` |
| 21 | `IF (>TopListe [D]='PL','planning','')` |
| 22 | `IF (>TopListe [D]='GR',MlsTrans ('vol'),'')` |
| 23 | `IF (>TopListe [D]='CA',MlsTrans ('caisse'),'')` |
| 24 | `IF (>TopListe [D]='MI',MlsTrans ('millesias'),'')` |
| 25 | `IF (>TopListe [D]='BB',MlsTrans ('bebe'),'')` |
| 26 | `IF (>TopListe [D]='EN',MlsTrans ('enfant'),'')` |
| 27 | `IF (>TopListe [D]='SI','single','')` |
| 28 | `IF (>TopListe [D]='NS','non single','')` |
| 29 | `IF (>TopListe [D]='PY',MlsTrans ('pays'),'')` |
| 30 | `IF (>TopListe [D]='HM','honey moon','')` |
| 31 | `IF (>TopListe [D]='VV','Vil/Vil','')` |
| 32 | `IF (>TopListe [D]='NV','non Vil/Vil','')` |
| 34 | `IF (>TopListe [D]='CO',MlsTrans ('commentaire'),'')` |
| 35 | `IF (>TopListe [D]='CP',MlsTrans ('comptage'),'')` |
| 52 | `IF([BH] OR [BN] OR [BT],'EA'&Trim([BZ]),'')&IF(VG29,CASE([AU],'C',' CRE','D',' DEB','S',' SET',''),'')` |
| 56 | `IF([BH],Trim(VG61),'')&IF([BN],Trim(VG62),'')&IF([BT],Trim(VG63),'')` |
| 58 | `IF(VG88 AND [CM],TStr([CL],'HHhMMZ'), [AC])` |
| 1 | `>CodeListe [C]='P'` |
| 2 | `>CodeListe [C]<>'P'` |
| 3 | `>TopListe [D]='AG' OR >TopListe [D]='BB' OR >TopListe [D]='EN'` |
| 17 | `[AM]=''` |
| 18 | `[AM]='' AND >TopListe [D]='CO'` |
| 19 | `[AM]='CIRCUIT'` |
| 36 | `w0_f(CodeListe) [M]=''` |
| 44 | `INIGet ('[MAGIC_LOGICAL_NAMES]preview')='O'` |
| 45 | `>NbSelect [G]>0` |
| 61 | `>DateCalcul [A]` |

#### CONSTANTE (5)

| IDE | Expression Decodee |
|-----|-------------------|
| 42 | `''` |
| 47 | `'PNT'` |
| 53 | `60` |
| 54 | `61` |
| 55 | `62` |

#### OTHER (9)

| IDE | Expression Decodee |
|-----|-------------------|
| 5 | `W0_Libelle Logement [O]` |
| 6 | `[AH]` |
| 7 | `[AI]` |
| 12 | `GetParam ('SOCIETE')` |
| 13 | `GetParam ('LANGUE')` |
| 14 | `'Village '&GetParam ('VILLAGE')` |
| 16 | `Counter (0)` |
| 48 | `w0_NbPied02 [X]` |
| 62 | `ExpCalc('1'EXP) AND [CS]` |

#### REFERENCE_VG (4)

| IDE | Expression Decodee |
|-----|-------------------|
| 15 | `VG1` |
| 46 | `VG1` |
| 57 | `VG5` |
| 60 | `VG88` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [  Liste Clients present (IDE 162)](PBP-IDE-162.md) -> **Imprim GM present planning (IDE 165)**

Main -> ... -> [  Affich present planning GM (IDE 164)](PBP-IDE-164.md) -> **Imprim GM present planning (IDE 165)**

```mermaid
graph LR
    T165[165 Imprim GM present ...]
    style T165 fill:#58a6ff
    CC161[161 Liste des presents]
    style CC161 fill:#8b5cf6
    CC162[162 Liste Clients present]
    style CC162 fill:#3fb950
    CC164[164 Affich present pla...]
    style CC164 fill:#3fb950
    CC161 --> CC162
    CC161 --> CC164
    CC162 --> T165
    CC164 --> T165
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [162](PBP-IDE-162.md) |   Liste Clients present | 1 |
| [164](PBP-IDE-164.md) |   Affich present planning GM | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T165[165 Imprim GM present ...]
    style T165 fill:#58a6ff
    C166[166 Suppression nation...]
    T165 --> C166
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
| Lignes de logique | 220 | Taille moyenne |
| Expressions | 63 | Logique moderee |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 1 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 220) | Code sain |
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
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 15:34*
