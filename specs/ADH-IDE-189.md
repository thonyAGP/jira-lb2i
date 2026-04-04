# ADH IDE 189 - Print solde compte

> **Version spec**: 4.0
> **Analyse**: 2026-01-27 23:09
> **Source**: `D:\Data\Migration\XPA\PMS\ADH\Source\Prg_185.xml`
> **Methode**: APEX + PDCA (Auto-generated)

---

<!-- TAB:Fonctionnel -->

## SPECIFICATION FONCTIONNELLE

### 1.1 Objectif metier

**Print solde compte** est un **generateur d'edition comptable** qui **imprime l'etat des soldes de comptes des adherents**.

**Objectif metier** : Produire un document d'impression detaille des soldes comptables des adherents. Ce programme est le plus complet du module d'impression ADH, croisant les donnees de 10 tables pour etablir une situation comptable complete : identification adherent (gm-recherche, gm-complet), hebergement, ecritures comptables, lignes de solde, moyens de paiement. Le programme utilise une table temporaire (tempo_comptage_nation) pour les calculs intermediaires et le cumul des soldes.

| Element | Description |
|---------|-------------|
| **Qui** | Operateur comptable, responsable administratif |
| **Quoi** | Impression d'un etat detaille des soldes de comptes adherents |
| **Pourquoi** | Suivi comptable, controle des creances/dettes, relance clients |
| **Declencheur** | Demande d'edition depuis le menu comptable ou en fin de periode |
| **Resultat** | Document imprime avec solde par adherent, detail des ecritures et moyens de paiement |

### 1.2 Regles metier

| Code | Regle | Condition |
|------|-------|-----------|
| RM-001 | Execution du traitement principal | Conditions d'entree validees |
| RM-002 | Gestion des tables (10 tables) | Acces selon mode (R/W/L) |
| RM-003 | Appels sous-programmes (0 callees) | Selon logique metier |

### 1.3 Flux utilisateur

1. Reception des parametres d'entree (0 params)
2. Initialisation et verification conditions
3. Traitement principal (19 taches)
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
| **IDE Position** | 189 |
| **Fichier XML** | `Prg_185.xml` |
| **Description** | Print solde compte |
| **Module** | ADH |
| **Public Name** |  |
| **Nombre taches** | 19 |
| **Lignes logique** | 386 |
| **Expressions** | 0 |

### 2.2 Tables

| # | Nom logique | Nom physique | Acces | Usage |
|---|-------------|--------------|-------|-------|
| 30 | gm-recherche_____gmr | cafil008_dat | READ | Lecture |
| 31 | gm-complet_______gmc | cafil009_dat | LINK | Jointure |
| 34 | hebergement______heb | cafil012_dat | LINK | Jointure |
| 40 | comptable________cte | cafil018_dat | READ | Lecture |
| 48 | lignes_de_solde__sld | cafil026_dat | READ | Lecture |
| 89 | moyen_paiement___mop | cafil067_dat | LINK | Jointure |
| 140 | moyen_paiement___mop | cafil118_dat | READ | Lecture |
| 148 | lignes_de_solde__sld | cafil126_dat | LINK | Jointure |
| 582 | tempo_comptage_nation | %club_user%tempocomptagen_dat | READ/WRITE | Lecture+Ecriture |

**Resume**: 10 tables accedees dont **1 en ecriture**

### 2.3 Parametres d'entree (0 parametres)

| Var | Nom | Type | Picture |
|-----|-----|------|---------|
| - | Aucun parametre | - | - |

### 2.4 Algorigramme

```mermaid
flowchart TD
    START([START - 0 params])
    INIT["Initialisation"]
    PROCESS["Traitement principal<br/>19 taches"]
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
| **Taches** | 19 |
| **Lignes logique** | 386 |
| **Expressions** | 0 |
| **Parametres** | 0 |
| **Tables accedees** | 10 |
| **Tables en ecriture** | 1 |
| **Callees niveau 1** | 0 |

---

<!-- TAB:Cartographie -->

## CARTOGRAPHIE APPLICATIVE

### 3.1 Chaine d'appels depuis Main

```mermaid
graph LR
    T[189 Print solde com]
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
    T[189 Print solde com]
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
| Taches | 19 | Moyen |
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
| 2026-01-27 23:09 | **V4.0 APEX/PDCA** - Generation automatique complete | Script |

---

*Specification V4.0 - Auto-generated with APEX/PDCA methodology*

