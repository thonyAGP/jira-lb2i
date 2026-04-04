# ADH IDE 22 - Calcul equivalent

> **Analyse**: Phases 1-4 2026-02-07 06:39 -> 01:21 (18h42min) | Assemblage 01:21
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | ADH |
| IDE Position | 22 |
| Nom Programme | Calcul equivalent |
| Fichier source | `Prg_22.xml` |
| Dossier IDE | General |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |
| Complexite | **BASSE** (score 0/100) |

## 2. DESCRIPTION FONCTIONNELLE

### 1.1 Objectif metier

**Calcul equivalent** est le **programme de conversion monetaire** qui **calcule l'equivalent en devise locale d'un montant en devise etrangere**.

**Objectif metier** : Ce programme est le moteur de calcul de change du systeme. Il recoit un montant en devise etrangere avec son mode de paiement et son type d'operation (achat/vente), puis calcule l'equivalent en devise locale en appliquant le taux de change approprie. Il gere les specificites bilaterales (Uni/BI) et les differents types d'operations. Ce programme est appele massivement (20 appels) par les programmes d'impression de recus de change et le tableau recapitulatif de fermeture de caisse.

**Calcul equivalent** assure la gestion complete de ce processus, accessible depuis [Print reçu change achat (IDE 23)](ADH-IDE-23.md), [Print reçu change vente (IDE 24)](ADH-IDE-24.md), [Tableau recap fermeture (IDE 154)](ADH-IDE-154.md).

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Consultation** (1 tache) : ecrans de recherche, selection et consultation

## 3. BLOCS FONCTIONNELS

## 5. REGLES METIER

5 regles identifiees:

### Autres (5 regles)

#### <a id="rm-RM-001"></a>[RM-001] Condition: > Type operation [J]='A' AND > Uni/BI [B] different de 'B'

| Element | Detail |
|---------|--------|
| **Condition** | `> Type operation [J]='A' AND > Uni/BI [B]<>'B'` |
| **Si vrai** | Action si vrai |
| **Variables** | EO (> Uni/BI), EW (> Type operation) |
| **Expression source** | Expression 12 : `> Type operation [J]='A' AND > Uni/BI [B]<>'B'` |
| **Exemple** | Si > Type operation [J]='A' AND > Uni/BI [B]<>'B' â†’ Action si vrai |

#### <a id="rm-RM-002"></a>[RM-002] Condition: > Type operation [J]='A' AND > Uni/BI [B] egale 'B'

| Element | Detail |
|---------|--------|
| **Condition** | `> Type operation [J]='A' AND > Uni/BI [B]='B'` |
| **Si vrai** | Action si vrai |
| **Variables** | EO (> Uni/BI), EW (> Type operation) |
| **Expression source** | Expression 13 : `> Type operation [J]='A' AND > Uni/BI [B]='B'` |
| **Exemple** | Si > Type operation [J]='A' AND > Uni/BI [B]='B' â†’ Action si vrai |

#### <a id="rm-RM-003"></a>[RM-003] Condition: > Uni/BI [B] different de 'B'

| Element | Detail |
|---------|--------|
| **Condition** | `> Uni/BI [B]<>'B'` |
| **Si vrai** | Action si vrai |
| **Variables** | EO (> Uni/BI) |
| **Expression source** | Expression 14 : `> Uni/BI [B]<>'B'` |
| **Exemple** | Si > Uni/BI [B]<>'B' â†’ Action si vrai |

#### <a id="rm-RM-004"></a>[RM-004] Condition: > Uni/BI [B] egale 'B'

| Element | Detail |
|---------|--------|
| **Condition** | `> Uni/BI [B]='B'` |
| **Si vrai** | Action si vrai |
| **Variables** | EO (> Uni/BI) |
| **Expression source** | Expression 15 : `> Uni/BI [B]='B'` |
| **Exemple** | Si > Uni/BI [B]='B' â†’ Action si vrai |

#### <a id="rm-RM-005"></a>[RM-005] Condition: > Type operation [J] different de 'A'

| Element | Detail |
|---------|--------|
| **Condition** | `> Type operation [J]<>'A'` |
| **Si vrai** | Action si vrai |
| **Variables** | EW (> Type operation) |
| **Expression source** | Expression 16 : `> Type operation [J]<>'A'` |
| **Exemple** | Si > Type operation [J]<>'A' â†’ Action si vrai |

## 6. CONTEXTE

- **Appele par**: [Print reçu change achat (IDE 23)](ADH-IDE-23.md), [Print reçu change vente (IDE 24)](ADH-IDE-24.md), [Tableau recap fermeture (IDE 154)](ADH-IDE-154.md)
- **Appelle**: 0 programmes | **Tables**: 2 (W:0 R:1 L:1) | **Taches**: 1 | **Expressions**: 16

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (0 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Traitement principal]
    DECISION{Variable B}
    PROCESS[Traitement]
    ENDOK([END OK])
    ENDKO([END KO])

    START --> INIT --> SAISIE --> DECISION
    DECISION -->|OUI| PROCESS
    DECISION -->|NON| ENDKO
    PROCESS --> ENDOK

    style START fill:#3fb950,color:#000
    style ENDOK fill:#3fb950,color:#000
    style ENDKO fill:#f85149,color:#fff
    style DECISION fill:#58a6ff,color:#000
