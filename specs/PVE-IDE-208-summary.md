# PVE IDE 208 - Print Invoice or Ticket

> **Analyse**: 2026-02-03 18:54
> **Pipeline**: V7.2 Enrichi

## RESUME EXECUTIF

- **Fonction**: Print Invoice or Ticket
- **Tables modifiees**: 12
- **Complexite**: **MOYENNE** (55/100)
- **Statut**: NON_ORPHELIN
- **Raison**: Appele par 10 programme(s): Generate Preview Payments (IDE 189), Choice Re_Print Invoice (IDE 204), Generate Preview OD==LEX Book (IDE 418), Generate Preview OD==V4 (IDE 423), Generate Preview OD==LEX (IDE 424), Generate Preview Payments 1212 (IDE 434), Generate Preview Payments 1112 (IDE 435), Generate Preview Payments 1012 (IDE 436), Generate Preview Payment 1212E (IDE 437), Generate Preview Payments (IDE 441)

## PROGRAMMES LIES

| Direction | Programmes |
|-----------|------------|
| **Appele par** | [Generate Preview Payments (IDE 189)](PVE-IDE-189.md), [Choice Re_Print Invoice (IDE 204)](PVE-IDE-204.md), [Generate Preview OD==LEX Book (IDE 418)](PVE-IDE-418.md), [Generate Preview OD==V4 (IDE 423)](PVE-IDE-423.md), [Generate Preview OD==LEX (IDE 424)](PVE-IDE-424.md), [Generate Preview Payments 1212 (IDE 434)](PVE-IDE-434.md), [Generate Preview Payments 1112 (IDE 435)](PVE-IDE-435.md), [Generate Preview Payments 1012 (IDE 436)](PVE-IDE-436.md), [Generate Preview Payment 1212E (IDE 437)](PVE-IDE-437.md), [Generate Preview Payments (IDE 441)](PVE-IDE-441.md) |
| **Appelle** | [TraceLogBooker (IDE 175)](PVE-IDE-175.md), [CancelAppointment (IDE 159)](PVE-IDE-159.md), [AddPaymentToOrder (IDE 169)](PVE-IDE-169.md), [GetLocationPaymentSettings (IDE 174)](PVE-IDE-174.md), [Creation pied Ticket(Tva) (IDE 281)](PVE-IDE-281.md), [AddSpecialToOrder-392 (IDE 170)](PVE-IDE-170.md), [Edition ticket (Tva) LEX (IDE 205)](PVE-IDE-205.md), [Edition ticket (Tva) (IDE 206)](PVE-IDE-206.md), [Set Village Address (IDE 277)](PVE-IDE-277.md), [Set Customer (IDE 278)](PVE-IDE-278.md), [Search  for messages (IDE 279)](PVE-IDE-279.md), [SynchronisationRecuPDF (IDE 320)](PVE-IDE-320.md), [Browse - pv_comptab (IDE 446)](PVE-IDE-446.md), [Browse - pv_cust_package (IDE 447)](PVE-IDE-447.md), [Browse - pv_comptab_temp (IDE 448)](PVE-IDE-448.md) |

## STATISTIQUES

| Metrique | Valeur |
|----------|--------|
| Taches | 47 |
| Lignes Logic | 1694 |
| Expressions | 40 |
| Tables | 30 |

---
*Spec SUMMARY generee par Pipeline V7.2*
