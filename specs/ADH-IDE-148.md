# ADH IDE 148 - Devises RAZ WS

> **Analyse**: Phases 1-4 2026-02-07 03:50 -> 03:30 (23h40min) | Assemblage 03:30
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | ADH |
| IDE Position | 148 |
| Nom Programme | Devises RAZ WS |
| Fichier source | `Prg_148.xml` |
| Dossier IDE | Change |
| Taches | 3 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |
| Complexite | **BASSE** (score 0/100) |

## 2. DESCRIPTION FONCTIONNELLE

**ADH IDE 148 - Devises RAZ WS** est un programme de synchronisation critique appelé à chaque ouverture et fermeture de caisse pour maintenir la cohérence des devises en session. Le programme traite deux flux distincts : les moyens de réglement unitaires (table 50) via la tâche UNI et les moyens bilatéraux (table 139) via la tâche BI, en fonction d'un paramètre discriminant. Cette bifurcation est déterminée par la variable E (Param UNI/BI) qui achemine le traitement vers l'une ou l'autre tâche sans écrire en base de données—le programme agit comme un synchroniseur de référentiels consultant les tables moyens_reglement_mor pour assurer que les devises en cours de session caisse restent alignées.

Le programme ne contient aucun code mort (zéro lignes désactivées), aucune condition constante et aucun appel externe, ce qui en fait un candidat de migration facile. Ses 58 lignes se répartissent entre une orchestration principale (8 lignes) et deux tâches de traitement indépendantes qui lisent les mêmes tables de référence mais appliquent des logiques métier légèrement différentes selon le mode de réglement. L'absence de persistance spécifique suggère que la synchronisation modifie uniquement l'état mémoire de la session caisse, retourné à l'appelant pour que les opérations suivantes disposent d'une vue cohérente des devises disponibles.

Appelé massivement depuis quatre programmes critiques (ouverture/fermeture caisse en versions 142 et 144, soit 9 appels au total), **ADH IDE 148** est essentiel au moteur transactionnel de la caisse multidevise et représente une obligation réglementaire pour les installations de paiement français/espagnoles. Sa migration en endpoint API simple (`POST /caisse/devise-sync?mode=UNI|BI`) permettrait de consolider cette logique métier sans risque de régression.

## 3. BLOCS FONCTIONNELS

### 3.1 Initialisation (3 taches)

Reinitialisation d'etats et variables de travail.

---

#### <a id="t1"></a>148 - Devises RAZ WS

**Role** : Reinitialisation : Devises RAZ WS.

---

#### <a id="t2"></a>148.1 - Devises RAZ WS

**Role** : Reinitialisation : Devises RAZ WS.

---

#### <a id="t3"></a>148.2 - Devises RAZ WS

**Role** : Reinitialisation : Devises RAZ WS.


## 5. REGLES METIER

2 regles identifiees:

### Autres (2 regles)

#### <a id="rm-RM-001"></a>[RM-001] Condition: Param UNI/BI [E] different de 'B'

| Element | Detail |
|---------|--------|
| **Condition** | `Param UNI/BI [E]<>'B'` |
| **Si vrai** | Action si vrai |
| **Variables** | ER (Param UNI/BI) |
| **Expression source** | Expression 1 : `Param UNI/BI [E]<>'B'` |
| **Exemple** | Si Param UNI/BI [E]<>'B' â†’ Action si vrai |

#### <a id="rm-RM-002"></a>[RM-002] Condition: Param UNI/BI [E] egale 'B'

| Element | Detail |
|---------|--------|
| **Condition** | `Param UNI/BI [E]='B'` |
| **Si vrai** | Action si vrai |
| **Variables** | ER (Param UNI/BI) |
| **Expression source** | Expression 2 : `Param UNI/BI [E]='B'` |
| **Exemple** | Si Param UNI/BI [E]='B' â†’ Action si vrai |

## 6. CONTEXTE