```

> **Legende**: Vert = START/END OK | Rouge = END KO | Bleu = Decisions
> *Algorigramme auto-genere. Utiliser `/algorigramme` pour une synthese metier detaillee.*

<!-- TAB:Donnees -->

## 10. TABLES

### Tables utilisees (2)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 50 | moyens_reglement_mor | Reglements / paiements | DB | R |   |   | 1 |
| 139 | moyens_reglement_mor | Reglements / paiements | DB |   |   | L | 1 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 50 - moyens_reglement_mor (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | > Societe | R | Alpha |
| B | > Uni/BI | R | Alpha |
| C | > devise locale | R | Alpha |
| D | > nombre de decimal | R | Numeric |
| E | > Devise | R | Alpha |
| F | < cdrt devise in | R | Logical |
| G | > mode de paiement | R | Alpha |
| H | > quantite | R | Numeric |
| I | < Equivalent | R | Numeric |
| J | > Type operation | R | Alpha |
| K | > Type de devise | R | Numeric |

</details>

## 11. VARIABLES

### 11.1 Autres (11)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| EN | > Societe | Alpha | 1x refs |
| EO | > Uni/BI | Alpha | 4x refs |
| EP | > devise locale | Alpha | - |
| EQ | > nombre de decimal | Numeric | 3x refs |
| ER | > Devise | Alpha | 1x refs |
| ES | < cdrt devise in | Logical | - |
| ET | > mode de paiement | Alpha | 1x refs |
| EU | > quantite | Numeric | 3x refs |
| EV | < Equivalent | Numeric | - |
| EW | > Type operation | Alpha | 4x refs |
| EX | > Type de devise | Numeric | 1x refs |

## 12. EXPRESSIONS

**16 / 16 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONDITION | 13 | 5 |
| CONSTANTE | 2 | 0 |
| CAST_LOGIQUE | 1 | 0 |

### 12.2 Expressions cles par type

#### CONDITION (13 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 13 | `> Type operation [J]='A' AND > Uni/BI [B]='B'` | [RM-002](#rm-RM-002) |
| CONDITION | 14 | `> Uni/BI [B]<>'B'` | [RM-003](#rm-RM-003) |
| CONDITION | 16 | `> Type operation [J]<>'A'` | [RM-005](#rm-RM-005) |
| CONDITION | 12 | `> Type operation [J]='A' AND > Uni/BI [B]<>'B'` | [RM-001](#rm-RM-001) |
| CONDITION | 15 | `> Uni/BI [B]='B'` | [RM-004](#rm-RM-004) |
| ... | | *+8 autres* | |

#### CONSTANTE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 6 | `'O'` | - |
| CONSTANTE | 4 | `''` | - |

#### CAST_LOGIQUE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 10 | `'FALSE'LOG` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Print reçu change achat (IDE 23)](ADH-IDE-23.md) -> **Calcul equivalent (IDE 22)**

Main -> ... -> [Print reçu change vente (IDE 24)](ADH-IDE-24.md) -> **Calcul equivalent (IDE 22)**

Main -> ... -> [Tableau recap fermeture (IDE 154)](ADH-IDE-154.md) -> **Calcul equivalent (IDE 22)**

```mermaid
graph LR
    T22[22 Calcul equivalent]
    style T22 fill:#58a6ff
    CC163[163 Menu caisse GM - s...]
    style CC163 fill:#8b5cf6
    CC131[131 Fermeture caisse]
    style CC131 fill:#f59e0b
    CC193[193 Solde compte fin s...]
    style CC193 fill:#f59e0b
    CC299[299 Fermeture caisse 144]
    style CC299 fill:#f59e0b
    CC151[151 Reimpression ticke...]
    style CC151 fill:#f59e0b
    CC25[25 Change GM]
    style CC25 fill:#f59e0b
    CC174[174 VersementRetrait]
    style CC174 fill:#f59e0b
    CC23[23 Print reçu change a...]
    style CC23 fill:#3fb950
    CC24[24 Print reçu change v...]
    style CC24 fill:#3fb950
    CC154[154 Tableau recap ferm...]
    style CC154 fill:#3fb950
    CC25 --> CC23
    CC174 --> CC23
    CC193 --> CC23
    CC131 --> CC23
    CC151 --> CC23
    CC299 --> CC23
    CC25 --> CC24
    CC174 --> CC24
    CC193 --> CC24
    CC131 --> CC24
    CC151 --> CC24
    CC299 --> CC24
    CC25 --> CC154
    CC174 --> CC154
    CC193 --> CC154
    CC131 --> CC154
    CC151 --> CC154
    CC299 --> CC154
    CC163 --> CC25
    CC163 --> CC174
    CC163 --> CC193
    CC163 --> CC131
    CC163 --> CC151
    CC163 --> CC299
    CC23 --> T22
    CC24 --> T22
    CC154 --> T22
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [23](ADH-IDE-23.md) | Print reçu change achat | 7 |
| [24](ADH-IDE-24.md) | Print reçu change vente | 7 |
| [154](ADH-IDE-154.md) | Tableau recap fermeture | 6 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T22[22 Calcul equivalent]
    style T22 fill:#58a6ff
    NONE[Aucun callee]
    T22 -.-> NONE
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
| Lignes de logique | 34 | Programme compact |
| Expressions | 16 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 34) | Code sain |
| Regles metier | 5 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-08 01:21*
