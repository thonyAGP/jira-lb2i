# PMS-1521 — Analyse Technique

> **Analyse**: 2026-03-18 11:30 -> 12:00
> **Projet Magic**: PVE (Point de Vente)
> **Programme principal**: PVE Prg_178 — "Menu Equipment inventory" (18 sous-taches)

---

## 1. Programme impacte

### PVE Prg_178 — Menu Equipment inventory

Programme complexe avec **18 sous-taches** gerant :
- Ecran principal "EQUIPMENT CENTER" (grille equipements)
- Gestion Bindings (encart a remplacer)
- Impression Labels
- Inventaires, Range, Purge, Duplicate, Historiques

**Sous-taches :**

| ISN_2 | Description | Impact ticket |
|-------|-------------|---------------|
| 1 | Menu Equipment inventory (root) | Variables Bindings a remplacer par EPI |
| 2 | Equipments (MAIN) | Ecran principal — colonnes + encart a modifier |
| 3 | duplicate new | Aucun |
| 4 | Range | Aucun |
| 5 | Set Purge Status | Aucun |
| 6 | purge | Aucun |
| 7 | process | Aucun |
| 8-18 | Inventaires | Model Year affiche aussi en sous-tache 14 |

### Programmes secondaires

| Prg | Description | Impact |
|-----|-------------|--------|
| **Prg_90** | Calcul - binding setting | A REMPLACER par calcul EPI (decommission date) |
| **Prg_91** | Print Equipment SELECT | A ETENDRE pour Notice/Procedure/ID Sheet |
| **NOUVEAU** | Report EPI | Nouveau programme ou nouvelle tache dans Reports > Rental |

---

## 2. Tables base de donnees

### Tables actuellement utilisees par Prg_178

| obj ID | Table | Usage |
|--------|-------|-------|
| 389 | `pv_inv000000_dat01` | Table principale equipements (CRUD) |
| 394 | `pv_manufacturer_dat01` | Reference fabricants |
| 380 | `pv_daymodes_dat01` | Modes journaliers |
| 388 | `pv_hoteldays_dat01` | Jours hotel |
| 393 | `pv_invoicehistoprintagain01` | Historique impressions |
| 398 | `pv_presta_dat01` | Prestations |
| 399 | `pv_product_dat01` | Produits |
| 404 | `pv_sellersweek_dat01` | Vendeurs semaine |
| 412 | `pv_testski01` | Test ski |
| 419 | `realarca_dat01` | Real Arca |

### Table Binding existante
| obj ID | Table | Usage |
|--------|-------|-------|
| 371 | `pv_bindingset_dat01` | Calcul binding — A REMPLACER par EPI |

### Table Equipment (source de verite)
| obj ID | Table | Usage |
|--------|-------|-------|
| 385 | `pv_equipment_dat01` | Reference equipements — NOUVEAUX CHAMPS EPI requis |

---

## 3. Champs existants a modifier

### Colonne "Model Year" → "Purchase/Start Date"

| Champ actuel | Type | Taille | Nouveau champ |
|-------------|------|--------|---------------|
| `v year` (id=35) | ALPHA | 4 chars ("2025") | `v purchase_date` — ALPHA 7 chars ("mm/yyyy") |

**Impact**:
- Ecran principal (tache 2) : `ColumnTitle "Model year"` → `"Purchase/Start date"`
- Sous-tache 14 (online inventory) : `ColumnTitle "Model year"` aussi present
- Format passe de "4" (yyyy) a "7" (mm/yyyy)

### Encart Bindings → EPI Settings

**Champs actuels (a SUPPRIMER ou REMPLACER) :**

| Variable | Type | Taille | UI Label |
|----------|------|--------|----------|
| `v binding model` (id=38) | NUMERIC | 3 | "Model" (sous "Bindings") |
| `v bind manufacturer` (id=39) | NUMERIC | 2 | "Manufacturer" |
| `v bind year` (id=40) | ALPHA | 4 | "Year" |

**Nouveaux champs (a CREER) :**

| Variable | Type | Valeurs | Defaut | UI Label |
|----------|------|---------|--------|----------|
| `v epi_cat` | NUMERIC | 1, 2, 3 | 2 | "EPI CAT" |
| `v epi_years_lifetime` | NUMERIC | 1, 2, 3 | 3 | "EPI YEARS LIFETIME" |
| `v epi_decommission_date` | ALPHA (7) | mm/yyyy | *calcule* | "EXPECTED DECOMMISSION DATE" |

**Logique calcul** : `epi_decommission_date = purchase_date + epi_years_lifetime`
- Ex: purchase "10/2025" + lifetime 3 → decommission "10/2028"

---

## 4. Nouveaux boutons

### 4.1 NOTICE & PROCEDURE

**Emplacement** : Ecran principal, zone anciennement Bindings (voir maquette)

**Comportement** :
- Clic → ouvre sous-tache/dialog "Print Label Advanced"
- 2 checkboxes : NOTICE / PROCEDURE
- Bouton Print → genere PDF du fichier selectionne
- Fichiers statiques, toujours les memes pour categorie HELMET

