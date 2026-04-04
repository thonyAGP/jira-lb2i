# PBP IDE 58 - Edition effectif quotidien

> **Analyse**: Phases 1-4 2026-02-03 09:01 -> 09:01 (21s) | Assemblage 09:01
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBP |
| IDE Position | 58 |
| Nom Programme | Edition effectif quotidien |
| Fichier source | `Prg_58.xml` |
| Domaine metier | Impression |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Edition effectif quotidien** assure la gestion complete de ce processus, accessible depuis [Effectif economat (IDE 53)](PBP-IDE-53.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Impression** (1 tache) : generation de tickets et documents

## 3. BLOCS FONCTIONNELS

### 3.1 Impression (1 tache)

Generation des documents et tickets.

---

#### <a id="t1"></a>58 - Edition effectif quotidien

**Role** : Generation du document : Edition effectif quotidien.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Effectif economat (IDE 53)](PBP-IDE-53.md)
- **Appelle**: 0 programmes | **Tables**: 1 (W:0 R:1 L:0) | **Taches**: 1 | **Expressions**: 207

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **58.1** | [**Edition effectif quotidien** (58)](#t1) | - | - | Impression |

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
| 824 | fac_pied_tva_pro |  | DB | R |   |   | 1 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 824 - fac_pied_tva_pro (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P.Date | R | Date |
| B | P.Code village | R | Alpha |
| C | P.Lieu sejour | R | Alpha |
| D | P.Nom lieu | R | Alpha |
| E | GM ORDI prev midi | R | Numeric |
| F | GM ORDI prev soir | R | Numeric |
| G | GM ORDI real midi | R | Numeric |
| H | GM ORDI real soir | R | Numeric |
| I | GM PROP prev midi | R | Numeric |
| J | GM PROP prev soir | R | Numeric |
| K | GM PROP real midi | R | Numeric |
| L | GM PROP real soir | R | Numeric |
| M | GM CLUB prev midi | R | Numeric |
| N | GM CLUB prev soir | R | Numeric |
| O | GM CLUB real midi | R | Numeric |
| P | GM CLUB real soir | R | Numeric |
| Q | GM SEM prev midi | R | Numeric |
| R | GM SEM prev soir | R | Numeric |
| S | GM SEM real midi | R | Numeric |
| T | GM SEM real soir | R | Numeric |
| U | GM VSL prev midi | R | Numeric |
| V | GM VSL prev soir | R | Numeric |
| W | GM VSL real midi | R | Numeric |
| X | GM VSL real soir | R | Numeric |
| Y | Total repas payant prev midi | R | Numeric |
| Z | Total repas payant prev soir | R | Numeric |
| BA | Total repas payant real midi | R | Numeric |
| BB | Total repas payant real soir | R | Numeric |
| BC | Nb JHP prev | R | Numeric |
| BD | NB JHP real | R | Numeric |
| BE | VRL prev midi | R | Numeric |
| BF | VRL prev soir | R | Numeric |
| BG | VRL real midi | R | Numeric |
| BH | VRL real soir | R | Numeric |
| BI | VRL HP CMB prev midi | R | Numeric |
| BJ | VRL HP CMB prev soir | R | Numeric |
| BK | VRL HP CMB real midi | R | Numeric |
| BL | VRL HP CMB real soir | R | Numeric |
| BM | Total repas VRL prev midi | R | Numeric |
| BN | Total repas VRL prev soir | R | Numeric |
| BO | Total repas VRL real midi | R | Numeric |
| BP | Total repas VRL real soir | R | Numeric |
| BQ | Nb JH vrl prev | R | Numeric |
| BR | Nb JH vrl real | R | Numeric |
| BS | Total JHP prev | R | Numeric |
| BT | Total JHP real | R | Numeric |
| BU | GO VILL prev midi | R | Numeric |
| BV | GO VILL prev soir | R | Numeric |
| BW | GO VILL real midi | R | Numeric |
| BX | GO VILL real soir | R | Numeric |
| BY | GO LOC prev midi | R | Numeric |
| BZ | GO LOC prev soir | R | Numeric |
| CA | GO LOC real midi | R | Numeric |
| CB | GO LOC real soir | R | Numeric |
| CC | GO VILL + LOC prev midi | R | Numeric |
| CD | GO VILL + LOC prev soir | R | Numeric |
| CE | GO VILL + LOC real midi | R | Numeric |
| CF | GO VILL + LOC real soir | R | Numeric |
| CG | GO OFFI prev midi | R | Numeric |
| CH | GO OFFI prev soir | R | Numeric |
| CI | GO OFFI real midi | R | Numeric |
| CJ | GO OFFI real soir | R | Numeric |
| CK | GO MARI prev midi | R | Numeric |
| CL | GO MARI prev soir | R | Numeric |
| CM | GO MARI real midi | R | Numeric |
| CN | GO MARI real soir | R | Numeric |
| CO | GE prev midi | R | Numeric |
| CP | GE prev soir | R | Numeric |
| CQ | GE real midi | R | Numeric |
| CR | GE real soir | R | Numeric |
| CS | GO MISS prev midi | R | Numeric |
| CT | GO MISS prev soir | R | Numeric |
| CU | GO MISS real midi | R | Numeric |
| CV | GO MISS real soir | R | Numeric |
| CW | GO ARTI prev midi | R | Numeric |
| CX | GO ARTI prev soir | R | Numeric |
| CY | GO ARTI real midi | R | Numeric |
| CZ | GO ARTI real soir | R | Numeric |
| DA | GO DOCT prev midi | R | Numeric |
| DB | GO DOCT prev soir | R | Numeric |
| DC | GO DOCT real midi | R | Numeric |
| DD | GO DOCT real soir | R | Numeric |
| DE | GO EDUC prev midi | R | Numeric |
| DF | GO EDUC prev soir | R | Numeric |
| DG | GO EDUC real midi | R | Numeric |
| DH | GO EDUC real soir | R | Numeric |
| DI | GO STAG prev midi | R | Numeric |
| DJ | GO STAG prev soir | R | Numeric |
| DK | GO STAG real midi | R | Numeric |
| DL | GO STAG real soir | R | Numeric |
| DM | GO IGP prev midi | R | Numeric |
| DN | GO IGP prev soir | R | Numeric |
| DO | GO IGP real midi | R | Numeric |
| DP | GO IGP real soir | R | Numeric |
| DQ | GO IGP2 prev midi | R | Numeric |
| DR | GO IGP2 prev soir | R | Numeric |
| DS | GO IGP2 real midi | R | Numeric |
| DT | GO IGP2 real soir | R | Numeric |
| DU | GO IGPV prev midi | R | Numeric |
| DV | GO IGPV prev soir | R | Numeric |
| DW | GO IGPV real midi | R | Numeric |
| DX | GO IGPV real soir | R | Numeric |
| DY | IGR prev midi | R | Numeric |
| DZ | IGR prev soir | R | Numeric |
| EA | IGR real midi | R | Numeric |
| EB | IGR real soir | R | Numeric |
| EC | IGR CM2 prev midi | R | Numeric |
| ED | IGR CM2 prev soir | R | Numeric |
| EE | IGR CM2 real midi | R | Numeric |
| EF | IGR CM2 real soir | R | Numeric |
| EG | GO ANS prev midi | R | Numeric |
| EH | GO ANS prev soir | R | Numeric |
| EI | GO ANS real midi | R | Numeric |
| EJ | GO ANS real soir | R | Numeric |
| EK | EXC real midi | R | Numeric |
| EL | EXC real soir | R | Numeric |
| EM | EXC prev midi | R | Numeric |
| EN | EXC prev soir | R | Numeric |
| EO | ECH real midi | R | Numeric |
| EP | ECH real soir | R | Numeric |
| EQ | ECH prev midi | R | Numeric |
| ER | ECH prev soir | R | Numeric |
| ES | GM SEJ PRES prev midi | R | Numeric |
| ET | GM SEJ PRES prev soir | R | Numeric |
| EU | GM SEJ PRES real midi | R | Numeric |
| EV | GM SEJ PRES real soir | R | Numeric |
| EW | IGR REPAS PRES prev midi | R | Numeric |
| EX | IGR REPAS PRES prev soir | R | Numeric |
| EY | IGR REPAS PRES real midi | R | Numeric |
| EZ | IGR REPAS PRES real soir | R | Numeric |
| FA | Total repas deficit prev midi | R | Numeric |
| FB | Total repas deficit prev soir | R | Numeric |
| FC | Total repas deficit real midi | R | Numeric |
| FD | Total repas deficit real soir | R | Numeric |
| FE | Nb JH deficit prev | R | Numeric |
| FF | NB JH deficit real | R | Numeric |
| FG | Nb repas Total prev midi | R | Numeric |
| FH | Nb repas Total prev soir | R | Numeric |
| FI | Nb repas Total real midi | R | Numeric |
| FJ | Nb repas Total real soir | R | Numeric |
| FK | Nb JH economat prev | R | Numeric |
| FL | Nb JH economat real | R | Numeric |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (4)

Variables recues du programme appelant ([Effectif economat (IDE 53)](PBP-IDE-53.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P.Date | Date | 2x parametre entrant |
| B | P.Code village | Alpha | 30x parametre entrant |
| C | P.Lieu sejour | Alpha | 30x parametre entrant |
| D | P.Nom lieu | Alpha | 27x parametre entrant |

### 11.2 Autres (138)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| E | GM ORDI prev midi | Numeric | 27x refs |
| F | GM ORDI prev soir | Numeric | 27x refs |
| G | GM ORDI real midi | Numeric | 7x refs |
| H | GM ORDI real soir | Numeric | - |
| I | GM PROP prev midi | Numeric | - |
| J | GM PROP prev soir | Numeric | - |
| K | GM PROP real midi | Numeric | - |
| L | GM PROP real soir | Numeric | 2x refs |
| M | GM CLUB prev midi | Numeric | 2x refs |
| N | GM CLUB prev soir | Numeric | 2x refs |
| O | GM CLUB real midi | Numeric | 2x refs |
| P | GM CLUB real soir | Numeric | 2x refs |
| Q | GM SEM prev midi | Numeric | 2x refs |
| R | GM SEM prev soir | Numeric | 2x refs |
| S | GM SEM real midi | Numeric | 2x refs |
| T | GM SEM real soir | Numeric | 2x refs |
| U | GM VSL prev midi | Numeric | 2x refs |
| V | GM VSL prev soir | Numeric | 2x refs |
| W | GM VSL real midi | Numeric | 2x refs |
| X | GM VSL real soir | Numeric | 2x refs |
| Y | Total repas payant prev midi | Numeric | - |
| Z | Total repas payant prev soir | Numeric | - |
| BA | Total repas payant real midi | Numeric | - |
| BB | Total repas payant real soir | Numeric | - |
| BC | Nb JHP prev | Numeric | 2x refs |
| BD | NB JHP real | Numeric | 2x refs |
| BE | VRL prev midi | Numeric | 3x refs |
| BF | VRL prev soir | Numeric | 3x refs |
| BG | VRL real midi | Numeric | 3x refs |
| BH | VRL real soir | Numeric | 2x refs |
| BI | VRL HP CMB prev midi | Numeric | 2x refs |
| BJ | VRL HP CMB prev soir | Numeric | 2x refs |
| BK | VRL HP CMB real midi | Numeric | 2x refs |
| BL | VRL HP CMB real soir | Numeric | 2x refs |
| BM | Total repas VRL prev midi | Numeric | 2x refs |
| BN | Total repas VRL prev soir | Numeric | 2x refs |
| BO | Total repas VRL real midi | Numeric | 2x refs |
| BP | Total repas VRL real soir | Numeric | - |
| BQ | Nb JH vrl prev | Numeric | - |
| BR | Nb JH vrl real | Numeric | - |
| BS | Total JHP prev | Numeric | - |
| BT | Total JHP real | Numeric | 2x refs |
| BU | GO VILL prev midi | Numeric | 2x refs |
| BV | GO VILL prev soir | Numeric | 2x refs |
| BW | GO VILL real midi | Numeric | 2x refs |
| BX | GO VILL real soir | Numeric | 2x refs |
| BY | GO LOC prev midi | Numeric | 2x refs |
| BZ | GO LOC prev soir | Numeric | 2x refs |
| CA | GO LOC real midi | Numeric | 2x refs |
| CB | GO LOC real soir | Numeric | 3x refs |
| CC | GO VILL + LOC prev midi | Numeric | 3x refs |
| CD | GO VILL + LOC prev soir | Numeric | 3x refs |
| CE | GO VILL + LOC real midi | Numeric | 3x refs |
| CF | GO VILL + LOC real soir | Numeric | 3x refs |
| CG | GO OFFI prev midi | Numeric | 3x refs |
| CH | GO OFFI prev soir | Numeric | 3x refs |
| CI | GO OFFI real midi | Numeric | 3x refs |
| CJ | GO OFFI real soir | Numeric | 2x refs |
| CK | GO MARI prev midi | Numeric | 2x refs |
| CL | GO MARI prev soir | Numeric | 2x refs |
| CM | GO MARI real midi | Numeric | 2x refs |
| CN | GO MARI real soir | Numeric | 2x refs |
| CO | GE prev midi | Numeric | 2x refs |
| CP | GE prev soir | Numeric | 2x refs |
| CQ | GE real midi | Numeric | 2x refs |
| CR | GE real soir | Numeric | 1x refs |
| CS | GO MISS prev midi | Numeric | 1x refs |
| CT | GO MISS prev soir | Numeric | - |
| CU | GO MISS real midi | Numeric | - |
| CV | GO MISS real soir | Numeric | - |
| CW | GO ARTI prev midi | Numeric | 2x refs |
| CX | GO ARTI prev soir | Numeric | 2x refs |
| CY | GO ARTI real midi | Numeric | 2x refs |
| CZ | GO ARTI real soir | Numeric | 2x refs |
| DA | GO DOCT prev midi | Numeric | - |
| DB | GO DOCT prev soir | Numeric | - |
| DC | GO DOCT real midi | Numeric | - |
| DD | GO DOCT real soir | Numeric | - |
| DE | GO EDUC prev midi | Numeric | - |
| DF | GO EDUC prev soir | Numeric | 27x refs |
| DG | GO EDUC real midi | Numeric | 2x refs |
| DH | GO EDUC real soir | Numeric | 2x refs |
| DI | GO STAG prev midi | Numeric | 2x refs |
| DJ | GO STAG prev soir | Numeric | 2x refs |
| DK | GO STAG real midi | Numeric | 2x refs |
| DL | GO STAG real soir | Numeric | 2x refs |
| DM | GO IGP prev midi | Numeric | 2x refs |
| DN | GO IGP prev soir | Numeric | 2x refs |
| DO | GO IGP real midi | Numeric | 3x refs |
| DP | GO IGP real soir | Numeric | 3x refs |
| DQ | GO IGP2 prev midi | Numeric | 3x refs |
| DR | GO IGP2 prev soir | Numeric | - |
| DS | GO IGP2 real midi | Numeric | 3x refs |
| DT | GO IGP2 real soir | Numeric | - |
| DU | GO IGPV prev midi | Numeric | 1x refs |
| DV | GO IGPV prev soir | Numeric | - |
| DW | GO IGPV real midi | Numeric | - |
| DX | GO IGPV real soir | Numeric | - |
| DY | IGR prev midi | Numeric | - |
| DZ | IGR prev soir | Numeric | 2x refs |
| EA | IGR real midi | Numeric | 2x refs |
| EB | IGR real soir | Numeric | 2x refs |
| EC | IGR CM2 prev midi | Numeric | 2x refs |
| ED | IGR CM2 prev soir | Numeric | 2x refs |
| EE | IGR CM2 real midi | Numeric | 2x refs |
| EF | IGR CM2 real soir | Numeric | 2x refs |
| EG | GO ANS prev midi | Numeric | 2x refs |
| EH | GO ANS prev soir | Numeric | 2x refs |
| EI | GO ANS real midi | Numeric | 2x refs |
| EJ | GO ANS real soir | Numeric | 2x refs |
| EK | EXC real midi | Numeric | 2x refs |
| EL | EXC real soir | Numeric | - |
| EM | EXC prev midi | Numeric | 3x refs |
| EN | EXC prev soir | Numeric | - |
| EO | ECH real midi | Numeric | - |
| EP | ECH real soir | Numeric | - |
| EQ | ECH prev midi | Numeric | 2x refs |
| ER | ECH prev soir | Numeric | 2x refs |
| ES | GM SEJ PRES prev midi | Numeric | 2x refs |
| ET | GM SEJ PRES prev soir | Numeric | 2x refs |
| EU | GM SEJ PRES real midi | Numeric | 2x refs |
| EV | GM SEJ PRES real soir | Numeric | 2x refs |
| EW | IGR REPAS PRES prev midi | Numeric | 2x refs |
| EX | IGR REPAS PRES prev soir | Numeric | 2x refs |
| EY | IGR REPAS PRES real midi | Numeric | 2x refs |
| EZ | IGR REPAS PRES real soir | Numeric | 2x refs |
| FA | Total repas deficit prev midi | Numeric | - |
| FB | Total repas deficit prev soir | Numeric | - |
| FC | Total repas deficit real midi | Numeric | - |
| FD | Total repas deficit real soir | Numeric | - |
| FE | Nb JH deficit prev | Numeric | 2x refs |
| FF | NB JH deficit real | Numeric | 2x refs |
| FG | Nb repas Total prev midi | Numeric | 2x refs |
| FH | Nb repas Total prev soir | Numeric | 2x refs |
| FI | Nb repas Total real midi | Numeric | 2x refs |
| FJ | Nb repas Total real soir | Numeric | 2x refs |
| FK | Nb JH economat prev | Numeric | 2x refs |
| FL | Nb JH economat real | Numeric | - |

<details>
<summary>Toutes les 142 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| P0 | **A** | P.Date | Date |
| P0 | **B** | P.Code village | Alpha |
| P0 | **C** | P.Lieu sejour | Alpha |
| P0 | **D** | P.Nom lieu | Alpha |
| Autre | **E** | GM ORDI prev midi | Numeric |
| Autre | **F** | GM ORDI prev soir | Numeric |
| Autre | **G** | GM ORDI real midi | Numeric |
| Autre | **H** | GM ORDI real soir | Numeric |
| Autre | **I** | GM PROP prev midi | Numeric |
| Autre | **J** | GM PROP prev soir | Numeric |
| Autre | **K** | GM PROP real midi | Numeric |
| Autre | **L** | GM PROP real soir | Numeric |
| Autre | **M** | GM CLUB prev midi | Numeric |
| Autre | **N** | GM CLUB prev soir | Numeric |
| Autre | **O** | GM CLUB real midi | Numeric |
| Autre | **P** | GM CLUB real soir | Numeric |
| Autre | **Q** | GM SEM prev midi | Numeric |
| Autre | **R** | GM SEM prev soir | Numeric |
| Autre | **S** | GM SEM real midi | Numeric |
| Autre | **T** | GM SEM real soir | Numeric |
| Autre | **U** | GM VSL prev midi | Numeric |
| Autre | **V** | GM VSL prev soir | Numeric |
| Autre | **W** | GM VSL real midi | Numeric |
| Autre | **X** | GM VSL real soir | Numeric |
| Autre | **Y** | Total repas payant prev midi | Numeric |
| Autre | **Z** | Total repas payant prev soir | Numeric |
| Autre | **BA** | Total repas payant real midi | Numeric |
| Autre | **BB** | Total repas payant real soir | Numeric |
| Autre | **BC** | Nb JHP prev | Numeric |
| Autre | **BD** | NB JHP real | Numeric |
| Autre | **BE** | VRL prev midi | Numeric |
| Autre | **BF** | VRL prev soir | Numeric |
| Autre | **BG** | VRL real midi | Numeric |
| Autre | **BH** | VRL real soir | Numeric |
| Autre | **BI** | VRL HP CMB prev midi | Numeric |
| Autre | **BJ** | VRL HP CMB prev soir | Numeric |
| Autre | **BK** | VRL HP CMB real midi | Numeric |
| Autre | **BL** | VRL HP CMB real soir | Numeric |
| Autre | **BM** | Total repas VRL prev midi | Numeric |
| Autre | **BN** | Total repas VRL prev soir | Numeric |
| Autre | **BO** | Total repas VRL real midi | Numeric |
| Autre | **BP** | Total repas VRL real soir | Numeric |
| Autre | **BQ** | Nb JH vrl prev | Numeric |
| Autre | **BR** | Nb JH vrl real | Numeric |
| Autre | **BS** | Total JHP prev | Numeric |
| Autre | **BT** | Total JHP real | Numeric |
| Autre | **BU** | GO VILL prev midi | Numeric |
| Autre | **BV** | GO VILL prev soir | Numeric |
| Autre | **BW** | GO VILL real midi | Numeric |
| Autre | **BX** | GO VILL real soir | Numeric |
| Autre | **BY** | GO LOC prev midi | Numeric |
| Autre | **BZ** | GO LOC prev soir | Numeric |
| Autre | **CA** | GO LOC real midi | Numeric |
| Autre | **CB** | GO LOC real soir | Numeric |
| Autre | **CC** | GO VILL + LOC prev midi | Numeric |
| Autre | **CD** | GO VILL + LOC prev soir | Numeric |
| Autre | **CE** | GO VILL + LOC real midi | Numeric |
| Autre | **CF** | GO VILL + LOC real soir | Numeric |
| Autre | **CG** | GO OFFI prev midi | Numeric |
| Autre | **CH** | GO OFFI prev soir | Numeric |
| Autre | **CI** | GO OFFI real midi | Numeric |
| Autre | **CJ** | GO OFFI real soir | Numeric |
| Autre | **CK** | GO MARI prev midi | Numeric |
| Autre | **CL** | GO MARI prev soir | Numeric |
| Autre | **CM** | GO MARI real midi | Numeric |
| Autre | **CN** | GO MARI real soir | Numeric |
| Autre | **CO** | GE prev midi | Numeric |
| Autre | **CP** | GE prev soir | Numeric |
| Autre | **CQ** | GE real midi | Numeric |
| Autre | **CR** | GE real soir | Numeric |
| Autre | **CS** | GO MISS prev midi | Numeric |
| Autre | **CT** | GO MISS prev soir | Numeric |
| Autre | **CU** | GO MISS real midi | Numeric |
| Autre | **CV** | GO MISS real soir | Numeric |
| Autre | **CW** | GO ARTI prev midi | Numeric |
| Autre | **CX** | GO ARTI prev soir | Numeric |
| Autre | **CY** | GO ARTI real midi | Numeric |
| Autre | **CZ** | GO ARTI real soir | Numeric |
| Autre | **DA** | GO DOCT prev midi | Numeric |
| Autre | **DB** | GO DOCT prev soir | Numeric |
| Autre | **DC** | GO DOCT real midi | Numeric |
| Autre | **DD** | GO DOCT real soir | Numeric |
| Autre | **DE** | GO EDUC prev midi | Numeric |
| Autre | **DF** | GO EDUC prev soir | Numeric |
| Autre | **DG** | GO EDUC real midi | Numeric |
| Autre | **DH** | GO EDUC real soir | Numeric |
| Autre | **DI** | GO STAG prev midi | Numeric |
| Autre | **DJ** | GO STAG prev soir | Numeric |
| Autre | **DK** | GO STAG real midi | Numeric |
| Autre | **DL** | GO STAG real soir | Numeric |
| Autre | **DM** | GO IGP prev midi | Numeric |
| Autre | **DN** | GO IGP prev soir | Numeric |
| Autre | **DO** | GO IGP real midi | Numeric |
| Autre | **DP** | GO IGP real soir | Numeric |
| Autre | **DQ** | GO IGP2 prev midi | Numeric |
| Autre | **DR** | GO IGP2 prev soir | Numeric |
| Autre | **DS** | GO IGP2 real midi | Numeric |
| Autre | **DT** | GO IGP2 real soir | Numeric |
| Autre | **DU** | GO IGPV prev midi | Numeric |
| Autre | **DV** | GO IGPV prev soir | Numeric |
| Autre | **DW** | GO IGPV real midi | Numeric |
| Autre | **DX** | GO IGPV real soir | Numeric |
| Autre | **DY** | IGR prev midi | Numeric |
| Autre | **DZ** | IGR prev soir | Numeric |
| Autre | **EA** | IGR real midi | Numeric |
| Autre | **EB** | IGR real soir | Numeric |
| Autre | **EC** | IGR CM2 prev midi | Numeric |
| Autre | **ED** | IGR CM2 prev soir | Numeric |
| Autre | **EE** | IGR CM2 real midi | Numeric |
| Autre | **EF** | IGR CM2 real soir | Numeric |
| Autre | **EG** | GO ANS prev midi | Numeric |
| Autre | **EH** | GO ANS prev soir | Numeric |
| Autre | **EI** | GO ANS real midi | Numeric |
| Autre | **EJ** | GO ANS real soir | Numeric |
| Autre | **EK** | EXC real midi | Numeric |
| Autre | **EL** | EXC real soir | Numeric |
| Autre | **EM** | EXC prev midi | Numeric |
| Autre | **EN** | EXC prev soir | Numeric |
| Autre | **EO** | ECH real midi | Numeric |
| Autre | **EP** | ECH real soir | Numeric |
| Autre | **EQ** | ECH prev midi | Numeric |
| Autre | **ER** | ECH prev soir | Numeric |
| Autre | **ES** | GM SEJ PRES prev midi | Numeric |
| Autre | **ET** | GM SEJ PRES prev soir | Numeric |
| Autre | **EU** | GM SEJ PRES real midi | Numeric |
| Autre | **EV** | GM SEJ PRES real soir | Numeric |
| Autre | **EW** | IGR REPAS PRES prev midi | Numeric |
| Autre | **EX** | IGR REPAS PRES prev soir | Numeric |
| Autre | **EY** | IGR REPAS PRES real midi | Numeric |
| Autre | **EZ** | IGR REPAS PRES real soir | Numeric |
| Autre | **FA** | Total repas deficit prev midi | Numeric |
| Autre | **FB** | Total repas deficit prev soir | Numeric |
| Autre | **FC** | Total repas deficit real midi | Numeric |
| Autre | **FD** | Total repas deficit real soir | Numeric |
| Autre | **FE** | Nb JH deficit prev | Numeric |
| Autre | **FF** | NB JH deficit real | Numeric |
| Autre | **FG** | Nb repas Total prev midi | Numeric |
| Autre | **FH** | Nb repas Total prev soir | Numeric |
| Autre | **FI** | Nb repas Total real midi | Numeric |
| Autre | **FJ** | Nb repas Total real soir | Numeric |
| Autre | **FK** | Nb JH economat prev | Numeric |
| Autre | **FL** | Nb JH economat real | Numeric |

</details>

## 12. EXPRESSIONS

**207 / 207 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCULATION | 149 | 0 |
| CONDITION | 34 | 0 |
| FORMAT | 4 | 0 |
| REFERENCE_VG | 1 | 0 |
| OTHER | 19 | 0 |

### 12.2 Expressions cles par type

#### CALCULATION (149 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 105 | `([AL]+[AM])/2` | - |
| CALCULATION | 104 | `[AS]+[AU]` | - |
| CALCULATION | 107 | `GO EDUC real midi [DG]+GO STAG real midi [DK]` | - |
| CALCULATION | 106 | `([AN]+[AO])/2` | - |
| CALCULATION | 103 | `[AR]+[AT]` | - |
| ... | | *+144 autres* | |

#### CONDITION (34 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 143 | `P.Code village [B]='IGR' AND (P.Lieu sejour [C]='HCMB' OR P.Lieu sejour [C]='')` | - |
| CONDITION | 142 | `P.Code village [B]='GM' AND P.Lieu sejour [C]='IGPV'` | - |
| CONDITION | 145 | `P.Code village [B]='GO' AND P.Lieu sejour [C]='ANS'` | - |
| CONDITION | 144 | `P.Code village [B]='IGR' AND P.Lieu sejour [C]='VSP'` | - |
| CONDITION | 139 | `P.Code village [B]='GO' AND P.Lieu sejour [C]='STAG'` | - |
| ... | | *+29 autres* | |

#### FORMAT (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| FORMAT | 5 | `'c:\temp\'&Trim(GO IGPV prev midi [DU])&IF(EXC prev midi [EM]<>'','_'&Trim(EXC prev midi [EM])&'_','_')&'effectif_quotidien_'&Trim(DStr(Date(),'YYYYMMDD'))&'.htm'` | - |
| FORMAT | 148 | `DStr(GM ORDI real midi [G],'DD/MM/YYYY')` | - |
| FORMAT | 1 | `DStr(GM ORDI real midi [G]-1,'DD/MM/YYYY')` | - |
| FORMAT | 2 | `DStr(GM ORDI real midi [G]+1,'DD/MM/YYYY')` | - |

#### REFERENCE_VG (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 6 | `VG37` | - |

#### OTHER (19 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 200 | `MlsTrans('Soir')` | - |
| OTHER | 202 | `MlsTrans('GO Artiste')` | - |
| OTHER | 198 | `MlsTrans('Nb de JH Economat')` | - |
| OTHER | 199 | `MlsTrans('Midi')` | - |
| OTHER | 203 | `MlsTrans('GO Docteur')` | - |
| ... | | *+14 autres* | |

### 12.3 Toutes les expressions (207)

<details>
<summary>Voir les 207 expressions</summary>

#### CALCULATION (149)

| IDE | Expression Decodee |
|-----|-------------------|
| 3 | `GM ORDI real midi [G]-1` |
| 4 | `GM ORDI real midi [G]+1` |
| 7 | `GM PROP real soir [L]+GO EDUC prev soir [DF]` |
| 8 | `IGR CM2 real soir [EF]+GO EDUC prev soir [DF]` |
| 9 | `IGR real soir [EB]+GO EDUC prev soir [DF]` |
| 10 | `GO OFFI real soir [CJ]+GO EDUC prev soir [DF]` |
| 11 | `GO IGP real midi [DO]+GO EDUC prev soir [DF]` |
| 12 | `GO LOC real soir [CB]+GO EDUC prev soir [DF]` |
| 13 | `GO VILL real soir [BX]+GO EDUC prev soir [DF]` |
| 14 | `Total JHP real [BT]+GO EDUC prev soir [DF]` |
| 15 | `VRL HP CMB real soir [BL]+GO EDUC prev soir [DF]` |
| 16 | `VRL real soir [BH]+GO EDUC prev soir [DF]` |
| 17 | `NB JHP real [BD]+GO EDUC prev soir [DF]` |
| 18 | `[AZ]+GO EDUC prev soir [DF]` |
| 19 | `GO STAG real midi [DK]+GO EDUC prev soir [DF]` |
| 20 | `GO EDUC real midi [DG]+GO EDUC prev soir [DF]` |
| 21 | `[AJ]+GO EDUC prev soir [DF]` |
| 22 | `[AH]+GO EDUC prev soir [DF]` |
| 23 | `[AB]+GO EDUC prev soir [DF]` |
| 24 | `GM VSL real soir [X]+GO EDUC prev soir [DF]` |
| 25 | `GM SEM real soir [T]+GO EDUC prev soir [DF]` |
| 26 | `GM CLUB real soir [P]+GO EDUC prev soir [DF]` |
| 27 | `GO VILL + LOC real soir [CF]+GO EDUC prev soir [DF]` |
| 28 | `GM CLUB prev midi [M]+GM ORDI prev soir [F]` |
| 29 | `GO ANS prev midi [EG]+GM ORDI prev soir [F]` |
| 30 | `IGR CM2 prev midi [EC]+GM ORDI prev soir [F]` |
| 31 | `GO MARI prev midi [CK]+GM ORDI prev soir [F]` |
| 32 | `GO IGP real soir [DP]+GM ORDI prev soir [F]` |
| 33 | `GO VILL + LOC prev midi [CC]+GM ORDI prev soir [F]` |
| 34 | `GO LOC prev midi [BY]+GM ORDI prev soir [F]` |
| 35 | `GO VILL prev midi [BU]+GM ORDI prev soir [F]` |
| 36 | `Total repas VRL prev midi [BM]+GM ORDI prev soir [F]` |
| 37 | `VRL HP CMB prev midi [BI]+GM ORDI prev soir [F]` |
| 38 | `VRL prev midi [BE]+GM ORDI prev soir [F]` |
| 39 | `Total repas payant rea... [BA]+GM ORDI prev soir [F]` |
| 40 | `GO STAG real soir [DL]+GM ORDI prev soir [F]` |
| 41 | `GO EDUC real soir [DH]+GM ORDI prev soir [F]` |
| 42 | `[AK]+GM ORDI prev soir [F]` |
| 43 | `[AI]+GM ORDI prev soir [F]` |
| 44 | `[AC]+GM ORDI prev soir [F]` |
| 45 | `Total repas payant pre... [Y]+GM ORDI prev soir [F]` |
| 46 | `GM VSL prev midi [U]+GM ORDI prev soir [F]` |
| 47 | `GM SEM prev midi [Q]+GM ORDI prev soir [F]` |
| 48 | `GO OFFI prev midi [CG]+GM ORDI prev soir [F]` |
| 49 | `GM CLUB prev soir [N]+P.Nom lieu [D]` |
| 50 | `IGR CM2 prev soir [ED]+P.Nom lieu [D]` |
| 51 | `IGR prev soir [DZ]+P.Nom lieu [D]` |
| 52 | `GO MARI prev soir [CL]+P.Nom lieu [D]` |
| 53 | `GO IGP2 prev midi [DQ]+P.Nom lieu [D]` |
| 54 | `GO VILL + LOC prev soir [CD]+P.Nom lieu [D]` |
| 55 | `GO LOC prev soir [BZ]+P.Nom lieu [D]` |
| 56 | `GO VILL prev soir [BV]+P.Nom lieu [D]` |
| 57 | `Total repas VRL prev soir [BN]+P.Nom lieu [D]` |
| 58 | `VRL HP CMB prev soir [BJ]+P.Nom lieu [D]` |
| 59 | `VRL prev soir [BF]+P.Nom lieu [D]` |
| 60 | `Total repas payant rea... [BB]+P.Nom lieu [D]` |
| 61 | `GO IGP prev midi [DM]+P.Nom lieu [D]` |
| 62 | `GO STAG prev midi [DI]+P.Nom lieu [D]` |
| 63 | `[AT]+P.Nom lieu [D]` |
| 64 | `[AR]+P.Nom lieu [D]` |
| 65 | `[AS]+GM ORDI prev midi [E]` |
| 66 | `[AD]+P.Nom lieu [D]` |
| 67 | `Total repas payant pre... [Z]+P.Nom lieu [D]` |
| 68 | `GM VSL prev soir [V]+P.Nom lieu [D]` |
| 69 | `GM SEM prev soir [R]+P.Nom lieu [D]` |
| 70 | `GO OFFI prev soir [CH]+P.Nom lieu [D]` |
| 71 | `GM CLUB real midi [O]+GM ORDI prev midi [E]` |
| 72 | `IGR CM2 real midi [EE]+GM ORDI prev midi [E]` |
| 73 | `IGR real midi [EA]+GM ORDI prev midi [E]` |
| 74 | `GO MARI real midi [CM]+GM ORDI prev midi [E]` |
| 75 | `GO IGP2 real midi [DS]+GM ORDI prev midi [E]` |
| 76 | `GO VILL + LOC real midi [CE]+GM ORDI prev midi [E]` |
| 77 | `GO LOC real midi [CA]+GM ORDI prev midi [E]` |
| 78 | `GO VILL real midi [BW]+GM ORDI prev midi [E]` |
| 79 | `Total repas VRL real midi [BO]+GM ORDI prev midi [E]` |
| 80 | `VRL HP CMB real midi [BK]+GM ORDI prev midi [E]` |
| 81 | `VRL real midi [BG]+GM ORDI prev midi [E]` |
| 82 | `Nb JHP prev [BC]+GM ORDI prev midi [E]` |
| 83 | `GO IGP prev soir [DN]+GM ORDI prev midi [E]` |
| 84 | `GO STAG prev soir [DJ]+GM ORDI prev midi [E]` |
| 85 | `[AU]+GM ORDI prev midi [E]` |
| 86 | `[AE]+GM ORDI prev midi [E]` |
| 87 | `[AA]+GM ORDI prev midi [E]` |
| 88 | `GM VSL real midi [W]+GM ORDI prev midi [E]` |
| 89 | `GM SEM real midi [S]+GM ORDI prev midi [E]` |
| 90 | `GO OFFI real midi [CI]+GM ORDI prev midi [E]` |
| 91 | `GM PROP real soir [L]+GM CLUB real soir [P]+GM SEM real soir [T]+GM VSL real soir [X]+[AB]` |
| 92 | `GM CLUB prev midi [M]+GM SEM prev midi [Q]+GM VSL prev midi [U]+Total repas payant pre... [Y]+[AC]` |
| 93 | `GM CLUB prev soir [N]+GM SEM prev soir [R]+GM VSL prev soir [V]+Total repas payant pre... [Z]+[AD]` |
| 94 | `GM CLUB real midi [O]+GM SEM real midi [S]+GM VSL real midi [W]+[AA]+[AE]` |
| 95 | `(GO ARTI prev midi [CW]+GO ARTI prev soir [CX])/2` |
| 96 | `(GO ARTI real midi [CY]+GO ARTI real soir [CZ])/2` |
| 97 | `GO VILL + LOC prev soir [CD]+GO IGP2 prev midi [DQ]` |
| 98 | `GO VILL + LOC real midi [CE]+GO IGP2 real midi [DS]` |
| 99 | `GO LOC real soir [CB]+GO IGP real midi [DO]` |
| 100 | `GO VILL + LOC prev midi [CC]+GO IGP real soir [DP]` |
| 101 | `[AH]+[AJ]` |
| 102 | `[AI]+[AK]` |
| 103 | `[AR]+[AT]` |
| 104 | `[AS]+[AU]` |
| 105 | `([AL]+[AM])/2` |
| 106 | `([AN]+[AO])/2` |
| 107 | `GO EDUC real midi [DG]+GO STAG real midi [DK]` |
| 108 | `GO EDUC real soir [DH]+GO STAG real soir [DL]` |
| 109 | `GO STAG prev midi [DI]+GO IGP prev midi [DM]` |
| 110 | `GO STAG prev soir [DJ]+GO IGP prev soir [DN]` |
| 111 | `[AV]+ECH prev midi [EQ]+GM SEJ PRES real midi [EU]+[AZ]+NB JHP real [BD]+VRL real soir [BH]+VRL HP CMB real soir [BL]+Total JHP real [BT]+GO VILL real soir [BX]+GO LOC real soir [CB]+GO IGP real midi [DO]+IGR REPAS PRES real midi [EY]+GO VILL + LOC real soir [CF]+Total repas deficit re... [FD]+GO OFFI real soir [CJ]+GO ANS prev soir [EH]+Nb repas Total prev soir [FH]` |
| 112 | `[AW]+ECH prev soir [ER]+GM SEJ PRES real soir [EV]+Total repas payant rea... [BA]+VRL prev midi [BE]+VRL HP CMB prev midi [BI]+Total repas VRL prev midi [BM]+GO VILL prev midi [BU]+GO LOC prev midi [BY]+GO VILL + LOC prev midi [CC]+GO IGP real soir [DP]+IGR REPAS PRES real soir [EZ]+GO OFFI prev midi [CG]+Nb JH deficit prev [FE]+GO MARI prev midi [CK]+GO ANS real midi [EI]+Nb repas Total real midi [FI]` |
| 113 | `[AX]+GM SEJ PRES prev midi [ES]+IGR REPAS PRES prev midi [EW]+Total repas payant rea... [BB]+VRL prev soir [BF]+VRL HP CMB prev soir [BJ]+Total repas VRL prev soir [BN]+GO VILL prev soir [BV]+GO LOC prev soir [BZ]+GO VILL + LOC prev soir [CD]+GO IGP2 prev midi [DQ]+Total repas deficit pr... [FA]+GO OFFI prev soir [CH]+NB JH deficit real [FF]+GO MARI prev soir [CL]+GO ANS real soir [EJ]+Nb repas Total real soir [FJ]` |
| 114 | `[AY]+GM SEJ PRES prev soir [ET]+IGR REPAS PRES prev soir [EX]+Nb JHP prev [BC]+VRL real midi [BG]+VRL HP CMB real midi [BK]+Total repas VRL real midi [BO]+GO VILL real midi [BW]+GO LOC real midi [CA]+GO VILL + LOC real midi [CE]+GO IGP2 real midi [DS]+Total repas deficit pr... [FB]+GO OFFI real midi [CI]+Nb repas Total prev midi [FG]+GO MARI real midi [CM]+EXC real midi [EK]+Nb JH economat prev [FK]` |
| 115 | `(GO MARI real soir [CN]+GE prev midi [CO])/2` |
| 116 | `(GE prev soir [CP]+GE real midi [CQ])/2` |
| 117 | `GO ARTI prev midi [CW]+[AL]+GO MARI real soir [CN]` |
| 118 | `GO ARTI prev soir [CX]+[AM]+GE prev midi [CO]` |
| 119 | `GO ARTI real midi [CY]+[AN]+GE prev soir [CP]` |
| 120 | `GO ARTI real soir [CZ]+[AO]+GE real midi [CQ]` |
| 121 | `[AF]+[AP]+GE real soir [CR]` |
| 122 | `[AG]+[AQ]+GO MISS prev midi [CS]` |
| 149 | `[AG]+[AQ]` |
| 150 | `[AF]+[AP]` |
| 156 | `GO OFFI prev soir [CH]-IGR prev soir [DZ]-IGR CM2 prev soir [ED]` |
| 157 | `GO OFFI real midi [CI]-IGR real midi [EA]-IGR CM2 real midi [EE]` |
| 158 | `GO VILL + LOC real soir [CF]-IGR real soir [EB]-IGR CM2 real soir [EF]` |
| 159 | `GO OFFI prev midi [CG]-IGR CM2 prev midi [EC]-GO ANS prev midi [EG]` |
| 160 | `GO ANS real soir [EJ]+P.Nom lieu [D]` |
| 161 | `Nb repas Total real soir [FJ]+P.Nom lieu [D]` |
| 162 | `EXC real midi [EK]+GM ORDI prev midi [E]` |
| 163 | `Nb JH economat prev [FK]+GM ORDI prev midi [E]` |
| 164 | `GO ANS prev soir [EH]+GO EDUC prev soir [DF]` |
| 165 | `Nb repas Total prev soir [FH]+GO EDUC prev soir [DF]` |
| 166 | `GO ANS real midi [EI]+GM ORDI prev soir [F]` |
| 167 | `Nb repas Total real midi [FI]+GM ORDI prev soir [F]` |
| 170 | `GM SEJ PRES prev midi [ES]+P.Nom lieu [D]` |
| 171 | `GM SEJ PRES prev soir [ET]+GM ORDI prev midi [E]` |
| 172 | `IGR REPAS PRES prev midi [EW]+P.Nom lieu [D]` |
| 173 | `IGR REPAS PRES prev soir [EX]+GM ORDI prev midi [E]` |
| 174 | `Total repas deficit pr... [FA]+P.Nom lieu [D]` |
| 175 | `Total repas deficit pr... [FB]+GM ORDI prev midi [E]` |
| 176 | `NB JH deficit real [FF]+P.Nom lieu [D]` |
| 177 | `Nb repas Total prev midi [FG]+GM ORDI prev midi [E]` |
| 178 | `ECH prev midi [EQ]+GO EDUC prev soir [DF]` |
| 179 | `ECH prev soir [ER]+GM ORDI prev soir [F]` |
| 180 | `GM SEJ PRES real midi [EU]+GO EDUC prev soir [DF]` |
| 181 | `GM SEJ PRES real soir [EV]+GM ORDI prev soir [F]` |
| 182 | `IGR REPAS PRES real midi [EY]+GO EDUC prev soir [DF]` |
| 183 | `IGR REPAS PRES real soir [EZ]+GM ORDI prev soir [F]` |
| 184 | `Total repas deficit re... [FD]+GO EDUC prev soir [DF]` |
| 185 | `Nb JH deficit prev [FE]+GM ORDI prev soir [F]` |
| 201 | `MlsTrans('GO Village + GO Locaux')` |

#### CONDITION (34)

| IDE | Expression Decodee |
|-----|-------------------|
| 146 | `P.Date [A]=GM ORDI real midi [G]-1` |
| 147 | `P.Date [A]=GM ORDI real midi [G]+1` |
| 123 | `P.Code village [B]='GM' AND P.Lieu sejour [C]='ORDI'` |
| 124 | `P.Code village [B]='GM' AND P.Lieu sejour [C]='PROP'` |
| 125 | `P.Code village [B]='GM' AND P.Lieu sejour [C]='CLUB'` |
| 126 | `P.Code village [B]='GM' AND P.Lieu sejour [C]='SEM'` |
| 127 | `P.Code village [B]='GM' AND P.Lieu sejour [C]='VSL'` |
| 128 | `P.Code village [B]='VRL' AND P.Lieu sejour [C]=''` |
| 129 | `P.Code village [B]='VRL' AND P.Lieu sejour [C]='CMB'` |
| 130 | `P.Code village [B]='GO' AND P.Lieu sejour [C]='VILL'` |
| 131 | `P.Code village [B]='GO' AND P.Lieu sejour [C]='LOC'` |
| 132 | `P.Code village [B]='GO' AND P.Lieu sejour [C]='OFFI'` |
| 133 | `P.Code village [B]='GO' AND P.Lieu sejour [C]='MARI'` |
| 134 | `P.Code village [B]='GO' AND P.Lieu sejour [C]='GE'` |
| 135 | `P.Code village [B]='GO' AND P.Lieu sejour [C]='MISS'` |
| 136 | `P.Code village [B]='GO' AND P.Lieu sejour [C]='ARTI'` |
| 137 | `P.Code village [B]='GO' AND P.Lieu sejour [C]='DOCT'` |
| 138 | `P.Code village [B]='GO' AND P.Lieu sejour [C]='EDUC'` |
| 139 | `P.Code village [B]='GO' AND P.Lieu sejour [C]='STAG'` |
| 140 | `P.Code village [B]='GM' AND P.Lieu sejour [C]='IGP'` |
| 141 | `P.Code village [B]='GM' AND P.Lieu sejour [C]='IGP2'` |
| 142 | `P.Code village [B]='GM' AND P.Lieu sejour [C]='IGPV'` |
| 143 | `P.Code village [B]='IGR' AND (P.Lieu sejour [C]='HCMB' OR P.Lieu sejour [C]='')` |
| 144 | `P.Code village [B]='IGR' AND P.Lieu sejour [C]='VSP'` |
| 145 | `P.Code village [B]='GO' AND P.Lieu sejour [C]='ANS'` |
| 151 | `P.Code village [B]='IGR' AND P.Lieu sejour [C]='EXC'` |
| 152 | `P.Code village [B]='IGR' AND P.Lieu sejour [C]='ECH'` |
| 153 | `IN(P.Code village [B],'GM','IGR') AND P.Lieu sejour [C]='PRES'` |
| 154 | `P.Code village [B]='GM' AND P.Lieu sejour [C]='PRES'` |
| 155 | `P.Code village [B]='IGR' AND P.Lieu sejour [C]='PRES'` |
| 168 | `CndRange(EXC prev midi [EM]<>'',EXC prev midi [EM])` |
| 169 | `EXC prev midi [EM]<>''` |
| 186 | `P.Code village [B]='GM' AND P.Lieu sejour [C]='PRES'` |
| 187 | `P.Code village [B]='IGR' AND P.Lieu sejour [C]='PRES'` |

#### FORMAT (4)

| IDE | Expression Decodee |
|-----|-------------------|
| 1 | `DStr(GM ORDI real midi [G]-1,'DD/MM/YYYY')` |
| 2 | `DStr(GM ORDI real midi [G]+1,'DD/MM/YYYY')` |
| 5 | `'c:\temp\'&Trim(GO IGPV prev midi [DU])&IF(EXC prev midi [EM]<>'','_'&Trim(EXC prev midi [EM])&'_','_')&'effectif_quotidien_'&Trim(DStr(Date(),'YYYYMMDD'))&'.htm'` |
| 148 | `DStr(GM ORDI real midi [G],'DD/MM/YYYY')` |

#### REFERENCE_VG (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 6 | `VG37` |

#### OTHER (19)

| IDE | Expression Decodee |
|-----|-------------------|
| 188 | `MlsTrans('Effectifs Quotidiens')` |
| 189 | `MlsTrans('Réalisations du')` |
| 190 | `MlsTrans('Prévisionnel du')` |
| 191 | `MlsTrans('Repas payants')` |
| 192 | `MlsTrans('Nb de JHP')` |
| 193 | `MlsTrans('Repas VRL')` |
| 194 | `MlsTrans('Nb de JH VRL')` |
| 195 | `MlsTrans('Repas Deficit')` |
| 196 | `MlsTrans('Nb de JH Deficit')` |
| 197 | `MlsTrans('Nb de Repas Total')` |
| 198 | `MlsTrans('Nb de JH Economat')` |
| 199 | `MlsTrans('Midi')` |
| 200 | `MlsTrans('Soir')` |
| 202 | `MlsTrans('GO Artiste')` |
| 203 | `MlsTrans('GO Docteur')` |
| 204 | `MlsTrans('GM Prestataire Séjour')` |
| 205 | `MlsTrans('GM Prestataire Repas')` |
| 206 | `MlsTrans('GO Stagiaire')` |
| 207 | `MlsTrans('GM Echange Inter Village')` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Effectif economat (IDE 53)](PBP-IDE-53.md) -> **Edition effectif quotidien (IDE 58)**

```mermaid
graph LR
    T58[58 Edition effectif qu...]
    style T58 fill:#58a6ff
    CC53[53 Effectif economat]
    style CC53 fill:#8b5cf6
    CC53 --> T58
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [53](PBP-IDE-53.md) | Effectif economat | 2 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T58[58 Edition effectif qu...]
    style T58 fill:#58a6ff
    NONE[Aucun callee]
    T58 -.-> NONE
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
| Lignes de logique | 306 | Taille moyenne |
| Expressions | 207 | Beaucoup de logique conditionnelle |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 1.3% (4 / 306) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Impression (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Templates HTML -> PDF via wkhtmltopdf ou Puppeteer.
- `PrintService` injectable avec choix imprimante

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 09:01*
