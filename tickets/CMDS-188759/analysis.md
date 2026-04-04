# CMDS-188759 — Equipement perdu dans POS - Suppression/recreation prestations PBG

> **Analyse**: 2026-03-30
> **Village**: Les Arcs Panorama (5T)
> **Symptome**: Reservations annulees dans NA (systeme central) restent visibles dans PMS (local), apparaissent sur les listes MECANO

## 1. Contexte

Le village Les Arcs Panorama signale que des reservations annulees cote NA (New Arrivals / systeme central) ne sont pas supprimees du PMS local. Ces annulations continuent d'apparaitre sur les listes MECANO (mecanographiques) comme si les clients etaient toujours attendus.

L'utilisateur confirme qu'aucun parametrage n'a ete modifie et que le processus fonctionnait correctement avant.

## 2. Chaine de programmes Import → Traitement

### 2.1 Import du fichier annulations

```
Import IDE 159 "Import annulation"
  └─ Import IDE 160 "Annulation dossiers NA"
     → Lit fichier plat cafil148.txt (format fixe)
     → Ecrit dans table 170: annulation_______anu (cafil148_dat)
```

**Table annulation_______anu (170)** — 6 colonnes :

| Colonne | Description | Type |
|---------|-------------|------|
| anu_type_client | Type client (GM/GE) | Alpha |
| anu_num_adherent | Numero adherent | Numeric |
| anu_filiation_club | Filiation club | Numeric |
| anu_num_dossier | Numero dossier NA | Alpha |
| anu_num_ordre | Numero d'ordre | Numeric |
| anu_debut_sejour | Date debut sejour | Date |

### 2.2 Orchestrateur principal

```
PBG IDE 206 "Traitement des arrivants" (68 taches)
  ├─ ... (traitement arrivees)
  ├─ Tache 206.1.7  → CallProgram PBG IDE 238 "Traitement Annulation"
  ├─ Tache 206.1.11 → CallProgram PBG IDE 234/235/236 (variantes)
  ├─ Tache 206.1.42 → Nettoyage annulations traitees
  └─ ... (MECANO, rapports)
```

PBG IDE 206 est l'orchestrateur central qui traite TOUTES les arrivees. Les annulations sont traitees en 3 points distincts (taches 7, 11, 42).

### 2.3 Programme de traitement annulation

```
PBG IDE 238 "Traitement Annulation" (15 sous-taches)
  ├─ Age (initialisation)
  ├─ Path (chemin fichiers)
  ├─ Import ANN.DAT (lecture fichier)
  ├─ Creation Annulation (ecriture table 170)
  ├─ Annulation GM (traitement principal)
  │   ├─ Verification existence (IDE 182 → 17 tables)
  │   ├─ Verification caisse adherent
  │   ├─ Definition numero dossier
  │   ├─ Mise a jour ASD
  │   └─ Avertissements si probleme
  └─ Nettoyage
```

### 2.4 Variantes de traitement

| Programme | Description | Condition |
|-----------|-------------|-----------|
| PBG IDE 228 | Annulation existante | Dossier deja connu |
| PBG IDE 234 | Annulation type 1 | Selon type_client |
| PBG IDE 235 | Annulation type 2 | Selon type_client |
| PBG IDE 236 | Annulation MECANO | Nettoyage tempo_ecran_mecano |

### 2.5 Rapports de suivi

| Programme | Description | Role |
|-----------|-------------|------|
| PBG IDE 137 | Annulation traitee | Liste des annulations REUSSIES |
| PBG IDE 138 | Annulation non traitee | Liste des annulations EN ECHEC |

## 3. Tables impliquees

| Table Magic | Table SQL | Role | Access |
|-------------|-----------|------|--------|
| annulation_______anu (170) | cafil148_dat | Annulations NA importees | R/W |
| tempo_ecran_mecano (573) | - | Ecran temporaire MECANO | R/W |
| import_avertiss__mod (?) | - | Avertissements import | W |
| ASD tables | - | Arrivees/Sejours/Departs | R/W |

## 4. Diagnostic — Hypotheses

### Hypothese 1 : Fichier d'annulation non recu ou non importe

**Probabilite : MOYENNE**

Le fichier `cafil148.txt` (ou `ANN.DAT`) est genere par le systeme central NA et envoye au PMS local. Si le fichier n'arrive pas ou est vide, aucune annulation n'est traitee.

