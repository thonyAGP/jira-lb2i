# VIL IDE 90 - Saisie contenu caisse

> **Analyse**: 2026-02-03 09:17
> **Pipeline**: V7.2 Enrichi

## RESUME EXECUTIF

- **Fonction**: Saisie contenu caisse
- **Tables modifiees**: 3
- **Complexite**: **BASSE** (32/100)
- **Statut**: NON_ORPHELIN
- **Raison**: Appele par 3 programme(s): Menu gestion caisse (IDE 86), Sortie de devises (IDE 161), Menu pièces de caisse (IDE 100)

## PROGRAMMES LIES

| Direction | Programmes |
|-----------|------------|
| **Appele par** | [Menu gestion caisse (IDE 86)](VIL-IDE-86.md), [Sortie de devises (IDE 161)](VIL-IDE-161.md), [Menu pièces de caisse (IDE 100)](VIL-IDE-100.md) |
| **Appelle** | [Recuperation du titre (IDE 41)](VIL-IDE-41.md), [Mise a jour comptage caisse (IDE 92)](VIL-IDE-92.md), [Print comptage (IDE 104)](VIL-IDE-104.md) |

## STATISTIQUES

| Metrique | Valeur |
|----------|--------|
| Taches | 75 |
| Lignes Logic | 906 |
| Expressions | 11 |
| Tables | 20 |

---
*Spec SUMMARY generee par Pipeline V7.2*
