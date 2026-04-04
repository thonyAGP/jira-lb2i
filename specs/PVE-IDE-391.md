# PVE IDE 391 - Report - Discount & Gratuities

> **Analyse**: Phases 1-4 2026-02-03 19:54 -> 19:54 (11s) | Assemblage 19:54
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PVE |
| IDE Position | 391 |
| Nom Programme | Report - Discount & Gratuities |
| Fichier source | `Prg_391.xml` |
| Dossier IDE | A |
| Taches | 11 (0 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 3 |

## 2. DESCRIPTION FONCTIONNELLE

**Report - Discount & Gratuities** assure la gestion complete de ce processus, accessible depuis [Menu Cloture du service (IDE 180)](PVE-IDE-180.md), [Menu Service cloture v2 (IDE 397)](PVE-IDE-397.md), [Menu Service cloture (IDE 402)](PVE-IDE-402.md).

Le flux de traitement s'organise en **4 blocs fonctionnels** :

- **Traitement** (4 taches) : traitements metier divers
- **Impression** (4 taches) : generation de tickets et documents
- **Calcul** (2 taches) : calculs de montants, stocks ou compteurs
- **Consultation** (1 tache) : ecrans de recherche, selection et consultation

**Donnees modifiees** : 1 tables en ecriture (logement_par_village).

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Impression (4 taches)

- **391** - Print Discounts **[[ECRAN]](#ecran-t1)**
- **391.1** - Print
- **391.1.1** - Printing
- **391.1.3** - Printing

#### Phase 2 : Traitement (4 taches)

- **391.1.1.1** - Discount line
- **391.1.2.2.1** - Temp generation
- **391.1.2.3** - Temp generation
- **391.1.3.1** - Discount line

Delegue a : [IoDel fichier CSV (IDE 56)](PVE-IDE-56.md), [Choice today tomorrow (IDE 202)](PVE-IDE-202.md)

#### Phase 3 : Consultation (1 tache)

- **391.1.2** - SELECTION

#### Phase 4 : Calcul (2 taches)

- **391.1.2.1** - Selection compta
- **391.1.2.2** - Selection compta

Delegue a : [Browse - pv_comptab_temp (IDE 448)](PVE-IDE-448.md)

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| logement_par_village | R/**W** (4 usages) |  |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Impression (4 taches)

Generation des documents et tickets.

---

#### <a id="t1"></a>391 - Print Discounts [[ECRAN]](#ecran-t1)

**Role** : Generation du document : Print Discounts.
**Ecran** : 312 x 173 DLU (MDI) | [Voir mockup](#ecran-t1)

<details>
<summary>3 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [391.1](#t2) | Print | Impression |
| [391.1.1](#t3) | Printing | Impression |
| [391.1.3](#t10) | Printing | Impression |

</details>

---

#### <a id="t2"></a>391.1 - Print

**Role** : Generation du document : Print.

---

#### <a id="t3"></a>391.1.1 - Printing

**Role** : Generation du document : Printing.

---

#### <a id="t10"></a>391.1.3 - Printing

**Role** : Generation du document : Printing.


### 3.2 Traitement (4 taches)

Traitements internes.

---

#### <a id="t4"></a>391.1.1.1 - Discount line

**Role** : Traitement : Discount line.
**Delegue a** : [IoDel fichier CSV (IDE 56)](PVE-IDE-56.md), [Choice today tomorrow (IDE 202)](PVE-IDE-202.md)

---

#### <a id="t8"></a>391.1.2.2.1 - Temp generation

**Role** : Traitement : Temp generation.
**Delegue a** : [IoDel fichier CSV (IDE 56)](PVE-IDE-56.md), [Choice today tomorrow (IDE 202)](PVE-IDE-202.md)

---

#### <a id="t9"></a>391.1.2.3 - Temp generation

**Role** : Traitement : Temp generation.
**Delegue a** : [IoDel fichier CSV (IDE 56)](PVE-IDE-56.md), [Choice today tomorrow (IDE 202)](PVE-IDE-202.md)

---

#### <a id="t11"></a>391.1.3.1 - Discount line

**Role** : Traitement : Discount line.
**Delegue a** : [IoDel fichier CSV (IDE 56)](PVE-IDE-56.md), [Choice today tomorrow (IDE 202)](PVE-IDE-202.md)


### 3.3 Consultation (1 tache)

Ecrans de recherche et consultation.

---

#### <a id="t5"></a>391.1.2 - SELECTION

**Role** : Selection par l'operateur : SELECTION.


### 3.4 Calcul (2 taches)

Calculs metier : montants, stocks, compteurs.

---

#### <a id="t6"></a>391.1.2.1 - Selection compta

**Role** : Selection par l'operateur : Selection compta.
**Delegue a** : [Browse - pv_comptab_temp (IDE 448)](PVE-IDE-448.md)

---

#### <a id="t7"></a>391.1.2.2 - Selection compta

**Role** : Selection par l'operateur : Selection compta.
**Delegue a** : [Browse - pv_comptab_temp (IDE 448)](PVE-IDE-448.md)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Menu Cloture du service (IDE 180)](PVE-IDE-180.md), [Menu Service cloture v2 (IDE 397)](PVE-IDE-397.md), [Menu Service cloture (IDE 402)](PVE-IDE-402.md)
- **Appelle**: 3 programmes | **Tables**: 11 (W:1 R:3 L:8) | **Taches**: 11 | **Expressions**: 3

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (11 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **391.1** | [**Print Discounts** (391)](#t1) [mockup](#ecran-t1) | MDI | 312x173 | Impression |
| 391.1.1 | [Print (391.1)](#t2) | MDI | - | |
| 391.1.2 | [Printing (391.1.1)](#t3) | MDI | - | |
| 391.1.3 | [Printing (391.1.3)](#t10) | MDI | - | |
| **391.2** | [**Discount line** (391.1.1.1)](#t4) | MDI | - | Traitement |
| 391.2.1 | [Temp generation (391.1.2.2.1)](#t8) | MDI | - | |
| 391.2.2 | [Temp generation (391.1.2.3)](#t9) | - | - | |
| 391.2.3 | [Discount line (391.1.3.1)](#t11) | MDI | - | |
| **391.3** | [**SELECTION** (391.1.2)](#t5) | MDI | - | Consultation |
| **391.4** | [**Selection compta** (391.1.2.1)](#t6) | MDI | - | Calcul |
| 391.4.1 | [Selection compta (391.1.2.2)](#t7) | MDI | - | |

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

### Tables utilisees (11)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 30 | gm-recherche_____gmr | Index de recherche | DB |   |   | L | 1 |
| 31 | gm-complet_______gmc |  | DB |   |   | L | 1 |
| 38 | comptable_gratuite |  | DB |   |   | L | 1 |
| 386 | ski_frame |  | DB |   |   | L | 1 |
| 403 | pv_sellers |  | DB |   |   | L | 1 |
| 420 | req_dispatch |  | DB |   |   | L | 1 |
| 523 | synthese_garanties | Depots et garanties | TMP | R |   |   | 2 |
| 526 | liste_des_lieux |  | TMP |   |   | L | 1 |
| 528 | logement_par_village |  | TMP | R | **W** |   | 4 |
| 534 | liste_des_caisses | Sessions de caisse | TMP |   |   | L | 1 |
| 763 | pv_inv_stock | Articles et stock | DB | R |   |   | 1 |

### Colonnes par table (3 / 3 tables avec colonnes identifiees)

<details>
<summary>Table 523 - synthese_garanties (R) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 528 - logement_par_village (R/**W**) - 4 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | V.Regular_price | W | Numeric |
| B | V.Discounted price | W | Numeric |
| C | V.Total CA | W | Numeric |
| D | V.Total regular | W | Numeric |
| E | V.Total discounted | W | Numeric |

</details>

<details>
<summary>Table 763 - pv_inv_stock (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | T.Gratuite | R | Logical |
| B | T.Credit conso | R | Logical |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (5)

Variables recues du programme appelant ([Menu Cloture du service (IDE 180)](PVE-IDE-180.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P. Village name | Alpha | - |
| B | P. Currency | Alpha | - |
| C | P. Amount format | Alpha | - |
| D | P. Amount format sans Z | Alpha | - |
| E | P. Decimales | Numeric | - |

### 11.2 Variables de session (4)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| F | V Période nombre JH | Numeric | - |
| G | V Jours Période | Numeric | - |
| H | V Date mini | Date | 1x session |
| I | V Date maxi | Date | 2x session |

### 11.3 Autres (1)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| J | S | Alpha | - |

## 12. EXPRESSIONS

**3 / 3 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONDITION | 2 | 0 |
| REFERENCE_VG | 1 | 0 |

### 12.2 Expressions cles par type

#### CONDITION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 2 | `V Date maxi [I]<>'00/00/0000'DATE` | - |
| CONDITION | 1 | `V Date mini [H]='00/00/0000'DATE AND V Date maxi [I]='00/00/0000'DATE` | - |

#### REFERENCE_VG (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 3 | `VG37` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Menu Cloture du service (IDE 180)](PVE-IDE-180.md) -> **Report - Discount & Gratuities (IDE 391)**

Main -> ... -> [Menu Service cloture v2 (IDE 397)](PVE-IDE-397.md) -> **Report - Discount & Gratuities (IDE 391)**

Main -> ... -> [Menu Service cloture (IDE 402)](PVE-IDE-402.md) -> **Report - Discount & Gratuities (IDE 391)**

```mermaid
graph LR
    T391[391 Report - Discount ...]
    style T391 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC143[143 START]
    style CC143 fill:#f59e0b
    CC420[420 Menu==V4___]
    style CC420 fill:#f59e0b
    CC439[439 Menu]
    style CC439 fill:#f59e0b
    CC353[353 Menu==V4]
    style CC353 fill:#f59e0b
    CC185[185 Menu]
    style CC185 fill:#f59e0b
    CC180[180 Menu Cloture du se...]
    style CC180 fill:#3fb950
    CC397[397 Menu Service clotu...]
    style CC397 fill:#3fb950
    CC402[402 Menu Service cloture]
    style CC402 fill:#3fb950
    CC185 --> CC180
    CC353 --> CC180
    CC420 --> CC180
    CC439 --> CC180
    CC185 --> CC397
    CC353 --> CC397
    CC420 --> CC397
    CC439 --> CC397
    CC185 --> CC402
    CC353 --> CC402
    CC420 --> CC402
    CC439 --> CC402
    CC143 --> CC185
    CC143 --> CC353
    CC143 --> CC420
    CC143 --> CC439
    CC1 --> CC143
    CC180 --> T391
    CC397 --> T391
    CC402 --> T391
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [180](PVE-IDE-180.md) | Menu Cloture du service | 1 |
| [397](PVE-IDE-397.md) | Menu Service cloture v2 | 1 |
| [402](PVE-IDE-402.md) | Menu Service cloture | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T391[391 Report - Discount ...]
    style T391 fill:#58a6ff
    C56[56 IoDel fichier CSV]
    T391 --> C56
    style C56 fill:#3fb950
    C202[202 Choice today tomorrow]
    T391 --> C202
    style C202 fill:#3fb950
    C448[448 Browse - pv_compta...]
    T391 --> C448
    style C448 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [56](PVE-IDE-56.md) | IoDel fichier CSV | 1 | Sous-programme |
| [202](PVE-IDE-202.md) | Choice today tomorrow | 1 | Sous-programme |
| [448](PVE-IDE-448.md) | Browse - pv_comptab_temp | 1 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 303 | Taille moyenne |
| Expressions | 3 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 3 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 1% (3 / 303) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Impression (4 taches: 1 ecran, 3 traitements)

- **Strategie** : Templates HTML -> PDF via wkhtmltopdf ou Puppeteer.
- `PrintService` injectable avec choix imprimante

#### Traitement (4 taches: 0 ecran, 4 traitements)

- **Strategie** : 4 service(s) backend injectable(s) (Domain Services).
- 3 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Consultation (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Composants de recherche/selection en modales.

#### Calcul (2 taches: 0 ecran, 2 traitements)

- **Strategie** : Services de calcul purs (Domain Services).
- Migrer la logique de calcul (stock, compteurs, montants)

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| logement_par_village | Table WRITE (Temp) | 2x | Schema + repository |
| [Browse - pv_comptab_temp (IDE 448)](PVE-IDE-448.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Choice today tomorrow (IDE 202)](PVE-IDE-202.md) | Sous-programme | 1x | Normale - Sous-programme |
| [IoDel fichier CSV (IDE 56)](PVE-IDE-56.md) | Sous-programme | 1x | Normale - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 19:54*