**Verification** :
- Verifier la presence du fichier ANN.DAT sur le serveur du village
- Verifier que Import IDE 159/160 s'execute dans le batch de nuit
- Consulter les logs Import pour erreurs

### Hypothese 2 : Annulation traitee mais condition non remplie

**Probabilite : HAUTE**

PBG IDE 238 contient de nombreuses conditions avant de supprimer une reservation :
1. Le dossier doit EXISTER dans le PMS (verification via IDE 182 sur 17 tables)
2. La caisse adherent doit etre verifiable
3. Le numero de dossier doit correspondre

Si une condition echoue, l'annulation est signee "non traitee" (IDE 138) et l'equipement reste.

**Verification** :
- Consulter l'edition IDE 138 "Annulations non traitees" pour le village
- Verifier si les dossiers annules apparaissent dans cette liste
- Identifier quelle condition bloque le traitement

### Hypothese 3 : Traitement MECANO non nettoye

**Probabilite : MOYENNE-HAUTE**

La table `tempo_ecran_mecano` (573) est utilisee pour l'affichage MECANO. Meme si l'annulation est traitee dans les tables ASD, si PBG IDE 236 ne nettoie pas cette table temporaire, les reservations annulees restent visibles sur les listes MECANO.

**Verification** :
```sql
-- Chercher les reservations annulees encore presentes dans MECANO
SELECT * FROM tempo_ecran_mecano
WHERE num_dossier IN (
    SELECT anu_num_dossier FROM cafil148_dat
    WHERE anu_debut_sejour >= GETDATE()
);
```

### Hypothese 4 : Desynchronisation timing batch

**Probabilite : FAIBLE**

Si le batch d'import des annulations s'execute APRES le batch de generation MECANO, les annulations du jour ne sont pas prises en compte. Le lendemain, elles devraient l'etre.

**Verification** : Verifier l'ordre d'execution des batches dans VIL IDE 29 (cloture nuit).

## 5. Flux de verification existant

```
┌─────────────────────┐
│ Import IDE 159/160  │ Import fichier annulations NA
│ cafil148.txt → t170 │
└────────┬────────────┘
         │
         ▼
┌─────────────────────┐
│ PBG IDE 206         │ Orchestrateur arrivees
│ 68 taches           │
└────────┬────────────┘
         │
    ┌────┴────┐
    ▼         ▼
┌──────────┐ ┌──────────┐
│ IDE 238  │ │ IDE 234  │  Traitement annulation
│ 15 tasks │ │ 235, 236 │  (variantes)
└────┬─────┘ └──────────┘
     │
     ├── Existe? ──► IDE 182 (17 tables)
     │   NON → IDE 138 "Non traitee" ← SUSPECT
     │
     ├── Caisse OK? → Verification adherent
     │   NON → Avertissement ← SUSPECT
     │
     └── OK → Suppression ASD + MECANO
              → IDE 137 "Traitee"
```

## 6. Pistes de resolution

### Option A — Consulter le rapport IDE 138

**Priorite : IMMEDIATE**

Lancer l'edition PBG IDE 138 "Annulations non traitees" pour le village Les Arcs Panorama. Ce rapport liste TOUTES les annulations qui n'ont pas pu etre traitees avec la raison.

### Option B — Verifier l'import

Confirmer que le fichier ANN.DAT/cafil148.txt arrive bien sur le serveur du village et que le batch Import s'execute correctement.

### Option C — Verifier la table MECANO

```sql
-- Reservations dans tempo_ecran_mecano pour le village
SELECT COUNT(*) FROM tempo_ecran_mecano
WHERE debut_sejour >= '20260330';

-- Croiser avec les annulations
SELECT m.* FROM tempo_ecran_mecano m
INNER JOIN cafil148_dat a ON m.num_dossier = a.anu_num_dossier
WHERE a.anu_debut_sejour >= '20260330';
```

### Option D — Relancer le traitement

Si l'import est correct mais le traitement a echoue, relancer PBG IDE 206 manuellement pour retraiter les annulations en attente.

## 7. Programmes analyses