**Implementation Magic** :
- Nouvelle sous-tache dans Prg_178 (ISN_2=19 ou nouveau)
- Formulaire avec 2 checkboxes + bouton Print
- Logic : ouvrir fichier PDF correspondant via shell/print

### 4.2 ID SHEET

**Emplacement** : Ecran principal, a cote du bouton NOTICE & PROCEDURE

**Comportement** :
- Clic → ouvre sous-tache affichant toutes les infos du casque selectionne
- Impression PDF possible

**Implementation Magic** :
- Nouvelle sous-tache dans Prg_178
- Formulaire read-only avec tous les champs de l'equipement
- Bouton Print → generer PDF

### 4.3 Rapport EPI (REPORTS > RENTAL)

**Emplacement** : Menu Reports (Prg_176 "Menu Reports")

**Comportement** :
- Nouveau bouton "EPI" dans la section Rental
- Genere PDF ou Excel
- 12 colonnes : Equipment ID, Serial Number, Equipment Type, Manufacturer, Model, Purchase/start date, Length, Status, Classification, EPI Cat., EPI Lifetime, Decomm. Date
- Filtre : uniquement equipements avec EPI Settings remplis
- Peut etre conditionne a un code projet

**Implementation Magic** :
- Nouveau programme (ou nouvelle tache dans un programme Reports existant)
- Query sur `pv_equipment_dat01` WHERE epi_cat IS NOT NULL
- Export : utiliser le mecanisme existant d'export (Print Equipment SELECT / Prg_91)

---

## 5. Modifications base de donnees

### Table `pv_equipment_dat01` — NOUVEAUX CHAMPS

| Champ | Type SQL | Default | Description |
|-------|----------|---------|-------------|
| `purchase_start_date` | VARCHAR(7) | NULL | Format mm/yyyy (remplace model_year) |
| `epi_cat` | SMALLINT | 2 | Categorie EPI (1, 2 ou 3) |
| `epi_years_lifetime` | SMALLINT | 3 | Duree de vie EPI en annees (1, 2 ou 3) |
| `epi_decommission_date` | VARCHAR(7) | NULL | Calcule: purchase_date + lifetime |

### Table `pv_bindingset_dat01` — A DEPRECIER
- Plus utilisee pour les casques
- Verifier si utilisee ailleurs avant suppression

---

## 6. Estimation d'effort

| Tache | Effort | Complexite |
|-------|--------|------------|
| Ajout champs DB (pv_equipment_dat01) | 0.5j | Faible |
| Renommage "Model Year" → "Purchase/Start Date" | 0.5j | Faible |
| Remplacement encart Bindings → EPI Settings | 1j | Moyenne |
| Logique calcul decommission date | 0.5j | Faible |
| Remplacement Prg_90 (binding → EPI calc) | 0.5j | Faible |
| Bouton + Dialog NOTICE & PROCEDURE | 1j | Moyenne |
| Bouton + Dialog ID SHEET | 1j | Moyenne |
| Rapport EPI (nouveau programme) | 1.5j | Moyenne |
| Tests + recette | 1.5j | — |
| **TOTAL** | **~8j** | **Moyenne** |

---

## 7. Risques et points d'attention

| Risque | Impact | Mitigation |
|--------|--------|------------|
| Migration du champ `model_year` existant | Donnees existantes au format "yyyy" a convertir en "mm/yyyy" | Script de migration, defaulter mois a "01" |
| `pv_bindingset_dat01` utilisee ailleurs | Suppression pourrait casser d'autres programmes | Audit callers avant suppression |
| Impression PDF Notice/Procedure | Fichiers PDF a fournir par le metier | Demander les fichiers source |
| Export EPI en Excel | Mecanisme d'export existant a verifier | Reutiliser Prg_91 si possible |
| Sous-tache 14 (online inventory) | Affiche aussi "Model year" | Ne pas oublier de modifier aussi |
| Condition code projet sur rapport | Logique de filtrage a definir | Clarifier avec le metier |

---

## 8. Diagramme d'impact

```
PVE Prg_178 (Menu Equipment inventory)
├── Tache 1 (root) ── Variables Bindings → EPI
├── Tache 2 (MAIN) ── Ecran principal
│   ├── "Model year" → "Purchase/Start date" (ColumnTitle)
│   ├── Encart "Bindings" → "EPI Settings" (Text label)
│   ├── 3 champs Binding → 3 champs EPI (Variables)
│   ├── [NOUVEAU] Bouton "NOTICE & PROCEDURE"
│   └── [NOUVEAU] Bouton "ID SHEET"
├── Tache 14 (online) ── "Model year" → "Purchase/Start date"
└── [NOUVEAU] Sous-tache "Print Label Advanced" (Notice/Procedure)

PVE Prg_90 (Calcul binding setting) → REMPLACER par calcul EPI

PVE Prg_91 (Print Equipment SELECT) → ETENDRE pour ID Sheet

Menu Reports (Prg_176)
└── [NOUVEAU] Bouton/Programme "Report EPI"

Table pv_equipment_dat01
└── +purchase_start_date, +epi_cat, +epi_years_lifetime, +epi_decommission_date

Table pv_bindingset_dat01 → A DEPRECIER (verifier dependances)
```
