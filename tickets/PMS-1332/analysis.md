# PMS-1332 - Date fiche police 00/00/0000

## Informations Jira

| Champ | Valeur |
|-------|--------|
| **Titre** | Saisie fiche police - date fin 00/00/0000 non affichee |
| **Type** | Story |
| **Priorite** | Basse |
| **Statut** | En cours |
| **Reporter** | Anthony Leberre |
| **Assignee** | Anthony Leberre |
| **Labels** | PBG |
| **Cree** | 2025-06-16 |

## Description

Lors de la saisie de la date du debut de sejour, celle-ci initialise directement la meme date de fin.

**Probleme**: Si on ne souhaite pas de date de fin, il faut quand meme en saisir une.

**Besoin**: Pouvoir faire en sorte que 00/00/0000 soit considere comme "sans limite".

**Cas pratique**: Saisie des informations fiche de police pour un GO (date tres longue a renseigner).

## Analyse Magic IDE

### Programme principal

| Projet | IDE | Nom |
|--------|-----|-----|
| PBG | 93 | Saisie des fiches de police |

### Arborescence des taches

```
PBG IDE 93 - Saisie des fiches de police
└── 93.1 - Saisie des fiches de police
    └── 93.1.1 - Clients
        └── 93.1.1.1 - Fiche de police            ← Ecran de saisie
            ├── 93.1.1.1.1 - Verification zones   ← Validation des dates
            └── 93.1.1.1.2 - Modification autres fichiers
                ├── 93.1.1.1.2.1 - Modification circuit
                ├── 93.1.1.1.2.2 - Modification recherche
                ├── 93.1.1.1.2.3 - Modification Client PVE
                ├── 93.1.1.1.2.4 - Modification Heb
                ├── 93.1.1.1.2.5 - Modification specifique grec
                └── 93.1.1.1.2.6 - Maj Fiche de police
```

### Programmes lies

| Projet | IDE | Nom |
|--------|-----|-----|
| PBG | 92 | Fiche de police Bresil |
| PBG | 275 | Traitement Fiche de police |

### Points d'intervention

1. **Tache 93.1.1.1** - Initialisation date fin = date debut (a modifier)
2. **Tache 93.1.1.1.1 - Verification zones** - Accepter 00/00/0000 comme valide

## Pistes d'investigation

1. Analyser **Tache 93.1.1.1** pour trouver l'initialisation de la date fin
2. Modifier la verification dans **Tache 93.1.1.1.1** pour accepter 00/00/0000
3. Verifier l'impact sur les autres fichiers (circuit, recherche, etc.)

## Statut

- [x] Ticket fetche depuis Jira
- [x] Programme Magic identifie
- [ ] Analyse detaillee de la logique
- [ ] Identification du point de modification
- [ ] Proposition de correction

---

*DerniÃ¨re mise Ã  jour : 2026-01-22T18:55*
