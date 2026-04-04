# PBP IDE 268 - Liste mec preparation planning

> **Analyse**: Phases 1-4 2026-02-03 16:04 -> 16:04 (14s) | Assemblage 16:04
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBP |
| IDE Position | 268 |
| Nom Programme | Liste mec preparation planning |
| Fichier source | `Prg_268.xml` |
| Dossier IDE | Mecano |
| Taches | 9 (1 ecrans visibles) |
| Tables modifiees | 6 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Liste mec preparation planning** assure la gestion complete de ce processus, accessible depuis [Liste Mecanographique (IDE 127)](PBP-IDE-127.md).

Le flux de traitement s'organise en **3 blocs fonctionnels** :

- **Traitement** (4 taches) : traitements metier divers
- **Creation** (3 taches) : insertion d'enregistrements en base (mouvements, prestations)
- **Initialisation** (2 taches) : reinitialisation d'etats et de variables de travail

**Donnees modifiees** : 6 tables en ecriture (tempo_present_excel, tempo_zone_secteur, tempo_facturation, tempo_livre_de_porte_bresil, tempo_livre_de_porte, fichier_fictif_blocage_import).

**Logique metier** : 3 regles identifiees couvrant conditions metier.

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (4 taches)

- **268** - Veuillez patienter ... **[[ECRAN]](#ecran-t1)**
- **268.1** - eff mecano 1
- **268.2** - eff mecano 2
- **268.4** - eff nombre

#### Phase 2 : Initialisation (2 taches)

- **268.3** - RaZ 161
- **268.5** - RaZ Tempo ecran

#### Phase 3 : Creation (3 taches)

- **268.6** - creation mecano 1
- **268.7** - creation mecano 1
- **268.8** - creation mecano 2

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| tempo_zone_secteur | **W** (2 usages) | Table temporaire ecran |
| tempo_facturation | **W** (2 usages) | Table temporaire ecran |
| tempo_livre_de_porte | **W**/L (2 usages) | Table temporaire ecran |
| fichier_fictif_blocage_import | **W** (1 usages) |  |
| tempo_livre_de_porte_bresil | **W** (1 usages) | Table temporaire ecran |
| tempo_present_excel | **W** (1 usages) | Table temporaire ecran |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (4 taches)

Traitements internes.

---

#### <a id="t1"></a>268 - Veuillez patienter ... [[ECRAN]](#ecran-t1)

**Role** : Traitement : Veuillez patienter ....
**Ecran** : 427 x 58 DLU (MDI) | [Voir mockup](#ecran-t1)

<details>
<summary>3 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [268.1](#t2) | eff mecano 1 | Traitement |
| [268.2](#t3) | eff mecano 2 | Traitement |
| [268.4](#t5) | eff nombre | Traitement |

</details>

---

#### <a id="t2"></a>268.1 - eff mecano 1

**Role** : Traitement : eff mecano 1.

---

#### <a id="t3"></a>268.2 - eff mecano 2

**Role** : Traitement : eff mecano 2.

---

#### <a id="t5"></a>268.4 - eff nombre

**Role** : Calcul : eff nombre.


### 3.2 Initialisation (2 taches)

Reinitialisation d'etats et variables de travail.

---

#### <a id="t4"></a>268.3 - RaZ 161

**Role** : Reinitialisation : RaZ 161.

---

#### <a id="t6"></a>268.5 - RaZ Tempo ecran

**Role** : Reinitialisation : RaZ Tempo ecran.


### 3.3 Creation (3 taches)

Insertion de nouveaux enregistrements en base.

---

#### <a id="t7"></a>268.6 - creation mecano 1

**Role** : Creation d'enregistrement : creation mecano 1.

---

#### <a id="t8"></a>268.7 - creation mecano 1

**Role** : Creation d'enregistrement : creation mecano 1.

---

#### <a id="t9"></a>268.8 - creation mecano 2

**Role** : Creation d'enregistrement : creation mecano 2.


## 5. REGLES METIER

3 regles identifiees:

### Autres (3 regles)

#### <a id="rm-RM-001"></a>[RM-001] Condition toujours vraie (flag actif)

| Element | Detail |
|---------|--------|
| **Condition** | `[BO]='TRUE'LOG` |
| **Si vrai** | '> Heb' |
| **Si faux** | IF ([BH]='TRUE'LOG,'> '&[BN],'')) |
| **Expression source** | Expression 1 : `IF ([BO]='TRUE'LOG,'> Heb',IF ([BH]='TRUE'LOG,'> '&[BN],''))` |
| **Exemple** | Si [BO]='TRUE'LOG â†’ '> Heb'. Sinon â†’ IF ([BH]='TRUE'LOG,'> '&[BN],'')) |

#### <a id="rm-RM-002"></a>[RM-002] Si VG42 alors [GY] sinon [GX])

| Element | Detail |
|---------|--------|
| **Condition** | `VG42` |
| **Si vrai** | [GY] |
| **Si faux** | [GX]) |
| **Expression source** | Expression 32 : `IF(VG42,[GY],[GX])` |
| **Exemple** | Si VG42 â†’ [GY]. Sinon â†’ [GX]) |

#### <a id="rm-RM-003"></a>[RM-003] Condition toujours vraie (flag actif)

| Element | Detail |
|---------|--------|
| **Condition** | `[HC]` |
| **Si vrai** | [HB] |
| **Si faux** | 'TRUE'LOG) |
| **Expression source** | Expression 33 : `IF([HC],[HB],'TRUE'LOG)` |
| **Exemple** | Si [HC] â†’ [HB]. Sinon â†’ 'TRUE'LOG) |

