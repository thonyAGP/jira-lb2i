# PUG IDE 14 - Purge Point de vente

> **Analyse**: 2026-02-03 18:30
> **Pipeline**: V7.2 Enrichi

## RESUME EXECUTIF

- **Fonction**: Purge Point de vente
- **Tables modifiees**: 9
- **Complexite**: **BASSE** (32/100)
- **Statut**: NON_ORPHELIN
- **Raison**: Appele par 3 programme(s): Purge Batch (IDE 18), Purge - NU - (IDE 24), Purge Batch Save (IDE 25)

## PROGRAMMES LIES

| Direction | Programmes |
|-----------|------------|
| **Appele par** | [Purge Batch (IDE 18)](PUG-IDE-18.md), [Purge - NU - (IDE 24)](PUG-IDE-24.md), [Purge Batch Save (IDE 25)](PUG-IDE-25.md) |
| **Appelle** | [Vidage table SQL (IDE 20)](PUG-IDE-20.md) |

## STATISTIQUES

| Metrique | Valeur |
|----------|--------|
| Taches | 9 |
| Lignes Logic | 274 |
| Expressions | 3 |
| Tables | 10 |

---
*Spec SUMMARY generee par Pipeline V7.2*
