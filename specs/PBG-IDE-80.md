# PBG IDE 80 - Interruption Client

> **Analyse**: Phases 1-4 2026-02-03 09:12 -> 09:12 (19s) | Assemblage 09:12
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBG |
| IDE Position | 80 |
| Nom Programme | Interruption Client |
| Fichier source | `Prg_80.xml` |
| Domaine metier | General |
| Taches | 14 (1 ecrans visibles) |
| Tables modifiees | 7 |
| Programmes appeles | 4 |

## 2. DESCRIPTION FONCTIONNELLE

**Interruption Client** assure la gestion complete de ce processus, accessible depuis [Module Sejours CallTask (IDE 0)](PBG-IDE-0.md), [Module Sejours CallTask (IDE 94)](PBG-IDE-94.md), [Module Sejours SubForm (IDE 391)](PBG-IDE-391.md).

Le flux de traitement s'organise en **5 blocs fonctionnels** :

- **Traitement** (8 taches) : traitements metier divers
- **Validation** (2 taches) : controles et verifications de coherence
- **Creation** (2 taches) : insertion d'enregistrements en base (mouvements, prestations)
- **Calcul** (1 tache) : calculs de montants, stocks ou compteurs
- **Saisie** (1 tache) : ecrans de saisie utilisateur (formulaires, champs, donnees)

**Donnees modifiees** : 7 tables en ecriture (gm-recherche_____gmr, hebergement______heb, client_gm, compte_gm________cgm, historik_station, fichier_validation, groupe_arr_dep___vol).

**Logique metier** : 3 regles identifiees couvrant valeurs par defaut.

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (8 taches)

