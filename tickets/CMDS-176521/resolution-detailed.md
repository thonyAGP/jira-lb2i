# Resolution Detaillee CMDS-176521

> **Jira** : [CMDS-176521](https://clubmed.atlassian.net/browse/CMDS-176521)

## Statut: RESOLU - MAIS RESOLUTION INCOMPLETE

---

## Critique de la resolution existante

La resolution existante manque de precision technique. Elle indique que "la variable referenc\u00e9e etait incorrecte" sans specifier:

| Information manquante | Ce qui devrait etre documente |
|----------------------|-------------------------------|
| Expression exacte | Numero de l'expression modifiee (ex: Expression 33) |
| Variable fautive | Reference exacte (ex: `{0,3}` = Variable D = v.Compte) |
| Variable correcte | Reference correcte (ex: `{0,21}` = Variable V = prix) |
| Ligne IDE | Position dans Magic IDE (ex: Tache 181.55 ligne 12) |
| Fichier XML | Ligne dans le fichier XML source |

---

## Analyse technique approfondie

### Programmes concernes

| Projet | IDE | Fichier | Description |
|--------|-----|---------|-------------|
| PVE | 180 | Prg_180.xml | Main Sale |
| PVE | **181** | Prg_181.xml | Main Sale-664 (75514 lignes) |
| PVE | 284 | Prg_284.xml | Main Sale Sale Bar Code |

### Variables identifiees dans PVE IDE 181

| Column ID | Variable | Nom | Type |
|-----------|----------|-----|------|
| 3 | **D** | v.Compte | Numero GM (41,857) |
| 21 | V | v.% de reduction / price | % ou prix selon sous-tache |
| 22 | W | v.prix du produit / discount | Prix ou % selon sous-tache |
| 38 | AM | V pms filiation from card | Filiation |

### Expressions de calcul prix remise trouvees

**Expression 33** (ligne 34526):
```
Round({1,13}*(1-ExpCalc('15'EXP)/100),10,{32768,43})
```
- `{1,13}` = Variable N du niveau parent = Prix original
- `ExpCalc('15'EXP)` = Expression 15 = % remise
- Formule: `Prix * (1 - Remise%/100)` = Prix remise

**Expression 35** (ligne 69256):
```
Round({0,21}*(1-{0,22}/100),10,{32768,43})
```
- `{0,21}` = Variable V = prix
- `{0,22}` = Variable W = % discount
- Formule: `Prix * (1 - Discount%/100)` = Prix remise

### Controles d'affichage "price"

| Ligne XML | Control | Data source | Nom |
|-----------|---------|-------------|-----|
| 53430 | price | `Exp="21"` | Expression 21 |
| 53564 | price | `Exp="22"` | Expression 22 |
| 69064 | price | `FieldID="21"` | Variable V directe |

### Hypothese du bug

Le bug pourrait etre dans **Expression 21** (ligne 6152):
```
{0,38}
```

Cette expression reference `{0,38}` = Variable AM = "V pms filiation from card".
Mais un controle "price" utilise `Exp="21"` pour s'afficher (ligne 53429).

**Si** la variable `{0,38}` contient parfois le numero de compte (41,857) au lieu de la filiation, cela expliquerait le bug.

---

## Fix propose (reconstitution)

### Avant (bug)
```xml
<Expression id="21">
  <ExpSyntax val="{0,38}"/>  <!-- Reference filiation/compte au lieu de prix -->
</Expression>
```

### Apres (fix)
```xml
<Expression id="21">
  <ExpSyntax val="{0,prix_variable}"/>  <!-- Reference prix correct -->
</Expression>
```

---

## DEMANDE D'INFORMATION

Pour completer cette analyse, il faudrait:

1. **Acces au commit Git** du fix (si disponible)
2. **Diff du fichier XML** avant/apres correction
3. **Confirmation Davide** sur l'expression exacte modifiee

---

## Lecons apprises

Pour les prochaines resolutions de bugs, TOUJOURS documenter:

1. **Programme** : Projet IDE Numero - Nom Public
2. **Sous-tache** : Tache X.Y.Z
3. **Expression** : Expression N (ligne XML)
4. **Variable fautive** : `{niveau,colonne}` = Lettre = Nom logique
5. **Variable correcte** : `{niveau,colonne}` = Lettre = Nom logique
6. **Formule avant/apres** : Code exact

---

*Analyse approfondie: 2026-01-12*
*Statut: Resolution incomplete - precision manquante*