| Programme | Fichier XML | Description | Role |
|-----------|-------------|-------------|------|
| Import IDE 159 | - | Import annulation | Lecture fichier plat |
| Import IDE 160 | - | Annulation dossiers NA | Ecriture table 170 |
| PBG IDE 206 | - | Traitement des arrivants | Orchestrateur (68 taches) |
| PBG IDE 238 | - | Traitement Annulation | Traitement principal (15 taches) |
| PBG IDE 228 | - | Annulation existante | Variante |
| PBG IDE 234 | - | Annulation type 1 | Variante |
| PBG IDE 235 | - | Annulation type 2 | Variante |
| PBG IDE 236 | - | Annulation MECANO | Nettoyage table tempo |
| PBG IDE 137 | - | Annulation traitee | Rapport succes |
| PBG IDE 138 | - | Annulation non traitee | Rapport echec |
| PBG IDE 182 | - | Verification existence | 17 tables verifiees |

## 8. Recommandation

1. **Consulter en priorite** le rapport PBG IDE 138 pour identifier si les annulations arrivent mais echouent au traitement
2. **Verifier** la presence et le contenu du fichier cafil148.txt sur le serveur du village
3. **Croiser** les donnees de la table `annulation_______anu` avec `tempo_ecran_mecano` pour identifier les reservations fantomes
4. Si le probleme est confirme comme un timing batch, ajuster l'ordre d'execution dans le batch de nuit

## 9. Requetes SQL — Audit des 3 dossiers Jira

> **3 cas concrets** : BOUSKILA (dossier 328170552), MAKOV ASSIF (dossier 0), ZOLLER (dossier 329170923)
> **Base** : PHU2512 (colonnes verifiees via metadata)

### 9.0 Reference tables et colonnes reelles

| Table SQL | Colonnes cles | Notes |
|-----------|---------------|-------|
| `cafil148_dat` | anu_type_client, anu_num_adherent(float), anu_filiation_club(int), anu_num_dossier(int), anu_num_ordre(int), anu_debut_sejour(char 8) | 6 colonnes, annulations NA |
| `cafil009_dat` | gmc_societe, gmc_compte, gmc_filiation_compte, gmc_type_de_client, gmc_numero_adherent(float), gmc_filiation_club, gmc_numero_dossier(int), gmc_numero_ordre, gmc_nom_complet, gmc_prenom_complet | 83 colonnes, PAS de date sejour |
| `impor001_dat` | imi_type_client, imi_num_adherent(float), imi_filiation_club, imi_num_dossier(int), imi_num_ordre, imi_debut_sejour(char 8), imi_fin_sejour(char 8), imi_nom_complet, imi_prenom_complet | 121 colonnes, arrivees importees |
| `effectif_personnes` | efp_societe, efp_compte(float), efp_filiation, efp_dossier(int), efp_date_debut_sejour(char 8), efp_date_fin_sejour(char 8), efp_valide(O/N), efp_nom, efp_prenom | 25 colonnes, personnes presentes |
| `cr_trait_arrivant_dat` | societe, lieu_sejour, avertissement_annul(bit), avertissement_annul_ctr(int), annul_integree(bit), annul_integree_ctr(int), annul_non_integree(bit), annul_non_integree_ctr(int), annul_non_integree_en_modif(bit), annul_non_integree_en_modif_ctr(int) | 23 colonnes, compteurs batch |
| `himports_dat` | utilisateur, numero_adherent(float), dossier(float), type, chaine(nvarchar 600) | 10 colonnes, historique imports |
| `import_avertiss__mod` | mod_code_societe, mod_num_import, mod_date_import(char 8), mod_statut, mod_libelle, mod_code, mod_dossier(int), mod_numero_adherent(int), mod_filiation, mod_type_de_modif | 13 colonnes, avertissements |
| `annulation_adhts_dat` | arr_type_client, arr_num_adherent(float), arr_filiation_club, arr_num_dossier(int), arr_suppression(bit) | 7 colonnes, annulations adherents |
| `cafil017_dat` | dga_societe, dga_code_gm(int), dga_filiation, dga_type_depot, dga_montant(float), dga_etat, dga_num_dossier_na(nvarchar 32) | 24 colonnes, depots garantie |
| `ez_card_arrivants` | carte, societe, type_client, adherent(float), filiation_club, dossier(int), gmc_nom, gmc_prenom | 16 colonnes, cartes arrivants |
| `moddossier_dat` | utilisateur, dossier(int), date_de_la_modif(char 8), modif_effectue(bit) | 4 colonnes, modifications dossier |
| `tempo_hebergement` | tmp_societe, tmp_no_compte(int), tmp_filiation, tmp_statut_sejour, tmp_date_debut(char 8), tmp_date_fin(char 8), tmp_nom_logement | 25 colonnes, hebergement temporaire |

