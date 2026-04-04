# Spécification d'Implémentation PMS-1373

> **Jira** : [PMS-1373](https://clubmed.atlassian.net/browse/PMS-1373)

## Résumé

**Demande** : Masquer les lignes d'annulation (+/-) dans l'extrait de compte GM.

**Solution** : Ajouter une question "Extrait complet ?" avant l'édition, puis filtrer sur `cte_flag_annulation = 'Normal'` si NON.

---

## 1. Découverte Clé : Champ Annulation Existant

La **Table n°40** (`cafil018_dat` / operations_dat) possède déjà un champ de flag :

| Champ | Type | Valeurs |
|-------|------|---------|
| `cte_flag_annulation` | Unicode | `Normal`, `Annulation`, `X-annule` |

**Pas besoin de logique complexe de matching** - il suffit de filtrer sur ce champ !

---

## 2. Architecture Actuelle

> **Note** : Offset Main ADH = 117. Variables globales dans Tâche 69.3.

```
ADH IDE 69 (EXTRAIT_COMPTE)
└── Tâche 69.3 "scroll sur compte"
    └── Handler Variable KN (W1 Choix_action)
        ├── Choix 'N' → CallTask ADH IDE 70 (EXTRAIT_NOM)      [14 params]
        ├── Choix 'D' → CallTask ADH IDE 71 (EXTRAIT_DATE)     [13 params]
        ├── Choix 'C' → CallTask ADH IDE 72 (EXTRAIT_CUM)      [12 params]
        ├── Choix 'I' → CallTask ADH IDE 73 (EXTRAIT_IMP)      [12 params]
        └── Choix 'S' → CallTask ADH IDE 76 (EXTRAIT_SERVICE)  [13 params]
```

---

## 3. Modifications ADH IDE 69 (EXTRAIT_COMPTE)

### 3.1 Variable existante

La variable existe DÉJÀ dans **Tâche 69.3** :

| Variable | Nom | Type | Ligne DataView |
|----------|-----|------|----------------|
| **KZ** | v. Edition partielle ? | Numeric | Ligne 24 |

**Note** : TRUE = extrait complet, FALSE = masquer annulations

### 3.2 Question existante (Verify Warning)

La question est **DÉJÀ IMPLÉMENTÉE** dans la logique :

| Emplacement | Valeur |
|-------------|--------|
| **Programme** | ADH IDE 69 |
| **Tâche** | Tâche 69.3 (scroll sur compte) |
| **Opération** | Verify Warning |
| **Message** | "Voulez-vous éditer l'extrait de compte complet ?" |
| **Retour** | Variable **KZ** (TRUE = Oui, FALSE = Non) |

**Alternative UX** : Checkbox sur l'écran plutôt que popup (meilleure ergonomie)

### 3.3 Modifier les 5 CallTask

Ajouter un argument **Variable KZ** à chaque CallTask :

| CallTask vers | Tâche | Block | Argument à ajouter |
|---------------|-------|-------|-------------------|
| ADH IDE 70 | Tâche 69.3, Handler KN | Block 'N' | Arg 15 = **Variable KZ** |
| ADH IDE 71 | Tâche 69.3, Handler KN | Block 'D' | Arg 14 = **Variable KZ** |
| ADH IDE 72 | Tâche 69.3, Handler KN | Block 'C' | Arg 13 = **Variable KZ** |
| ADH IDE 73 | Tâche 69.3, Handler KN | Block 'I' | Arg 13 = **Variable KZ** |
| ADH IDE 76 | Tâche 69.3, Handler KN | Block 'S' | Arg 14 = **Variable KZ** |

---

## 4. Modifications Programmes Édition (ADH IDE 70, 71, 72, 73, 76)

### 4.1 Ajouter Paramètre d'entrée

Pour CHAQUE programme d'édition, ajouter un paramètre :

| # | Nom Paramètre | Type | Direction | Description |
|---|---------------|------|-----------|-------------|
| 15 | P.ExtraitComplet | Logical | Input | TRUE=tout, FALSE=masquer annulations |

**Emplacement** : Task Properties > Parameters du programme

### 4.2 Modifier le Filtrage MainSource

Dans CHAQUE sous-tâche d'impression (A4, TMT88, etc.) :

**Avant** (Range/Locate actuel) :
```
cte_societe = P.societe AND cte_compte_gm = P.compte
```

**Après** (ajouter condition) :
```
cte_societe = P.societe AND cte_compte_gm = P.compte
AND (P.ExtraitComplet OR cte_flag_annulation = 'Normal')
```

**Expression Magic équivalente** :
```
IF(P.ExtraitComplet, TRUE, cte_flag_annulation = 'Normal')
```

### 4.3 Localisation des Modifications par Programme

| Programme | Sous-tâches à modifier | MainSource |
|-----------|------------------------|------------|
| ADH IDE 70 | Tâches 70.2 à 70.19 (impressions) | **Table n°40** (cafil018_dat) |
| ADH IDE 71 | Tâches 71.2 à 71.17 (impressions) | **Table n°40** (cafil018_dat) |
| ADH IDE 72 | Tâches 72.2 à 72.15 (impressions) | **Table n°40** (cafil018_dat) |
| ADH IDE 73 | Tâches 73.2 à 73.14 (impressions) | **Table n°40** (cafil018_dat) |
| ADH IDE 76 | Tâches 76.2 à 76.17 (impressions) | **Table n°40** (cafil018_dat) |

---

## 5. Résumé des Modifications

| Programme | Action | Complexité |
|-----------|--------|------------|
| ADH IDE 69 | +1 variable, +1 question, +5 arguments CallTask | Moyenne |
| ADH IDE 70 | +1 paramètre, modifier Range ~17 sous-tâches | Haute |
| ADH IDE 71 | +1 paramètre, modifier Range ~15 sous-tâches | Haute |
| ADH IDE 72 | +1 paramètre, modifier Range ~13 sous-tâches | Haute |
| ADH IDE 73 | +1 paramètre, modifier Range ~12 sous-tâches | Haute |
| ADH IDE 76 | +1 paramètre, modifier Range ~15 sous-tâches | Haute |

**Total** : 6 programmes, ~75 sous-tâches à modifier

---

## 6. Tests de Recette

### Scénarios de Test

| # | Scénario | Résultat Attendu |
|---|----------|------------------|
| 1 | Extrait par Nom, répondre OUI | Toutes les lignes affichées |
| 2 | Extrait par Nom, répondre NON | Lignes `Annulation` et `X-annule` masquées |
| 3 | Extrait par Date, répondre NON | Idem - annulations masquées |
| 4 | Extrait par Service, répondre NON | Idem - annulations masquées |
| 5 | Extrait Cumulé, répondre NON | Idem - annulations masquées |
| 6 | Impression, répondre NON | Idem - annulations masquées |
| 7 | Compte sans annulations | Comportement identique OUI/NON |

### Données de Test

| Village | Compte GM | Caractéristique |
|---------|-----------|-----------------|
| ADH (Alpe d'Huez) | 572185684 (BENNUN Rachel) | Annulations visibles |
| ADH | À identifier | Compte sans annulations (contrôle) |

---

## 7. Risques et Points d'Attention

| Risque | Mitigation |
|--------|------------|
| Recette KO précédente | Vérifier ce qui avait été implémenté avant |
| Impact Odyssey | Mentionné par @Nelly Becquart - à évaluer |
| Performance filtrage | Le champ `cte_flag_annulation` devrait être indexé |
| Cohérence calculs | Vérifier que les totaux restent corrects après filtrage |

---

## 8. Étapes d'Implémentation

1. [ ] Créer branche `feature/PMS-1373-masquer-annulations` ✅
2. [ ] Modifier ADH IDE 69 (variable + question + CallTask)
3. [ ] Modifier ADH IDE 70 (paramètre + Range)
4. [ ] Modifier ADH IDE 71 (paramètre + Range)
5. [ ] Modifier ADH IDE 72 (paramètre + Range)
6. [ ] Modifier ADH IDE 73 (paramètre + Range)
7. [ ] Modifier ADH IDE 76 (paramètre + Range)
8. [ ] Tests unitaires Magic
9. [ ] Déployer sur environnement de recette
10. [ ] Validation Jessica Palermo
11. [ ] Merge et déploiement production

---

*Spécification générée le 2026-01-08*
*Branche : feature/PMS-1373-masquer-annulations*

---

*DerniÃ¨re mise Ã  jour : 2026-01-22T18:55*
