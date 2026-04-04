# CMDS-183643-X : Equipement perdu dans POS

> **Analyse** : 2026-02-25
> **Statut Jira** : Ferme (sans fix)
> **Priorite** : Moderee
> **Reporter** : Responsable Ski Pro Shop Val Thorens Sensations

---

## 1. Symptome

Les codes equipement saisis manuellement dans ADH/POS sur les lignes PREPAID d'un client **disparaissent** apres le traitement des arrivants.

- Le search equipement retourne une page vierge
- Les lignes PREPAID sont presentes mais les codes sont vides
- Probleme constate depuis ~2 semaines (au moment du ticket)
- ~6 cas en 2 semaines au Pro Shop Ski VTH

---

## 2. Cause racine

### Flux defaillant

```
1. Operateur saisit codes equipement dans ADH/POS
   → Ecriture dans pv_globalca_prepaid (codes sur lignes PREPAID)

2. Modification dossier client (ex: changement sejour, extension)
   → Declenche PBG IDE 206 (Traitement des arrivants)

3. IDE 206, tache 206.1 (Import Client)
   → Appelle PBG IDE 82 (Suppression Client)
   → DELETE COMPLET de pv_globalca_prepaid pour ce client
   → 30 tables effacees au total

4. Chaine de validation (IDE 121/122/124)
   → Appelle PBG IDE 64 (Ecriture log valid devalid)
   → Tache 64.2 : CREATE nouvelles lignes PREPAID
   → Seuls P.Compte et P.Filiation sont reinjectes
   → Les codes equipement ne sont PAS recopies

5. Resultat : lignes PREPAID recreees avec nouveau numero
   → Codes equipement = VIDES
```

### Schema

```
                    ┌──────────────────┐
                    │  ADH / POS       │
                    │  Saisie codes    │
                    │  equipement      │
                    └────────┬─────────┘
                             │ WRITE codes dans pv_globalca_prepaid
                             ▼
                    ┌──────────────────┐
                    │  pv_globalca_    │
                    │  prepaid         │
                    │  (avec codes)    │
                    └────────┬─────────┘
                             │
        Modification dossier │
                             ▼
                    ┌──────────────────┐
                    │  PBG IDE 206     │
                    │  Traitement      │
                    │  arrivants       │
                    └────────┬─────────┘
                             │
                    ┌────────▼─────────┐
                    │  PBG IDE 82      │
                    │  Suppression     │──── DELETE pv_globalca_prepaid
                    │  Client          │     (codes equipement PERDUS)
                    └────────┬─────────┘
                             │
                    ┌────────▼─────────┐
                    │  PBG IDE 64      │
                    │  Ecriture log    │──── CREATE nouvelles lignes
                    │  valid devalid   │     (SANS codes equipement)
                    └──────────────────┘
```

### Programmes concernes

| IDE | Programme | Role dans le bug | Tables impactees |
|-----|-----------|------------------|------------------|
| **206** | Traitement des arrivants | Orchestrateur | 9 tables |
| **82** | Suppression Client | Efface les lignes PREPAID | 30 tables (dont pv_globalca_prepaid) |
| **64** | Ecriture log valid devalid | Recree les lignes PREPAID sans codes | pv_globalca_prepaid (3 usages) |

### Table cle

| Table | ID | Nom technique | Role |
|-------|-----|---------------|------|
| 832 | pv_globalca_prepaid | Lignes PREPAID avec codes equipement | Stockage CA prepaid + equipement |

---

## 3. Lien avec pattern existant

Le pattern `extension-treated-as-arrival.md` (source: CMDS-176481) decrit un mecanisme similaire :

| Aspect | CMDS-176481 | CMDS-183643 |
|--------|-------------|-------------|
| **Declencheur** | Extension sejour (VSL) | Modification dossier |
| **Mecanisme** | Traite comme nouvelle arrivee | Traite comme nouvelle arrivee |
| **Effet** | Double attribution credit | Perte codes equipement |
| **Racine commune** | Effacer/recreer au lieu de mettre a jour en place |

**Conclusion** : Meme famille de bug. Le traitement arrivants est trop agressif — il fait un DELETE+CREATE au lieu d'un UPDATE.

---

## 4. Specification du fix

### 4.1 Approche recommandee : Sauvegarde/Restauration des codes equipement

**Principe** : Avant la suppression par IDE 82, sauvegarder les codes equipement des lignes PREPAID, puis les reinjecter apres la recreation par IDE 64.

#### Etape 1 — Sauvegarde (AVANT appel IDE 82)

Dans **PBG IDE 206**, tache 206.1, AVANT l'appel a IDE 82 :

```
GIVEN le traitement des arrivants est declenche pour un client
WHEN le client possede des lignes pv_globalca_prepaid avec codes equipement non vides
THEN le systeme SHALL sauvegarder en memoire :
  - Numero de compte (P.Compte)
  - Filiation (P.Filiation)
  - Code(s) equipement
  - Toute donnee metier saisie manuellement
```

