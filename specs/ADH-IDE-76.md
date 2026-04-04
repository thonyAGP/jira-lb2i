# ADH IDE 76 - Print extrait compte /Service

> **Analyse**: Phases 1-4 2026-02-07 03:44 -> 02:11 (22h27min) | Assemblage 02:11
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | ADH |
| IDE Position | 76 |
| Nom Programme | Print extrait compte /Service |
| Fichier source | `Prg_76.xml` |
| Dossier IDE | Comptabilite |
| Taches | 17 (3 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 5 |
| Complexite | **BASSE** (score 25/100) |

## 2. DESCRIPTION FONCTIONNELLE

ADH IDE 76 est un programme technique d'impression orchestrant l'édition des extraits de compte à travers trois imprimantes configurables (Printer 1, 8, 9). Le programme récupère les données adhérent via des tables de référence (comptable_cte, tables, type_lit), construit les layouts d'impression en trois sections (extrait compte principal, pied de page, récapitulatifs Free Etra) et enregistre la traçabilité dans la table log_maj_tpe. La sélection de l'imprimante est pilotée par paramètres dynamiques via GetParam(), garantissant flexibilité sans hard-coding.

Le flux logique est minimal et très sain : cinq appels sous-programmes dédiés (IDE 75 pour le pied, 21 pour la devise locale, 179/181/182 pour gestion imprimante), zéro code mort (0.2% de lignes désactivées seulement), treize expressions claires (principalement des conditions d'imprimante et des opérations de mise en forme). Les variables essentielles (W0 masque extrait, W0 devise locale, paramètres de format PDF/email) sont injectées en entrée, permettant un réemploi dans les contextes Easy Check Out et extraction simple.

Aucun couplage métier complexe : le programme est un composant purement technique appelé uniquement par deux modules (IDE 53 Extrait Easy Check Out J+1, IDE 69 Extrait de compte), ce qui en fait un service d'édition autonome et maintenable. Le statut dans ADH.ecf le rend disponible aux autres projets (PBP, PVE) s'ils requièrent une édition d'extrait compatible, justifiant son intégration dans le composant Sessions_Reprises.

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (4 taches)

Traitements internes.

---

#### <a id="t1"></a>76 - Veuillez patienter... [[ECRAN]](#ecran-t1)

**Role** : Traitement : Veuillez patienter....
**Ecran** : 422 x 56 DLU (MDI) | [Voir mockup](#ecran-t1)

<details>
<summary>3 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [76.2.1](#t10) | Veuillez patienter... **[[ECRAN]](#ecran-t10)** | Traitement |
| [76.3.1](#t14) | Veuillez patienter... **[[ECRAN]](#ecran-t14)** | Traitement |
| [76.4](#t17) | recup nom adherent | Traitement |

</details>
**Delegue a** : [Recupere devise local (IDE 21)](ADH-IDE-21.md), [Set Listing Number (IDE 181)](ADH-IDE-181.md)

---

#### <a id="t10"></a>76.2.1 - Veuillez patienter... [[ECRAN]](#ecran-t10)

**Role** : Traitement : Veuillez patienter....
**Ecran** : 422 x 57 DLU (MDI) | [Voir mockup](#ecran-t10)
**Delegue a** : [Recupere devise local (IDE 21)](ADH-IDE-21.md), [Set Listing Number (IDE 181)](ADH-IDE-181.md)

---

#### <a id="t14"></a>76.3.1 - Veuillez patienter... [[ECRAN]](#ecran-t14)

**Role** : Traitement : Veuillez patienter....
**Ecran** : 422 x 57 DLU (MDI) | [Voir mockup](#ecran-t14)
**Delegue a** : [Recupere devise local (IDE 21)](ADH-IDE-21.md), [Set Listing Number (IDE 181)](ADH-IDE-181.md)

---

#### <a id="t17"></a>76.4 - recup nom adherent

**Role** : Consultation/chargement : recup nom adherent.
**Variables liees** : EO (P0 code adherent), FF (W0 n° adherent)
**Delegue a** : [Recupere devise local (IDE 21)](ADH-IDE-21.md), [Set Listing Number (IDE 181)](ADH-IDE-181.md)


### 3.2 Impression (13 taches)

Generation des documents et tickets.

---

#### <a id="t2"></a>76.1 - Printer 1

**Role** : Generation du document : Printer 1.

---

#### <a id="t3"></a>76.1.1 - edition extrait compte

**Role** : Generation du document : edition extrait compte.
**Variables liees** : FP (W0 masque extrait), FN (v. Libelle edition)

---

#### <a id="t4"></a>76.1.1.1 - Edition du pied

**Role** : Generation du document : Edition du pied.
**Variables liees** : FN (v. Libelle edition)

---

#### <a id="t5"></a>76.1.1.2 - Edition recap Free Etra

**Role** : Generation du document : Edition recap Free Etra.
**Variables liees** : FN (v. Libelle edition)

---

#### <a id="t6"></a>76.1.2 - edition extrait compte

**Role** : Generation du document : edition extrait compte.
**Variables liees** : FP (W0 masque extrait), FN (v. Libelle edition)

---

#### <a id="t7"></a>76.1.2.1 - Edition du pied

**Role** : Generation du document : Edition du pied.
**Variables liees** : FN (v. Libelle edition)

---

#### <a id="t8"></a>76.1.2.2 - Edition recap Free Etra

**Role** : Generation du document : Edition recap Free Etra.
**Variables liees** : FN (v. Libelle edition)

---

#### <a id="t9"></a>76.2 - Printer 8 [[ECRAN]](#ecran-t9)

**Role** : Generation du document : Printer 8.
**Ecran** : 422 x 57 DLU (MDI) | [Voir mockup](#ecran-t9)

---

#### <a id="t11"></a>76.2.1.1 - Edition du pied

**Role** : Generation du document : Edition du pied.
**Variables liees** : FN (v. Libelle edition)

---

#### <a id="t12"></a>76.2.1.2 - Edition recap Free Etra

**Role** : Generation du document : Edition recap Free Etra.
**Variables liees** : FN (v. Libelle edition)

---

#### <a id="t13"></a>76.3 - Printer 9 [[ECRAN]](#ecran-t13)

**Role** : Generation du document : Printer 9.
**Ecran** : 422 x 57 DLU (MDI) | [Voir mockup](#ecran-t13)

---

#### <a id="t15"></a>76.3.1.1 - Edition du pied

**Role** : Generation du document : Edition du pied.
**Variables liees** : FN (v. Libelle edition)

---

#### <a id="t16"></a>76.3.1.2 - Edition recap Free Etra

**Role** : Generation du document : Edition recap Free Etra.
**Variables liees** : FN (v. Libelle edition)


## 5. REGLES METIER

4 regles identifiees:

### Impression (3 regles)

#### <a id="rm-RM-002"></a>[RM-002] Verification que l'imprimante courante est la n1

| Element | Detail |
|---------|--------|
| **Condition** | `GetParam ('CURRENTPRINTERNUM')=1` |
| **Si vrai** | Action si CURRENTPRINTERNUM = 1 |
| **Expression source** | Expression 6 : `GetParam ('CURRENTPRINTERNUM')=1` |
| **Exemple** | Si GetParam ('CURRENTPRINTERNUM')=1 â†’ Action si CURRENTPRINTERNUM = 1 |
| **Impact** | [76.1 - Printer 1](#t2) |

#### <a id="rm-RM-003"></a>[RM-003] Verification que l'imprimante courante est la n8

| Element | Detail |
|---------|--------|
| **Condition** | `GetParam ('CURRENTPRINTERNUM')=8` |
| **Si vrai** | Action si CURRENTPRINTERNUM = 8 |
| **Expression source** | Expression 7 : `GetParam ('CURRENTPRINTERNUM')=8` |
| **Exemple** | Si GetParam ('CURRENTPRINTERNUM')=8 â†’ Action si CURRENTPRINTERNUM = 8 |
| **Impact** | [76.1 - Printer 1](#t2) |

#### <a id="rm-RM-004"></a>[RM-004] Verification que l'imprimante courante est la n9

| Element | Detail |
|---------|--------|
| **Condition** | `GetParam ('CURRENTPRINTERNUM')=9` |
| **Si vrai** | Action si CURRENTPRINTERNUM = 9 |
| **Expression source** | Expression 8 : `GetParam ('CURRENTPRINTERNUM')=9` |
| **Exemple** | Si GetParam ('CURRENTPRINTERNUM')=9 â†’ Action si CURRENTPRINTERNUM = 9 |
| **Impact** | [76.1 - Printer 1](#t2) |

### Autres (1 regles)

#### <a id="rm-RM-001"></a>[RM-001] Condition composite: IsComponent () AND NOT(P.Appel Direct [N])

| Element | Detail |
|---------|--------|
| **Condition** | `IsComponent () AND NOT(P.Appel Direct [N])` |
| **Si vrai** | Action si vrai |
| **Variables** | FA (P.Appel Direct) |
| **Expression source** | Expression 2 : `IsComponent () AND NOT(P.Appel Direct [N])` |
| **Exemple** | Si IsComponent () AND NOT(P.Appel Direct [N]) â†’ Action si vrai |

## 6. CONTEXTE

- **Appele par**: [Extrait Easy Check Out à J+1 (IDE 53)](ADH-IDE-53.md), [Extrait de compte (IDE 69)](ADH-IDE-69.md)
- **Appelle**: 5 programmes | **Tables**: 9 (W:1 R:3 L:8) | **Taches**: 17 | **Expressions**: 13

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (3 / 17)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 76 | 76 | Veuillez patienter... | MDI | 422 | 56 | Traitement |
| 2 | 76.2.1 | 76.2.1 | Veuillez patienter... | MDI | 422 | 57 | Traitement |
| 3 | 76.3.1 | 76.3.1 | Veuillez patienter... | MDI | 422 | 57 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>76 - Veuillez patienter...
**Tache** : [76](#t1) | **Type** : MDI | **Dimensions** : 422 x 56 DLU
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
                         "x":  69,
                         "type":  "label",
                         "var":  "",
                         "y":  38,
                         "w":  285,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Edition de l\u0027extrait de compte",
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
    "taskId":  "76",
    "height":  56
}
-->

---

#### <a id="ecran-t10"></a>76.2.1 - Veuillez patienter...
**Tache** : [76.2.1](#t10) | **Type** : MDI | **Dimensions** : 422 x 57 DLU
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
                         "x":  69,
                         "type":  "label",
                         "var":  "",
                         "y":  38,
                         "w":  285,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Edition de l\u0027extrait de compte",
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
    "taskId":  "76.2.1",
    "height":  57
}
-->

---

#### <a id="ecran-t14"></a>76.3.1 - Veuillez patienter...
**Tache** : [76.3.1](#t14) | **Type** : MDI | **Dimensions** : 422 x 57 DLU
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
                         "x":  69,
                         "type":  "label",
                         "var":  "",
                         "y":  38,
                         "w":  285,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Edition de l\u0027extrait de compte",
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
    "taskId":  "76.3.1",
    "height":  57
}
-->

## 9. NAVIGATION

### 9.1 Enchainement des ecrans

```mermaid
flowchart TD
    START([Entree])
    style START fill:#3fb950
    VF1[76 Veuillez patienter...]
    style VF1 fill:#58a6ff
    VF10[76.2.1 Veuillez patienter...]
    style VF10 fill:#58a6ff
    VF14[76.3.1 Veuillez patienter...]
    style VF14 fill:#58a6ff
    EXT75[IDE 75 Creation Pied F...]
    style EXT75 fill:#3fb950
    EXT21[IDE 21 Recupere devise...]
    style EXT21 fill:#3fb950
    EXT179[IDE 179 Get Printer]
    style EXT179 fill:#3fb950
    EXT181[IDE 181 Set Listing Nu...]
    style EXT181 fill:#3fb950
    EXT182[IDE 182 Raz Current Pr...]
    style EXT182 fill:#3fb950
    FIN([Sortie])
    style FIN fill:#f85149
    START --> VF1
    VF1 -->|Sous-programme| EXT75
    VF1 -->|Recuperation donnees| EXT21
    VF1 -->|Impression ticket/document| EXT179
    VF1 -->|Configuration impression| EXT181
    VF1 -->|Impression ticket/document| EXT182
    EXT182 --> FIN
```

**Detail par enchainement :**

| Depuis | Action | Vers | Retour |
|--------|--------|------|--------|
| Veuillez patienter... | Sous-programme | [Creation Pied Facture (IDE 75)](ADH-IDE-75.md) | Retour ecran |
| Veuillez patienter... | Recuperation donnees | [Recupere devise local (IDE 21)](ADH-IDE-21.md) | Retour ecran |
| Veuillez patienter... | Impression ticket/document | [Get Printer (IDE 179)](ADH-IDE-179.md) | Retour ecran |
| Veuillez patienter... | Configuration impression | [Set Listing Number (IDE 181)](ADH-IDE-181.md) | Retour ecran |
| Veuillez patienter... | Impression ticket/document | [Raz Current Printer (IDE 182)](ADH-IDE-182.md) | Retour ecran |

### 9.3 Structure hierarchique (17 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **76.1** | [**Veuillez patienter...** (76)](#t1) [mockup](#ecran-t1) | MDI | 422x56 | Traitement |
| 76.1.1 | [Veuillez patienter... (76.2.1)](#t10) [mockup](#ecran-t10) | MDI | 422x57 | |
| 76.1.2 | [Veuillez patienter... (76.3.1)](#t14) [mockup](#ecran-t14) | MDI | 422x57 | |
| 76.1.3 | [recup nom adherent (76.4)](#t17) | MDI | - | |
| **76.2** | [**Printer 1** (76.1)](#t2) | MDI | - | Impression |
| 76.2.1 | [edition extrait compte (76.1.1)](#t3) | MDI | - | |
| 76.2.2 | [Edition du pied (76.1.1.1)](#t4) | - | - | |
| 76.2.3 | [Edition recap Free Etra (76.1.1.2)](#t5) | - | - | |
| 76.2.4 | [edition extrait compte (76.1.2)](#t6) | MDI | - | |
| 76.2.5 | [Edition du pied (76.1.2.1)](#t7) | - | - | |
| 76.2.6 | [Edition recap Free Etra (76.1.2.2)](#t8) | - | - | |
| 76.2.7 | [Printer 8 (76.2)](#t9) [mockup](#ecran-t9) | MDI | 422x57 | |
| 76.2.8 | [Edition du pied (76.2.1.1)](#t11) | - | - | |
| 76.2.9 | [Edition recap Free Etra (76.2.1.2)](#t12) | - | - | |
| 76.2.10 | [Printer 9 (76.3)](#t13) [mockup](#ecran-t13) | MDI | 422x57 | |
| 76.2.11 | [Edition du pied (76.3.1.1)](#t15) | - | - | |
| 76.2.12 | [Edition recap Free Etra (76.3.1.2)](#t16) | - | - | |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Traitement principal]
    DECISION{P.Appel Direct}
    PROCESS[Traitement]
    UPDATE[MAJ 1 tables]
    ENDOK([END OK])
    ENDKO([END KO])

    START --> INIT --> SAISIE --> DECISION
    DECISION -->|OUI| PROCESS
    DECISION -->|NON| ENDKO
    PROCESS --> UPDATE --> ENDOK

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
| 867 | log_maj_tpe |  | DB |   | **W** |   | 4 |
| 40 | comptable________cte |  | DB | R |   | L | 8 |
| 30 | gm-recherche_____gmr | Index de recherche | DB | R |   | L | 5 |
| 31 | gm-complet_______gmc |  | DB | R |   | L | 3 |
| 67 | tables___________tab |  | DB |   |   | L | 3 |
| 928 | type_lit |  | DB |   |   | L | 2 |
| 413 | pv_tva |  | DB |   |   | L | 1 |
| 34 | hebergement______heb | Hebergement (chambres) | DB |   |   | L | 1 |
| 400 | pv_cust_rentals |  | DB |   |   | L | 1 |

### Colonnes par table (1 / 4 tables avec colonnes identifiees)

<details>
<summary>Table 867 - log_maj_tpe (**W**) - 4 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 40 - comptable________cte (R/L) - 8 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | W1 cumul compte | R | Numeric |
| B | W1 solde compte | R | Numeric |
| C | W1 ss_total compte | R | Numeric |
| D | v.retour offre | R | Logical |
| E | W1 detection papier | R | Alpha |
| F | W1 inhibe panel | R | Alpha |
| G | W1 massicot | R | Alpha |
| H | W1 selection feuille | R | Alpha |
| I | W1 selection rouleau | R | Alpha |
| J | W1 cumul compte | R | Numeric |
| K | W1 solde compte | R | Numeric |
| L | W1 ss_total compte | R | Numeric |
| M | v.retour special offer | R | Logical |

</details>

<details>
<summary>Table 30 - gm-recherche_____gmr (R/L) - 5 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 31 - gm-complet_______gmc (R/L) - 3 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (15)

Variables recues du programme appelant ([Extrait Easy Check Out à J+1 (IDE 53)](ADH-IDE-53.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| EN | P0 societe | Alpha | - |
| EO | P0 code adherent | Numeric | - |
| EP | P0 filiation | Numeric | - |
| EQ | P0 masque montant | Alpha | 1x parametre entrant |
| ER | P0 nom village | Alpha | - |
| ES | P0 fictif | Logical | - |
| ET | P0 date comptable | Date | - |
| EU | P0 Edtion Tva V2 | Logical | - |
| EV | P.FormatPdf | Logical | 1x parametre entrant |
| EW | P.Chemin | Alpha | - |
| EX | P.NomFichierPdf | Alpha | - |
| EY | P.Print or Email | Alpha | - |
| EZ | P.Print GIFT PASS | Logical | - |
| FA | P.Appel Direct | Logical | 1x parametre entrant |
| FB | P. Sans annulations | Logical | - |

### 11.2 Variables de session (2)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| FN | v. Libelle edition | Alpha | - |
| FO | v. Libelle Categ | Alpha | - |

### 11.3 Variables de travail (13)

Variables internes au programme.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| FC | W0 nom | Alpha | - |
| FD | W0 prenom | Alpha | - |
| FE | W0 titre | Alpha | - |
| FF | W0 n° adherent | Numeric | - |
| FG | W0 lettre contrôle | Alpha | - |
| FH | W0 filiation | Numeric | - |
| FI | W0 langue parlee | Alpha | - |
| FJ | W0 chambre | Alpha | - |
| FK | W0 Date Début Séjour | Date | - |
| FL | W0 Date Fin Séjour | Date | - |
| FM | W0 code inscription | Unicode | - |
| FP | W0 masque extrait | Alpha | - |
| FQ | W0 devise local | Alpha | - |

<details>
<summary>Toutes les 30 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| P0 | **EN** | P0 societe | Alpha |
| P0 | **EO** | P0 code adherent | Numeric |
| P0 | **EP** | P0 filiation | Numeric |
| P0 | **EQ** | P0 masque montant | Alpha |
| P0 | **ER** | P0 nom village | Alpha |
| P0 | **ES** | P0 fictif | Logical |
| P0 | **ET** | P0 date comptable | Date |
| P0 | **EU** | P0 Edtion Tva V2 | Logical |
| P0 | **EV** | P.FormatPdf | Logical |
| P0 | **EW** | P.Chemin | Alpha |
| P0 | **EX** | P.NomFichierPdf | Alpha |
| P0 | **EY** | P.Print or Email | Alpha |
| P0 | **EZ** | P.Print GIFT PASS | Logical |
| P0 | **FA** | P.Appel Direct | Logical |
| P0 | **FB** | P. Sans annulations | Logical |
| W0 | **FC** | W0 nom | Alpha |
| W0 | **FD** | W0 prenom | Alpha |
| W0 | **FE** | W0 titre | Alpha |
| W0 | **FF** | W0 n° adherent | Numeric |
| W0 | **FG** | W0 lettre contrôle | Alpha |
| W0 | **FH** | W0 filiation | Numeric |
| W0 | **FI** | W0 langue parlee | Alpha |
| W0 | **FJ** | W0 chambre | Alpha |
| W0 | **FK** | W0 Date Début Séjour | Date |
| W0 | **FL** | W0 Date Fin Séjour | Date |
| W0 | **FM** | W0 code inscription | Unicode |
| W0 | **FP** | W0 masque extrait | Alpha |
| W0 | **FQ** | W0 devise local | Alpha |
| V. | **FN** | v. Libelle edition | Alpha |
| V. | **FO** | v. Libelle Categ | Alpha |

</details>

## 12. EXPRESSIONS

**13 / 13 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCULATION | 1 | 0 |
| CONDITION | 4 | 4 |
| CONSTANTE | 2 | 0 |
| OTHER | 5 | 0 |
| CAST_LOGIQUE | 1 | 0 |

### 12.2 Expressions cles par type

#### CALCULATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 5 | `Left (P0 masque montant [D],Len (RTrim (P0 masque montant [D]))-1)` | - |

#### CONDITION (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 7 | `GetParam ('CURRENTPRINTERNUM')=8` | [RM-003](#rm-RM-003) |
| CONDITION | 8 | `GetParam ('CURRENTPRINTERNUM')=9` | [RM-004](#rm-RM-004) |
| CONDITION | 2 | `IsComponent () AND NOT(P.Appel Direct [N])` | [RM-001](#rm-RM-001) |
| CONDITION | 6 | `GetParam ('CURRENTPRINTERNUM')=1` | [RM-002](#rm-RM-002) |

#### CONSTANTE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 12 | `'Par Service / By Service'` | - |
| CONSTANTE | 11 | `'Extrait de compte / Account statement'` | - |

#### OTHER (5 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 9 | `DbDel ('{867,4}'DSOURCE,'')` | - |
| OTHER | 10 | `NOT(P.FormatPdf [I])` | - |
| OTHER | 4 | `SetCrsr (2)` | - |
| OTHER | 1 | `GetParam ('LISTINGNUMPRINTERCHOICE')` | - |
| OTHER | 3 | `SetCrsr (1)` | - |

#### CAST_LOGIQUE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 13 | `'TRUE'LOG` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Extrait Easy Check Out à J+1 (IDE 53)](ADH-IDE-53.md) -> **Print extrait compte /Service (IDE 76)**

Main -> ... -> [Extrait de compte (IDE 69)](ADH-IDE-69.md) -> **Print extrait compte /Service (IDE 76)**

```mermaid
graph LR
    T76[76 Print extrait compt...]
    style T76 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC163[163 Menu caisse GM - s...]
    style CC163 fill:#f59e0b
    CC53[53 Extrait Easy Check ...]
    style CC53 fill:#3fb950
    CC69[69 Extrait de compte]
    style CC69 fill:#3fb950
    CC163 --> CC53
    CC163 --> CC69
    CC1 --> CC163
    CC53 --> T76
    CC69 --> T76
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [53](ADH-IDE-53.md) | Extrait Easy Check Out à J+1 | 1 |
| [69](ADH-IDE-69.md) | Extrait de compte | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T76[76 Print extrait compt...]
    style T76 fill:#58a6ff
    C75[75 Creation Pied Facture]
    T76 --> C75
    style C75 fill:#3fb950
    C21[21 Recupere devise local]
    T76 --> C21
    style C21 fill:#3fb950
    C179[179 Get Printer]
    T76 --> C179
    style C179 fill:#3fb950
    C181[181 Set Listing Number]
    T76 --> C181
    style C181 fill:#3fb950
    C182[182 Raz Current Printer]
    T76 --> C182
    style C182 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [75](ADH-IDE-75.md) | Creation Pied Facture | 4 | Sous-programme |
| [21](ADH-IDE-21.md) | Recupere devise local | 1 | Recuperation donnees |
| [179](ADH-IDE-179.md) | Get Printer | 1 | Impression ticket/document |
| [181](ADH-IDE-181.md) | Set Listing Number | 1 | Configuration impression |
| [182](ADH-IDE-182.md) | Raz Current Printer | 1 | Impression ticket/document |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 626 | Programme volumineux |
| Expressions | 13 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 5 | Peu de dependances |
| Ecrans visibles | 3 | Quelques ecrans |
| Code desactive | 0.2% (1 / 626) | Code sain |
| Regles metier | 4 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (4 taches: 3 ecrans, 1 traitement)

- **Strategie** : Orchestrateur avec 3 ecrans (Razor/React) et 1 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 5 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Impression (13 taches: 2 ecrans, 11 traitements)

- **Strategie** : Templates HTML -> PDF via wkhtmltopdf ou Puppeteer.
- `PrintService` injectable avec choix imprimante

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| log_maj_tpe | Table WRITE (Database) | 4x | Schema + repository |
| [Creation Pied Facture (IDE 75)](ADH-IDE-75.md) | Sous-programme | 4x | **CRITIQUE** - Sous-programme |
| [Set Listing Number (IDE 181)](ADH-IDE-181.md) | Sous-programme | 1x | Normale - Configuration impression |
| [Raz Current Printer (IDE 182)](ADH-IDE-182.md) | Sous-programme | 1x | Normale - Impression ticket/document |
| [Recupere devise local (IDE 21)](ADH-IDE-21.md) | Sous-programme | 1x | Normale - Recuperation donnees |
| [Get Printer (IDE 179)](ADH-IDE-179.md) | Sous-programme | 1x | Normale - Impression ticket/document |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-08 02:14*
