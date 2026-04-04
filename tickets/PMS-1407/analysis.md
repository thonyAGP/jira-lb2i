# PMS-1407 - Validation automatique Back Office

> **Jira** : [PMS-1407](https://clubmed.atlassian.net/browse/PMS-1407)

## Informations Jira

| Champ | Valeur |
|-------|--------|
| **Titre** | [Back Office] impossible de valider en automatique |
| **Type** | Bug |
| **Priorite** | Basse |
| **Statut** | En cours |
| **Reporter** | Jessica Palermo |
| **Cree** | 2025-11-13 |

## Description

Regression: lorsque le valide en automatique, je dois pouvoir valider des GM qui sont en arrivee par VV et par vol. Cela n'est plus possible.

---

## DIAGNOSTIC FINAL : NON REGRESSION

### Commentaire Alan Lecorre (17/11/2025)

> "Cela fonctionne sur le serveur mais pas en local car tu as surement un Magic.ini avec une mauvaise configuration. **Ce n'est pas une regression**."

### Suivi (24/12/2025)

> "Il va falloir qu'on regarde ceci ensemble car j'ai refait le test chez moi qu'on avait fait ensemble et c'est OK."

---

## Analyse Magic IDE (2026-01-19)

### Programme principal

| Projet | IDE | Nom | Public Name |
|--------|-----|-----|-------------|
| **PBG** | **121** | Validation Auto filiations | VALID_AUTO_FILIATION |

> **Note** : Fichier source `Prg_59.xml` (ISN=59) → Position IDE **121** dans ProgramsRepositoryOutLine.

### Arborescence des taches

```
PBG IDE 121 - Validation Auto filiations (VALID_AUTO_FILIATION)
|
+-- Tache 121.1 - Verif Logement et Vol      <-- POINT DE VERIFICATION VV/Vol
|
+-- Tache 121.2 - Creation VV Aller
|
+-- Tache 121.3 - Creation VV retour
|
+-- Tache 121.4 - Zoom Village/Village
|
+-- Tache 121.5 - Validation Arrivee
     |
     +-- Tache 121.5.1 - Marquage Periodes
     +-- Tache 121.5.2 - Marquage Periodes Circuit
     +-- Tache 121.5.3 - Marquage Recherche
     +-- Tache 121.5.4 - Marquage Validation
     +-- Tache 121.5.5 - Creation Historique
     +-- Tache 121.5.6 - Creation Specif Greque
          |
          +-- Tache 121.5.6.1 - Creation Specif Greque (nested)
          +-- Tache 121.5.6.2 - Verif si GO Greek
```

### Parametres du programme (18 params)

| Variable | Nom | Type | Description |
|----------|-----|------|-------------|
| A | P0 Societe | Alpha | Code societe |
| B | P0 Compte | Numeric | Numero compte GM |
| C | P0 Filiation | Numeric | Numero filiation |
| D | P0 Village | Alpha | Code village |
| E | P0 Service | Alpha | Code service |
| F | P0 Date arrivee | Date | Date arrivee prevue |
| G | P0 Date depart | Date | Date depart prevue |
| H | P0 Mode creation | Alpha | Mode (A/Z/H) |
| ... | ... | ... | ... |
| P | P0 ZOOM VV Global | Logical | Flag VV global |
| Q | P0 New Code Vol ALLER | Alpha | Nouveau code vol aller |
| R | P0 New Heure ALLER | Alpha | Heure vol aller |
| S | P0 New Code Vol RETOUR | Alpha | Nouveau code vol retour |
| T | P0 New Heure RETOUR | Alpha | Heure vol retour |

### Tache 121.1 - Verif Logement et Vol (detail)

**Tables utilisees :**
- Table n°34 (REF) - Filiations (cafil014_dat)
- Table n°104 (REF) - Table liee (a identifier)

**Variable de sortie :**
- Variable CL (V.Existe chambre ?) - Logical

**Conditions de verification (Expressions) :**

| Expression | Formule | Signification |
|------------|---------|---------------|
| **16** | `H='H' AND (CJ='' OR NOT CL)` | Type Hotel ET (Pas de chambre OU chambre inexistante) |
| **17** | `H='H' AND CJ<>'' AND CL` | Type Hotel ET Chambre assignee ET existe |
| **10** | `H='A'` | Type Aller |
| **11** | `H='Z'` | Type Zone/Retour |

> **Variable H** = P0 Mode creation (valeurs: 'A'=Aller, 'Z'=Zone, 'H'=Hotel)

### Logique de validation

La validation automatique verifie :
1. **Mode de creation** (A/Z/H)
2. **Chambre assignee** (si Hotel)
3. **Existence chambre** dans la base
4. **Codes vols** (aller/retour si applicable)

---

## Conclusion

| Element | Statut |
|---------|--------|
| Bug dans le code | **NON** - Fonctionne sur serveur |
| Probleme Magic.ini local | **OUI** - Config manquante/incorrecte |
| Action requise | Verifier Magic.ini avec Jessica |

### Configuration Magic.ini a verifier

Sections susceptibles d'affecter la validation automatique :
- `[MAGIC_ENV]` - Variables d'environnement
- `[MAGIC_DATABASES]` - Connexions base de donnees
- `[MAGIC_SERVERS]` - Configuration serveurs
- `[MAGIC_LOGICAL_NAMES]` - Noms logiques (chemins tables)

### Prochaine action

**En attente** - Retest avec Jessica pour identifier la difference de config entre son poste et le serveur.

---

*Derniere mise a jour: 2026-01-19*
*Status: EN ATTENTE - Probleme de configuration locale, pas de bug code*
*Programme: PBG IDE 121 - VALID_AUTO_FILIATION (source: Prg_59.xml)*

---

*DerniÃ¨re mise Ã  jour : 2026-01-22T18:55*
