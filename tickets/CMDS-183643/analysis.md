# CMDS-183643 - Equipement perdu dans POS

> **Jira** : [CMDS-183643](https://clubmed.atlassian.net/browse/CMDS-183643)

## Synthese

| Champ | Valeur |
|-------|--------|
| **Statut** | Complet (ticket ferme par Davide) |
| **Village** | Val Thorens Sensations |
| **Reporter** | Responsable Ski Pro Shop |
| **Domaine** | POS / Location ski / Traitement arrivants |

## Probleme signale

Les codes equipement (ski) saisis dans POS sur les lignes RENTAL/PREPAID disparaissent apres modification du dossier dans NA.

**Symptomes observes :**
1. Client AYAV en package EASY avec lignes prepaid location ski
2. Codes equipement saisis dans POS (VI205, 295ATB06, SV302)
3. Apres traitement arrivants (modification dossier) :
   - Search Equipment → page vierge (plus de client associe)
   - Lignes prepaid toujours presentes mais colonne CODE vide

## Cause identifiee (par Davide)

> "quand il y a des dossiers avec une modification on les efface et on les recree. du coup si t'as pose les codes sans valider, ils s'effacent."

Le traitement des arrivants (batch PBG) :
1. Detecte une modification du dossier dans les imports NA
2. Supprime les prestations existantes
3. Recree de nouvelles prestations avec de nouveaux IDs
4. Les codes equipement etaient lies aux anciens IDs → ils sont perdus

## Analyse technique

### Programme principal

| Projet | IDE | Nom | Fichier source |
|--------|-----|-----|----------------|
| **PBG** | **206** | Traitement des arrivants | Prg_65.xml |

> **Note** : Fichier source `Prg_65.xml` (ISN=65) → Position IDE **206**.

### Flux de traitement

```
Import NA (modification dossier)
       │
       ▼
PBG IDE 206 - Traitement des arrivants
       │
       ├─ Detection modification (dates, nb GM, etc.)
       │
       ├─ Sauvegarde Prestations (Tache 206.97)
       │     └─ Copie table prestations pour historique
       │
       ├─ Suppression prestations existantes
       │     └─ DbDel() sur table prestations (cafil018)
       │
       ├─ Si sejour existe deja + nouveau importe :
       │     └─ "on ira supprimer le client" (Traitement Annulation)
       │     └─ CallTask → Prg_99
       │
       └─ Traitement Prestation (Tache 206.24)
             └─ Creation nouvelles prestations avec nouveaux IDs
```

### Expressions de suppression identifiees

| Expression | Code | Table cible |
|------------|------|-------------|
| Exp 84 | `DbDel('{8,2}'DSOURCE,'')` | Table via datasource colonne 8 |
| Exp 93 | `DbDel('{1078,2}'DSOURCE,'')` | Table via datasource colonne 1078 |
| Exp 5 | `DbDel('{645,2}'DSOURCE,'')` | Table via datasource colonne 645 |

### Tables concernees

| Table | Nom | Role |
|-------|-----|------|
| cafil018 | cafil018_dat | Prestations (RENTAL, PREPAID, etc.) |
| pv_loc_* | Tables PVE | Codes equipement associes aux prestations |

## Impact metier

- **Frequence** : ~6 cas en 2 semaines (Val Thorens)
- **Villages touches** : Potentiellement tous les villages ski avec location equipement
- **Workflow impacte** :
  1. Client arrive → recoit equipement ski au Pro Shop
  2. Code equipement saisi sur ligne prepaid (non valide)
  3. Modification last minute du dossier dans NA
  4. Traitement arrivants efface/recree → code perdu
  5. Client repart avec equipement non trace

## Solution proposee

### Option A : Preservation des codes lors de la recreation

Avant de supprimer les prestations, sauvegarder les codes equipement associes (table PVE) et les reassocier aux nouvelles prestations.

**Complexite** : Moyenne - necessite modification PBG + verification liaison PVE

### Option B : Validation automatique des codes saisis

Quand un code equipement est saisi dans POS, valider immediatement la ligne pour eviter la perte lors du traitement arrivants.

**Complexite** : Faible - modification POS uniquement

### Option C : Bloquer suppression si codes saisis

Detecter si des codes equipement sont associes aux prestations avant suppression et alerter/bloquer.

**Complexite** : Moyenne - ajout condition dans PBG IDE 206

## Statut resolution

**Ticket ferme** par Davide le 24/02/2026 :
> "pas de solution de suite mais on a pris le point pour que les developpeurs vont travailler"

Le probleme est documente et escalade pour developpement futur.

## Pieces jointes

- `image-20260222-091744.png` : Search Equipment vide (codes sans client)
- `image-20260222-092150.png` : Ecran client AYAV - lignes RENTAL sans CODE

## Changelog

- 2026-02-25 : Analyse technique complete, identification PBG IDE 206
