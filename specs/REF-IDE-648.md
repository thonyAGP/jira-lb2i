# REF IDE 648 - Create TAI Comptes speciaux

> **Analyse**: Phases 1-4 2026-02-03 13:24 -> 13:24 (15s) | Assemblage 13:24
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | REF |
| IDE Position | 648 |
| Nom Programme | Create TAI Comptes speciaux |
| Fichier source | `Prg_648.xml` |
| Dossier IDE | Comptabilite |
| Taches | 5 (2 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 4 |

## 2. DESCRIPTION FONCTIONNELLE

**Create TAI Comptes speciaux** assure la gestion complete de ce processus, accessible depuis [Comptes speciaux (IDE 647)](REF-IDE-647.md).

Le flux de traitement s'organise en **2 blocs fonctionnels** :

- **Traitement** (4 taches) : traitements metier divers
- **Creation** (1 tache) : insertion d'enregistrements en base (mouvements, prestations)

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (4 taches)

- **648** - Gratuites GM
- **648.1** - Forfaits TAI **[[ECRAN]](#ecran-t2)**
- **648.1.1** - Liste des Forfaits NA **[[ECRAN]](#ecran-t3)**
- **648.1.2** - Existe Forfait ?

Delegue a : [Recuperation du titre (IDE 658)](REF-IDE-658.md), [Combo - type credit conso (IDE 781)](REF-IDE-781.md)

#### Phase 2 : Creation (1 tache)

- **648.2** - Creation TAIGM

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (4 taches)

Traitements internes.

---

#### <a id="t1"></a>648 - Gratuites GM

**Role** : Traitement : Gratuites GM.

<details>
<summary>3 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [648.1](#t2) | Forfaits TAI **[[ECRAN]](#ecran-t2)** | Traitement |
| [648.1.1](#t3) | Liste des Forfaits NA **[[ECRAN]](#ecran-t3)** | Traitement |
| [648.1.2](#t4) | Existe Forfait ? | Traitement |

</details>
**Delegue a** : [Recuperation du titre (IDE 658)](REF-IDE-658.md), [Combo - type credit conso (IDE 781)](REF-IDE-781.md)

---

#### <a id="t2"></a>648.1 - Forfaits TAI [[ECRAN]](#ecran-t2)

**Role** : Traitement : Forfaits TAI.
**Ecran** : 1260 x 314 DLU (MDI) | [Voir mockup](#ecran-t2)
**Delegue a** : [Recuperation du titre (IDE 658)](REF-IDE-658.md), [Combo - type credit conso (IDE 781)](REF-IDE-781.md)

---

#### <a id="t3"></a>648.1.1 - Liste des Forfaits NA [[ECRAN]](#ecran-t3)

**Role** : Traitement : Liste des Forfaits NA.
**Ecran** : 873 x 99 DLU (Modal) | [Voir mockup](#ecran-t3)
**Delegue a** : [Recuperation du titre (IDE 658)](REF-IDE-658.md), [Combo - type credit conso (IDE 781)](REF-IDE-781.md)

---

#### <a id="t4"></a>648.1.2 - Existe Forfait ?

**Role** : Traitement : Existe Forfait ?.
**Variables liees** : X (v.code forfait)
**Delegue a** : [Recuperation du titre (IDE 658)](REF-IDE-658.md), [Combo - type credit conso (IDE 781)](REF-IDE-781.md)


### 3.2 Creation (1 tache)

Insertion de nouveaux enregistrements en base.

---

#### <a id="t5"></a>648.2 - Creation TAIGM

**Role** : Creation d'enregistrement : Creation TAIGM.
**Variables liees** : U (v.confirmation creation)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Comptes speciaux (IDE 647)](REF-IDE-647.md)
- **Appelle**: 4 programmes | **Tables**: 5 (W:0 R:3 L:3) | **Taches**: 5 | **Expressions**: 11

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (2 / 5)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 648.1 | 648.1 | Forfaits TAI | MDI | 1260 | 314 | Traitement |
| 2 | 648.1.1 | 648.1.1 | Liste des Forfaits NA | Modal | 873 | 99 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t2"></a>648.1 - Forfaits TAI
**Tache** : [648.1](#t2) | **Type** : MDI | **Dimensions** : 1260 x 314 DLU
**Bloc** : Traitement | **Titre IDE** : Forfaits TAI

<!-- FORM-DATA:
{
    "width":  1260,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  1,
                         "w":  1261,
                         "fmt":  "",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  44,
                         "type":  "label",
                         "var":  "",
                         "y":  26,
                         "w":  1178,
                         "fmt":  "",
                         "name":  "",
                         "h":  14,
                         "color":  "5",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  543,
                         "type":  "label",
                         "var":  "",
                         "y":  170,
                         "w":  188,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "142",
                         "text":  "Forfait TAI",
                         "parent":  null
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  293,
                         "w":  1261,
                         "fmt":  "",
                         "name":  "",
                         "h":  21,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  195,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  15,
                         "color":  "6",
                         "w":  870,
                         "y":  25,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  15,
                         "h":  119,
                         "cols":  [
                                      {
                                          "title":  "Nom",
                                          "layer":  1,
                                          "w":  214
                                      },
                                      {
                                          "title":  "Prénom",
                                          "layer":  2,
                                          "w":  140
                                      },
                                      {
                                          "title":  "Date début",
                                          "layer":  3,
                                          "w":  147
                                      },
                                      {
                                          "title":  "Date fin",
                                          "layer":  4,
                                          "w":  147
                                      },
                                      {
                                          "title":  "TAI actif",
                                          "layer":  5,
                                          "w":  191
                                      }
                                  ],
                         "rows":  5
                     },
                     {
                         "x":  200,
                         "type":  "label",
                         "var":  "",
                         "y":  145,
                         "w":  285,
                         "fmt":  "",
                         "name":  "",
                         "h":  35,
                         "color":  "",
                         "text":  "Saisie",
                         "parent":  null
                     },
                     {
                         "x":  773,
                         "type":  "label",
                         "var":  "",
                         "y":  145,
                         "w":  287,
                         "fmt":  "",
                         "name":  "",
                         "h":  35,
                         "color":  "",
                         "text":  "Impression",
                         "parent":  null
                     },
                     {
                         "x":  1088,
                         "type":  "button",
                         "var":  "",
                         "y":  295,
                         "w":  168,
                         "fmt":  "",
                         "name":  "bouton Quitter",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  203,
                         "type":  "edit",
                         "var":  "",
                         "y":  42,
                         "w":  200,
                         "fmt":  "",
                         "name":  "SPC Nom",
                         "h":  11,
                         "color":  "6",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  419,
                         "type":  "edit",
                         "var":  "",
                         "y":  42,
                         "w":  122,
                         "fmt":  "",
                         "name":  "SPC Prenom",
                         "h":  11,
                         "color":  "6",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  563,
                         "type":  "edit",
                         "var":  "",
                         "y":  42,
                         "w":  120,
                         "fmt":  "DD/MM/YYYY",
                         "name":  "",
                         "h":  11,
                         "color":  "6",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  714,
                         "type":  "edit",
                         "var":  "",
                         "y":  42,
                         "w":  120,
                         "fmt":  "DD/MM/YYYY",
                         "name":  "",
                         "h":  11,
                         "color":  "6",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  14,
                         "type":  "edit",
                         "var":  "",
                         "y":  5,
                         "w":  396,
                         "fmt":  "30",
                         "name":  "",
                         "h":  11,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  950,
                         "type":  "edit",
                         "var":  "",
                         "y":  5,
                         "w":  298,
                         "fmt":  "WWW DD MMM YYYYT",
                         "name":  "",
                         "h":  11,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  874,
                         "type":  "edit",
                         "var":  "",
                         "y":  42,
                         "w":  154,
                         "fmt":  "30",
                         "name":  "",
                         "h":  11,
                         "color":  "6",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  278,
                         "type":  "button",
                         "var":  "",
                         "y":  159,
                         "w":  129,
                         "fmt":  "Individuel",
                         "name":  "GI",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  852,
                         "type":  "button",
                         "var":  "",
                         "y":  159,
                         "w":  129,
                         "fmt":  "Individuel",
                         "name":  "HI",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "648.1",
    "height":  314
}
-->

<details>
<summary><strong>Champs : 7 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 203,42 | SPC Nom | - | edit |
| 419,42 | SPC Prenom | - | edit |
| 563,42 | DD/MM/YYYY | - | edit |
| 714,42 | DD/MM/YYYY | - | edit |
| 14,5 | 30 | - | edit |
| 950,5 | WWW DD MMM YYYYT | - | edit |
| 874,42 | 30 | - | edit |

</details>

<details>
<summary><strong>Boutons : 3 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Quitter | 1088,295 | Quitte le programme |
| Individuel | 278,159 | Bouton fonctionnel |
| Individuel | 852,159 | Bouton fonctionnel |

</details>

---

#### <a id="ecran-t3"></a>648.1.1 - Liste des Forfaits NA
**Tache** : [648.1.1](#t3) | **Type** : Modal | **Dimensions** : 873 x 99 DLU
**Bloc** : Traitement | **Titre IDE** : Liste des Forfaits NA

<!-- FORM-DATA:
{
    "width":  873,
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
                         "w":  867,
                         "y":  0,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  12,
                         "h":  51,
                         "cols":  [
                                      {
                                          "title":  "Code",
                                          "layer":  1,
                                          "w":  90
                                      },
                                      {
                                          "title":  "Libellé Forfait",
                                          "layer":  2,
                                          "w":  152
                                      },
                                      {
                                          "title":  "Date début",
                                          "layer":  3,
                                          "w":  117
                                      },
                                      {
                                          "title":  "Date fin",
                                          "layer":  4,
                                          "w":  114
                                      },
                                      {
                                          "title":  "Nom",
                                          "layer":  5,
                                          "w":  175
                                      },
                                      {
                                          "title":  "Compte",
                                          "layer":  6,
                                          "w":  179
                                      }
                                  ],
                         "rows":  6
                     },
                     {
                         "x":  250,
                         "type":  "edit",
                         "var":  "",
                         "y":  14,
                         "w":  107,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  6
                     },
                     {
                         "x":  366,
                         "type":  "edit",
                         "var":  "",
                         "y":  14,
                         "w":  104,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  6
                     },
                     {
                         "x":  8,
                         "type":  "edit",
                         "var":  "",
                         "y":  14,
                         "w":  76,
                         "fmt":  "",
                         "name":  "TAI Code Forfait",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  6
                     },
                     {
                         "x":  2,
                         "type":  "edit",
                         "var":  "",
                         "y":  60,
                         "w":  88,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "2",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  633,
                         "type":  "edit",
                         "var":  "",
                         "y":  86,
                         "w":  144,
                         "fmt":  "N12.3Z",
                         "name":  "",
                         "h":  10,
                         "color":  "2",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  2,
                         "type":  "button",
                         "var":  "",
                         "y":  80,
                         "w":  168,
                         "fmt":  "",
                         "name":  "Bouton Supprimer",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  96,
                         "type":  "edit",
                         "var":  "",
                         "y":  14,
                         "w":  137,
                         "fmt":  "30",
                         "name":  "",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  6
                     },
                     {
                         "x":  478,
                         "type":  "edit",
                         "var":  "",
                         "y":  14,
                         "w":  165,
                         "fmt":  "30",
                         "name":  "",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  6
                     },
                     {
                         "x":  654,
                         "type":  "edit",
                         "var":  "",
                         "y":  14,
                         "w":  176,
                         "fmt":  "30",
                         "name":  "",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  6
                     },
                     {
                         "x":  96,
                         "type":  "edit",
                         "var":  "",
                         "y":  60,
                         "w":  168,
                         "fmt":  "30",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  633,
                         "type":  "edit",
                         "var":  "",
                         "y":  60,
                         "w":  144,
                         "fmt":  "30",
                         "name":  "",
                         "h":  10,
                         "color":  "2",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  224,
                         "type":  "edit",
                         "var":  "",
                         "y":  86,
                         "w":  360,
                         "fmt":  "100",
                         "name":  "",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "648.1.1",
    "height":  99
}
-->

<details>
<summary><strong>Champs : 11 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 250,14 | (sans nom) | - | edit |
| 366,14 | (sans nom) | - | edit |
| 8,14 | TAI Code Forfait | - | edit |
| 2,60 | (sans nom) | - | edit |
| 633,86 | N12.3Z | - | edit |
| 96,14 | 30 | - | edit |
| 478,14 | 30 | - | edit |
| 654,14 | 30 | - | edit |
| 96,60 | 30 | - | edit |
| 633,60 | 30 | - | edit |
| 224,86 | 100 | - | edit |

</details>

<details>
<summary><strong>Boutons : 1 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Supprimer | 2,80 | Supprime l'element selectionne |

</details>

## 9. NAVIGATION

### 9.1 Enchainement des ecrans

```mermaid
flowchart TD
    START([Entree])
    style START fill:#3fb950
    VF2[648.1 Forfaits TAI]
    style VF2 fill:#58a6ff
    VF3[648.1.1 Liste des Forfaits NA]
    style VF3 fill:#58a6ff
    EXT658[IDE 658 Recuperation d...]
    style EXT658 fill:#3fb950
    EXT781[IDE 781 Combo - type c...]
    style EXT781 fill:#3fb950
    EXT782[IDE 782 Zoom code TAI]
    style EXT782 fill:#3fb950
    EXT783[IDE 783 Edition TAI NA]
    style EXT783 fill:#3fb950
    FIN([Sortie])
    style FIN fill:#f85149
    START --> VF2
    VF2 -->|Recuperation donnees| EXT658
    VF2 -->|Sous-programme| EXT781
    VF2 -->|Selection/consultation| EXT782
    VF2 -->|Impression ticket/document| EXT783
    EXT783 --> FIN
```

**Detail par enchainement :**

| Depuis | Action | Vers | Retour |
|--------|--------|------|--------|
| Forfaits TAI | Recuperation donnees | [Recuperation du titre (IDE 658)](REF-IDE-658.md) | Retour ecran |
| Forfaits TAI | Sous-programme | [Combo - type credit conso (IDE 781)](REF-IDE-781.md) | Retour ecran |
| Forfaits TAI | Selection/consultation | [Zoom code TAI (IDE 782)](REF-IDE-782.md) | Retour ecran |
| Forfaits TAI | Impression ticket/document | [Edition TAI NA (IDE 783)](REF-IDE-783.md) | Retour ecran |

### 9.3 Structure hierarchique (5 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **648.1** | [**Gratuites GM** (648)](#t1) | MDI | - | Traitement |
| 648.1.1 | [Forfaits TAI (648.1)](#t2) [mockup](#ecran-t2) | MDI | 1260x314 | |
| 648.1.2 | [Liste des Forfaits NA (648.1.1)](#t3) [mockup](#ecran-t3) | Modal | 873x99 | |
| 648.1.3 | [Existe Forfait ? (648.1.2)](#t4) | MDI | - | |
| **648.2** | [**Creation TAIGM** (648.2)](#t5) | MDI | - | Creation |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Affiche CS]
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

### Tables utilisees (5)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 30 | gm-recherche_____gmr | Index de recherche | DB | R |   |   | 1 |
| 34 | hebergement______heb | Hebergement (chambres) | DB | R |   |   | 2 |
| 453 | tai_forfait |  | DB |   |   | L | 1 |
| 454 | tai_gm |  | DB | R |   | L | 4 |
| 758 | comptes_speciaux_spc_cash | Comptes GM (generaux) | DB |   |   | L | 1 |

### Colonnes par table (3 / 3 tables avec colonnes identifiees)

<details>
<summary>Table 30 - gm-recherche_____gmr (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | CURSOR | R | Logical |
| B | ConfirmationSuppression | R | Numeric |
| C | Bouton Supprimer | R | Alpha |

</details>

<details>
<summary>Table 34 - hebergement______heb (R) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | bouton Quitter | R | Alpha |
| B | v.titre | R | Alpha |
| C | v.existe Forfait Actif | R | Logical |
| D | v.existe Forfait | R | Logical |
| E | v.liste Forfait Affichee | R | Logical |

</details>

<details>
<summary>Table 454 - tai_gm (R/L) - 4 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (10)

Variables recues du programme appelant ([Comptes speciaux (IDE 647)](REF-IDE-647.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | p.societe | Alpha | 1x parametre entrant |
| B | p.decimales | Numeric | - |
| C | p.masque-mtt-compte GM | Alpha | - |
| D | p.code-devise | Alpha | - |
| E | p.nom village | Alpha | - |
| F | p.TAI Obligatoire | Alpha | - |
| G | p.nom-gm | Alpha | - |
| H | p.prenom-gm | Alpha | - |
| I | p.code-gm | Numeric | - |
| J | p.filiation | Numeric | - |

### 11.2 Variables de session (10)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| K | v.action | Alpha | - |
| P | v.montant | Numeric | - |
| Q | v.type CS | Alpha | - |
| R | v.date operation | Date | - |
| S | v.heure operation | Time | - |
| T | v.List combo type CS | Alpha | - |
| U | v.confirmation creation | Numeric | [648.2](#t5) |
| V | v.last action sur 2 | Alpha | 2x session |
| W | v.last name | Alpha | - |
| X | v.code forfait | Alpha | - |

### 11.3 Autres (4)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| L | F.qualite | Alpha | - |
| M | F.seminaire | Alpha | - |
| N | F.date du seminaire | Date | - |
| O | F.date au seminaire | Date | - |

<details>
<summary>Toutes les 24 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| P0 | **A** | p.societe | Alpha |
| P0 | **B** | p.decimales | Numeric |
| P0 | **C** | p.masque-mtt-compte GM | Alpha |
| P0 | **D** | p.code-devise | Alpha |
| P0 | **E** | p.nom village | Alpha |
| P0 | **F** | p.TAI Obligatoire | Alpha |
| P0 | **G** | p.nom-gm | Alpha |
| P0 | **H** | p.prenom-gm | Alpha |
| P0 | **I** | p.code-gm | Numeric |
| P0 | **J** | p.filiation | Numeric |
| V. | **K** | v.action | Alpha |
| V. | **P** | v.montant | Numeric |
| V. | **Q** | v.type CS | Alpha |
| V. | **R** | v.date operation | Date |
| V. | **S** | v.heure operation | Time |
| V. | **T** | v.List combo type CS | Alpha |
| V. | **U** | v.confirmation creation | Numeric |
| V. | **V** | v.last action sur 2 | Alpha |
| V. | **W** | v.last name | Alpha |
| V. | **X** | v.code forfait | Alpha |
| Autre | **L** | F.qualite | Alpha |
| Autre | **M** | F.seminaire | Alpha |
| Autre | **N** | F.date du seminaire | Date |
| Autre | **O** | F.date au seminaire | Date |

</details>

## 12. EXPRESSIONS

**11 / 11 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONSTANTE | 3 | 0 |
| DATE | 1 | 0 |
| CONDITION | 4 | 0 |
| CAST_LOGIQUE | 2 | 0 |
| OTHER | 1 | 0 |

### 12.2 Expressions cles par type

#### CONSTANTE (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 10 | `''` | - |
| CONSTANTE | 3 | `'F'` | - |
| CONSTANTE | 1 | `'C'` | - |

#### DATE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| DATE | 8 | `Date ()` | - |

#### CONDITION (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 5 | `v.last action sur 2 [V]='HI'` | - |
| CONDITION | 11 | `v.confirmation creation [U]=6` | - |
| CONDITION | 2 | `p.societe [A]=''` | - |
| CONDITION | 4 | `v.last action sur 2 [V]='GI'` | - |

#### CAST_LOGIQUE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 7 | `'TRUE'LOG` | - |
| CAST_LOGIQUE | 6 | `'FALSE'LOG` | - |

#### OTHER (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 9 | `Time ()` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Comptes speciaux (IDE 647)](REF-IDE-647.md) -> **Create TAI Comptes speciaux (IDE 648)**

```mermaid
graph LR
    T648[648 Create TAI Comptes...]
    style T648 fill:#58a6ff
    CC647[647 Comptes speciaux]
    style CC647 fill:#8b5cf6
    CC647 --> T648
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [647](REF-IDE-647.md) | Comptes speciaux | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T648[648 Create TAI Comptes...]
    style T648 fill:#58a6ff
    C658[658 Recuperation du titre]
    T648 --> C658
    style C658 fill:#3fb950
    C781[781 Combo - type credi...]
    T648 --> C781
    style C781 fill:#3fb950
    C782[782 Zoom code TAI]
    T648 --> C782
    style C782 fill:#3fb950
    C783[783 Edition TAI NA]
    T648 --> C783
    style C783 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [658](REF-IDE-658.md) | Recuperation du titre | 1 | Recuperation donnees |
| [781](REF-IDE-781.md) | Combo - type credit conso | 1 | Sous-programme |
| [782](REF-IDE-782.md) | Zoom code TAI | 1 | Selection/consultation |
| [783](REF-IDE-783.md) | Edition TAI NA | 1 | Impression ticket/document |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 229 | Taille moyenne |
| Expressions | 11 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 4 | Peu de dependances |
| Ecrans visibles | 2 | Quelques ecrans |
| Code desactive | 0% (0 / 229) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (4 taches: 2 ecrans, 2 traitements)

- **Strategie** : Orchestrateur avec 2 ecrans (Razor/React) et 2 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 4 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Creation (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Repository pattern avec Entity Framework Core.
- Insertion via `IRepository<T>.CreateAsync()`

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| [Zoom code TAI (IDE 782)](REF-IDE-782.md) | Sous-programme | 1x | Normale - Selection/consultation |
| [Edition TAI NA (IDE 783)](REF-IDE-783.md) | Sous-programme | 1x | Normale - Impression ticket/document |
| [Recuperation du titre (IDE 658)](REF-IDE-658.md) | Sous-programme | 1x | Normale - Recuperation donnees |
| [Combo - type credit conso (IDE 781)](REF-IDE-781.md) | Sous-programme | 1x | Normale - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 13:24*
