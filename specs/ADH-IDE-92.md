# ADH IDE 92 - flag ligne boutique

> **Analyse**: Phases 1-4 2026-02-07 03:47 -> 02:30 (22h42min) | Assemblage 02:30
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | ADH |
| IDE Position | 92 |
| Nom Programme | flag ligne boutique |
| Fichier source | `Prg_92.xml` |
| Dossier IDE | General |
| Taches | 2 (0 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 0 |
| Complexite | **BASSE** (score 7/100) |

## 2. DESCRIPTION FONCTIONNELLE

Le programme **ADH IDE 92** est un utilitaire léger qui marque les lignes de factures boutique en mettant à jour la table `maj_appli_tpe` avec les informations de société et de compte reçues en paramètres. Appelé par trois variantes de traitement de factures (ADH IDE 89, 54 et 97), il joue un rôle critique dans le cycle de règlement des comptes en permettant la traçabilité des transactions. Avec seulement 2 tâches imbriquées et 5 expressions, le code est extrêmement compact et sans dépendances externes.

La logique métier est minimaliste : le programme accepte deux paramètres d'entrée (Societe et Compte), effectue une vérification conditionnelle basique sur une variable intermédiaire (G = 0), puis exécute l'écriture des deux champs de la table cible. Aucun sous-programme n'est appelé, ce qui en fait un programme terminal dans la chaîne d'appels. Son statut "non-orphelin" est confirmé par ses trois appelants directs intégrés dans les flux de caisse, de settlement et de checkout.

La complexité très basse (7/100), le code sain à 100% (aucune ligne désactivée), et la responsabilité unique clairement définie font de ce programme un candidat idéal pour la migration vers un service backend C# injectable et testable.

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (2 taches)

Traitements internes.

---

#### <a id="t1"></a>92 - flag ligne boutique

**Role** : Traitement : flag ligne boutique.

---

#### <a id="t2"></a>92.1 - flag ligne

**Role** : Traitement : flag ligne.


## 5. REGLES METIER

1 regles identifiees:

### Autres (1 regles)

#### <a id="rm-RM-001"></a>[RM-001] Condition: [G] egale 0

| Element | Detail |
|---------|--------|
| **Condition** | `[G] = 0` |
| **Si vrai** | Action si vrai |
| **Expression source** | Expression 5 : `[G] = 0` |
| **Exemple** | Si [G] = 0 â†’ Action si vrai |

## 6. CONTEXTE

- **Appele par**: [Factures (Tble Compta&Vent (IDE 89)](ADH-IDE-89.md), [Factures_Check_Out (IDE 54)](ADH-IDE-54.md), [Factures (Tble Compta&Vent) V3 (IDE 97)](ADH-IDE-97.md)
- **Appelle**: 0 programmes | **Tables**: 1 (W:1 R:0 L:0) | **Taches**: 2 | **Expressions**: 5

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (2 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **92.1** | [**flag ligne boutique** (92)](#t1) | - | - | Traitement |
| 92.1.1 | [flag ligne (92.1)](#t2) | - | - | |

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
| 866 | maj_appli_tpe |  | DB |   | **W** |   | 2 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 866 - maj_appli_tpe (**W**) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | p.Societe | W | Unicode |
| B | p.Compte | W | Numeric |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (2)

Variables recues du programme appelant ([Factures (Tble Compta&Vent (IDE 89)](ADH-IDE-89.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| EN | p.Societe | Unicode | 1x parametre entrant |
| EO | p.Compte | Numeric | 1x parametre entrant |

## 12. EXPRESSIONS

**5 / 5 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONDITION | 1 | 5 |
| CONSTANTE | 1 | 0 |
| CAST_LOGIQUE | 1 | 0 |
| OTHER | 2 | 0 |

### 12.2 Expressions cles par type

#### CONDITION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 5 | `[G] = 0` | [RM-001](#rm-RM-001) |

#### CONSTANTE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 2 | `'R'` | - |

#### CAST_LOGIQUE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 1 | `'TRUE'LOG` | - |

#### OTHER (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 4 | `p.Compte [B]` | - |
| OTHER | 3 | `p.Societe [A]` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Factures (Tble Compta&Vent (IDE 89)](ADH-IDE-89.md) -> **flag ligne boutique (IDE 92)**

Main -> ... -> [Factures_Check_Out (IDE 54)](ADH-IDE-54.md) -> **flag ligne boutique (IDE 92)**

Main -> ... -> [Factures (Tble Compta&Vent) V3 (IDE 97)](ADH-IDE-97.md) -> **flag ligne boutique (IDE 92)**

```mermaid
graph LR
    T92[92 flag ligne boutique]
    style T92 fill:#58a6ff
    CC287[287 Solde Easy Check Out]
    style CC287 fill:#8b5cf6
    CC193[193 Solde compte fin s...]
    style CC193 fill:#8b5cf6
    CC313[313 Easy Check-Out ===...]
    style CC313 fill:#8b5cf6
    CC190[190 Menu solde dun compte]
    style CC190 fill:#8b5cf6
    CC163[163 Menu caisse GM - s...]
    style CC163 fill:#8b5cf6
    CC283[283 Easy Check-Out ===...]
    style CC283 fill:#8b5cf6
    CC64[64 Solde Easy Check Out]
    style CC64 fill:#8b5cf6
    CC280[280 Lanceur Facture]
    style CC280 fill:#8b5cf6
    CC54[54 Factures_Check_Out]
    style CC54 fill:#3fb950
    CC97[97 Factures Tble Compt...]
    style CC97 fill:#3fb950
    CC89[89 Factures Tble Compt...]
    style CC89 fill:#3fb950
    CC64 --> CC54
    CC280 --> CC54
    CC283 --> CC54
    CC287 --> CC54
    CC313 --> CC54
    CC163 --> CC54
    CC190 --> CC54
    CC193 --> CC54
    CC64 --> CC89
    CC280 --> CC89
    CC283 --> CC89
    CC287 --> CC89
    CC313 --> CC89
    CC163 --> CC89
    CC190 --> CC89
    CC193 --> CC89
    CC64 --> CC97
    CC280 --> CC97
    CC283 --> CC97
    CC287 --> CC97
    CC313 --> CC97
    CC163 --> CC97
    CC190 --> CC97
    CC193 --> CC97
    CC54 --> T92
    CC89 --> T92
    CC97 --> T92
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [89](ADH-IDE-89.md) | Factures (Tble Compta&Vent | 2 |
| [54](ADH-IDE-54.md) | Factures_Check_Out | 1 |
| [97](ADH-IDE-97.md) | Factures (Tble Compta&Vent) V3 | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T92[92 flag ligne boutique]
    style T92 fill:#58a6ff
    NONE[Aucun callee]
    T92 -.-> NONE
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
| Lignes de logique | 17 | Programme compact |
| Expressions | 5 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 17) | Code sain |
| Regles metier | 1 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (2 taches: 0 ecran, 2 traitements)

- **Strategie** : 2 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| maj_appli_tpe | Table WRITE (Database) | 2x | Schema + repository |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-08 02:32*
