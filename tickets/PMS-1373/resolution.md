# PMS-1373 - Résolution Technique

## Principe

Filtrer sur le champ existant `cte_flag_annulation` de la **Table n°40** (`cafil018_dat` / operations).
- Valeur `Normal` = ligne à afficher
- Valeurs `Annulation` ou `X-annule` = lignes à masquer

---

## Références Magic IDE

### Tables

| N° Table | Nom Logique | Nom Physique | Description |
|----------|-------------|--------------|-------------|
| **40** | operations_dat | `cafil018_dat` | Opérations compte (MainSource des extraits) |

### Programmes

| IDE | Projet | Nom Public | Description |
|-----|--------|------------|-------------|
| **ADH IDE 69** | ADH | EXTRAIT_COMPTE | Point d'entrée extrait |
| **ADH IDE 70** | ADH | EXTRAIT_NOM | Edition par nom |
| **ADH IDE 71** | ADH | EXTRAIT_DATE | Edition par date |
| **ADH IDE 72** | ADH | EXTRAIT_CUM | Edition cumulée |
| **ADH IDE 73** | ADH | EXTRAIT_IMP | Edition impression |
| **ADH IDE 76** | ADH | EXTRAIT_SERVICE | Edition par service |

---

## ÉTAPE 1 : Modifier ADH IDE 69 (EXTRAIT_COMPTE)

### Structure des tâches ADH IDE 69

| Tâche | Nom | Description |
|-------|-----|-------------|
| **69** | EXTRAIT_COMPTE | Programme principal |
| 69.1 | Recalcul solde | Sous-tâche calcul |
| 69.1.1 | Solde GM | Sous-sous-tâche |
| 69.2 | ... | ... |
| **69.3** | scroll sur compte | **Écran principal extrait** |

### 1.1 Variable existante à utiliser

La variable existe déjà dans **Tâche 69.3** :

| Propriété | Valeur |
|-----------|--------|
| **Variable** | **KZ** |
| **Nom** | `v.Edition partielle?` |
| **Type** | Logical (Boolean) |
| **Position** | Data View > Columns |

### 1.2 Question existante (Verify Warning)

La question est **DÉJÀ IMPLÉMENTÉE** :

| Emplacement | Valeur |
|-------------|--------|
| **Programme** | ADH IDE 69 |
| **Tâche** | **69.3** (scroll sur compte) |
| **Section** | Logic |
| **Ligne** | **21** |
| **Opération** | **Verify Warning** |

```
Tâche 69.3 ligne 21 : Verify Warning
  Message : "Voulez-vous éditer l'extrait de compte complet ?"
  Buttons : Yes / No
  Return  : KZ (v.Edition partielle?)
            TRUE = Yes (extrait complet)
            FALSE = No (masquer annulations)
```

**NOTE** : La logique d'interrogation existe déjà. Il reste à propager la variable KZ vers les programmes d'édition et à ajouter le filtre.

### 1.3 Modifier les 5 CallTask

Pour CHAQUE CallTask vers les programmes d'édition, ajouter un argument :

| CallTask vers | IDE | Position | Argument à ajouter |
|---------------|-----|----------|-------------------|
| EXTRAIT_NOM | **ADH IDE 70** | Tâche 69.3, Handler Variable KN (W1 Choix_action), Block 'N' | Arg 15 = `KZ` |
| EXTRAIT_DATE | **ADH IDE 71** | Tâche 69.3, Handler Variable KN (W1 Choix_action), Block 'D' | Arg 14 = `KZ` |
| EXTRAIT_CUM | **ADH IDE 72** | Tâche 69.3, Handler Variable KN (W1 Choix_action), Block 'C' | Arg 13 = `KZ` |
| EXTRAIT_IMP | **ADH IDE 73** | Tâche 69.3, Handler Variable KN (W1 Choix_action), Block 'I' | Arg 13 = `KZ` |
| EXTRAIT_SERVICE | **ADH IDE 76** | Tâche 69.3, Handler Variable KN (W1 Choix_action), Block 'S' | Arg 14 = `KZ` |

**Procédure :**
1. Ouvrir le CallTask dans Tâche 69.3
2. Aller dans Arguments
3. Ajouter une nouvelle ligne à la fin
4. Sélectionner la variable `KZ` (v.Edition partielle?)

---

## ÉTAPE 2 : Modifier ADH IDE 70 (EXTRAIT_NOM)

### 2.1 Ajouter le paramètre d'entrée

| Emplacement | Valeur |
|-------------|--------|
| **Programme** | ADH IDE 70 |
| **Section** | Task Properties > Parameters |

**Paramètre à ajouter :**

| # | Nom | Type | Direction | Description |
|---|-----|------|-----------|-------------|
| 15 | `P.ExtraitComplet` | Logical | Input | TRUE=complet, FALSE=masquer annulations |

### 2.2 Modifier le Range/Locate des sous-tâches d'impression

**Sous-tâches concernées** : Toutes les sous-tâches utilisant **Table n°40** comme MainSource
- "extrait Nom A4"
- "extrait Nom TMT88"
- "extrait Nom A4 V2"
- etc. (~17 sous-tâches)

| Emplacement | Valeur |
|-------------|--------|
| **Section** | Data View > Main Source > Range/Locate |

**Ajouter dans Locate Expression :**

