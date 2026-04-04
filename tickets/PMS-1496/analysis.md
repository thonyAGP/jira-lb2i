# PMS-1496 : POS SKI - Changement libellé service SKIN → Ski sur documents

> **Analyse**: 2026-03-31 15:00 → 16:30
> **Statut**: Recette KO — le libellé ne change pas sur les reçus PDF

## 1. Contexte

L'Asie demande de remplacer le code service "SKIN" par le libellé "Ski" sur les documents émis par le POS SKI (reçus PDF, CGV, emails). Eric Rebibo propose de remplacer le code service par le libellé service en s'assurant que les colonnes BDD sont assez grandes.

**Symptôme** : Les reçus PDF portent le nom `Receipt_SKIN_7708_20260331.pdf` et les CGV `SKIN_Rentals_Terms&Conditions.pdf` — le code "SKIN" apparaît au lieu du libellé "Ski".

**Observation Davide** : Les extractions CSV montrent bien "Ski" (`406Ski_PRESTATIONS_...`) mais les reçus PDF montrent toujours "SKIN".

## 2. Localisation programmes

### 2.1 Programmes d'impression (BUG - utilisent le CODE)

| Programme | Description | Référence service |
|-----------|-------------|-------------------|
| PVE Prg_351 | Print Invoice or Ticket | `{0,13}` = param "P. Service" = **CODE** |
| PVE Prg_406 | Print Invoice or Ticket V4 | `{0,13}` = **CODE** |
| PVE Prg_423 | Print Invoice or Ticket NEW | `{0,13}` = **CODE** |
| PVE Prg_433 | Print Invoice or Ticket v2 | `{0,13}` = **CODE** |

### 2.2 Programmes UI (OK - utilisent le LIBELLÉ)

| Programme | Description | Référence service |
|-----------|-------------|-------------------|
| PVE Prg_108-181 | Écrans POS (Sale, Menu, etc.) | `GetParam('SERVICELIB')` = **LABEL** |

### 2.3 Programme d'email

| Programme | Description | Notes |
|-----------|-------------|-------|
| REF Prg_878 | Mail Envoi Multi_PJ | Reçoit les noms de fichiers du caller |

### 2.4 Programmes d'extraction (OK)

| Programme | Description | Notes |
|-----------|-------------|-------|
| PBP Prg_445 | CSV location | Lit le libellé depuis table → affiche "Ski" |
| PBP Prg_451 | CSV Enfant | Filtre sur 'SKIN' mais affiche libellé |

## 3. Root Cause

### 3.1 Le mécanisme SERVICE / SERVICELIB

La chaîne d'appel POS SKI définit **deux paramètres** :

```
PVE Prg_142 (Main POS):
  SetParam('SERVICE', {0,1})      → CODE ('SKIN', 'BOUT', 'REST', etc.)
  SetParam('SERVICELIB', {0,43})  → LABEL ('Ski', 'Boutique', 'Restaurant', etc.)

PVE Prg_288 (Get Service):
  SetParam('SERVICE', {0,6})      → CODE depuis groupe_dat.grp_chemin_respons_
  SetParam('SERVICELIB', {0,10})  → LABEL depuis table liée (colonne 7)
```

### 3.2 Le problème

Les **4 programmes d'impression** (351, 406, 423, 433) n'utilisent **JAMAIS** `GetParam('SERVICELIB')`. Ils utilisent uniquement `{0,13}` (le paramètre "P. Service" qui contient le **CODE**).

#### Nom de fichier Receipt (les 4 programmes)
```
'Receipt_' & Trim({0,13}) & '_' & Trim(Str({0,45},'6Z')) & '_' & DStr(Date(),'YYYYMMDD') & '.pdf'
→ Receipt_SKIN_7708_20260331.pdf
```

#### Nom de fichier CGV (Prg_351 sous-tâche "Generation CGV Files")
```
Trim({0,1}) & '_Sales_Terms&Conditions.pdf'     → SKIN_Sales_Terms&Conditions.pdf
Trim({0,1}) & '_Rentals_Terms&Conditions.pdf'    → SKIN_Rentals_Terms&Conditions.pdf
```

#### Corps du reçu PDF (Prg_351 ligne 15442)
```
Trim({0,13}) & ' ' & Trim({0,14})               → SKIN V
```

### 3.3 Pourquoi les extractions fonctionnent

Les programmes PBP (445, 451) lisent le libellé depuis les tables de référence (`tqu_libelle`) et l'affichent dans les CSV. Ils ne passent pas par le paramètre "P. Service".

## 4. Solution proposée

### Option A : Utiliser `GetParam('SERVICELIB')` (recommandé)

Dans les 4 programmes d'impression, remplacer `{0,13}` par `GetParam('SERVICELIB')` pour les usages d'**affichage** (nom de fichier, corps du reçu).

**Conserver** `{0,13}` = CODE pour les **conditions logiques** (`IF {0,13}='SKIN'` pour activer les sections SKI-spécifiques).

| Emplacement | Avant | Après |
|-------------|-------|-------|
| Filename Receipt | `Trim({0,13})` | `Trim(GetParam('SERVICELIB'))` |
| Filename CGV | `Trim({0,1})` | `Trim(GetParam('SERVICELIB'))` |
| Corps reçu | `Trim({0,13})` | `Trim(GetParam('SERVICELIB'))` |

**Impact** : 4 programmes à modifier (351, 406, 423, 433), ~3-4 expressions par programme.

### Option B : Ajouter un paramètre SERVICELIB aux programmes d'impression

Si les programmes n'ont pas accès à `GetParam('SERVICELIB')`, ajouter un paramètre supplémentaire passé par le caller.

## 5. Programmes impactés (tous projets)

| Projet | Programme | Rôle | Action |
|--------|-----------|------|--------|
| **PVE** | Prg_351 | Print Invoice or Ticket | Modifier filename + body |
| **PVE** | Prg_406 | Print Invoice or Ticket V4 | Modifier filename |
| **PVE** | Prg_423 | Print Invoice or Ticket NEW | Modifier filename |
| **PVE** | Prg_433 | Print Invoice or Ticket v2 | Modifier filename |
| **REF** | Prg_878 | Mail Envoi Multi_PJ | Pas de modif (reçoit filenames du caller) |
| **PBP** | Prg_445/451 | Extractions CSV | Déjà correct |

## 6. Réponse à Davide

> "Depuis où est prise l'information du libellé exactement ?"

Le libellé sur les **reçus PDF** vient du paramètre `{0,13}` ("P. Service") qui contient le **code service** (`SKIN`), pas le libellé. Le libellé "Ski" existe dans `GetParam('SERVICELIB')` (posé par Prg_142/288) mais les programmes d'impression ne le lisent pas. Les **extractions CSV** fonctionnent car elles lisent le libellé directement depuis la table `activite` (colonne `libelle`).