#### Etape 2 — Suppression (inchangee)

IDE 82 continue a effacer normalement les 30 tables.

#### Etape 3 — Restauration (APRES recreation par IDE 64)

Dans **PBG IDE 64**, tache 64.2, APRES la creation des nouvelles lignes :

```
GIVEN de nouvelles lignes pv_globalca_prepaid ont ete creees
WHEN des codes equipement avaient ete sauvegardes a l'etape 1
THEN le systeme SHALL restaurer les codes equipement sur les lignes correspondantes
  en faisant correspondre par Compte + Filiation
```

### 4.2 Approche alternative : UPDATE au lieu de DELETE+CREATE

**Principe** : Modifier IDE 82 pour ne pas supprimer les lignes PREPAID qui ont des codes equipement.

```
GIVEN IDE 82 est appele pour supprimer un client
WHEN une ligne pv_globalca_prepaid contient un code equipement non vide
THEN le systeme SHALL conserver cette ligne intacte
  ET le systeme SHALL uniquement mettre a jour les champs non-equipement
```

**Avantage** : Plus simple, pas de sauvegarde/restauration.
**Risque** : Peut laisser des lignes orphelines si le client est reellement supprime (pas une modification).

### 4.3 Comparaison approches

| Critere | Approche 1 (Save/Restore) | Approche 2 (Skip DELETE) |
|---------|---------------------------|--------------------------|
| Complexite | Moyenne | Faible |
| Risque regression | Faible | Moyen (lignes orphelines) |
| Impact sur IDE 82 | Aucun | Modification logique |
| Impact sur IDE 206 | Ajout sauvegarde avant appel | Aucun |
| Impact sur IDE 64 | Ajout restauration apres create | Aucun |
| Cas suppression reelle | OK (rien a restaurer) | Risque lignes restantes |

**Recommandation** : Approche 1 (Save/Restore) — plus sure, pas d'effet de bord sur les autres 8 callers de IDE 82.

---

## 5. Acceptance Criteria

| # | Critere | Verification |
|---|---------|-------------|
| AC-1 | Les codes equipement saisis dans ADH/POS DOIVENT survivre au traitement des arrivants | Saisir code → declencher traitement → verifier code present |
| AC-2 | Le traitement des arrivants DOIT continuer a fonctionner normalement pour les clients sans equipement | Traitement standard sans regression |
| AC-3 | La suppression reelle d'un client (hors traitement arrivants) NE DOIT PAS etre affectee | IDE 82 appele depuis IDE 228/234/238 fonctionne normalement |
| AC-4 | Le search equipement DOIT retourner les resultats apres traitement arrivants | Verifier recherche post-traitement |

---

## 6. Tests de validation

### Scenario 1 : Cas nominal (reproduction du bug)
```
GIVEN un client EASY avec lignes PREPAID
AND des codes equipement saisis dans ADH/POS
WHEN le traitement des arrivants est declenche (modification dossier)
THEN les codes equipement sont preserves sur les lignes PREPAID
AND le search equipement retourne les bons resultats
```

### Scenario 2 : Client sans equipement
```
GIVEN un client avec lignes PREPAID sans code equipement
WHEN le traitement des arrivants est declenche
THEN le traitement se deroule normalement (pas de regression)
```

### Scenario 3 : Suppression reelle
```
GIVEN un client avec codes equipement
WHEN IDE 82 est appele depuis IDE 228 (annulation)
THEN les lignes PREPAID sont supprimees normalement
AND les codes equipement sont supprimes (comportement attendu)
```

### Scenario 4 : Codes partiels
```
GIVEN un client avec 3 lignes PREPAID dont 1 seule a un code equipement
WHEN le traitement des arrivants est declenche
THEN seul le code existant est preserve
AND les 2 autres lignes sont recreees normalement
```

---

## 7. Perimetre d'impact

| Programme | Modification | Risque |
|-----------|-------------|--------|
| PBG IDE 206 | Ajout sauvegarde codes avant appel IDE 82 | Faible |
| PBG IDE 64 | Ajout restauration codes apres creation | Faible |
| PBG IDE 82 | Aucune modification | Nul |
| ADH (POS) | Aucune modification | Nul |
| 8 autres callers IDE 82 | Non impactes | Nul |

---

## 8. Informations manquantes

| Element | Statut | Action requise |
|---------|--------|----------------|
| Structure colonnes pv_globalca_prepaid | Inconnue | Extraire schema table depuis DB |
| Nom exact du champ "code equipement" | Inconnu | Verifier dans DataView ADH |
| Tache exacte dans IDE 206 qui appelle IDE 82 | 206.1 (confirme) | OK |
| Frequence du bug en production | ~6 cas / 2 semaines (VTH) | Verifier autres villages |
