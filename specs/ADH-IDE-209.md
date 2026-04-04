# ADH IDE 209 - Affectation code autocom

> **Version spec**: 4.0
> **Analyse**: 2026-01-27 23:10
> **Source**: `D:\Data\Migration\XPA\PMS\ADH\Source\Prg_205.xml`
> **Methode**: APEX + PDCA (Auto-generated)

---

<!-- TAB:Fonctionnel -->

## SPECIFICATION FONCTIONNELLE

### 1.1 Objectif metier

**Affectation code autocom** est le **gestionnaire d'attribution des codes d'autocommutateur telephonique** qui **affecte les codes d'acces telephonique aux hebergements et postes du village**.

**Objectif metier** : Automatiser l'attribution des codes d'autocommutateur (PABX) aux chambres et postes telephoniques lors de l'arrivee des clients ou de la configuration du systeme telephonique. Ce programme gere les series de lignes telephoniques, les codes d'acces et leur liaison avec les hebergements pour permettre la facturation des appels.

| Element | Description |
|---------|-------------|
| **Qui** | Operateur reception ou systeme automatique |
| **Quoi** | Attribution des codes d'autocommutateur telephonique aux hebergements |
| **Pourquoi** | Permettre l'identification des appels telephoniques pour la facturation et le suivi des communications |
| **Declencheur** | Arrivee client, configuration telephone, ou demande d'activation de ligne |
| **Resultat** | Code autocom affecte a l'hebergement avec mise a jour des tables de telephonie |

### 1.2 Regles metier

| Code | Regle | Condition |
|------|-------|-----------|
| RM-001 | Execution du traitement principal | Conditions d'entree validees |
| RM-002 | Gestion des tables (30 tables) | Acces selon mode (R/W/L) |
| RM-003 | Appels sous-programmes (0 callees) | Selon logique metier |

### 1.3 Flux utilisateur

1. Reception des parametres d'entree (0 params)
2. Initialisation et verification conditions
3. Traitement principal (57 taches)
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
| **IDE Position** | 209 |
| **Fichier XML** | `Prg_205.xml` |
| **Description** | Affectation code autocom |
| **Module** | ADH |
| **Public Name** |  |
| **Nombre taches** | 57 |
| **Lignes logique** | 1079 |
| **Expressions** | 0 |

### 2.2 Tables

| # | Nom logique | Nom physique | Acces | Usage |
|---|-------------|--------------|-------|-------|
| 30 | gm-recherche_____gmr | cafil008_dat | LINK/READ | Jointure+Lecture |
| 34 | hebergement______heb | cafil012_dat | LINK/READ/WRITE | Jointure+R/W |
| 52 | serie_ligne______slg | cafil030_dat | READ/WRITE | Lecture+Ecriture |
| 53 | ligne_telephone__lgn | cafil031_dat | WRITE | Ecriture |
| 68 | compteurs________cpt | cafil046_dat | WRITE | Ecriture |
| 72 | generation_code_gen | cafil050_dat | WRITE | Ecriture |
| 73 | serie_telephone__stl | cafil051_dat | READ/WRITE | Lecture+Ecriture |
| 75 | commande_autocom_cot | cafil053_dat | WRITE | Ecriture |
| 80 | codes_autocom____aut | cafil058_dat | READ/WRITE | Lecture+Ecriture |
| 86 | serie_sda________ssd | cafil064_dat | READ/WRITE | Lecture+Ecriture |
| 87 | sda_telephone____sda | cafil065_dat | LINK/WRITE | Jointure+Ecriture |
| 88 | historik_station | cafil066_dat | LINK | Jointure |
| 104 | fichier_menage | cafil082_dat | READ | Lecture |
| 130 | fichier_langue | cafil108_dat | LINK | Jointure |
| 131 | fichier_validation | cafil109_dat | LINK | Jointure |
| 136 | fichier_echanges | cafil114_dat | WRITE | Ecriture |
| 151 | nb_code__poste | cafil129_dat | WRITE | Ecriture |
| 152 | parametres_pour_pabx | cafil130_dat | LINK/READ | Jointure+Lecture |
| 169 | salle_seminaire__sse | cafil147_dat | READ | Lecture |
| 188 | correspondance_sda | cafil216_dat | LINK | Jointure |
| 786 | qualite_avant_reprise | qualite_avant_reprise | READ | Lecture |

**Resume**: 30 tables accedees dont **12 en ecriture**

### 2.3 Parametres d'entree (0 parametres)

| Var | Nom | Type | Picture |
|-----|-----|------|---------|
| - | Aucun parametre | - | - |

### 2.4 Algorigramme

```mermaid
flowchart TD
    START([START - 0 params])
    INIT["Initialisation"]
    PROCESS["Traitement principal<br/>57 taches"]
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
| **Taches** | 57 |
| **Lignes logique** | 1079 |
| **Expressions** | 0 |
| **Parametres** | 0 |
| **Tables accedees** | 30 |
| **Tables en ecriture** | 12 |
| **Callees niveau 1** | 0 |

---

<!-- TAB:Cartographie -->

## CARTOGRAPHIE APPLICATIVE

### 3.1 Chaine d'appels depuis Main

```mermaid
graph LR
    T[209 Affectation cod]
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
    T[209 Affectation cod]
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
| Taches | 57 | Complexe |
| Tables | 30 | Ecriture |
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
| 2026-01-27 23:10 | **V4.0 APEX/PDCA** - Generation automatique complete | Script |

---

*Specification V4.0 - Auto-generated with APEX/PDCA methodology*

