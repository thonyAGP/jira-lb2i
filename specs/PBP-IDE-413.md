# PBP IDE 413 - Edition effectif mensuel

> **Analyse**: Phases 1-4 2026-02-03 16:55 -> 16:55 (15s) | Assemblage 16:55
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBP |
| IDE Position | 413 |
| Nom Programme | Edition effectif mensuel |
| Fichier source | `Prg_413.xml` |
| Dossier IDE | Sauvegardes |
| Taches | 10 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 7 |
| :warning: Statut | **ORPHELIN_POTENTIEL** |

## 2. DESCRIPTION FONCTIONNELLE

**Edition effectif mensuel** assure la gestion complete de ce processus.

Le flux de traitement s'organise en **3 blocs fonctionnels** :

- **Traitement** (7 taches) : traitements metier divers
- **Impression** (2 taches) : generation de tickets et documents
- **Calcul** (1 tache) : calculs de montants, stocks ou compteurs

**Logique metier** : 9 regles identifiees couvrant conditions metier.

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Impression (2 taches)

- **413** - Edition effectif mensuel
- **413.1** - Edition effectif mensuel **[[ECRAN]](#ecran-t2)**

Delegue a : [Edition corrections effectif (IDE 62)](PBP-IDE-62.md)

#### Phase 2 : Calcul (1 tache)

- **413.1.1** - Calcul capacite

#### Phase 3 : Traitement (7 taches)

- **413.1.1.1** - Cumul Plafond Lit **[[ECRAN]](#ecran-t4)**
- **413.1.1.2** - Cumul Lit Table Import
- **413.1.2** - Cumul GM tranférés HP/SP **[[ECRAN]](#ecran-t6)**
- **413.1.3** - Execute SQL command **[[ECRAN]](#ecran-t7)**
- **413.1.4** - Execute SQL command **[[ECRAN]](#ecran-t8)**
- **413.1.5** - Execute SQL command **[[ECRAN]](#ecran-t9)**
- **413.2** - Pilotage Gestion de Crise

Delegue a : [Deficit ANS/MISS/ARTI/DOCT (IDE 49)](PBP-IDE-49.md), [Deficit IGP (IDE 46)](PBP-IDE-46.md), [Deficit IGR (IDE 47)](PBP-IDE-47.md), [Deficit CMB (IDE 48)](PBP-IDE-48.md), [Deficit PRES (IDE 51)](PBP-IDE-51.md), [Deficit CM2 (IDE 52)](PBP-IDE-52.md)

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Impression (2 taches)

Generation des documents et tickets.

---

#### <a id="t1"></a>413 - Edition effectif mensuel

**Role** : Generation du document : Edition effectif mensuel.
**Delegue a** : [Edition corrections effectif (IDE 62)](PBP-IDE-62.md)

---

#### <a id="t2"></a>413.1 - Edition effectif mensuel [[ECRAN]](#ecran-t2)

**Role** : Generation du document : Edition effectif mensuel.
**Ecran** : 302 x 71 DLU | [Voir mockup](#ecran-t2)
**Delegue a** : [Edition corrections effectif (IDE 62)](PBP-IDE-62.md)


### 3.2 Calcul (1 tache)

Calculs metier : montants, stocks, compteurs.

---

#### <a id="t3"></a>413.1.1 - Calcul capacite

**Role** : Calcul : Calcul capacite.
**Variables liees** : HW (V.Capacite M1), HX (V.Capacite M2), HY (V.Capacite M3), HZ (V.Capacite M4), IA (V.Capacite M5)


### 3.3 Traitement (7 taches)

Traitements internes.

---

#### <a id="t4"></a>413.1.1.1 - Cumul Plafond Lit [[ECRAN]](#ecran-t4)

**Role** : Traitement : Cumul Plafond Lit.
**Ecran** : 488 x 0 DLU | [Voir mockup](#ecran-t4)
**Variables liees** : J (V.Cumul sur 1er mois), K (V.Cumul sur dernier mois), KB (v Cumul Gm Arrivés), KC (v Cumul Gm Transportés / Packag), KD (v Cumul GM V/V)
**Delegue a** : [Deficit ANS/MISS/ARTI/DOCT (IDE 49)](PBP-IDE-49.md), [Deficit IGP (IDE 46)](PBP-IDE-46.md), [Deficit IGR (IDE 47)](PBP-IDE-47.md)

---

#### <a id="t5"></a>413.1.1.2 - Cumul Lit Table Import

**Role** : Traitement : Cumul Lit Table Import.
**Variables liees** : J (V.Cumul sur 1er mois), K (V.Cumul sur dernier mois), KB (v Cumul Gm Arrivés), KC (v Cumul Gm Transportés / Packag), KD (v Cumul GM V/V)
**Delegue a** : [Deficit ANS/MISS/ARTI/DOCT (IDE 49)](PBP-IDE-49.md), [Deficit IGP (IDE 46)](PBP-IDE-46.md), [Deficit IGR (IDE 47)](PBP-IDE-47.md)

---

#### <a id="t6"></a>413.1.2 - Cumul GM tranférés HP/SP [[ECRAN]](#ecran-t6)

**Role** : Traitement : Cumul GM tranférés HP/SP.
**Ecran** : 681 x 0 DLU | [Voir mockup](#ecran-t6)
**Variables liees** : J (V.Cumul sur 1er mois), K (V.Cumul sur dernier mois), KB (v Cumul Gm Arrivés), KC (v Cumul Gm Transportés / Packag), KD (v Cumul GM V/V)
**Delegue a** : [Deficit ANS/MISS/ARTI/DOCT (IDE 49)](PBP-IDE-49.md), [Deficit IGP (IDE 46)](PBP-IDE-46.md), [Deficit IGR (IDE 47)](PBP-IDE-47.md)

---

#### <a id="t7"></a>413.1.3 - Execute SQL command [[ECRAN]](#ecran-t7)

**Role** : Traitement : Execute SQL command.
**Ecran** : 120 x 195 DLU | [Voir mockup](#ecran-t7)
**Delegue a** : [Deficit ANS/MISS/ARTI/DOCT (IDE 49)](PBP-IDE-49.md), [Deficit IGP (IDE 46)](PBP-IDE-46.md), [Deficit IGR (IDE 47)](PBP-IDE-47.md)

---

#### <a id="t8"></a>413.1.4 - Execute SQL command [[ECRAN]](#ecran-t8)

**Role** : Traitement : Execute SQL command.
**Ecran** : 120 x 195 DLU | [Voir mockup](#ecran-t8)
**Delegue a** : [Deficit ANS/MISS/ARTI/DOCT (IDE 49)](PBP-IDE-49.md), [Deficit IGP (IDE 46)](PBP-IDE-46.md), [Deficit IGR (IDE 47)](PBP-IDE-47.md)

---

#### <a id="t9"></a>413.1.5 - Execute SQL command [[ECRAN]](#ecran-t9)

**Role** : Traitement : Execute SQL command.
**Ecran** : 120 x 195 DLU | [Voir mockup](#ecran-t9)
**Delegue a** : [Deficit ANS/MISS/ARTI/DOCT (IDE 49)](PBP-IDE-49.md), [Deficit IGP (IDE 46)](PBP-IDE-46.md), [Deficit IGR (IDE 47)](PBP-IDE-47.md)

---

#### <a id="t10"></a>413.2 - Pilotage Gestion de Crise

**Role** : Gestion du moyen de paiement : Pilotage Gestion de Crise.
**Variables liees** : A (P.Appel de gestion crise)
**Delegue a** : [Deficit ANS/MISS/ARTI/DOCT (IDE 49)](PBP-IDE-49.md), [Deficit IGP (IDE 46)](PBP-IDE-46.md), [Deficit IGR (IDE 47)](PBP-IDE-47.md)


## 5. REGLES METIER

9 regles identifiees:

### Autres (9 regles)

#### <a id="rm-RM-001"></a>[RM-001] Traitement si P.Lieu sejour [C] est renseigne

| Element | Detail |
|---------|--------|
| **Condition** | `P.Lieu sejour [C]<>'' AND [AI]<>0` |
| **Si vrai** | [AI] |
| **Si faux** | V Existe Correctif [U]) |
| **Variables** | C (P.Lieu sejour), U (V Existe Correctif) |
| **Expression source** | Expression 39 : `IF(P.Lieu sejour [C]<>'' AND [AI]<>0,[AI],V Existe Correctif` |
| **Exemple** | Si P.Lieu sejour [C]<>'' AND [AI]<>0 â†’ [AI]. Sinon â†’ V Existe Correctif [U]) |

#### <a id="rm-RM-002"></a>[RM-002] Traitement si P.Lieu sejour [C] est renseigne

| Element | Detail |
|---------|--------|
| **Condition** | `P.Lieu sejour [C]<>'' AND [AJ]<>0` |
| **Si vrai** | [AJ] |
| **Si faux** | v Budget GM Arrivés [V]) |
| **Variables** | C (P.Lieu sejour), V (v Budget GM Arrivés) |
| **Expression source** | Expression 40 : `IF(P.Lieu sejour [C]<>'' AND [AJ]<>0,[AJ],v Budget GM Arrivé` |
| **Exemple** | Si P.Lieu sejour [C]<>'' AND [AJ]<>0 â†’ [AJ]. Sinon â†’ v Budget GM Arrivés [V]) |

#### <a id="rm-RM-003"></a>[RM-003] Traitement si P.Lieu sejour [C] est renseigne

| Element | Detail |
|---------|--------|
| **Condition** | `P.Lieu sejour [C]<>'' AND [AK]<>0` |
| **Si vrai** | [AK] |
| **Si faux** | v Budget GM Transporté... [W]) |
| **Variables** | C (P.Lieu sejour) |
| **Expression source** | Expression 41 : `IF(P.Lieu sejour [C]<>'' AND [AK]<>0,[AK],v Budget GM Transp` |
| **Exemple** | Si P.Lieu sejour [C]<>'' AND [AK]<>0 â†’ [AK]. Sinon â†’ v Budget GM Transporté... [W]) |

#### <a id="rm-RM-004"></a>[RM-004] Traitement si P.Lieu sejour [C] est renseigne

| Element | Detail |
|---------|--------|
| **Condition** | `P.Lieu sejour [C]<>'' AND [AL]<>0` |
| **Si vrai** | [AL] |
| **Si faux** | v Buget GM V/V [X]) |
| **Variables** | C (P.Lieu sejour), X (v Buget GM V/V) |
| **Expression source** | Expression 43 : `IF(P.Lieu sejour [C]<>'' AND [AL]<>0,[AL],v Buget GM V/V [X]` |
| **Exemple** | Si P.Lieu sejour [C]<>'' AND [AL]<>0 â†’ [AL]. Sinon â†’ v Buget GM V/V [X]) |

#### <a id="rm-RM-005"></a>[RM-005] Traitement si P.Lieu sejour [C] est renseigne

| Element | Detail |
|---------|--------|
| **Condition** | `P.Lieu sejour [C]<>'' AND [AM]<>0` |
| **Si vrai** | [AM] |
| **Si faux** | v Budget GM V/V Trans.... [Y]) |
| **Variables** | C (P.Lieu sejour) |
| **Expression source** | Expression 44 : `IF(P.Lieu sejour [C]<>'' AND [AM]<>0,[AM],v Budget GM V/V Tr` |
| **Exemple** | Si P.Lieu sejour [C]<>'' AND [AM]<>0 â†’ [AM]. Sinon â†’ v Budget GM V/V Trans.... [Y]) |

#### <a id="rm-RM-006"></a>[RM-006] Traitement si P.Lieu sejour [C] est renseigne

| Element | Detail |
|---------|--------|
| **Condition** | `P.Lieu sejour [C]<>'' AND [AN]<>0` |
| **Si vrai** | [AN] |
| **Si faux** | v Budget GM V/V Trans.... [Z]) |
| **Variables** | C (P.Lieu sejour) |
| **Expression source** | Expression 45 : `IF(P.Lieu sejour [C]<>'' AND [AN]<>0,[AN],v Budget GM V/V Tr` |
| **Exemple** | Si P.Lieu sejour [C]<>'' AND [AN]<>0 â†’ [AN]. Sinon â†’ v Budget GM V/V Trans.... [Z]) |

