# PBP IDE 180 - Imprim AVPBDR secretaire

> **Analyse**: Phases 1-4 2026-02-03 15:40 -> 15:40 (12s) | Assemblage 15:40
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBP |
| IDE Position | 180 |
| Nom Programme | Imprim AVPBDR secretaire |
| Fichier source | `Prg_180.xml` |
| Dossier IDE | Liste |
| Taches | 3 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Imprim AVPBDR secretaire** assure la gestion complete de ce processus, accessible depuis [  Liste present personnel plan (IDE 227)](PBP-IDE-227.md), [  Liste personnels AVPBDR (IDE 234)](PBP-IDE-234.md), [  Liste CLients arrivant (IDE 156)](PBP-IDE-156.md), [  Liste Clients present (IDE 162)](PBP-IDE-162.md), [  Liste CLients depart (IDE 168)](PBP-IDE-168.md), [Liste CLients AVPBDR (IDE 174)](PBP-IDE-174.md), [  Affichage AVPBDR secretaire (IDE 179)](PBP-IDE-179.md).

Le flux de traitement s'organise en **2 blocs fonctionnels** :

- **Traitement** (2 taches) : traitements metier divers
- **Calcul** (1 tache) : calculs de montants, stocks ou compteurs

**Logique metier** : 5 regles identifiees couvrant conditions metier.

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (2 taches)

- **180** - Veuillez patienter ... **[[ECRAN]](#ecran-t1)**
- **180.2** - Ligne commentaire

#### Phase 2 : Calcul (1 tache)

- **180.1** - Calcul pied

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (2 taches)

Traitements internes.

---

#### <a id="t1"></a>180 - Veuillez patienter ... [[ECRAN]](#ecran-t1)

**Role** : Traitement : Veuillez patienter ....
**Ecran** : 424 x 56 DLU (MDI) | [Voir mockup](#ecran-t1)

---

#### <a id="t3"></a>180.2 - Ligne commentaire

**Role** : Traitement : Ligne commentaire.


### 3.2 Calcul (1 tache)

Calculs metier : montants, stocks, compteurs.

---

#### <a id="t2"></a>180.1 - Calcul pied

**Role** : Calcul : Calcul pied.
**Variables liees** : A (>DateCalcul), W (w0_NomPied01), X (w0_NbPied01), Y (w0_NomPied02), Z (w0_NbPied02)


## 5. REGLES METIER

5 regles identifiees:

### Autres (5 regles)

#### <a id="rm-RM-001"></a>[RM-001] Si >CodeListe [B]='A' alors MlsTrans ('arrivants') sinon IF (>CodeListe [B]='V',MlsTrans ('arrivees'),IF (>CodeListe [B]='P',MlsTrans ('presents'),IF (>CodeListe [B]='D',MlsTrans ('departs'),IF (>CodeListe [B]='R',MlsTrans ('partants'),MlsTrans ('absents'))))))

| Element | Detail |
|---------|--------|
| **Condition** | `>CodeListe [B]='A'` |
| **Si vrai** | MlsTrans ('arrivants') |
| **Si faux** | IF (>CodeListe [B]='V',MlsTrans ('arrivees'),IF (>CodeListe [B]='P',MlsTrans ('presents'),IF (>CodeListe [B]='D',MlsTrans ('departs'),IF (>CodeListe [B]='R',MlsTrans ('partants'),MlsTrans ('absents')))))) |
| **Variables** | B (>CodeListe) |
| **Expression source** | Expression 14 : `IF (>CodeListe [B]='A',MlsTrans ('arrivants'),IF (>CodeListe` |
| **Exemple** | Si >CodeListe [B]='A' â†’ MlsTrans ('arrivants') |

#### <a id="rm-RM-002"></a>[RM-002] Si >TopListe [C]='SE' alors MlsTrans ('secretaire') sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [C]='SE'` |
| **Si vrai** | MlsTrans ('secretaire') |
| **Si faux** | '') |
| **Variables** | C (>TopListe) |
| **Expression source** | Expression 15 : `IF (>TopListe [C]='SE',MlsTrans ('secretaire'),'')` |
| **Exemple** | Si >TopListe [C]='SE' â†’ MlsTrans ('secretaire'). Sinon â†’ '') |

