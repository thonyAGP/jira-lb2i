# PVE IDE 167 - UpdateAppointment

> **Analyse**: Phases 1-4 2026-02-03 18:37 -> 18:37 (20s) | Assemblage 18:37
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PVE |
| IDE Position | 167 |
| Nom Programme | UpdateAppointment |
| Fichier source | `Prg_167.xml` |
| Dossier IDE | Interface |
| Taches | 2 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 2 |

## 2. DESCRIPTION FONCTIONNELLE

**UpdateAppointment** assure la gestion complete de ce processus, accessible depuis [SearchBooking (IDE 153)](PVE-IDE-153.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (2 taches) : traitements metier divers

**Logique metier** : 1 regles identifiees couvrant conditions metier.

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (2 taches)

Traitements internes.

---

#### <a id="t1"></a>167 - UpdateAppointment

**Role** : Traitement : UpdateAppointment.
**Delegue a** : [GetToken (IDE 151)](PVE-IDE-151.md), [TraceLogBooker (IDE 175)](PVE-IDE-175.md)

---

#### <a id="t2"></a>167.1 - ExtractDataFromXML

**Role** : Traitement : ExtractDataFromXML.
**Delegue a** : [GetToken (IDE 151)](PVE-IDE-151.md), [TraceLogBooker (IDE 175)](PVE-IDE-175.md)


## 5. REGLES METIER

1 regles identifiees:

### Autres (1 regles)

#### <a id="rm-RM-001"></a>[RM-001] Si ErrorMessageToken [X] = 0 alors 'null' sinon Str(ErrorMessageToken [X],'10'))

| Element | Detail |
|---------|--------|
| **Condition** | `ErrorMessageToken [X] = 0` |
| **Si vrai** | 'null' |
| **Si faux** | Str(ErrorMessageToken [X],'10')) |
| **Variables** | N (Token), X (ErrorMessageToken), Z (ErrorMessage) |
| **Expression source** | Expression 8 : `IF(ErrorMessageToken [X] = 0,'null',Str(ErrorMessageToken [X` |
| **Exemple** | Si ErrorMessageToken [X] = 0 â†’ 'null'. Sinon â†’ Str(ErrorMessageToken [X],'10')) |

## 6. CONTEXTE

