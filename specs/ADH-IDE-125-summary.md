# ADH IDE 125 - Remise en caisse

> **Analyse**: 2026-02-08 03:05
> **Pipeline**: V7.2 Enrichi

## RESUME EXECUTIF

- **Fonction**: Remise en caisse
- **Tables modifiees**: 5
- **Complexite**: **BASSE** (38/100)
- **Statut**: NON_ORPHELIN
- **Raison**: Appele par 4 programme(s): Gestion caisse (IDE 121), Fermeture caisse (IDE 131), Gestion caisse 142 (IDE 298), Fermeture caisse 144 (IDE 299)

## PROGRAMMES LIES

| Direction | Programmes |
|-----------|------------|
| **Appele par** | [Gestion caisse (IDE 121)](ADH-IDE-121.md), [Fermeture caisse (IDE 131)](ADH-IDE-131.md), [Gestion caisse 142 (IDE 298)](ADH-IDE-298.md), [Fermeture caisse 144 (IDE 299)](ADH-IDE-299.md) |
| **Appelle** | [Recuperation du titre (IDE 43)](ADH-IDE-43.md), [Devise update session WS (IDE 142)](ADH-IDE-142.md), [Calcul stock produit WS (IDE 149)](ADH-IDE-149.md) |

## STATISTIQUES

| Metrique | Valeur |
|----------|--------|
| Taches | 33 |
| Lignes Logic | 512 |
| Expressions | 2 |
| Tables | 9 |

---
*Spec SUMMARY generee par Pipeline V7.2*
