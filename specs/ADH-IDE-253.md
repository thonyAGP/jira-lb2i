# ADH IDE 253 - Histo ventes Gratuités

> **Version spec**: 4.0
> **Analyse**: 2026-01-27 23:13
> **Source**: `D:\Data\Migration\XPA\PMS\ADH\Source\Prg_249.xml`
> **Methode**: APEX + PDCA (Auto-generated)

---

<!-- TAB:Fonctionnel -->

## SPECIFICATION FONCTIONNELLE

### 1.1 Objectif metier

**Histo ventes Gratuites** est le **gestionnaire d'historique des ventes gratuites** qui **permet de consulter, modifier et annuler les ventes gratuites accordees aux clients (GM)**.

**Objectif metier** : Fournir un ecran de consultation et de gestion de l'historique des ventes gratuites. Les ventes gratuites sont des prestations offertes aux clients (remises 100%, gestes commerciaux, etc.). Ce programme (17 taches, 652 lignes, 23 tables dont 4 en ecriture) permet de visualiser ces transactions, d'effectuer des corrections ou annulations, et de gerer les reemissions de tickets. Il accede aux tables de ventes gratuites specifiques et aux tables de gratuites pour la categorisation.

| Element | Description |
|---------|-------------|
| **Qui** | Operateur de caisse ou responsable (avec droits) |
| **Quoi** | Consultation et gestion de l'historique des ventes gratuites |
| **Pourquoi** | Tracer et controler les gratuites accordees aux clients |
| **Declencheur** | Acces depuis le menu caisse ou historique gratuites |
| **Resultat** | Affichage historique gratuites, modifications si applicable |

### 1.2 Regles metier

| Code | Regle | Condition |
|------|-------|-----------|
| RM-001 | Execution du traitement principal | Conditions d'entree validees |
| RM-002 | Gestion des tables (23 tables) | Acces selon mode (R/W/L) |
| RM-003 | Appels sous-programmes (0 callees) | Selon logique metier |

### 1.3 Flux utilisateur

1. Reception des parametres d'entree (0 params)
2. Initialisation et verification conditions
3. Traitement principal (17 taches)
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
| **IDE Position** | 253 |
| **Fichier XML** | `Prg_249.xml` |
| **Description** | Histo ventes Gratuités |
| **Module** | ADH |
| **Public Name** |  |
| **Nombre taches** | 17 |
| **Lignes logique** | 652 |
| **Expressions** | 0 |

### 2.2 Tables

| # | Nom logique | Nom physique | Acces | Usage |
|---|-------------|--------------|-------|-------|
| 23 | reseau_cloture___rec | cafil001_dat | READ/WRITE | Lecture+Ecriture |
| 30 | gm-recherche_____gmr | cafil008_dat | READ | Lecture |
| 34 | hebergement______heb | cafil012_dat | READ | Lecture |
| 38 | comptable_gratuite | cafil016_dat | LINK | Jointure |
| 40 | comptable________cte | cafil018_dat | LINK | Jointure |
| 47 | compte_gm________cgm | cafil025_dat | WRITE | Ecriture |
| 70 | date_comptable___dat | cafil048_dat | READ | Lecture |
| 77 | articles_________art | cafil055_dat | LINK | Jointure |
| 79 | gratuites________gra | cafil057_dat | READ | Lecture |
| 89 | moyen_paiement___mop | cafil067_dat | LINK | Jointure |
| 197 | articles_en_stock | caisse_artstock | LINK | Jointure |
| 263 | vente | caisse_vente | LINK | Jointure |
| 264 | vente_gratuite | caisse_vente_gratuite | LINK | Jointure |
| 596 | tempo_ecran_police | %club_user%tmp_ecrpolice_dat | LINK | Jointure |
| 728 | arc_cc_total | arc_cctotal | LINK | Jointure |
| 804 | valeur_credit_bar_defaut | valeur_credit_bar_defaut | LINK | Jointure |
| 847 | stat_lieu_vente_date | %club_user%_stat_lieu_vente_date | LINK | Jointure |
| 933 | taxe_add_vente | taxe_add_vente | LINK/READ/WRITE | Jointure+R/W |
| 945 | Table_945 |  | LINK/WRITE | Jointure+Ecriture |

**Resume**: 23 tables accedees dont **4 en ecriture**

### 2.3 Parametres d'entree (0 parametres)

| Var | Nom | Type | Picture |
|-----|-----|------|---------|
| - | Aucun parametre | - | - |

### 2.4 Algorigramme

```mermaid
flowchart TD
    START([START - 0 params])
    INIT["Initialisation"]
    PROCESS["Traitement principal<br/>17 taches"]
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
| **Taches** | 17 |
| **Lignes logique** | 652 |
| **Expressions** | 0 |
| **Parametres** | 0 |
| **Tables accedees** | 23 |
| **Tables en ecriture** | 4 |
| **Callees niveau 1** | 0 |

---

<!-- TAB:Cartographie -->

## CARTOGRAPHIE APPLICATIVE

### 3.1 Chaine d'appels depuis Main

```mermaid
graph LR
    T[253 Histo ventes Gr]
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
    T[253 Histo ventes Gr]
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
| Taches | 17 | Moyen |
| Tables | 23 | Ecriture |
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

