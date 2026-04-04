# PMS-1337 - Lancement de 2 instances de Caisse Adherent

> **Jira** : [PMS-1337](https://clubmed.atlassian.net/browse/PMS-1337)

## Contexte

Certains GO ouvrent 2 fenetres de caisse adherent en double-cliquant. Quand une session est ouverte sur la fenetre 1 puis que le GO ouvre la fenetre 2 (qui montre la caisse fermee), il peut re-ouvrir sa session, ecrasant les transactions de la fenetre 1.

**Recette du 01/12/2025** : Un controle a ete ajoute - message d'avertissement si session deja ouverte.

**Retour village 21/01/2026** : Le controle doit etre sur **meme session + meme utilisateur + meme poste**, pas juste le terminal.

## Programme principal

| Projet | IDE | Nom | Public Name |
|--------|-----|-----|-------------|
| **ADH** | **121** | Gestion Caisse | CA0142 |
| **ADH** | **122** | Ouverture caisse | - |
| **ADH** | **156** | Verif session caisse ouverte2 | - |
| **ADH** | **116** | Calcul concurrence sessions | - |

## Flux du controle de session

```
ADH IDE 122 "Ouverture caisse"
    |
    +-- Sous-tache 122.2 "Ouverture caisse"
           |
           +-- CallTask --> ADH IDE 156 (Verif session caisse ouverte2)
                   |
                   +-- Verifie dans table n.249 (caisse_session_detail)
                   |      - Cherche derniere session du terminal
                   |      - Verifie si fermee ou non
                   |
                   +-- Retourne: Po.Ouverture caisse possible? (Boolean)
           |
           +-- Si FALSE --> STP Warning (Expression 62)
                   Message: "Une session de caisse est deja ouverte pour ce numero de terminal"
```

## Tables de tracking identifiees

| N. Table | Nom physique | Nom logique | Usage |
|----------|--------------|-------------|-------|
| **227** | `caisse_concurrences` | concurrence_sessions | Concurrence coffre |
| **246** | `caisse_session` | histo_sessions_caisse | Sessions principales |
| **249** | `caisse_session_detail` | histo_sessions_caisse_detail | Details evenements |

### Structure table n.227 - caisse_concurrences

| Colonne | Type | Description |
|---------|------|-------------|
| `utilisateur` | Unicode 8 | Utilisateur connecte |
| `fonction` | Unicode | "Coffre" ou "Reception" |
| `flag_occupe` | Unicode | Flag d'occupation |
| `terminal_session` | Numeric 3 | N. terminal |
| `hostname_session` | Unicode 50 | Nom du poste |

### Structure table n.246 - caisse_session

| Colonne | Type | Description |
|---------|------|-------------|
| `utilisateur` | Unicode 8 | Utilisateur |
| `chrono` | Numeric 12 | Chrono session |
| `date_debut_session` | Date | Date ouverture |
| `heure_debut_session` | Time | Heure ouverture |
| `date_fin_session` | Date | Date fermeture |
| `heure_fin_session` | Time | Heure fermeture |

### Structure table n.249 - caisse_session_detail

| Colonne | Type | Description |
|---------|------|-------------|
| `utilisateur` | Unicode 8 | Utilisateur |
| `chrono_session` | Numeric 12 | Chrono session |
| `quand` | Unicode (O/P/F) | Ouverture/Pendant/Fermeture |
| `date` | Date | Date evenement |
| `heure` | Time | Heure evenement |

## Logique actuelle (ADH IDE 156)

```
Expression 9 : NOT({0,22}) OR {0,21}
             = NOT(Caisse ouverte aujourd'hui?) OR (Caisse fermee?)

Resultat:
- Aucune caisse ouverte --> TRUE (peut ouvrir)
- Caisse ouverte + fermee --> TRUE (peut ouvrir)
- Caisse ouverte + pas fermee --> FALSE (message d'erreur)
```

**Derniere modification ADH IDE 156** : 07/01/2026 10:59:45

## Mecanisme de logging

### Ce qui existe

| Moment | Programme | Action |
|--------|-----------|--------|
| **Ouverture fenetre** | ADH IDE 121 Task Prefix | Appelle ADH IDE 116 (concurrence coffre) |
| **Ouverture session** | ADH IDE 121 sous-tache 12 | "Creation histo session" --> INSERT caisse_session_detail (quand='O') |
| **Fermeture session** | ADH IDE 121 sous-tache 16 | "Cloture histo session" --> UPDATE date_fin_session |

### Ce qui N'EXISTE PAS

- **Aucun heartbeat/timer** : Pas de mise a jour periodique pendant que la fenetre est ouverte
- **Pas de champ `derniere_activite`** ou `timestamp_ping`
- Le systeme ne detecte pas si une fenetre a ete fermee brutalement (kill process, crash)

## Probleme identifie

Le controle actuel verifie uniquement le **terminal**. Mais il devrait verifier :
- Meme **terminal**
- Meme **utilisateur/session**

**Cas d'usage souhaite (Jessica 21/01/2026)** :
- Jessica ouvre caisse --> Marine peut ouvrir une autre caisse (different utilisateur) = OK
- Jessica ouvre 2 fenetres --> Message d'erreur sur la 2eme (meme utilisateur) = CONTROLE

## Solution potentielle

1. **Ajouter verification utilisateur** dans ADH IDE 156 :
   - Comparer `utilisateur` en plus du `terminal`
   - Si meme utilisateur + meme terminal + session non fermee --> ERREUR

2. **Ajouter heartbeat** (optionnel, pour robustesse) :
   - Nouveau champ `timestamp_derniere_activite` dans caisse_session_detail
   - Timer event qui met a jour toutes les X minutes
   - Session consideree "morte" si heartbeat > X minutes

## Fichiers source

| Fichier | Position IDE | Description |
|---------|--------------|-------------|
| `Prg_121.xml` | ADH IDE 121 | Gestion Caisse (ecran principal) |
| `Prg_122.xml` | ADH IDE 122 | Ouverture caisse |
| `Prg_329.xml` | ADH IDE 156 | Verif session caisse ouverte2 |
| `Prg_116.xml` | ADH IDE 116 | Calcul concurrence sessions |

---
*Analyse effectuee le 21/01/2026*

---

*DerniÃ¨re mise Ã  jour : 2026-01-22T18:55*