- **Appele par**: [SearchBooking (IDE 153)](PVE-IDE-153.md)
- **Appelle**: 2 programmes | **Tables**: 1 (W:0 R:1 L:0) | **Taches**: 2 | **Expressions**: 14

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (2 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **167.1** | [**UpdateAppointment** (167)](#t1) | - | - | Traitement |
| 167.1.1 | [ExtractDataFromXML (167.1)](#t2) | - | - | |

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

### Tables utilisees (1)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 382 | pv_discount_reasons |  | DB | R |   |   | 1 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 382 - pv_discount_reasons (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| V | JsonIN | R | Blob |
| BA | JsonResponse | R | Blob |
| BB | XMLResponse | R | Blob |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (13)

Variables recues du programme appelant ([SearchBooking (IDE 153)](PVE-IDE-153.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P.AppointmentID | Unicode | 2x parametre entrant |
| B | P.CustomerID | Numeric | 1x parametre entrant |
| C | P.SoinsID | Numeric | 1x parametre entrant |
| D | P.DateDebut | Date | - |
| E | P.TimeDebut | Time | - |
| F | P.DateFin | Date | - |
| G | P.TimeFin | Time | 1x parametre entrant |
| H | P.PraticienID | Numeric | 1x parametre entrant |
| I | P.CabineID | Numeric | 1x parametre entrant |
| J | P.BookingID | Unicode | - |
| K | P.OrderID | Numeric | - |
| L | P.BookerCustID | Numeric | - |
| M | P.RecoveryTime | Numeric | 2x parametre entrant |

### 11.2 Variables de session (1)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| T | V.TimeFin(+RecoveryTime) | Time | - |

### 11.3 Autres (14)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| N | Token | Unicode | 2x refs |
| O | LocationID | Numeric | - |
| P | typeRequest | Alpha | - |
| Q | UrlApi | Alpha | - |
| R | TimestampDebut | Unicode | 1x refs |
| S | TimeStampFin | Unicode | 1x refs |
| U | id_customer_bookerAlpha | Unicode | - |
| V | JsonIN | Blob | 1x refs |
| W | IsSuccessToken | Logical | 1x refs |
| X | ErrorMessageToken | Alpha | 1x refs |
| Y | IsSuccess | Logical | 1x refs |
| Z | ErrorMessage | Alpha | 1x refs |
| BA | JsonResponse | Blob | - |
| BB | XMLResponse | Blob | - |

<details>
<summary>Toutes les 28 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| P0 | **A** | P.AppointmentID | Unicode |
| P0 | **B** | P.CustomerID | Numeric |
| P0 | **C** | P.SoinsID | Numeric |
| P0 | **D** | P.DateDebut | Date |
| P0 | **E** | P.TimeDebut | Time |
| P0 | **F** | P.DateFin | Date |
| P0 | **G** | P.TimeFin | Time |
| P0 | **H** | P.PraticienID | Numeric |
| P0 | **I** | P.CabineID | Numeric |
| P0 | **J** | P.BookingID | Unicode |
| P0 | **K** | P.OrderID | Numeric |
| P0 | **L** | P.BookerCustID | Numeric |
| P0 | **M** | P.RecoveryTime | Numeric |
| V. | **T** | V.TimeFin(+RecoveryTime) | Time |
| Autre | **N** | Token | Unicode |
| Autre | **O** | LocationID | Numeric |
| Autre | **P** | typeRequest | Alpha |
| Autre | **Q** | UrlApi | Alpha |
| Autre | **R** | TimestampDebut | Unicode |
| Autre | **S** | TimeStampFin | Unicode |
| Autre | **U** | id_customer_bookerAlpha | Unicode |
| Autre | **V** | JsonIN | Blob |
| Autre | **W** | IsSuccessToken | Logical |
| Autre | **X** | ErrorMessageToken | Alpha |
| Autre | **Y** | IsSuccess | Logical |
| Autre | **Z** | ErrorMessage | Alpha |
| Autre | **BA** | JsonResponse | Blob |
| Autre | **BB** | XMLResponse | Blob |

</details>

## 12. EXPRESSIONS

**14 / 14 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCULATION | 3 | 0 |
| CONCATENATION | 1 | 0 |
| CONDITION | 1 | 5 |
| CONSTANTE | 1 | 0 |
| FORMAT | 1 | 0 |
| DATE | 1 | 0 |
| REFERENCE_VG | 3 | 0 |
| OTHER | 3 | 0 |

### 12.2 Expressions cles par type

#### CALCULATION (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 9 | `Right(P.AppointmentID [A],Len(P.AppointmentID [A]) - 3)` | - |
| CALCULATION | 4 | `Trim(VG66) & '/v4.1/merchant/appointment'` | - |
| CALCULATION | 3 | `Trim(VG66) & '/appointment'` | - |

#### CONCATENATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 6 | `'<?xml version="1.0" encoding="UTF-8"?>' &ASCIIChr(13)& ASCIIChr(10)&DotNet.System.Xml.Linq.XElement.Load(  DotNet.System.Runtime.Serialization.Json.JsonReaderWriterFactory.CreateJsonReader( [AE],DotNet.System.Xml.XmlDictionaryReaderQuotas()   )).ToString()` | - |

#### CONDITION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 8 | `IF(ErrorMessageToken [X] = 0,'null',Str(ErrorMessageToken [X],'10'))` | [RM-001](#rm-RM-001) |

#### CONSTANTE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 2 | `'PUT'` | - |

#### FORMAT (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| FORMAT | 5 | `'{
    "AppointmentDate": "/Date(' & Trim(TimestampDebut [R]) & ')/",
    "AppointmentTreatmentDTOs": [
        {
            "AppointmentTreatmentID": null,
            "Employee2ID": null,
            "EmployeeID": ' & Trim(Str(P.PraticienID [H],'10')) & ',
            "EmployeeWasRequested": null,
            "EndTime": "/Date(' & Trim(TimeStampFin [S]) & ')/",
            "GapFinishDuration": null,
            "GapProcessingDuration": null,
            "GapStartDuration": null,
            "IsDurationOverridden": null,
            "LockToTechnician": null,
            "RecoveryTime": ' & Trim(Str(P.RecoveryTime [M],'3')) & ',
            "RoomID":' & Trim(Str(P.CabineID [I],'10')) & ',
            "StartTime": "/Date(' & Trim(TimestampDebut [R]) & ')/",
            "TreatmentID": ' & Trim(Str(P.SoinsID [C],'10')) & '
        }
    ],
    "Customer": {
        "Email": "mail@clubmed.com",
        "FirstName": "' & Trim(IsSuccessToken [W]) & '",
        "HomePhone": "1234567890",
        "ID": ' & Trim(IsSuccess [Y]) & ',
        "LastName": "' & Trim(JsonIN [V]) & '",
        "MobilePhone": "1234567890"
	},
    "Customer2": null,
    "ID": ' & Trim(P.AppointmentID [A]) & ',
    "IsPackage": true,
    "MarkAsConfirmed": true,
    "Notes": "Customer appointment Note",
    "ResourceTypeID": 1,
    "SendCustomerEmail": true,
    "ShowAppointmentIconFlags": true,
    "CampaignID": null,
    "ReferredByCustomerID": null,
    "access_token": "' & Trim(Token [N]) & '"
}'` | - |

#### DATE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| DATE | 10 | `Date()` | - |

#### REFERENCE_VG (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 14 | `VG63` | - |
| REFERENCE_VG | 12 | `VG65` | - |
| REFERENCE_VG | 1 | `VG67` | - |

#### OTHER (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 13 | `AddTime(P.TimeFin [G],0,P.RecoveryTime [M],0)` | - |
| OTHER | 11 | `Time()` | - |
| OTHER | 7 | `P.CustomerID [B]` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [SearchBooking (IDE 153)](PVE-IDE-153.md) -> **UpdateAppointment (IDE 167)**

```mermaid
graph LR
    T167[167 UpdateAppointment]
    style T167 fill:#58a6ff
    CC143[143 START]
    style CC143 fill:#8b5cf6
    CC185[185 Menu]
    style CC185 fill:#f59e0b
    CC352[352 Main Sale ===V4 bck]
    style CC352 fill:#f59e0b
    CC363[363 Main Sale]
    style CC363 fill:#f59e0b
    CC214[214 Main Sale Sale Bar...]
    style CC214 fill:#f59e0b
    CC186[186 Main Sale]
    style CC186 fill:#f59e0b
    CC187[187 Main Sale-664]
    style CC187 fill:#f59e0b
    CC192[192 Select Product]
    style CC192 fill:#f59e0b
    CC153[153 SearchBooking]
    style CC153 fill:#3fb950
    CC186 --> CC153
    CC187 --> CC153
    CC192 --> CC153
    CC214 --> CC153
    CC363 --> CC153
    CC185 --> CC186
    CC352 --> CC186
    CC185 --> CC187
    CC352 --> CC187
    CC185 --> CC192
    CC352 --> CC192
    CC185 --> CC214
    CC352 --> CC214
    CC185 --> CC363
    CC352 --> CC363
    CC143 --> CC185
    CC143 --> CC352
    CC153 --> T167
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [153](PVE-IDE-153.md) | SearchBooking | 2 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T167[167 UpdateAppointment]
    style T167 fill:#58a6ff
    C151[151 GetToken]
    T167 --> C151
    style C151 fill:#3fb950
    C175[175 TraceLogBooker]
    T167 --> C175
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
| Lignes de logique | 78 | Programme compact |
| Expressions | 14 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 2 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 78) | Code sain |
| Regles metier | 1 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (2 taches: 0 ecran, 2 traitements)

- **Strategie** : 2 service(s) backend injectable(s) (Domain Services).
- 2 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| [TraceLogBooker (IDE 175)](PVE-IDE-175.md) | Sous-programme | 1x | Normale - Sous-programme |
| [GetToken (IDE 151)](PVE-IDE-151.md) | Sous-programme | 1x | Normale - Recuperation donnees |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 18:37*
