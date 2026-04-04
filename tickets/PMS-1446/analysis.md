# PMS-1446 - Location materiel ski courts sejours

> **Jira** : [PMS-1446](https://clubmed.atlassian.net/browse/PMS-1446)

## Informations Jira

| Champ | Valeur |
|-------|--------|
| **Ticket** | PMS-1446 |
| **Titre** | [POS] location materiel de ski court sejour / sejours dates libres |
| **Statut** | En cours |
| **Priorite** | Haute |
| **Reporter** | Jessica Palermo |
| **Assignee** | Anthony Leberre |
| **Cree** | 2025-12-31 |

## Demande

### Regle actuelle (sejour 7 jours = semaine Club Med)
- Materiel de ski donne le **lendemain** du jour d'arrivee
- Forfait ski valide du lendemain au depart

### Regle demandee (courts sejours < 7 jours)
- Materiel de ski donne le **jour d'arrivee**
- Alignement avec la regle du forfait ski (si droit de skier des l'arrivee -> materiel des l'arrivee)
- Garder les regles AM/PM (demi-journees)

### Contrainte additionnelle
> "Ces regles risquent de changer chaque annee, il faudrait trouver un systeme pour l'adapter rapidement sans devoir attendre un developpement"

---

## Analyse Technique

### Programmes concernes

| Programme | Nom | Role |
|-----------|-----|------|
| **PVE IDE 145** | Initialization | Initialisation parametres POS, SetParam MODEDAYINC |
| **PVE IDE 186** | Main Sale | Programme principal vente/location |
| **PVE IDE 263** | Choix - Select AM/PM | Selection mode AM/PM |

### Parametre cle : MODEDAYINC

Le parametre **MODEDAYINC** controle le decalage en jours :
- `0` = Materiel donne le **jour meme**
- `1` = Materiel donne le **lendemain**

Ce parametre est initialise dans **PVE IDE 145** (Tache 145.1 - Init mode day / Interfaces).

### Variables cles (PVE IDE 186 - Main Sale)

> **Note** : Offset Main PVE = 143. Les variables de la tâche root 186 commencent à l'index 143.

| Variable | Nom | Type | Role |
|----------|-----|------|------|
| **MG** | v.Deb_Sejour | Date | Date debut sejour GM |
| **MH** | v.Fin_sejour | Date | Date fin sejour GM |

Ces variables sont passees en **parametres d'entree** (parametres 42 et 43 du programme).

### Calcul duree sejour

La duree du sejour peut etre calculee :
```
DureeSejour = Variable MH - Variable MG
```

### Tables concernees

| Table | Nom | Contenu |
|-------|-----|---------|
| Table n°384 | pv_equipment_models | Modeles equipements |
| Table n°379 | pv_products | Catalogue produits location |

---

## Solution proposee

### Option retenue : Calcul automatique + seuil configurable

**Principe** : Calculer automatiquement MODEDAYINC en fonction de la duree du sejour.

| Duree sejour | MODEDAYINC | Resultat |
|--------------|------------|----------|
| < 7 nuits | 0 | Materiel jour arrivee |
| >= 7 nuits | 1 | Materiel lendemain |

### Pseudo-code logique

```
DureeSejour = Variable MH - Variable MG   -- Fin sejour - Debut sejour

SI DureeSejour < SeuilCourtSejour ALORS
    MODEDAYINC = 0   -- Court sejour : materiel jour arrivee
SINON
    MODEDAYINC = 1   -- Semaine : materiel lendemain
FIN SI
```

### Configuration annuelle (sans developpement)

| Parametre | Valeur defaut | Description |
|-----------|---------------|-------------|
| SEUIL_COURT_SEJOUR | 7 | Nombre de nuits seuil |
| MODEDAYINC_COURT | 0 | Increment courts sejours |
| MODEDAYINC_LONG | 1 | Increment longs sejours |

---

## Points de modification

### 1. PVE IDE 145 - Initialization

**Tache concernee** : Tache 145.1 (Init mode day / Interfaces)

**Modification** : Ajouter le calcul conditionnel de MODEDAYINC base sur la duree du sejour.

### 2. PVE IDE 186 - Main Sale

**Variables a utiliser** :
- Variable MG (v.Deb_Sejour)
- Variable MH (v.Fin_sejour)

**Modification** : Les expressions utilisant GetParam('MODEDAYINC') beneficieront automatiquement de la nouvelle valeur calculee.

---

## Questions en suspens

1. Le seuil de 7 jours est-il fixe ou peut-il varier selon le village ?
2. Les regles AM/PM restent-elles identiques pour tous les types de sejour ?
3. Y a-t-il des exceptions (types de produits specifiques) ?

---

## Verification MCP (2026-01-13)

### Arborescence PVE IDE 145 (Initialization)

| Tache | Nom | Role |
|-------|-----|------|
| 145 | Initialization | Racine |
| 145.1 | Init mode day / Interfaces | **SetParam MODEDAYINC** |
| 145.2 | Parameters for invoice v1 | Parametres facture |
| 145.2.1 | Lecture tpe v1 | Lecture TPE |
| 145.3 | Parameters for invoice T2H | Parametres T2H |

### Variables PVE IDE 186 confirmees (avec offset Main)

| Variable | Nom | Type | Ligne DataView |
|----------|-----|------|----------------|
| **MG** | v.Deb_Sejour | Date | Ligne 35 |
| **MH** | v.Fin_sejour | Date | Ligne 36 |

---

## Status

| Element | Valeur |
|---------|--------|
| **Analyse** | CONFIRMEE par MCP |
| **Variables disponibles** | Variable MG, Variable MH |
| **Solution** | Calcul auto + seuil configurable |
| **Prochaine etape** | Valider avec le metier |

---

$12026-01-22T18:55*
*Verification MCP: 2026-01-13*
*Statut: SPEC COMPLETE - En attente validation metier*
