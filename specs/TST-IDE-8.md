# TST IDE 8 - Club Med API token

> **Analyse**: Phases 1-4 2026-02-03 20:49 -> 20:49 (16s) | Assemblage 20:49
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | TST |
| IDE Position | 8 |
| Nom Programme | Club Med API token |
| Fichier source | `Prg_8.xml` |
| Dossier IDE | General |
| Taches | 3 (0 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 0 |
| :warning: Statut | **ORPHELIN_POTENTIEL** |

## 2. DESCRIPTION FONCTIONNELLE

**Club Med API token** assure la gestion complete de ce processus.

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (3 taches) : traitements metier divers

**Donnees modifiees** : 1 tables en ecriture (initialisation___ini).

**Logique metier** : 1 regles identifiees couvrant conditions metier.

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (3 taches)

Traitements internes.

---

#### <a id="t1"></a>8 - Club Med API token

**Role** : Traitement : Club Med API token.
**Variables liees** : A (p.o.Access Token), T (v.Access Token), U (v.Token type)

---

#### <a id="t2"></a>8.1 - XML refresh/access token

**Role** : Traitement : XML refresh/access token.
**Variables liees** : A (p.o.Access Token), T (v.Access Token), U (v.Token type)

---

#### <a id="t3"></a>8.2 - Lecture paramètres API

**Role** : Traitement : Lecture paramètres API.


## 5. REGLES METIER

1 regles identifiees:

### Autres (1 regles)

#### <a id="rm-RM-001"></a>[RM-001] Si v.JSonResponse [P] alors 'OK' sinon 'ERR')

| Element | Detail |
|---------|--------|
| **Condition** | `v.JSonResponse [P]` |
| **Si vrai** | 'OK' |
| **Si faux** | 'ERR') |
| **Variables** | P (v.JSonResponse) |
| **Expression source** | Expression 11 : `IF(v.JSonResponse [P], 'OK', 'ERR')` |
| **Exemple** | Si v.JSonResponse [P] â†’ 'OK'. Sinon â†’ 'ERR') |

## 6. CONTEXTE

