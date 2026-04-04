# Notes de travail - CMDS-176521

## 2026-01-08

### Observations screenshots

**121313.png** - Le bug en action:
- Ligne selectionnee: Peter Lehmann Riesli
- Prix original: 6,000 (affiche en haut)
- Remise: -10% (affiche en rouge)
- Prix remise: 41,857 (affiche en dessous, FAUX)

**121410.png** - Validation correcte:
- Amount: 5,400
- Ticket Value: 5,400
- Total to pay: 5,400

### Questions

- D'ou vient 41,857 ?
- Est-ce un solde de compte cumule ?
- Est-ce une autre ligne de vente ?

### Pistes

Le nombre 41,857 pourrait etre:
- Le total des ventes du jour/periode
- Le solde du compte BAR CASH JAN 26
- Une erreur de reference de champ dans le DataView

### TODO

- [ ] Chercher "discount" ou "remise" dans PVE
- [ ] Analyser l'ecran POS principal
- [ ] Trouver l'expression du champ prix remise
