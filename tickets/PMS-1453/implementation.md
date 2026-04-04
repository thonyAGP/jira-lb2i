# PMS-1453 - Implementation

> **Jira** : [PMS-1453](https://clubmed.atlassian.net/browse/PMS-1453)

## Programme a modifier

| Projet | IDE | Nom | Fichier |
|--------|-----|-----|---------|
| ADH | 307 | Saisie transaction Nouv vente | Prg_307.xml |
| ADH | 313 | Saisie transaction Nouv vente (variante) | Prg_313.xml |

## Modifications requises

### 1. Ajouter Picture de validation sur colonnes FIELD_TIME

**Localisation** : ADH IDE 307, Tache 307.37 "Affiche details transfert"

**Colonnes a modifier** :
- Column id="5" - W1 Heure transfert Aller (ligne ~31823)
- Column id="13" - W1 Heure transfert Retour (ligne ~31880)

**Modification** : Ajouter `<Picture id="157" valUnicode="HH:MM"/>` dans PropertyList

### 2. XML Avant/Apres

**AVANT** (Column id="5"):
```xml
<Column id="5" name="W1 Heure transfert Aller">
  <PropertyList model="FIELD">
    <Model attr_obj="FIELD_TIME" id="1"/>
    <_FieldStyle id="276" val="1"/>
  </PropertyList>
</Column>
```

**APRES** :
```xml
<Column id="5" name="W1 Heure transfert Aller">
  <PropertyList model="FIELD">
    <Model attr_obj="FIELD_TIME" id="1"/>
    <Picture id="157" valUnicode="HH:MM"/>
    <_FieldStyle id="276" val="1"/>
  </PropertyList>
</Column>
```

### 3. Verification Prg_313.xml

Appliquer la meme correction sur le programme variante si les memes colonnes existent.

## Tests de validation

| Scenario | Entree | Attendu |
|----------|--------|---------|
| Heure valide | 10:30 | Accepte |
| Heure limite min | 00:00 | Accepte |
| Heure limite max | 23:59 | Accepte |
| Heure invalide | 70:00 | Erreur format |
| Heure invalide | 24:00 | Erreur format |

## Commits

*Aucun commit pour l'instant*

---

*Derniere mise a jour : 2026-01-26*
