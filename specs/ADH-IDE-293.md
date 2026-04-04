# ADH IDE 293 - Bi  Change GM Achat

> **Version spec**: 4.0
> **Analyse**: 2026-01-27 23:15
> **Source**: `D:\Data\Migration\XPA\PMS\ADH\Source\Prg_289.xml`
> **Methode**: APEX + PDCA (Auto-generated)

---

<!-- TAB:Fonctionnel -->

## SPECIFICATION FONCTIONNELLE

### 1.1 Objectif metier

**BI Change GM Achat** est le **module de traitement bilateral** qui **enregistre une operation de change achat sur le compte GM (Grand Membre) avec mise a jour complete des compteurs**.

**Objectif metier** : Ce programme gere l'enregistrement comptable complet d'une operation de change ou le client achete des devises. Il effectue une ecriture bilaterale (debit/credit) impactant le reseau cloture, la table change, le compte GM, les compteurs, les moyens de reglement et le comptage caisse devise. Il applique le type de taux de change approprie et met a jour la date comptable. C'est le coeur transactionnel des operations de change achat avec 6 tables en ecriture pour garantir la coherence comptable.

| Element | Description |
|---------|-------------|
| **Qui** | Caissier lors d'une vente de devises au client |
| **Quoi** | Enregistrement comptable bilateral de l'operation de change achat |
| **Pourquoi** | Garantir l'integrite comptable et la tracabilite complete de l'operation |
| **Declencheur** | Validation d'une operation de change achat par le caissier |
| **Resultat** | Ecritures comptables creees, compteurs mis a jour, solde caisse ajuste |

### 1.2 Regles metier

| Code | Regle | Condition |
|------|-------|-----------|
| RM-001 | Execution du traitement principal | Conditions d'entree validees |
| RM-002 | Gestion des tables (16 tables) | Acces selon mode (R/W/L) |
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
| **IDE Position** | 293 |
| **Fichier XML** | `Prg_289.xml` |
| **Description** | Bi  Change GM Achat |
| **Module** | ADH |
| **Public Name** |  |
| **Nombre taches** | 17 |
| **Lignes logique** | 377 |
| **Expressions** | 0 |

### 2.2 Tables

| # | Nom logique | Nom physique | Acces | Usage |
|---|-------------|--------------|-------|-------|
| 23 | reseau_cloture___rec | cafil001_dat | READ/WRITE | Lecture+Ecriture |
| 30 | gm-recherche_____gmr | cafil008_dat | LINK | Jointure |
| 44 | change___________chg | cafil022_dat | READ/WRITE | Lecture+Ecriture |
| 47 | compte_gm________cgm | cafil025_dat | WRITE | Ecriture |
| 68 | compteurs________cpt | cafil046_dat | WRITE | Ecriture |
| 70 | date_comptable___dat | cafil048_dat | READ | Lecture |
| 124 | type_taux_change | cafil102_dat | LINK/READ | Jointure+Lecture |
| 139 | moyens_reglement_mor | cafil117_dat | LINK/READ/WRITE | Jointure+R/W |
| 141 | devises__________dev | cafil119_dat | READ | Lecture |
| 474 | comptage_caisse_devise | %club_user%_caisse_compcais_devise | LINK/WRITE | Jointure+Ecriture |

**Resume**: 16 tables accedees dont **6 en ecriture**

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
| **Lignes logique** | 377 |
| **Expressions** | 0 |
| **Parametres** | 0 |
| **Tables accedees** | 16 |
| **Tables en ecriture** | 6 |
| **Callees niveau 1** | 0 |

---

<!-- TAB:Cartographie -->

## CARTOGRAPHIE APPLICATIVE

### 3.1 Chaine d'appels depuis Main

```mermaid
graph LR
    T[293 Bi  Change GM A]
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
    T[293 Bi  Change GM A]
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
| Tables | 16 | Ecriture |
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
| 2026-01-27 23:15 | **V4.0 APEX/PDCA** - Generation automatique complete | Script |

---

*Specification V4.0 - Auto-generated with APEX/PDCA methodology*