- **Appele par**: (aucun)
- **Appelle**: 0 programmes | **Tables**: 2 (W:1 R:0 L:1) | **Taches**: 3 | **Expressions**: 21

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (3 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **8.1** | [**Club Med API token** (8)](#t1) | - | - | Traitement |
| 8.1.1 | [XML refresh/access token (8.1)](#t2) | - | - | |
| 8.1.2 | [Lecture paramètres API (8.2)](#t3) | - | - | |

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

### 11.1 Parametres entrants (1)

Variables recues en parametre.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | p.o.Access Token | Unicode | - |

### 11.2 Variables de session (15)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| I | v.Client_id | Unicode | 1x session |
| J | v.Client_secret | Unicode | - |
| K | v.Grant_type | Unicode | - |
| L | v.Scope | Unicode | 1x session |
| M | v.UrlApi | Unicode | - |
| N | v.Proxy adress http | Unicode | 2x session |
| O | v.bypassproxyonlocal | Logical | - |
| P | v.JSonResponse | Blob | 1x session |
| Q | v.XML response | Blob | 2x session |
| R | v.IsSuccess | Logical | 2x session |
| S | v.ErrorMessage | Alpha | 1x session |
| T | v.Access Token | Unicode | - |
| U | v.Token type | Unicode | 1x session |
| V | v.Expiration | Unicode | - |
| W | v.Id batch | Numeric | 1x session |

### 11.3 Autres (7)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| B | i.Client_id | Unicode | 1x refs |
| C | i.Client_secret | Unicode | 2x refs |
| D | i.Grant_type | Unicode | 1x refs |
| E | i.Scope | Unicode | 1x refs |
| F | i.UrlApi | Unicode | 1x refs |
| G | i.Proxy adress http | Unicode | 1x refs |
| H | i.bypassproxyonlocal | Logical | 1x refs |

<details>
<summary>Toutes les 23 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| P0 | **A** | p.o.Access Token | Unicode |
| V. | **I** | v.Client_id | Unicode |
| V. | **J** | v.Client_secret | Unicode |
| V. | **K** | v.Grant_type | Unicode |
| V. | **L** | v.Scope | Unicode |
| V. | **M** | v.UrlApi | Unicode |
| V. | **N** | v.Proxy adress http | Unicode |
| V. | **O** | v.bypassproxyonlocal | Logical |
| V. | **P** | v.JSonResponse | Blob |
| V. | **Q** | v.XML response | Blob |
| V. | **R** | v.IsSuccess | Logical |
| V. | **S** | v.ErrorMessage | Alpha |
| V. | **T** | v.Access Token | Unicode |
| V. | **U** | v.Token type | Unicode |
| V. | **V** | v.Expiration | Unicode |
| V. | **W** | v.Id batch | Numeric |
| Autre | **B** | i.Client_id | Unicode |
| Autre | **C** | i.Client_secret | Unicode |
| Autre | **D** | i.Grant_type | Unicode |
| Autre | **E** | i.Scope | Unicode |
| Autre | **F** | i.UrlApi | Unicode |
| Autre | **G** | i.Proxy adress http | Unicode |
| Autre | **H** | i.bypassproxyonlocal | Logical |

</details>

## 12. EXPRESSIONS

**21 / 21 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONCATENATION | 1 | 0 |
| CONDITION | 3 | 5 |
| CONSTANTE | 4 | 0 |
| OTHER | 13 | 0 |

### 12.2 Expressions cles par type

#### CONCATENATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 1 | `'<?xml version="1.0" encoding="UTF-8"?>' &
ASCIIChr(13)& ASCIIChr(10)&
DotNet.System.Xml.Linq.XElement.Load(
  DotNet.System.Runtime.Serialization.Json.JsonReaderWriterFactory.CreateJsonReader( 
     v.Proxy adress http [N],
     DotNet.System.Xml.XmlDictionaryReaderQuotas()
   )
).ToString()` | - |

#### CONDITION (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 11 | `IF(v.JSonResponse [P], 'OK', 'ERR')` | [RM-001](#rm-RM-001) |
| CONDITION | 14 | `i.Client_secret [C]=''` | - |
| CONDITION | 2 | `v.ErrorMessage [S]='Bearer' AND v.IsSuccess [R]<>''` | - |

#### CONSTANTE (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 7 | `'DEB'` | - |
| CONSTANTE | 10 | `'json'` | - |
| CONSTANTE | 4 | `'ClubMedAPI'` | - |
| CONSTANTE | 5 | `'Token'` | - |

#### OTHER (13 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 18 | `i.Scope [E]` | - |
| OTHER | 17 | `i.Grant_type [D]` | - |
| OTHER | 16 | `i.Client_secret [C]` | - |
| OTHER | 21 | `v.Id batch [W]` | - |
| OTHER | 20 | `i.Proxy adress http [G]` | - |
| ... | | *+8 autres* | |

### 12.3 Toutes les expressions (21)

<details>
<summary>Voir les 21 expressions</summary>

#### CONCATENATION (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 1 | `'<?xml version="1.0" encoding="UTF-8"?>' &
ASCIIChr(13)& ASCIIChr(10)&
DotNet.System.Xml.Linq.XElement.Load(
  DotNet.System.Runtime.Serialization.Json.JsonReaderWriterFactory.CreateJsonReader( 
     v.Proxy adress http [N],
     DotNet.System.Xml.XmlDictionaryReaderQuotas()
   )
).ToString()` |

#### CONDITION (3)

| IDE | Expression Decodee |
|-----|-------------------|
| 11 | `IF(v.JSonResponse [P], 'OK', 'ERR')` |
| 2 | `v.ErrorMessage [S]='Bearer' AND v.IsSuccess [R]<>''` |
| 14 | `i.Client_secret [C]=''` |

#### CONSTANTE (4)

| IDE | Expression Decodee |
|-----|-------------------|
| 4 | `'ClubMedAPI'` |
| 5 | `'Token'` |
| 7 | `'DEB'` |
| 10 | `'json'` |

#### OTHER (13)

| IDE | Expression Decodee |
|-----|-------------------|
| 3 | `StrBuild('Json error @1@ ; Client Id @2@, Client Secret @3@', v.XML response [Q], i.bypassproxyonlocal [H], v.Client_id [I])` |
| 6 | `v.Scope [L]` |
| 8 | `v.Token type [U]` |
| 9 | `v.Proxy adress http [N]` |
| 12 | `v.XML response [Q]` |
| 13 | `v.IsSuccess [R]` |
| 15 | `i.Client_id [B]` |
| 16 | `i.Client_secret [C]` |
| 17 | `i.Grant_type [D]` |
| 18 | `i.Scope [E]` |
| 19 | `i.UrlApi [F]` |
| 20 | `i.Proxy adress http [G]` |
| 21 | `v.Id batch [W]` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

**Chemin**: (pas de callers directs)

```mermaid
graph LR
    T8[8 Club Med API token]
    style T8 fill:#58a6ff
    NONE[Aucun caller]
    NONE -.-> T8
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| - | (aucun) | - |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T8[8 Club Med API token]
    style T8 fill:#58a6ff
    NONE[Aucun callee]
    T8 -.-> NONE
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| - | (aucun) | - | - |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 83 | Programme compact |
| Expressions | 21 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 83) | Code sain |
| Regles metier | 1 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (3 taches: 0 ecran, 3 traitements)

- **Strategie** : 3 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| initialisation___ini | Table WRITE (Database) | 1x | Schema + repository |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 20:49*
