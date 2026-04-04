# PBP IDE 66 - Edition effectif mensuel V3

> **Analyse**: Phases 1-4 2026-02-03 09:05 -> 09:05 (22s) | Assemblage 09:05
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBP |
| IDE Position | 66 |
| Nom Programme | Edition effectif mensuel V3 |
| Fichier source | `Prg_66.xml` |
| Domaine metier | Impression |
| Taches | 10 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 20 |

## 2. DESCRIPTION FONCTIONNELLE

**Edition effectif mensuel V3** assure la gestion complete de ce processus, accessible depuis [Edition et envoi effectif (IDE 64)](PBP-IDE-64.md), [Effectif mensuel lancement (IDE 54)](PBP-IDE-54.md).

Le flux de traitement s'organise en **3 blocs fonctionnels** :

- **Traitement** (7 taches) : traitements metier divers
- **Impression** (2 taches) : generation de tickets et documents
- **Calcul** (1 tache) : calculs de montants, stocks ou compteurs

**Logique metier** : 15 regles identifiees couvrant conditions metier.

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Impression (2 taches)

- **66** - Edition effectif mensuel V3
- **66.1** - Edition effectif mensuel **[[ECRAN]](#ecran-t2)**

Delegue a : [Edition effectif calcul dates (IDE 57)](PBP-IDE-57.md), [Edition corrections effectifV3 (IDE 67)](PBP-IDE-67.md)

#### Phase 2 : Calcul (1 tache)

- **66.1.1** - Calcul capacite

#### Phase 3 : Traitement (7 taches)

- **66.1.1.1** - Cumul Plafond Lit **[[ECRAN]](#ecran-t4)**
- **66.1.1.2** - Cumul Lit Table Import
- **66.1.2** - Cumul GM tranférés HP/SP **[[ECRAN]](#ecran-t6)**
- **66.1.3** - Execute SQL command **[[ECRAN]](#ecran-t7)**
- **66.1.4** - Execute SQL command **[[ECRAN]](#ecran-t8)**
- **66.1.5** - Execute SQL command **[[ECRAN]](#ecran-t9)**
- **66.2** - Pilotage Gestion de Crise

Delegue a : [Deficit GE sejour et repas V3 (IDE 68)](PBP-IDE-68.md), [Deficit GO sejour et repas V3 (IDE 69)](PBP-IDE-69.md), [Deficit IGP Hors CDV V3 (IDE 70)](PBP-IDE-70.md), [Deficit IGP CDV Sej V3 (IDE 71)](PBP-IDE-71.md), [Deficit IGP Global CDV V3 (IDE 72)](PBP-IDE-72.md), [Deficit GM echange Repas V3 (IDE 73)](PBP-IDE-73.md), [Deficit Excursions RepasV3? (IDE 74)](PBP-IDE-74.md), [Deficit IGR V3 (IDE 75)](PBP-IDE-75.md), [Deficit CMB V3 (IDE 76)](PBP-IDE-76.md), [Deficit ANS V3 (IDE 77)](PBP-IDE-77.md), [Deficit Fournisseurs V3 (IDE 78)](PBP-IDE-78.md), [Deficit VSHIP repasV3 (IDE 79)](PBP-IDE-79.md), [Deficit MISS V3 (IDE 80)](PBP-IDE-80.md), [Deficit Artiste V3 (IDE 81)](PBP-IDE-81.md), [Deficit Educteur V3 (IDE 82)](PBP-IDE-82.md), [Deficit Medecin V3 (IDE 83)](PBP-IDE-83.md), [Deficit Stagiaire V3 (IDE 84)](PBP-IDE-84.md), [Deficit PRES sejour V3 (IDE 85)](PBP-IDE-85.md)

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Impression (2 taches)

Generation des documents et tickets.

---

#### <a id="t1"></a>66 - Edition effectif mensuel V3

**Role** : Generation du document : Edition effectif mensuel V3.
**Delegue a** : [Edition effectif calcul dates (IDE 57)](PBP-IDE-57.md), [Edition corrections effectifV3 (IDE 67)](PBP-IDE-67.md)

---

#### <a id="t2"></a>66.1 - Edition effectif mensuel [[ECRAN]](#ecran-t2)

**Role** : Generation du document : Edition effectif mensuel.
**Ecran** : 317 x 60 DLU | [Voir mockup](#ecran-t2)
**Delegue a** : [Edition effectif calcul dates (IDE 57)](PBP-IDE-57.md), [Edition corrections effectifV3 (IDE 67)](PBP-IDE-67.md)


### 3.2 Calcul (1 tache)

Calculs metier : montants, stocks, compteurs.

---

#### <a id="t3"></a>66.1.1 - Calcul capacite

**Role** : Calcul : Calcul capacite.
**Variables liees** : HW (V.Capacite M1), HX (V.Capacite M2), HY (V.Capacite M3), HZ (V.Capacite M4), IA (V.Capacite M5)


### 3.3 Traitement (7 taches)

Traitements internes.

---

#### <a id="t4"></a>66.1.1.1 - Cumul Plafond Lit [[ECRAN]](#ecran-t4)

**Role** : Traitement : Cumul Plafond Lit.
**Ecran** : 488 x 0 DLU | [Voir mockup](#ecran-t4)
**Variables liees** : L (V.Cumul sur 1er mois), M (V.Cumul sur dernier mois), KB (v Cumul Gm Arrivés), KC (v Cumul Gm Transportés / Packag), KD (v Cumul GM V/V)
**Delegue a** : [Deficit GE sejour et repas V3 (IDE 68)](PBP-IDE-68.md), [Deficit GO sejour et repas V3 (IDE 69)](PBP-IDE-69.md), [Deficit IGP Hors CDV V3 (IDE 70)](PBP-IDE-70.md)

---

#### <a id="t5"></a>66.1.1.2 - Cumul Lit Table Import

**Role** : Traitement : Cumul Lit Table Import.
**Variables liees** : L (V.Cumul sur 1er mois), M (V.Cumul sur dernier mois), KB (v Cumul Gm Arrivés), KC (v Cumul Gm Transportés / Packag), KD (v Cumul GM V/V)
**Delegue a** : [Deficit GE sejour et repas V3 (IDE 68)](PBP-IDE-68.md), [Deficit GO sejour et repas V3 (IDE 69)](PBP-IDE-69.md), [Deficit IGP Hors CDV V3 (IDE 70)](PBP-IDE-70.md)

---

#### <a id="t6"></a>66.1.2 - Cumul GM tranférés HP/SP [[ECRAN]](#ecran-t6)

**Role** : Traitement : Cumul GM tranférés HP/SP.
**Ecran** : 681 x 0 DLU | [Voir mockup](#ecran-t6)
**Variables liees** : L (V.Cumul sur 1er mois), M (V.Cumul sur dernier mois), KB (v Cumul Gm Arrivés), KC (v Cumul Gm Transportés / Packag), KD (v Cumul GM V/V)
**Delegue a** : [Deficit GE sejour et repas V3 (IDE 68)](PBP-IDE-68.md), [Deficit GO sejour et repas V3 (IDE 69)](PBP-IDE-69.md), [Deficit IGP Hors CDV V3 (IDE 70)](PBP-IDE-70.md)

---

#### <a id="t7"></a>66.1.3 - Execute SQL command [[ECRAN]](#ecran-t7)

**Role** : Traitement : Execute SQL command.
**Ecran** : 120 x 195 DLU | [Voir mockup](#ecran-t7)
**Delegue a** : [Deficit GE sejour et repas V3 (IDE 68)](PBP-IDE-68.md), [Deficit GO sejour et repas V3 (IDE 69)](PBP-IDE-69.md), [Deficit IGP Hors CDV V3 (IDE 70)](PBP-IDE-70.md)

---

#### <a id="t8"></a>66.1.4 - Execute SQL command [[ECRAN]](#ecran-t8)

**Role** : Traitement : Execute SQL command.
**Ecran** : 120 x 195 DLU | [Voir mockup](#ecran-t8)
**Delegue a** : [Deficit GE sejour et repas V3 (IDE 68)](PBP-IDE-68.md), [Deficit GO sejour et repas V3 (IDE 69)](PBP-IDE-69.md), [Deficit IGP Hors CDV V3 (IDE 70)](PBP-IDE-70.md)

---

#### <a id="t9"></a>66.1.5 - Execute SQL command [[ECRAN]](#ecran-t9)

**Role** : Traitement : Execute SQL command.
**Ecran** : 120 x 195 DLU | [Voir mockup](#ecran-t9)
**Delegue a** : [Deficit GE sejour et repas V3 (IDE 68)](PBP-IDE-68.md), [Deficit GO sejour et repas V3 (IDE 69)](PBP-IDE-69.md), [Deficit IGP Hors CDV V3 (IDE 70)](PBP-IDE-70.md)

---

#### <a id="t10"></a>66.2 - Pilotage Gestion de Crise

**Role** : Gestion du moyen de paiement : Pilotage Gestion de Crise.
**Variables liees** : A (P.Appel de gestion crise)
**Delegue a** : [Deficit GE sejour et repas V3 (IDE 68)](PBP-IDE-68.md), [Deficit GO sejour et repas V3 (IDE 69)](PBP-IDE-69.md), [Deficit IGP Hors CDV V3 (IDE 70)](PBP-IDE-70.md)


## 5. REGLES METIER

15 regles identifiees:

### Autres (15 regles)

#### <a id="rm-RM-001"></a>[RM-001] Traitement si P.Lieu sejour [C] est renseigne

| Element | Detail |
|---------|--------|
| **Condition** | `P.Lieu sejour [C]<>'' AND [AI]<>0` |
| **Si vrai** | [AI] |
| **Si faux** | V.NbrJoursSemestre1 [U]) |
| **Variables** | C (P.Lieu sejour), U (V.NbrJoursSemestre1) |
| **Expression source** | Expression 70 : `IF(P.Lieu sejour [C]<>'' AND [AI]<>0,[AI],V.NbrJoursSemestre` |
| **Exemple** | Si P.Lieu sejour [C]<>'' AND [AI]<>0 â†’ [AI]. Sinon â†’ V.NbrJoursSemestre1 [U]) |

#### <a id="rm-RM-002"></a>[RM-002] Traitement si P.Lieu sejour [C] est renseigne

| Element | Detail |
|---------|--------|
| **Condition** | `P.Lieu sejour [C]<>'' AND [AJ]<>0` |
| **Si vrai** | [AJ] |
| **Si faux** | V.NbrJoursSaison1 [V]) |
| **Variables** | C (P.Lieu sejour), V (V.NbrJoursSaison1) |
| **Expression source** | Expression 71 : `IF(P.Lieu sejour [C]<>'' AND [AJ]<>0,[AJ],V.NbrJoursSaison1 ` |
| **Exemple** | Si P.Lieu sejour [C]<>'' AND [AJ]<>0 â†’ [AJ]. Sinon â†’ V.NbrJoursSaison1 [V]) |

#### <a id="rm-RM-003"></a>[RM-003] Traitement si P.Lieu sejour [C] est renseigne

| Element | Detail |
|---------|--------|
| **Condition** | `P.Lieu sejour [C]<>'' AND [AK]<>0` |
| **Si vrai** | [AK] |
| **Si faux** | V.NbrJoursSemestre2 [W]) |
| **Variables** | C (P.Lieu sejour), W (V.NbrJoursSemestre2) |
| **Expression source** | Expression 72 : `IF(P.Lieu sejour [C]<>'' AND [AK]<>0,[AK],V.NbrJoursSemestre` |
| **Exemple** | Si P.Lieu sejour [C]<>'' AND [AK]<>0 â†’ [AK]. Sinon â†’ V.NbrJoursSemestre2 [W]) |

#### <a id="rm-RM-004"></a>[RM-004] Traitement si P.Lieu sejour [C] est renseigne

| Element | Detail |
|---------|--------|
| **Condition** | `P.Lieu sejour [C]<>'' AND [AL]<>0` |
| **Si vrai** | [AL] |
| **Si faux** | V.NbrJoursSaison2 [X]) |
| **Variables** | C (P.Lieu sejour), X (V.NbrJoursSaison2) |
| **Expression source** | Expression 74 : `IF(P.Lieu sejour [C]<>'' AND [AL]<>0,[AL],V.NbrJoursSaison2 ` |
| **Exemple** | Si P.Lieu sejour [C]<>'' AND [AL]<>0 â†’ [AL]. Sinon â†’ V.NbrJoursSaison2 [X]) |

#### <a id="rm-RM-005"></a>[RM-005] Traitement si P.Lieu sejour [C] est renseigne

| Element | Detail |
|---------|--------|
| **Condition** | `P.Lieu sejour [C]<>'' AND [AM]<>0` |
| **Si vrai** | [AM] |
| **Si faux** | budget_total_jhp [Y]) |
| **Variables** | C (P.Lieu sejour), Y (budget_total_jhp) |
| **Expression source** | Expression 75 : `IF(P.Lieu sejour [C]<>'' AND [AM]<>0,[AM],budget_total_jhp [` |
| **Exemple** | Si P.Lieu sejour [C]<>'' AND [AM]<>0 â†’ [AM]. Sinon â†’ budget_total_jhp [Y]) |

#### <a id="rm-RM-006"></a>[RM-006] Traitement si P.Lieu sejour [C] est renseigne

| Element | Detail |
|---------|--------|
| **Condition** | `P.Lieu sejour [C]<>'' AND [AN]<>0` |
| **Si vrai** | [AN] |
| **Si faux** | budget_total_jh_vrl [Z]) |
| **Variables** | C (P.Lieu sejour), Z (budget_total_jh_vrl) |
| **Expression source** | Expression 76 : `IF(P.Lieu sejour [C]<>'' AND [AN]<>0,[AN],budget_total_jh_vr` |
| **Exemple** | Si P.Lieu sejour [C]<>'' AND [AN]<>0 â†’ [AN]. Sinon â†’ budget_total_jh_vrl [Z]) |

