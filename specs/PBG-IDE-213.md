# PBG IDE 213 - Traitement des Voyages

> **Analyse**: Phases 1-4 2026-02-03 10:14 -> 10:15 (20s) | Assemblage 10:15
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBG |
| IDE Position | 213 |
| Nom Programme | Traitement des Voyages |
| Fichier source | `Prg_213.xml` |
| Domaine metier | General |
| Taches | 28 (1 ecrans visibles) |
| Tables modifiees | 3 |
| Programmes appeles | 1 |

## 2. DESCRIPTION FONCTIONNELLE

**Traitement des Voyages** assure la gestion complete de ce processus, accessible depuis [Traitement des arrivants (IDE 206)](PBG-IDE-206.md).

Le flux de traitement s'organise en **3 blocs fonctionnels** :

- **Creation** (13 taches) : insertion d'enregistrements en base (mouvements, prestations)
- **Validation** (12 taches) : controles et verifications de coherence
- **Traitement** (3 taches) : traitements metier divers

**Donnees modifiees** : 3 tables en ecriture (hebergement______heb, groupe_arr_dep___vol, commentaire______com).

**Logique metier** : 2 regles identifiees couvrant conditions metier.

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (3 taches)

- **213** - Veuillez patienter... **[[ECRAN]](#ecran-t1)**
- **213.1** - Lecture Heure Diff
- **213.11.3** - Veuillez patienter... **[[ECRAN]](#ecran-t33)**

#### Phase 2 : Validation (12 taches)

- **213.2** - Verification Code-Vol Aller
- **213.3** - Verification Voyage Aller
- **213.4** - Verification Code-Vol Aller
- **213.5** - Verification Voyage Aller
- **213.6** - Verification Code-Vol Retour
- **213.7** - Verification Voyage Retour
- **213.8** - Verification Code-Vol Retour
- **213.9** - Verification Voyage Retour
- **213.10** - Verification V/V Aller
- **213.11** - Verification V/V Aller
- **213.12** - Verification V/V Retour
- **213.13** - Verification V/V Retour

#### Phase 3 : Creation (13 taches)

- **213.3.1** - Creation Package Aller
- **213.3.2** - Creation Package Retour
- **213.5.1** - Creation Package Aller
- **213.5.2** - Creation Package Retour
- **213.7.1** - Creation Package Retour
- **213.7.2** - Creation Package Retour
- **213.9.1** - Creation Package Retour
- **213.9.2** - Creation Package Retour
- **213.11.1** - Creation Package Aller
- **213.11.2** - Creation Package Aller
- **213.11.3.1** - Creation Circuit
- **213.13.1** - Creation Package Retour
- **213.13.2** - Creation Package Retour

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| hebergement______heb | **W** (18 usages) | Hebergement (chambres) |
| groupe_arr_dep___vol | **W**/L (11 usages) |  |
| commentaire______com | **W** (1 usages) |  |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (3 taches)

Traitements internes.

---

#### <a id="t1"></a>213 - Veuillez patienter... [[ECRAN]](#ecran-t1)

**Role** : Traitement : Veuillez patienter....
**Ecran** : 427 x 68 DLU (MDI) | [Voir mockup](#ecran-t1)

---

#### <a id="t2"></a>213.1 - Lecture Heure Diff

**Role** : Traitement : Lecture Heure Diff.
**Variables liees** : M (W0 Heure Diff Aller), N (W0 Heure Diff Retour), K (W0-Code Aller Diff), L (W0-Code Retour Diff)

---

#### <a id="t33"></a>213.11.3 - Veuillez patienter... [[ECRAN]](#ecran-t33)

**Role** : Traitement : Veuillez patienter....
**Ecran** : 424 x 66 DLU (MDI) | [Voir mockup](#ecran-t33)


### 3.2 Validation (12 taches)

Controles de coherence : 12 taches verifient les donnees et conditions.

---

#### <a id="t3"></a>213.2 - Verification Code-Vol Aller

**Role** : Verification : Verification Code-Vol Aller.
**Variables liees** : M (W0 Heure Diff Aller), O (W0 VV Aller ?), I (W0-Code Aller), K (W0-Code Aller Diff)

---

#### <a id="t4"></a>213.3 - Verification Voyage Aller

**Role** : Verification : Verification Voyage Aller.
**Variables liees** : M (W0 Heure Diff Aller), O (W0 VV Aller ?), I (W0-Code Aller), K (W0-Code Aller Diff)

---

#### <a id="t7"></a>213.4 - Verification Code-Vol Aller

**Role** : Verification : Verification Code-Vol Aller.
**Variables liees** : M (W0 Heure Diff Aller), O (W0 VV Aller ?), I (W0-Code Aller), K (W0-Code Aller Diff)

---

#### <a id="t8"></a>213.5 - Verification Voyage Aller

**Role** : Verification : Verification Voyage Aller.
**Variables liees** : M (W0 Heure Diff Aller), O (W0 VV Aller ?), I (W0-Code Aller), K (W0-Code Aller Diff)

---

#### <a id="t11"></a>213.6 - Verification Code-Vol Retour

**Role** : Verification : Verification Code-Vol Retour.
**Variables liees** : N (W0 Heure Diff Retour), P (W0 VV Retour ?), J (W0-Code Retour), L (W0-Code Retour Diff)

---

#### <a id="t12"></a>213.7 - Verification Voyage Retour

**Role** : Verification : Verification Voyage Retour.
**Variables liees** : N (W0 Heure Diff Retour), P (W0 VV Retour ?), J (W0-Code Retour), L (W0-Code Retour Diff)

---

#### <a id="t15"></a>213.8 - Verification Code-Vol Retour

**Role** : Verification : Verification Code-Vol Retour.
**Variables liees** : N (W0 Heure Diff Retour), P (W0 VV Retour ?), J (W0-Code Retour), L (W0-Code Retour Diff)

---

#### <a id="t16"></a>213.9 - Verification Voyage Retour

**Role** : Verification : Verification Voyage Retour.
**Variables liees** : N (W0 Heure Diff Retour), P (W0 VV Retour ?), J (W0-Code Retour), L (W0-Code Retour Diff)

---

#### <a id="t29"></a>213.10 - Verification V/V Aller

**Role** : Verification : Verification V/V Aller.
**Variables liees** : M (W0 Heure Diff Aller), O (W0 VV Aller ?), I (W0-Code Aller), K (W0-Code Aller Diff)

---

#### <a id="t30"></a>213.11 - Verification V/V Aller

**Role** : Verification : Verification V/V Aller.
**Variables liees** : M (W0 Heure Diff Aller), O (W0 VV Aller ?), I (W0-Code Aller), K (W0-Code Aller Diff)

---

#### <a id="t35"></a>213.12 - Verification V/V Retour

**Role** : Verification : Verification V/V Retour.
**Variables liees** : N (W0 Heure Diff Retour), P (W0 VV Retour ?), J (W0-Code Retour), L (W0-Code Retour Diff)

---

#### <a id="t36"></a>213.13 - Verification V/V Retour

**Role** : Verification : Verification V/V Retour.
**Variables liees** : N (W0 Heure Diff Retour), P (W0 VV Retour ?), J (W0-Code Retour), L (W0-Code Retour Diff)


### 3.3 Creation (13 taches)

Insertion de nouveaux enregistrements en base.

---

#### <a id="t5"></a>213.3.1 - Creation Package Aller

**Role** : Creation d'enregistrement : Creation Package Aller.
**Variables liees** : M (W0 Heure Diff Aller), O (W0 VV Aller ?), I (W0-Code Aller), K (W0-Code Aller Diff)

---

#### <a id="t6"></a>213.3.2 - Creation Package Retour

**Role** : Creation d'enregistrement : Creation Package Retour.
**Variables liees** : N (W0 Heure Diff Retour), P (W0 VV Retour ?), J (W0-Code Retour), L (W0-Code Retour Diff)

---

#### <a id="t9"></a>213.5.1 - Creation Package Aller

**Role** : Creation d'enregistrement : Creation Package Aller.
**Variables liees** : M (W0 Heure Diff Aller), O (W0 VV Aller ?), I (W0-Code Aller), K (W0-Code Aller Diff)

---

#### <a id="t10"></a>213.5.2 - Creation Package Retour

**Role** : Creation d'enregistrement : Creation Package Retour.
**Variables liees** : N (W0 Heure Diff Retour), P (W0 VV Retour ?), J (W0-Code Retour), L (W0-Code Retour Diff)

---

#### <a id="t13"></a>213.7.1 - Creation Package Retour

**Role** : Creation d'enregistrement : Creation Package Retour.
**Variables liees** : N (W0 Heure Diff Retour), P (W0 VV Retour ?), J (W0-Code Retour), L (W0-Code Retour Diff)

---

#### <a id="t14"></a>213.7.2 - Creation Package Retour

**Role** : Creation d'enregistrement : Creation Package Retour.
**Variables liees** : N (W0 Heure Diff Retour), P (W0 VV Retour ?), J (W0-Code Retour), L (W0-Code Retour Diff)

---

#### <a id="t17"></a>213.9.1 - Creation Package Retour

**Role** : Creation d'enregistrement : Creation Package Retour.
**Variables liees** : N (W0 Heure Diff Retour), P (W0 VV Retour ?), J (W0-Code Retour), L (W0-Code Retour Diff)

---

#### <a id="t18"></a>213.9.2 - Creation Package Retour

**Role** : Creation d'enregistrement : Creation Package Retour.
**Variables liees** : N (W0 Heure Diff Retour), P (W0 VV Retour ?), J (W0-Code Retour), L (W0-Code Retour Diff)

---

#### <a id="t31"></a>213.11.1 - Creation Package Aller

**Role** : Creation d'enregistrement : Creation Package Aller.
**Variables liees** : M (W0 Heure Diff Aller), O (W0 VV Aller ?), I (W0-Code Aller), K (W0-Code Aller Diff)

---

#### <a id="t32"></a>213.11.2 - Creation Package Aller

**Role** : Creation d'enregistrement : Creation Package Aller.
**Variables liees** : M (W0 Heure Diff Aller), O (W0 VV Aller ?), I (W0-Code Aller), K (W0-Code Aller Diff)

---

#### <a id="t34"></a>213.11.3.1 - Creation Circuit

**Role** : Creation d'enregistrement : Creation Circuit.

---

#### <a id="t37"></a>213.13.1 - Creation Package Retour

**Role** : Creation d'enregistrement : Creation Package Retour.
**Variables liees** : N (W0 Heure Diff Retour), P (W0 VV Retour ?), J (W0-Code Retour), L (W0-Code Retour Diff)

---

#### <a id="t38"></a>213.13.2 - Creation Package Retour

**Role** : Creation d'enregistrement : Creation Package Retour.
**Variables liees** : N (W0 Heure Diff Retour), P (W0 VV Retour ?), J (W0-Code Retour), L (W0-Code Retour Diff)


## 5. REGLES METIER

2 regles identifiees:

### Autres (2 regles)

#### <a id="rm-RM-001"></a>[RM-001] Si W0-Code Aller [I]=0 OR W0-Code Aller [I]<>0 AND W0-Code Aller Diff [K]=0 AND W0 Heure Diff Aller [M]<>0 AND Hour ([AR])>W0 Heure Diff Aller [M] alors 'N' sinon 'O')

| Element | Detail |
|---------|--------|
| **Condition** | `W0-Code Aller [I]=0 OR W0-Code Aller [I]<>0 AND W0-Code Aller Diff [K]=0 AND W0 Heure Diff Aller [M]<>0 AND Hour ([AR])>W0 Heure Diff Aller [M]` |
| **Si vrai** | 'N' |
| **Si faux** | 'O') |
| **Variables** | M (W0 Heure Diff Aller), I (W0-Code Aller), K (W0-Code Aller Diff) |
| **Expression source** | Expression 21 : `IF (W0-Code Aller [I]=0 OR W0-Code Aller [I]<>0 AND W0-Code ` |
| **Exemple** | Si W0-Code Aller [I]=0 OR W0-Code Aller [I]<>0 AND W0-Code Aller Diff [K]=0 AND W0 Heure Diff Aller [M]<>0 AND Hour ([AR])>W0 Heure Diff Aller [M] â†’ 'N'. Sinon â†’ 'O') |

#### <a id="rm-RM-002"></a>[RM-002] Si W0-Code Retour [J]=0 OR W0-Code Retour [J]<>0 AND W0-Code Retour Diff [L]=0 AND W0 Heure Diff Retour [N]<>0 AND Hour ([BN])<W0 Heure Diff Retour [N] alors 'N' sinon 'O')

| Element | Detail |
|---------|--------|
| **Condition** | `W0-Code Retour [J]=0 OR W0-Code Retour [J]<>0 AND W0-Code Retour Diff [L]=0 AND W0 Heure Diff Retour [N]<>0 AND Hour ([BN])<W0 Heure Diff Retour [N]` |
| **Si vrai** | 'N' |
| **Si faux** | 'O') |
| **Variables** | N (W0 Heure Diff Retour), J (W0-Code Retour), L (W0-Code Retour Diff) |
| **Expression source** | Expression 22 : `IF (W0-Code Retour [J]=0 OR W0-Code Retour [J]<>0 AND W0-Cod` |
| **Exemple** | Si W0-Code Retour [J]=0 OR W0-Code Retour [J]<>0 AND W0-Code Retour Diff [L]=0 AND W0 Heure Diff Retour [N]<>0 AND Hour ([BN])<W0 Heure Diff Retour [N] â†’ 'N'. Sinon â†’ 'O') |

