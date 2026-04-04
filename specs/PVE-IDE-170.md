# PVE IDE 170 - AddSpecialToOrder-392

> **Analyse**: Phases 1-4 2026-02-03 18:38 -> 18:38 (18s) | Assemblage 18:38
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PVE |
| IDE Position | 170 |
| Nom Programme | AddSpecialToOrder-392 |
| Fichier source | `Prg_170.xml` |
| Dossier IDE | Interface |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 2 |

## 2. DESCRIPTION FONCTIONNELLE

**AddSpecialToOrder-392** assure la gestion complete de ce processus, accessible depuis [Print Invoice or Ticket (IDE 208)](PVE-IDE-208.md), [Print Invoice or Ticket-664 (IDE 209)](PVE-IDE-209.md), [Print Invoice or Ticket (IDE 358)](PVE-IDE-358.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

**Logique metier** : 1 regles identifiees couvrant conditions metier.

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>170 - AddSpecialToOrder-392

**Role** : Traitement : AddSpecialToOrder-392.
**Delegue a** : [GetToken (IDE 151)](PVE-IDE-151.md), [TraceLogBooker (IDE 175)](PVE-IDE-175.md)


## 5. REGLES METIER

1 regles identifiees:

### Autres (1 regles)

#### <a id="rm-RM-001"></a>[RM-001] Traitement si P.Payment_FBOv1.00 [E] est renseigne

| Element | Detail |
|---------|--------|
| **Condition** | `P.Payment_FBOv1.00 [E]<>''` |
| **Si vrai** | P.Payment_FBOv1.00 [E] |
| **Si faux** | 'Marketing') |
| **Variables** | E (P.Payment_FBOv1.00) |
| **Expression source** | Expression 2 : `IF(P.Payment_FBOv1.00 [E]<>'',P.Payment_FBOv1.00 [E],'Market` |
| **Exemple** | Si P.Payment_FBOv1.00 [E]<>'' â†’ P.Payment_FBOv1.00 [E]. Sinon â†’ 'Marketing') |

## 6. CONTEXTE

