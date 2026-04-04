# {PROJET} IDE {N} - {DESCRIPTION}

> **Généré le** : {DATE}
> **Source** : `D:\Data\Migration\XPA\PMS\{PROJET}\Source\Prg_{N}.xml`
> **Modèle** : Spécification Programme Magic v1.0

---

## 1. SPÉCIFICATION FONCTIONNELLE

### 1.1 Identification

| Attribut | Valeur |
|----------|--------|
| **IDE Position** | {N} |
| **Nom Public** | {PUBLIC_NAME} |
| **Description** | {DESCRIPTION} |
| **Type** | {TASK_TYPE} (O=Online, B=Batch) |
| **Module** | {PROJET} |

### 1.2 Objectif Métier

**Quoi ?** {Description fonctionnelle du programme}

**Pour qui ?** {Utilisateurs cibles}

**Pourquoi ?** {Raison d'être, valeur ajoutée}

### 1.3 Règles Métier

| Règle | Description | Expression |
|-------|-------------|------------|
| **RM-001** | {Règle 1} | {Expression associée} |
| **RM-002** | {Règle 2} | {Expression associée} |

### 1.4 Actions/Fonctions Principales

| Code | Action | Condition | Résultat |
|------|--------|-----------|----------|
| {X} | {Action} | {Condition} | {Résultat} |

---

## 2. SPÉCIFICATION TECHNIQUE

### 2.1 Paramètres d'Entrée ({COUNT})

| # | Nom | Type | Description |
|---|-----|------|-------------|
| 1 | {Param1} | {Type} | {Description} |

### 2.2 Tables Utilisées

| ID | Nom Physique | Nom Logique | Access | Rôle |
|----|--------------|-------------|--------|------|
| **{OBJ}** | `{PHYSICAL_NAME}` | {LOGICAL_NAME} | {R/W} | {Rôle} |

### 2.3 Structure des Tâches

```
{PROJET} IDE {N} - {DESCRIPTION}
│
├── Tâche {N}.1 (ISN_2=1) - {Nom}
│   ├── Type: {Type}
│   ├── Tables: {Liste}
│   └── Logic: {Description}
│
└── Tâche {N}.X (ISN_2=X) - {Nom}
    └── ...
```

### 2.4 Variables Principales

| Variable | Type | Rôle |
|----------|------|------|
| {Var} | {Type} | {Rôle} |

### 2.5 Expressions Clés

| ID | Expression | Signification |
|----|------------|---------------|
| **{X}** | `{Expression}` | {Signification} |

### 2.6 Flux de Décision

```
{Diagramme ASCII du flux principal}
```

---

## 3. CARTOGRAPHIE APPLICATIVE

### 3.1 Programmes Appelants (Callers)

| Caller | IDE | Nom | Type Appel | Condition |
|--------|-----|-----|------------|-----------|
| **Prg_{X}** | {X} | {Nom} | {Type} | {Condition} |

### 3.2 Programmes Appelés (Callees)

| Callee | IDE | Nom | Type Appel | Contexte |
|--------|-----|-----|------------|----------|
| **Prg_{X}** | {X} | {Nom} | {Type} | {Contexte} |

### 3.3 Diagramme de Dépendances

```
{Diagramme ASCII des dépendances}
```

### 3.4 Tables Partagées (Cross-Reference)

| Table | Programmes utilisant | Access |
|-------|---------------------|--------|
| {Table} | {Liste programmes} | {R/W} |

---

## 4. NOTES DE MIGRATION

### 4.1 Complexité

| Critère | Score | Justification |
|---------|-------|---------------|
| Nombre de tâches | {N} | {Évaluation} |
| Tables en écriture | {N} | {Évaluation} |
| Expressions complexes | {N} | {Évaluation} |
| Appels externes | {N} | {Évaluation} |
| **Total** | **{NIVEAU}** | |

### 4.2 Points d'Attention

1. {Point 1}
2. {Point 2}

### 4.3 Suggestion Architecture Cible

```
{Proposition d'architecture moderne}
```

---

## 5. HISTORIQUE

| Date | Action | Auteur |
|------|--------|--------|
| {DATE} | Création spécification | {Auteur} |

---

*Modèle de spécification v1.0*