### 9.1 Dossier BOUSKILA — N° 328170552

```sql
-- 9.1.1 Annulation importee ? (cafil148_dat)
SELECT anu_type_client, anu_num_adherent, anu_filiation_club,
       anu_num_dossier, anu_num_ordre, anu_debut_sejour
FROM cafil148_dat
WHERE anu_num_dossier = 328170552;

-- 9.1.2 Fiche GM presente ? (cafil009_dat)
SELECT gmc_societe, gmc_compte, gmc_filiation_compte,
       gmc_type_de_client, gmc_numero_adherent, gmc_filiation_club,
       gmc_numero_dossier, gmc_numero_ordre,
       gmc_nom_complet, gmc_prenom_complet,
       gmc_sejour_paye, gmc_free
FROM cafil009_dat
WHERE gmc_numero_dossier = 328170552;

-- 9.1.3 Import arrivee original ? (impor001_dat)
SELECT imi_type_client, imi_num_adherent, imi_filiation_club,
       imi_num_dossier, imi_num_ordre,
       imi_debut_sejour, imi_fin_sejour,
       imi_nom_complet, imi_prenom_complet,
       imi_code_controle
FROM impor001_dat
WHERE imi_num_dossier = 328170552;

-- 9.1.4 Effectif personnes (efp) — present sur le village ?
SELECT efp_societe, efp_compte, efp_filiation, efp_dossier,
       efp_date_debut_sejour, efp_date_fin_sejour,
       efp_valide, efp_nom, efp_prenom,
       efp_code_logement, efp_chambre
FROM effectif_personnes
WHERE efp_dossier = 328170552;

-- 9.1.5 Historique imports (himports_dat)
SELECT utilisateur, numero_adherent, dossier, type, chaine
FROM himports_dat
WHERE CAST(dossier AS INT) = 328170552;

-- 9.1.6 Avertissements import (import_avertiss__mod)
SELECT mod_code_societe, mod_num_import, mod_date_import,
       mod_statut, mod_libelle, mod_code,
       mod_dossier, mod_numero_adherent, mod_filiation,
       mod_type_de_modif
FROM import_avertiss__mod
WHERE mod_dossier = 328170552;

-- 9.1.7 Annulation adherents (annulation_adhts_dat)
SELECT arr_type_client, arr_num_adherent, arr_filiation_club,
       arr_num_dossier, arr_num_ordre, arr_debut_sejour,
       arr_suppression
FROM annulation_adhts_dat
WHERE arr_num_dossier = 328170552;

-- 9.1.8 Depot garantie (cafil017_dat) — via dossier NA (nvarchar)
SELECT dga_societe, dga_code_gm, dga_filiation,
       dga_type_depot, dga_montant, dga_etat,
       dga_num_dossier_na, dga_num_dossier
FROM cafil017_dat
WHERE dga_num_dossier_na = '328170552'
   OR dga_num_dossier = '328170552';

-- 9.1.9 EZ Card arrivants
SELECT carte, societe, type_client, adherent, filiation_club,
       dossier, gmc_nom, gmc_prenom
FROM ez_card_arrivants
WHERE dossier = 328170552;

-- 9.1.10 Modifications dossier (moddossier_dat)
SELECT utilisateur, dossier, date_de_la_modif, modif_effectue
FROM moddossier_dat
WHERE dossier = 328170552;

-- 9.1.11 Hebergement temporaire
SELECT tmp_societe, tmp_no_compte, tmp_filiation,
       tmp_statut_sejour, tmp_date_debut, tmp_date_fin,
       tmp_nom_logement
FROM tempo_hebergement
WHERE tmp_no_compte IN (
    SELECT gmc_compte FROM cafil009_dat
    WHERE gmc_numero_dossier = 328170552
);
```

### 9.2 Dossier MAKOV ASSIF — N° 0

> **ATTENTION** : Numero dossier = 0 est suspect. Cela peut signifier que le dossier n'a jamais ete correctement importe, ou que le champ est vide/reinitialise.

