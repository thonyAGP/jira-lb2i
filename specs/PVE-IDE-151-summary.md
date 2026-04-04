# PVE IDE 151 - GetToken

> **Analyse**: 2026-02-03 09:45
> **Pipeline**: V7.2 Enrichi

## RESUME EXECUTIF

- **Fonction**: GetToken
- **Tables modifiees**: 1
- **Complexite**: **BASSE** (12/100)
- **Statut**: NON_ORPHELIN
- **Raison**: Appele par 20 programme(s): General settings (IDE 12), FindAppointmentsAbsentPOS (IDE 152), FindTreatments (IDE 154), GetCustomerAppointments (IDE 155), GetTreatment (IDE 156), FindRooms (IDE 157), FindEmployees (IDE 158), CancelAppointment (IDE 159), CreateAppointment (IDE 160), GetAppointment (IDE 161), TakeDeposit (IDE 162), CloseOrder (IDE 163), CloseOrder-392 (IDE 164), UpdateAppointment (IDE 167), AddPaymentToOrder (IDE 169), AddSpecialToOrder-392 (IDE 170), FindAppointmentsToClose (IDE 172), FindAvailability (IDE 173), GetLocationPaymentSettings (IDE 174), FindAppointments (IDE 176)

## PROGRAMMES LIES

| Direction | Programmes |
|-----------|------------|
| **Appele par** | [General settings (IDE 12)](PVE-IDE-12.md), [FindAppointmentsAbsentPOS (IDE 152)](PVE-IDE-152.md), [FindTreatments (IDE 154)](PVE-IDE-154.md), [GetCustomerAppointments (IDE 155)](PVE-IDE-155.md), [GetTreatment (IDE 156)](PVE-IDE-156.md), [FindRooms (IDE 157)](PVE-IDE-157.md), [FindEmployees (IDE 158)](PVE-IDE-158.md), [CancelAppointment (IDE 159)](PVE-IDE-159.md), [CreateAppointment (IDE 160)](PVE-IDE-160.md), [GetAppointment (IDE 161)](PVE-IDE-161.md), [TakeDeposit (IDE 162)](PVE-IDE-162.md), [CloseOrder (IDE 163)](PVE-IDE-163.md), [CloseOrder-392 (IDE 164)](PVE-IDE-164.md), [UpdateAppointment (IDE 167)](PVE-IDE-167.md), [AddPaymentToOrder (IDE 169)](PVE-IDE-169.md), [AddSpecialToOrder-392 (IDE 170)](PVE-IDE-170.md), [FindAppointmentsToClose (IDE 172)](PVE-IDE-172.md), [FindAvailability (IDE 173)](PVE-IDE-173.md), [GetLocationPaymentSettings (IDE 174)](PVE-IDE-174.md), [FindAppointments (IDE 176)](PVE-IDE-176.md) |
| **Appelle** | [TraceLogBooker (IDE 175)](PVE-IDE-175.md) |

## STATISTIQUES

| Metrique | Valeur |
|----------|--------|
| Taches | 2 |
| Lignes Logic | 51 |
| Expressions | 13 |
| Tables |  |

---
*Spec SUMMARY generee par Pipeline V7.2*
