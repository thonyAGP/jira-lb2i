# ADH IDE 71 - Print extrait compte /Date

> **Analyse**: 2026-02-08 02:08
> **Pipeline**: V7.2 Enrichi

## RESUME EXECUTIF

- **Fonction**: Print extrait compte /Date
- **Tables modifiees**: 1
- **Complexite**: **BASSE** (25/100)
- **Statut**: NON_ORPHELIN
- **Raison**: Appele par 4 programme(s): Extrait de compte (IDE 69), Extrait Easy Check Out à J+1 (IDE 53), Solde Easy Check Out (IDE 64), Solde Easy Check Out (IDE 287)

## PROGRAMMES LIES

| Direction | Programmes |
|-----------|------------|
| **Appele par** | [Extrait de compte (IDE 69)](ADH-IDE-69.md), [Extrait Easy Check Out à J+1 (IDE 53)](ADH-IDE-53.md), [Solde Easy Check Out (IDE 64)](ADH-IDE-64.md), [Solde Easy Check Out (IDE 287)](ADH-IDE-287.md) |
| **Appelle** | [Creation Pied Facture (IDE 75)](ADH-IDE-75.md), [Recupere devise local (IDE 21)](ADH-IDE-21.md), [Get Printer (IDE 179)](ADH-IDE-179.md), [Set Listing Number (IDE 181)](ADH-IDE-181.md), [Raz Current Printer (IDE 182)](ADH-IDE-182.md) |

## STATISTIQUES

| Metrique | Valeur |
|----------|--------|
| Taches | 24 |
| Lignes Logic | 780 |
| Expressions | 16 |
| Tables | 8 |

---
*Spec SUMMARY generee par Pipeline V7.2*