## 6. CONTEXTE

- **Appele par**: [Traitement des arrivants (IDE 206)](PBG-IDE-206.md)
- **Appelle**: 1 programmes | **Tables**: 7 (W:3 R:3 L:3) | **Taches**: 28 | **Expressions**: 37

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 28)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 213 | 213 | Veuillez patienter... | MDI | 427 | 68 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>213 - Veuillez patienter...
**Tache** : [213](#t1) | **Type** : MDI | **Dimensions** : 427 x 68 DLU
**Bloc** : Traitement | **Titre IDE** : Veuillez patienter...

<!-- FORM-DATA:
{
    "width":  427,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  1,
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
                         "x":  99,
                         "type":  "label",
                         "var":  "",
                         "y":  10,
                         "w":  275,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "7",
                         "text":  "Traitement des Voyages",
                         "parent":  null
                     },
                     {
                         "x":  1,
                         "type":  "label",
                         "var":  "",
                         "y":  29,
                         "w":  423,
                         "fmt":  "",
                         "name":  "",
                         "h":  37,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  9,
                         "type":  "label",
                         "var":  "",
                         "y":  41,
                         "w":  405,
                         "fmt":  "",
                         "name":  "",
                         "h":  19,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  2,
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
                         "x":  12,
                         "type":  "edit",
                         "var":  "",
                         "y":  42,
                         "w":  400,
                         "fmt":  "30",
                         "name":  "",
                         "h":  17,
                         "color":  "159",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  177,
                         "type":  "edit",
                         "var":  "",
                         "y":  46,
                         "w":  64,
                         "fmt":  "3 %",
                         "name":  "",
                         "h":  8,
                         "color":  "143",
                         "text":  "",
                         "parent":  1
                     }
                 ],
    "taskId":  "213",
    "height":  68
}
-->

