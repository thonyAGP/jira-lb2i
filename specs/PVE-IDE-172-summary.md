# PVE IDE 172 - FindAppointmentsToClose

> **Analyse**: 2026-02-03 18:39
> **Pipeline**: V7.2 Enrichi

## RESUME EXECUTIF

- **Fonction**: FindAppointmentsToClose
- **Tables modifiees**: 0
- **Complexite**: **BASSE** (5/100)
- **Statut**: NON_ORPHELIN
- **Raison**: Appele par 2 programme(s): Ligne Non Validées & Edit Book (IDE 129), Menu (IDE 185)

## PROGRAMMES LIES

| Direction | Programmes |
|-----------|------------|
| **Appele par** | [Ligne Non Validées & Edit Book (IDE 129)](PVE-IDE-129.md), [Menu (IDE 185)](PVE-IDE-185.md) |
| **Appelle** | [TraceLogBooker (IDE 175)](PVE-IDE-175.md), [GetToken (IDE 151)](PVE-IDE-151.md), [CloseOrder (IDE 163)](PVE-IDE-163.md), [CloseOrder-392 (IDE 164)](PVE-IDE-164.md) |

## STATISTIQUES

| Metrique | Valeur |
|----------|--------|
| Taches | 2 |
| Lignes Logic | 148 |
| Expressions | 13 |
| Tables |  |

---
*Spec SUMMARY generee par Pipeline V7.2*
