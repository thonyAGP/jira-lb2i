# Analyse PMS-1404

> **Jira** : [PMS-1404](https://clubmed.atlassian.net/browse/PMS-1404)

## Symptome

**POS REPORTS M&E : Ajouter colonne Quantite et verifier filtres**

Dans le menu POS > REPORTS > M&E, deux problemes :
1. **Colonne Quantity manquante** : On ne voit pas combien de produits ont ete pris
2. **Filtres non fonctionnels** : Les filtres "person", "item label" ne fonctionnent pas, l'extraction reste identique

## Contexte

| Element | Valeur |
|---------|--------|
| **Type** | Story (evolution) |
| **Statut** | Recette KO |
| **Priorite** | Moderee |
| **Reporter** | Davide Morandi |
| **Assignee** | Anthony Leberre |
| **Label** | PVE |
| **Cree** | 2025-11-12 |

---

## CLASSEMENT DES PISTES PAR SUSPICION (2026-01-13)

### PISTE 1 : Colonne Quantity - CONFIRMEE

**Localisation** : Tache 87.1.1.1 "Discount line"

**Programme** : PVE IDE 87 - Report - Discount & Gratuities

**Decouverte** :
- L'**en-tete** (Expression 8) contient bien "Quantity" dans la liste des colonnes
- Les **lignes de donnees** ne contiennent PAS de variable Quantity dans le DataView

**Variables du DataView de la Tache 87.1.1.1** (60 colonnes) :

> **Note** : Les variables sont numerotees globalement avec offset cumulatif.
> Offset = Main PVE (143) + Tache 87 (18) + Tache 87.1 (17) + Tache 87.1.1 (1) = 179
> Premiere variable de 87.1.1.1 = **Variable MK** (index 322)

| Variable | Nom | Type | Role |
|----------|-----|------|------|
| **MK** | v. Date operation | Date | Date de l'operation |
| **ML** | v. Date debut sejour | Date | Debut sejour |
| **MM** | v. Date fin sejour | Date | Fin sejour |
| **MS** | v.LabelAafficher | Unicode | Label produit |
| **MV** | V.Regular_price Ht | Numeric | Prix normal HT |
| **MW** | V.Regular_price Ttc | Numeric | Prix normal TTC |
| **MY** | V.Discounted price Ht | Numeric | Prix remise HT |
| **MZ** | V.Discounted price Ttc | Numeric | Prix remise TTC |
| **NB-NJ** | V.Total CA... | Numeric | Totaux CA |
| **NK-OP** | V.Total... | Numeric | Autres totaux |

**AUCUNE variable "Quantity" dans la liste !**

**Cause confirmee** : Le champ Quantity existe dans le header mais n'est jamais rempli dans les donnees car il n'y a pas de variable correspondante dans le DataView.

**Solution** :
1. Ajouter une variable `V.Quantity` dans le DataView de la Tache 87.1.1.1
2. La lier au champ quantite de la table source (probablement table hebergement ou table liee)
3. L'inclure dans le FormIO de sortie a la position correspondant au header

---

### PISTE 2 : Filtres Person/Item Label - NON IMPLEMENTES

**Statut** : CONFIRME PAR INVESTIGATION

**Decouverte** :
Les filtres "person" et "item label" mentionnes dans le ticket :
- Ne sont PAS connectes aux Range/Locate de la requete
- Les controles UI peuvent exister mais ne filtrent pas les donnees

**Programme concerne** : PVE IDE 87 - Report - Discount & Gratuities

**Taches a verifier** :
| Tache | Nom | Role potentiel |
|-------|-----|----------------|
| Tache 87.1.2 | SELECTION | Tache de filtrage principale |
| Tache 87.1.2.1 | Calcul CA | Calcul chiffre d'affaires |
| Tache 87.1.2.2 | Selection compta | Selection comptable |

**Solution** :
1. Identifier les controles de saisie filtre dans le form principal
2. Lier ces controles aux variables de Range/Locate
3. Appliquer les conditions dans la Tache 87.1.2 "SELECTION"

---

### PISTE 3 : Mauvais programme cible - A CLARIFIER

**Observation** :
Le ticket parle de "M&E" (Meetings & Events) mais nous analysons "Discount & Gratuities".

**Programmes potentiellement concernes** :

| Programme | Nom |
|-----------|-----|
| **PVE IDE 87** | Report - Discount & Gratuities |
| PVE IDE 77 | Report - Revenue by products (a verifier) |

**Question pour Davide** : Quel est le chemin exact dans le menu POS pour acceder au rapport M&E ?

---

## SYNTHESE ET PRIORITES

| Piste | Suspicion | Action |
|-------|-----------|--------|
| **1. Colonne Quantity manquante** | CONFIRMEE | Ajouter variable dans DataView Tache 87.1.1.1 |
| **2. Filtres non implementes** | CONFIRMEE | Connecter UI aux Range/Locate dans Tache 87.1.2 |
| **3. Mauvais programme** | A CLARIFIER | Demander confirmation chemin menu |

---

## SOLUTION TECHNIQUE PROPOSEE

### 1. Ajouter Quantity

**Etape 1** : Identifier la source de la quantite
- Verifier les tables liees dans la Tache 87.1.2 (SELECTION)
- Trouver le champ quantite (probablement dans table operations ou ventes)

**Etape 2** : Ajouter dans DataView de Tache 87.1.1.1
- Ajouter nouvelle variable apres Variable OP (position 61)
- Nom: V.Quantity
- Type: Numeric
- Picture: N5

**Etape 3** : Ajouter Select dans Logic
- Lier la nouvelle variable au champ de la table source

**Etape 4** : Inclure dans FormIO de sortie
- Positionner entre "Reason" et "Product" (position 9 dans header)

### 2. Implementer filtres

**A completer apres clarification du chemin menu exact**

---

## Arborescence des taches

```
PVE IDE 87 - Report - Discount & Gratuities
  |
  +-- Tache 87.1 - Print
       |
       +-- Tache 87.1.1 - EDITION V3
       |    |
       |    +-- Tache 87.1.1.1 - Discount line  <-- MANQUE QUANTITY
       |
       +-- Tache 87.1.2 - SELECTION  <-- FILTRES NON CONNECTES
       |    |
       |    +-- Tache 87.1.2.1 - Calcul CA
       |    +-- Tache 87.1.2.2 - Selection compta
       |    |    +-- Tache 87.1.2.2.1 - Temp generation
       |    +-- Tache 87.1.2.3 - Temp generation
       |    +-- Tache 87.1.2.4 - Temp generation Gift Pass
       |
       +-- Tache 87.1.3 - EXISTE Enregistrement
```

---

## Questions pour le demandeur

1. Quel est le chemin exact dans le menu pour acceder au rapport M&E ?
2. La colonne Quantity apparait-elle dans l'export mais vide, ou n'apparait-elle pas du tout ?
3. Sur quel village avez-vous teste ?
4. Pouvez-vous fournir un export exemple montrant le probleme ?
5. Quels sont les filtres "person" et "item label" exactement (noms des champs a l'ecran) ?

---

## MISE A JOUR 2026-01-18

### Retour Recette (15/01/2026)

**Davide Morandi** : "la colonne s'affiche bien mais les filtres ne fonctionnent toujours pas"

| Element | Statut |
|---------|--------|
| ✅ Colonne Quantity | **RESOLU** - s'affiche correctement |
| ❌ Filtres Person/Item Label | **KO** - ne filtrent pas les données |

---

## INVESTIGATION FILTRES (2026-01-18)

### DECOUVERTE CRITIQUE : Filtres NON IMPLEMENTES

**Conclusion** : Les filtres "person" et "item label" **N'EXISTENT PAS** dans le code actuel.
Il ne s'agit pas de filtres qui ne fonctionnent pas, mais de filtres qui n'ont **JAMAIS ETE CREES**.

### Programmes analyses

| Fichier | Programme | Paramètres | Filtres person/item |
|---------|-----------|------------|---------------------|
| Prg_82.xml | PVE IDE 82 - Report - Discount & Gratuities | 12 | ❌ ABSENTS |
| Prg_83.xml | PVE IDE 83 - Report - Discount&Gratuit-719 | 13 | ❌ ABSENTS |
| Prg_87.xml | PVE IDE 87 - Report - Selection/Tempo | 11 | ❌ ABSENTS |
| Prg_354.xml | PVE IDE 354 - Report - Discount & Gratuities | 12 | ❌ ABSENTS |
| Prg_383.xml | PVE IDE 383 - Report - Discount & Gratuities | 11 | ❌ ABSENTS |
| Prg_176.xml | PVE IDE 176 - Menu Reports | 0 | ❌ ABSENTS |

### Parametres existants (PVE IDE 82/83)

| # | Paramètre | Type | Description |
|---|-----------|------|-------------|
| 1 | P. Village name | Alpha | Nom du village |
| 2 | P. Currency | Alpha | Devise |
| 3 | P. Amount format | Alpha | Format montant |
| 4 | P. Amount format sans Z | Alpha | Format sans zéros |
| 5 | P. Decimales | Numeric | Nombre décimales |
| 6 | P. HD Contrôle | Logical | Flag HD |
| 7 | P Période nombre JH | Numeric | Jours/Hommes |
| 8 | P Jours Période | Numeric | Jours période |
| 9 | P Date mini | Date | Date début |
| 10 | P Date maxi | Date | Date fin |
| 11 | P Discount & Free of Charge | Numeric | Type remise |
| 12 | P.I Flag Cloture Service | Logical | Flag clôture |
| 13 | (IDE 83) P.? | Logical | Paramètre additionnel |

**AUCUN paramètre "person" ou "item label" !**

### Flux d'appel

```
Menu Reports (PVE IDE 176)
    │
    └── CallTask FlowIsn="83" ──► PVE IDE 83 - Report - Discount&Gratuit-719
                                      │
                                      └── CallTask FlowIsn="87" ──► PVE IDE 87 - Selection/Tempo
```

### Pistes d'implementation

**PISTE A : Ajouter filtres en paramètres**

1. **Modifier PVE IDE 83** (ou 82/354/383 selon version utilisée)
   - Ajouter 2 nouveaux paramètres : `P.Filter Person` (Alpha), `P.Filter Item Label` (Alpha)
   - Passer ces paramètres à PVE IDE 87

2. **Modifier PVE IDE 87** (Report - Selection/Tempo)
   - Ajouter les paramètres filtres dans le DataView
   - Appliquer conditions dans Tâche 87.1.2 "SELECTION"
   - Utiliser Range/Locate pour filtrer les données

3. **Modifier l'interface Menu Reports (PVE IDE 176)**
   - Ajouter 2 champs de saisie pour les filtres
   - Lier aux paramètres du CallTask vers IDE 83

**PISTE B : Identifier tables sources**

Tables utilisées par PVE IDE 87 :
| obj | Table probable |
|-----|----------------|
| 379 | ? (à identifier via Comps.xml) |
| 403 | ? |
| 413 | ? |
| 1471 | ? |
| 762 | ? |

Champs potentiels à filtrer :
- `person` → Table clients/adhérents (champ nom/prénom)
- `item label` → Table articles (champ libellé produit)

### Questions pour clarification

1. **Où ces filtres sont-ils affichés ?**
   - Dans le Menu Reports (PVE IDE 176) ?
   - Dans un écran de saisie préalable ?
   - L'utilisateur les voit-il mais ils ne fonctionnent pas ?

2. **Quel est le comportement attendu ?**
   - Filtrer par nom de personne (GM) ?
   - Filtrer par libellé d'article ?
   - Recherche exacte ou partielle (LIKE) ?

3. **Quelle version du rapport est utilisée ?**
   - PVE IDE 82, 83, 354 ou 383 ?
   - Dépend du village et de la configuration

---

*Derniere mise a jour: 2026-01-18*
*Status: EN COURS - Colonne OK, Filtres JAMAIS IMPLEMENTES*
*Action requise: Clarification + Développement nouvelle fonctionnalité*

---

*DerniÃ¨re mise Ã  jour : 2026-01-22T18:55*
