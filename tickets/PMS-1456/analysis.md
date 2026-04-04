# PMS-1456 : Planning Print - Fiches police Italie (PRAC & CFAC)

> **Analyse**: 2026-03-31 16:30 → 17:00
> **Statut**: En cours — En attente retour Jessica (atelier prestataire)
> **Priorité**: Critique

## 1. Contexte

Les villages italiens (PRAC = Pragelato, CFAC = Cefalù) ont une obligation légale d'enregistrer les données des GM auprès de la police locale. Actuellement, un prestataire externe envoie un lien par email au GM pour collecter ses infos, puis les GO téléchargent un fichier Excel pour le charger sur le site de la police.

**Problème** : Le tableau Excel contient des formules que les GO suppriment régulièrement, causant des erreurs.

**Demande** : Générer cet Excel directement depuis PMS (Planning Print) pour éliminer le prestataire et les erreurs manuelles.

## 2. Spécifications fonctionnelles

### 2.1 Pré-requis : champ PROPERTY ID

Dans l'écran **Caisse Gestion (CG0076 - Paramètres d'initialisation)**, ajouter un champ "Matricule" (PROPERTY ID) fourni par la police. Visible sur la capture : section "Fiche police" en bas à droite de l'écran.

### 2.2 Export Excel - Colonnes requises

| Colonne | Contenu | Source PMS | Format |
|---------|---------|------------|--------|
| **A** | PROPERTY ID | Champ "Matricule" (Caisse Gestion) | Code fixe par village |
| **B** | BOOKING REF | Numéro d'adhérent (identifie le foyer fiscal) | Numérique |
| **C** | CHECK-IN | Date d'arrivée du GM | `DD-MM-YYYY` (tirets, PAS slashes) |
| **D** | CHECK-OUT | Date de départ du GM | `DD-MM-YYYY` |
| **E** | NUMBER OF GUEST | Nombre de GM de la même filiation séjournant au village | Entier |
| **F** | LANGUAGE | Langue selon nationalité (code pays réservation) | FR→"French", IT→"Italian", ES→"Spanish", autres→"English" |
| **G** | EMAIL | Email du compte maître (sinon filiation suivante, sinon vide) | Texte |
| **H** | ROOM CODE | Code logement chambre (C4.C2) | Texte |
| **I** | ROOM NAME | Nom de la chambre tel qu'indiqué dans PMS | Texte |
| **J** | GUEST NAME | Prénom + Nom (compte maître uniquement) | "Giampietro Angelucci" |
| **K** | *(non utilisé)* | Vide mais colonne obligatoire | — |
| **L** | *(non utilisé)* | Vide mais colonne obligatoire avec intitulé | — |

### 2.3 Règles métier

- **Colonnes C/D** : Format date avec TIRETS (`20-02-2020`), PAS le format classique (`20/02/2020`)
- **Colonne E** : Compter les GM de la même filiation présents au village
- **Colonne F** : Mapping nationalité → langue EN ANGLAIS :
  - FR → "French"
  - IT → "Italian"
  - ES → "Spanish"
  - Tout autre pays → "English"
- **Colonne G** : Cascade email : compte maître → filiation suivante → ... → vide si aucun
- **Colonne J** : Uniquement le compte maître, format "Prénom Nom"
- **Colonnes K/L** : Présentes avec intitulé mais jamais remplies

## 3. Localisation programmes

### 3.1 Écran Caisse Gestion (ajout champ Matricule)

L'écran CG0076 est dans le projet **GES** (Gestion). Le champ "Fiche police / Matricule" doit être ajouté dans la table de paramétrage village.

### 3.2 Planning Print (génération Excel)

Le module Planning Print est dans le projet **PBG** (Planification/Batch). L'export Excel doit être ajouté comme nouvelle option dans le menu d'impression planning.

### 3.3 Tables source

| Table | Données |
|-------|---------|
| `adherent` / `cafil001_dat` | Numéro adhérent, nom, prénom |
| `reservation` | Dates séjour, filiation |
| `logement` / `chambre` | Code et nom chambre |
| `pays` / nationalité | Code pays pour mapping langue |
| Paramètres village | PROPERTY ID (nouveau champ) |

## 4. Statut et prochaines étapes

**En attente** : Jessica Palermo devait compléter le ticket après un atelier avec le prestataire le 12/03. Son dernier commentaire confirme la mise à jour.

### Points à clarifier

1. Le format exact du fichier Excel attendu par le site de la police (PJ `Bookings_Italy.xlsx` = template de référence)
2. Faut-il filtrer par dates (arrivées du jour ? de la semaine ?)
3. Le champ PROPERTY ID est-il unique par village ou par saison ?
4. Quelle est la volumétrie attendue (nombre de lignes par export) ?

## 5. Estimation effort

| Composant | Effort |
|-----------|--------|
| Ajout champ Matricule (CG0076) | 0.5j |
| Requête SQL extraction données | 1j |
| Génération Excel avec formatage | 1j |
| Tests sur PRAC/CFAC | 0.5j |
| **Total estimé** | **3j** |