<details>
<summary><strong>Champs : 2 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 12,42 | 30 | - | edit |
| 177,46 | 3 % | - | edit |

</details>

## 9. NAVIGATION

Ecran unique: **Veuillez patienter...**

### 9.3 Structure hierarchique (28 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **213.1** | [**Veuillez patienter...** (213)](#t1) [mockup](#ecran-t1) | MDI | 427x68 | Traitement |
| 213.1.1 | [Lecture Heure Diff (213.1)](#t2) | MDI | - | |
| 213.1.2 | [Veuillez patienter... (213.11.3)](#t33) [mockup](#ecran-t33) | MDI | 424x66 | |
| **213.2** | [**Verification Code-Vol Aller** (213.2)](#t3) | MDI | - | Validation |
| 213.2.1 | [Verification Voyage Aller (213.3)](#t4) | MDI | - | |
| 213.2.2 | [Verification Code-Vol Aller (213.4)](#t7) | MDI | - | |
| 213.2.3 | [Verification Voyage Aller (213.5)](#t8) | MDI | - | |
| 213.2.4 | [Verification Code-Vol Retour (213.6)](#t11) | MDI | - | |
| 213.2.5 | [Verification Voyage Retour (213.7)](#t12) | MDI | - | |
| 213.2.6 | [Verification Code-Vol Retour (213.8)](#t15) | MDI | - | |
| 213.2.7 | [Verification Voyage Retour (213.9)](#t16) | MDI | - | |
| 213.2.8 | [Verification V/V Aller (213.10)](#t29) | MDI | - | |
| 213.2.9 | [Verification V/V Aller (213.11)](#t30) | MDI | - | |
| 213.2.10 | [Verification V/V Retour (213.12)](#t35) | MDI | - | |
| 213.2.11 | [Verification V/V Retour (213.13)](#t36) | MDI | - | |
| **213.3** | [**Creation Package Aller** (213.3.1)](#t5) | MDI | - | Creation |
| 213.3.1 | [Creation Package Retour (213.3.2)](#t6) | MDI | - | |
| 213.3.2 | [Creation Package Aller (213.5.1)](#t9) | MDI | - | |
| 213.3.3 | [Creation Package Retour (213.5.2)](#t10) | MDI | - | |
| 213.3.4 | [Creation Package Retour (213.7.1)](#t13) | MDI | - | |
| 213.3.5 | [Creation Package Retour (213.7.2)](#t14) | MDI | - | |
| 213.3.6 | [Creation Package Retour (213.9.1)](#t17) | MDI | - | |
| 213.3.7 | [Creation Package Retour (213.9.2)](#t18) | MDI | - | |
| 213.3.8 | [Creation Package Aller (213.11.1)](#t31) | MDI | - | |
| 213.3.9 | [Creation Package Aller (213.11.2)](#t32) | MDI | - | |
| 213.3.10 | [Creation Circuit (213.11.3.1)](#t34) | MDI | - | |
| 213.3.11 | [Creation Package Retour (213.13.1)](#t37) | MDI | - | |
| 213.3.12 | [Creation Package Retour (213.13.2)](#t38) | MDI | - | |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Traitement principal]
    UPDATE[MAJ 3 tables]
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
| 34 | hebergement______heb | Hebergement (chambres) | DB |   | **W** |   | 18 |
| 112 | tables_paris |  | DB |   |   | L | 1 |
| 113 | tables_village |  | DB | R |   |   | 1 |
| 134 | groupe_arr_dep___vol |  | DB |   | **W** | L | 11 |
| 171 | commentaire______com |  | DB |   | **W** |   | 1 |
| 569 | pointage_articles_caution | Articles et stock | TMP | R |   |   | 1 |
| 576 | temp_recap_sessions | Sessions de caisse | TMP | R |   | L | 2 |

### Colonnes par table (2 / 6 tables avec colonnes identifiees)

<details>
<summary>Table 34 - hebergement______heb (**W**) - 18 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | W1-Hebergement ? | W | Numeric |
| B | W1-Circuit avant ? | W | Numeric |

</details>

<details>
<summary>Table 113 - tables_village (R) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 134 - groupe_arr_dep___vol (**W**/L) - 11 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 171 - commentaire______com (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 569 - pointage_articles_caution (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P0-Code Societe | R | Alpha |
| B | P0-Code Langue | R | Alpha |
| C | P0-Lieu de Sejour | R | Alpha |
| D | P0-Nb Arrivants | R | Numeric |
| E | W0-Operande | R | Numeric |
| F | W0-Operateur | R | Numeric |
| G | W0-Pourcentage | R | Numeric |
| H | W0-Calcul Pourcent | R | Numeric |
| I | W0-Code Aller | R | Numeric |
| J | W0-Code Retour | R | Numeric |
| K | W0-Code Aller Diff | R | Numeric |
| L | W0-Code Retour Diff | R | Numeric |
| M | W0 Heure Diff Aller | R | Numeric |
| N | W0 Heure Diff Retour | R | Numeric |
| O | W0 VV Aller ? | R | Alpha |
| P | W0 VV Retour ? | R | Alpha |
| Q | V.Compteur | R | Numeric |

</details>

<details>
<summary>Table 576 - temp_recap_sessions (R/L) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Variables de session (1)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| Q | V.Compteur | Numeric | - |

### 11.2 Variables de travail (4)

Variables internes au programme.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| M | W0 Heure Diff Aller | Numeric | [213.1](#t2), [213.2](#t3), [213.3](#t4) |
| N | W0 Heure Diff Retour | Numeric | [213.1](#t2), [213.3.2](#t6), [213.5.2](#t10) |
| O | W0 VV Aller ? | Alpha | [213.2](#t3), [213.3](#t4), [213.3.1](#t5) |
| P | W0 VV Retour ? | Alpha | [213.3.2](#t6), [213.5.2](#t10), [213.6](#t11) |

### 11.3 Autres (12)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P0-Code Societe | Alpha | - |
| B | P0-Code Langue | Alpha | 1x refs |
| C | P0-Lieu de Sejour | Alpha | - |
| D | P0-Nb Arrivants | Numeric | 2x refs |
| E | W0-Operande | Numeric | - |
| F | W0-Operateur | Numeric | 2x refs |
| G | W0-Pourcentage | Numeric | - |
| H | W0-Calcul Pourcent | Numeric | 1x refs |
| I | W0-Code Aller | Numeric | [213.2](#t3), [213.3](#t4), [213.3.1](#t5) |
| J | W0-Code Retour | Numeric | [213.3.2](#t6), [213.5.2](#t10), [213.6](#t11) |
| K | W0-Code Aller Diff | Numeric | [213.1](#t2), [213.2](#t3), [213.3](#t4) |
| L | W0-Code Retour Diff | Numeric | [213.1](#t2), [213.3.2](#t6), [213.5.2](#t10) |

<details>
<summary>Toutes les 17 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| W0 | **M** | W0 Heure Diff Aller | Numeric |
| W0 | **N** | W0 Heure Diff Retour | Numeric |
| W0 | **O** | W0 VV Aller ? | Alpha |
| W0 | **P** | W0 VV Retour ? | Alpha |
| V. | **Q** | V.Compteur | Numeric |
| Autre | **A** | P0-Code Societe | Alpha |
| Autre | **B** | P0-Code Langue | Alpha |
| Autre | **C** | P0-Lieu de Sejour | Alpha |
| Autre | **D** | P0-Nb Arrivants | Numeric |
| Autre | **E** | W0-Operande | Numeric |
| Autre | **F** | W0-Operateur | Numeric |
| Autre | **G** | W0-Pourcentage | Numeric |
| Autre | **H** | W0-Calcul Pourcent | Numeric |
| Autre | **I** | W0-Code Aller | Numeric |
| Autre | **J** | W0-Code Retour | Numeric |
| Autre | **K** | W0-Code Aller Diff | Numeric |
| Autre | **L** | W0-Code Retour Diff | Numeric |

</details>

## 12. EXPRESSIONS

**37 / 37 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCULATION | 9 | 0 |
| CONDITION | 14 | 2 |
| CONSTANTE | 5 | 0 |
| OTHER | 8 | 0 |
| REFERENCE_VG | 1 | 0 |

### 12.2 Expressions cles par type

#### CALCULATION (9 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 20 | `[AA]+1` | - |
| CALCULATION | 18 | `[Z]-1` | - |
| CALCULATION | 36 | `[EQ]+1` | - |
| CALCULATION | 35 | `W0-Operateur [F]+1` | - |
| CALCULATION | 15 | `W0-Operateur [F]/W0-Calcul Pourcent [H]` | - |
| ... | | *+4 autres* | |

#### CONDITION (14 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 22 | `IF (W0-Code Retour [J]=0 OR W0-Code Retour [J]<>0 AND W0-Code Retour Diff [L]=0 AND W0 Heure Diff Retour [N]<>0 AND Hour ([BN])<W0 Heure Diff Retour [N],'N','O')` | [RM-002](#rm-RM-002) |
| CONDITION | 21 | `IF (W0-Code Aller [I]=0 OR W0-Code Aller [I]<>0 AND W0-Code Aller Diff [K]=0 AND W0 Heure Diff Aller [M]<>0 AND Hour ([AR])>W0 Heure Diff Aller [M],'N','O')` | [RM-001](#rm-RM-001) |
| CONDITION | 31 | `W0 VV Aller ? [O]='O' AND [Z]<>0` | - |
| CONDITION | 30 | `W0-Code Retour [J]<>0 AND W0-Code Retour Diff [L]=0 AND W0 Heure Diff Retour [N]<>0 AND Hour ([BN])<W0 Heure Diff Retour [N]` | - |
| CONDITION | 29 | `W0-Code Retour [J]<>0 AND [Z]<>0 AND W0-Code Retour Diff [L]=0 AND W0 Heure Diff Retour [N]<>0 AND Hour ([BN])<W0 Heure Diff Retour [N]` | - |
| ... | | *+9 autres* | |

#### CONSTANTE (5 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 12 | `'I'` | - |
| CONSTANTE | 37 | `1` | - |
| CONSTANTE | 11 | `'F'` | - |
| CONSTANTE | 1 | `''` | - |
| CONSTANTE | 4 | `'TTRAN'` | - |

#### OTHER (8 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 16 | `[S]` | - |
| OTHER | 9 | `[BO]` | - |
| OTHER | 19 | `[AA]` | - |
| OTHER | 17 | `[Z]` | - |
| OTHER | 6 | `[AH]` | - |
| ... | | *+3 autres* | |

#### REFERENCE_VG (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 10 | `VG20` | - |

### 12.3 Toutes les expressions (37)

<details>
<summary>Voir les 37 expressions</summary>

#### CALCULATION (9)

| IDE | Expression Decodee |
|-----|-------------------|
| 2 | `([EQ]/VG1)*100` |
| 3 | `([EQ]/VG1)*50` |
| 13 | `P0-Nb Arrivants [D]/29` |
| 14 | `P0-Nb Arrivants [D]/98` |
| 15 | `W0-Operateur [F]/W0-Calcul Pourcent [H]` |
| 18 | `[Z]-1` |
| 20 | `[AA]+1` |
| 35 | `W0-Operateur [F]+1` |
| 36 | `[EQ]+1` |

#### CONDITION (14)

| IDE | Expression Decodee |
|-----|-------------------|
| 21 | `IF (W0-Code Aller [I]=0 OR W0-Code Aller [I]<>0 AND W0-Code Aller Diff [K]=0 AND W0 Heure Diff Aller [M]<>0 AND Hour ([AR])>W0 Heure Diff Aller [M],'N','O')` |
| 22 | `IF (W0-Code Retour [J]=0 OR W0-Code Retour [J]<>0 AND W0-Code Retour Diff [L]=0 AND W0 Heure Diff Retour [N]<>0 AND Hour ([BN])<W0 Heure Diff Retour [N],'N','O')` |
| 23 | `W0-Code Aller [I]=0 AND [Z]<>0` |
| 24 | `W0-Code Aller [I]<>0 AND [Z]<>0 AND W0-Code Aller Diff [K]=0 AND W0 Heure Diff Aller [M]<>0 AND Hour ([AR])>W0 Heure Diff Aller [M]` |
| 25 | `W0-Code Aller [I]=0` |
| 26 | `W0-Code Aller [I]<>0 AND W0-Code Aller Diff [K]=0 AND W0 Heure Diff Aller [M]<>0 AND Hour ([AR])>W0 Heure Diff Aller [M]` |
| 27 | `W0-Code Retour [J]=0 AND [Z]<>0` |
| 28 | `W0-Code Retour [J]=0` |
| 29 | `W0-Code Retour [J]<>0 AND [Z]<>0 AND W0-Code Retour Diff [L]=0 AND W0 Heure Diff Retour [N]<>0 AND Hour ([BN])<W0 Heure Diff Retour [N]` |
| 30 | `W0-Code Retour [J]<>0 AND W0-Code Retour Diff [L]=0 AND W0 Heure Diff Retour [N]<>0 AND Hour ([BN])<W0 Heure Diff Retour [N]` |
| 31 | `W0 VV Aller ? [O]='O' AND [Z]<>0` |
| 32 | `W0 VV Aller ? [O]='O'` |
| 33 | `W0 VV Retour ? [P]='O' AND [Z]<>0` |
| 34 | `W0 VV Retour ? [P]='O'` |

#### CONSTANTE (5)

| IDE | Expression Decodee |
|-----|-------------------|
| 1 | `''` |
| 4 | `'TTRAN'` |
| 11 | `'F'` |
| 12 | `'I'` |
| 37 | `1` |

#### OTHER (8)

| IDE | Expression Decodee |
|-----|-------------------|
| 5 | `P0-Code Langue [B]` |
| 6 | `[AH]` |
| 7 | `[AS]` |
| 8 | `[BD]` |
| 9 | `[BO]` |
| 16 | `[S]` |
| 17 | `[Z]` |
| 19 | `[AA]` |

#### REFERENCE_VG (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 10 | `VG20` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Traitement des arrivants (IDE 206)](PBG-IDE-206.md) -> **Traitement des Voyages (IDE 213)**

```mermaid
graph LR
    T213[213 Traitement des Voy...]
    style T213 fill:#58a6ff
    CC206[206 Traitement des arr...]
    style CC206 fill:#8b5cf6
    CC206 --> T213
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [206](PBG-IDE-206.md) | Traitement des arrivants | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T213[213 Traitement des Voy...]
    style T213 fill:#58a6ff
    C338[338 Date fin effectift...]
    T213 --> C338
    style C338 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [338](PBG-IDE-338.md) | Date fin effectif/t transfert | 2 | Transfert donnees |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 669 | Programme volumineux |
| Expressions | 37 | Peu de logique |
| Tables WRITE | 3 | Impact modere |
| Sous-programmes | 1 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 669) | Code sain |
| Regles metier | 2 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (3 taches: 2 ecrans, 1 traitement)

- **Strategie** : Orchestrateur avec 2 ecrans (Razor/React) et 1 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 1 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Validation (12 taches: 0 ecran, 12 traitements)

- **Strategie** : FluentValidation avec validators specifiques.
- Chaque tache de validation -> un validator injectable

#### Creation (13 taches: 0 ecran, 13 traitements)

- **Strategie** : Repository pattern avec Entity Framework Core.
- Insertion via `IRepository<T>.CreateAsync()`

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| hebergement______heb | Table WRITE (Database) | 18x | Schema + repository |
| groupe_arr_dep___vol | Table WRITE (Database) | 6x | Schema + repository |
| commentaire______com | Table WRITE (Database) | 1x | Schema + repository |
| [Date fin effectif/t transfert (IDE 338)](PBG-IDE-338.md) | Sous-programme | 2x | Haute - Transfert donnees |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 10:15*
