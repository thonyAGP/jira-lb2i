# ADH IDE 243 - Histo ventes payantes

> **Analyse**: 2026-02-08 04:35
> **Pipeline**: V7.2 Enrichi

## RESUME EXECUTIF

- **Fonction**: Histo ventes payantes
- **Tables modifiees**: 4
- **Complexite**: **MOYENNE** (46/100)
- **Statut**: NON_ORPHELIN
- **Raison**: Appele par 4 programme(s): Transaction Nouv vente PMS-584 (IDE 0), Transaction Nouv vente PMS-710 (IDE 0), Transaction Nouv vente PMS-721 (IDE 0), Menu Choix Saisie/Annul vente (IDE 242)

## PROGRAMMES LIES

| Direction | Programmes |
|-----------|------------|
| **Appele par** | [Transaction Nouv vente PMS-584 (IDE 0)](ADH-IDE-0.md), [Transaction Nouv vente PMS-710 (IDE 0)](ADH-IDE-0.md), [Transaction Nouv vente PMS-721 (IDE 0)](ADH-IDE-0.md), [Menu Choix Saisie/Annul vente (IDE 242)](ADH-IDE-242.md) |
| **Appelle** | [Appel Print ticket vente PMS28 (IDE 233)](ADH-IDE-233.md), [ Print ticket vente LEX (IDE 235)](ADH-IDE-235.md), [ Print ticket vente PMS-584 (IDE 236)](ADH-IDE-236.md), [Get Printer (IDE 179)](ADH-IDE-179.md), [Set Listing Number (IDE 181)](ADH-IDE-181.md), [Raz Current Printer (IDE 182)](ADH-IDE-182.md), [Deversement Transaction (IDE 247)](ADH-IDE-247.md) |

## STATISTIQUES

| Metrique | Valeur |
|----------|--------|
| Taches | 22 |
| Lignes Logic | 1528 |
| Expressions | 72 |
| Tables | 25 |

---
*Spec SUMMARY generee par Pipeline V7.2*
