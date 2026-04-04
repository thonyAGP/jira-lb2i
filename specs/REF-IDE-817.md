# REF IDE 817 - Converti csv en xlsx / Exe

> **Analyse**: Phases 1-4 2026-02-03 14:32 -> 14:32 (14s) | Assemblage 14:32
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | REF |
| IDE Position | 817 |
| Nom Programme | Converti csv en xlsx / Exe |
| Fichier source | `Prg_817.xml` |
| Dossier IDE | General |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 1 |

## 2. DESCRIPTION FONCTIONNELLE

**Converti csv en xlsx / Exe** assure la gestion complete de ce processus, accessible depuis [Extraction biking (IDE 616)](REF-IDE-616.md), [Converti csv en xlsx (IDE 816)](REF-IDE-816.md), [Affiche csv/xlsx Office Web (IDE 819)](REF-IDE-819.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

**Logique metier** : 2 regles identifiees couvrant valeurs par defaut.

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>817 - Converti csv en xlsx / Exe [[ECRAN]](#ecran-t1)

**Role** : Traitement : Converti csv en xlsx / Exe.
**Ecran** : 585 x 222 DLU | [Voir mockup](#ecran-t1)
**Variables liees** : B (p.o.Fichier xlsx), F (v.Commande convertir)
**Delegue a** : [Log batch (IDE 829)](REF-IDE-829.md)


## 5. REGLES METIER

2 regles identifiees:

### Autres (2 regles)

#### <a id="rm-RM-001"></a>[RM-001] Valeur par defaut si p.o.Statut (blanc pour... [D] est vide

| Element | Detail |
|---------|--------|
| **Condition** | `p.o.Statut (blanc pour... [D]=''` |
| **Si vrai** | 'OK' |
| **Si faux** | 'ERR') |
| **Expression source** | Expression 16 : `IF(p.o.Statut (blanc pour... [D]='', 'OK', 'ERR')` |
| **Exemple** | Si p.o.Statut (blanc pour... [D]='' â†’ 'OK'. Sinon â†’ 'ERR') |

#### <a id="rm-RM-002"></a>[RM-002] Valeur par defaut si p.i.Séparateur [C] est vide

| Element | Detail |
|---------|--------|
| **Condition** | `p.i.Séparateur [C]=''` |
| **Si vrai** | IF(Translate('%club_excel_separator%')='' |
| **Si faux** | ';', Translate('%club_excel_separator%')), p.i.Séparateur [C]) |
| **Variables** | C (p.i.Séparateur) |
| **Expression source** | Expression 23 : `IF(p.i.Séparateur [C]='', IF(Translate('%club_excel_separato` |
| **Exemple** | Si p.i.Séparateur [C]='' â†’ IF(Translate('%club_excel_separator%')='' |

## 6. CONTEXTE

- **Appele par**: [Extraction biking (IDE 616)](REF-IDE-616.md), [Converti csv en xlsx (IDE 816)](REF-IDE-816.md), [Affiche csv/xlsx Office Web (IDE 819)](REF-IDE-819.md)
- **Appelle**: 1 programmes | **Tables**: 0 (W:0 R:0 L:0) | **Taches**: 1 | **Expressions**: 24

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **817.1** | [**Converti csv en xlsx / Exe** (817)](#t1) [mockup](#ecran-t1) | - | 585x222 | Traitement |

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

### 11.1 Parametres entrants (4)

Variables recues du programme appelant ([Extraction biking (IDE 616)](REF-IDE-616.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | p.i.Fichier csv | Unicode | 7x parametre entrant |
| B | p.o.Fichier xlsx | Unicode | [817](#t1) |
| C | p.i.Séparateur | Unicode | 1x parametre entrant |
| D | p.o.Statut (blanc pour OK) | Unicode | - |

### 11.2 Variables de session (4)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| E | v.Séparateur | Unicode | 1x session |
| F | v.Commande convertir | Alpha | 2x session |
| G | v.Retour cmd | Numeric | 2x session |
| H | v.Fichier retour | Unicode | 3x session |

## 12. EXPRESSIONS

**24 / 24 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCULATION | 1 | 0 |
| CONDITION | 4 | 2 |
| CONSTANTE | 4 | 0 |
| NEGATION | 2 | 0 |
| OTHER | 10 | 0 |
| FORMAT | 3 | 0 |

### 12.2 Expressions cles par type

#### CALCULATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 4 | `'cmd /c ' &v.Commande convertir [F]` | - |

#### CONDITION (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 23 | `IF(p.i.Séparateur [C]='', IF(Translate('%club_excel_separator%')='', ';', Translate('%club_excel_separator%')), p.i.Séparateur [C])` | [RM-002](#rm-RM-002) |
| CONDITION | 16 | `IF(p.o.Statut (blanc pour... [D]='', 'OK', 'ERR')` | [RM-001](#rm-RM-001) |
| CONDITION | 5 | `v.Retour cmd [G]<>0` | - |
| CONDITION | 3 | `StrBuild(Translate('%club_exe%ITRT.CsvToExcelConverter "@1@" @2@ > "@3@"  2>&1'), p.i.Fichier csv [A], v.Séparateur [E], v.Fichier retour [H])` | - |

#### CONSTANTE (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 19 | `'xlsx'` | - |
| CONSTANTE | 21 | `'txt'` | - |
| CONSTANTE | 9 | `''` | - |
| CONSTANTE | 12 | `'OFFICEWEB'` | - |

#### NEGATION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| NEGATION | 8 | `NOT FileExist (p.o.Fichier xlsx [B])` | - |
| NEGATION | 7 | `NOT FileExist (p.i.Fichier csv [A])` | - |

#### OTHER (10 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 18 | `File2Blb (p.i.Fichier csv [A])` | - |
| OTHER | 17 | `StrToken (p.i.Fichier csv [A],StrTokenCnt(p.i.Fichier csv [A], '.'),'.')` | - |
| OTHER | 20 | `File2Blb (p.o.Fichier xlsx [B])` | - |
| OTHER | 24 | `FileDelete (v.Fichier retour [H])` | - |
| OTHER | 22 | `File2Blb (v.Fichier retour [H])` | - |
| ... | | *+5 autres* | |

#### FORMAT (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| FORMAT | 6 | `StrBuild('CSV conversion error @1@', Str(v.Retour cmd [G], 'N3L'))` | - |
| FORMAT | 2 | `RepStr(p.o.Fichier xlsx [B], '.xlsx', '_csv_cnv_return.txt')` | - |
| FORMAT | 1 | `RepStr(p.i.Fichier csv [A], '.' & StrToken (p.i.Fichier csv [A],StrTokenCnt(p.i.Fichier csv [A], '.'),'.'), '.xlsx')` | - |

### 12.3 Toutes les expressions (24)

<details>
<summary>Voir les 24 expressions</summary>

#### CALCULATION (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 4 | `'cmd /c ' &v.Commande convertir [F]` |

#### CONDITION (4)

| IDE | Expression Decodee |
|-----|-------------------|
| 16 | `IF(p.o.Statut (blanc pour... [D]='', 'OK', 'ERR')` |
| 23 | `IF(p.i.Séparateur [C]='', IF(Translate('%club_excel_separator%')='', ';', Translate('%club_excel_separator%')), p.i.Séparateur [C])` |
| 3 | `StrBuild(Translate('%club_exe%ITRT.CsvToExcelConverter "@1@" @2@ > "@3@"  2>&1'), p.i.Fichier csv [A], v.Séparateur [E], v.Fichier retour [H])` |
| 5 | `v.Retour cmd [G]<>0` |

#### CONSTANTE (4)

| IDE | Expression Decodee |
|-----|-------------------|
| 9 | `''` |
| 12 | `'OFFICEWEB'` |
| 19 | `'xlsx'` |
| 21 | `'txt'` |

#### NEGATION (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 7 | `NOT FileExist (p.i.Fichier csv [A])` |
| 8 | `NOT FileExist (p.o.Fichier xlsx [B])` |

#### OTHER (10)

| IDE | Expression Decodee |
|-----|-------------------|
| 10 | `StrBuild('Excel file @1@ not found', p.o.Fichier xlsx [B])` |
| 11 | `StrBuild('Unable to find input file @1@.', p.i.Fichier csv [A])` |
| 13 | `StrBuild('@1@ : CSV to XLSX convertion', GetLibelleProg())` |
| 14 | `StrBuild ('"@1@" conversion', p.i.Fichier csv [A])` |
| 15 | `v.Commande convertir [F]` |
| 17 | `StrToken (p.i.Fichier csv [A],StrTokenCnt(p.i.Fichier csv [A], '.'),'.')` |
| 18 | `File2Blb (p.i.Fichier csv [A])` |
| 20 | `File2Blb (p.o.Fichier xlsx [B])` |
| 22 | `File2Blb (v.Fichier retour [H])` |
| 24 | `FileDelete (v.Fichier retour [H])` |

#### FORMAT (3)

| IDE | Expression Decodee |
|-----|-------------------|
| 1 | `RepStr(p.i.Fichier csv [A], '.' & StrToken (p.i.Fichier csv [A],StrTokenCnt(p.i.Fichier csv [A], '.'),'.'), '.xlsx')` |
| 2 | `RepStr(p.o.Fichier xlsx [B], '.xlsx', '_csv_cnv_return.txt')` |
| 6 | `StrBuild('CSV conversion error @1@', Str(v.Retour cmd [G], 'N3L'))` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Extraction biking (IDE 616)](REF-IDE-616.md) -> **Converti csv en xlsx / Exe (IDE 817)**

Main -> ... -> [Converti csv en xlsx (IDE 816)](REF-IDE-816.md) -> **Converti csv en xlsx / Exe (IDE 817)**

Main -> ... -> [Affiche csv/xlsx Office Web (IDE 819)](REF-IDE-819.md) -> **Converti csv en xlsx / Exe (IDE 817)**

```mermaid
graph LR
    T817[817 Converti csv en xl...]
    style T817 fill:#58a6ff
    CC663[663 Extraction Ca Comp...]
    style CC663 fill:#8b5cf6
    CC616[616 Extraction biking]
    style CC616 fill:#3fb950
    CC819[819 Affiche csvxlsx Of...]
    style CC819 fill:#3fb950
    CC816[816 Converti csv en xlsx]
    style CC816 fill:#3fb950
    CC663 --> CC616
    CC663 --> CC816
    CC663 --> CC819
    CC616 --> T817
    CC816 --> T817
    CC819 --> T817
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [616](REF-IDE-616.md) | Extraction biking | 1 |
| [816](REF-IDE-816.md) | Converti csv en xlsx | 1 |
| [819](REF-IDE-819.md) | Affiche csv/xlsx Office Web | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T817[817 Converti csv en xl...]
    style T817 fill:#58a6ff
    C829[829 Log batch]
    T817 --> C829
    style C829 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [829](REF-IDE-829.md) | Log batch | 1 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 42 | Programme compact |
| Expressions | 24 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 1 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 42) | Code sain |
| Regles metier | 2 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 1 ecran, 0 traitement)

- **Strategie** : 1 composant(s) UI (Razor/React) avec formulaires et validation.
- 1 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| [Log batch (IDE 829)](REF-IDE-829.md) | Sous-programme | 1x | Normale - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 14:32*
