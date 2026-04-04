# PMS-1521 — POS SKI: evolution pour LOCATION CASQUE

| Champ | Valeur |
|-------|--------|
| **Type** | Story |
| **Status** | Idee |
| **Priority** | Critique |
| **Reporter** | Davide Morandi |
| **Assignee** | Anthony Leberre |
| **Created** | 2026-03-17 |
| **Updated** | 2026-03-17 |

## Contexte

Suite au passage de la repression de fraudes dans nos Club, ils nous ont remonte un manquement dans le suivi des casques de location. C'est un dev a prioriser au max pour la prochaine livraison.

## Modifications demandees

### 1. Renommage colonne MODEL YEAR → PURCHASE/START DATE
- Remplacer le libelle "MODEL YEAR" par "PURCHASE/START DATE"
- Possibilite d'integrer au format mm/yyyy

### 2. Remplacement encart BINDINGS → EPI Settings
- L'encart "BINDINGS" n'est plus utilise, le remplacer par "EPI Settings"
- **EPI CAT**: menu deroulant 1/2/3 (defaut: 2)
- **EPI YEARS LIFETIME**: menu deroulant 1/2/3 (defaut: 3)
- **EXPECTED DECOMMISSION DATE**: calcule automatiquement = PURCHASE DATE + EPI YEARS LIFETIME

### 3. Bouton NOTICE & PROCEDURE
- Clic ouvre un ecran avec 2 choix d'impression:
  - **NOTICE** (PDF notice)
  - **PROCEDURE** (procedure de controle)
- Les fichiers sont toujours les memes pour toute la categorie HELMET

### 4. Bouton ID SHEET
- Clic affiche un ecran avec l'ensemble des informations d'un casque
- Possibilite d'impression en PDF

### 5. Rapport EPI dans REPORTS > RENTAL
- Nouveau bouton "EPI" qui genere un PDF ou Excel
- Colonnes: Equipment ID, Serial Number, Equipment Type, Manufacturer, Model, Purchase/start date, Length, Status, Classification, EPI Cat., EPI Lifetime, Decomm. Date
- Imprime la totalite des equipements ayant les infos EPI completees
- Peut etre conditionne a un code projet

## Attachments
- `image-20260317-104456.png` — Maquette ecran principal Equipment Center avec EPI Settings
- `image-20260317-105656.png` — Dialog Print Label Advanced (Notice/Procedure)
- `image-20260317-105802.png` — Dialog ID Sheet (fiche casque)
- `image-20260317-105925.png` — Colonnes export EPI (Excel/PDF)
