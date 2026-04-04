# PVE IDE 148 - Parameters Initialization

> **Analyse**: Phases 1-4 2026-02-03 09:44 -> 09:44 (17s) | Assemblage 09:44
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PVE |
| IDE Position | 148 |
| Nom Programme | Parameters Initialization |
| Fichier source | `Prg_148.xml` |
| Domaine metier | General |
| Taches | 5 (0 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 1 |

## 2. DESCRIPTION FONCTIONNELLE

**Parameters Initialization** assure la gestion complete de ce processus, accessible depuis [General settings (IDE 12)](PVE-IDE-12.md), [Initialization (IDE 145)](PVE-IDE-145.md), [Choix - Services (IDE 332)](PVE-IDE-332.md), [General settings (IDE 408)](PVE-IDE-408.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (5 taches) : traitements metier divers

**Donnees modifiees** : 1 tables en ecriture (arc_tai_gm).

**Logique metier** : 4 regles identifiees couvrant conditions metier.

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (5 taches)

- **148** - Browse - Parametre generaux **[[ECRAN]](#ecran-t1)**
- **148.1** - Get Max Price
- **148.2** - Terminal boutique ?
- **148.3** - Terminal boutique ?
- **148.4** - (sans nom)

Delegue a : [Existence Rental (IDE 292)](PVE-IDE-292.md)

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| arc_tai_gm | **W** (1 usages) |  |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (5 taches)

Traitements internes.

---

#### <a id="t1"></a>148 - Browse - Parametre generaux [[ECRAN]](#ecran-t1)

**Role** : Traitement : Browse - Parametre generaux.
**Ecran** : 187 x 45 DLU (MDI) | [Voir mockup](#ecran-t1)

<details>
<summary>4 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [148.1](#t3) | Get Max Price | Traitement |
| [148.2](#t4) | Terminal boutique ? | Traitement |
| [148.3](#t5) | Terminal boutique ? | Traitement |
| [148.4](#t6) | (sans nom) | Traitement |

</details>
**Delegue a** : [Existence Rental (IDE 292)](PVE-IDE-292.md)

---

#### <a id="t3"></a>148.1 - Get Max Price

**Role** : Consultation/chargement : Get Max Price.
**Delegue a** : [Existence Rental (IDE 292)](PVE-IDE-292.md)

---

#### <a id="t4"></a>148.2 - Terminal boutique ?

**Role** : Traitement : Terminal boutique ?.
**Variables liees** : B (L Boutique)
**Delegue a** : [Existence Rental (IDE 292)](PVE-IDE-292.md)

---

#### <a id="t5"></a>148.3 - Terminal boutique ?

**Role** : Traitement : Terminal boutique ?.
**Variables liees** : B (L Boutique)
**Delegue a** : [Existence Rental (IDE 292)](PVE-IDE-292.md)

---

#### <a id="t6"></a>148.4 - (sans nom)

**Role** : Traitement interne.
**Delegue a** : [Existence Rental (IDE 292)](PVE-IDE-292.md)


## 5. REGLES METIER

4 regles identifiees:

### Autres (4 regles)

#### <a id="rm-RM-001"></a>[RM-001] Condition toujours vraie (flag actif)

| Element | Detail |
|---------|--------|
| **Condition** | `[AH]<>[AT] AND [AI]<>[AT] AND [AJ]<>[AT] AND [AK]<>[AT] AND [AL]<>[AT] AND NOT ([AM])` |
| **Si vrai** | 'TRUE'LOG |
| **Si faux** | 'FALSE'LOG) |
| **Expression source** | Expression 4 : `IF ([AH]<>[AT] AND [AI]<>[AT] AND [AJ]<>[AT] AND [AK]<>[AT] ` |
| **Exemple** | Si [AH]<>[AT] AND [AI]<>[AT] AND [AJ]<>[AT] AND [AK]<>[AT] AND [AL]<>[AT] AND NOT ([AM]) â†’ 'TRUE'LOG. Sinon â†’ 'FALSE'LOG) |

#### <a id="rm-RM-002"></a>[RM-002] Si VG63 alors [AF] sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `VG63` |
| **Si vrai** | [AF] |
| **Si faux** | '') |
| **Expression source** | Expression 50 : `IF(VG63, [AF], '')` |
| **Exemple** | Si VG63 â†’ [AF]. Sinon â†’ '') |

#### <a id="rm-RM-003"></a>[RM-003] Condition toujours fausse (flag inactif)

| Element | Detail |
|---------|--------|
| **Condition** | `VG118` |
| **Si vrai** | [P] |
| **Si faux** | 'FALSE'LOG) AND NOT(VG10) |
| **Expression source** | Expression 51 : `IF(VG118,[P],'FALSE'LOG) AND NOT(VG10)` |
| **Exemple** | Si VG118 â†’ [P]. Sinon â†’ 'FALSE'LOG) AND NOT(VG10) |

#### <a id="rm-RM-004"></a>[RM-004] Condition toujours fausse (flag inactif)

| Element | Detail |
|---------|--------|
| **Condition** | `VG125` |
| **Si vrai** | [Q] |
| **Si faux** | 'FALSE'LOG) AND NOT(VG10) |
| **Expression source** | Expression 52 : `IF(VG125,[Q],'FALSE'LOG) AND NOT(VG10)` |
| **Exemple** | Si VG125 â†’ [Q]. Sinon â†’ 'FALSE'LOG) AND NOT(VG10) |

