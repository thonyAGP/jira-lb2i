# CAB IDE 9 - Verification pooling

> **Analyse**: Phases 1-4 2026-02-03 09:59 -> 09:59 (16s) | Assemblage 09:59
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | CAB |
| IDE Position | 9 |
| Nom Programme | Verification pooling |
| Fichier source | `Prg_9.xml` |
| Domaine metier | General |
| Taches | 8 (2 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 2 |
| :warning: Statut | **ORPHELIN_POTENTIEL** |

## 2. DESCRIPTION FONCTIONNELLE

**Verification pooling** assure la gestion complete de ce processus.

Le flux de traitement s'organise en **2 blocs fonctionnels** :

- **Traitement** (7 taches) : traitements metier divers
- **Validation** (1 tache) : controles et verifications de coherence

**Donnees modifiees** : 1 tables en ecriture (comptes_pour_changer_activite).

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Validation (1 tache)

- **9** - Verification pooling

Delegue a : [Suppression demande verif pool (IDE 7)](CAB-IDE-7.md)

#### Phase 2 : Traitement (7 taches)

- **9.1** - Mise à jour telephone
- **9.2** - Mise à jour monetique
- **9.3** - Traitement en attente **[[ECRAN]](#ecran-t4)**
- **9.3.1** - Veuillez patienter ... **[[ECRAN]](#ecran-t5)**
- **9.4** - Mise à jour telephone
- **9.5** - Mise à jour monetique
- **9.3.2** - Veuillez patienter ... **[[ECRAN]](#ecran-t14)**

Delegue a : [Visualisation pooling (IDE 8)](CAB-IDE-8.md)

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| comptes_pour_changer_activite | R/**W** (6 usages) | Comptes GM (generaux) |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Validation (1 tache)

Controles de coherence : 1 tache verifie les donnees et conditions.

---

#### <a id="t1"></a>9 - Verification pooling

**Role** : Verification : Verification pooling.
**Delegue a** : [Suppression demande verif pool (IDE 7)](CAB-IDE-7.md)


### 3.2 Traitement (7 taches)

Traitements internes.

---

#### <a id="t2"></a>9.1 - Mise à jour telephone

**Role** : Traitement : Mise à jour telephone.
**Delegue a** : [Visualisation pooling (IDE 8)](CAB-IDE-8.md)

---

#### <a id="t3"></a>9.2 - Mise à jour monetique

**Role** : Traitement : Mise à jour monetique.
**Delegue a** : [Visualisation pooling (IDE 8)](CAB-IDE-8.md)

---

#### <a id="t4"></a>9.3 - Traitement en attente [[ECRAN]](#ecran-t4)

**Role** : Traitement : Traitement en attente.
**Ecran** : 442 x 48 DLU (MDI) | [Voir mockup](#ecran-t4)
**Delegue a** : [Visualisation pooling (IDE 8)](CAB-IDE-8.md)

---

#### <a id="t5"></a>9.3.1 - Veuillez patienter ... [[ECRAN]](#ecran-t5)

**Role** : Traitement : Veuillez patienter ....
**Ecran** : 442 x 55 DLU (MDI) | [Voir mockup](#ecran-t5)
**Delegue a** : [Visualisation pooling (IDE 8)](CAB-IDE-8.md)

---

#### <a id="t8"></a>9.4 - Mise à jour telephone

**Role** : Traitement : Mise à jour telephone.
**Delegue a** : [Visualisation pooling (IDE 8)](CAB-IDE-8.md)

---

#### <a id="t11"></a>9.5 - Mise à jour monetique

**Role** : Traitement : Mise à jour monetique.
**Delegue a** : [Visualisation pooling (IDE 8)](CAB-IDE-8.md)

---

#### <a id="t14"></a>9.3.2 - Veuillez patienter ... [[ECRAN]](#ecran-t14)

**Role** : Traitement : Veuillez patienter ....
**Ecran** : 442 x 55 DLU (MDI) | [Voir mockup](#ecran-t14)
**Delegue a** : [Visualisation pooling (IDE 8)](CAB-IDE-8.md)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: (aucun)
- **Appelle**: 2 programmes | **Tables**: 2 (W:1 R:2 L:0) | **Taches**: 8 | **Expressions**: 9

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (2 / 8)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 9.5.1 | 9.3.1 | Veuillez patienter ... | MDI | 442 | 55 | Traitement |
| 2 | 9.5.2 | 9.3.2 | Veuillez patienter ... | MDI | 442 | 55 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t5"></a>9.5.1 - Veuillez patienter ...
**Tache** : [9.3.1](#t5) | **Type** : MDI | **Dimensions** : 442 x 55 DLU
**Bloc** : Traitement | **Titre IDE** : Veuillez patienter ...

<!-- FORM-DATA:
{
    "width":  442,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  139,
                         "type":  "label",
                         "var":  "",
                         "y":  45,
                         "w":  253,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "(Attente au plus de 30 secondes)",
                         "parent":  null
                     },
                     {
                         "x":  2,
                         "type":  "image",
                         "var":  "",
                         "y":  0,
                         "w":  85,
                         "fmt":  "",
                         "name":  "",
                         "h":  33,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  3,
                         "type":  "image",
                         "var":  "",
                         "y":  0,
                         "w":  77,
                         "fmt":  "",
                         "name":  "",
                         "h":  33,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  3,
                         "type":  "image",
                         "var":  "",
                         "y":  0,
                         "w":  75,
                         "fmt":  "",
                         "name":  "",
                         "h":  33,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  3,
                         "type":  "image",
                         "var":  "",
                         "y":  1,
                         "w":  75,
                         "fmt":  "",
                         "name":  "",
                         "h":  33,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  90,
                         "type":  "edit",
                         "var":  "",
                         "y":  5,
                         "w":  350,
                         "fmt":  "80",
                         "name":  "",
                         "h":  19,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  213,
                         "type":  "edit",
                         "var":  "",
                         "y":  32,
                         "w":  104,
                         "fmt":  "HH:MM:SS",
                         "name":  "",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "9.5.1",
    "height":  55
}
-->

<details>
<summary><strong>Champs : 2 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 90,5 | 80 | - | edit |
| 213,32 | HH:MM:SS | - | edit |

</details>

---

#### <a id="ecran-t14"></a>9.5.2 - Veuillez patienter ...
**Tache** : [9.3.2](#t14) | **Type** : MDI | **Dimensions** : 442 x 55 DLU
**Bloc** : Traitement | **Titre IDE** : Veuillez patienter ...

<!-- FORM-DATA:
{
    "width":  442,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  139,
                         "type":  "label",
                         "var":  "",
                         "y":  45,
                         "w":  253,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "(Attente au plus de 30 secondes)",
                         "parent":  null
                     },
                     {
                         "x":  2,
                         "type":  "image",
                         "var":  "",
                         "y":  0,
                         "w":  85,
                         "fmt":  "",
                         "name":  "",
                         "h":  33,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  3,
                         "type":  "image",
                         "var":  "",
                         "y":  0,
                         "w":  77,
                         "fmt":  "",
                         "name":  "",
                         "h":  33,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  3,
                         "type":  "image",
                         "var":  "",
                         "y":  0,
                         "w":  75,
                         "fmt":  "",
                         "name":  "",
                         "h":  33,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  3,
                         "type":  "image",
                         "var":  "",
                         "y":  1,
                         "w":  75,
                         "fmt":  "",
                         "name":  "",
                         "h":  33,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  90,
                         "type":  "edit",
                         "var":  "",
                         "y":  5,
                         "w":  350,
                         "fmt":  "80",
                         "name":  "",
                         "h":  19,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  213,
                         "type":  "edit",
                         "var":  "",
                         "y":  32,
                         "w":  104,
                         "fmt":  "HH:MM:SS",
                         "name":  "",
                         "h":  10,
                         "color":  "6",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "9.5.2",
    "height":  55
}
-->

<details>
<summary><strong>Champs : 2 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 90,5 | 80 | - | edit |
| 213,32 | HH:MM:SS | - | edit |

</details>

## 9. NAVIGATION

### 9.1 Enchainement des ecrans

```mermaid
flowchart TD
    START([Entree])
    style START fill:#3fb950
    VF5[9.3.1 Veuillez patienter ...]
    style VF5 fill:#58a6ff
    VF14[9.3.2 Veuillez patienter...]
    style VF14 fill:#58a6ff
    EXT7[IDE 7 Suppression dema...]
    style EXT7 fill:#3fb950
    EXT8[IDE 8 Visualisation po...]
    style EXT8 fill:#3fb950
    FIN([Sortie])
    style FIN fill:#f85149
    START --> VF5
    VF5 -->|Controle/validation| EXT7
    VF5 -->|Sous-programme| EXT8
    EXT8 --> FIN
```

**Detail par enchainement :**

| Depuis | Action | Vers | Retour |
|--------|--------|------|--------|
| Veuillez patienter ... | Controle/validation | [Suppression demande verif pool (IDE 7)](CAB-IDE-7.md) | Retour ecran |
| Veuillez patienter ... | Sous-programme | [Visualisation pooling (IDE 8)](CAB-IDE-8.md) | Retour ecran |

### 9.3 Structure hierarchique (8 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **9.1** | [**Verification pooling** (9)](#t1) | MDI | - | Validation |
| **9.2** | [**Mise à jour telephone** (9.1)](#t2) | MDI | - | Traitement |
| 9.2.1 | [Mise à jour monetique (9.2)](#t3) | MDI | - | |
| 9.2.2 | [Traitement en attente (9.3)](#t4) [mockup](#ecran-t4) | MDI | 442x48 | |
| 9.2.3 | [Veuillez patienter ... (9.3.1)](#t5) [mockup](#ecran-t5) | MDI | 442x55 | |
| 9.2.4 | [Mise à jour telephone (9.4)](#t8) | MDI | - | |
| 9.2.5 | [Mise à jour monetique (9.5)](#t11) | MDI | - | |
| 9.2.6 | [Veuillez patienter ... (9.3.2)](#t14) [mockup](#ecran-t14) | MDI | 442x55 | |

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

### Tables utilisees (2)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 63 | parametres___par |  | DB | R |   |   | 1 |
| 476 | comptes_pour_changer_activite | Comptes GM (generaux) | TMP | R | **W** |   | 6 |

### Colonnes par table (0 / 2 tables avec colonnes identifiees)

<details>
<summary>Table 63 - parametres___par (R) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 476 - comptes_pour_changer_activite (R/**W**) - 6 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Variables de session (2)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | v. fin | Logical | - |
| B | v. time | Time | - |

## 12. EXPRESSIONS

**9 / 9 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONSTANTE | 3 | 0 |
| CONDITION | 4 | 0 |
| NEGATION | 1 | 0 |
| REFERENCE_VG | 1 | 0 |

### 12.2 Expressions cles par type

#### CONSTANTE (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 3 | `2` | - |
| CONSTANTE | 2 | `1` | - |
| CONSTANTE | 1 | `'C'` | - |

#### CONDITION (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 6 | `[C]='O' OR [F]='O'` | - |
| CONDITION | 7 | `[C]='N' AND [F]='N'` | - |
| CONDITION | 4 | `[C]='O'` | - |
| CONDITION | 5 | `[F]='O'` | - |

#### NEGATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| NEGATION | 8 | `NOT VG6` | - |

#### REFERENCE_VG (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 9 | `VG6` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

**Chemin**: (pas de callers directs)

```mermaid
graph LR
    T9[9 Verification pooling]
    style T9 fill:#58a6ff
    NONE[Aucun caller]
    NONE -.-> T9
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| - | (aucun) | - |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T9[9 Verification pooling]
    style T9 fill:#58a6ff
    C7[7 Suppression demande ...]
    T9 --> C7
    style C7 fill:#3fb950
    C8[8 Visualisation pooling]
    T9 --> C8
    style C8 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [7](CAB-IDE-7.md) | Suppression demande verif pool | 2 | Controle/validation |
| [8](CAB-IDE-8.md) | Visualisation pooling | 1 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 85 | Programme compact |
| Expressions | 9 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 2 | Peu de dependances |
| Ecrans visibles | 2 | Quelques ecrans |
| Code desactive | 0% (0 / 85) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Validation (1 tache: 0 ecran, 1 traitement)

- **Strategie** : FluentValidation avec validators specifiques.
- Chaque tache de validation -> un validator injectable

#### Traitement (7 taches: 3 ecrans, 4 traitements)

- **Strategie** : Orchestrateur avec 3 ecrans (Razor/React) et 4 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 2 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| comptes_pour_changer_activite | Table WRITE (Temp) | 4x | Schema + repository |
| [Suppression demande verif pool (IDE 7)](CAB-IDE-7.md) | Sous-programme | 2x | Haute - Controle/validation |
| [Visualisation pooling (IDE 8)](CAB-IDE-8.md) | Sous-programme | 1x | Normale - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 09:59*
