# ADH IDE 178 - Set Village Address

> **Analyse**: Phases 1-4 2026-02-07 03:52 -> 03:57 (24h04min) | Assemblage 03:57
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | ADH |
| IDE Position | 178 |
| Nom Programme | Set Village Address |
| Fichier source | `Prg_178.xml` |
| Dossier IDE | General |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 0 |
| Complexite | **BASSE** (score 0/100) |

## 2. DESCRIPTION FONCTIONNELLE

ADH IDE 178 est un utilitaire d'impression pour configurer les paramètres d'adresse du village. Ce programme lit une seule table (pv_budget) et mappe ses colonnes dans dix paramètres distincts : identifiant club, nom, adresses (ligne 1 et 2), code postal, téléphone, contact, email, SIREN et numéro de TVA. Les six derniers paramètres appliquent une fonction Trim() pour nettoyer les espaces.

C'est un programme batch sans écran d'interaction directe, classé comme composant partagé dans ADH.ecf (ECF Sessions_Reprises). Il n'effectue aucune modification de données et n'appelle aucun autre programme ; sa seule responsabilité est d'extraire et préparer les informations de village pour les opérations d'affichage ou d'impression. Avec ses 30 lignes de code, zéro dépendances internes et pas de logique métier complexe, il représente un cas d'école pour une migration simple vers un service TypeScript/C#.

Le programme est appelable depuis plusieurs modules (PBP, PVE) via son PublicName GET_PRINTER, ce qui le rend non-orphelin malgré l'absence d'appels directs identifiés dans la chaîne principale ADH. C'est un pur collecteur de données sans effets de bord.

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>178 - Set Village Address

**Role** : Traitement : Set Village Address.


## 5. REGLES METIER

*(Aucune regle metier identifiee dans les expressions)*

## 6. CONTEXTE

- **Appele par**: (aucun)
- **Appelle**: 0 programmes | **Tables**: 1 (W:0 R:1 L:0) | **Taches**: 1 | **Expressions**: 10

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **178.1** | [**Set Village Address** (178)](#t1) | MDI | - | Traitement |

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
| 372 | pv_budget |  | DB | R |   |   | 1 |

### Colonnes par table (0 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 372 - pv_budget (R) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

*(Programme sans variables locales mappees)*

## 12. EXPRESSIONS

**10 / 10 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| OTHER | 4 | 0 |
| STRING | 6 | 0 |

### 12.2 Expressions cles par type

#### OTHER (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 3 | `SetParam ('VI_ADR1',[D])` | - |
| OTHER | 4 | `SetParam ('VI_ADR2',[E])` | - |
| OTHER | 1 | `SetParam ('VI_CLUB',[B])` | - |
| OTHER | 2 | `SetParam ('VI_NAME',[C])` | - |

#### STRING (6 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| STRING | 8 | `SetParam ('VI_MAIL',Trim([I]))` | - |
| STRING | 9 | `SetParam ('VI_SIRE',Trim([J]))` | - |
| STRING | 10 | `SetParam ('VI_VATN',Trim([K]))` | - |
| STRING | 5 | `SetParam ('VI_ZIPC',Trim([F]))` | - |
| STRING | 6 | `SetParam ('VI_PHON',Trim([G]))` | - |
| ... | | *+1 autres* | |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

**Chemin**: (pas de callers directs)

```mermaid
graph LR
    T178[178 Set Village Address]
    style T178 fill:#58a6ff
    NONE[Aucun caller]
    NONE -.-> T178
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| - | (aucun) | - |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T178[178 Set Village Address]
    style T178 fill:#58a6ff
    NONE[Aucun callee]
    T178 -.-> NONE
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
| Lignes de logique | 30 | Programme compact |
| Expressions | 10 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 0 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 30) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 0 ecran, 1 traitement)

- **Strategie** : 1 service(s) backend injectable(s) (Domain Services).
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-08 04:00*
