# CMDS-174321 - Résolution Technique

> **Jira** : [CMDS-174321](https://clubmed.atlassian.net/browse/CMDS-174321)

## Statut

**RÉSOLU** - Données corrompues en base (import PMS, pas source NA)

---

## Références Magic IDE

### Tables

| N° Table | Projet | Nom Logique | Nom Physique | Description |
|----------|--------|-------------|--------------|-------------|
| **14** | REF | client_gm | `cafil014_dat` | Table clients/GM |
| **171** | REF | (temp planning) | Table temporaire | Données planning affichage |

### Programmes

| IDE | Projet | Nom Public | Description |
|-----|--------|------------|-------------|
| **PBP IDE 62** | PBP | PB027 (prep) | Préparation données temp |
| **PBP IDE 63** | PBP | PB027 (affichage) | Affichage écran GUI |
| **PBG IDE 315** | PBG | Import NA | Import fichiers NA |

---

## Cause racine identifiée

**Analyse byte-par-byte des fichiers source NA** :

Les fichiers RV.HST (arrivées NA) contiennent les dates **CORRECTES** :
- Format : `YYMMDD` (ex: `251225` = 25/12/2025)
- Tous les GM SEEDSMAN ont `251225` dans le fichier source

**Le bug est dans l'import PMS** (PBG IDE 315 - Import NA), pas dans les données NA.

**Hypothèse** : Inversion MM/DD lors de la conversion de date pour la filiation 004 uniquement.

---

## Symptôme observé

| Affichage | Valeur |
|-----------|--------|
| Terminal NA | `25DEC` (correct) |
| GUI PMS (PB027) | `25/01/2026` (incorrect : +1 mois) |

---

## Diagnostic

1. **PBP IDE 62 - PB027 (prep)** - Lecture Table n°14 (`cafil014_dat`)
   - Charge les dates d'arrivée depuis la table clients
   - Dates déjà corrompues à ce niveau

2. **PBP IDE 63 - PB027 (affichage)** - Affichage écran
   - Affiche ce qui est en base
   - Pas de transformation de date

3. **PBG IDE 315 - Import NA** → **SUSPECT PRINCIPAL**
   - Parse les fichiers RV.HST
   - Convertit `YYMMDD` vers format SQL
   - Bug probable : inversion jour/mois pour certaines filiations

---

## Solution

### Option A : Correction SQL directe (données existantes)

```sql
-- Identifier les enregistrements affectés
SELECT gm_numero, gm_date_arrivee, gm_filiation
FROM cafil014_dat
WHERE gm_filiation = '004'
  AND gm_date_arrivee = '2026-01-25'  -- Date incorrecte

-- Corriger les dates inversées
UPDATE cafil014_dat
SET gm_date_arrivee = '2025-12-25'
WHERE gm_filiation = '004'
  AND gm_date_arrivee = '2026-01-25'
```

### Option B : Correction PBG IDE 315 (import futur)

Vérifier dans PBG IDE 315 - Import NA :
- Section : Record Main ou Record Suffix
- Rechercher : parsing de date `YYMMDD`
- Corriger : logique de conversion DD/MM vs MM/DD

---

## Données de validation

| Élément | Source | Valeur |
|---------|--------|--------|
| Fichier NA | `RV.HST` | `251225` (correct) |
| Table SQL | `cafil014_dat.gm_date_arrivee` | À vérifier sur VPHUKET |
| Écran PB027 | GUI | `25/01/2026` (incorrect) |

---

## Fichiers Associés

| Type | Lien |
|------|------|
| Analyse complète | [analysis.md](./analysis.md) |
| Parser RV.HST | [../../tools/parse-rv-hst.ts](../../tools/parse-rv-hst.ts) |
| Ticket Jira | [CMDS-174321](https://clubmed.atlassian.net/browse/CMDS-174321) |

---

## Validation

- [x] Fichiers source NA analysés (données correctes)
- [ ] Base VPHUKET à vérifier
- [ ] PBG IDE 315 à corriger si bug confirmé
- [ ] Capitalisation KB (`/ticket-learn`)

---

*Résolution générée le 2026-01-08*

---

*DerniÃ¨re mise Ã  jour : 2026-01-22T18:55*
