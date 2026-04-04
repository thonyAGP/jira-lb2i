# ADH IDE 239 - Transaction Nouv vente PMS-721

> **Version spec**: 4.0
> **Analyse**: 2026-01-27 23:12
> **Source**: `D:\Data\Migration\XPA\PMS\ADH\Source\Prg_235.xml`
> **Methode**: APEX + PDCA (Auto-generated)

---

<!-- TAB:Fonctionnel -->

## SPECIFICATION FONCTIONNELLE

### 1.1 Objectif metier

**Transaction Nouv vente PMS-721** est le **moteur de transaction de vente version PMS-721** qui **gere l'ensemble du processus de vente en caisse avec les fonctionnalites specifiques de la version 721 du PMS**.

**Objectif metier** : Enregistrer une nouvelle vente complete avec toutes les operations comptables associees. Ce programme tres complexe (60 taches, 2207 lignes, 42 tables dont 9 en ecriture) gere la selection d'articles, le calcul des prix, la gestion des modes de paiement, la mise a jour des prestations, des comptes GM, des compteurs et des statistiques. Il integre les specificites de la version 721 du PMS (gestion des budgets, reservations horaires, circuits).

| Element | Description |
|---------|-------------|
| **Qui** | Operateur de caisse (vendeur point de vente) |
| **Quoi** | Enregistrement complet d'une transaction de vente |
| **Pourquoi** | Realiser une vente avec tracabilite complete et mise a jour comptable |
| **Declencheur** | Selection depuis le menu de saisie transaction ou caisse GM |
| **Resultat** | Vente enregistree, compte client debite, statistiques mises a jour |

### 1.2 Regles metier

| Code | Regle | Condition |
|------|-------|-----------|
| RM-001 | Execution du traitement principal | Conditions d'entree validees |
| RM-002 | Gestion des tables (42 tables) | Acces selon mode (R/W/L) |
| RM-003 | Appels sous-programmes (0 callees) | Selon logique metier |

### 1.3 Flux utilisateur

1. Reception des parametres d'entree (0 params)
2. Initialisation et verification conditions
3. Traitement principal (60 taches)
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
| **IDE Position** | 239 |
| **Fichier XML** | `Prg_235.xml` |
| **Description** | Transaction Nouv vente PMS-721 |
| **Module** | ADH |
| **Public Name** |  |
| **Nombre taches** | 60 |
| **Lignes logique** | 2207 |
| **Expressions** | 0 |

### 2.2 Tables

| # | Nom logique | Nom physique | Acces | Usage |
|---|-------------|--------------|-------|-------|
| 23 | reseau_cloture___rec | cafil001_dat | READ/WRITE | Lecture+Ecriture |
| 26 | comptes_speciaux_spc | cafil004_dat | LINK | Jointure |
| 30 | gm-recherche_____gmr | cafil008_dat | LINK/READ | Jointure+Lecture |
| 32 | prestations | cafil010_dat | READ/WRITE | Lecture+Ecriture |
| 34 | hebergement______heb | cafil012_dat | LINK | Jointure |
| 39 | depot_garantie___dga | cafil017_dat | READ | Lecture |
| 46 | mvt_prestation___mpr | cafil024_dat | LINK/WRITE | Jointure+Ecriture |
| 47 | compte_gm________cgm | cafil025_dat | WRITE | Ecriture |
| 50 | moyens_reglement_mor | cafil028_dat | READ | Lecture |
| 67 | tables___________tab | cafil045_dat | LINK | Jointure |
| 68 | compteurs________cpt | cafil046_dat | WRITE | Ecriture |
| 70 | date_comptable___dat | cafil048_dat | LINK | Jointure |
| 77 | articles_________art | cafil055_dat | LINK/READ | Jointure+Lecture |
| 79 | gratuites________gra | cafil057_dat | READ | Lecture |
| 89 | moyen_paiement___mop | cafil067_dat | LINK/READ | Jointure+Lecture |
| 96 | table_prestation_pre | cafil074_dat | LINK/READ | Jointure+Lecture |
| 103 | logement_client__loc | cafil081_dat | READ | Lecture |
| 108 | code_logement____clo | cafil086_dat | LINK | Jointure |
| 109 | table_utilisateurs | cafil087_dat | READ | Lecture |
| 139 | moyens_reglement_mor | cafil117_dat | READ | Lecture |
| 140 | moyen_paiement___mop | cafil118_dat | LINK | Jointure |
| 197 | articles_en_stock | caisse_artstock | LINK | Jointure |
| 372 | pv_budget | pv_budget_dat | LINK | Jointure |
| 596 | tempo_ecran_police | %club_user%tmp_ecrpolice_dat | LINK/READ/WRITE | Jointure+R/W |
| 697 | droits_applications | droits | LINK | Jointure |
| 728 | arc_cc_total | arc_cctotal | LINK | Jointure |
| 801 | moyens_reglement_complem | moyens_reglement_complem | LINK | Jointure |
| 818 | Circuit supprime | zcircafil146 | LINK | Jointure |
| 847 | stat_lieu_vente_date | %club_user%_stat_lieu_vente_date | LINK/WRITE | Jointure+Ecriture |
| 899 | Boo_ResultsRechercheHoraire | Boo_ResultsRechercheHoraire | READ/WRITE | Lecture+Ecriture |
| 1037 | Table_1037 |  | WRITE | Ecriture |

**Resume**: 42 tables accedees dont **9 en ecriture**

### 2.3 Parametres d'entree (0 parametres)

| Var | Nom | Type | Picture |
|-----|-----|------|---------|
| - | Aucun parametre | - | - |

### 2.4 Algorigramme

```mermaid
flowchart TD
    START([START - 0 params])
    INIT["Initialisation"]
    PROCESS["Traitement principal<br/>60 taches"]
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
| **Taches** | 60 |
| **Lignes logique** | 2207 |
| **Expressions** | 0 |
| **Parametres** | 0 |
| **Tables accedees** | 42 |
| **Tables en ecriture** | 9 |
| **Callees niveau 1** | 0 |

---

<!-- TAB:Cartographie -->

## CARTOGRAPHIE APPLICATIVE

### 3.1 Chaine d'appels depuis Main

```mermaid
graph LR
    T[239 Transaction Nou]
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
    T[239 Transaction Nou]
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
| Taches | 60 | Complexe |
| Tables | 42 | Ecriture |
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

