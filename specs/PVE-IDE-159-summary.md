# PVE IDE 159 - CancelAppointment

> **Analyse**: 2026-02-03 09:50
> **Pipeline**: V7.2 Enrichi

## RESUME EXECUTIF

- **Fonction**: CancelAppointment
- **Tables modifiees**: 0
- **Complexite**: **BASSE** (5/100)
- **Statut**: NON_ORPHELIN
- **Raison**: Appele par 5 programme(s): Print Invoice or Ticket (IDE 208), Print Invoice or Ticket-664 (IDE 209), Print Invoice or Ticket (IDE 358), Print Invoice or Ticket==NEW (IDE 429), Delete Product (IDE 194)

## PROGRAMMES LIES

| Direction | Programmes |
|-----------|------------|
| **Appele par** | [Print Invoice or Ticket (IDE 208)](PVE-IDE-208.md), [Print Invoice or Ticket-664 (IDE 209)](PVE-IDE-209.md), [Print Invoice or Ticket (IDE 358)](PVE-IDE-358.md), [Print Invoice or Ticket==NEW (IDE 429)](PVE-IDE-429.md), [Delete Product (IDE 194)](PVE-IDE-194.md) |
| **Appelle** | [GetToken (IDE 151)](PVE-IDE-151.md), [TraceLogBooker (IDE 175)](PVE-IDE-175.md) |

## STATISTIQUES

| Metrique | Valeur |
|----------|--------|
| Taches | 1 |
| Lignes Logic | 35 |
| Expressions | 10 |
| Tables | 0 |

---
*Spec SUMMARY generee par Pipeline V7.2*
