# Analyse PMS-1373

> **Jira** : [PMS-1373](https://clubmed.atlassian.net/browse/PMS-1373)

## Symptome

**Demande d'évolution** : Possibilité d'extraire l'extrait de compte GM en masquant les lignes d'annulation (+/-).

Sur les Resorts montagne, les annulations génèrent des paires de lignes (+/-) qui polluent visuellement l'extrait de compte présenté aux clients.

**Comportement souhaité :**
1. Lors de l'impression de l'extrait (toutes les éditions > date + nom + service)
2. Afficher une question : "Voulez-vous éditer l'extrait de compte complet ?"
3. Si OUI → comportement actuel (toutes les lignes)
4. Si NON → masquer les paires de lignes qui s'annulent

## Contexte

| Element | Valeur |
|---------|--------|
| **Village/Site** | Alpe d'Huez (exemple captures) |
| **Type** | Story (évolution) |
| **Statut** | Recette KO |
| **Reporter** | Jessica Palermo |
| **Assignee** | Anthony Leberre |
| **Label** | ADH |

## Captures d'écran

### Image 1 : Extrait par Service
![Extrait par service](attachments/image-20250911-140855.png)

- Section "Ski" : lignes surlignées jaune
- "Prestige ski 6 DAY" 28/01 = **-208.00** (annulation)
- "Prestige ski 6 DAY" 01/02 = **+208.00** (nouvelle vente)
- Ces lignes s'annulent mais encombrent l'affichage

### Image 2 : Extrait par Nom
![Extrait par nom](attachments/image-20260106-144012.png)

- Lignes "WAXING + CER. SHARP" surlignées
- 04/01 = **-36.00** et **+36.00**
- Même problème de paires d'annulation

## Investigation

### Programmes impliqués (ADH.ecf - Sessions_Reprises)

| Projet | Prg ID | Public Name | Description | Role |
|--------|--------|-------------|-------------|------|
| ADH | 69 | EXTRAIT_COMPTE | Extrait de compte | Point d'entrée |
| ADH | 70 | EXTRAIT_NOM | Extrait par nom | Édition par nom |
| ADH | 71 | EXTRAIT_DATE | Extrait par date | Édition par date |
| ADH | 72 | EXTRAIT_CUM | Extrait cumulé | Édition cumul |
| ADH | 73 | EXTRAIT_IMP | Extrait impression | **Impression finale** |
| ADH | 76 | EXTRAIT_SERVICE | Extrait par service | Édition par service |

### Tables concernées

| Table | ID REF | Fichier Physique | Champs clés |
|-------|--------|------------------|-------------|
| operations | - | operations_dat | montant, date_op, service, type_op |
| cc_total_par_type | - | ccpartyp | societe, compte, filiation |

### Hypothèses

| # | Hypothèse | Probabilité | Explication |
|---|-----------|-------------|-------------|
| 1 | Filtrage dans requête SQL | Haute | Exclure paires +/- avec même libellé/date/montant |
| 2 | Post-traitement en mémoire | Moyenne | Parcourir résultats et éliminer paires |
| 3 | Paramètre édition Magic | Basse | Flag passé aux programmes d'édition |

## Analyse technique

### Logique de détection des annulations

Une annulation se caractérise par :
- **Même libellé** (article/service)
- **Même date** ou dates proches
- **Montants opposés** (+X et -X)
- Éventuellement **même service**

### Algorithme proposé

```
POUR chaque ligne de l'extrait:
  SI montant < 0:
    CHERCHER ligne correspondante avec:
      - même libellé
      - montant = -montant_actuel
      - même date (ou date proche)
    SI trouvée:
      MARQUER les deux lignes comme "annulation"

SI option "masquer annulations" = OUI:
  EXCLURE toutes les lignes marquées
```

### Questions à résoudre

1. **Où ajouter la question ?** Dans quel programme (69, 70, 71, 76 ?)
2. **Comment passer le paramètre ?** Variable globale ou paramètre CallTask ?
3. **Filtrage SQL ou mémoire ?** Dépend de la structure actuelle des programmes

## Analyse ADH IDE 69 (EXTRAIT_COMPTE) - COMPLETE

### Structure découverte (466KB, 12 sous-tâches)

| ISN_2 | Description | Type | Rôle |
|-------|-------------|------|------|
| 1 | Extrait de compte | B | Point d'entrée principal |
| 2 | Recalcul solde | B | Calcul du solde GM |
| 3 | Solde GM | B | Sous-calcul solde |
| 4 | Presence Ecritures GIFT PASS | B | Vérification GP |
| **5** | **scroll sur compte** | **O** | **Écran principal - affichage opérations** |
| **6** | **Choix Edition** | **O** | **Menu Print/Email/Cancel** |
| 7 | Zoom Listing | O | Zoom détail |
| 8 | SendMail | B | Envoi email |
| 9 | Vérif. Vente avec signature | B | Contrôle signature |
| 10 | Check recu detail | B | Vérification reçu |
| 11 | Recu mobilité POS | B | Ticket mobile |
| 12 | Reaffichage infos compte | B | Refresh écran |

### Flux d'édition identifié

```
ADH IDE 69 (EXTRAIT_COMPTE)
  └── Sous-tâche 5 "scroll sur compte"
        │   Variable: W1 Choix_action (Alpha 1)
        │
        ├── Choix 'N' → CallTask ADH IDE 70 (EXTRAIT_NOM)
        ├── Choix 'D' → CallTask ADH IDE 71 (EXTRAIT_DATE)
        ├── Choix 'C' → CallTask ADH IDE 72 (EXTRAIT_CUM)
        ├── Choix 'I' → CallTask ADH IDE 73 (EXTRAIT_IMP)
        └── Choix 'S' → CallTask ADH IDE 76 (EXTRAIT_SERVICE)
```

### Tables utilisées (obj REF.ecf)

| obj | Table | Usage |
|-----|-------|-------|
| 40 | operations_dat | MainSource - mouvements compte |
| 30 | ? | Link 1 |
| 67 | ? | Link 2 |
| 396 | ? | Link 3 |
| 473 | ? | Link 4 |
| 945 | ? | Link 5 (Cache) |

### Paramètres du programme

| Direction | ID | Nom | Type |
|-----------|-----|-----|------|
| Entrée | 11 | societe | Alpha 1 |
| Entrée | 13 | code_adherent | Numeric 8 |
| Entrée | 14 | filiation | Numeric 3 |
| Entrée | 15 | masque mtt | Alpha 16 |
| Entrée | 16 | nom village | Alpha 30 |
| Entrée | 23 | P_FormatPDF | Boolean |
| Entrée | 30 | P.ViensDe | Alpha 3 |
| Sortie | 17 | solde compte | Numeric 11.3 |
| Sortie | 18 | etat compte | Alpha 1 |
| Sortie | 19 | date solde | Date |
| Sortie | 20 | garanti O/N | Alpha 1 |

### Point d'injection recommandé

**Option retenue : Sous-tâche 5 "scroll sur compte"**

1. Ajouter variable `v.MasquerAnnulations` (Boolean)
2. Afficher checkbox ou question AVANT l'appel aux programmes d'édition
3. Passer ce paramètre aux programmes 70, 71, 72, 73, 76
4. Modifier chaque programme d'édition pour filtrer si paramètre = TRUE

### Analyse ADH IDE 70 & ADH IDE 76 - COMPLETE

Les deux programmes ont une **structure identique** avec 14 paramètres :

| # | Paramètre | Type | Description |
|---|-----------|------|-------------|
| 1 | P0 societe | Alpha 1 | Code société |
| 2 | P0 code adherent | Numeric 8 | N° compte GM |
| 3 | P0 filiation | Numeric 3 | Filiation |
| 4 | P0 masque montant | Alpha 16 | Format affichage |
| 5 | P0 nom village | Alpha 30 | Nom du village |
| 6 | P0 fictif | Boolean | Flag fictif |
| 7 | P0 date comptable | Date | Date comptable |
| 8 | P0 Affichage Tva | Boolean | Édition TVA V2 |
| 9 | P.FormatPDF | Boolean | Sortie PDF |
| 10 | P.Chemin | Alpha 128 | Chemin fichier |
| 11 | P.NomFichierPdf | Alpha 128 | Nom fichier |
| 12 | P.Print or Email | Alpha 1 | P=Print, E=Email |
| 13 | P.Print GIFT PASS | Boolean | Inclure GIFT PASS |
| 14 | P.Appel Direct | Boolean | Appel direct |

**Table principale identifiée : obj=40 = `operations_dat`**

Cette table est utilisée comme MainSource dans TOUTES les sous-tâches d'impression.

### Options d'implémentation

| Option | Complexité | Avantages | Inconvénients |
|--------|------------|-----------|---------------|
| **A. Paramètre 15** | Moyenne | Standard, propre | Modifier 5 programmes + tous les appels |
| **B. Variable globale** | Basse | Rapide à implémenter | Mauvaise pratique |
| **C. SQL WHERE** | Haute | Performant | Logique complexe de détection paires |

### Solution recommandée : Option A

1. **Ajouter paramètre 15** : `P.MasquerAnnulations` (Boolean) aux programmes 70, 71, 72, 73, 76
2. **Modifier ADH IDE 69** : Passer ce paramètre depuis la sous-tâche 5
3. **Logique de filtrage** : Dans chaque sous-tâche d'impression, ajouter condition sur MainSource

### Prochaines étapes

- [x] Analyser ADH IDE 70 (EXTRAIT_NOM) - 14 params, 19 sous-tâches
- [x] Analyser ADH IDE 76 (EXTRAIT_SERVICE) - 14 params, 17 sous-tâches
- [x] Identifier table opérations (obj=40 = operations_dat)
- [ ] Synchroniser sources sur GitLab
- [ ] Vérifier branche tentative précédente (Recette KO)
- [ ] Implémenter solution (ajout paramètre 15)

## DONNEES REQUISES POUR COMPLETER L'ANALYSE

### Base de données

| Element | Valeur |
|---------|--------|
| **Village** | Alpe d'Huez ou autre avec annulations |
| **Date** | Période avec annulations visibles |
| **Dossier concerné** | BENNUN Rachel (572185684) ou LOBO Nabil |

### Questions pour le demandeur

1. La recette KO - quel était le problème constaté ?
2. Y a-t-il une branche Git avec la tentative précédente ?
3. Odyssey doit aussi être impacté (mentionné par @Nelly Becquart)

---

## Verification MCP (2026-01-12)

### Structure ADH IDE 69 confirmée

| IDE | Nom | Role |
|-----|-----|------|
| 69 | Extrait de compte | Point d'entrée |
| 69.1 | Recalcul solde | Calcul |
| 69.2 | Presence Ecritures GIFT PASS | Vérification GP |
| **69.3** | **scroll sur compte** | **Écran principal** ✅ |
| 69.3.1 | Choix Edition | Menu Print/Email |
| 69.4 | Reaffichage infos compte | Refresh |

### Point d'injection confirmé

**Tâche 69.3 "scroll sur compte"** est le bon endroit pour :
1. Ajouter la question "Masquer annulations ?"
2. Passer le paramètre aux programmes d'édition (70, 71, 72, 73, 76)

### Status

| Element | Valeur |
|---------|--------|
| **Analyse** | CONFIRMÉE par MCP ✅ |
| **Point d'injection** | Tâche 69.3 |
| **Prochaine étape** | Implémenter paramètre P.MasquerAnnulations |

---

## IMPLEMENTATION REALISEE (2026-01-08)

### Commit

| Element | Valeur |
|---------|--------|
| **Hash** | `000d134efd31e5c42971149a936f24dd099995f1` |
| **Date** | 2026-01-08 23:57:34 |
| **Message** | Mise à jour des extraits de compte afin de ne pas afficher les lignes en doubles si on n'a pas demandé un extrait complet. |

### Fichiers modifies

| Fichier | Modifications |
|---------|---------------|
| `Prg_69.xml` | +2 arguments CallTask vers ADH IDE 72/73 |
| `Prg_72.xml` | +1 parametre `P. Sans annulations`, decalage colonnes |
| `Prg_73.xml` | +1 parametre, +2 colonnes Select, Expression 44, Range Exp |
| `Prg_3.xml` | Ajustements mineurs |
| `Prg_64.xml` | Ajustements mineurs |
| `Prg_98.xml` | Ajustements mineurs |

### Solution technique

**Parametre ajoute** : `P. Sans annulations` (Boolean)

**Expression de filtrage (Expression 44)** :
```
IF({2,25}, {0,28}=0 AND {0,29}<>'A', 'TRUE'LOG)
```

**Logique** :
- `{2,25}` = Parametre Boolean du parent
- `{0,28}` = Montant lie a l'annulation
- `{0,29}` = Flag type operation ('A' = Annulation)
- Si parametre TRUE → exclure les lignes avec flag='A'

**Mecanisme** : Utilisation du Range Expression pour filtrer au niveau SQL

### Pattern documente

Voir : `.openspec/patterns/add-filter-parameter.md`

### Status final

| Element | Valeur |
|---------|--------|
| **Implementation** | COMPLETE ✅ |
| **Recette** | A VALIDER |
| **Pattern capitalise** | OUI |

---

*Rapport généré le 2026-01-07*
*Verification MCP: 2026-01-12*
*Implementation: 2026-01-08*
*Statut: IMPLEMENTE - EN ATTENTE RECETTE*

---

*DerniÃ¨re mise Ã  jour : 2026-01-22T18:55*
