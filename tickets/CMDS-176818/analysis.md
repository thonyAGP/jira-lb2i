# Analyse CMDS-176818

> **Jira** : [CMDS-176818](https://clubmed.atlassian.net/browse/CMDS-176818)

## Symptome

**Tickets Epson imprimes avec police trop grande et partie droite coupee**

Sur le village Valmorel (Exclusive Collection), les tickets PMS (extraits de compte, etc.) sortent :
1. Avec une police de caracteres trop grande
2. Avec la partie droite coupee (montants non visibles)

### Exemple du ticket (IMG_7438.pdf)

| Element | Affichage | Attendu |
|---------|-----------|---------|
| Titre | "Extrait c" | "Extrait compte" |
| Sous-total | "Sous-t" | "Sous-total" |
| Colonnes | "Libelle Operation / Operati" | "Libelle Operation / Operation" |
| Montants | **NON VISIBLES** | Montants en EUR |

## Contexte

| Element | Valeur |
|---------|--------|
| **Village** | Valmorel (VVALMOREL) |
| **Type** | Incident materiel |
| **Priorite** | Basse |
| **Status** | En cours de traitement |
| **Reporter** | Exclusive Collection Space Conciergerie Valmorel |
| **Assignee** | Yohan FREDERIC |
| **Cree** | 2026-01-09 |

## Equipement concerne

| Equipement | Modele | Probleme |
|------------|--------|----------|
| **Imprimante ticket** | Epson (modele ?) | Police trop grande, ticket coupe |
| Imprimante bureau | HP LaserJet Pro M404-M405 (HP8D45BD) | Ne fonctionne pas (autre probleme) |

## Diagnostic

### Cause probable : Configuration imprimante

Ce n'est **PAS un bug dans le code Magic/PMS**. C'est un probleme de configuration :

| Hypothese | Probabilite | Verification |
|-----------|-------------|--------------|
| **Largeur papier mal configuree** | HAUTE | Verifier parametres imprimante Epson |
| **Driver imprimante incorrect** | MOYENNE | Reinstaller driver Epson |
| **DPI/Resolution incorrecte** | MOYENNE | Verifier parametres impression |
| **Police imprimante modifiee** | BASSE | Reset configuration Epson |

### Points a verifier (cote village)

1. **Parametres imprimante Epson** :
   - Largeur papier (80mm standard pour tickets)
   - Mode impression (normal vs condensed)
   - Police par defaut

2. **Configuration PMS** :
   - Fichier INI imprimante
   - Mapping imprimante dans PMS

3. **Driver Windows** :
   - Version du driver Epson
   - Parametres par defaut du driver

## Historique des echanges

| Date | Intervenant | Action |
|------|-------------|--------|
| 09/01 12:10 | Conciergerie | Ouverture ticket - message "plus de papier" |
| 09/01 14:29 | Valery Pores | Constat: police grande, ticket incomplet |
| 09/01 14:33 | Yohan Frederic | Demande exemple ticket |
| 09/01 14:56 | Lena | Confirme probleme sur extraits PMS |
| 09/01 15:21 | Lena | Envoie photo ticket + signale pb HP |
| 09/01 15:47 | Yohan Frederic | Demande appel Teams |

## Resolution recommandee

### Action immediate (Yohan/Support)

1. **Verifier config Epson** via appel Teams
2. **Reset parametres imprimante** aux valeurs usine
3. **Reinstaller driver** si necessaire

### Verification PMS (si probleme persiste)

Si apres reset imprimante le probleme persiste, verifier dans PMS :

| Programme | Role | Verification |
|-----------|------|--------------|
| ADH IDE 73 | EXTRAIT_IMP | Parametres edition ticket |
| ADH IDE 69 | EXTRAIT_COMPTE | Configuration impression |

**Table parametres impression** : Verifier obj=XXX pour config imprimante village

## Pieces jointes

| Fichier | Description |
|---------|-------------|
| `IMG_7438.pdf` | Photo du ticket coupe (preuve du bug) |
| `Outlook-kdu1eczm.png` | Logo Le Lodge Exclusive Collection |

## Conclusion

**Type** : Incident materiel / Configuration
**Impact code Magic** : AUCUN
**Resolution** : Support technique imprimante

---

$12026-01-22T18:55*
*Statut: DIAGNOSTIC - Probleme configuration imprimante*
