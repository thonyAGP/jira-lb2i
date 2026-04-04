# ADH IDE 244 - Histo ventes payantes /PMS-605

> **Version spec**: 4.0
> **Analyse**: 2026-01-27 23:12
> **Source**: `D:\Data\Migration\XPA\PMS\ADH\Source\Prg_240.xml`
> **Methode**: APEX + PDCA (Auto-generated)

---

<!-- TAB:Fonctionnel -->

## SPECIFICATION FONCTIONNELLE

### 1.1 Objectif metier

**Histo ventes payantes /PMS-605** est le **gestionnaire d'historique des ventes payantes version PMS-605** qui **permet de consulter, modifier et annuler les ventes payantes effectuees, avec les specificites de la version 605 du PMS**.

**Objectif metier** : Fournir un ecran de consultation et de gestion de l'historique des ventes payantes. Ce programme complexe (30 taches, 1841 lignes, 33 tables dont 7 en ecriture) permet aux operateurs de visualiser les ventes realisees, d'effectuer des corrections ou annulations si necessaire, et de gerer les reemissions de tickets. Il integre les fonctionnalites de gestion des taxes, locations, emails et logs.

| Element | Description |
|---------|-------------|
| **Qui** | Operateur de caisse ou responsable (avec droits de modification) |
| **Quoi** | Consultation et gestion de l'historique des ventes payantes |
| **Pourquoi** | Permettre les corrections, annulations et reimpressions de ventes |
| **Declencheur** | Acces depuis le menu caisse ou historique ventes |
| **Resultat** | Affichage historique, modifications enregistrees si applicable |

### 1.2 Regles metier

| Code | Regle | Condition |
|------|-------|-----------|
| RM-001 | Execution du traitement principal | Conditions d'entree validees |
| RM-002 | Gestion des tables (33 tables) | Acces selon mode (R/W/L) |
| RM-003 | Appels sous-programmes (0 callees) | Selon logique metier |

### 1.3 Flux utilisateur

1. Reception des parametres d'entree (0 params)
2. Initialisation et verification conditions
3. Traitement principal (30 taches)
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
| **IDE Position** | 244 |
| **Fichier XML** | `Prg_240.xml` |
| **Description** | Histo ventes payantes /PMS-605 |
| **Module** | ADH |
| **Public Name** |  |
| **Nombre taches** | 30 |
| **Lignes logique** | 1841 |
| **Expressions** | 0 |

### 2.2 Tables

| # | Nom logique | Nom physique | Acces | Usage |
|---|-------------|--------------|-------|-------|
| 23 | reseau_cloture___rec | cafil001_dat | READ/WRITE | Lecture+Ecriture |
| 30 | gm-recherche_____gmr | cafil008_dat | READ | Lecture |
| 34 | hebergement______heb | cafil012_dat | READ | Lecture |
| 40 | comptable________cte | cafil018_dat | LINK/READ | Jointure+Lecture |
| 47 | compte_gm________cgm | cafil025_dat | WRITE | Ecriture |
| 67 | tables___________tab | cafil045_dat | LINK | Jointure |
| 70 | date_comptable___dat | cafil048_dat | READ | Lecture |
| 77 | articles_________art | cafil055_dat | LINK | Jointure |
| 79 | gratuites________gra | cafil057_dat | READ | Lecture |
| 89 | moyen_paiement___mop | cafil067_dat | LINK | Jointure |
| 197 | articles_en_stock | caisse_artstock | LINK | Jointure |
| 263 | vente | caisse_vente | LINK | Jointure |
| 285 | email | email | READ | Lecture |
| 400 | pv_cust_rentals | pv_rentals_dat | LINK | Jointure |
| 473 | comptage_caisse | %club_user%_caisse_compcais | LINK | Jointure |
| 519 | pv_cust_rentals | %club_user%_pv_rentals_dat | READ/WRITE | Lecture+Ecriture |
| 596 | tempo_ecran_police | %club_user%tmp_ecrpolice_dat | LINK/WRITE | Jointure+Ecriture |
| 728 | arc_cc_total | arc_cctotal | LINK | Jointure |
| 804 | valeur_credit_bar_defaut | valeur_credit_bar_defaut | LINK | Jointure |
| 847 | stat_lieu_vente_date | %club_user%_stat_lieu_vente_date | LINK | Jointure |
| 899 | Boo_ResultsRechercheHoraire | Boo_ResultsRechercheHoraire | WRITE | Ecriture |
| 910 | classification_memory | classification_memory | LINK | Jointure |
| 911 | log_booker | log_booker | WRITE | Ecriture |
| 933 | taxe_add_vente | taxe_add_vente | LINK/READ/WRITE | Jointure+R/W |
| 945 | Table_945 |  | LINK/READ | Jointure+Lecture |
| 1069 | Table_1069 |  | LINK | Jointure |

**Resume**: 33 tables accedees dont **7 en ecriture**

### 2.3 Parametres d'entree (0 parametres)

| Var | Nom | Type | Picture |
|-----|-----|------|---------|
| - | Aucun parametre | - | - |

### 2.4 Algorigramme

```mermaid
flowchart TD
    START([START - 0 params])
    INIT["Initialisation"]
    PROCESS["Traitement principal<br/>30 taches"]
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
| **Taches** | 30 |
| **Lignes logique** | 1841 |
| **Expressions** | 0 |
| **Parametres** | 0 |
| **Tables accedees** | 33 |
| **Tables en ecriture** | 7 |
| **Callees niveau 1** | 0 |

---

<!-- TAB:Cartographie -->

## CARTOGRAPHIE APPLICATIVE

### 3.1 Chaine d'appels depuis Main

```mermaid
graph LR
    T[244 Histo ventes pa]
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
    T[244 Histo ventes pa]
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
| Taches | 30 | Complexe |
| Tables | 33 | Ecriture |
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

