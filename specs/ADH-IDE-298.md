# ADH IDE 298 - Gestion caisse 142

> **Version spec**: 4.0
> **Analyse**: 2026-01-27 23:15
> **Source**: `D:\Data\Migration\XPA\PMS\ADH\Source\Prg_294.xml`
> **Methode**: APEX + PDCA (Auto-generated)

---

<!-- TAB:Fonctionnel -->

## SPECIFICATION FONCTIONNELLE

### 1.1 Objectif metier

**Gestion caisse 142** est le **module central de gestion de caisse** qui **orchestre l'ensemble des operations de caisse : ventes, approvisionnements, sessions et concurrences**.

**Objectif metier** : Ce programme est le coeur du systeme de caisse avec 44 taches et 1100 lignes de logique. Il gere le cycle de vie complet d'une session de caisse : suivi des ventes par moyen de paiement (ventes_par_mop), gestion des articles en stock, approvisionnements (saisie_appro), sessions coffre, historique des sessions, communications IMS, et gestion des concurrences d'acces. Il consulte les coupures de monnaie locale, les moyens de reglement et les droits utilisateur. C'est le programme principal qui coordonne toutes les operations de caisse au quotidien avec 6 tables en ecriture pour la tracabilite complete.

| Element | Description |
|---------|-------------|
| **Qui** | Caissier pendant sa session de travail |
| **Quoi** | Gestion complete des operations de caisse (ventes, stocks, approvisionnements) |
| **Pourquoi** | Centraliser le pilotage de toutes les operations de caisse en temps reel |
| **Declencheur** | Chaque operation de caisse (vente, approvisionnement, consultation) |
| **Resultat** | Operations enregistrees, stocks mis a jour, sessions tracees |

### 1.2 Regles metier

| Code | Regle | Condition |
|------|-------|-----------|
| RM-001 | Execution du traitement principal | Conditions d'entree validees |
| RM-002 | Gestion des tables (22 tables) | Acces selon mode (R/W/L) |
| RM-003 | Appels sous-programmes (0 callees) | Selon logique metier |

### 1.3 Flux utilisateur

1. Reception des parametres d'entree (0 params)
2. Initialisation et verification conditions
3. Traitement principal (44 taches)
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
| **IDE Position** | 298 |
| **Fichier XML** | `Prg_294.xml` |
| **Description** | Gestion caisse 142 |
| **Module** | ADH |
| **Public Name** |  |
| **Nombre taches** | 44 |
| **Lignes logique** | 1100 |
| **Expressions** | 0 |

### 2.2 Tables

| # | Nom logique | Nom physique | Acces | Usage |
|---|-------------|--------------|-------|-------|
| 23 | reseau_cloture___rec | cafil001_dat | READ | Lecture |
| 50 | moyens_reglement_mor | cafil028_dat | READ | Lecture |
| 70 | date_comptable___dat | cafil048_dat | READ | Lecture |
| 197 | articles_en_stock | caisse_artstock | LINK | Jointure |
| 198 | coupures_monnaie_locale | caisse_banknote | READ | Lecture |
| 219 | communication_ims | caisse_com_ims | READ | Lecture |
| 227 | concurrence_sessions | caisse_concurrences | WRITE | Ecriture |
| 232 | gestion_devise_session | caisse_devise | READ | Lecture |
| 244 | saisie_approvisionnement | caisse_saisie_appro_dev | LINK/WRITE | Jointure+Ecriture |
| 246 | histo_sessions_caisse | caisse_session | LINK/READ/WRITE | Jointure+R/W |
| 248 | sessions_coffre2 | caisse_session_coffre2 | LINK/WRITE | Jointure+Ecriture |
| 249 | histo_sessions_caisse_detail | caisse_session_detail | READ/WRITE | Lecture+Ecriture |
| 497 | ventes_par_mop | %club_user%_caisse_vente_par_mop | LINK/READ/WRITE | Jointure+R/W |
| 697 | droits_applications | droits | READ | Lecture |
| 740 | pv_stock_movements | pv_stockmvt_dat | READ | Lecture |

**Resume**: 22 tables accedees dont **6 en ecriture**

### 2.3 Parametres d'entree (0 parametres)

| Var | Nom | Type | Picture |
|-----|-----|------|---------|
| - | Aucun parametre | - | - |

### 2.4 Algorigramme

```mermaid
flowchart TD
    START([START - 0 params])
    INIT["Initialisation"]
    PROCESS["Traitement principal<br/>44 taches"]
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
| **Taches** | 44 |
| **Lignes logique** | 1100 |
| **Expressions** | 0 |
| **Parametres** | 0 |
| **Tables accedees** | 22 |
| **Tables en ecriture** | 6 |
| **Callees niveau 1** | 0 |

---

<!-- TAB:Cartographie -->

## CARTOGRAPHIE APPLICATIVE

### 3.1 Chaine d'appels depuis Main

```mermaid
graph LR
    T[298 Gestion caisse ]
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
    T[298 Gestion caisse ]
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
| Taches | 44 | Complexe |
| Tables | 22 | Ecriture |
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
| 2026-01-27 23:15 | **V4.0 APEX/PDCA** - Generation automatique complete | Script |

---

*Specification V4.0 - Auto-generated with APEX/PDCA methodology*

