# PVE IDE 426 - FindAailibility

> **Analyse**: Phases 1-4 2026-02-03 20:04 -> 20:04 (12s) | Assemblage 20:04
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PVE |
| IDE Position | 426 |
| Nom Programme | FindAailibility |
| Fichier source | `Prg_426.xml` |
| Dossier IDE | A |
| Taches | 4 (0 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 2 |
| :warning: Statut | **ORPHELIN_POTENTIEL** |

## 2. DESCRIPTION FONCTIONNELLE

**FindAailibility** assure la gestion complete de ce processus.

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (4 taches) : traitements metier divers

**Donnees modifiees** : 1 tables en ecriture (Table_1549).

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (4 taches)

- **426** - FindAailibility
- **426.1** - ExtractDataFromXML
- **426.1.1** - DataToTables
- **426.1.2** - DeleteAvailibility

Delegue a : [GetToken (IDE 151)](PVE-IDE-151.md), [TraceLogBooker (IDE 175)](PVE-IDE-175.md)

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| Table_1549 | **W** (2 usages) |  |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (4 taches)

Traitements internes.

---

#### <a id="t1"></a>426 - FindAailibility

**Role** : Traitement : FindAailibility.

<details>
<summary>3 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [426.1](#t2) | ExtractDataFromXML | Traitement |
| [426.1.1](#t3) | DataToTables | Traitement |
| [426.1.2](#t4) | DeleteAvailibility | Traitement |

</details>
**Delegue a** : [GetToken (IDE 151)](PVE-IDE-151.md), [TraceLogBooker (IDE 175)](PVE-IDE-175.md)

---

#### <a id="t2"></a>426.1 - ExtractDataFromXML

**Role** : Traitement : ExtractDataFromXML.
**Delegue a** : [GetToken (IDE 151)](PVE-IDE-151.md), [TraceLogBooker (IDE 175)](PVE-IDE-175.md)

---

#### <a id="t3"></a>426.1.1 - DataToTables

**Role** : Traitement : DataToTables.
**Delegue a** : [GetToken (IDE 151)](PVE-IDE-151.md), [TraceLogBooker (IDE 175)](PVE-IDE-175.md)

---

#### <a id="t4"></a>426.1.2 - DeleteAvailibility

**Role** : Traitement : DeleteAvailibility.
**Delegue a** : [GetToken (IDE 151)](PVE-IDE-151.md), [TraceLogBooker (IDE 175)](PVE-IDE-175.md)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: (aucun)
- **Appelle**: 2 programmes | **Tables**: 1 (W:1 R:0 L:0) | **Taches**: 4 | **Expressions**: 9

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (4 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **426.1** | [**FindAailibility** (426)](#t1) | - | - | Traitement |
| 426.1.1 | [ExtractDataFromXML (426.1)](#t2) | - | - | |
| 426.1.2 | [DataToTables (426.1.1)](#t3) | - | - | |
| 426.1.3 | [DeleteAvailibility (426.1.2)](#t4) | - | - | |

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

### Tables utilisees (1)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 1549 | Table_1549 |  | MEM |   | **W** |   | 2 |

### Colonnes par table (0 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 1549 - Table_1549 (**W**) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (8)

Variables recues en parametre.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P.DateDebut | Date | - |
| B | P.DateFin | Date | - |
| C | P.TimeDebut | Time | - |
| D | P.TimeFin | Time | - |
| E | P.Praticien | Numeric | 1x parametre entrant |
| F | P.Cabine | Numeric | 1x parametre entrant |
| G | P.ProduitID | Numeric | 1x parametre entrant |
| H | P.RajoutDonnees | Logical | - |

### 11.2 Autres (15)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| I | DateTimeDebutUnix | Unicode | 1x refs |
| J | DateTimeFinUnix | Unicode | 1x refs |
| K | Token | Unicode | 1x refs |
| L | LocationID | Numeric | 1x refs |
| M | typeRequest | Alpha | - |
| N | UrlApi | Alpha | - |
| O | JsonIN | Blob | 1x refs |
| P | IsSuccessToken | Logical | - |
| Q | ErrorMessageToken | Alpha | - |
| R | IsSuccess | Logical | - |
| S | ErrorMessage | Alpha | - |
| T | JsonResponse | Blob | 2x refs |
| U | XMLResponse | Blob | - |
| V | IsSuccessDate | Logical | - |
| W | ErrorDate | Alpha | - |

<details>
<summary>Toutes les 23 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| P0 | **A** | P.DateDebut | Date |
| P0 | **B** | P.DateFin | Date |
| P0 | **C** | P.TimeDebut | Time |
| P0 | **D** | P.TimeFin | Time |
| P0 | **E** | P.Praticien | Numeric |
| P0 | **F** | P.Cabine | Numeric |
| P0 | **G** | P.ProduitID | Numeric |
| P0 | **H** | P.RajoutDonnees | Logical |
| Autre | **I** | DateTimeDebutUnix | Unicode |
| Autre | **J** | DateTimeFinUnix | Unicode |
| Autre | **K** | Token | Unicode |
| Autre | **L** | LocationID | Numeric |
| Autre | **M** | typeRequest | Alpha |
| Autre | **N** | UrlApi | Alpha |
| Autre | **O** | JsonIN | Blob |
| Autre | **P** | IsSuccessToken | Logical |
| Autre | **Q** | ErrorMessageToken | Alpha |
| Autre | **R** | IsSuccess | Logical |
| Autre | **S** | ErrorMessage | Alpha |
| Autre | **T** | JsonResponse | Blob |
| Autre | **U** | XMLResponse | Blob |
| Autre | **V** | IsSuccessDate | Logical |
| Autre | **W** | ErrorDate | Alpha |

</details>

## 12. EXPRESSIONS

**9 / 9 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCULATION | 1 | 0 |
| CONCATENATION | 1 | 0 |
| CONSTANTE | 1 | 0 |
| FORMAT | 1 | 0 |
| DATE | 1 | 0 |
| REFERENCE_VG | 1 | 0 |
| OTHER | 3 | 0 |

### 12.2 Expressions cles par type

#### CALCULATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 3 | `Trim(VG66) & '/availability'` | - |

#### CONCATENATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 7 | `'<?xml version="1.0" encoding="UTF-8"?>' &ASCIIChr(13)& ASCIIChr(10)&DotNet.System.Xml.Linq.XElement.Load(  DotNet.System.Runtime.Serialization.Json.JsonReaderWriterFactory.CreateJsonReader(JsonResponse [T],     DotNet.System.Xml.XmlDictionaryReaderQuotas()   )).ToString()` | - |

#### CONSTANTE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 2 | `'POST'` | - |

#### FORMAT (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| FORMAT | 6 | `'{
    "AppointmentID": null,
    "EmployeeID": ' & IF(P.Praticien [E] <> 0,Trim(Str(P.Praticien [E],'10')),'null') & ',
    "EndDateTime": "/Date(' & Trim(DateTimeFinUnix [J]) & ')/",
    "IncludeFreelancers": false,
    "IsPackage": false,
    "LocationID":' & Trim(Str(LocationID [L],'10')) &',
    "MaxTimesPerDay": null,
    "PackageID": null,
    "Quantity": 1,
    "ServiceID":' & Trim(Str(P.ProduitID [G],'10')) &',
    "ServiceTypeID": 1,
    "StartDateTime": "/Date(' & Trim(DateTimeDebutUnix [I]) & ')/",
    "RoomID": ' & IF(P.Cabine [F] <> 0,Trim(Str(P.Cabine [F],'10')),'null') & ',
    "AdjustEndTime": true,
    "access_token": "'& Trim(Token [K]) &'"
}'` | - |

#### DATE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| DATE | 8 | `Date()` | - |

#### REFERENCE_VG (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 1 | `VG67` | - |

#### OTHER (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 9 | `Time()` | - |
| OTHER | 5 | `Blb2File(JsonResponse [T],'c:\Temp\availabilityOUT.json')` | - |
| OTHER | 4 | `Blb2File(JsonIN [O],'c:\Temp\availabilityIN.json')` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

**Chemin**: (pas de callers directs)

```mermaid
graph LR
    T426[426 FindAailibility]
    style T426 fill:#58a6ff
    NONE[Aucun caller]
    NONE -.-> T426
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| - | (aucun) | - |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T426[426 FindAailibility]
    style T426 fill:#58a6ff
    C151[151 GetToken]
    T426 --> C151
    style C151 fill:#3fb950
    C175[175 TraceLogBooker]
    T426 --> C175
    style C175 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [151](PVE-IDE-151.md) | GetToken | 1 | Recuperation donnees |
| [175](PVE-IDE-175.md) | TraceLogBooker | 1 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 123 | Programme compact |
| Expressions | 9 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 2 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 1.6% (2 / 123) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (4 taches: 0 ecran, 4 traitements)

- **Strategie** : 4 service(s) backend injectable(s) (Domain Services).
- 2 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| Table_1549 | Table WRITE (Memory) | 2x | Schema + repository |
| [TraceLogBooker (IDE 175)](PVE-IDE-175.md) | Sous-programme | 1x | Normale - Sous-programme |
| [GetToken (IDE 151)](PVE-IDE-151.md) | Sous-programme | 1x | Normale - Recuperation donnees |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 20:04*
