# ADH IDE 237 - Transaction Nouv vente avec GP

> **Analyse**: 2026-02-07 03:54
> **Pipeline**: V7.2 Enrichi

## RESUME EXECUTIF

- **Fonction**: Transaction Nouv vente avec GP
- **Tables modifiees**: 9
- **Complexite**: **HAUTE** (85/100)
- **Statut**: NON_ORPHELIN
- **Raison**: Appele par 3 programme(s): Menu caisse GM - scroll (IDE 163), Menu Choix Saisie/Annul vente (IDE 242), Saisie transaction Nouv vente (IDE 316)

## PROGRAMMES LIES

| Direction | Programmes |
|-----------|------------|
| **Appele par** | [Menu caisse GM - scroll (IDE 163)](ADH-IDE-163.md), [Menu Choix Saisie/Annul vente (IDE 242)](ADH-IDE-242.md), [Saisie transaction Nouv vente (IDE 316)](ADH-IDE-316.md) |
| **Appelle** | [Recup Classe et Lib du MOP (IDE 152)](ADH-IDE-152.md), [    SP Caractères Interdits (IDE 84)](ADH-IDE-84.md), [Appel Print ticket vente PMS28 (IDE 233)](ADH-IDE-233.md), [Reinit Aff PYR (IDE 249)](ADH-IDE-249.md), [Selection Vols /t Ville à côté (IDE 277)](ADH-IDE-277.md), [Recuperation du titre (IDE 43)](ADH-IDE-43.md), [Calcul stock produit WS (IDE 149)](ADH-IDE-149.md), [Get Printer (IDE 179)](ADH-IDE-179.md), [Printer choice (IDE 180)](ADH-IDE-180.md), [Set Listing Number (IDE 181)](ADH-IDE-181.md), [Raz Current Printer (IDE 182)](ADH-IDE-182.md), [Get Fidelisation et Remise (IDE 225)](ADH-IDE-225.md), [Get Matricule (IDE 227)](ADH-IDE-227.md), [Gestion Chèque (IDE 228)](ADH-IDE-228.md), [Solde Gift Pass (IDE 241)](ADH-IDE-241.md), [Deversement Transaction (IDE 247)](ADH-IDE-247.md), [Choix PYR (plusieurs chambres) (IDE 248)](ADH-IDE-248.md), [Solde Resort Credit (IDE 254)](ADH-IDE-254.md), [Zoom articles (IDE 257)](ADH-IDE-257.md), [Zoom services village (IDE 269)](ADH-IDE-269.md) |

## STATISTIQUES

| Metrique | Valeur |
|----------|--------|
| Taches | 49 |
| Lignes Logic | 1818 |
| Expressions | 305 |
| Tables | 30 |

---
*Spec SUMMARY generee par Pipeline V7.2*
