# ADH IDE 213 - Reçu fiscal grec

> **Version spec**: 4.0
> **Analyse**: 2026-01-27 23:10
> **Source**: `D:\Data\Migration\XPA\PMS\ADH\Source\Prg_209.xml`
> **Methode**: APEX + PDCA (Auto-generated)

---

<!-- TAB:Fonctionnel -->

## SPECIFICATION FONCTIONNELLE

### 1.1 Objectif metier

**Recu fiscal grec** est le **generateur de recus fiscaux conformes a la legislation grecque** qui **produit les justificatifs fiscaux des communications telephoniques**.

**Objectif metier** : Generer des recus fiscaux conformes aux exigences de la legislation fiscale grecque pour les communications telephoniques facturees aux clients. Ce programme formate les donnees de telephonie selon les normes locales et produit les documents fiscaux requis.

| Element | Description |
|---------|-------------|
| **Qui** | Operateur comptabilite ou systeme de facturation |
| **Quoi** | Generation de recus fiscaux grecs pour les appels telephoniques |
| **Pourquoi** | Conformite avec la legislation fiscale grecque pour les prestations telephoniques |
| **Declencheur** | Facturation client ou demande de recu fiscal |
| **Resultat** | Recu fiscal grec genere et pret a imprimer ou archiver |

### 1.2 Regles metier

| Code | Regle | Condition |
|------|-------|-----------|
| RM-001 | Execution du traitement principal | Conditions d'entree validees |
| RM-002 | Gestion des tables (8 tables) | Acces selon mode (R/W/L) |
| RM-003 | Appels sous-programmes (0 callees) | Selon logique metier |

### 1.3 Flux utilisateur

1. Reception des parametres d'entree (0 params)
2. Initialisation et verification conditions
3. Traitement principal (4 taches)
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
| **IDE Position** | 213 |
| **Fichier XML** | `Prg_209.xml` |
| **Description** | Reçu fiscal grec |
| **Module** | ADH |
| **Public Name** |  |
| **Nombre taches** | 4 |
| **Lignes logique** | 104 |
| **Expressions** | 0 |

### 2.2 Tables

| # | Nom logique | Nom physique | Acces | Usage |
|---|-------------|--------------|-------|-------|
| 30 | gm-recherche_____gmr | cafil008_dat | READ | Lecture |
| 60 | table_code_acces_tca | cafil038_dat | READ | Lecture |
| 80 | codes_autocom____aut | cafil058_dat | LINK | Jointure |
| 137 | fichier_histotel | cafil115_dat | LINK/READ | Jointure+Lecture |
| 138 | fichier_taxetel | cafil116_dat | LINK | Jointure |
| 155 | historique_pabx | cafil133_dat | LINK | Jointure |
| 157 | coef__telephone__coe | cafil135_dat | LINK | Jointure |

**Resume**: 8 tables accedees dont **0 en ecriture**

### 2.3 Parametres d'entree (0 parametres)

| Var | Nom | Type | Picture |
|-----|-----|------|---------|
| - | Aucun parametre | - | - |

### 2.4 Algorigramme

```mermaid
flowchart TD
    START([START - 0 params])
    INIT["Initialisation"]
    PROCESS["Traitement principal<br/>4 taches"]
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
| **Taches** | 4 |
| **Lignes logique** | 104 |
| **Expressions** | 0 |
| **Parametres** | 0 |
| **Tables accedees** | 8 |
| **Tables en ecriture** | 0 |
| **Callees niveau 1** | 0 |

---

<!-- TAB:Cartographie -->

## CARTOGRAPHIE APPLICATIVE

### 3.1 Chaine d'appels depuis Main

```mermaid
graph LR
    T[213 Reçu fiscal gre]
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
    T[213 Reçu fiscal gre]
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
| Taches | 4 | Simple |
| Tables | 8 | Lecture seule |
| Callees | 0 | Faible couplage |
| **Score global** | **FAIBLE** | - |

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

