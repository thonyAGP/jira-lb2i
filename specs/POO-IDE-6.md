# POO IDE 6 - Export Ucopia

> **Analyse**: Phases 1-4 2026-02-03 17:36 -> 17:36 (11s) | Assemblage 17:36
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | POO |
| IDE Position | 6 |
| Nom Programme | Export Ucopia |
| Fichier source | `Prg_6.xml` |
| Dossier IDE | Export |
| Taches | 8 (2 ecrans visibles) |
| Tables modifiees | 2 |
| Programmes appeles | 1 |

## 2. DESCRIPTION FONCTIONNELLE

**Export Ucopia** assure la gestion complete de ce processus, accessible depuis [Main Program (IDE 1)](POO-IDE-1.md), [Lancement Export (IDE 5)](POO-IDE-5.md), [Batch sur PABX (IDE 24)](POO-IDE-24.md).

Le flux de traitement s'organise en **2 blocs fonctionnels** :

- **Traitement** (6 taches) : traitements metier divers
- **Initialisation** (2 taches) : reinitialisation d'etats et de variables de travail

**Donnees modifiees** : 2 tables en ecriture (saisie_autorisations, recap_devise_cloture).

**Logique metier** : 1 regles identifiees couvrant conditions metier.

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (6 taches)

- **6** - Export Ucopia **[[ECRAN]](#ecran-t1)**
- **6.1** - Export
- **6.2** - Write Log
- **6.4** - Log Prog
- **6.5** - View Export **[[ECRAN]](#ecran-t24)**
- **6.1.1** - Delete by userid

Delegue a : [Convert Timestamp (IDE 8)](POO-IDE-8.md)

#### Phase 2 : Initialisation (2 taches)

- **6.3** - Init Table Tempo **[[ECRAN]](#ecran-t4)**
- **6.6** - Init Table Tempo **[[ECRAN]](#ecran-t28)**

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| saisie_autorisations | R/**W** (2 usages) |  |
| recap_devise_cloture | **W** (1 usages) | Donnees reseau/cloture |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (6 taches)

Traitements internes.

---

#### <a id="t1"></a>6 - Export Ucopia [[ECRAN]](#ecran-t1)

**Role** : Tache d'orchestration : point d'entree du programme (6 sous-taches). Coordonne l'enchainement des traitements.
**Ecran** : 480 x 74 DLU | [Voir mockup](#ecran-t1)

<details>
<summary>5 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [6.1](#t2) | Export | Traitement |
| [6.2](#t3) | Write Log | Traitement |
| [6.4](#t8) | Log Prog | Traitement |
| [6.5](#t24) | View Export **[[ECRAN]](#ecran-t24)** | Traitement |
| [6.1.1](#t25) | Delete by userid | Traitement |

</details>
**Variables liees** : H (v.export iteratif), S (v.Export UCP V6)
**Delegue a** : [Convert Timestamp (IDE 8)](POO-IDE-8.md)

---

#### <a id="t2"></a>6.1 - Export

**Role** : Traitement : Export.
**Variables liees** : H (v.export iteratif), S (v.Export UCP V6)
**Delegue a** : [Convert Timestamp (IDE 8)](POO-IDE-8.md)

---

#### <a id="t3"></a>6.2 - Write Log

**Role** : Traitement : Write Log.
**Delegue a** : [Convert Timestamp (IDE 8)](POO-IDE-8.md)

---

#### <a id="t8"></a>6.4 - Log Prog

**Role** : Traitement : Log Prog.
**Delegue a** : [Convert Timestamp (IDE 8)](POO-IDE-8.md)

---

#### <a id="t24"></a>6.5 - View Export [[ECRAN]](#ecran-t24)

**Role** : Traitement : View Export.
**Ecran** : 1285 x 325 DLU | [Voir mockup](#ecran-t24)
**Variables liees** : H (v.export iteratif), S (v.Export UCP V6)
**Delegue a** : [Convert Timestamp (IDE 8)](POO-IDE-8.md)

---

#### <a id="t25"></a>6.1.1 - Delete by userid

**Role** : Traitement : Delete by userid.
**Delegue a** : [Convert Timestamp (IDE 8)](POO-IDE-8.md)


### 3.2 Initialisation (2 taches)

Reinitialisation d'etats et variables de travail.

---

#### <a id="t4"></a>6.3 - Init Table Tempo [[ECRAN]](#ecran-t4)

**Role** : Reinitialisation : Init Table Tempo.
**Ecran** : 750 x 277 DLU | [Voir mockup](#ecran-t4)

---

#### <a id="t28"></a>6.6 - Init Table Tempo [[ECRAN]](#ecran-t28)

**Role** : Reinitialisation : Init Table Tempo.
**Ecran** : 750 x 277 DLU | [Voir mockup](#ecran-t28)


## 5. REGLES METIER

1 regles identifiees:

### Autres (1 regles)

#### <a id="rm-RM-001"></a>[RM-001] Traitement conditionnel si NOT(v.reprise [I]) OR v.retour log [B] est a zero

| Element | Detail |
|---------|--------|
| **Condition** | `NOT(v.reprise [I]) OR v.retour log [B]=0` |
| **Si vrai** | Val(Left([Z] |
| **Si faux** | 10),'10'),v.retour log [B]) |
| **Variables** | B (v.retour log), I (v.reprise) |
| **Expression source** | Expression 13 : `IF(NOT(v.reprise [I]) OR v.retour log [B]=0,Val(Left([Z],10)` |
| **Exemple** | Si NOT(v.reprise [I]) OR v.retour log [B]=0 â†’ Val(Left([Z]. Sinon â†’ 10),'10'),v.retour log [B]) |

## 6. CONTEXTE

- **Appele par**: [Main Program (IDE 1)](POO-IDE-1.md), [Lancement Export (IDE 5)](POO-IDE-5.md), [Batch sur PABX (IDE 24)](POO-IDE-24.md)
- **Appelle**: 1 programmes | **Tables**: 7 (W:2 R:4 L:3) | **Taches**: 8 | **Expressions**: 33

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (2 / 8)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 6 | 6 | Export Ucopia | Type0 | 480 | 74 | Traitement |
| 2 | 6.6 | 6.5 | View Export | Type0 | 1285 | 325 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>6 - Export Ucopia
**Tache** : [6](#t1) | **Type** : Type0 | **Dimensions** : 480 x 74 DLU
**Bloc** : Traitement | **Titre IDE** : Export Ucopia

<!-- FORM-DATA:
{
    "width":  480,
    "vFactor":  8,
    "type":  "Type0",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  8,
                         "type":  "label",
                         "var":  "",
                         "y":  23,
                         "w":  72,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "v.nb boucles while",
                         "parent":  null
                     },
                     {
                         "x":  84,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  52,
                         "fmt":  "",
                         "name":  "v.nb boucles while",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  8,
                         "type":  "edit",
                         "var":  "",
                         "y":  39,
                         "w":  468,
                         "fmt":  "50",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "6",
    "height":  74
}
-->

<details>
<summary><strong>Champs : 2 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 84,23 | v.nb boucles while | - | edit |
| 8,39 | 50 | - | edit |

</details>

---

#### <a id="ecran-t24"></a>6.6 - View Export
**Tache** : [6.5](#t24) | **Type** : Type0 | **Dimensions** : 1285 x 325 DLU
**Bloc** : Traitement | **Titre IDE** : View Export

<!-- FORM-DATA:
{
    "width":  1285,
    "vFactor":  8,
    "type":  "Type0",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  4,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "",
                         "w":  1638,
                         "y":  8,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  13,
                         "h":  312,
                         "cols":  [
                                      {
                                          "title":  "Session Id",
                                          "layer":  1,
                                          "w":  53
                                      },
                                      {
                                          "title":  "User Id",
                                          "layer":  2,
                                          "w":  151
                                      },
                                      {
                                          "title":  "Timestamp",
                                          "layer":  3,
                                          "w":  58
                                      },
                                      {
                                          "title":  "Date Alpha",
                                          "layer":  4,
                                          "w":  151
                                      },
                                      {
                                          "title":  "Last Name",
                                          "layer":  5,
                                          "w":  151
                                      },
                                      {
                                          "title":  "First Name",
                                          "layer":  6,
                                          "w":  151
                                      },
                                      {
                                          "title":  "Field Title 1",
                                          "layer":  7,
                                          "w":  151
                                      },
                                      {
                                          "title":  "Field Value 1",
                                          "layer":  8,
                                          "w":  151
                                      },
                                      {
                                          "title":  "Field Title 2",
                                          "layer":  9,
                                          "w":  151
                                      },
                                      {
                                          "title":  "Field Value 2",
                                          "layer":  10,
                                          "w":  151
                                      },
                                      {
                                          "title":  "Email",
                                          "layer":  11,
                                          "w":  151
                                      },
                                      {
                                          "title":  "Nationality",
                                          "layer":  12,
                                          "w":  151
                                      }
                                  ],
                         "rows":  12
                     },
                     {
                         "x":  8,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  46,
                         "fmt":  "",
                         "name":  "Session Id",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  29
                     },
                     {
                         "x":  61,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  144,
                         "fmt":  "",
                         "name":  "User Id",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  29
                     },
                     {
                         "x":  212,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  51,
                         "fmt":  "",
                         "name":  "Timestamp",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  29
                     },
                     {
                         "x":  270,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  144,
                         "fmt":  "",
                         "name":  "Date Alpha",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  29
                     },
                     {
                         "x":  421,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  144,
                         "fmt":  "",
                         "name":  "Last Name",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  29
                     },
                     {
                         "x":  572,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  144,
                         "fmt":  "",
                         "name":  "First Name",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  29
                     },
                     {
                         "x":  723,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  144,
                         "fmt":  "",
                         "name":  "Field Title 1",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  29
                     },
                     {
                         "x":  874,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  144,
                         "fmt":  "",
                         "name":  "Field Value 1",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  29
                     },
                     {
                         "x":  1025,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  144,
                         "fmt":  "",
                         "name":  "Field Title 2",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  29
                     },
                     {
                         "x":  1176,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  144,
                         "fmt":  "",
                         "name":  "Field Value 2",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  29
                     },
                     {
                         "x":  1327,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  144,
                         "fmt":  "",
                         "name":  "Email",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  29
                     },
                     {
                         "x":  1478,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  144,
                         "fmt":  "",
                         "name":  "Nationality",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  29
                     }
                 ],
    "taskId":  "6.6",
    "height":  325
}
-->

<details>
<summary><strong>Champs : 12 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 8,23 | Session Id | - | edit |
| 61,23 | User Id | - | edit |
| 212,23 | Timestamp | - | edit |
| 270,23 | Date Alpha | - | edit |
| 421,23 | Last Name | - | edit |
| 572,23 | First Name | - | edit |
| 723,23 | Field Title 1 | - | edit |
| 874,23 | Field Value 1 | - | edit |
| 1025,23 | Field Title 2 | - | edit |
| 1176,23 | Field Value 2 | - | edit |
| 1327,23 | Email | - | edit |
| 1478,23 | Nationality | - | edit |

</details>

## 9. NAVIGATION

### 9.1 Enchainement des ecrans

```mermaid
flowchart TD
    START([Entree])
    style START fill:#3fb950
    VF1[6 Export Ucopia]
    style VF1 fill:#58a6ff
    VF24[6.5 View Export]
    style VF24 fill:#58a6ff
    EXT8[IDE 8 Convert Timestamp]
    style EXT8 fill:#3fb950
    FIN([Sortie])
    style FIN fill:#f85149
    START --> VF1
    VF1 -->|Sous-programme| EXT8
    EXT8 --> FIN
```

**Detail par enchainement :**

| Depuis | Action | Vers | Retour |
|--------|--------|------|--------|
| Export Ucopia | Sous-programme | [Convert Timestamp (IDE 8)](POO-IDE-8.md) | Retour ecran |

### 9.3 Structure hierarchique (8 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **6.1** | [**Export Ucopia** (6)](#t1) [mockup](#ecran-t1) | - | 480x74 | Traitement |
| 6.1.1 | [Export (6.1)](#t2) | - | - | |
| 6.1.2 | [Write Log (6.2)](#t3) | - | - | |
| 6.1.3 | [Log Prog (6.4)](#t8) | - | - | |
| 6.1.4 | [View Export (6.5)](#t24) [mockup](#ecran-t24) | - | 1285x325 | |
| 6.1.5 | [Delete by userid (6.1.1)](#t25) | - | - | |
| **6.2** | [**Init Table Tempo** (6.3)](#t4) [mockup](#ecran-t4) | - | 750x277 | Initialisation |
| 6.2.1 | [Init Table Tempo (6.6)](#t28) [mockup](#ecran-t28) | - | 750x277 | |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[View Export]
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

### Tables utilisees (7)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 2 | parametre_workgroup |  | DB | R |   |   | 1 |
| 6 | saisie_autorisations |  | TMP | R | **W** |   | 2 |
| 7 | recap_devise_cloture | Donnees reseau/cloture | TMP |   | **W** |   | 1 |
| 8 | compte_sans_fil_zero | Comptes GM (generaux) | TMP | R |   | L | 3 |
| 10 | bre_tempo_export_market | Table temporaire ecran | TMP |   |   | L | 1 |
| 11 | ann |  | DB | R |   |   | 1 |
| 13 | automate_autorite |  | DB |   |   | L | 1 |

### Colonnes par table (5 / 5 tables avec colonnes identifiees)

<details>
<summary>Table 2 - parametre_workgroup (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | p.Borne min timestamp | R | Numeric |
| B | p.Borne max timestamp | R | Numeric |

</details>

<details>
<summary>Table 6 - saisie_autorisations (R/**W**) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | p. Test | W | Logical |
| B | v.retour log | W | Logical |
| C | v.nb enreg lus | W | Numeric |
| D | v.nb adresses | W | Numeric |
| E | v.lieu de séjour | W | Alpha |
| F | v.date time | W | Alpha |
| G | v.last time | W | Numeric |
| H | v.export iteratif | W | Logical |
| I | v.reprise | W | Logical |
| J | v.timestamp actuel alpha | W | Alpha |
| K | v.timestamp actuel numerique | W | Numeric |
| L | v.borne min timestamp | W | Numeric |
| M | v.borne max timestamp | W | Numeric |
| N | v.intervalle reprise | W | Numeric |
| O | v.intervalle interrogation | W | Numeric |
| P | v.arret while | W | Logical |
| Q | v.nb boucles while | W | Numeric |
| R | v.timestamp origine alpha | W | Alpha |
| S | v.Export UCP V6 | W | Logical |

</details>

<details>
<summary>Table 7 - recap_devise_cloture (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 8 - compte_sans_fil_zero (R/L) - 3 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | v.date time | R | Alpha |
| B | v.ligne export | R | Alpha |
| C | v.last user id | R | Alpha |

</details>

<details>
<summary>Table 11 - ann (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | p.Borne min timestamp | R | Numeric |
| B | p.Borne max timestamp | R | Numeric |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (1)

Variables recues du programme appelant ([Main Program (IDE 1)](POO-IDE-1.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | p. Test | Logical | - |

### 11.2 Variables de session (18)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| B | v.retour log | Logical | 4x session |
| C | v.nb enreg lus | Numeric | - |
| D | v.nb adresses | Numeric | - |
| E | v.lieu de séjour | Alpha | - |
| F | v.date time | Alpha | - |
| G | v.last time | Numeric | - |
| H | v.export iteratif | Logical | - |
| I | v.reprise | Logical | 3x session |
| J | v.timestamp actuel alpha | Alpha | - |
| K | v.timestamp actuel numerique | Numeric | - |
| L | v.borne min timestamp | Numeric | 1x session |
| M | v.borne max timestamp | Numeric | 2x session |
| N | v.intervalle reprise | Numeric | 3x session |
| O | v.intervalle interrogation | Numeric | - |
| P | v.arret while | Logical | - |
| Q | v.nb boucles while | Numeric | 1x session |
| R | v.timestamp origine alpha | Alpha | 1x session |
| S | v.Export UCP V6 | Logical | 1x session |

<details>
<summary>Toutes les 19 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| P0 | **A** | p. Test | Logical |
| V. | **B** | v.retour log | Logical |
| V. | **C** | v.nb enreg lus | Numeric |
| V. | **D** | v.nb adresses | Numeric |
| V. | **E** | v.lieu de séjour | Alpha |
| V. | **F** | v.date time | Alpha |
| V. | **G** | v.last time | Numeric |
| V. | **H** | v.export iteratif | Logical |
| V. | **I** | v.reprise | Logical |
| V. | **J** | v.timestamp actuel alpha | Alpha |
| V. | **K** | v.timestamp actuel numerique | Numeric |
| V. | **L** | v.borne min timestamp | Numeric |
| V. | **M** | v.borne max timestamp | Numeric |
| V. | **N** | v.intervalle reprise | Numeric |
| V. | **O** | v.intervalle interrogation | Numeric |
| V. | **P** | v.arret while | Logical |
| V. | **Q** | v.nb boucles while | Numeric |
| V. | **R** | v.timestamp origine alpha | Alpha |
| V. | **S** | v.Export UCP V6 | Logical |

</details>

## 12. EXPRESSIONS

**33 / 33 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCULATION | 3 | 0 |
| CONDITION | 5 | 5 |
| FORMAT | 3 | 0 |
| CONSTANTE | 5 | 0 |
| DATE | 2 | 0 |
| OTHER | 12 | 0 |
| CAST_LOGIQUE | 1 | 0 |
| CONCATENATION | 1 | 0 |
| STRING | 1 | 0 |

### 12.2 Expressions cles par type

#### CALCULATION (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 31 | `[V]+1` | - |
| CALCULATION | 16 | `v.intervalle reprise [N]+[W]` | - |
| CALCULATION | 1 | `DbExist('{10,-1}'DSOURCE,'')` | - |

#### CONDITION (5 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 13 | `IF(NOT(v.reprise [I]) OR v.retour log [B]=0,Val(Left([Z],10),'10'),v.retour log [B])` | [RM-001](#rm-RM-001) |
| CONDITION | 12 | `NOT(v.reprise [I]) OR v.retour log [B]=0` | - |
| CONDITION | 20 | `v.intervalle interroga... [O]>v.borne max timestamp [M]` | - |
| CONDITION | 4 | `NOT(v.reprise [I]) OR v.retour log [B]+v.nb boucles while [Q]<v.borne max timestamp [M]` | - |
| CONDITION | 28 | `DOW(Date())=1` | - |

#### FORMAT (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| FORMAT | 3 | `DStr(Date(),'DD/MM/YYYY')&' '&TStr(Time(),'HHMM')` | - |
| FORMAT | 24 | `'INIT TABLE PRIM :'&Trim(Str(v.intervalle reprise [N],'10'))&'-EOT'` | - |
| FORMAT | 22 | `'INIT TABLE PRIM :'&Trim(Str(v.intervalle reprise [N],'10'))&'-'&Trim(Str(v.intervalle interroga... [O],'10'))` | - |

#### CONSTANTE (5 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 26 | `'EXPORT TABLE'` | - |
| CONSTANTE | 27 | `'WRITE LOG'` | - |
| CONSTANTE | 25 | `'FIN INIT TABLE'` | - |
| CONSTANTE | 14 | `432000` | - |
| CONSTANTE | 15 | `7200` | - |

#### DATE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| DATE | 10 | `BOY(AddDate(Date(),-2,0,0))` | - |
| DATE | 7 | `Date()` | - |

#### OTHER (12 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 23 | `v.retour log [B]` | - |
| OTHER | 21 | `v.intervalle interroga... [O]` | - |
| OTHER | 19 | `DbDiscnt('Ucp ODBC')` | - |
| OTHER | 33 | `[AA]` | - |
| OTHER | 32 | `NOT([AA])` | - |
| ... | | *+7 autres* | |

#### CAST_LOGIQUE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 5 | `'TRUE'LOG` | - |

#### CONCATENATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 30 | `FileRename(Translate('%env%')&'Log_Prog_Exp_Ucp.txt',Translate('%env%')&'Log_Prog_Exp_Ucp_LW.txt')` | - |

#### STRING (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| STRING | 9 | `Val(Left(v.borne min timestamp [L],10),'10')` | - |

### 12.3 Toutes les expressions (33)

<details>
<summary>Voir les 33 expressions</summary>

#### CALCULATION (3)

| IDE | Expression Decodee |
|-----|-------------------|
| 1 | `DbExist('{10,-1}'DSOURCE,'')` |
| 16 | `v.intervalle reprise [N]+[W]` |
| 31 | `[V]+1` |

#### CONDITION (5)

| IDE | Expression Decodee |
|-----|-------------------|
| 4 | `NOT(v.reprise [I]) OR v.retour log [B]+v.nb boucles while [Q]<v.borne max timestamp [M]` |
| 13 | `IF(NOT(v.reprise [I]) OR v.retour log [B]=0,Val(Left([Z],10),'10'),v.retour log [B])` |
| 28 | `DOW(Date())=1` |
| 12 | `NOT(v.reprise [I]) OR v.retour log [B]=0` |
| 20 | `v.intervalle interroga... [O]>v.borne max timestamp [M]` |

#### FORMAT (3)

| IDE | Expression Decodee |
|-----|-------------------|
| 22 | `'INIT TABLE PRIM :'&Trim(Str(v.intervalle reprise [N],'10'))&'-'&Trim(Str(v.intervalle interroga... [O],'10'))` |
| 24 | `'INIT TABLE PRIM :'&Trim(Str(v.intervalle reprise [N],'10'))&'-EOT'` |
| 3 | `DStr(Date(),'DD/MM/YYYY')&' '&TStr(Time(),'HHMM')` |

#### CONSTANTE (5)

| IDE | Expression Decodee |
|-----|-------------------|
| 14 | `432000` |
| 15 | `7200` |
| 25 | `'FIN INIT TABLE'` |
| 26 | `'EXPORT TABLE'` |
| 27 | `'WRITE LOG'` |

#### DATE (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 7 | `Date()` |
| 10 | `BOY(AddDate(Date(),-2,0,0))` |

#### OTHER (12)

| IDE | Expression Decodee |
|-----|-------------------|
| 2 | `Translate('%pool_lieu_sejour%')` |
| 6 | `v.timestamp actuel num... [K]` |
| 8 | `Time()` |
| 11 | `'00:00:00'TIME` |
| 17 | `NOT(v.timestamp origine alpha [R])` |
| 18 | `NOT(v.Export UCP V6 [S])` |
| 19 | `DbDiscnt('Ucp ODBC')` |
| 21 | `v.intervalle interroga... [O]` |
| 23 | `v.retour log [B]` |
| 29 | `FileDelete(Translate('%env%')&'Log_Prog_Exp_Ucp_LW.txt')` |
| 32 | `NOT([AA])` |
| 33 | `[AA]` |

#### CAST_LOGIQUE (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 5 | `'TRUE'LOG` |

#### CONCATENATION (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 30 | `FileRename(Translate('%env%')&'Log_Prog_Exp_Ucp.txt',Translate('%env%')&'Log_Prog_Exp_Ucp_LW.txt')` |

#### STRING (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 9 | `Val(Left(v.borne min timestamp [L],10),'10')` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Main Program (IDE 1)](POO-IDE-1.md) -> **Export Ucopia (IDE 6)**

Main -> ... -> [Lancement Export (IDE 5)](POO-IDE-5.md) -> **Export Ucopia (IDE 6)**

Main -> ... -> [Batch sur PABX (IDE 24)](POO-IDE-24.md) -> **Export Ucopia (IDE 6)**

```mermaid
graph LR
    T6[6 Export Ucopia]
    style T6 fill:#58a6ff
    CC24[24 Batch sur PABX]
    style CC24 fill:#8b5cf6
    CC5[5 Lancement Export]
    style CC5 fill:#8b5cf6
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC1 --> T6
    CC5 --> T6
    CC24 --> T6
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [1](POO-IDE-1.md) | Main Program | 1 |
| [5](POO-IDE-5.md) | Lancement Export | 1 |
| [24](POO-IDE-24.md) | Batch sur PABX | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T6[6 Export Ucopia]
    style T6 fill:#58a6ff
    C8[8 Convert Timestamp]
    T6 --> C8
    style C8 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [8](POO-IDE-8.md) | Convert Timestamp | 2 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 265 | Taille moyenne |
| Expressions | 33 | Peu de logique |
| Tables WRITE | 2 | Impact faible |
| Sous-programmes | 1 | Peu de dependances |
| Ecrans visibles | 2 | Quelques ecrans |
| Code desactive | 0.8% (2 / 265) | Code sain |
| Regles metier | 1 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (6 taches: 2 ecrans, 4 traitements)

- **Strategie** : Orchestrateur avec 2 ecrans (Razor/React) et 4 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 1 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Initialisation (2 taches: 2 ecrans, 0 traitement)

- **Strategie** : Constructeur/methode `InitAsync()` dans l'orchestrateur.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| saisie_autorisations | Table WRITE (Temp) | 1x | Schema + repository |
| recap_devise_cloture | Table WRITE (Temp) | 1x | Schema + repository |
| [Convert Timestamp (IDE 8)](POO-IDE-8.md) | Sous-programme | 2x | Haute - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 17:36*
