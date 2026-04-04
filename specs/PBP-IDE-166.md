# PBP IDE 166 - Suppression nationalite

> **Analyse**: Phases 1-4 2026-02-03 15:34 -> 15:35 (14s) | Assemblage 15:35
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBP |
| IDE Position | 166 |
| Nom Programme | Suppression nationalite |
| Fichier source | `Prg_166.xml` |
| Dossier IDE | Liste |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Suppression nationalite** assure la gestion complete de ce processus, accessible depuis [  Imprim GM present planning (IDE 165)](PBP-IDE-165.md), [  Imprim GM depart comptage (IDE 171)](PBP-IDE-171.md), [  Imprim AVPBDR toutes GM (IDE 176)](PBP-IDE-176.md), [Imprim GM present planning CL (IDE 251)](PBP-IDE-251.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

**Donnees modifiees** : 1 tables en ecriture (tempo_heures).

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>166 - Suppression nationalite

**Role** : Traitement : Suppression nationalite.


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [  Imprim GM present planning (IDE 165)](PBP-IDE-165.md), [  Imprim GM depart comptage (IDE 171)](PBP-IDE-171.md), [  Imprim AVPBDR toutes GM (IDE 176)](PBP-IDE-176.md), [Imprim GM present planning CL (IDE 251)](PBP-IDE-251.md)
- **Appelle**: 0 programmes | **Tables**: 1 (W:1 R:0 L:0) | **Taches**: 1 | **Expressions**: 2

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **166.1** | [**Suppression nationalite** (166)](#t1) | MDI | - | Traitement |

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
| 600 | tempo_heures | Table temporaire ecran | TMP |   | **W** |   | 1 |

### Colonnes par table (0 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 600 - tempo_heures (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

*(Programme sans variables locales mappees)*

## 12. EXPRESSIONS

**2 / 2 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONSTANTE | 1 | 0 |
| REFERENCE_VG | 1 | 0 |

### 12.2 Expressions cles par type

#### CONSTANTE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 2 | `'PNT'` | - |

#### REFERENCE_VG (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 1 | `VG1` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [  Imprim GM present planning (IDE 165)](PBP-IDE-165.md) -> **Suppression nationalite (IDE 166)**

Main -> ... -> [  Imprim GM depart comptage (IDE 171)](PBP-IDE-171.md) -> **Suppression nationalite (IDE 166)**

Main -> ... -> [  Imprim AVPBDR toutes GM (IDE 176)](PBP-IDE-176.md) -> **Suppression nationalite (IDE 166)**

Main -> ... -> [Imprim GM present planning CL (IDE 251)](PBP-IDE-251.md) -> **Suppression nationalite (IDE 166)**

```mermaid
graph LR
    T166[166 Suppression nation...]
    style T166 fill:#58a6ff
    CC168[168 Liste CLients depart]
    style CC168 fill:#8b5cf6
    CC175[175 Affichage AVPBDR t...]
    style CC175 fill:#8b5cf6
    CC170[170 Affich depart comp...]
    style CC170 fill:#8b5cf6
    CC174[174 Liste CLients AVPBDR]
    style CC174 fill:#8b5cf6
    CC156[156 Liste CLients arri...]
    style CC156 fill:#8b5cf6
    CC164[164 Affich present pla...]
    style CC164 fill:#8b5cf6
    CC162[162 Liste Clients present]
    style CC162 fill:#8b5cf6
    CC165[165 Imprim GM present ...]
    style CC165 fill:#3fb950
    CC171[171 Imprim GM depart c...]
    style CC171 fill:#3fb950
    CC251[251 Imprim GM present ...]
    style CC251 fill:#3fb950
    CC176[176 Imprim AVPBDR tout...]
    style CC176 fill:#3fb950
    CC162 --> CC165
    CC164 --> CC165
    CC168 --> CC165
    CC170 --> CC165
    CC156 --> CC165
    CC174 --> CC165
    CC175 --> CC165
    CC162 --> CC171
    CC164 --> CC171
    CC168 --> CC171
    CC170 --> CC171
    CC156 --> CC171
    CC174 --> CC171
    CC175 --> CC171
    CC162 --> CC176
    CC164 --> CC176
    CC168 --> CC176
    CC170 --> CC176
    CC156 --> CC176
    CC174 --> CC176
    CC175 --> CC176
    CC162 --> CC251
    CC164 --> CC251
    CC168 --> CC251
    CC170 --> CC251
    CC156 --> CC251
    CC174 --> CC251
    CC175 --> CC251
    CC165 --> T166
    CC171 --> T166
    CC176 --> T166
    CC251 --> T166
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [165](PBP-IDE-165.md) |   Imprim GM present planning | 1 |
| [171](PBP-IDE-171.md) |   Imprim GM depart comptage | 1 |
| [176](PBP-IDE-176.md) |   Imprim AVPBDR toutes GM | 1 |
| [251](PBP-IDE-251.md) | Imprim GM present planning CL | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T166[166 Suppression nation...]
    style T166 fill:#58a6ff
    NONE[Aucun callee]
    T166 -.-> NONE
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
| Lignes de logique | 3 | Programme compact |
| Expressions | 2 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 3) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 0 ecran, 1 traitement)

- **Strategie** : 1 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| tempo_heures | Table WRITE (Temp) | 1x | Schema + repository |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 15:35*
