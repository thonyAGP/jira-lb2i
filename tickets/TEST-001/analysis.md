# TEST-001 - Ã€ complÃ©ter

> **Jira** : [TEST-001](https://clubmed.atlassian.net/browse/TEST-001)
> **Protocole** : .claude/protocols/ticket-analysis.md appliquÃ©
> **GÃ©nÃ©rÃ©** : 2026-01-24 11:18

---

<!-- ONGLET: Contexte -->
## 1. Contexte Jira

| Ã‰lÃ©ment | Valeur |
|---------|--------|
| **SymptÃ´me** | Ã€ extraire du ticket Jira |
| **DonnÃ©es entrÃ©e** | Ã€ extraire |
| **Attendu** | Ã€ extraire |
| **Obtenu** | Ã€ extraire |
| **Reporter** |  |
| **Date** | 2026-01-24 |

### Indices extraits automatiquement
- Programmes mentionnÃ©s : 
- Tables mentionnÃ©es : 
- Villages : 
- Dates : 

---

<!-- ONGLET: Localisation -->
## 2. Localisation Programmes

### magic_find_program("[recherche]")

| Project | IDE | ID | Name | Public |
|---------|-----|----|------|--------|
| ... | ... | ... | ... | ... |

> **TODO** : Appeler magic_find_program() pour chaque indice extrait

### Programmes identifiÃ©s

| IDE VÃ©rifiÃ© | Nom | RÃ´le dans le flux |
|-------------|-----|-------------------|
| ... | ... | ... |

---

<!-- ONGLET: Flux -->
## 3. TraÃ§age Flux

### magic_get_tree("[projet]", [id])

| IDE | ISN_2 | Nom | Niveau |
|-----|-------|-----|--------|
| ... | ... | ... | ... |

> **TODO** : Appeler magic_get_tree() puis magic_get_logic() pour tÃ¢ches suspectes

### Diagramme du flux

```
â”Œâ”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”
â”‚ [PROJET] IDE [N]                        â”‚
â”‚ [Nom Programme]                         â”‚
â””â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”¬â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”˜
                     â”‚
                     â–¼
         [Ã€ complÃ©ter avec appels MCP]
```

---

<!-- ONGLET: Expressions -->
## 4. Analyse Expressions

> **Note** : L'offset est calculÃ© automatiquement par OffsetCalculator.
> Utiliser magic_decode_expression() et magic_get_line().

### magic_decode_expression("[projet]", [prgId], [taskIsn2], [expId])

| RÃ©fÃ©rence | Position | Index Global | Variable | Nom logique |
|-----------|----------|--------------|----------|-------------|
| ... | ... | ... | ... | ... |

### Formule dÃ©codÃ©e

```
[Ã€ complÃ©ter avec rÃ©sultat MCP]
```

---

<!-- ONGLET: Root Cause -->
## 5. Root Cause

| Ã‰lÃ©ment | Valeur |
|---------|--------|
| **Programme** | [PROJET] IDE [N] - [Nom] |
| **Sous-tÃ¢che** | TÃ¢che [N.X.Y] |
| **Ligne Logic** | Ligne [L] |
| **Expression** | Expression [E] |
| **Erreur** | [Description prÃ©cise] |
| **Impact** | [ConsÃ©quence observable] |

---

<!-- ONGLET: Solution -->
## 6. Solution

### Modification

| Ã‰lÃ©ment | Avant (bug) | AprÃ¨s (fix) |
|---------|-------------|-------------|
| ... | ... | ... |

### Variables concernÃ©es

| Variable | Nom logique | RÃ´le | Statut |
|----------|-------------|------|--------|
| ... | ... | ... | ... |

---

## DonnÃ©es requises

- Base de donnÃ©es : [Village] Ã  la date [JJ/MM/AAAA]
- Table(s) Ã  extraire : [noms tables]

---

*Analyse gÃ©nÃ©rÃ©e : 2026-01-24T11:18*
