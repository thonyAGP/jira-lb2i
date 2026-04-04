# CAP IDE 41 - Recuperation du titre

> **Analyse**: Phases 1-4 2026-02-03 10:23 -> 10:24 (18s) | Assemblage 10:24
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | CAP |
| IDE Position | 41 |
| Nom Programme | Recuperation du titre |
| Fichier source | `Prg_41.xml` |
| Domaine metier | General |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Recuperation du titre** assure la gestion complete de ce processus, accessible depuis [Liste des forfaits TAI (IDE 29)](CAP-IDE-29.md), [Compte les seminaires (IDE 26)](CAP-IDE-26.md), [Menu caisse GM - scroll @ (IDE 49)](CAP-IDE-49.md), [Extrait de compte (IDE 16)](CAP-IDE-16.md), [Extrait de compte  Vente (IDE 18)](CAP-IDE-18.md), [Liste des affilies@ (IDE 28)](CAP-IDE-28.md), [Choix date de Purge (IDE 30)](CAP-IDE-30.md), [Menu caisse (IDE 34)](CAP-IDE-34.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>41 - Recuperation du titre

**Role** : Consultation/chargement : Recuperation du titre.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Liste des forfaits TAI (IDE 29)](CAP-IDE-29.md), [Compte les seminaires (IDE 26)](CAP-IDE-26.md), [Menu caisse GM - scroll @ (IDE 49)](CAP-IDE-49.md), [Extrait de compte (IDE 16)](CAP-IDE-16.md), [Extrait de compte  Vente (IDE 18)](CAP-IDE-18.md), [Liste des affilies@ (IDE 28)](CAP-IDE-28.md), [Choix date de Purge (IDE 30)](CAP-IDE-30.md), [Menu caisse (IDE 34)](CAP-IDE-34.md)
- **Appelle**: 0 programmes | **Tables**: 1 (W:0 R:1 L:0) | **Taches**: 1 | **Expressions**: 4

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **41.1** | [**Recuperation du titre** (41)](#t1) | MDI | - | Traitement |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Traitement principal]
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

### Tables utilisees (1)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 719 | arc_transac_detail_bar |  | DB | R |   |   | 1 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 719 - arc_transac_detail_bar (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | > code ecran | R | Numeric |
| B | < nom ecran | R | Alpha |

</details>

## 11. VARIABLES

### 11.1 Autres (2)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | > code ecran | Numeric | 1x refs |
| B | < nom ecran | Alpha | - |

## 12. EXPRESSIONS

**4 / 4 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONCATENATION | 1 | 0 |
| CONSTANTE | 1 | 0 |
| OTHER | 1 | 0 |
| CONDITION | 1 | 0 |

### 12.2 Expressions cles par type

#### CONCATENATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 4 | `Trim ([F])&' - '&Trim ([G])` | - |

#### CONSTANTE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 3 | `'GA'` | - |

#### OTHER (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 1 | `GetParam ('CODELANGUE')` | - |

#### CONDITION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 2 | `> code ecran [A]` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Liste des forfaits TAI (IDE 29)](CAP-IDE-29.md) -> **Recuperation du titre (IDE 41)**

Main -> ... -> [Compte les seminaires (IDE 26)](CAP-IDE-26.md) -> **Recuperation du titre (IDE 41)**

Main -> ... -> [Menu caisse GM - scroll @ (IDE 49)](CAP-IDE-49.md) -> **Recuperation du titre (IDE 41)**

Main -> ... -> [Extrait de compte (IDE 16)](CAP-IDE-16.md) -> **Recuperation du titre (IDE 41)**

Main -> ... -> [Extrait de compte  Vente (IDE 18)](CAP-IDE-18.md) -> **Recuperation du titre (IDE 41)**

Main -> ... -> [Liste des affilies@ (IDE 28)](CAP-IDE-28.md) -> **Recuperation du titre (IDE 41)**

Main -> ... -> [Choix date de Purge (IDE 30)](CAP-IDE-30.md) -> **Recuperation du titre (IDE 41)**

Main -> ... -> [Menu caisse (IDE 34)](CAP-IDE-34.md) -> **Recuperation du titre (IDE 41)**

```mermaid
graph LR
    T41[41 Recuperation du titre]
    style T41 fill:#58a6ff
    CC33[33 Affichage Clients]
    style CC33 fill:#8b5cf6
    CC49[49 Menu caisse GM - sc...]
    style CC49 fill:#f59e0b
    CC34[34 Menu caisse]
    style CC34 fill:#f59e0b
    CC25[25 Gratuites GM]
    style CC25 fill:#f59e0b
    CC37[37 Menu caisse GM - sc...]
    style CC37 fill:#f59e0b
    CC16[16 Extrait de compte]
    style CC16 fill:#3fb950
    CC26[26 Compte les seminaires]
    style CC26 fill:#3fb950
    CC18[18 Extrait de compte V...]
    style CC18 fill:#3fb950
    CC29[29 Liste des forfaits TAI]
    style CC29 fill:#3fb950
    CC28[28 Liste des affilies@]
    style CC28 fill:#3fb950
    CC34 --> CC16
    CC49 --> CC16
    CC25 --> CC16
    CC37 --> CC16
    CC34 --> CC18
    CC49 --> CC18
    CC25 --> CC18
    CC37 --> CC18
    CC34 --> CC26
    CC49 --> CC26
    CC25 --> CC26
    CC37 --> CC26
    CC34 --> CC28
    CC49 --> CC28
    CC25 --> CC28
    CC37 --> CC28
    CC34 --> CC29
    CC49 --> CC29
    CC25 --> CC29
    CC37 --> CC29
    CC33 --> CC34
    CC33 --> CC49
    CC33 --> CC25
    CC33 --> CC37
    CC16 --> T41
    CC18 --> T41
    CC26 --> T41
    CC28 --> T41
    CC29 --> T41
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [29](CAP-IDE-29.md) | Liste des forfaits TAI | 3 |
| [26](CAP-IDE-26.md) | Compte les seminaires | 2 |
| [49](CAP-IDE-49.md) | Menu caisse GM - scroll @ | 2 |
| [16](CAP-IDE-16.md) | Extrait de compte | 1 |
| [18](CAP-IDE-18.md) | Extrait de compte  Vente | 1 |
| [28](CAP-IDE-28.md) | Liste des affilies@ | 1 |
| [30](CAP-IDE-30.md) | Choix date de Purge | 1 |
| [34](CAP-IDE-34.md) | Menu caisse | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T41[41 Recuperation du titre]
    style T41 fill:#58a6ff
    NONE[Aucun callee]
    T41 -.-> NONE
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
| Lignes de logique | 12 | Programme compact |
| Expressions | 4 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 12) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 0 ecran, 1 traitement)

- **Strategie** : 1 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 10:24*