## 6. CONTEXTE

- **Appele par**: [General settings (IDE 12)](PVE-IDE-12.md), [Initialization (IDE 145)](PVE-IDE-145.md), [Choix - Services (IDE 332)](PVE-IDE-332.md), [General settings (IDE 408)](PVE-IDE-408.md)
- **Appelle**: 1 programmes | **Tables**: 6 (W:1 R:1 L:4) | **Taches**: 5 | **Expressions**: 55

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (5 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **148.1** | [**Browse - Parametre generaux** (148)](#t1) [mockup](#ecran-t1) | MDI | 187x45 | Traitement |
| 148.1.1 | [Get Max Price (148.1)](#t3) | - | - | |
| 148.1.2 | [Terminal boutique ? (148.2)](#t4) | - | - | |
| 148.1.3 | [Terminal boutique ? (148.3)](#t5) | - | - | |
| 148.1.4 | [(sans nom) (148.4)](#t6) | - | - | |

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

### Tables utilisees (6)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 67 | tables___________tab |  | DB |   |   | L | 1 |
| 256 | terminaux_boutique |  | DB | R |   |   | 2 |
| 379 | pv_customer_temp |  | DB |   |   | L | 1 |
| 413 | pv_tva |  | DB |   |   | L | 1 |
| 697 | droits_applications | Droits operateur | DB |   |   | L | 1 |
| 731 | arc_tai_gm |  | DB |   | **W** |   | 1 |

### Colonnes par table (2 / 2 tables avec colonnes identifiees)

<details>
<summary>Table 256 - terminaux_boutique (R) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| B | L Boutique | R | Logical |

</details>

<details>
<summary>Table 731 - arc_tai_gm (**W**) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P. Service (new) | W | Alpha |
| B | L Boutique | W | Logical |
| C | V Service | W | Alpha |
| D | L Input Sale and Products | W | Logical |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (1)

Variables recues du programme appelant ([General settings (IDE 12)](PVE-IDE-12.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P. Service (new) | Alpha | 3x parametre entrant |

### 11.2 Variables de session (1)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| C | V Service | Alpha | - |

### 11.3 Autres (2)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| B | L Boutique | Logical | [148.2](#t4), [148.3](#t5) |
| D | L Input Sale and Products | Logical | 1x refs |

## 12. EXPRESSIONS

**55 / 55 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONCATENATION | 1 | 0 |
| FORMAT | 2 | 0 |
| CAST_LOGIQUE | 5 | 3 |
| CONDITION | 3 | 5 |
| CONSTANTE | 3 | 0 |
| OTHER | 36 | 0 |
| REFERENCE_VG | 2 | 0 |
| NEGATION | 1 | 0 |
| STRING | 2 | 0 |

### 12.2 Expressions cles par type

#### CONCATENATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 39 | `SetParam ('LIBELBESTOF',Trim([AX])&' - '&Trim([BB]))` | - |

#### FORMAT (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| FORMAT | 48 | `DNSet(DNCast(DotNet.System.Windows.Forms.Control.FromHandle(DNCast(VG106,DotNet.System.IntPtr)),DotNet.System.Windows.Forms.Form).Text,RTrim(VG107) & ' Terminal : ' & Trim(Str(VG105, '3')) & IF(VG24 AND VG25<>'', ' - TPE : '& VG25 , '')  )` | - |
| FORMAT | 47 | `DNSet(DNCast(DotNet.System.Windows.Forms.Control.FromHandle(DNCast(VG106,DotNet.System.IntPtr)),DotNet.System.Windows.Forms.Form).Text,RTrim(VG107) & ' Computer : ' & GetHostName()& '/' & Trim(Str(VG105, '3')) & IF(VG24 AND VG25<>'', ' - TPE : '& VG25, '') )` | - |

#### CAST_LOGIQUE (5 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 52 | `IF(VG125,[Q],'FALSE'LOG) AND NOT(VG10)` | [RM-004](#rm-RM-004) |
| CAST_LOGIQUE | 51 | `IF(VG118,[P],'FALSE'LOG) AND NOT(VG10)` | [RM-003](#rm-RM-003) |
| CAST_LOGIQUE | 4 | `IF ([AH]<>[AT] AND [AI]<>[AT] AND [AJ]<>[AT] AND [AK]<>[AT] AND [AL]<>[AT] AND NOT ([AM]),'TRUE'LOG,'FALSE'LOG)` | [RM-001](#rm-RM-001) |
| CAST_LOGIQUE | 54 | `'TRUE'LOG` | - |
| CAST_LOGIQUE | 27 | `SetParam ('INPUTPRODUCTS','TRUE'LOG)` | - |

#### CONDITION (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 50 | `IF(VG63, [AF], '')` | [RM-002](#rm-RM-002) |
| CONDITION | 53 | `NOT(Trim(VG130)='')` | - |
| CONDITION | 6 | `[H]=0` | - |

#### CONSTANTE (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 5 | `7` | - |
| CONSTANTE | 3 | `'O'` | - |
| CONSTANTE | 2 | `'VSERV'` | - |

#### OTHER (36 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 31 | `SetParam ('EDITMESSAGE',[J])` | - |
| OTHER | 30 | `SetParam ('SERVICELIB',[AQ])` | - |
| OTHER | 33 | `[L]` | - |
| OTHER | 32 | `[K]` | - |
| OTHER | 29 | `SetParam ('SERVICE',P. Service (new) [A])` | - |
| ... | | *+31 autres* | |

#### REFERENCE_VG (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 46 | `VG104` | - |
| REFERENCE_VG | 36 | `VG86` | - |

#### NEGATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| NEGATION | 45 | `NOT VG104` | - |

#### STRING (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| STRING | 38 | `Val(Right([AC],2),'2P0')` | - |
| STRING | 37 | `Val(Left([AC],2),'2P0')` | - |

### 12.3 Toutes les expressions (55)

<details>
<summary>Voir les 55 expressions</summary>

#### CONCATENATION (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 39 | `SetParam ('LIBELBESTOF',Trim([AX])&' - '&Trim([BB]))` |

#### FORMAT (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 47 | `DNSet(DNCast(DotNet.System.Windows.Forms.Control.FromHandle(DNCast(VG106,DotNet.System.IntPtr)),DotNet.System.Windows.Forms.Form).Text,RTrim(VG107) & ' Computer : ' & GetHostName()& '/' & Trim(Str(VG105, '3')) & IF(VG24 AND VG25<>'', ' - TPE : '& VG25, '') )` |
| 48 | `DNSet(DNCast(DotNet.System.Windows.Forms.Control.FromHandle(DNCast(VG106,DotNet.System.IntPtr)),DotNet.System.Windows.Forms.Form).Text,RTrim(VG107) & ' Terminal : ' & Trim(Str(VG105, '3')) & IF(VG24 AND VG25<>'', ' - TPE : '& VG25 , '')  )` |

#### CAST_LOGIQUE (5)

| IDE | Expression Decodee |
|-----|-------------------|
| 4 | `IF ([AH]<>[AT] AND [AI]<>[AT] AND [AJ]<>[AT] AND [AK]<>[AT] AND [AL]<>[AT] AND NOT ([AM]),'TRUE'LOG,'FALSE'LOG)` |
| 51 | `IF(VG118,[P],'FALSE'LOG) AND NOT(VG10)` |
| 52 | `IF(VG125,[Q],'FALSE'LOG) AND NOT(VG10)` |
| 27 | `SetParam ('INPUTPRODUCTS','TRUE'LOG)` |
| 54 | `'TRUE'LOG` |

#### CONDITION (3)

| IDE | Expression Decodee |
|-----|-------------------|
| 50 | `IF(VG63, [AF], '')` |
| 6 | `[H]=0` |
| 53 | `NOT(Trim(VG130)='')` |

#### CONSTANTE (3)

| IDE | Expression Decodee |
|-----|-------------------|
| 2 | `'VSERV'` |
| 3 | `'O'` |
| 5 | `7` |

#### OTHER (36)

| IDE | Expression Decodee |
|-----|-------------------|
| 1 | `P. Service (new) [A]` |
| 7 | `[M]` |
| 8 | `[R]` |
| 9 | `[T]` |
| 10 | `[S]` |
| 11 | `[U]` |
| 12 | `[V]` |
| 13 | `[W]` |
| 14 | `[X]` |
| 15 | `[Y]` |
| 16 | `[Z]` |
| 17 | `[AA]` |
| 18 | `[AB]` |
| 19 | `[AD]` |
| 20 | `SetParam ('AUTODAYS',L Input Sale and Products [D])` |
| 21 | `SetParam ('ZONEGEO',[E])` |
| 22 | `SetParam ('OKNOGUARANTY',[F])` |
| 23 | `SetParam ('SKISERVICECODE',L Boutique [B])` |
| 24 | `SetParam ('INSCATEG',[G])` |
| 25 | `SetParam ('SALESCANCEL',[H])` |
| 26 | `SetParam ('INPUTSALES',[AU])` |
| 28 | `SetParam ('LOGO',[I])` |
| 29 | `SetParam ('SERVICE',P. Service (new) [A])` |
| 30 | `SetParam ('SERVICELIB',[AQ])` |
| 31 | `SetParam ('EDITMESSAGE',[J])` |
| 32 | `[K]` |
| 33 | `[L]` |
| 34 | `[N]` |
| 35 | `[O]` |
| 40 | `[AC]` |
| 41 | `P. Service (new) [A]` |
| 42 | `[AQ]` |
| 43 | `[AS]` |
| 44 | `[AR]` |
| 49 | `GetPseudoTerminal ()` |
| 55 | `[BC]` |

#### REFERENCE_VG (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 36 | `VG86` |
| 46 | `VG104` |

#### NEGATION (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 45 | `NOT VG104` |

#### STRING (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 37 | `Val(Left([AC],2),'2P0')` |
| 38 | `Val(Right([AC],2),'2P0')` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [General settings (IDE 12)](PVE-IDE-12.md) -> **Parameters Initialization (IDE 148)**

Main -> ... -> [Initialization (IDE 145)](PVE-IDE-145.md) -> **Parameters Initialization (IDE 148)**

Main -> ... -> [Choix - Services (IDE 332)](PVE-IDE-332.md) -> **Parameters Initialization (IDE 148)**

Main -> ... -> [General settings (IDE 408)](PVE-IDE-408.md) -> **Parameters Initialization (IDE 148)**

```mermaid
graph LR
    T148[148 Parameters Initial...]
    style T148 fill:#58a6ff
    CC5[5 Test Upgrade]
    style CC5 fill:#8b5cf6
    CC353[353 Menu==V4]
    style CC353 fill:#8b5cf6
    CC143[143 START]
    style CC143 fill:#8b5cf6
    CC294[294 Get Service]
    style CC294 fill:#8b5cf6
    CC185[185 Menu]
    style CC185 fill:#8b5cf6
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC178[178 Menu Administration]
    style CC178 fill:#8b5cf6
    CC12[12 General settings]
    style CC12 fill:#3fb950
    CC145[145 Initialization]
    style CC145 fill:#3fb950
    CC408[408 General settings]
    style CC408 fill:#3fb950
    CC332[332 Choix - Services]
    style CC332 fill:#3fb950
    CC178 --> CC12
    CC1 --> CC12
    CC5 --> CC12
    CC143 --> CC12
    CC185 --> CC12
    CC294 --> CC12
    CC353 --> CC12
    CC178 --> CC145
    CC1 --> CC145
    CC5 --> CC145
    CC143 --> CC145
    CC185 --> CC145
    CC294 --> CC145
    CC353 --> CC145
    CC178 --> CC332
    CC1 --> CC332
    CC5 --> CC332
    CC143 --> CC332
    CC185 --> CC332
    CC294 --> CC332
    CC353 --> CC332
    CC178 --> CC408
    CC1 --> CC408
    CC5 --> CC408
    CC143 --> CC408
    CC185 --> CC408
    CC294 --> CC408
    CC353 --> CC408
    CC12 --> T148
    CC145 --> T148
    CC332 --> T148
    CC408 --> T148
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [12](PVE-IDE-12.md) | General settings | 1 |
| [145](PVE-IDE-145.md) | Initialization | 1 |
| [332](PVE-IDE-332.md) | Choix - Services | 1 |
| [408](PVE-IDE-408.md) | General settings | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T148[148 Parameters Initial...]
    style T148 fill:#58a6ff
    C292[292 Existence Rental]
    T148 --> C292
    style C292 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [292](PVE-IDE-292.md) | Existence Rental | 1 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 163 | Programme compact |
| Expressions | 55 | Logique moderee |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 1 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 163) | Code sain |
| Regles metier | 4 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (5 taches: 1 ecran, 4 traitements)

- **Strategie** : Orchestrateur avec 1 ecrans (Razor/React) et 4 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 1 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| arc_tai_gm | Table WRITE (Database) | 1x | Schema + repository |
| [Existence Rental (IDE 292)](PVE-IDE-292.md) | Sous-programme | 1x | Normale - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 09:44*
