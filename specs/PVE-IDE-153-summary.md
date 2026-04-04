# PVE IDE 153 - SearchBooking

> **Analyse**: 2026-02-03 09:47
> **Pipeline**: V7.2 Enrichi

## RESUME EXECUTIF

- **Fonction**: SearchBooking
- **Tables modifiees**: 1
- **Complexite**: **BASSE** (24/100)
- **Statut**: NON_ORPHELIN
- **Raison**: Appele par 8 programme(s): Main Sale (IDE 186), Main Sale-664 (IDE 187), Select Product (IDE 192), Main Sale Sale Bar Code (IDE 214), Main Sale (IDE 363), Main Sale-664 (IDE 364), Main Sale ===V4 Booking ACTUEL (IDE 417), Main Sale (IDE 440)

## PROGRAMMES LIES

| Direction | Programmes |
|-----------|------------|
| **Appele par** | [Main Sale (IDE 186)](PVE-IDE-186.md), [Main Sale-664 (IDE 187)](PVE-IDE-187.md), [Select Product (IDE 192)](PVE-IDE-192.md), [Main Sale Sale Bar Code (IDE 214)](PVE-IDE-214.md), [Main Sale (IDE 363)](PVE-IDE-363.md), [Main Sale-664 (IDE 364)](PVE-IDE-364.md), [Main Sale ===V4 Booking ACTUEL (IDE 417)](PVE-IDE-417.md), [Main Sale (IDE 440)](PVE-IDE-440.md) |
| **Appelle** | [FindAvailability (IDE 173)](PVE-IDE-173.md), [CreateAppointment (IDE 160)](PVE-IDE-160.md), [UpdateAppointment (IDE 167)](PVE-IDE-167.md), [Choix - Cabine (IDE 340)](PVE-IDE-340.md), [Choix - Praticien (IDE 341)](PVE-IDE-341.md), [GetTreatment (IDE 156)](PVE-IDE-156.md), [FindRooms (IDE 157)](PVE-IDE-157.md), [FindEmployees (IDE 158)](PVE-IDE-158.md), [GetAppointment (IDE 161)](PVE-IDE-161.md), [ControleBookingId (IDE 165)](PVE-IDE-165.md) |

## STATISTIQUES

| Metrique | Valeur |
|----------|--------|
| Taches | 9 |
| Lignes Logic | 313 |
| Expressions | 39 |
| Tables | 9 |

---
*Spec SUMMARY generee par Pipeline V7.2*
