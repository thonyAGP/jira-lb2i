# POO IDE 15 - Export Ucopia bck 20220923

> **Analyse**: Phases 1-4 2026-02-03 17:40 -> 17:40 (17s) | Assemblage 17:40
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | POO |
| IDE Position | 15 |
| Nom Programme | Export Ucopia bck 20220923 |
| Fichier source | `Prg_15.xml` |
| Dossier IDE | Pooling |
| Taches | 12 (2 ecrans visibles) |
| Tables modifiees | 4 |
| Programmes appeles | 1 |
| :warning: Statut | **ORPHELIN_POTENTIEL** |

## 2. DESCRIPTION FONCTIONNELLE

**Export Ucopia bck 20220923** assure la gestion complete de ce processus.

Le flux de traitement s'organise en **3 blocs fonctionnels** :

- **Traitement** (7 taches) : traitements metier divers
- **Initialisation** (3 taches) : reinitialisation d'etats et de variables de travail
- **Creation** (2 taches) : insertion d'enregistrements en base (mouvements, prestations)

**Donnees modifiees** : 4 tables en ecriture (parametre_workgroup, saisie_autorisations, recap_devise_cloture, compte_sans_fil_zero).

**Logique metier** : 1 regles identifiees couvrant conditions metier.

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (7 taches)

