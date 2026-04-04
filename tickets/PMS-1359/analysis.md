# PMS-1359 - Analyse Technique Detaillee

> **Jira** : [PMS-1359](https://clubmed.atlassian.net/browse/PMS-1359)
> **Protocole** : `.claude/protocols/ticket-analysis.md` applique
> **Date analyse** : 2026-01-22 (v1), 2026-02-17 (v2 - root cause trouvee)

---

## 1. Contexte Jira

### Informations ticket

| Element | Valeur |
|---------|--------|
| **Titre** | Edition Cloture (suite) |
| **Type** | Story (nouvelle fonctionnalite) |
| **Statut Jira** | Resolu (mais bug persistant) |
| **Priorite** | Basse |
| **Reporter** | Jessica Palermo |
| **Assignee** | Anthony Leberre |
| **Label** | VIL |
| **Cree le** | 2025-08-26 |
| **Commit initial** | `9422490b5` (01/10/2025) |

### Description originale

> "Il faudrait mettre `**` sur le document qui arrive ce jour dans la colonne FDR initial
> afin de prevenir que le montant de fermeture de la veille etait different de celui ci.
> Il se peut que la case soit vide, il faudra donc avoir quand meme les `**`"

### Retours recette (probleme persistant)

| Date | Commentaire Jessica |
|------|-------------------|
| 2025-10-24 | Voit des etoiles sur coffre 2 alors qu'elle a touche la caisse de Nunziato |
| 2026-02-06 | Screenshots montrant que ca ne fonctionne toujours pas |
| 2026-02-06 | "Le 4/02 j'etais a 300 EUR de monnaie, j'aurais du voir les etoiles" |

---

## 2. Localisation Programme

| Parametre | Valeur |
|-----------|--------|
| **Projet** | VIL |
| **Position IDE** | **22** |
| **Nom** | **Print recap sessions** |
| **Fichier XML** | Prg_558.xml (ISN=558) |

### Arborescence concernee

```
VIL IDE 22 - Print recap sessions
├── 22.16 (ISN_2=18) - Edition
│   └── 22.16.1 (ISN_2=19) - Reception     ← TACHE PRINCIPALE
│       └── 22.16.1.1 (ISN_2=56) - Update FDR Precedent  ← LOGIQUE LECTURE
│           ├── 22.16.1.1.1 (ISN_2=57) - CAISSE v1
│           └── 22.16.1.1.2 (ISN_2=58) - CAISSE T2H
```

---

## 3. Tables Identifiees

| N° Table | Nom logique | Role |
|----------|-------------|------|
| **246** | histo_sessions_caisse | Session J-1 (chrono-1, user, date) |
| **249** | histo_sessions_caisse_detail | Montant FDR fermeture type='F' |
| **471** | comptage_coffre_devise | Source principale (comptage) |
| **594** | temp recap sessions | Table temporaire edition |

---

## 4. ROOT CAUSE IDENTIFIEE

### Expressions creees mais NON BRANCHEES dans le template

Dans la tache 22.16.1 (Reception), 4 expressions gèrent l'affichage `*`/`**` :

| Expression | Formule | But | Dans MERGE_PARM ? |
|------------|---------|-----|:------------------:|
| **33** | `Trim(Str({0,5},{2,4})&IF({0,76},'*',''))` | FDR Final + `*` si ecart ligne | **OUI** |
| **34** | `Trim(Str({0,5},{2,4})&IF({0,75},'*',''))` | FDR Final + `*` si ecart ligne | **OUI** |
| **35** | `Trim(Str({0,4},{2,4})&IF({0,78},'**',''))` | FDR Initial + `**` si ecart FDR | **NON** |
| **36** | `Trim(Str({0,4},{2,4})&IF({0,79},'**',''))` | FDR Initial + `**` si ecart FDR | **NON** |

**Les expressions 33/34 (FDR Final avec `*`) FONCTIONNENT** car elles sont referencees
dans les MERGE_PARM du template `sessions2.htm`.

**Les expressions 35/36 (FDR Initial avec `**`) NE FONCTIONNENT PAS** car elles ne sont
referencees NULLE PART dans les MERGE_PARM.

### MERGE_PARM actuels vs corriges

**Form 3 - "Merge Coffre 2"** (ligne 18094 du XML) :

| Tag HTML | Expression actuelle | Expression correcte |
|----------|-------------------|-------------------|
| `FDRICOFFRE2` | `Exp="8"` (somme numerique) | `Exp="35"` (FDR + `**` si ecart) |
| `FDRCOFFRE2` | `Exp="34"` (FDR Final + `*`) | OK - deja correct |

**Form 4 - "Merge Recept."** (ligne 18135 du XML) :

| Tag HTML | Expression actuelle | Expression correcte |
|----------|-------------------|-------------------|
| `FDRIRECEP2` | `Exp="9"` (valeur brute) | `Exp="36"` (FDR + `**` si ecart) |
| `FDRRECEP` | `Exp="33"` (FDR Final + `*`) | OK - deja correct |

### Variables ecart (correctement implementees)

| Variable | Column | Nom | Type | Correcte ? |
|----------|--------|-----|------|:----------:|
| **EX** | 39 | v.Ecart F.D.R. COFFRE2 | Logical | OUI |
| **EY** | 40 | v.Ecart F.D.R. RECEPTION ? | Logical | OUI |
| **EU** | 41 | v.FDR fermeture de la veille | Numeric | OUI |
| **EV** | 42 | v.Session de Fermeture prec exi | Logical | OUI |

La logique de lecture J-1 (tache 22.16.1.1) et les flags ecart sont corrects.
Seul le branchement dans le template d'impression manque.

---

## 5. Fix Propose

### Modification XML dans Prg_558.xml

**Fix 1 - Form "Merge Coffre 2" (ligne 18094)** :

```xml
<!-- AVANT -->
<MERGE_PARM Exp="8" PIC_U="30" TXT_U="FDRICOFFRE2" id="10"/>
<!-- APRES -->
<MERGE_PARM Exp="35" PIC_U="30" TXT_U="FDRICOFFRE2" id="10"/>
```

**Fix 2 - Form "Merge Recept." (ligne 18135)** :

```xml
<!-- AVANT -->
<MERGE_PARM Exp="9" PIC_U="30" TXT_U="FDRIRECEP2" id="54"/>
<!-- APRES -->
<MERGE_PARM Exp="36" PIC_U="30" TXT_U="FDRIRECEP2" id="54"/>
```

### Points a verifier

1. **Expression 8 vs 35** : Verifier que Expression 35 produit bien la meme valeur
   FDR Initial que Expression 8, en plus du `**`. Si Exp 8 fait un calcul different
   (somme), il faudra peut-etre garder Exp 8 pour d'autres tags et ajouter un
   NOUVEAU MERGE_PARM avec Exp 35.

2. **Croisement coffres** : Jessica voit des etoiles sur coffre 2 quand elle touche
   une autre caisse. A verifier si le filtre utilisateur dans la tache 22.16.1.1
   (Expression 9 = `IF(Trim(DI)='COFFRE 2'...)`) est correct.

3. **Cas "case vide"** : Si FDR Initial = 0 (case vide), verifier que les expressions
   35/36 affichent quand meme `**` si ecart. `Str(0, picture)` pourrait retourner
   une chaine vide ou "0" — `Trim("0**")` vs `Trim("**")`.

---

## 6. Tests de Recette

| # | Scenario | Resultat attendu |
|---|----------|------------------|
| 1 | FDR Initial = FDR Fermeture veille | Pas de `**` sur FDRI |
| 2 | FDR Initial != FDR Fermeture veille | `**` affiche apres le montant |
| 3 | FDR Initial vide, fermeture veille existante | `**` affiche (case "vide") |
| 4 | Premiere session (pas de J-1) | Pas de `**` |
| 5 | COFFRE2 modifie, RECEPTION non | `**` uniquement sur ligne COFFRE2 |
| 6 | RECEPTION modifie, COFFRE2 non | `**` uniquement sur ligne RECEPTION |
| 7 | Multi-sessions meme jour | Verifier chrono correct |

---

## 7. Checklist Validation

- [x] Programme identifie avec position IDE verifiee
- [x] Tables identifiees avec numeros
- [x] Expressions decodees avec formules lisibles
- [x] Root cause documentee avec localisation exacte
- [x] Diagramme flux present
- [x] Fix propose avec lignes XML exactes
- [x] Tests de recette definis

---

*Analyse v1 : 2026-01-22 (structure + variables)*
*Analyse v2 : 2026-02-17 (root cause : MERGE_PARM non branches)*
