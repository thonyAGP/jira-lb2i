# {TICKET_KEY} - {TITRE}

> **Jira** : [{TICKET_KEY}](https://clubmed.atlassian.net/browse/{TICKET_KEY})
> **Protocole** : `.claude/protocols/ticket-analysis.md` applique
> **Version** : Template v3.0

---

## 1. Contexte Jira

| Element | Valeur |
|---------|--------|
| **Symptome** | {citation exacte du ticket} |
| **Donnees entree** | {valeurs precises qui declenchent le bug} |
| **Attendu** | {comportement correct} |
| **Obtenu** | {comportement actuel} |
| **Reporter** | {nom} |
| **Date** | {date creation} |

### Indices extraits du ticket
- Programme mentionne : `{nom}` -> a verifier ETAPE 2
- Table mentionnee : `{nom}` -> a verifier ETAPE 2
- Village concerne : {code}
- Date des donnees : {date}

---

## 2. Localisation Programmes

### MCP Evidence

> **OBLIGATOIRE** : Documenter chaque appel MCP effectue

| Outil | Parametres | Resultat |
|-------|------------|----------|
| `magic_find_program` | "{recherche}" | {N resultats} |
| `magic_get_position` | "{projet}", {id} | **{PROJET} IDE {N} - {Nom}** |
| `magic_get_tree` | "{projet}", {id} | {N} taches |

### Programmes identifies

| Fichier XML | IDE Verifie | Nom | Role dans le flux |
|-------------|-------------|-----|-------------------|
| Prg_{X}.xml | **{PROJET} IDE {N}** | {Nom} | {Role} |

---

## 3. Tracage Flux

### Arborescence Taches

> **OBLIGATOIRE** : Chemin hierarchique depuis la racine

```
{PROJET} IDE {N} - {Nom}
├── Tache {N}.1 - Main
│   ├── Tache {N}.1.1 - {Nom sous-tache}
│   │   └── Tache {N}.1.1.2 - {Cible} ← POINT D'INTERET
│   └── Tache {N}.1.2 - {Autre}
└── Tache {N}.2 - {Handler}
```

### Resolution des CallTask/CallProgram

| Ligne | Source | TargetPrg | MCP Verifie | Destination |
|-------|--------|-----------|-------------|-------------|
| {L} | Tache {N.X} | {X} | `magic_get_position` | **{PROJET} IDE {Y} - {Nom}** |

### Diagramme du flux

```
┌─────────────────┐
│ {PROJET} IDE {N}│ {Nom}
│ Tache {N.X}     │ {Description}
└────────┬────────┘
         │ {Type appel} (condition Exp {N})
         ▼
┌─────────────────┐
│ {PROJET} IDE {M}│ {Nom}
│ {Zone suspecte} │ ← POINT D'INTERET
└─────────────────┘
```

---

## 4. Analyse Expressions

### MCP Evidence

| Outil | Parametres | Resultat |
|-------|------------|----------|
| `magic_get_line` | "{projet}", "{task}", {ligne} | {Variables listees} |
| `magic_decode_expression` | "{projet}", {prog}, {exp} | {Formule decodee} |

### Variable Mapping

> **OBLIGATOIRE si references {N,Y} presentes** : Table de correspondance

| Reference | Position | Variable | Nom Logique | Localisation |
|-----------|----------|----------|-------------|--------------|
| {0,X} | {pos} | **{VAR}** | {nom} | Tache {N.X} ligne {L} |
| {1,Y} | {pos} | **{VAR}** | {nom} | Select sur table {T} |

### Formule decodee (lisible)

**Expression originale** : `{formule brute avec {N,Y}}`

**Expression decodee** :
```
{Formule avec noms de variables au lieu de {N,Y}}
```

---

## 5. Root Cause

| Element | Valeur |
|---------|--------|
| **Programme** | {PROJET} IDE {N} - {Nom} |
| **Sous-tache** | Tache {N.X.Y} |
| **Ligne Logic** | Ligne {L} |
| **Expression** | Expression {E} |
| **Erreur** | {Description precise} |
| **Impact** | {Consequence observable} |

### Localisation dans l'arborescence

```
{PROJET} IDE {N}
└── Tache {N.X}
    └── Tache {N.X.Y}
        └── Ligne {L} : {Operation} ← ROOT CAUSE
```

---

## 6. Solution

### Avant (bug)

```
{Code/Configuration actuelle avec le probleme}
```

### Apres (fix)

```
{Code/Configuration corrigee}
```

### Actions requises

| Fichier | Ligne | Action |
|---------|-------|--------|
| `Prg_{X}.xml` | {L} | {Description modification} |

---

## Donnees requises

- Base de donnees : Village {NOM} a la date {JJ/MM/AAAA}
- Fichier(s) : {nom_fichier.ext}
- Table(s) a extraire : {nom_table}

---

*Analyse : {YYYY-MM-DDTHH:MM}*
*Pattern KB : {pattern-name ou "nouveau"}*
