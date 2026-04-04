# PMS-1459 - Annulation echange POS SKI rembourse montant total

## Contexte Jira

| Element | Valeur |
|---------|--------|
| **Type** | Bug |
| **Symptome** | CANCEL d'un EXCHANGE rembourse le prix total du nouvel equipement au lieu de la difference |
| **Village** | Best Of - Insurance - SKI |
| **Exemple** | Echange SPORT 66 EUR -> PERF 74 EUR, difference 8 EUR. Annulation rembourse 74 EUR |
| **Priorite** | Haute |

## Programmes identifies

| Programme | Role |
|-----------|------|
| PVE IDE 393 - Menu Check IN/Exchange V4 | Point d'entree echange V4 |
| PVE IDE 183 - Menu Check IN / Exchange | Version anterieure (meme flux) |
| PVE IDE 218 - Package pricing | Calcul des prix (66 expressions, gere SALE/RENTAL/EXCHANGE/RETURN-/EXTEND) |
| PVE IDE 312 - Recalcul annulations | **ROOT CAUSE** - filtre les lignes EXCHANGE (expr 31/32) |
| PVE IDE 226 - Stock Sale/Cancel | Gestion stock annulation |
| PVE IDE 214 - Main Sale Sale Bar Code | Ecran principal vente |

## Tables concernees

| Table | Nom | Usage |
|-------|-----|-------|
| pv_cust_rentals | Locations client | Historique locations |
| pv_equipment_inventory | Inventaire | Stock equipements |
| pv_sellers_by_week | Vendeurs | Stats vendeur (W) |
| vente_par_moyen_paiement | Ventes MOP | Enregistrement paiement (W) |
| articles_________art | Articles | Catalogue prix |

## Root Cause

1. L'echange cree 3 lignes liees (retour ancien 0, credit -66, debit +74 = net 8)
2. L'annulation via PVE IDE 312 IGNORE les lignes EXCHANGE (expressions 31/32 forcent a 0/FALSE)
3. Seule la ligne RENTAL (74 EUR) est annulee -> remboursement de 74 au lieu de 8
4. Ecart = 66 EUR par annulation d'echange

## Expressions cles

- PVE IDE 312 expr 31: `IF(Trim({1,21})='EXCHANGE','FALSE',{1,38})` → ignore EXCHANGE
- PVE IDE 312 expr 32: `IF(Trim({1,21})='EXCHANGE',0,{1,40})` → montant = 0 pour EXCHANGE
- PVE IDE 218 expr 2: Utilise `Date()` → annulation jour meme uniquement
- PVE IDE 218 expr 12: `P.Action[C]<>'EXTEND' AND P.Action[C]<>'EXCHANGE'` → distinction actions

## Questions ouvertes

- [ ] Les 3 lignes d'echange sont-elles liees par un Package Id commun ?
- [ ] Le bug existe-t-il aussi sur la version non-V4 (PVE IDE 183) ?
- [ ] Quelle option de correction est preferee (annuler les 3 lignes vs calculer le net) ?
- [ ] Impact sur les echanges deja annules dans l'historique ?

## Mots-cles

- annulation, echange, exchange, cancel, POS SKI, remboursement
- montant total, difference, delta, 3 lignes, RENTAL, EXCHANGE
- PVE IDE 312, recalcul, expressions 31/32
