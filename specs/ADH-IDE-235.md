# ADH IDE 235 -  Print ticket vente LEX

> **Version spec**: 4.0
> **Analyse**: 2026-01-27 23:12
> **Source**: `D:\Data\Migration\XPA\PMS\ADH\Source\Prg_231.xml`
> **Methode**: APEX + PDCA (Auto-generated)

---

<!-- TAB:Fonctionnel -->

## SPECIFICATION FONCTIONNELLE

### 1.1 Objectif metier

**Print ticket vente LEX** est le **generateur de tickets de caisse format LEX** qui **produit l'impression du ticket de vente dans un format etendu specifique aux besoins Club Med**.

**Objectif metier** : Generer et imprimer le ticket de caisse dans le format LEX (format enrichi specifique). Ce programme, plus complexe que le format standard (38 taches, 1507 lignes), inclut des informations supplementaires comme les donnees d'hebergement, les budgets, les poids (pv_weight), et d'autres donnees specifiques au contexte Club Med. Il accede a 23 tables pour composer un ticket complet repondant aux exigences particulieres de reporting et de tracabilite.

| Element | Description |
|---------|-------------|
| **Qui** | Systeme d'impression (appel automatique selon contexte LEX) |
| **Quoi** | Generation et impression du ticket de vente format LEX enrichi |
| **Pourquoi** | Produire un ticket detaille incluant informations hebergement, budget et donnees specifiques |
| **Declencheur** | Appel depuis le dispatcher d'impression (IDE 233) pour contexte LEX |
| **Resultat** | Ticket de caisse format LEX imprime ou genere en PDF |

### 1.2 Regles metier

| Code | Regle | Condition |
|------|-------|-----------|
| RM-001 | Execution du traitement principal | Conditions d'entree validees |
| RM-002 | Gestion des tables (23 tables) | Acces selon mode (R/W/L) |
| RM-003 | Appels sous-programmes (0 callees) | Selon logique metier |

### 1.3 Flux utilisateur

1. Reception des parametres d'entree (0 params)
2. Initialisation et verification conditions
3. Traitement principal (38 taches)
4. Appels sous-programmes si necessaire
5. Retour resultats

### 1.4 Cas d'erreur

| Erreur | Comportement |
|--------|--------------|
| Conditions non remplies | Abandon avec message |
| Erreur sous-programme | Propagation erreur |

---

<!-- TAB:Technique -->

## SPECIFICATION TECHNIQUE

### 2.1 Identification

| Attribut | Valeur |
|----------|--------|
| **IDE Position** | 235 |
| **Fichier XML** | `Prg_231.xml` |
| **Description** |  Print ticket vente LEX |
| **Module** | ADH |
| **Public Name** |  |
| **Nombre taches** | 38 |
| **Lignes logique** | 1507 |
| **Expressions** | 0 |

### 2.2 Tables

| # | Nom logique | Nom physique | Acces | Usage |
|---|-------------|--------------|-------|-------|
| 31 | gm-complet_______gmc | cafil009_dat | READ | Lecture |
| 34 | hebergement______heb | cafil012_dat | LINK/READ | Jointure+Lecture |
| 40 | comptable________cte | cafil018_dat | LINK/READ | Jointure+Lecture |
| 67 | tables___________tab | cafil045_dat | LINK/READ | Jointure+Lecture |
| 69 | initialisation___ini | cafil047_dat | READ | Lecture |
| 77 | articles_________art | cafil055_dat | LINK/READ | Jointure+Lecture |
| 263 | vente | caisse_vente | LINK | Jointure |
| 372 | pv_budget | pv_budget_dat | LINK | Jointure |
| 417 | pv_weight | pv_weight | LINK | Jointure |
| 596 | tempo_ecran_police | %club_user%tmp_ecrpolice_dat | LINK/READ | Jointure+Lecture |
| 728 | arc_cc_total | arc_cctotal | LINK | Jointure |
| 818 | Circuit supprime | zcircafil146 | LINK | Jointure |
| 847 | stat_lieu_vente_date | %club_user%_stat_lieu_vente_date | LINK/READ | Jointure+Lecture |
| 867 | log_maj_tpe | log_maj_tpe | READ | Lecture |
| 878 | categorie_operation_mw | categorie_operation_mw | READ | Lecture |
| 904 | Boo_AvailibleEmployees | Boo_AvailibleEmployees | LINK | Jointure |
| 1037 | Table_1037 |  | READ | Lecture |

