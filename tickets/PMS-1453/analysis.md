# PMS-1453 - Vente de transfert > heure erronee

> **Jira** : [PMS-1453](https://clubmed.atlassian.net/browse/PMS-1453)
> **Protocole** : `.claude/protocols/ticket-analysis.md` applique
> **Version** : Template v3.0 - ANALYSE CORRIGEE

---

## 1. Contexte Jira

| Element | Valeur |
|---------|--------|
| **Symptome** | Dans l'ecran de vente de transfert, l'utilisateur peut saisir une heure invalide (ex: 70:00) |
| **Donnees entree** | Saisie de "70:00" dans le champ heure transfert |
| **Attendu** | Le systeme devrait limiter la saisie aux heures valides (00:00 a 23:59) |
| **Obtenu** | Donnees incoherentes stockees dans la table `transfertn` |
| **Reporter** | Utilisateur metier |
| **Date** | 2026-01 |

### Indices extraits du ticket
- Ecran : Saisie vente transfert
- Table cible : `transfertn`
- Champ concerne : `trf_heure` (heure transfert Aller/Retour)

---

## 2. Localisation Programmes

### Analyse dossiers Progs.xml

| Dossier | Position | Contenu |
|---------|----------|---------|
| **Ventes** | 232-255 | Programmes ACTIFS de vente |
| **Suppr** | 289-322 | Programmes ORPHELINS/supprimes |

### Programmes ORPHELINS (a IGNORER)

| IDE | Fichier | Dossier | Statut |
|-----|---------|---------|--------|
| 304 | Prg_304.xml | Suppr | **ORPHELIN - NE PAS CORRIGER** |
| 307 | Prg_307.xml | Suppr | **ORPHELIN - NE PAS CORRIGER** |
| 313 | Prg_313.xml | Suppr | **ORPHELIN - NE PAS CORRIGER** |

> **IMPORTANT** : Ces programmes n'ont pas de PublicName et aucun CallProg ne les appelle.
> Ils sont dans le dossier "Suppr" = code mort.

### Programmes ACTIFS (dossier Ventes)

| IDE | Fichier | Nom | Colonnes heure transfert |
|-----|---------|-----|-------------------------|
| **233** | Prg_233.xml | Transaction Nouv vente avec GP | 4 colonnes |
| **234** | Prg_234.xml | Transaction Nouv vente PMS-584 | 4 colonnes |
| **235** | Prg_235.xml | Transaction Nouv vente PMS-721 | 4 colonnes |
| **236** | Prg_236.xml | Transaction Nouv vente PMS-710 | 4 colonnes |

---

## 3. Analyse Expressions

### Colonnes FIELD_TIME sans Picture (BUG)

Chaque programme (233-236) contient **4 colonnes** de saisie d'heure transfert **SANS validation Picture** :

| Colonne ID | Nom | Ligne approx | Picture |
|------------|-----|--------------|---------|
| 222 | W0 Heure du transfert Aller | ~590 | **ABSENT** |
| 234 | W0 Heure du transfert Retour | ~666 | **ABSENT** |
| 5 | W1 Heure transfert Aller | ~36943 (233) | **ABSENT** |
| 13 | W1 Heure transfert Retour | ~37000 (233) | **ABSENT** |

### Exemple code XML (Prg_233.xml ligne 590)

```xml
<Column id="222" name="W0 Heure du transfert Aller">
  <PropertyList model="FIELD">
    <Model attr_obj="FIELD_TIME" id="1"/>
    <_FieldStyle id="276" val="1"/>
    <!-- MISSING: <Picture id="157" valUnicode="HH:MM"/> -->
  </PropertyList>
</Column>
```

### Table REF (correctement definie)

La table `transfertn` dans REF/DataSources.xml definit le champ avec Picture :
```xml
<_FieldPhysical Name="trf_heure" PIC_U="HH:MM:SS" ... />
```

Mais cette validation table n'empeche pas la saisie invalide dans le programme.

---

## 4. Root Cause

| Element | Valeur |
|---------|--------|
| **Programmes** | ADH IDE 233, 234, 235, 236 (dossier Ventes) |
| **Colonnes** | id=222, 234 (W0) et id=5, 13 (W1) |
| **Expression** | PropertyList des colonnes FIELD_TIME |
| **Erreur** | Picture de validation HH:MM absente |
| **Impact** | Saisie de valeurs invalides (ex: 70:00) acceptee |

### Cause technique

Le type `FIELD_TIME` definit le format de stockage (secondes depuis minuit) mais **le Picture definit la validation de saisie**.
Sans Picture, Magic accepte n'importe quelle valeur numerique.

---

## 5. Solution

### Avant (bug)

```xml
<Column id="222" name="W0 Heure du transfert Aller">
  <PropertyList model="FIELD">
    <Model attr_obj="FIELD_TIME" id="1"/>
    <_FieldStyle id="276" val="1"/>
  </PropertyList>
</Column>
```

### Apres (fix)

```xml
<Column id="222" name="W0 Heure du transfert Aller">
  <PropertyList model="FIELD">
    <Model attr_obj="FIELD_TIME" id="1"/>
    <Picture id="157" valUnicode="HH:MM"/>
    <_FieldStyle id="276" val="1"/>
  </PropertyList>
</Column>
```

### Actions requises (16 modifications)

| Fichier | Colonne | Ligne approx | Action |
|---------|---------|--------------|--------|
| Prg_233.xml | 222 | ~590 | Ajouter Picture HH:MM |
| Prg_233.xml | 234 | ~666 | Ajouter Picture HH:MM |
| Prg_233.xml | 5 | ~36943 | Ajouter Picture HH:MM |
| Prg_233.xml | 13 | ~37000 | Ajouter Picture HH:MM |
| Prg_234.xml | 222 | ~590 | Ajouter Picture HH:MM |
| Prg_234.xml | 234 | ~666 | Ajouter Picture HH:MM |
| Prg_234.xml | 5 | ~42574 | Ajouter Picture HH:MM |
| Prg_234.xml | 13 | ~42631 | Ajouter Picture HH:MM |
| Prg_235.xml | 222 | ~590 | Ajouter Picture HH:MM |
| Prg_235.xml | 234 | ~666 | Ajouter Picture HH:MM |
| Prg_235.xml | 5 | ~39036 | Ajouter Picture HH:MM |
| Prg_235.xml | 13 | ~39093 | Ajouter Picture HH:MM |
| Prg_236.xml | 222 | ~590 | Ajouter Picture HH:MM |
| Prg_236.xml | 234 | ~666 | Ajouter Picture HH:MM |
| Prg_236.xml | 5 | ~41187 | Ajouter Picture HH:MM |
| Prg_236.xml | 13 | ~41244 | Ajouter Picture HH:MM |

---

## 6. Tests de validation

- [ ] Saisie 00:00 -> Acceptee
- [ ] Saisie 12:30 -> Acceptee
- [ ] Saisie 23:59 -> Acceptee
- [ ] Saisie 24:00 -> Rejetee
- [ ] Saisie 70:00 -> Rejetee

---

## Donnees requises

- Base de donnees : N/A (modification code source uniquement)
- Fichiers : `Prg_233.xml`, `Prg_234.xml`, `Prg_235.xml`, `Prg_236.xml`
- Table : `transfertn` (lecture seule pour verification)

---

*Analyse corrigee : 2026-01-26*
*Pattern KB : [missing-time-validation](../../patterns/missing-time-validation.md)*
*Erreur precedente : ADH IDE 307 est ORPHELIN (dossier Suppr), corrige vers IDE 233-236*
