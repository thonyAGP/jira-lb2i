# ADH IDE 138 - Ticket fermeture session

> **Analyse**: 2026-02-08 03:18
> **Pipeline**: V7.2 Enrichi

## RESUME EXECUTIF

- **Fonction**: Ticket fermeture session
- **Tables modifiees**: 0
- **Complexite**: **BASSE** (18/100)
- **Statut**: NON_ORPHELIN
- **Raison**: Appele par 3 programme(s): Fermeture caisse (IDE 131), Reimpression tickets fermeture (IDE 151), Fermeture caisse 144 (IDE 299)

## PROGRAMMES LIES

| Direction | Programmes |
|-----------|------------|
| **Appele par** | [Fermeture caisse (IDE 131)](ADH-IDE-131.md), [Reimpression tickets fermeture (IDE 151)](ADH-IDE-151.md), [Fermeture caisse 144 (IDE 299)](ADH-IDE-299.md) |
| **Appelle** | [Recuperation du titre (IDE 43)](ADH-IDE-43.md), [Get Printer (IDE 179)](ADH-IDE-179.md), [Set Listing Number (IDE 181)](ADH-IDE-181.md), [Raz Current Printer (IDE 182)](ADH-IDE-182.md) |

## STATISTIQUES

| Metrique | Valeur |
|----------|--------|
| Taches | 23 |
| Lignes Logic | 378 |
| Expressions | 10 |
| Tables | 8 |

---
*Spec SUMMARY generee par Pipeline V7.2*
