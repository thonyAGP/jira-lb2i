# PMS-1359 - Details Implementation

> **Jira** : [PMS-1359](https://clubmed.atlassian.net/browse/PMS-1359)

---

## Localisation exacte

| Element | Valeur |
|---------|--------|
| **Programme** | VIL IDE 22 - Print recap sessions |
| **Fichier source** | `Prg_558.xml` (ISN=558) |
| **Tache principale** | 22.16.1 (ISN_2=19) - Reception |
| **Tache cle** | 22.16.1.1 (ISN_2=56) - Update FDR Precedent |
| **Commit** | `9422490b5` (01/10/2025) |

---

## Schema de donnees

### Tables utilisees

| N° | Nom physique | Nom logique | Utilisation |
|----|--------------|-------------|-------------|
| 246 | caisse_session | histo_sessions_caisse | Session J-1 (chrono, user, date) |
| 249 | caisse_session_detail | histo_sessions_caisse_detail | Montant FDR fermeture |
| 471 | comptage_coffre_devise | (prefixe %club_user%) | Source principale |

### Champs lus dans Table 249

| FieldID | Colonne | Description |
|---------|---------|-------------|
| 7 | 1 | Utilisateur |
| 8 | 2 | Chrono |
| 9 | 3 | (non documente) |
| 10 | 4 | Type = 'F' (Fermeture) |
| 11 | 5 | Type = 'F' (Fermeture) |
| 12 | 8 | Montant FDR |

---

## Variables creees

### Dans Tache 22.16.1 (ISN_2=19) - Reception

| Variable | Nom | Type | Precision | Role |
|----------|-----|------|-----------|------|
| **ET** | v.total FDR Init | Numeric | 11.3 | FDR initial du jour courant |
| **EU** | v.FDR fermeture de la veille | Numeric | 11.3 | Montant FDR cloture session J-1 |
| **EV** | v.Session de Fermeture prec exi | Logical | - | TRUE si une session J-1 existe |
| **EW** | v.total FDR Final | Numeric | 11.3 | FDR final du jour courant |
| **EX** | v.Ecart F.D.R. COFFRE2 | Logical | - | TRUE si ecart detecte sur COFFRE2 |
| **EY** | v.Ecart F.D.R. RECEPTION ? | Logical | - | TRUE si ecart detecte sur RECEPTION |

### Dans Tache 22.16.1.1 (ISN_2=56) - Update FDR Precedent

| Variable | Nom | Type | Source |
|----------|-----|------|--------|
| **EZ** | utilisateur | Unicode | temp_histo_sessions_caisse (Table 246) |
| **FA** | chrono en cours | Numeric | temp_histo_sessions_caisse (Table 246) |
| **FJ** | montant | Numeric | histo_sessions_caisse_detail (Table 249) |

---

## Logic detaillee

### Tache 22.16.1.1 - Update FDR Precedent

#### Record Main (Handler M)

```
Ligne 1:  DATAVIEW_SRC Table 471 (Main)
Ligne 3:  Select user = Expression 9
Ligne 5:  Select chrono_courant
Ligne 6:  Select date = Expression 1

Ligne 8:  LINK Table 246 (caisse_session)
Ligne 9:    Select user = Expression 2
Ligne 10:   Select chrono_precedent = Expression 3 (chrono - 1)
Ligne 11:   Select date
Ligne 12: END_LINK

Ligne 15: LINK Table 249 (caisse_session_detail)
Ligne 16:   Select user = Expression 2
Ligne 17:   Select chrono = Expression 3
Ligne 19:   Select type = 'F' (Fermeture)
Ligne 21:   Select montant_fdr (FieldID 12)
Ligne 22: END_LINK
```

#### Task Prefix (Handler P)

```
Ligne 2: Update EU (v.FDR fermeture de la veille) = Expression 11, valeur 0
Ligne 3: Update EV (v.Session de Fermeture prec exi) = Expression 10, valeur 'FALSE'LOG
```

> Les variables EU et EV du parent (Tache 22.16.1) sont initialisees en debut de tache.

#### Record Suffix (Handler S)

```
Ligne 5: Block IF Expression 6
           → FJ<>0
           → (montant <> 0)
Ligne 6:   Call SubTask 1 (CAISSE v1) Condition: Expression 7
             → NOT VG.Hostname au lieu de...
Ligne 7:   Call SubTask 2 (CAISSE T2H) Condition: Expression 8
             → VG.Hostname au lieu de...
Ligne 9: Block End }
```

---

## Expressions cles

| ID | Formule (variables) | Formule (traduction) | Description |
|----|---------------------|----------------------|-------------|
| 6 | `FJ<>0` | `montant <> 0` | Verifie qu'on a trouve des donnees FDR |
| 7 | `NOT VG.Hostname` | `NOT (VG.Hostname au lieu de...)` | Condition pour appeler CAISSE v1 |
| 8 | `VG.Hostname` | `VG.Hostname au lieu de...` | Condition pour appeler CAISSE T2H |
| 10 | `'FALSE'LOG` | valeur logique FALSE | Initialise EV (session existe) |
| 11 | `0` | valeur numerique 0 | Initialise EU (montant FDR veille) |

### Expressions du DataView (Record Main)

| ID | Formule (variables) | Formule (traduction) | Description |
|----|---------------------|----------------------|-------------|
| 1 | `CA` | `p.Date Comptable` | Date comptable du niveau 3 |
| 2 | `EZ` | `utilisateur` | Utilisateur courant |
| 3 | `FA-1` | `chrono en cours - 1` | Chrono session precedente |
| 9 | `IF(Trim(DI)='COFFRE 2', Str(CB,'3P0'), Trim(DI))` | `IF(type_utilisateur='COFFRE 2', formater(chrono), type_utilisateur)` | Formatage conditionnel |

---

## Algorithme simplifie

```
POUR CHAQUE ligne de comptage_coffre_devise (Table 471):

    1. Lire la session PRECEDENTE (chrono - 1) dans Table 246
       → Stocker dans v.Session de Fermeture prec exi = TRUE/FALSE

    2. SI session precedente trouvee:
       Lire le detail de FERMETURE (type='F') dans Table 249
       → Stocker montant dans v.FDR fermeture de la veille

    3. Comparer:
       - SI v.total FDR Init (J) <> v.FDR fermeture de la veille (J-1)
         → Mettre flag v.Ecart F.D.R. COFFRE2 = TRUE (ou RECEPTION)

    4. Appeler sous-taches specifiques:
       - CAISSE v1 (ISN_2=57) pour coffres standard
       - CAISSE T2H (ISN_2=58) pour coffres T2H

FIN POUR
```

---

## Notes techniques

### Ordre de lecture

La lecture se fait en ordre **descendant** sur le chrono pour toujours avoir la session la plus recente en premier, puis on fait chrono-1 pour obtenir la precedente.

### Gestion multi-utilisateurs

Chaque utilisateur (COFFRE, RECEPTION, etc.) est traite independamment grace au filtre sur la variable **DI** (type utilisateur).

### Flags vs Affichage

Les variables `v.Ecart F.D.R. COFFRE2` et `v.Ecart F.D.R. RECEPTION ?` sont des **flags logiques**. L'affichage du `**` sur l'edition depend de la partie Forms/Output qui utilise ces flags (non analysee ici car hors scope Logic).

---

*Implementation documentee le 2026-01-22*

---

*DerniÃ¨re mise Ã  jour : 2026-01-22T18:55*
