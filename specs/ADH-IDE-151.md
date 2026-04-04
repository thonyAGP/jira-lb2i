# ADH IDE 151 - Reimpression tickets fermeture

> **Analyse**: Phases 1-4 2026-02-23 18:22 -> 18:22 (1s) | Assemblage 12:25
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | ADH |
| IDE Position | 151 |
| Nom Programme | Reimpression tickets fermeture |
| Fichier source | `Prg_151.xml` |
| Dossier IDE | Impression |
| Taches | 5 (1 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 3 |
| Complexite | **BASSE** (score 5/100) |

## 2. DESCRIPTION FONCTIONNELLE

**Reimpression tickets fermeture** permet de reimprimer les documents de cloture de session sans rejouer la fermeture complete. Appele depuis [Gestion Caisse (IDE 121)](ADH-IDE-121.md) et [IDE 298](ADH-IDE-298.md), il propose 3 types de documents : tableau recapitulatif, ticket standard et ticket appro remise. Programme simple (5 taches, 1 ecran de choix).

### Recuperation et parametrage

La tache racine (151.1) configure le contexte de reimpression. La sous-tache "Derniere session" (151.2) interroge histo_sessions_caisse_detail pour charger la derniere cloture disponible (variable EV = session, FJ = date fin). La sous-tache "parametres" (151.3) charge les preferences d'impression (numero imprimante, format).

<details>
<summary>3 taches : 151.1, 151.2, 151.3</summary>

- **151.1** - Reimpression tickets fermeture (racine, config contexte)
- **151.2** - Derniere session (lit histo_sessions_caisse_detail, delegue a [IDE 154](ADH-IDE-154.md))
- **151.3** - Parametres (charge preferences impression)

</details>

### Choix du document et impression

L'ecran de choix (151.4) **[ECRAN]** presente une grille 595x151 DLU avec les 3 types de documents reimprimables. L'utilisateur selectionne le document souhaite et la tache "imprimer" (151.5) execute le CallTask correspondant : [Ticket fermeture session (IDE 138)](ADH-IDE-138.md), [Ticket appro remise (IDE 139)](ADH-IDE-139.md) ou [Tableau recap fermeture (IDE 154)](ADH-IDE-154.md). Si erreur d'impression (variable FI), le flux s'interrompt sans impact comptable.

<details>
<summary>2 taches : 151.4, 151.5</summary>

- **151.4** - Choix **[ECRAN]** (grille selection document, 595x151 DLU)
- **151.5** - Imprimer (execute CallTask selon choix, delegue a [IDE 138](ADH-IDE-138.md), [IDE 139](ADH-IDE-139.md))

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Impression (2 taches)

Generation des documents et tickets.

---

#### <a id="t1"></a>T1 - Reimpression tickets fermeture

**Role** : Generation du document : Reimpression tickets fermeture.
**Variables liees** : FH (P2 montant ecart fermeture)
**Delegue a** : [Ticket fermeture session (IDE 138)](ADH-IDE-138.md), [Ticket appro remise (IDE 139)](ADH-IDE-139.md)

---

#### <a id="t5"></a>T5 - imprimer

**Role** : Configuration/parametrage : imprimer.
**Delegue a** : [Ticket fermeture session (IDE 138)](ADH-IDE-138.md), [Ticket appro remise (IDE 139)](ADH-IDE-139.md)


### 3.2 Traitement (2 taches)

Traitements internes.

---

#### <a id="t2"></a>T2 - Dernière session

**Role** : Traitement : Dernière session.
**Variables liees** : EV (P0 session), FJ (date fin session)
**Delegue a** : [Tableau recap fermeture (IDE 154)](ADH-IDE-154.md)

---

#### <a id="t3"></a>T3 - parametres

**Role** : Traitement : parametres.
**Delegue a** : [Tableau recap fermeture (IDE 154)](ADH-IDE-154.md)


### 3.3 Consultation (1 tache)

Ecrans de recherche et consultation.

---

#### <a id="t4"></a>T4 - Choix [ECRAN]

**Role** : Selection par l'operateur : Choix.
**Ecran** : 595 x 151 DLU (MDI) | [Voir mockup](#ecran-t4)


## 5. REGLES METIER

1 regles identifiees:

### Autres (1 regles)

#### <a id="rm-RM-001"></a>[RM-001] Negation de (erreur [V]) (condition inversee)

| Element | Detail |
|---------|--------|
| **Condition** | `NOT (erreur [V])` |
| **Si vrai** | Action si vrai |
| **Variables** | FI (erreur) |
| **Expression source** | Expression 6 : `NOT (erreur [V])` |
| **Exemple** | Si NOT (erreur [V]) â†’ Action si vrai |

## 6. CONTEXTE

- **Appele par**: [Gestion caisse (IDE 121)](ADH-IDE-121.md), [Gestion caisse 142 (IDE 298)](ADH-IDE-298.md)
- **Appelle**: 3 programmes | **Tables**: 2 (W:0 R:2 L:0) | **Taches**: 5 | **Expressions**: 6

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 5)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 151.3 | T4 | Choix | MDI | 595 | 151 | Consultation |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t4"></a>151.3 - Choix
**Tache** : [T4](#t4) | **Type** : MDI | **Dimensions** : 595 x 151 DLU
**Bloc** : Consultation | **Titre IDE** : Choix

<!-- FORM-DATA:
{
    "width":  595,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  595,
                         "fmt":  "",
                         "name":  "",
                         "h":  21,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  142,
                         "type":  "label",
                         "var":  "",
                         "y":  51,
                         "w":  311,
                         "fmt":  "",
                         "name":  "",
                         "h":  49,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  127,
                         "w":  595,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  153,
                         "type":  "checkbox",
                         "var":  "",
                         "y":  54,
                         "w":  280,
                         "fmt":  "",
                         "name":  "",
                         "h":  12,
                         "color":  "",
                         "text":  "ticket récapitulatif des opérations",
                         "parent":  4
                     },
                     {
                         "x":  235,
                         "type":  "radio",
                         "var":  "",
                         "y":  67,
                         "w":  107,
                         "fmt":  "",
                         "name":  "",
                         "h":  31,
                         "color":  "",
                         "text":  "Détaillée,Globale",
                         "parent":  4
                     },
                     {
                         "x":  327,
                         "type":  "edit",
                         "var":  "",
                         "y":  6,
                         "w":  259,
                         "fmt":  "WWW DD MMM YYYYT",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  7,
                         "type":  "button",
                         "var":  "",
                         "y":  130,
                         "w":  200,
                         "fmt":  "\u0026Quitter",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  386,
                         "type":  "button",
                         "var":  "",
                         "y":  130,
                         "w":  200,
                         "fmt":  "\u0026Imprimer",
                         "name":  "",
                         "h":  18,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  7,
                         "type":  "edit",
                         "var":  "",
                         "y":  6,
                         "w":  248,
                         "fmt":  "30",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "151.3",
    "height":  151
}
-->

<details>
<summary><strong>Champs : 3 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 153,54 | ticket récapitulatif des opérations | - | checkbox |
| 327,6 | WWW DD MMM YYYYT | - | edit |
| 7,6 | 30 | - | edit |

</details>

<details>
<summary><strong>Boutons : 2 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Quitter | 7,130 | Quitte le programme |
| Imprimer | 386,130 | Lance l'impression |

</details>

## 9. NAVIGATION

Ecran unique: **Choix**

### 9.3 Structure hierarchique (5 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **151.1** | [**Reimpression tickets fermeture** (T1)](#t1) | MDI | - | Impression |
| 151.1.1 | [imprimer (T5)](#t5) | MDI | - | |
| **151.2** | [**Dernière session** (T2)](#t2) | MDI | - | Traitement |
| 151.2.1 | [parametres (T3)](#t3) | MDI | - | |
| **151.3** | [**Choix** (T4)](#t4) [mockup](#ecran-t4) | MDI | 595x151 | Consultation |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([Appel reimpression])
    LSESS[Charger derniere session]
    PARAMS[Charger preferences]
    CHOIX{Choix document}
    RECAP[Tableau recapitulatif]
    TICKET[Ticket fermeture]
    APPRO[Ticket appro remise]
    PRINT[Lancer impression]
    CHERR{Erreur impression}
    ENDOK([Fin OK])
    ENDKO([Fin KO])

    START --> LSESS
    LSESS --> PARAMS
    PARAMS --> CHOIX
    CHOIX -->|Recap| RECAP
    CHOIX -->|Standard| TICKET
    CHOIX -->|Appro| APPRO
    RECAP --> PRINT
    TICKET --> PRINT
    APPRO --> PRINT
    PRINT --> CHERR
    CHERR -->|NON| ENDOK
    CHERR -->|OUI| ENDKO

    style START fill:#3fb950,color:#000
    style ENDOK fill:#3fb950,color:#000
    style ENDKO fill:#f85149,color:#fff
    style CHOIX fill:#58a6ff,color:#000
    style CHERR fill:#58a6ff,color:#000
    style PRINT fill:#ffeb3b,color:#000
```

> **Legende**: Vert = START/END OK | Rouge = END KO | Jaune = Flux impression | Bleu = Decisions

| Noeud | Source | Justification |
|-------|--------|---------------|
| LSESS | Tache 151.2 | Interroge histo_sessions_caisse_detail pour derniere cloture |
| PARAMS | Tache 151.3 | Charge preferences impression (imprimante, format) |
| CHOIX | Tache 151.4 | Ecran de selection parmi 3 types de documents |
| RECAP | CallTask vers IDE 154 | Tableau recapitulatif fermeture |
| TICKET | CallTask vers IDE 138 | Ticket fermeture session standard |
| APPRO | CallTask vers IDE 139 | Ticket approvisionnement remise |
| PRINT | Tache 151.5 | Execute impression selon choix utilisateur |
| CHERR | Expression 6 | NOT(erreur FI) : gestion erreur impression |

<!-- TAB:Donnees -->

## 10. TABLES

### Tables utilisees (2)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 249 | histo_sessions_caisse_detail | Sessions de caisse | DB | R |   |   | 1 |
| 246 | histo_sessions_caisse | Sessions de caisse | DB | R |   |   | 1 |

### Colonnes par table (1 / 2 tables avec colonnes identifiees)

<details>
<summary>Table 249 - histo_sessions_caisse_detail (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| ES | Recap globale/detaillee | R | Alpha |

</details>

<details>
<summary>Table 246 - histo_sessions_caisse (R) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (9)

Variables recues du programme appelant ([Gestion caisse (IDE 121)](ADH-IDE-121.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| EN | P0 societe | Alpha | - |
| EO | P0 nbre decimales | Numeric | - |
| EP | P0 nom village | Alpha | - |
| EQ | P0 masque cumul | Alpha | - |
| ER | P0 devise locale | Alpha | - |
| ES | P0 uni/bi | Alpha | - |
| ET | P0 village tai | Alpha | - |
| EU | P0 date comptable | Date | - |
| EV | P0 session | Numeric | - |

### 11.2 Autres (15)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| EW | P1 quand | Alpha | - |
| EX | P1 montant appro monnaie | Numeric | - |
| EY | P1 montant appro produit | Numeric | - |
| EZ | P1 montant remise monnaie | Numeric | - |
| FA | P1 montant remise cartes | Numeric | - |
| FB | P1 montant remise chèques | Numeric | - |
| FC | P1 montant remise od | Numeric | - |
| FD | P1 remise nbre devises | Numeric | - |
| FE | P1 montant remise produits | Numeric | - |
| FF | P2 montant appro monnaie final | Numeric | - |
| FG | P2 montant remise monnaie final | Numeric | - |
| FH | P2 montant ecart fermeture | Numeric | - |
| FI | erreur | Logical | 1x refs |
| FJ | date fin session | Date | [T2](#t2) |
| FK | date comptable | Date | 1x refs |

<details>
<summary>Toutes les 24 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| P0 | **EN** | P0 societe | Alpha |
| P0 | **EO** | P0 nbre decimales | Numeric |
| P0 | **EP** | P0 nom village | Alpha |
| P0 | **EQ** | P0 masque cumul | Alpha |
| P0 | **ER** | P0 devise locale | Alpha |
| P0 | **ES** | P0 uni/bi | Alpha |
| P0 | **ET** | P0 village tai | Alpha |
| P0 | **EU** | P0 date comptable | Date |
| P0 | **EV** | P0 session | Numeric |
| Autre | **EW** | P1 quand | Alpha |
| Autre | **EX** | P1 montant appro monnaie | Numeric |
| Autre | **EY** | P1 montant appro produit | Numeric |
| Autre | **EZ** | P1 montant remise monnaie | Numeric |
| Autre | **FA** | P1 montant remise cartes | Numeric |
| Autre | **FB** | P1 montant remise chèques | Numeric |
| Autre | **FC** | P1 montant remise od | Numeric |
| Autre | **FD** | P1 remise nbre devises | Numeric |
| Autre | **FE** | P1 montant remise produits | Numeric |
| Autre | **FF** | P2 montant appro monnaie final | Numeric |
| Autre | **FG** | P2 montant remise monnaie final | Numeric |
| Autre | **FH** | P2 montant ecart fermeture | Numeric |
| Autre | **FI** | erreur | Logical |
| Autre | **FJ** | date fin session | Date |
| Autre | **FK** | date comptable | Date |

</details>

## 12. EXPRESSIONS

**6 / 6 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONDITION | 2 | 0 |
| NEGATION | 1 | 5 |
| CONSTANTE | 1 | 0 |
| CAST_LOGIQUE | 2 | 0 |

### 12.2 Expressions cles par type

#### CONDITION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 5 | `date comptable [X]<>'00/00/0000'DATE` | - |
| CONDITION | 4 | `date fin session [W]='00/00/0000'DATE` | - |

#### NEGATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| NEGATION | 6 | `NOT (erreur [V])` | [RM-001](#rm-RM-001) |

#### CONSTANTE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 1 | `'F'` | - |

#### CAST_LOGIQUE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 3 | `'TRUE'LOG` | - |
| CAST_LOGIQUE | 2 | `'FALSE'LOG` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Gestion caisse (IDE 121)](ADH-IDE-121.md) -> **Reimpression tickets fermeture (IDE 151)**

Main -> ... -> [Gestion caisse 142 (IDE 298)](ADH-IDE-298.md) -> **Reimpression tickets fermeture (IDE 151)**

```mermaid
graph LR
    T151[151 Reimpression ticke...]
    style T151 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC281[281 Fermeture Sessions]
    style CC281 fill:#f59e0b
    CC163[163 Menu caisse GM - s...]
    style CC163 fill:#f59e0b
    CC121[121 Gestion caisse]
    style CC121 fill:#3fb950
    CC298[298 Gestion caisse 142]
    style CC298 fill:#3fb950
    CC163 --> CC121
    CC281 --> CC121
    CC163 --> CC298
    CC281 --> CC298
    CC1 --> CC163
    CC1 --> CC281
    CC121 --> T151
    CC298 --> T151
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [121](ADH-IDE-121.md) | Gestion caisse | 1 |
| [298](ADH-IDE-298.md) | Gestion caisse 142 | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T151[151 Reimpression ticke...]
    style T151 fill:#58a6ff
    C154[154 Tableau recap ferm...]
    T151 --> C154
    style C154 fill:#3fb950
    C138[138 Ticket fermeture s...]
    T151 --> C138
    style C138 fill:#3fb950
    C139[139 Ticket appro remise]
    T151 --> C139
    style C139 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [154](ADH-IDE-154.md) | Tableau recap fermeture | 2 | Fermeture session |
| [138](ADH-IDE-138.md) | Ticket fermeture session | 1 | Impression ticket/document |
| [139](ADH-IDE-139.md) | Ticket appro remise | 1 | Impression ticket/document |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 152 | Programme compact |
| Expressions | 6 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 3 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 152) | Code sain |
| Regles metier | 1 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Impression (2 taches: 0 ecran, 2 traitements)

- **Strategie** : Templates HTML -> PDF via wkhtmltopdf ou Puppeteer.
- `PrintService` injectable avec choix imprimante

#### Traitement (2 taches: 0 ecran, 2 traitements)

- **Strategie** : 2 service(s) backend injectable(s) (Domain Services).
- 3 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Consultation (1 tache: 1 ecran, 0 traitement)

- **Strategie** : Composants de recherche/selection en modales.
- 1 ecran : Choix

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| [Tableau recap fermeture (IDE 154)](ADH-IDE-154.md) | Sous-programme | 2x | Haute - Fermeture session |
| [Ticket appro remise (IDE 139)](ADH-IDE-139.md) | Sous-programme | 1x | Normale - Impression ticket/document |
| [Ticket fermeture session (IDE 138)](ADH-IDE-138.md) | Sous-programme | 1x | Normale - Impression ticket/document |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-25 12:25*