- **Appele par**: [Ouverture caisse (IDE 122)](ADH-IDE-122.md), [Fermeture caisse (IDE 131)](ADH-IDE-131.md), [Ouverture caisse 143 (IDE 297)](ADH-IDE-297.md), [Fermeture caisse 144 (IDE 299)](ADH-IDE-299.md)
- **Appelle**: 0 programmes | **Tables**: 3 (W:0 R:2 L:1) | **Taches**: 3 | **Expressions**: 2

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (3 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **148.1** | [**Devises RAZ WS** (148)](#t1) | MDI | - | Initialisation |
| 148.1.1 | [Devises RAZ WS (148.1)](#t2) | MDI | - | |
| 148.1.2 | [Devises RAZ WS (148.2)](#t3) | MDI | - | |

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
| 139 | moyens_reglement_mor | Reglements / paiements | DB | R |   |   | 1 |
| 50 | moyens_reglement_mor | Reglements / paiements | DB | R |   |   | 1 |
| 232 | gestion_devise_session | Sessions de caisse | DB |   |   | L | 2 |

### Colonnes par table (3 / 2 tables avec colonnes identifiees)

<details>
<summary>Table 139 - moyens_reglement_mor (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | Param societe | R | Alpha |
| B | Param devise locale | R | Alpha |
| C | Param quand | R | Alpha |
| D | Param Type | R | Alpha |
| E | RUPTURE_DEV_MOP | R | Alpha |

</details>

<details>
<summary>Table 50 - moyens_reglement_mor (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | Param societe | R | Alpha |
| B | Param devise locale | R | Alpha |
| C | Param quand | R | Alpha |
| D | Param Type | R | Alpha |

</details>

## 11. VARIABLES

### 11.1 Autres (5)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| EN | Param societe | Alpha | - |
| EO | Param devise locale | Alpha | - |
| EP | Param quand | Alpha | - |
| EQ | Param type | Alpha | - |
| ER | Param UNI/BI | Alpha | 2x refs |

## 12. EXPRESSIONS

**2 / 2 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONDITION | 2 | 2 |

### 12.2 Expressions cles par type

#### CONDITION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 2 | `Param UNI/BI [E]='B'` | [RM-002](#rm-RM-002) |
| CONDITION | 1 | `Param UNI/BI [E]<>'B'` | [RM-001](#rm-RM-001) |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Ouverture caisse (IDE 122)](ADH-IDE-122.md) -> **Devises RAZ WS (IDE 148)**

Main -> ... -> [Fermeture caisse (IDE 131)](ADH-IDE-131.md) -> **Devises RAZ WS (IDE 148)**

Main -> ... -> [Ouverture caisse 143 (IDE 297)](ADH-IDE-297.md) -> **Devises RAZ WS (IDE 148)**

Main -> ... -> [Fermeture caisse 144 (IDE 299)](ADH-IDE-299.md) -> **Devises RAZ WS (IDE 148)**

```mermaid
graph LR
    T148[148 Devises RAZ WS]
    style T148 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC163[163 Menu caisse GM - s...]
    style CC163 fill:#f59e0b
    CC281[281 Fermeture Sessions]
    style CC281 fill:#f59e0b
    CC298[298 Gestion caisse 142]
    style CC298 fill:#f59e0b
    CC121[121 Gestion caisse]
    style CC121 fill:#f59e0b
    CC131[131 Fermeture caisse]
    style CC131 fill:#3fb950
    CC122[122 Ouverture caisse]
    style CC122 fill:#3fb950
    CC299[299 Fermeture caisse 144]
    style CC299 fill:#3fb950
    CC297[297 Ouverture caisse 143]
    style CC297 fill:#3fb950
    CC121 --> CC122
    CC298 --> CC122
    CC121 --> CC131
    CC298 --> CC131
    CC121 --> CC297
    CC298 --> CC297
    CC121 --> CC299
    CC298 --> CC299
    CC163 --> CC121
    CC281 --> CC121
    CC163 --> CC298
    CC281 --> CC298
    CC1 --> CC163
    CC1 --> CC281
    CC122 --> T148
    CC131 --> T148
    CC297 --> T148
    CC299 --> T148
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [122](ADH-IDE-122.md) | Ouverture caisse | 3 |
| [131](ADH-IDE-131.md) | Fermeture caisse | 2 |
| [297](ADH-IDE-297.md) | Ouverture caisse 143 | 2 |
| [299](ADH-IDE-299.md) | Fermeture caisse 144 | 2 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T148[148 Devises RAZ WS]
    style T148 fill:#58a6ff
    NONE[Aucun callee]
    T148 -.-> NONE
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
| Lignes de logique | 58 | Programme compact |
| Expressions | 2 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 58) | Code sain |
| Regles metier | 2 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Initialisation (3 taches: 0 ecran, 3 traitements)

- **Strategie** : Constructeur/methode `InitAsync()` dans l'orchestrateur.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-08 03:32*
