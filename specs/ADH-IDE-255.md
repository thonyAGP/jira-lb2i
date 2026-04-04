# ADH IDE 255 - VAD validés à imprimer

> **Version spec**: 4.0
> **Analyse**: 2026-01-27 23:13
> **Source**: `D:\Data\Migration\XPA\PMS\ADH\Source\Prg_251.xml`
> **Methode**: APEX + PDCA (Auto-generated)

---

<!-- TAB:Fonctionnel -->

## SPECIFICATION FONCTIONNELLE

### 1.1 Objectif metier

**VAD valides a imprimer** est le **gestionnaire des ventes a distance en attente d'impression** qui **affiche et permet l'impression des tickets pour les ventes VAD (Vente A Distance) validees mais pas encore imprimees**.

**Objectif metier** : Fournir un ecran de suivi des ventes effectuees a distance (VAD) qui ont ete validees mais dont le ticket n'a pas encore ete imprime. Ce programme (4 taches, 451 lignes, 16 tables en lecture) permet aux operateurs de consulter la liste des VAD en attente et de declencher l'impression des tickets correspondants. Il accede aux donnees clients, hebergement, comptables et articles pour reconstituer les informations necessaires a l'impression.

| Element | Description |
|---------|-------------|
| **Qui** | Operateur de caisse ou back-office |
| **Quoi** | Liste et impression des tickets VAD en attente |
| **Pourquoi** | Assurer que chaque vente a distance dispose de son ticket imprime |
| **Declencheur** | Acces depuis le menu des ventes ou impression tickets |
| **Resultat** | Liste des VAD affichee, tickets imprimes sur demande |

### 1.2 Regles metier

| Code | Regle | Condition |
|------|-------|-----------|
| RM-001 | Execution du traitement principal | Conditions d'entree validees |
| RM-002 | Gestion des tables (16 tables) | Acces selon mode (R/W/L) |
| RM-003 | Appels sous-programmes (0 callees) | Selon logique metier |

### 1.3 Flux utilisateur

1. Reception des parametres d'entree (0 params)
2. Initialisation et verification conditions
3. Traitement principal (4 taches)
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
| **IDE Position** | 255 |
| **Fichier XML** | `Prg_251.xml` |
| **Description** | VAD validés à imprimer |
| **Module** | ADH |
| **Public Name** |  |
| **Nombre taches** | 4 |
| **Lignes logique** | 451 |
| **Expressions** | 0 |

### 2.2 Tables

| # | Nom logique | Nom physique | Acces | Usage |
|---|-------------|--------------|-------|-------|
| 31 | gm-complet_______gmc | cafil009_dat | READ | Lecture |
| 34 | hebergement______heb | cafil012_dat | LINK/READ | Jointure+Lecture |
| 40 | comptable________cte | cafil018_dat | LINK/READ | Jointure+Lecture |
| 69 | initialisation___ini | cafil047_dat | LINK | Jointure |
| 122 | unilateral_bilateral | cafil100_dat | LINK | Jointure |
| 197 | articles_en_stock | caisse_artstock | LINK/READ | Jointure+Lecture |
| 263 | vente | caisse_vente | LINK | Jointure |
| 382 | pv_discount_reasons | pv_discountlist_dat | LINK | Jointure |
| 519 | pv_cust_rentals | %club_user%_pv_rentals_dat | LINK | Jointure |
| 596 | tempo_ecran_police | %club_user%tmp_ecrpolice_dat | LINK | Jointure |
| 804 | valeur_credit_bar_defaut | valeur_credit_bar_defaut | LINK | Jointure |
| 847 | stat_lieu_vente_date | %club_user%_stat_lieu_vente_date | LINK | Jointure |
| 945 | Table_945 |  | LINK | Jointure |

**Resume**: 16 tables accedees dont **0 en ecriture**

### 2.3 Parametres d'entree (0 parametres)

| Var | Nom | Type | Picture |
|-----|-----|------|---------|
| - | Aucun parametre | - | - |

### 2.4 Algorigramme

```mermaid
flowchart TD
    START([START - 0 params])
    INIT["Initialisation"]
    PROCESS["Traitement principal<br/>4 taches"]
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
| **Taches** | 4 |
| **Lignes logique** | 451 |
| **Expressions** | 0 |
| **Parametres** | 0 |
| **Tables accedees** | 16 |
| **Tables en ecriture** | 0 |
| **Callees niveau 1** | 0 |

---

<!-- TAB:Cartographie -->

## CARTOGRAPHIE APPLICATIVE

### 3.1 Chaine d'appels depuis Main

```mermaid
graph LR
    T[255 VAD validés à i]
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
    T[255 VAD validés à i]
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
| Taches | 4 | Simple |
| Tables | 16 | Lecture seule |
| Callees | 0 | Faible couplage |
| **Score global** | **MOYENNE** | - |

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
| 2026-01-27 23:13 | **V4.0 APEX/PDCA** - Generation automatique complete | Script |

---

*Specification V4.0 - Auto-generated with APEX/PDCA methodology*

