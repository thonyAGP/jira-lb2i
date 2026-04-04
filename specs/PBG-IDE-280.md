# PBG IDE 280 - Traitement Sejours new

> **Analyse**: Phases 1-4 2026-02-03 10:48 -> 10:49 (18s) | Assemblage 10:49
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBG |
| IDE Position | 280 |
| Nom Programme | Traitement Sejours new |
| Fichier source | `Prg_280.xml` |
| Domaine metier | General |
| Taches | 7 (0 ecrans visibles) |
| Tables modifiees | 3 |
| Programmes appeles | 1 |

## 2. DESCRIPTION FONCTIONNELLE

**Traitement Sejours new** assure la gestion complete de ce processus, accessible depuis [Traitement des arrivants (IDE 206)](PBG-IDE-206.md).

Le flux de traitement s'organise en **2 blocs fonctionnels** :

- **Creation** (4 taches) : insertion d'enregistrements en base (mouvements, prestations)
- **Traitement** (3 taches) : traitements metier divers

**Donnees modifiees** : 3 tables en ecriture (voyages__________voy, compte_gm________cgm, pointage_articles_caution).

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (3 taches)

- **280** - Veuillez patienter... **[[ECRAN]](#ecran-t1)**
- **280.1** - Determination Periodes
- **280.2** - Traitement Sejour **[[ECRAN]](#ecran-t8)**

Delegue a : [Suppression vol doublons (IDE 339)](PBG-IDE-339.md)

#### Phase 2 : Creation (4 taches)

- **280.1.1** - Creation Voyage Aller
- **280.1.2** - Creation Voyage Aller
- **280.1.3** - Creation Voyage Aller
- **280.1.4** - Creation Voyage Aller

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| voyages__________voy | **W** (4 usages) |  |
| pointage_articles_caution | **W** (1 usages) | Articles et stock |
| compte_gm________cgm | **W** (1 usages) | Comptes GM (generaux) |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (3 taches)

Traitements internes.

---

#### <a id="t1"></a>280 - Veuillez patienter... [[ECRAN]](#ecran-t1)

**Role** : Traitement : Veuillez patienter....
**Ecran** : 429 x 68 DLU (MDI) | [Voir mockup](#ecran-t1)
**Delegue a** : [Suppression vol doublons (IDE 339)](PBG-IDE-339.md)

---

#### <a id="t3"></a>280.1 - Determination Periodes

**Role** : Traitement : Determination Periodes.
**Delegue a** : [Suppression vol doublons (IDE 339)](PBG-IDE-339.md)

---

#### <a id="t8"></a>280.2 - Traitement Sejour [[ECRAN]](#ecran-t8)

**Role** : Traitement : Traitement Sejour.
**Ecran** : 40 x 8 DLU (Modal) | [Voir mockup](#ecran-t8)
**Variables liees** : B (P0-Lieu de Sejour)
**Delegue a** : [Suppression vol doublons (IDE 339)](PBG-IDE-339.md)


### 3.2 Creation (4 taches)

Insertion de nouveaux enregistrements en base.

---

#### <a id="t4"></a>280.1.1 - Creation Voyage Aller

**Role** : Creation d'enregistrement : Creation Voyage Aller.
**Variables liees** : E (P0 Heure diff aller -1)

---

#### <a id="t5"></a>280.1.2 - Creation Voyage Aller

**Role** : Creation d'enregistrement : Creation Voyage Aller.
**Variables liees** : E (P0 Heure diff aller -1)

---

#### <a id="t6"></a>280.1.3 - Creation Voyage Aller

**Role** : Creation d'enregistrement : Creation Voyage Aller.
**Variables liees** : E (P0 Heure diff aller -1)

---

#### <a id="t7"></a>280.1.4 - Creation Voyage Aller

**Role** : Creation d'enregistrement : Creation Voyage Aller.
**Variables liees** : E (P0 Heure diff aller -1)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Traitement des arrivants (IDE 206)](PBG-IDE-206.md)
- **Appelle**: 1 programmes | **Tables**: 7 (W:3 R:1 L:3) | **Taches**: 7 | **Expressions**: 9

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (7 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **280.1** | [**Veuillez patienter...** (280)](#t1) [mockup](#ecran-t1) | MDI | 429x68 | Traitement |
| 280.1.1 | [Determination Periodes (280.1)](#t3) | MDI | - | |
| 280.1.2 | [Traitement Sejour (280.2)](#t8) [mockup](#ecran-t8) | Modal | 40x8 | |
| **280.2** | [**Creation Voyage Aller** (280.1.1)](#t4) | MDI | - | Creation |
| 280.2.1 | [Creation Voyage Aller (280.1.2)](#t5) | MDI | - | |
| 280.2.2 | [Creation Voyage Aller (280.1.3)](#t6) | MDI | - | |
| 280.2.3 | [Creation Voyage Aller (280.1.4)](#t7) | MDI | - | |

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
| 29 | voyages__________voy |  | DB |   | **W** |   | 4 |
| 34 | hebergement______heb | Hebergement (chambres) | DB | R |   |   | 1 |
| 47 | compte_gm________cgm | Comptes GM (generaux) | DB |   | **W** |   | 1 |
| 132 | code_vol_________vot |  | DB |   |   | L | 4 |
| 569 | pointage_articles_caution | Articles et stock | TMP |   | **W** |   | 1 |
| 571 | inter_prestation_inp | Prestations/services vendus | TMP |   |   | L | 1 |
| 576 | temp_recap_sessions | Sessions de caisse | TMP |   |   | L | 2 |

### Colonnes par table (4 / 4 tables avec colonnes identifiees)

<details>
<summary>Table 29 - voyages__________voy (**W**) - 4 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 34 - hebergement______heb (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | v.aller_compagnie | R | Unicode |
| B | v.aller_d-1_compagnie | R | Unicode |
| C | v.aller_d+1_compagnie | R | Unicode |
| D | W1 Vol Retour ? | R | Numeric |
| E | v.retour_compagnie | R | Unicode |
| F | v.retour_d+1_compagnie | R | Unicode |
| G | W1 Vol Aller ? | R | Numeric |
| H | W1 Vol Aller Dif -1? | R | Numeric |
| I | W1 Vol Aller Dif +1? | R | Numeric |
| J | W1 Vol Retour Dif ? | R | Numeric |

</details>

<details>
<summary>Table 47 - compte_gm________cgm (**W**) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| N | V.Compteur | W | Numeric |

</details>

<details>
<summary>Table 569 - pointage_articles_caution (**W**) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P0-Code Societe | W | Alpha |
| B | P0-Lieu de Sejour | W | Alpha |
| C | P0-Nb Arrivants | W | Numeric |
| D | P0-Num ressource | W | Numeric |
| E | P0 Heure diff aller -1 | W | Numeric |
| F | P0 Heure diff retour | W | Numeric |
| G | W0-Operande | W | Numeric |
| H | W0-Operateur | W | Numeric |
| I | W0-Pourcentage | W | Numeric |
| J | W0-Calcul Pourcent | W | Numeric |
| K | W0-Date Debut | W | Date |
| L | W0-Date Fin | W | Date |
| M | W0-Alerte | W | Alpha |
| N | V.Compteur | W | Numeric |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (2)

Variables recues du programme appelant ([Traitement des arrivants (IDE 206)](PBG-IDE-206.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| E | P0 Heure diff aller -1 | Numeric | - |
| F | P0 Heure diff retour | Numeric | - |

### 11.2 Variables de session (1)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| N | V.Compteur | Numeric | - |

### 11.3 Autres (11)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P0-Code Societe | Alpha | - |
| B | P0-Lieu de Sejour | Alpha | - |
| C | P0-Nb Arrivants | Numeric | - |
| D | P0-Num ressource | Numeric | - |
| G | W0-Operande | Numeric | - |
| H | W0-Operateur | Numeric | - |
| I | W0-Pourcentage | Numeric | - |
| J | W0-Calcul Pourcent | Numeric | - |
| K | W0-Date Debut | Date | - |
| L | W0-Date Fin | Date | - |
| M | W0-Alerte | Alpha | - |

## 12. EXPRESSIONS

**9 / 9 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCULATION | 3 | 0 |
| CONSTANTE | 3 | 0 |
| REFERENCE_VG | 1 | 0 |
| OTHER | 2 | 0 |

### 12.2 Expressions cles par type

#### CALCULATION (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 8 | `[X]+1` | - |
| CALCULATION | 3 | `([X]/VG1)*50` | - |
| CALCULATION | 2 | `([X]/VG1)*100` | - |

#### CONSTANTE (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 6 | `'I'` | - |
| CONSTANTE | 5 | `'F'` | - |
| CONSTANTE | 1 | `''` | - |

#### REFERENCE_VG (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 4 | `VG20` | - |

#### OTHER (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 9 | `[Y]` | - |
| OTHER | 7 | `[O]` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Traitement des arrivants (IDE 206)](PBG-IDE-206.md) -> **Traitement Sejours new (IDE 280)**

```mermaid
graph LR
    T280[280 Traitement Sejours...]
    style T280 fill:#58a6ff
    CC206[206 Traitement des arr...]
    style CC206 fill:#8b5cf6
    CC206 --> T280
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [206](PBG-IDE-206.md) | Traitement des arrivants | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T280[280 Traitement Sejours...]
    style T280 fill:#58a6ff
    C339[339 Suppression vol do...]
    T280 --> C339
    style C339 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [339](PBG-IDE-339.md) | Suppression vol doublons | 2 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 249 | Taille moyenne |
| Expressions | 9 | Peu de logique |
| Tables WRITE | 3 | Impact modere |
| Sous-programmes | 1 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 249) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (3 taches: 2 ecrans, 1 traitement)

- **Strategie** : Orchestrateur avec 2 ecrans (Razor/React) et 1 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 1 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Creation (4 taches: 0 ecran, 4 traitements)

- **Strategie** : Repository pattern avec Entity Framework Core.
- Insertion via `IRepository<T>.CreateAsync()`

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| voyages__________voy | Table WRITE (Database) | 4x | Schema + repository |
| compte_gm________cgm | Table WRITE (Database) | 1x | Schema + repository |
| pointage_articles_caution | Table WRITE (Temp) | 1x | Schema + repository |
| [Suppression vol doublons (IDE 339)](PBG-IDE-339.md) | Sous-programme | 2x | Haute - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 10:49*
