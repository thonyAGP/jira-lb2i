# PBP IDE 62 - Edition corrections effectif

> **Analyse**: Phases 1-4 2026-02-03 09:03 -> 09:03 (20s) | Assemblage 09:03
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBP |
| IDE Position | 62 |
| Nom Programme | Edition corrections effectif |
| Fichier source | `Prg_62.xml` |
| Domaine metier | Impression |
| Taches | 10 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |

## 2. DESCRIPTION FONCTIONNELLE

**Edition corrections effectif** assure la gestion complete de ce processus, accessible depuis [Effectif economat (IDE 53)](PBP-IDE-53.md), [Edition effectif mensuel (IDE 56)](PBP-IDE-56.md), [Edition effectif mensuel (IDE 413)](PBP-IDE-413.md).

Le flux de traitement s'organise en **2 blocs fonctionnels** :

- **Traitement** (7 taches) : traitements metier divers
- **Impression** (3 taches) : generation de tickets et documents

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Impression (3 taches)

- **62** - Edition corrections effectif
- **62.1** - Edition corrections effectif
- **62.2** - Edition corrections effectif

#### Phase 2 : Traitement (7 taches)

- **62.1.1** - Repas
- **62.1.2** - (sans nom)
- **62.1.3** - Qualites
- **62.2.1** - Repas
- **62.2.2** - Personnes
- **62.2.3** - Qualites
- **62.1.4** - correctif repas

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Impression (3 taches)

Generation des documents et tickets.

---

#### <a id="t1"></a>62 - Edition corrections effectif

**Role** : Generation du document : Edition corrections effectif.

---

#### <a id="t17"></a>62.1 - Edition corrections effectif

**Role** : Generation du document : Edition corrections effectif.

---

#### <a id="t27"></a>62.2 - Edition corrections effectif

**Role** : Generation du document : Edition corrections effectif.


### 3.2 Traitement (7 taches)

Traitements internes.

---

#### <a id="t19"></a>62.1.1 - Repas

**Role** : Traitement : Repas.

---

#### <a id="t21"></a>62.1.2 - (sans nom)

**Role** : Traitement interne.

---

#### <a id="t23"></a>62.1.3 - Qualites

**Role** : Traitement : Qualites.

---

#### <a id="t28"></a>62.2.1 - Repas

**Role** : Traitement : Repas.

---

#### <a id="t30"></a>62.2.2 - Personnes

**Role** : Traitement : Personnes.

---

#### <a id="t32"></a>62.2.3 - Qualites

**Role** : Traitement : Qualites.

---

#### <a id="t33"></a>62.1.4 - correctif repas