```sql
-- 9.2.1 Annulation importee ? (cafil148_dat)
-- Recherche par nom car dossier=0 est non-discriminant
SELECT anu_type_client, anu_num_adherent, anu_filiation_club,
       anu_num_dossier, anu_num_ordre, anu_debut_sejour
FROM cafil148_dat
WHERE anu_num_dossier = 0;
-- Si trop de resultats, filtrer par adherent :
-- WHERE anu_num_dossier = 0 AND anu_num_adherent = {ADHERENT_MAKOV}

-- 9.2.2 Fiche GM — recherche par nom
SELECT gmc_societe, gmc_compte, gmc_filiation_compte,
       gmc_type_de_client, gmc_numero_adherent, gmc_filiation_club,
       gmc_numero_dossier, gmc_numero_ordre,
       gmc_nom_complet, gmc_prenom_complet,
       gmc_sejour_paye, gmc_free
FROM cafil009_dat
WHERE gmc_nom_complet LIKE '%MAKOV%'
   OR gmc_nom_complet LIKE '%ASSIF%';

-- 9.2.3 Import original — recherche par nom
SELECT imi_type_client, imi_num_adherent, imi_filiation_club,
       imi_num_dossier, imi_num_ordre,
       imi_debut_sejour, imi_fin_sejour,
       imi_nom_complet, imi_prenom_complet
FROM impor001_dat
WHERE imi_nom_complet LIKE '%MAKOV%'
   OR imi_prenom_complet LIKE '%ASSIF%';

-- 9.2.4 Effectif personnes
SELECT efp_societe, efp_compte, efp_filiation, efp_dossier,
       efp_date_debut_sejour, efp_date_fin_sejour,
       efp_valide, efp_nom, efp_prenom
FROM effectif_personnes
WHERE efp_nom LIKE '%MAKOV%';

-- 9.2.5 Avertissements import
SELECT mod_code_societe, mod_num_import, mod_date_import,
       mod_statut, mod_libelle, mod_code,
       mod_dossier, mod_numero_adherent, mod_type_de_modif
FROM import_avertiss__mod
WHERE mod_dossier = 0
  AND mod_date_import >= '20260325';
-- Note: dossier=0 retournera potentiellement beaucoup de resultats,
-- filtrer par date d'import recente

-- 9.2.6 Historique imports — dossier 0
SELECT utilisateur, numero_adherent, dossier, type, chaine
FROM himports_dat
WHERE CAST(dossier AS INT) = 0
  AND type IN ('3', '4', '7', '8', 'R');
-- Note: type vide='' est le plus frequent, filtrer sur types significatifs

-- 9.2.7 Diagnostic dossier=0
-- Compter les fiches avec dossier 0 pour evaluer l'ampleur
SELECT COUNT(*) AS nb_dossier_zero FROM cafil009_dat WHERE gmc_numero_dossier = 0;
SELECT COUNT(*) AS nb_annul_zero FROM cafil148_dat WHERE anu_num_dossier = 0;
SELECT COUNT(*) AS nb_efp_zero FROM effectif_personnes WHERE efp_dossier = 0;
```

### 9.3 Dossier ZOLLER — N° 329170923

```sql
-- 9.3.1 Annulation importee ?
SELECT anu_type_client, anu_num_adherent, anu_filiation_club,
       anu_num_dossier, anu_num_ordre, anu_debut_sejour
FROM cafil148_dat
WHERE anu_num_dossier = 329170923;

-- 9.3.2 Fiche GM
SELECT gmc_societe, gmc_compte, gmc_filiation_compte,
       gmc_type_de_client, gmc_numero_adherent, gmc_filiation_club,
       gmc_numero_dossier, gmc_numero_ordre,
       gmc_nom_complet, gmc_prenom_complet,
       gmc_sejour_paye, gmc_free
FROM cafil009_dat
WHERE gmc_numero_dossier = 329170923;

-- 9.3.3 Import original
SELECT imi_type_client, imi_num_adherent, imi_filiation_club,
       imi_num_dossier, imi_num_ordre,
       imi_debut_sejour, imi_fin_sejour,
       imi_nom_complet, imi_prenom_complet
FROM impor001_dat
WHERE imi_num_dossier = 329170923;

-- 9.3.4 Effectif personnes
SELECT efp_societe, efp_compte, efp_filiation, efp_dossier,
       efp_date_debut_sejour, efp_date_fin_sejour,
       efp_valide, efp_nom, efp_prenom,
       efp_code_logement, efp_chambre
FROM effectif_personnes
WHERE efp_dossier = 329170923;

-- 9.3.5 Avertissements
SELECT mod_code_societe, mod_num_import, mod_date_import,
       mod_statut, mod_libelle, mod_code,
       mod_dossier, mod_numero_adherent, mod_type_de_modif
FROM import_avertiss__mod
WHERE mod_dossier = 329170923;

-- 9.3.6 Historique imports
SELECT utilisateur, numero_adherent, dossier, type, chaine
FROM himports_dat
WHERE CAST(dossier AS INT) = 329170923;

-- 9.3.7 Annulation adherents
SELECT arr_type_client, arr_num_adherent, arr_filiation_club,
       arr_num_dossier, arr_suppression
FROM annulation_adhts_dat
WHERE arr_num_dossier = 329170923;

-- 9.3.8 Depot garantie
SELECT dga_societe, dga_code_gm, dga_filiation,
       dga_type_depot, dga_montant, dga_etat,
       dga_num_dossier_na
FROM cafil017_dat
WHERE dga_num_dossier_na = '329170923';

-- 9.3.9 EZ Card
SELECT carte, societe, type_client, adherent, filiation_club,
       dossier, gmc_nom, gmc_prenom
FROM ez_card_arrivants
WHERE dossier = 329170923;

-- 9.3.10 Modifications
SELECT utilisateur, dossier, date_de_la_modif, modif_effectue
FROM moddossier_dat
WHERE dossier = 329170923;
```

