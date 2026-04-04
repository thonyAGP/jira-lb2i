# REF IDE 689 - Creation tempo ecran par doss

> **Analyse**: Phases 1-4 2026-02-03 13:41 -> 13:41 (21s) | Assemblage 13:41
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | REF |
| IDE Position | 689 |
| Nom Programme | Creation tempo ecran par doss |
| Fichier source | `Prg_689.xml` |
| Dossier IDE | General |
| Taches | 3 (1 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 1 |
| :warning: Statut | **ORPHELIN_POTENTIEL** |

## 2. DESCRIPTION FONCTIONNELLE

**Creation tempo ecran par doss** assure la gestion complete de ce processus.

Le flux de traitement s'organise en **2 blocs fonctionnels** :

- **Creation** (2 taches) : insertion d'enregistrements en base (mouvements, prestations)
- **Traitement** (1 tache) : traitements metier divers

**Donnees modifiees** : 1 tables en ecriture (tempo_ecran_mecano).

**Logique metier** : 3 regles identifiees couvrant conditions metier.

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (1 tache)

- **689** - Veuillez patienter ... **[[ECRAN]](#ecran-t1)**

Delegue a : [Determination Age Bebe (IDE 776)](REF-IDE-776.md)

#### Phase 2 : Creation (2 taches)

- **689.1** - Creat separateur
- **689.2** - Creat Blanc

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| tempo_ecran_mecano | **W**/L (3 usages) | Table temporaire ecran |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>689 - Veuillez patienter ... [[ECRAN]](#ecran-t1)

**Role** : Traitement : Veuillez patienter ....
**Ecran** : 427 x 59 DLU (MDI) | [Voir mockup](#ecran-t1)
**Delegue a** : [Determination Age Bebe (IDE 776)](REF-IDE-776.md)


### 3.2 Creation (2 taches)

Insertion de nouveaux enregistrements en base.

---

#### <a id="t2"></a>689.1 - Creat separateur

**Role** : Traitement : Creat separateur.

---

#### <a id="t3"></a>689.2 - Creat Blanc

**Role** : Traitement : Creat Blanc.
**Variables liees** : J (w0_LigneBlanche)


## 5. REGLES METIER

3 regles identifiees:

### Autres (3 regles)

#### <a id="rm-RM-001"></a>[RM-001] Traitement si [AL] est renseigne

| Element | Detail |
|---------|--------|
| **Condition** | `[AL]<>''` |
| **Si vrai** | [AL] |
| **Si faux** | IF([AH]='GO',[BA],'')) |
| **Expression source** | Expression 12 : `IF([AL]<>'',[AL],IF([AH]='GO',[BA],''))` |
| **Exemple** | Si [AL]<>'' â†’ [AL]. Sinon â†’ IF([AH]='GO',[BA],'')) |

#### <a id="rm-RM-002"></a>[RM-002] Si [AR]>0 alors Str ([AG] sinon '3Z'),'40')

| Element | Detail |
|---------|--------|
| **Condition** | `[AR]>0` |
| **Si vrai** | Str ([AG] |
| **Si faux** | '3Z'),'40') |
| **Expression source** | Expression 17 : `IF ([AR]>0,Str ([AG],'3Z'),'40')` |
| **Exemple** | Si [AR]>0 â†’ Str ([AG]. Sinon â†’ '3Z'),'40') |

#### <a id="rm-RM-003"></a>[RM-003] Si [AR]>0 AND [AG]<=[BJ] alors 'B' sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `[AR]>0 AND [AG]<=[BJ]` |
| **Si vrai** | 'B' |
| **Si faux** | '') |
| **Expression source** | Expression 28 : `IF ([AR]>0 AND [AG]<=[BJ],'B','')` |
| **Exemple** | Si [AR]>0 AND [AG]<=[BJ] â†’ 'B'. Sinon â†’ '') |

## 6. CONTEXTE

