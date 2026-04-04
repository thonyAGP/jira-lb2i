# PMS-1381 - Messages de verrouillage pendant la PURGE

> **Jira** : [PMS-1381](https://clubmed.atlassian.net/browse/PMS-1381)
> **Protocole** : `.claude/protocols/ticket-analysis.md` appliqué

---

## 1. Contexte Jira

| Élément | Valeur |
|---------|--------|
| **Symptôme** | Messages de verrouillage pendant la purge intersaison |
| **Application** | Archivage -V 4.17 (09/09/2025) |
| **Programme** | CP0001 - Purge et restructuration |
| **Village** | DSIOP |
| **Reporter** | Jessica Palermo |
| **Date** | 2025-09-24 |

### Tables verrouillées (captures d'écran)

| Table | Message |
|-------|---------|
| `pv_customer_dat` | Attente pour enregistrement verrouillé |
| `pv_cafil18_dat` | Attente pour enregistrement verrouillé |
| `cafil008_dat` | Attente pour enregistrement verrouillé |
| `cafil012_dat` | Attente pour enregistrement verrouillé |
| `cafil014_dat` | Attente pour enregistrement verrouillé |
| `cctotal` | Attente pour enregistrement verrouillé |

---

## 2. Localisation Programme

### Programme principal identifié

| Projet | IDE | Fichier | Nom | Public Name |
|--------|-----|---------|-----|-------------|
| **PUG** | **18** | Prg_101.xml | **Purge Batch** | **PURGE** |

### Programmes associés (dossier Purge)

| IDE | Fichier | Nom | Rôle |
|-----|---------|-----|------|
| 12 | Prg_9.xml | Delete GMR adh=0 | Nettoyage GM sans adhérent |
| 13 | Prg_10.xml | Delete GMR cpte=0 | Nettoyage GM sans compte |
| 14 | Prg_11.xml | Purge Point de vente | Purge POS |
| 15 | Prg_12.xml | Recherche Due | Recherche dues |
| 16 | Prg_71.xml | Purge SQL par adherent | Purge SQL |
| 17 | Prg_97.xml | Lancement Purge | Interface lancement |
| **18** | **Prg_101.xml** | **Purge Batch** | **Programme principal** |
| 19 | Prg_108.xml | test purge | Tests |
| 22 | Prg_103.xml | Lancement UNITAIRE de la Purge | Purge unitaire |

---

## 3. Structure du programme PUG IDE 18

### Sous-tâches principales

```
PUG IDE 18 - Purge Batch
│
├── 18.1  Station eteinte erreur v1
├── 18.2  Station eteinte erreur T2H
├── 18.3  Lecture paramètres PAR
├── 18.4  Lecture de date purge
├── 18.5  Lecture date comptable
├── 18.6  Lecture Paramètres tel
├── 18.7  Lecture Param Purge
├── 18.8  Creat. Enreg Date purge
├── 18.9  Blocage des comptes à purger
│   ├── Recherche GM
│   │   ├── Comptes Speciaux
│   │   ├── GMC
│   │   ├── Personnel
│   │   ├── Client
│   │   └── Validation
│   ├── Date max opération
│   └── Check Pending Payment
│
├── 18.10 **Purge (1ère partie)**     ◄── VERROUILLAGES ICI
│   ├── Purge depot_garantie___dga
│   ├── Purge caisse_vente orphelin
│   ├── Purge caisse_vente
│   ├── **Purge GMR**                 ◄── cafil008_dat
│   ├── Purge telephone
│   ├── Purge comptable
│   ├── Export conso
│   └── **Purge Hebergement**         ◄── cafil012_dat
│
└── 18.11 **Purge (2ème partie)**     ◄── VERROUILLAGES ICI
    ├── Purge Change
    ├── Purge EZCard
    ├── Purge GM
    ├── Purge transac
    ├── Purge CC comptable
    ├── **Purge CC total**            ◄── cctotal
    ├── Purge CC par type
    ├── Purge CC type detail
    ├── Purge Plafond
    ├── Purge TAIGM
    └── Purge caisse
```

---

## 4. Tables concernées

### Tables PMS (source)

| Table | Nom physique | Rôle | Accès |
|-------|--------------|------|-------|
| pv_customer_dat | pv_customer_dat | Clients POS | WRITE |
| pv_cafil18_dat | pv_cafil18_dat | Données cafil18 POS | WRITE |
| cafil008_dat | cafil008_dat | gm-recherche | WRITE |
| cafil012_dat | cafil012_dat | hebergement | WRITE |
| cafil014_dat | cafil014_dat | client | WRITE |
| cctotal | cctotal | cc_total | WRITE |

### Tables Archive (destination)

| Table source | Table archive |
|--------------|---------------|
| cafil008_dat | arc_cafil008_dat |
| cafil012_dat | arc_cafil012_dat |
| cafil014_dat | arc_cafil014_dat |
| cctotal | arc_cctotal |
| pv_customer_dat | arc_pv_customer_dat |

---

## 5. Root Cause

### Cause des verrouillages

| Élément | Description |
|---------|-------------|
| **Contexte** | Purge intersaison (24/09/2025) |
| **Problème** | Verrouillages de type "Attente pour enregistrement verrouillé" |
| **Cause** | Accès concurrent aux tables en mode WRITE |

### Analyse technique

1. **Accès WRITE simultanés** : Le programme de purge accède à de nombreuses tables en mode WRITE (Access val="W"). Si d'autres processus (utilisateurs, batches) accèdent aux mêmes enregistrements, Magic affiche le message d'attente.

2. **Processus concurrent** : Pendant l'intersaison, plusieurs processus peuvent s'exécuter en parallèle :
   - Purge batch
   - Import de données
   - Accès utilisateur aux écrans de consultation

3. **Comportement Magic** : Le message "Attente pour enregistrement verrouillé" indique que Magic attend la libération du verrou plutôt qu'un échec. C'est un comportement **normal** de gestion de concurrence.

---

## 6. Diagnostic

### Le message est-il une erreur ?

**NON** - Le message "Attente pour enregistrement verrouillé" est un **message informatif**, pas une erreur.

| Type | Comportement |
|------|-------------|
| **Attente** | Magic attend que le verrou soit libéré |
| **Timeout** | Si le timeout est atteint, alors erreur |
| **Succès** | Si le verrou est libéré à temps, la purge continue |

### Impact observé

Les captures d'écran montrent que :
1. La purge **continue** malgré les messages (pas de blocage fatal)
2. Les dates de solde des adhérents sont affichées (le traitement avance)
3. Le message est affiché dans la barre de statut (information)

---

## 7. Recommandations

### Option 1 : Lancer la purge en période creuse (RECOMMANDÉ)

| Action | Détail |
|--------|--------|
| **Horaire** | Lancer la purge la nuit ou très tôt le matin |
| **Vérification** | S'assurer qu'aucun autre batch ne tourne |
| **Communication** | Informer les utilisateurs de ne pas accéder au système |

### Option 2 : Augmenter le timeout de verrouillage

Dans le fichier `magic.ini` ou les paramètres serveur, augmenter la valeur de timeout pour les verrous :

```ini
[MAGIC_ENV]
LockTimeout=300  ; Timeout en secondes (défaut: 60)
```

### Option 3 : Mode exclusif (si supporté)

Lancer l'application Archivage avec un paramètre de mode exclusif pour empêcher les accès concurrents pendant la purge.

---

## 8. Données des captures

### Captures analysées

| Capture | Table verrouillée | Phase purge | Adhérents traités |
|---------|-------------------|-------------|-------------------|
| image-20250924-072240.png | pv_customer_dat | 1ère partie | 00193353, 00193871... |
| image-20250924-072553.png | pv_cafil18_dat | 1ère partie | 00197203, 00197201... |
| image-20250924-072919.png | cafil008_dat | 1ère partie | 00200917, 00200993... |
| image-20250924-072945.png | cafil012_dat | 1ère partie | 00197514, 00197507... |
| image-20250924-073211.png | cafil014_dat | 2ème partie | 00176277, 00176279... |
| image-20250924-073358.png | cctotal | 2ème partie | 00187777, 00187737... |

---

## 9. Conclusion

| Élément | Verdict |
|---------|---------|
| **Bug ?** | **NON** - Comportement normal de gestion de concurrence |
| **Correction requise ?** | Non obligatoire |
| **Action recommandée** | Planifier la purge en période creuse |

Le message "Attente pour enregistrement verrouillé" est un message informatif de Magic indiquant qu'il attend la libération d'un verrou. C'est le comportement attendu lors d'accès concurrents. La purge continue normalement une fois le verrou libéré.

---

## Références Magic IDE

### Programmes

| IDE | Projet | Nom | Fichier |
|-----|--------|-----|---------|
| 18 | PUG | Purge Batch | Prg_101.xml |
| 17 | PUG | Lancement Purge | Prg_97.xml |
| 14 | PUG | Purge Point de vente | Prg_11.xml |

---

*Dernière mise à jour : 2026-01-22T21:00*
*Diagnostic : Message informatif de gestion de concurrence, pas une erreur*
