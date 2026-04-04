# WEL IDE 59 - Print Calls Statement Normal

> **Analyse**: Phases 1-4 2026-02-03 21:31 -> 21:31 (10s) | Assemblage 21:31
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | WEL |
| IDE Position | 59 |
| Nom Programme | Print Calls Statement Normal |
| Fichier source | `Prg_59.xml` |
| Dossier IDE | Phone |
| Taches | 5 (1 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 1 |

## 2. DESCRIPTION FONCTIONNELLE

**Print Calls Statement Normal** assure la gestion complete de ce processus, accessible depuis [Print calls statement (IDE 60)](WEL-IDE-60.md), [Email calls statement (IDE 61)](WEL-IDE-61.md).

Le flux de traitement s'organise en **2 blocs fonctionnels** :

- **Impression** (3 taches) : generation de tickets et documents
- **Traitement** (2 taches) : traitements metier divers

**Logique metier** : 1 regles identifiees couvrant conditions metier.

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (2 taches)

- **59** - Veuillez patienter... **[[ECRAN]](#ecran-t1)**
- **59.1** - recup nom adherent

Delegue a : [Traitement des mails (IDE 89)](WEL-IDE-89.md)

#### Phase 2 : Impression (3 taches)

- **59.2** - Printer
- **59.2.1** - edition extrait compte **[[ECRAN]](#ecran-t4)**
- **59.2.2** - edition extrait compte

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (2 taches)

Traitements internes.

---

#### <a id="t1"></a>59 - Veuillez patienter... [[ECRAN]](#ecran-t1)

**Role** : Traitement : Veuillez patienter....
**Ecran** : 424 x 57 DLU (MDI) | [Voir mockup](#ecran-t1)
**Delegue a** : [Traitement des mails (IDE 89)](WEL-IDE-89.md)

---

#### <a id="t2"></a>59.1 - recup nom adherent

**Role** : Consultation/chargement : recup nom adherent.
**Variables liees** : I (W0 nom adherent), J (W0 prenom adherent), K (W0 n° adherent)
**Delegue a** : [Traitement des mails (IDE 89)](WEL-IDE-89.md)


### 3.2 Impression (3 taches)

Generation des documents et tickets.

---

#### <a id="t3"></a>59.2 - Printer

**Role** : Generation du document : Printer.

---

#### <a id="t4"></a>59.2.1 - edition extrait compte [[ECRAN]](#ecran-t4)

**Role** : Generation du document : edition extrait compte.
**Ecran** : 370 x 184 DLU (MDI) | [Voir mockup](#ecran-t4)
**Variables liees** : B (P0 n° compte)

---

#### <a id="t5"></a>59.2.2 - edition extrait compte

**Role** : Generation du document : edition extrait compte.
**Variables liees** : B (P0 n° compte)


## 5. REGLES METIER

1 regles identifiees:

### Autres (1 regles)

#### <a id="rm-RM-001"></a>[RM-001] Si VG53=2 alors 'N9.2C' sinon 'N9.3C')

| Element | Detail |
|---------|--------|
| **Condition** | `VG53=2` |
| **Si vrai** | 'N9.2C' |
| **Si faux** | 'N9.3C') |
| **Expression source** | Expression 10 : `IF(VG53=2,'N9.2C','N9.3C')` |
| **Exemple** | Si VG53=2 â†’ 'N9.2C'. Sinon â†’ 'N9.3C') |

## 6. CONTEXTE

- **Appele par**: [Print calls statement (IDE 60)](WEL-IDE-60.md), [Email calls statement (IDE 61)](WEL-IDE-61.md)
- **Appelle**: 1 programmes | **Tables**: 6 (W:0 R:3 L:3) | **Taches**: 5 | **Expressions**: 12

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 5)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 59 | 59 | Veuillez patienter... | MDI | 424 | 57 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>59 - Veuillez patienter...
**Tache** : [59](#t1) | **Type** : MDI | **Dimensions** : 424 x 57 DLU
**Bloc** : Traitement | **Titre IDE** : Veuillez patienter...

<!-- FORM-DATA:
{
    "width":  424,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  423,
                         "fmt":  "",
                         "name":  "",
                         "h":  29,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  120,
                         "type":  "label",
                         "var":  "",
                         "y":  10,
                         "w":  221,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "7",
                         "text":  "Impression en cours ...",
                         "parent":  null
                     },
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  29,
                         "w":  423,
                         "fmt":  "",
                         "name":  "",
                         "h":  27,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  52,
                         "type":  "label",
                         "var":  "",
                         "y":  38,
                         "w":  318,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Impression de l\u0027extrait de compte",
                         "parent":  null
                     },
                     {
                         "x":  4,
                         "type":  "image",
                         "var":  "",
                         "y":  2,
                         "w":  72,
                         "fmt":  "",
                         "name":  "",
                         "h":  25,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "59",
    "height":  57
}
-->

## 9. NAVIGATION

Ecran unique: **Veuillez patienter...**

### 9.3 Structure hierarchique (5 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **59.1** | [**Veuillez patienter...** (59)](#t1) [mockup](#ecran-t1) | MDI | 424x57 | Traitement |
| 59.1.1 | [recup nom adherent (59.1)](#t2) | MDI | - | |
| **59.2** | [**Printer** (59.2)](#t3) | MDI | - | Impression |
| 59.2.1 | [edition extrait compte (59.2.1)](#t4) [mockup](#ecran-t4) | MDI | 370x184 | |
| 59.2.2 | [edition extrait compte (59.2.2)](#t5) | MDI | - | |

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

### Tables utilisees (6)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 30 | gm-recherche_____gmr | Index de recherche | DB |   |   | L | 1 |
| 31 | gm-complet_______gmc |  | DB | R |   |   | 1 |
| 34 | hebergement______heb | Hebergement (chambres) | DB |   |   | L | 1 |
| 60 | table_code_acces_tca |  | DB | R |   |   | 2 |
| 155 | historique_pabx | Historique / journal | DB |   |   | L | 2 |
| 368 | pms_village |  | DB | R |   |   | 1 |

### Colonnes par table (2 / 3 tables avec colonnes identifiees)

<details>
<summary>Table 31 - gm-complet_______gmc (R) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 60 - table_code_acces_tca (R) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| D | P0.CodeAutocom | R | Numeric |

</details>

<details>
<summary>Table 368 - pms_village (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P0 societe | R | Alpha |
| B | P0 n° compte | R | Numeric |
| C | P0 filiation | R | Numeric |
| D | P0.CodeAutocom | R | Numeric |
| E | P0 date Debut | R | Date |
| F | P0 date Fin | R | Date |
| G | P0.Print/EMail | R | Alpha |
| H | P0.MailTo | R | Alpha |
| I | W0 nom adherent | R | Alpha |
| J | W0 prenom adherent | R | Alpha |
| K | W0 n° adherent | R | Numeric |
| L | W0 chambre | R | Alpha |
| M | v.Masaque | R | Alpha |
| N | v.devise locale | R | Alpha |
| O | v.Chemin | R | Alpha |
| P | v.NomFichier | R | Alpha |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (8)

Variables recues du programme appelant ([Print calls statement (IDE 60)](WEL-IDE-60.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P0 societe | Alpha | - |
| B | P0 n° compte | Numeric | [59.2.1](#t4), [59.2.2](#t5) |
| C | P0 filiation | Numeric | 1x parametre entrant |
| D | P0.CodeAutocom | Numeric | - |
| E | P0 date Debut | Date | - |
| F | P0 date Fin | Date | - |
| G | P0.Print/EMail | Alpha | 2x parametre entrant |
| H | P0.MailTo | Alpha | - |

### 11.2 Variables de session (4)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| M | v.Masaque | Alpha | - |
| N | v.devise locale | Alpha | - |
| O | v.Chemin | Alpha | 1x session |
| P | v.NomFichier | Alpha | 1x session |

### 11.3 Variables de travail (4)

Variables internes au programme.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| I | W0 nom adherent | Alpha | - |
| J | W0 prenom adherent | Alpha | - |
| K | W0 n° adherent | Numeric | - |
| L | W0 chambre | Alpha | - |

<details>
<summary>Toutes les 16 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| P0 | **A** | P0 societe | Alpha |
| P0 | **B** | P0 n° compte | Numeric |
| P0 | **C** | P0 filiation | Numeric |
| P0 | **D** | P0.CodeAutocom | Numeric |
| P0 | **E** | P0 date Debut | Date |
| P0 | **F** | P0 date Fin | Date |
| P0 | **G** | P0.Print/EMail | Alpha |
| P0 | **H** | P0.MailTo | Alpha |
| W0 | **I** | W0 nom adherent | Alpha |
| W0 | **J** | W0 prenom adherent | Alpha |
| W0 | **K** | W0 n° adherent | Numeric |
| W0 | **L** | W0 chambre | Alpha |
| V. | **M** | v.Masaque | Alpha |
| V. | **N** | v.devise locale | Alpha |
| V. | **O** | v.Chemin | Alpha |
| V. | **P** | v.NomFichier | Alpha |

</details>

## 12. EXPRESSIONS

**12 / 12 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONDITION | 3 | 5 |
| CONSTANTE | 1 | 0 |
| FORMAT | 1 | 0 |
| OTHER | 3 | 0 |
| REFERENCE_VG | 2 | 0 |
| STRING | 1 | 0 |
| CONCATENATION | 1 | 0 |

### 12.2 Expressions cles par type

#### CONDITION (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 10 | `IF(VG53=2,'N9.2C','N9.3C')` | [RM-001](#rm-RM-001) |
| CONDITION | 12 | `P0.Print/EMail [G]='E'` | - |
| CONDITION | 11 | `P0.Print/EMail [G]='P'` | - |

#### CONSTANTE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 5 | `'WELPHONE_S'` | - |

#### FORMAT (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| FORMAT | 8 | `'CALLS_STATEMENT_'&Trim(Str(P0 n° compte [B],'8P0'))&'_'&Trim(Str(P0 filiation [C],'##'))&'_'&Trim(VG15)&'_'&DStr(Date(),'YYMMDD')&TStr(Time(),'HHMMSS')&'.pdf'` | - |

#### OTHER (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 6 | `Translate('%club_exportdata%')&'WELCOME\'` | - |
| OTHER | 2 | `SetCrsr (2)` | - |
| OTHER | 1 | `SetCrsr (1)` | - |

#### REFERENCE_VG (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 4 | `VG55` | - |
| REFERENCE_VG | 3 | `VG54` | - |

#### STRING (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| STRING | 7 | `Trim(VG67)` | - |

#### CONCATENATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 9 | `Trim(v.Chemin [O])&v.NomFichier [P]` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Print calls statement (IDE 60)](WEL-IDE-60.md) -> **Print Calls Statement Normal (IDE 59)**

Main -> ... -> [Email calls statement (IDE 61)](WEL-IDE-61.md) -> **Print Calls Statement Normal (IDE 59)**

```mermaid
graph LR
    T59[59 Print Calls Stateme...]
    style T59 fill:#58a6ff
    CC58[58 Open phone line]
    style CC58 fill:#8b5cf6
    CC60[60 Print calls statement]
    style CC60 fill:#3fb950
    CC61[61 Email calls statement]
    style CC61 fill:#3fb950
    CC58 --> CC60
    CC58 --> CC61
    CC60 --> T59
    CC61 --> T59
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [60](WEL-IDE-60.md) | Print calls statement | 1 |
| [61](WEL-IDE-61.md) | Email calls statement | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T59[59 Print Calls Stateme...]
    style T59 fill:#58a6ff
    C89[89 Traitement des mails]
    T59 --> C89
    style C89 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [89](WEL-IDE-89.md) | Traitement des mails | 1 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 136 | Programme compact |
| Expressions | 12 | Peu de logique |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 1 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0.7% (1 / 136) | Code sain |
| Regles metier | 1 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (2 taches: 1 ecran, 1 traitement)

- **Strategie** : Orchestrateur avec 1 ecrans (Razor/React) et 1 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 1 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Impression (3 taches: 1 ecran, 2 traitements)

- **Strategie** : Templates HTML -> PDF via wkhtmltopdf ou Puppeteer.
- `PrintService` injectable avec choix imprimante

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| [Traitement des mails (IDE 89)](WEL-IDE-89.md) | Sous-programme | 1x | Normale - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 21:31*