#### <a id="rm-RM-007"></a>[RM-007] Traitement si P.Lieu sejour [C] est renseigne

| Element | Detail |
|---------|--------|
| **Condition** | `P.Lieu sejour [C]<>'' AND [AO]<>0` |
| **Si vrai** | [AO] |
| **Si faux** | [AA]) |
| **Variables** | C (P.Lieu sejour) |
| **Expression source** | Expression 77 : `IF(P.Lieu sejour [C]<>'' AND [AO]<>0,[AO],[AA])` |
| **Exemple** | Si P.Lieu sejour [C]<>'' AND [AO]<>0 â†’ [AO]. Sinon â†’ [AA]) |

#### <a id="rm-RM-008"></a>[RM-008] Traitement si P.Lieu sejour [C] est renseigne

| Element | Detail |
|---------|--------|
| **Condition** | `P.Lieu sejour [C]<>'' AND [AQ]<>0` |
| **Si vrai** | [AQ] |
| **Si faux** | [AC]) |
| **Variables** | C (P.Lieu sejour) |
| **Expression source** | Expression 78 : `IF(P.Lieu sejour [C]<>'' AND [AQ]<>0,[AQ],[AC])` |
| **Exemple** | Si P.Lieu sejour [C]<>'' AND [AQ]<>0 â†’ [AQ]. Sinon â†’ [AC]) |

