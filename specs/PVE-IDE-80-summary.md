# PVE IDE 80 - Print Income

> **Analyse**: 2026-02-03 09:13
> **Pipeline**: V7.2 Enrichi

## RESUME EXECUTIF

- **Fonction**: Print Income
- **Tables modifiees**: 3
- **Complexite**: **BASSE** (19/100)
- **Statut**: NON_ORPHELIN
- **Raison**: Appele par 5 programme(s): Menu Cloture du service (IDE 180), Menu Reports (IDE 182), Ecran Prepaid Income GEST (IDE 82), Menu Service cloture v2 (IDE 397), Menu Service cloture (IDE 402)

## PROGRAMMES LIES

| Direction | Programmes |
|-----------|------------|
| **Appele par** | [Menu Cloture du service (IDE 180)](PVE-IDE-180.md), [Menu Reports (IDE 182)](PVE-IDE-182.md), [Ecran Prepaid Income GEST (IDE 82)](PVE-IDE-82.md), [Menu Service cloture v2 (IDE 397)](PVE-IDE-397.md), [Menu Service cloture (IDE 402)](PVE-IDE-402.md) |
| **Appelle** | [Alimentation_product_price (IDE 85)](PVE-IDE-85.md), [Get Temp Files (IDE 46)](PVE-IDE-46.md), [IoDel fichier CSV (IDE 56)](PVE-IDE-56.md) |

## STATISTIQUES

| Metrique | Valeur |
|----------|--------|
| Taches | 14 |
| Lignes Logic | 1030 |
| Expressions | 10 |
| Tables | 17 |

---
*Spec SUMMARY generee par Pipeline V7.2*
