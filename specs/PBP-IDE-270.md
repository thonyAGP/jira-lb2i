# PBP IDE 270 - Creation tempo ecran par nom

> **Analyse**: Phases 1-4 2026-02-03 16:05 -> 16:05 (16s) | Assemblage 16:05
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBP |
| IDE Position | 270 |
| Nom Programme | Creation tempo ecran par nom |
| Fichier source | `Prg_270.xml` |
| Dossier IDE | Mecano |
| Taches | 4 (1 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 1 |

## 2. DESCRIPTION FONCTIONNELLE

**Creation tempo ecran par nom** assure la gestion complete de ce processus, accessible depuis [Liste Mecanographique (IDE 127)](PBP-IDE-127.md).

Le flux de traitement s'organise en **2 blocs fonctionnels** :

- **Creation** (2 taches) : insertion d'enregistrements en base (mouvements, prestations)
- **Traitement** (2 taches) : traitements metier divers

**Donnees modifiees** : 1 tables en ecriture (tempo_present_excel).

**Logique metier** : 4 regles identifiees couvrant conditions metier.

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (2 taches)

- **270** - Veuillez patienter ... **[[ECRAN]](#ecran-t1)**
- **270.3** - View

#### Phase 2 : Creation (2 taches)

- **270.1** - Creat separateur
- **270.2** - Creat Blanc

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| tempo_present_excel | **W**/L (3 usages) | Table temporaire ecran |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (2 taches)

Traitements internes.

---

#### <a id="t1"></a>270 - Veuillez patienter ... [[ECRAN]](#ecran-t1)

**Role** : Traitement : Veuillez patienter ....
**Ecran** : 427 x 59 DLU (MDI) | [Voir mockup](#ecran-t1)

---

#### <a id="t4"></a>270.3 - View

**Role** : Traitement : View.


### 3.2 Creation (2 taches)

Insertion de nouveaux enregistrements en base.

---

#### <a id="t2"></a>270.1 - Creat separateur

**Role** : Traitement : Creat separateur.

---

#### <a id="t3"></a>270.2 - Creat Blanc

**Role** : Traitement : Creat Blanc.
**Variables liees** : J (w0_LigneBlanche)


## 5. REGLES METIER

4 regles identifiees:

### Autres (4 regles)

#### <a id="rm-RM-001"></a>[RM-001] Si VG42 alors [HO] sinon [BG])

| Element | Detail |
|---------|--------|
| **Condition** | `VG42` |
| **Si vrai** | [HO] |
| **Si faux** | [BG]) |
| **Expression source** | Expression 7 : `IF(VG42,[HO],[BG])` |
| **Exemple** | Si VG42 â†’ [HO]. Sinon â†’ [BG]) |

#### <a id="rm-RM-002"></a>[RM-002] Traitement si [BA] est renseigne

| Element | Detail |
|---------|--------|
| **Condition** | `[BA]<>''` |
| **Si vrai** | [BA] |
| **Si faux** | IF([IM]='GO',[IL],'')) |
| **Expression source** | Expression 12 : `IF([BA]<>'',[BA],IF([IM]='GO',[IL],''))` |
| **Exemple** | Si [BA]<>'' â†’ [BA]. Sinon â†’ IF([IM]='GO',[IL],'')) |

#### <a id="rm-RM-003"></a>[RM-003] Si [HT]>0 alors Str ([HY] sinon '3Z'),'40')

| Element | Detail |
|---------|--------|
| **Condition** | `[HT]>0` |
| **Si vrai** | Str ([HY] |
| **Si faux** | '3Z'),'40') |
| **Expression source** | Expression 17 : `IF ([HT]>0,Str ([HY],'3Z'),'40')` |
| **Exemple** | Si [HT]>0 â†’ Str ([HY]. Sinon â†’ '3Z'),'40') |

#### <a id="rm-RM-004"></a>[RM-004] Si [HT]>0 AND [HY]<=[BH] alors 'B' sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `[HT]>0 AND [HY]<=[BH]` |
| **Si vrai** | 'B' |
| **Si faux** | '') |
| **Expression source** | Expression 28 : `IF ([HT]>0 AND [HY]<=[BH],'B','')` |
| **Exemple** | Si [HT]>0 AND [HY]<=[BH] â†’ 'B'. Sinon â†’ '') |

