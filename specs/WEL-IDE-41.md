# WEL IDE 41 - Reserver logement

> **Analyse**: Phases 1-4 2026-02-03 21:25 -> 21:25 (18s) | Assemblage 21:25
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | WEL |
| IDE Position | 41 |
| Nom Programme | Reserver logement |
| Fichier source | `Prg_41.xml` |
| Dossier IDE | Logement |
| Taches | 6 (0 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 2 |
| :warning: Statut | **ORPHELIN_POTENTIEL** |

## 2. DESCRIPTION FONCTIONNELLE

**Reserver logement** assure la gestion complete de ce processus.

Le flux de traitement s'organise en **4 blocs fonctionnels** :

- **Validation** (2 taches) : controles et verifications de coherence
- **Traitement** (2 taches) : traitements metier divers
- **Creation** (1 tache) : insertion d'enregistrements en base (mouvements, prestations)
- **Consultation** (1 tache) : ecrans de recherche, selection et consultation

**Donnees modifiees** : 1 tables en ecriture (hebergement______heb).

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (2 taches)

- **41** - Reserver logement
- **41.3** - Attribution N° blocage

#### Phase 2 : Validation (2 taches)

- **41.1** - Verification logement
- **41.2** - Verification logement

#### Phase 3 : Consultation (1 tache)

- **41.3.1** - Recherche n° blocage

#### Phase 4 : Creation (1 tache)

- **41.4** - Creation blocage

Delegue a : [Create logbook (IDE 81)](WEL-IDE-81.md)

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| hebergement______heb | R/**W** (4 usages) | Hebergement (chambres) |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (2 taches)

Traitements internes.

---

#### <a id="t1"></a>41 - Reserver logement

**Role** : Traitement : Reserver logement.

---

#### <a id="t4"></a>41.3 - Attribution N° blocage

**Role** : Traitement : Attribution N° blocage.
**Variables liees** : G (V0.N° blocage)


### 3.2 Validation (2 taches)

Controles de coherence : 2 taches verifient les donnees et conditions.

---

#### <a id="t2"></a>41.1 - Verification logement

**Role** : Verification : Verification logement.

---

#### <a id="t3"></a>41.2 - Verification logement

**Role** : Verification : Verification logement.


### 3.3 Consultation (1 tache)

Ecrans de recherche et consultation.

---

#### <a id="t5"></a>41.3.1 - Recherche n° blocage

**Role** : Traitement : Recherche n° blocage.
**Variables liees** : G (V0.N° blocage)


### 3.4 Creation (1 tache)

Insertion de nouveaux enregistrements en base.

---

#### <a id="t6"></a>41.4 - Creation blocage

**Role** : Creation d'enregistrement : Creation blocage.
**Variables liees** : G (V0.N° blocage)
**Delegue a** : [Create logbook (IDE 81)](WEL-IDE-81.md)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: (aucun)
- **Appelle**: 2 programmes | **Tables**: 1 (W:1 R:1 L:0) | **Taches**: 6 | **Expressions**: 6

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (6 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **41.1** | [**Reserver logement** (41)](#t1) | - | - | Traitement |
| 41.1.1 | [Attribution N° blocage (41.3)](#t4) | - | - | |
| **41.2** | [**Verification logement** (41.1)](#t2) | - | - | Validation |
| 41.2.1 | [Verification logement (41.2)](#t3) | - | - | |
| **41.3** | [**Recherche n° blocage** (41.3.1)](#t5) | - | - | Consultation |
| **41.4** | [**Creation blocage** (41.4)](#t6) | - | - | Creation |

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

### Tables utilisees (1)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 34 | hebergement______heb | Hebergement (chambres) | DB | R | **W** |   | 4 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 34 - hebergement______heb (R/**W**) - 4 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | V1.Date/heure debut | W | Numeric |
| B | V1.Date/heure fin | W | Numeric |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (1)

Variables recues en parametre.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P.Refresh view ? | Logical | 1x parametre entrant |

### 11.2 Autres (9)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| B | V0.Accord suite | Logical | - |
| C | V0.Operateur | Unicode | - |
| D | V0.Commentaire | Unicode | - |
| E | V0.Date debut | Date | - |
| F | V0.Date fin | Date | - |
| G | V0.N° blocage | Numeric | - |
| H | V0.User | Alpha | - |
| I | V0.Confirmation | Numeric | - |
| J | V0.Selection choix | Alpha | - |

## 12. EXPRESSIONS

**6 / 6 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONSTANTE | 4 | 0 |
| NEGATION | 1 | 0 |
| STRING | 1 | 0 |

### 12.2 Expressions cles par type

#### CONSTANTE (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 3 | `'ROOM'` | - |
| CONSTANTE | 5 | `'RESROOM'` | - |
| CONSTANTE | 1 | `'RES'` | - |
| CONSTANTE | 2 | `'R'` | - |

#### NEGATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| NEGATION | 4 | `NOT P.Refresh view ? [A]` | - |

#### STRING (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| STRING | 6 | `'Access screen room reservation : '&Trim(VG11)` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

**Chemin**: (pas de callers directs)

```mermaid
graph LR
    T41[41 Reserver logement]
    style T41 fill:#58a6ff
    NONE[Aucun caller]
    NONE -.-> T41
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| - | (aucun) | - |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T41[41 Reserver logement]
    style T41 fill:#58a6ff
    C48[48 Saisie blocagereser...]
    T41 --> C48
    style C48 fill:#3fb950
    C81[81 Create logbook]
    T41 --> C81
    style C81 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [48](WEL-IDE-48.md) | Saisie blocage/reserv room | 1 | Sous-programme |
| [81](WEL-IDE-81.md) | Create logbook | 1 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 93 | Programme compact |
| Expressions | 6 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 2 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 93) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (2 taches: 0 ecran, 2 traitements)

- **Strategie** : 2 service(s) backend injectable(s) (Domain Services).
- 2 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Validation (2 taches: 0 ecran, 2 traitements)

- **Strategie** : FluentValidation avec validators specifiques.
- Chaque tache de validation -> un validator injectable

#### Consultation (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Composants de recherche/selection en modales.

#### Creation (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Repository pattern avec Entity Framework Core.
- Insertion via `IRepository<T>.CreateAsync()`

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| hebergement______heb | Table WRITE (Database) | 1x | Schema + repository |
| [Create logbook (IDE 81)](WEL-IDE-81.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Saisie blocage/reserv room (IDE 48)](WEL-IDE-48.md) | Sous-programme | 1x | Normale - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 21:25*