```magic
P.ExtraitComplet OR Trim(A.cte_flag_annulation) = 'Normal'
```

---

## ÉTAPE 3 : Modifier ADH IDE 71 (EXTRAIT_DATE)

### 3.1 Ajouter paramètre

| # | Nom | Type | Direction |
|---|-----|------|-----------|
| 14 | `P.ExtraitComplet` | Logical | Input |

### 3.2 Modifier Range/Locate

Dans toutes les sous-tâches d'impression (~15 sous-tâches), ajouter dans Locate :
```magic
P.ExtraitComplet OR Trim(A.cte_flag_annulation) = 'Normal'
```

---

## ÉTAPE 4 : Modifier ADH IDE 72 (EXTRAIT_CUM)

### 4.1 Ajouter paramètre

| # | Nom | Type | Direction |
|---|-----|------|-----------|
| 13 | `P.ExtraitComplet` | Logical | Input |

### 4.2 Modifier Range/Locate

Dans toutes les sous-tâches d'impression (~13 sous-tâches), ajouter dans Locate :
```magic
P.ExtraitComplet OR Trim(A.cte_flag_annulation) = 'Normal'
```

---

## ÉTAPE 5 : Modifier ADH IDE 73 (EXTRAIT_IMP)

### 5.1 Ajouter paramètre

| # | Nom | Type | Direction |
|---|-----|------|-----------|
| 13 | `P.ExtraitComplet` | Logical | Input |

### 5.2 Modifier Range/Locate

Dans toutes les sous-tâches d'impression (~12 sous-tâches), ajouter dans Locate :
```magic
P.ExtraitComplet OR Trim(A.cte_flag_annulation) = 'Normal'
```

---

## ÉTAPE 6 : Modifier ADH IDE 76 (EXTRAIT_SERVICE)

### 6.1 Ajouter paramètre

| # | Nom | Type | Direction |
|---|-----|------|-----------|
| 14 | `P.ExtraitComplet` | Logical | Input |

### 6.2 Modifier Range/Locate

Dans toutes les sous-tâches d'impression (~15 sous-tâches), ajouter dans Locate :
```magic
P.ExtraitComplet OR Trim(A.cte_flag_annulation) = 'Normal'
```

---

## RÉSUMÉ DES MODIFICATIONS

| IDE | Nom | Modifications |
|-----|-----|---------------|
| **ADH IDE 69** | EXTRAIT_COMPTE | Variable KZ existe (ligne 21 Verify Warning), modifier 5 CallTask pour passer KZ |
| **ADH IDE 70** | EXTRAIT_NOM | +1 paramètre (n°15), modifier Locate ~17 sous-tâches |
| **ADH IDE 71** | EXTRAIT_DATE | +1 paramètre (n°14), modifier Locate ~15 sous-tâches |
| **ADH IDE 72** | EXTRAIT_CUM | +1 paramètre (n°13), modifier Locate ~13 sous-tâches |
| **ADH IDE 73** | EXTRAIT_IMP | +1 paramètre (n°13), modifier Locate ~12 sous-tâches |
| **ADH IDE 76** | EXTRAIT_SERVICE | +1 paramètre (n°14), modifier Locate ~15 sous-tâches |

**Total** : 6 programmes, ~75 modifications de Locate

**NOTE IMPORTANTE** : Le Verify Warning et la variable KZ existent déjà dans ADH IDE 69 Tâche 69.3 ligne 21.

---

## EXPRESSION CLÉ À UTILISER

```magic
P.ExtraitComplet OR Trim(A.cte_flag_annulation) = 'Normal'
```

**Explication** :
- Si `P.ExtraitComplet = TRUE` → afficher TOUTES les lignes (OR court-circuite)
- Si `P.ExtraitComplet = FALSE` → afficher seulement où `cte_flag_annulation = 'Normal'`

Le `Trim()` est important car le champ peut contenir des espaces.

---

## TEST DE VALIDATION

1. Ouvrir Caisse Adhérent sur un compte avec annulations (ex: BENNUN 572185684)
2. Aller sur Extrait de compte
3. Choisir édition par Nom (N)
4. Question "Extrait complet ?" → répondre **OUI**
   - Vérifier : toutes les lignes affichées (y compris annulations)
5. Refaire édition par Nom (N)
6. Question "Extrait complet ?" → répondre **NON**
   - Vérifier : lignes "Annulation" et "X-annule" masquées
7. Répéter pour Date (D), Service (S), Cumulé (C), Impression (I)

---

## Fichiers Associés

| Type | Lien |
|------|------|
| Analyse complète | [analysis.md](./analysis.md) |
| Notes de travail | [notes.md](./notes.md) |
| Spécification détaillée | [implementation.md](./implementation.md) |
| Captures d'écran | [attachments/](./attachments/) |
| Ticket Jira | [PMS-1373](https://clubmed.atlassian.net/browse/PMS-1373) |
| Branche Git | [feature/PMS-1373](https://github.com/thonyAGP/PMS-Magic-Sources/tree/feature/PMS-1373-masquer-annulations) |

---

## Validation

- [ ] Tests unitaires OK
- [ ] Recette fonctionnelle OK
- [ ] Documentation mise à jour
- [ ] Capitalisation KB (`/ticket-learn`)

---

*Résolution générée le 2026-01-08*

---

*DerniÃ¨re mise Ã  jour : 2026-01-22T18:55*
