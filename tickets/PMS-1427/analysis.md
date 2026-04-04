# Analyse Ticket PMS-1427

> **Genere automatiquement** par le pipeline d'analyse Magic
> Date: 2026-01-29 12:34

---

## 1. Contexte Jira

[PMS-1427](https://clubmed.atlassian.net/browse/PMS-1427)

| Element | Valeur |
|---------|--------|
| **Symptome** | POS Edition Income - Ventes GP multi-services absentes de la table tempo |
| **Source** | index |

### Mots-cles detectes

- **calcul**: calcul, montant
- **date**: date
- **import**: fichier, import, na

## 2. Localisation

### Programmes identifies

| Fichier XML | IDE Verifie | Nom | Source |
|-------------|-------------|-----|--------|
| Prg_330.xml | **ADH IDE 0** | Deversement Transaction /PMS14 | kb-exact |
| Prg_27.xml | **ADH IDE 27** | Separation | kb-exact |
| Prg_38.xml | **ADH IDE 38** | Program_38 | kb-exact |
| Prg_27.xml | **CAB IDE 19** |   Test si cloture en cours | kb-exact |
| Prg_38.xml | **EXB IDE 26** | Detail Excursion | kb-exact |
| Prg_27.xml | **EXF IDE 40** |  Annulation Ventes | kb-exact |
| Prg_38.xml | **GES IDE 24** |  Bi  Selection des devises | kb-exact |
| Prg_27.xml | **GES IDE 79** | CM  Menu Services village | kb-exact |
| Prg_38.xml | **MAI IDE 83** | Contrâ”œâ”¤le de Caractâ”œÂ¿re | kb-exact |
| Prg_389.xml | **PVE IDE 397** | Menu Service cloture v2 | kb-fuzzy |
| Prg_394.xml | **PVE IDE 402** | Menu Service cloture | kb-fuzzy |
| Prg_373.xml | **PBG IDE 134** | GM Presents | kb-exact |
| Prg_380.xml | **PBG IDE 245** | Edition Nouv. Prestations | kb-exact |
| Prg_394.xml | **PBG IDE 251** | Import - MOD | kb-exact |
| Prg_389.xml | **PBG IDE 256** | Import - FRA PRESTATION | kb-exact |
| Prg_372.xml | **PBG IDE 260** | Impression Ezcard modifiees | kb-exact |
| Prg_371.xml | **PBG IDE 261** | Affichage Ezcard modifiees | kb-exact |
| Prg_351.xml | **PBG IDE 318** | Affichage &Version | kb-exact |
| Prg_371.xml | **PBP IDE 244** |    Edit journal de police | kb-exact |
| Prg_372.xml | **PBP IDE 245** |    Generation Stat | kb-exact |
| Prg_373.xml | **PBP IDE 246** |    Edit Stat EOT | kb-exact |
| Prg_380.xml | **PBP IDE 250** | Affich present planning GM CL | kb-exact |
| Prg_381.xml | **PBP IDE 251** | Imprim GM present planning CL | kb-exact |
| Prg_394.xml | **PBP IDE 97** | Preparation â”œÂ®tiquettes(Chambre | kb-exact |
| Prg_27.xml | **Import IDE 27** | Import - client_gm | kb-id |
| Prg_351.xml | **Import IDE 350** | Import - pv_sellers_by_week | kb-id |
| Prg_351.xml | **PVE IDE 358** | Print Invoice or Ticket | kb-id |
| Prg_351.xml | **REF IDE 351** | Browse - erreur_od | kb-id |
| Prg_371.xml | **ADH IDE 0** | Transaction Nouv vente PMS-584 | kb-id |
| Prg_371.xml | **Import IDE 368** | Import - req_type_pb | kb-id |
| Prg_371.xml | **PVE IDE 379** | Print Deposit | kb-id |
| Prg_372.xml | **ADH IDE 0** |  Print ticket vente PMS-584 | kb-id |
| Prg_372.xml | **Import IDE 369** | Import - req_groups_profile1__ | kb-id |
| Prg_372.xml | **PVE IDE 380** | Print Stat Ventes *NU* | kb-id |
| Prg_373.xml | **ADH IDE 0** | Print creation garanti PMS-584 | kb-id |
| Prg_373.xml | **Import IDE 370** | Import - req_groups_profile2__ | kb-id |
| Prg_373.xml | **PVE IDE 381** | Export Insurance | kb-id |
| Prg_38.xml | **Import IDE 38** | Import - compte_gm________cgm | kb-id |
| Prg_380.xml | **Import IDE 377** | Import - req_type | kb-id |
| Prg_380.xml | **PVE IDE 388** | Print Global Income | kb-id |
| Prg_380.xml | **REF IDE 380** | Browse - pv_hotel_days | kb-id |
| Prg_381.xml | **Import IDE 378** | Import - req_type_options | kb-id |
| Prg_381.xml | **PVE IDE 389** | Print Global Income Tout serv | kb-id |
| Prg_381.xml | **REF IDE 381** | Browse - pv_equipment_inventor | kb-id |
| Prg_381.xml | **VIL IDE 112** | Calcul libelle du montant | kb-id |
| Prg_386.xml | **Import IDE 383** | Import - resto_reservations+ | kb-id |
| Prg_386.xml | **PVE IDE 394** | Report - Category selection | kb-id |
| Prg_386.xml | **REF IDE 386** | Browse - pv_manufacturers | kb-id |
| Prg_386.xml | **VIL IDE 114** | Tableau Excel - Cloture Auto | kb-id |
| Prg_389.xml | **ADH IDE 0** | Histo ventes payantes /PMS-623 | kb-id |
| Prg_389.xml | **Import IDE 386** | Import - resto_tables_schedule | kb-id |
| Prg_389.xml | **REF IDE 389** | Browse - pv_package_composants | kb-id |
| Prg_394.xml | **ADH IDE 0** | Transaction Nouv vente PMS-721 | kb-id |
| Prg_394.xml | **Import IDE 391** | Import - scelles | kb-id |
| Prg_38.xml | **PVE IDE 41** | Report - Margin by Day | kb-exact |

### Appels MCP documentes

- `magic_get_position("ADH", 330)` -> ADH IDE 0
- `magic_get_position("ADH", 27)` -> ADH IDE 27
- `magic_get_position("ADH", 38)` -> ADH IDE 38

## 3. Tracage Flux

*Flux non trace*

## 4. Analyse Expressions

*Aucune expression {N,Y} trouvee ou decodage non effectue*

## 5. Patterns KB

### Patterns similaires trouves

| Pattern | Score | Domaine | Source |
|---------|-------|---------|--------|
| **table-link-missing** | 3 | data |  |
| **date-format-inversion** | 3 | import |  |

### Pattern suggere: table-link-missing

Correspondances:
- [keyword] table (poids: 1)
- [domain] table (poids: 2)

> Voir: `.openspec/patterns/table-link-missing.md` pour la solution type

## 6. Root Cause

### Hypothese

*A completer manuellement apres analyse des donnees ci-dessus*

### Localisation

| Element | Valeur |
|---------|--------|
| Programme | *A definir* |
| Tache | *A definir* |
| Ligne | *A definir* |
| Expression | *A definir* |

## 7. Solution

### Modification proposee

| Element | Avant (bug) | Apres (fix) |
|---------|-------------|-------------|
| *A definir* | *valeur actuelle* | *valeur corrigee* |

---

## Checklist Validation

- [x] IDE verifie pour chaque programme
- [ ] Expressions {N,Y} decodees
- [x] Diagramme de flux present
- [ ] Root Cause identifiee (Programme + Tache + Ligne)
- [ ] Solution Avant/Apres documentee

---

*Analyse generee par: `tools/ticket-pipeline/Run-TicketPipeline.ps1`*

*Pipeline version: 1.0*

