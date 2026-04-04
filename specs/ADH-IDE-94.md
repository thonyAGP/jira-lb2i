# ADH IDE 94 - Maj des lignes saisies archive

> **Analyse**: Phases 1-4 2026-02-07 06:56 -> 02:34 (19h37min) | Assemblage 02:34
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | ADH |
| IDE Position | 94 |
| Nom Programme | Maj des lignes saisies archive |
| Fichier source | `Prg_94.xml` |
| Dossier IDE | General |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 0 |
| Complexite | **BASSE** (score 7/100) |

## 2. DESCRIPTION FONCTIONNELLE

# ADH IDE 94 - Maj des lignes saisies archive

**Rôle dans le flux Factures**
Programme appelé depuis l'écran Factures (ADH IDE 89 - Table Compta&Vent) pour mettre à jour les lignes de facture archivées. Intervient après validation ou modification d'une saisie de facture pour synchroniser l'état archive avec les modifications effectuées.

**Logique métier**
Parcourt les lignes saisies de la facture en cours et met à jour la table `projet` (stockage persistant des lignes archivées) avec les valeurs saisies, servant de point de synchronisation entre l'écran de saisie temporaire et l'archive définitive.

**Impact en cascade**
Opération d'écriture critique qui valide la persistance des lignes de facture. Son succès détermine si les modifications saisies deviennent durables dans la base de données projet. Appelé en fin de workflow de saisie pour confirmer l'archivage.

## 3. BLOCS FONCTIONNELS

## 5. REGLES METIER

3 regles identifiees:

### Autres (3 regles)

#### <a id="rm-RM-001"></a>[RM-001] Condition: [Y] egale 0

| Element | Detail |
|---------|--------|
| **Condition** | `[Y]=0` |
| **Si vrai** | Action si vrai |
| **Expression source** | Expression 1 : `[Y]=0` |
| **Exemple** | Si [Y]=0 â†’ Action si vrai |

#### <a id="rm-RM-002"></a>[RM-002] Condition: [BH] egale 0

| Element | Detail |
|---------|--------|
| **Condition** | `[BH]=0` |
| **Si vrai** | Action si vrai |
| **Expression source** | Expression 2 : `[BH]=0` |
| **Exemple** | Si [BH]=0 â†’ Action si vrai |

#### <a id="rm-RM-003"></a>[RM-003] Condition toujours vraie (flag actif)

| Element | Detail |
|---------|--------|
| **Condition** | `P.Flague [C]` |
| **Si vrai** | 'TRUE'LOG |
| **Si faux** | 'FALSE'LOG) |
| **Variables** | EP (P.Flague) |
| **Expression source** | Expression 9 : `IF(P.Flague [C],'TRUE'LOG,'FALSE'LOG)` |
| **Exemple** | Si P.Flague [C] â†’ 'TRUE'LOG. Sinon â†’ 'FALSE'LOG) |

## 6. CONTEXTE

- **Appele par**: [Factures (Tble Compta&Vent (IDE 89)](ADH-IDE-89.md)
- **Appelle**: 0 programmes | **Tables**: 4 (W:1 R:0 L:3) | **Taches**: 1 | **Expressions**: 14

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

### Tables utilisees (4)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 746 | projet |  | DB |   | **W** |   | 1 |
| 866 | maj_appli_tpe |  | DB |   |   | L | 1 |
| 871 | Activite |  | DB |   |   | L | 1 |
| 870 | Rayons_Boutique |  | DB |   |   | L | 1 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 746 - projet (**W**) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | p.Societe | W | Unicode |
| B | p.Compte | W | Numeric |
| C | P.Flague | W | Logical |
| D | p.No_Facture | W | Numeric |
| E | p.NomFichPDF | W | Alpha |
| F | V retour Compta | W | Logical |
| G | v Retour Vente | W | Logical |
| H | v Trouvé Compta | W | Logical |
| I | v Trouvé Vente | W | Logical |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (5)

Variables recues du programme appelant ([Factures (Tble Compta&Vent (IDE 89)](ADH-IDE-89.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| EN | p.Societe | Unicode | 1x parametre entrant |
| EO | p.Compte | Numeric | 1x parametre entrant |
| EP | P.Flague | Logical | 1x parametre entrant |
| EQ | p.No_Facture | Numeric | 1x parametre entrant |
| ER | p.NomFichPDF | Alpha | 1x parametre entrant |

### 11.2 Variables de session (4)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| ES | V retour Compta | Logical | - |
| ET | v Retour Vente | Logical | - |
| EU | v Trouvé Compta | Logical | - |
| EV | v Trouvé Vente | Logical | - |

## 12. EXPRESSIONS

**14 / 14 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONDITION | 2 | 2 |
| CAST_LOGIQUE | 1 | 5 |
| DATE | 2 | 0 |
| OTHER | 9 | 0 |

### 12.2 Expressions cles par type

#### CONDITION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 2 | `[BH]=0` | [RM-002](#rm-RM-002) |
| CONDITION | 1 | `[Y]=0` | [RM-001](#rm-RM-001) |

#### CAST_LOGIQUE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 9 | `IF(P.Flague [C],'TRUE'LOG,'FALSE'LOG)` | [RM-003](#rm-RM-003) |

#### DATE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| DATE | 8 | `Date()` | - |
| DATE | 4 | `Date()` | - |

#### OTHER (9 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 12 | `[BC]` | - |
| OTHER | 11 | `[W]` | - |
| OTHER | 14 | `[S]` | - |
| OTHER | 13 | `[K]` | - |
| OTHER | 10 | `[K]` | - |
| ... | | *+4 autres* | |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Factures (Tble Compta&Vent (IDE 89)](ADH-IDE-89.md) -> **Maj des lignes saisies archive (IDE 94)**

```mermaid
graph LR
    T94[94 Maj des lignes sais...]
    style T94 fill:#58a6ff
    CC89[89 Factures Tble Compt...]
    style CC89 fill:#8b5cf6
    CC89 --> T94
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [89](ADH-IDE-89.md) | Factures (Tble Compta&Vent | 3 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T94[94 Maj des lignes sais...]
    style T94 fill:#58a6ff
    NONE[Aucun callee]
    T94 -.-> NONE
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
| Lignes de logique | 63 | Programme compact |
| Expressions | 14 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 63) | Code sain |
| Regles metier | 3 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| projet | Table WRITE (Database) | 1x | Schema + repository |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-08 02:34*
