# PMS-1359 - Resolution

> **Jira** : [PMS-1359](https://clubmed.atlassian.net/browse/PMS-1359)

---

## Diagnostic

| Critere | Valeur |
|---------|--------|
| **Type** | Bug d'implementation (cablage manquant) |
| **Severite** | Moyenne - fonctionnalite implementee a moitie |
| **Programme** | VIL IDE 22 - Print recap sessions |
| **Tache** | 22.16.1 (ISN_2=19) - Reception |

### Root Cause

Les expressions 35 et 36 qui ajoutent `**` au FDR Initial quand il y a un ecart
avec la fermeture de la veille **existent dans le code** mais ne sont **pas referencees**
dans les MERGE_PARM des formulaires d'impression HTML (`sessions2.htm`).

Les tags HTML `FDRICOFFRE2` et `FDRIRECEP2` utilisent encore les anciennes expressions
(8 et 9) qui affichent juste la valeur numerique sans indicateur `**`.

### Chronologie du bug

1. **01/10/2025** : Commit `9422490b5` — creation expressions 35/36 + variables ecart
2. **01/10/2025** : Oubli de brancher Exp 35/36 dans les MERGE_PARM
3. **24/10/2025** : Jessica teste et signale que ca ne marche pas
4. **06/02/2026** : Jessica confirme que ca ne fonctionne toujours pas

---

## Fix

### 2 lignes a modifier dans Prg_558.xml

**1. MERGE_PARM FDRICOFFRE2 (Form "Merge Coffre 2")** :

```xml
<!-- Ligne 18094 - changer Exp="8" en Exp="35" -->
<MERGE_PARM Exp="35" PIC_U="30" TXT_U="FDRICOFFRE2" id="10"/>
```

**2. MERGE_PARM FDRIRECEP2 (Form "Merge Recept.")** :

```xml
<!-- Ligne 18135 - changer Exp="9" en Exp="36" -->
<MERGE_PARM Exp="36" PIC_U="30" TXT_U="FDRIRECEP2" id="54"/>
```

### Verification pre-fix

Avant d'appliquer, verifier dans l'IDE Magic :
1. Que Expression 35 retourne bien le FDR Initial formate (pas juste `**`)
2. Que Expression 8 n'est pas utilisee par d'autres MERGE_PARM pour d'autres valeurs
3. Que le PIC_U="30" est compatible (Expression 35 retourne du Alpha, PIC_U "30" = 30 chars)

---

## Decision

**STATUT** : `BUG CONFIRME - FIX IDENTIFIE`

Fix minimal : 2 attributs a changer dans les MERGE_PARM.

---

*Resolution documentee le 2026-02-17*
