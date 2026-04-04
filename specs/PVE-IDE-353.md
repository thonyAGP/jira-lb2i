# PVE IDE 353 - Menu==V4

> **Analyse**: Phases 1-4 2026-02-03 19:43 -> 19:44 (11s) | Assemblage 19:44
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PVE |
| IDE Position | 353 |
| Nom Programme | Menu==V4 |
| Fichier source | `Prg_353.xml` |
| Dossier IDE | Sauvegarde |
| Taches | 3 (1 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 11 |
| :warning: Statut | **ORPHELIN_POTENTIEL** |

## 2. DESCRIPTION FONCTIONNELLE

**Menu==V4** assure la gestion complete de ce processus.

Le flux de traitement s'organise en **2 blocs fonctionnels** :

- **Traitement** (2 taches) : traitements metier divers
- **Calcul** (1 tache) : calculs de montants, stocks ou compteurs

**Logique metier** : 1 regles identifiees couvrant valeurs par defaut.

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (2 taches)

- **353** - Main (TPE) **[[ECRAN]](#ecran-t1)**
- **353.2** - Exist place

Delegue a : [Main Sale ===V4 (IDE 0)](PVE-IDE-0.md), [Menu Administration (IDE 178)](PVE-IDE-178.md), [Menu Cloture du service (IDE 180)](PVE-IDE-180.md), [Menu Reports (IDE 182)](PVE-IDE-182.md), [Menu Check IN / Exchange (IDE 183)](PVE-IDE-183.md), [Menu Equipment inventory (IDE 184)](PVE-IDE-184.md), [Menu Service cloture (IDE 402)](PVE-IDE-402.md)

#### Phase 2 : Calcul (1 tache)

- **353.1** - Lecture solde du compte

Delegue a : [Menu Stocks Management (IDE 179)](PVE-IDE-179.md)

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (2 taches)

Traitements internes.

---

#### <a id="t1"></a>353 - Main (TPE) [[ECRAN]](#ecran-t1)

**Role** : Traitement : Main (TPE).
**Ecran** : 994 x 432 DLU | [Voir mockup](#ecran-t1)
**Delegue a** : [Main Sale ===V4 (IDE 0)](PVE-IDE-0.md), [Menu Administration (IDE 178)](PVE-IDE-178.md), [Menu Cloture du service (IDE 180)](PVE-IDE-180.md)

---

#### <a id="t3"></a>353.2 - Exist place

**Role** : Traitement : Exist place.
**Variables liees** : G (v.LieuExist)
**Delegue a** : [Main Sale ===V4 (IDE 0)](PVE-IDE-0.md), [Menu Administration (IDE 178)](PVE-IDE-178.md), [Menu Cloture du service (IDE 180)](PVE-IDE-180.md)


### 3.2 Calcul (1 tache)

Calculs metier : montants, stocks, compteurs.

---

#### <a id="t2"></a>353.1 - Lecture solde du compte

**Role** : Consultation/chargement : Lecture solde du compte.
**Variables liees** : H (v.Solde du compte)
**Delegue a** : [Menu Stocks Management (IDE 179)](PVE-IDE-179.md)


## 5. REGLES METIER

1 regles identifiees:

### Autres (1 regles)

#### <a id="rm-RM-001"></a>[RM-001] Valeur par defaut si Trim(v.MENU [B]) est vide

| Element | Detail |
|---------|--------|
| **Condition** | `Trim(v.MENU [B])=''` |
| **Si vrai** | 'POS' |
| **Si faux** | v.MENU [B]) |
| **Variables** | B (v.MENU) |
| **Expression source** | Expression 2 : `IF(Trim(v.MENU [B])='','POS',v.MENU [B])` |
| **Exemple** | Si Trim(v.MENU [B])='' â†’ 'POS'. Sinon â†’ v.MENU [B]) |

## 6. CONTEXTE

- **Appele par**: (aucun)
- **Appelle**: 11 programmes | **Tables**: 3 (W:0 R:2 L:1) | **Taches**: 3 | **Expressions**: 37

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 3)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 353 | 353 | Main (TPE) | Type0 | 994 | 432 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>353 - Main (TPE)
**Tache** : [353](#t1) | **Type** : Type0 | **Dimensions** : 994 x 432 DLU
**Bloc** : Traitement | **Titre IDE** : Main (TPE)

<!-- FORM-DATA:
{
    "width":  994,
    "vFactor":  8,
    "type":  "Type0",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  2,
                         "w":  992,
                         "fmt":  "",
                         "name":  "",
                         "h":  32,
                         "color":  "103",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  10,
                         "type":  "button",
                         "var":  "",
                         "y":  6,
                         "w":  316,
                         "fmt":  "LIEU",
                         "name":  "LIEU",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  569,
                         "type":  "button",
                         "var":  "",
                         "y":  6,
                         "w":  138,
                         "fmt":  "CHECK IN",
                         "name":  "CHECKIN",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  707,
                         "type":  "button",
                         "var":  "",
                         "y":  6,
                         "w":  138,
                         "fmt":  "INVENTORY",
                         "name":  "INVENTORY",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  844,
                         "type":  "button",
                         "var":  "",
                         "y":  6,
                         "w":  138,
                         "fmt":  "EXIT",
                         "name":  "EXIT",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  352,
                         "type":  "combobox",
                         "var":  "",
                         "y":  7,
                         "w":  138,
                         "fmt":  "",
                         "name":  "v.MENU",
                         "h":  23,
                         "color":  "103",
                         "text":  "POS,CLOSING,REPORTS,STOCK,SERVICES,ADMIN",
                         "parent":  null
                     },
                     {
                         "x":  511,
                         "type":  "edit",
                         "var":  "",
                         "y":  14,
                         "w":  31,
                         "fmt":  "",
                         "name":  "VG.RESOLUTION_1024_768",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  2,
                         "type":  "subform",
                         "var":  "",
                         "y":  35,
                         "w":  992,
                         "fmt":  "",
                         "name":  "SB_MAIN_TPE",
                         "h":  396,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "353",
    "height":  432
}
-->

<details>
<summary><strong>Champs : 2 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 352,7 | v.MENU | - | combobox |
| 511,14 | VG.RESOLUTION_1024_768 | - | edit |

</details>

<details>
<summary><strong>Boutons : 4 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| LIEU | 10,6 | Bouton fonctionnel |
| CHECK IN | 569,6 | Appel [Menu Check IN / Exchange (IDE 183)](PVE-IDE-183.md) |
| INVENTORY | 707,6 | Appel [Menu Equipment inventory (IDE 184)](PVE-IDE-184.md) |
| EXIT | 844,6 | Quitte le programme |

</details>

## 9. NAVIGATION

Ecran unique: **Main (TPE)**

### 9.3 Structure hierarchique (3 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **353.1** | [**Main (TPE)** (353)](#t1) [mockup](#ecran-t1) | - | 994x432 | Traitement |
| 353.1.1 | [Exist place (353.2)](#t3) | - | - | |
| **353.2** | [**Lecture solde du compte** (353.1)](#t2) | - | - | Calcul |

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

### Tables utilisees (3)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 47 | compte_gm________cgm | Comptes GM (generaux) | DB | R |   |   | 1 |
| 766 | temp_forfait_ski |  | DB | R |   |   | 1 |
| 786 | qualite_avant_reprise |  | DB |   |   | L | 1 |

### Colonnes par table (1 / 2 tables avec colonnes identifiees)

<details>
<summary>Table 47 - compte_gm________cgm (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| H | v.Solde du compte | R | Numeric |

</details>

<details>
<summary>Table 766 - temp_forfait_ski (R) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (2)

Variables recues en parametre.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| J | P.Change Reason | Numeric | - |
| K | P.Prev Value | Alpha | 1x parametre entrant |

### 11.2 Variables de session (9)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | v.Lieu de vente | Alpha | - |
| B | v.MENU | Alpha | 14x session |
| C | v.Retour ? | Numeric | 1x session |
| D | V.Nbre d'enregistrement non val | Numeric | - |
| E | v.Passage | Logical | 1x session |
| F | v.End | Logical | 1x session |
| G | v.LieuExist | Logical | 1x session |
| H | v.Solde du compte | Numeric | [353.1](#t2) |
| I | v.confirm closure | Numeric | 1x session |

## 12. EXPRESSIONS

**37 / 37 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONCATENATION | 1 | 0 |
| CONDITION | 17 | 5 |
| CONSTANTE | 6 | 0 |
| OTHER | 5 | 0 |
| CAST_LOGIQUE | 3 | 0 |
| REFERENCE_VG | 2 | 0 |
| NEGATION | 2 | 0 |
| FORMAT | 1 | 0 |

### 12.2 Expressions cles par type

#### CONCATENATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 1 | `Trim(GetParam ('SERVICELIB'))&'  -  POS '&Trim(VG6)` | - |

#### CONDITION (17 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 2 | `IF(Trim(v.MENU [B])='','POS',v.MENU [B])` | [RM-001](#rm-RM-001) |
| CONDITION | 20 | `Trim(v.MENU [B])='STOCK'` | - |
| CONDITION | 22 | `Trim(v.MENU [B])='SERVICES'` | - |
| CONDITION | 18 | `Trim(v.MENU [B])='REPORTS'` | - |
| CONDITION | 19 | `Trim(v.MENU [B])='STOCK' AND VG13` | - |
| ... | | *+12 autres* | |

#### CONSTANTE (6 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 26 | `'SB_MAIN_TPE'` | - |
| CONSTANTE | 30 | `'I'` | - |
| CONSTANTE | 33 | `'J'` | - |
| CONSTANTE | 7 | `''` | - |
| CONSTANTE | 8 | `'C'` | - |
| ... | | *+1 autres* | |

#### OTHER (5 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 27 | `'POS,CLOSING,REPORTS,STOCK,SERVICES,ADMIN'&IF(VG24,',TPE INIT,TPE DIARY','')` | - |
| OTHER | 31 | `P.Prev Value [K]` | - |
| OTHER | 15 | `GetParam ('SERVICE')` | - |
| OTHER | 3 | `v.LieuExist [G]` | - |
| OTHER | 10 | `v.End [F]` | - |

#### CAST_LOGIQUE (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 12 | `'TRUE'LOG` | - |
| CAST_LOGIQUE | 9 | `'TRUE'LOG` | - |
| CAST_LOGIQUE | 4 | `GetParam ('RENTAL')='TRUE'LOG` | - |

#### REFERENCE_VG (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 35 | `VG15` | - |
| REFERENCE_VG | 6 | `VG14` | - |

#### NEGATION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| NEGATION | 34 | `NOT VG15` | - |
| NEGATION | 11 | `NOT v.Passage [E]` | - |

#### FORMAT (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| FORMAT | 29 | `Str(VG105,'8P0')` | - |

### 12.3 Toutes les expressions (37)

<details>
<summary>Voir les 37 expressions</summary>

#### CONCATENATION (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 1 | `Trim(GetParam ('SERVICELIB'))&'  -  POS '&Trim(VG6)` |

#### CONDITION (17)

| IDE | Expression Decodee |
|-----|-------------------|
| 21 | `Trim(v.MENU [B])='SERVICES' AND IN(GetParam ('GROUP'),'INFORMATICIEN','GESTION','C D V - H S M')` |
| 2 | `IF(Trim(v.MENU [B])='','POS',v.MENU [B])` |
| 5 | `v.Retour ? [C]=6` |
| 36 | `v.Solde du compte [H]<>0` |
| 37 | `v.Solde du compte [H]=0 OR (v.Solde du compte [H]<>0 AND v.confirm closure [I]=6)` |
| 13 | `Trim(v.MENU [B])='POS'` |
| 14 | `Trim(v.MENU [B])='CLOSING' AND VG13` |
| 16 | `Trim(v.MENU [B])='CLOSING'` |
| 17 | `Trim(v.MENU [B])='REPORTS' AND VG13` |
| 18 | `Trim(v.MENU [B])='REPORTS'` |
| 19 | `Trim(v.MENU [B])='STOCK' AND VG13` |
| 20 | `Trim(v.MENU [B])='STOCK'` |
| 22 | `Trim(v.MENU [B])='SERVICES'` |
| 23 | `Trim(v.MENU [B])='ADMIN' AND VG9` |
| 24 | `Trim(v.MENU [B])='ADMIN'` |
| 28 | `Trim(v.MENU [B])='TPE INIT'` |
| 32 | `Trim(v.MENU [B])='TPE DIARY'` |

#### CONSTANTE (6)

| IDE | Expression Decodee |
|-----|-------------------|
| 7 | `''` |
| 8 | `'C'` |
| 25 | `'POS'` |
| 26 | `'SB_MAIN_TPE'` |
| 30 | `'I'` |
| 33 | `'J'` |

#### OTHER (5)

| IDE | Expression Decodee |
|-----|-------------------|
| 3 | `v.LieuExist [G]` |
| 10 | `v.End [F]` |
| 15 | `GetParam ('SERVICE')` |
| 27 | `'POS,CLOSING,REPORTS,STOCK,SERVICES,ADMIN'&IF(VG24,',TPE INIT,TPE DIARY','')` |
| 31 | `P.Prev Value [K]` |

#### CAST_LOGIQUE (3)

| IDE | Expression Decodee |
|-----|-------------------|
| 4 | `GetParam ('RENTAL')='TRUE'LOG` |
| 9 | `'TRUE'LOG` |
| 12 | `'TRUE'LOG` |

#### REFERENCE_VG (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 6 | `VG14` |
| 35 | `VG15` |

#### NEGATION (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 11 | `NOT v.Passage [E]` |
| 34 | `NOT VG15` |

#### FORMAT (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 29 | `Str(VG105,'8P0')` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

**Chemin**: (pas de callers directs)

```mermaid
graph LR
    T353[353 Menu==V4]
    style T353 fill:#58a6ff
    NONE[Aucun caller]
    NONE -.-> T353
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| - | (aucun) | - |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T353[353 Menu==V4]
    style T353 fill:#58a6ff
    C178[178 Menu Administration]
    T353 --> C178
    style C178 fill:#3fb950
    C179[179 Menu Stocks Manage...]
    T353 --> C179
    style C179 fill:#3fb950
    C180[180 Menu Cloture du se...]
    T353 --> C180
    style C180 fill:#3fb950
    C182[182 Menu Reports]
    T353 --> C182
    style C182 fill:#3fb950
    C183[183 Menu Check IN Exch...]
    T353 --> C183
    style C183 fill:#3fb950
    C184[184 Menu Equipment inv...]
    T353 --> C184
    style C184 fill:#3fb950
    C304[304 Ligne Fact Non Val...]
    T353 --> C304
    style C304 fill:#3fb950
    C331[331 Sales place - select]
    T353 --> C331
    style C331 fill:#3fb950
    C332[332 Choix - Services]
    T353 --> C332
    style C332 fill:#3fb950
    C402[402 Menu Service cloture]
    T353 --> C402
    style C402 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [0](PVE-IDE-0.md) | Main Sale ===V4 | 1 | Sous-programme |
| [178](PVE-IDE-178.md) | Menu Administration | 1 | Navigation menu |
| [179](PVE-IDE-179.md) | Menu Stocks Management | 1 | Calcul de donnees |
| [180](PVE-IDE-180.md) | Menu Cloture du service | 1 | Fermeture session |
| [182](PVE-IDE-182.md) | Menu Reports | 1 | Navigation menu |
| [183](PVE-IDE-183.md) | Menu Check IN / Exchange | 1 | Navigation menu |
| [184](PVE-IDE-184.md) | Menu Equipment inventory | 1 | Navigation menu |
| [304](PVE-IDE-304.md) | Ligne Fact Non Validées & Edit | 1 | Sous-programme |
| [331](PVE-IDE-331.md) | Sales place - select | 1 | Selection/consultation |
| [332](PVE-IDE-332.md) | Choix - Services | 1 | Selection/consultation |
| [402](PVE-IDE-402.md) | Menu Service cloture | 1 | Fermeture session |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 120 | Programme compact |
| Expressions | 37 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 11 | Forte dependance |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 120) | Code sain |
| Regles metier | 1 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (2 taches: 1 ecran, 1 traitement)

- **Strategie** : Orchestrateur avec 1 ecrans (Razor/React) et 1 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 11 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Calcul (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Services de calcul purs (Domain Services).
- Migrer la logique de calcul (stock, compteurs, montants)

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| [Ligne Fact Non Validées & Edit (IDE 304)](PVE-IDE-304.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Menu Equipment inventory (IDE 184)](PVE-IDE-184.md) | Sous-programme | 1x | Normale - Navigation menu |
| [Sales place - select (IDE 331)](PVE-IDE-331.md) | Sous-programme | 1x | Normale - Selection/consultation |
| [Menu Service cloture (IDE 402)](PVE-IDE-402.md) | Sous-programme | 1x | Normale - Fermeture session |
| [Choix - Services (IDE 332)](PVE-IDE-332.md) | Sous-programme | 1x | Normale - Selection/consultation |
| [Menu Check IN / Exchange (IDE 183)](PVE-IDE-183.md) | Sous-programme | 1x | Normale - Navigation menu |
| [Menu Administration (IDE 178)](PVE-IDE-178.md) | Sous-programme | 1x | Normale - Navigation menu |
| [Main Sale ===V4 (IDE 0)](PVE-IDE-0.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Menu Stocks Management (IDE 179)](PVE-IDE-179.md) | Sous-programme | 1x | Normale - Calcul de donnees |
| [Menu Reports (IDE 182)](PVE-IDE-182.md) | Sous-programme | 1x | Normale - Navigation menu |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 19:44*
