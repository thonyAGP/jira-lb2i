# REF IDE 634 - Appel Curl API

> **Analyse**: Phases 1-4 2026-02-03 13:17 -> 13:18 (22s) | Assemblage 13:18
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | REF |
| IDE Position | 634 |
| Nom Programme | Appel Curl API |
| Fichier source | `Prg_634.xml` |
| Dossier IDE | General |
| Taches | 4 (0 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 1 |

## 2. DESCRIPTION FONCTIONNELLE

**Appel Curl API** assure la gestion complete de ce processus, accessible depuis [Pilotage API CM Stay (IDE 639)](REF-IDE-639.md), [Club Med API demo (IDE 635)](REF-IDE-635.md), [Pilotage API CM Paiements (IDE 637)](REF-IDE-637.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (4 taches) : traitements metier divers

**Donnees modifiees** : 1 tables en ecriture (initialisation___ini).

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (4 taches)

- **634** - ClubMedAPICall
- **634.1** - Lecture paramètres API
- **634.2** - Write curl
- **634.3** - XML refresh/access token

Delegue a : [DateTimeToUnixTimeStamp (IDE 798)](REF-IDE-798.md)

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| initialisation___ini | **W** (1 usages) |  |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (4 taches)

Traitements internes.

---

#### <a id="t1"></a>634 - ClubMedAPICall

**Role** : Traitement : ClubMedAPICall.

<details>
<summary>3 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [634.1](#t2) | Lecture paramètres API | Traitement |
| [634.2](#t3) | Write curl | Traitement |
| [634.3](#t4) | XML refresh/access token | Traitement |

</details>
**Delegue a** : [DateTimeToUnixTimeStamp (IDE 798)](REF-IDE-798.md)

---

#### <a id="t2"></a>634.1 - Lecture paramètres API

**Role** : Traitement : Lecture paramètres API.
**Delegue a** : [DateTimeToUnixTimeStamp (IDE 798)](REF-IDE-798.md)

---

#### <a id="t3"></a>634.2 - Write curl

**Role** : Traitement : Write curl.
**Variables liees** : F (P.i.répertoire fichiers curl), P (v.commande CURL), Q (v.nom fichier curl bat), R (v.nom fichier curl reponse)
**Delegue a** : [DateTimeToUnixTimeStamp (IDE 798)](REF-IDE-798.md)

---

#### <a id="t4"></a>634.3 - XML refresh/access token

**Role** : Traitement : XML refresh/access token.
**Variables liees** : C (P.i.Bearer token)
**Delegue a** : [DateTimeToUnixTimeStamp (IDE 798)](REF-IDE-798.md)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Pilotage API CM Stay (IDE 639)](REF-IDE-639.md), [Club Med API demo (IDE 635)](REF-IDE-635.md), [Pilotage API CM Paiements (IDE 637)](REF-IDE-637.md)
- **Appelle**: 1 programmes | **Tables**: 2 (W:1 R:0 L:1) | **Taches**: 4 | **Expressions**: 28

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (4 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **634.1** | [**ClubMedAPICall** (634)](#t1) | - | - | Traitement |
| 634.1.1 | [Lecture paramètres API (634.1)](#t2) | - | - | |
| 634.1.2 | [Write curl (634.2)](#t3) | - | - | |
| 634.1.3 | [XML refresh/access token (634.3)](#t4) | - | - | |

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

### 11.1 Parametres entrants (12)

Variables recues du programme appelant ([Pilotage API CM Stay (IDE 639)](REF-IDE-639.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P.i.UrlApi | Alpha | 1x parametre entrant |
| B | P.i.JsonIN | Blob | 2x parametre entrant |
| C | P.i.Bearer token | Unicode | [634.3](#t4) |
| D | P.i.Api Key param | Unicode | [634.1](#t2) |
| E | P.i.Proxy adress http | Unicode | 1x parametre entrant |
| F | P.i.répertoire fichiers curl | Unicode | - |
| G | P.i.répertoire fichiers réponse | Unicode | - |
| H | P.i.méthode | Unicode | 1x parametre entrant |
| I | P.i.Avec Timestamp | Logical | - |
| J | P.o.IsSuccess | Logical | 1x parametre entrant |
| K | P.o.ErrorMessage | Alpha | 5x parametre entrant |
| L | P.o.JsonResponse | Blob | 4x parametre entrant |

### 11.2 Variables de session (12)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| M | v.Api Key param | Unicode | - |
| N | v.Authentification | Unicode | 3x session |
| O | v.Url complétée | Unicode | - |
| P | v.commande CURL | Alpha | [634.2](#t3) |
| Q | v.nom fichier curl bat | Alpha | [634.2](#t3) |
| R | v.nom fichier curl reponse | Alpha | - |
| S | v.XMLResponse | Blob | - |
| T | v.status | Alpha | 1x session |
| U | v.error code | Alpha | 1x session |
| V | v.date | Date | 1x session |
| W | v.time | Time | 2x session |
| X | v.timestamp alpha | Unicode | 1x session |

<details>
<summary>Toutes les 24 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| P0 | **A** | P.i.UrlApi | Alpha |
| P0 | **B** | P.i.JsonIN | Blob |
| P0 | **C** | P.i.Bearer token | Unicode |
| P0 | **D** | P.i.Api Key param | Unicode |
| P0 | **E** | P.i.Proxy adress http | Unicode |
| P0 | **F** | P.i.répertoire fichiers curl | Unicode |
| P0 | **G** | P.i.répertoire fichiers réponse | Unicode |
| P0 | **H** | P.i.méthode | Unicode |
| P0 | **I** | P.i.Avec Timestamp | Logical |
| P0 | **J** | P.o.IsSuccess | Logical |
| P0 | **K** | P.o.ErrorMessage | Alpha |
| P0 | **L** | P.o.JsonResponse | Blob |
| V. | **M** | v.Api Key param | Unicode |
| V. | **N** | v.Authentification | Unicode |
| V. | **O** | v.Url complétée | Unicode |
| V. | **P** | v.commande CURL | Alpha |
| V. | **Q** | v.nom fichier curl bat | Alpha |
| V. | **R** | v.nom fichier curl reponse | Alpha |
| V. | **S** | v.XMLResponse | Blob |
| V. | **T** | v.status | Alpha |
| V. | **U** | v.error code | Alpha |
| V. | **V** | v.date | Date |
| V. | **W** | v.time | Time |
| V. | **X** | v.timestamp alpha | Unicode |

</details>

## 12. EXPRESSIONS

**28 / 28 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONCATENATION | 5 | 0 |
| FORMAT | 6 | 0 |
| CONSTANTE | 2 | 0 |
| DATE | 1 | 0 |
| OTHER | 9 | 0 |
| CONDITION | 3 | 0 |
| CAST_LOGIQUE | 1 | 0 |
| STRING | 1 | 0 |

### 12.2 Expressions cles par type

#### CONCATENATION (5 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 8 | `RTrim(v.Authentification [N])&IF(Trim(P.o.JsonResponse [L])<>'','&','?')&'timestamp='&Trim([Y])` | - |
| CONCATENATION | 28 | `Trim(P.i.répertoire fichier... [G])&'testcurl.bat'` | - |
| CONCATENATION | 7 | `RTrim(v.Authentification [N]) & '?api_key=' & P.o.JsonResponse [L]` | - |
| CONCATENATION | 13 | `Translate('%club_exe%')&'curl\bin\curl '&IF(Trim(P.i.Proxy adress http [E])<>'','-x '&Trim(P.i.Proxy adress http [E]),'')&' -X '&Trim(v.error code [U])&' "'&Trim(v.Authentification [N])&'"'&' -H "accept: application/json"'&' -H  "authorization: Bearer '&Trim(P.i.Bearer token [C])&'"'&' -H "Content-Type: application/json; charset=utf-8"'&' -H  "accept-language: fr-FR"'&IF(ISNULL(P.i.JsonIN [B]) OR Trim(P.i.JsonIN [B])='','',' -d "'&Trim(P.i.JsonIN [B])&'"')& ' >'&Trim(v.nom fichier curl bat [Q])` | - |
| CONCATENATION | 26 | `'<?xml version="1.0" encoding="UTF-8"?>' &ASCIIChr(13)& ASCIIChr(10)&DotNet.System.Xml.Linq.XElement.Load(  DotNet.System.Runtime.Serialization.Json.JsonReaderWriterFactory.CreateJsonReader(      P.o.ErrorMessage [K],     DotNet.System.Xml.XmlDictionaryReaderQuotas()   )).ToString()` | - |

#### FORMAT (6 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| FORMAT | 23 | `Trim(RepStr(Trim(Left(P.o.IsSuccess [J],InStr(P.o.IsSuccess [J],',')-1)),'"',' '))&' ('&v.status [T]&')'` | - |
| FORMAT | 12 | `Trim(P.i.méthode [H])&DStr(v.date [V],'YYYYMMDD')&'_'&TStr(v.time [W],'HHMMSS')&'.txt'` | - |
| FORMAT | 20 | `InStr(P.o.ErrorMessage [K],'"error"')=0` | - |
| FORMAT | 14 | `'c:\temp\log_ApiCall-'&Trim(Str(Counter(1),'3'))&'.pdf'` | - |
| FORMAT | 21 | `Del(P.o.ErrorMessage [K],1,InStr(P.o.ErrorMessage [K],'"status_code":')+13)` | - |
| ... | | *+1 autres* | |

#### CONSTANTE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 25 | `''` | - |
| CONSTANTE | 16 | `'Content-Type: application/json; charset=utf-8'` | - |

#### DATE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| DATE | 1 | `Date()` | - |

#### OTHER (9 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 15 | `Left(P.i.JsonIN [B],2000)` | - |
| OTHER | 11 | `P.i.Api Key param [D]` | - |
| OTHER | 19 | `File2Blb(v.nom fichier curl bat [Q])` | - |
| OTHER | 17 | `Left(P.o.ErrorMessage [K],2000)` | - |
| OTHER | 6 | `P.i.UrlApi [A]` | - |
| ... | | *+4 autres* | |

#### CONDITION (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 27 | `Translate('%club_test%')='T'` | - |
| CONDITION | 10 | `P.o.JsonResponse [L]=''` | - |
| CONDITION | 9 | `P.o.JsonResponse [L]<>''` | - |

#### CAST_LOGIQUE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 24 | `'FALSE'LOG` | - |

#### STRING (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| STRING | 18 | `Trim(v.commande CURL [P])` | - |

### 12.3 Toutes les expressions (28)

<details>
<summary>Voir les 28 expressions</summary>

#### CONCATENATION (5)

| IDE | Expression Decodee |
|-----|-------------------|
| 13 | `Translate('%club_exe%')&'curl\bin\curl '&IF(Trim(P.i.Proxy adress http [E])<>'','-x '&Trim(P.i.Proxy adress http [E]),'')&' -X '&Trim(v.error code [U])&' "'&Trim(v.Authentification [N])&'"'&' -H "accept: application/json"'&' -H  "authorization: Bearer '&Trim(P.i.Bearer token [C])&'"'&' -H "Content-Type: application/json; charset=utf-8"'&' -H  "accept-language: fr-FR"'&IF(ISNULL(P.i.JsonIN [B]) OR Trim(P.i.JsonIN [B])='','',' -d "'&Trim(P.i.JsonIN [B])&'"')& ' >'&Trim(v.nom fichier curl bat [Q])` |
| 26 | `'<?xml version="1.0" encoding="UTF-8"?>' &ASCIIChr(13)& ASCIIChr(10)&DotNet.System.Xml.Linq.XElement.Load(  DotNet.System.Runtime.Serialization.Json.JsonReaderWriterFactory.CreateJsonReader(      P.o.ErrorMessage [K],     DotNet.System.Xml.XmlDictionaryReaderQuotas()   )).ToString()` |
| 7 | `RTrim(v.Authentification [N]) & '?api_key=' & P.o.JsonResponse [L]` |
| 8 | `RTrim(v.Authentification [N])&IF(Trim(P.o.JsonResponse [L])<>'','&','?')&'timestamp='&Trim([Y])` |
| 28 | `Trim(P.i.répertoire fichier... [G])&'testcurl.bat'` |

#### FORMAT (6)

| IDE | Expression Decodee |
|-----|-------------------|
| 14 | `'c:\temp\log_ApiCall-'&Trim(Str(Counter(1),'3'))&'.pdf'` |
| 21 | `Del(P.o.ErrorMessage [K],1,InStr(P.o.ErrorMessage [K],'"status_code":')+13)` |
| 22 | `RepStr(Del(P.o.ErrorMessage [K],1,InStr(P.o.ErrorMessage [K],'"error"')+7),'_',' ')` |
| 23 | `Trim(RepStr(Trim(Left(P.o.IsSuccess [J],InStr(P.o.IsSuccess [J],',')-1)),'"',' '))&' ('&v.status [T]&')'` |
| 12 | `Trim(P.i.méthode [H])&DStr(v.date [V],'YYYYMMDD')&'_'&TStr(v.time [W],'HHMMSS')&'.txt'` |
| 20 | `InStr(P.o.ErrorMessage [K],'"error"')=0` |

#### CONSTANTE (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 16 | `'Content-Type: application/json; charset=utf-8'` |
| 25 | `''` |

#### DATE (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 1 | `Date()` |

#### OTHER (9)

| IDE | Expression Decodee |
|-----|-------------------|
| 2 | `Time()` |
| 3 | `v.timestamp alpha [X]` |
| 4 | `Counter(1)` |
| 5 | `'Authorization: Bearer ' & P.i.Bearer token [C]` |
| 6 | `P.i.UrlApi [A]` |
| 11 | `P.i.Api Key param [D]` |
| 15 | `Left(P.i.JsonIN [B],2000)` |
| 17 | `Left(P.o.ErrorMessage [K],2000)` |
| 19 | `File2Blb(v.nom fichier curl bat [Q])` |

#### CONDITION (3)

| IDE | Expression Decodee |
|-----|-------------------|
| 9 | `P.o.JsonResponse [L]<>''` |
| 10 | `P.o.JsonResponse [L]=''` |
| 27 | `Translate('%club_test%')='T'` |

#### CAST_LOGIQUE (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 24 | `'FALSE'LOG` |

#### STRING (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 18 | `Trim(v.commande CURL [P])` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Pilotage API CM Stay (IDE 639)](REF-IDE-639.md) -> **Appel Curl API (IDE 634)**

Main -> ... -> [Club Med API demo (IDE 635)](REF-IDE-635.md) -> **Appel Curl API (IDE 634)**

Main -> ... -> [Pilotage API CM Paiements (IDE 637)](REF-IDE-637.md) -> **Appel Curl API (IDE 634)**

```mermaid
graph LR
    T634[634 Appel Curl API]
    style T634 fill:#58a6ff
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
    CC635 --> T634
    CC637 --> T634
    CC639 --> T634
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [639](REF-IDE-639.md) | Pilotage API CM Stay | 6 |
| [635](REF-IDE-635.md) | Club Med API demo | 1 |
| [637](REF-IDE-637.md) | Pilotage API CM Paiements | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T634[634 Appel Curl API]
    style T634 fill:#58a6ff
    C798[798 DateTimeToUnixTime...]
    T634 --> C798
    style C798 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [798](REF-IDE-798.md) | DateTimeToUnixTimeStamp | 1 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 100 | Programme compact |
| Expressions | 28 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 1 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 100) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (4 taches: 0 ecran, 4 traitements)

- **Strategie** : 4 service(s) backend injectable(s) (Domain Services).
- 1 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| initialisation___ini | Table WRITE (Database) | 1x | Schema + repository |
| [DateTimeToUnixTimeStamp (IDE 798)](REF-IDE-798.md) | Sous-programme | 1x | Normale - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 13:18*
