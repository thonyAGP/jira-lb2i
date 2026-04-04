# ADH IDE 311 - Factures (Tble Compta&Vent

> **Version spec**: 4.0
> **Analyse**: 2026-01-27 23:16
> **Source**: `D:\Data\Migration\XPA\PMS\ADH\Source\Prg_307.xml`
> **Methode**: APEX + PDCA (Auto-generated)

---

<!-- TAB:Fonctionnel -->

## SPECIFICATION FONCTIONNELLE

### 1.1 Objectif metier

| Element | Description |
|---------|-------------|
| **Qui** | Operateur (utilisateur connecte) |
| **Quoi** | Factures (Tble Compta&Vent |
| **Pourquoi** | Fonction metier du module ADH |
| **Declencheur** | Appel depuis programme parent ou menu |
| **Resultat** | Traitement effectue selon logique programme |

### 1.2 Regles metier

| Code | Regle | Condition |
|------|-------|-----------|
| RM-001 | Execution du traitement principal | Conditions d'entree validees |
| RM-002 | Gestion des tables (28 tables) | Acces selon mode (R/W/L) |
| RM-003 | Appels sous-programmes (0 callees) | Selon logique metier |

### 1.3 Flux utilisateur

1. Reception des parametres d'entree (0 params)
2. Initialisation et verification conditions
3. Traitement principal (34 taches)
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
| **IDE Position** | 311 |
| **Fichier XML** | `Prg_307.xml` |
| **Description** | Factures (Tble Compta&Vent |
| **Module** | ADH |
| **Public Name** |  |
| **Nombre taches** | 34 |
| **Lignes logique** | 1365 |
| **Expressions** | 0 |

### 2.2 Tables

| # | Nom logique | Nom physique | Acces | Usage |
|---|-------------|--------------|-------|-------|
| 30 | gm-recherche_____gmr | cafil008_dat | LINK | Jointure |
| 31 | gm-complet_______gmc | cafil009_dat | LINK | Jointure |
| 40 | comptable________cte | cafil018_dat | LINK/WRITE | Jointure+Ecriture |
| 68 | compteurs________cpt | cafil046_dat | WRITE | Ecriture |
| 263 | vente | caisse_vente | LINK | Jointure |
| 372 | pv_budget | pv_budget_dat | LINK | Jointure |
| 382 | pv_discount_reasons | pv_discountlist_dat | LINK | Jointure |
| 400 | pv_cust_rentals | pv_rentals_dat | LINK | Jointure |
| 744 | pv_lieux_vente | pv_lieux_vente | LINK | Jointure |
| 746 | projet | version | LINK/WRITE | Jointure+Ecriture |
| 755 | cafil_address_tmp | cafil_address_tmp | LINK | Jointure |
| 756 | Country_ISO | cafil_country_iso | LINK | Jointure |
| 866 | maj_appli_tpe | maj_appli_tpe | LINK/READ/WRITE | Jointure+R/W |
| 867 | log_maj_tpe | log_maj_tpe | LINK/READ | Jointure+Lecture |
| 868 | Affectation_Gift_Pass | affectation_gift_pass | LINK/READ/WRITE | Jointure+R/W |
| 870 | Rayons_Boutique | rayons_boutique | LINK/READ/WRITE | Jointure+R/W |
| 871 | Activite | activite | LINK | Jointure |
| 932 | taxe_add_param | taxe_add_param | LINK/WRITE | Jointure+Ecriture |

**Resume**: 28 tables accedees dont **7 en ecriture**

### 2.3 Parametres d'entree (0 parametres)

| Var | Nom | Type | Picture |
|-----|-----|------|---------|
| - | Aucun parametre | - | - |

### 2.4 Algorigramme

```mermaid
flowchart TD
    START([START - 0 params])
    INIT["Initialisation"]
    PROCESS["Traitement principal<br/>34 taches"]
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
| **Taches** | 34 |
| **Lignes logique** | 1365 |
| **Expressions** | 0 |
| **Parametres** | 0 |
| **Tables accedees** | 28 |
| **Tables en ecriture** | 7 |
| **Callees niveau 1** | 0 |

---

<!-- TAB:Cartographie -->

## CARTOGRAPHIE APPLICATIVE

### 3.1 Chaine d'appels depuis Main

```mermaid
graph LR
    T[311 Factures (Tble ]
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
    T[311 Factures (Tble ]
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
| Taches | 34 | Complexe |
| Tables | 28 | Ecriture |
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
| 2026-01-27 23:16 | **V4.0 APEX/PDCA** - Generation automatique complete | Script |

---

*Specification V4.0 - Auto-generated with APEX/PDCA methodology*

