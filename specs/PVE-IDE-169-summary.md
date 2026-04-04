# PVE IDE 169 - AddPaymentToOrder

> **Analyse**: 2026-02-03 18:38
> **Pipeline**: V7.2 Enrichi

## RESUME EXECUTIF

- **Fonction**: AddPaymentToOrder
- **Tables modifiees**: 0
- **Complexite**: **BASSE** (5/100)
- **Statut**: NON_ORPHELIN
- **Raison**: Appele par 4 programme(s): Print Invoice or Ticket (IDE 208), Print Invoice or Ticket-664 (IDE 209), Print Invoice or Ticket (IDE 358), Print Invoice or Ticket==NEW (IDE 429)

## PROGRAMMES LIES

| Direction | Programmes |
|-----------|------------|
| **Appele par** | [Print Invoice or Ticket (IDE 208)](PVE-IDE-208.md), [Print Invoice or Ticket-664 (IDE 209)](PVE-IDE-209.md), [Print Invoice or Ticket (IDE 358)](PVE-IDE-358.md), [Print Invoice or Ticket==NEW (IDE 429)](PVE-IDE-429.md) |
| **Appelle** | [GetToken (IDE 151)](PVE-IDE-151.md), [GetLocationPaymentSettings (IDE 174)](PVE-IDE-174.md), [TraceLogBooker (IDE 175)](PVE-IDE-175.md) |

## STATISTIQUES

| Metrique | Valeur |
|----------|--------|
| Taches | 1 |
| Lignes Logic | 51 |
| Expressions | 13 |
| Tables | 0 |

---
*Spec SUMMARY generee par Pipeline V7.2*
