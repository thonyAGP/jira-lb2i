# PMS-1412 - POS SKI: Loi japonaise impression facture obligatoire

> **Jira** : [PMS-1412](https://clubmed.atlassian.net/browse/PMS-1412)

## Contexte

| Element | Valeur |
|---------|--------|
| **Status Jira** | En cours |
| **Priorite** | Moderee |
| **Label** | PVE |
| **Reporter** | Davide Morandi |
| **Assignee** | Anthony Leberre |
| **Date creation** | 17/11/2025 |

## Demande

Au **Japon**, une loi oblige a conserver une copie des factures **en papier pendant 10 ans**.

Avec le projet **MRE** (ecrans tactiles), les clients peuvent :
- Envoyer la facture par **mail**
- **OU** imprimer les 2 copies

**DEMANDE** : Creer un **code projet** qui, si active, **imprime automatiquement** une copie signee de la facture meme si la facture est envoyee par mail.

---

## Analyse Technique

### Programmes concernes

| Projet | IDE | Nom | Fichier XML | Role |
|--------|-----|-----|-------------|------|
| **PVE** | **204** | Choice Re_Print Invoice | Prg_198.xml | Interface selection impression/mail |
| **PVE** | **205** | Edition ticket (Tva) LEX | Prg_199.xml | Generateur facture/ticket |
| **PVE** | **186** | Main Sale | Prg_180.xml | Programme principal vente |

> **Note** : Prg_198.xml (ISN=198) correspond a PVE IDE **204** (ligne 348 - 144 = 204)
> Prg_199.xml (ISN=199) correspond a PVE IDE **205** (ligne 349 - 144 = 205)

### Variables globales (Main PVE IDE 1)

Les codes projets sont declares dans le **Main** avec le prefixe **VG.**

| Variable Main | Column ID | Type | Statut | Description |
|---------------|-----------|------|--------|-------------|
| **VG.Recu vente Japon** | 175 | Logical | **EXISTE DEJA** | Code projet pour le Japon |
| VG.FACTURE TVA | 27 | Logical | Actif | Facture TVA actif |
| VG.Envoi Impress recu de vente | 149 | Logical | Actif | Envoi impression recu |
| VG.Facture THAI new | 157 | Logical | Actif | Facture Thailande |
| VG. Japan China DIN | 185 | Logical | Actif | Japan China DIN |

### Variables dans PVE IDE 204 (Prg_198.xml)

| Variable | Column ID | Type | Role |
|----------|-----------|------|------|
| **v.Mail** | 30 | Logical | Decision utilisateur (mail ou print) |
| v.Envoi Email | 19 | Logical | Flag envoi email |
| V Print Preview | 5 | Logical | Apercu avant impression |
| V Copy | 6 | Numeric | Nombre de copies |
| v.Adresse Mail | 17 | Alpha | Adresse email client |

### Variables dans PVE IDE 205 (Prg_199.xml)

| Variable | Column ID | Type | Role |
|----------|-----------|------|------|
| **p.Mail** | 54 | Logical | Parametre controle mail (recu de 204) |
| P. PrintAgainExecution | 18 | Logical | Re-impression execution |
| P. PrintAgainPreview | 19 | Logical | Re-impression preview |
| P. Facture | 20 | Logical | Mode facture |
| v.print separateur | 48 | Logical | Print separateur |

### Flux actuel

```
[Client termine achat]
        |
        v
[PVE IDE 204 - Choice Re_Print Invoice]
        |
        v
[Choix: PRINT ou EMAIL?]
        |
    +---+---+
    |       |
    v       v
[EMAIL]   [PRINT]
    |       |
    v       v
[v.Mail=TRUE]  [v.Mail=FALSE]
    |       |
    v       v
[PVE IDE 205 - Edition ticket (Tva) LEX]
        |
        v
[p.Mail recoit valeur de v.Mail]
        |
        v
[IF p.Mail=TRUE: envoi email uniquement]
[IF p.Mail=FALSE: impression directe]
```

---

## Solution proposee

### Code projet EXISTANT a utiliser

**VG.Recu vente Japon** (Column id=175) existe deja dans le Main PVE mais n'est **pas encore utilise**.

Il faut :
1. Activer ce code projet sur les villages japonais
2. Modifier PVE IDE 205 pour l'utiliser

### Modification PVE IDE 205 - Edition ticket (Tva) LEX

#### Localisation

- **Programme** : PVE IDE 205 - Edition ticket (Tva) LEX
- **Fichier** : `D:\Data\Migration\XPA\PMS\PVE\Source\Prg_199.xml`

#### Logique a modifier

**AVANT** (logique actuelle) :

```
Task Logic:
  IF p.Mail = TRUE
    -> Generer PDF + Envoyer email
  ELSE
    -> Imprimer directement
```

**APRES** (nouvelle logique) :

```
Task Logic:
  IF p.Mail = TRUE
    -> Generer PDF + Envoyer email
    IF VG.Recu vente Japon = TRUE  (via {32768,175})
      -> Imprimer AUSSI une copie
  ELSE
    -> Imprimer directement
```

#### Reference a la variable globale

Dans l'expression Magic, la variable globale se reference :
- **{32768,175}** = VG.Recu vente Japon

#### Condition a ajouter

```magic
p.Mail = TRUE AND {32768,175} = TRUE
```

Ou dans la sous-tache d'impression, modifier la condition :

```magic
p.Mail = FALSE OR {32768,175} = TRUE
```

---

## Implementation pas a pas (IDE Magic)

### Etape 1 : Verifier le code projet

1. Ouvrir **PVE IDE 1** (Main)
2. Aller dans **Data View** (F4)
3. Chercher **VG.Recu vente Japon** (Column id=175)
4. Verifier qu'il existe et est de type **Logical**

### Etape 2 : Modifier PVE IDE 205

#### 2.1 Localiser le bloc d'impression

1. Ouvrir **PVE IDE 205** dans l'IDE Magic
2. Aller dans **Task Logic** (Ctrl+L)
3. Trouver le bloc qui gere l'impression apres envoi mail

#### 2.2 Ajouter la condition

Option A - Modifier la condition d'impression existante :
```
IF p.Mail = FALSE OR {32768,175} = TRUE
   -> Appeler sous-tache impression
```

Option B - Ajouter un bloc apres l'envoi mail :
```
Ligne X   : IF p.Mail = TRUE AND {32768,175} = TRUE
Ligne X+1 :    Call Task -> Sous-tache impression
Ligne X+2 : End Block
```

### Etape 3 : Activer sur les villages

1. Ouvrir la configuration village pour les villages japonais
2. Activer **VG.Recu vente Japon** = TRUE

### Etape 4 : Test

1. Se connecter sur un village japonais (code projet actif)
2. Faire une vente avec envoi facture par mail
3. Verifier que :
   - Email est bien envoye
   - **ET** une copie est imprimee

---

## Points d'attention

| Point | Description | Action |
|-------|-------------|--------|
| **Code projet existant** | VG.Recu vente Japon existe deja | Utiliser ce code, ne pas en creer un nouveau |
| **MRE** | Le projet MRE utilise des ecrans tactiles | Verifier compatibilite |
| **Imprimante** | Doit etre configuree sur le poste | S'assurer que l'imprimante est definie |
| **Performance** | Double operation (mail + print) | Tester temps de reponse |

---

## Fichiers a modifier

| Fichier | Programme | Action |
|---------|-----------|--------|
| `PVE/Source/Prg_199.xml` | PVE IDE 205 | Ajouter condition avec {32768,175} |

---

## Estimation

| Tache | Effort |
|-------|--------|
| Verification code projet | 10 min |
| Modification PVE IDE 205 | 45 min |
| Tests | 30 min |
| **TOTAL** | ~1h30 |

---

*Analyse: 2026-01-21 (mise a jour)*
*Status: PRET POUR IMPLEMENTATION*

---

*DerniÃ¨re mise Ã  jour : 2026-01-22T18:55*