- **Appele par**: (aucun)
- **Appelle**: 1 programmes | **Tables**: 11 (W:1 R:1 L:10) | **Taches**: 3 | **Expressions**: 56

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 3)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 689 | 689 | Veuillez patienter ... | MDI | 427 | 59 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>689 - Veuillez patienter ...
**Tache** : [689](#t1) | **Type** : MDI | **Dimensions** : 427 x 59 DLU
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
    "taskId":  "689",
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

### 9.3 Structure hierarchique (3 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **689.1** | [**Veuillez patienter ...** (689)](#t1) [mockup](#ecran-t1) | MDI | 427x59 | Traitement |
| **689.2** | [**Creat separateur** (689.1)](#t2) | MDI | - | Creation |
| 689.2.1 | [Creat Blanc (689.2)](#t3) | MDI | - | |

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

### Tables utilisees (11)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 30 | gm-recherche_____gmr | Index de recherche | DB | R |   |   | 1 |
| 31 | gm-complet_______gmc |  | DB |   |   | L | 1 |
| 35 | personnel_go______go |  | DB |   |   | L | 1 |
| 36 | client_gm |  | DB |   |   | L | 1 |
| 121 | tables_pays_ventes | Donnees de ventes | DB |   |   | L | 1 |
| 356 | gm_millesia |  | DB |   |   | L | 1 |
| 584 | tempo_type_millesia | Table temporaire ecran | TMP |   |   | L | 1 |
| 594 | tempo_ecran_mecano | Table temporaire ecran | TMP |   | **W** | L | 3 |
| 606 | tempo_mecano_3_mec3 | Table temporaire ecran | TMP |   |   | L | 1 |
| 610 | tempo_nombres | Table temporaire ecran | TMP |   |   | L | 1 |
| 621 | tempo_ecran_mecano | Table temporaire ecran | TMP |   |   | L | 1 |

### Colonnes par table (1 / 2 tables avec colonnes identifiees)

<details>
<summary>Table 30 - gm-recherche_____gmr (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | <Total | R | Numeric |
| B | <NbSelect | R | Numeric |
| C | <Societe | R | Unicode |
| D | w0_Sequence | R | Numeric |
| E | w0_fidelisation ? | R | Logical |
| F | w0_AgeBebe | R | Numeric |
| G | w0_AgeEnfant | R | Numeric |
| H | w0_Dossier | R | Numeric |
| I | w0_NumAdher | R | Numeric |
| J | w0_LigneBlanche | R | Logical |

</details>

<details>
<summary>Table 594 - tempo_ecran_mecano (**W**/L) - 3 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Autres (10)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | <Total | Numeric | - |
| B | <NbSelect | Numeric | 1x refs |
| C | <Societe | Unicode | 1x refs |
| D | w0_Sequence | Numeric | 2x refs |
| E | w0_fidelisation ? | Logical | - |
| F | w0_AgeBebe | Numeric | - |
| G | w0_AgeEnfant | Numeric | - |
| H | w0_Dossier | Numeric | - |
| I | w0_NumAdher | Numeric | - |
| J | w0_LigneBlanche | Logical | 1x refs |

## 12. EXPRESSIONS

**56 / 56 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCULATION | 9 | 0 |
| CONDITION | 15 | 3 |
| CONSTANTE | 3 | 0 |
| REFERENCE_VG | 1 | 0 |
| OTHER | 24 | 0 |
| STRING | 3 | 0 |
| CONCATENATION | 1 | 0 |

### 12.2 Expressions cles par type

#### CALCULATION (9 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 47 | `[CV]+1` | - |
| CALCULATION | 45 | `[CU]+1` | - |
| CALCULATION | 51 | `w0_Sequence [D]+1` | - |
| CALCULATION | 49 | `[CW]+1` | - |
| CALCULATION | 44 | `[CT]+1` | - |
| ... | | *+4 autres* | |

#### CONDITION (15 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 28 | `IF ([AR]>0 AND [AG]<=[BJ],'B','')` | [RM-003](#rm-RM-003) |
| CONDITION | 12 | `IF([AL]<>'',[AL],IF([AH]='GO',[BA],''))` | [RM-001](#rm-RM-001) |
| CONDITION | 17 | `IF ([AR]>0,Str ([AG],'3Z'),'40')` | [RM-002](#rm-RM-002) |
| CONDITION | 53 | `[CY]<>0 AND [CX]<>[Y]` | - |
| CONDITION | 52 | `[CX]<>0 AND [CX]<>[Y]` | - |
| ... | | *+10 autres* | |

#### CONSTANTE (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 30 | `''` | - |
| CONSTANTE | 10 | `'VENFA'` | - |
| CONSTANTE | 9 | `'VBEBE'` | - |

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
| OTHER | 21 | `[AW]` | - |
| OTHER | 23 | `[S]` | - |
| ... | | *+19 autres* | |

#### STRING (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| STRING | 22 | `Str ([AM],'9')` | - |
| STRING | 20 | `Str ([R],'2')` | - |
| STRING | 16 | `Str ([M],'2')&Str ([K],'10P0Z0')` | - |

#### CONCATENATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 29 | `Trim([BF])&IF(VG138 AND [DJ]='O','N','')` | - |

### 12.3 Toutes les expressions (56)

<details>
<summary>Voir les 56 expressions</summary>

#### CALCULATION (9)

| IDE | Expression Decodee |
|-----|-------------------|
| 36 | `[CP]+1` |
| 38 | `[CQ]+1` |
| 41 | `[CR]+1` |
| 42 | `[CS]+1` |
| 44 | `[CT]+1` |
| 45 | `[CU]+1` |
| 47 | `[CV]+1` |
| 49 | `[CW]+1` |
| 51 | `w0_Sequence [D]+1` |

#### CONDITION (15)

| IDE | Expression Decodee |
|-----|-------------------|
| 50 | `<NbSelect [B]+1` |
| 12 | `IF([AL]<>'',[AL],IF([AH]='GO',[BA],''))` |
| 17 | `IF ([AR]>0,Str ([AG],'3Z'),'40')` |
| 28 | `IF ([AR]>0 AND [AG]<=[BJ],'B','')` |
| 2 | `<Societe [C]` |
| 35 | `[AR]=0 OR [AG]>IF ([BK]=0,12,[BK])` |
| 37 | `[AF]<>'F'` |
| 39 | `[AF]='F'` |
| 40 | `[AG]>IF ([BJ]=0,2,[BJ]) AND [AG]<=IF ([BK]=0,12,[BK])` |
| 43 | `[AR]>0 AND [AG]<=IF ([BJ]=0,2,[BJ])` |
| 52 | `[CX]<>0 AND [CX]<>[Y]` |
| 53 | `[CY]<>0 AND [CX]<>[Y]` |
| 54 | `[CY]>0 AND [CY]<>[K]` |
| 48 | `Trim(MID ([U],2,2))='1'` |
| 56 | `Trim([BF])<>''` |

#### CONSTANTE (3)

| IDE | Expression Decodee |
|-----|-------------------|
| 9 | `'VBEBE'` |
| 10 | `'VENFA'` |
| 30 | `''` |

#### REFERENCE_VG (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 1 | `VG1` |

#### OTHER (24)

| IDE | Expression Decodee |
|-----|-------------------|
| 3 | `w0_LigneBlanche [J]` |
| 4 | `[K]` |
| 5 | `[M]` |
| 6 | `[AD]` |
| 7 | `[AE]` |
| 8 | `[BF]` |
| 11 | `w0_Sequence [D]` |
| 13 | `[AO]` |
| 14 | `[AP]` |
| 15 | `[AQ]` |
| 18 | `[P]` |
| 19 | `[Q]` |
| 21 | `[AW]` |
| 23 | `[S]` |
| 24 | `[T]` |
| 25 | `[U]` |
| 26 | `[V]` |
| 27 | `[W]` |
| 31 | `[X]` |
| 32 | `[AN]` |
| 33 | `[CK]` |
| 34 | `[CL]` |
| 46 | `[BG]` |
| 55 | `[Y]` |

#### STRING (3)

| IDE | Expression Decodee |
|-----|-------------------|
| 16 | `Str ([M],'2')&Str ([K],'10P0Z0')` |
| 20 | `Str ([R],'2')` |
| 22 | `Str ([AM],'9')` |

#### CONCATENATION (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 29 | `Trim([BF])&IF(VG138 AND [DJ]='O','N','')` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

**Chemin**: (pas de callers directs)

```mermaid
graph LR
    T689[689 Creation tempo ecr...]
    style T689 fill:#58a6ff
    NONE[Aucun caller]
    NONE -.-> T689
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| - | (aucun) | - |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T689[689 Creation tempo ecr...]
    style T689 fill:#58a6ff
    C776[776 Determination Age ...]
    T689 --> C776
    style C776 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [776](REF-IDE-776.md) | Determination Age Bebe | 2 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 214 | Taille moyenne |
| Expressions | 56 | Logique moderee |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 1 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0.5% (1 / 214) | Code sain |
| Regles metier | 3 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 1 ecran, 0 traitement)

- **Strategie** : 1 composant(s) UI (Razor/React) avec formulaires et validation.
- 1 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Creation (2 taches: 0 ecran, 2 traitements)

- **Strategie** : Repository pattern avec Entity Framework Core.
- Insertion via `IRepository<T>.CreateAsync()`

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| tempo_ecran_mecano | Table WRITE (Temp) | 2x | Schema + repository |
| [Determination Age Bebe (IDE 776)](REF-IDE-776.md) | Sous-programme | 2x | Haute - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 13:41*
