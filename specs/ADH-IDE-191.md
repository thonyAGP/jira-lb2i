# ADH IDE 191 - Annulation solde

> **Version spec**: 4.0
> **Analyse**: 2026-01-27 23:09
> **Source**: `D:\Data\Migration\XPA\PMS\ADH\Source\Prg_187.xml`
> **Methode**: APEX + PDCA (Auto-generated)

---

<!-- TAB:Fonctionnel -->

## SPECIFICATION FONCTIONNELLE

### 1.1 Objectif metier

**Annulation solde** est le **programme de contre-passation comptable** qui **annule une operation de solde precedemment enregistree**.

**Objectif metier** : Permettre l'annulation complete d'un solde de compte GM deja effectue. Ce programme inverse les ecritures comptables, met a jour les totaux par type de paiement (cc_total_par_type), reajuste les compteurs et restaure l'etat du compte avant le solde. Il gere 19 tables dont les ecritures de change, les moyens de paiement et les totaux carte de credit.

| Element | Description |
|---------|-------------|
| **Qui** | Operateur caisse avec droits d'annulation |
| **Quoi** | Annulation complete d'une operation de solde de compte |
| **Pourquoi** | Corriger une erreur de solde ou annuler a la demande du client |
| **Declencheur** | Demande d'annulation depuis le menu solde ou la consultation compte |
| **Resultat** | Contre-passation des ecritures, restauration du solde anterieur, mise a jour des totaux |

### 1.2 Regles metier

| Code | Regle | Condition |
|------|-------|-----------|
| RM-001 | Execution du traitement principal | Conditions d'entree validees |
| RM-002 | Gestion des tables (19 tables) | Acces selon mode (R/W/L) |
| RM-003 | Appels sous-programmes (0 callees) | Selon logique metier |

### 1.3 Flux utilisateur

1. Reception des parametres d'entree (0 params)
2. Initialisation et verification conditions
3. Traitement principal (15 taches)
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
| **IDE Position** | 191 |
| **Fichier XML** | `Prg_187.xml` |
| **Description** | Annulation solde |
| **Module** | ADH |
| **Public Name** |  |
| **Nombre taches** | 15 |
| **Lignes logique** | 805 |
| **Expressions** | 0 |

### 2.2 Tables

| # | Nom logique | Nom physique | Acces | Usage |
|---|-------------|--------------|-------|-------|
| 30 | gm-recherche_____gmr | cafil008_dat | LINK | Jointure |
| 31 | gm-complet_______gmc | cafil009_dat | READ | Lecture |
| 40 | comptable________cte | cafil018_dat | LINK/READ | Jointure+Lecture |
| 44 | change___________chg | cafil022_dat | LINK/WRITE | Jointure+Ecriture |
| 47 | compte_gm________cgm | cafil025_dat | LINK | Jointure |
| 68 | compteurs________cpt | cafil046_dat | LINK | Jointure |
| 70 | date_comptable___dat | cafil048_dat | LINK | Jointure |
| 89 | moyen_paiement___mop | cafil067_dat | LINK | Jointure |
| 140 | moyen_paiement___mop | cafil118_dat | LINK | Jointure |
| 268 | cc_total_par_type | ccpartyp | WRITE | Ecriture |
| 271 | cc_total | cctotal | LINK | Jointure |
| 272 | cc_type_detail | cctypdet | LINK | Jointure |
| 517 | pv_palmtemp | %club_user%_pv_palmtmp_dat | LINK/READ | Jointure+Lecture |
| 582 | tempo_comptage_nation | %club_user%tempocomptagen_dat | LINK/WRITE | Jointure+Ecriture |
| 945 | Table_945 |  | WRITE | Ecriture |

**Resume**: 19 tables accedees dont **4 en ecriture**

### 2.3 Parametres d'entree (0 parametres)

| Var | Nom | Type | Picture |
|-----|-----|------|---------|
| - | Aucun parametre | - | - |

### 2.4 Algorigramme

```mermaid
flowchart TD
    START([START - 0 params])
    INIT["Initialisation"]
    PROCESS["Traitement principal<br/>15 taches"]
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
| **Taches** | 15 |
| **Lignes logique** | 805 |
| **Expressions** | 0 |
| **Parametres** | 0 |
| **Tables accedees** | 19 |
| **Tables en ecriture** | 4 |
| **Callees niveau 1** | 0 |

---

<!-- TAB:Cartographie -->

## CARTOGRAPHIE APPLICATIVE

### 3.1 Chaine d'appels depuis Main

```mermaid
graph LR
    T[191 Annulation sold]
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
    T[191 Annulation sold]
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
| Taches | 15 | Moyen |
| Tables | 19 | Ecriture |
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
| 2026-01-27 23:09 | **V4.0 APEX/PDCA** - Generation automatique complete | Script |

---

*Specification V4.0 - Auto-generated with APEX/PDCA methodology*