- **Appele par**: [Print Invoice or Ticket (IDE 208)](PVE-IDE-208.md), [Print Invoice or Ticket-664 (IDE 209)](PVE-IDE-209.md), [Print Invoice or Ticket (IDE 358)](PVE-IDE-358.md)
- **Appelle**: 2 programmes | **Tables**: 0 (W:0 R:0 L:0) | **Taches**: 1 | **Expressions**: 16

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **170.1** | [**AddSpecialToOrder-392** (170)](#t1) | - | - | Traitement |

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

### 11.1 Parametres entrants (5)

Variables recues du programme appelant ([Print Invoice or Ticket (IDE 208)](PVE-IDE-208.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P.OrderID | Numeric | 2x parametre entrant |
| B | P.Amount | Numeric | - |
| C | P.Currency | Unicode | - |
| D | P.CustomPaymentMethodeID | Numeric | 1x parametre entrant |
| E | P.Payment_FBOv1.00 | Unicode | 1x parametre entrant |

### 11.2 Variables de session (1)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| T | V.Special ID | Unicode | 1x session |

### 11.3 Autres (14)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| F | PaymentMethodeID | Numeric | 1x refs |
| G | PaymentMethodeName | Unicode | - |
| H | CustomPaymentMethodID | Numeric | - |
| I | Token | Unicode | 1x refs |
| J | LocationID | Numeric | - |
| K | typeRequest | Alpha | - |
| L | UrlApi | Alpha | - |
| M | JsonIN | Blob | - |
| N | IsSuccessToken | Logical | - |
| O | ErrorMessageToken | Alpha | - |
| P | IsSuccess | Logical | - |
| Q | ErrorMessage | Alpha | - |
| R | JsonResponse | Blob | 1x refs |
| S | XMLResponse | Blob | - |

<details>
<summary>Toutes les 20 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| P0 | **A** | P.OrderID | Numeric |
| P0 | **B** | P.Amount | Numeric |
| P0 | **C** | P.Currency | Unicode |
| P0 | **D** | P.CustomPaymentMethodeID | Numeric |
| P0 | **E** | P.Payment_FBOv1.00 | Unicode |
| V. | **T** | V.Special ID | Unicode |
| Autre | **F** | PaymentMethodeID | Numeric |
| Autre | **G** | PaymentMethodeName | Unicode |
| Autre | **H** | CustomPaymentMethodID | Numeric |
| Autre | **I** | Token | Unicode |
| Autre | **J** | LocationID | Numeric |
| Autre | **K** | typeRequest | Alpha |
| Autre | **L** | UrlApi | Alpha |
| Autre | **M** | JsonIN | Blob |
| Autre | **N** | IsSuccessToken | Logical |
| Autre | **O** | ErrorMessageToken | Alpha |
| Autre | **P** | IsSuccess | Logical |
| Autre | **Q** | ErrorMessage | Alpha |
| Autre | **R** | JsonResponse | Blob |
| Autre | **S** | XMLResponse | Blob |

</details>

## 12. EXPRESSIONS

**16 / 16 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONCATENATION | 2 | 0 |
| FORMAT | 2 | 0 |
| CONDITION | 2 | 5 |
| CONSTANTE | 3 | 0 |
| DATE | 1 | 0 |
| OTHER | 2 | 0 |
| REFERENCE_VG | 4 | 0 |

### 12.2 Expressions cles par type

#### CONCATENATION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 10 | `'{"SpecialIDs": ['&Trim(V.Special ID [T])&'], "access_token": "' & Trim(Token [I]) & '"}'` | - |
| CONCATENATION | 6 | `'<?xml version="1.0" encoding="UTF-8"?>' &ASCIIChr(13)& ASCIIChr(10)&DotNet.System.Xml.Linq.XElement.Load(  DotNet.System.Runtime.Serialization.Json.JsonReaderWriterFactory.CreateJsonReader( JsonResponse [R],DotNet.System.Xml.XmlDictionaryReaderQuotas()   )).ToString()` | - |

#### FORMAT (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| FORMAT | 12 | `Trim(VG66) & '/v4.1/merchant/order/' & Trim(Str(P.OrderID [A],'18')) & '/add_special'` | - |
| FORMAT | 11 | `Trim(VG66) & '/order/' & Trim(Str(P.OrderID [A],'18')) & '/add_special'` | - |

#### CONDITION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 2 | `IF(P.Payment_FBOv1.00 [E]<>'',P.Payment_FBOv1.00 [E],'Marketing')` | [RM-001](#rm-RM-001) |
| CONDITION | 15 | `VG77=''` | - |

#### CONSTANTE (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 14 | `'Booker special ID is not set'` | - |
| CONSTANTE | 5 | `'POST'` | - |
| CONSTANTE | 1 | `11` | - |

#### DATE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| DATE | 7 | `Date()` | - |

#### OTHER (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 8 | `Time()` | - |
| OTHER | 3 | `P.CustomPaymentMethodeID [D]` | - |

#### REFERENCE_VG (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 13 | `VG77` | - |
| REFERENCE_VG | 16 | `VG63` | - |
| REFERENCE_VG | 4 | `VG67` | - |
| REFERENCE_VG | 9 | `VG65` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Print Invoice or Ticket (IDE 208)](PVE-IDE-208.md) -> **AddSpecialToOrder-392 (IDE 170)**

Main -> ... -> [Print Invoice or Ticket-664 (IDE 209)](PVE-IDE-209.md) -> **AddSpecialToOrder-392 (IDE 170)**

Main -> ... -> [Print Invoice or Ticket (IDE 358)](PVE-IDE-358.md) -> **AddSpecialToOrder-392 (IDE 170)**

```mermaid
graph LR
    T170[170 AddSpecialToOrder-392]
    style T170 fill:#58a6ff
    CC423[423 Generate Preview O...]
    style CC423 fill:#8b5cf6
    CC436[436 Generate Preview P...]
    style CC436 fill:#8b5cf6
    CC424[424 Generate Preview O...]
    style CC424 fill:#8b5cf6
    CC435[435 Generate Preview P...]
    style CC435 fill:#8b5cf6
    CC434[434 Generate Preview P...]
    style CC434 fill:#8b5cf6
    CC418[418 Generate Preview O...]
    style CC418 fill:#8b5cf6
    CC189[189 Generate Preview P...]
    style CC189 fill:#8b5cf6
    CC204[204 Choice Re_Print In...]
    style CC204 fill:#8b5cf6
    CC208[208 Print Invoice or T...]
    style CC208 fill:#3fb950
    CC358[358 Print Invoice or T...]
    style CC358 fill:#3fb950
    CC209[209 Print Invoice or T...]
    style CC209 fill:#3fb950
    CC189 --> CC208
    CC204 --> CC208
    CC418 --> CC208
    CC423 --> CC208
    CC424 --> CC208
    CC434 --> CC208
    CC435 --> CC208
    CC436 --> CC208
    CC189 --> CC209
    CC204 --> CC209
    CC418 --> CC209
    CC423 --> CC209
    CC424 --> CC209
    CC434 --> CC209
    CC435 --> CC209
    CC436 --> CC209
    CC189 --> CC358
    CC204 --> CC358
    CC418 --> CC358
    CC423 --> CC358
    CC424 --> CC358
    CC434 --> CC358
    CC435 --> CC358
    CC436 --> CC358
    CC208 --> T170
    CC209 --> T170
    CC358 --> T170
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [208](PVE-IDE-208.md) | Print Invoice or Ticket | 1 |
| [209](PVE-IDE-209.md) | Print Invoice or Ticket-664 | 1 |
| [358](PVE-IDE-358.md) | Print Invoice or Ticket | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T170[170 AddSpecialToOrder-392]
    style T170 fill:#58a6ff
    C151[151 GetToken]
    T170 --> C151
    style C151 fill:#3fb950
    C175[175 TraceLogBooker]
    T170 --> C175
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
| Lignes de logique | 49 | Programme compact |
| Expressions | 16 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 2 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 49) | Code sain |
| Regles metier | 1 | Quelques regles a preserver |

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
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 18:38*
