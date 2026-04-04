# PBG IDE 10 - Clean log

> **Analyse**: Phases 1-4 2026-02-03 00:58 -> 00:59 (36s) | Assemblage 00:59
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBG |
| IDE Position | 10 |
| Nom Programme | Clean log |
| Fichier source | `Prg_10.xml` |
| Domaine metier | General |
| Taches | 2 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Clean log** assure la gestion complete de ce processus, accessible depuis [Traitement affec auto chambres (IDE 8)](PBG-IDE-8.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (2 taches) : traitements metier divers

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (2 taches)

Traitements internes.

---

#### <a id="t1"></a>10 - Clean log

**Role** : Traitement : Clean log.

---

#### <a id="t2"></a>10.1 - maj entete

**Role** : Traitement : maj entete.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Traitement affec auto chambres (IDE 8)](PBG-IDE-8.md)
- **Appelle**: 0 programmes | **Tables**: 3 (W:0 R:1 L:2) | **Taches**: 2 | **Expressions**: 6

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (2 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **10.1** | [**Clean log** (10)](#t1) | - | - | Traitement |
| 10.1.1 | [maj entete (10.1)](#t2) | - | - | |

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

### Tables utilisees (3)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 820 | Commentaire supprime |  | DB | R |   |   | 2 |
| 822 | pv_message |  | DB |   |   | L | 1 |
| 823 | fac_tva_pro |  | DB |   |   | L | 1 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 820 - Commentaire supprime (R) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P.Date traitement | R | Date |
| B | V.Nb rejet | R | Numeric |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (1)

Variables recues du programme appelant ([Traitement affec auto chambres (IDE 8)](PBG-IDE-8.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P.Date traitement | Date | - |

### 11.2 Variables de session (1)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| B | V.Nb rejet | Numeric | 1x session |

## 12. EXPRESSIONS

**6 / 6 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| OTHER | 5 | 0 |
| CONDITION | 1 | 0 |

### 12.2 Expressions cles par type

#### OTHER (5 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 5 | `[C]` | - |
| OTHER | 6 | `[D]` | - |
| OTHER | 4 | `V.Nb rejet [B]` | - |
| OTHER | 1 | `GetParam('SOCIETE')` | - |
| OTHER | 3 | `[L]` | - |

#### CONDITION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 2 | `[J]<>''` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Traitement affec auto chambres (IDE 8)](PBG-IDE-8.md) -> **Clean log (IDE 10)**

```mermaid
graph LR
    T10[10 Clean log]
    style T10 fill:#58a6ff
    CC5[5 Affectation auto cha...]
    style CC5 fill:#8b5cf6
    CC21[21 Affec manuelle chambre]
    style CC21 fill:#f59e0b
    CC14[14 lancement affec aut...]
    style CC14 fill:#f59e0b
    CC6[6 Affectation auto cha...]
    style CC6 fill:#f59e0b
    CC8[8 Traitement affec aut...]
    style CC8 fill:#3fb950
    CC6 --> CC8
    CC14 --> CC8
    CC21 --> CC8
    CC5 --> CC6
    CC5 --> CC14
    CC5 --> CC21
    CC8 --> T10
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [8](PBG-IDE-8.md) | Traitement affec auto chambres | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T10[10 Clean log]
    style T10 fill:#58a6ff
    NONE[Aucun callee]
    T10 -.-> NONE
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
| Lignes de logique | 31 | Programme compact |
| Expressions | 6 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 31) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (2 taches: 0 ecran, 2 traitements)

- **Strategie** : 2 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 00:59*
