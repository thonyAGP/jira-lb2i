# POO IDE 37 - Recuperation In/Out

> **Analyse**: Phases 1-4 2026-02-03 17:48 -> 17:49 (16s) | Assemblage 17:49
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | POO |
| IDE Position | 37 |
| Nom Programme | Recuperation In/Out |
| Fichier source | `Prg_37.xml` |
| Dossier IDE | Pooling |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 1 |

## 2. DESCRIPTION FONCTIONNELLE

**Recuperation In/Out** assure la gestion complete de ce processus, accessible depuis [ Puttel transfert fichier (IDE 36)](POO-IDE-36.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>37 - Recuperation txt serveur

**Role** : Consultation/chargement : Recuperation txt serveur.
**Delegue a** : [Check (IDE 69)](POO-IDE-69.md)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [ Puttel transfert fichier (IDE 36)](POO-IDE-36.md)
- **Appelle**: 1 programmes | **Tables**: 0 (W:0 R:0 L:0) | **Taches**: 1 | **Expressions**: 10

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **37.1** | [**Recuperation txt serveur** (37)](#t1) | MDI | - | Traitement |

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

### Tables utilisees (0)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|

### Colonnes par table (0 / 0 tables avec colonnes identifiees)

## 11. VARIABLES

### 11.1 Variables de travail (2)

Variables internes au programme.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| D | W0 Compteur In | Numeric | - |
| E | W0 Compteur Out | Numeric | 1x calcul interne |

### 11.2 Autres (3)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | > chemin | Alpha | 2x refs |
| B | > chaine | Alpha | 4x refs |
| C | > Chemin Log | Alpha | 1x refs |

## 12. EXPRESSIONS

**10 / 10 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCULATION | 2 | 0 |
| CONDITION | 4 | 0 |
| DATE | 1 | 0 |
| OTHER | 2 | 0 |
| CONCATENATION | 1 | 0 |

### 12.2 Expressions cles par type

#### CALCULATION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 8 | `[F]+1` | - |
| CALCULATION | 7 | `W0 Compteur Out [E]+1` | - |

#### CONDITION (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 3 | `Trim (> Chemin Log [C])` | - |
| CONDITION | 4 | `Trim(> chaine [B])<>''` | - |
| CONDITION | 9 | `MID (> chaine [B],19,1)='+'` | - |
| CONDITION | 10 | `MID (> chaine [B],19,1)='-'` | - |

#### DATE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| DATE | 5 | `Date ()` | - |

#### OTHER (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 6 | `Time ()` | - |
| OTHER | 2 | `Translate('%club_tf_pabx%PUT.TXT')` | - |

#### CONCATENATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 1 | `Trim (> chemin [A])&'\'&Trim (> chaine [B])` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [ Puttel transfert fichier (IDE 36)](POO-IDE-36.md) -> **Recuperation In/Out (IDE 37)**

```mermaid
graph LR
    T37[37 Recuperation InOut]
    style T37 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC24[24 Batch sur PABX]
    style CC24 fill:#f59e0b
    CC35[35 Execution PUT TXT]
    style CC35 fill:#f59e0b
    CC36[36 Puttel transfert fi...]
    style CC36 fill:#3fb950
    CC35 --> CC36
    CC24 --> CC35
    CC1 --> CC24
    CC36 --> T37
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [36](POO-IDE-36.md) |  Puttel transfert fichier | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T37[37 Recuperation InOut]
    style T37 fill:#58a6ff
    C69[69 Check]
    T37 --> C69
    style C69 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [69](POO-IDE-69.md) | Check | 1 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 14 | Programme compact |
| Expressions | 10 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 1 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 14) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 0 ecran, 1 traitement)

- **Strategie** : 1 service(s) backend injectable(s) (Domain Services).
- 1 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| [Check (IDE 69)](POO-IDE-69.md) | Sous-programme | 1x | Normale - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 17:49*
