# PMS-1479 - Resolution

## Status: BUG CONFIRME - CAUSE RACINE IDENTIFIEE

### Verdict

| Element | Valeur |
|---------|--------|
| **Type** | Bug de donnees (WRITE) |
| **Severite** | Moderee |
| **Cause racine** | Le programme Vente (ADH IDE 237 et variants) ecrit le nom du SERVICE ("Caisse") dans `cte_libelle` au lieu de la description de l'OD ("TAXE DE SEJOUR"). Le DEVERSEMENT (ADH IDE 247) copie fidelement cette valeur dans la table comptable. |
| **Programme source** | **Programme Vente** (ADH IDE 237 "Vente GP" ou equivalent) qui cree le record dans la table vente/temp avec le mauvais libelle |
| **Programme transfert** | ADH IDE 247 "Deversement Transaction" (Prg_243.xml) - non fautif, copie fidelement |
| **Expressions cles** | Exp 11: `IF(NOT(VG46) OR type='O', {1,19}, {0,44})` → pour OD, utilise {1,19} = col 6 source |

### Ce qui est confirme

1. `cte_libelle` contient "Caisse" (nom du service GEST dans VSERV) → **INCORRECT**
2. `cte_libelle_supplem_` contient "TAXE SEJOURS" → **CORRECT**
3. Le bug est dans l'**ecriture du record source** (pas dans DEVERSEMENT ni dans l'affichage)
4. **ADH IDE 247 "Deversement Transaction"** (Prg_243.xml) cree physiquement les OD dans cafil018_dat via subtask 247.2 (ISN_2=3) "creation d'un O.D. v1"
5. Ce programme copie fidelement col 6 → `cte_libelle` et col 7 → `cte_libelle_supplem_` depuis sa table source
6. **15 programmes Vente** appellent DEVERSEMENT via CallTask
7. **ADH IDE 105** ne cree PAS les OD - il met uniquement a jour num_facture et flag sur des records existants
8. **PBG IDE 343** calcule le montant de la taxe mais ne touche ni la table vente ni la table comptable

### Mecanisme precis du bug

```
1. Programme Vente (ex: Vente GP) cree un record OD taxe de sejour:
   - col 6 (libelle)       = lookup VSERV → tab_libelle20 du service = "Caisse"
   - col 7 (libelle_supp)  = description OD = "TAXE SEJOURS"

2. DEVERSEMENT (IDE 247) est appele comme sous-tache:
   - Itere la table source des transactions
   - Subtask "creation O.D. v1" (ISN_2=3):
     - cte_libelle ← Expression 11 → {1,19} = col 6 source = "Caisse"
     - cte_libelle_supplem_ ← Expression 12 → {1,20} = col 7 source = "TAXE SEJOURS"

3. Resultat dans cafil018_dat:
   - cte_libelle = "Caisse" (mauvais)
   - cte_libelle_supplem_ = "TAXE SEJOURS" (correct)
```

### Pistes de correction

#### Option A : Corriger dans le programme Vente (RECOMMANDE)

Modifier le programme Vente (ADH IDE 237 et variants) pour utiliser la **description de l'OD** comme libelle principal quand `code_type = 'O'`.

**Avantages:** Corrige la cause racine. Toutes les futures OD auront le bon libelle.
**Inconvenient:** Doit etre applique sur les 15 callers de DEVERSEMENT (ou au moins ceux qui creent des OD taxe de sejour).

#### Option B : Corriger dans DEVERSEMENT (ALTERNATIF)

Modifier l'Expression 11 dans la subtask 247.2 (ISN_2=3) de ADH IDE 247 pour utiliser `{1,20}` (col 7 = description) au lieu de `{1,19}` (col 6 = service) quand le type est 'O'.

Remplacer:
```
IF(NOT({32768,46}) OR {1,2}='O', {1,19}, {0,44})
```
Par:
```
IF({1,2}='O', {1,20}, IF(NOT({32768,46}), {1,19}, {0,44}))
```

**Avantages:** Correction centralisee (1 seul programme a modifier).
**Inconvenient:** Affecte TOUTES les OD, pas seulement taxe de sejour. Risque de regression sur d'autres OD ou le libelle du service est pertinent.

#### Option C : Inverser libelle/libelle_supplem_ dans l'affichage

Pour les OD (`cte_code_type='O'`, `cte_mode_de_paiement='OD'`), afficher `cte_libelle_supplem_` comme libelle principal.

**Avantages:** Pas de modification du code de creation.
**Inconvenient:** Ne corrige pas la cause racine, necessite modification dans les ecrans d'affichage.

#### Option D : Script correctif data (COMPLEMENTAIRE)

UPDATE les lignes existantes dans cafil018_dat pour les OD de taxe de sejour :
```sql
-- A VALIDER avant execution
-- Compte les lignes affectees d'abord:
SELECT COUNT(*)
FROM cafil018_dat
WHERE cte_code_type = 'O'
  AND cte_mode_de_paiement = 'OD'
  AND cte_libelle_supplem_ LIKE '%TAXE%'
  AND cte_libelle = 'Caisse';

-- Correction:
UPDATE cafil018_dat
SET cte_libelle = cte_libelle_supplem_
WHERE cte_code_type = 'O'
  AND cte_mode_de_paiement = 'OD'
  AND cte_libelle_supplem_ LIKE '%TAXE%'
  AND cte_libelle = 'Caisse';
```

**A executer sur chaque village affecte.**

### Recommandation

1. **Court terme** : Executer Option D (script correctif) pour corriger les donnees existantes
2. **Moyen terme** : Implementer Option A ou B pour corriger la cause racine
3. **Avant correction code** : Verifier si d'autres villages sont affectes (meme chaine de programmes)
4. **Avant correction code** : Analyser le programme Vente GP (ADH IDE 237) pour confirmer exactement ou le libelle est affecte et le modifier

### Prochaines etapes

1. Executer le SELECT de comptage sur Pragelato pour quantifier l'impact
2. Verifier sur d'autres villages si le meme probleme existe
3. Decider entre Option A (correction source - 15 programmes) ou Option B (correction DEVERSEMENT - 1 programme)
4. Si Option B retenue: tester l'impact sur les autres types d'OD (pas seulement taxe de sejour)
5. Deployer le script correctif (Option D) en production