#### <a id="rm-RM-009"></a>[RM-009] Traitement si P.Lieu sejour [C] est renseigne

| Element | Detail |
|---------|--------|
| **Condition** | `P.Lieu sejour [C]<>'' AND [AR]<>0` |
| **Si vrai** | [AR] |
| **Si faux** | [AD]) |
| **Variables** | C (P.Lieu sejour) |
| **Expression source** | Expression 79 : `IF(P.Lieu sejour [C]<>'' AND [AR]<>0,[AR],[AD])` |
| **Exemple** | Si P.Lieu sejour [C]<>'' AND [AR]<>0 â†’ [AR]. Sinon â†’ [AD]) |

#### <a id="rm-RM-010"></a>[RM-010] Si v Budget GM V/V Trans.... [BN] alors V.Date-14 [S]-14 sinon P.TypeCalendrier [G])

| Element | Detail |
|---------|--------|
| **Condition** | `v Budget GM V/V Trans.... [BN]` |
| **Si vrai** | V.Date-14 [S]-14 |
| **Si faux** | P.TypeCalendrier [G]) |
| **Variables** | G (P.TypeCalendrier), S (V.Date-14) |
| **Expression source** | Expression 82 : `IF(v Budget GM V/V Trans.... [BN],V.Date-14 [S]-14,P.TypeCal` |
| **Exemple** | Si v Budget GM V/V Trans.... [BN] â†’ V.Date-14 [S]-14. Sinon â†’ P.TypeCalendrier [G]) |

#### <a id="rm-RM-011"></a>[RM-011] Si P.Lieu sejour [C] <> '' AND JHD GE M2 [BV] <> 0 alors JHD GE M2 [BV] sinon GM VRL HP M5 [BS])

| Element | Detail |
|---------|--------|
| **Condition** | `P.Lieu sejour [C] <> '' AND JHD GE M2 [BV] <> 0` |
| **Si vrai** | JHD GE M2 [BV] |
| **Si faux** | GM VRL HP M5 [BS]) |
| **Variables** | C (P.Lieu sejour), BS (GM VRL HP M5), BV (JHD GE M2) |
| **Expression source** | Expression 87 : `IF(P.Lieu sejour [C] <> '' AND JHD GE M2 [BV] <> 0, JHD GE M` |
| **Exemple** | Si P.Lieu sejour [C] <> '' AND JHD GE M2 [BV] <> 0 â†’ JHD GE M2 [BV]. Sinon â†’ GM VRL HP M5 [BS]) |

#### <a id="rm-RM-012"></a>[RM-012] Si P.Lieu sejour [C] <> '' AND JHD GE M3 [BW] <> 0 alors JHD GE M3 [BW] sinon GM VRL HP M6 [BT])

| Element | Detail |
|---------|--------|
| **Condition** | `P.Lieu sejour [C] <> '' AND JHD GE M3 [BW] <> 0` |
| **Si vrai** | JHD GE M3 [BW] |
| **Si faux** | GM VRL HP M6 [BT]) |
| **Variables** | C (P.Lieu sejour), BT (GM VRL HP M6), BW (JHD GE M3) |
| **Expression source** | Expression 88 : `IF(P.Lieu sejour [C] <> '' AND JHD GE M3 [BW] <> 0, JHD GE M` |
| **Exemple** | Si P.Lieu sejour [C] <> '' AND JHD GE M3 [BW] <> 0 â†’ JHD GE M3 [BW]. Sinon â†’ GM VRL HP M6 [BT]) |

#### <a id="rm-RM-013"></a>[RM-013] Si P.Lieu sejour [C] <> '' AND JHD GE M4 [BX] <> 0 alors JHD GE M4 [BX] sinon JHD GE M1 [BU])

| Element | Detail |
|---------|--------|
| **Condition** | `P.Lieu sejour [C] <> '' AND JHD GE M4 [BX] <> 0` |
| **Si vrai** | JHD GE M4 [BX] |
| **Si faux** | JHD GE M1 [BU]) |
| **Variables** | C (P.Lieu sejour), BU (JHD GE M1), BX (JHD GE M4) |
| **Expression source** | Expression 89 : `IF(P.Lieu sejour [C] <> '' AND JHD GE M4 [BX] <> 0, JHD GE M` |
| **Exemple** | Si P.Lieu sejour [C] <> '' AND JHD GE M4 [BX] <> 0 â†’ JHD GE M4 [BX]. Sinon â†’ JHD GE M1 [BU]) |

#### <a id="rm-RM-014"></a>[RM-014] Si Range(Month(P.Date de fin [B]) alors 1 sinon 6),[AS],JHD GE M5 [BY])

| Element | Detail |
|---------|--------|
| **Condition** | `Range(Month(P.Date de fin [B])` |
| **Si vrai** | 1 |
| **Si faux** | 6),[AS],JHD GE M5 [BY]) |
| **Variables** | B (P.Date de fin), BY (JHD GE M5) |
| **Expression source** | Expression 90 : `IF(Range(Month(P.Date de fin [B]),1,6),[AS],JHD GE M5 [BY])` |
| **Exemple** | Si Range(Month(P.Date de fin [B]) â†’ 1. Sinon â†’ 6),[AS],JHD GE M5 [BY]) |

#### <a id="rm-RM-015"></a>[RM-015] Si v Budget GM V/V Trans.... [BM] vaut 'C' alors 'comptable', sinon 'operationnel'

