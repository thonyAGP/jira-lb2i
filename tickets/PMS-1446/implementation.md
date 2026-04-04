# PMS-1446 - Specification d'implementation

> **Jira** : [PMS-1446](https://clubmed.atlassian.net/browse/PMS-1446)

## Solution retenue : Calcul automatique + seuil configurable

Calcul automatique de MODEDAYINC base sur la duree du sejour, avec seuil configurable en table.

---

## 1. Table de configuration

### Nouvelle table ou ajout a table existante REF

| Champ | Type | Valeur defaut | Description |
|-------|------|---------------|-------------|
| SEUIL_COURT_SEJOUR | Numeric | 7 | Nb nuits seuil (< = court sejour) |
| MODEDAYINC_COURT | Numeric | 0 | Increment courts sejours (jour meme) |
| MODEDAYINC_LONG | Numeric | 1 | Increment longs sejours (lendemain) |

### Emplacement suggere

- Option A : Table `pos_parametres` existante (si existe)
- Option B : Nouvelle table `pos_rental_config`

---

## 2. Modifications PVE IDE 145 - Initialization

### Localisation

- **Programme** : PVE IDE 145 - Initialization
- **Tache** : Tache 145.1 (Init mode day / Interfaces)

### Modification requise

**Actuel** :
```
SetParam('MODEDAYINC', [valeur table modes AM/PM])
```

**Nouveau** :
```
SetParam('MODEDAYINC',
    IF(DureeSejour < GetParam('SEUIL_COURT_SEJOUR'),
       GetParam('MODEDAYINC_COURT'),
       GetParam('MODEDAYINC_LONG')
    )
)
```

### Nouvelles operations a ajouter

1. **Charger parametres depuis table config** :
   - Lire SEUIL_COURT_SEJOUR
   - Lire MODEDAYINC_COURT
   - Lire MODEDAYINC_LONG

2. **Calcul duree sejour** :
   - DureeSejour = Date fin - Date debut

---

## 3. Modifications PVE IDE 186 - Main Sale

### Variables existantes a utiliser

> **Note** : Offset Main PVE = 143. Les variables ci-dessous sont les vraies variables globales.

| Variable | Nom | Type | Usage |
|----------|-----|------|-------|
| **MG** | v.Deb_Sejour | Date | Date arrivee |
| **MH** | v.Fin_sejour | Date | Date depart |

### Nouvelle logique

Avant l'appel a `GetParam('MODEDAYINC')`, calculer :

```
v.DureeSejour = Variable MH - Variable MG
v.EstCourtSejour = (v.DureeSejour < 7)

SI v.EstCourtSejour ALORS
    DateDebutLocation = Date()           -- Jour meme
SINON
    DateDebutLocation = Date() + 1       -- Lendemain
FIN SI
```

---

## 4. Regles AM/PM (inchangees)

Les regles AM/PM existantes restent identiques :

| Heure | Condition | Comportement |
|-------|-----------|--------------|
| < 12:00 | Matin | Selon mode AM |
| 12:00 - 15:00 | Mi-journee | Demi-journee |
| > 15:00 | Apres-midi | Selon mode PM |

Ces regles s'appliquent **apres** le calcul du MODEDAYINC.

---

## 5. Matrice de test

### Cas de test requis

| # | Duree sejour | Mode | Heure vente | Date debut attendue |
|---|--------------|------|-------------|---------------------|
| 1 | 7 nuits | AM | 10:00 | Lendemain arrivee |
| 2 | 7 nuits | PM | 14:00 | Lendemain arrivee |
| 3 | 6 nuits | AM | 10:00 | Jour arrivee |
| 4 | 6 nuits | PM | 14:00 | Jour arrivee |
| 5 | 4 nuits | AM | 10:00 | Jour arrivee |
| 6 | 3 nuits | PM | 16:00 | Jour arrivee |
| 7 | 8 nuits | AM | 09:00 | Lendemain arrivee |
| 8 | 14 nuits | PM | 13:00 | Lendemain arrivee |

### Cas limites

| # | Cas | Duree | Attendu |
|---|-----|-------|---------|
| 9 | Seuil exact | 7 nuits | Lendemain (>= seuil) |
| 10 | Seuil -1 | 6 nuits | Jour meme (< seuil) |
| 11 | 1 nuit | 1 nuit | Jour meme |
| 12 | Dates libres 5 nuits | 5 nuits | Jour meme |

---

## 6. Configuration annuelle

### Procedure de modification du seuil

1. Ouvrir la table de configuration POS
2. Modifier la valeur `SEUIL_COURT_SEJOUR`
3. Sauvegarder
4. Redemarrer les sessions POS

**Aucun developpement requis pour changer le seuil.**

### Exemple de changement

Si Club Med decide que le seuil passe a 5 nuits :

| Parametre | Ancienne valeur | Nouvelle valeur |
|-----------|-----------------|-----------------|
| SEUIL_COURT_SEJOUR | 7 | 5 |

Resultat :
- Sejours < 5 nuits -> Materiel jour arrivee
- Sejours >= 5 nuits -> Materiel lendemain

---

## 7. Impact et dependances

### Programmes impactes

| Programme | Type modification |
|-----------|-------------------|
| PVE IDE 145 | Ajout lecture config + calcul |
| PVE IDE 186 | Utilise nouvelle valeur MODEDAYINC |

### Composants non impactes

- Logique AM/PM - inchangee
- Calcul prix - inchange
- Interface utilisateur - inchangee

---

## 8. Estimation effort

| Tache | Effort |
|-------|--------|
| Creation/modification table config | 0.5j |
| Modification PVE IDE 145 | 0.5j |
| Tests unitaires | 1j |
| Tests integration | 0.5j |
| Documentation | 0.5j |
| **Total** | **3 jours** |

---

## 9. Risques

| Risque | Probabilite | Impact | Mitigation |
|--------|-------------|--------|------------|
| Regression calcul dates | Moyenne | Eleve | Tests exhaustifs |
| Performance (calcul supplementaire) | Faible | Faible | Calcul simple |
| Erreur seuil config | Faible | Moyen | Validation valeur > 0 |

---

## Validation

- [ ] Validation metier de la solution
- [ ] Validation technique Magic
- [ ] Identification table configuration exacte
- [ ] Planification developpement
- [ ] Environnement de test disponible

---

*Specification: 2026-01-13*
*Statut: EN ATTENTE VALIDATION*

---

*DerniÃ¨re mise Ã  jour : 2026-01-22T18:55*
