# REF IDE 633 - Club Med API token

> **Analyse**: Phases 1-4 2026-02-03 13:17 -> 13:17 (18s) | Assemblage 13:17
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | REF |
| IDE Position | 633 |
| Nom Programme | Club Med API token |
| Fichier source | `Prg_633.xml` |
| Dossier IDE | General |
| Taches | 3 (0 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 1 |

## 2. DESCRIPTION FONCTIONNELLE

**Club Med API token** assure la gestion complete de ce processus, accessible depuis [Club Med API demo (IDE 635)](REF-IDE-635.md), [Pilotage API CM Paiements (IDE 637)](REF-IDE-637.md), [Pilotage API CM Stay (IDE 639)](REF-IDE-639.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (3 taches) : traitements metier divers

**Donnees modifiees** : 1 tables en ecriture (initialisation___ini).

**Logique metier** : 1 regles identifiees couvrant conditions metier.

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (3 taches)

Traitements internes.

---

#### <a id="t1"></a>633 - Club Med API token

**Role** : Traitement : Club Med API token.
**Variables liees** : A (P.o.Access Token), U (v.Access Token), V (v.Token type)
**Delegue a** : [Log batch (IDE 829)](REF-IDE-829.md)

---

#### <a id="t2"></a>633.1 - XML refresh/access token

**Role** : Traitement : XML refresh/access token.
**Variables liees** : A (P.o.Access Token), U (v.Access Token), V (v.Token type)
**Delegue a** : [Log batch (IDE 829)](REF-IDE-829.md)

---

#### <a id="t3"></a>633.2 - Lecture paramètres API

**Role** : Traitement : Lecture paramètres API.
**Delegue a** : [Log batch (IDE 829)](REF-IDE-829.md)


## 5. REGLES METIER

1 regles identifiees:

### Autres (1 regles)

#### <a id="rm-RM-001"></a>[RM-001] Si v.XML response [R] alors 'OK' sinon 'ERR')

| Element | Detail |
|---------|--------|
| **Condition** | `v.XML response [R]` |
| **Si vrai** | 'OK' |
| **Si faux** | 'ERR') |
| **Variables** | R (v.XML response) |
| **Expression source** | Expression 11 : `IF(v.XML response [R], 'OK', 'ERR')` |
| **Exemple** | Si v.XML response [R] â†’ 'OK'. Sinon â†’ 'ERR') |

## 6. CONTEXTE