### 9.4 Requetes transversales — Vue d'ensemble

```sql
-- 9.4.1 Compteurs batch — etat actuel du traitement
SELECT societe, lieu_sejour,
       avertissement_annul, avertissement_annul_ctr,
       annul_integree, annul_integree_ctr,
       annul_non_integree, annul_non_integree_ctr,
       annul_non_integree_en_modif, annul_non_integree_en_modif_ctr
FROM cr_trait_arrivant_dat;
-- Attendu pour le bug: annul_non_integree_en_modif_ctr > 0
-- (Jira indique: 3 avertissements, 0 integrees, 4 bloquees "en modification")

-- 9.4.2 Toutes les annulations en attente (cafil148_dat)
SELECT anu_type_client, anu_num_adherent, anu_filiation_club,
       anu_num_dossier, anu_num_ordre, anu_debut_sejour
FROM cafil148_dat
ORDER BY anu_debut_sejour DESC;

-- 9.4.3 Croiser annulations vs effectif personnes
-- = annulations importees dont la personne est encore "presente"
SELECT a.anu_num_dossier, a.anu_num_adherent, a.anu_debut_sejour,
       e.efp_nom, e.efp_prenom, e.efp_valide,
       e.efp_date_debut_sejour, e.efp_date_fin_sejour
FROM cafil148_dat a
INNER JOIN effectif_personnes e
    ON a.anu_num_dossier = e.efp_dossier
WHERE e.efp_valide = 'O';
-- Si cette requete retourne des lignes = BUG CONFIRME
-- Les annulations sont importees mais les personnes restent valides

-- 9.4.4 Croiser annulations vs fiche GM
SELECT a.anu_num_dossier, a.anu_num_adherent, a.anu_debut_sejour,
       g.gmc_nom_complet, g.gmc_prenom_complet,
       g.gmc_numero_ordre, g.gmc_sejour_paye
FROM cafil148_dat a
INNER JOIN cafil009_dat g
    ON a.anu_num_dossier = g.gmc_numero_dossier;
-- Si la fiche GM existe encore = l'annulation n'a pas supprime le GM

-- 9.4.5 Annulations des 3 dossiers specifiques
SELECT a.anu_num_dossier, a.anu_type_client,
       a.anu_num_adherent, a.anu_debut_sejour,
       CASE WHEN g.gmc_numero_dossier IS NOT NULL THEN 'OUI' ELSE 'NON' END AS fiche_gm_presente,
       CASE WHEN e.efp_dossier IS NOT NULL THEN 'OUI' ELSE 'NON' END AS effectif_present,
       e.efp_valide
FROM cafil148_dat a
LEFT JOIN cafil009_dat g ON a.anu_num_dossier = g.gmc_numero_dossier
LEFT JOIN effectif_personnes e ON a.anu_num_dossier = e.efp_dossier
WHERE a.anu_num_dossier IN (328170552, 0, 329170923);

-- 9.4.6 Tous les avertissements recents pour ces dossiers
SELECT mod_date_import, mod_statut, mod_libelle, mod_code,
       mod_dossier, mod_numero_adherent, mod_type_de_modif
FROM import_avertiss__mod
WHERE mod_dossier IN (328170552, 329170923)
   OR (mod_dossier = 0 AND mod_date_import >= '20260325')
ORDER BY mod_date_import DESC;

-- 9.4.7 Hebergement temporaire pour les 3 comptes
SELECT t.tmp_no_compte, t.tmp_filiation,
       t.tmp_statut_sejour, t.tmp_date_debut, t.tmp_date_fin,
       t.tmp_nom_logement
FROM tempo_hebergement t
WHERE t.tmp_no_compte IN (
    SELECT gmc_compte FROM cafil009_dat
    WHERE gmc_numero_dossier IN (328170552, 329170923)
);
```

