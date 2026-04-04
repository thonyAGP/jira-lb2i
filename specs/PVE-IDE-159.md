# PVE IDE 159 - CancelAppointment

> **Analyse**: Phases 1-4 2026-02-03 09:49 -> 09:50 (21s) | Assemblage 09:50
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PVE |
| IDE Position | 159 |
| Nom Programme | CancelAppointment |
| Fichier source | `Prg_159.xml` |
| Domaine metier | General |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 2 |

## 2. DESCRIPTION FONCTIONNELLE

**CancelAppointment** assure la gestion complete de ce processus, accessible depuis [Print Invoice or Ticket (IDE 208)](PVE-IDE-208.md), [Print Invoice or Ticket-664 (IDE 209)](PVE-IDE-209.md), [Print Invoice or Ticket (IDE 358)](PVE-IDE-358.md), [Print Invoice or Ticket==NEW (IDE 429)](PVE-IDE-429.md), [Delete Product (IDE 194)](PVE-IDE-194.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>159 - CancelAppointment

**Role** : Traitement : CancelAppointment.
**Delegue a** : [GetToken (IDE 151)](PVE-IDE-151.md), [TraceLogBooker (IDE 175)](PVE-IDE-175.md)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Print Invoice or Ticket (IDE 208)](PVE-IDE-208.md), [Print Invoice or Ticket-664 (IDE 209)](PVE-IDE-209.md), [Print Invoice or Ticket (IDE 358)](PVE-IDE-358.md), [Print Invoice or Ticket==NEW (IDE 429)](PVE-IDE-429.md), [Delete Product (IDE 194)](PVE-IDE-194.md)
- **Appelle**: 2 programmes | **Tables**: 0 (W:0 R:0 L:0) | **Taches**: 1 | **Expressions**: 10

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **159.1** | [**CancelAppointment** (159)](#t1) | - | - | Traitement |

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

### Tables utilisees (0)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|

### Colonnes par table (0 / 0 tables avec colonnes identifiees)

## 11. VARIABLES

### 11.1 Parametres entrants (1)

Variables recues du programme appelant ([Print Invoice or Ticket (IDE 208)](PVE-IDE-208.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P.BookingID | Unicode | 1x parametre entrant |

### 11.2 Autres (11)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| B | Token | Unicode | 1x refs |
| C | LocationID | Numeric | - |
| D | typeRequest | Alpha | - |
| E | UrlApi | Alpha | - |
| F | JsonIN | Blob | - |
| G | IsSuccessToken | Logical | - |
| H | ErrorMessageToken | Alpha | - |
| I | IsSuccess | Logical | - |
| J | ErrorMessage | Alpha | - |
| K | JsonResponse | Blob | 1x refs |
| L | XMLResponse | Blob | - |

## 12. EXPRESSIONS

**10 / 10 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCULATION | 2 | 0 |
| CONCATENATION | 2 | 0 |
| CONSTANTE | 1 | 0 |
| DATE | 1 | 0 |
| REFERENCE_VG | 3 | 0 |
| OTHER | 1 | 0 |

### 12.2 Expressions cles par type

#### CALCULATION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 4 | `Trim(VG66) & '/v4.1/merchant/appointment/cancel'` | - |
| CALCULATION | 3 | `Trim(VG66) & '/appointment/cancel'` | - |

#### CONCATENATION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 5 | `'{
    "ID": ' & Trim(P.BookingID [A]) & ',
    "access_token": "' & Trim(Token [B]) & '",
    "SkipItemsForOtherAppointmentsInGroup": null,
    "CancellationReasonID": null,
    "AppointmentCancellationType": {
        "ID": null,
        "Name": ""
    },
    "ShowAppointmentIconFlags": true,
    "RequireCancellationReason": false
}'` | - |
| CONCATENATION | 6 | `'<?xml version="1.0" encoding="UTF-8"?>' &ASCIIChr(13)& ASCIIChr(10)&DotNet.System.Xml.Linq.XElement.Load(  DotNet.System.Runtime.Serialization.Json.JsonReaderWriterFactory.CreateJsonReader( JsonResponse [K],DotNet.System.Xml.XmlDictionaryReaderQuotas()   )).ToString()` | - |

#### CONSTANTE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 2 | `'PUT'` | - |

#### DATE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| DATE | 7 | `Date()` | - |

#### REFERENCE_VG (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 10 | `VG63` | - |
| REFERENCE_VG | 9 | `VG65` | - |
| REFERENCE_VG | 1 | `VG67` | - |

#### OTHER (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 8 | `Time()` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Print Invoice or Ticket (IDE 208)](PVE-IDE-208.md) -> **CancelAppointment (IDE 159)**

Main -> ... -> [Print Invoice or Ticket-664 (IDE 209)](PVE-IDE-209.md) -> **CancelAppointment (IDE 159)**

Main -> ... -> [Print Invoice or Ticket (IDE 358)](PVE-IDE-358.md) -> **CancelAppointment (IDE 159)**

Main -> ... -> [Print Invoice or Ticket==NEW (IDE 429)](PVE-IDE-429.md) -> **CancelAppointment (IDE 159)**

Main -> ... -> [Delete Product (IDE 194)](PVE-IDE-194.md) -> **CancelAppointment (IDE 159)**

```mermaid
graph LR
    T159[159 CancelAppointment]
    style T159 fill:#58a6ff
    CC187[187 Main Sale-664]
    style CC187 fill:#8b5cf6
    CC186[186 Main Sale]
    style CC186 fill:#8b5cf6
    CC192[192 Select Product]
    style CC192 fill:#8b5cf6
    CC214[214 Main Sale Sale Bar...]
    style CC214 fill:#8b5cf6
    CC194[194 Delete Product]
    style CC194 fill:#3fb950
    CC209[209 Print Invoice or T...]
    style CC209 fill:#3fb950
    CC208[208 Print Invoice or T...]
    style CC208 fill:#3fb950
    CC429[429 Print Invoice or T...]
    style CC429 fill:#3fb950
    CC358[358 Print Invoice or T...]
    style CC358 fill:#3fb950
    CC186 --> CC194
    CC187 --> CC194
    CC192 --> CC194
    CC214 --> CC194
    CC186 --> CC208
    CC187 --> CC208
    CC192 --> CC208
    CC214 --> CC208
    CC186 --> CC209
    CC187 --> CC209
    CC192 --> CC209
    CC214 --> CC209
    CC186 --> CC358
    CC187 --> CC358
    CC192 --> CC358
    CC214 --> CC358
    CC186 --> CC429
    CC187 --> CC429
    CC192 --> CC429
    CC214 --> CC429
    CC194 --> T159
    CC208 --> T159
    CC209 --> T159
    CC358 --> T159
    CC429 --> T159
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [208](PVE-IDE-208.md) | Print Invoice or Ticket | 2 |
| [209](PVE-IDE-209.md) | Print Invoice or Ticket-664 | 2 |
| [358](PVE-IDE-358.md) | Print Invoice or Ticket | 2 |
| [429](PVE-IDE-429.md) | Print Invoice or Ticket==NEW | 2 |
| [194](PVE-IDE-194.md) | Delete Product | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T159[159 CancelAppointment]
    style T159 fill:#58a6ff
    C151[151 GetToken]
    T159 --> C151
    style C151 fill:#3fb950
    C175[175 TraceLogBooker]
    T159 --> C175
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
| Lignes de logique | 35 | Programme compact |
| Expressions | 10 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 2 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 35) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 0 ecran, 1 traitement)

- **Strategie** : 1 service(s) backend injectable(s) (Domain Services).
- 2 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| [TraceLogBooker (IDE 175)](PVE-IDE-175.md) | Sous-programme | 1x | Normale - Sous-programme |
| [GetToken (IDE 151)](PVE-IDE-151.md) | Sous-programme | 1x | Normale - Recuperation donnees |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 09:50*
