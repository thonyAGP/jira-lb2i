# PVE IDE 46 - Get Temp Files

> **Analyse**: 2026-02-03 08:55
> **Pipeline**: V7.2 Enrichi

## RESUME EXECUTIF

- **Fonction**: Get Temp Files
- **Tables modifiees**: 0
- **Complexite**: **BASSE** (10/100)
- **Statut**: NON_ORPHELIN
- **Raison**: Appele par 20 programme(s): Report - Cost by Day (IDE 21), Report - Cost by Category (IDE 22), Report - Cost by Product (IDE 23), Report - Cost by Seller (IDE 24), Report - Cost by Place (IDE 25), Report - Margin by Seller (IDE 26), Best Of (SALE) (IDE 28), Print BestOf (select) (IDE 32), Report - Margin by Product (IDE 37), Report - Net Margin by Product (IDE 38), Report - Net Margin by Product (IDE 39), Report - Margin by Product (IDE 40), Report - Margin by Day (IDE 41), Report - Margin by Category (IDE 42), Report - Margin by Place (IDE 43), Print/Export Stat Ventes (IDE 63), Print Deposit (IDE 64), Export Insurance (IDE 65), Print Local & Prepaid Rentals (IDE 66), Edition UPGRADE (IDE 72)

## PROGRAMMES LIES

| Direction | Programmes |
|-----------|------------|
| **Appele par** | [Report - Cost by Day (IDE 21)](PVE-IDE-21.md), [Report - Cost by Category (IDE 22)](PVE-IDE-22.md), [Report - Cost by Product (IDE 23)](PVE-IDE-23.md), [Report - Cost by Seller (IDE 24)](PVE-IDE-24.md), [Report - Cost by Place (IDE 25)](PVE-IDE-25.md), [Report - Margin by Seller (IDE 26)](PVE-IDE-26.md), [Best Of (SALE) (IDE 28)](PVE-IDE-28.md), [Print BestOf (select) (IDE 32)](PVE-IDE-32.md), [Report - Margin by Product (IDE 37)](PVE-IDE-37.md), [Report - Net Margin by Product (IDE 38)](PVE-IDE-38.md), [Report - Net Margin by Product (IDE 39)](PVE-IDE-39.md), [Report - Margin by Product (IDE 40)](PVE-IDE-40.md), [Report - Margin by Day (IDE 41)](PVE-IDE-41.md), [Report - Margin by Category (IDE 42)](PVE-IDE-42.md), [Report - Margin by Place (IDE 43)](PVE-IDE-43.md), [Print/Export Stat Ventes (IDE 63)](PVE-IDE-63.md), [Print Deposit (IDE 64)](PVE-IDE-64.md), [Export Insurance (IDE 65)](PVE-IDE-65.md), [Print Local & Prepaid Rentals (IDE 66)](PVE-IDE-66.md), [Edition UPGRADE (IDE 72)](PVE-IDE-72.md) |
| **Appelle** | [Create TempDb_Customer PMS (IDE 47)](PVE-IDE-47.md), [Create TempDbRentals PMS (IDE 48)](PVE-IDE-48.md), [Create TemdbPackage PMS (IDE 49)](PVE-IDE-49.md), [Create TempAccounting PMS (IDE 50)](PVE-IDE-50.md), [Modify Accounting (IDE 51)](PVE-IDE-51.md), [Insert TempDb_Customer ARCH (IDE 52)](PVE-IDE-52.md), [Create TempDbRentals ARCH (IDE 53)](PVE-IDE-53.md), [Create TemdbPackage ARCH (IDE 54)](PVE-IDE-54.md), [Create TempAccounting ARCH (IDE 55)](PVE-IDE-55.md), [Liste services=>tempo_userlist (IDE 81)](PVE-IDE-81.md) |

## STATISTIQUES

| Metrique | Valeur |
|----------|--------|
| Taches | 5 |
| Lignes Logic | 124 |
| Expressions | 14 |
| Tables | 3 |

---
*Spec SUMMARY generee par Pipeline V7.2*
