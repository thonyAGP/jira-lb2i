# PMS-1453 - Resolution

> **Jira** : [PMS-1453](https://clubmed.atlassian.net/browse/PMS-1453)
> **Pattern KB** : `missing-time-validation`

## Diagnostic

Les champs de saisie d'heure de transfert dans **ADH IDE 233, 234, 235, 236** (dossier Ventes) n'ont pas de Picture de validation. L'utilisateur peut saisir des heures invalides comme "70:00" qui sont acceptees et stockees dans la table `transfertn`.

**Cause racine** : Les colonnes FIELD_TIME sans Picture acceptent n'importe quelle valeur numerique.

> **ATTENTION** : ADH IDE 307/313 sont dans le dossier **Suppr** (orphelins) - NE PAS CORRIGER.

## Solution recommandee : Ajouter Picture HH:MM

### Modification XML

Pour chaque programme **Prg_233.xml, Prg_234.xml, Prg_235.xml, Prg_236.xml** :

**Colonnes a modifier** (4 par programme = 16 total) :
- Colonne 222 "W0 Heure du transfert Aller"
- Colonne 234 "W0 Heure du transfert Retour"
- Colonne 5 "W1 Heure transfert Aller"
- Colonne 13 "W1 Heure transfert Retour"

**Ajout requis** :
```xml
<Picture id="157" valUnicode="HH:MM"/>
```

### Programmes a modifier

| Programme | Fichier | Dossier | Statut |
|-----------|---------|---------|--------|
| ADH IDE 233 | Prg_233.xml | **Ventes** | A CORRIGER |
| ADH IDE 234 | Prg_234.xml | **Ventes** | A CORRIGER |
| ADH IDE 235 | Prg_235.xml | **Ventes** | A CORRIGER |
| ADH IDE 236 | Prg_236.xml | **Ventes** | A CORRIGER |
| ~~ADH IDE 307~~ | ~~Prg_307.xml~~ | ~~Suppr~~ | **ORPHELIN - IGNORER** |
| ~~ADH IDE 313~~ | ~~Prg_313.xml~~ | ~~Suppr~~ | **ORPHELIN - IGNORER** |

## Alternative : Validation Control Verify

Si modification Picture impossible, ajouter handler Control Verify :

```
IF heure > 86399 OR heure < 0 THEN
   Verify Error "L'heure doit etre entre 00:00 et 23:59"
   Annuler
END IF
```

## Statut

| Etape | Statut | Date |
|-------|--------|------|
| Analyse initiale | Terminee (erreur) | 2026-01-22T18:55 |
| Analyse corrigee | **Terminee** | **2026-01-26** |
| Pattern KB cree | Termine | 2026-01-26 |
| Validation solution | En attente | |
| Implementation | En attente | |
| Tests | En attente | |
| Deploiement | En attente | |

## Tests de validation

- [ ] Saisie 00:00 -> Acceptee
- [ ] Saisie 12:30 -> Acceptee
- [ ] Saisie 23:59 -> Acceptee
- [ ] Saisie 24:00 -> Rejetee
- [ ] Saisie 70:00 -> Rejetee

---

*Derniere mise a jour : 2026-01-26*
*Correction : IDE 307/313 orphelins, vrais programmes = IDE 233-236*
