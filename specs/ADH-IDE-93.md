# ADH IDE 93 - Creation Pied Facture

> **Analyse**: Phases 1-4 2026-02-07 06:56 -> 02:32 (19h35min) | Assemblage 02:32
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | ADH |
| IDE Position | 93 |
| Nom Programme | Creation Pied Facture |
| Fichier source | `Prg_93.xml` |
| Dossier IDE | Facturation |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |
| Complexite | **BASSE** (score 0/100) |

## 2. DESCRIPTION FONCTIONNELLE

ADH IDE 93 — **Creation Pied Facture** (Invoice Footer Creation) — est un programme batch allégé conçu pour consolider les montants de lignes facture individuelles en un résumé financier global appelé "pied de facture". À partir de 5 paramètres d'entrée (société, compte, filiation, numéro de facture et flag), le programme lit les données brutes de la table `maj_appli_tpe` (table TPE) et agrège les totaux HT (hors taxes), TTC (TTC avec taxes incluses) et TVA calculée via une formule inverse sophistiquée : TVA = (TTC / (1 + taux%)) × taux%. Ce calcul double-cumul garantit l'exactitude même quand seul le montant TTC initial est connu — un pattern courant dans les systèmes de facturation distribués.

Le programme intègre une logique métier unique (RM-001) : un traitement conditionnel activé par la variable globale VG77 qui distingue les remboursements (type 'R') de la facturation normale. Les deux approches d'accumulation parallèles (AL/AM/AN vs AU/AV/AW) permettent une validation croisée des résultats. Bien que classé comme potentiellement orphelin (zéro callers détectés), le programme est probablement appelé dynamiquement par le module de facturation PBP ou via `ProgIdx()`, car il expose un nom public (PublicName) et fait partie des composants critiques de la chaîne de facturation.

Avec ses 72 lignes de logique purement active, aucune opération d'écriture en base de données, et un flux sans état, ADH IDE 93 est un excellent exemple de service métier spécialisé : prendre des données fragmentées, les transformer en consolidation fiable, et retourner les résultats au caller sans effets secondaires. Son absence de sous-appels (callees) en fait un programme terminal robuste idéal pour les traitements de facturation transactionnels.

## 3. BLOCS FONCTIONNELS

## 5. REGLES METIER

1 regles identifiees:

### Autres (1 regles)

#### <a id="rm-RM-001"></a>[RM-001] Condition toujours vraie (flag actif)

| Element | Detail |
|---------|--------|
| **Condition** | `VG77` |
| **Si vrai** | 'TRUE'LOG |
| **Si faux** | [BD]<>'R') |
| **Expression source** | Expression 14 : `IF(VG77,'TRUE'LOG,[BD]<>'R')` |
| **Exemple** | Si VG77 â†’ 'TRUE'LOG. Sinon â†’ [BD]<>'R') |

## 6. CONTEXTE

- **Appele par**: [Factures (Tble Compta&Vent (IDE 89)](ADH-IDE-89.md), [Factures_Check_Out (IDE 54)](ADH-IDE-54.md)
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

### Tables utilisees (2)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 866 | maj_appli_tpe |  | DB | R |   |   | 1 |
| 867 | log_maj_tpe |  | DB |   |   | L | 1 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 866 - maj_appli_tpe (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | p.Societe | R | Unicode |
| B | p.Compte | R | Numeric |
| C | p.Filiation | R | Numeric |
| D | p.NumFac | R | Numeric |
| E | P.Flaguee | R | Logical |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (5)

Variables recues du programme appelant ([Factures (Tble Compta&Vent (IDE 89)](ADH-IDE-89.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| EN | p.Societe | Unicode | 1x parametre entrant |
| EO | p.Compte | Numeric | 1x parametre entrant |
| EP | p.Filiation | Numeric | 1x parametre entrant |
| EQ | p.NumFac | Numeric | 1x parametre entrant |
| ER | P.Flaguee | Logical | - |

## 12. EXPRESSIONS

**16 / 16 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CALCULATION | 4 | 0 |
| CALCUL | 2 | 0 |
| CAST_LOGIQUE | 1 | 5 |
| CONSTANTE | 2 | 0 |
| OTHER | 7 | 0 |

### 12.2 Expressions cles par type

#### CALCULATION (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 12 | `[BN]+[Z]` | - |
| CALCULATION | 13 | `[BW]+[Z]` | - |
| CALCULATION | 8 | `[BL]+[Y]` | - |
| CALCULATION | 9 | `[BU]+[Y]` | - |

#### CALCUL (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCUL | 11 | `[BV]+Round(([Z]/(1+[X]/100)*[X]/100),12,2)` | - |
| CALCUL | 10 | `[BM]+Round(([Z]/(1+[X]/100)*[X]/100),12,2)` | - |

#### CAST_LOGIQUE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 14 | `IF(VG77,'TRUE'LOG,[BD]<>'R')` | [RM-001](#rm-RM-001) |

#### CONSTANTE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 7 | `0` | - |
| CONSTANTE | 4 | `999` | - |

#### OTHER (7 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 6 | `p.Filiation [C]` | - |
| OTHER | 15 | `CndRange(VG53,'O')` | - |
| OTHER | 16 | `IsFirstRecordCycle(0)` | - |
| OTHER | 5 | `p.Compte [B]` | - |
| OTHER | 1 | `p.Societe [A]` | - |
| ... | | *+2 autres* | |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Factures (Tble Compta&Vent (IDE 89)](ADH-IDE-89.md) -> **Creation Pied Facture (IDE 93)**

Main -> ... -> [Factures_Check_Out (IDE 54)](ADH-IDE-54.md) -> **Creation Pied Facture (IDE 93)**

```mermaid
graph LR
    T93[93 Creation Pied Facture]
    style T93 fill:#58a6ff
    CC55[55 Easy Check-Out === ...]
    style CC55 fill:#8b5cf6
    CC66[66 Lancement Solde ECO]
    style CC66 fill:#8b5cf6
    CC287[287 Solde Easy Check Out]
    style CC287 fill:#f59e0b
    CC313[313 Easy Check-Out ===...]
    style CC313 fill:#f59e0b
    CC283[283 Easy Check-Out ===...]
    style CC283 fill:#f59e0b
    CC64[64 Solde Easy Check Out]
    style CC64 fill:#f59e0b
    CC280[280 Lanceur Facture]
    style CC280 fill:#f59e0b
    CC54[54 Factures_Check_Out]
    style CC54 fill:#3fb950
    CC89[89 Factures Tble Compt...]
    style CC89 fill:#3fb950
    CC64 --> CC54
    CC280 --> CC54
    CC283 --> CC54
    CC287 --> CC54
    CC313 --> CC54
    CC64 --> CC89
    CC280 --> CC89
    CC283 --> CC89
    CC287 --> CC89
    CC313 --> CC89
    CC55 --> CC64
    CC66 --> CC64
    CC55 --> CC280
    CC66 --> CC280
    CC55 --> CC283
    CC66 --> CC283
    CC55 --> CC287
    CC66 --> CC287
    CC55 --> CC313
    CC66 --> CC313
    CC54 --> T93
    CC89 --> T93
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [89](ADH-IDE-89.md) | Factures (Tble Compta&Vent | 3 |
| [54](ADH-IDE-54.md) | Factures_Check_Out | 2 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T93[93 Creation Pied Facture]
    style T93 fill:#58a6ff
    NONE[Aucun callee]
    T93 -.-> NONE
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
| Lignes de logique | 72 | Programme compact |
| Expressions | 16 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 72) | Code sain |
| Regles metier | 1 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-08 02:33*
