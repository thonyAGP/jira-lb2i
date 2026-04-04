# ADH IDE 120 - Saisie contenu caisse

> **Analyse**: 2026-02-08 03:01
> **Pipeline**: V7.2 Enrichi

## RESUME EXECUTIF

- **Fonction**: Saisie contenu caisse
- **Tables modifiees**: 5
- **Complexite**: **BASSE** (38/100)
- **Statut**: NON_ORPHELIN
- **Raison**: Appele par 4 programme(s): Ouverture caisse (IDE 122), Fermeture caisse (IDE 131), Ouverture caisse 143 (IDE 297), Fermeture caisse 144 (IDE 299)

## PROGRAMMES LIES

| Direction | Programmes |
|-----------|------------|
| **Appele par** | [Ouverture caisse (IDE 122)](ADH-IDE-122.md), [Fermeture caisse (IDE 131)](ADH-IDE-131.md), [Ouverture caisse 143 (IDE 297)](ADH-IDE-297.md), [Fermeture caisse 144 (IDE 299)](ADH-IDE-299.md) |
| **Appelle** | [Recuperation du titre (IDE 43)](ADH-IDE-43.md), [Devise update session WS (IDE 142)](ADH-IDE-142.md), [Mise a jour comptage caisse WS (IDE 133)](ADH-IDE-133.md), [Print comptage WS (IDE 150)](ADH-IDE-150.md) |

## STATISTIQUES

| Metrique | Valeur |
|----------|--------|
| Taches | 105 |
| Lignes Logic | 1378 |
| Expressions | 11 |
| Tables | 27 |

---
*Spec SUMMARY generee par Pipeline V7.2*