- **Appele par**: [Club Med API demo (IDE 635)](REF-IDE-635.md), [Pilotage API CM Paiements (IDE 637)](REF-IDE-637.md), [Pilotage API CM Stay (IDE 639)](REF-IDE-639.md)
- **Appelle**: 1 programmes | **Tables**: 2 (W:1 R:0 L:1) | **Taches**: 3 | **Expressions**: 23

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (3 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **633.1** | [**Club Med API token** (633)](#t1) | - | - | Traitement |
| 633.1.1 | [XML refresh/access token (633.1)](#t2) | - | - | |
| 633.1.2 | [Lecture paramètres API (633.2)](#t3) | - | - | |

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

### Tables utilisees (2)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 69 | initialisation___ini |  | DB |   | **W** |   | 1 |
| 368 | pms_village |  | DB |   |   | L | 1 |

### Colonnes par table (0 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 69 - initialisation___ini (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (9)

Variables recues du programme appelant ([Club Med API demo (IDE 635)](REF-IDE-635.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P.o.Access Token | Unicode | - |
| B | P.i.Client_id | Unicode | 2x parametre entrant |
| C | P.i.Client_secret | Unicode | 1x parametre entrant |
| D | P.i.Grant_type | Unicode | 1x parametre entrant |
| E | P.i.Scope | Unicode | 1x parametre entrant |
| F | P.i.UrlApi | Unicode | 1x parametre entrant |
| G | P.i.Proxy adress http | Unicode | 1x parametre entrant |
| H | P.i.BypassProxyOnLocalAdr | Logical | 1x parametre entrant |
| I | P.o.Expiration Time | Time | 1x parametre entrant |

### 11.2 Variables de session (16)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| J | v.Client_id | Unicode | 1x session |
| K | v.Client_secret | Unicode | - |
| L | v.Grant_type | Unicode | - |
| M | v.Scope | Unicode | 1x session |
| N | v.UrlApi | Unicode | - |
| O | v.Proxy adress http | Unicode | - |
| P | v.BypassProxyOnLocalAdr | Logical | 2x session |
| Q | v.JSonResponse | Blob | - |
| R | v.XML response | Blob | 1x session |
| S | v.IsSuccess | Logical | 2x session |
| T | v.ErrorMessage | Alpha | 2x session |
| U | v.Access Token | Unicode | [633](#t1), [633.1](#t2) |
| V | v.Token type | Unicode | 1x session |
| W | v.Expiration | Unicode | 1x session |
| X | v.Id batch | Numeric | - |
| Y | v.time | Time | 1x session |

<details>
<summary>Toutes les 25 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| P0 | **A** | P.o.Access Token | Unicode |
| P0 | **B** | P.i.Client_id | Unicode |
| P0 | **C** | P.i.Client_secret | Unicode |
| P0 | **D** | P.i.Grant_type | Unicode |
| P0 | **E** | P.i.Scope | Unicode |
| P0 | **F** | P.i.UrlApi | Unicode |
| P0 | **G** | P.i.Proxy adress http | Unicode |
| P0 | **H** | P.i.BypassProxyOnLocalAdr | Logical |
| P0 | **I** | P.o.Expiration Time | Time |
| V. | **J** | v.Client_id | Unicode |
| V. | **K** | v.Client_secret | Unicode |
| V. | **L** | v.Grant_type | Unicode |
| V. | **M** | v.Scope | Unicode |
| V. | **N** | v.UrlApi | Unicode |
| V. | **O** | v.Proxy adress http | Unicode |
| V. | **P** | v.BypassProxyOnLocalAdr | Logical |
| V. | **Q** | v.JSonResponse | Blob |
| V. | **R** | v.XML response | Blob |
| V. | **S** | v.IsSuccess | Logical |
| V. | **T** | v.ErrorMessage | Alpha |
| V. | **U** | v.Access Token | Unicode |
| V. | **V** | v.Token type | Unicode |
| V. | **W** | v.Expiration | Unicode |
| V. | **X** | v.Id batch | Numeric |
| V. | **Y** | v.time | Time |

</details>

## 12. EXPRESSIONS

**23 / 23 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONCATENATION | 1 | 0 |
| CONDITION | 3 | 5 |
| CONSTANTE | 4 | 0 |
| OTHER | 14 | 0 |
| STRING | 1 | 0 |

### 12.2 Expressions cles par type

#### CONCATENATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 1 | `'<?xml version="1.0" encoding="UTF-8"?>' &
ASCIIChr(13)& ASCIIChr(10)&
DotNet.System.Xml.Linq.XElement.Load(
  DotNet.System.Runtime.Serialization.Json.JsonReaderWriterFactory.CreateJsonReader( 
     v.BypassProxyOnLocalAdr [P],
     DotNet.System.Xml.XmlDictionaryReaderQuotas()
   )
).ToString()` | - |

#### CONDITION (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 11 | `IF(v.XML response [R], 'OK', 'ERR')` | [RM-001](#rm-RM-001) |
| CONDITION | 14 | `Trim(P.i.Client_id [B])=''` | - |
| CONDITION | 2 | `v.Access Token [U]='Bearer' AND v.ErrorMessage [T]<>''` | - |

#### CONSTANTE (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 7 | `'DEB'` | - |
| CONSTANTE | 10 | `'json'` | - |
| CONSTANTE | 4 | `'ClubMedAPI'` | - |
| CONSTANTE | 5 | `'Token'` | - |

#### OTHER (14 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 18 | `P.i.Scope [E]` | - |
| OTHER | 17 | `P.i.Grant_type [D]` | - |
| OTHER | 16 | `P.i.Client_secret [C]` | - |
| OTHER | 19 | `P.i.UrlApi [F]` | - |
| OTHER | 22 | `Time()` | - |
| ... | | *+9 autres* | |

#### STRING (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| STRING | 23 | `AddTime(v.time [Y],0,0,Val(v.Token type [V],'8'))` | - |

### 12.3 Toutes les expressions (23)

<details>
<summary>Voir les 23 expressions</summary>

#### CONCATENATION (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 1 | `'<?xml version="1.0" encoding="UTF-8"?>' &
ASCIIChr(13)& ASCIIChr(10)&
DotNet.System.Xml.Linq.XElement.Load(
  DotNet.System.Runtime.Serialization.Json.JsonReaderWriterFactory.CreateJsonReader( 
     v.BypassProxyOnLocalAdr [P],
     DotNet.System.Xml.XmlDictionaryReaderQuotas()
   )
).ToString()` |

#### CONDITION (3)

| IDE | Expression Decodee |
|-----|-------------------|
| 11 | `IF(v.XML response [R], 'OK', 'ERR')` |
| 2 | `v.Access Token [U]='Bearer' AND v.ErrorMessage [T]<>''` |
| 14 | `Trim(P.i.Client_id [B])=''` |

#### CONSTANTE (4)

| IDE | Expression Decodee |
|-----|-------------------|
| 4 | `'ClubMedAPI'` |
| 5 | `'Token'` |
| 7 | `'DEB'` |
| 10 | `'json'` |

#### OTHER (14)

| IDE | Expression Decodee |
|-----|-------------------|
| 3 | `StrBuild('Json error @1@ ; Client Id @2@, Client Secret @3@', v.IsSuccess [S], P.o.Expiration Time [I], v.Client_id [J])` |
| 6 | `v.Scope [M]` |
| 8 | `v.Expiration [W]` |
| 9 | `v.BypassProxyOnLocalAdr [P]` |
| 12 | `v.IsSuccess [S]` |
| 13 | `v.ErrorMessage [T]` |
| 15 | `P.i.Client_id [B]` |
| 16 | `P.i.Client_secret [C]` |
| 17 | `P.i.Grant_type [D]` |
| 18 | `P.i.Scope [E]` |
| 19 | `P.i.UrlApi [F]` |
| 20 | `P.i.Proxy adress http [G]` |
| 21 | `P.i.BypassProxyOnLocalAdr [H]` |
| 22 | `Time()` |

#### STRING (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 23 | `AddTime(v.time [Y],0,0,Val(v.Token type [V],'8'))` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Club Med API demo (IDE 635)](REF-IDE-635.md) -> **Club Med API token (IDE 633)**

Main -> ... -> [Pilotage API CM Paiements (IDE 637)](REF-IDE-637.md) -> **Club Med API token (IDE 633)**

Main -> ... -> [Pilotage API CM Stay (IDE 639)](REF-IDE-639.md) -> **Club Med API token (IDE 633)**

```mermaid
graph LR
    T633[633 Club Med API token]
    style T633 fill:#58a6ff
    CC713[713 Test Execution TPE]
    style CC713 fill:#8b5cf6
    CC718[718 Appel Gestion TPE ...]
    style CC718 fill:#f59e0b
    CC712[712 Gestion TPE Axis O...]
    style CC712 fill:#f59e0b
    CC884[884 Appel Routes]
    style CC884 fill:#f59e0b
    CC638[638 Controle Presence ...]
    style CC638 fill:#f59e0b
    CC635[635 Club Med API demo]
    style CC635 fill:#3fb950
    CC637[637 Pilotage API CM Pa...]
    style CC637 fill:#3fb950
    CC639[639 Pilotage API CM Stay]
    style CC639 fill:#3fb950
    CC638 --> CC635
    CC712 --> CC635
    CC884 --> CC635
    CC638 --> CC637
    CC712 --> CC637
    CC884 --> CC637
    CC638 --> CC639
    CC712 --> CC639
    CC884 --> CC639
    CC718 --> CC638
    CC718 --> CC712
    CC718 --> CC884
    CC713 --> CC718
    CC635 --> T633
    CC637 --> T633
    CC639 --> T633
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [635](REF-IDE-635.md) | Club Med API demo | 1 |
| [637](REF-IDE-637.md) | Pilotage API CM Paiements | 1 |
| [639](REF-IDE-639.md) | Pilotage API CM Stay | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T633[633 Club Med API token]
    style T633 fill:#58a6ff
    C829[829 Log batch]
    T633 --> C829
    style C829 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [829](REF-IDE-829.md) | Log batch | 2 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 85 | Programme compact |
| Expressions | 23 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 1 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 85) | Code sain |
| Regles metier | 1 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (3 taches: 0 ecran, 3 traitements)

- **Strategie** : 3 service(s) backend injectable(s) (Domain Services).
- 1 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| initialisation___ini | Table WRITE (Database) | 1x | Schema + repository |
| [Log batch (IDE 829)](REF-IDE-829.md) | Sous-programme | 2x | Haute - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 13:17*
