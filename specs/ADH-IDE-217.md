# ADH IDE 217 - Menu telephone

> **Version spec**: 4.0
> **Analyse**: 2026-01-27 23:11
> **Source**: `D:\Data\Migration\XPA\PMS\ADH\Source\Prg_213.xml`
> **Methode**: APEX + PDCA (Auto-generated)

---

<!-- TAB:Fonctionnel -->

## SPECIFICATION FONCTIONNELLE

### 1.1 Objectif metier

**Menu telephone** est le **point d'entree principal du module telephonie** qui **centralise l'acces a toutes les fonctions de gestion telephonique du village**.

**Objectif metier** : Fournir le menu principal de gestion de la telephonie permettant d'acceder aux fonctions d'affectation de codes, consultation des appels, parametrage PABX, editions et statistiques. Ce programme est le hub central de navigation du module telephonie.

| Element | Description |
|---------|-------------|
| **Qui** | Operateur reception ou responsable telephonie |
| **Quoi** | Menu principal des fonctions telephoniques |
| **Pourquoi** | Centraliser l'acces a toutes les fonctionnalites de telephonie |
| **Declencheur** | Selection du module telephonie depuis le menu principal |
| **Resultat** | Affichage du menu avec acces aux sous-fonctions telephoniques |

### 1.2 Regles metier

| Code | Regle | Condition |
|------|-------|-----------|
| RM-001 | Execution du traitement principal | Conditions d'entree validees |
| RM-002 | Gestion des tables (11 tables) | Acces selon mode (R/W/L) |
| RM-003 | Appels sous-programmes (0 callees) | Selon logique metier |

### 1.3 Flux utilisateur

1. Reception des parametres d'entree (0 params)
2. Initialisation et verification conditions
3. Traitement principal (10 taches)
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
| **IDE Position** | 217 |
| **Fichier XML** | `Prg_213.xml` |
| **Description** | Menu telephone |
| **Module** | ADH |
| **Public Name** |  |
| **Nombre taches** | 10 |
| **Lignes logique** | 261 |
| **Expressions** | 0 |

### 2.2 Tables

| # | Nom logique | Nom physique | Acces | Usage |
|---|-------------|--------------|-------|-------|
| 31 | gm-complet_______gmc | cafil009_dat | LINK | Jointure |
| 47 | compte_gm________cgm | cafil025_dat | WRITE | Ecriture |
| 80 | codes_autocom____aut | cafil058_dat | READ | Lecture |
| 87 | sda_telephone____sda | cafil065_dat | LINK | Jointure |
| 88 | historik_station | cafil066_dat | READ | Lecture |
| 104 | fichier_menage | cafil082_dat | LINK | Jointure |
| 169 | salle_seminaire__sse | cafil147_dat | LINK | Jointure |
| 188 | correspondance_sda | cafil216_dat | LINK | Jointure |
| 367 | pms_print_param_default | pmsprintparamdefault | WRITE | Ecriture |
| 454 | tai_gm | taigm | LINK | Jointure |
| 786 | qualite_avant_reprise | qualite_avant_reprise | LINK | Jointure |

**Resume**: 11 tables accedees dont **2 en ecriture**

### 2.3 Parametres d'entree (0 parametres)

| Var | Nom | Type | Picture |
|-----|-----|------|---------|
| - | Aucun parametre | - | - |

### 2.4 Algorigramme

```mermaid
flowchart TD
    START([START - 0 params])
    INIT["Initialisation"]
    PROCESS["Traitement principal<br/>10 taches"]
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
| **Taches** | 10 |
| **Lignes logique** | 261 |
| **Expressions** | 0 |
| **Parametres** | 0 |
| **Tables accedees** | 11 |
| **Tables en ecriture** | 2 |
| **Callees niveau 1** | 0 |

---

<!-- TAB:Cartographie -->

## CARTOGRAPHIE APPLICATIVE

### 3.1 Chaine d'appels depuis Main

```mermaid
graph LR
    T[217 Menu telephone]
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
    T[217 Menu telephone]
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
| Taches | 10 | Moyen |
| Tables | 11 | Ecriture |
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
| 2026-01-27 23:11 | **V4.0 APEX/PDCA** - Generation automatique complete | Script |

---

*Specification V4.0 - Auto-generated with APEX/PDCA methodology*

