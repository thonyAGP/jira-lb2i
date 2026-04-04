# PVE IDE 83 - Print Global Income

> **Analyse**: 2026-02-03 09:14
> **Pipeline**: V7.2 Enrichi

## RESUME EXECUTIF

- **Fonction**: Print Global Income
- **Tables modifiees**: 1
- **Complexite**: **BASSE** (19/100)
- **Statut**: NON_ORPHELIN
- **Raison**: Appele par 4 programme(s): Menu Cloture du service (IDE 180), Menu Reports (IDE 182), Menu Service cloture v2 (IDE 397), Menu Service cloture (IDE 402)

## PROGRAMMES LIES

| Direction | Programmes |
|-----------|------------|
| **Appele par** | [Menu Cloture du service (IDE 180)](PVE-IDE-180.md), [Menu Reports (IDE 182)](PVE-IDE-182.md), [Menu Service cloture v2 (IDE 397)](PVE-IDE-397.md), [Menu Service cloture (IDE 402)](PVE-IDE-402.md) |
| **Appelle** | [Get Temp Files (IDE 46)](PVE-IDE-46.md), [IoDel fichier CSV (IDE 56)](PVE-IDE-56.md) |

## STATISTIQUES

| Metrique | Valeur |
|----------|--------|
| Taches | 14 |
| Lignes Logic | 446 |
| Expressions | 8 |
| Tables | 6 |

---
*Spec SUMMARY generee par Pipeline V7.2*
