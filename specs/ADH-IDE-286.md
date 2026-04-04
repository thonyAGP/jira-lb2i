# ADH IDE 286 - Deversement Transaction /PMS14

> **Version spec**: 4.0
> **Analyse**: 2026-01-27 23:15
> **Source**: `D:\Data\Migration\XPA\PMS\ADH\Source\Prg_282.xml`
> **Methode**: APEX + PDCA (Auto-generated)

---

<!-- TAB:Fonctionnel -->

## SPECIFICATION FONCTIONNELLE

### 1.1 Objectif metier

**Deversement Transaction PMS14** est le **programme de deversement des transactions vers le format PMS14** qui **permet de transferer les ventes et transactions vers le systeme comptable au format PMS14**.

**Objectif metier** : Effectuer le deversement des transactions de vente (ventes, gratuites, paiements) depuis les tables de caisse vers les tables comptables et de reporting au format PMS14, permettant l'integration avec le systeme de gestion central.

| Element | Description |
|---------|-------------|
| **Qui** | Processus automatique ou superviseur comptable |
| **Quoi** | Transfert des transactions vers le format PMS14 |
| **Pourquoi** | Assurer l'integration comptable et le reporting des ventes |
| **Declencheur** | Cloture de caisse ou traitement batch |
| **Resultat** | Transactions deversees dans les tables comptables au format PMS14 |

### 1.2 Regles metier

| Code | Regle | Condition |
|------|-------|-----------|
| RM-001 | Execution du traitement principal | Conditions d'entree validees |
| RM-002 | Gestion des tables (22 tables) | Acces selon mode (R/W/L) |
| RM-003 | Appels sous-programmes (0 callees) | Selon logique metier |

### 1.3 Flux utilisateur

1. Reception des parametres d'entree (0 params)
2. Initialisation et verification conditions
3. Traitement principal (9 taches)
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
| **IDE Position** | 286 |
| **Fichier XML** | `Prg_282.xml` |
| **Description** | Deversement Transaction /PMS14 |
| **Module** | ADH |
| **Public Name** |  |
| **Nombre taches** | 9 |
| **Lignes logique** | 625 |
| **Expressions** | 0 |

### 2.2 Tables

| # | Nom logique | Nom physique | Acces | Usage |
|---|-------------|--------------|-------|-------|
| 26 | comptes_speciaux_spc | cafil004_dat | READ | Lecture |
| 30 | gm-recherche_____gmr | cafil008_dat | LINK | Jointure |
| 31 | gm-complet_______gmc | cafil009_dat | LINK | Jointure |
| 34 | hebergement______heb | cafil012_dat | LINK | Jointure |
| 38 | comptable_gratuite | cafil016_dat | WRITE | Ecriture |
| 40 | comptable________cte | cafil018_dat | LINK | Jointure |
| 47 | compte_gm________cgm | cafil025_dat | WRITE | Ecriture |
| 65 | comptes_recette__cre | cafil043_dat | LINK/READ | Jointure+Lecture |
| 68 | compteurs________cpt | cafil046_dat | WRITE | Ecriture |
| 77 | articles_________art | cafil055_dat | LINK | Jointure |
| 89 | moyen_paiement___mop | cafil067_dat | LINK | Jointure |
| 263 | vente | caisse_vente | LINK | Jointure |
| 264 | vente_gratuite | caisse_vente_gratuite | LINK | Jointure |
| 268 | cc_total_par_type | ccpartyp | LINK | Jointure |
| 271 | cc_total | cctotal | LINK | Jointure |
| 596 | tempo_ecran_police | %club_user%tmp_ecrpolice_dat | LINK | Jointure |
| 804 | valeur_credit_bar_defaut | valeur_credit_bar_defaut | LINK | Jointure |
| 847 | stat_lieu_vente_date | %club_user%_stat_lieu_vente_date | LINK/READ | Jointure+Lecture |
| 933 | taxe_add_vente | taxe_add_vente | LINK | Jointure |
| 945 | Table_945 |  | LINK | Jointure |

**Resume**: 22 tables accedees dont **3 en ecriture**

### 2.3 Parametres d'entree (0 parametres)

| Var | Nom | Type | Picture |
|-----|-----|------|---------|
| - | Aucun parametre | - | - |

### 2.4 Algorigramme

```mermaid
flowchart TD
    START([START - 0 params])
    INIT["Initialisation"]
    PROCESS["Traitement principal<br/>9 taches"]
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
| **Taches** | 9 |
| **Lignes logique** | 625 |
| **Expressions** | 0 |
| **Parametres** | 0 |
| **Tables accedees** | 22 |
| **Tables en ecriture** | 3 |
| **Callees niveau 1** | 0 |

---

<!-- TAB:Cartographie -->

## CARTOGRAPHIE APPLICATIVE

### 3.1 Chaine d'appels depuis Main

```mermaid
graph LR
    T[286 Deversement Tra]
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
    T[286 Deversement Tra]
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
| Taches | 9 | Moyen |
| Tables | 22 | Ecriture |
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

