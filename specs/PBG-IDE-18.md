# PBG IDE 18 - Affectation chambre

> **Analyse**: Phases 1-4 2026-02-03 01:05 -> 01:06 (40s) | Assemblage 01:06
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBG |
| IDE Position | 18 |
| Nom Programme | Affectation chambre |
| Fichier source | `Prg_18.xml` |
| Domaine metier | General |
| Taches | 3 (0 ecrans visibles) |
| Tables modifiees | 2 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Affectation chambre** assure la gestion complete de ce processus, accessible depuis [Recherche chambre dispo new (IDE 15)](PBG-IDE-15.md), [Affec manuelle chambre (IDE 21)](PBG-IDE-21.md), [Chambres GM disponibles (IDE 291)](PBG-IDE-291.md), [Chambres GO disponibles (IDE 292)](PBG-IDE-292.md), [Recherche chambre dispo sav (IDE 390)](PBG-IDE-390.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (3 taches) : traitements metier divers

**Donnees modifiees** : 2 tables en ecriture (hebergement______heb, tairejet).

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (3 taches)

Traitements internes.

---

#### <a id="t1"></a>18 - Affectation chambre

**Role** : Traitement : Affectation chambre.

---

#### <a id="t19"></a>18.1 - Crzation chambre

**Role** : Traitement : Crzation chambre.

---

#### <a id="t23"></a>18.2 - Affectation

**Role** : Traitement : Affectation.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Recherche chambre dispo new (IDE 15)](PBG-IDE-15.md), [Affec manuelle chambre (IDE 21)](PBG-IDE-21.md), [Chambres GM disponibles (IDE 291)](PBG-IDE-291.md), [Chambres GO disponibles (IDE 292)](PBG-IDE-292.md), [Recherche chambre dispo sav (IDE 390)](PBG-IDE-390.md)
- **Appelle**: 0 programmes | **Tables**: 3 (W:2 R:1 L:0) | **Taches**: 3 | **Expressions**: 3

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (3 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **18.1** | [**Affectation chambre** (18)](#t1) | - | - | Traitement |
| 18.1.1 | [Crzation chambre (18.1)](#t19) | - | - | |
| 18.1.2 | [Affectation (18.2)](#t23) | - | - | |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Traitement principal]
    UPDATE[MAJ 2 tables]
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
| 30 | gm-recherche_____gmr | Index de recherche | DB | R |   |   | 1 |
| 34 | hebergement______heb | Hebergement (chambres) | DB |   | **W** |   | 1 |
| 455 | tairejet |  | DB |   | **W** |   | 1 |

### Colonnes par table (1 / 3 tables avec colonnes identifiees)

<details>
<summary>Table 30 - gm-recherche_____gmr (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P.Societe | R | Alpha |
| B | P.Compte | R | Numeric |
| C | P.Filiation | R | Numeric |
| D | P.Date debut | R | Date |
| E | P.Date fin | R | Date |
| F | P.Nom logement | R | Alpha |
| G | P.Traitement auto | R | Alpha |

</details>

<details>
<summary>Table 34 - hebergement______heb (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 455 - tairejet (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (7)

Variables recues du programme appelant ([Recherche chambre dispo new (IDE 15)](PBG-IDE-15.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P.Societe | Alpha | 1x parametre entrant |
| B | P.Compte | Numeric | 1x parametre entrant |
| C | P.Filiation | Numeric | 1x parametre entrant |
| D | P.Date debut | Date | - |
| E | P.Date fin | Date | - |
| F | P.Nom logement | Alpha | - |
| G | P.Traitement auto | Alpha | - |

## 12. EXPRESSIONS

**3 / 3 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| OTHER | 3 | 0 |

### 12.2 Expressions cles par type

#### OTHER (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 3 | `P.Filiation [C]` | - |
| OTHER | 2 | `P.Compte [B]` | - |
| OTHER | 1 | `P.Societe [A]` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Recherche chambre dispo new (IDE 15)](PBG-IDE-15.md) -> **Affectation chambre (IDE 18)**

Main -> ... -> [Affec manuelle chambre (IDE 21)](PBG-IDE-21.md) -> **Affectation chambre (IDE 18)**

Main -> ... -> [Chambres GM disponibles (IDE 291)](PBG-IDE-291.md) -> **Affectation chambre (IDE 18)**

Main -> ... -> [Chambres GO disponibles (IDE 292)](PBG-IDE-292.md) -> **Affectation chambre (IDE 18)**

Main -> ... -> [Recherche chambre dispo sav (IDE 390)](PBG-IDE-390.md) -> **Affectation chambre (IDE 18)**

```mermaid
graph LR
    T18[18 Affectation chambre]
    style T18 fill:#58a6ff
    CC8[8 Traitement affec aut...]
    style CC8 fill:#8b5cf6
    CC13[13 lancement]
    style CC13 fill:#f59e0b
    CC9[9 Gestion priorite]
    style CC9 fill:#f59e0b
    CC290[290 Traitement Import ...]
    style CC290 fill:#f59e0b
    CC376[376 Traitement Import ...]
    style CC376 fill:#f59e0b
    CC15[15 Recherche chambre d...]
    style CC15 fill:#3fb950
    CC291[291 Chambres GM dispon...]
    style CC291 fill:#3fb950
    CC21[21 Affec manuelle chambre]
    style CC21 fill:#3fb950
    CC390[390 Recherche chambre ...]
    style CC390 fill:#3fb950
    CC292[292 Chambres GO dispon...]
    style CC292 fill:#3fb950
    CC9 --> CC15
    CC13 --> CC15
    CC290 --> CC15
    CC376 --> CC15
    CC9 --> CC21
    CC13 --> CC21
    CC290 --> CC21
    CC376 --> CC21
    CC9 --> CC291
    CC13 --> CC291
    CC290 --> CC291
    CC376 --> CC291
    CC9 --> CC292
    CC13 --> CC292
    CC290 --> CC292
    CC376 --> CC292
    CC9 --> CC390
    CC13 --> CC390
    CC290 --> CC390
    CC376 --> CC390
    CC8 --> CC9
    CC8 --> CC13
    CC8 --> CC290
    CC8 --> CC376
    CC15 --> T18
    CC21 --> T18
    CC291 --> T18
    CC292 --> T18
    CC390 --> T18
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [15](PBG-IDE-15.md) | Recherche chambre dispo new | 2 |
| [21](PBG-IDE-21.md) | Affec manuelle chambre | 1 |
| [291](PBG-IDE-291.md) | Chambres GM disponibles | 1 |
| [292](PBG-IDE-292.md) | Chambres GO disponibles | 1 |
| [390](PBG-IDE-390.md) | Recherche chambre dispo sav | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T18[18 Affectation chambre]
    style T18 fill:#58a6ff
    NONE[Aucun callee]
    T18 -.-> NONE
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
| Lignes de logique | 40 | Programme compact |
| Expressions | 3 | Peu de logique |
| Tables WRITE | 2 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 40) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (3 taches: 0 ecran, 3 traitements)

- **Strategie** : 3 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| hebergement______heb | Table WRITE (Database) | 1x | Schema + repository |
| tairejet | Table WRITE (Database) | 1x | Schema + repository |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 01:06*
