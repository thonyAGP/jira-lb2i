# ADH IDE 211 - Opposition code autocom

> **Version spec**: 4.0
> **Analyse**: 2026-01-27 23:10
> **Source**: `D:\Data\Migration\XPA\PMS\ADH\Source\Prg_207.xml`
> **Methode**: APEX + PDCA (Auto-generated)

---

<!-- TAB:Fonctionnel -->

## SPECIFICATION FONCTIONNELLE

### 1.1 Objectif metier

**Opposition code autocom** est le **gestionnaire de blocage des codes telephoniques** qui **met en opposition les codes d'autocommutateur pour empecher les appels sortants**.

**Objectif metier** : Bloquer l'acces telephonique d'un hebergement en mettant le code autocom en opposition. Cette fonction est utilisee lors du depart d'un client, en cas de non-paiement, ou sur demande explicite. Le programme desactive les lignes telephoniques associees et met a jour l'historique des stations.

| Element | Description |
|---------|-------------|
| **Qui** | Operateur reception ou systeme de check-out automatique |
| **Quoi** | Mise en opposition des codes d'autocommutateur telephonique |
| **Pourquoi** | Empecher les appels sortants non autorises apres depart ou sur demande |
| **Declencheur** | Depart client, demande de blocage, ou non-paiement |
| **Resultat** | Code autocom bloque avec mise a jour des tables de telephonie et historique |

### 1.2 Regles metier

| Code | Regle | Condition |
|------|-------|-----------|
| RM-001 | Execution du traitement principal | Conditions d'entree validees |
| RM-002 | Gestion des tables (10 tables) | Acces selon mode (R/W/L) |
| RM-003 | Appels sous-programmes (0 callees) | Selon logique metier |

### 1.3 Flux utilisateur

1. Reception des parametres d'entree (0 params)
2. Initialisation et verification conditions
3. Traitement principal (13 taches)
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
| **IDE Position** | 211 |
| **Fichier XML** | `Prg_207.xml` |
| **Description** | Opposition code autocom |
| **Module** | ADH |
| **Public Name** |  |
| **Nombre taches** | 13 |
| **Lignes logique** | 173 |
| **Expressions** | 0 |

### 2.2 Tables

| # | Nom logique | Nom physique | Acces | Usage |
|---|-------------|--------------|-------|-------|
| 30 | gm-recherche_____gmr | cafil008_dat | READ | Lecture |
| 53 | ligne_telephone__lgn | cafil031_dat | WRITE | Ecriture |
| 68 | compteurs________cpt | cafil046_dat | WRITE | Ecriture |
| 75 | commande_autocom_cot | cafil053_dat | WRITE | Ecriture |
| 80 | codes_autocom____aut | cafil058_dat | WRITE | Ecriture |
| 87 | sda_telephone____sda | cafil065_dat | LINK/WRITE | Jointure+Ecriture |
| 88 | historik_station | cafil066_dat | WRITE | Ecriture |
| 136 | fichier_echanges | cafil114_dat | WRITE | Ecriture |
| 151 | nb_code__poste | cafil129_dat | WRITE | Ecriture |

**Resume**: 10 tables accedees dont **8 en ecriture**

### 2.3 Parametres d'entree (0 parametres)

| Var | Nom | Type | Picture |
|-----|-----|------|---------|
| - | Aucun parametre | - | - |

### 2.4 Algorigramme

```mermaid
flowchart TD
    START([START - 0 params])
    INIT["Initialisation"]
    PROCESS["Traitement principal<br/>13 taches"]
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
| **Taches** | 13 |
| **Lignes logique** | 173 |
| **Expressions** | 0 |
| **Parametres** | 0 |
| **Tables accedees** | 10 |
| **Tables en ecriture** | 8 |
| **Callees niveau 1** | 0 |

---

<!-- TAB:Cartographie -->

## CARTOGRAPHIE APPLICATIVE

### 3.1 Chaine d'appels depuis Main

```mermaid
graph LR
    T[211 Opposition code]
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
    T[211 Opposition code]
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
| Taches | 13 | Moyen |
| Tables | 10 | Ecriture |
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
| 2026-01-27 23:10 | **V4.0 APEX/PDCA** - Generation automatique complete | Script |

---

*Specification V4.0 - Auto-generated with APEX/PDCA methodology*

