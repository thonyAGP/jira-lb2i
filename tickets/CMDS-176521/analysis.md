# Analyse CMDS-176521

> **Jira** : [CMDS-176521](https://clubmed.atlassian.net/browse/CMDS-176521)

## Symptome

**Bug d'affichage du prix remise dans le POS**

Dans le POS, quand une remise est appliquee, le prix affiche apres remise est incorrect.
Le prix facture (a la validation) est correct.

**Exemple concret:**
- Article: Peter Lehmann Riesli (ID 2713)
- Prix original: 6,000 JPY
- Remise: -10%
- Prix affiche: **41,857 JPY** (FAUX)
- Prix correct attendu: **5,400 JPY** (6000 * 0.9)
- Prix a la validation: **5,400 JPY** (CORRECT)

## Contexte

| Element | Valeur |
|---------|--------|
| **Village/Site** | Kiroro Grand (Japon) |
| **Service** | BARD (Bar) |
| **Date incident** | 2026-01-08 |
| **Reporter** | Bar Manager Kiroro Grand |
| **Statut Jira** | Complete (confirme par Davide, fix prevu fin janvier) |

## Investigation

### Observations cles

1. **Le calcul backend est correct** - A la validation, le prix est bien 5,400 JPY
2. **L'affichage est incorrect** - Le champ prix remise affiche 41,857 au lieu de 5,400
3. **Origine du 41,857** - Valeur suspecte, probablement:
   - Un autre champ (solde cumule?)
   - Une mauvaise reference de variable
   - Un probleme de formatage numerique

### Module concerne

**PVE** (Point de Vente/POS) - `D:\Data\Migration\XPA\PMS\PVE\Source\`

### Programmes identifies

| Projet | Prg ID | Nom Public | Description | Statut |
|--------|--------|------------|-------------|--------|
| PVE | **180** | Main Sale | Ecran principal POS | ANALYSE |
| PVE | **195** | Discounts | Gestion des remises | **ANALYSE COMPLETE** |
| PVE | 181 | Main Sale-664 | Version alternative | Reference |
| PVE | 219 | Discounts | Autre version | Reference |

### Tables concernees

| Table | Fichier Physique | Champs cles | Role |
|-------|------------------|-------------|------|
| ventes_pos | ? | prix, remise, prix_remise | Lignes de vente |
| articles | ? | prix_vente | Prix catalogue |

### Hypotheses

| # | Hypothese | Probabilite | Explication |
|---|-----------|-------------|-------------|
| 1 | **Mauvaise variable affichee** | HAUTE | Le champ "prix remise" reference une autre variable (solde compte?) au lieu du prix calcule |
| 2 | Probleme de calcul d'expression | MOYENNE | L'expression qui calcule le prix remise a une erreur |
| 3 | Bug de formatage numerique | FAIBLE | Confusion virgule/point (peu probable avec JPY) |

## Analyse technique

### Tracage a effectuer

1. Identifier l'ecran POS principal dans PVE
2. Trouver le champ "Prix" dans la grille des ventes
3. Tracer l'expression qui alimente ce champ quand une remise est appliquee
4. Verifier la variable source

### Requetes de verification

```sql
-- Verifier si 41857 correspond a un solde existant
SELECT * FROM operations_dat
WHERE solde = 41857 OR credit = 41857 OR debit = 41857

-- Verifier les ventes recentes a Kiroro
SELECT * FROM ventes
WHERE village = 'KIRO' AND date_vente >= '2026-01-08'
```

## Resolution prevue

Davide (CMDS) a confirme:
- Bug acknowledge
- Correction prevue avant fin janvier 2026
- Ticket Jira dev ouvert pour prochaine release PMS

## Prochaines etapes

1. [ ] Identifier les programmes POS dans PVE avec `/magic-search`
2. [ ] Analyser le formulaire de vente (grille des lignes)
3. [ ] Tracer l'expression du champ "prix remise"
4. [ ] Identifier la variable fautive
5. [ ] Proposer le fix

---

*Rapport genere le 2026-01-08*
*Pieces jointes: 4 screenshots dans attachments/*

---

*DerniÃ¨re mise Ã  jour : 2026-01-22T18:55*
