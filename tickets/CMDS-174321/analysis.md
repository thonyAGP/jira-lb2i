# Analyse Bug CMDS-174321

> **Jira** : [CMDS-174321](https://clubmed.atlassian.net/browse/CMDS-174321)

## Symptome

| Source | Date Arrivee | Statut |
|--------|--------------|--------|
| NA (Easy Arrival) | **25 DEC 2025** | Correct |
| PMS (PB027) | **25 JAN 2026** | INCORRECT |

**Ecart:** +1 mois

**GM concerne:** SEEDSMAN Zoe (file 363116431)

---

## Ecran PB027 - Planning/Display of GM Lodging

### Programmes impliques

| IDE | Projet | Nom Public | Description |
|-----|--------|------------|-------------|
| PBP IDE 62 | PBP | Prep tempo arrivant planning | Preparation donnees temp |
| PBP IDE 63 | PBP | Affich arrivant planning GM | Affichage ecran |
| PBP IDE 64 | PBP | Imprim GM arrivant planning | Impression |
| PBG IDE 315 | PBG | Import GM seminaire via txt | Import fichiers NA |

### Tables cles

| Table | ID REF | Fichier Physique | Champ Date |
|-------|--------|------------------|------------|
| client_gm | 36 | cafil014_dat | `gm_date_debut` (char(8)) |
| gm-complet | 31 | cafil009_dat | - |
| heure_de_passage | 463 | verifpool_dat | `con_heure` (Time) |

---

## Flux de donnees

```
NA (Easy Arrival)
    |
    v
[Fichier TXT/CSV]
    |
    v
PBG IDE 315 "Import GM seminaire via txt"
    |
    v
Table client_gm (gm_date_debut)
    |
    v
PBP IDE 62 "Prep tempo arrivant planning"
    |
    v
Tables temporaires
    |
    v
PBP IDE 63 "Affich arrivant planning GM" --> Ecran PB027
```

---

## Analyse technique

### Format de stockage date Magic

- **Type:** Date (attribute="D")
- **Picture:** DD/MM/YYYY
- **Stockage:** char(8) - format interne YYYYMMDD
- **StoredAs:** 19 (Date Internal)

### Hypotheses du bug

| # | Hypothese | Probabilite | Explication |
|---|-----------|-------------|-------------|
| 1 | **Parsing DD/MM vs MM/DD** | Moyenne | 25/12/2025 interprete comme 12/25/2025 puis converti en 25/01/2026 (mois suivant car jour 25 > max decembre) |
| 2 | **Donnee source corrompue** | Haute | Le fichier NA pourrait contenir une date incorrecte pour ce GM specifique |
| 3 | **Bug calcul dans PBP IDE 62** | Faible | Manipulation incorrecte des dates dans la preparation |
| 4 | **Cache non rafraichi** | Faible | Tables temporaires avec ancienne valeur |

### Analyse de l'hypothese 1 (Parsing)

Si le systeme source envoie `25-12-2025` et le parsing Magic l'interprete comme:
- Mois = 25 (invalide -> corrige a 01 du mois suivant = Janvier)
- Jour = 12
- Annee = 2025 + 1 = 2026 (car debordement mois)

Resultat: **25/01/2026** - correspond exactement au bug!

---

## Actions recommandees

### Verification immediate

1. **Verifier la donnee en base**
   ```sql
   SELECT gm_societe, gm_compte, gm_filiation, gm_date_debut, gm_date_fin
   FROM cafil014_dat
   WHERE gm_compte = 363116431
   ```

2. **Comparer avec autre membre famille**
   - Verifier si d'autres membres du meme dossier ont la bonne date
   - Si oui, le probleme est specifique a cet enregistrement

### Investigation approfondie

3. **Analyser PBG IDE 315 - Import NA**
   - Localiser la lecture du fichier TXT/CSV
   - Verifier le format de date attendu vs recu
   - Chercher les expressions `DVal()` ou conversion de date

4. **Tracer le flux complet**
   - Ajouter des logs dans PBP IDE 62 pour voir la valeur de `gm_date_debut` en entree
   - Comparer avec la valeur affichee en sortie

---

## Analyse approfondie (2026-01-07)

### Tracage du flux PB027

| IDE | Projet | Role |
|-----|--------|------|
| PBP IDE 62 | PBP | Preparation donnees temp |
| PBP IDE 63 | PBP | Affichage ecran GUI |

### Champs identifies dans PBP IDE 63

| FieldID | Column Source | Contenu |
|---------|---------------|---------|
| 26 | Column 12 | Date arrivee |
| 27 | Column 13 | Heure arrivee |
| 28 | Column 14 | Date depart |
| 29 | Column 15 | Heure depart |

### Observation CRITIQUE des captures

| Source | Date Arrivee | Date Depart | Format |
|--------|--------------|-------------|--------|
| Terminal (image 2) | **25DEC** | 04JAN26 | DDMMM |
| GUI PB027 (images 1,3) | **25/01/2026** | 04/01/2026 | DD/MM/YYYY |

**Le terminal et le GUI sont le MEME ecran PB027** mais en modes differents !
- Terminal : affiche la date correcte (25 decembre)
- GUI : affiche une date erronee (25 janvier)

### Hypothese raffinee

Le bug n'est **PAS dans l'import** mais dans **l'affichage GUI** de PBP IDE 63.

Possibilites :
1. **Type de colonne incorrect** : La colonne 12 de la table temporaire est stockee comme String (YYYYMMDD) mais affichee comme Date avec Picture DD/MM/YYYY → inversion des bytes
2. **Probleme de locale/format** : Le GUI interprete differemment le format de date interne
3. **Bug specifique a ce GM** : Donnee corrompue uniquement pour ce dossier

---

## Actions pour resolution

### Immediat (utilisateur)

1. **Requete SQL de verification:**
   ```sql
   -- Verifier la donnee brute dans la table temporaire
   SELECT * FROM [table_temp_planning]
   WHERE compte = 363116431

   -- Verifier la table source client_gm
   SELECT gm_societe, gm_compte, gm_filiation,
          gm_date_debut, gm_date_fin
   FROM cafil014_dat
   WHERE gm_compte = 363116431
   ```

2. **Comparer les donnees** entre le stockage interne et l'affichage

### Investigation technique

3. **Verifier le type de la Column 12** dans la table obj="171" (REF comp=2)
4. **Comparer le Picture** du champ FieldID=26 avec le format attendu
5. **Tester avec un GM ayant jour <= 12** pour voir si le bug se manifeste

---

## Conclusion

**Cause probable:** Incompatibilite de type/format entre le stockage de la date (table temporaire) et l'affichage GUI.

Le terminal lit et affiche la donnee correctement car il utilise un format different (DDMMM).
Le GUI convertit mal la date car il y a un decalage dans l'interpretation du format interne.

**Recommandation:**
- Verifier le type de donnee de la colonne 12 dans la table temporaire de planning
- Si le type est String (char), verifier que le Picture d'affichage correspond au format stocke

---

## DONNÉES REQUISES POUR COMPLÉTER L'ANALYSE

### Base de données

| Élément | Valeur |
|---------|--------|
| **Village** | VPHUKET (Thaïlande) |
| **Date** | 21/12/2025 (ou date proche du symptôme) |
| **Dossier concerné** | 363116431 |

### Tables à extraire

| Table SQL | Champs critiques | Description |
|-----------|------------------|-------------|
| `cafil014_dat` | `gm_societe`, `gm_compte`, `gm_filiation`, `gm_date_debut`, `gm_date_fin` | Table client_gm - source des dates GM |
| `planning_temp` ou table obj=171 | colonnes 4, 5, 12, 13 | Table temporaire préparation planning |
| `roomfile` (si existe) | `room_date_debut_sejour`, `room_date_fin_sejour` | Hébergements/logements |

### Requêtes SQL à exécuter

```sql
-- 1. Données GM du dossier concerné
SELECT gm_societe, gm_compte, gm_filiation,
       gm_date_debut, gm_date_fin,
       gm_nom, gm_prenom
FROM cafil014_dat
WHERE gm_compte = 363116431
ORDER BY gm_filiation;

-- 2. Vérifier le format de stockage (raw bytes si possible)
SELECT gm_date_debut,
       CONVERT(VARBINARY(8), gm_date_debut) as raw_bytes
FROM cafil014_dat
WHERE gm_compte = 363116431;

-- 3. Chercher d'autres GM avec date > 12ème jour (pour confirmer pattern)
SELECT TOP 20 gm_compte, gm_filiation, gm_date_debut
FROM cafil014_dat
WHERE gm_date_debut IS NOT NULL
  AND DAY(gm_date_debut) > 12
ORDER BY gm_date_debut DESC;
```

### Fichiers d'import (si disponibles)

| Fichier | Source | Contenu attendu |
|---------|--------|-----------------|
| `*.txt` ou `*.csv` import NA | Easy Arrival / NA | Fichier d'import GM séminaire |
| Logs import PBG | Dossier logs | Traces de l'import PBG IDE 315 |

---

## Fichiers MCP crees (bonus)

Dans le cadre de cette analyse, 4 nouveaux outils MCP ont ete implementes:

| Outil | Description |
|-------|-------------|
| `magic_find_program` | Recherche fuzzy cross-projet |
| `magic_list_programs` | Liste paginee avec filtres |
| `magic_index_stats` | Statistiques de l'index |
| `magic_get_dependencies` | Dependances cross-projet |

**Build:** `tools/MagicMcp/bin/Release/net8.0/`

---

*Rapport genere le 2026-01-06, mis a jour le 2026-01-07*
*Migre vers .openspec/tickets/ le 2026-01-07*

---

*DerniÃ¨re mise Ã  jour : 2026-01-22T18:55*
