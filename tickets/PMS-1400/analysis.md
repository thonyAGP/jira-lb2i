# PMS-1400 - POS REPORTS: Evolution report REVENUE CANCELATIONS

> **Jira** : [PMS-1400](https://clubmed.atlassian.net/browse/PMS-1400)

## Contexte

| Element | Valeur |
|---------|--------|
| **Status Jira** | Pret |
| **Priorite** | Moderee |
| **Label** | (aucun) |
| **Reporter** | Davide Morandi |
| **Assignee** | Anthony Leberre |
| **Date creation** | 06/11/2025 |

## Demande

Modifier l'edition **REVENUE CANCELATION** pour ameliorer la visibilite des annulations :

1. **Faire apparaitre le montant GIFT PASS rembourse** (ligne existe mais sans montant)
2. **Ajouter une colonne "Payment Type"** pour comprendre la nature du remboursement :
   - CLUB MED PASS
   - CREDIT CARD
   - GIFT PASS
3. **Ajouter des lignes de TOTAL**

---

## Analyse Technique

### Programme principal

| Projet | IDE | Nom | Role | Fichier XML |
|--------|-----|-----|------|-------------|
| **PVE** | **75** | Report - Revenue Cancelations | Edition des annulations de revenus | Prg_75.xml |

> **Note** : Ce programme est appele depuis **PVE IDE 176** (Menu Reports) via le bouton "Revenue cancelations".

### Structure actuelle du rapport

#### Parametres d'entree (7 parametres)

| # | Nom | Type | Description |
|---|-----|------|-------------|
| 1 | P. Village name | Alpha 128 | Nom du village |
| 2 | P. Currency | Alpha 3 | Devise |
| 3 | P. Amount format | Alpha 20 | Format montant |
| 4 | P. Amount format sans Z | Alpha 20 | Format sans zero |
| 5 | P. Decimales | Numeric 1 | Nombre decimales |
| 6 | P Date mini | Date | Date debut |
| 7 | P Date maxi | Date | Date fin |

#### Tables utilisees

| N° Table | Nom Logique | Nom Physique | Role |
|----------|-------------|--------------|------|
| **30** | gm-recherche | cafil008_dat | Recherche GM |
| **1468** | pv_customer | ##_pv_customer_dat | Donnees client |
| **1471** | pv_package | ##_pv_package_dat | Donnees package |
| **523** | synthese_garanties | %club_user%_syn_garantie | Synthese garanties |

#### Sous-taches existantes

| Tache | ISN | Nom | Role |
|-------|-----|-----|------|
| 75.1 | 2 | Selection | Selection dates |
| 75.2 | 3 | Main | Traitement principal |
| 75.3 | 4 | Print subtask | Generation rapport |
| 75.4 | 5 | CSV Export | Export CSV |

#### Variables existantes dans 75.2 (Main)

| Variable | Type | Nom | Role |
|----------|------|-----|------|
| A | Numeric | v.montant taxes | Montant taxes |
| B | Logical | v.taxes multiples | Flag taxes multiples |
| ... | ... | ... | ... |

#### Fichier CSV genere

```
%club_exportdata%{VILLAGECODE}{SERVICE}_revenuecancelation_{DATEDEB}_{DATEFIN}.csv
```

---

## Problemes identifies

### Probleme 1 : Montant GIFT PASS vide

**Symptome** : La ligne GIFT PASS existe mais le montant est toujours vide.

**Cause probable** :
- Le champ n'est pas mappe a la bonne colonne de la table source
- Ou la jointure avec la table Gift Pass n'est pas faite

**Investigation** :
- Verifier l'expression qui calcule le montant GIFT PASS
- Verifier la table source des remboursements Gift Pass

### Probleme 2 : Colonne Payment Type manquante

**Symptome** : Pas de colonne indiquant le type de paiement utilise pour le remboursement.

**Cause** : La colonne n'existe pas dans le rapport actuel.

### Probleme 3 : Pas de totaux

**Symptome** : Pas de lignes de total en fin de rapport.

**Cause** : Les expressions de totalisation ne sont pas definies.

---

## Solution proposee

### Modification 1 : Corriger montant GIFT PASS

#### Localisation

- **Programme** : PVE IDE 75 - Report - Revenue Cancelations
- **Sous-tache** : Tache 75.2 (Main) ou 75.3 (Print)
- **Fichier** : `D:\Data\Migration\XPA\PMS\PVE\Source\Prg_75.xml`

#### Action

1. Identifier la variable qui stocke le montant GIFT PASS
2. Verifier l'expression de calcul
3. S'assurer que la table source contient bien le montant

**Table a verifier** : Probablement une jointure vers la table `gift_pass` ou `ccventes` (ventes Gift Pass).

### Modification 2 : Ajouter colonne Payment Type

#### Variables a ajouter

| Variable | Type | Nom | Expression |
|----------|------|-----|------------|
| **v.PaymentType** | Alpha 20 | v.Payment Type | Voir expression ci-dessous |

#### Expression proposee

```magic
IF {champ_moyen_paiement} = 'CMP'
  'CLUB MED PASS'
ELSE IF {champ_moyen_paiement} = 'CB' OR {champ_moyen_paiement} = 'CC'
  'CREDIT CARD'
ELSE IF {champ_moyen_paiement} = 'GP'
  'GIFT PASS'
ELSE
  {champ_moyen_paiement}
```

> **Note** : Les codes exacts des moyens de paiement sont a verifier dans la table REF des moyens de reglement.

#### Modification formulaire

1. Ouvrir le formulaire d'edition (Form) de la tache 75.3
2. Ajouter une colonne "Payment Type" entre les colonnes existantes
3. Lier a la variable `v.PaymentType`

### Modification 3 : Ajouter lignes de TOTAL

#### Variables de totalisation a ajouter

| Variable | Type | Nom | Expression |
|----------|------|-----|------------|
| **v.Total montant** | Numeric | V.Total montant | Somme des montants |
| **v.Total HT** | Numeric | V.Montant Total HT | Somme HT |
| **v.Total TVA** | Numeric | V.Montant Total Tva | Somme TVA |

> **Note** : Ces variables existent deja partiellement (lignes 3106-3128 du XML).

#### Logique de totalisation

Dans le **Task Suffix** de la tache 75.2 ou 75.3 :

```
Ligne X : Update v.Total montant = v.Total montant + {montant_ligne}
```

Dans le **Group Suffix** (fin de groupe) :

```
Ligne Y : Output → Afficher ligne TOTAL avec v.Total montant, v.Total HT, v.Total TVA
```

---

## Implementation pas a pas (IDE Magic)

### Etape 1 : Analyser la structure existante

1. Ouvrir **PVE IDE 75** dans l'IDE Magic
2. Aller dans **Data View** (F4)
3. Identifier toutes les variables existantes
4. Noter les tables liees (Browse)

### Etape 2 : Identifier la source du montant GIFT PASS

1. Dans la tache 75.2 ou 75.3, chercher les variables liees aux Gift Pass
2. Verifier les expressions de calcul
3. Si le champ n'est pas lie, ajouter un lien vers la table source

**Tables candidates** :
- `ccventes` (cc_ventes) - Ventes Gift Pass
- `gift_pass` - Table des Gift Pass
- `ccpartyp` (cc_total_par_type) - Totaux par type

### Etape 3 : Ajouter la colonne Payment Type

1. Dans **Data View**, ajouter une variable virtuelle :
   - Nom : `v.Payment Type`
   - Type : Alpha 20
   - Init : Expression basee sur le moyen de paiement

2. Dans **Form Editor**, ajouter la colonne dans le formulaire

### Etape 4 : Ajouter les totaux

1. Dans **Data View**, verifier/ajouter les variables de totalisation
2. Dans **Task Logic**, ajouter les lignes d'incrementation
3. Dans **Form Editor**, ajouter la ligne de TOTAL en fin de groupe

### Etape 5 : Modifier l'export CSV

Le fichier CSV genere doit aussi inclure :
- La nouvelle colonne Payment Type
- Les lignes de TOTAL

Modifier l'expression ligne 4639 :
```
Trim({3,1})&{3,8}&'Total'&{3,8}&...&Trim(v.PaymentType)&{3,8}&...
```

---

## Points d'attention

| Point | Description | Action |
|-------|-------------|--------|
| **Codes paiement** | Les codes exacts des moyens de paiement | Verifier table REF moyens reglement |
| **Performance** | Le rapport peut etre volumineux | Tester sur periode longue |
| **Export CSV** | Le format doit rester compatible | Ajouter colonne en fin de ligne |
| **Totaux** | Plusieurs niveaux possibles | Definir si total par jour/par type/global |

---

## Tables de reference a consulter

| Table | Contenu | Utilite |
|-------|---------|---------|
| **cafil047_dat** | Moyens de reglement | Codes paiement (CMP, CB, GP...) |
| **ccventes** | Ventes | Detail des ventes avec montants |
| **operations_dat** | Operations | Mouvements financiers |

---

## Questions ouvertes

1. **Quels sont les codes exacts des moyens de paiement** dans le systeme ?
   - CMP = Club Med Pass ?
   - CB/CC = Credit Card ?
   - GP = Gift Pass ?

2. **Quel niveau de totalisation** est souhaite ?
   - Total global en fin de rapport ?
   - Total par jour ?
   - Total par type de paiement ?

3. **Le Gift Pass rembourse** correspond a quelle operation exactement ?
   - Annulation d'achat Gift Pass ?
   - Utilisation Gift Pass pour payer (donc pas de cash) ?

---

## Fichiers a modifier

| Fichier | Action |
|---------|--------|
| `PVE/Source/Prg_75.xml` | Modifier programme principal |
| `PVE/Source/Forms.xml` | Modifier formulaire edition (si externe) |

---

## Estimation

| Tache | Effort |
|-------|--------|
| Analyse structure existante | 30 min |
| Correction montant GIFT PASS | 1h |
| Ajout colonne Payment Type | 1h |
| Ajout lignes TOTAL | 1h |
| Modification export CSV | 30 min |
| Tests | 1h |
| **TOTAL** | ~5h |

---

$12026-01-22T18:55*
*Status: ANALYSE INITIALE - Questions ouvertes*