**Resume**: 23 tables accedees dont **0 en ecriture**

### 2.3 Parametres d'entree (0 parametres)

| Var | Nom | Type | Picture |
|-----|-----|------|---------|
| - | Aucun parametre | - | - |

### 2.4 Algorigramme

```mermaid
flowchart TD
    START([START - 0 params])
    INIT["Initialisation"]
    PROCESS["Traitement principal<br/>38 taches"]
    CALLS["Appels sous-programmes<br/>0 callees"]
    ENDOK([END])

    START --> INIT --> PROCESS --> CALLS --> ENDOK

    style START fill:#3fb950
    style ENDOK fill:#f85149
    style PROCESS fill:#58a6ff
```

### 2.5 Statistiques

| Metrique | Valeur |
|----------|--------|
| **Taches** | 38 |
| **Lignes logique** | 1507 |
| **Expressions** | 0 |
| **Parametres** | 0 |
| **Tables accedees** | 23 |
| **Tables en ecriture** | 0 |
| **Callees niveau 1** | 0 |

---

<!-- TAB:Cartographie -->

## CARTOGRAPHIE APPLICATIVE

### 3.1 Chaine d'appels depuis Main

```mermaid
graph LR
    T[235  Print ticket v]
    ORPHAN([ORPHELIN ou Main])
    T -.-> ORPHAN
    style T fill:#58a6ff,color:#000
    style ORPHAN fill:#6b7280,stroke-dasharray: 5 5
```

### 3.2 Callers directs

| IDE | Programme | Nb appels |
|-----|-----------|-----------|
| - | ORPHELIN ou Main direct | - |

### 3.3 Callees (3 niveaux)

```mermaid
graph LR
    T[235  Print ticket v]
    TERM([TERMINAL])
    T -.-> TERM
    style TERM fill:#6b7280,stroke-dasharray: 5 5
    style T fill:#58a6ff,color:#000
```

| Niv | IDE | Programme | Nb appels | Status |
|-----|-----|-----------|-----------|--------|
| - | - | TERMINAL | - | - |

### 3.4 Composants ECF utilises

| ECF | IDE | Public Name | Description |
|-----|-----|-------------|-------------|
| - | - | Aucun composant ECF | - |

### 3.5 Verification orphelin

| Critere | Resultat |
|---------|----------|
| Callers actifs | 0 programmes |
| PublicName | Non defini |
| ECF partage | NON |
| **Conclusion** | **ORPHELIN** - Pas de callers actifs |

---

## NOTES MIGRATION

### Complexite

| Critere | Score | Detail |
|---------|-------|--------|
| Taches | 38 | Complexe |
| Tables | 23 | Lecture seule |
| Callees | 0 | Faible couplage |
| **Score global** | **HAUTE** | - |

### Points d'attention migration

| Point | Solution moderne |
|-------|-----------------|
| Variables globales (VG*) | Service/Repository injection |
| Tables Magic | Entity Framework / Dapper |
| CallTask | Service method calls |
| Forms | React/Angular components |

---

## HISTORIQUE

| Date | Action | Auteur |
|------|--------|--------|
| 2026-01-27 23:12 | **V4.0 APEX/PDCA** - Generation automatique complete | Script |

---

*Specification V4.0 - Auto-generated with APEX/PDCA methodology*