## 6. CONTEXTE

- **Appele par**: [Liste Mecanographique (IDE 127)](PBP-IDE-127.md)
- **Appelle**: 0 programmes | **Tables**: 14 (W:6 R:1 L:8) | **Taches**: 9 | **Expressions**: 33

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 9)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 268 | 268 | Veuillez patienter ... | MDI | 427 | 58 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>268 - Veuillez patienter ...
**Tache** : [268](#t1) | **Type** : MDI | **Dimensions** : 427 x 58 DLU
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
    "taskId":  "268",
    "height":  58
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

### 9.3 Structure hierarchique (9 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **268.1** | [**Veuillez patienter ...** (268)](#t1) [mockup](#ecran-t1) | MDI | 427x58 | Traitement |
| 268.1.1 | [eff mecano 1 (268.1)](#t2) | MDI | - | |
| 268.1.2 | [eff mecano 2 (268.2)](#t3) | MDI | - | |
| 268.1.3 | [eff nombre (268.4)](#t5) | MDI | - | |
| **268.2** | [**RaZ 161** (268.3)](#t4) | MDI | - | Initialisation |
| 268.2.1 | [RaZ Tempo ecran (268.5)](#t6) | MDI | - | |
| **268.3** | [**creation mecano 1** (268.6)](#t7) | MDI | - | Creation |
| 268.3.1 | [creation mecano 1 (268.7)](#t8) | MDI | - | |
| 268.3.2 | [creation mecano 2 (268.8)](#t9) | MDI | - | |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Traitement principal]
    UPDATE[MAJ 6 tables]
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

### Tables utilisees (14)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 30 | gm-recherche_____gmr | Index de recherche | DB | R |   |   | 1 |
| 31 | gm-complet_______gmc |  | DB |   |   | L | 1 |
| 34 | hebergement______heb | Hebergement (chambres) | DB |   |   | L | 1 |
| 36 | client_gm |  | DB |   |   | L | 1 |
| 120 | tables_qualites__qua |  | DB |   |   | L | 1 |
| 358 | import_mod |  | DB |   |   | L | 1 |
| 602 | tempo_liste_service | Table temporaire ecran | TMP |   |   | L | 1 |
| 612 | tempo_present_excel | Table temporaire ecran | TMP |   | **W** |   | 1 |
| 622 | tempo_zone_secteur | Table temporaire ecran | TMP |   | **W** |   | 2 |
| 623 | tempo_facturation | Table temporaire ecran | TMP |   | **W** |   | 2 |
| 624 | tempo_livre_de_porte_bresil | Table temporaire ecran | TMP |   | **W** |   | 1 |
| 625 | tempo_livre_de_porte | Table temporaire ecran | TMP |   | **W** | L | 2 |
| 628 | fichier_fictif_blocage_import |  | DB |   | **W** |   | 1 |
| 637 | tempo_zone_secteur | Table temporaire ecran | DB |   |   | L | 1 |

### Colonnes par table (1 / 7 tables avec colonnes identifiees)

<details>
<summary>Table 30 - gm-recherche_____gmr (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | >Date | R | Date |
| B | >Categorie | R | Alpha |
| C | >Sejour | R | Alpha |
| D | <Total | R | Numeric |
| E | <NbSelect | R | Numeric |
| F | >Seminaire | R | Alpha |
| G | >Date Alpha | R | Alpha |
| H | >Filtre Fidelisation | R | Logical |
| I | w0_Circuit | R | Alpha |
| J | w0_RetQualite | R | Logical |
| K | w0_PackA----------------------- | R | Alpha |
| L | w0_RetCirApres----------------- | R | Logical |
| M | w0_RetHebApres----------------- | R | Logical |

</details>

<details>
<summary>Table 612 - tempo_present_excel (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 622 - tempo_zone_secteur (**W**) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 623 - tempo_facturation (**W**) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 624 - tempo_livre_de_porte_bresil (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 625 - tempo_livre_de_porte (**W**/L) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 628 - fichier_fictif_blocage_import (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Autres (13)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | >Date | Date | - |
| B | >Categorie | Alpha | 1x refs |
| C | >Sejour | Alpha | 2x refs |
| D | <Total | Numeric | 1x refs |
| E | <NbSelect | Numeric | 1x refs |
| F | >Seminaire | Alpha | 1x refs |
| G | >Date Alpha | Alpha | - |
| H | >Filtre Fidelisation | Logical | - |
| I | w0_Circuit | Alpha | - |
| J | w0_RetQualite | Logical | - |
| K | w0_PackA----------------------- | Alpha | - |
| L | w0_RetCirApres----------------- | Logical | - |
| M | w0_RetHebApres----------------- | Logical | - |

## 12. EXPRESSIONS

**33 / 33 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONDITION | 6 | 5 |
| CAST_LOGIQUE | 2 | 2 |
| CONSTANTE | 7 | 0 |
| OTHER | 17 | 0 |
| REFERENCE_VG | 1 | 0 |

### 12.2 Expressions cles par type

#### CONDITION (6 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 32 | `IF(VG42,[GY],[GX])` | [RM-002](#rm-RM-002) |
| CONDITION | 24 | `CndRange (Trim (>Seminaire [F])<>'',>Seminaire [F])` | - |
| CONDITION | 27 | `CndRange (Trim (>Sejour [C])<>'',>Sejour [C])` | - |
| CONDITION | 2 | `(>Categorie [B]=[BG] OR >Categorie [B]=MlsTrans ('Toutes') OR Trim (>Categorie [B])='') AND (>Sejour [C]=[AH] OR >Sejour [C]='') AND [AV] AND [CA] AND ([CG] OR [AI]='')` | - |
| CONDITION | 20 | `<NbSelect [E]+1` | - |
| ... | | *+1 autres* | |

#### CAST_LOGIQUE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 33 | `IF([HC],[HB],'TRUE'LOG)` | [RM-003](#rm-RM-003) |
| CAST_LOGIQUE | 1 | `IF ([BO]='TRUE'LOG,'> Heb',IF ([BH]='TRUE'LOG,'> '&[BN],''))` | [RM-001](#rm-RM-001) |

#### CONSTANTE (7 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 16 | `'TQUME'` | - |
| CONSTANTE | 25 | `'D'` | - |
| CONSTANTE | 26 | `'TCLME'` | - |
| CONSTANTE | 11 | `'H'` | - |
| CONSTANTE | 3 | `'A'` | - |
| ... | | *+2 autres* | |

#### OTHER (17 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 22 | `DbDel ('{626,2}'DSOURCE,'')` | - |
| OTHER | 23 | `DbDel ('{627,2}'DSOURCE,'')` | - |
| OTHER | 18 | `[AF]` | - |
| OTHER | 21 | `DbDel ('{625,2}'DSOURCE,'')` | - |
| OTHER | 30 | `[GC]` | - |
| ... | | *+12 autres* | |

#### REFERENCE_VG (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 15 | `VG1` | - |

### 12.3 Toutes les expressions (33)

<details>
<summary>Voir les 33 expressions</summary>

#### CONDITION (6)

| IDE | Expression Decodee |
|-----|-------------------|
| 19 | `<Total [D]+1` |
| 20 | `<NbSelect [E]+1` |
| 32 | `IF(VG42,[GY],[GX])` |
| 2 | `(>Categorie [B]=[BG] OR >Categorie [B]=MlsTrans ('Toutes') OR Trim (>Categorie [B])='') AND (>Sejour [C]=[AH] OR >Sejour [C]='') AND [AV] AND [CA] AND ([CG] OR [AI]='')` |
| 24 | `CndRange (Trim (>Seminaire [F])<>'',>Seminaire [F])` |
| 27 | `CndRange (Trim (>Sejour [C])<>'',>Sejour [C])` |

#### CAST_LOGIQUE (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 1 | `IF ([BO]='TRUE'LOG,'> Heb',IF ([BH]='TRUE'LOG,'> '&[BN],''))` |
| 33 | `IF([HC],[HB],'TRUE'LOG)` |

#### CONSTANTE (7)

| IDE | Expression Decodee |
|-----|-------------------|
| 3 | `'A'` |
| 4 | `'1'` |
| 7 | `'C'` |
| 11 | `'H'` |
| 16 | `'TQUME'` |
| 25 | `'D'` |
| 26 | `'TCLME'` |

#### OTHER (17)

| IDE | Expression Decodee |
|-----|-------------------|
| 5 | `[AE]` |
| 6 | `[AF]` |
| 8 | `[S]` |
| 9 | `[T]` |
| 10 | `[R]` |
| 12 | `GetParam ('SOCIETE')` |
| 13 | `[AQ]` |
| 14 | `[AC]` |
| 17 | `[AE]` |
| 18 | `[AF]` |
| 21 | `DbDel ('{625,2}'DSOURCE,'')` |
| 22 | `DbDel ('{626,2}'DSOURCE,'')` |
| 23 | `DbDel ('{627,2}'DSOURCE,'')` |
| 28 | `[AI]` |
| 29 | `[GB]` |
| 30 | `[GC]` |
| 31 | `[FW]` |

#### REFERENCE_VG (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 15 | `VG1` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Liste Mecanographique (IDE 127)](PBP-IDE-127.md) -> **Liste mec preparation planning (IDE 268)**

```mermaid
graph LR
    T268[268 Liste mec preparat...]
    style T268 fill:#58a6ff
    CC127[127 Liste Mecanographique]
    style CC127 fill:#8b5cf6
    CC127 --> T268
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [127](PBP-IDE-127.md) | Liste Mecanographique | 2 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T268[268 Liste mec preparat...]
    style T268 fill:#58a6ff
    NONE[Aucun callee]
    T268 -.-> NONE
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
| Lignes de logique | 236 | Taille moyenne |
| Expressions | 33 | Peu de logique |
| Tables WRITE | 6 | Fort impact donnees |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 236) | Code sain |
| Regles metier | 3 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (4 taches: 1 ecran, 3 traitements)

- **Strategie** : Orchestrateur avec 1 ecrans (Razor/React) et 3 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- Decomposer les taches en services unitaires testables.

#### Initialisation (2 taches: 0 ecran, 2 traitements)

- **Strategie** : Constructeur/methode `InitAsync()` dans l'orchestrateur.

#### Creation (3 taches: 0 ecran, 3 traitements)

- **Strategie** : Repository pattern avec Entity Framework Core.
- Insertion via `IRepository<T>.CreateAsync()`

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| tempo_present_excel | Table WRITE (Temp) | 1x | Schema + repository |
| tempo_zone_secteur | Table WRITE (Temp) | 2x | Schema + repository |
| tempo_facturation | Table WRITE (Temp) | 2x | Schema + repository |
| tempo_livre_de_porte_bresil | Table WRITE (Temp) | 1x | Schema + repository |
| tempo_livre_de_porte | Table WRITE (Temp) | 1x | Schema + repository |
| fichier_fictif_blocage_import | Table WRITE (Database) | 1x | Schema + repository |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 16:04*
