# ADH IDE 86 - Bar Limit

> **Analyse**: Phases 1-4 2026-02-07 03:45 -> 02:21 (22h35min) | Assemblage 02:21
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | ADH |
| IDE Position | 86 |
| Nom Programme | Bar Limit |
| Fichier source | `Prg_86.xml` |
| Dossier IDE | General |
| Taches | 14 (4 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 6 |
| Complexite | **BASSE** (score 24/100) |

## 2. DESCRIPTION FONCTIONNELLE

## ADH IDE 86 - Bar Limit

**Objectif:** Gerer les plafonds de depense (bar limit) associes aux cartes Club Med Pass. Le programme permet de consulter le plafond actuel alloue a un compte, de modifier ce plafond via une tache de creation, et de valider ou annuler les modifications avant de les enregistrer dans la table `ez_card`.

**Flux principal:** Apres selection d'un compte depuis le menu Club Med Pass (IDE 77), l'utilisateur accede a la tache initiale qui affiche le plafond actuel. La tache "Create" permet de saisir un nouveau plafond avec validation D/C (debit/credit check). Une fois valide, le programme genere une edition du plafond alloue via IDE 87, puis initialise l'impression (IDE 179-182) avant de persister les modifications dans la base de donnees.

**Interactions externes:** Le programme s'appuie sur l'appel programme (IDE 44) pour les requetes metier, et integre un workflow complet d'impression avec selection imprimante, positionnement du listing, et reinitialisation après impression. Les taches "Bar Limit Cancel" et "validate D/C GO" encadrent le flux de validation avec rollback possible en cas d'annulation utilisateur.

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (9 taches)

Traitements internes.

---

#### <a id="t1"></a>86 - Bar Limit [[ECRAN]](#ecran-t1)

**Role** : Tache d'orchestration : point d'entree du programme (9 sous-taches). Coordonne l'enchainement des traitements.
**Ecran** : 806 x 235 DLU (MDI) | [Voir mockup](#ecran-t1)

<details>
<summary>8 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [86.1.1](#t3) | Bar Limit Cancel **[[ECRAN]](#ecran-t3)** | Traitement |
| [86.1.1.2](#t5) | Plafond actuel | Traitement |
| [86.1.1.3](#t6) | plafond reste | Traitement |
| [86.1.1.4](#t7) | derniere annulation | Traitement |
| [86.3](#t11) | Bar Limit **[[ECRAN]](#ecran-t11)** | Traitement |
| [86.4](#t12) | Plafond actuel | Traitement |
| [86.5](#t13) | derniere annulation | Traitement |
| [86.6](#t14) | plafond reste | Traitement |

</details>
**Delegue a** : [Appel programme (IDE 44)](ADH-IDE-44.md), [Set Listing Number (IDE 181)](ADH-IDE-181.md)

---

#### <a id="t3"></a>86.1.1 - Bar Limit Cancel [[ECRAN]](#ecran-t3)

**Role** : Traitement : Bar Limit Cancel.
**Ecran** : 627 x 121 DLU (MDI) | [Voir mockup](#ecran-t3)
**Delegue a** : [Appel programme (IDE 44)](ADH-IDE-44.md), [Set Listing Number (IDE 181)](ADH-IDE-181.md)

---

#### <a id="t5"></a>86.1.1.2 - Plafond actuel

**Role** : Traitement : Plafond actuel.
**Variables liees** : ET (v.plafond actuel), EU (v.plafond reste)
**Delegue a** : [Appel programme (IDE 44)](ADH-IDE-44.md), [Set Listing Number (IDE 181)](ADH-IDE-181.md)

---

#### <a id="t6"></a>86.1.1.3 - plafond reste

**Role** : Traitement : plafond reste.
**Variables liees** : ET (v.plafond actuel), EU (v.plafond reste)
**Delegue a** : [Appel programme (IDE 44)](ADH-IDE-44.md), [Set Listing Number (IDE 181)](ADH-IDE-181.md)

---

#### <a id="t7"></a>86.1.1.4 - derniere annulation

**Role** : Traitement : derniere annulation.
**Variables liees** : EW (V.Date derniere annulation), EX (V.Time derniere annulation)
**Delegue a** : [Appel programme (IDE 44)](ADH-IDE-44.md), [Set Listing Number (IDE 181)](ADH-IDE-181.md)

---

#### <a id="t11"></a>86.3 - Bar Limit [[ECRAN]](#ecran-t11)

**Role** : Traitement : Bar Limit.
**Ecran** : 803 x 121 DLU (Modal) | [Voir mockup](#ecran-t11)
**Delegue a** : [Appel programme (IDE 44)](ADH-IDE-44.md), [Set Listing Number (IDE 181)](ADH-IDE-181.md)

---

#### <a id="t12"></a>86.4 - Plafond actuel

**Role** : Traitement : Plafond actuel.
**Variables liees** : ET (v.plafond actuel), EU (v.plafond reste)
**Delegue a** : [Appel programme (IDE 44)](ADH-IDE-44.md), [Set Listing Number (IDE 181)](ADH-IDE-181.md)

---

#### <a id="t13"></a>86.5 - derniere annulation

**Role** : Traitement : derniere annulation.
**Variables liees** : EW (V.Date derniere annulation), EX (V.Time derniere annulation)
**Delegue a** : [Appel programme (IDE 44)](ADH-IDE-44.md), [Set Listing Number (IDE 181)](ADH-IDE-181.md)

---

#### <a id="t14"></a>86.6 - plafond reste

**Role** : Traitement : plafond reste.
**Variables liees** : ET (v.plafond actuel), EU (v.plafond reste)
**Delegue a** : [Appel programme (IDE 44)](ADH-IDE-44.md), [Set Listing Number (IDE 181)](ADH-IDE-181.md)


### 3.2 Creation (3 taches)

Insertion de nouveaux enregistrements en base.

---

#### <a id="t2"></a>86.1 - Create [[ECRAN]](#ecran-t2)

**Role** : Traitement : Create.
**Ecran** : 144 x 59 DLU (MDI) | [Voir mockup](#ecran-t2)

---

#### <a id="t8"></a>86.2 - Create [[ECRAN]](#ecran-t8)

**Role** : Traitement : Create.
**Ecran** : 144 x 59 DLU (MDI) | [Voir mockup](#ecran-t8)

---

#### <a id="t9"></a>86.2.1 - Creation [[ECRAN]](#ecran-t9)

**Role** : Creation d'enregistrement : Creation.
**Ecran** : 627 x 121 DLU (MDI) | [Voir mockup](#ecran-t9)


### 3.3 Validation (2 taches)

Controles de coherence : 2 taches verifient les donnees et conditions.

---

#### <a id="t4"></a>86.1.1.1 - validate D/C GO [[ECRAN]](#ecran-t4)

**Role** : Verification : validate D/C GO.
**Ecran** : 127 x 81 DLU (MDI) | [Voir mockup](#ecran-t4)

---

#### <a id="t10"></a>86.2.1.1 - validate D/C GO [[ECRAN]](#ecran-t10)

**Role** : Verification : validate D/C GO.
**Ecran** : 127 x 81 DLU (MDI) | [Voir mockup](#ecran-t10)


## 5. REGLES METIER

3 regles identifiees:

### Autres (3 regles)

#### <a id="rm-RM-001"></a>[RM-001] Condition: [N] egale 'A'

| Element | Detail |
|---------|--------|
| **Condition** | `[N]='A'` |
| **Si vrai** | Action si vrai |
| **Expression source** | Expression 9 : `[N]='A'` |
| **Exemple** | Si [N]='A' â†’ Action si vrai |

#### <a id="rm-RM-002"></a>[RM-002] Condition: [N] egale 'B'

| Element | Detail |
|---------|--------|
| **Condition** | `[N]='B'` |
| **Si vrai** | Action si vrai |
| **Expression source** | Expression 10 : `[N]='B'` |
| **Exemple** | Si [N]='B' â†’ Action si vrai |

#### <a id="rm-RM-003"></a>[RM-003] Condition: [N] egale 'C'

| Element | Detail |
|---------|--------|
| **Condition** | `[N]='C'` |
| **Si vrai** | Action si vrai |
| **Expression source** | Expression 11 : `[N]='C'` |
| **Exemple** | Si [N]='C' â†’ Action si vrai |

## 6. CONTEXTE

- **Appele par**: [Club Med Pass menu (IDE 77)](ADH-IDE-77.md)
- **Appelle**: 6 programmes | **Tables**: 3 (W:1 R:3 L:1) | **Taches**: 14 | **Expressions**: 11

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (4 / 14)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 86 | 86 | Bar Limit | MDI | 806 | 235 | Traitement |
| 2 | 86.1.1 | 86.1.1 | Bar Limit Cancel | MDI | 627 | 121 | Traitement |
| 3 | 86.2.1 | 86.2.1 | Creation | MDI | 627 | 121 | Creation |
| 4 | 86.3 | 86.3 | Bar Limit | Modal | 803 | 121 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>86 - Bar Limit
**Tache** : [86](#t1) | **Type** : MDI | **Dimensions** : 806 x 235 DLU
**Bloc** : Traitement | **Titre IDE** : Bar Limit

<!-- FORM-DATA:
{
    "width":  806,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  1,
                         "w":  806,
                         "fmt":  "",
                         "name":  "",
                         "h":  21,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  211,
                         "w":  806,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  52,
                         "type":  "label",
                         "var":  "",
                         "y":  150,
                         "w":  459,
                         "fmt":  "",
                         "name":  "",
                         "h":  56,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  56,
                         "type":  "label",
                         "var":  "",
                         "y":  152,
                         "w":  449,
                         "fmt":  "",
                         "name":  "",
                         "h":  53,
                         "color":  "",
                         "text":  "",
                         "parent":  8
                     },
                     {
                         "x":  59,
                         "type":  "label",
                         "var":  "",
                         "y":  154,
                         "w":  42,
                         "fmt":  "",
                         "name":  "",
                         "h":  50,
                         "color":  "",
                         "text":  "",
                         "parent":  8
                     },
                     {
                         "x":  112,
                         "type":  "label",
                         "var":  "",
                         "y":  158,
                         "w":  170,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "142",
                         "text":  "Création",
                         "parent":  8
                     },
                     {
                         "x":  112,
                         "type":  "label",
                         "var":  "",
                         "y":  174,
                         "w":  170,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "142",
                         "text":  "Annulation",
                         "parent":  8
                     },
                     {
                         "x":  112,
                         "type":  "label",
                         "var":  "",
                         "y":  190,
                         "w":  170,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "142",
                         "text":  "Edition",
                         "parent":  8
                     },
                     {
                         "x":  305,
                         "type":  "label",
                         "var":  "",
                         "y":  190,
                         "w":  120,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "Votre choix",
                         "parent":  8
                     },
                     {
                         "x":  433,
                         "type":  "edit",
                         "var":  "",
                         "y":  190,
                         "w":  26,
                         "fmt":  "UA",
                         "name":  "v.choix action",
                         "h":  9,
                         "color":  "6",
                         "text":  "",
                         "parent":  8
                     },
                     {
                         "x":  5,
                         "type":  "image",
                         "var":  "",
                         "y":  3,
                         "w":  59,
                         "fmt":  "",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  77,
                         "type":  "edit",
                         "var":  "",
                         "y":  7,
                         "w":  267,
                         "fmt":  "30",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  514,
                         "type":  "edit",
                         "var":  "",
                         "y":  7,
                         "w":  259,
                         "fmt":  "WWW DD MMM YYYYT",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  594,
                         "type":  "image",
                         "var":  "",
                         "y":  152,
                         "w":  159,
                         "fmt":  "",
                         "name":  "",
                         "h":  53,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  67,
                         "type":  "button",
                         "var":  "",
                         "y":  158,
                         "w":  27,
                         "fmt":  "A",
                         "name":  "A",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  67,
                         "type":  "button",
                         "var":  "",
                         "y":  174,
                         "w":  27,
                         "fmt":  "B",
                         "name":  "B",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  67,
                         "type":  "button",
                         "var":  "",
                         "y":  190,
                         "w":  27,
                         "fmt":  "C",
                         "name":  "C",
                         "h":  9,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  8,
                         "type":  "button",
                         "var":  "",
                         "y":  214,
                         "w":  154,
                         "fmt":  "\u0026Quitter",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  6
                     },
                     {
                         "x":  631,
                         "type":  "button",
                         "var":  "",
                         "y":  214,
                         "w":  168,
                         "fmt":  "Printer",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  0,
                         "type":  "subform",
                         "var":  "",
                         "y":  23,
                         "w":  805,
                         "fmt":  "",
                         "name":  "LISTEOPE",
                         "h":  126,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "86",
    "height":  235
}
-->

<details>
<summary><strong>Champs : 3 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 433,190 | v.choix action | - | edit |
| 77,7 | 30 | - | edit |
| 514,7 | WWW DD MMM YYYYT | - | edit |

</details>

<details>
<summary><strong>Boutons : 5 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| A | 67,158 | Bouton fonctionnel |
| B | 67,174 | Bouton fonctionnel |
| C | 67,190 | Bouton fonctionnel |
| Quitter | 8,214 | Quitte le programme |
| Printer | 631,214 | Appel [    Print Plafonds alloués (IDE 87)](ADH-IDE-87.md) |

</details>

---

#### <a id="ecran-t3"></a>86.1.1 - Bar Limit Cancel
**Tache** : [86.1.1](#t3) | **Type** : MDI | **Dimensions** : 627 x 121 DLU
**Bloc** : Traitement | **Titre IDE** : Bar Limit Cancel

<!-- FORM-DATA:
{
    "width":  627,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  2,
                         "type":  "label",
                         "var":  "",
                         "y":  1,
                         "w":  621,
                         "fmt":  "",
                         "name":  "",
                         "h":  21,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  258,
                         "type":  "label",
                         "var":  "",
                         "y":  39,
                         "w":  162,
                         "fmt":  "",
                         "name":  "",
                         "h":  11,
                         "color":  "",
                         "text":  "Actual Bar Limit",
                         "parent":  null
                     },
                     {
                         "x":  258,
                         "type":  "label",
                         "var":  "",
                         "y":  57,
                         "w":  162,
                         "fmt":  "",
                         "name":  "",
                         "h":  11,
                         "color":  "",
                         "text":  "Balance",
                         "parent":  null
                     },
                     {
                         "x":  272,
                         "type":  "label",
                         "var":  "",
                         "y":  75,
                         "w":  309,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "143",
                         "text":  "Bar Limit Cancelation",
                         "parent":  null
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  97,
                         "w":  621,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  438,
                         "type":  "edit",
                         "var":  "",
                         "y":  39,
                         "w":  151,
                         "fmt":  "## ### ### ###.###Z",
                         "name":  "",
                         "h":  11,
                         "color":  "6",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  438,
                         "type":  "edit",
                         "var":  "",
                         "y":  57,
                         "w":  151,
                         "fmt":  "N## ### ### ###.###Z",
                         "name":  "",
                         "h":  11,
                         "color":  "6",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  315,
                         "type":  "button",
                         "var":  "",
                         "y":  100,
                         "w":  296,
                         "fmt":  "Confirm Bar \\Limit Cancelation",
                         "name":  "VALID",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  7,
                         "type":  "image",
                         "var":  "",
                         "y":  3,
                         "w":  59,
                         "fmt":  "",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  79,
                         "type":  "edit",
                         "var":  "",
                         "y":  7,
                         "w":  267,
                         "fmt":  "30",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  371,
                         "type":  "edit",
                         "var":  "",
                         "y":  7,
                         "w":  238,
                         "fmt":  "WWW DD MMM YYYYT",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  27,
                         "type":  "image",
                         "var":  "",
                         "y":  38,
                         "w":  159,
                         "fmt":  "",
                         "name":  "",
                         "h":  53,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  8,
                         "type":  "button",
                         "var":  "",
                         "y":  100,
                         "w":  154,
                         "fmt":  "\u0026Quitter",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  11
                     }
                 ],
    "taskId":  "86.1.1",
    "height":  121
}
-->

<details>
<summary><strong>Champs : 4 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 438,39 | ## ### ### ###.###Z | - | edit |
| 438,57 | N## ### ### ###.###Z | - | edit |
| 79,7 | 30 | - | edit |
| 371,7 | WWW DD MMM YYYYT | - | edit |

</details>

<details>
<summary><strong>Boutons : 2 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Confirm Bar \Limit Cancelation | 315,100 | Valide la saisie et enregistre Annule et retour au menu |
| Quitter | 8,100 | Quitte le programme |

</details>

---

#### <a id="ecran-t9"></a>86.2.1 - Creation
**Tache** : [86.2.1](#t9) | **Type** : MDI | **Dimensions** : 627 x 121 DLU
**Bloc** : Creation | **Titre IDE** : Creation

<!-- FORM-DATA:
{
    "width":  627,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  2,
                         "type":  "label",
                         "var":  "",
                         "y":  1,
                         "w":  621,
                         "fmt":  "",
                         "name":  "",
                         "h":  21,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  291,
                         "type":  "label",
                         "var":  "",
                         "y":  53,
                         "w":  111,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "Amount",
                         "parent":  null
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  97,
                         "w":  621,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  412,
                         "type":  "edit",
                         "var":  "",
                         "y":  53,
                         "w":  151,
                         "fmt":  "## ### ### ###.###Z",
                         "name":  "v.montant",
                         "h":  12,
                         "color":  "6",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  459,
                         "type":  "button",
                         "var":  "",
                         "y":  100,
                         "w":  154,
                         "fmt":  "\u0026Creation",
                         "name":  "VALID",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  7,
                         "type":  "image",
                         "var":  "",
                         "y":  3,
                         "w":  59,
                         "fmt":  "",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  79,
                         "type":  "edit",
                         "var":  "",
                         "y":  7,
                         "w":  267,
                         "fmt":  "30",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  371,
                         "type":  "edit",
                         "var":  "",
                         "y":  7,
                         "w":  238,
                         "fmt":  "WWW DD MMM YYYYT",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  27,
                         "type":  "image",
                         "var":  "",
                         "y":  38,
                         "w":  159,
                         "fmt":  "",
                         "name":  "",
                         "h":  53,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  8,
                         "type":  "button",
                         "var":  "",
                         "y":  100,
                         "w":  154,
                         "fmt":  "\u0026Quitter",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  8
                     }
                 ],
    "taskId":  "86.2.1",
    "height":  121
}
-->

<details>
<summary><strong>Champs : 3 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 412,53 | v.montant | - | edit |
| 79,7 | 30 | - | edit |
| 371,7 | WWW DD MMM YYYYT | - | edit |

</details>

<details>
<summary><strong>Boutons : 2 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Creation | 459,100 | Bouton fonctionnel |
| Quitter | 8,100 | Quitte le programme |

</details>

---

#### <a id="ecran-t11"></a>86.3 - Bar Limit
**Tache** : [86.3](#t11) | **Type** : Modal | **Dimensions** : 803 x 121 DLU
**Bloc** : Traitement | **Titre IDE** : Bar Limit

<!-- FORM-DATA:
{
    "width":  803,
    "vFactor":  8,
    "type":  "Modal",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  32,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  101,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Account # :",
                         "parent":  null
                     },
                     {
                         "x":  32,
                         "type":  "label",
                         "var":  "",
                         "y":  101,
                         "w":  192,
                         "fmt":  "",
                         "name":  "",
                         "h":  14,
                         "color":  "6",
                         "text":  "Last Bar Limit",
                         "parent":  null
                     },
                     {
                         "x":  407,
                         "type":  "label",
                         "var":  "",
                         "y":  101,
                         "w":  192,
                         "fmt":  "",
                         "name":  "",
                         "h":  14,
                         "color":  "6",
                         "text":  "Balance",
                         "parent":  null
                     },
                     {
                         "x":  32,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "6",
                         "w":  739,
                         "y":  14,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  14,
                         "h":  84,
                         "cols":  [
                                      {
                                          "title":  "Montant",
                                          "layer":  1,
                                          "w":  304
                                      },
                                      {
                                          "title":  "Opération",
                                          "layer":  2,
                                          "w":  401
                                      }
                                  ],
                         "rows":  2
                     },
                     {
                         "x":  221,
                         "type":  "edit",
                         "var":  "",
                         "y":  101,
                         "w":  169,
                         "fmt":  "N## ### ### ###.###Z",
                         "name":  "",
                         "h":  14,
                         "color":  "6",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  596,
                         "type":  "edit",
                         "var":  "",
                         "y":  101,
                         "w":  169,
                         "fmt":  "N## ### ### ###.###Z",
                         "name":  "",
                         "h":  14,
                         "color":  "6",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  245,
                         "type":  "edit",
                         "var":  "",
                         "y":  0,
                         "w":  42,
                         "fmt":  "",
                         "name":  "p.filiation",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  354,
                         "type":  "edit",
                         "var":  "",
                         "y":  28,
                         "w":  126,
                         "fmt":  "##/##/####Z",
                         "name":  "",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  9
                     },
                     {
                         "x":  496,
                         "type":  "edit",
                         "var":  "",
                         "y":  28,
                         "w":  80,
                         "fmt":  "HH:MMZ",
                         "name":  "",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  9
                     },
                     {
                         "x":  595,
                         "type":  "edit",
                         "var":  "",
                         "y":  28,
                         "w":  126,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  9
                     },
                     {
                         "x":  135,
                         "type":  "edit",
                         "var":  "",
                         "y":  0,
                         "w":  98,
                         "fmt":  "",
                         "name":  "p.code-8chiffres",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  307,
                         "type":  "edit",
                         "var":  "",
                         "y":  0,
                         "w":  299,
                         "fmt":  "60",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  66,
                         "type":  "edit",
                         "var":  "",
                         "y":  28,
                         "w":  194,
                         "fmt":  "30",
                         "name":  "",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  9
                     }
                 ],
    "taskId":  "86.3",
    "height":  121
}
-->

<details>
<summary><strong>Champs : 9 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 221,101 | N## ### ### ###.###Z | - | edit |
| 596,101 | N## ### ### ###.###Z | - | edit |
| 245,0 | p.filiation | - | edit |
| 354,28 | ##/##/####Z | - | edit |
| 496,28 | HH:MMZ | - | edit |
| 595,28 | (sans nom) | - | edit |
| 135,0 | p.code-8chiffres | - | edit |
| 307,0 | 60 | - | edit |
| 66,28 | 30 | - | edit |

</details>

## 9. NAVIGATION

### 9.1 Enchainement des ecrans

```mermaid
flowchart TD
    START([Entree])
    style START fill:#3fb950
    VF1[86 Bar Limit]
    style VF1 fill:#58a6ff
    VF3[86.1.1 Bar Limit Cancel]
    style VF3 fill:#58a6ff
    VF9[86.2.1 Creation]
    style VF9 fill:#58a6ff
    VF11[86.3 Bar Limit]
    style VF11 fill:#58a6ff
    EXT44[IDE 44 Appel programme]
    style EXT44 fill:#3fb950
    EXT87[IDE 87 Print Plafonds ...]
    style EXT87 fill:#3fb950
    EXT179[IDE 179 Get Printer]
    style EXT179 fill:#3fb950
    EXT180[IDE 180 Printer choice]
    style EXT180 fill:#3fb950
    EXT181[IDE 181 Set Listing Nu...]
    style EXT181 fill:#3fb950
    EXT182[IDE 182 Raz Current Pr...]
    style EXT182 fill:#3fb950
    FIN([Sortie])
    style FIN fill:#f85149
    START --> VF1
    VF1 -->|Sous-programme| EXT44
    VF1 -->|Impression ticket/document| EXT87
    VF1 -->|Impression ticket/document| EXT179
    VF1 -->|Impression ticket/document| EXT180
    VF1 -->|Configuration impression| EXT181
    VF1 -->|Impression ticket/document| EXT182
    EXT182 --> FIN
```

**Detail par enchainement :**

| Depuis | Action | Vers | Retour |
|--------|--------|------|--------|
| Bar Limit | Sous-programme | [Appel programme (IDE 44)](ADH-IDE-44.md) | Retour ecran |
| Bar Limit | Impression ticket/document | [    Print Plafonds alloués (IDE 87)](ADH-IDE-87.md) | Retour ecran |
| Bar Limit | Impression ticket/document | [Get Printer (IDE 179)](ADH-IDE-179.md) | Retour ecran |
| Bar Limit | Impression ticket/document | [Printer choice (IDE 180)](ADH-IDE-180.md) | Retour ecran |
| Bar Limit | Configuration impression | [Set Listing Number (IDE 181)](ADH-IDE-181.md) | Retour ecran |
| Bar Limit | Impression ticket/document | [Raz Current Printer (IDE 182)](ADH-IDE-182.md) | Retour ecran |

### 9.3 Structure hierarchique (14 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **86.1** | [**Bar Limit** (86)](#t1) [mockup](#ecran-t1) | MDI | 806x235 | Traitement |
| 86.1.1 | [Bar Limit Cancel (86.1.1)](#t3) [mockup](#ecran-t3) | MDI | 627x121 | |
| 86.1.2 | [Plafond actuel (86.1.1.2)](#t5) | MDI | - | |
| 86.1.3 | [plafond reste (86.1.1.3)](#t6) | MDI | - | |
| 86.1.4 | [derniere annulation (86.1.1.4)](#t7) | MDI | - | |
| 86.1.5 | [Bar Limit (86.3)](#t11) [mockup](#ecran-t11) | Modal | 803x121 | |
| 86.1.6 | [Plafond actuel (86.4)](#t12) | MDI | - | |
| 86.1.7 | [derniere annulation (86.5)](#t13) | MDI | - | |
| 86.1.8 | [plafond reste (86.6)](#t14) | MDI | - | |
| **86.2** | [**Create** (86.1)](#t2) [mockup](#ecran-t2) | MDI | 144x59 | Creation |
| 86.2.1 | [Create (86.2)](#t8) [mockup](#ecran-t8) | MDI | 144x59 | |
| 86.2.2 | [Creation (86.2.1)](#t9) [mockup](#ecran-t9) | MDI | 627x121 | |
| **86.3** | [**validate D/C GO** (86.1.1.1)](#t4) [mockup](#ecran-t4) | MDI | 127x81 | Validation |
| 86.3.1 | [validate D/C GO (86.2.1.1)](#t10) [mockup](#ecran-t10) | MDI | 127x81 | |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Liste]
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

### Tables utilisees (3)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 312 | ez_card |  | DB | R | **W** |   | 4 |
| 19 | bl_detail |  | DB | R |   | L | 7 |
| 30 | gm-recherche_____gmr | Index de recherche | DB | R |   |   | 1 |

### Colonnes par table (3 / 3 tables avec colonnes identifiees)

<details>
<summary>Table 312 - ez_card (R/**W**) - 4 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| ES | p.card code | W | Alpha |

</details>

<details>
<summary>Table 19 - bl_detail (R/L) - 7 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | v.plafond actuel | R | Numeric |
| B | v.plafond reste liste | R | Numeric |

</details>

<details>
<summary>Table 30 - gm-recherche_____gmr (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | p.societe | R | Alpha |
| B | p.code-8chiffres | R | Numeric |
| C | p.filiation | R | Numeric |
| D | p.masque montant | R | Alpha |
| E | p.masque cumul | R | Alpha |
| F | p.card code | R | Alpha |
| G | v.plafond actuel | R | Numeric |
| H | v.plafond reste | R | Numeric |
| I | v.choix action | R | Alpha |
| J | V.Date derniere annulation | R | Date |
| K | V.Time derniere annulation | R | Time |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (6)

Variables recues du programme appelant ([Club Med Pass menu (IDE 77)](ADH-IDE-77.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| EN | p.societe | Alpha | 1x parametre entrant |
| EO | p.code-8chiffres | Numeric | 1x parametre entrant |
| EP | p.filiation | Numeric | 1x parametre entrant |
| EQ | p.masque montant | Alpha | - |
| ER | p.masque cumul | Alpha | - |
| ES | p.card code | Alpha | - |

### 11.2 Variables de session (5)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| ET | v.plafond actuel | Numeric | - |
| EU | v.plafond reste | Numeric | - |
| EV | v.choix action | Alpha | - |
| EW | V.Date derniere annulation | Date | - |
| EX | V.Time derniere annulation | Time | - |

## 12. EXPRESSIONS

**11 / 11 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONDITION | 3 | 3 |
| CONSTANTE | 3 | 0 |
| DATE | 1 | 0 |
| REFERENCE_VG | 1 | 0 |
| OTHER | 3 | 0 |

### 12.2 Expressions cles par type

#### CONDITION (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 11 | `[N]='C'` | [RM-003](#rm-RM-003) |
| CONDITION | 10 | `[N]='B'` | [RM-002](#rm-RM-002) |
| CONDITION | 9 | `[N]='A'` | [RM-001](#rm-RM-001) |

#### CONSTANTE (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 8 | `'LISTEOPE'` | - |
| CONSTANTE | 7 | `40` | - |
| CONSTANTE | 1 | `''` | - |

#### DATE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| DATE | 2 | `Date ()` | - |

#### REFERENCE_VG (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 3 | `VG1` | - |

#### OTHER (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 6 | `p.filiation [C]` | - |
| OTHER | 5 | `p.code-8chiffres [B]` | - |
| OTHER | 4 | `p.societe [A]` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Club Med Pass menu (IDE 77)](ADH-IDE-77.md) -> **Bar Limit (IDE 86)**

```mermaid
graph LR
    T86[86 Bar Limit]
    style T86 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC163[163 Menu caisse GM - s...]
    style CC163 fill:#f59e0b
    CC77[77 Club Med Pass menu]
    style CC77 fill:#3fb950
    CC163 --> CC77
    CC1 --> CC163
    CC77 --> T86
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [77](ADH-IDE-77.md) | Club Med Pass menu | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T86[86 Bar Limit]
    style T86 fill:#58a6ff
    C44[44 Appel programme]
    T86 --> C44
    style C44 fill:#3fb950
    C87[87 Print Plafonds alloués]
    T86 --> C87
    style C87 fill:#3fb950
    C179[179 Get Printer]
    T86 --> C179
    style C179 fill:#3fb950
    C180[180 Printer choice]
    T86 --> C180
    style C180 fill:#3fb950
    C181[181 Set Listing Number]
    T86 --> C181
    style C181 fill:#3fb950
    C182[182 Raz Current Printer]
    T86 --> C182
    style C182 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [44](ADH-IDE-44.md) | Appel programme | 1 | Sous-programme |
| [87](ADH-IDE-87.md) |     Print Plafonds alloués | 1 | Impression ticket/document |
| [179](ADH-IDE-179.md) | Get Printer | 1 | Impression ticket/document |
| [180](ADH-IDE-180.md) | Printer choice | 1 | Impression ticket/document |
| [181](ADH-IDE-181.md) | Set Listing Number | 1 | Configuration impression |
| [182](ADH-IDE-182.md) | Raz Current Printer | 1 | Impression ticket/document |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 177 | Programme compact |
| Expressions | 11 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 6 | Dependances moderees |
| Ecrans visibles | 4 | Quelques ecrans |
| Code desactive | 0% (0 / 177) | Code sain |
| Regles metier | 3 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (9 taches: 3 ecrans, 6 traitements)

- **Strategie** : Orchestrateur avec 3 ecrans (Razor/React) et 6 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 6 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Creation (3 taches: 3 ecrans, 0 traitement)

- **Strategie** : Repository pattern avec Entity Framework Core.
- Insertion via `IRepository<T>.CreateAsync()`

#### Validation (2 taches: 2 ecrans, 0 traitement)

- **Strategie** : FluentValidation avec validators specifiques.
- Chaque tache de validation -> un validator injectable

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| ez_card | Table WRITE (Database) | 2x | Schema + repository |
| [Printer choice (IDE 180)](ADH-IDE-180.md) | Sous-programme | 1x | Normale - Impression ticket/document |
| [Set Listing Number (IDE 181)](ADH-IDE-181.md) | Sous-programme | 1x | Normale - Configuration impression |
| [Raz Current Printer (IDE 182)](ADH-IDE-182.md) | Sous-programme | 1x | Normale - Impression ticket/document |
| [Appel programme (IDE 44)](ADH-IDE-44.md) | Sous-programme | 1x | Normale - Sous-programme |
| [    Print Plafonds alloués (IDE 87)](ADH-IDE-87.md) | Sous-programme | 1x | Normale - Impression ticket/document |
| [Get Printer (IDE 179)](ADH-IDE-179.md) | Sous-programme | 1x | Normale - Impression ticket/document |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-08 02:22*