#### <a id="rm-RM-007"></a>[RM-007] Traitement si P.Lieu sejour [C] est renseigne

| Element | Detail |
|---------|--------|
| **Condition** | `P.Lieu sejour [C]<>'' AND [AO]<>0` |
| **Si vrai** | [AO] |
| **Si faux** | [AA]) |
| **Variables** | C (P.Lieu sejour) |
| **Expression source** | Expression 46 : `IF(P.Lieu sejour [C]<>'' AND [AO]<>0,[AO],[AA])` |
| **Exemple** | Si P.Lieu sejour [C]<>'' AND [AO]<>0 â†’ [AO]. Sinon â†’ [AA]) |

#### <a id="rm-RM-008"></a>[RM-008] Traitement si P.Lieu sejour [C] est renseigne

| Element | Detail |
|---------|--------|
| **Condition** | `P.Lieu sejour [C]<>'' AND [AQ]<>0` |
| **Si vrai** | [AQ] |
| **Si faux** | [AC]) |
| **Variables** | C (P.Lieu sejour) |
| **Expression source** | Expression 47 : `IF(P.Lieu sejour [C]<>'' AND [AQ]<>0,[AQ],[AC])` |
| **Exemple** | Si P.Lieu sejour [C]<>'' AND [AQ]<>0 â†’ [AQ]. Sinon â†’ [AC]) |

#### <a id="rm-RM-009"></a>[RM-009] Traitement si P.Lieu sejour [C] est renseigne

| Element | Detail |
|---------|--------|
| **Condition** | `P.Lieu sejour [C]<>'' AND [AR]<>0` |
| **Si vrai** | [AR] |
| **Si faux** | [AD]) |
| **Variables** | C (P.Lieu sejour) |
| **Expression source** | Expression 48 : `IF(P.Lieu sejour [C]<>'' AND [AR]<>0,[AR],[AD])` |
| **Exemple** | Si P.Lieu sejour [C]<>'' AND [AR]<>0 â†’ [AR]. Sinon â†’ [AD]) |

## 6. CONTEXTE