## 6. CONTEXTE

- **Appele par**: [Liste Mecanographique (IDE 127)](PBP-IDE-127.md)
- **Appelle**: 1 programmes | **Tables**: 11 (W:1 R:1 L:10) | **Taches**: 4 | **Expressions**: 57

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 4)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 270 | 270 | Veuillez patienter ... | MDI | 427 | 59 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>270 - Veuillez patienter ...
**Tache** : [270](#t1) | **Type** : MDI | **Dimensions** : 427 x 59 DLU
**Bloc** : Traitement | **Titre IDE** : Veuillez patienter ...

<!-- FORM-DATA:
{
    "width":  427,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  423,
                         "fmt":  "",
                         "name":  "",
                         "h":  29,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  120,
                         "type":  "label",
                         "var":  "",
                         "y":  10,
                         "w":  221,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "7",
                         "text":  "Traitement en cours ...",
                         "parent":  null
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  29,
                         "w":  423,
                         "fmt":  "",
                         "name":  "",
                         "h":  27,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  110,
                         "type":  "label",
                         "var":  "",
                         "y":  32,
                         "w":  114,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Analyses :",
                         "parent":  4
                     },
                     {
                         "x":  110,
                         "type":  "label",
                         "var":  "",
                         "y":  44,
                         "w":  139,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Selectiones :",
                         "parent":  4
                     },
                     {
                         "x":  4,
                         "type":  "image",
                         "var":  "",
                         "y":  2,
                         "w":  72,
                         "fmt":  "",
                         "name":  "",
                         "h":  25,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  259,
                         "type":  "edit",
                         "var":  "",
                         "y":  32,
                         "w":  56,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  259,
                         "type":  "edit",
                         "var":  "",
                         "y":  44,
                         "w":  56,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  4
                     }
                 ],
    "taskId":  "270",
    "height":  59
}
-->

<details>
<summary><strong>Champs : 2 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 259,32 | (sans nom) | - | edit |
| 259,44 | (sans nom) | - | edit |

</details>

## 9. NAVIGATION

Ecran unique: **Veuillez patienter ...**

