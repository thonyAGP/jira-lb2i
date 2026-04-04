# Analyse Ticket PMS-1457

> **Analyse**: 2026-02-03 10:00 -> 10:45
> **Type**: Story (nouvelle fonctionnalite)
> **Priorite**: Haute

---

## 1. Contexte Jira

[PMS-1457](https://clubmed.atlassian.net/browse/PMS-1457) - [Caisse Adherent] Caution forfait de ski automatique

| Element | Valeur |
|---------|--------|
| **Demande** | Creer automatiquement une caution de 25 CHF sur le compte de chaque GM arrivant a St Moritz (SMRC) |
| **Declencheur** | Cloture de nuit (batch), jour d'arrivee du GM |
| **Montant** | 25 CHF |
| **Village** | St Moritz (code SMRC) |
| **Raison** | La station facture 25 CHF par ski pass non rendu |

### Regles d'exclusion

| Regle | Description |
|-------|-------------|
| Code presta SMRNS1 | GM ayant le code prestation SMRNS1 = exempt de caution |
| Enfants < 6 ans | Ne pas charger les enfants de moins de 6 ans |
| GM non valides | Seuls les GM valides (confirmes) sont concernes |
| Code projet | Le traitement doit etre activable/desactivable par un code projet |

---

## 2. Localisation - Programmes identifies

### Programme modele : REF IDE 667 - Affectation de Garantie (`AFF_GARANTIE_CLUB`)

C'est le **modele exact** a suivre. Ce programme cree deja des garanties automatiquement pendant le batch de nuit (traitement arrivants).

| Element | Valeur |
|---------|--------|
| **Projet** | REF |
| **IDE** | 667 |
| **PublicName** | `AFF_GARANTIE_CLUB` |
| **Taches** | 5 (dont 1 SQL, 1 boucle GM, 1 creation garantie, 1 mails) |
| **Parametre** | P1 = "Du Traitement Arrivants" (Logical) |

### Programme creation : ADH IDE 111 - Garantie sur compte (`GARANTIE`)

Programme de creation/MAJ de garantie sur un compte GM. 17 parametres, gere uni/bi-devise, ecrit dans `depot_garantie`, `compte_gm`, `historik_station`.

### Programme cautions : ADH IDE 165 - Saisies cautions

Programme de saisie manuelle de cautions (articles loues). Utilise `arc_pv_cust_rentals` et `req_param`.

### Batch cloture : EXB IDE 8 - Menu cloture

Point d'entree de la cloture de nuit (24 taches). Sequence : Edition ventes -> Blocage reseau -> Incrementation date comptable -> Deblocage.

### Utilitaire age : PBP IDE 307 - Recherche age Bebe_Enfant

Programme standard pour determiner l'age bebe/enfant. Appele par 20+ programmes.

---

## 3. Tracage Flux

### Flux actuel de la cloture de nuit

```
EXB IDE 1 (Main)
  -> EXB IDE 31 (Menu general)
       -> EXB IDE 8 (Menu cloture)
            |
            +-> Edition des ventes (EXB IDE 9)
            +-> Blocage reseau
            +-> Incrementation date comptable
            +-> Deblocage cloture
```

### Flux du modele AFF_GARANTIE_CLUB (REF IDE 667)

```
REF IDE 667 - Affectation de Garantie
  |
  +-> 667.2 - Check Nb Arrivants (SQL)
  |   SELECT COUNT(*) FROM cafil008_dat (GM)
  |   JOIN cafil012_dat (hebergement)
  |   WHERE debut_sejour = Date()
  |     AND qualite = 'GM'
  |     AND type_chambre IN ('ORDI','VSL','IGP','IGP2','CLUB')
  |
  +-> CONDITION : NbArrivants >= Seuil (pms_village col.52)
  |
  +-> 667.1 - Boucle sur GM arrivants
  |   |
  |   +-> POUR CHAQUE GM :
  |       |
  |       +-> CONDITION :
  |       |   - Pas de garantie existante
  |       |   - Type hebergement IN ('ORDI','VSL','IGP','IGP2','CLUB')
  |       |   - Si seuil > 0 : sejour > 3 jours
  |       |
  |       +-> 667.1.1 - Creation Garantie
  |       |   - INSERT depot_garantie (cafil017)
  |       |     code='CLUB', libelle='AFFAUTO'
  |       |   - UPDATE compte_gm (cafil025)
  |       |
  |       +-> 667.1.2 - Mails (si appel manuel uniquement)
  |
  +-> Log batch (REF IDE 829)
```

### Flux propose pour la caution ski (NOUVEAU)

```
NOUVEAU PROGRAMME - Caution Ski Auto (type REF ou VIL)
  |
  +-> Verifier code projet actif (table motif_no_enreg_na 768)
  |   SI code projet inactif -> LOG + FIN
  |
  +-> Compter arrivants eligibles (SQL)
  |   SELECT COUNT(*) FROM cafil008_dat
  |   JOIN cafil012_dat (hebergement)
  |   JOIN cafil011_dat (prestations)
  |   WHERE debut_sejour = Date()
  |     AND qualite = 'GM'
  |     AND gmr_valide = 'O'                    -- GM valides uniquement
  |     AND age >= 6                             -- Exclure < 6 ans
  |     AND NOT EXISTS prestation 'SMRNS1'       -- Exclure code presta
  |     AND NOT EXISTS garantie ski existante    -- Eviter doublons
  |
  +-> Boucle sur GM eligibles
  |   |
  |   +-> POUR CHAQUE GM :
  |       +-> Verifier age >= 6 ans (date naissance)
  |       +-> Verifier pas de code presta SMRNS1 (cafil011_dat)
  |       +-> Verifier GM valide
  |       +-> Verifier pas de garantie ski existante
  |       |
  |       +-> Creation Garantie Ski
  |           - INSERT depot_garantie (cafil017)
  |             type='SKI', montant=25, devise='CHF'
  |           - UPDATE compte_gm (cafil025)
  |           - TRACE historik_station (cafil066)
  |
  +-> Log batch (REF IDE 829)
  +-> Rapport PDF (optionnel)
```

---

## 4. Tables concernees

### Tables en lecture

| Table | Nom physique | Usage |
|-------|-------------|-------|
| **30** cafil008_dat | gm-recherche | Boucle sur GM arrivants du jour |
| **34** cafil012_dat | hebergement | Jointure dates sejour, type chambre |
| **33** cafil011_dat | prestations | **Verification code presta SMRNS1** |
| **91** cafil069_dat | types garantie | Lookup type garantie SKI + montant |
| **39** cafil017_dat | depot_garantie | Verification garantie existante (eviter doublons) |
| **368** pmsvillage | config village | Devise locale (CHF), seuils |
| **69** cafil047_dat | initialisation | Parametres generaux |
| **768** motif_no_enreg_na | codes projet | **Activation/desactivation par code projet** |

### Tables en ecriture

| Table | Nom physique | Usage |
|-------|-------------|-------|
| **39** cafil017_dat | depot_garantie | **Creation enregistrement caution ski** |
| **47** cafil025_dat | compte_gm | MAJ compteur compte |
| **88** cafil066_dat | historik_station | Trace historique (CGAR) |

### Structure depot_garantie (cafil017_dat) - colonnes cles

| Colonne | Nom | Valeur pour caution ski |
|---------|-----|------------------------|
| 1 | dga_societe | Code societe du village |
| 2 | dga_code_gm | Numero compte GM |
| 3 | dga_filiation | Filiation GM |
| 4 | dga_date_depot | Date() (jour arrivee) |
| 5 | dga_heure_depot | Time() |
| 8 | dga_type_depot | **'SKI'** (a definir) |
| 9 | dga_devise | **'CHF'** |
| 10 | dga_montant | **25.000** |
| 11 | dga_etat | 'C' (creation) |
| 12 | dga_operateur | 'BATCH' ou 'CAUTSKI' |
| 21 | dga_fapplication_ouv | 'O' (ouvert) |

### Structure prestations (cafil011_dat) - verification exclusion

| Colonne | Nom | Usage |
|---------|-----|-------|
| 1 | pre_societe | Filtre societe |
| 2 | pre_num_compte | Filtre compte GM |
| 3 | pre_filiation | Filtre filiation |
| 4 | pre_code_circuit | **= 'SMRNS1' pour exclusion** |
| 5 | pre_date_debut | Verification periode |
| 6 | pre_date_fin | Verification periode |

---

## 5. Specification de la solution

### Architecture proposee

**Option recommandee** : Creer un **nouveau programme** base sur le modele de REF IDE 667 (`AFF_GARANTIE_CLUB`).

| Aspect | Choix | Justification |
|--------|-------|---------------|
| **Projet** | REF (ou VIL si specifique St Moritz) | Reutilise les memes tables REF partagees |
| **Modele** | Copie de REF IDE 667 | Structure identique : SQL check + boucle + creation |
| **Appel** | Via ProgIdx depuis le traitement arrivants PBG | Comme AFF_GARANTIE_CLUB |
| **Activation** | Code projet (table 768) | Configurable par village |

### Parametres du nouveau programme

| # | Nom | Type | Description |
|---|-----|------|-------------|
| 1 | P.i.Du Traitement Arrivants | Logical | TRUE si batch nuit |
| 2 | P.i.Code Village | Alpha(4) | Code village (pour filtre SMRC) |

### Conditions d'eligibilite (GM par GM)

```
POUR CHAQUE GM arrivant (debut_sejour = Date()) :
  1. gmr_qualite = 'GM'                                    -- GM uniquement
  2. gmr_valide = 'O' (ou equivalent)                      -- GM valides
  3. Age >= 6 ans (Date() - gmc_date_naissance >= 6 ans)   -- Pas les bebes
  4. NOT EXISTS prestations WHERE code = 'SMRNS1'           -- Pas le code presta
  5. NOT EXISTS depot_garantie type='SKI' pour ce GM        -- Pas de doublon
  6. type_hebergement IN ('ORDI','VSL','IGP','IGP2','CLUB') -- Hebergement Club
```

### Valeurs d'insertion dans depot_garantie

| Champ | Valeur | Source |
|-------|--------|--------|
| dga_societe | societe village | Parametre ou pms_village |
| dga_code_gm | numero compte | Boucle GM |
| dga_filiation | filiation | Boucle GM |
| dga_date_depot | Date() | Fonction Magic |
| dga_heure_depot | Time() | Fonction Magic |
| dga_type_depot | Code type garantie SKI | cafil069_dat ou constante |
| dga_devise | 'CHF' | pms_village.devise_locale |
| dga_montant | 25.000 | Configurable (cafil069_dat ou constante) |
| dga_etat | 'C' | Creation |
| dga_operateur | 'CAUTSKI' | Identifiant batch |
| dga_fapplication_ouv | 'O' | Ouvert |

### Diagramme de la solution

```
┌─────────────────────────┐
│ PBG IDE 206             │ Traitement des arrivants (batch nuit)
│ Traitement Arrivants    │
└────────────┬────────────┘
             │ CallTask / ProgIdx
             ▼
┌─────────────────────────┐
│ NOUVEAU PROGRAMME       │ Caution Ski Automatique
│ "CAUTION_SKI_AUTO"      │ (modele: REF IDE 667)
└────────────┬────────────┘
             │
     ┌───────┴───────┐
     ▼               ▼
┌──────────┐  ┌──────────────────┐
│ Verif    │  │ Boucle GM        │
│ Code     │  │ arrivants        │
│ Projet   │  │ eligibles        │
│ (768)    │  └────────┬─────────┘
└──────────┘           │
                ┌──────┴──────┐
                ▼             ▼
          ┌──────────┐  ┌──────────┐
          │ Verif    │  │ Creation │
          │ exclus.  │  │ garantie │
          │ SMRNS1   │  │ 25 CHF   │
          │ age < 6  │  │ (39)     │
          │ valide   │  └──────────┘
          └──────────┘
```

---

## 6. Points d'attention

### Ambiguite code village

Le ticket mentionne "SMRC" mais les notes precedentes mentionnent "SMO". A clarifier avec le demandeur.

### Montant configurable vs fixe

Le ticket dit "25 CHF". Deux options :
- **Fixe dans le code** : simple mais rigide
- **Configurable dans cafil069_dat** : creer un type garantie "SKI" avec montant=25 dans la table des types garantie. Plus flexible (modifiable sans toucher au code).

**Recommandation** : Configurable via cafil069_dat pour permettre des ajustements sans recompilation.

### Code projet

Le ticket demande "cela devra fonctionner avec un code projet". Cela signifie :
- Creer un code projet dans la table `motif_no_enreg_na` (768)
- Verifier l'activation de ce code au debut du traitement
- Permet d'activer/desactiver la caution ski par village sans toucher au code

### Verification doublon

Il est critique de verifier qu'une caution ski n'existe pas deja pour ce GM (meme sejour). Sinon le batch recreerait la caution chaque nuit.

### Retrait automatique de la caution

Le ticket ne mentionne pas le retrait de la caution au depart. A clarifier : la caution doit-elle etre retiree automatiquement quand le ski pass est rendu ? Ou est-ce un processus manuel ?

### Programme de desaffectation

PBP IDE 123 - Desaffectation de Garantie existe et pourrait servir de modele pour le retrait automatique si necessaire.

---

## 7. Checklist implementation

- [ ] Clarifier code village exact (SMRC vs SMO)
- [ ] Creer type garantie "SKI" dans cafil069_dat avec montant 25 CHF
- [ ] Creer code projet dans motif_no_enreg_na (768) pour activation
- [ ] Creer nouveau programme base sur REF IDE 667
- [ ] Ajouter verification code presta SMRNS1 (table cafil011_dat)
- [ ] Ajouter verification age >= 6 ans (date naissance)
- [ ] Ajouter verification GM valide
- [ ] Ajouter verification doublon garantie ski existante
- [ ] Integrer appel depuis traitement arrivants PBG
- [ ] Tester sur base CSK0912 avec donnees St Moritz
- [ ] Clarifier le processus de retrait de caution
- [ ] Documenter dans REF IDE 829 (Log batch)

---

## 8. Programmes references

| Programme | Role dans la solution |
|-----------|---------------------|
| **REF IDE 667** - AFF_GARANTIE_CLUB | Modele a copier/adapter |
| **ADH IDE 111** - GARANTIE | Reference creation garantie (17 params) |
| **ADH IDE 165** - Saisies cautions | Reference saisie manuelle |
| **PBG IDE 206** - Traitement arrivants | Point d'appel du nouveau batch |
| **PBP IDE 307** - Recherche age Bebe_Enfant | Utilitaire calcul age |
| **REF IDE 829** - Log batch | Tracabilite |
| **PBP IDE 123** - Desaffectation garantie | Modele pour retrait (si necessaire) |

---

## 9. Commits / Historique

*A completer lors de l'implementation*

---

*Analyse realisee avec: Claude Code + MCP Magic Tools*
*Pipeline version: 2.0 (analyse manuelle enrichie)*
