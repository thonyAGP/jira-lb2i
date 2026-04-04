# WEL IDE 114 - Print extrait compte /Imp

> **Analyse**: Phases 1-4 2026-02-03 21:51 -> 21:51 (21s) | Assemblage 21:51
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | WEL |
| IDE Position | 114 |
| Nom Programme | Print extrait compte /Imp |
| Fichier source | `Prg_114.xml` |
| Dossier IDE | A |
| Taches | 9 (1 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 1 |
| :warning: Statut | **ORPHELIN_POTENTIEL** |

## 2. DESCRIPTION FONCTIONNELLE

**Print extrait compte /Imp** assure la gestion complete de ce processus.

Le flux de traitement s'organise en **2 blocs fonctionnels** :

- **Impression** (7 taches) : generation de tickets et documents
- **Traitement** (2 taches) : traitements metier divers

**Donnees modifiees** : 1 tables en ecriture (Ventilation_Lg_Vente).

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (2 taches)

- **114** - Veuillez patienter... **[[ECRAN]](#ecran-t1)**
- **114.2** - recup nom adherent

#### Phase 2 : Impression (7 taches)

- **114.1** - Printer 1
- **114.1.1** - edition extrait compte
- **114.1.1.1** - Edition du pied
- **114.1.1.2** - Edition recap Free Etra
- **114.1.2** - edition extrait compte
- **114.1.2.1** - Edition du pied
- **114.1.2.2** - Edition recap Free Etra

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| Ventilation_Lg_Vente | **W** (2 usages) | Donnees de ventes |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (2 taches)

Traitements internes.

---

#### <a id="t1"></a>114 - Veuillez patienter... [[ECRAN]](#ecran-t1)

**Role** : Traitement : Veuillez patienter....
**Ecran** : 422 x 56 DLU (MDI) | [Voir mockup](#ecran-t1)

---

#### <a id="t9"></a>114.2 - recup nom adherent

**Role** : Consultation/chargement : recup nom adherent.
**Variables liees** : B (P0 code adherent), K (W0 n° adherent)


### 3.2 Impression (7 taches)

Generation des documents et tickets.

---

#### <a id="t2"></a>114.1 - Printer 1

**Role** : Generation du document : Printer 1.

---

#### <a id="t3"></a>114.1.1 - edition extrait compte

**Role** : Generation du document : edition extrait compte.

---

#### <a id="t4"></a>114.1.1.1 - Edition du pied

**Role** : Generation du document : Edition du pied.

---

#### <a id="t5"></a>114.1.1.2 - Edition recap Free Etra

**Role** : Generation du document : Edition recap Free Etra.

---

#### <a id="t6"></a>114.1.2 - edition extrait compte

**Role** : Generation du document : edition extrait compte.

---

#### <a id="t7"></a>114.1.2.1 - Edition du pied

**Role** : Generation du document : Edition du pied.

---

#### <a id="t8"></a>114.1.2.2 - Edition recap Free Etra

**Role** : Generation du document : Edition recap Free Etra.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: (aucun)
- **Appelle**: 1 programmes | **Tables**: 7 (W:1 R:3 L:4) | **Taches**: 9 | **Expressions**: 9

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 9)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 114 | 114 | Veuillez patienter... | MDI | 422 | 56 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>114 - Veuillez patienter...
**Tache** : [114](#t1) | **Type** : MDI | **Dimensions** : 422 x 56 DLU
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
    "taskId":  "114",
    "height":  56
}
-->

## 9. NAVIGATION

Ecran unique: **Veuillez patienter...**

### 9.3 Structure hierarchique (9 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **114.1** | [**Veuillez patienter...** (114)](#t1) [mockup](#ecran-t1) | MDI | 422x56 | Traitement |
| 114.1.1 | [recup nom adherent (114.2)](#t9) | MDI | - | |
| **114.2** | [**Printer 1** (114.1)](#t2) | MDI | - | Impression |
| 114.2.1 | [edition extrait compte (114.1.1)](#t3) | MDI | - | |
| 114.2.2 | [Edition du pied (114.1.1.1)](#t4) | - | - | |
| 114.2.3 | [Edition recap Free Etra (114.1.1.2)](#t5) | - | - | |
| 114.2.4 | [edition extrait compte (114.1.2)](#t6) | MDI | - | |
| 114.2.5 | [Edition du pied (114.1.2.1)](#t7) | - | - | |
| 114.2.6 | [Edition recap Free Etra (114.1.2.2)](#t8) | - | - | |

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

### Tables utilisees (7)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 30 | gm-recherche_____gmr | Index de recherche | DB | R |   |   | 3 |
| 31 | gm-complet_______gmc |  | DB | R |   | L | 3 |
| 34 | hebergement______heb | Hebergement (chambres) | DB |   |   | L | 1 |
| 40 | comptable________cte |  | DB |   |   | L | 4 |
| 368 | pms_village |  | DB | R |   |   | 1 |
| 821 | Ventilation_Lg_Vente | Donnees de ventes | DB |   | **W** |   | 2 |
| 870 | Rayons_Boutique |  | DB |   |   | L | 1 |

### Colonnes par table (2 / 4 tables avec colonnes identifiees)

<details>
<summary>Table 30 - gm-recherche_____gmr (R) - 3 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | W1 cumul compte | R | Numeric |
| B | W1 solde compte | R | Numeric |
| C | W1 ss_total compte | R | Numeric |
| D | v.retour offre | R | Logical |

</details>

<details>
<summary>Table 31 - gm-complet_______gmc (R/L) - 3 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 368 - pms_village (R) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 821 - Ventilation_Lg_Vente (**W**) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (7)

Variables recues en parametre.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P0 societe | Alpha | - |
| B | P0 code adherent | Numeric | [114.2](#t9) |
| C | P0 filiation | Numeric | 1x parametre entrant |
| D | P0 date comptable | Date | - |
| E | P0 Edtion Tva V2 | Logical | - |
| F | P0.Print_Email | Unicode | 1x parametre entrant |
| G | P0.NomFichier | Unicode | 1x parametre entrant |

### 11.2 Variables de travail (9)

Variables internes au programme.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| H | W0 nom | Alpha | - |
| I | W0 prenom | Alpha | - |
| J | W0 titre | Alpha | - |
| K | W0 n° adherent | Numeric | - |
| L | W0 lettre contrôle | Alpha | - |
| M | W0 filiation | Numeric | - |
| N | W0 langue parlee | Alpha | - |
| O | W0 chambre | Alpha | - |
| P | W0 devise local | Alpha | - |

### 11.3 Autres (1)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| Q | v0.Chemin | Alpha | 1x refs |

<details>
<summary>Toutes les 17 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| P0 | **A** | P0 societe | Alpha |
| P0 | **B** | P0 code adherent | Numeric |
| P0 | **C** | P0 filiation | Numeric |
| P0 | **D** | P0 date comptable | Date |
| P0 | **E** | P0 Edtion Tva V2 | Logical |
| P0 | **F** | P0.Print_Email | Unicode |
| P0 | **G** | P0.NomFichier | Unicode |
| W0 | **H** | W0 nom | Alpha |
| W0 | **I** | W0 prenom | Alpha |
| W0 | **J** | W0 titre | Alpha |
| W0 | **K** | W0 n° adherent | Numeric |
| W0 | **L** | W0 lettre contrôle | Alpha |
| W0 | **M** | W0 filiation | Numeric |
| W0 | **N** | W0 langue parlee | Alpha |
| W0 | **O** | W0 chambre | Alpha |
| W0 | **P** | W0 devise local | Alpha |
| Autre | **Q** | v0.Chemin | Alpha |

</details>

## 12. EXPRESSIONS

**9 / 9 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| FORMAT | 1 | 0 |
| OTHER | 4 | 0 |
| REFERENCE_VG | 1 | 0 |
| CONDITION | 1 | 0 |
| CONCATENATION | 1 | 0 |
| STRING | 1 | 0 |

### 12.2 Expressions cles par type

#### FORMAT (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| FORMAT | 9 | `'EXTRAIT_IMP_'&Trim(Str(P0 code adherent [B],'8P0'))&'_'&Trim(Str(P0 filiation [C],'##'))&'_'&Trim(VG15)&'_'&DStr(Date(),'YYMMDD')&TStr(Time(),'HHMMSS')&'.pdf'` | - |

#### OTHER (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 3 | `DbDel ('{821,4}'DSOURCE,'')` | - |
| OTHER | 7 | `Translate('%club_exportdata%')&'WELCOME\'` | - |
| OTHER | 1 | `SetCrsr (1)` | - |
| OTHER | 2 | `SetCrsr (2)` | - |

#### REFERENCE_VG (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 4 | `VG54` | - |

#### CONDITION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 6 | `P0.Print_Email [F]='P'` | - |

#### CONCATENATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 5 | `Trim(v0.Chemin [Q])&Trim(P0.NomFichier [G])` | - |

#### STRING (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| STRING | 8 | `Trim(VG67)` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

**Chemin**: (pas de callers directs)

```mermaid
graph LR
    T114[114 Print extrait comp...]
    style T114 fill:#58a6ff
    NONE[Aucun caller]
    NONE -.-> T114
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| - | (aucun) | - |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T114[114 Print extrait comp...]
    style T114 fill:#58a6ff
    C25[25 Creation Pied Facture]
    T114 --> C25
    style C25 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [25](WEL-IDE-25.md) | Creation Pied Facture | 2 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 294 | Taille moyenne |
| Expressions | 9 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 1 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 1% (3 / 294) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (2 taches: 1 ecran, 1 traitement)

- **Strategie** : Orchestrateur avec 1 ecrans (Razor/React) et 1 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 1 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Impression (7 taches: 0 ecran, 7 traitements)

- **Strategie** : Templates HTML -> PDF via wkhtmltopdf ou Puppeteer.
- `PrintService` injectable avec choix imprimante

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| Ventilation_Lg_Vente | Table WRITE (Database) | 2x | Schema + repository |
| [Creation Pied Facture (IDE 25)](WEL-IDE-25.md) | Sous-programme | 2x | Haute - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 21:51*
