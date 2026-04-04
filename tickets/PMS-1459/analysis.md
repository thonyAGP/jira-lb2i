# Analyse Ticket PMS-1459

> **Analyse**: 2026-02-03 14:00 -> 15:30
> **Type**: Bug
> **Priorite**: Haute

---

## 1. Contexte Jira

[PMS-1459](https://clubmed.atlassian.net/browse/PMS-1459) - [POS SKI] Annulation d'echange rembourse le montant total au lieu de la difference

| Element | Valeur |
|---------|--------|
| **Symptome** | L'annulation d'un echange (EXCHANGE) de materiel ski rembourse le montant total du nouveau materiel au lieu de la difference entre les deux |
| **Village** | Best Of - Insurance - SKI (station de ski) |
| **Exemple concret** | Echange SPORT/LOISIR (66 EUR) vers PERFORMANCE (74 EUR) = difference 8 EUR. Annulation rembourse 74 EUR au lieu de 8 EUR |
| **Impact** | Perte financiere : chaque annulation d'echange credit le GM du montant total au lieu du delta |

### Reproduction du bug

**Etape 1 - Location initiale :**
- SKI RENTAL SPORT/LOISIR - 2 DAY - 66 EUR - PREPAID

**Etape 2 - Echange (EXCHANGE) :**
L'echange cree 3 lignes dans la vente :

| # | Customer | Product | Description | Qty | Payment type | Amount |
|---|----------|---------|-------------|-----|-------------|--------|
| 1 | AFRIAT BENHAMOU | SKI RENTAL SPORT/LOISIR | 2 DAY | 1 | PREPAID | **0.00** |
| 2 | AFRIAT BENHAMOU | SKI RENTAL PERFORMANCE | 2 DAY | -1 | CLUBMED PASS | **-66.00** |
| 3 | AFRIAT BENHAMOU | SKI RENTAL PERFORMANCE | 2 DAY | 1 | CLUBMED PASS | **74.00** |

- **Ticket Value = 8.00** (difference correcte)
- **Total to pay = 8.00**

**Etape 3 - Annulation (CANCEL) :**
L'annulation cree une seule ligne :

| # | Date | Description | Cmt | Price | Qty | Payment |
|---|------|-------------|-----|-------|-----|---------|
| 1 | 15/01/2026 08:45 | SKI RENTAL PERFORMANCE - 2 DAY | CANCEL 15/01-16/01 | **74.00** | -1.00 | CLUBMED PASS |

- **Montant rembourse = 74.00 EUR** (BUG - devrait etre 8.00)

**Resultat dans l'extrait de compte (CA0122) :**

| Credit/Debit | Date | Heure | Libelle | Montant |
|-------------|------|-------|---------|---------|
| CR | 15/01/2026 | 08:45 | Perf ski 2 DAY | **74.00** |
| DB | 15/01/2026 | 08:44 | Perf ski 2 DAY | -74.00 |
| CR | 15/01/2026 | 08:44 | Sport ski 2 DAY | 66.00 |

Le GM est credite de 74 EUR (ligne CANCEL) alors que seuls 8 EUR ont ete debites lors de l'echange.

### Pieces jointes

| Fichier | Description |
|---------|-------------|
| `image-20260115-074858.png` | Ecran validation echange : 3 lignes, total 8.00 EUR (correct) |
| `image-20260115-075148.png` | Ecran POS SKI apres CANCEL : prix 74.00 EUR rembourse (BUG) |
| `image-20260115-075156.png` | Extrait de compte CA0122 : CR 74.00 au lieu de 8.00 |

---

## 2. Localisation - Programmes identifies

### Programme principal : PVE IDE 393 - Menu Check IN/Exchange V4

Version V4 du menu d'echange/check-in, utilisee sur ce village.

| Element | Valeur |
|---------|--------|
| **Projet** | PVE |
| **IDE** | 393 |
| **Nom** | Menu Check IN/Exchange V4 |
| **Role** | Orchestre les operations de Check-IN, Exchange et Return |
| **Appelle** | PVE IDE 218 (Package pricing) pour le calcul des prix |

### Programme de calcul des prix : PVE IDE 218 - Package pricing

| Element | Valeur |
|---------|--------|
| **Projet** | PVE |
| **IDE** | 218 |
| **Nom** | Package pricing |
| **Taches** | 2 (1 ecran visible) |
| **Expressions** | 66 (31 conditions, 22 other, 3 concatenations) |
| **Parametres cles** | P.Action (C), P.Date (D), P.Customer Id (A), P.Package Id (B) |

Ce programme distingue les actions par le parametre `P. Action [C]` :
- `SALE` : Vente directe
- `RENTAL` : Location
- `RETURN-` : Retour d'equipement
- `EXCHANGE` : Echange
- `EXTEND` : Extension de duree

### Programme d'annulation : PVE IDE 312 - Recalcul annulations

| Element | Valeur |
|---------|--------|
| **Projet** | PVE |
| **IDE** | 312 |
| **Nom** | Recalcul annulations |
| **Role** | Recalcule les montants lors des annulations de lignes de vente |

### Programme de gestion stock/vente : PVE IDE 226 - Stock Sale/Cancel

| Element | Valeur |
|---------|--------|
| **Projet** | PVE |
| **IDE** | 226 |
| **Nom** | Stock Sale/Cancel |
| **Role** | Gere le stock et les operations de vente/annulation |

### Programme Check-IN (ancienne version) : PVE IDE 183 - Menu Check IN / Exchange

| Element | Valeur |
|---------|--------|
| **Projet** | PVE |
| **IDE** | 183 |
| **Nom** | Menu Check IN / Exchange |
| **Taches** | 8 (3 ecrans visibles) |
| **Role** | Version anterieure du menu d'echange - meme logique de base |
| **Ecrans** | Rental operations (1988x432), Rentals (628x197), Confirm (554x157) |

---

## 3. Tables concernees

### Tables en lecture

| Table | Nom physique | Usage |
|-------|-------------|-------|
| **400** pv_cust_rentals | Locations client | Historique des locations (equipement, dates, statut) |
| **389** pv_equipment_inventory | Inventaire equipement | Stock des equipements ski |
| **77** articles_________art | Articles et stock | Catalogue articles avec prix |
| **380** pv_day_modes | Modes jour | Configuration facturation jour |
| **382** pv_discount_reasons | Raisons remise | Remises applicables |
| **413** pv_tva | TVA | Taux TVA |
| **36** client_gm | Client GM | Donnees client |

### Tables en ecriture

| Table | Nom physique | Usage |
|-------|-------------|-------|
| **404** pv_sellers_by_week | Vendeurs par semaine | MAJ stats vendeur |
| **805** vente_par_moyen_paiement | Vente par MOP | Enregistrement du paiement |

---

## 4. Flux de l'echange et de l'annulation

### 4.1 Flux de l'ECHANGE (fonctionne correctement)

```
┌─────────────────────────────┐
│ PVE IDE 214 / 186           │ Main Sale (ou Main Sale Bar Code)
│ Bouton EXCHANGE             │
└────────────┬────────────────┘
             │ CallTask
             ▼
┌─────────────────────────────┐
│ PVE IDE 183 / 393           │ Menu Check IN / Exchange (V4)
│ Ecran: serial IN + OUT      │
│ Bouton EXCHANGE / RETURN    │
└────────────┬────────────────┘
             │ CallTask (6 fois)
             ▼
┌─────────────────────────────┐
│ PVE IDE 218                 │ Package pricing
│ P.Action = 'EXCHANGE'       │
│ Calcul prix                 │
└────────────┬────────────────┘
             │
    Resultat : 3 lignes de vente
             │
             ▼
┌─────────────────────────────────────────────────┐
│ Ligne 1: SPORT/LOISIR  → Montant = 0.00        │ (ancien rendu)
│ Ligne 2: PERFORMANCE   → Montant = -66.00      │ (credit ancien prix)
│ Ligne 3: PERFORMANCE   → Montant = +74.00      │ (debit nouveau prix)
│                                                  │
│ TOTAL = 8.00 EUR (difference correcte)          │
└─────────────────────────────────────────────────┘
```

### 4.2 Flux de l'ANNULATION (BUG)

```
┌─────────────────────────────┐
│ PVE IDE 214 / 186           │ Main Sale
│ Bouton CANCEL               │
└────────────┬────────────────┘
             │
             ▼
┌─────────────────────────────┐
│ PVE IDE 312                 │ Recalcul annulations ← SUSPECT
│ Boucle sur lignes vente     │
└────────────┬────────────────┘
             │
    Pour chaque ligne :
    - Type = 'EXCHANGE' ?
    - Expression 31 → Force FALSE
    - Expression 32 → Force montant = 0
             │
             ▼
┌─────────────────────────────────────────────────┐
│ RESULTAT : Seule la ligne RENTAL PERFORMANCE    │
│ est annulee a son montant TOTAL = 74.00         │
│                                                  │
│ Les lignes EXCHANGE sont IGNOREES (forcees a 0) │
│                                                  │
│ MONTANT REMBOURSE = 74.00 au lieu de 8.00       │ ← BUG
└─────────────────────────────────────────────────┘
```

---

## 5. Expressions cles

### PVE IDE 312 - Expressions d'exclusion des lignes EXCHANGE

| Expression | Decodee | Effet |
|-----------|---------|-------|
| **Expr 31** | `IF(Trim({1,21})='EXCHANGE','FALSE',{1,38})` | Si type = EXCHANGE, force le flag a FALSE → ligne ignoree dans le recalcul |
| **Expr 32** | `IF(Trim({1,21})='EXCHANGE',0,{1,40})` | Si type = EXCHANGE, force le montant a 0 → pas de remboursement EXCHANGE |

Ces expressions sont **intentionnelles** : elles empechent le recalcul administratif de toucher aux lignes d'echange. Mais le probleme est que lors de l'annulation en temps reel, le systeme ne les utilise pas et traite chaque ligne independamment.

### PVE IDE 218 - Expression critique de pricing

| Expression | Decodee | Signification |
|-----------|---------|---------------|
| **Expr 2** | `CndRange(P.Action[C]<>'SALE' AND (...), IF(P.FlagDate[J]=1 OR ..., Date()-P.Date[D]+1-IF(GetParam('MODEDAY')='AM',1,0), ...))` | Le calcul de prix utilise `Date()` → ne fonctionne que le jour meme |
| **Expr 12** | `P.Action[C]<>'EXTEND' AND P.Action[C]<>'EXCHANGE'` | Condition qui distingue les EXCHANGE des autres actions |
| **Expr 39** | `IF(Trim(P.Action[C])='RETURN-', P.Date[D]-V.Quantite[T], P.Date[D]-V.Quantite[T]+1)` | Calcul date different pour RETURN vs autres |
| **Expr 66** | `IF(Left([CY],6)='RETURN',[CX],P.Package Id[B])` | Distinction RETURN dans le Package Id |

---

## 6. Diagnostic - Root Cause

### Hypothese principale confirmee

**Le processus d'annulation (CANCEL) ne comprend pas la notion d'echange (EXCHANGE).** Il traite chaque ligne de vente comme une operation independante.

#### Deroulement du bug :

1. **L'echange cree 3 lignes** liees entre elles par le contexte commercial (retour ancien + credit + debit nouveau)
2. **L'annulation lit la derniere ligne RENTAL** (PERFORMANCE, 74 EUR, qty=1) et la considere comme une vente standalone
3. **Le CANCEL cree une ligne inverse** : PERFORMANCE, 74 EUR, qty=-1 → credit de 74 EUR
4. **Les lignes EXCHANGE** (-66 EUR) ne sont **pas annulees** car PVE IDE 312 les ignore intentionnellement (expressions 31/32)
5. **Resultat** : le GM recoit 74 EUR de credit au lieu des 8 EUR qu'il a reellement payes

#### Pourquoi l'annulation est limitee au jour meme ?

Expression 2 de PVE IDE 218 utilise `Date()` dans le calcul du prix. Cela signifie que le prix recalcule lors de l'annulation depend de la date courante. Si l'annulation est faite un autre jour, le calcul de jours de location change et le prix recalcule sera different du prix original.

### Schema de la root cause

```
ECHANGE (8 EUR net) :
  Ligne 1 : SPORT/LOISIR   =   0.00  (retour, prix zero)
  Ligne 2 : PERFORMANCE    = -66.00  (credit ancien, type=EXCHANGE)
  Ligne 3 : PERFORMANCE    = +74.00  (debit nouveau, type=RENTAL)
                              ------
  Net GM debite             =  8.00   ← CORRECT

ANNULATION :
  PVE IDE 312 ignore lignes EXCHANGE (expr 31/32)
  → Seule la ligne 3 (RENTAL, +74.00) est annulee
  → CANCEL PERFORMANCE     = -74.00  (credit, type=CANCEL)
                              ------
  Net GM credite            = 74.00   ← BUG (devrait etre 8.00)

ERREUR = 74.00 - 8.00 = 66.00 EUR de trop rembourse
```

---

## 7. Piste de correction

### Option A : Annuler les 3 lignes de l'echange (recommandee)

L'annulation d'un echange devrait annuler **les 3 lignes** ensemble :
- CANCEL ligne 1 (SPORT/LOISIR 0.00) → inversion 0.00
- CANCEL ligne 2 (EXCHANGE -66.00) → inversion +66.00
- CANCEL ligne 3 (RENTAL 74.00) → inversion -74.00
- **Net = 0.00 + 66.00 - 74.00 = -8.00** (correct)

**Modifications** :
- PVE IDE 312 : ne plus ignorer les lignes EXCHANGE lors d'une annulation d'echange
- PVE IDE 226 : s'assurer que les 3 lignes sont identifiees comme un groupe lie

### Option B : Calculer le montant net de l'echange

Au lieu d'annuler chaque ligne, calculer le montant net debite lors de l'echange (8.00) et ne rembourser que ce montant.

**Modifications** :
- PVE IDE 312 : ajouter une condition pour detecter que la ligne RENTAL fait partie d'un echange
- Si c'est le cas, remplacer le montant par la difference (prix_nouveau - prix_ancien)

### Option C : Traiter l'annulation comme un retour + re-location de l'ancien

Annuler l'echange = remettre le client dans l'etat avant l'echange :
- Retour du materiel PERFORMANCE
- Re-location du materiel SPORT/LOISIR
- Remboursement de la difference 8.00

---

## 8. Checklist verification

- [ ] Verifier dans PVE IDE 312 comment les lignes sont selectionnees pour annulation
- [ ] Confirmer que les expressions 31/32 de PVE IDE 312 sont bien la cause du filtrage
- [ ] Identifier comment les 3 lignes d'echange sont liees (Package Id ? Sale Id ?)
- [ ] Verifier si PVE IDE 393 (V4) a un comportement different de PVE IDE 183
- [ ] Tester si le bug existe aussi sur la version non-V4 (PVE IDE 183)
- [ ] Clarifier avec le demandeur quelle option de correction est preferee
- [ ] Evaluer l'impact sur les echanges deja annules (historique)

---

## 9. Programmes references

| Programme | Role dans l'analyse |
|-----------|-------------------|
| **PVE IDE 393** - Menu Check IN/Exchange V4 | Point d'entree de l'echange (version V4) |
| **PVE IDE 183** - Menu Check IN / Exchange | Version anterieure (meme logique de base) |
| **PVE IDE 218** - Package pricing | Calcul des prix selon l'action (66 expressions) |
| **PVE IDE 312** - Recalcul annulations | **ROOT CAUSE** - ignore les lignes EXCHANGE |
| **PVE IDE 226** - Stock Sale/Cancel | Gestion stock lors des annulations |
| **PVE IDE 214** - Main Sale Sale Bar Code | Point d'appel principal (bouton CANCEL) |
| **PVE IDE 186** - Main Sale | Point d'appel alternatif |

### 9.1 Screenshots

| # | Fichier | Description |
|---|---------|-------------|
| 1 | [image-20260115-074858.png](attachments/image-20260115-074858.png) | Validation echange - 3 lignes, total 8.00 EUR |
| 2 | [image-20260115-075148.png](attachments/image-20260115-075148.png) | POS SKI - CANCEL rembourse 74.00 EUR (BUG) |
| 3 | [image-20260115-075156.png](attachments/image-20260115-075156.png) | Extrait compte CA0122 - CR 74.00 EUR |

---

## 10. Commits / Historique

*A completer lors de l'implementation*

---

*Analyse realisee avec: Claude Code + specs PVE (Pipeline V7.2)*
*Ticket-analyze protocol v2.0*
