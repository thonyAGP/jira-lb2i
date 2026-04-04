# WEL IDE 112 - Print extrait compte /Date

> **Analyse**: Phases 1-4 2026-02-03 21:50 -> 21:50 (19s) | Assemblage 21:50
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | WEL |
| IDE Position | 112 |
| Nom Programme | Print extrait compte /Date |
| Fichier source | `Prg_112.xml` |
| Dossier IDE | A |
| Taches | 7 (1 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 1 |
| :warning: Statut | **ORPHELIN_POTENTIEL** |

## 2. DESCRIPTION FONCTIONNELLE

**Print extrait compte /Date** assure la gestion complete de ce processus.

Le flux de traitement s'organise en **2 blocs fonctionnels** :

- **Impression** (5 taches) : generation de tickets et documents
- **Traitement** (2 taches) : traitements metier divers

**Donnees modifiees** : 1 tables en ecriture (Ventilation_Lg_Vente).

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (2 taches)

- **112** - Veuillez patienter... **[[ECRAN]](#ecran-t1)**
- **112.1** - recup nom adherent

#### Phase 2 : Impression (5 taches)

- **112.2** - Printer
- **112.2.1** - edition extrait compte
- **112.2.2** - edition extrait compte
- **112.2.2.1** - Edition du pied
- **112.2.2.2** - Edition recap Free Etra

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| Ventilation_Lg_Vente | **W** (1 usages) | Donnees de ventes |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (2 taches)

Traitements internes.

---

#### <a id="t1"></a>112 - Veuillez patienter... [[ECRAN]](#ecran-t1)

**Role** : Traitement : Veuillez patienter....
**Ecran** : 424 x 57 DLU (MDI) | [Voir mockup](#ecran-t1)

---

#### <a id="t2"></a>112.1 - recup nom adherent

**Role** : Consultation/chargement : recup nom adherent.
**Variables liees** : J (W0 nom adherent), K (W0 prenom adherent), L (W0 n° adherent)


### 3.2 Impression (5 taches)

Generation des documents et tickets.

---

#### <a id="t3"></a>112.2 - Printer

**Role** : Generation du document : Printer.

---

#### <a id="t4"></a>112.2.1 - edition extrait compte

**Role** : Generation du document : edition extrait compte.
**Variables liees** : B (P0 n° compte), E (P0 edition Tva V2)

---

#### <a id="t5"></a>112.2.2 - edition extrait compte

**Role** : Generation du document : edition extrait compte.
**Variables liees** : B (P0 n° compte), E (P0 edition Tva V2)

---

#### <a id="t6"></a>112.2.2.1 - Edition du pied

**Role** : Generation du document : Edition du pied.
**Variables liees** : E (P0 edition Tva V2)

---

#### <a id="t7"></a>112.2.2.2 - Edition recap Free Etra

**Role** : Generation du document : Edition recap Free Etra.
**Variables liees** : E (P0 edition Tva V2)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: (aucun)
- **Appelle**: 1 programmes | **Tables**: 6 (W:1 R:3 L:4) | **Taches**: 7 | **Expressions**: 10

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 7)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 112 | 112 | Veuillez patienter... | MDI | 424 | 57 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>112 - Veuillez patienter...
**Tache** : [112](#t1) | **Type** : MDI | **Dimensions** : 424 x 57 DLU
**Bloc** : Traitement | **Titre IDE** : Veuillez patienter...

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
                         "x":  52,
                         "type":  "label",
                         "var":  "",
                         "y":  38,
                         "w":  318,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Impression de l\u0027extrait de compte",
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
    "taskId":  "112",
    "height":  57
}
-->

## 9. NAVIGATION

Ecran unique: **Veuillez patienter...**

### 9.3 Structure hierarchique (7 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **112.1** | [**Veuillez patienter...** (112)](#t1) [mockup](#ecran-t1) | MDI | 424x57 | Traitement |
| 112.1.1 | [recup nom adherent (112.1)](#t2) | MDI | - | |
| **112.2** | [**Printer** (112.2)](#t3) | MDI | - | Impression |
| 112.2.1 | [edition extrait compte (112.2.1)](#t4) | MDI | - | |
| 112.2.2 | [edition extrait compte (112.2.2)](#t5) | MDI | - | |
| 112.2.3 | [Edition du pied (112.2.2.1)](#t6) | - | - | |
| 112.2.4 | [Edition recap Free Etra (112.2.2.2)](#t7) | - | - | |

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

### Tables utilisees (6)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 30 | gm-recherche_____gmr | Index de recherche | DB | R |   | L | 2 |
| 31 | gm-complet_______gmc |  | DB | R |   | L | 4 |
| 34 | hebergement______heb | Hebergement (chambres) | DB |   |   | L | 1 |
| 40 | comptable________cte |  | DB |   |   | L | 3 |
| 368 | pms_village |  | DB | R |   |   | 1 |
| 821 | Ventilation_Lg_Vente | Donnees de ventes | DB |   | **W** |   | 1 |

### Colonnes par table (2 / 4 tables avec colonnes identifiees)

<details>
<summary>Table 30 - gm-recherche_____gmr (R/L) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 31 - gm-complet_______gmc (R/L) - 4 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 368 - pms_village (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P0 societe | R | Alpha |
| B | P0 n° compte | R | Numeric |
| C | P0 filiation | R | Numeric |
| D | P0 date comptable | R | Date |
| E | P0 edition Tva V2 | R | Logical |
| F | P0.Print_Email | R | Unicode |
| G | P0.NomFichier | R | Alpha |
| H | W0 imprimante | R | Numeric |
| I | W0 titre | R | Alpha |
| J | W0 nom adherent | R | Alpha |
| K | W0 prenom adherent | R | Alpha |
| L | W0 n° adherent | R | Numeric |
| M | P0 langue parlee | R | Alpha |
| N | W0 lettre contrôle | R | Alpha |
| O | W0 filiation | R | Numeric |
| P | W0 chambre | R | Alpha |
| Q | W0 devise locale | R | Alpha |
| R | v.Chemin | R | Alpha |

</details>

<details>
<summary>Table 821 - Ventilation_Lg_Vente (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (8)

Variables recues en parametre.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P0 societe | Alpha | - |
| B | P0 n° compte | Numeric | [112.2.1](#t4), [112.2.2](#t5) |
| C | P0 filiation | Numeric | 1x parametre entrant |
| D | P0 date comptable | Date | - |
| E | P0 edition Tva V2 | Logical | - |
| F | P0.Print_Email | Unicode | 1x parametre entrant |
| G | P0.NomFichier | Alpha | 1x parametre entrant |
| M | P0 langue parlee | Alpha | - |

### 11.2 Variables de session (1)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| R | v.Chemin | Alpha | 1x session |

### 11.3 Variables de travail (9)

Variables internes au programme.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| H | W0 imprimante | Numeric | - |
| I | W0 titre | Alpha | - |
| J | W0 nom adherent | Alpha | - |
| K | W0 prenom adherent | Alpha | - |
| L | W0 n° adherent | Numeric | - |
| N | W0 lettre contrôle | Alpha | - |
| O | W0 filiation | Numeric | - |
| P | W0 chambre | Alpha | - |
| Q | W0 devise locale | Alpha | - |

<details>
<summary>Toutes les 18 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| P0 | **A** | P0 societe | Alpha |
| P0 | **B** | P0 n° compte | Numeric |
| P0 | **C** | P0 filiation | Numeric |
| P0 | **D** | P0 date comptable | Date |
| P0 | **E** | P0 edition Tva V2 | Logical |
| P0 | **F** | P0.Print_Email | Unicode |
| P0 | **G** | P0.NomFichier | Alpha |
| P0 | **M** | P0 langue parlee | Alpha |
| W0 | **H** | W0 imprimante | Numeric |
| W0 | **I** | W0 titre | Alpha |
| W0 | **J** | W0 nom adherent | Alpha |
| W0 | **K** | W0 prenom adherent | Alpha |
| W0 | **L** | W0 n° adherent | Numeric |
| W0 | **N** | W0 lettre contrôle | Alpha |
| W0 | **O** | W0 filiation | Numeric |
| W0 | **P** | W0 chambre | Alpha |
| W0 | **Q** | W0 devise locale | Alpha |
| V. | **R** | v.Chemin | Alpha |

</details>

## 12. EXPRESSIONS

**10 / 10 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| FORMAT | 1 | 0 |
| OTHER | 4 | 0 |
| REFERENCE_VG | 2 | 0 |
| CONDITION | 1 | 0 |
| STRING | 1 | 0 |
| CONCATENATION | 1 | 0 |

### 12.2 Expressions cles par type

#### FORMAT (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| FORMAT | 9 | `'EXTRAIT_DAT_'&Trim(Str(P0 n° compte [B],'8P0'))&'_'&Trim(Str(P0 filiation [C],'##'))&'_'&Trim(VG15)&'_'&DStr(Date(),'YYMMDD')&TStr(Time(),'HHMMSS')&'.pdf'` | - |

#### OTHER (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 3 | `DbDel ('{821,4}'DSOURCE,'')` | - |
| OTHER | 7 | `Translate('%club_exportdata%')&'WELCOME\'` | - |
| OTHER | 1 | `SetCrsr (1)` | - |
| OTHER | 2 | `SetCrsr (2)` | - |

#### REFERENCE_VG (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 5 | `VG55` | - |
| REFERENCE_VG | 4 | `VG54` | - |

#### CONDITION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 6 | `P0.Print_Email [F]='P'` | - |

#### STRING (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| STRING | 8 | `Trim(VG67)` | - |

#### CONCATENATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 10 | `Trim(v.Chemin [R])&P0.NomFichier [G]` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

**Chemin**: (pas de callers directs)

```mermaid
graph LR
    T112[112 Print extrait comp...]
    style T112 fill:#58a6ff
    NONE[Aucun caller]
    NONE -.-> T112
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| - | (aucun) | - |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T112[112 Print extrait comp...]
    style T112 fill:#58a6ff
    C25[25 Creation Pied Facture]
    T112 --> C25
    style C25 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [25](WEL-IDE-25.md) | Creation Pied Facture | 1 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 219 | Taille moyenne |
| Expressions | 10 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 1 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0.9% (2 / 219) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (2 taches: 1 ecran, 1 traitement)

- **Strategie** : Orchestrateur avec 1 ecrans (Razor/React) et 1 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 1 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Impression (5 taches: 0 ecran, 5 traitements)

- **Strategie** : Templates HTML -> PDF via wkhtmltopdf ou Puppeteer.
- `PrintService` injectable avec choix imprimante

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| Ventilation_Lg_Vente | Table WRITE (Database) | 1x | Schema + repository |
| [Creation Pied Facture (IDE 25)](WEL-IDE-25.md) | Sous-programme | 1x | Normale - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 21:50*