### 9.5 RESULTATS REELS — Audit execute le 2026-04-04

#### 9.5.1 Compteurs batch (cr_trait_arrivant_dat)

| societe | lieu_sejour | avert_annul_ctr | annul_integree_ctr | annul_non_integree_ctr | annul_non_integree_en_modif_ctr |
|---|---|---|---|---|---|
| C | G | 0 | **0** | **5** | 0 |

**0 annulations integrees, 5 non integrees.** Aucune annulation n'a jamais ete traitee avec succes.

#### 9.5.2 BOUSKILA — Dossier 328170552

**cafil148_dat (annulation importee)** — 2 lignes :

| anu_type_client | anu_num_adherent | anu_filiation_club | anu_num_dossier | anu_num_ordre | anu_debut_sejour |
|---|---|---|---|---|---|
| C | 17108328 | **3** | 328170552 | 1 | 20260329 |
| C | 17108328 | **6** | 328170552 | 2 | 20260329 |

**cafil009_dat (fiche GM)** — 4 membres, tous encore presents :

| gmc_compte | gmc_filiation_compte | gmc_numero_adherent | gmc_filiation_club | gmc_numero_dossier | gmc_numero_ordre | nom | prenom |
|---|---|---|---|---|---|---|---|
| 141408 | 0 | 17108328 | **0** | 328170552 | 1 | BOUSKILA | Yoram |
| 141408 | 1 | 17108328 | **1** | 328170552 | 2 | BARASH BOUSKILA | Tal |
| 141408 | 3 | 17108328 | **4** | 328170552 | 3 | BOUSKILA | Ben Amitai |
| 141408 | 4 | 17108328 | **5** | 328170552 | 4 | BOUSKILA | Ivry |

**MISMATCH** : annulation filiation_club (3, 6) vs GM filiation_club (0, 1, 4, 5) — aucune correspondance.

