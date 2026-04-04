# Resolution Detaillee CMDS-174321

> **Jira** : [CMDS-174321](https://clubmed.atlassian.net/browse/CMDS-174321)

## Statut: INCERTITUDE - 2 HYPOTHESES

---

## Contradiction dans l'analyse

| Source | Affichage | Interpretation |
|--------|-----------|----------------|
| Terminal NA | **25DEC** (correct) | Format DDMMM |
| GUI PMS (PB027) | **25/01/2026** (incorrect) | Format DD/MM/YYYY |

**Si les donnees etaient corrompues en base**, les deux interfaces afficheraient la meme erreur.
Or le Terminal affiche CORRECT et le GUI affiche INCORRECT.

---

## Hypothese A: Bug d'affichage GUI (plus probable)

### Localisation suspectee

| Element | Valeur |
|---------|--------|
| **Programme** | PBP IDE 63 - Affich arrivant planning GM |
| **Table source** | Table n°171 (temporaire planning) |
| **Variable** | Variable V (Column 21 = ">Date") - type FIELD_DATE |

### Mecanisme suppose

1. La donnee stockee est correcte: `20251225` (format YYYYMMDD interne)
2. Le Terminal lit en mode texte et affiche "25DEC" (correct)
3. Le GUI applique un Picture ou une conversion incorrecte
4. Resultat: interpretation MM/DD au lieu de DD/MM

### Fix potentiel

Verifier le **Picture** du controle GUI qui affiche la date:
- Picture actuel: potentiellement "MM/DD/YYYY"
- Picture attendu: "DD/MM/YYYY"

---

## Hypothese B: Donnees corrompues en base (resolution existante)

### Localisation suspectee

| Element | Valeur |
|---------|--------|
| **Programme** | PBG IDE 24 - Import GM seminaire via txt |
| **Fichier source** | A:\GM.TXT ou fichier CSV |
| **Variable** | Variable BR (Column 43 = "v. date de debut") - type FIELD_DATE |

### Mecanisme suppose

1. Le fichier source NA contient `251225` (format YYMMDD)
2. L'import PBG IDE 24 parse avec inversion MM/DD
3. Resultat: 25 (mois) -> invalide -> janvier 2026

### Variables cles dans PBG IDE 24

| Variable | Index | Nom | Type |
|----------|-------|-----|------|
| AO | 40 | v. handicap | Logical |
| AP | 41 | v. age numerique | Numeric (3) |
| AQ | 42 | v. age codifie | Alpha (1) |
| **AR** | 43 | v. date de debut | **Date** |
| AS | 44 | v. ville delivrance passport | Alpha (50) |

---

## DONNEES REQUISES POUR TRANCHER

### Verification SQL

```sql
-- 1. Verifier la donnee brute en base
SELECT gm_compte, gm_filiation, gm_date_debut,
       CONVERT(VARCHAR, gm_date_debut, 112) as format_yyyymmdd
FROM cafil014_dat
WHERE gm_compte = 363116431;

-- 2. Si format_yyyymmdd = '20251225' -> Bug AFFICHAGE (Hypothese A)
-- 2. Si format_yyyymmdd = '20260125' -> Bug IMPORT (Hypothese B)
```

### Fichiers necessaires

| Fichier | Source | But |
|---------|--------|-----|
| RV.HST | Serveur NA | Verifier la date source (deja fait: 251225 = correct) |
| Dump table cafil014_dat | Base VPHUKET | Verifier le stockage reel |

---

## Elements de resolution precise (A COMPLETER)

### Si Hypothese A (affichage)

```markdown
## Fix technique

### Localisation
- **Programme** : PBP IDE 63 - Affich arrivant planning GM
- **Sous-tache** : Tache principale ou sous-tache formulaire
- **Ligne Logic** : A determiner - control de date dans le Form

### Modification
| Controle | Propriete | Avant (bug) | Apres (fix) |
|----------|-----------|-------------|-------------|
| Champ date arrivee | Picture | MM/DD/YYYY (ou autre) | DD/MM/YYYY |

### Variables concernees
| Variable | Nom logique | Role |
|----------|-------------|------|
| V | >Date | Date liee de la table 171 |
```

### Si Hypothese B (import)

```markdown
## Fix technique

### Localisation
- **Programme** : PBG IDE 24 - Import GM seminaire via txt
- **Sous-tache** : A determiner - parsing fichier
- **Ligne Logic** : A determiner - expression de conversion date

### Modification Expression
| Expression | Avant (bug) | Apres (fix) |
|------------|-------------|-------------|
| Expression N | DVal(AR,'MMDDYY') | DVal(AR,'DDMMYY') |

### Variables concernees
| Variable | Nom logique | Role |
|----------|-------------|------|
| AR | v. date de debut | Date extraite du fichier |
```

---

## Lecons apprises

1. **Terminal vs GUI** : Toujours comparer les 2 modes d'affichage
2. **Picture de date** : Source frequente de bugs d'affichage
3. **Donnees brutes** : Toujours verifier le format en base avant de conclure

---

*Analyse approfondie: 2026-01-12*
*Statut: En attente de verification base VPHUKET*
