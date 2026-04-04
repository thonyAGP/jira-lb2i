# PMS-1457 - Caution forfait ski automatique St Moritz

## Contexte Jira

| Element | Valeur |
|---------|--------|
| **Type** | Story (nouvelle fonctionnalite) |
| **Symptome** | Caution forfait ski 25 CHF doit etre creee automatiquement a la cloture nuit |
| **Village** | St Moritz (SMRC) |
| **Service** | Forfait ski |
| **Montant** | 25 CHF |
| **Priorite** | Haute |

## Programmes identifies

| Programme | Role |
|-----------|------|
| REF IDE 667 - AFF_GARANTIE_CLUB | **Modele exact** - Affectation auto de garantie |
| ADH IDE 111 - GARANTIE | Creation/MAJ garantie (17 params) |
| ADH IDE 165 - Saisies cautions | Saisie manuelle cautions |
| EXB IDE 8 - Menu cloture | Orchestrateur cloture nuit |
| PBG IDE 206 - Traitement arrivants | Point d'appel batch nuit |
| PBP IDE 307 - Recherche age Bebe | Utilitaire age bebe/enfant |
| GES IDE 87 - CM Table cautions | Parametrage cautions |

## Tables concernees

| Table | Nom | Usage |
|-------|-----|-------|
| cafil017_dat | depot_garantie | Table cible - creation caution ski |
| cafil011_dat | prestations | Verification exclusion SMRNS1 |
| cafil069_dat | types garantie | Type SKI + montant configurable |
| cafil008_dat | gm-recherche | Boucle sur GM arrivants |
| cafil012_dat | hebergement | Jointure sejour |
| cafil025_dat | compte_gm | MAJ compteur |
| cafil066_dat | historik_station | Trace CGAR |
| motif_no_enreg_na | codes projet | Activation par code projet |

## Regles metier

1. **Declencheur** : Cloture de nuit, jour d'arrivee GM
2. **Montant** : 25 CHF
3. **Exclusions** :
   - Code presta SMRNS1
   - Enfants < 6 ans
   - GM non valides
4. **Activation** : Code projet (table 768)
5. **Doublon** : Verifier garantie ski existante

## Questions ouvertes

- [ ] Code village exact : SMRC ou SMO ?
- [ ] Montant fixe (25) ou configurable (cafil069_dat) ?
- [ ] Retrait automatique de la caution au depart ?
- [ ] Quel code type depot utiliser ? ('SKI' ?)
- [ ] Le programme doit-il aller dans REF ou VIL ?

## Mots-cles

- caution, forfait ski, cloture nuit, batch, automatique
- St Moritz, SMRC, 25 CHF, depot garantie
- SMRNS1, code projet, age bebe
