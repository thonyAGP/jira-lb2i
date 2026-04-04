# PVE IDE 206 - Edition ticket (Tva)

> **Analyse**: 2026-02-03 18:54
> **Pipeline**: V7.2 Enrichi

## RESUME EXECUTIF

- **Fonction**: Edition ticket (Tva)
- **Tables modifiees**: 0
- **Complexite**: **BASSE** (30/100)
- **Statut**: NON_ORPHELIN
- **Raison**: Appele par 4 programme(s): Choice Re_Print Invoice (IDE 204), Print Invoice or Ticket (IDE 208), Print Invoice or Ticket-664 (IDE 209), Print Invoice or Ticket (IDE 358)

## PROGRAMMES LIES

| Direction | Programmes |
|-----------|------------|
| **Appele par** | [Choice Re_Print Invoice (IDE 204)](PVE-IDE-204.md), [Print Invoice or Ticket (IDE 208)](PVE-IDE-208.md), [Print Invoice or Ticket-664 (IDE 209)](PVE-IDE-209.md), [Print Invoice or Ticket (IDE 358)](PVE-IDE-358.md) |
| **Appelle** | [Creation pied Ticket(Tva) (IDE 281)](PVE-IDE-281.md), [GetAppointment (IDE 161)](PVE-IDE-161.md), [Concatène libellé Cat/Ss-Cat (IDE 321)](PVE-IDE-321.md), [Set Listing Number (IDE 274)](PVE-IDE-274.md), [Raz Current Printer (IDE 275)](PVE-IDE-275.md), [Get Printer (IDE 276)](PVE-IDE-276.md), [Search  for messages (IDE 279)](PVE-IDE-279.md), [GetPrinter/t impression (IDE 283)](PVE-IDE-283.md) |

## STATISTIQUES

| Metrique | Valeur |
|----------|--------|
| Taches | 36 |
| Lignes Logic | 1537 |
| Expressions | 40 |
| Tables | 13 |

---
*Spec SUMMARY generee par Pipeline V7.2*
