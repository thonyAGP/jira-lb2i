# PUG IDE 18 - Purge Batch

> **Analyse**: 2026-02-03 18:32
> **Pipeline**: V7.2 Enrichi

## RESUME EXECUTIF

- **Fonction**: Purge Batch
- **Tables modifiees**: 69
- **Complexite**: **MOYENNE** (50/100)
- **Statut**: NON_ORPHELIN
- **Raison**: Appele par 3 programme(s): Lancement Purge (IDE 17), test purge (IDE 19), Lancement UNITAIRE de la Purge (IDE 22)

## PROGRAMMES LIES

| Direction | Programmes |
|-----------|------------|
| **Appele par** | [Lancement Purge (IDE 17)](PUG-IDE-17.md), [test purge (IDE 19)](PUG-IDE-19.md), [Lancement UNITAIRE de la Purge (IDE 22)](PUG-IDE-22.md) |
| **Appelle** | [Purge SQL par adherent (IDE 16)](PUG-IDE-16.md), [Vidage table SQL (IDE 20)](PUG-IDE-20.md), [update version caisse (IDE 9)](PUG-IDE-9.md), [Generation presents (IDE 10)](PUG-IDE-10.md), [Generation presents temp (IDE 11)](PUG-IDE-11.md), [   Delete GMR adh=0 (IDE 12)](PUG-IDE-12.md), [   Delete GMR cpte=0 (IDE 13)](PUG-IDE-13.md), [   Purge Point de vente (IDE 14)](PUG-IDE-14.md), [   Recherche Due (IDE 15)](PUG-IDE-15.md) |

## STATISTIQUES

| Metrique | Valeur |
|----------|--------|
| Taches | 117 |
| Lignes Logic | 2066 |
| Expressions | 22 |
| Tables | 86 |

---
*Spec SUMMARY generee par Pipeline V7.2*