**Role** : Traitement : correctif repas.
**Variables liees** : C (P.Existe correctif ?)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Effectif economat (IDE 53)](PBP-IDE-53.md), [Edition effectif mensuel (IDE 56)](PBP-IDE-56.md), [Edition effectif mensuel (IDE 413)](PBP-IDE-413.md)
- **Appelle**: 0 programmes | **Tables**: 7 (W:0 R:4 L:3) | **Taches**: 10 | **Expressions**: 7

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (10 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **62.1** | [**Edition corrections effectif** (62)](#t1) | - | - | Impression |
| 62.1.1 | [Edition corrections effectif (62.1)](#t17) | - | - | |
| 62.1.2 | [Edition corrections effectif (62.2)](#t27) | - | - | |
| **62.2** | [**Repas** (62.1.1)](#t19) | - | - | Traitement |
| 62.2.1 | [(sans nom) (62.1.2)](#t21) | - | - | |
| 62.2.2 | [Qualites (62.1.3)](#t23) | - | - | |
| 62.2.3 | [Repas (62.2.1)](#t28) | - | - | |
| 62.2.4 | [Personnes (62.2.2)](#t30) | - | - | |
| 62.2.5 | [Qualites (62.2.3)](#t32) | - | - | |
| 62.2.6 | [correctif repas (62.1.4)](#t33) | - | - | |

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

### Tables utilisees (7)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 120 | tables_qualites__qua |  | DB | R |   |   | 1 |
| 824 | fac_pied_tva_pro |  | DB | R |   |   | 2 |
| 825 | fac_hebergement_pro | Hebergement (chambres) | DB | R |   |   | 2 |
| 826 | wording_mention_legal |  | DB |   |   | L | 2 |
| 831 | import_go_erreur_affection |  | DB | R |   |   | 2 |
| 834 | tpe_par_terminal |  | DB |   |   | L | 2 |
| 950 | Table_950 |  | MEM |   |   | L | 2 |

### Colonnes par table (1 / 4 tables avec colonnes identifiees)

<details>
<summary>Table 120 - tables_qualites__qua (R) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 824 - fac_pied_tva_pro (R) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | V.Total ajust midi | R | Numeric |
| B | V.Total ajust soir | R | Numeric |

</details>

<details>
<summary>Table 825 - fac_hebergement_pro (R) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 831 - import_go_erreur_affection (R) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (7)

Variables recues du programme appelant ([Effectif economat (IDE 53)](PBP-IDE-53.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P.Date debut | Date | - |
| B | P.Date fin | Date | - |
| C | P.Existe correctif ? | Logical | - |
| D | P.Lieu sejour | Alpha | 1x parametre entrant |
| E | P.Premier lieu sejour | Alpha | - |
| F | P.Nom lieu | Alpha | - |
| G | P.Lieu Sejour Saisie | Logical | - |

### 11.2 Variables de session (2)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| H | V.Clause where lieu sejour | Alpha | - |
| I | V.Clause where lieu sejour repa | Alpha | - |

## 12. EXPRESSIONS

**7 / 7 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| FORMAT | 1 | 0 |
| REFERENCE_VG | 1 | 0 |
| OTHER | 3 | 0 |
| CAST_LOGIQUE | 2 | 0 |

### 12.2 Expressions cles par type

#### FORMAT (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| FORMAT | 3 | `'c:\temp\'&Trim(VG33)&IF(P.Lieu sejour [D]<>'','_'&Trim(P.Lieu sejour [D])&'_','_')&'EFF_Correctifs_'&Trim(DStr(Date(),'YYYYMM'))&'.htm'` | - |

#### REFERENCE_VG (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 1 | `VG113` | - |

#### OTHER (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 6 | `{1,2}` | - |
| OTHER | 5 | `{1,1}` | - |
| OTHER | 2 | `NOT(VG113)` | - |

#### CAST_LOGIQUE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 7 | `'TRUE'LOG` | - |
| CAST_LOGIQUE | 4 | `'FALSE'LOG` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Effectif economat (IDE 53)](PBP-IDE-53.md) -> **Edition corrections effectif (IDE 62)**

Main -> ... -> [Edition effectif mensuel (IDE 56)](PBP-IDE-56.md) -> **Edition corrections effectif (IDE 62)**

Main -> ... -> [Edition effectif mensuel (IDE 413)](PBP-IDE-413.md) -> **Edition corrections effectif (IDE 62)**

```mermaid
graph LR
    T62[62 Edition corrections...]
    style T62 fill:#58a6ff
    CC148[148 Liste Gestion de C...]
    style CC148 fill:#8b5cf6
    CC152[152 Start]
    style CC152 fill:#8b5cf6
    CC63[63 Cloture saison effe...]
    style CC63 fill:#f59e0b
    CC146[146 Pilotage Gestion d...]
    style CC146 fill:#f59e0b
    CC414[414 Call Extraction]
    style CC414 fill:#f59e0b
    CC54[54 Effectif mensuel la...]
    style CC54 fill:#f59e0b
    CC64[64 Edition et envoi ef...]
    style CC64 fill:#f59e0b
    CC53[53 Effectif economat]
    style CC53 fill:#3fb950
    CC56[56 Edition effectif me...]
    style CC56 fill:#3fb950
    CC413[413 Edition effectif m...]
    style CC413 fill:#3fb950
    CC54 --> CC53
    CC64 --> CC53
    CC54 --> CC56
    CC64 --> CC56
    CC54 --> CC413
    CC64 --> CC413
    CC63 --> CC54
    CC146 --> CC54
    CC414 --> CC54
    CC63 --> CC64
    CC146 --> CC64
    CC414 --> CC64
    CC148 --> CC63
    CC152 --> CC63
    CC148 --> CC146
    CC152 --> CC146
    CC148 --> CC414
    CC152 --> CC414
    CC53 --> T62
    CC56 --> T62
    CC413 --> T62
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [53](PBP-IDE-53.md) | Effectif economat | 2 |
| [56](PBP-IDE-56.md) | Edition effectif mensuel | 1 |
| [413](PBP-IDE-413.md) | Edition effectif mensuel | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T62[62 Edition corrections...]
    style T62 fill:#58a6ff
    NONE[Aucun callee]
    T62 -.-> NONE
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
| Lignes de logique | 209 | Taille moyenne |
| Expressions | 7 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 209) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Impression (3 taches: 0 ecran, 3 traitements)

- **Strategie** : Templates HTML -> PDF via wkhtmltopdf ou Puppeteer.
- `PrintService` injectable avec choix imprimante

#### Traitement (7 taches: 0 ecran, 7 traitements)

- **Strategie** : 7 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 09:03*