| Element | Detail |
|---------|--------|
| **Condition** | `v Budget GM V/V Trans.... [BM]='C'` |
| **Si vrai** | 'comptable' |
| **Si faux** | 'operationnel') |
| **Expression source** | Expression 98 : `IF(v Budget GM V/V Trans.... [BM]='C','comptable','operation` |
| **Exemple** | Si v Budget GM V/V Trans.... [BM]='C' â†’ 'comptable'. Sinon â†’ 'operationnel') |

## 6. CONTEXTE

- **Appele par**: [Edition et envoi effectif (IDE 64)](PBP-IDE-64.md), [Effectif mensuel lancement (IDE 54)](PBP-IDE-54.md)
- **Appelle**: 20 programmes | **Tables**: 9 (W:0 R:3 L:7) | **Taches**: 10 | **Expressions**: 100

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (10 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **66.1** | [**Edition effectif mensuel V3** (66)](#t1) | - | - | Impression |
| 66.1.1 | [Edition effectif mensuel (66.1)](#t2) [mockup](#ecran-t2) | - | 317x60 | |
| **66.2** | [**Calcul capacite** (66.1.1)](#t3) | - | - | Calcul |
| **66.3** | [**Cumul Plafond Lit** (66.1.1.1)](#t4) [mockup](#ecran-t4) | - | 488x0 | Traitement |
| 66.3.1 | [Cumul Lit Table Import (66.1.1.2)](#t5) | - | - | |
| 66.3.2 | [Cumul GM tranférés HP/SP (66.1.2)](#t6) [mockup](#ecran-t6) | - | 681x0 | |
| 66.3.3 | [Execute SQL command (66.1.3)](#t7) [mockup](#ecran-t7) | - | 120x195 | |
| 66.3.4 | [Execute SQL command (66.1.4)](#t8) [mockup](#ecran-t8) | - | 120x195 | |
| 66.3.5 | [Execute SQL command (66.1.5)](#t9) [mockup](#ecran-t9) | - | 120x195 | |
| 66.3.6 | [Pilotage Gestion de Crise (66.2)](#t10) | MDI | - | |

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
| 834 | tpe_par_terminal |  | DB |   |   | L | 1 |
| 851 | correspittivi |  | DB |   |   | L | 2 |
| 949 | Table_949 |  | MEM |   |   | L | 1 |

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
| G | P.TypeCalendrier | R | Unicode |
| H | P.Reporte? | R | Logical |
| I | V.Date debut | R | Date |
| J | V.Date fin | R | Date |
| K | V.Code village | R | Alpha |
| L | V.Cumul sur 1er mois | R | Logical |
| M | V.Cumul sur dernier mois | R | Logical |
| N | V.Date debut ete | R | Date |
| O | V.Date fin ete | R | Date |
| P | V.Date debut hiver | R | Date |
| Q | V.Date fin hiver | R | Date |
| R | V.Saison | R | Alpha |
| S | V.Date-14 | R | Logical |
| T | V.DateReport | R | Date |
| U | V.NbrJoursSemestre1 | R | Numeric |
| V | V.NbrJoursSaison1 | R | Numeric |
| W | V.NbrJoursSemestre2 | R | Numeric |
| X | V.NbrJoursSaison2 | R | Numeric |
| Y | budget_total_jhp | R | Numeric |
| Z | budget_total_jh_vrl | R | Numeric |
| BA | budget_total_jhd | R | Numeric |
| BB | budget_total_jhp_S2 | R | Numeric |
| BC | budget_total_jh_vrl_S2 | R | Numeric |
| BD | budget_total_jhd_S2 | R | Numeric |
| BE | V.Existe qualite GM PRES ? | R | Logical |
| BF | V Existe Correctif | R | Logical |
| BG | v Budget GM Arrivés | R | Numeric |
| BH | v Budget GM Transportés Package | R | Numeric |
| BI | v Buget GM V/V | R | Numeric |
| BJ | v Budget GM V/V Trans. A HP | R | Numeric |
| BK | v Budget GM V/V Trans. R HP | R | Numeric |
| BL | v Budget GM V/V Trans. A SP | R | Numeric |
| BM | v Budget GM V/V Trans. R SP | R | Numeric |
| BN | v Budget GM V/V Trans. A+R | R | Numeric |
| BO | LibelleTypeCalendrier | R | Alpha |
| BP | V.DateDebutSemestre | R | Date |
| BQ | V.DateFinSemestre | R | Date |

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

### 11.1 Parametres entrants (8)

Variables recues du programme appelant ([Edition et envoi effectif (IDE 64)](PBP-IDE-64.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P.Appel de gestion crise | Logical | [66.2](#t10) |
| B | P.Date de fin | Date | 11x parametre entrant |
| C | P.Lieu sejour | Alpha | 66x parametre entrant |
| D | P.Premier lieu sejour | Alpha | - |
| E | P.Nom lieu | Alpha | - |
| F | P Lieu de Sejour Saisie ? | Logical | 1x parametre entrant |
| G | P.TypeCalendrier | Unicode | 1x parametre entrant |
| H | P.Reporte? | Logical | 3x parametre entrant |

### 11.2 Variables de session (121)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| I | V.Date debut | Date | - |
| J | V.Date fin | Date | - |
| K | V.Code village | Alpha | - |
| L | V.Cumul sur 1er mois | Logical | - |
| M | V.Cumul sur dernier mois | Logical | - |
| N | V.Date debut ete | Date | - |
| O | V.Date fin ete | Date | - |
| P | V.Date debut hiver | Date | - |
| Q | V.Date fin hiver | Date | - |
| R | V.Saison | Alpha | - |
| S | V.Date-14 | Logical | 1x session |
| T | V.DateReport | Date | - |
| U | V.NbrJoursSemestre1 | Numeric | 1x session |
| V | V.NbrJoursSaison1 | Numeric | 1x session |
| W | V.NbrJoursSemestre2 | Numeric | 1x session |
| X | V.NbrJoursSaison2 | Numeric | 1x session |
| BE | V.Existe qualite GM PRES ? | Logical | - |
| BF | V Existe Correctif | Logical | - |
| BG | v Budget GM Arrivés | Numeric | 1x session |
| BH | v Budget GM Transportés Package | Numeric | - |
| BI | v Buget GM V/V | Numeric | 1x session |
| BJ | v Budget GM V/V Trans. A HP | Numeric | - |
| BK | v Budget GM V/V Trans. R HP | Numeric | - |
| BL | v Budget GM V/V Trans. A SP | Numeric | - |
| BM | v Budget GM V/V Trans. R SP | Numeric | - |
| BN | v Budget GM V/V Trans. A+R | Numeric | - |
| BP | V.DateDebutSemestre | Date | 3x session |
| BQ | V.DateFinSemestre | Date | 3x session |
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

### 11.3 Autres (148)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| Y | budget_total_jhp | Numeric | 1x refs |
| Z | budget_total_jh_vrl | Numeric | 2x refs |
| BA | budget_total_jhd | Numeric | - |
| BB | budget_total_jhp_S2 | Numeric | - |
| BC | budget_total_jh_vrl_S2 | Numeric | 1x refs |
| BD | budget_total_jhd_S2 | Numeric | - |
| BO | LibelleTypeCalendrier | Alpha | 3x refs |
| BR | GM VRL HP M4 | Numeric | 3x refs |
| BS | GM VRL HP M5 | Numeric | 1x refs |
| BT | GM VRL HP M6 | Numeric | 1x refs |
| BU | JHD GE M1 | Numeric | 1x refs |
| BV | JHD GE M2 | Numeric | 1x refs |
| BW | JHD GE M3 | Numeric | 1x refs |
| BX | JHD GE M4 | Numeric | 1x refs |
| BY | JHD GE M5 | Numeric | 2x refs |
| BZ | JHD GE M6 | Numeric | 2x refs |
| CA | JHD GO M1 | Numeric | 2x refs |
| CB | JHD GO M2 | Numeric | 1x refs |
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
| P0 | **G** | P.TypeCalendrier | Unicode |
| P0 | **H** | P.Reporte? | Logical |
| V. | **I** | V.Date debut | Date |
| V. | **J** | V.Date fin | Date |
| V. | **K** | V.Code village | Alpha |
| V. | **L** | V.Cumul sur 1er mois | Logical |
| V. | **M** | V.Cumul sur dernier mois | Logical |
| V. | **N** | V.Date debut ete | Date |
| V. | **O** | V.Date fin ete | Date |
| V. | **P** | V.Date debut hiver | Date |
| V. | **Q** | V.Date fin hiver | Date |
| V. | **R** | V.Saison | Alpha |
| V. | **S** | V.Date-14 | Logical |
| V. | **T** | V.DateReport | Date |
| V. | **U** | V.NbrJoursSemestre1 | Numeric |
| V. | **V** | V.NbrJoursSaison1 | Numeric |
| V. | **W** | V.NbrJoursSemestre2 | Numeric |
| V. | **X** | V.NbrJoursSaison2 | Numeric |
| V. | **BE** | V.Existe qualite GM PRES ? | Logical |
| V. | **BF** | V Existe Correctif | Logical |
| V. | **BG** | v Budget GM Arrivés | Numeric |
| V. | **BH** | v Budget GM Transportés Package | Numeric |
| V. | **BI** | v Buget GM V/V | Numeric |
| V. | **BJ** | v Budget GM V/V Trans. A HP | Numeric |
| V. | **BK** | v Budget GM V/V Trans. R HP | Numeric |
| V. | **BL** | v Budget GM V/V Trans. A SP | Numeric |
| V. | **BM** | v Budget GM V/V Trans. R SP | Numeric |
| V. | **BN** | v Budget GM V/V Trans. A+R | Numeric |
| V. | **BP** | V.DateDebutSemestre | Date |
| V. | **BQ** | V.DateFinSemestre | Date |
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
| Autre | **Y** | budget_total_jhp | Numeric |
| Autre | **Z** | budget_total_jh_vrl | Numeric |
| Autre | **BA** | budget_total_jhd | Numeric |
| Autre | **BB** | budget_total_jhp_S2 | Numeric |
| Autre | **BC** | budget_total_jh_vrl_S2 | Numeric |
| Autre | **BD** | budget_total_jhd_S2 | Numeric |
| Autre | **BO** | LibelleTypeCalendrier | Alpha |
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

**100 / 100 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCULATION | 1 | 0 |
| CALCUL | 3 | 0 |
| CONDITION | 22 | 15 |
| CONSTANTE | 2 | 0 |
| FORMAT | 58 | 0 |
| OTHER | 10 | 0 |
| NEGATION | 1 | 0 |
| REFERENCE_VG | 3 | 0 |

### 12.2 Expressions cles par type

#### CALCULATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 73 | `v Budget GM Arrivés [BG]+v Budget GM Transporté... [BH]+v Buget GM V/V [BI]+v Budget GM V/V Trans.... [BJ]` | - |

#### CALCUL (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCUL | 95 | `MAX(([AU]*LibelleTypeCalendrier [BO]/V.DateDebutSemestre [BP]) + (JHD GO M1 [CA]*GM VRL HP M4 [BR]/V.DateFinSemestre [BQ]),0)` | - |
| CALCUL | 94 | `MAX(([AT]*LibelleTypeCalendrier [BO]/V.DateDebutSemestre [BP]) + (JHD GE M6 [BZ]*GM VRL HP M4 [BR]/V.DateFinSemestre [BQ]),0)` | - |
| CALCUL | 93 | `MAX(([AS]*LibelleTypeCalendrier [BO]/V.DateDebutSemestre [BP]) + (JHD GE M5 [BY]*GM VRL HP M4 [BR]/V.DateFinSemestre [BQ]),0)` | - |

#### CONDITION (22 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 87 | `IF(P.Lieu sejour [C] <> '' AND JHD GE M2 [BV] <> 0, JHD GE M2 [BV], GM VRL HP M5 [BS])` | [RM-011](#rm-RM-011) |
| CONDITION | 82 | `IF(v Budget GM V/V Trans.... [BN],V.Date-14 [S]-14,P.TypeCalendrier [G])` | [RM-010](#rm-RM-010) |
| CONDITION | 79 | `IF(P.Lieu sejour [C]<>'' AND [AR]<>0,[AR],[AD])` | [RM-009](#rm-RM-009) |
| CONDITION | 88 | `IF(P.Lieu sejour [C] <> '' AND JHD GE M3 [BW] <> 0, JHD GE M3 [BW], GM VRL HP M6 [BT])` | [RM-012](#rm-RM-012) |
| CONDITION | 98 | `IF(v Budget GM V/V Trans.... [BM]='C','comptable','operationnel')` | [RM-015](#rm-RM-015) |
| ... | | *+17 autres* | |

#### CONSTANTE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 61 | `'PRES'` | - |
| CONSTANTE | 60 | `'GM'` | - |

#### FORMAT (58 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| FORMAT | 43 | `FileExist(Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_ARTI_'&Trim(DStr(Date(),'YYYYMM'))&'.htm')` | - |
| FORMAT | 42 | `FileExist(Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_MISS_'&Trim(DStr(Date(),'YYYYMM'))&'.htm')` | - |
| FORMAT | 41 | `FileExist(Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_ANS_'&Trim(DStr(Date(),'YYYYMM'))&'.htm')` | - |
| FORMAT | 44 | `FileExist(Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_EDUC_'&Trim(DStr(Date(),'YYYYMM'))&'.htm')` | - |
| FORMAT | 47 | `FileExist(Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_PRESS_'&Trim(DStr(Date(),'YYYYMM'))&'.htm')` | - |
| ... | | *+53 autres* | |

#### OTHER (10 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 64 | `P Lieu de Sejour Saisie ? [F]` | - |
| OTHER | 62 | `[AY]` | - |
| OTHER | 66 | `budget_total_jh_vrl_S2 [BC]` | - |
| OTHER | 85 | `NOT(VG74)` | - |
| OTHER | 68 | `P.Lieu sejour [C]` | - |
| ... | | *+5 autres* | |

#### NEGATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| NEGATION | 59 | `NOT P.Appel de gestion crise [A]` | - |

#### REFERENCE_VG (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 86 | `VG74` | - |
| REFERENCE_VG | 67 | `VG47` | - |
| REFERENCE_VG | 63 | `VG47` | - |

### 12.3 Toutes les expressions (100)

<details>
<summary>Voir les 100 expressions</summary>

#### CALCULATION (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 73 | `v Budget GM Arrivés [BG]+v Budget GM Transporté... [BH]+v Buget GM V/V [BI]+v Budget GM V/V Trans.... [BJ]` |

#### CALCUL (3)

| IDE | Expression Decodee |
|-----|-------------------|
| 93 | `MAX(([AS]*LibelleTypeCalendrier [BO]/V.DateDebutSemestre [BP]) + (JHD GE M5 [BY]*GM VRL HP M4 [BR]/V.DateFinSemestre [BQ]),0)` |
| 94 | `MAX(([AT]*LibelleTypeCalendrier [BO]/V.DateDebutSemestre [BP]) + (JHD GE M6 [BZ]*GM VRL HP M4 [BR]/V.DateFinSemestre [BQ]),0)` |
| 95 | `MAX(([AU]*LibelleTypeCalendrier [BO]/V.DateDebutSemestre [BP]) + (JHD GO M1 [CA]*GM VRL HP M4 [BR]/V.DateFinSemestre [BQ]),0)` |

#### CONDITION (22)

| IDE | Expression Decodee |
|-----|-------------------|
| 70 | `IF(P.Lieu sejour [C]<>'' AND [AI]<>0,[AI],V.NbrJoursSemestre1 [U])` |
| 71 | `IF(P.Lieu sejour [C]<>'' AND [AJ]<>0,[AJ],V.NbrJoursSaison1 [V])` |
| 72 | `IF(P.Lieu sejour [C]<>'' AND [AK]<>0,[AK],V.NbrJoursSemestre2 [W])` |
| 74 | `IF(P.Lieu sejour [C]<>'' AND [AL]<>0,[AL],V.NbrJoursSaison2 [X])` |
| 75 | `IF(P.Lieu sejour [C]<>'' AND [AM]<>0,[AM],budget_total_jhp [Y])` |
| 76 | `IF(P.Lieu sejour [C]<>'' AND [AN]<>0,[AN],budget_total_jh_vrl [Z])` |
| 77 | `IF(P.Lieu sejour [C]<>'' AND [AO]<>0,[AO],[AA])` |
| 78 | `IF(P.Lieu sejour [C]<>'' AND [AQ]<>0,[AQ],[AC])` |
| 79 | `IF(P.Lieu sejour [C]<>'' AND [AR]<>0,[AR],[AD])` |
| 82 | `IF(v Budget GM V/V Trans.... [BN],V.Date-14 [S]-14,P.TypeCalendrier [G])` |
| 87 | `IF(P.Lieu sejour [C] <> '' AND JHD GE M2 [BV] <> 0, JHD GE M2 [BV], GM VRL HP M5 [BS])` |
| 88 | `IF(P.Lieu sejour [C] <> '' AND JHD GE M3 [BW] <> 0, JHD GE M3 [BW], GM VRL HP M6 [BT])` |
| 89 | `IF(P.Lieu sejour [C] <> '' AND JHD GE M4 [BX] <> 0, JHD GE M4 [BX], JHD GE M1 [BU])` |
| 90 | `IF(Range(Month(P.Date de fin [B]),1,6),[AS],JHD GE M5 [BY])` |
| 91 | `IF(Range(Month(P.Date de fin [B]),1,6),[AT],JHD GE M6 [BZ])` |
| 92 | `IF(Range(Month(P.Date de fin [B]),1,6),[AU],JHD GO M1 [CA])` |
| 98 | `IF(v Budget GM V/V Trans.... [BM]='C','comptable','operationnel')` |
| 99 | `IF(Range(Month(P.Date de fin [B]),1,6),DVal('01/01/'&Str(Year(P.Date de fin [B]),'4'),'DD/MM/YYYY'),DVal('01/07/'&Str(Year(P.Date de fin [B]),'4'),'DD/MM/YYYY'))` |
| 100 | `IF(Range(Month(P.Date de fin [B]),1,6),DVal('30/06/'&Str(Year(P.Date de fin [B]),'4'),'DD/MM/YYYY'),DVal('31/12/'&Str(Year(P.Date de fin [B]),'4'),'DD/MM/YYYY'))` |
| 69 | `P.Lieu sejour [C]<>''` |
| 96 | `v Budget GM V/V Trans.... [BM] = 'C'` |
| 97 | `v Budget GM V/V Trans.... [BM] = 'O'` |

#### CONSTANTE (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 60 | `'GM'` |
| 61 | `'PRES'` |

#### FORMAT (58)

| IDE | Expression Decodee |
|-----|-------------------|
| 1 | `DVal('01/05/'&Str(Year(P.Date de fin [B]),'4'),'DD/MM/YYYY')` |
| 2 | `DVal('31/10/'&Str(Year(P.Date de fin [B]),'4'),'DD/MM/YYYY')` |
| 3 | `DVal('01/11/'&Str(IF(Range(Month(P.Date de fin [B]),5,12),Year(P.Date de fin [B]),Year(P.Date de fin [B])-1),'4'),'DD/MM/YYYY')` |
| 4 | `DVal('30/04/'&Str(IF(Range(Month(P.Date de fin [B]),5,12),Year(P.Date de fin [B])+1,Year(P.Date de fin [B])),'4'),'DD/MM/YYYY')` |
| 6 | `Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_effectif_mensuel_' & Trim(JHD GO M2 [CB]) & '_' &Trim(DStr(Date(),'YYYYMM'))&'.htm'` |
| 7 | `Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_GE_'&Trim(DStr(Date(),'YYYYMM'))&'.htm'` |
| 8 | `Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_GO_'&Trim(DStr(Date(),'YYYYMM'))&'.htm'` |
| 9 | `Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_ECH_'&Trim(DStr(Date(),'YYYYMM'))&'.htm'` |
| 10 | `Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_EXC_'&Trim(DStr(Date(),'YYYYMM'))&'.htm'` |
| 11 | `Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_IGR_'&Trim(DStr(Date(),'YYYYMM'))&'.htm'` |
| 12 | `Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_IGP_'&Trim(DStr(Date(),'YYYYMM'))&'.htm'` |
| 13 | `Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_IGP2_'&Trim(DStr(Date(),'YYYYMM'))&'.htm'` |
| 14 | `Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_ANS_'&Trim(DStr(Date(),'YYYYMM'))&'.htm'` |
| 15 | `Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_MISS_'&Trim(DStr(Date(),'YYYYMM'))&'.htm'` |
| 16 | `Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_ARTI_'&Trim(DStr(Date(),'YYYYMM'))&'.htm'` |
| 17 | `Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_EDUC_'&Trim(DStr(Date(),'YYYYMM'))&'.htm'` |
| 18 | `Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_DOCT_'&Trim(DStr(Date(),'YYYYMM'))&'.htm'` |
| 19 | `Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_STAG_'&Trim(DStr(Date(),'YYYYMM'))&'.htm'` |
| 20 | `Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_PRESS_'&Trim(DStr(Date(),'YYYYMM'))&'.htm'` |
| 21 | `Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_PRESR_'&Trim(DStr(Date(),'YYYYMM'))&'.htm'` |
| 22 | `Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_VSHIP_'&Trim(DStr(Date(),'YYYYMM'))&'.htm'` |
| 23 | `Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_FOU_'&Trim(DStr(Date(),'YYYYMM'))&'.htm'` |
| 24 | `Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_IGR_'&Trim(DStr(Date(),'YYYYMM'))&'.htm'` |
| 25 | `Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_Rep_Enc_HP_'&Trim(DStr(Date(),'YYYYMM'))&'.htm'` |
| 26 | `Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_ANS_'&Trim(DStr(Date(),'YYYYMM'))&'.htm'` |
| 27 | `Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_MISS_'&Trim(DStr(Date(),'YYYYMM'))&'.htm'` |
| 28 | `Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_PRES_'&Trim(DStr(Date(),'YYYYMM'))&'.htm'` |
| 29 | `Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_VSHIP_'&Trim(DStr(Date(),'YYYYMM'))&'.htm'` |
| 30 | `FileExist(Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_effectif_mensuel_'&Trim(DStr(Date(),'YYYYMM'))&'.htm')` |
| 34 | `FileExist(Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_GE_'&Trim(DStr(Date(),'YYYYMM'))&'.htm')` |
| 35 | `FileExist(Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_GO_'&Trim(DStr(Date(),'YYYYMM'))&'.htm')` |
| 36 | `FileExist(Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_ECH_'&Trim(DStr(Date(),'YYYYMM'))&'.htm')` |
| 37 | `FileExist(Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_EXC_'&Trim(DStr(Date(),'YYYYMM'))&'.htm')` |
| 38 | `FileExist(Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_IGR_'&Trim(DStr(Date(),'YYYYMM'))&'.htm')` |
| 39 | `FileExist(Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_IGP_'&Trim(DStr(Date(),'YYYYMM'))&'.htm')` |
| 40 | `FileExist(Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_IGP2_'&Trim(DStr(Date(),'YYYYMM'))&'.htm')` |
| 41 | `FileExist(Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_ANS_'&Trim(DStr(Date(),'YYYYMM'))&'.htm')` |
| 42 | `FileExist(Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_MISS_'&Trim(DStr(Date(),'YYYYMM'))&'.htm')` |
| 43 | `FileExist(Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_ARTI_'&Trim(DStr(Date(),'YYYYMM'))&'.htm')` |
| 44 | `FileExist(Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_EDUC_'&Trim(DStr(Date(),'YYYYMM'))&'.htm')` |
| 45 | `FileExist(Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_DOCT_'&Trim(DStr(Date(),'YYYYMM'))&'.htm')` |
| 46 | `FileExist(Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_STAG_'&Trim(DStr(Date(),'YYYYMM'))&'.htm')` |
| 47 | `FileExist(Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_PRESS_'&Trim(DStr(Date(),'YYYYMM'))&'.htm')` |
| 48 | `FileExist(Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_PRESR_'&Trim(DStr(Date(),'YYYYMM'))&'.htm')` |
| 49 | `FileExist(Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_FOU_'&Trim(DStr(Date(),'YYYYMM'))&'.htm')` |
| 50 | `FileExist(Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_VSHIP_'&Trim(DStr(Date(),'YYYYMM'))&'.htm')` |
| 51 | `FileExist(Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_IGP_'&Trim(DStr(Date(),'YYYYMM'))&'.htm')` |
| 52 | `FileExist(Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_IGR_'&Trim(DStr(Date(),'YYYYMM'))&'.htm')` |
| 53 | `FileExist(Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_Rep_Enc_HP_'&Trim(DStr(Date(),'YYYYMM'))&'.htm')` |
| 54 | `FileExist(Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_ANS_'&Trim(DStr(Date(),'YYYYMM'))&'.htm')` |
| 55 | `FileExist(Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_MISS_'&Trim(DStr(Date(),'YYYYMM'))&'.htm')` |
| 56 | `FileExist(Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_PRES_'&Trim(DStr(Date(),'YYYYMM'))&'.htm')` |
| 57 | `FileExist(Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_VSHIP_'&Trim(DStr(Date(),'YYYYMM'))&'.htm')` |
| 65 | `'c:\temp\'&Trim(VG33)&'_'&IF(Trim(P.Lieu sejour [C])<>'',Trim(P.Lieu sejour [C])&'_','')&'EFF_Correctifs_'&Trim(DStr(Date(),'YYYYMM'))&'.htm'` |
| 80 | `FileExist(Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_Rep_Enc_HP_'&Trim(DStr(Date(),'YYYYMM'))&'.htm')` |
| 81 | `Trim(Translate('%club_exportdata%'))&'trsft\'&Trim(VG33)&IF(P.Lieu sejour [C]<>'','_'&Trim(P.Lieu sejour [C])&'_','_')&'EFF_Deficit_Rep_Enc_HP_'&Trim(DStr(Date(),'YYYYMM'))&'.htm'` |
| 83 | `DVal('30/06/'&Str(Year(P.Date de fin [B]),'4'),'DD/MM/YYYY') - DVal('01/01/'&Str(Year(P.Date de fin [B]),'4'),'DD/MM/YYYY')` |
| 84 | `DVal('31/12/'&Str(Year(P.Date de fin [B]),'4'),'DD/MM/YYYY') - DVal('01/07/'&Str(Year(P.Date de fin [B]),'4'),'DD/MM/YYYY')` |

#### OTHER (10)

| IDE | Expression Decodee |
|-----|-------------------|
| 5 | `GetParam('SOCIETE')` |
| 31 | `BOM(P.Reporte? [H])` |
| 32 | `EOM(P.Reporte? [H])` |
| 33 | `P.Reporte? [H]` |
| 58 | `Delay(15)` |
| 62 | `[AY]` |
| 64 | `P Lieu de Sejour Saisie ? [F]` |
| 66 | `budget_total_jh_vrl_S2 [BC]` |
| 68 | `P.Lieu sejour [C]` |
| 85 | `NOT(VG74)` |

#### NEGATION (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 59 | `NOT P.Appel de gestion crise [A]` |

#### REFERENCE_VG (3)

| IDE | Expression Decodee |
|-----|-------------------|
| 63 | `VG47` |
| 67 | `VG47` |
| 86 | `VG74` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Edition et envoi effectif (IDE 64)](PBP-IDE-64.md) -> **Edition effectif mensuel V3 (IDE 66)**

Main -> ... -> [Effectif mensuel lancement (IDE 54)](PBP-IDE-54.md) -> **Edition effectif mensuel V3 (IDE 66)**

```mermaid
graph LR
    T66[66 Edition effectif me...]
    style T66 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC148[148 Liste Gestion de C...]
    style CC148 fill:#f59e0b
    CC152[152 Start]
    style CC152 fill:#f59e0b
    CC414[414 Call Extraction]
    style CC414 fill:#f59e0b
    CC63[63 Cloture saison effe...]
    style CC63 fill:#f59e0b
    CC146[146 Pilotage Gestion d...]
    style CC146 fill:#f59e0b
    CC54[54 Effectif mensuel la...]
    style CC54 fill:#3fb950
    CC64[64 Edition et envoi ef...]
    style CC64 fill:#3fb950
    CC63 --> CC54
    CC146 --> CC54
    CC414 --> CC54
    CC63 --> CC64
    CC146 --> CC64
    CC414 --> CC64
    CC148 --> CC63
    CC152 --> CC63
    CC148 --> CC146
    CC152 --> CC146
    CC148 --> CC414
    CC152 --> CC414
    CC1 --> CC148
    CC1 --> CC152
    CC54 --> T66
    CC64 --> T66
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [64](PBP-IDE-64.md) | Edition et envoi effectif | 4 |
| [54](PBP-IDE-54.md) | Effectif mensuel lancement | 2 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T66[66 Edition effectif me...]
    style T66 fill:#58a6ff
    C57[57 Edition effectif ca...]
    T66 --> C57
    style C57 fill:#3fb950
    C67[67 Edition corrections...]
    T66 --> C67
    style C67 fill:#3fb950
    C68[68 Deficit GE sejour e...]
    T66 --> C68
    style C68 fill:#3fb950
    C69[69 Deficit GO sejour e...]
    T66 --> C69
    style C69 fill:#3fb950
    C70[70 Deficit IGP Hors CD...]
    T66 --> C70
    style C70 fill:#3fb950
    C71[71 Deficit IGP CDV Sej V3]
    T66 --> C71
    style C71 fill:#3fb950
    C72[72 Deficit IGP Global ...]
    T66 --> C72
    style C72 fill:#3fb950
    C73[73 Deficit GM echange ...]
    T66 --> C73
    style C73 fill:#3fb950
    C74[74 Deficit Excursions ...]
    T66 --> C74
    style C74 fill:#3fb950
    C75[75 Deficit IGR V3]
    T66 --> C75
    style C75 fill:#3fb950
    C76[76 Deficit CMB V3]
    T66 --> C76
    style C76 fill:#3fb950
    C77[77 Deficit ANS V3]
    T66 --> C77
    style C77 fill:#3fb950
    C78[78 Deficit Fournisseur...]
    T66 --> C78
    style C78 fill:#3fb950
    C79[79 Deficit VSHIP repasV3]
    T66 --> C79
    style C79 fill:#3fb950
    C80[80 Deficit MISS V3]
    T66 --> C80
    style C80 fill:#3fb950
    C81[81 Deficit Artiste V3]
    T66 --> C81
    style C81 fill:#3fb950
    C82[82 Deficit Educteur V3]
    T66 --> C82
    style C82 fill:#3fb950
    C83[83 Deficit Medecin V3]
    T66 --> C83
    style C83 fill:#3fb950
    C84[84 Deficit Stagiaire V3]
    T66 --> C84
    style C84 fill:#3fb950
    C85[85 Deficit PRES sejour V3]
    T66 --> C85
    style C85 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [57](PBP-IDE-57.md) | Edition effectif calcul dates | 1 | Impression ticket/document |
| [67](PBP-IDE-67.md) | Edition corrections effectifV3 | 1 | Impression ticket/document |
| [68](PBP-IDE-68.md) | Deficit GE sejour et repas V3 | 1 | Sous-programme |
| [69](PBP-IDE-69.md) | Deficit GO sejour et repas V3 | 1 | Sous-programme |
| [70](PBP-IDE-70.md) | Deficit IGP Hors CDV V3 | 1 | Sous-programme |
| [71](PBP-IDE-71.md) | Deficit IGP CDV Sej V3 | 1 | Sous-programme |
| [72](PBP-IDE-72.md) | Deficit IGP Global CDV V3 | 1 | Sous-programme |
| [73](PBP-IDE-73.md) | Deficit GM echange Repas V3 | 1 | Sous-programme |
| [74](PBP-IDE-74.md) | Deficit Excursions RepasV3? | 1 | Sous-programme |
| [75](PBP-IDE-75.md) | Deficit IGR V3 | 1 | Sous-programme |
| [76](PBP-IDE-76.md) | Deficit CMB V3 | 1 | Sous-programme |
| [77](PBP-IDE-77.md) | Deficit ANS V3 | 1 | Sous-programme |
| [78](PBP-IDE-78.md) | Deficit Fournisseurs V3 | 1 | Sous-programme |
| [79](PBP-IDE-79.md) | Deficit VSHIP repasV3 | 1 | Sous-programme |
| [80](PBP-IDE-80.md) | Deficit MISS V3 | 1 | Sous-programme |
| [81](PBP-IDE-81.md) | Deficit Artiste V3 | 1 | Sous-programme |
| [82](PBP-IDE-82.md) | Deficit Educteur V3 | 1 | Sous-programme |
| [83](PBP-IDE-83.md) | Deficit Medecin V3 | 1 | Sous-programme |
| [84](PBP-IDE-84.md) | Deficit Stagiaire V3 | 1 | Sous-programme |
| [85](PBP-IDE-85.md) | Deficit PRES sejour V3 | 1 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 1166 | Programme volumineux |
| Expressions | 100 | Logique moderee |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 20 | Forte dependance |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 3.9% (45 / 1166) | Code sain |
| Regles metier | 15 | Logique metier riche |

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
- 20 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| [Deficit VSHIP repasV3 (IDE 79)](PBP-IDE-79.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Deficit MISS V3 (IDE 80)](PBP-IDE-80.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Deficit Fournisseurs V3 (IDE 78)](PBP-IDE-78.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Deficit CMB V3 (IDE 76)](PBP-IDE-76.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Deficit ANS V3 (IDE 77)](PBP-IDE-77.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Deficit Stagiaire V3 (IDE 84)](PBP-IDE-84.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Deficit PRES sejour V3 (IDE 85)](PBP-IDE-85.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Deficit Medecin V3 (IDE 83)](PBP-IDE-83.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Deficit Artiste V3 (IDE 81)](PBP-IDE-81.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Deficit Educteur V3 (IDE 82)](PBP-IDE-82.md) | Sous-programme | 1x | Normale - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 09:05*
