# ADH IDE 70 - Print extrait compte /Nom

> **Analyse**: Phases 1-4 2026-02-08 00:49 -> 02:06 (1h17min) | Assemblage 02:06
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | ADH |
| IDE Position | 70 |
| Nom Programme | Print extrait compte /Nom |
| Fichier source | `Prg_70.xml` |
| Dossier IDE | Comptabilite |
| Taches | 19 (0 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 5 |
| Complexite | **BASSE** (score 25/100) |

## 2. DESCRIPTION FONCTIONNELLE

**ADH IDE 70** imprime l'extrait de compte d'un adhérent Club Med trié par **ordre alphabétique (nom)**. C'est un programme de traitement batch appelé depuis IDE 69 (Extrait de compte), conçu pour gérer le formatage et la distribution multi-imprimante des documents de facturation. Le flux suit trois phases : initialisation des données du titulaire via IDE 21 (devise) et IDE 181 (numérotation), édition du document principal sur imprimante sélectionnée (appels multiples à IDE 75 pour calcul fiscal), et traçabilité via mise à jour de la table d'audit `log_maj_tpe` (4 écritures). Le programme gère 4 variantes d'imprimantes (1, 6, 8, 9) avec chacune ses sous-tâches d'édition pied de facture et récapitulatif (Free Extract ou Gift Pass selon imprimante 9).

Structurellement, le programme comprend 19 tâches réparties entre écrans d'attente, blocs d'impression, et traitements invisibles de calcul. Ses 15 paramètres d'entrée (code adhérent, filiation, société, dates comptables, etc.) configurent entièrement le traitement sans branchements complexes. La table `log_maj_tpe` enregistre systématiquement les éditions pour audit, tandis que 7 autres tables (comptable, gm-complet, type de lit, paramètres TVA) fournissent les données en lecture. Aucune gestion d'erreur explicite : les appels aux IDE 21, 75, 179, 181, 182 gèrent eux-mêmes leurs exceptions.

Le programme est **critique pour la migration** car il représente un pattern courant : édition multi-formats avec calcul fiscal et traçabilité. Sa complexité basse (25/100), absence de code mort, et absence d'orphelinat en font un candidat idéal pour validation de la première génération de migration vers API .NET/TypeScript, particulièrement pour le module Ventes/Extraits (ADH IDE 237-250 déjà migrées).

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (5 taches)

Traitements internes.

---

#### <a id="t1"></a>70 - Veuillez patienter... [[ECRAN]](#ecran-t1)

**Role** : Traitement : Veuillez patienter....
**Ecran** : 422 x 56 DLU (MDI) | [Voir mockup](#ecran-t1)

<details>
<summary>4 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [70.1](#t2) | recup nom adherent | Traitement |
| [70.3.1](#t11) | Veuillez pateinter... **[[ECRAN]](#ecran-t11)** | Traitement |
| [70.4.1](#t13) | Veuillez pateinter... **[[ECRAN]](#ecran-t13)** | Traitement |
| [70.5.1](#t17) | Veuillez pateinter... **[[ECRAN]](#ecran-t17)** | Traitement |

</details>
**Delegue a** : [Recupere devise local (IDE 21)](ADH-IDE-21.md), [Set Listing Number (IDE 181)](ADH-IDE-181.md)

---

#### <a id="t2"></a>70.1 - recup nom adherent

**Role** : Consultation/chargement : recup nom adherent.
**Variables liees** : EO (P0 code adherent), FF (W0 n° adherent)
**Delegue a** : [Recupere devise local (IDE 21)](ADH-IDE-21.md), [Set Listing Number (IDE 181)](ADH-IDE-181.md)

---

#### <a id="t11"></a>70.3.1 - Veuillez pateinter... [[ECRAN]](#ecran-t11)

**Role** : Traitement : Veuillez pateinter....
**Ecran** : 422 x 56 DLU (MDI) | [Voir mockup](#ecran-t11)
**Delegue a** : [Recupere devise local (IDE 21)](ADH-IDE-21.md), [Set Listing Number (IDE 181)](ADH-IDE-181.md)

---

#### <a id="t13"></a>70.4.1 - Veuillez pateinter... [[ECRAN]](#ecran-t13)

**Role** : Traitement : Veuillez pateinter....
**Ecran** : 422 x 56 DLU (MDI) | [Voir mockup](#ecran-t13)
**Delegue a** : [Recupere devise local (IDE 21)](ADH-IDE-21.md), [Set Listing Number (IDE 181)](ADH-IDE-181.md)

---

#### <a id="t17"></a>70.5.1 - Veuillez pateinter... [[ECRAN]](#ecran-t17)

**Role** : Traitement : Veuillez pateinter....
**Ecran** : 422 x 56 DLU (MDI) | [Voir mockup](#ecran-t17)
**Delegue a** : [Recupere devise local (IDE 21)](ADH-IDE-21.md), [Set Listing Number (IDE 181)](ADH-IDE-181.md)


### 3.2 Impression (14 taches)

Generation des documents et tickets.

---

#### <a id="t3"></a>70.2 - Printer 1 [[ECRAN]](#ecran-t3)

**Role** : Generation du document : Printer 1.
**Ecran** : 1058 x 791 DLU (MDI) | [Voir mockup](#ecran-t3)

---

#### <a id="t4"></a>70.2.1 - edition extrait compte [[ECRAN]](#ecran-t4)

**Role** : Generation du document : edition extrait compte.
**Ecran** : 1058 x 791 DLU (MDI) | [Voir mockup](#ecran-t4)
**Variables liees** : FP (W0 masque extrait), FN (v. Libelle edition)

---

#### <a id="t5"></a>70.2.1.1 - Edition du pied

**Role** : Generation du document : Edition du pied.
**Variables liees** : FN (v. Libelle edition)

---

#### <a id="t6"></a>70.2.1.2 - Edition recap Free Etra

**Role** : Generation du document : Edition recap Free Etra.
**Variables liees** : FN (v. Libelle edition)

---

#### <a id="t7"></a>70.2.2 - edition extrait compte [[ECRAN]](#ecran-t7)

**Role** : Generation du document : edition extrait compte.
**Ecran** : 1058 x 791 DLU (MDI) | [Voir mockup](#ecran-t7)
**Variables liees** : FP (W0 masque extrait), FN (v. Libelle edition)

---

#### <a id="t8"></a>70.2.2.1 - Edition du pied

**Role** : Generation du document : Edition du pied.
**Variables liees** : FN (v. Libelle edition)

---

#### <a id="t9"></a>70.2.2.2 - Edition recap Free Etra

**Role** : Generation du document : Edition recap Free Etra.
**Variables liees** : FN (v. Libelle edition)

---

#### <a id="t10"></a>70.3 - Printer 6 [[ECRAN]](#ecran-t10)

**Role** : Generation du document : Printer 6.
**Ecran** : 422 x 56 DLU (MDI) | [Voir mockup](#ecran-t10)

---

#### <a id="t12"></a>70.4 - Printer 8 [[ECRAN]](#ecran-t12)

**Role** : Generation du document : Printer 8.
**Ecran** : 422 x 56 DLU (MDI) | [Voir mockup](#ecran-t12)

---

#### <a id="t14"></a>70.4.1.1 - Edition du pied

**Role** : Generation du document : Edition du pied.
**Variables liees** : FN (v. Libelle edition)

---

#### <a id="t15"></a>70.4.1.2 - Edition recap Free Etra

**Role** : Generation du document : Edition recap Free Etra.
**Variables liees** : FN (v. Libelle edition)

---

#### <a id="t16"></a>70.5 - Printer 9 [[ECRAN]](#ecran-t16)

**Role** : Generation du document : Printer 9.
**Ecran** : 422 x 56 DLU (MDI) | [Voir mockup](#ecran-t16)

---

#### <a id="t18"></a>70.5.1.1 - Edition du pied

**Role** : Generation du document : Edition du pied.
**Variables liees** : FN (v. Libelle edition)

---

#### <a id="t19"></a>70.5.1.2 - Edition recap Gift Pass

**Role** : Generation du document : Edition recap Gift Pass.
**Variables liees** : EZ (P.Print GIFT PASS), FN (v. Libelle edition)


## 5. REGLES METIER

5 regles identifiees:

### Impression (4 regles)

#### <a id="rm-RM-002"></a>[RM-002] Verification que l'imprimante courante est la n1

| Element | Detail |
|---------|--------|
| **Condition** | `GetParam ('CURRENTPRINTERNUM')=1` |
| **Si vrai** | Action si CURRENTPRINTERNUM = 1 |
| **Expression source** | Expression 6 : `GetParam ('CURRENTPRINTERNUM')=1` |
| **Exemple** | Si GetParam ('CURRENTPRINTERNUM')=1 â†’ Action si CURRENTPRINTERNUM = 1 |
| **Impact** | [70.2 - Printer 1](#t3) |

#### <a id="rm-RM-003"></a>[RM-003] Verification que l'imprimante courante est la n6

| Element | Detail |
|---------|--------|
| **Condition** | `GetParam ('CURRENTPRINTERNUM')=6` |
| **Si vrai** | Action si CURRENTPRINTERNUM = 6 |
| **Expression source** | Expression 7 : `GetParam ('CURRENTPRINTERNUM')=6` |
| **Exemple** | Si GetParam ('CURRENTPRINTERNUM')=6 â†’ Action si CURRENTPRINTERNUM = 6 |
| **Impact** | [70.2 - Printer 1](#t3) |

#### <a id="rm-RM-004"></a>[RM-004] Verification que l'imprimante courante est la n8

| Element | Detail |
|---------|--------|
| **Condition** | `GetParam ('CURRENTPRINTERNUM')=8` |
| **Si vrai** | Action si CURRENTPRINTERNUM = 8 |
| **Expression source** | Expression 8 : `GetParam ('CURRENTPRINTERNUM')=8` |
| **Exemple** | Si GetParam ('CURRENTPRINTERNUM')=8 â†’ Action si CURRENTPRINTERNUM = 8 |
| **Impact** | [70.2 - Printer 1](#t3) |

#### <a id="rm-RM-005"></a>[RM-005] Verification que l'imprimante courante est la n9

| Element | Detail |
|---------|--------|
| **Condition** | `GetParam ('CURRENTPRINTERNUM')=9` |
| **Si vrai** | Action si CURRENTPRINTERNUM = 9 |
| **Expression source** | Expression 9 : `GetParam ('CURRENTPRINTERNUM')=9` |
| **Exemple** | Si GetParam ('CURRENTPRINTERNUM')=9 â†’ Action si CURRENTPRINTERNUM = 9 |
| **Impact** | [70.2 - Printer 1](#t3) |

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

- **Appele par**: [Extrait de compte (IDE 69)](ADH-IDE-69.md)
- **Appelle**: 5 programmes | **Tables**: 8 (W:1 R:3 L:7) | **Taches**: 19 | **Expressions**: 14

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (19 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **70.1** | [**Veuillez patienter...** (70)](#t1) [mockup](#ecran-t1) | MDI | 422x56 | Traitement |
| 70.1.1 | [recup nom adherent (70.1)](#t2) | MDI | - | |
| 70.1.2 | [Veuillez pateinter... (70.3.1)](#t11) [mockup](#ecran-t11) | MDI | 422x56 | |
| 70.1.3 | [Veuillez pateinter... (70.4.1)](#t13) [mockup](#ecran-t13) | MDI | 422x56 | |
| 70.1.4 | [Veuillez pateinter... (70.5.1)](#t17) [mockup](#ecran-t17) | MDI | 422x56 | |
| **70.2** | [**Printer 1** (70.2)](#t3) [mockup](#ecran-t3) | MDI | 1058x791 | Impression |
| 70.2.1 | [edition extrait compte (70.2.1)](#t4) [mockup](#ecran-t4) | MDI | 1058x791 | |
| 70.2.2 | [Edition du pied (70.2.1.1)](#t5) | - | - | |
| 70.2.3 | [Edition recap Free Etra (70.2.1.2)](#t6) | - | - | |
| 70.2.4 | [edition extrait compte (70.2.2)](#t7) [mockup](#ecran-t7) | MDI | 1058x791 | |
| 70.2.5 | [Edition du pied (70.2.2.1)](#t8) | - | - | |
| 70.2.6 | [Edition recap Free Etra (70.2.2.2)](#t9) | - | - | |
| 70.2.7 | [Printer 6 (70.3)](#t10) [mockup](#ecran-t10) | MDI | 422x56 | |
| 70.2.8 | [Printer 8 (70.4)](#t12) [mockup](#ecran-t12) | MDI | 422x56 | |
| 70.2.9 | [Edition du pied (70.4.1.1)](#t14) | - | - | |
| 70.2.10 | [Edition recap Free Etra (70.4.1.2)](#t15) | - | - | |
| 70.2.11 | [Printer 9 (70.5)](#t16) [mockup](#ecran-t16) | MDI | 422x56 | |
| 70.2.12 | [Edition du pied (70.5.1.1)](#t18) | - | - | |
| 70.2.13 | [Edition recap Gift Pass (70.5.1.2)](#t19) | - | - | |

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

### Tables utilisees (8)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 867 | log_maj_tpe |  | DB |   | **W** |   | 4 |
| 40 | comptable________cte |  | DB | R |   | L | 9 |
| 31 | gm-complet_______gmc |  | DB | R |   | L | 9 |
| 30 | gm-recherche_____gmr | Index de recherche | DB | R |   | L | 6 |
| 928 | type_lit |  | DB |   |   | L | 2 |
| 413 | pv_tva |  | DB |   |   | L | 1 |
| 400 | pv_cust_rentals |  | DB |   |   | L | 1 |
| 34 | hebergement______heb | Hebergement (chambres) | DB |   |   | L | 1 |

### Colonnes par table (1 / 4 tables avec colonnes identifiees)

<details>
<summary>Table 867 - log_maj_tpe (**W**) - 4 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 40 - comptable________cte (R/L) - 9 usages</summary>

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
<summary>Table 31 - gm-complet_______gmc (R/L) - 9 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 30 - gm-recherche_____gmr (R/L) - 6 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (15)

Variables recues du programme appelant ([Extrait de compte (IDE 69)](ADH-IDE-69.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| EN | P0 societe | Alpha | - |
| EO | P0 code adherent | Numeric | - |
| EP | P0 filiation | Numeric | - |
| EQ | P0 masque montant | Alpha | 1x parametre entrant |
| ER | P0 nom village | Alpha | - |
| ES | P0 Fictif | Logical | - |
| ET | P0 date comptable | Date | - |
| EU | P0 Affichage Tva ? | Logical | - |
| EV | P.FormatPDF | Logical | - |
| EW | P.Chemin | Alpha | - |
| EX | p.NomFichierPDF | Alpha | - |
| EY | P.Print or Mail | Alpha | - |
| EZ | P.Print GIFT PASS | Logical | - |
| FA | P.Appel Direct | Logical | 1x parametre entrant |
| FB | P. Sans annulations ? | Logical | - |

### 11.2 Variables de session (2)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| FN | v. Libelle edition | Alpha | - |
| FO | v. Libelle Categ | Alpha | - |

### 11.3 Variables de travail (14)

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
| FK | W0 D.Sejour Debut | Date | - |
| FL | W0 D.Sejour Fin | Date | - |
| FM | W0 code inscription | Unicode | - |
| FP | W0 masque extrait | Alpha | - |
| FQ | W0 devise locale | Alpha | - |
| FR | W0.Nombre de copies | Numeric | - |

<details>
<summary>Toutes les 31 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| P0 | **EN** | P0 societe | Alpha |
| P0 | **EO** | P0 code adherent | Numeric |
| P0 | **EP** | P0 filiation | Numeric |
| P0 | **EQ** | P0 masque montant | Alpha |
| P0 | **ER** | P0 nom village | Alpha |
| P0 | **ES** | P0 Fictif | Logical |
| P0 | **ET** | P0 date comptable | Date |
| P0 | **EU** | P0 Affichage Tva ? | Logical |
| P0 | **EV** | P.FormatPDF | Logical |
| P0 | **EW** | P.Chemin | Alpha |
| P0 | **EX** | p.NomFichierPDF | Alpha |
| P0 | **EY** | P.Print or Mail | Alpha |
| P0 | **EZ** | P.Print GIFT PASS | Logical |
| P0 | **FA** | P.Appel Direct | Logical |
| P0 | **FB** | P. Sans annulations ? | Logical |
| W0 | **FC** | W0 nom | Alpha |
| W0 | **FD** | W0 prenom | Alpha |
| W0 | **FE** | W0 titre | Alpha |
| W0 | **FF** | W0 n° adherent | Numeric |
| W0 | **FG** | W0 lettre contrôle | Alpha |
| W0 | **FH** | W0 filiation | Numeric |
| W0 | **FI** | W0 langue parlee | Alpha |
| W0 | **FJ** | W0 chambre | Alpha |
| W0 | **FK** | W0 D.Sejour Debut | Date |
| W0 | **FL** | W0 D.Sejour Fin | Date |
| W0 | **FM** | W0 code inscription | Unicode |
| W0 | **FP** | W0 masque extrait | Alpha |
| W0 | **FQ** | W0 devise locale | Alpha |
| W0 | **FR** | W0.Nombre de copies | Numeric |
| V. | **FN** | v. Libelle edition | Alpha |
| V. | **FO** | v. Libelle Categ | Alpha |

</details>

## 12. EXPRESSIONS

**14 / 14 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCULATION | 1 | 0 |
| CONDITION | 5 | 5 |
| CONSTANTE | 2 | 0 |
| OTHER | 5 | 0 |
| CAST_LOGIQUE | 1 | 0 |

### 12.2 Expressions cles par type

#### CALCULATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 5 | `Left (P0 masque montant [D],Len (RTrim (P0 masque montant [D]))-1)` | - |

#### CONDITION (5 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 8 | `GetParam ('CURRENTPRINTERNUM')=8` | [RM-004](#rm-RM-004) |
| CONDITION | 9 | `GetParam ('CURRENTPRINTERNUM')=9` | [RM-005](#rm-RM-005) |
| CONDITION | 7 | `GetParam ('CURRENTPRINTERNUM')=6` | [RM-003](#rm-RM-003) |
| CONDITION | 2 | `IsComponent () AND NOT(P.Appel Direct [N])` | [RM-001](#rm-RM-001) |
| CONDITION | 6 | `GetParam ('CURRENTPRINTERNUM')=1` | [RM-002](#rm-RM-002) |

#### CONSTANTE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 12 | `'Par Nom / By Name'` | - |
| CONSTANTE | 11 | `'Extrait de compte/Account statement'` | - |

#### OTHER (5 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 10 | `DbDel ('{867,4}'DSOURCE,'')` | - |
| OTHER | 14 | `GetParam ('NUMBERCOPIES')` | - |
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

Main -> ... -> [Extrait de compte (IDE 69)](ADH-IDE-69.md) -> **Print extrait compte /Nom (IDE 70)**

```mermaid
graph LR
    T70[70 Print extrait compt...]
    style T70 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC163[163 Menu caisse GM - s...]
    style CC163 fill:#f59e0b
    CC69[69 Extrait de compte]
    style CC69 fill:#3fb950
    CC163 --> CC69
    CC1 --> CC163
    CC69 --> T70
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [69](ADH-IDE-69.md) | Extrait de compte | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T70[70 Print extrait compt...]
    style T70 fill:#58a6ff
    C75[75 Creation Pied Facture]
    T70 --> C75
    style C75 fill:#3fb950
    C21[21 Recupere devise local]
    T70 --> C21
    style C21 fill:#3fb950
    C179[179 Get Printer]
    T70 --> C179
    style C179 fill:#3fb950
    C181[181 Set Listing Number]
    T70 --> C181
    style C181 fill:#3fb950
    C182[182 Raz Current Printer]
    T70 --> C182
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
| Lignes de logique | 700 | Programme volumineux |
| Expressions | 14 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 5 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 700) | Code sain |
| Regles metier | 5 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (5 taches: 4 ecrans, 1 traitement)

- **Strategie** : Orchestrateur avec 4 ecrans (Razor/React) et 1 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 5 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Impression (14 taches: 6 ecrans, 8 traitements)

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
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-08 02:08*
