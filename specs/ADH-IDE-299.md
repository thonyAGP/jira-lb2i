# ADH IDE 299 - Fermeture caisse 144

> **Version spec**: 4.0
> **Analyse**: 2026-01-27 23:15
> **Source**: `D:\Data\Migration\XPA\PMS\ADH\Source\Prg_295.xml`
> **Methode**: APEX + PDCA (Auto-generated)

---

<!-- TAB:Fonctionnel -->

## SPECIFICATION FONCTIONNELLE

### 1.1 Objectif metier

**Fermeture caisse 144** est le **module de cloture de session** qui **effectue le pointage final et la fermeture comptable de la caisse**.

**Objectif metier** : Ce programme cloture une session de caisse en effectuant les operations de pointage obligatoires. Il ecrit dans les tables de pointage (pointage_appro_remise, pointage_article, pointage_devise) pour enregistrer l'etat final de la caisse. Il consulte les moyens de reglement, les tables de configuration, les devises de session et les devises parametrees pour valider la coherence. Le pointage compare les montants theoriques aux montants reels et enregistre les eventuels ecarts. Le numero 144 correspond a un identifiant de version/type de cloture.

| Element | Description |
|---------|-------------|
| **Qui** | Caissier en fin de service |
| **Quoi** | Pointage et fermeture comptable de la session de caisse |
| **Pourquoi** | Valider la coherence des operations du jour et cloturer la session |
| **Declencheur** | Fin de service du caissier ou cloture journaliere |
| **Resultat** | Session cloturee avec pointages enregistres et ecarts documentes |

### 1.2 Regles metier

| Code | Regle | Condition |
|------|-------|-----------|
| RM-001 | Execution du traitement principal | Conditions d'entree validees |
| RM-002 | Gestion des tables (8 tables) | Acces selon mode (R/W/L) |
| RM-003 | Appels sous-programmes (0 callees) | Selon logique metier |

### 1.3 Flux utilisateur

1. Reception des parametres d'entree (0 params)
2. Initialisation et verification conditions
3. Traitement principal (14 taches)
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
| **IDE Position** | 299 |
| **Fichier XML** | `Prg_295.xml` |
| **Description** | Fermeture caisse 144 |
| **Module** | ADH |
| **Public Name** |  |
| **Nombre taches** | 14 |
| **Lignes logique** | 489 |
| **Expressions** | 0 |

### 2.2 Tables

| # | Nom logique | Nom physique | Acces | Usage |
|---|-------------|--------------|-------|-------|
| 50 | moyens_reglement_mor | cafil028_dat | READ | Lecture |
| 67 | tables___________tab | cafil045_dat | READ | Lecture |
| 139 | moyens_reglement_mor | cafil117_dat | READ | Lecture |
| 232 | gestion_devise_session | caisse_devise | LINK | Jointure |
| 241 | pointage_appro_remise | caisse_pointage_apprem | WRITE | Ecriture |
| 242 | pointage_article | caisse_pointage_article | WRITE | Ecriture |
| 243 | pointage_devise | caisse_pointage_devise | WRITE | Ecriture |
| 693 | devise_in | devisein_par | READ | Lecture |

**Resume**: 8 tables accedees dont **3 en ecriture**

### 2.3 Parametres d'entree (0 parametres)

| Var | Nom | Type | Picture |
|-----|-----|------|---------|
| - | Aucun parametre | - | - |

### 2.4 Algorigramme

```mermaid
flowchart TD
    START([START - 0 params])
    INIT["Initialisation"]
    PROCESS["Traitement principal<br/>14 taches"]
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
| **Taches** | 14 |
| **Lignes logique** | 489 |
| **Expressions** | 0 |
| **Parametres** | 0 |
| **Tables accedees** | 8 |
| **Tables en ecriture** | 3 |
| **Callees niveau 1** | 0 |

---

<!-- TAB:Cartographie -->

## CARTOGRAPHIE APPLICATIVE

### 3.1 Chaine d'appels depuis Main

```mermaid
graph LR
    T[299 Fermeture caiss]
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
    T[299 Fermeture caiss]
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
| Taches | 14 | Moyen |
| Tables | 8 | Ecriture |
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

