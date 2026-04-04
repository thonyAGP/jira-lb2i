# RET IDE 9 - Start

> **Analyse**: Phases 1-4 2026-02-03 20:41 -> 20:41 (15s) | Assemblage 20:41
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | RET |
| IDE Position | 9 |
| Nom Programme | Start |
| Fichier source | `Prg_9.xml` |
| Dossier IDE | Start |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 5 |

## 2. DESCRIPTION FONCTIONNELLE

**Start** assure la gestion complete de ce processus, accessible depuis [Main Program (IDE 1)](RET-IDE-1.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>9 - Start

**Role** : Traitement : Start.
**Delegue a** : [CB menu caisse/boutique (IDE 10)](RET-IDE-10.md), [lancement automatique (IDE 11)](RET-IDE-11.md), [Operation durant Cloture (IDE 12)](RET-IDE-12.md)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Main Program (IDE 1)](RET-IDE-1.md)
- **Appelle**: 5 programmes | **Tables**: 0 (W:0 R:0 L:0) | **Taches**: 1 | **Expressions**: 6

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **9.1** | [**Start** (9)](#t1) | MDI | - | Traitement |

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

*(Programme sans variables locales mappees)*

## 12. EXPRESSIONS

**6 / 6 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONSTANTE | 1 | 0 |
| CONDITION | 2 | 0 |
| OTHER | 2 | 0 |
| REFERENCE_VG | 1 | 0 |

### 12.2 Expressions cles par type

#### CONSTANTE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 4 | `'OD'` | - |

#### CONDITION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 2 | `INIGet ('[MAGIC_LOGICAL_NAMES]RunMode')='B'` | - |
| CONDITION | 1 | `INIGet ('[MAGIC_LOGICAL_NAMES]RunMode')='O'` | - |

#### OTHER (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 5 | `NOT(VG25)` | - |
| OTHER | 3 | `SetParam ('VERIF_USERB','O')` | - |

#### REFERENCE_VG (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 6 | `VG25` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Main Program (IDE 1)](RET-IDE-1.md) -> **Start (IDE 9)**

```mermaid
graph LR
    T9[9 Start]
    style T9 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC1 --> T9
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [1](RET-IDE-1.md) | Main Program | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T9[9 Start]
    style T9 fill:#58a6ff
    C10[10 CB menu caisseboutique]
    T9 --> C10
    style C10 fill:#3fb950
    C11[11 lancement automatique]
    T9 --> C11
    style C11 fill:#3fb950
    C12[12 Operation durant Cl...]
    T9 --> C12
    style C12 fill:#3fb950
    C13[13 Recuperation langue]
    T9 --> C13
    style C13 fill:#3fb950
    C14[14 Scroll GM]
    T9 --> C14
    style C14 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [10](RET-IDE-10.md) | CB menu caisse/boutique | 1 | Navigation menu |
| [11](RET-IDE-11.md) | lancement automatique | 1 | Sous-programme |
| [12](RET-IDE-12.md) | Operation durant Cloture | 1 | Fermeture session |
| [13](RET-IDE-13.md) | Recuperation langue | 1 | Recuperation donnees |
| [14](RET-IDE-14.md) | Scroll GM | 1 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 12 | Programme compact |
| Expressions | 6 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 5 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 12) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 0 ecran, 1 traitement)

- **Strategie** : 1 service(s) backend injectable(s) (Domain Services).
- 5 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| [Recuperation langue (IDE 13)](RET-IDE-13.md) | Sous-programme | 1x | Normale - Recuperation donnees |
| [Scroll GM (IDE 14)](RET-IDE-14.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Operation durant Cloture (IDE 12)](RET-IDE-12.md) | Sous-programme | 1x | Normale - Fermeture session |
| [CB menu caisse/boutique (IDE 10)](RET-IDE-10.md) | Sous-programme | 1x | Normale - Navigation menu |
| [lancement automatique (IDE 11)](RET-IDE-11.md) | Sous-programme | 1x | Normale - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 20:41*
