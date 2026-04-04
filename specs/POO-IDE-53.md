# POO IDE 53 - Fichier Tampon Retour

> **Analyse**: Phases 1-4 2026-02-03 17:55 -> 17:55 (17s) | Assemblage 17:55
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | POO |
| IDE Position | 53 |
| Nom Programme | Fichier Tampon Retour |
| Fichier source | `Prg_53.xml` |
| Dossier IDE | Pooling |
| Taches | 3 (0 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 1 |

## 2. DESCRIPTION FONCTIONNELLE

**Fichier Tampon Retour** assure la gestion complete de ce processus, accessible depuis [ Retour transfert fichier (IDE 52)](POO-IDE-52.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (3 taches) : traitements metier divers

**Donnees modifiees** : 1 tables en ecriture (tai_gm).

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (3 taches)

Traitements internes.

---

#### <a id="t1"></a>53 - Fichier Tampon PABX

**Role** : Traitement : Fichier Tampon PABX.
**Delegue a** : [Check (IDE 69)](POO-IDE-69.md)

---

#### <a id="t2"></a>53.1 - delete enregistrement vide

**Role** : Traitement : delete enregistrement vide.
**Delegue a** : [Check (IDE 69)](POO-IDE-69.md)

---

#### <a id="t3"></a>53.2 - Mise a jour file

**Role** : Traitement : Mise a jour file.
**Delegue a** : [Check (IDE 69)](POO-IDE-69.md)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [ Retour transfert fichier (IDE 52)](POO-IDE-52.md)
- **Appelle**: 1 programmes | **Tables**: 1 (W:1 R:0 L:0) | **Taches**: 3 | **Expressions**: 15

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (3 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **53.1** | [**Fichier Tampon PABX** (53)](#t1) | MDI | - | Traitement |
| 53.1.1 | [delete enregistrement vide (53.1)](#t2) | MDI | - | |
| 53.1.2 | [Mise a jour file (53.2)](#t3) | MDI | - | |

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
| 454 | tai_gm |  | DB |   | **W** |   | 2 |

### Colonnes par table (0 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 454 - tai_gm (**W**) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Variables de session (13)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| C | v. date sys | Date | - |
| D | v. time sys | Time | - |
| E | v. numero de poste | Numeric | 1x session |
| F | v. numero ligne | Numeric | 1x session |
| G | v. code autocom | Numeric | 1x session |
| H | v. sens | Alpha | 2x session |
| I | v. valeur | Numeric | 2x session |
| J | v. date | Date | - |
| K | v. time | Time | - |
| L | v. In ok | Numeric | 1x session |
| M | v. In no ok | Numeric | 1x session |
| N | v. Out ok | Numeric | 1x session |
| O | v. Out no ok | Numeric | 1x session |

### 11.2 Autres (2)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | < Compteur | Numeric | - |
| B | > chemin Get.log | Alpha | 1x refs |

## 12. EXPRESSIONS

**15 / 15 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCULATION | 4 | 0 |
| CONDITION | 6 | 0 |
| CONSTANTE | 2 | 0 |
| DATE | 1 | 0 |
| OTHER | 2 | 0 |

### 12.2 Expressions cles par type

#### CALCULATION (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 9 | `v. Out ok [N]+1` | - |
| CALCULATION | 10 | `v. Out no ok [O]+1` | - |
| CALCULATION | 7 | `v. In ok [L]+1` | - |
| CALCULATION | 8 | `v. In no ok [M]+1` | - |

#### CONDITION (6 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 13 | `v. valeur [I]=1` | - |
| CONDITION | 14 | `v. valeur [I]=0` | - |
| CONDITION | 5 | `Trim (> chemin Get.log [B])` | - |
| CONDITION | 11 | `v. sens [H]='+'` | - |
| CONDITION | 12 | `v. sens [H]='-'` | - |
| ... | | *+1 autres* | |

#### CONSTANTE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 15 | `0` | - |
| CONSTANTE | 4 | `'%club_tf_pabx%RETOUR.TCK'` | - |

#### DATE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| DATE | 1 | `Date ()` | - |

#### OTHER (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 3 | `EOF (0,1)` | - |
| OTHER | 2 | `Time ()` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [ Retour transfert fichier (IDE 52)](POO-IDE-52.md) -> **Fichier Tampon Retour (IDE 53)**

```mermaid
graph LR
    T53[53 Fichier Tampon Retour]
    style T53 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC19[19 lancement retail OD]
    style CC19 fill:#f59e0b
    CC24[24 Batch sur PABX]
    style CC24 fill:#f59e0b
    CC16[16 Transfert ODS Boutique]
    style CC16 fill:#f59e0b
    CC51[51 Execution RETOUR TXT]
    style CC51 fill:#f59e0b
    CC52[52 Retour transfert fi...]
    style CC52 fill:#3fb950
    CC16 --> CC52
    CC51 --> CC52
    CC19 --> CC16
    CC24 --> CC16
    CC19 --> CC51
    CC24 --> CC51
    CC1 --> CC19
    CC1 --> CC24
    CC52 --> T53
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [52](POO-IDE-52.md) |  Retour transfert fichier | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T53[53 Fichier Tampon Retour]
    style T53 fill:#58a6ff
    C69[69 Check]
    T53 --> C69
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
| Lignes de logique | 57 | Programme compact |
| Expressions | 15 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 1 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 57) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (3 taches: 0 ecran, 3 traitements)

- **Strategie** : 3 service(s) backend injectable(s) (Domain Services).
- 1 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| tai_gm | Table WRITE (Database) | 2x | Schema + repository |
| [Check (IDE 69)](POO-IDE-69.md) | Sous-programme | 1x | Normale - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 17:55*
