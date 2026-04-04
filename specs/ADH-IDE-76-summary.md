# ADH IDE 76 - Print extrait compte /Service

> **Analyse**: 2026-02-08 02:11
> **Pipeline**: V7.2 Enrichi

## RESUME EXECUTIF

- **Fonction**: Print extrait compte /Service
- **Tables modifiees**: 1
- **Complexite**: **BASSE** (25/100)
- **Statut**: NON_ORPHELIN
- **Raison**: Appele par 2 programme(s): Extrait Easy Check Out à J+1 (IDE 53), Extrait de compte (IDE 69)

## PROGRAMMES LIES

| Direction | Programmes |
|-----------|------------|
| **Appele par** | [Extrait Easy Check Out à J+1 (IDE 53)](ADH-IDE-53.md), [Extrait de compte (IDE 69)](ADH-IDE-69.md) |
| **Appelle** | [Creation Pied Facture (IDE 75)](ADH-IDE-75.md), [Recupere devise local (IDE 21)](ADH-IDE-21.md), [Get Printer (IDE 179)](ADH-IDE-179.md), [Set Listing Number (IDE 181)](ADH-IDE-181.md), [Raz Current Printer (IDE 182)](ADH-IDE-182.md) |

## STATISTIQUES

| Metrique | Valeur |
|----------|--------|
| Taches | 17 |
| Lignes Logic | 626 |
| Expressions | 13 |
| Tables | 9 |

---
*Spec SUMMARY generee par Pipeline V7.2*
