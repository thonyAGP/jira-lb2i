# Resolution CMDS-176521

> **Jira** : [CMDS-176521](https://clubmed.atlassian.net/browse/CMDS-176521)

## Statut: RÉSOLU ✅

---

## Symptôme

**Bug d'affichage du prix remisé dans le POS (module PVE)**

- Prix attendu avec -10% : **5,400 JPY**
- Prix affiché : **41,857** (valeur incorrecte = numéro adhérent)
- Prix facturé à la validation : **CORRECT**

---

## Cause racine

**L'expression d'affichage utilisait le numéro d'adhérent au lieu du prix_net de la ligne.**

Dans l'expression de calcul du prix remisé, la variable référencée était incorrecte :
- **Variable utilisée** : Numéro adhérent (valeur 41,857)
- **Variable attendue** : Prix_net de la ligne (5,400 JPY avant remise → 4,860 JPY après -10%)

---

## Fix appliqué

### Modification technique

**Remplacement de la variable dans l'expression d'affichage** :

| Élément | Avant (bug) | Après (fix) |
|---------|-------------|-------------|
| Variable | Numéro adhérent | Prix_net ligne |
| Valeur affichée | 41,857 | Prix calculé correct |

### Programmes corrigés

| Programme | Description |
|-----------|-------------|
| PVE IDE 180 | Main Sale |
| **PVE IDE 181** | Main Sale-664 |
| PVE IDE 284 | Main Sale Sale Bar Code |

---

## Explication du bug

La valeur **41,857** correspondait au **numéro d'adhérent** du GM, qui était affiché par erreur à la place du prix remisé.

Le calcul du prix était correct (d'où la facturation correcte), mais l'affichage à l'écran référençait la mauvaise variable.

---

## Références Magic IDE

### Programme principal

| IDE | Projet | Nom Public | Fichier |
|-----|--------|------------|---------|
| **PVE IDE 181** | PVE | Main Sale-664 | Prg_181.xml |

---

## Validation

- [x] Fix déployé
- [x] 3 programmes corrigés (180, 181, 284)
- [x] Affichage prix remisé correct

---

*Dernière mise à jour : 2026-01-22T18:55*
*Fix: remplacement numéro adhérent par prix_net dans expression d'affichage*
