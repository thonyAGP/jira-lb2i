# PMS-1451 - Implémentation

> **Jira** : [PMS-1451](https://clubmed.atlassian.net/browse/PMS-1451)

## Programme à modifier

| Projet | IDE | Nom | Fichier |
|--------|-----|-----|---------|
| REF | 746 | Purge caisse | Prg_723.xml |

*Note: Le programme exact de sélection des GM à purger doit être identifié dans le flux d'appel.*

## Modifications requises

### 1. Ajouter Link vers table troncon

**Localisation** : Tâche principale ou sous-tâche de sélection GM

**Ajouter** :
- Link vers **Table n°167** (troncon__________tro / cafil145_dat)
- Index: cafil145_dat_IDX_1
- Clé: societe + compte + filiation + code_a_i_r = 'R'
- Tri: date_depart DESC (pour avoir le plus récent en premier)

### 2. Créer une nouvelle sous-tâche

**Nom** : `Recherche date fin max tronçon`

**DataView** :
- Main Source : **Table n°167** (troncon / cafil145_dat)
- Locate : tro_societe, tro_compte, tro_filiation, tro_code_a_i_r = 'R'
- Range : Max sur tro_date_depart_vol

**Logic** :
- Record Suffix : Récupérer MAX(tro_date_depart_vol) dans variable

### 3. Modifier le critère de purge

**Localisation** : Tâche 746.3 (user)

**Avant** :
```
Condition purge = gmr_fin_sejour < Date_Purge
```

**Après** :
```
1. CallTask vers "Recherche date fin max tronçon"
2. SI date_fin_max trouvée (tronçon existe) ALORS
     Condition purge = date_fin_max < Date_Purge
   SINON (fallback)
     Condition purge = gmr_fin_sejour < Date_Purge
```

### 4. Alternative : Sous-requête SQL

Si le programme utilise du SQL direct, modifier la requête :

```sql
-- Ajouter une sous-requête pour obtenir la vraie date de fin
SELECT gm.*
FROM cafil008_dat gm
WHERE COALESCE(
    (SELECT MAX(tro_date_depart_vol)
     FROM cafil145_dat tro
     WHERE tro.tro_societe = gm.gmr_societe
       AND tro.tro_compte = gm.gmr_code_gm
       AND tro.tro_filiation = gm.gmr_filiation_villag
       AND tro.tro_code_a_i_r = 'R'),
    gm.gmr_fin_sejour
) < @Date_Purge
```

## Variables à ajouter

| Variable | Type | Description |
|----------|------|-------------|
| v.DateFinMaxTroncon | DATE | Date départ du dernier tronçon retour |
| v.TronconTrouve | LOGICAL | Indique si un tronçon retour existe |

## Tables utilisées

| Table | Mode | Index | Usage |
|-------|------|-------|-------|
| n°30 cafil008_dat | Read | IDX_1 | Liste des GM à évaluer |
| **n°167 cafil145_dat** | Read | IDX_1 | Tronçons pour calculer date fin réelle |

## Tests de validation

| Scénario | Entrée | Attendu |
|----------|--------|---------|
| GM 1 tronçon, fin < purge | tro: 01/12, purge: 15/12 | Purgé |
| GM 1 tronçon, fin > purge | tro: 20/12, purge: 15/12 | Conservé |
| GM 2 tronçons, 1er < purge, 2ème > purge | tro1: 01/12, tro2: 15/06/2026, purge: 15/12 | **Conservé** |
| GM 2 tronçons, tous < purge | tro1: 01/11, tro2: 01/12, purge: 15/12 | Purgé |
| GM sans tronçon (cas rare) | gmr_fin_sejour: 01/12, purge: 15/12 | Purgé (fallback) |

## Commits

*Aucun commit pour l'instant*

---

*Dernière mise à jour : 2026-01-22T18:49*