- **15** - Export Ucopia bck 23/09/2022 **[[ECRAN]](#ecran-t1)**
- **15.1** - Export
- **15.2** - Write Log
- **15.5** - Log Prog
- **15.8** - Drop Tempdb
- **15.9** - View Export **[[ECRAN]](#ecran-t24)**
- **15.1.1** - Delete by userid

Delegue a : [Convert Timestamp (IDE 8)](POO-IDE-8.md)

#### Phase 2 : Initialisation (3 taches)

- **15.3** - Init Table Tempo **[[ECRAN]](#ecran-t4)**
- **15.4** - Init Table Tempo
- **15.6** - Init Table Tempo

#### Phase 3 : Creation (2 taches)

- **15.7** - Create Temdb
- **15.7.1** - Create Index

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| parametre_workgroup | R/**W** (3 usages) |  |
| recap_devise_cloture | **W**/L (2 usages) | Donnees reseau/cloture |
| compte_sans_fil_zero | **W**/L (2 usages) | Comptes GM (generaux) |
| saisie_autorisations | R/**W** (2 usages) |  |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (7 taches)

Traitements internes.

---

#### <a id="t1"></a>15 - Export Ucopia bck 23/09/2022 [[ECRAN]](#ecran-t1)

**Role** : Tache d'orchestration : point d'entree du programme (7 sous-taches). Coordonne l'enchainement des traitements.
**Ecran** : 480 x 74 DLU | [Voir mockup](#ecran-t1)

<details>
<summary>6 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [15.1](#t2) | Export | Traitement |
| [15.2](#t3) | Write Log | Traitement |
| [15.5](#t8) | Log Prog | Traitement |
| [15.8](#t13) | Drop Tempdb | Traitement |
| [15.9](#t24) | View Export **[[ECRAN]](#ecran-t24)** | Traitement |
| [15.1.1](#t25) | Delete by userid | Traitement |

</details>
**Variables liees** : H (v.export iteratif)
**Delegue a** : [Convert Timestamp (IDE 8)](POO-IDE-8.md)

---

#### <a id="t2"></a>15.1 - Export

**Role** : Traitement : Export.
**Variables liees** : H (v.export iteratif)
**Delegue a** : [Convert Timestamp (IDE 8)](POO-IDE-8.md)

---

#### <a id="t3"></a>15.2 - Write Log

**Role** : Traitement : Write Log.
**Delegue a** : [Convert Timestamp (IDE 8)](POO-IDE-8.md)

---

#### <a id="t8"></a>15.5 - Log Prog

**Role** : Traitement : Log Prog.
**Delegue a** : [Convert Timestamp (IDE 8)](POO-IDE-8.md)

---

#### <a id="t13"></a>15.8 - Drop Tempdb

**Role** : Traitement : Drop Tempdb.
**Delegue a** : [Convert Timestamp (IDE 8)](POO-IDE-8.md)

---

#### <a id="t24"></a>15.9 - View Export [[ECRAN]](#ecran-t24)

**Role** : Traitement : View Export.
**Ecran** : 1285 x 325 DLU | [Voir mockup](#ecran-t24)
**Variables liees** : H (v.export iteratif)
**Delegue a** : [Convert Timestamp (IDE 8)](POO-IDE-8.md)

---

#### <a id="t25"></a>15.1.1 - Delete by userid

**Role** : Traitement : Delete by userid.
**Delegue a** : [Convert Timestamp (IDE 8)](POO-IDE-8.md)


### 3.2 Initialisation (3 taches)

Reinitialisation d'etats et variables de travail.

---

#### <a id="t4"></a>15.3 - Init Table Tempo [[ECRAN]](#ecran-t4)

**Role** : Reinitialisation : Init Table Tempo.
**Ecran** : 750 x 277 DLU | [Voir mockup](#ecran-t4)

---

#### <a id="t7"></a>15.4 - Init Table Tempo

**Role** : Reinitialisation : Init Table Tempo.

---

#### <a id="t11"></a>15.6 - Init Table Tempo

**Role** : Reinitialisation : Init Table Tempo.


### 3.3 Creation (2 taches)

Insertion de nouveaux enregistrements en base.

---

#### <a id="t12"></a>15.7 - Create Temdb

**Role** : Traitement : Create Temdb.

---

#### <a id="t23"></a>15.7.1 - Create Index

**Role** : Traitement : Create Index.


## 5. REGLES METIER

1 regles identifiees:

### Autres (1 regles)

#### <a id="rm-RM-001"></a>[RM-001] Traitement conditionnel si NOT(v.reprise [I]) OR v.retour log [B] est a zero

| Element | Detail |
|---------|--------|
| **Condition** | `NOT(v.reprise [I]) OR v.retour log [B]=0` |
| **Si vrai** | 1504216800 |
| **Si faux** | v.retour log [B]) |
| **Variables** | B (v.retour log), I (v.reprise) |
| **Expression source** | Expression 9 : `IF(NOT(v.reprise [I]) OR v.retour log [B]=0,1504216800,v.ret` |
| **Exemple** | Si NOT(v.reprise [I]) OR v.retour log [B]=0 â†’ 1504216800. Sinon â†’ v.retour log [B]) |

## 6. CONTEXTE

- **Appele par**: (aucun)
- **Appelle**: 1 programmes | **Tables**: 4 (W:4 R:2 L:2) | **Taches**: 12 | **Expressions**: 28

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (2 / 12)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 15 | 15 | Export Ucopia bck 23/09/2022 | Type0 | 480 | 74 | Traitement |
| 2 | 15.9 | 15.9 | View Export | Type0 | 1285 | 325 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>15 - Export Ucopia bck 23/09/2022
**Tache** : [15](#t1) | **Type** : Type0 | **Dimensions** : 480 x 74 DLU
**Bloc** : Traitement | **Titre IDE** : Export Ucopia bck 23/09/2022

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
    "taskId":  "15",
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

#### <a id="ecran-t24"></a>15.9 - View Export
**Tache** : [15.9](#t24) | **Type** : Type0 | **Dimensions** : 1285 x 325 DLU
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
    "taskId":  "15.9",
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
    VF1[15 Export Ucopia bck 2...]
    style VF1 fill:#58a6ff
    VF24[15.9 View Export]
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
| Export Ucopia bck 23/09/2022 | Sous-programme | [Convert Timestamp (IDE 8)](POO-IDE-8.md) | Retour ecran |

### 9.3 Structure hierarchique (12 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **15.1** | [**Export Ucopia bck 23/09/2022** (15)](#t1) [mockup](#ecran-t1) | - | 480x74 | Traitement |
| 15.1.1 | [Export (15.1)](#t2) | - | - | |
| 15.1.2 | [Write Log (15.2)](#t3) | - | - | |
| 15.1.3 | [Log Prog (15.5)](#t8) | - | - | |
| 15.1.4 | [Drop Tempdb (15.8)](#t13) | - | - | |
| 15.1.5 | [View Export (15.9)](#t24) [mockup](#ecran-t24) | - | 1285x325 | |
| 15.1.6 | [Delete by userid (15.1.1)](#t25) | - | - | |
| **15.2** | [**Init Table Tempo** (15.3)](#t4) [mockup](#ecran-t4) | - | 750x277 | Initialisation |
| 15.2.1 | [Init Table Tempo (15.4)](#t7) | - | - | |
| 15.2.2 | [Init Table Tempo (15.6)](#t11) | - | - | |
| **15.3** | [**Create Temdb** (15.7)](#t12) | - | - | Creation |
| 15.3.1 | [Create Index (15.7.1)](#t23) | - | - | |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Init Table Tempo PRIM ...]
    UPDATE[MAJ 4 tables]
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

### Tables utilisees (4)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 2 | parametre_workgroup |  | DB | R | **W** |   | 3 |
| 6 | saisie_autorisations |  | TMP | R | **W** |   | 2 |
| 7 | recap_devise_cloture | Donnees reseau/cloture | TMP |   | **W** | L | 2 |
| 8 | compte_sans_fil_zero | Comptes GM (generaux) | TMP |   | **W** | L | 2 |

### Colonnes par table (3 / 4 tables avec colonnes identifiees)

<details>
<summary>Table 2 - parametre_workgroup (R/**W**) - 3 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | p.Borne min timestamp | W | Numeric |
| B | p.Borne max timestamp | W | Numeric |
| C | v.date alpha | W | Alpha |

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

</details>

<details>
<summary>Table 7 - recap_devise_cloture (**W**/L) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 8 - compte_sans_fil_zero (**W**/L) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | v.date time | W | Alpha |
| B | v.ligne export | W | Alpha |
| C | v.last user id | W | Alpha |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (1)

Variables recues en parametre.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | p. Test | Logical | - |

### 11.2 Variables de session (16)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| B | v.retour log | Logical | 3x session |
| C | v.nb enreg lus | Numeric | - |
| D | v.nb adresses | Numeric | - |
| E | v.lieu de séjour | Alpha | - |
| F | v.date time | Alpha | - |
| G | v.last time | Numeric | - |
| H | v.export iteratif | Logical | - |
| I | v.reprise | Logical | 2x session |
| J | v.timestamp actuel alpha | Alpha | - |
| K | v.timestamp actuel numerique | Numeric | - |
| L | v.borne min timestamp | Numeric | 1x session |
| M | v.borne max timestamp | Numeric | 2x session |
| N | v.intervalle reprise | Numeric | 3x session |
| O | v.intervalle interrogation | Numeric | - |
| P | v.arret while | Logical | - |
| Q | v.nb boucles while | Numeric | 1x session |

<details>
<summary>Toutes les 17 variables (liste complete)</summary>

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

</details>

## 12. EXPRESSIONS

**28 / 28 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONDITION | 4 | 5 |
| CALCULATION | 2 | 0 |
| FORMAT | 3 | 0 |
| CONSTANTE | 5 | 0 |
| DATE | 1 | 0 |
| OTHER | 10 | 0 |
| CAST_LOGIQUE | 1 | 0 |
| CONCATENATION | 1 | 0 |
| STRING | 1 | 0 |

### 12.2 Expressions cles par type

#### CONDITION (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 9 | `IF(NOT(v.reprise [I]) OR v.retour log [B]=0,1504216800,v.retour log [B])` | [RM-001](#rm-RM-001) |
| CONDITION | 17 | `v.intervalle interroga... [O]>v.borne max timestamp [M]` | - |
| CONDITION | 25 | `DOW(Date())=1` | - |
| CONDITION | 3 | `NOT(v.reprise [I]) OR v.retour log [B]+v.nb boucles while [Q]<v.borne max timestamp [M]` | - |

#### CALCULATION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 28 | `[V]+1` | - |
| CALCULATION | 12 | `v.intervalle reprise [N]+[W]` | - |

#### FORMAT (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| FORMAT | 2 | `DStr(Date(),'DD/MM/YYYY')&' '&TStr(Time(),'HHMM')` | - |
| FORMAT | 21 | `'INIT TABLE PRIM :'&Trim(Str(v.intervalle reprise [N],'10'))&'-EOT'` | - |
| FORMAT | 19 | `'INIT TABLE PRIM :'&Trim(Str(v.intervalle reprise [N],'10'))&'-'&Trim(Str(v.intervalle interroga... [O],'10'))` | - |

#### CONSTANTE (5 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 23 | `'EXPORT TABLE'` | - |
| CONSTANTE | 24 | `'WRITE LOG'` | - |
| CONSTANTE | 22 | `'FIN INIT TABLE'` | - |
| CONSTANTE | 10 | `432000` | - |
| CONSTANTE | 11 | `7200` | - |

#### DATE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| DATE | 6 | `Date()` | - |

#### OTHER (10 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 16 | `DbDiscnt('Ucp ODBC')` | - |
| OTHER | 15 | `[S]` | - |
| OTHER | 18 | `v.intervalle interroga... [O]` | - |
| OTHER | 26 | `FileDelete(Translate('%env%')&'Log_Prog_Exp_Ucp_LW.txt')` | - |
| OTHER | 20 | `v.retour log [B]` | - |
| ... | | *+5 autres* | |

#### CAST_LOGIQUE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 4 | `'TRUE'LOG` | - |

#### CONCATENATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 27 | `FileRename(Translate('%env%')&'Log_Prog_Exp_Ucp.txt',Translate('%env%')&'Log_Prog_Exp_Ucp_LW.txt')` | - |

#### STRING (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| STRING | 8 | `Val(Left(v.borne min timestamp [L],10),'10')` | - |

### 12.3 Toutes les expressions (28)

<details>
<summary>Voir les 28 expressions</summary>

#### CONDITION (4)

| IDE | Expression Decodee |
|-----|-------------------|
| 3 | `NOT(v.reprise [I]) OR v.retour log [B]+v.nb boucles while [Q]<v.borne max timestamp [M]` |
| 9 | `IF(NOT(v.reprise [I]) OR v.retour log [B]=0,1504216800,v.retour log [B])` |
| 25 | `DOW(Date())=1` |
| 17 | `v.intervalle interroga... [O]>v.borne max timestamp [M]` |

#### CALCULATION (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 12 | `v.intervalle reprise [N]+[W]` |
| 28 | `[V]+1` |

#### FORMAT (3)

| IDE | Expression Decodee |
|-----|-------------------|
| 19 | `'INIT TABLE PRIM :'&Trim(Str(v.intervalle reprise [N],'10'))&'-'&Trim(Str(v.intervalle interroga... [O],'10'))` |
| 21 | `'INIT TABLE PRIM :'&Trim(Str(v.intervalle reprise [N],'10'))&'-EOT'` |
| 2 | `DStr(Date(),'DD/MM/YYYY')&' '&TStr(Time(),'HHMM')` |

#### CONSTANTE (5)

| IDE | Expression Decodee |
|-----|-------------------|
| 10 | `432000` |
| 11 | `7200` |
| 22 | `'FIN INIT TABLE'` |
| 23 | `'EXPORT TABLE'` |
| 24 | `'WRITE LOG'` |

#### DATE (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 6 | `Date()` |

#### OTHER (10)

| IDE | Expression Decodee |
|-----|-------------------|
| 1 | `Translate('%pool_lieu_sejour%')` |
| 5 | `v.timestamp actuel num... [K]` |
| 7 | `Time()` |
| 13 | `NOT([R])` |
| 14 | `NOT([S])` |
| 15 | `[S]` |
| 16 | `DbDiscnt('Ucp ODBC')` |
| 18 | `v.intervalle interroga... [O]` |
| 20 | `v.retour log [B]` |
| 26 | `FileDelete(Translate('%env%')&'Log_Prog_Exp_Ucp_LW.txt')` |

#### CAST_LOGIQUE (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 4 | `'TRUE'LOG` |

#### CONCATENATION (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 27 | `FileRename(Translate('%env%')&'Log_Prog_Exp_Ucp.txt',Translate('%env%')&'Log_Prog_Exp_Ucp_LW.txt')` |

#### STRING (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 8 | `Val(Left(v.borne min timestamp [L],10),'10')` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

**Chemin**: (pas de callers directs)

```mermaid
graph LR
    T15[15 Export Ucopia bck 2...]
    style T15 fill:#58a6ff
    NONE[Aucun caller]
    NONE -.-> T15
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| - | (aucun) | - |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T15[15 Export Ucopia bck 2...]
    style T15 fill:#58a6ff
    C8[8 Convert Timestamp]
    T15 --> C8
    style C8 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [8](POO-IDE-8.md) | Convert Timestamp | 3 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 250 | Taille moyenne |
| Expressions | 28 | Peu de logique |
| Tables WRITE | 4 | Impact modere |
| Sous-programmes | 1 | Peu de dependances |
| Ecrans visibles | 2 | Quelques ecrans |
| Code desactive | 1.6% (4 / 250) | Code sain |
| Regles metier | 1 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (7 taches: 2 ecrans, 5 traitements)

- **Strategie** : Orchestrateur avec 2 ecrans (Razor/React) et 5 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 1 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Initialisation (3 taches: 1 ecran, 2 traitements)

- **Strategie** : Constructeur/methode `InitAsync()` dans l'orchestrateur.

#### Creation (2 taches: 0 ecran, 2 traitements)

- **Strategie** : Repository pattern avec Entity Framework Core.
- Insertion via `IRepository<T>.CreateAsync()`

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| parametre_workgroup | Table WRITE (Database) | 1x | Schema + repository |
| saisie_autorisations | Table WRITE (Temp) | 1x | Schema + repository |
| recap_devise_cloture | Table WRITE (Temp) | 1x | Schema + repository |
| compte_sans_fil_zero | Table WRITE (Temp) | 1x | Schema + repository |
| [Convert Timestamp (IDE 8)](POO-IDE-8.md) | Sous-programme | 3x | **CRITIQUE** - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 17:40*
