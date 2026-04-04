# Analyse CMDS-176481

> **Jira** : [CMDS-176481](https://clubmed.atlassian.net/browse/CMDS-176481)

## Symptome

**Double attribution de Gift Pass lors d'extensions de sejour**

Un GM (NACACH LOPEZ Sergio, membre 21148576) a recu 2 Gift Pass Gold (110 USD chacun) au lieu d'un seul, suite a des extensions de sejour.

## Contexte

| Element | Valeur |
|---------|--------|
| **Village** | Turquoise (Turks & Caicos) |
| **Membre** | 21148576 - NACACH LOPEZ Sergio |
| **Statut** | GOLD |
| **Dossier** | 550019301 |
| **Arrivee initiale** | 27/12/2025 |
| **Depart final** | 12/01/2026 |
| **Reporter** | Reception Turquoise |
| **Assignee** | Kim Dulon |

## Chronologie du sejour

D'apres PB027 et PB0001, le GM a eu **5 periodes distinctes** :

| Periode | Dates | Chambre | Type | Commentaire |
|---------|-------|---------|------|-------------|
| U1 | 27/12 → 03/01 | 2034 | ORDI | Arrivee initiale |
| U1 | 03/01 → 04/01 | 2034 | **VSL** | Extension (Vente Sejour) |
| U1 | 04/01 → 06/01 | 2034 | ORDI | Suite |
| U2 | 06/01 → 12/01 | 2131 | ORDI | Arrivee epouse (chambre upgrade) |

**Observation cle** : La periode 03/01-04/01 a le type "VSL" (Vente Sejour) au lieu de "ORDI".

## Gift Pass - Historique des mouvements

| Date | Heure | Mouvement | Montant | Utilisateur | Description |
|------|-------|-----------|---------|-------------|-------------|
| 27/12/2025 | 10:48 | Credit | +110.00 | AFFAUTO | Gift Pass initial (arrivee) |
| 31/12/2025 | 10:11 | Debit | -110.00 | Spa Manage | SIGNATURE 60M (Spa) |
| **31/12/2025** | **14:44** | **Credit** | **+110.00** | **AFFAUTO** | **BUG: Re-credit apres usage** |
| 31/12/2025 | 14:46 | Debit | -110.00 | Spa Manage | MASSAGES - SWEDISH 60M |
| **03/01/2026** | **10:08** | **Credit** | **+110.00** | **AFFAUTO** | **BUG: Extension sejour (VSL)** |
| 03/01/2026 | 10:08 | Debit | -12.00 | Boutique R | Boutique Sales |
| 03/01/2026 | 10:10 | Credit | +12.00 | AFFAUTO | Re-credit journalier |
| 04/01/2026 | 18:31 | Debit | -12.00 | Boutique R | Boutique Sales |
| 05/01/2026 | 09:54 | Credit | +12.00 | AFFAUTO | Re-credit journalier |
| 05/01/2026 | 09:55 | Debit | -19.00 | Boutique R | Boutique Sales |
| 06/01/2026 | 09:51 | Credit | +19.00 | AFFAUTO | Re-credit journalier |

**Balance finale** : 110.00 USD (apres reset par Kim a 0)

## Diagnostic

### Cause racine identifiee

**Le systeme declenche un nouveau Gift Pass a chaque "evenement d'arrivee"**, incluant :
1. Arrivee initiale (correct)
2. Extension de sejour creant une nouvelle periode (BUG)
3. Arrivee d'un accompagnant (a verifier)

Le 03/01/2026, l'extension de sejour (type VSL) a ete interpretee comme une nouvelle arrivee, declenchant un 2eme Gift Pass.

### Hypotheses sur les montants 12/19 USD

Les credits de 12.00 et 19.00 USD pourraient etre :
1. **Daily Gift Pass** - Certains villages ont un GP journalier au lieu d'un montant fixe
2. **Ajustements automatiques** - Corrections suite a des achats en boutique
3. **Bug supplementaire** - Logique defaillante de credit/debit

### Programme(s) suspect(s)

| Module | Programme | Role |
|--------|-----------|------|
| ADH | ADH IDE 237 | Solde Gift Pass (lecture) |
| ADH | ADH IDE 250 | Solde Resort Credit |
| PBG | ? | Traitement arrivees/extensions |
| ? | ? | Attribution Gift Pass |

## Statut resolution

| Action | Responsable | Statut |
|--------|-------------|--------|
| Reset Gift Pass a 0 | Kim Dulon | FAIT |
| Bug acknowledge | Yohan Frederic | FAIT |
| Fix Mountains + Asia | Dev | DEPLOYE |
| Fix Worldwide | Dev | **PREVU lundi-mardi** |

## Donnees requises pour analyse approfondie

Pour identifier le programme exact qui attribue les Gift Pass :

1. **Base de donnees** : Village VTURKOISE a la date du 03/01/2026
2. **Tables a extraire** :
   - `ccpartyp` (cc_total_par_type) - Credits Gift Pass
   - `operations_dat` - Mouvements compte
   - `planning` ou equivalent - Periodes de sejour
3. **Programmes a analyser** :
   - Programme d'import arrivees PBG
   - Programme d'attribution Gift Pass (a identifier)

## Programmes identifies

### Gift Pass (ADH)

| IDE | Programme | Description | Role |
|-----|-----------|-------------|------|
| ADH IDE 195 | Prg_195 | Choix Articles Gift Pass | Selection articles GP |
| ADH IDE 233 | Prg_233 | Transaction Nouv vente avec GP | Vente avec paiement GP |
| ADH IDE 237 | Prg_237 | Solde Gift Pass | Lecture solde GP |
| ADH IDE 250 | Prg_250 | Solde Resort Credit | Lecture solde RC |

### Traitement arrivees (PBG)

| IDE | Programme | Description | Role |
|-----|-----------|-------------|------|
| PBG IDE 65 | Prg_65 | Traitement des arrivants | **Programme principal arrivees** (115 sous-taches) |
| PBG IDE 56 | Prg_56 | Validation Arrivants | Validation (102 sous-taches) |
| PBG IDE 734 | Prg_734 | AFFECT_CREDIT_BAR | Attribution Credit Bar |
| PBG IDE 783 | Prg_783 | Traitement Resort Credit | Attribution Resort Credit |

### Table cle

| Table | ID | Nom physique | Role |
|-------|-----|--------------|------|
| cc_total_par_type | 268 | ccpartyp | Stockage credits par type (Gift Pass, Resort Credit) |

## Hypothese de bug

Le programme **PBG IDE 65** (Traitement des arrivants) appelle probablement une sous-routine pour attribuer le Gift Pass. Le bug serait dans la condition de declenchement :

```
SI nouvelle_periode ET type_arrivee (VSL inclus)
   ALORS attribuer_gift_pass()
```

Au lieu de :
```
SI premiere_arrivee_sejour ET NOT extension
   ALORS attribuer_gift_pass()
```

## Questions ouvertes

1. Quel est le call exact dans PBG IDE 65 qui attribue le Gift Pass ?
2. Pourquoi le type "VSL" (Vente Sejour) declenche-t-il un nouveau GP ?
3. D'ou viennent les credits de 12/19 USD ?
4. La correction deployee Montagne/Asie corrige-t-elle ce cas precis ?

## Verification Base TUR0801

### Mouvements Gift Pass (table cctypdet, type 99)

| Date | Heure | Montant | Utilisateur | Analyse |
|------|-------|---------|-------------|---------|
| 27/12/2025 | 10:48 | **+110** | AFFAUTO | Credit initial arrivee OK |
| 31/12/2025 | 10:11 | -110 | Spa Manage | Utilise (massage) |
| **31/12/2025** | **14:44** | **+110** | **AFFAUTO** | **BUG: Re-credit apres usage** |
| 31/12/2025 | 14:46 | -110 | Spa Manage | Utilise (massage) |
| **03/01/2026** | **10:08** | **+110** | **AFFAUTO** | **BUG: Extension sejour** |
| 03/01/2026 | 10:08 | -12 | Boutique R | Utilise |
| 03/01/2026 | 10:10 | +12 | AFFAUTO | Re-credit journalier |
| 04/01/2026 | 18:31 | -12 | Boutique R | Utilise |
| 05/01/2026 | 09:54 | +12 | AFFAUTO | Re-credit journalier |
| 05/01/2026 | 09:55 | -19 | Boutique R | Utilise |
| 06/01/2026 | 09:51 | +19 | AFFAUTO | Re-credit journalier |

### Solde actuel (table ccpartyp)

| Type | Filiation | Solde |
|------|-----------|-------|
| 99 (Gift Pass) | 0 | 110 USD |
| 30 | 0,1,2,3 | 0 |

### CONCLUSIONS

**3 BUGS identifies dans le process AFFAUTO :**

1. **Bug Extension** - Le re-credit du 03/01 a 10:08 correspond a l'extension de sejour (type VSL)
2. **Bug Recalcul** - Le re-credit du 31/12 a 14:44 semble etre un recalcul apres usage
3. **Bug Daily** - Les re-credits de 12/19 USD montrent que AFFAUTO recredite chaque jour ce qui a ete utilise

### Process fautif

Le batch **AFFAUTO** (Affectation Automatique) qui s'execute quotidiennement recalcule et recredite le Gift Pass de maniere incorrecte.

**Programme suspect :** PBG IDE 65 - Traitement des arrivants ou batch specifique Gift Pass

### Programme d'appel API identifie

| Programme | Nom Public | Role |
|-----------|------------|------|
| **PBG IDE 808** | CurlAffAuto | Appel API externe pour affectation automatique |

**Structure PBG IDE 808** :
- Tache 808.1 : Programme principal (4 sous-taches)
- Tache 808.2 : Lecture parametres (AFFAUTOWSURL, AFFAUTOAPIKEY, AFFAUTOMETHOD)
- Tache 808.3 : Write curl (construction commande)
- Tache 808.4 : XML check (verification reponse)

**Parametres API lus depuis table obj=1065** :
- `AFFAUTOWSURL` : URL de l'API
- `AFFAUTOAPIKEY` : Cle API
- `AFFAUTOMETHOD` : Methode HTTP

**Conclusion** : Le bug d'attribution Gift Pass est probablement dans :
1. L'API externe appelee (logique de declenchement)
2. Le programme appelant PBG IDE 808 (condition de declenchement)
3. La logique de detection "nouvelle arrivee vs extension"

---

*Analyse completee: 2026-01-09*
*Base verifiee: TUR0801*
*Pieces jointes: 7 screenshots dans attachments/*

---

*DerniÃ¨re mise Ã  jour : 2026-01-22T18:55*
