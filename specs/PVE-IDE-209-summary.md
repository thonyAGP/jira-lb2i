# PVE IDE 209 - Print Invoice or Ticket-664

> **Analyse**: 2026-02-03 18:55
> **Pipeline**: V7.2 Enrichi

## RESUME EXECUTIF

- **Fonction**: Print Invoice or Ticket-664
- **Tables modifiees**: 14
- **Complexite**: **MOYENNE** (55/100)
- **Statut**: NON_ORPHELIN
- **Raison**: Appele par 6 programme(s): Generate Preview Payments (IDE 189), Choice Re_Print Invoice (IDE 204), Generate Preview Payments 1212 (IDE 434), Generate Preview Payments 1112 (IDE 435), Generate Preview Payments 1012 (IDE 436), Generate Preview Payment 1212E (IDE 437)

## PROGRAMMES LIES

| Direction | Programmes |
|-----------|------------|
| **Appele par** | [Generate Preview Payments (IDE 189)](PVE-IDE-189.md), [Choice Re_Print Invoice (IDE 204)](PVE-IDE-204.md), [Generate Preview Payments 1212 (IDE 434)](PVE-IDE-434.md), [Generate Preview Payments 1112 (IDE 435)](PVE-IDE-435.md), [Generate Preview Payments 1012 (IDE 436)](PVE-IDE-436.md), [Generate Preview Payment 1212E (IDE 437)](PVE-IDE-437.md) |
| **Appelle** | [TraceLogBooker (IDE 175)](PVE-IDE-175.md), [CancelAppointment (IDE 159)](PVE-IDE-159.md), [AddPaymentToOrder (IDE 169)](PVE-IDE-169.md), [GetLocationPaymentSettings (IDE 174)](PVE-IDE-174.md), [Creation pied Ticket(Tva) (IDE 281)](PVE-IDE-281.md), [Print label code barre DIN (IDE 113)](PVE-IDE-113.md), [AddSpecialToOrder-392 (IDE 170)](PVE-IDE-170.md), [Edition ticket (Tva) LEX (IDE 205)](PVE-IDE-205.md), [Edition ticket (Tva) (IDE 206)](PVE-IDE-206.md), [Set Village Address (IDE 277)](PVE-IDE-277.md), [Set Customer (IDE 278)](PVE-IDE-278.md), [Search  for messages (IDE 279)](PVE-IDE-279.md), [SynchronisationRecuPDF (IDE 320)](PVE-IDE-320.md) |

## STATISTIQUES

| Metrique | Valeur |
|----------|--------|
| Taches | 51 |
| Lignes Logic | 1686 |
| Expressions | 40 |
| Tables | 32 |

---
*Spec SUMMARY generee par Pipeline V7.2*