#### <a id="rm-RM-003"></a>[RM-003] Si [DB] OR [DH] OR [DT] alors 'EA' sinon '')&IF([DB],Trim(VG61),'')&IF([DH],Trim(VG62),'')&IF([DT],Trim(VG63),'')

| Element | Detail |
|---------|--------|
| **Condition** | `[DB] OR [DH] OR [DT]` |
| **Si vrai** | 'EA' |
| **Si faux** | '')&IF([DB],Trim(VG61),'')&IF([DH],Trim(VG62),'')&IF([DT],Trim(VG63),'') |
| **Expression source** | Expression 32 : `IF([DB] OR [DH] OR [DT],'EA','')&IF([DB],Trim(VG61),'')&IF([` |
| **Exemple** | Si [DB] OR [DH] OR [DT] â†’ 'EA' |

#### <a id="rm-RM-004"></a>[RM-004] Si [EC] alors [ED]&[EE]&Str([AF] sinon '3P0'),Str(w0_f(CodeListe) [N],'4P0')&w0_g(TopListe) [O]&w0_LibelleEdition [P]&W0_Libelle Logement [Q])

| Element | Detail |
|---------|--------|
| **Condition** | `[EC]` |
| **Si vrai** | [ED]&[EE]&Str([AF] |
| **Si faux** | '3P0'),Str(w0_f(CodeListe) [N],'4P0')&w0_g(TopListe) [O]&w0_LibelleEdition [P]&W0_Libelle Logement [Q]) |
| **Variables** | N (w0_f(CodeListe)), O (w0_g(TopListe)), P (w0_LibelleEdition), Q (W0_Libelle Logement) |
| **Expression source** | Expression 34 : `IF([EC],[ED]&[EE]&Str([AF],'3P0'),Str(w0_f(CodeListe) [N],'4` |
| **Exemple** | Si [EC] â†’ [ED]&[EE]&Str([AF] |

#### <a id="rm-RM-005"></a>[RM-005] Si VG88 AND [EJ] alors TStr([EI] sinon 'HHhMMZ'),w0_NbPied02 [Z])

| Element | Detail |
|---------|--------|
| **Condition** | `VG88 AND [EJ]` |
| **Si vrai** | TStr([EI] |
| **Si faux** | 'HHhMMZ'),w0_NbPied02 [Z]) |
| **Variables** | Z (w0_NbPied02) |
| **Expression source** | Expression 36 : `IF(VG88 AND [EJ],TStr([EI],'HHhMMZ'),w0_NbPied02 [Z])` |
| **Exemple** | Si VG88 AND [EJ] â†’ TStr([EI]. Sinon â†’ 'HHhMMZ'),w0_NbPied02 [Z]) |

## 6. CONTEXTE

