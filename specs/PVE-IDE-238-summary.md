# PVE IDE 238 - Input Inventory

> **Analyse**: 2026-02-03 19:08
> **Pipeline**: V7.2 Enrichi

## RESUME EXECUTIF

- **Fonction**: Input Inventory
- **Tables modifiees**: 2
- **Complexite**: **BASSE** (17/100)
- **Statut**: NON_ORPHELIN
- **Raison**: Appele par 2 programme(s): Menu Stocks Management (IDE 179), Visu des Gap (IDE 242)

## PROGRAMMES LIES

| Direction | Programmes |
|-----------|------------|
| **Appele par** | [Menu Stocks Management (IDE 179)](PVE-IDE-179.md), [Visu des Gap (IDE 242)](PVE-IDE-242.md) |
| **Appelle** | [Saisie date stock (IDE 239)](PVE-IDE-239.md), [Visu des Gap (IDE 242)](PVE-IDE-242.md), [Verif si Gap existe (IDE 243)](PVE-IDE-243.md), [Batch validation inventory (IDE 244)](PVE-IDE-244.md), [Stock - Inventory list (IDE 245)](PVE-IDE-245.md), [Stock - Gap list (IDE 246)](PVE-IDE-246.md) |

## STATISTIQUES

| Metrique | Valeur |
|----------|--------|
| Taches | 5 |
| Lignes Logic | 205 |
| Expressions | 49 |
| Tables | 6 |

---
*Spec SUMMARY generee par Pipeline V7.2*