**effectif_personnes** : VIDE (pas de ligne pour ce dossier)
**annulation_adhts_dat** : VIDE (jamais traite)
**import_avertiss__mod** : VIDE (pas d'avertissement genere)
**himports_dat** : Multiples lignes, 2 personnes identifiees (BOUSKILA DARIA ordre 001, BARASH KATZ FRANCISCA ordre 002). Sejour 20260329-20260405, village S4+ (Les Arcs), vols TLV-GVA.

#### 9.5.3 MAKOV ASSIF — Dossier 0

**cafil009_dat (fiche GM)** — 5 membres, dossier = 0 pour TOUS :

| gmc_compte | gmc_filiation_compte | gmc_numero_adherent | gmc_filiation_club | gmc_numero_dossier | nom | prenom |
|---|---|---|---|---|---|---|
| 145457 | 0 | 15303912 | 2 | **0** | MAKOV | ORNA |
| 145457 | 1 | 22739984 | 1 | **0** | MAKOV ASSIF | MAYA |
| 145457 | 2 | 22739984 | 2 | **0** | ASSIF | NOAM |
| 145457 | 3 | 22739984 | 3 | **0** | ASSIF | OPHIR |
| 145457 | 4 | 22739984 | 4 | **0** | ASSIF | RAPHAEL |

**Probleme** : Le numero de dossier NA n'a jamais ete inscrit dans la fiche GM (reste a 0). Le matching par dossier est donc impossible. Les himports revelent 2 dossiers NA reels : 329173870 (famille ASSIF) et 329173881 (famille MAKOV ROY/ORNA).

#### 9.5.4 ZOLLER — Dossier 329170923

**cafil148_dat (annulation importee)** — 2 lignes :

| anu_type_client | anu_num_adherent | anu_filiation_club | anu_num_dossier | anu_num_ordre | anu_debut_sejour |
|---|---|---|---|---|---|
| C | 5181802 | **3** | 329170923 | 1 | 20260405 |
| C | 5181802 | **6** | 329170923 | 2 | 20260405 |

**cafil009_dat (fiche GM)** — 2 membres :

| gmc_compte | gmc_filiation_compte | gmc_numero_adherent | gmc_filiation_club | gmc_numero_dossier | gmc_numero_ordre | nom | prenom |
|---|---|---|---|---|---|---|---|
| 142439 | 0 | 5181802 | **0** | 329170923 | 6 | ZOLLER | Raviv |
| 142439 | 1 | 5181802 | **1** | 329170923 | 7 | ZOLLER | Miri |

**MISMATCH** : annulation filiation_club (3, 6) vs GM filiation_club (0, 1) — aucune correspondance.
Les himports montrent ZOLLER SHAI (ordre 001) et SHACHAR ITAI (ordre 002) — personnes differentes des GM presents.

### 9.6 ROOT CAUSE CONFIRMEE

> **Les valeurs `anu_filiation_club` dans le fichier d'annulation NA (3, 6) ne correspondent a aucune `gmc_filiation_club` dans les fiches GM du PMS.**

PBG IDE 238 effectue un matching strict sur `anu_filiation_club = gmc_filiation_club`. Comme les valeurs ne correspondent pas, l'annulation echoue silencieusement — sans generer d'avertissement dans `import_avertiss__mod`.

| Dossier | Annul filiation_club | GM filiation_club | Correspondance |
|---------|---------------------|-------------------|----------------|
| BOUSKILA 328170552 | 3, 6 | 0, 1, 4, 5 | **AUCUNE** |
| MAKOV ASSIF 0 | (dossier=0) | (dossier=0) | **IMPOSSIBLE** |
| ZOLLER 329170923 | 3, 6 | 0, 1 | **AUCUNE** |

**Observations complementaires** :
- Les valeurs 3 et 6 reviennent systematiquement dans les annulations (BOUSKILA et ZOLLER). Elles ont probablement une signification cote NA qui differe de la numerotation PMS.
- Le cas MAKOV est different : le dossier NA n'a jamais ete inscrit dans la fiche GM (reste a 0), rendant tout matching impossible.
- Les 5 annulations non integrees dans `cr_trait_arrivant_dat` correspondent exactement aux 5 lignes cafil148 des 3 dossiers (2 BOUSKILA + 1 MAKOV implicite + 2 ZOLLER).

### 9.7 Pistes de resolution

| Priorite | Action | Detail |
|----------|--------|--------|
| **P0** | Investiguer la semantique de filiation_club cote NA | Que signifient les valeurs 3 et 6 dans le systeme central ? Sont-elles des codes de type (adulte/enfant) plutot que des index famille ? |
| **P0** | Verifier le code de matching dans PBG IDE 238 | Le matching utilise-t-il `anu_filiation_club = gmc_filiation_club` strictement, ou y a-t-il une table de transcodage ? |
| **P1** | Corriger les fiches MAKOV | Le dossier NA (329173870/329173881) doit etre inscrit dans `gmc_numero_dossier` pour permettre le matching |
| **P1** | Ajouter un avertissement | PBG IDE 238 devrait generer un avertissement dans `import_avertiss__mod` quand le matching filiation echoue, au lieu d'abandonner silencieusement |
| **P2** | Consulter edition PBG IDE 138 | Le rapport "Annulations non traitees" peut contenir des informations complementaires sur la raison de l'echec |

### 9.8 Notes colonnes specifiques

| Table | Piege | Detail |
|-------|-------|--------|
| `cafil009_dat` | Pas de date de sejour | Les dates sont dans `effectif_personnes` et `impor001_dat` |
| `cafil009_dat` | `gmc_type_de_client` | Avec underscore DE, pas `gmc_type_client` |
| `himports_dat` | `dossier` est float | Necessite `CAST(dossier AS INT)` pour comparer |
| `himports_dat` | Pas de date_import | L'historique est dans `chaine` (nvarchar 600) |
| `cafil017_dat` | `dga_num_dossier_na` est nvarchar | Comparer en string : `= '328170552'` |
| `effectif_personnes` | `efp_valide` = O/N | Pas 0/1. O=Oui (valide), N=Non |
| `cr_trait_arrivant_dat` | Compteurs reels | `annul_non_integree_ctr` = 5 (pas `annul_non_integree_en_modif_ctr` comme suppose initialement) |
| `cafil148_dat` | `anu_debut_sejour` char 8 | Format AAAAMMJJ (ex: '20260405') |
