# PBG IDE 381 - Repas non encaissés au villNEW

> **Analyse**: Phases 1-4 2026-02-03 11:33 -> 11:33 (17s) | Assemblage 11:33
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBG |
| IDE Position | 381 |
| Nom Programme | Repas non encaissés au villNEW |
| Fichier source | `Prg_381.xml` |
| Dossier IDE | General |
| Taches | 4 (3 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 2 |
| :warning: Statut | **ORPHELIN_POTENTIEL** |

## 2. DESCRIPTION FONCTIONNELLE

**Repas non encaissés au villNEW** assure la gestion complete de ce processus.

Le flux de traitement s'organise en **2 blocs fonctionnels** :

- **Traitement** (3 taches) : traitements metier divers
- **Creation** (1 tache) : insertion d'enregistrements en base (mouvements, prestations)

**Donnees modifiees** : 1 tables en ecriture (lg_vente_facture).

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (3 taches)

- **381** - Repas non encaissés au village **[[ECRAN]](#ecran-t2)**
- **381.1** - Liste **[[ECRAN]](#ecran-t19)**
- **381.1.2** - suppresion ligne

Delegue a : [Qualite et Complements (IDE 68)](PBG-IDE-68.md)

#### Phase 2 : Creation (1 tache)

- **381.1.1** - Creation **[[ECRAN]](#ecran-t20)**

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| lg_vente_facture | R/**W** (3 usages) | Donnees de ventes |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (3 taches)

Traitements internes.

---

#### <a id="t2"></a>381 - Repas non encaissés au village [[ECRAN]](#ecran-t2)

**Role** : Traitement : Repas non encaissés au village.
**Ecran** : 1102 x 263 DLU (MDI) | [Voir mockup](#ecran-t2)
**Variables liees** : K (V.Existe Repas DEJ ou DIN ?)
**Delegue a** : [Qualite et Complements (IDE 68)](PBG-IDE-68.md)

---

#### <a id="t19"></a>381.1 - Liste [[ECRAN]](#ecran-t19)

**Role** : Traitement : Liste.
**Ecran** : 1080 x 179 DLU (Modal) | [Voir mockup](#ecran-t19)
**Delegue a** : [Qualite et Complements (IDE 68)](PBG-IDE-68.md)

---

#### <a id="t21"></a>381.1.2 - suppresion ligne

**Role** : Traitement : suppresion ligne.
**Variables liees** : E (V.Affiche ligne ?)
**Delegue a** : [Qualite et Complements (IDE 68)](PBG-IDE-68.md)


### 3.2 Creation (1 tache)

Insertion de nouveaux enregistrements en base.

---

#### <a id="t20"></a>381.1.1 - Creation [[ECRAN]](#ecran-t20)

**Role** : Creation d'enregistrement : Creation.
**Ecran** : 1226 x 148 DLU | [Voir mockup](#ecran-t20)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: (aucun)
- **Appelle**: 2 programmes | **Tables**: 2 (W:1 R:1 L:1) | **Taches**: 4 | **Expressions**: 20

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (3 / 4)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 381.1 | 381 | Repas non encaissés au village | MDI | 1102 | 263 | Traitement |
| 2 | 381.1.1 | 381.1 | Liste | Modal | 1080 | 179 | Traitement |
| 3 | 381.1.1.1 | 381.1.1 | Creation | Type0 | 1226 | 148 | Creation |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t2"></a>381.1 - Repas non encaissés au village
**Tache** : [381](#t2) | **Type** : MDI | **Dimensions** : 1102 x 263 DLU
**Bloc** : Traitement | **Titre IDE** : Repas non encaissés au village

<!-- FORM-DATA:
{
    "width":  1102,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  1,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  1095,
                         "fmt":  "",
                         "name":  "",
                         "h":  22,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  2,
                         "type":  "label",
                         "var":  "",
                         "y":  235,
                         "w":  1096,
                         "fmt":  "",
                         "name":  "",
                         "h":  23,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  16,
                         "type":  "label",
                         "var":  "",
                         "y":  32,
                         "w":  183,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "Date de consommation",
                         "parent":  101
                     },
                     {
                         "x":  6,
                         "type":  "label",
                         "var":  "",
                         "y":  23,
                         "w":  918,
                         "fmt":  "",
                         "name":  "",
                         "h":  25,
                         "color":  "1",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  9,
                         "type":  "button",
                         "var":  "",
                         "y":  238,
                         "w":  154,
                         "fmt":  "\u0026Quitter",
                         "name":  "bouton quitter",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  42
                     },
                     {
                         "x":  7,
                         "type":  "edit",
                         "var":  "",
                         "y":  6,
                         "w":  394,
                         "fmt":  "20",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  813,
                         "type":  "edit",
                         "var":  "",
                         "y":  6,
                         "w":  274,
                         "fmt":  "WWW DD MMM YYYYT",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  8,
                         "type":  "subform",
                         "var":  "",
                         "y":  52,
                         "w":  1085,
                         "fmt":  "",
                         "name":  "REPAS",
                         "h":  181,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  195,
                         "type":  "edit",
                         "var":  "",
                         "y":  32,
                         "w":  126,
                         "fmt":  "DD/MM/YYYYZ",
                         "name":  "w0_DateConsommation",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  101
                     },
                     {
                         "x":  324,
                         "type":  "button",
                         "var":  "",
                         "y":  32,
                         "w":  28,
                         "fmt":  "...",
                         "name":  "b_date",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  101
                     },
                     {
                         "x":  930,
                         "type":  "button",
                         "var":  "",
                         "y":  27,
                         "w":  154,
                         "fmt":  "\u0026Consultation",
                         "name":  "b_consultation",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  189,
                         "type":  "edit",
                         "var":  "",
                         "y":  241,
                         "w":  724,
                         "fmt":  "80",
                         "name":  "",
                         "h":  10,
                         "color":  "143",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "381.1",
    "height":  263
}
-->

<details>
<summary><strong>Champs : 4 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 7,6 | 20 | - | edit |
| 813,6 | WWW DD MMM YYYYT | - | edit |
| 195,32 | w0_DateConsommation | - | edit |
| 189,241 | 80 | - | edit |

</details>

<details>
<summary><strong>Boutons : 3 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Quitter | 9,238 | Quitte le programme |
| ... | 324,32 | Bouton fonctionnel |
| Consultation | 930,27 | Bouton fonctionnel |

</details>

---

#### <a id="ecran-t19"></a>381.1.1 - Liste
**Tache** : [381.1](#t19) | **Type** : Modal | **Dimensions** : 1080 x 179 DLU
**Bloc** : Traitement | **Titre IDE** : Liste

<!-- FORM-DATA:
{
    "width":  1080,
    "vFactor":  8,
    "type":  "Modal",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "110",
                         "w":  915,
                         "y":  1,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  15,
                         "h":  172,
                         "cols":  [
                                      {
                                          "title":  "Type de repas",
                                          "layer":  1,
                                          "w":  204
                                      },
                                      {
                                          "title":  "Village/Groupe",
                                          "layer":  2,
                                          "w":  394
                                      },
                                      {
                                          "title":  "Nb de repas",
                                          "layer":  3,
                                          "w":  126
                                      },
                                      {
                                          "title":  "Repas",
                                          "layer":  4,
                                          "w":  155
                                      }
                                  ],
                         "rows":  4
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  167,
                         "w":  122,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "Motif annulation",
                         "parent":  null
                     },
                     {
                         "x":  9,
                         "type":  "edit",
                         "var":  "",
                         "y":  16,
                         "w":  192,
                         "fmt":  "",
                         "name":  "type_repas",
                         "h":  12,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  213,
                         "type":  "edit",
                         "var":  "",
                         "y":  16,
                         "w":  382,
                         "fmt":  "",
                         "name":  "village",
                         "h":  12,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  609,
                         "type":  "edit",
                         "var":  "",
                         "y":  16,
                         "w":  110,
                         "fmt":  "N6Z",
                         "name":  "nb_repas",
                         "h":  12,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  922,
                         "type":  "button",
                         "var":  "",
                         "y":  7,
                         "w":  154,
                         "fmt":  "\u0026Modification",
                         "name":  "b_modification",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  922,
                         "type":  "button",
                         "var":  "",
                         "y":  29,
                         "w":  154,
                         "fmt":  "\u0026Création",
                         "name":  "b_creation",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  732,
                         "type":  "combobox",
                         "var":  "",
                         "y":  16,
                         "w":  143,
                         "fmt":  "",
                         "name":  "repas",
                         "h":  12,
                         "color":  "110",
                         "text":  "DIN,DEJ,DDE",
                         "parent":  1
                     },
                     {
                         "x":  922,
                         "type":  "button",
                         "var":  "",
                         "y":  51,
                         "w":  154,
                         "fmt":  "\u0026Annulation",
                         "name":  "b_annulation",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  127,
                         "type":  "edit",
                         "var":  "",
                         "y":  167,
                         "w":  937,
                         "fmt":  "",
                         "name":  "effq_motif_annulation",
                         "h":  10,
                         "color":  "143",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "381.1.1",
    "height":  179
}
-->

<details>
<summary><strong>Champs : 5 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 9,16 | type_repas | - | edit |
| 213,16 | village | - | edit |
| 609,16 | nb_repas | - | edit |
| 732,16 | repas | - | combobox |
| 127,167 | effq_motif_annulation | - | edit |

</details>

<details>
<summary><strong>Boutons : 3 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Modification | 922,7 | Modifie l'element |
| Création | 922,29 | Bouton fonctionnel |
| Annulation | 922,51 | Annule et retour au menu |

</details>

---

#### <a id="ecran-t20"></a>381.1.1.1 - Creation
**Tache** : [381.1.1](#t20) | **Type** : Type0 | **Dimensions** : 1226 x 148 DLU
**Bloc** : Creation | **Titre IDE** : Creation

<!-- FORM-DATA:
{
    "width":  1226,
    "vFactor":  8,
    "type":  "Type0",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  10,
                         "type":  "label",
                         "var":  "",
                         "y":  5,
                         "w":  1209,
                         "fmt":  "",
                         "name":  "",
                         "h":  101,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  29,
                         "type":  "label",
                         "var":  "",
                         "y":  35,
                         "w":  104,
                         "fmt":  "",
                         "name":  "",
                         "h":  13,
                         "color":  "",
                         "text":  "Type repas",
                         "parent":  1
                     },
                     {
                         "x":  645,
                         "type":  "label",
                         "var":  "",
                         "y":  33,
                         "w":  58,
                         "fmt":  "",
                         "name":  "",
                         "h":  13,
                         "color":  "",
                         "text":  "Village",
                         "parent":  1
                     },
                     {
                         "x":  29,
                         "type":  "label",
                         "var":  "",
                         "y":  51,
                         "w":  88,
                         "fmt":  "",
                         "name":  "",
                         "h":  13,
                         "color":  "",
                         "text":  "Nombre",
                         "parent":  1
                     },
                     {
                         "x":  645,
                         "type":  "label",
                         "var":  "",
                         "y":  51,
                         "w":  58,
                         "fmt":  "",
                         "name":  "",
                         "h":  13,
                         "color":  "",
                         "text":  "Repas",
                         "parent":  1
                     },
                     {
                         "x":  647,
                         "type":  "label",
                         "var":  "",
                         "y":  35,
                         "w":  119,
                         "fmt":  "",
                         "name":  "",
                         "h":  13,
                         "color":  "",
                         "text":  "Nom du groupe",
                         "parent":  1
                     },
                     {
                         "x":  10,
                         "type":  "label",
                         "var":  "",
                         "y":  114,
                         "w":  1206,
                         "fmt":  "",
                         "name":  "",
                         "h":  25,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  29,
                         "type":  "label",
                         "var":  "",
                         "y":  67,
                         "w":  184,
                         "fmt":  "",
                         "name":  "",
                         "h":  13,
                         "color":  "",
                         "text":  "Motif annulation",
                         "parent":  1
                     },
                     {
                         "x":  29,
                         "type":  "label",
                         "var":  "",
                         "y":  19,
                         "w":  112,
                         "fmt":  "",
                         "name":  "",
                         "h":  13,
                         "color":  "",
                         "text":  "Lieu de séjour",
                         "parent":  1
                     },
                     {
                         "x":  678,
                         "type":  "label",
                         "var":  "",
                         "y":  19,
                         "w":  88,
                         "fmt":  "",
                         "name":  "",
                         "h":  13,
                         "color":  "",
                         "text":  "Date de fin",
                         "parent":  1
                     },
                     {
                         "x":  149,
                         "type":  "combobox",
                         "var":  "",
                         "y":  19,
                         "w":  485,
                         "fmt":  "",
                         "name":  "vhp_lieu_sejour",
                         "h":  13,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  770,
                         "type":  "edit",
                         "var":  "",
                         "y":  19,
                         "w":  157,
                         "fmt":  "DD/MM/YYYYZ",
                         "name":  "v.Date de fin_0001",
                         "h":  13,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  937,
                         "type":  "button",
                         "var":  "",
                         "y":  19,
                         "w":  28,
                         "fmt":  "...",
                         "name":  "Bt.DateFIn",
                         "h":  13,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  149,
                         "type":  "combobox",
                         "var":  "",
                         "y":  35,
                         "w":  485,
                         "fmt":  "",
                         "name":  "vhp_code_repas_nenc_vil",
                         "h":  13,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  770,
                         "type":  "edit",
                         "var":  "",
                         "y":  35,
                         "w":  432,
                         "fmt":  "U50",
                         "name":  "effq_groupe",
                         "h":  13,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  149,
                         "type":  "edit",
                         "var":  "",
                         "y":  51,
                         "w":  64,
                         "fmt":  "6Z",
                         "name":  "V.Nb repas",
                         "h":  13,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  770,
                         "type":  "combobox",
                         "var":  "",
                         "y":  51,
                         "w":  210,
                         "fmt":  "",
                         "name":  "effq_repas",
                         "h":  13,
                         "color":  "",
                         "text":  "DIN,DEJ,DDE",
                         "parent":  1
                     },
                     {
                         "x":  28,
                         "type":  "edit",
                         "var":  "",
                         "y":  83,
                         "w":  1165,
                         "fmt":  "",
                         "name":  "effq_motif_annulation",
                         "h":  13,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  887,
                         "type":  "button",
                         "var":  "",
                         "y":  117,
                         "w":  154,
                         "fmt":  "\u0026Annuler",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  1046,
                         "type":  "button",
                         "var":  "",
                         "y":  117,
                         "w":  154,
                         "fmt":  "\u0026Valider",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "381.1.1.1",
    "height":  148
}
-->

<details>
<summary><strong>Champs : 7 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 149,19 | vhp_lieu_sejour | - | combobox |
| 770,19 | v.Date de fin_0001 | - | edit |
| 149,35 | vhp_code_repas_nenc_vil | - | combobox |
| 770,35 | effq_groupe | - | edit |
| 149,51 | V.Nb repas | - | edit |
| 770,51 | effq_repas | - | combobox |
| 28,83 | effq_motif_annulation | - | edit |

</details>

<details>
<summary><strong>Boutons : 3 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| ... | 937,19 | Bouton fonctionnel |
| Annuler | 887,117 | Annule et retour au menu |
| Valider | 1046,117 | Valide la saisie et enregistre |

</details>

## 9. NAVIGATION

### 9.1 Enchainement des ecrans

```mermaid
flowchart TD
    START([Entree])
    style START fill:#3fb950
    VF2[381 Repas non encaissés...]
    style VF2 fill:#58a6ff
    VF19[381.1 Liste]
    style VF19 fill:#58a6ff
    VF20[381.1.1 Creation]
    style VF20 fill:#58a6ff
    EXT63[IDE 63 Calcul JH]
    style EXT63 fill:#3fb950
    EXT68[IDE 68 Qualite et Comp...]
    style EXT68 fill:#3fb950
    FIN([Sortie])
    style FIN fill:#f85149
    START --> VF2
    VF2 -->|Calcul de donnees| EXT63
    VF2 -->|Sous-programme| EXT68
    EXT68 --> FIN
```

**Detail par enchainement :**

| Depuis | Action | Vers | Retour |
|--------|--------|------|--------|
| Repas non encaissés au village | Calcul de donnees | [Calcul JH (IDE 63)](PBG-IDE-63.md) | Retour ecran |
| Repas non encaissés au village | Sous-programme | [Qualite et Complements (IDE 68)](PBG-IDE-68.md) | Retour ecran |

### 9.3 Structure hierarchique (4 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **381.1** | [**Repas non encaissés au village** (381)](#t2) [mockup](#ecran-t2) | MDI | 1102x263 | Traitement |
| 381.1.1 | [Liste (381.1)](#t19) [mockup](#ecran-t19) | Modal | 1080x179 | |
| 381.1.2 | [suppresion ligne (381.1.2)](#t21) | - | - | |
| **381.2** | [**Creation** (381.1.1)](#t20) [mockup](#ecran-t20) | - | 1226x148 | Creation |

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

### Tables utilisees (2)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 826 | wording_mention_legal |  | DB |   |   | L | 2 |
| 827 | lg_vente_facture | Donnees de ventes | DB | R | **W** |   | 3 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 827 - lg_vente_facture (R/**W**) - 3 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | Bt.Modification | W | Alpha |
| B | Bt.Création | W | Alpha |
| C | Bt.Annulation | W | Alpha |
| D | V.Confirm annulation | W | Numeric |
| E | v.Date de fin | W | Date |
| F | Bt.DateFIn | W | Alpha |
| G | v.qualite | W | Unicode |
| H | v.complement qualite | W | Unicode |
| I | V.Btn Valider | W | Alpha |
| J | V.Existe DDE ? | W | Logical |
| K | V.Existe Repas DEJ ou DIN ? | W | Logical |

</details>

## 11. VARIABLES

### 11.1 Variables de session (8)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| B | V.Date de consommation | Date | 2x session |
| E | V.Affiche ligne ? | Logical | - |
| F | V.Modif effectuee ? | Logical | - |
| G | V.Affiche recalcul | Logical | - |
| H | v.complement qualite | Unicode | - |
| I | V.Btn Valider | Alpha | - |
| J | V.Existe DDE ? | Logical | - |
| K | V.Existe Repas DEJ ou DIN ? | Logical | - |

### 11.2 Autres (3)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | W1-Fin de Tache | Alpha | - |
| C | Bt.Date | Alpha | - |
| D | Bt.Consultation | Alpha | - |

## 12. EXPRESSIONS

**20 / 20 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONSTANTE | 4 | 0 |
| DATE | 2 | 0 |
| CONDITION | 4 | 0 |
| REFERENCE_VG | 1 | 0 |
| CAST_LOGIQUE | 2 | 0 |
| OTHER | 7 | 0 |

### 12.2 Expressions cles par type

#### CONSTANTE (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 18 | `'C'` | - |
| CONSTANTE | 19 | `'M'` | - |
| CONSTANTE | 3 | `'...'` | - |
| CONSTANTE | 6 | `'REPAS'` | - |

#### DATE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| DATE | 11 | `Date()-1` | - |
| DATE | 2 | `Date()` | - |

#### CONDITION (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 5 | `LastClicked()<>'b_date'` | - |
| CONDITION | 20 | `[AJ]=6` | - |
| CONDITION | 10 | `V.Date de consommation [B]<BOM(Date()) AND Date()>BOM(Date()) OR V.Date de consommation [B]<BOM(Date()-1) AND Date()=BOM(Date())` | - |
| CONDITION | 4 | `V.Date de consommation [B]=0` | - |

#### REFERENCE_VG (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 1 | `VG21` | - |

#### CAST_LOGIQUE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 9 | `'FALSE'LOG` | - |
| CAST_LOGIQUE | 7 | `'TRUE'LOG` | - |

#### OTHER (7 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 15 | `MlsTrans('Recalcul effectif en cours...')` | - |
| OTHER | 16 | `[CW]` | - |
| OTHER | 17 | `{1,2}` | - |
| OTHER | 14 | `SetCrsr(1)` | - |
| OTHER | 8 | `[CR]` | - |
| ... | | *+2 autres* | |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

**Chemin**: (pas de callers directs)

```mermaid
graph LR
    T381[381 Repas non encaissé...]
    style T381 fill:#58a6ff
    NONE[Aucun caller]
    NONE -.-> T381
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| - | (aucun) | - |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T381[381 Repas non encaissé...]
    style T381 fill:#58a6ff
    C63[63 Calcul JH]
    T381 --> C63
    style C63 fill:#3fb950
    C68[68 Qualite et Complements]
    T381 --> C68
    style C68 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [63](PBG-IDE-63.md) | Calcul JH | 1 | Calcul de donnees |
| [68](PBG-IDE-68.md) | Qualite et Complements | 1 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 203 | Taille moyenne |
| Expressions | 20 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 2 | Peu de dependances |
| Ecrans visibles | 3 | Quelques ecrans |
| Code desactive | 0.5% (1 / 203) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (3 taches: 2 ecrans, 1 traitement)

- **Strategie** : Orchestrateur avec 2 ecrans (Razor/React) et 1 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 2 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Creation (1 tache: 1 ecran, 0 traitement)

- **Strategie** : Repository pattern avec Entity Framework Core.
- Insertion via `IRepository<T>.CreateAsync()`

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| lg_vente_facture | Table WRITE (Database) | 2x | Schema + repository |
| [Qualite et Complements (IDE 68)](PBG-IDE-68.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Calcul JH (IDE 63)](PBG-IDE-63.md) | Sous-programme | 1x | Normale - Calcul de donnees |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 11:33*