### 9.3 Structure hierarchique (4 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **270.1** | [**Veuillez patienter ...** (270)](#t1) [mockup](#ecran-t1) | MDI | 427x59 | Traitement |
| 270.1.1 | [View (270.3)](#t4) | - | - | |
| **270.2** | [**Creat separateur** (270.1)](#t2) | MDI | - | Creation |
| 270.2.1 | [Creat Blanc (270.2)](#t3) | MDI | - | |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[View]
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

### Tables utilisees (11)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 30 | gm-recherche_____gmr | Index de recherche | DB | R |   |   | 1 |
| 31 | gm-complet_______gmc |  | DB |   |   | L | 1 |
| 35 | personnel_go______go |  | DB |   |   | L | 1 |
| 36 | client_gm |  | DB |   |   | L | 1 |
| 121 | tables_pays_ventes | Donnees de ventes | DB |   |   | L | 1 |
| 358 | import_mod |  | DB |   |   | L | 1 |
| 602 | tempo_liste_service | Table temporaire ecran | TMP |   |   | L | 1 |
| 612 | tempo_present_excel | Table temporaire ecran | TMP |   | **W** | L | 3 |
| 624 | tempo_livre_de_porte_bresil | Table temporaire ecran | TMP |   |   | L | 1 |
| 628 | fichier_fictif_blocage_import |  | DB |   |   | L | 1 |
| 639 | tempo_code_autocom | Table temporaire ecran | DB |   |   | L | 1 |

### Colonnes par table (1 / 2 tables avec colonnes identifiees)

<details>
<summary>Table 30 - gm-recherche_____gmr (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | <Total | R | Numeric |
| B | <NbSelect | R | Numeric |
| C | <Ordre Tri | R | Alpha |
| D | w0_Sequence | R | Numeric |
| E | V.Fidelisation ? | R | Logical |
| F | w0_AgeBebe | R | Numeric |
| G | w0_AgeEnfant | R | Numeric |
| H | w0_NomGroupe | R | Alpha |
| I | w0_NumAdher | R | Numeric |
| J | w0_LigneBlanche | R | Logical |

</details>

<details>
<summary>Table 612 - tempo_present_excel (**W**/L) - 3 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Variables de session (1)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| E | V.Fidelisation ? | Logical | - |

### 11.2 Autres (9)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | <Total | Numeric | - |
| B | <NbSelect | Numeric | 1x refs |
| C | <Ordre Tri | Alpha | - |
| D | w0_Sequence | Numeric | 2x refs |
| F | w0_AgeBebe | Numeric | - |
| G | w0_AgeEnfant | Numeric | - |
| H | w0_NomGroupe | Alpha | 2x refs |
| I | w0_NumAdher | Numeric | - |
| J | w0_LigneBlanche | Logical | - |

## 12. EXPRESSIONS

**57 / 57 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCULATION | 9 | 0 |
| CONDITION | 15 | 4 |
| CONSTANTE | 3 | 0 |
| REFERENCE_VG | 1 | 0 |
| OTHER | 24 | 0 |
| CAST_LOGIQUE | 1 | 0 |
| STRING | 3 | 0 |
| CONCATENATION | 1 | 0 |

### 12.2 Expressions cles par type

#### CALCULATION (9 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 46 | `[CT]+1` | - |
| CALCULATION | 45 | `[CS]+1` | - |
| CALCULATION | 50 | `w0_Sequence [D]+1` | - |
| CALCULATION | 48 | `[CU]+1` | - |
| CALCULATION | 44 | `[CR]+1` | - |
| ... | | *+4 autres* | |

#### CONDITION (15 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 12 | `IF([BA]<>'',[BA],IF([IM]='GO',[IL],''))` | [RM-002](#rm-RM-002) |
| CONDITION | 17 | `IF ([HT]>0,Str ([HY],'3Z'),'40')` | [RM-003](#rm-RM-003) |
| CONDITION | 28 | `IF ([HT]>0 AND [HY]<=[BH],'B','')` | [RM-004](#rm-RM-004) |
| CONDITION | 7 | `IF(VG42,[HO],[BG])` | [RM-001](#rm-RM-001) |
| CONDITION | 52 | `[CV]<>'' AND [CV]<>w0_NomGroupe [H]` | - |
| ... | | *+10 autres* | |

#### CONSTANTE (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 30 | `''` | - |
| CONSTANTE | 9 | `'VENFA'` | - |
| CONSTANTE | 8 | `'VBEBE'` | - |

#### REFERENCE_VG (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 1 | `VG1` | - |

#### OTHER (24 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 25 | `[U]` | - |
| OTHER | 26 | `[V]` | - |
| OTHER | 27 | `[W]` | - |
| OTHER | 21 | `[AS]` | - |
| OTHER | 23 | `[S]` | - |
| ... | | *+19 autres* | |

#### CAST_LOGIQUE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 51 | `'FALSE'LOG` | - |

#### STRING (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| STRING | 22 | `Str ([BB],'9')` | - |
| STRING | 20 | `Str ([R],'2')` | - |
| STRING | 16 | `Str ([M],'2')&Str ([K],'10P0Z0')` | - |

#### CONCATENATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 29 | `Trim([HO])&IF(VG125 AND [IR]='O','N','')` | - |

### 12.3 Toutes les expressions (57)

<details>
<summary>Voir les 57 expressions</summary>

#### CALCULATION (9)

| IDE | Expression Decodee |
|-----|-------------------|
| 36 | `[CN]+1` |
| 38 | `[CO]+1` |
| 41 | `[CP]+1` |
| 42 | `[CQ]+1` |
| 44 | `[CR]+1` |
| 45 | `[CS]+1` |
| 46 | `[CT]+1` |
| 48 | `[CU]+1` |
| 50 | `w0_Sequence [D]+1` |

#### CONDITION (15)

| IDE | Expression Decodee |
|-----|-------------------|
| 49 | `<NbSelect [B]+1` |
| 7 | `IF(VG42,[HO],[BG])` |
| 12 | `IF([BA]<>'',[BA],IF([IM]='GO',[IL],''))` |
| 17 | `IF ([HT]>0,Str ([HY],'3Z'),'40')` |
| 28 | `IF ([HT]>0 AND [HY]<=[BH],'B','')` |
| 56 | `IF(VG42,[HO]<>'' OR [BG]<>'',[BG]<>'')` |
| 35 | `[HT]=0 OR [HY]>IF ([BI]=0,12,[BI])` |
| 37 | `[HZ]<>'F'` |
| 39 | `[HZ]='F'` |
| 40 | `[HY]>IF ([BH]=0,2,[BH]) AND [HY]<=IF ([BI]=0,12,[BI])` |
| 43 | `[HT]>0 AND [HY]<=IF ([BH]=0,2,[BH])` |
| 52 | `[CV]<>'' AND [CV]<>w0_NomGroupe [H]` |
| 53 | `[CW]>0 AND [CW]<>[K]` |
| 57 | `[IE]=10455022` |
| 47 | `Trim(MID ([U],2,2))='1'` |

#### CONSTANTE (3)

| IDE | Expression Decodee |
|-----|-------------------|
| 8 | `'VBEBE'` |
| 9 | `'VENFA'` |
| 30 | `''` |

#### REFERENCE_VG (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 1 | `VG1` |

#### OTHER (24)

| IDE | Expression Decodee |
|-----|-------------------|
| 2 | `GetParam ('SOCIETE')` |
| 3 | `[K]` |
| 4 | `[M]` |
| 5 | `[HW]` |
| 6 | `[HV]` |
| 10 | `w0_Sequence [D]` |
| 11 | `[BA]` |
| 13 | `[HS]` |
| 14 | `[HP]` |
| 15 | `[HQ]` |
| 18 | `[P]` |
| 19 | `[Q]` |
| 21 | `[AS]` |
| 23 | `[S]` |
| 24 | `[T]` |
| 25 | `[U]` |
| 26 | `[V]` |
| 27 | `[W]` |
| 31 | `[X]` |
| 32 | `[BC]` |
| 33 | `[CI]` |
| 34 | `[CJ]` |
| 54 | `w0_NomGroupe [H]` |
| 55 | `[IH]` |

#### CAST_LOGIQUE (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 51 | `'FALSE'LOG` |

#### STRING (3)

| IDE | Expression Decodee |
|-----|-------------------|
| 16 | `Str ([M],'2')&Str ([K],'10P0Z0')` |
| 20 | `Str ([R],'2')` |
| 22 | `Str ([BB],'9')` |

#### CONCATENATION (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 29 | `Trim([HO])&IF(VG125 AND [IR]='O','N','')` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Liste Mecanographique (IDE 127)](PBP-IDE-127.md) -> **Creation tempo ecran par nom (IDE 270)**

```mermaid
graph LR
    T270[270 Creation tempo ecr...]
    style T270 fill:#58a6ff
    CC127[127 Liste Mecanographique]
    style CC127 fill:#8b5cf6
    CC127 --> T270
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [127](PBP-IDE-127.md) | Liste Mecanographique | 2 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T270[270 Creation tempo ecr...]
    style T270 fill:#58a6ff
    C307[307 Recherche age Bebe...]
    T270 --> C307
    style C307 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [307](PBP-IDE-307.md) | Recherche age Bebe_Enfant | 2 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 217 | Taille moyenne |
| Expressions | 57 | Logique moderee |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 1 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0.5% (1 / 217) | Code sain |
| Regles metier | 4 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (2 taches: 1 ecran, 1 traitement)

- **Strategie** : Orchestrateur avec 1 ecrans (Razor/React) et 1 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 1 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Creation (2 taches: 0 ecran, 2 traitements)

- **Strategie** : Repository pattern avec Entity Framework Core.
- Insertion via `IRepository<T>.CreateAsync()`

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| tempo_present_excel | Table WRITE (Temp) | 2x | Schema + repository |
| [Recherche age Bebe_Enfant (IDE 307)](PBP-IDE-307.md) | Sous-programme | 2x | Haute - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 16:05*
