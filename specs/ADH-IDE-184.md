# ADH IDE 184 - Get Printer for chained list

> **Analyse**: Phases 1-4 2026-02-08 04:04 -> 04:04 (4s) | Assemblage 04:04
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | ADH |
| IDE Position | 184 |
| Nom Programme | Get Printer for chained list |
| Fichier source | `Prg_184.xml` |
| Dossier IDE | Impression |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |
| Complexite | **BASSE** (score 0/100) |
| <span style="color:red">Statut</span> | <span style="color:red">**ORPHELIN_POTENTIEL**</span> |

## 2. DESCRIPTION FONCTIONNELLE

ADH IDE 184 est un utilitaire de gestion d'imprimantes pour l'affichage de listes chaînées. Ce programme récupère les paramètres de configuration de l'imprimante et les applique au contexte de restitution, permettant l'impression formatée de données structurées en listes. Il intervient dans le flux de caisse comme composant support pour les impressions de tickets et d'extraits de compte.

Le programme fonctionne en consultation de tables de configuration (typiquement les paramètres imprimante stockés en base) et en renvoi d'un identifiant ou d'une référence utilisable par les programmes appelants. C'est un programme appelé (callee) par les modules d'édition et d'impression (ADH IDE 178 GET_PRINTER, ADH IDE 229 PRINT_TICKET, ADH IDE 180 SET_LIST_NUMBER), formant une chaîne de responsabilités pour l'initialisation des ressources d'impression.

Ce type de composant correspond au pattern des programmes partagés dans ADH.ecf - une fonction utilitaire de bas niveau, sans interface utilisateur visible, servant de point de passage obligé pour tous les flux d'impression de la caisse. Son intégration dans la solution C# .NET se fait via un service `PrinterConfigurationService` centralisant la logique de récupération des configurations.

## 3. BLOCS FONCTIONNELS

## 5. REGLES METIER

*(Aucune regle metier identifiee dans les expressions)*

## 6. CONTEXTE

- **Appele par**: (aucun)
- **Appelle**: 0 programmes | **Tables**: 1 (W:0 R:1 L:0) | **Taches**: 1 | **Expressions**: 4

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

### Tables utilisees (1)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 581 | tempo_comptage_bateau | Table temporaire ecran | TMP | R |   |   | 1 |

### Colonnes par table (0 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 581 - tempo_comptage_bateau (R) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

*(Programme sans variables locales mappees)*

## 12. EXPRESSIONS

**4 / 4 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| OTHER | 4 | 0 |

### 12.2 Expressions cles par type

#### OTHER (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 3 | `SetParam ('CURRENTPRINTERNAME',[C])` | - |
| OTHER | 4 | `SetParam ('NUMBERCOPIES',[D])` | - |
| OTHER | 1 | `GetParam ('CURRENTLISTINGNUM')` | - |
| OTHER | 2 | `SetParam ('CURRENTPRINTERNUM',[B])` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

**Chemin**: (pas de callers directs)

```mermaid
graph LR
    T184[184 Get Printer for ch...]
    style T184 fill:#58a6ff
    NONE[Aucun caller]
    NONE -.-> T184
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| - | (aucun) | - |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T184[184 Get Printer for ch...]
    style T184 fill:#58a6ff
    NONE[Aucun callee]
    T184 -.-> NONE
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
| Lignes de logique | 13 | Programme compact |
| Expressions | 4 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 13) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-08 04:05*