- **80** - Interruption Client **[[ECRAN]](#ecran-t1)**
- **80.1** - Recuperation Periode
- **80.4** - Confirmation Interruption **[[ECRAN]](#ecran-t5)**
- **80.5** - Interruption Batch **[[ECRAN]](#ecran-t6)**
- **80.5.1** - Modification Hebergement
- **80.5.2** - Modification Package
- **80.5.3** - Modification Sejour
- **80.5.4** - Modification Sejour

Delegue a : [Maj effect_personnes_modif_sej (IDE 65)](PBG-IDE-65.md), [Demarquage Caisse (IDE 176)](PBG-IDE-176.md)

#### Phase 2 : Saisie (1 tache)

- **80.2** - Saisie Date Fin **[[ECRAN]](#ecran-t3)**

#### Phase 3 : Creation (2 taches)

- **80.3** - Creation Groupe V/V
- **80.5.8** - Creation Historique

#### Phase 4 : Validation (2 taches)

- **80.5.5** - Verification Compte
- **80.5.7** - Modification Validation

#### Phase 5 : Calcul (1 tache)

- **80.5.6** - Modification Compte

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| hebergement______heb | R/**W** (3 usages) | Hebergement (chambres) |
| gm-recherche_____gmr | R/**W** (2 usages) | Index de recherche |
| client_gm | R/**W** (2 usages) |  |
| historik_station | **W** (1 usages) | Historique / journal |
| fichier_validation | **W** (1 usages) |  |
| groupe_arr_dep___vol | **W** (1 usages) |  |
| compte_gm________cgm | **W** (1 usages) | Comptes GM (generaux) |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (8 taches)

Traitements internes.

---

#### <a id="t1"></a>80 - Interruption Client [[ECRAN]](#ecran-t1)

**Role** : Tache d'orchestration : point d'entree du programme (8 sous-taches). Coordonne l'enchainement des traitements.
**Ecran** : 132 x 48 DLU (MDI) | [Voir mockup](#ecran-t1)

<details>
<summary>7 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [80.1](#t2) | Recuperation Periode | Traitement |
| [80.4](#t5) | Confirmation Interruption **[[ECRAN]](#ecran-t5)** | Traitement |
| [80.5](#t6) | Interruption Batch **[[ECRAN]](#ecran-t6)** | Traitement |
| [80.5.1](#t7) | Modification Hebergement | Traitement |
| [80.5.2](#t8) | Modification Package | Traitement |
| [80.5.3](#t9) | Modification Sejour | Traitement |
| [80.5.4](#t10) | Modification Sejour | Traitement |

</details>
**Delegue a** : [Maj effect_personnes_modif_sej (IDE 65)](PBG-IDE-65.md), [Demarquage Caisse (IDE 176)](PBG-IDE-176.md)

---

#### <a id="t2"></a>80.1 - Recuperation Periode

**Role** : Consultation/chargement : Recuperation Periode.
**Delegue a** : [Maj effect_personnes_modif_sej (IDE 65)](PBG-IDE-65.md), [Demarquage Caisse (IDE 176)](PBG-IDE-176.md)

---

#### <a id="t5"></a>80.4 - Confirmation Interruption [[ECRAN]](#ecran-t5)

**Role** : Traitement : Confirmation Interruption.
**Ecran** : 132 x 32 DLU (MDI) | [Voir mockup](#ecran-t5)
**Delegue a** : [Maj effect_personnes_modif_sej (IDE 65)](PBG-IDE-65.md), [Demarquage Caisse (IDE 176)](PBG-IDE-176.md)

---

#### <a id="t6"></a>80.5 - Interruption Batch [[ECRAN]](#ecran-t6)

**Role** : Traitement : Interruption Batch.
**Ecran** : 132 x 32 DLU (Modal) | [Voir mockup](#ecran-t6)
**Delegue a** : [Maj effect_personnes_modif_sej (IDE 65)](PBG-IDE-65.md), [Demarquage Caisse (IDE 176)](PBG-IDE-176.md)

---

#### <a id="t7"></a>80.5.1 - Modification Hebergement

**Role** : Traitement : Modification Hebergement.
**Delegue a** : [Maj effect_personnes_modif_sej (IDE 65)](PBG-IDE-65.md), [Demarquage Caisse (IDE 176)](PBG-IDE-176.md)

---

#### <a id="t8"></a>80.5.2 - Modification Package

**Role** : Traitement : Modification Package.
**Delegue a** : [Maj effect_personnes_modif_sej (IDE 65)](PBG-IDE-65.md), [Demarquage Caisse (IDE 176)](PBG-IDE-176.md)

---

#### <a id="t9"></a>80.5.3 - Modification Sejour

**Role** : Traitement : Modification Sejour.
**Delegue a** : [Maj effect_personnes_modif_sej (IDE 65)](PBG-IDE-65.md), [Demarquage Caisse (IDE 176)](PBG-IDE-176.md)

---

#### <a id="t10"></a>80.5.4 - Modification Sejour

**Role** : Traitement : Modification Sejour.
**Delegue a** : [Maj effect_personnes_modif_sej (IDE 65)](PBG-IDE-65.md), [Demarquage Caisse (IDE 176)](PBG-IDE-176.md)


### 3.2 Saisie (1 tache)

L'operateur saisit les donnees de la transaction via 1 ecran (Saisie Date Fin).

---

#### <a id="t3"></a>80.2 - Saisie Date Fin [[ECRAN]](#ecran-t3)

**Role** : Saisie des donnees : Saisie Date Fin.
**Ecran** : 413 x 86 DLU (MDI) | [Voir mockup](#ecran-t3)
**Variables liees** : C (W0-Date Debut), E (W0-Date Prevue), G (W0-Date Fin)


### 3.3 Creation (2 taches)

Insertion de nouveaux enregistrements en base.

---

#### <a id="t4"></a>80.3 - Creation Groupe V/V

**Role** : Creation d'enregistrement : Creation Groupe V/V.

---

#### <a id="t14"></a>80.5.8 - Creation Historique

**Role** : Consultation/chargement : Creation Historique.


### 3.4 Validation (2 taches)

Controles de coherence : 2 taches verifient les donnees et conditions.

---

#### <a id="t11"></a>80.5.5 - Verification Compte

**Role** : Verification : Verification Compte.

---

#### <a id="t13"></a>80.5.7 - Modification Validation

**Role** : Verification : Modification Validation.


### 3.5 Calcul (1 tache)

Calculs metier : montants, stocks, compteurs.

---

#### <a id="t12"></a>80.5.6 - Modification Compte

**Role** : Traitement : Modification Compte.


## 5. REGLES METIER

3 regles identifiees:

### Saisie (3 regles)

#### <a id="rm-RM-001"></a>[RM-001] Valeur par defaut si W0-Heure Debut [D] est vide

| Element | Detail |
|---------|--------|
| **Condition** | `W0-Heure Debut [D]=''` |
| **Si vrai** | 'U3' |
| **Si faux** | 'U2h') |
| **Variables** | D (W0-Heure Debut) |
| **Expression source** | Expression 8 : `IF (W0-Heure Debut [D]='','U3','U2h')` |
| **Exemple** | Si W0-Heure Debut [D]='' â†’ 'U3'. Sinon â†’ 'U2h') |
| **Impact** | Bloc Saisie |

#### <a id="rm-RM-002"></a>[RM-002] Valeur par defaut si W0-Heure Prevue [F] est vide

| Element | Detail |
|---------|--------|
| **Condition** | `W0-Heure Prevue [F]=''` |
| **Si vrai** | 'U3' |
| **Si faux** | 'U2h') |
| **Variables** | F (W0-Heure Prevue) |
| **Expression source** | Expression 9 : `IF (W0-Heure Prevue [F]='','U3','U2h')` |
| **Exemple** | Si W0-Heure Prevue [F]='' â†’ 'U3'. Sinon â†’ 'U2h') |
| **Impact** | Bloc Saisie |

#### <a id="rm-RM-003"></a>[RM-003] Valeur par defaut si W0-Heure Fin [H] est vide

| Element | Detail |
|---------|--------|
| **Condition** | `W0-Heure Fin [H]=''` |
| **Si vrai** | 'U3' |
| **Si faux** | 'U2h') |
| **Variables** | H (W0-Heure Fin) |
| **Expression source** | Expression 10 : `IF (W0-Heure Fin [H]='','U3','U2h')` |
| **Exemple** | Si W0-Heure Fin [H]='' â†’ 'U3'. Sinon â†’ 'U2h') |
| **Impact** | Bloc Saisie |

## 6. CONTEXTE

- **Appele par**: [Module Sejours CallTask (IDE 0)](PBG-IDE-0.md), [Module Sejours CallTask (IDE 94)](PBG-IDE-94.md), [Module Sejours SubForm (IDE 391)](PBG-IDE-391.md)
- **Appelle**: 4 programmes | **Tables**: 7 (W:7 R:3 L:0) | **Taches**: 14 | **Expressions**: 10

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 14)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 80.2 | 80.2 | Saisie Date Fin | MDI | 413 | 86 | Saisie |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t3"></a>80.2 - Saisie Date Fin
**Tache** : [80.2](#t3) | **Type** : MDI | **Dimensions** : 413 x 86 DLU
**Bloc** : Saisie | **Titre IDE** : Saisie Date Fin

<!-- FORM-DATA:
{
    "width":  413,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  137,
                         "type":  "label",
                         "var":  "",
                         "y":  14,
                         "w":  266,
                         "fmt":  "",
                         "name":  "",
                         "h":  29,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  145,
                         "type":  "label",
                         "var":  "",
                         "y":  23,
                         "w":  91,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Date fin",
                         "parent":  2
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  60,
                         "w":  409,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  368,
                         "type":  "button",
                         "var":  "",
                         "y":  23,
                         "w":  27,
                         "fmt":  "...",
                         "name":  "Btn date",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  240,
                         "type":  "edit",
                         "var":  "",
                         "y":  23,
                         "w":  126,
                         "fmt":  "",
                         "name":  "W1-Date Fin",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  2
                     },
                     {
                         "x":  2,
                         "type":  "image",
                         "var":  "",
                         "y":  3,
                         "w":  144,
                         "fmt":  "",
                         "name":  "",
                         "h":  53,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  5,
                         "type":  "button",
                         "var":  "",
                         "y":  63,
                         "w":  154,
                         "fmt":  "\u0026Ok",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  166,
                         "type":  "button",
                         "var":  "",
                         "y":  63,
                         "w":  154,
                         "fmt":  "A\u0026bandonner",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "80.2",
    "height":  86
}
-->

<details>
<summary><strong>Champs : 1 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 240,23 | W1-Date Fin | - | edit |

</details>

<details>
<summary><strong>Boutons : 3 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| ... | 368,23 | Bouton fonctionnel |
| Ok | 5,63 | Valide la saisie et enregistre |
| Abandonner | 166,63 | Annule et retour au menu |

</details>

## 9. NAVIGATION

Ecran unique: **Saisie Date Fin**

### 9.3 Structure hierarchique (14 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **80.1** | [**Interruption Client** (80)](#t1) [mockup](#ecran-t1) | MDI | 132x48 | Traitement |
| 80.1.1 | [Recuperation Periode (80.1)](#t2) | MDI | - | |
| 80.1.2 | [Confirmation Interruption (80.4)](#t5) [mockup](#ecran-t5) | MDI | 132x32 | |
| 80.1.3 | [Interruption Batch (80.5)](#t6) [mockup](#ecran-t6) | Modal | 132x32 | |
| 80.1.4 | [Modification Hebergement (80.5.1)](#t7) | MDI | - | |
| 80.1.5 | [Modification Package (80.5.2)](#t8) | MDI | - | |
| 80.1.6 | [Modification Sejour (80.5.3)](#t9) | MDI | - | |
| 80.1.7 | [Modification Sejour (80.5.4)](#t10) | MDI | - | |
| **80.2** | [**Saisie Date Fin** (80.2)](#t3) [mockup](#ecran-t3) | MDI | 413x86 | Saisie |
| **80.3** | [**Creation Groupe V/V** (80.3)](#t4) | MDI | - | Creation |
| 80.3.1 | [Creation Historique (80.5.8)](#t14) | MDI | - | |
| **80.4** | [**Verification Compte** (80.5.5)](#t11) | MDI | - | Validation |
| 80.4.1 | [Modification Validation (80.5.7)](#t13) | MDI | - | |
| **80.5** | [**Modification Compte** (80.5.6)](#t12) | MDI | - | Calcul |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Saisie Date Fin]
    UPDATE[MAJ 7 tables]
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

### Tables utilisees (7)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 30 | gm-recherche_____gmr | Index de recherche | DB | R | **W** |   | 2 |
| 34 | hebergement______heb | Hebergement (chambres) | DB | R | **W** |   | 3 |
| 36 | client_gm |  | DB | R | **W** |   | 2 |
| 47 | compte_gm________cgm | Comptes GM (generaux) | DB |   | **W** |   | 1 |
| 88 | historik_station | Historique / journal | DB |   | **W** |   | 1 |
| 131 | fichier_validation |  | DB |   | **W** |   | 1 |
| 134 | groupe_arr_dep___vol |  | DB |   | **W** |   | 1 |

### Colonnes par table (2 / 7 tables avec colonnes identifiees)

<details>
<summary>Table 30 - gm-recherche_____gmr (R/**W**) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 34 - hebergement______heb (R/**W**) - 3 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 36 - client_gm (R/**W**) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | W1-Date Compte | W | Date |
| B | W1-Code Retour | W | Numeric |
| C | W1-Date Voyage | W | Date |
| D | W1-Heure Voyage | W | Alpha |
| E | W1-Fin de Sejour | W | Date |
| F | V.Sejour valide | W | Alpha |

</details>

<details>
<summary>Table 47 - compte_gm________cgm (**W**) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | W1-Date Compte | W | Date |

</details>

<details>
<summary>Table 88 - historik_station (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 131 - fichier_validation (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 134 - groupe_arr_dep___vol (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Variables de travail (1)

Variables internes au programme.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| L | W0 libelle transport | Alpha | - |

### 11.2 Autres (12)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | W0-Qualite | Alpha | - |
| B | W0-Complement | Alpha | - |
| C | W0-Date Debut | Date | - |
| D | W0-Heure Debut | Alpha | 1x refs |
| E | W0-Date Prevue | Date | - |
| F | W0-Heure Prevue | Alpha | 1x refs |
| G | W0-Date Fin | Date | - |
| H | W0-Heure Fin | Alpha | 1x refs |
| I | W0-Code Vol | Alpha | - |
| J | W0-Transport | Alpha | - |
| K | W0-Ville | Alpha | - |
| M | W0-Accord Suite | Alpha | 2x refs |

## 12. EXPRESSIONS

**10 / 10 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONDITION | 5 | 3 |
| CONSTANTE | 2 | 0 |
| OTHER | 3 | 0 |

### 12.2 Expressions cles par type

#### CONDITION (5 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 10 | `IF (W0-Heure Fin [H]='','U3','U2h')` | [RM-003](#rm-RM-003) |
| CONDITION | 9 | `IF (W0-Heure Prevue [F]='','U3','U2h')` | [RM-002](#rm-RM-002) |
| CONDITION | 8 | `IF (W0-Heure Debut [D]='','U3','U2h')` | [RM-001](#rm-RM-001) |
| CONDITION | 7 | `W0-Accord Suite [M]='E'` | - |
| CONDITION | 6 | `W0-Accord Suite [M]='O'` | - |

#### CONSTANTE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 5 | `''` | - |
| CONSTANTE | 4 | `'R'` | - |

#### OTHER (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 3 | `GetParam ('LANGUE')` | - |
| OTHER | 2 | `GetParam ('SOCIETE')` | - |
| OTHER | 1 | `GetParam ('NRO_CPTE')` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Module Sejours CallTask (IDE 0)](PBG-IDE-0.md) -> **Interruption Client (IDE 80)**

Main -> ... -> [Module Sejours CallTask (IDE 94)](PBG-IDE-94.md) -> **Interruption Client (IDE 80)**

Main -> ... -> [Module Sejours SubForm (IDE 391)](PBG-IDE-391.md) -> **Interruption Client (IDE 80)**

```mermaid
graph LR
    T80[80 Interruption Client]
    style T80 fill:#58a6ff
    CC391[391 Module Sejours Sub...]
    style CC391 fill:#8b5cf6
    CC94[94 Module Sejours Call...]
    style CC94 fill:#8b5cf6
    CC94 --> T80
    CC391 --> T80
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [0](PBG-IDE-0.md) | Module Sejours CallTask | 1 |
| [94](PBG-IDE-94.md) | Module Sejours CallTask | 1 |
| [391](PBG-IDE-391.md) | Module Sejours SubForm | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T80[80 Interruption Client]
    style T80 fill:#58a6ff
    C65[65 Maj effect_personne...]
    T80 --> C65
    style C65 fill:#3fb950
    C176[176 Demarquage Caisse]
    T80 --> C176
    style C176 fill:#3fb950
    C338[338 Date fin effectift...]
    T80 --> C338
    style C338 fill:#3fb950
    C363[363 Zoom Selection Cod...]
    T80 --> C363
    style C363 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [65](PBG-IDE-65.md) | Maj effect_personnes_modif_sej | 1 | Mise a jour donnees |
| [176](PBG-IDE-176.md) | Demarquage Caisse | 1 | Sous-programme |
| [338](PBG-IDE-338.md) | Date fin effectif/t transfert | 1 | Transfert donnees |
| [363](PBG-IDE-363.md) | Zoom Selection Code-Vol | 1 | Selection/consultation |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 249 | Taille moyenne |
| Expressions | 10 | Peu de logique |
| Tables WRITE | 7 | Fort impact donnees |
| Sous-programmes | 4 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 249) | Code sain |
| Regles metier | 3 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (8 taches: 3 ecrans, 5 traitements)

- **Strategie** : Orchestrateur avec 3 ecrans (Razor/React) et 5 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 4 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Saisie (1 tache: 1 ecran, 0 traitement)

- **Strategie** : Formulaire React/Blazor avec validation Zod/FluentValidation.
- Reproduire 1 ecran : Saisie Date Fin
- Validation temps reel cote client + serveur

#### Creation (2 taches: 0 ecran, 2 traitements)

- **Strategie** : Repository pattern avec Entity Framework Core.
- Insertion via `IRepository<T>.CreateAsync()`

#### Validation (2 taches: 0 ecran, 2 traitements)

- **Strategie** : FluentValidation avec validators specifiques.
- Chaque tache de validation -> un validator injectable

#### Calcul (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Services de calcul purs (Domain Services).
- Migrer la logique de calcul (stock, compteurs, montants)

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| gm-recherche_____gmr | Table WRITE (Database) | 1x | Schema + repository |
| hebergement______heb | Table WRITE (Database) | 2x | Schema + repository |
| client_gm | Table WRITE (Database) | 1x | Schema + repository |
| compte_gm________cgm | Table WRITE (Database) | 1x | Schema + repository |
| historik_station | Table WRITE (Database) | 1x | Schema + repository |
| fichier_validation | Table WRITE (Database) | 1x | Schema + repository |
| groupe_arr_dep___vol | Table WRITE (Database) | 1x | Schema + repository |
| [Date fin effectif/t transfert (IDE 338)](PBG-IDE-338.md) | Sous-programme | 1x | Normale - Transfert donnees |
| [Zoom Selection Code-Vol (IDE 363)](PBG-IDE-363.md) | Sous-programme | 1x | Normale - Selection/consultation |
| [Maj effect_personnes_modif_sej (IDE 65)](PBG-IDE-65.md) | Sous-programme | 1x | Normale - Mise a jour donnees |
| [Demarquage Caisse (IDE 176)](PBG-IDE-176.md) | Sous-programme | 1x | Normale - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 09:12*
