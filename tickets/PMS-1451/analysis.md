# PMS-1451 - PURGE prend uniquement le 1er troncon de sejour

> **Jira** : [PMS-1451](https://clubmed.atlassian.net/browse/PMS-1451)
> **Protocole** : `.claude/protocols/ticket-analysis.md` applique

---

## 1. Contexte Jira

| Element | Valeur |
|---------|--------|
| **Symptome** | "Tous les GO qui avaient plusieurs troncons de sejour ont ete archives meme si leur date de fin etait juin 2026" |
| **Donnees entree** | Purge lancee le 3/12 pour la date du 26/12 |
| **Attendu** | Le systeme doit regarder la date de depart du 2eme troncon (GM et GO) |
| **Obtenu** | Le systeme regarde uniquement la date de depart du 1er troncon (le 7/12) |
| **Reporter** | Jessica Palermo |
| **Date** | 2026-01-06 |

### Indices extraits du ticket

- Troncons de sejour multiples -> **Table n166 - troncon (cafil145_dat)**
- Date fin sejour GM -> **Table n30 - gm-recherche (cafil008_dat)** champ `gmr_fin_sejour`
- Selection archivage -> Programme de selection a identifier

---

## 2. Clarification PUG vs REF

### Confusion initiale

L'utilisateur a indique "PMS-1451 est present dans le projet PUG". Apres investigation :

| Projet | Programme | Role | Bug ? |
|--------|-----------|------|-------|
| **PUG** | PUG IDE 18 "Purge Batch" | Purge des donnees **CAISSE** (sessions, ventes, coffre) | **NON** |
| **REF** | REF IDE 749.1 "selection" | Selection des **GO a archiver** | **OUI** |

### Analyse de PUG IDE 18

| Element | Constat |
|---------|---------|
| Fichier | Prg_101.xml |
| Role | Purge intersaison des donnees de caisse |
| Reference cafil145_dat | Presente (ligne 34786) mais **uniquement comme nom de table dans DELETE SQL** |
| DataView | Ne lit PAS la table troncon pour verifier les dates |

**Conclusion** : PUG IDE 18 **supprime** les enregistrements mais **ne decide pas** lesquels supprimer.
La **selection** des GO a archiver est faite par **REF IDE 749.1**.

---

## 3. Localisation du bug - REF IDE 749.1

### Programme fautif identifie

| Projet | IDE | Fichier | Nom | Role |
|--------|-----|---------|-----|------|
| **REF** | **749** | Prg_726.xml | lancement reparation | Orchestrateur archivage |
| **REF** | **749.1** | Prg_726.xml | **selection** | **SELECTION DES GO A ARCHIVER** |
| **REF** | **749.2** | Prg_726.xml | supress des arrivees avant dim | Nettoyage zselect |

### DataView de REF IDE 749.1 (LE BUG)

| Source | Table | Acces | Role |
|--------|-------|-------|------|
| **Main Source** | Table n31 - gm_complet (cafil011_dat) | **WRITE** | Itere sur tous les GM |
| **Link 1** | Table n34 - hebergement (cafil012_dat) | READ | Joint l'hebergement |
| **Link 2** | Table n808 - zselect | WRITE | Ecrit la liste des GO a supprimer |
| **MANQUANT** | **Table n167 - troncon (cafil145_dat)** | - | **NON JOINT = BUG** |

### Root Cause

Le programme REF IDE 749.1 utilise une **date du gm_complet** (1er troncon) pour decider si un GM doit etre archive, **sans verifier** s'il existe d'autres troncons avec des dates plus tardives.

---

## 4. Exemple concret (du ticket)

| Troncon | Date depart | Code A/I/R | Commentaire |
|---------|-------------|------------|-------------|
| 1er | 07/12/2025 | R (Retour) | Verifie par selection actuelle |
| 2eme | 15/06/2026 | R (Retour) | **NON VERIFIE** |

- Date utilisee dans selection = **07/12/2025** (depuis gm_complet)
- Date purge = 26/12/2025
- Resultat : GM archive car 07/12 < 26/12
- **Attendu** : Garder car dernier troncon = 15/06/2026 > 26/12/2025

---

## 5. Tables concernees

### Table n31 - gm_complet (cafil011_dat)

**Role** : Main Source du programme de selection

| Champ | Type | Description |
|-------|------|-------------|
| code_gm | Numeric | Numero compte |
| filiation | Numeric | Filiation |
| ... | ... | Autres champs GM |

### Table n167 - troncon (cafil145_dat)

**Role** : A ajouter comme Link pour verifier la vraie date de fin

| Champ | Type | Description |
|-------|------|-------------|
| tro_societe | Unicode | Code societe |
| tro_compte | Numeric | Numero compte GM |
| tro_filiation | Numeric | Filiation |
| tro_code_a_i_r | Unicode | **A**ller / **I**nterne / **R**etour |
| tro_date_depart_vol | Date | **Date depart du vol** |
| tro_date_arrivee_vol | Date | Date arrivee du vol |

**Index** : cafil145_dat_IDX_1 (societe, compte, filiation, code_a_i_r, date_depart)

### Table n808 - zselect (Selection des noms a supprimer)

**Role** : Table intermediaire contenant la liste des GM/GO a supprimer

---

## 6. Fix propose

### Modification de REF IDE 749.1

#### 1. Ajouter un Link vers Table n167 (troncon)

| Link | Table | Acces | Cles de jointure |
|------|-------|-------|------------------|
| **Link 3** (nouveau) | Table n167 - troncon | READ | `tro_societe`, `tro_compte`, `tro_filiation` |

#### 2. Ajouter une variable virtuelle

| Variable | Type | Expression | Description |
|----------|------|------------|-------------|
| **V.MaxDateRetour** | Date | Voir ci-dessous | Date du dernier vol retour |

**Expression pour V.MaxDateRetour** :
```
DbSum(Table n167, tro_date_depart_vol,
      tro_compte = code_gm AND
      tro_filiation = filiation AND
      tro_code_a_i_r = 'R',
      MAX)
```

#### 3. Modifier la condition de selection (Range)

| Element | Avant (bug) | Apres (fix) |
|---------|-------------|-------------|
| Condition Range | `date_gm < Variable C` | `V.MaxDateRetour < Variable C` |
| Variable C | Date de purge (formulaire) | Inchange |

### Pseudo-code

**Avant (BUG)** :
```
FOR EACH gm_complet WHERE date < DatePurge
    INSERT INTO zselect (compte, filiation, ...)
END FOR

-> Ne verifie PAS si le GM a d'autres troncons apres DatePurge
```

**Apres (FIX)** :
```
FOR EACH gm_complet
    max_date_retour = MAX(troncon.tro_date_depart_vol)
                      WHERE tro_compte = compte
                      AND tro_filiation = filiation
                      AND tro_code_a_i_r = 'R'

    IF max_date_retour IS NULL THEN
        max_date_retour = date_gm  -- Fallback si pas de troncon

    IF max_date_retour < DatePurge THEN
        INSERT INTO zselect (compte, filiation, ...)
    END IF
END FOR

-> Verifie la date du DERNIER troncon retour
```

---

## 7. Flux d'archivage complet

```
+---------------------------------------------------------------+
|  REF IDE 749 - lancement reparation                           |
|  Formulaire "Lancement de la selection"                       |
|  Variable C = "date a partir d'ou on suprime"                 |
+-----------------------+---------------------------------------+
                        | Bouton "Lancement"
                        v
+---------------------------------------------------------------+
|  Tache 749.1 - selection                      <-- FIX ICI    |
|  -------------------------------------------------------------|
|  Main Source: Table n31 (gm_complet)                         |
|  Link 1: Table n34 (hebergement)                             |
|  Link 2: Table n808 (zselect) [WRITE]                        |
|  -------------------------------------------------------------|
|  [!] AJOUTER: Link 3 vers Table n167 (troncon)               |
|  [!] AJOUTER: Variable V.MaxDateRetour                       |
|  [!] MODIFIER: Condition Range sur V.MaxDateRetour           |
+-----------------------+---------------------------------------+
                        | Remplit zselect
                        v
+---------------------------------------------------------------+
|  Tache 749.2 - supress des arrivees avant dim                 |
|  Nettoie zselect                                              |
+-----------------------+---------------------------------------+
                        |
                        v
+---------------------------------------------------------------+
|  CallTask REF IDE 750-761 (suppress *)                        |
|  Chaque programme lit zselect et supprime dans sa table       |
+---------------------------------------------------------------+
```

---

## 8. Validation

### Tests de non-regression

| Scenario | Donnees test | Resultat attendu |
|----------|--------------|------------------|
| GO 1 troncon, fin < purge | Troncon R au 01/12 | Archive |
| GO 1 troncon, fin > purge | Troncon R au 15/01 | Conserve |
| GO 2 troncons, 2eme > purge | T1=07/12, T2=15/06 | **Conserve** |
| GO 2 troncons, 2eme < purge | T1=01/11, T2=15/12 | Archive |
| GM sans troncon R | Seulement A et I | Conserve (fallback) |

### Requete SQL de verification

```sql
-- Trouver les GM qui auraient du etre conserves lors de la purge du 26/12
SELECT gmc.code_gm, gmc.filiation,
       MIN(t.tro_date_depart_vol) as premier_retour,
       MAX(t.tro_date_depart_vol) as dernier_retour
FROM cafil011_dat gmc  -- gm_complet
JOIN cafil145_dat t ON t.tro_compte = gmc.code_gm
                   AND t.tro_filiation = gmc.filiation
                   AND t.tro_code_a_i_r = 'R'
GROUP BY gmc.code_gm, gmc.filiation
HAVING MIN(t.tro_date_depart_vol) < '2025-12-26'
   AND MAX(t.tro_date_depart_vol) > '2025-12-26'
```

---

## 9. Recuperation des donnees

Les donnees supprimees sont dans la base **ARCHIVAGE**, pas definitivement perdues.

**Tables archivees** :
- Table n722 - arc_gm-recherche
- Autres tables arc_*

---

## References Magic IDE

### Tables concernees

| N Table | Nom Logique | Nom Physique | Role |
|---------|-------------|--------------|------|
| 30 | gm-recherche | cafil008_dat | Index recherche GM |
| 31 | gm_complet | cafil011_dat | Main Source selection |
| 34 | hebergement | cafil012_dat | Lie dans selection |
| 167 | troncon | cafil145_dat | **A ajouter** |
| 808 | zselect | - | Liste GM a supprimer |

### Programmes

| IDE | Projet | Nom | Fichier | Role |
|-----|--------|-----|---------|------|
| 749 | REF | lancement reparation | Prg_726.xml | Orchestrateur |
| 749.1 | REF | selection | Prg_726.xml | **A modifier** |
| 749.2 | REF | supress des arrivees avant dim | Prg_726.xml | Nettoyage |
| 750-761 | REF | suppress * | Prg_727-738.xml | Suppressions |
| 18 | PUG | Purge Batch | Prg_101.xml | Purge caisse (non concerne) |

---

## Statut

| Etape | Statut | Date |
|-------|--------|------|
| Analyse | Terminee | 2026-01-22 |
| Clarification PUG vs REF | Terminee | 2026-01-22 |
| Diagnostic confirme | **REF IDE 749.1** | 2026-01-22 |
| Validation solution | En attente | |
| Implementation | En attente | |
| Tests | En attente | |
| Deploiement | En attente | |

---

*Derniere mise a jour : 2026-01-22T22:00*
*Programme a modifier : REF IDE 749.1 "selection"*
*Fix : Ajouter Link Table n167 + verifier MAX(tro_date_depart_vol) WHERE tro_code_a_i_r = 'R'*
*Note : PUG IDE 18 n'est PAS concerne - c'est la purge caisse, pas l'archivage GO*
