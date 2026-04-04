# PMS-1414 - Validation groupee seminaire

> **Jira** : [PMS-1414](https://clubmed.atlassian.net/browse/PMS-1414)

## Informations Jira

| Champ | Valeur |
|-------|--------|
| **Titre** | Validation groupee d'un seminaire |
| **Type** | Bug |
| **Priorite** | Haute |
| **Statut** | Backlog |
| **Reporter** | Davide Morandi |
| **Cree** | 2025-11-18 |

## Description du probleme

Lors de la validation groupee d'un seminaire, le systeme exige le vol retour alors que :
- Le GM peut arriver par **vol aller** uniquement
- Le GM peut arriver par **VV2** (Village/Village) sans vol retour requis

**Comportement attendu** : La validation doit etre possible si l'arrivee est par vol aller OU par VV (Village/Village).

---

## Analyse Magic IDE (2026-01-19)

### Programme principal

| Projet | IDE | Nom | Public Name | Fichier Source |
|--------|-----|-----|-------------|----------------|
| **PBG** | **124** | Validation Arrivants | VALIDATION_ARRIVANTS | Prg_56.xml |

> **Calcul position** : Progs.xml ligne 254 contient id="56" -> Position = 254 - 131 + 1 = **124**

### Arborescence complete des taches

```
PBG IDE 124 - Validation Arrivants (Main, ISN_2=1)
|
+-- Tache 124.1 - Determination Age Bebe (ISN_2=2)
+-- Tache 124.2 - Test Base Validation (ISN_2=3)
+-- Tache 124.3 - Affichage Validation (ISN_2=4)  <-- Ecran principal
|    |
|    +-- Tache 124.3.1 - Affichage Hebergement (ISN_2=5)
|    +-- Tache 124.3.2 - Affichage Prestations (ISN_2=6)
|    +-- Tache 124.3.3 - Affichage Circuits (ISN_2=7)
|    +-- Tache 124.3.4 - Recherche Nom (ISN_2=9)
|    +-- Tache 124.3.5 - Validation Arrivant (ISN_2=10)  <-- Expressions VV
|    |    |
|    |    +-- Tache 124.3.5.1 - Verif Logement et Vol (ISN_2=11)
|    |    +-- Tache 124.3.5.2 - Creation VV Aller (ISN_2=12)
|    |    +-- Tache 124.3.5.3 - Creation VV Retour (ISN_2=13)
|    |    +-- Tache 124.3.5.4 - Zoom Village/Village (ISN_2=14)
|    |    +-- Tache 124.3.5.5 - Validation Arrivee (ISN_2=16)
|    |    +-- Tache 124.3.5.6 - Validation Credit Bar (ISN_2=70)
|    |
|    +-- Tache 124.3.6 - Devalidation Arrivant (ISN_2=25)
|    +-- Tache 124.3.7 - Validation Serie (ISN_2=34)  <-- SEMINAIRES
|    |    |
|    |    +-- Tache 124.3.7.1 - Verif Existence Groupe Vol (ISN_2=35)  <-- POINT CLE
|    |    +-- Tache 124.3.7.2 - Verif Existence Groupe/Transf (ISN_2=78)
|    |    +-- Tache 124.3.7.3 - Verif Existence Seminaire (ISN_2=36)
|    |    +-- Tache 124.3.7.4 - Validation Automatique v1 (ISN_2=38)
|    |    +-- Tache 124.3.7.5 - Validation Automatique TRA 2.0 (ISN_2=81)
|    |    +-- Tache 124.3.7.6 - Zoom Village/Village (ISN_2=49)
|    |
|    +-- Tache 124.3.8 - Liste des Filiations (ISN_2=52)
|    +-- Tache 124.3.9 - Arr.differee (ISN_2=59)
|    +-- Tache 124.3.10 - Lecture email (ISN_2=65)
|
+-- Tache 124.4 - Test fdp Turquie (ISN_2=90)
```

### Expressions de verification vol (Tache 124.3.7.1)

| Expression | Formule | Description |
|------------|---------|-------------|
| **56** | `'Code vol aller non renseigne !'` | Message erreur vol aller |
| **57** | `W2-New-Code-Vol-Aller=''` | Vol aller vide |
| **58** | `'Code vol retour non renseigne !'` | Message erreur vol retour (BLOQUANT) |
| **59** | `W2-New-Code-Vol-Retour=''` | Vol retour vide |

### Variables DataView - Tache 124.3.7 (Validation Serie)

| Position | Column ID | Nom variable | Role |
|----------|-----------|--------------|------|
| 0 | 18 | v.choix GroupArriv ou Seminaire | Choix mode |
| 1 | 19 | v.titre | Titre ecran |
| 2 | 20 | W2-Liste Combo Vols | Liste deroulante vols |
| 4 | 21 | W2-Autorisation | Flag autorisation |
| 5 | 22 | W2-Accord Suite | Flag suite |
| 6 | 23 | W2-Date Arrivee | Date arrivee prevue |
| 8 | 25 | W2-Code-Vol | Code vol selectionne |
| 10 | 27 | W2-Code-Vol-Aller | Code vol aller actuel |
| 11 | 28 | W2-Code-Vol-Retour | Code vol retour actuel |
| **12** | **29** | **W2-New-Code-Vol-Aller** | Nouveau code vol aller → `{0,12}` |
| 14 | 31 | **W2-New-Code-Vol-Retour** | Nouveau code vol retour → `{0,14}` |

### Expressions VV (Tache 124.3.5 - Validation Arrivant)

Ces expressions sont dans une tache differente, utilisees pour la validation individuelle :

| Expression | Formule | Description |
|------------|---------|-------------|
| **12** | `{0,4}='VV1' OR {0,4}='VV2' OR {0,4}='VV3'` | Type transport aller = VV |
| **13** | `{0,5}='VV1' OR {0,5}='VV2' OR {0,5}='VV3'` | Type transport retour = VV |
| **27** | Idem 12 | Doublon aller VV |
| **28** | `({0,5}='VV1' OR {0,5}='VV2' OR {0,5}='VV3') AND {0,10}<>'N'` | Retour VV ET confirme |

> **Important** : Les expressions VV sont definies dans Tache 124.3.5 mais la Tache 124.3.7 (Validation Serie) ne semble PAS utiliser ces expressions.

### Tables utilisees

| N Table | Projet | Nom Physique | Description |
|---------|--------|--------------|-------------|
| **30** | REF | cafil014_dat | Table filiations (compte GM) |
| **31** | REF | cafil015_dat | Table planning GM |
| **34** | REF | cafil014_dat | Filiations (jointure) |
| **104** | REF | (a verifier) | Table hebergement |
| **131** | REF | (a verifier) | Table validation |
| **134** | REF | cafil112_dat01 | Table vols/transport |

---

## PISTES DE RECHERCHE CONCRETES

### PISTE 1 : Condition de blocage vol retour (HAUTE PRIORITE)

**Objectif** : Trouver OU Expression 59 (vol retour vide) bloque la validation dans Tache 124.3.7.1.

**Actions** :
1. Chercher `Condition val="59"` dans la Logic de Tache 124.3.7.1
2. Chercher les operations `STP Mode="E"` (Error) qui utilisent Expression 58
3. Verifier quelle condition combine Expression 59 avec le type transport

**Commande MCP** :
```
magic_get_line(project="PBG", taskPosition="124.3.7.1", lineNumber=*)
```
> Note: L'offset est calculé automatiquement par OffsetCalculator

### PISTE 2 : Absence d'expressions VV dans Validation Serie (HAUTE PRIORITE)

**Constat** : Les expressions VV (12, 13, 27, 28) sont dans Tache 124.3.5, pas dans Tache 124.3.7.

**Hypothese** : La Tache 124.3.7 "Validation Serie" n'a PAS de logique pour bypasser le vol retour quand le mode est VV. Elle verifie uniquement si les codes vol sont remplis.

**Actions** :
1. Verifier si la Tache 124.3.7.1 a des expressions pour le type transport
2. Si non, creer des expressions similaires a 12/13 pour cette tache
3. Ajouter condition : `NOT(type_transport_retour IN ('VV1','VV2','VV3'))` avant l'erreur

### PISTE 3 : Validation vol aller seul (MOYENNE PRIORITE)

**Objectif** : Permettre vol aller seul (type 'A') sans vol retour.

**Hypothese** : Meme si le type transport aller = 'A' (vol), le systeme exige un vol retour.

**Actions** :
1. Analyser la condition complete de l'erreur vol retour
2. Verifier si type_transport_aller est pris en compte
3. Ajouter condition : `OR type_transport_aller = 'A'`

### PISTE 4 : Comparaison avec validation individuelle (BASSE PRIORITE)

**Contexte** : La validation individuelle (Tache 124.3.5) fonctionne correctement avec VV.

**Actions** :
1. Comparer la logique de Tache 124.3.5 vs Tache 124.3.7
2. Identifier les expressions manquantes dans 124.3.7
3. Recopier/adapter la logique VV

---

## SOLUTION POTENTIELLE

### Diagnostic principal

La Tache 124.3.7 "Validation Serie" (seminaires) ne possede probablement PAS les memes conditions VV que la Tache 124.3.5 "Validation Arrivant" (individuel).

### Modification proposee

**Dans Tache 124.3.7.1 - Verif Existence Groupe Vol** :

Ajouter une expression qui teste le type transport :
```
Expression XX : {parent,type_transport_retour}='VV1'
             OR {parent,type_transport_retour}='VV2'
             OR {parent,type_transport_retour}='VV3'
```

Modifier la condition de l'erreur vol retour :
```
AVANT : SI W2-New-Code-Vol-Retour = ''
        ALORS Erreur "Code vol retour non renseigne !"

APRES : SI W2-New-Code-Vol-Retour = ''
           ET Type_Transport_Retour NOT IN ('VV1','VV2','VV3')
           ET Type_Transport_Aller <> 'A'
        ALORS Erreur "Code vol retour non renseigne !"
```

### Localisation precise du fix

| Element | Valeur |
|---------|--------|
| **Programme** | PBG IDE 124 - Validation Arrivants |
| **Tache** | Tache 124.3.7.1 - Verif Existence Groupe Vol |
| **Expression a modifier** | Condition utilisant Expression 59 |
| **Modification** | Ajouter condition OR sur type transport VV/vol aller |

---

## DONNEES REQUISES POUR VALIDER

| Element | Detail |
|---------|--------|
| **Base de donnees** | Village avec seminaires actifs |
| **Scenario de test 1** | Seminaire avec GM arrivant par vol aller seul |
| **Scenario de test 2** | Seminaire avec GM arrivant par VV2 (sans vol retour) |
| **Table a extraire** | cafil014_dat (filiations avec type transport) |

---

## Questions pour clarification

1. **Quel village teste ?** - Pour avoir les bonnes donnees seminaire
2. **Le mode VV fonctionne-t-il en validation individuelle ?** - Confirmer que seul le mode serie pose probleme
3. **Message d'erreur exact ?** - "Code vol retour non renseigne !" ou autre formulation ?
4. **Ecran concerne ?** - Interface de validation groupee seminaire (Tache 124.3.7)

---

*Derniere mise a jour: 2026-01-19*
*Status: INVESTIGATION EN COURS - Diagnostic : expressions VV manquantes dans Tache 124.3.7*
*Programme: PBG IDE 124 - Validation Arrivants (source: Prg_56.xml)*

---

*DerniÃ¨re mise Ã  jour : 2026-01-22T18:55*