- **Appele par**: [  Liste present personnel plan (IDE 227)](PBP-IDE-227.md), [  Liste personnels AVPBDR (IDE 234)](PBP-IDE-234.md), [  Liste CLients arrivant (IDE 156)](PBP-IDE-156.md), [  Liste Clients present (IDE 162)](PBP-IDE-162.md), [  Liste CLients depart (IDE 168)](PBP-IDE-168.md), [Liste CLients AVPBDR (IDE 174)](PBP-IDE-174.md), [  Affichage AVPBDR secretaire (IDE 179)](PBP-IDE-179.md)
- **Appelle**: 0 programmes | **Tables**: 5 (W:0 R:3 L:2) | **Taches**: 3 | **Expressions**: 40

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (3 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **180.1** | [**Veuillez patienter ...** (180)](#t1) [mockup](#ecran-t1) | MDI | 424x56 | Traitement |
| 180.1.1 | [Ligne commentaire (180.2)](#t3) | MDI | - | |
| **180.2** | [**Calcul pied** (180.1)](#t2) | MDI | - | Calcul |

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

### Tables utilisees (5)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 118 | tables_imports |  | DB | R |   |   | 1 |
| 171 | commentaire______com |  | DB | R |   |   | 1 |
| 598 | tempo_ecr_previsions | Table temporaire ecran | TMP | R |   |   | 1 |
| 619 | tempo_userlist | Table temporaire ecran | TMP |   |   | L | 1 |
| 804 | valeur_credit_bar_defaut |  | DB |   |   | L | 1 |

### Colonnes par table (2 / 3 tables avec colonnes identifiees)

<details>
<summary>Table 118 - tables_imports (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | >DateCalcul | R | Date |
| B | >CodeListe | R | Alpha |
| C | >TopListe | R | Alpha |
| D | >HeurePresence | R | Alpha |
| E | >NomLogement | R | Alpha |
| F | >Total | R | Numeric |
| G | >NbSelect | R | Numeric |
| H | >Excel | R | Logical |
| I | >NomFicExcel | R | Alpha |
| J | >Libellé Sélection du Solde* | R | Unicode |
| K | >Soldé,Non_soldé,Tous | R | Unicode |
| L | >Tri Nom/Filiation | R | Logical |
| M | P.I Depart Village | R | Logical |
| N | w0_f(CodeListe) | R | Alpha |
| O | w0_g(TopListe) | R | Alpha |
| P | w0_LibelleEdition | R | Alpha |
| Q | W0_Libelle Logement | R | Alpha |
| R | v.LineExcel | R | Alpha |
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
| BG | w0_TotalSelect | R | Numeric |
| BH | Ordre Tri | R | Alpha |
| BI | w0_Dernier n° Compte | R | Numeric |

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

Variables recues du programme appelant ([  Liste present personnel plan (IDE 227)](PBP-IDE-227.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| M | P.I Depart Village | Logical | - |

### 11.2 Variables de session (5)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| R | v.LineExcel | Alpha | - |
| S | V.Existe ECI (Q60 Location) | Logical | - |
| T | V.Existe ECI (Q61 Cours) | Logical | - |
| U | V.Existe ECI (Q62 Enfant) | Logical | - |
| V | v Libelle affichage ECI | Alpha | 1x session |

### 11.3 Autres (29)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | >DateCalcul | Date | 1x refs |
| B | >CodeListe | Alpha | 2x refs |
| C | >TopListe | Alpha | 2x refs |
| D | >HeurePresence | Alpha | 2x refs |
| E | >NomLogement | Alpha | - |
| F | >Total | Numeric | - |
| G | >NbSelect | Numeric | - |
| H | >Excel | Logical | 1x refs |
| I | >NomFicExcel | Alpha | 1x refs |
| J | >Libellé Sélection du Solde* | Unicode | - |
| K | >Soldé,Non_soldé,Tous | Unicode | - |
| L | >Tri Nom/Filiation | Logical | 1x refs |
| N | w0_f(CodeListe) | Alpha | 1x refs |
| O | w0_g(TopListe) | Alpha | 2x refs |
| P | w0_LibelleEdition | Alpha | 2x refs |
| Q | W0_Libelle Logement | Alpha | 2x refs |
| W | w0_NomPied01 | Alpha | 2x refs |
| X | w0_NbPied01 | Numeric | 2x refs |
| Y | w0_NomPied02 | Alpha | 2x refs |
| Z | w0_NbPied02 | Numeric | 3x refs |
| BA | w0_NomPied03 | Alpha | - |
| BB | w0_NbPied03 | Numeric | - |
| BC | w0_NomPied04 | Alpha | - |
| BD | w0_NbPied04 | Numeric | - |
| BE | w0_NomPied05 | Alpha | - |
| BF | w0_NbPied05 | Numeric | - |
| BG | w0_TotalSelect | Numeric | - |
| BH | Ordre Tri | Alpha | - |
| BI | w0_Dernier n° Compte | Numeric | - |

<details>
<summary>Toutes les 35 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| P0 | **M** | P.I Depart Village | Logical |
| V. | **R** | v.LineExcel | Alpha |
| V. | **S** | V.Existe ECI (Q60 Location) | Logical |
| V. | **T** | V.Existe ECI (Q61 Cours) | Logical |
| V. | **U** | V.Existe ECI (Q62 Enfant) | Logical |
| V. | **V** | v Libelle affichage ECI | Alpha |
| Autre | **A** | >DateCalcul | Date |
| Autre | **B** | >CodeListe | Alpha |
| Autre | **C** | >TopListe | Alpha |
| Autre | **D** | >HeurePresence | Alpha |
| Autre | **E** | >NomLogement | Alpha |
| Autre | **F** | >Total | Numeric |
| Autre | **G** | >NbSelect | Numeric |
| Autre | **H** | >Excel | Logical |
| Autre | **I** | >NomFicExcel | Alpha |
| Autre | **J** | >Libellé Sélection du Solde* | Unicode |
| Autre | **K** | >Soldé,Non_soldé,Tous | Unicode |
| Autre | **L** | >Tri Nom/Filiation | Logical |
| Autre | **N** | w0_f(CodeListe) | Alpha |
| Autre | **O** | w0_g(TopListe) | Alpha |
| Autre | **P** | w0_LibelleEdition | Alpha |
| Autre | **Q** | W0_Libelle Logement | Alpha |
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
| Autre | **BG** | w0_TotalSelect | Numeric |
| Autre | **BH** | Ordre Tri | Alpha |
| Autre | **BI** | w0_Dernier n° Compte | Numeric |

</details>

## 12. EXPRESSIONS

**40 / 40 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONCATENATION | 7 | 0 |
| CONDITION | 13 | 5 |
| CONSTANTE | 4 | 0 |
| FORMAT | 1 | 0 |
| OTHER | 9 | 0 |
| REFERENCE_VG | 3 | 0 |
| NEGATION | 1 | 0 |
| CAST_LOGIQUE | 1 | 0 |
| STRING | 1 | 0 |

### 12.2 Expressions cles par type

#### CONCATENATION (7 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 9 | `'Nom'&VG36&'Prénom'&VG36&'Sex'&VG36&'Pays'&VG36&'N° Adherent'&VG36&'Adresse'&VG36&'Date Arrivée'&VG36&'Date Départ'&VG36&'LIB ECI'` | - |
| CONCATENATION | 37 | `MlsTrans('Heure de fin :')&' '&MlsTrans(IF(VG88 AND [EJ], 'Libération logement','Départ Village'))` | - |
| CONCATENATION | 17 | `Trim (>Libellé Sélection du ... [J])&' '&>HeurePresence [D]&IF (>HeurePresence [D]='','',' h')` | - |
| CONCATENATION | 20 | `MlsTrans ('Depart le')&' '&DStr (w0_NomPied01 [W],'DD/MM/YYYY')&' '&MlsTrans ('à')&' '&w0_NbPied01 [X]&'  '&MlsTrans ('Retour le')&'  '&DStr (w0_NomPied02 [Y],'DD/MM/YYYY')&' '&MlsTrans ('à')&' '&w0_NbPied02 [Z]` | - |
| CONCATENATION | 22 | `'- '&Str (Page (0,1),'3P0Z0')&' -'` | - |
| ... | | *+2 autres* | |

#### CONDITION (13 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 34 | `IF([EC],[ED]&[EE]&Str([AF],'3P0'),Str(w0_f(CodeListe) [N],'4P0')&w0_g(TopListe) [O]&w0_LibelleEdition [P]&W0_Libelle Logement [Q])` | [RM-004](#rm-RM-004) |
| CONDITION | 36 | `IF(VG88 AND [EJ],TStr([EI],'HHhMMZ'),w0_NbPied02 [Z])` | [RM-005](#rm-RM-005) |
| CONDITION | 32 | `IF([DB] OR [DH] OR [DT],'EA','')&IF([DB],Trim(VG61),'')&IF([DH],Trim(VG62),'')&IF([DT],Trim(VG63),'')` | [RM-003](#rm-RM-003) |
| CONDITION | 14 | `IF (>CodeListe [B]='A',MlsTrans ('arrivants'),IF (>CodeListe [B]='V',MlsTrans ('arrivees'),IF (>CodeListe [B]='P',MlsTrans ('presents'),IF (>CodeListe [B]='D',MlsTrans ('departs'),IF (>CodeListe [B]='R',MlsTrans ('partants'),MlsTrans ('absents'))))))` | [RM-001](#rm-RM-001) |
| CONDITION | 15 | `IF (>TopListe [C]='SE',MlsTrans ('secretaire'),'')` | [RM-002](#rm-RM-002) |
| ... | | *+8 autres* | |

#### CONSTANTE (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 30 | `61` | - |
| CONSTANTE | 31 | `62` | - |
| CONSTANTE | 21 | `''` | - |
| CONSTANTE | 29 | `60` | - |

#### FORMAT (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| FORMAT | 10 | `Trim(w0_g(TopListe) [O])&VG36&Trim(w0_LibelleEdition [P])&VG36&W0_Libelle Logement [Q]&VG36&v Libelle affichage ECI [V]&VG36&Trim([AL])&' '& Trim([AM])&' '&
Trim([AJ])&' '&Trim([AI])&' '&Trim([AH])&' '&Trim([AK])&VG36&
DStr(w0_NomPied01 [W],'DD/MM/YYYY')&' '&w0_NbPied01 [X]&VG36&TStr(w0_NomPied02 [Y],'DD/MM/YYYY')&' '&
IF (VG88 AND [EJ],TStr([EI],'HHhMMZ'),w0_NbPied02 [Z])&VG36&[DU]` | - |

#### OTHER (9 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 26 | `[AF]` | - |
| OTHER | 25 | `[AE]` | - |
| OTHER | 35 | `[AE]` | - |
| OTHER | 27 | `[DC]` | - |
| OTHER | 11 | `Counter (0)` | - |
| ... | | *+4 autres* | |

#### REFERENCE_VG (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 38 | `VG88` | - |
| REFERENCE_VG | 33 | `VG5` | - |
| REFERENCE_VG | 3 | `VG1` | - |

#### NEGATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| NEGATION | 5 | `NOT [DX]` | - |

#### CAST_LOGIQUE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 18 | `'FALSE'LOG` | - |

#### STRING (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| STRING | 4 | `Trim([DY])` | - |

### 12.3 Toutes les expressions (40)

<details>
<summary>Voir les 40 expressions</summary>

#### CONCATENATION (7)

| IDE | Expression Decodee |
|-----|-------------------|
| 22 | `'- '&Str (Page (0,1),'3P0Z0')&' -'` |
| 16 | `MlsTrans ('Liste des')&' '&Trim (>Excel [H])&' '&Trim (>NomFicExcel [I])&' '&MlsTrans ('le')&' '&DStr (>DateCalcul [A],'DD/MM/YYYY')&IF (>CodeListe [B]='P',' '&>HeurePresence [D]&' h','')` |
| 19 | `MlsTrans ('Edition du')&' '&DStr (Date (),'DD/MM/YYYY')&' '&MlsTrans ('à')&' '&TStr (Time (),'HH:MM:SS')` |
| 20 | `MlsTrans ('Depart le')&' '&DStr (w0_NomPied01 [W],'DD/MM/YYYY')&' '&MlsTrans ('à')&' '&w0_NbPied01 [X]&'  '&MlsTrans ('Retour le')&'  '&DStr (w0_NomPied02 [Y],'DD/MM/YYYY')&' '&MlsTrans ('à')&' '&w0_NbPied02 [Z]` |
| 9 | `'Nom'&VG36&'Prénom'&VG36&'Sex'&VG36&'Pays'&VG36&'N° Adherent'&VG36&'Adresse'&VG36&'Date Arrivée'&VG36&'Date Départ'&VG36&'LIB ECI'` |
| 37 | `MlsTrans('Heure de fin :')&' '&MlsTrans(IF(VG88 AND [EJ], 'Libération logement','Départ Village'))` |
| 17 | `Trim (>Libellé Sélection du ... [J])&' '&>HeurePresence [D]&IF (>HeurePresence [D]='','',' h')` |

#### CONDITION (13)

| IDE | Expression Decodee |
|-----|-------------------|
| 14 | `IF (>CodeListe [B]='A',MlsTrans ('arrivants'),IF (>CodeListe [B]='V',MlsTrans ('arrivees'),IF (>CodeListe [B]='P',MlsTrans ('presents'),IF (>CodeListe [B]='D',MlsTrans ('departs'),IF (>CodeListe [B]='R',MlsTrans ('partants'),MlsTrans ('absents'))))))` |
| 15 | `IF (>TopListe [C]='SE',MlsTrans ('secretaire'),'')` |
| 32 | `IF([DB] OR [DH] OR [DT],'EA','')&IF([DB],Trim(VG61),'')&IF([DH],Trim(VG62),'')&IF([DT],Trim(VG63),'')` |
| 34 | `IF([EC],[ED]&[EE]&Str([AF],'3P0'),Str(w0_f(CodeListe) [N],'4P0')&w0_g(TopListe) [O]&w0_LibelleEdition [P]&W0_Libelle Logement [Q])` |
| 36 | `IF(VG88 AND [EJ],TStr([EI],'HHhMMZ'),w0_NbPied02 [Z])` |
| 12 | `[AJ]='' AND >TopListe [C]='CO'` |
| 13 | `[AJ]='CIRCUIT'` |
| 23 | `INIGet ('[MAGIC_LOGICAL_NAMES]preview')='O'` |
| 24 | `>Tri Nom/Filiation [L]` |
| 28 | `VG44>1` |
| 40 | `[EL]='T'` |
| 7 | `Trim(>Libellé Sélection du ... [J])` |
| 39 | `CndRange(Trim([EK])<>'' AND [EL]<>'T',IF([EL]='N','X',''))` |

#### CONSTANTE (4)

| IDE | Expression Decodee |
|-----|-------------------|
| 21 | `''` |
| 29 | `60` |
| 30 | `61` |
| 31 | `62` |

#### FORMAT (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 10 | `Trim(w0_g(TopListe) [O])&VG36&Trim(w0_LibelleEdition [P])&VG36&W0_Libelle Logement [Q]&VG36&v Libelle affichage ECI [V]&VG36&Trim([AL])&' '& Trim([AM])&' '&
Trim([AJ])&' '&Trim([AI])&' '&Trim([AH])&' '&Trim([AK])&VG36&
DStr(w0_NomPied01 [W],'DD/MM/YYYY')&' '&w0_NbPied01 [X]&VG36&TStr(w0_NomPied02 [Y],'DD/MM/YYYY')&' '&
IF (VG88 AND [EJ],TStr([EI],'HHhMMZ'),w0_NbPied02 [Z])&VG36&[DU]` |

#### OTHER (9)

| IDE | Expression Decodee |
|-----|-------------------|
| 1 | `GetParam ('SOCIETE')` |
| 2 | `'Village '&GetParam ('VILLAGE')` |
| 6 | `[DX]` |
| 8 | `IsFirstRecordCycle (0)` |
| 11 | `Counter (0)` |
| 25 | `[AE]` |
| 26 | `[AF]` |
| 27 | `[DC]` |
| 35 | `[AE]` |

#### REFERENCE_VG (3)

| IDE | Expression Decodee |
|-----|-------------------|
| 3 | `VG1` |
| 33 | `VG5` |
| 38 | `VG88` |

#### NEGATION (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 5 | `NOT [DX]` |

#### CAST_LOGIQUE (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 18 | `'FALSE'LOG` |

#### STRING (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 4 | `Trim([DY])` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [  Liste present personnel plan (IDE 227)](PBP-IDE-227.md) -> **Imprim AVPBDR secretaire (IDE 180)**

Main -> ... -> [  Liste personnels AVPBDR (IDE 234)](PBP-IDE-234.md) -> **Imprim AVPBDR secretaire (IDE 180)**

Main -> ... -> [  Liste CLients arrivant (IDE 156)](PBP-IDE-156.md) -> **Imprim AVPBDR secretaire (IDE 180)**

Main -> ... -> [  Liste Clients present (IDE 162)](PBP-IDE-162.md) -> **Imprim AVPBDR secretaire (IDE 180)**

Main -> ... -> [  Liste CLients depart (IDE 168)](PBP-IDE-168.md) -> **Imprim AVPBDR secretaire (IDE 180)**

Main -> ... -> [Liste CLients AVPBDR (IDE 174)](PBP-IDE-174.md) -> **Imprim AVPBDR secretaire (IDE 180)**

Main -> ... -> [  Affichage AVPBDR secretaire (IDE 179)](PBP-IDE-179.md) -> **Imprim AVPBDR secretaire (IDE 180)**

```mermaid
graph LR
    T180[180 Imprim AVPBDR secr...]
    style T180 fill:#58a6ff
    CC161[161 Liste des presents]
    style CC161 fill:#8b5cf6
    CC173[173 Liste des Absents]
    style CC173 fill:#8b5cf6
    CC167[167 Liste des departs]
    style CC167 fill:#8b5cf6
    CC172[172 Liste des partants]
    style CC172 fill:#8b5cf6
    CC160[160 Liste des arrivees]
    style CC160 fill:#8b5cf6
    CC155[155 Liste des arrivants]
    style CC155 fill:#8b5cf6
    CC162[162 Liste Clients present]
    style CC162 fill:#3fb950
    CC156[156 Liste CLients arri...]
    style CC156 fill:#3fb950
    CC179[179 Affichage AVPBDR s...]
    style CC179 fill:#3fb950
    CC174[174 Liste CLients AVPBDR]
    style CC174 fill:#3fb950
    CC168[168 Liste CLients depart]
    style CC168 fill:#3fb950
    CC155 --> CC156
    CC161 --> CC156
    CC167 --> CC156
    CC160 --> CC156
    CC172 --> CC156
    CC173 --> CC156
    CC155 --> CC162
    CC161 --> CC162
    CC167 --> CC162
    CC160 --> CC162
    CC172 --> CC162
    CC173 --> CC162
    CC155 --> CC168
    CC161 --> CC168
    CC167 --> CC168
    CC160 --> CC168
    CC172 --> CC168
    CC173 --> CC168
    CC155 --> CC174
    CC161 --> CC174
    CC167 --> CC174
    CC160 --> CC174
    CC172 --> CC174
    CC173 --> CC174
    CC155 --> CC179
    CC161 --> CC179
    CC167 --> CC179
    CC160 --> CC179
    CC172 --> CC179
    CC173 --> CC179
    CC156 --> T180
    CC162 --> T180
    CC168 --> T180
    CC174 --> T180
    CC179 --> T180
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [227](PBP-IDE-227.md) |   Liste present personnel plan | 2 |
| [234](PBP-IDE-234.md) |   Liste personnels AVPBDR | 2 |
| [156](PBP-IDE-156.md) |   Liste CLients arrivant | 1 |
| [162](PBP-IDE-162.md) |   Liste Clients present | 1 |
| [168](PBP-IDE-168.md) |   Liste CLients depart | 1 |
| [174](PBP-IDE-174.md) | Liste CLients AVPBDR | 1 |
| [179](PBP-IDE-179.md) |   Affichage AVPBDR secretaire | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T180[180 Imprim AVPBDR secr...]
    style T180 fill:#58a6ff
    NONE[Aucun callee]
    T180 -.-> NONE
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
| Lignes de logique | 178 | Programme compact |
| Expressions | 40 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 178) | Code sain |
| Regles metier | 5 | Quelques regles a preserver |

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
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 15:40*
