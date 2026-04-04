# RET IDE 16 - Transfert ODS Boutique

> **Analyse**: Phases 1-4 2026-02-03 20:44 -> 20:44 (20s) | Assemblage 20:44
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | RET |
| IDE Position | 16 |
| Nom Programme | Transfert ODS Boutique |
| Fichier source | `Prg_16.xml` |
| Dossier IDE | Transfert |
| Taches | 16 (2 ecrans visibles) |
| Tables modifiees | 7 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Transfert ODS Boutique** assure la gestion complete de ce processus, accessible depuis [CB menu caisse/boutique (IDE 10)](RET-IDE-10.md).

Le flux de traitement s'organise en **4 blocs fonctionnels** :

- **Traitement** (8 taches) : traitements metier divers
- **Creation** (5 taches) : insertion d'enregistrements en base (mouvements, prestations)
- **Transfert** (2 taches) : transferts de donnees entre modules ou deversements
- **Calcul** (1 tache) : calculs de montants, stocks ou compteurs

**Donnees modifiees** : 7 tables en ecriture (reseau_cloture___rec, gm-complet_______gmc, comptable_gratuite, comptable________cte, intermed__gratuititg, intermed_compta__ite, tai_forfait).

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Transfert (2 taches)

- **16** - Transfert ODS Boutique
- **16.1.1** - CB Transfert ODS boutique **[[ECRAN]](#ecran-t3)**

#### Phase 2 : Traitement (8 taches)

- **16.1** - Please wait ... **[[ECRAN]](#ecran-t2)**
- **16.1.1.1** - Veuillez patienter... **[[ECRAN]](#ecran-t4)**
- **16.2** - prepare boutique file **[[ECRAN]](#ecran-t10)**
- **16.3** - Test si cloture en cours
- **16.3.1** - Blocage cloture
- **16.4** - Deblocage cloture
- **16.3.2** - Blocage cloture
- **16.6** - Deblocage cloture

#### Phase 3 : Creation (5 taches)

- **16.1.1.1.1** - Creation OD boutique
- **16.1.1.1.2** - Creation OD boutique
- **16.1.1.1.3** - Creation d'un O.D
- **16.1.1.1.4** - Creation d'un O.D
- **16.1.1.2** - Create Err

#### Phase 4 : Calcul (1 tache)

- **16.5** - Lecture date comptable

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| reseau_cloture___rec | R/**W** (5 usages) | Donnees reseau/cloture |
| intermed__gratuititg | **W** (1 usages) |  |
| intermed_compta__ite | **W** (1 usages) |  |
| comptable________cte | **W** (1 usages) |  |
| gm-complet_______gmc | **W** (1 usages) |  |
| tai_forfait | **W** (1 usages) |  |
| comptable_gratuite | **W** (1 usages) |  |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Transfert (2 taches)

Transfert de donnees entre modules.

---

#### <a id="t1"></a>16 - Transfert ODS Boutique

**Role** : Transfert de donnees : Transfert ODS Boutique.

---

#### <a id="t3"></a>16.1.1 - CB Transfert ODS boutique [[ECRAN]](#ecran-t3)

**Role** : Transfert de donnees : CB Transfert ODS boutique.
**Ecran** : 80 x 28 DLU (MDI) | [Voir mockup](#ecran-t3)


### 3.2 Traitement (8 taches)

Traitements internes.

---

#### <a id="t2"></a>16.1 - Please wait ... [[ECRAN]](#ecran-t2)

**Role** : Traitement : Please wait ....
**Ecran** : 426 x 56 DLU (MDI) | [Voir mockup](#ecran-t2)

---

#### <a id="t4"></a>16.1.1.1 - Veuillez patienter... [[ECRAN]](#ecran-t4)

**Role** : Traitement : Veuillez patienter....
**Ecran** : 768 x 172 DLU (MDI) | [Voir mockup](#ecran-t4)

---

#### <a id="t10"></a>16.2 - prepare boutique file [[ECRAN]](#ecran-t10)

**Role** : Traitement : prepare boutique file.
**Ecran** : 273 x 58 DLU (MDI) | [Voir mockup](#ecran-t10)

---

#### <a id="t11"></a>16.3 - Test si cloture en cours

**Role** : Verification : Test si cloture en cours.
**Variables liees** : C (v. retour cloture), D (v. operation durant cloture)

---

#### <a id="t12"></a>16.3.1 - Blocage cloture

**Role** : Traitement : Blocage cloture.
**Variables liees** : C (v. retour cloture), D (v. operation durant cloture)

---

#### <a id="t13"></a>16.4 - Deblocage cloture

**Role** : Traitement : Deblocage cloture.
**Variables liees** : C (v. retour cloture), D (v. operation durant cloture)

---

#### <a id="t17"></a>16.3.2 - Blocage cloture

**Role** : Traitement : Blocage cloture.
**Variables liees** : C (v. retour cloture), D (v. operation durant cloture)

---

#### <a id="t20"></a>16.6 - Deblocage cloture

**Role** : Traitement : Deblocage cloture.
**Variables liees** : C (v. retour cloture), D (v. operation durant cloture)


### 3.3 Creation (5 taches)

Insertion de nouveaux enregistrements en base.

---

#### <a id="t5"></a>16.1.1.1.1 - Creation OD boutique

**Role** : Creation d'enregistrement : Creation OD boutique.

---

#### <a id="t6"></a>16.1.1.1.2 - Creation OD boutique

**Role** : Creation d'enregistrement : Creation OD boutique.

---

#### <a id="t7"></a>16.1.1.1.3 - Creation d'un O.D

**Role** : Creation d'enregistrement : Creation d'un O.D.

---

#### <a id="t8"></a>16.1.1.1.4 - Creation d'un O.D

**Role** : Creation d'enregistrement : Creation d'un O.D.

---

#### <a id="t9"></a>16.1.1.2 - Create Err

**Role** : Traitement : Create Err.


### 3.4 Calcul (1 tache)

Calculs metier : montants, stocks, compteurs.

---

#### <a id="t14"></a>16.5 - Lecture date comptable

**Role** : Traitement : Lecture date comptable.
**Variables liees** : A (> W date comptable), K (W1 date depart)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [CB menu caisse/boutique (IDE 10)](RET-IDE-10.md)
- **Appelle**: 0 programmes | **Tables**: 13 (W:7 R:3 L:4) | **Taches**: 16 | **Expressions**: 11

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (2 / 16)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 16.1.1.1 | 16.1.1.1 | Veuillez patienter... | MDI | 768 | 172 | Traitement |
| 2 | 16.2 | 16.2 | prepare boutique file | MDI | 273 | 58 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t4"></a>16.1.1.1 - Veuillez patienter...
**Tache** : [16.1.1.1](#t4) | **Type** : MDI | **Dimensions** : 768 x 172 DLU
**Bloc** : Traitement | **Titre IDE** : Veuillez patienter...

<!-- FORM-DATA:
{
    "width":  768,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  8,
                         "type":  "label",
                         "var":  "",
                         "y":  3,
                         "w":  752,
                         "fmt":  "",
                         "name":  "",
                         "h":  29,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  233,
                         "type":  "label",
                         "var":  "",
                         "y":  13,
                         "w":  302,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "7",
                         "text":  "Mise à jour des ODS...",
                         "parent":  null
                     },
                     {
                         "x":  8,
                         "type":  "label",
                         "var":  "",
                         "y":  32,
                         "w":  752,
                         "fmt":  "",
                         "name":  "",
                         "h":  139,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  62,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "6",
                         "w":  638,
                         "y":  39,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  12,
                         "h":  123,
                         "cols":  [
                                      {
                                          "title":  "",
                                          "layer":  1,
                                          "w":  638
                                      }
                                  ],
                         "rows":  1
                     },
                     {
                         "x":  68,
                         "type":  "label",
                         "var":  "",
                         "y":  41,
                         "w":  345,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "146",
                         "text":  "GMC nom complet",
                         "parent":  5
                     },
                     {
                         "x":  430,
                         "type":  "label",
                         "var":  "",
                         "y":  41,
                         "w":  265,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "146",
                         "text":  "GMC prenom complet",
                         "parent":  5
                     },
                     {
                         "x":  68,
                         "type":  "edit",
                         "var":  "",
                         "y":  53,
                         "w":  344,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "6",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  448,
                         "type":  "edit",
                         "var":  "",
                         "y":  53,
                         "w":  232,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "6",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  14,
                         "type":  "image",
                         "var":  "",
                         "y":  5,
                         "w":  72,
                         "fmt":  "",
                         "name":  "",
                         "h":  25,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "16.1.1.1",
    "height":  172
}
-->

<details>
<summary><strong>Champs : 2 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 68,53 | (sans nom) | - | edit |
| 448,53 | (sans nom) | - | edit |

</details>

---

#### <a id="ecran-t10"></a>16.2 - prepare boutique file
**Tache** : [16.2](#t10) | **Type** : MDI | **Dimensions** : 273 x 58 DLU
**Bloc** : Traitement | **Titre IDE** : prepare boutique file

<!-- FORM-DATA:
{
    "width":  273,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  3,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  268,
                         "fmt":  "",
                         "name":  "",
                         "h":  29,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  84,
                         "type":  "label",
                         "var":  "",
                         "y":  10,
                         "w":  164,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "7",
                         "text":  "Tranfer in progress",
                         "parent":  null
                     },
                     {
                         "x":  3,
                         "type":  "label",
                         "var":  "",
                         "y":  29,
                         "w":  268,
                         "fmt":  "",
                         "name":  "",
                         "h":  27,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  12,
                         "type":  "label",
                         "var":  "",
                         "y":  38,
                         "w":  248,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Transfering boutique ODS",
                         "parent":  null
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
                     }
                 ],
    "taskId":  "16.2",
    "height":  58
}
-->

## 9. NAVIGATION

### 9.1 Enchainement des ecrans

```mermaid
flowchart TD
    START([Entree])
    style START fill:#3fb950
    VF4[16.1.1.1 Veuillez patienter...]
    style VF4 fill:#58a6ff
    VF10[16.2 prepare boutique file]
    style VF10 fill:#58a6ff
    FIN([Sortie])
    style FIN fill:#f85149
    START --> VF4
    VF4 --> FIN
```

**Detail par enchainement :**

| Depuis | Action | Vers | Retour |
|--------|--------|------|--------|

### 9.3 Structure hierarchique (16 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **16.1** | [**Transfert ODS Boutique** (16)](#t1) | MDI | - | Transfert |
| 16.1.1 | [CB Transfert ODS boutique (16.1.1)](#t3) [mockup](#ecran-t3) | MDI | 80x28 | |
| **16.2** | [**Please wait ...** (16.1)](#t2) [mockup](#ecran-t2) | MDI | 426x56 | Traitement |
| 16.2.1 | [Veuillez patienter... (16.1.1.1)](#t4) [mockup](#ecran-t4) | MDI | 768x172 | |
| 16.2.2 | [prepare boutique file (16.2)](#t10) [mockup](#ecran-t10) | MDI | 273x58 | |
| 16.2.3 | [Test si cloture en cours (16.3)](#t11) | MDI | - | |
| 16.2.4 | [Blocage cloture (16.3.1)](#t12) | MDI | - | |
| 16.2.5 | [Deblocage cloture (16.4)](#t13) | MDI | - | |
| 16.2.6 | [Blocage cloture (16.3.2)](#t17) | MDI | - | |
| 16.2.7 | [Deblocage cloture (16.6)](#t20) | MDI | - | |
| **16.3** | [**Creation OD boutique** (16.1.1.1.1)](#t5) | MDI | - | Creation |
| 16.3.1 | [Creation OD boutique (16.1.1.1.2)](#t6) | MDI | - | |
| 16.3.2 | [Creation d'un O.D (16.1.1.1.3)](#t7) | MDI | - | |
| 16.3.3 | [Creation d'un O.D (16.1.1.1.4)](#t8) | MDI | - | |
| 16.3.4 | [Create Err (16.1.1.2)](#t9) | MDI | - | |
| **16.4** | [**Lecture date comptable** (16.5)](#t14) | MDI | - | Calcul |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[rename fichier boutique]
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

### Tables utilisees (13)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 23 | reseau_cloture___rec | Donnees reseau/cloture | DB | R | **W** |   | 5 |
| 31 | gm-complet_______gmc |  | DB |   | **W** |   | 1 |
| 38 | comptable_gratuite |  | DB |   | **W** |   | 1 |
| 40 | comptable________cte |  | DB |   | **W** |   | 1 |
| 47 | compte_gm________cgm | Comptes GM (generaux) | DB |   |   | L | 2 |
| 69 | initialisation___ini |  | DB |   |   | L | 1 |
| 70 | date_comptable___dat |  | DB | R |   |   | 1 |
| 77 | articles_________art | Articles et stock | DB | R |   |   | 1 |
| 79 | gratuites________gra |  | DB |   |   | L | 1 |
| 172 | intermed__gratuititg |  | DB |   | **W** |   | 1 |
| 173 | intermed_compta__ite |  | DB |   | **W** |   | 1 |
| 453 | tai_forfait |  | DB |   | **W** |   | 1 |
| 729 | arc_cc_type_detail |  | DB |   |   | L | 1 |

### Colonnes par table (8 / 9 tables avec colonnes identifiees)

<details>
<summary>Table 23 - reseau_cloture___rec (R/**W**) - 5 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| C | v. retour cloture | W | Logical |
| D | v. operation durant cloture | W | Logical |

</details>

<details>
<summary>Table 31 - gm-complet_______gmc (**W**) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | W2 retour lien GMC | W | Numeric |
| B | W2 ret.lien gratuite | W | Numeric |

</details>

<details>
<summary>Table 38 - comptable_gratuite (**W**) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | > W date comptable | W | Date |
| B | W2 ret.lien gratuite | W | Numeric |

</details>

<details>
<summary>Table 40 - comptable________cte (**W**) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | V.RETOUR 18 | W | Logical |
| B | V.RETOUR 25 | W | Logical |

</details>

<details>
<summary>Table 70 - date_comptable___dat (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | > W date comptable | R | Date |
| E | W1 date jour | R | Date |
| K | W1 date depart | R | Date |

</details>

<details>
<summary>Table 77 - articles_________art (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | > W date comptable | R | Date |
| B | V.sauvedata exist | R | Logical |
| C | v. retour cloture | R | Logical |
| D | v. operation durant cloture | R | Logical |
| E | v.retour rename bout | R | Logical |
| F | v.retour rename golf | R | Logical |

</details>

<details>
<summary>Table 172 - intermed__gratuititg (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 173 - intermed_compta__ite (**W**) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | > W date comptable | W | Date |

</details>

<details>
<summary>Table 453 - tai_forfait (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Variables de session (5)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| B | V.sauvedata exist | Logical | 2x session |
| C | v. retour cloture | Logical | [16.3](#t11), [16.3.1](#t12), [16.4](#t13) |
| D | v. operation durant cloture | Logical | - |
| E | v.retour rename bout | Logical | [16](#t1), [16.1.1](#t3), [16.1.1.1.1](#t5) |
| F | v.retour rename golf | Logical | 1x session |

### 11.2 Autres (11)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | > W date comptable | Date | - |
| G | W1 numero club | Numeric | 2x refs |
| H | W1 lettre controle | Alpha | - |
| I | W1 lettre controle modifiee | Alpha | - |
| J | W1 filiation | Numeric | - |
| K | W1 date depart | Date | - |
| L | W1 paiement | Alpha | - |
| M | W1 annulation | Alpha | - |
| N | W1 lieu | Numeric | - |
| O | W1 retour lien GMC | Numeric | - |
| P | W1 etat compte | Alpha | - |

<details>
<summary>Toutes les 16 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| V. | **B** | V.sauvedata exist | Logical |
| V. | **C** | v. retour cloture | Logical |
| V. | **D** | v. operation durant cloture | Logical |
| V. | **E** | v.retour rename bout | Logical |
| V. | **F** | v.retour rename golf | Logical |
| Autre | **A** | > W date comptable | Date |
| Autre | **G** | W1 numero club | Numeric |
| Autre | **H** | W1 lettre controle | Alpha |
| Autre | **I** | W1 lettre controle modifiee | Alpha |
| Autre | **J** | W1 filiation | Numeric |
| Autre | **K** | W1 date depart | Date |
| Autre | **L** | W1 paiement | Alpha |
| Autre | **M** | W1 annulation | Alpha |
| Autre | **N** | W1 lieu | Numeric |
| Autre | **O** | W1 retour lien GMC | Numeric |
| Autre | **P** | W1 etat compte | Alpha |

</details>

## 12. EXPRESSIONS

**11 / 11 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONSTANTE | 2 | 0 |
| NEGATION | 1 | 0 |
| OTHER | 3 | 0 |
| CAST_LOGIQUE | 2 | 0 |
| CONDITION | 2 | 0 |
| REFERENCE_VG | 1 | 0 |

### 12.2 Expressions cles par type

#### CONSTANTE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 8 | `'G'` | - |
| CONSTANTE | 6 | `'B'` | - |

#### NEGATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| NEGATION | 1 | `NOT (V.sauvedata exist [B])` | - |

#### OTHER (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 4 | `v.retour rename golf [F]` | - |
| OTHER | 3 | `v.retour rename bout [E]` | - |
| OTHER | 2 | `FileExist ('%club_ip_sauvdata%sauve.DAT')` | - |

#### CAST_LOGIQUE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 10 | `'FALSE'LOG` | - |
| CAST_LOGIQUE | 5 | `NOT (V.sauvedata exist [B]) AND IF (v. retour cloture [C],v. operation durant cl... [D],'TRUE'LOG)` | - |

#### CONDITION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 9 | `[T] AND W1 numero club [G]<>0` | - |
| CONDITION | 7 | `[S] AND W1 numero club [G]<>0` | - |

#### REFERENCE_VG (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 11 | `VG26` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [CB menu caisse/boutique (IDE 10)](RET-IDE-10.md) -> **Transfert ODS Boutique (IDE 16)**

```mermaid
graph LR
    T16[16 Transfert ODS Boutique]
    style T16 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC9[9 Start]
    style CC9 fill:#f59e0b
    CC10[10 CB menu caisseboutique]
    style CC10 fill:#3fb950
    CC9 --> CC10
    CC1 --> CC9
    CC10 --> T16
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [10](RET-IDE-10.md) | CB menu caisse/boutique | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T16[16 Transfert ODS Boutique]
    style T16 fill:#58a6ff
    NONE[Aucun callee]
    T16 -.-> NONE
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
| Lignes de logique | 368 | Taille moyenne |
| Expressions | 11 | Peu de logique |
| Tables WRITE | 7 | Fort impact donnees |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 2 | Quelques ecrans |
| Code desactive | 0% (0 / 368) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Transfert (2 taches: 1 ecran, 1 traitement)

- **Strategie** : Service `ITransfertService` avec logique de deversement.

#### Traitement (8 taches: 3 ecrans, 5 traitements)

- **Strategie** : Orchestrateur avec 3 ecrans (Razor/React) et 5 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- Decomposer les taches en services unitaires testables.

#### Creation (5 taches: 0 ecran, 5 traitements)

- **Strategie** : Repository pattern avec Entity Framework Core.
- Insertion via `IRepository<T>.CreateAsync()`

#### Calcul (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Services de calcul purs (Domain Services).
- Migrer la logique de calcul (stock, compteurs, montants)

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| reseau_cloture___rec | Table WRITE (Database) | 4x | Schema + repository |
| gm-complet_______gmc | Table WRITE (Database) | 1x | Schema + repository |
| comptable_gratuite | Table WRITE (Database) | 1x | Schema + repository |
| comptable________cte | Table WRITE (Database) | 1x | Schema + repository |
| intermed__gratuititg | Table WRITE (Database) | 1x | Schema + repository |
| intermed_compta__ite | Table WRITE (Database) | 1x | Schema + repository |
| tai_forfait | Table WRITE (Database) | 1x | Schema + repository |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 20:44*
