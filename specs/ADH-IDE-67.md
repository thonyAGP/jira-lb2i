# ADH IDE 67 - Reedition Recap Easy Check Out

> **Analyse**: Phases 1-4 2026-02-07 03:43 -> 02:01 (22h17min) | Assemblage 02:01
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | ADH |
| IDE Position | 67 |
| Nom Programme | Reedition Recap Easy Check Out |
| Fichier source | `Prg_67.xml` |
| Dossier IDE | Impression |
| Taches | 1 (1 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 1 |
| Complexite | **BASSE** (score 5/100) |
| <span style="color:red">Statut</span> | <span style="color:red">**ORPHELIN_POTENTIEL**</span> |

## 2. DESCRIPTION FONCTIONNELLE

ADH IDE 67 - Reedition Recap Easy Check Out est un programme de gestion des documents Easy Check-Out qui permet de regenerer et de renvoyer les recapitulatifs d'une transaction de paiement facile. Ce programme constitue une fonction de support client, offrant la possibilite de reimprimer ou de retransmettre par email les details d'une operation Easy Check-Out deja executee. Il s'integre dans le flux de sortie des clients, intervenant apres une transaction de paiement reussie.

Le programme appelle directement Edition & Mail Easy Check Out (IDE 65), qui gere la generation du document recapitulatif et son envoi. Cette dependance indique que ADH IDE 67 fonctionne comme un point d'entree de reedition, permettant aux operateurs de caisse de regenerer les documents de synthese a la demande, sans rejouer toute la transaction de paiement. Les cas d'usage typiques incluent la reedition pour un client qui aurait perdu son recu ou la retransmission par email d'une confirmation de paiement.

La logique du programme reste probablement simple : recuperation des donnees de la transaction original, validation des droits d'acces, puis delegation a ADH IDE 65 pour la generation et distribution du document. Cela en fait un programme de service client integre au processus Easy Check-Out, garantissant la traçabilite et la satisfaction client apres chaque transaction.

## 3. BLOCS FONCTIONNELS

### 3.1 Impression (1 tache)

Generation des documents et tickets.

---

#### <a id="t1"></a>67 - Reedition Recap Easy Check Out [[ECRAN]](#ecran-t1)

**Role** : Generation du document : Reedition Recap Easy Check Out.
**Ecran** : 410 x 119 DLU (MDI) | [Voir mockup](#ecran-t1)
**Variables liees** : EQ (v.retour log easy check out)
**Delegue a** : [Edition & Mail Easy Check Out (IDE 65)](ADH-IDE-65.md)


## 5. REGLES METIER

*(Programme d'impression - logique technique sans conditions metier)*

## 6. CONTEXTE

- **Appele par**: (aucun)
- **Appelle**: 1 programmes | **Tables**: 1 (W:0 R:1 L:0) | **Taches**: 1 | **Expressions**: 6

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 1)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 67 | 67 | Reedition Recap Easy Check Out | MDI | 410 | 119 | Impression |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>67 - Reedition Recap Easy Check Out
**Tache** : [67](#t1) | **Type** : MDI | **Dimensions** : 410 x 119 DLU
**Bloc** : Impression | **Titre IDE** : Reedition Recap Easy Check Out

<!-- FORM-DATA:
{
    "width":  410,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  106,
                         "type":  "label",
                         "var":  "",
                         "y":  2,
                         "w":  284,
                         "fmt":  "",
                         "name":  "",
                         "h":  24,
                         "color":  "1",
                         "text":  "Easy Check-Out",
                         "parent":  null
                     },
                     {
                         "x":  92,
                         "type":  "label",
                         "var":  "",
                         "y":  42,
                         "w":  234,
                         "fmt":  "",
                         "name":  "",
                         "h":  9,
                         "color":  "",
                         "text":  "Rééditer le récapitulatif du traitement en date du",
                         "parent":  null
                     },
                     {
                         "x":  6,
                         "type":  "label",
                         "var":  "",
                         "y":  89,
                         "w":  396,
                         "fmt":  "",
                         "name":  "",
                         "h":  28,
                         "color":  "7",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  14,
                         "type":  "image",
                         "var":  "",
                         "y":  2,
                         "w":  72,
                         "fmt":  "",
                         "name":  "",
                         "h":  48,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  330,
                         "type":  "edit",
                         "var":  "",
                         "y":  42,
                         "w":  64,
                         "fmt":  "",
                         "name":  "v.Date",
                         "h":  10,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  92,
                         "type":  "checkbox",
                         "var":  "",
                         "y":  57,
                         "w":  308,
                         "fmt":  "",
                         "name":  "v.Erreurs",
                         "h":  12,
                         "color":  "42",
                         "text":  "Editer juste les erreurs",
                         "parent":  null
                     },
                     {
                         "x":  92,
                         "type":  "checkbox",
                         "var":  "",
                         "y":  75,
                         "w":  308,
                         "fmt":  "",
                         "name":  "v.Mode Test",
                         "h":  12,
                         "color":  "42",
                         "text":  "Test des garanties",
                         "parent":  null
                     },
                     {
                         "x":  14,
                         "type":  "button",
                         "var":  "",
                         "y":  95,
                         "w":  76,
                         "fmt":  "\u0026Editer",
                         "name":  "b.Lancer",
                         "h":  16,
                         "color":  "",
                         "text":  "",
                         "parent":  5
                     },
                     {
                         "x":  318,
                         "type":  "button",
                         "var":  "",
                         "y":  95,
                         "w":  76,
                         "fmt":  "\u0026Quitter",
                         "name":  "b.Quitter",
                         "h":  16,
                         "color":  "",
                         "text":  "",
                         "parent":  5
                     }
                 ],
    "taskId":  "67",
    "height":  119
}
-->

<details>
<summary><strong>Champs : 3 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 330,42 | v.Date | - | edit |
| 92,57 | v.Erreurs | - | checkbox |
| 92,75 | v.Mode Test | - | checkbox |

</details>

<details>
<summary><strong>Boutons : 2 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| Editer | 14,95 | Modifie l'element |
| Quitter | 318,95 | Quitte le programme |

</details>

## 9. NAVIGATION

Ecran unique: **Reedition Recap Easy Check Out**

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **67.1** | [**Reedition Recap Easy Check Out** (67)](#t1) [mockup](#ecran-t1) | MDI | 410x119 | Impression |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Traitement principal]
    ENDOK([END OK])

    START --> INIT --> SAISIE
    SAISIE --> ENDOK

    style START fill:#3fb950,color:#000
    style ENDOK fill:#3fb950,color:#000
```

> **Legende**: Vert = START/END OK | Rouge = END KO | Bleu = Decisions
> *Algorigramme auto-genere. Utiliser `/algorigramme` pour une synthese metier detaillee.*

<!-- TAB:Donnees -->

## 10. TABLES

### Tables utilisees (1)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 934 | selection enregistrement diver |  | DB | R |   |   | 1 |

### Colonnes par table (1 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 934 - selection enregistrement diver (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | v.Date Récapitulatif | R | Date |
| B | v.Mode Test | R | Logical |
| C | v.Erreurs Seules | R | Logical |
| D | v.retour log easy check out | R | Logical |

</details>

## 11. VARIABLES

### 11.1 Variables de session (4)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| EN | v.Date Récapitulatif | Date | 1x session |
| EO | v.Mode Test | Logical | 1x session |
| EP | v.Erreurs Seules | Logical | 1x session |
| EQ | v.retour log easy check out | Logical | - |

## 12. EXPRESSIONS

**6 / 6 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| DATE | 1 | 0 |
| OTHER | 2 | 0 |
| CAST_LOGIQUE | 2 | 0 |
| REFERENCE_VG | 1 | 0 |

### 12.2 Expressions cles par type

#### DATE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| DATE | 4 | `Date()` | - |

#### OTHER (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 6 | `NOT(v.retour log easy chec... [D])` | - |
| OTHER | 1 | `v.Date Récapitulatif [A]` | - |

#### CAST_LOGIQUE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 3 | `CndRange(v.Mode Test [B],'TRUE'LOG)` | - |
| CAST_LOGIQUE | 2 | `CndRange(v.Erreurs Seules [C],'TRUE'LOG)` | - |

#### REFERENCE_VG (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 5 | `VG91` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

**Chemin**: (pas de callers directs)

```mermaid
graph LR
    T67[67 Reedition Recap Eas...]
    style T67 fill:#58a6ff
    NONE[Aucun caller]
    NONE -.-> T67
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| - | (aucun) | - |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T67[67 Reedition Recap Eas...]
    style T67 fill:#58a6ff
    C65[65 Edition Mail Easy C...]
    T67 --> C65
    style C65 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [65](ADH-IDE-65.md) | Edition & Mail Easy Check Out | 1 | Impression ticket/document |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 15 | Programme compact |
| Expressions | 6 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 1 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 15) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Impression (1 tache: 1 ecran, 0 traitement)

- **Strategie** : Templates HTML -> PDF via wkhtmltopdf ou Puppeteer.
- `PrintService` injectable avec choix imprimante

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| [Edition & Mail Easy Check Out (IDE 65)](ADH-IDE-65.md) | Sous-programme | 1x | Normale - Impression ticket/document |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-08 02:01*
