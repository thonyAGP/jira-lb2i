# ADH IDE 16 - Browse - Countries iso

> **Analyse**: Phases 1-4 2026-02-07 03:39 -> 01:18 (21h38min) | Assemblage 01:18
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | ADH |
| IDE Position | 16 |
| Nom Programme | Browse - Countries iso |
| Fichier source | `Prg_16.xml` |
| Dossier IDE | General |
| Taches | 4 (3 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 0 |
| Complexite | **BASSE** (score 7/100) |

## 2. DESCRIPTION FONCTIONNELLE

# ADH IDE 16 - Browse - Countries iso

ADH IDE 16 est un programme de consultation (Browse) qui affiche une liste des pays avec leurs codes ISO. Appelé depuis le menu Data Catching (IDE 7), il permet de consulter et potentiellement gérer les codes de pays normalisés dans le système.

Le programme structure les données à partir de la table `type_repas_nenc_vill` (bien que le nom soit trompeur - c'est une table de référence pays). Il propose une interface de navigation standard avec trois tâches nommées "List of countries", probablement pour différents modes de consultation ou filtres sur les données de pays.

Ce type de browse est typiquement utilisé dans les systèmes de gestion pour maintenir les référentiels de données transversales (pays, devises, langues, etc.). Les utilisateurs peuvent y consulter la liste complète des codes ISO pays disponibles dans le système, essentiels pour les formulaires d'identification, les adresses ou les configurations multilingues.

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (4 taches)

Traitements internes.

---

#### <a id="t1"></a>16 - Browse - Countries iso [[ECRAN]](#ecran-t1)

**Role** : Traitement : Browse - Countries iso.
**Ecran** : 537 x 331 DLU (MDI) | [Voir mockup](#ecran-t1)

<details>
<summary>3 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [16.1](#t2) | List of countries **[[ECRAN]](#ecran-t2)** | Traitement |
| [16.2](#t3) | List of countries **[[ECRAN]](#ecran-t3)** | Traitement |
| [16.3](#t4) | List of countries **[[ECRAN]](#ecran-t4)** | Traitement |

</details>

---

#### <a id="t2"></a>16.1 - List of countries [[ECRAN]](#ecran-t2)

**Role** : Traitement : List of countries.
**Ecran** : 537 x 331 DLU (MDI) | [Voir mockup](#ecran-t2)

---

#### <a id="t3"></a>16.2 - List of countries [[ECRAN]](#ecran-t3)

**Role** : Traitement : List of countries.
**Ecran** : 537 x 331 DLU (MDI) | [Voir mockup](#ecran-t3)

---

#### <a id="t4"></a>16.3 - List of countries [[ECRAN]](#ecran-t4)

**Role** : Traitement : List of countries.
**Ecran** : 537 x 331 DLU (MDI) | [Voir mockup](#ecran-t4)


## 5. REGLES METIER

3 regles identifiees:

### Autres (3 regles)

#### <a id="rm-RM-001"></a>[RM-001] Condition: parametre LANGUAGE different de 'FRE'

| Element | Detail |
|---------|--------|
| **Condition** | `GetParam ('LANGUAGE')<>'FRE'` |
| **Si vrai** | Action si LANGUAGE <> 'FRE' |
| **Expression source** | Expression 1 : `GetParam ('LANGUAGE')<>'FRE'` |
| **Exemple** | Si GetParam ('LANGUAGE')<>'FRE' â†’ Action si LANGUAGE <> 'FRE' |

#### <a id="rm-RM-002"></a>[RM-002] Condition: parametre LANGUAGE egale 'FRE'

| Element | Detail |
|---------|--------|
| **Condition** | `GetParam ('LANGUAGE')='FRE'` |
| **Si vrai** | Action si LANGUAGE = 'FRE' |
| **Expression source** | Expression 2 : `GetParam ('LANGUAGE')='FRE'` |
| **Exemple** | Si GetParam ('LANGUAGE')='FRE' â†’ Action si LANGUAGE = 'FRE' |

#### <a id="rm-RM-003"></a>[RM-003] Condition: parametre LANGUAGE egale 'SPA'

| Element | Detail |
|---------|--------|
| **Condition** | `GetParam ('LANGUAGE')='SPA'` |
| **Si vrai** | Action si LANGUAGE = 'SPA' |
| **Expression source** | Expression 3 : `GetParam ('LANGUAGE')='SPA'` |
| **Exemple** | Si GetParam ('LANGUAGE')='SPA' â†’ Action si LANGUAGE = 'SPA' |

## 6. CONTEXTE

- **Appele par**: [Menu Data Catching (IDE 7)](ADH-IDE-7.md)
- **Appelle**: 0 programmes | **Tables**: 1 (W:1 R:0 L:0) | **Taches**: 4 | **Expressions**: 3

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (3 / 4)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 16.1 | 16.1 | List of countries | MDI | 537 | 331 | Traitement |
| 2 | 16.2 | 16.2 | List of countries | MDI | 537 | 331 | Traitement |
| 3 | 16.3 | 16.3 | List of countries | MDI | 537 | 331 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t2"></a>16.1 - List of countries
**Tache** : [16.1](#t2) | **Type** : MDI | **Dimensions** : 537 x 331 DLU
**Bloc** : Traitement | **Titre IDE** : List of countries

<!-- FORM-DATA:
{
    "width":  537,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  2,
                         "type":  "label",
                         "var":  "",
                         "y":  1,
                         "w":  532,
                         "fmt":  "",
                         "name":  "",
                         "h":  39,
                         "color":  "200",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  21,
                         "type":  "label",
                         "var":  "",
                         "y":  13,
                         "w":  512,
                         "fmt":  "",
                         "name":  "",
                         "h":  14,
                         "color":  "205",
                         "text":  "Please choose your country of residence from the list and click \"Select\"",
                         "parent":  1
                     },
                     {
                         "x":  59,
                         "type":  "label",
                         "var":  "",
                         "y":  48,
                         "w":  117,
                         "fmt":  "",
                         "name":  "",
                         "h":  13,
                         "color":  "201",
                         "text":  "Countries",
                         "parent":  null
                     },
                     {
                         "x":  78,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "110",
                         "w":  323,
                         "y":  64,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  19,
                         "h":  209,
                         "cols":  [
                                      {
                                          "title":  "",
                                          "layer":  1,
                                          "w":  309
                                      }
                                  ],
                         "rows":  1
                     },
                     {
                         "x":  90,
                         "type":  "edit",
                         "var":  "",
                         "y":  67,
                         "w":  293,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "205",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  401,
                         "type":  "button",
                         "var":  "",
                         "y":  63,
                         "w":  60,
                         "fmt":  "ñ",
                         "name":  "",
                         "h":  106,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  473,
                         "type":  "button",
                         "var":  "",
                         "y":  63,
                         "w":  60,
                         "fmt":  "Ù",
                         "name":  "",
                         "h":  106,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  401,
                         "type":  "button",
                         "var":  "",
                         "y":  170,
                         "w":  60,
                         "fmt":  "ò",
                         "name":  "",
                         "h":  102,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  473,
                         "type":  "button",
                         "var":  "",
                         "y":  170,
                         "w":  60,
                         "fmt":  "Ú",
                         "name":  "",
                         "h":  102,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  41,
                         "type":  "button",
                         "var":  "",
                         "y":  296,
                         "w":  93,
                         "fmt":  "Exit",
                         "name":  "",
                         "h":  29,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  402,
                         "type":  "button",
                         "var":  "",
                         "y":  296,
                         "w":  93,
                         "fmt":  "Select",
                         "name":  "",
                         "h":  29,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  96,
                         "type":  "image",
                         "var":  "",
                         "y":  63,
                         "w":  311,
                         "fmt":  "",
                         "name":  "",
                         "h":  234,
                         "color":  "6",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "16.1",
    "height":  331
}
-->

<details>
<summary><strong>Champs : 1 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 90,67 | (sans nom) | - | edit |

</details>

<details>
<summary><strong>Boutons : 6 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| ñ | 401,63 | Bouton fonctionnel |
| Ù | 473,63 | Bouton fonctionnel |
| ò | 401,170 | Bouton fonctionnel |
| Ú | 473,170 | Bouton fonctionnel |
| Exit | 41,296 | Quitte le programme |
| Select | 402,296 | Ouvre la selection |

</details>

---

#### <a id="ecran-t3"></a>16.2 - List of countries
**Tache** : [16.2](#t3) | **Type** : MDI | **Dimensions** : 537 x 331 DLU
**Bloc** : Traitement | **Titre IDE** : List of countries

<!-- FORM-DATA:
{
    "width":  537,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  2,
                         "type":  "label",
                         "var":  "",
                         "y":  1,
                         "w":  532,
                         "fmt":  "",
                         "name":  "",
                         "h":  39,
                         "color":  "200",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  16,
                         "type":  "label",
                         "var":  "",
                         "y":  13,
                         "w":  516,
                         "fmt":  "",
                         "name":  "",
                         "h":  14,
                         "color":  "205",
                         "text":  "Veuillez s\u0027il vous plait, choisir, votre pays de résidence dans la liste, et appuyer sur \"Select\"",
                         "parent":  1
                     },
                     {
                         "x":  59,
                         "type":  "label",
                         "var":  "",
                         "y":  48,
                         "w":  117,
                         "fmt":  "",
                         "name":  "",
                         "h":  13,
                         "color":  "201",
                         "text":  "Pays",
                         "parent":  null
                     },
                     {
                         "x":  78,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "205",
                         "w":  323,
                         "y":  64,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  19,
                         "h":  209,
                         "cols":  [
                                      {
                                          "title":  "",
                                          "layer":  1,
                                          "w":  309
                                      }
                                  ],
                         "rows":  1
                     },
                     {
                         "x":  90,
                         "type":  "edit",
                         "var":  "",
                         "y":  67,
                         "w":  293,
                         "fmt":  "U30",
                         "name":  "",
                         "h":  12,
                         "color":  "205",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  401,
                         "type":  "button",
                         "var":  "",
                         "y":  63,
                         "w":  60,
                         "fmt":  "ñ",
                         "name":  "",
                         "h":  106,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  473,
                         "type":  "button",
                         "var":  "",
                         "y":  63,
                         "w":  60,
                         "fmt":  "Ù",
                         "name":  "",
                         "h":  106,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  401,
                         "type":  "button",
                         "var":  "",
                         "y":  170,
                         "w":  60,
                         "fmt":  "ò",
                         "name":  "",
                         "h":  102,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  473,
                         "type":  "button",
                         "var":  "",
                         "y":  170,
                         "w":  60,
                         "fmt":  "Ú",
                         "name":  "",
                         "h":  102,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  41,
                         "type":  "button",
                         "var":  "",
                         "y":  296,
                         "w":  93,
                         "fmt":  "Retour",
                         "name":  "",
                         "h":  29,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  402,
                         "type":  "button",
                         "var":  "",
                         "y":  296,
                         "w":  93,
                         "fmt":  "Selectionner",
                         "name":  "",
                         "h":  29,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  96,
                         "type":  "image",
                         "var":  "",
                         "y":  63,
                         "w":  311,
                         "fmt":  "",
                         "name":  "",
                         "h":  234,
                         "color":  "6",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "16.2",
    "height":  331
}
-->

<details>
<summary><strong>Champs : 1 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 90,67 | U30 | - | edit |

</details>

<details>
<summary><strong>Boutons : 6 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| ñ | 401,63 | Bouton fonctionnel |
| Ù | 473,63 | Bouton fonctionnel |
| ò | 401,170 | Bouton fonctionnel |
| Ú | 473,170 | Bouton fonctionnel |
| Retour | 41,296 | Annule et retour au menu |
| Selectionner | 402,296 | Ouvre la selection |

</details>

---

#### <a id="ecran-t4"></a>16.3 - List of countries
**Tache** : [16.3](#t4) | **Type** : MDI | **Dimensions** : 537 x 331 DLU
**Bloc** : Traitement | **Titre IDE** : List of countries

<!-- FORM-DATA:
{
    "width":  537,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  2,
                         "type":  "label",
                         "var":  "",
                         "y":  1,
                         "w":  532,
                         "fmt":  "",
                         "name":  "",
                         "h":  39,
                         "color":  "200",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  16,
                         "type":  "label",
                         "var":  "",
                         "y":  13,
                         "w":  516,
                         "fmt":  "",
                         "name":  "",
                         "h":  14,
                         "color":  "205",
                         "text":  "Veuillez s\u0027il vous plait, choisir, votre pays de résidence dans la liste, et appuyer sur \"Select\"",
                         "parent":  1
                     },
                     {
                         "x":  59,
                         "type":  "label",
                         "var":  "",
                         "y":  48,
                         "w":  117,
                         "fmt":  "",
                         "name":  "",
                         "h":  13,
                         "color":  "201",
                         "text":  "Pays",
                         "parent":  null
                     },
                     {
                         "x":  78,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "205",
                         "w":  323,
                         "y":  64,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  19,
                         "h":  209,
                         "cols":  [
                                      {
                                          "title":  "",
                                          "layer":  1,
                                          "w":  309
                                      }
                                  ],
                         "rows":  1
                     },
                     {
                         "x":  90,
                         "type":  "edit",
                         "var":  "",
                         "y":  67,
                         "w":  293,
                         "fmt":  "U30",
                         "name":  "",
                         "h":  12,
                         "color":  "205",
                         "text":  "",
                         "parent":  7
                     },
                     {
                         "x":  401,
                         "type":  "button",
                         "var":  "",
                         "y":  63,
                         "w":  60,
                         "fmt":  "ñ",
                         "name":  "",
                         "h":  106,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  473,
                         "type":  "button",
                         "var":  "",
                         "y":  63,
                         "w":  60,
                         "fmt":  "Ù",
                         "name":  "",
                         "h":  106,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  401,
                         "type":  "button",
                         "var":  "",
                         "y":  170,
                         "w":  60,
                         "fmt":  "ò",
                         "name":  "",
                         "h":  102,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  473,
                         "type":  "button",
                         "var":  "",
                         "y":  170,
                         "w":  60,
                         "fmt":  "Ú",
                         "name":  "",
                         "h":  102,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  41,
                         "type":  "button",
                         "var":  "",
                         "y":  296,
                         "w":  93,
                         "fmt":  "Retour",
                         "name":  "",
                         "h":  29,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  402,
                         "type":  "button",
                         "var":  "",
                         "y":  296,
                         "w":  93,
                         "fmt":  "Selectionner",
                         "name":  "",
                         "h":  29,
                         "color":  "110",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  96,
                         "type":  "image",
                         "var":  "",
                         "y":  63,
                         "w":  311,
                         "fmt":  "",
                         "name":  "",
                         "h":  234,
                         "color":  "6",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "16.3",
    "height":  331
}
-->

<details>
<summary><strong>Champs : 1 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 90,67 | U30 | - | edit |

</details>

<details>
<summary><strong>Boutons : 6 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| ñ | 401,63 | Bouton fonctionnel |
| Ù | 473,63 | Bouton fonctionnel |
| ò | 401,170 | Bouton fonctionnel |
| Ú | 473,170 | Bouton fonctionnel |
| Retour | 41,296 | Annule et retour au menu |
| Selectionner | 402,296 | Ouvre la selection |

</details>

## 9. NAVIGATION

### 9.1 Enchainement des ecrans

```mermaid
flowchart TD
    START([Entree])
    style START fill:#3fb950
    VF2[16.1 List of countries]
    style VF2 fill:#58a6ff
    VF3[16.2 List of countries]
    style VF3 fill:#58a6ff
    VF4[16.3 List of countries]
    style VF4 fill:#58a6ff
    FIN([Sortie])
    style FIN fill:#f85149
    START --> VF2
    VF2 --> FIN
```

**Detail par enchainement :**

| Depuis | Action | Vers | Retour |
|--------|--------|------|--------|

### 9.3 Structure hierarchique (4 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **16.1** | [**Browse - Countries iso** (16)](#t1) [mockup](#ecran-t1) | MDI | 537x331 | Traitement |
| 16.1.1 | [List of countries (16.1)](#t2) [mockup](#ecran-t2) | MDI | 537x331 | |
| 16.1.2 | [List of countries (16.2)](#t3) [mockup](#ecran-t3) | MDI | 537x331 | |
| 16.1.3 | [List of countries (16.3)](#t4) [mockup](#ecran-t4) | MDI | 537x331 | |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[ANG]
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

### Tables utilisees (1)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 784 | type_repas_nenc_vill |  | DB |   | **W** |   | 3 |

### Colonnes par table (0 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 784 - type_repas_nenc_vill (**W**) - 3 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Autres (2)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| EN | PARAM LANGUAGE | Alpha | - |
| EO | PARAM COUNTRY CODE ISO | Alpha | - |

## 12. EXPRESSIONS

**3 / 3 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONDITION | 3 | 3 |

### 12.2 Expressions cles par type

#### CONDITION (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 3 | `GetParam ('LANGUAGE')='SPA'` | [RM-003](#rm-RM-003) |
| CONDITION | 2 | `GetParam ('LANGUAGE')='FRE'` | [RM-002](#rm-RM-002) |
| CONDITION | 1 | `GetParam ('LANGUAGE')<>'FRE'` | [RM-001](#rm-RM-001) |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Menu Data Catching (IDE 7)](ADH-IDE-7.md) -> **Browse - Countries iso (IDE 16)**

```mermaid
graph LR
    T16[16 Browse - Countries iso]
    style T16 fill:#58a6ff
    CC7[7 Menu Data Catching]
    style CC7 fill:#8b5cf6
    CC7 --> T16
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [7](ADH-IDE-7.md) | Menu Data Catching | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T16[16 Browse - Countries iso]
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
| Lignes de logique | 43 | Programme compact |
| Expressions | 3 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 3 | Quelques ecrans |
| Code desactive | 0% (0 / 43) | Code sain |
| Regles metier | 3 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (4 taches: 4 ecrans, 0 traitement)

- **Strategie** : 4 composant(s) UI (Razor/React) avec formulaires et validation.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| type_repas_nenc_vill | Table WRITE (Database) | 3x | Schema + repository |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-08 01:18*
