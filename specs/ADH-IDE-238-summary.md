# ADH IDE 238 - Transaction Nouv vente PMS-584

> **Analyse**: 2026-02-08 04:33
> **Pipeline**: V7.2 Enrichi

## RESUME EXECUTIF

- **Fonction**: Transaction Nouv vente PMS-584
- **Tables modifiees**: 11
- **Complexite**: **HAUTE** (85/100)
- **Statut**: NON_ORPHELIN
- **Raison**: Appele par 2 programme(s): Menu caisse GM - scroll (IDE 163), Menu Choix Saisie/Annul vente (IDE 242)

## PROGRAMMES LIES

| Direction | Programmes |
|-----------|------------|
| **Appele par** | [Menu caisse GM - scroll (IDE 163)](ADH-IDE-163.md), [Menu Choix Saisie/Annul vente (IDE 242)](ADH-IDE-242.md) |
| **Appelle** | [Recup Classe et Lib du MOP (IDE 152)](ADH-IDE-152.md), [ Print ticket vente PMS-584 (IDE 236)](ADH-IDE-236.md), [Solde Gift Pass (IDE 241)](ADH-IDE-241.md), [    SP Caractères Interdits (IDE 84)](ADH-IDE-84.md), [ Print ticket vente LEX (IDE 235)](ADH-IDE-235.md), [Reinit Aff PYR (IDE 249)](ADH-IDE-249.md), [Selection Vols /t Ville à côté (IDE 277)](ADH-IDE-277.md), [Recuperation du titre (IDE 43)](ADH-IDE-43.md), [Calcul stock produit WS (IDE 149)](ADH-IDE-149.md), [Get Printer (IDE 179)](ADH-IDE-179.md), [Printer choice (IDE 180)](ADH-IDE-180.md), [Set Listing Number (IDE 181)](ADH-IDE-181.md), [Raz Current Printer (IDE 182)](ADH-IDE-182.md), [Get Fidelisation et Remise (IDE 225)](ADH-IDE-225.md), [Get Matricule (IDE 227)](ADH-IDE-227.md), [Gestion Chèque (IDE 228)](ADH-IDE-228.md), [Deversement Transaction (IDE 247)](ADH-IDE-247.md), [Choix PYR (plusieurs chambres) (IDE 248)](ADH-IDE-248.md), [Solde Resort Credit (IDE 254)](ADH-IDE-254.md), [Zoom articles (IDE 257)](ADH-IDE-257.md) |

## STATISTIQUES

| Metrique | Valeur |
|----------|--------|
| Taches | 63 |
| Lignes Logic | 2324 |
| Expressions | 350 |
| Tables | 34 |

---
*Spec SUMMARY generee par Pipeline V7.2*
