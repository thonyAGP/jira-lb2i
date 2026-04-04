# Analyse PMS-1437

> **Jira** : [PMS-1437](https://clubmed.atlassian.net/browse/PMS-1437)

## Symptome

**POS SKI: early return mauvaise date affichee**

Lors d'un EARLY RETURN sur location ski, les dates affichees sur la ligne de vente sont incorrectes.

### Exemple du ticket

| Element | Valeur |
|---------|--------|
| **Village** | VTHC (Val Thorens) |
| **Article** | SKI PRESTIGE 6 jours |
| **Periode location** | 15/12 au 20/12 |
| **Early Return** | 16/12 (2 jours utilises) |
| **Dates attendues** | 15 au 16 |
| **Dates affichees** | 16 au 17 (BUG) |

**IMPORTANT** : Les montants calcules sont CORRECTS. C'est uniquement un souci d'affichage.

## Contexte

| Element | Valeur |
|---------|--------|
| **Type** | Bug |
| **Priority** | Haute |
| **Status** | Recette KO |
| **Reporter** | Davide Morandi |
| **Assignee** | Anthony Leberre |
| **Labels** | PVE |

---

## CLASSEMENT DES PISTES PAR SUSPICION (2026-01-13)

### PISTE 1 : Expression avec MODEDAYINC - HAUTE SUSPICION

**Localisation** : Tache 186.1.5.4.3 "Saisir Date Fin de location"

**Programme** : PVE IDE 186 - Main Sale

**Expression decouverte** :
```
Expression 28 = Date() - GetParam('MODEDAYINC') + Variable WG
```

**Analyse** :
- `GetParam('MODEDAYINC')` retourne 0 (AM) ou 1 (PM)
- En Magic, les dates sont stockees comme numeriques (jours depuis epoch)
- Si MODEDAYINC=1, le calcul devient : `AujourdHui - 1 + DateFinSelectionnee`

**Probleme potentiel** :
Cette expression melange des dates de maniere confuse. Elle est utilisee pour calculer une date qui sera ensuite affichee. Le `-1` de MODEDAYINC pourrait causer le decalage observe.

**Verification requise** :
1. Quelle est la valeur de MODEDAYINC sur VTHC ?
2. Ou cette expression est-elle utilisee exactement ?
3. Tester avec MODEDAYINC=0 vs MODEDAYINC=1

---

### PISTE 2 : Update desactive dans UpdateCustRentals - MOYENNE SUSPICION

**Localisation** : Tache 186.1.5.4.4 "UpdateCustRentals"

**Decouverte** :
Un Update est DESACTIVE dans cette tache.

**Interpretation** :
- Cet update etait cense mettre a jour un champ date
- Il a ete desactive volontairement ou par erreur
- Les autres updates sont actifs

**Hypothese** :
L'update de la date a ete desactive, ce qui explique pourquoi la date affichee est incorrecte apres l'Early Return.

**Verification requise** :
1. Pourquoi cet update est-il desactive ?
2. Quel champ est concerne ?
3. Reactiver et tester

---

### PISTE 3 : Variables de dates dans Tache 186.1.5.4 - MOYENNE SUSPICION

**Variables du DataView** :

> **Note** : Les variables sont numerotees globalement avec offset cumulatif.
> Premiere variable de Tache 186.1.5.4 = **Variable WB** (pas A)

| Variable | Nom | Type | Role |
|----------|-----|------|------|
| **WF** | V.PremierJourLocation | Date | Premier jour de location |
| **WG** | V.DernierJourLocation | Date | Dernier jour de location |
| **WH** | V.NumberDaysAFacture | Numeric | Nombre de jours a facturer |

**Observation** :
Les variables WF et WG sont les dates de location. Si elles ne sont pas mises a jour correctement lors de l'Early Return, l'affichage sera incorrect.

**Hypothese** :
Les updates envoient les dates vers les mauvaises variables ?

---

### PISTE 4 : Calcul du nombre de jours (Variable WH) - BASSE SUSPICION

**Statut** : PARTIELLEMENT ECARTEE

Les montants sont corrects, ce qui suggere que le calcul du nombre de jours est correct.

**Expression concernee** :
```
Variable WH = Variable WG - Variable WF + 1
```

**Verification** :
Confirmer que Variable WH n'est pas utilise dans l'expression d'affichage des dates.

---

## SYNTHESE ET PRIORITES

| Piste | Suspicion | Action |
|-------|-----------|--------|
| **1. Expression 28 + MODEDAYINC** | HAUTE | Tracer valeur MODEDAYINC, tester impact |
| **2. Update desactive** | MOYENNE | Reactiver et tester |
| **3. Variables WF/WG mal mises a jour** | MOYENNE | Verifier mapping exact |
| **4. Calcul Variable WH** | BASSE | Deja verifie (montants OK) |

---

## ARBORESCENCE DES TACHES

```
PVE IDE 186 - Main Sale
  |
  +-- Tache 186.1 - Choix Onglet
       |
       +-- Tache 186.1.5 - Sales
            |
            +-- Tache 186.1.5.4 - actions
                 |
                 +-- Tache 186.1.5.4.1 - Cancel other Packages
                 |    +-- Tache 186.1.5.4.1.1 - UpdateCustRentals
                 |
                 +-- Tache 186.1.5.4.2 - Saisie comment annulation
                 |
                 +-- Tache 186.1.5.4.3 - Saisir Date Fin de location  <-- CALENDRIER
                 |
                 +-- Tache 186.1.5.4.4 - UpdateCustRentals  <-- UPDATE DESACTIVE
```

---

## VARIABLES TACHE 186.1.5.4

> **Note** : Offset cumulatif = Main PVE (143) + Tache 186 (119) + Tache 186.1 (3) + Tache 186.1.5 (165) = 430
> Premiere variable = **Variable WB** (index 586)

| Variable | Nom | Type | Description |
|----------|-----|------|-------------|
| **WB** | BP. Exit | Alpha | Bouton sortie |
| **WC** | V days difference | Numeric | Difference jours |
| **WD** | V allow cancel | Logical | Autoriser annulation |
| **WE** | V.Comment annulation | Alpha | Commentaire |
| **WF** | V.PremierJourLocation | Date | Premier jour |
| **WG** | V.DernierJourLocation | Date | Dernier jour |
| **WH** | V.NumberDaysAFacture | Numeric | Jours a facturer |
| **WI** | V.AnnulerToutLaPeriode | Logical | Annuler toute periode |

---

## RECOMMANDATIONS

### Test immediat (sans modification code)

1. **Verifier MODEDAYINC** :
   ```sql
   SELECT * FROM sys_params WHERE param_name = 'MODEDAYINC'
   ```

2. **Comparer dates BDD vs affichage** :
   ```sql
   SELECT
       rental_id,
       date_debut,
       date_fin,
       status
   FROM pv_rentals_dat
   WHERE rental_id = [ID de la location du ticket]
   ```

### Test avec modification (environnement test)

1. **Reactiver update desactive** dans Tache 186.1.5.4.4
2. **Forcer MODEDAYINC=0** et retester
3. **Tracer** avec logs les valeurs de Variable WF, Variable WG, Variable WH lors de l'Early Return

---

*Derniere mise a jour: 2026-01-13*
*Status: INVESTIGATION APPROFONDIE - 4 pistes identifiees*
*Piste prioritaire: Expression 28 avec MODEDAYINC*

---

*DerniÃ¨re mise Ã  jour : 2026-01-22T18:55*
