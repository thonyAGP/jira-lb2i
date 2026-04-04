# CAP IDE 26 - Compte les seminaires

> **Analyse**: Phases 1-4 2026-02-03 10:17 -> 10:18 (18s) | Assemblage 10:18
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | CAP |
| IDE Position | 26 |
| Nom Programme | Compte les seminaires |
| Fichier source | `Prg_26.xml` |
| Domaine metier | Comptabilite |
| Taches | 4 (2 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 1 |

## 2. DESCRIPTION FONCTIONNELLE

**Compte les seminaires** assure la gestion complete de ce processus, accessible depuis [Gratuites GM (IDE 25)](CAP-IDE-25.md).

Le flux de traitement s'organise en **3 blocs fonctionnels** :

- **Traitement** (2 taches) : traitements metier divers
- **Consultation** (1 tache) : ecrans de recherche, selection et consultation
- **Creation** (1 tache) : insertion d'enregistrements en base (mouvements, prestations)

**Donnees modifiees** : 1 tables en ecriture (tempo_ecr_previsions).

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (2 taches)

- **26** - cpte seminaire **[[ECRAN]](#ecran-t1)**
- **26.1** - generation des seminaires **[[ECRAN]](#ecran-t2)**

Delegue a : [Recuperation du titre (IDE 41)](CAP-IDE-41.md)

#### Phase 2 : Creation (1 tache)

- **26.1.1** - Creation temp

#### Phase 3 : Consultation (1 tache)

- **26.2** - Choix seminaire **[[ECRAN]](#ecran-t4)**

Delegue a : [Recuperation du titre (IDE 41)](CAP-IDE-41.md)

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| tempo_ecr_previsions | **W** (2 usages) | Table temporaire ecran |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (2 taches)

Traitements internes.

---

#### <a id="t1"></a>26 - cpte seminaire [[ECRAN]](#ecran-t1)

**Role** : Traitement : cpte seminaire.
**Ecran** : 424 x 55 DLU (MDI) | [Voir mockup](#ecran-t1)
**Variables liees** : B (PO Date seminaire du), C (PO Date seminaire au), D (P0 nom seminaire), F (V SEMINAIRE)
**Delegue a** : [Recuperation du titre (IDE 41)](CAP-IDE-41.md)

---

#### <a id="t2"></a>26.1 - generation des seminaires [[ECRAN]](#ecran-t2)

**Role** : Traitement : generation des seminaires.
**Ecran** : 422 x 26 DLU (MDI) | [Voir mockup](#ecran-t2)
**Delegue a** : [Recuperation du titre (IDE 41)](CAP-IDE-41.md)


### 3.2 Creation (1 tache)

Insertion de nouveaux enregistrements en base.

---

#### <a id="t3"></a>26.1.1 - Creation temp

**Role** : Creation d'enregistrement : Creation temp.


### 3.3 Consultation (1 tache)

Ecrans de recherche et consultation.

---

#### <a id="t4"></a>26.2 - Choix seminaire [[ECRAN]](#ecran-t4)

**Role** : Selection par l'operateur : Choix seminaire.
**Ecran** : 442 x 212 DLU (MDI) | [Voir mockup](#ecran-t4)
**Variables liees** : B (PO Date seminaire du), C (PO Date seminaire au), D (P0 nom seminaire), F (V SEMINAIRE)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Gratuites GM (IDE 25)](CAP-IDE-25.md)
- **Appelle**: 1 programmes | **Tables**: 2 (W:1 R:1 L:0) | **Taches**: 4 | **Expressions**: 4

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (2 / 4)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 26.1 | 26.1 | generation des seminaires | MDI | 422 | 26 | Traitement |
| 2 | 26.2 | 26.2 | Choix seminaire | MDI | 442 | 212 | Consultation |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t2"></a>26.1 - generation des seminaires
**Tache** : [26.1](#t2) | **Type** : MDI | **Dimensions** : 422 x 26 DLU
**Bloc** : Traitement | **Titre IDE** : generation des seminaires

<!-- FORM-DATA:
{
    "width":  422,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  119,
                         "type":  "label",
                         "var":  "",
                         "y":  8,
                         "w":  266,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "142",
                         "text":  "Chargement en cours ...",
                         "parent":  null
                     },
                     {
                         "x":  3,
                         "type":  "image",
                         "var":  "",
                         "y":  0,
                         "w":  72,
                         "fmt":  "",
                         "name":  "",
                         "h":  25,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "26.1",
    "height":  26
}
-->

---

#### <a id="ecran-t4"></a>26.2 - Choix seminaire
**Tache** : [26.2](#t4) | **Type** : MDI | **Dimensions** : 442 x 212 DLU
**Bloc** : Consultation | **Titre IDE** : Choix seminaire

<!-- FORM-DATA:
{
    "width":  442,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  2,
                         "type":  "label",
                         "var":  "",
                         "y":  2,
                         "w":  436,
                         "fmt":  "",
                         "name":  "",
                         "h":  17,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  37,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "110",
                         "w":  280,
                         "y":  28,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  14,
                         "h":  144,
                         "cols":  [
                                      {
                                          "title":  "Séminaire",
                                          "layer":  1,
                                          "w":  125
                                      },
                                      {
                                          "title":  "Date début",
                                          "layer":  2,
                                          "w":  73
                                      },
                                      {
                                          "title":  "Date fin",
                                          "layer":  3,
                                          "w":  68
                                      }
                                  ],
                         "rows":  3
                     },
                     {
                         "x":  2,
                         "type":  "label",
                         "var":  "",
                         "y":  186,
                         "w":  436,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  40,
                         "type":  "edit",
                         "var":  "",
                         "y":  42,
                         "w":  119,
                         "fmt":  "",
                         "name":  "SEM Seminaire",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  165,
                         "type":  "edit",
                         "var":  "",
                         "y":  42,
                         "w":  63,
                         "fmt":  "",
                         "name":  "SEM date Debut",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  238,
                         "type":  "edit",
                         "var":  "",
                         "y":  42,
                         "w":  63,
                         "fmt":  "",
                         "name":  "SEM date fin",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  344,
                         "type":  "button",
                         "var":  "",
                         "y":  189,
                         "w":  80,
                         "fmt":  "Selectionner",
                         "name":  "Bouton Edition",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  13,
                         "type":  "edit",
                         "var":  "",
                         "y":  6,
                         "w":  114,
                         "fmt":  "30",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  318,
                         "type":  "edit",
                         "var":  "",
                         "y":  6,
                         "w":  114,
                         "fmt":  "WWW DD MMM YYYYZ",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  1
                     },
                     {
                         "x":  340,
                         "type":  "image",
                         "var":  "",
                         "y":  73,
                         "w":  80,
                         "fmt":  "",
                         "name":  "",
                         "h":  54,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  11,
                         "type":  "button",
                         "var":  "",
                         "y":  189,
                         "w":  80,
                         "fmt":  "\u0026Quitter",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "26.2",
    "height":  212
}
-->

<details>
<summary><strong>Champs : 5 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 40,42 | SEM Seminaire | - | edit |
| 165,42 | SEM date Debut | - | edit |
| 238,42 | SEM date fin | - | edit |
| 13,6 | 30 | - | edit |
| 318,6 | WWW DD MMM YYYYZ | - | edit |

</details>

<details>
<summary><strong>Boutons : 2 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Selectionner | 344,189 | Ouvre la selection |
| Quitter | 11,189 | Quitte le programme |

</details>

## 9. NAVIGATION

### 9.1 Enchainement des ecrans

```mermaid
flowchart TD
    START([Entree])
    style START fill:#3fb950
    VF2[26.1 generation des semi...]
    style VF2 fill:#58a6ff
    VF4[26.2 Choix seminaire]
    style VF4 fill:#58a6ff
    EXT41[IDE 41 Recuperation du...]
    style EXT41 fill:#3fb950
    FIN([Sortie])
    style FIN fill:#f85149
    START --> VF2
    VF2 -->|Recuperation donnees| EXT41
    EXT41 --> FIN
```

**Detail par enchainement :**

| Depuis | Action | Vers | Retour |
|--------|--------|------|--------|
| generation des seminaires | Recuperation donnees | [Recuperation du titre (IDE 41)](CAP-IDE-41.md) | Retour ecran |

### 9.3 Structure hierarchique (4 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **26.1** | [**cpte seminaire** (26)](#t1) [mockup](#ecran-t1) | MDI | 424x55 | Traitement |
| 26.1.1 | [generation des seminaires (26.1)](#t2) [mockup](#ecran-t2) | MDI | 422x26 | |
| **26.2** | [**Creation temp** (26.1.1)](#t3) | MDI | - | Creation |
| **26.3** | [**Choix seminaire** (26.2)](#t4) [mockup](#ecran-t4) | MDI | 442x212 | Consultation |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[generation des seminaires]
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
| 597 | tempo_ecr_previsions | Table temporaire ecran | TMP |   | **W** |   | 2 |
| 745 | pv_serv_lieu_vendeur |  | DB | R |   |   | 1 |

### Colonnes par table (1 / 2 tables avec colonnes identifiees)

<details>
<summary>Table 597 - tempo_ecr_previsions (**W**) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | Bouton Edition | W | Alpha |
| B | V TITRE 9 | W | Alpha |

</details>

<details>
<summary>Table 745 - pv_serv_lieu_vendeur (R) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (4)

Variables recues du programme appelant ([Gratuites GM (IDE 25)](CAP-IDE-25.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P0 Societe | Alpha | - |
| B | PO Date seminaire du | Date | - |
| C | PO Date seminaire au | Date | - |
| D | P0 nom seminaire | Alpha | - |

### 11.2 Variables de session (4)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| E | V ACTION | Alpha | - |
| F | V SEMINAIRE | Alpha | - |
| G | V DATE DEB | Date | - |
| H | V TOTAL | Numeric | - |

## 12. EXPRESSIONS

**4 / 4 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCULATION | 1 | 0 |
| CONSTANTE | 1 | 0 |
| OTHER | 1 | 0 |
| REFERENCE_VG | 1 | 0 |

### 12.2 Expressions cles par type

#### CALCULATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 1 | `'00/00/0000'DATE` | - |

#### CONSTANTE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 2 | `''` | - |

#### OTHER (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 3 | `DbDel ('{597,2}'DSOURCE,'')` | - |

#### REFERENCE_VG (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 4 | `VG1` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Gratuites GM (IDE 25)](CAP-IDE-25.md) -> **Compte les seminaires (IDE 26)**

```mermaid
graph LR
    T26[26 Compte les seminaires]
    style T26 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC31[31 Start]
    style CC31 fill:#f59e0b
    CC32[32 Lancement barre menu]
    style CC32 fill:#f59e0b
    CC30[30 Choix date de Purge]
    style CC30 fill:#f59e0b
    CC37[37 Menu caisse GM - sc...]
    style CC37 fill:#f59e0b
    CC49[49 Menu caisse GM - sc...]
    style CC49 fill:#f59e0b
    CC25[25 Gratuites GM]
    style CC25 fill:#3fb950
    CC37 --> CC25
    CC49 --> CC25
    CC30 --> CC37
    CC32 --> CC37
    CC30 --> CC49
    CC32 --> CC49
    CC31 --> CC30
    CC31 --> CC32
    CC1 --> CC31
    CC25 --> T26
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [25](CAP-IDE-25.md) | Gratuites GM | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T26[26 Compte les seminaires]
    style T26 fill:#58a6ff
    C41[41 Recuperation du titre]
    T26 --> C41
    style C41 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [41](CAP-IDE-41.md) | Recuperation du titre | 2 | Recuperation donnees |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 47 | Programme compact |
| Expressions | 4 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 1 | Peu de dependances |
| Ecrans visibles | 2 | Quelques ecrans |
| Code desactive | 0% (0 / 47) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (2 taches: 2 ecrans, 0 traitement)

- **Strategie** : 2 composant(s) UI (Razor/React) avec formulaires et validation.
- 1 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Creation (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Repository pattern avec Entity Framework Core.
- Insertion via `IRepository<T>.CreateAsync()`

#### Consultation (1 tache: 1 ecran, 0 traitement)

- **Strategie** : Composants de recherche/selection en modales.
- 1 ecran : Choix seminaire

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| tempo_ecr_previsions | Table WRITE (Temp) | 2x | Schema + repository |
| [Recuperation du titre (IDE 41)](CAP-IDE-41.md) | Sous-programme | 2x | Haute - Recuperation donnees |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 10:18*