- **Appele par**: (aucun)
- **Appelle**: 7 programmes | **Tables**: 9 (W:0 R:3 L:7) | **Taches**: 10 | **Expressions**: 48

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (10 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **413.1** | [**Edition effectif mensuel** (413)](#t1) | - | - | Impression |
| 413.1.1 | [Edition effectif mensuel (413.1)](#t2) [mockup](#ecran-t2) | - | 302x71 | |
| **413.2** | [**Calcul capacite** (413.1.1)](#t3) | - | - | Calcul |
| **413.3** | [**Cumul Plafond Lit** (413.1.1.1)](#t4) [mockup](#ecran-t4) | - | 488x0 | Traitement |
| 413.3.1 | [Cumul Lit Table Import (413.1.1.2)](#t5) | - | - | |
| 413.3.2 | [Cumul GM tranférés HP/SP (413.1.2)](#t6) [mockup](#ecran-t6) | - | 681x0 | |
| 413.3.3 | [Execute SQL command (413.1.3)](#t7) [mockup](#ecran-t7) | - | 120x195 | |
| 413.3.4 | [Execute SQL command (413.1.4)](#t8) [mockup](#ecran-t8) | - | 120x195 | |
| 413.3.5 | [Execute SQL command (413.1.5)](#t9) [mockup](#ecran-t9) | - | 120x195 | |
| 413.3.6 | [Pilotage Gestion de Crise (413.2)](#t10) | MDI | - | |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Traitement principal]
    DECISION{P.Lieu sejour}
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

### Tables utilisees (9)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 69 | initialisation___ini |  | DB | R |   |   | 1 |
| 81 | societe__________soc |  | DB |   |   | L | 1 |
| 118 | tables_imports |  | DB | R |   | L | 5 |
| 120 | tables_qualites__qua |  | DB |   |   | L | 1 |
| 372 | pv_budget |  | DB |   |   | L | 1 |
| 473 | comptage_caisse | Sessions de caisse | TMP | R |   |   | 1 |
| 824 | fac_pied_tva_pro |  | DB |   |   | L | 1 |
| 834 | tpe_par_terminal |  | DB |   |   | L | 1 |
| 851 | correspittivi |  | DB |   |   | L | 2 |

### Colonnes par table (4 / 3 tables avec colonnes identifiees)

<details>
<summary>Table 69 - initialisation___ini (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P.Appel de gestion crise | R | Logical |
| B | P.Date de fin | R | Date |
| C | P.Lieu sejour | R | Alpha |
| D | P.Premier lieu sejour | R | Alpha |
| E | P.Nom lieu | R | Alpha |
| F | P Lieu de Sejour Saisie ? | R | Logical |
| G | V.Date debut | R | Date |
| H | V.Date fin | R | Date |
| I | V.Code village | R | Alpha |
| J | V.Cumul sur 1er mois | R | Logical |
| K | V.Cumul sur dernier mois | R | Logical |
| L | V.Date debut ete | R | Date |
| M | V.Date fin ete | R | Date |
| N | V.Date debut hiver | R | Date |
| O | V.Date fin hiver | R | Date |
| P | V.Saison | R | Alpha |
| Q | budget_total_jhp | R | Numeric |
| R | budget_total_jh_vrl | R | Numeric |
| S | budget_total_jhd | R | Numeric |
| T | V.Existe qualite GM PRES ? | R | Logical |
| U | V Existe Correctif | R | Logical |
| V | v Budget GM Arrivés | R | Numeric |
| W | v Budget GM Transportés Package | R | Numeric |
| X | v Buget GM V/V | R | Numeric |
| Y | v Budget GM V/V Trans. A HP | R | Numeric |
| Z | v Budget GM V/V Trans. R HP | R | Numeric |
| BA | v Budget GM V/V Trans. A SP | R | Numeric |
| BB | v Budget GM V/V Trans. R SP | R | Numeric |
| BC | v Budget GM V/V Trans. A+R | R | Numeric |

</details>

<details>
<summary>Table 118 - tables_imports (R/L) - 5 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | V.Avc JHP | R | Numeric |
| B | V.Avc JHD | R | Numeric |
| C | V.Cumul JHP | R | Numeric |
| D | V.Cumul JH economat | R | Numeric |
| E | GM ORDI M1 | R | Numeric |
| F | GM ORDI M2 | R | Numeric |
| G | GM ORDI M3 | R | Numeric |
| H | GM ORDI M4 | R | Numeric |
| I | GM ORDI M5 | R | Numeric |
| J | GM ORDI M6 | R | Numeric |
| K | GM PROP M1 | R | Numeric |
| L | GM PROP M2 | R | Numeric |
| M | GM PROP M3 | R | Numeric |
| N | GM PROP M4 | R | Numeric |
| O | GM PROP M5 | R | Numeric |
| P | GM PROP M6 | R | Numeric |
| Q | GM CLUB M1 | R | Numeric |
| R | GM CLUB M2 | R | Numeric |
| S | GM CLUB M3 | R | Numeric |
| T | GM CLUB M4 | R | Numeric |
| U | GM CLUB M5 | R | Numeric |
| V | GM CLUB M6 | R | Numeric |
| W | GM SEM M1 | R | Numeric |
| X | GM SEM M2 | R | Numeric |
| Y | GM SEM M3 | R | Numeric |
| Z | GM SEM M4 | R | Numeric |
| BA | GM SEM M5 | R | Numeric |
| BB | GM SEM M6 | R | Numeric |
| BC | GM VSL M1 | R | Numeric |
| BD | GM VSL M2 | R | Numeric |
| BE | GM VSL M3 | R | Numeric |
| BF | GM VSL M4 | R | Numeric |
| BG | GM VSL M5 | R | Numeric |
| BH | GM VSL M6 | R | Numeric |
| BI | GM VRL SP M1 | R | Numeric |
| BJ | GM VRL SP M2 | R | Numeric |
| BK | GM VRL SP M3 | R | Numeric |
| BL | GM VRL SP M4 | R | Numeric |
| BM | GM VRL SP M5 | R | Numeric |
| BN | GM VRL SP M6 | R | Numeric |
| BO | GM VRL HP M1 | R | Numeric |
| BP | GM VRL HP M2 | R | Numeric |
| BQ | GM VRL HP M3 | R | Numeric |
| BR | GM VRL HP M4 | R | Numeric |
| BS | GM VRL HP M5 | R | Numeric |
| BT | GM VRL HP M6 | R | Numeric |
| BU | JHD GE M1 | R | Numeric |
| BV | JHD GE M2 | R | Numeric |
| BW | JHD GE M3 | R | Numeric |
| BX | JHD GE M4 | R | Numeric |
| BY | JHD GE M5 | R | Numeric |
| BZ | JHD GE M6 | R | Numeric |
| CA | JHD GO M1 | R | Numeric |
| CB | JHD GO M2 | R | Numeric |
| CC | JHD GO M3 | R | Numeric |
| CD | JHD GO M4 | R | Numeric |
| CE | JHD GO M5 | R | Numeric |
| CF | JHD GO M6 | R | Numeric |
| CG | JHD GM AV DEJ M1 | R | Numeric |
| CH | JHD GM AV DEJ M2 | R | Numeric |
| CI | JHD GM AV DEJ M3 | R | Numeric |
| CJ | JHD GM AV DEJ M4 | R | Numeric |
| CK | JHD GM AV DEJ M5 | R | Numeric |
| CL | JHD GM AV DEJ M6 | R | Numeric |
| CM | JHD IGR ech M1 | R | Numeric |
| CN | JHD IGR ech M2 | R | Numeric |
| CO | JHD IGR ech M3 | R | Numeric |
| CP | JHD IGR ech M4 | R | Numeric |
| CQ | JHD IGR ech M5 | R | Numeric |
| CR | JHD IGR ech M6 | R | Numeric |
| CS | JHD EXC M1 | R | Numeric |
| CT | JHD EXC M2 | R | Numeric |
| CU | JHD EXC M3 | R | Numeric |
| CV | JHD EXC M4 | R | Numeric |
| CW | JHD EXC M5 | R | Numeric |
| CX | JHD EXC M6 | R | Numeric |
| CY | JHD IGR M1 | R | Numeric |
| CZ | JHD IGR M2 | R | Numeric |
| DA | JHD IGR M3 | R | Numeric |
| DB | JHD IGR M4 | R | Numeric |
| DC | JHD IGR M5 | R | Numeric |
| DD | JHD IGR M6 | R | Numeric |
| DE | JHD IGP M1 | R | Numeric |
| DF | JHD IGP M2 | R | Numeric |
| DG | JHD IGP M3 | R | Numeric |
| DH | JHD IGP M4 | R | Numeric |
| DI | JHD IGP M5 | R | Numeric |
| DJ | JHD IGP M6 | R | Numeric |
| DK | JHD BUR M1 | R | Numeric |
| DL | JHD BUR M2 | R | Numeric |
| DM | JHD BUR M3 | R | Numeric |
| DN | JHD BUR M4 | R | Numeric |
| DO | JHD BUR M5 | R | Numeric |
| DP | JHD BUR M6 | R | Numeric |
| DQ | JHD FOUR M1 | R | Numeric |
| DR | JHD FOUR M2 | R | Numeric |
| DS | JHD FOUR M3 | R | Numeric |
| DT | JHD FOUR M4 | R | Numeric |
| DU | JHD FOUR M5 | R | Numeric |
| DV | JHD FOUR M6 | R | Numeric |
| DW | JHD FOUR VSHIP M1 | R | Numeric |
| DX | JHD FOUR VSHIP M2 | R | Numeric |
| DY | JHD FOUR VSHIP M3 | R | Numeric |
| DZ | JHD FOUR VSHIP M4 | R | Numeric |
| EA | JHD FOUR VSHIP M5 | R | Numeric |
| EB | JHD FOUR VSHIP M6 | R | Numeric |
| EC | JHD GO MISS M1 | R | Numeric |
| ED | JHD GO MISS M2 | R | Numeric |
| EE | JHD GO MISS M3 | R | Numeric |
| EF | JHD GO MISS M4 | R | Numeric |
| EG | JHD GO MISS M5 | R | Numeric |
| EH | JHD GO MISS M6 | R | Numeric |
| EI | JHD GO ART M1 | R | Numeric |
| EJ | JHD GO ART M2 | R | Numeric |
| EK | JHD GO ART M3 | R | Numeric |
| EL | JHD GO ART M4 | R | Numeric |
| EM | JHD GO ART M5 | R | Numeric |
| EN | JHD GO ART M6 | R | Numeric |
| EO | JHD GO EDUC M1 | R | Numeric |
| EP | JHD GO EDUC M2 | R | Numeric |
| EQ | JHD GO EDUC M3 | R | Numeric |
| ER | JHD GO EDUC M4 | R | Numeric |
| ES | JHD GO EDUC M5 | R | Numeric |
| ET | JHD GO EDUC M6 | R | Numeric |
| EU | JHD GO MED M1 | R | Numeric |
| EV | JHD GO MED M2 | R | Numeric |
| EW | JHD GO MED M3 | R | Numeric |
| EX | JHD GO MED M4 | R | Numeric |
| EY | JHD GO MED M5 | R | Numeric |
| EZ | JHD GO MED M6 | R | Numeric |
| FA | JHD GO STA M1 | R | Numeric |
| FB | JHD GO STA M2 | R | Numeric |
| FC | JHD GO STA M3 | R | Numeric |
| FD | JHD GO STA M4 | R | Numeric |
| FE | JHD GO STA M5 | R | Numeric |
| FF | JHD GO STA M6 | R | Numeric |
| FG | JHD GO ANS M1 | R | Numeric |
| FH | JHD GO ANS M2 | R | Numeric |
| FI | JHD GO ANS M3 | R | Numeric |
| FJ | JHD GO ANS M4 | R | Numeric |
| FK | JHD GO ANS M5 | R | Numeric |
| FL | JHD GO ANS M6 | R | Numeric |
| FM | JHD GO PRES SEJ M1 | R | Numeric |
| FN | JHD GO PRES SEJ M2 | R | Numeric |
| FO | JHD GO PRES SEJ M3 | R | Numeric |
| FP | JHD GO PRES SEJ M4 | R | Numeric |
| FQ | JHD GO PRES SEJ M5 | R | Numeric |
| FR | JHD GO PRES SEJ M6 | R | Numeric |
| FS | JHD GO PRES REP M1 | R | Numeric |
| FT | JHD GO PRES REP M2 | R | Numeric |
| FU | JHD GO PRES REP M3 | R | Numeric |
| FV | JHD GO PRES REP M4 | R | Numeric |
| FW | JHD GO PRES REP M5 | R | Numeric |
| FX | JHD GO PRES REP M6 | R | Numeric |
| FY | Total JH hors place M1 | R | Numeric |
| FZ | Total JH hors place M2 | R | Numeric |
| GA | Total JH hors place M3 | R | Numeric |
| GB | Total JH hors place M4 | R | Numeric |
| GC | Total JH hors place M5 | R | Numeric |
| GD | Total JH hors place M6 | R | Numeric |
| GE | Total JHP M1 | R | Numeric |
| GF | Total JHP M2 | R | Numeric |
| GG | Total JHP M3 | R | Numeric |
| GH | Total JHP M4 | R | Numeric |
| GI | Total JHP M5 | R | Numeric |
| GJ | Total JHP M6 | R | Numeric |
| GK | Total JH VRL M1 | R | Numeric |
| GL | Total JH VRL M2 | R | Numeric |
| GM | Total JH VRL M3 | R | Numeric |
| GN | Total JH VRL M4 | R | Numeric |
| GO | Total JH VRL M5 | R | Numeric |
| GP | Total JH VRL M6 | R | Numeric |
| GQ | Total JH DEF M1 | R | Numeric |
| GR | Total JH DEF M2 | R | Numeric |
| GS | Total JH DEF M3 | R | Numeric |
| GT | Total JH DEF M4 | R | Numeric |
| GU | Total JH DEF M5 | R | Numeric |
| GV | Total JH DEF M6 | R | Numeric |
| GW | Total JH eco M1 | R | Numeric |
| GX | Total JH eco M2 | R | Numeric |
| GY | Total JH eco M3 | R | Numeric |
| GZ | Total JH eco M4 | R | Numeric |
| HA | Total JH eco M5 | R | Numeric |
| HB | Total JH eco M6 | R | Numeric |
| HC | V.AnneeMois | R | Alpha |
| HD | V.Num mois | R | Numeric |
| HE | V.Nom M1 | R | Alpha |
| HF | V.Nom M2 | R | Alpha |
| HG | V.Nom M3 | R | Alpha |
| HH | V.Nom M4 | R | Alpha |
| HI | V.Nom M5 | R | Alpha |
| HJ | V.Nom M6 | R | Alpha |
| HK | V.Nb jours d'exploitation budge | R | Numeric |
| HL | V.Nb jour M1 | R | Numeric |
| HM | V.Nb jour M2 | R | Numeric |
| HN | V.Nb jour M3 | R | Numeric |
| HO | V.Nb jour M4 | R | Numeric |
| HP | V.Nb jour M5 | R | Numeric |
| HQ | V.Nb jour M6 | R | Numeric |
| HR | V.Nb passe | R | Numeric |
| HS | V.Chaine mois | R | Alpha |
| HT | V.A cheval sur 2 saison | R | Logical |
| HU | V.Dernier mois ete | R | Numeric |
| HV | V.Dernier mois hiver | R | Numeric |
| HW | V.Capacite M1 | R | Numeric |
| HX | V.Capacite M2 | R | Numeric |
| HY | V.Capacite M3 | R | Numeric |
| HZ | V.Capacite M4 | R | Numeric |
| IA | V.Capacite M5 | R | Numeric |
| IB | V.Capacite M6 | R | Numeric |
| IC | V.Capacite Totale | R | Numeric |
| ID | V.Capacite budget | R | Numeric |
| IE | V lien Nb/Lit Lieu | R | Logical |
| IF | v GM Arrivés M1 | R | Numeric |
| IG | v GMTranspPackage M1 | R | Numeric |
| IH | v GM VV M1 | R | Numeric |
| II | v GM V/V Trans A HP M1 | R | Numeric |
| IJ | v GM V/V Trans R HP M1 | R | Numeric |
| IK | v GM V/V Trans A SP M1 | R | Numeric |
| IL | v GM V/V Trans R SP M1 | R | Numeric |
| IM | v GM V/V Trans T  A+R M1 | R | Numeric |
| IN | v GM Arrivés M2 | R | Numeric |
| IO | v GMTranspPackage M2 | R | Numeric |
| IP | v GM VV M2 | R | Numeric |
| IQ | v GM V/V Trans A HP M2 | R | Numeric |
| IR | v GM V/V Trans R HP M2 | R | Numeric |
| IS | v GM V/V Trans A SP M2 | R | Numeric |
| IT | v GM V/V Trans R SP M2 | R | Numeric |
| IU | v GM V/V Trans T  A+R M2 | R | Numeric |
| IV | v GM Arrivés M3 | R | Numeric |
| IW | v GMTranspPackage M3 | R | Numeric |
| IX | v GM VV M3 | R | Numeric |
| IY | v GM V/V Trans A HP M3 | R | Numeric |
| IZ | v GM V/V Trans R HP M3 | R | Numeric |
| JA | v GM V/V Trans A SP M3 | R | Numeric |
| JB | v GM V/V Trans R SP M3 | R | Numeric |
| JC | v GM V/V Trans T  A+R M3 | R | Numeric |
| JD | v GM Arrivés M4 | R | Numeric |
| JE | v GMTranspPackage M4 | R | Numeric |
| JF | v GM VV M4 | R | Numeric |
| JG | v GM V/V Trans A HP M4 | R | Numeric |
| JH | v GM V/V Trans R HP M4 | R | Numeric |
| JI | v GM V/V Trans A SP M4 | R | Numeric |
| JJ | v GM V/V Trans R SP M4 | R | Numeric |
| JK | v GM V/V Trans T  A+R M4 | R | Numeric |
| JL | v GM Arrivés M5 | R | Numeric |
| JM | v GMTranspPackage M5 | R | Numeric |
| JN | v GM VV M5 | R | Numeric |
| JO | v GM V/V Trans A HP M5 | R | Numeric |
| JP | v GM V/V Trans R HP M5 | R | Numeric |
| JQ | v GM V/V Trans A SP M5 | R | Numeric |
| JR | v GM V/V Trans R SP M5 | R | Numeric |
| JS | v GM V/V Trans T  A+R M5 | R | Numeric |
| JT | v GM Arrivés M6 | R | Numeric |
| JU | v GMTranspPackage M6 | R | Numeric |
| JV | v GM VV M6 | R | Numeric |
| JW | v GM V/V Trans A HP M6 | R | Numeric |
| JX | v GM V/V Trans R HP M6 | R | Numeric |
| JY | v GM V/V Trans A SP M6 | R | Numeric |
| JZ | v GM V/V Trans R SP M6 | R | Numeric |
| KA | v GM V/V Trans T  A+R M6 | R | Numeric |
| KB | v Cumul Gm Arrivés | R | Numeric |
| KC | v Cumul Gm Transportés / Packag | R | Numeric |
| KD | v Cumul GM V/V | R | Numeric |
| KE | v Cumul GM V/V A HP | R | Numeric |
| KF | v Cumul GM V/V R HP | R | Numeric |
| KG | v Cumul GM V/V A SP | R | Numeric |
| KH | v Cumul GM V/V R SP | R | Numeric |
| KI | v Cumul GM V/V A+R Total | R | Numeric |
| KJ | v Reel/Budget Gm Arrivés | R | Numeric |
| KK | v Reel/Budget Gm Trans/Package | R | Numeric |
| KL | v Reel/Budget Gm V/V | R | Numeric |
| KM | v Reel/Budget Gm Trans A HP | R | Numeric |
| KN | v Reel/Budget Gm Trans R HP | R | Numeric |
| KO | v Reel/Budget Gm Trans A SP | R | Numeric |
| KP | v Reel/Budget Gm Trans R SP | R | Numeric |
| KQ | v Reel/Budget Gm Tran A+R | R | Numeric |

</details>

<details>
<summary>Table 473 - comptage_caisse (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P.GM V/V Trans. A HP | R | Numeric |
| B | P.GM V/V Trans. R HP | R | Numeric |
| C | P.GM V/V Trans. A SP | R | Numeric |
| D | P.GM V/V Trans. R SP | R | Numeric |
| E | P.GM V/V Trans. Total | R | Numeric |
| F | v.lien effectif_personne | R | Logical |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (6)

Variables recues en parametre.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P.Appel de gestion crise | Logical | [413.2](#t10) |
| B | P.Date de fin | Date | - |
| C | P.Lieu sejour | Alpha | 28x parametre entrant |
| D | P.Premier lieu sejour | Alpha | - |
| E | P.Nom lieu | Alpha | - |
| F | P Lieu de Sejour Saisie ? | Logical | 1x parametre entrant |

### 11.2 Variables de session (113)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| G | V.Date debut | Date | - |
| H | V.Date fin | Date | 3x session |
| I | V.Code village | Alpha | - |
| J | V.Cumul sur 1er mois | Logical | - |
| K | V.Cumul sur dernier mois | Logical | - |
| L | V.Date debut ete | Date | - |
| M | V.Date fin ete | Date | - |
| N | V.Date debut hiver | Date | - |
| O | V.Date fin hiver | Date | - |
| P | V.Saison | Alpha | - |
| T | V.Existe qualite GM PRES ? | Logical | - |
| U | V Existe Correctif | Logical | 1x session |
| V | v Budget GM Arrivés | Numeric | 1x session |
| W | v Budget GM Transportés Package | Numeric | - |
| X | v Buget GM V/V | Numeric | 1x session |
| Y | v Budget GM V/V Trans. A HP | Numeric | - |
| Z | v Budget GM V/V Trans. R HP | Numeric | - |
| BA | v Budget GM V/V Trans. A SP | Numeric | - |
| BB | v Budget GM V/V Trans. R SP | Numeric | - |
| BC | v Budget GM V/V Trans. A+R | Numeric | - |
| HC | V.AnneeMois | Alpha | - |
| HD | V.Num mois | Numeric | - |
| HE | V.Nom M1 | Alpha | - |
| HF | V.Nom M2 | Alpha | - |
| HG | V.Nom M3 | Alpha | - |
| HH | V.Nom M4 | Alpha | - |
| HI | V.Nom M5 | Alpha | - |
| HJ | V.Nom M6 | Alpha | - |
| HK | V.Nb jours d'exploitation budge | Numeric | - |
| HL | V.Nb jour M1 | Numeric | - |
| HM | V.Nb jour M2 | Numeric | - |
| HN | V.Nb jour M3 | Numeric | - |
| HO | V.Nb jour M4 | Numeric | - |
| HP | V.Nb jour M5 | Numeric | - |
| HQ | V.Nb jour M6 | Numeric | - |
| HR | V.Nb passe | Numeric | - |
| HS | V.Chaine mois | Alpha | - |
| HT | V.A cheval sur 2 saison | Logical | - |
| HU | V.Dernier mois ete | Numeric | - |
| HV | V.Dernier mois hiver | Numeric | - |
| HW | V.Capacite M1 | Numeric | - |
| HX | V.Capacite M2 | Numeric | - |
| HY | V.Capacite M3 | Numeric | - |
| HZ | V.Capacite M4 | Numeric | - |
| IA | V.Capacite M5 | Numeric | - |
| IB | V.Capacite M6 | Numeric | - |
| IC | V.Capacite Totale | Numeric | - |
| ID | V.Capacite budget | Numeric | - |
| IE | V lien Nb/Lit Lieu | Logical | - |
| IF | v GM Arrivés M1 | Numeric | - |
| IG | v GMTranspPackage M1 | Numeric | - |
| IH | v GM VV M1 | Numeric | - |
| II | v GM V/V Trans A HP M1 | Numeric | - |
| IJ | v GM V/V Trans R HP M1 | Numeric | - |
| IK | v GM V/V Trans A SP M1 | Numeric | - |
| IL | v GM V/V Trans R SP M1 | Numeric | - |
| IM | v GM V/V Trans T  A+R M1 | Numeric | - |
| IN | v GM Arrivés M2 | Numeric | - |
| IO | v GMTranspPackage M2 | Numeric | - |
| IP | v GM VV M2 | Numeric | - |
| IQ | v GM V/V Trans A HP M2 | Numeric | - |
| IR | v GM V/V Trans R HP M2 | Numeric | - |
| IS | v GM V/V Trans A SP M2 | Numeric | - |
| IT | v GM V/V Trans R SP M2 | Numeric | - |
| IU | v GM V/V Trans T  A+R M2 | Numeric | - |
| IV | v GM Arrivés M3 | Numeric | - |
| IW | v GMTranspPackage M3 | Numeric | - |
| IX | v GM VV M3 | Numeric | - |
| IY | v GM V/V Trans A HP M3 | Numeric | - |
| IZ | v GM V/V Trans R HP M3 | Numeric | - |
| JA | v GM V/V Trans A SP M3 | Numeric | - |
| JB | v GM V/V Trans R SP M3 | Numeric | - |
| JC | v GM V/V Trans T  A+R M3 | Numeric | - |
| JD | v GM Arrivés M4 | Numeric | - |
| JE | v GMTranspPackage M4 | Numeric | - |
| JF | v GM VV M4 | Numeric | - |
| JG | v GM V/V Trans A HP M4 | Numeric | - |
| JH | v GM V/V Trans R HP M4 | Numeric | - |
| JI | v GM V/V Trans A SP M4 | Numeric | - |
| JJ | v GM V/V Trans R SP M4 | Numeric | - |
| JK | v GM V/V Trans T  A+R M4 | Numeric | - |
| JL | v GM Arrivés M5 | Numeric | - |
| JM | v GMTranspPackage M5 | Numeric | - |
| JN | v GM VV M5 | Numeric | - |
| JO | v GM V/V Trans A HP M5 | Numeric | - |
| JP | v GM V/V Trans R HP M5 | Numeric | - |
| JQ | v GM V/V Trans A SP M5 | Numeric | - |
| JR | v GM V/V Trans R SP M5 | Numeric | - |
| JS | v GM V/V Trans T  A+R M5 | Numeric | - |
| JT | v GM Arrivés M6 | Numeric | - |
| JU | v GMTranspPackage M6 | Numeric | - |
| JV | v GM VV M6 | Numeric | - |
| JW | v GM V/V Trans A HP M6 | Numeric | - |
| JX | v GM V/V Trans R HP M6 | Numeric | - |
| JY | v GM V/V Trans A SP M6 | Numeric | - |
| JZ | v GM V/V Trans R SP M6 | Numeric | - |
| KA | v GM V/V Trans T  A+R M6 | Numeric | - |
| KB | v Cumul Gm Arrivés | Numeric | - |
| KC | v Cumul Gm Transportés / Packag | Numeric | - |
| KD | v Cumul GM V/V | Numeric | - |
| KE | v Cumul GM V/V A HP | Numeric | - |
| KF | v Cumul GM V/V R HP | Numeric | - |
| KG | v Cumul GM V/V A SP | Numeric | - |
| KH | v Cumul GM V/V R SP | Numeric | - |
| KI | v Cumul GM V/V A+R Total | Numeric | - |
| KJ | v Reel/Budget Gm Arrivés | Numeric | - |
| KK | v Reel/Budget Gm Trans/Package | Numeric | - |
| KL | v Reel/Budget Gm V/V | Numeric | - |
| KM | v Reel/Budget Gm Trans A HP | Numeric | - |
| KN | v Reel/Budget Gm Trans R HP | Numeric | - |
| KO | v Reel/Budget Gm Trans A SP | Numeric | - |
| KP | v Reel/Budget Gm Trans R SP | Numeric | - |
| KQ | v Reel/Budget Gm Tran A+R | Numeric | - |

### 11.3 Autres (158)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| Q | budget_total_jhp | Numeric | - |
| R | budget_total_jh_vrl | Numeric | - |
| S | budget_total_jhd | Numeric | - |
| BD | GM VSL M2 | Numeric | - |
| BE | GM VSL M3 | Numeric | - |
| BF | GM VSL M4 | Numeric | - |
| BG | GM VSL M5 | Numeric | 1x refs |
| BH | GM VSL M6 | Numeric | 1x refs |
| BI | GM VRL SP M1 | Numeric | 1x refs |
| BJ | GM VRL SP M2 | Numeric | 1x refs |
| BK | GM VRL SP M3 | Numeric | - |
| BL | GM VRL SP M4 | Numeric | - |
| BM | GM VRL SP M5 | Numeric | - |
| BN | GM VRL SP M6 | Numeric | - |
| BO | GM VRL HP M1 | Numeric | - |
| BP | GM VRL HP M2 | Numeric | - |
| BQ | GM VRL HP M3 | Numeric | - |
| BR | GM VRL HP M4 | Numeric | - |
| BS | GM VRL HP M5 | Numeric | - |
| BT | GM VRL HP M6 | Numeric | - |
| BU | JHD GE M1 | Numeric | - |
| BV | JHD GE M2 | Numeric | - |
| BW | JHD GE M3 | Numeric | - |
| BX | JHD GE M4 | Numeric | - |
| BY | JHD GE M5 | Numeric | - |
| BZ | JHD GE M6 | Numeric | - |
| CA | JHD GO M1 | Numeric | - |
| CB | JHD GO M2 | Numeric | - |
| CC | JHD GO M3 | Numeric | - |
| CD | JHD GO M4 | Numeric | - |
| CE | JHD GO M5 | Numeric | - |
| CF | JHD GO M6 | Numeric | - |
| CG | JHD GM AV DEJ M1 | Numeric | - |
| CH | JHD GM AV DEJ M2 | Numeric | - |
| CI | JHD GM AV DEJ M3 | Numeric | - |
| CJ | JHD GM AV DEJ M4 | Numeric | - |
| CK | JHD GM AV DEJ M5 | Numeric | - |
| CL | JHD GM AV DEJ M6 | Numeric | - |
| CM | JHD IGR ech M1 | Numeric | - |
| CN | JHD IGR ech M2 | Numeric | - |
| CO | JHD IGR ech M3 | Numeric | - |
| CP | JHD IGR ech M4 | Numeric | - |
| CQ | JHD IGR ech M5 | Numeric | - |
| CR | JHD IGR ech M6 | Numeric | - |
| CS | JHD EXC M1 | Numeric | - |
| CT | JHD EXC M2 | Numeric | - |
| CU | JHD EXC M3 | Numeric | - |
| CV | JHD EXC M4 | Numeric | - |
| CW | JHD EXC M5 | Numeric | - |
| CX | JHD EXC M6 | Numeric | - |
| CY | JHD IGR M1 | Numeric | - |
| CZ | JHD IGR M2 | Numeric | - |
| DA | JHD IGR M3 | Numeric | - |
| DB | JHD IGR M4 | Numeric | - |
| DC | JHD IGR M5 | Numeric | - |
| DD | JHD IGR M6 | Numeric | - |
| DE | JHD IGP M1 | Numeric | - |
| DF | JHD IGP M2 | Numeric | - |
| DG | JHD IGP M3 | Numeric | - |
| DH | JHD IGP M4 | Numeric | - |
| DI | JHD IGP M5 | Numeric | - |
| DJ | JHD IGP M6 | Numeric | - |
| DK | JHD BUR M1 | Numeric | - |
| DL | JHD BUR M2 | Numeric | - |
| DM | JHD BUR M3 | Numeric | - |
| DN | JHD BUR M4 | Numeric | - |
| DO | JHD BUR M5 | Numeric | - |
| DP | JHD BUR M6 | Numeric | - |
| DQ | JHD FOUR M1 | Numeric | - |
| DR | JHD FOUR M2 | Numeric | - |
| DS | JHD FOUR M3 | Numeric | - |
| DT | JHD FOUR M4 | Numeric | - |
| DU | JHD FOUR M5 | Numeric | - |
| DV | JHD FOUR M6 | Numeric | - |
| DW | JHD FOUR VSHIP M1 | Numeric | - |
| DX | JHD FOUR VSHIP M2 | Numeric | - |
| DY | JHD FOUR VSHIP M3 | Numeric | - |
| DZ | JHD FOUR VSHIP M4 | Numeric | - |
| EA | JHD FOUR VSHIP M5 | Numeric | - |
| EB | JHD FOUR VSHIP M6 | Numeric | - |
| EC | JHD GO MISS M1 | Numeric | - |
| ED | JHD GO MISS M2 | Numeric | - |
| EE | JHD GO MISS M3 | Numeric | - |
| EF | JHD GO MISS M4 | Numeric | - |
| EG | JHD GO MISS M5 | Numeric | - |
| EH | JHD GO MISS M6 | Numeric | - |
| EI | JHD GO ART M1 | Numeric | - |
| EJ | JHD GO ART M2 | Numeric | - |
| EK | JHD GO ART M3 | Numeric | - |
| EL | JHD GO ART M4 | Numeric | - |
| EM | JHD GO ART M5 | Numeric | - |
| EN | JHD GO ART M6 | Numeric | - |
| EO | JHD GO EDUC M1 | Numeric | - |
| EP | JHD GO EDUC M2 | Numeric | - |
| EQ | JHD GO EDUC M3 | Numeric | - |
| ER | JHD GO EDUC M4 | Numeric | - |
| ES | JHD GO EDUC M5 | Numeric | - |
| ET | JHD GO EDUC M6 | Numeric | - |
| EU | JHD GO MED M1 | Numeric | - |
| EV | JHD GO MED M2 | Numeric | - |
| EW | JHD GO MED M3 | Numeric | - |
| EX | JHD GO MED M4 | Numeric | - |
| EY | JHD GO MED M5 | Numeric | - |
| EZ | JHD GO MED M6 | Numeric | - |
| FA | JHD GO STA M1 | Numeric | - |
| FB | JHD GO STA M2 | Numeric | - |
| FC | JHD GO STA M3 | Numeric | - |
| FD | JHD GO STA M4 | Numeric | - |
| FE | JHD GO STA M5 | Numeric | - |
| FF | JHD GO STA M6 | Numeric | - |
| FG | JHD GO ANS M1 | Numeric | - |
| FH | JHD GO ANS M2 | Numeric | - |
| FI | JHD GO ANS M3 | Numeric | - |
| FJ | JHD GO ANS M4 | Numeric | - |
| FK | JHD GO ANS M5 | Numeric | - |
| FL | JHD GO ANS M6 | Numeric | - |
| FM | JHD GO PRES SEJ M1 | Numeric | - |
| FN | JHD GO PRES SEJ M2 | Numeric | - |
| FO | JHD GO PRES SEJ M3 | Numeric | - |
| FP | JHD GO PRES SEJ M4 | Numeric | - |
| FQ | JHD GO PRES SEJ M5 | Numeric | - |
| FR | JHD GO PRES SEJ M6 | Numeric | - |
| FS | JHD GO PRES REP M1 | Numeric | - |
| FT | JHD GO PRES REP M2 | Numeric | - |
| FU | JHD GO PRES REP M3 | Numeric | - |
| FV | JHD GO PRES REP M4 | Numeric | - |
| FW | JHD GO PRES REP M5 | Numeric | - |
| FX | JHD GO PRES REP M6 | Numeric | - |
| FY | Total JH hors place M1 | Numeric | - |
| FZ | Total JH hors place M2 | Numeric | - |
| GA | Total JH hors place M3 | Numeric | - |
| GB | Total JH hors place M4 | Numeric | - |
| GC | Total JH hors place M5 | Numeric | - |
| GD | Total JH hors place M6 | Numeric | - |
| GE | Total JHP M1 | Numeric | - |
| GF | Total JHP M2 | Numeric | - |
| GG | Total JHP M3 | Numeric | - |
| GH | Total JHP M4 | Numeric | - |
| GI | Total JHP M5 | Numeric | - |
| GJ | Total JHP M6 | Numeric | - |
| GK | Total JH VRL M1 | Numeric | - |
| GL | Total JH VRL M2 | Numeric | - |
| GM | Total JH VRL M3 | Numeric | - |
| GN | Total JH VRL M4 | Numeric | - |
| GO | Total JH VRL M5 | Numeric | - |
| GP | Total JH VRL M6 | Numeric | - |
| GQ | Total JH DEF M1 | Numeric | - |
| GR | Total JH DEF M2 | Numeric | - |
| GS | Total JH DEF M3 | Numeric | - |
| GT | Total JH DEF M4 | Numeric | - |
| GU | Total JH DEF M5 | Numeric | - |
| GV | Total JH DEF M6 | Numeric | - |
| GW | Total JH eco M1 | Numeric | - |
| GX | Total JH eco M2 | Numeric | - |
| GY | Total JH eco M3 | Numeric | - |
| GZ | Total JH eco M4 | Numeric | - |
| HA | Total JH eco M5 | Numeric | - |
| HB | Total JH eco M6 | Numeric | - |

<details>
<summary>Toutes les 277 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| P0 | **A** | P.Appel de gestion crise | Logical |
| P0 | **B** | P.Date de fin | Date |
| P0 | **C** | P.Lieu sejour | Alpha |
| P0 | **D** | P.Premier lieu sejour | Alpha |
| P0 | **E** | P.Nom lieu | Alpha |
| P0 | **F** | P Lieu de Sejour Saisie ? | Logical |
| V. | **G** | V.Date debut | Date |
| V. | **H** | V.Date fin | Date |
| V. | **I** | V.Code village | Alpha |
| V. | **J** | V.Cumul sur 1er mois | Logical |
| V. | **K** | V.Cumul sur dernier mois | Logical |
| V. | **L** | V.Date debut ete | Date |
| V. | **M** | V.Date fin ete | Date |
| V. | **N** | V.Date debut hiver | Date |
| V. | **O** | V.Date fin hiver | Date |
| V. | **P** | V.Saison | Alpha |
| V. | **T** | V.Existe qualite GM PRES ? | Logical |
| V. | **U** | V Existe Correctif | Logical |
| V. | **V** | v Budget GM Arrivés | Numeric |
| V. | **W** | v Budget GM Transportés Package | Numeric |
| V. | **X** | v Buget GM V/V | Numeric |
| V. | **Y** | v Budget GM V/V Trans. A HP | Numeric |
| V. | **Z** | v Budget GM V/V Trans. R HP | Numeric |
| V. | **BA** | v Budget GM V/V Trans. A SP | Numeric |
| V. | **BB** | v Budget GM V/V Trans. R SP | Numeric |
| V. | **BC** | v Budget GM V/V Trans. A+R | Numeric |
| V. | **HC** | V.AnneeMois | Alpha |
| V. | **HD** | V.Num mois | Numeric |
| V. | **HE** | V.Nom M1 | Alpha |
| V. | **HF** | V.Nom M2 | Alpha |
| V. | **HG** | V.Nom M3 | Alpha |
| V. | **HH** | V.Nom M4 | Alpha |
| V. | **HI** | V.Nom M5 | Alpha |
| V. | **HJ** | V.Nom M6 | Alpha |
| V. | **HK** | V.Nb jours d'exploitation budge | Numeric |
| V. | **HL** | V.Nb jour M1 | Numeric |
| V. | **HM** | V.Nb jour M2 | Numeric |
| V. | **HN** | V.Nb jour M3 | Numeric |
| V. | **HO** | V.Nb jour M4 | Numeric |
| V. | **HP** | V.Nb jour M5 | Numeric |
| V. | **HQ** | V.Nb jour M6 | Numeric |
| V. | **HR** | V.Nb passe | Numeric |
| V. | **HS** | V.Chaine mois | Alpha |
| V. | **HT** | V.A cheval sur 2 saison | Logical |
| V. | **HU** | V.Dernier mois ete | Numeric |
| V. | **HV** | V.Dernier mois hiver | Numeric |
| V. | **HW** | V.Capacite M1 | Numeric |
| V. | **HX** | V.Capacite M2 | Numeric |
| V. | **HY** | V.Capacite M3 | Numeric |
| V. | **HZ** | V.Capacite M4 | Numeric |
| V. | **IA** | V.Capacite M5 | Numeric |
| V. | **IB** | V.Capacite M6 | Numeric |
| V. | **IC** | V.Capacite Totale | Numeric |
| V. | **ID** | V.Capacite budget | Numeric |
| V. | **IE** | V lien Nb/Lit Lieu | Logical |
| V. | **IF** | v GM Arrivés M1 | Numeric |
| V. | **IG** | v GMTranspPackage M1 | Numeric |
| V. | **IH** | v GM VV M1 | Numeric |
| V. | **II** | v GM V/V Trans A HP M1 | Numeric |
| V. | **IJ** | v GM V/V Trans R HP M1 | Numeric |
| V. | **IK** | v GM V/V Trans A SP M1 | Numeric |
| V. | **IL** | v GM V/V Trans R SP M1 | Numeric |
| V. | **IM** | v GM V/V Trans T  A+R M1 | Numeric |
| V. | **IN** | v GM Arrivés M2 | Numeric |
| V. | **IO** | v GMTranspPackage M2 | Numeric |
| V. | **IP** | v GM VV M2 | Numeric |
| V. | **IQ** | v GM V/V Trans A HP M2 | Numeric |
| V. | **IR** | v GM V/V Trans R HP M2 | Numeric |
| V. | **IS** | v GM V/V Trans A SP M2 | Numeric |
| V. | **IT** | v GM V/V Trans R SP M2 | Numeric |
| V. | **IU** | v GM V/V Trans T  A+R M2 | Numeric |
| V. | **IV** | v GM Arrivés M3 | Numeric |
| V. | **IW** | v GMTranspPackage M3 | Numeric |
| V. | **IX** | v GM VV M3 | Numeric |
| V. | **IY** | v GM V/V Trans A HP M3 | Numeric |
| V. | **IZ** | v GM V/V Trans R HP M3 | Numeric |
| V. | **JA** | v GM V/V Trans A SP M3 | Numeric |
| V. | **JB** | v GM V/V Trans R SP M3 | Numeric |
| V. | **JC** | v GM V/V Trans T  A+R M3 | Numeric |
| V. | **JD** | v GM Arrivés M4 | Numeric |
| V. | **JE** | v GMTranspPackage M4 | Numeric |
| V. | **JF** | v GM VV M4 | Numeric |
| V. | **JG** | v GM V/V Trans A HP M4 | Numeric |
| V. | **JH** | v GM V/V Trans R HP M4 | Numeric |
| V. | **JI** | v GM V/V Trans A SP M4 | Numeric |
| V. | **JJ** | v GM V/V Trans R SP M4 | Numeric |
| V. | **JK** | v GM V/V Trans T  A+R M4 | Numeric |
| V. | **JL** | v GM Arrivés M5 | Numeric |
| V. | **JM** | v GMTranspPackage M5 | Numeric |
| V. | **JN** | v GM VV M5 | Numeric |
| V. | **JO** | v GM V/V Trans A HP M5 | Numeric |
| V. | **JP** | v GM V/V Trans R HP M5 | Numeric |
| V. | **JQ** | v GM V/V Trans A SP M5 | Numeric |
| V. | **JR** | v GM V/V Trans R SP M5 | Numeric |
| V. | **JS** | v GM V/V Trans T  A+R M5 | Numeric |
| V. | **JT** | v GM Arrivés M6 | Numeric |
| V. | **JU** | v GMTranspPackage M6 | Numeric |
| V. | **JV** | v GM VV M6 | Numeric |
| V. | **JW** | v GM V/V Trans A HP M6 | Numeric |
| V. | **JX** | v GM V/V Trans R HP M6 | Numeric |
| V. | **JY** | v GM V/V Trans A SP M6 | Numeric |
| V. | **JZ** | v GM V/V Trans R SP M6 | Numeric |
| V. | **KA** | v GM V/V Trans T  A+R M6 | Numeric |
| V. | **KB** | v Cumul Gm Arrivés | Numeric |
| V. | **KC** | v Cumul Gm Transportés / Packag | Numeric |
| V. | **KD** | v Cumul GM V/V | Numeric |
| V. | **KE** | v Cumul GM V/V A HP | Numeric |
| V. | **KF** | v Cumul GM V/V R HP | Numeric |
| V. | **KG** | v Cumul GM V/V A SP | Numeric |
| V. | **KH** | v Cumul GM V/V R SP | Numeric |
| V. | **KI** | v Cumul GM V/V A+R Total | Numeric |
| V. | **KJ** | v Reel/Budget Gm Arrivés | Numeric |
| V. | **KK** | v Reel/Budget Gm Trans/Package | Numeric |
| V. | **KL** | v Reel/Budget Gm V/V | Numeric |
| V. | **KM** | v Reel/Budget Gm Trans A HP | Numeric |
| V. | **KN** | v Reel/Budget Gm Trans R HP | Numeric |
| V. | **KO** | v Reel/Budget Gm Trans A SP | Numeric |
| V. | **KP** | v Reel/Budget Gm Trans R SP | Numeric |
| V. | **KQ** | v Reel/Budget Gm Tran A+R | Numeric |
| Autre | **Q** | budget_total_jhp | Numeric |
| Autre | **R** | budget_total_jh_vrl | Numeric |
| Autre | **S** | budget_total_jhd | Numeric |
| Autre | **BD** | GM VSL M2 | Numeric |
| Autre | **BE** | GM VSL M3 | Numeric |
| Autre | **BF** | GM VSL M4 | Numeric |
| Autre | **BG** | GM VSL M5 | Numeric |
| Autre | **BH** | GM VSL M6 | Numeric |
| Autre | **BI** | GM VRL SP M1 | Numeric |
| Autre | **BJ** | GM VRL SP M2 | Numeric |
| Autre | **BK** | GM VRL SP M3 | Numeric |
| Autre | **BL** | GM VRL SP M4 | Numeric |
| Autre | **BM** | GM VRL SP M5 | Numeric |
| Autre | **BN** | GM VRL SP M6 | Numeric |
| Autre | **BO** | GM VRL HP M1 | Numeric |
| Autre | **BP** | GM VRL HP M2 | Numeric |
| Autre | **BQ** | GM VRL HP M3 | Numeric |
| Autre | **BR** | GM VRL HP M4 | Numeric |
| Autre | **BS** | GM VRL HP M5 | Numeric |
| Autre | **BT** | GM VRL HP M6 | Numeric |
| Autre | **BU** | JHD GE M1 | Numeric |
| Autre | **BV** | JHD GE M2 | Numeric |
| Autre | **BW** | JHD GE M3 | Numeric |
| Autre | **BX** | JHD GE M4 | Numeric |
| Autre | **BY** | JHD GE M5 | Numeric |
| Autre | **BZ** | JHD GE M6 | Numeric |
| Autre | **CA** | JHD GO M1 | Numeric |
| Autre | **CB** | JHD GO M2 | Numeric |
| Autre | **CC** | JHD GO M3 | Numeric |
| Autre | **CD** | JHD GO M4 | Numeric |
| Autre | **CE** | JHD GO M5 | Numeric |
| Autre | **CF** | JHD GO M6 | Numeric |
| Autre | **CG** | JHD GM AV DEJ M1 | Numeric |
| Autre | **CH** | JHD GM AV DEJ M2 | Numeric |
| Autre | **CI** | JHD GM AV DEJ M3 | Numeric |
| Autre | **CJ** | JHD GM AV DEJ M4 | Numeric |
| Autre | **CK** | JHD GM AV DEJ M5 | Numeric |
| Autre | **CL** | JHD GM AV DEJ M6 | Numeric |
| Autre | **CM** | JHD IGR ech M1 | Numeric |
| Autre | **CN** | JHD IGR ech M2 | Numeric |
| Autre | **CO** | JHD IGR ech M3 | Numeric |
| Autre | **CP** | JHD IGR ech M4 | Numeric |
| Autre | **CQ** | JHD IGR ech M5 | Numeric |
| Autre | **CR** | JHD IGR ech M6 | Numeric |
| Autre | **CS** | JHD EXC M1 | Numeric |
| Autre | **CT** | JHD EXC M2 | Numeric |
| Autre | **CU** | JHD EXC M3 | Numeric |
| Autre | **CV** | JHD EXC M4 | Numeric |
| Autre | **CW** | JHD EXC M5 | Numeric |
| Autre | **CX** | JHD EXC M6 | Numeric |
| Autre | **CY** | JHD IGR M1 | Numeric |
| Autre | **CZ** | JHD IGR M2 | Numeric |
| Autre | **DA** | JHD IGR M3 | Numeric |
| Autre | **DB** | JHD IGR M4 | Numeric |
| Autre | **DC** | JHD IGR M5 | Numeric |
| Autre | **DD** | JHD IGR M6 | Numeric |
| Autre | **DE** | JHD IGP M1 | Numeric |
| Autre | **DF** | JHD IGP M2 | Numeric |
| Autre | **DG** | JHD IGP M3 | Numeric |
| Autre | **DH** | JHD IGP M4 | Numeric |
| Autre | **DI** | JHD IGP M5 | Numeric |
| Autre | **DJ** | JHD IGP M6 | Numeric |
| Autre | **DK** | JHD BUR M1 | Numeric |
| Autre | **DL** | JHD BUR M2 | Numeric |
| Autre | **DM** | JHD BUR M3 | Numeric |
| Autre | **DN** | JHD BUR M4 | Numeric |
| Autre | **DO** | JHD BUR M5 | Numeric |
| Autre | **DP** | JHD BUR M6 | Numeric |
| Autre | **DQ** | JHD FOUR M1 | Numeric |
| Autre | **DR** | JHD FOUR M2 | Numeric |
| Autre | **DS** | JHD FOUR M3 | Numeric |
| Autre | **DT** | JHD FOUR M4 | Numeric |
| Autre | **DU** | JHD FOUR M5 | Numeric |
| Autre | **DV** | JHD FOUR M6 | Numeric |
| Autre | **DW** | JHD FOUR VSHIP M1 | Numeric |
| Autre | **DX** | JHD FOUR VSHIP M2 | Numeric |
| Autre | **DY** | JHD FOUR VSHIP M3 | Numeric |
| Autre | **DZ** | JHD FOUR VSHIP M4 | Numeric |
| Autre | **EA** | JHD FOUR VSHIP M5 | Numeric |
| Autre | **EB** | JHD FOUR VSHIP M6 | Numeric |
| Autre | **EC** | JHD GO MISS M1 | Numeric |
| Autre | **ED** | JHD GO MISS M2 | Numeric |
| Autre | **EE** | JHD GO MISS M3 | Numeric |
| Autre | **EF** | JHD GO MISS M4 | Numeric |
| Autre | **EG** | JHD GO MISS M5 | Numeric |
| Autre | **EH** | JHD GO MISS M6 | Numeric |
| Autre | **EI** | JHD GO ART M1 | Numeric |
| Autre | **EJ** | JHD GO ART M2 | Numeric |
| Autre | **EK** | JHD GO ART M3 | Numeric |
| Autre | **EL** | JHD GO ART M4 | Numeric |
| Autre | **EM** | JHD GO ART M5 | Numeric |
| Autre | **EN** | JHD GO ART M6 | Numeric |
| Autre | **EO** | JHD GO EDUC M1 | Numeric |
| Autre | **EP** | JHD GO EDUC M2 | Numeric |
| Autre | **EQ** | JHD GO EDUC M3 | Numeric |
| Autre | **ER** | JHD GO EDUC M4 | Numeric |
| Autre | **ES** | JHD GO EDUC M5 | Numeric |
| Autre | **ET** | JHD GO EDUC M6 | Numeric |
| Autre | **EU** | JHD GO MED M1 | Numeric |
| Autre | **EV** | JHD GO MED M2 | Numeric |
| Autre | **EW** | JHD GO MED M3 | Numeric |
| Autre | **EX** | JHD GO MED M4 | Numeric |
| Autre | **EY** | JHD GO MED M5 | Numeric |
| Autre | **EZ** | JHD GO MED M6 | Numeric |
| Autre | **FA** | JHD GO STA M1 | Numeric |
| Autre | **FB** | JHD GO STA M2 | Numeric |
| Autre | **FC** | JHD GO STA M3 | Numeric |
| Autre | **FD** | JHD GO STA M4 | Numeric |
| Autre | **FE** | JHD GO STA M5 | Numeric |
| Autre | **FF** | JHD GO STA M6 | Numeric |
| Autre | **FG** | JHD GO ANS M1 | Numeric |
| Autre | **FH** | JHD GO ANS M2 | Numeric |
| Autre | **FI** | JHD GO ANS M3 | Numeric |
| Autre | **FJ** | JHD GO ANS M4 | Numeric |
| Autre | **FK** | JHD GO ANS M5 | Numeric |
| Autre | **FL** | JHD GO ANS M6 | Numeric |
| Autre | **FM** | JHD GO PRES SEJ M1 | Numeric |
| Autre | **FN** | JHD GO PRES SEJ M2 | Numeric |
| Autre | **FO** | JHD GO PRES SEJ M3 | Numeric |
| Autre | **FP** | JHD GO PRES SEJ M4 | Numeric |
| Autre | **FQ** | JHD GO PRES SEJ M5 | Numeric |
| Autre | **FR** | JHD GO PRES SEJ M6 | Numeric |
| Autre | **FS** | JHD GO PRES REP M1 | Numeric |
| Autre | **FT** | JHD GO PRES REP M2 | Numeric |
| Autre | **FU** | JHD GO PRES REP M3 | Numeric |
| Autre | **FV** | JHD GO PRES REP M4 | Numeric |
| Autre | **FW** | JHD GO PRES REP M5 | Numeric |
| Autre | **FX** | JHD GO PRES REP M6 | Numeric |
| Autre | **FY** | Total JH hors place M1 | Numeric |
| Autre | **FZ** | Total JH hors place M2 | Numeric |
| Autre | **GA** | Total JH hors place M3 | Numeric |
| Autre | **GB** | Total JH hors place M4 | Numeric |
| Autre | **GC** | Total JH hors place M5 | Numeric |
| Autre | **GD** | Total JH hors place M6 | Numeric |
| Autre | **GE** | Total JHP M1 | Numeric |
| Autre | **GF** | Total JHP M2 | Numeric |
| Autre | **GG** | Total JHP M3 | Numeric |
| Autre | **GH** | Total JHP M4 | Numeric |
| Autre | **GI** | Total JHP M5 | Numeric |
| Autre | **GJ** | Total JHP M6 | Numeric |
| Autre | **GK** | Total JH VRL M1 | Numeric |
| Autre | **GL** | Total JH VRL M2 | Numeric |
| Autre | **GM** | Total JH VRL M3 | Numeric |
| Autre | **GN** | Total JH VRL M4 | Numeric |
| Autre | **GO** | Total JH VRL M5 | Numeric |
| Autre | **GP** | Total JH VRL M6 | Numeric |
| Autre | **GQ** | Total JH DEF M1 | Numeric |
| Autre | **GR** | Total JH DEF M2 | Numeric |
| Autre | **GS** | Total JH DEF M3 | Numeric |
| Autre | **GT** | Total JH DEF M4 | Numeric |
| Autre | **GU** | Total JH DEF M5 | Numeric |
| Autre | **GV** | Total JH DEF M6 | Numeric |
| Autre | **GW** | Total JH eco M1 | Numeric |
| Autre | **GX** | Total JH eco M2 | Numeric |
| Autre | **GY** | Total JH eco M3 | Numeric |
| Autre | **GZ** | Total JH eco M4 | Numeric |
| Autre | **HA** | Total JH eco M5 | Numeric |
| Autre | **HB** | Total JH eco M6 | Numeric |

</details>

## 12. EXPRESSIONS

**48 / 48 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCULATION | 1 | 0 |
| CONDITION | 10 | 9 |
| CONSTANTE | 4 | 0 |
| FORMAT | 21 | 0 |
| OTHER | 9 | 0 |
| NEGATION | 1 | 0 |
| REFERENCE_VG | 2 | 0 |

### 12.2 Expressions cles par type

#### CALCULATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 42 | `GM VSL M5 [BG]+GM VSL M6 [BH]+GM VRL SP M1 [BI]+GM VRL SP M2 [BJ]` | - |

#### CONDITION (10 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 46 | `IF(P.Lieu sejour [C]<>'' AND [AO]<>0,[AO],[AA])` | [RM-007](#rm-RM-007) |
| CONDITION | 45 | `IF(P.Lieu sejour [C]<>'' AND [AN]<>0,[AN],v Budget GM V/V Trans.... [Z])` | [RM-006](#rm-RM-006) |
| CONDITION | 48 | `IF(P.Lieu sejour [C]<>'' AND [AR]<>0,[AR],[AD])` | [RM-009](#rm-RM-009) |
| CONDITION | 47 | `IF(P.Lieu sejour [C]<>'' AND [AQ]<>0,[AQ],[AC])` | [RM-008](#rm-RM-008) |
| CONDITION | 44 | `IF(P.Lieu sejour [C]<>'' AND [AM]<>0,[AM],v Budget GM V/V Trans.... [Y])` | [RM-005](#rm-RM-005) |
| ... | | *+5 autres* | |

#### CONSTANTE (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 29 | `'GM'` | - |
| CONSTANTE | 30 | `'PRES'` | - |
| CONSTANTE | 27 | `'ANS'` | - |
| CONSTANTE | 28 | `'MISS'` | - |

#### FORMAT (21 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| FORMAT | 19 | `FileExist(Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_IGR_'&Trim(DStr(Date(),'YYYYMM'))&'.htm')` | - |
| FORMAT | 20 | `FileExist(Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_Rep_Enc_HP_'&Trim(DStr(Date(),'YYYYMM'))&'.htm')` | - |
| FORMAT | 18 | `FileExist(Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_IGP_'&Trim(DStr(Date(),'YYYYMM'))&'.htm')` | - |
| FORMAT | 13 | `Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_VSHIP_'&Trim(DStr(Date(),'YYYYMM'))&'.htm'` | - |
| FORMAT | 14 | `FileExist(Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_effectif_mensuel_'&Trim(DStr(Date(),'YYYYMM'))&'.htm')` | - |
| ... | | *+16 autres* | |

#### OTHER (9 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 33 | `P Lieu de Sejour Saisie ? [F]` | - |
| OTHER | 31 | `[AY]` | - |
| OTHER | 37 | `P.Lieu sejour [C]` | - |
| OTHER | 35 | `v Budget GM V/V Trans.... [BC]` | - |
| OTHER | 25 | `Delay(15)` | - |
| ... | | *+4 autres* | |

#### NEGATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| NEGATION | 26 | `NOT P.Appel de gestion crise [A]` | - |

#### REFERENCE_VG (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 36 | `VG47` | - |
| REFERENCE_VG | 32 | `VG47` | - |

### 12.3 Toutes les expressions (48)

<details>
<summary>Voir les 48 expressions</summary>

#### CALCULATION (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 42 | `GM VSL M5 [BG]+GM VSL M6 [BH]+GM VRL SP M1 [BI]+GM VRL SP M2 [BJ]` |

#### CONDITION (10)

| IDE | Expression Decodee |
|-----|-------------------|
| 39 | `IF(P.Lieu sejour [C]<>'' AND [AI]<>0,[AI],V Existe Correctif [U])` |
| 40 | `IF(P.Lieu sejour [C]<>'' AND [AJ]<>0,[AJ],v Budget GM Arrivés [V])` |
| 41 | `IF(P.Lieu sejour [C]<>'' AND [AK]<>0,[AK],v Budget GM Transporté... [W])` |
| 43 | `IF(P.Lieu sejour [C]<>'' AND [AL]<>0,[AL],v Buget GM V/V [X])` |
| 44 | `IF(P.Lieu sejour [C]<>'' AND [AM]<>0,[AM],v Budget GM V/V Trans.... [Y])` |
| 45 | `IF(P.Lieu sejour [C]<>'' AND [AN]<>0,[AN],v Budget GM V/V Trans.... [Z])` |
| 46 | `IF(P.Lieu sejour [C]<>'' AND [AO]<>0,[AO],[AA])` |
| 47 | `IF(P.Lieu sejour [C]<>'' AND [AQ]<>0,[AQ],[AC])` |
| 48 | `IF(P.Lieu sejour [C]<>'' AND [AR]<>0,[AR],[AD])` |
| 38 | `P.Lieu sejour [C]<>''` |

#### CONSTANTE (4)

| IDE | Expression Decodee |
|-----|-------------------|
| 27 | `'ANS'` |
| 28 | `'MISS'` |
| 29 | `'GM'` |
| 30 | `'PRES'` |

#### FORMAT (21)

| IDE | Expression Decodee |
|-----|-------------------|
| 1 | `DVal('01/05/'&Str(Year(Date()),'4'),'DD/MM/YYYY')` |
| 2 | `DVal('31/10/'&Str(Year(Date()),'4'),'DD/MM/YYYY')` |
| 3 | `DVal('01/11/'&Str(IF(Range(Month(Date()),5,12),Year(Date()),Year(Date())-1),'4'),'DD/MM/YYYY')` |
| 4 | `DVal('30/04/'&Str(IF(Range(Month(Date()),5,12),Year(Date())+1,Year(Date())),'4'),'DD/MM/YYYY')` |
| 6 | `Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_effectif_mensuel_'&Trim(DStr(Date(),'YYYYMM'))&'.htm'` |
| 7 | `Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_IGP_'&Trim(DStr(Date(),'YYYYMM'))&'.htm'` |
| 8 | `Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_IGR_'&Trim(DStr(Date(),'YYYYMM'))&'.htm'` |
| 9 | `Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_Rep_Enc_HP_'&Trim(DStr(Date(),'YYYYMM'))&'.htm'` |
| 10 | `Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_ANS_'&Trim(DStr(Date(),'YYYYMM'))&'.htm'` |
| 11 | `Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_MISS_'&Trim(DStr(Date(),'YYYYMM'))&'.htm'` |
| 12 | `Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_PRES_'&Trim(DStr(Date(),'YYYYMM'))&'.htm'` |
| 13 | `Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_VSHIP_'&Trim(DStr(Date(),'YYYYMM'))&'.htm'` |
| 14 | `FileExist(Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_effectif_mensuel_'&Trim(DStr(Date(),'YYYYMM'))&'.htm')` |
| 18 | `FileExist(Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_IGP_'&Trim(DStr(Date(),'YYYYMM'))&'.htm')` |
| 19 | `FileExist(Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_IGR_'&Trim(DStr(Date(),'YYYYMM'))&'.htm')` |
| 20 | `FileExist(Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_Rep_Enc_HP_'&Trim(DStr(Date(),'YYYYMM'))&'.htm')` |
| 21 | `FileExist(Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_ANS_'&Trim(DStr(Date(),'YYYYMM'))&'.htm')` |
| 22 | `FileExist(Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_MISS_'&Trim(DStr(Date(),'YYYYMM'))&'.htm')` |
| 23 | `FileExist(Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_PRES_'&Trim(DStr(Date(),'YYYYMM'))&'.htm')` |
| 24 | `FileExist(Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_VSHIP_'&Trim(DStr(Date(),'YYYYMM'))&'.htm')` |
| 34 | `'c:\temp\'&Trim(VG33)&'_'&IF(Trim(P.Lieu sejour [C])<>'',Trim(P.Lieu sejour [C])&'_','')&'EFF_Correctifs_'&Trim(DStr(Date(),'YYYYMM'))&'.htm'` |

#### OTHER (9)

| IDE | Expression Decodee |
|-----|-------------------|
| 5 | `GetParam('SOCIETE')` |
| 15 | `BOM(V.Date fin [H])` |
| 16 | `EOM(V.Date fin [H])` |
| 17 | `V.Date fin [H]` |
| 25 | `Delay(15)` |
| 31 | `[AY]` |
| 33 | `P Lieu de Sejour Saisie ? [F]` |
| 35 | `v Budget GM V/V Trans.... [BC]` |
| 37 | `P.Lieu sejour [C]` |

#### NEGATION (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 26 | `NOT P.Appel de gestion crise [A]` |

#### REFERENCE_VG (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 32 | `VG47` |
| 36 | `VG47` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

**Chemin**: (pas de callers directs)

```mermaid
graph LR
    T413[413 Edition effectif m...]
    style T413 fill:#58a6ff
    NONE[Aucun caller]
    NONE -.-> T413
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| - | (aucun) | - |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T413[413 Edition effectif m...]
    style T413 fill:#58a6ff
    C49[49 Deficit ANSMISSARTI...]
    T413 --> C49
    style C49 fill:#3fb950
    C46[46 Deficit IGP]
    T413 --> C46
    style C46 fill:#3fb950
    C47[47 Deficit IGR]
    T413 --> C47
    style C47 fill:#3fb950
    C48[48 Deficit CMB]
    T413 --> C48
    style C48 fill:#3fb950
    C51[51 Deficit PRES]
    T413 --> C51
    style C51 fill:#3fb950
    C52[52 Deficit CM2]
    T413 --> C52
    style C52 fill:#3fb950
    C62[62 Edition corrections...]
    T413 --> C62
    style C62 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [49](PBP-IDE-49.md) | Deficit ANS/MISS/ARTI/DOCT | 2 | Sous-programme |
| [46](PBP-IDE-46.md) | Deficit IGP | 1 | Sous-programme |
| [47](PBP-IDE-47.md) | Deficit IGR | 1 | Sous-programme |
| [48](PBP-IDE-48.md) | Deficit CMB | 1 | Sous-programme |
| [51](PBP-IDE-51.md) | Deficit PRES | 1 | Sous-programme |
| [52](PBP-IDE-52.md) | Deficit CM2 | 1 | Sous-programme |
| [62](PBP-IDE-62.md) | Edition corrections effectif | 1 | Impression ticket/document |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 935 | Programme volumineux |
| Expressions | 48 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 7 | Dependances moderees |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0.7% (7 / 935) | Code sain |
| Regles metier | 9 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Impression (2 taches: 1 ecran, 1 traitement)

- **Strategie** : Templates HTML -> PDF via wkhtmltopdf ou Puppeteer.
- `PrintService` injectable avec choix imprimante

#### Calcul (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Services de calcul purs (Domain Services).
- Migrer la logique de calcul (stock, compteurs, montants)

#### Traitement (7 taches: 5 ecrans, 2 traitements)

- **Strategie** : Orchestrateur avec 5 ecrans (Razor/React) et 2 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 7 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| [Deficit ANS/MISS/ARTI/DOCT (IDE 49)](PBP-IDE-49.md) | Sous-programme | 2x | Haute - Sous-programme |
| [Deficit PRES (IDE 51)](PBP-IDE-51.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Deficit CM2 (IDE 52)](PBP-IDE-52.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Edition corrections effectif (IDE 62)](PBP-IDE-62.md) | Sous-programme | 1x | Normale - Impression ticket/document |
| [Deficit IGP (IDE 46)](PBP-IDE-46.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Deficit IGR (IDE 47)](PBP-IDE-47.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Deficit CMB (IDE 48)](PBP-IDE-48.md) | Sous-programme | 1x | Normale - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 16:55*
