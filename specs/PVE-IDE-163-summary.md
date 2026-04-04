# PVE IDE 163 - CloseOrder

> **Analyse**: 2026-02-03 09:52
> **Pipeline**: V7.2 Enrichi

## RESUME EXECUTIF

- **Fonction**: CloseOrder
- **Tables modifiees**: 0
- **Complexite**: **BASSE** (5/100)
- **Statut**: NON_ORPHELIN
- **Raison**: Appele par 2 programme(s): Ligne Non Validées & Edit Book (IDE 129), FindAppointmentsToClose (IDE 172)

## PROGRAMMES LIES

| Direction | Programmes |
|-----------|------------|
| **Appele par** | [Ligne Non Validées & Edit Book (IDE 129)](PVE-IDE-129.md), [FindAppointmentsToClose (IDE 172)](PVE-IDE-172.md) |
| **Appelle** | [GetToken (IDE 151)](PVE-IDE-151.md), [TraceLogBooker (IDE 175)](PVE-IDE-175.md) |

## STATISTIQUES

| Metrique | Valeur |
|----------|--------|
| Taches | 1 |
| Lignes Logic | 35 |
| Expressions | 11 |
| Tables | 0 |

---
*Spec SUMMARY generee par Pipeline V7.2*
