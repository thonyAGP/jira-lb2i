# PVE IDE 174 - GetLocationPaymentSettings

> **Analyse**: Phases 1-4 2026-02-03 18:40 -> 18:40 (18s) | Assemblage 18:40
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PVE |
| IDE Position | 174 |
| Nom Programme | GetLocationPaymentSettings |
| Fichier source | `Prg_174.xml` |
| Dossier IDE | Interface |
| Taches | 2 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 2 |

## 2. DESCRIPTION FONCTIONNELLE

**GetLocationPaymentSettings** assure la gestion complete de ce processus, accessible depuis [Print Invoice or Ticket (IDE 208)](PVE-IDE-208.md), [Print Invoice or Ticket-664 (IDE 209)](PVE-IDE-209.md), [Print Invoice or Ticket (IDE 358)](PVE-IDE-358.md), [Print Invoice or Ticket==NEW (IDE 429)](PVE-IDE-429.md), [AddPaymentToOrder (IDE 169)](PVE-IDE-169.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (2 taches) : traitements metier divers

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (2 taches)

Traitements internes.

---

#### <a id="t1"></a>174 - GetLocationPayment

**Role** : Consultation/chargement : GetLocationPayment.
**Delegue a** : [GetToken (IDE 151)](PVE-IDE-151.md), [TraceLogBooker (IDE 175)](PVE-IDE-175.md)

---

#### <a id="t2"></a>174.1 - ExtractDataFromXML

**Role** : Traitement : ExtractDataFromXML.
**Delegue a** : [GetToken (IDE 151)](PVE-IDE-151.md), [TraceLogBooker (IDE 175)](PVE-IDE-175.md)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Print Invoice or Ticket (IDE 208)](PVE-IDE-208.md), [Print Invoice or Ticket-664 (IDE 209)](PVE-IDE-209.md), [Print Invoice or Ticket (IDE 358)](PVE-IDE-358.md), [Print Invoice or Ticket==NEW (IDE 429)](PVE-IDE-429.md), [AddPaymentToOrder (IDE 169)](PVE-IDE-169.md)
- **Appelle**: 2 programmes | **Tables**: 0 (W:0 R:0 L:0) | **Taches**: 2 | **Expressions**: 9

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (2 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **174.1** | [**GetLocationPayment** (174)](#t1) | - | - | Traitement |
| 174.1.1 | [ExtractDataFromXML (174.1)](#t2) | - | - | |

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

### 11.1 Parametres entrants (2)

Variables recues du programme appelant ([Print Invoice or Ticket (IDE 208)](PVE-IDE-208.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P.LocationID | Numeric | 2x parametre entrant |
| B | P.PaymentID | Numeric | - |

### 11.2 Autres (10)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| C | Token | Unicode | 2x refs |
| D | typeRequest | Alpha | - |
| E | UrlApi | Alpha | - |
| F | JsonIN | Blob | - |
| G | IsSuccessToken | Logical | - |
| H | ErrorMessageToken | Alpha | - |
| I | IsSuccess | Logical | 1x refs |
| J | ErrorMessage | Alpha | - |
| K | JsonResponse | Blob | 1x refs |
| L | XmlResponse | Blob | - |

## 12. EXPRESSIONS

**9 / 9 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| FORMAT | 2 | 0 |
| CONCATENATION | 1 | 0 |
| CONSTANTE | 1 | 0 |
| DATE | 1 | 0 |
| OTHER | 2 | 0 |
| REFERENCE_VG | 2 | 0 |

### 12.2 Expressions cles par type

#### FORMAT (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| FORMAT | 3 | `Trim(VG66) & '/v4.1/merchant/location/' & Trim(Str(P.LocationID [A],'10')) & '/payment_settings?access_token=' & Trim(Token [C])` | - |
| FORMAT | 2 | `Trim(VG66) & '/location/' & Trim(Str(P.LocationID [A],'10')) & '/payment_settings?access_token=' & Trim(Token [C])` | - |

#### CONCATENATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 5 | `'<?xml version="1.0" encoding="UTF-8"?>' &
ASCIIChr(13)& ASCIIChr(10)&
DotNet.System.Xml.Linq.XElement.Load(
  DotNet.System.Runtime.Serialization.Json.JsonReaderWriterFactory.CreateJsonReader( 
     JsonResponse [K],
     DotNet.System.Xml.XmlDictionaryReaderQuotas()
   )
).ToString()` | - |

#### CONSTANTE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 1 | `'GET'` | - |

#### DATE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| DATE | 6 | `Date()` | - |

#### OTHER (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 7 | `Time()` | - |
| OTHER | 4 | `IsSuccess [I]` | - |

#### REFERENCE_VG (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 9 | `VG63` | - |
| REFERENCE_VG | 8 | `VG65` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Print Invoice or Ticket (IDE 208)](PVE-IDE-208.md) -> **GetLocationPaymentSettings (IDE 174)**

Main -> ... -> [Print Invoice or Ticket-664 (IDE 209)](PVE-IDE-209.md) -> **GetLocationPaymentSettings (IDE 174)**

Main -> ... -> [Print Invoice or Ticket (IDE 358)](PVE-IDE-358.md) -> **GetLocationPaymentSettings (IDE 174)**

Main -> ... -> [Print Invoice or Ticket==NEW (IDE 429)](PVE-IDE-429.md) -> **GetLocationPaymentSettings (IDE 174)**

Main -> ... -> [AddPaymentToOrder (IDE 169)](PVE-IDE-169.md) -> **GetLocationPaymentSettings (IDE 174)**

```mermaid
graph LR
    T174[174 GetLocationPayment...]
    style T174 fill:#58a6ff
    CC418[418 Generate Preview O...]
    style CC418 fill:#8b5cf6
    CC204[204 Choice Re_Print In...]
    style CC204 fill:#8b5cf6
    CC189[189 Generate Preview P...]
    style CC189 fill:#8b5cf6
    CC424[424 Generate Preview O...]
    style CC424 fill:#8b5cf6
    CC423[423 Generate Preview O...]
    style CC423 fill:#8b5cf6
    CC169[169 AddPaymentToOrder]
    style CC169 fill:#3fb950
    CC209[209 Print Invoice or T...]
    style CC209 fill:#3fb950
    CC208[208 Print Invoice or T...]
    style CC208 fill:#3fb950
    CC429[429 Print Invoice or T...]
    style CC429 fill:#3fb950
    CC358[358 Print Invoice or T...]
    style CC358 fill:#3fb950
    CC189 --> CC169
    CC204 --> CC169
    CC418 --> CC169
    CC423 --> CC169
    CC424 --> CC169
    CC189 --> CC208
    CC204 --> CC208
    CC418 --> CC208
    CC423 --> CC208
    CC424 --> CC208
    CC189 --> CC209
    CC204 --> CC209
    CC418 --> CC209
    CC423 --> CC209
    CC424 --> CC209
    CC189 --> CC358
    CC204 --> CC358
    CC418 --> CC358
    CC423 --> CC358
    CC424 --> CC358
    CC189 --> CC429
    CC204 --> CC429
    CC418 --> CC429
    CC423 --> CC429
    CC424 --> CC429
    CC169 --> T174
    CC208 --> T174
    CC209 --> T174
    CC358 --> T174
    CC429 --> T174
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [208](PVE-IDE-208.md) | Print Invoice or Ticket | 2 |
| [209](PVE-IDE-209.md) | Print Invoice or Ticket-664 | 2 |
| [358](PVE-IDE-358.md) | Print Invoice or Ticket | 2 |
| [429](PVE-IDE-429.md) | Print Invoice or Ticket==NEW | 2 |
| [169](PVE-IDE-169.md) | AddPaymentToOrder | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T174[174 GetLocationPayment...]
    style T174 fill:#58a6ff
    C151[151 GetToken]
    T174 --> C151
    style C151 fill:#3fb950
    C175[175 TraceLogBooker]
    T174 --> C175
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
| Lignes de logique | 57 | Programme compact |
| Expressions | 9 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 2 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 57) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

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
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 18:40*
