# ADH IDE 108 - Print annulation garantie

> **Analyse**: Phases 1-4 2026-02-07 03:49 -> 02:50 (23h01min) | Assemblage 02:50
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | ADH |
| IDE Position | 108 |
| Nom Programme | Print annulation garantie |
| Fichier source | `Prg_108.xml` |
| Dossier IDE | Garanties |
| Taches | 14 (1 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 1 |
| Complexite | **BASSE** (score 12/100) |

## 2. DESCRIPTION FONCTIONNELLE

ADH IDE 108 est un programme d'impression spécialisé dans l'annulation des garanties (cautions). Il gère l'édition et l'impression des documents de cancellation de dépôt de garantie pour un compte client. Le programme reçoit le contexte de la garantie depuis les programmes appelants (IDE 111, 112, 288) et prépare le ticket d'impression correspondant.

Le flux principal suit 6 tâches d'impression alternant entre initialisation du contrôleur d'impression (Printer 1, Printer 4) et édition des extraits de compte. Chaque séquence d'édition produit un document formaté contenant les détails de l'annulation - probablement le montant remboursé, la date, et les références du compte. Les appels répétés à l'édition d'extrait (3 fois) suggèrent une génération multi-copies ou des variantes de présentation du même document.

Le programme termine en appelant IDE 182 (Raz Current Printer) pour nettoyer l'état de l'imprimante après impression. C'est un programme de workflow classique d'édition-impression-réinitialisation, intégré dans la chaîne de gestion des garanties pour produire les documents de fin de dépôt.

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (4 taches)

Traitements internes.

---

#### <a id="t1"></a>108 - (sans nom)

**Role** : Traitement interne.

<details>
<summary>3 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [108.3](#t8) | Iteration **[[ECRAN]](#ecran-t8)** | Traitement |
| [108.3.1](#t9) | Veuillez patienter... **[[ECRAN]](#ecran-t9)** | Traitement |
| [108.4](#t10) | recup nom adherent | Traitement |

</details>

---

#### <a id="t8"></a>108.3 - Iteration [[ECRAN]](#ecran-t8)

**Role** : Traitement : Iteration.
**Ecran** : 422 x 56 DLU (MDI) | [Voir mockup](#ecran-t8)

---

#### <a id="t9"></a>108.3.1 - Veuillez patienter... [[ECRAN]](#ecran-t9)

**Role** : Traitement : Veuillez patienter....
**Ecran** : 422 x 56 DLU (MDI) | [Voir mockup](#ecran-t9)

---

#### <a id="t10"></a>108.4 - recup nom adherent

**Role** : Consultation/chargement : recup nom adherent.
**Variables liees** : EO (P0 code adherent), EU (W0 n° adherent)


### 3.2 Impression (10 taches)

Generation des documents et tickets.

---

#### <a id="t2"></a>108.1 - Printer 1

**Role** : Generation du document : Printer 1.
**Delegue a** : [Raz Current Printer (IDE 182)](ADH-IDE-182.md)

---

#### <a id="t3"></a>108.1.1 - edition extrait compte

**Role** : Generation du document : edition extrait compte.
**Delegue a** : [Raz Current Printer (IDE 182)](ADH-IDE-182.md)

---

#### <a id="t4"></a>108.1.2 - edition extrait compte

**Role** : Generation du document : edition extrait compte.
**Delegue a** : [Raz Current Printer (IDE 182)](ADH-IDE-182.md)

---

#### <a id="t5"></a>108.2 - Printer 4

**Role** : Generation du document : Printer 4.
**Delegue a** : [Raz Current Printer (IDE 182)](ADH-IDE-182.md)

---

#### <a id="t6"></a>108.2.1 - edition extrait compte

**Role** : Generation du document : edition extrait compte.
**Delegue a** : [Raz Current Printer (IDE 182)](ADH-IDE-182.md)

---

#### <a id="t7"></a>108.2.2 - edition extrait compte

**Role** : Generation du document : edition extrait compte.
**Delegue a** : [Raz Current Printer (IDE 182)](ADH-IDE-182.md)

---

#### <a id="t11"></a>108.5 - Printer 8

**Role** : Generation du document : Printer 8.
**Delegue a** : [Raz Current Printer (IDE 182)](ADH-IDE-182.md)

---

#### <a id="t12"></a>108.5.1 - edition extrait compte

**Role** : Generation du document : edition extrait compte.
**Delegue a** : [Raz Current Printer (IDE 182)](ADH-IDE-182.md)

---

#### <a id="t13"></a>108.6 - Printer 9

**Role** : Generation du document : Printer 9.
**Delegue a** : [Raz Current Printer (IDE 182)](ADH-IDE-182.md)

---

#### <a id="t14"></a>108.6.1 - edition extrait compte

**Role** : Generation du document : edition extrait compte.
**Delegue a** : [Raz Current Printer (IDE 182)](ADH-IDE-182.md)


## 5. REGLES METIER

5 regles identifiees:

### Impression (5 regles)

#### <a id="rm-RM-001"></a>[RM-001] Verification que l'imprimante courante est la n1

| Element | Detail |
|---------|--------|
| **Condition** | `GetParam ('CURRENTPRINTERNUM')=1` |
| **Si vrai** | Action si CURRENTPRINTERNUM = 1 |
| **Expression source** | Expression 3 : `GetParam ('CURRENTPRINTERNUM')=1` |
| **Exemple** | Si GetParam ('CURRENTPRINTERNUM')=1 â†’ Action si CURRENTPRINTERNUM = 1 |
| **Impact** | [108.1 - Printer 1](#t2) |

#### <a id="rm-RM-002"></a>[RM-002] Verification que l'imprimante courante est la n4

| Element | Detail |
|---------|--------|
| **Condition** | `GetParam ('CURRENTPRINTERNUM')=4` |
| **Si vrai** | Action si CURRENTPRINTERNUM = 4 |
| **Expression source** | Expression 4 : `GetParam ('CURRENTPRINTERNUM')=4` |
| **Exemple** | Si GetParam ('CURRENTPRINTERNUM')=4 â†’ Action si CURRENTPRINTERNUM = 4 |
| **Impact** | [108.1 - Printer 1](#t2) |

#### <a id="rm-RM-003"></a>[RM-003] Verification que l'imprimante courante est la n5

| Element | Detail |
|---------|--------|
| **Condition** | `GetParam ('CURRENTPRINTERNUM')=5` |
| **Si vrai** | Action si CURRENTPRINTERNUM = 5 |
| **Expression source** | Expression 5 : `GetParam ('CURRENTPRINTERNUM')=5` |
| **Exemple** | Si GetParam ('CURRENTPRINTERNUM')=5 â†’ Action si CURRENTPRINTERNUM = 5 |
| **Impact** | [108.1 - Printer 1](#t2) |

#### <a id="rm-RM-004"></a>[RM-004] Verification que l'imprimante courante est la n8

| Element | Detail |
|---------|--------|
| **Condition** | `GetParam ('CURRENTPRINTERNUM')=8` |
| **Si vrai** | Action si CURRENTPRINTERNUM = 8 |
| **Expression source** | Expression 6 : `GetParam ('CURRENTPRINTERNUM')=8` |
| **Exemple** | Si GetParam ('CURRENTPRINTERNUM')=8 â†’ Action si CURRENTPRINTERNUM = 8 |
| **Impact** | [108.1 - Printer 1](#t2) |

#### <a id="rm-RM-005"></a>[RM-005] Verification que l'imprimante courante est la n9

| Element | Detail |
|---------|--------|
| **Condition** | `GetParam ('CURRENTPRINTERNUM')=9` |
| **Si vrai** | Action si CURRENTPRINTERNUM = 9 |
| **Expression source** | Expression 7 : `GetParam ('CURRENTPRINTERNUM')=9` |
| **Exemple** | Si GetParam ('CURRENTPRINTERNUM')=9 â†’ Action si CURRENTPRINTERNUM = 9 |
| **Impact** | [108.1 - Printer 1](#t2) |

## 6. CONTEXTE

- **Appele par**: [Garantie sur compte (IDE 111)](ADH-IDE-111.md), [Garantie sur compte PMS-584 (IDE 112)](ADH-IDE-112.md), [Garantie sur compte (IDE 288)](ADH-IDE-288.md)
- **Appelle**: 1 programmes | **Tables**: 5 (W:0 R:2 L:3) | **Taches**: 14 | **Expressions**: 8

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 14)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 108.3.1 | 108.3.1 | Veuillez patienter... | MDI | 422 | 56 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t9"></a>108.3.1 - Veuillez patienter...
**Tache** : [108.3.1](#t9) | **Type** : MDI | **Dimensions** : 422 x 56 DLU
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
                         "x":  2,
                         "type":  "label",
                         "var":  "",
                         "y":  29,
                         "w":  420,
                         "fmt":  "",
                         "name":  "",
                         "h":  27,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  36,
                         "type":  "label",
                         "var":  "",
                         "y":  38,
                         "w":  355,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Impression de l\u0027annulation de garantie",
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
    "taskId":  "108.3.1",
    "height":  56
}
-->

## 9. NAVIGATION

Ecran unique: **Veuillez patienter...**

### 9.3 Structure hierarchique (14 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **108.1** | [**(sans nom)** (108)](#t1) | MDI | - | Traitement |
| 108.1.1 | [Iteration (108.3)](#t8) [mockup](#ecran-t8) | MDI | 422x56 | |
| 108.1.2 | [Veuillez patienter... (108.3.1)](#t9) [mockup](#ecran-t9) | MDI | 422x56 | |
| 108.1.3 | [recup nom adherent (108.4)](#t10) | MDI | - | |
| **108.2** | [**Printer 1** (108.1)](#t2) | MDI | - | Impression |
| 108.2.1 | [edition extrait compte (108.1.1)](#t3) | MDI | - | |
| 108.2.2 | [edition extrait compte (108.1.2)](#t4) | MDI | - | |
| 108.2.3 | [Printer 4 (108.2)](#t5) | MDI | - | |
| 108.2.4 | [edition extrait compte (108.2.1)](#t6) | MDI | - | |
| 108.2.5 | [edition extrait compte (108.2.2)](#t7) | MDI | - | |
| 108.2.6 | [Printer 8 (108.5)](#t11) | MDI | - | |
| 108.2.7 | [edition extrait compte (108.5.1)](#t12) | MDI | - | |
| 108.2.8 | [Printer 9 (108.6)](#t13) | MDI | - | |
| 108.2.9 | [edition extrait compte (108.6.1)](#t14) | MDI | - | |

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
| 39 | depot_garantie___dga | Depots et garanties | DB | R |   |   | 7 |
| 30 | gm-recherche_____gmr | Index de recherche | DB | R |   |   | 1 |
| 91 | garantie_________gar | Depots et garanties | DB |   |   | L | 7 |
| 31 | gm-complet_______gmc |  | DB |   |   | L | 1 |
| 34 | hebergement______heb | Hebergement (chambres) | DB |   |   | L | 1 |

### Colonnes par table (1 / 2 tables avec colonnes identifiees)

<details>
<summary>Table 39 - depot_garantie___dga (R) - 7 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | W1 initialisation | R | Alpha |
| B | W1 large | R | Alpha |
| C | W1 normal | R | Alpha |
| D | W1 condense | R | Alpha |
| E | W1 detection papier | R | Alpha |
| F | W1 inhibe panel | R | Alpha |
| G | W1 massicot | R | Alpha |
| H | W1 selection feuille | R | Alpha |
| I | W1 selection rouleau | R | Alpha |

</details>

<details>
<summary>Table 30 - gm-recherche_____gmr (R) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (5)

Variables recues du programme appelant ([Garantie sur compte (IDE 111)](ADH-IDE-111.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| EN | P0 societe | Alpha | - |
| EO | P0 code adherent | Numeric | - |
| EP | P0 filiation | Numeric | - |
| EQ | P0 nom village | Alpha | - |
| ER | P0 masque montant | Alpha | - |

### 11.2 Variables de travail (6)

Variables internes au programme.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| ES | W0 nom | Alpha | - |
| ET | W0 prenom | Alpha | - |
| EU | W0 n° adherent | Numeric | - |
| EV | W0 lettre contrôle | Alpha | - |
| EW | W0 filiation | Numeric | - |
| EX | W0 Chambre | Alpha | - |

## 12. EXPRESSIONS

**8 / 8 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONDITION | 5 | 5 |
| OTHER | 2 | 0 |
| CAST_LOGIQUE | 1 | 0 |

### 12.2 Expressions cles par type

#### CONDITION (5 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 6 | `GetParam ('CURRENTPRINTERNUM')=8` | [RM-004](#rm-RM-004) |
| CONDITION | 7 | `GetParam ('CURRENTPRINTERNUM')=9` | [RM-005](#rm-RM-005) |
| CONDITION | 5 | `GetParam ('CURRENTPRINTERNUM')=5` | [RM-003](#rm-RM-003) |
| CONDITION | 3 | `GetParam ('CURRENTPRINTERNUM')=1` | [RM-001](#rm-RM-001) |
| CONDITION | 4 | `GetParam ('CURRENTPRINTERNUM')=4` | [RM-002](#rm-RM-002) |

#### OTHER (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 2 | `SetCrsr (1)` | - |
| OTHER | 1 | `SetCrsr (2)` | - |

#### CAST_LOGIQUE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 8 | `'TRUE'LOG` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Garantie sur compte (IDE 111)](ADH-IDE-111.md) -> **Print annulation garantie (IDE 108)**

Main -> ... -> [Garantie sur compte PMS-584 (IDE 112)](ADH-IDE-112.md) -> **Print annulation garantie (IDE 108)**

Main -> ... -> [Garantie sur compte (IDE 288)](ADH-IDE-288.md) -> **Print annulation garantie (IDE 108)**

```mermaid
graph LR
    T108[108 Print annulation g...]
    style T108 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC163[163 Menu caisse GM - s...]
    style CC163 fill:#f59e0b
    CC111[111 Garantie sur compte]
    style CC111 fill:#3fb950
    CC112[112 Garantie sur compt...]
    style CC112 fill:#3fb950
    CC288[288 Garantie sur compte]
    style CC288 fill:#3fb950
    CC163 --> CC111
    CC163 --> CC112
    CC163 --> CC288
    CC1 --> CC163
    CC111 --> T108
    CC112 --> T108
    CC288 --> T108
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [111](ADH-IDE-111.md) | Garantie sur compte | 2 |
| [112](ADH-IDE-112.md) | Garantie sur compte PMS-584 | 2 |
| [288](ADH-IDE-288.md) | Garantie sur compte | 2 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T108[108 Print annulation g...]
    style T108 fill:#58a6ff
    C182[182 Raz Current Printer]
    T108 --> C182
    style C182 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [182](ADH-IDE-182.md) | Raz Current Printer | 1 | Impression ticket/document |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 239 | Taille moyenne |
| Expressions | 8 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 1 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 239) | Code sain |
| Regles metier | 5 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (4 taches: 2 ecrans, 2 traitements)

- **Strategie** : Orchestrateur avec 2 ecrans (Razor/React) et 2 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 1 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Impression (10 taches: 0 ecran, 10 traitements)

- **Strategie** : Templates HTML -> PDF via wkhtmltopdf ou Puppeteer.
- `PrintService` injectable avec choix imprimante

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| [Raz Current Printer (IDE 182)](ADH-IDE-182.md) | Sous-programme | 1x | Normale - Impression ticket/document |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-08 02:51*
