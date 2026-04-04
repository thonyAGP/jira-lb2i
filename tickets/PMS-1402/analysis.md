# Analyse PMS-1402

> **Jira** : [PMS-1402](https://clubmed.atlassian.net/browse/PMS-1402)

## Symptome

**Automatisation Taxe de sejour**

Actuellement, la taxe de sejour est geree manuellement par le Night Audit :
1. Impression de la liste mecano du jour
2. Ouverture du compte GM en club (si non ouvert)
3. Calcul manuel de la taxe et posting sur le compte
4. Fermeture du compte en garantie club

**Risques identifies :**
- Mauvais calcul manuel
- Prolongations non modifiees (n'apparaissent pas dans la mecano)
- Arrivees differees : taxe non ajoutee

## Contexte

| Element | Valeur |
|---------|--------|
| **Type** | Story (evolution) |
| **Statut** | Blocage ou attente infos |
| **Priorite** | Haute |
| **Reporter** | Jessica Palermo |
| **Assignee** | Eric Rebibo |
| **Labels** | ADH, PBG |
| **Cree** | 2025-11-06 |

---

## Besoins fonctionnels

### 1. Calcul automatique veille de depart

**Declencheur** : Batch de nuit, veille de depart du GM

**Logique** :
```
SI GM exonere ALORS
    RAS (pas de taxe)
SINON
    nb_nuits = calculer_nuits_sejour(date_arrivee, date_depart)
    nb_nuits_facturables = MIN(nb_nuits, max_jours_payants)
    montant = nb_nuits_facturables * prix_journalier
    poster_OD(compte_GM, montant, compte_467635000)
FIN SI
```

**Points d'attention** :
- Calcul PAR PERSONNE (pas par chambre)
- Arrivee differee : prendre date de validation, pas date prevue
- Respect du maximum de jours payants (ex: 7 nuits max a Cefalu)

### 2. Gestion des prolongations

**Declencheur** : Batch de nuit detecte modification de date depart

**Logique** :
```
SI date_depart modifiee ALORS
    nb_nuits_deja_facturees = lire_historique()
    SI nb_nuits_deja_facturees < max_jours_payants ALORS
        nb_nuits_supplementaires = calculer_supplement()
        poster_OD(compte_GM, supplement, compte_467635000)
    FIN SI
FIN SI
```

### 3. Anniversaire pendant sejour

**Cas particulier** : GM exonere au debut mais devient eligible pendant le sejour

**Logique** :
```
SI anniversaire_pendant_sejour ET devient_eligible ALORS
    calculer_taxe_depuis_date_anniversaire()
FIN SI
```

### 4. Annulation par utilisateur

**Acces** : Caisse Adherent (comme OD normale)
- Credit sur compte GM
- Justificatif obligatoire (existant)

---

## Programmes Magic concernes

### Programmes existants a modifier

| Programme | Projet | Role | Modification |
|-----------|--------|------|--------------|
| **REF IDE 684** | REF | Lancement Tempo Mecano | Point d'integration batch |
| **REF IDE 687** | REF | Preparation Mecano | Donnees GM/sejour |
| **REF IDE 690-692** | REF | Traitement Mecano 1/2/3 | Logique existante |
| **PBG IDE 116** | PBG | Arrivee/Depart | Dates sejour |

### Programmes a creer

| Programme | Projet | Role |
|-----------|--------|------|
| **TAXE_SEJOUR_BATCH** | PBG | Calcul et posting automatique |
| **TAXE_SEJOUR_CONFIG** | REF | Lecture parametrage Planning Setup |

### Tables concernees

| Table | Projet | Role |
|-------|--------|------|
| **cafil014_dat** | REF | Hebergement GM (dates sejour) |
| **operations_dat** | REF | Posting OD |
| **Table config taxe** | ? | Parametrage (max jours, prix, exonerations) |

---

## Parametrage existant

**Emplacement** : Planning Setup > Utilitaire > Parametrage taxe de sejour

**Champs a exploiter** :
- Prix journalier par type de personne (adulte/enfant)
- Duree maximale de jours payants
- Regles d'exoneration (age, statut, etc.)
- Compte comptable destination (467635000)

---

## Article a creer

| Propriete | Valeur |
|-----------|--------|
| **Type** | Taxe de sejour |
| **Groupe** | GESTION |
| **Modifiable** | NON |
| **Compte comptable** | 467635000 |

---

## Questions en suspens

1. **Structure table config** : Ou est stocke le parametrage "taxe de sejour" de Planning Setup ?
2. **Identification exoneres** : Quel champ/table indique si un GM est exonere ?
3. **Arrivee differee** : Comment identifier la date de validation effective ?
4. **Multi-resort** : Chaque resort a ses propres regles - comment gerer ?

---

## Commentaires Jira

**Anthony Leberre (2025-11-27)** :
> Besoin d'informations sur actuellement comment est poste la vente.

**Jessica Palermo (2026-01-12)** :
> C'est poste manuellement par le night audit :
> 1. le night imprime la liste mecano du jour
> 2. il ouvre le compte en club si le compte n'est pas ouvert
> 3. il calcule la taxe et la poste sur le compte
> 4. il referme le compte en garantie club si il l'avait ouvert

---

## Prochaines etapes

1. [ ] Identifier la table de configuration taxe de sejour
2. [ ] Analyser le batch de nuit existant (point d'integration)
3. [ ] Definir la structure du nouveau programme TAXE_SEJOUR_BATCH
4. [ ] Valider les regles d'exoneration avec le metier
5. [ ] Estimer l'effort de developpement

---

*Derniere mise a jour: 2026-01-13*
*Status: ANALYSE INITIALE - Questions en suspens*

---

*DerniÃ¨re mise Ã  jour : 2026-01-22T18:55*
