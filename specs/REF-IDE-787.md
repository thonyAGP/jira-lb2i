# REF IDE 787 - Mail Envoi Multi_PJ

> **Analyse**: Phases 1-4 2026-02-03 14:22 -> 14:22 (14s) | Assemblage 14:22
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | REF |
| IDE Position | 787 |
| Nom Programme | Mail Envoi Multi_PJ |
| Fichier source | `Prg_787.xml` |
| Dossier IDE | General |
| Taches | 1 (0 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 3 |
| :warning: Statut | **ORPHELIN_POTENTIEL** |

## 2. DESCRIPTION FONCTIONNELLE

**Mail Envoi Multi_PJ** assure la gestion complete de ce processus.

Le flux de traitement s'organise en **1 blocs fonctionnels** :

- **Traitement** (1 tache) : traitements metier divers

**Logique metier** : 1 regles identifiees couvrant conditions metier.

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (1 tache)

Traitements internes.

---

#### <a id="t1"></a>787 - Mail Envoi Multi_PJ [[ECRAN]](#ecran-t1)

**Role** : Traitement : Mail Envoi Multi_PJ.
**Ecran** : 1499 x 470 DLU | [Voir mockup](#ecran-t1)
**Variables liees** : C (p.o Code Retour Envoi OK), Q (v.Retour Envoi Mail), R (v.Mail from), W (v.Code erreur mail), X (v.Message erreur mail)
**Delegue a** : [Log batch (IDE 829)](REF-IDE-829.md), [Search From&Sujet&Corps Mul_PJ (IDE 789)](REF-IDE-789.md), [SendHtmlMail (IDE 804)](REF-IDE-804.md)


## 5. REGLES METIER

1 regles identifiees:

### Autres (1 regles)

#### <a id="rm-RM-001"></a>[RM-001] Si p.o Code Retour Envoi OK [C] alors 'OK' sinon 'ERR')

| Element | Detail |
|---------|--------|
| **Condition** | `p.o Code Retour Envoi OK [C]` |
| **Si vrai** | 'OK' |
| **Si faux** | 'ERR') |
| **Variables** | C (p.o Code Retour Envoi OK) |
| **Expression source** | Expression 24 : `IF(p.o Code Retour Envoi OK [C], 'OK', 'ERR')` |
| **Exemple** | Si p.o Code Retour Envoi OK [C] â†’ 'OK'. Sinon â†’ 'ERR') |

## 6. CONTEXTE

- **Appele par**: (aucun)
- **Appelle**: 3 programmes | **Tables**: 4 (W:0 R:1 L:3) | **Taches**: 1 | **Expressions**: 54

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (1 tache)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **787.1** | [**Mail Envoi Multi_PJ** (787)](#t1) [mockup](#ecran-t1) | - | 1499x470 | Traitement |

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

### Tables utilisees (4)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 67 | tables___________tab |  | DB | R |   |   | 1 |
| 69 | initialisation___ini |  | DB |   |   | L | 1 |
| 368 | pms_village |  | DB |   |   | L | 1 |
| 856 | adresse_service_village | Services / filieres | DB |   |   | L | 1 |

### Colonnes par table (3 / 1 tables avec colonnes identifiees)

<details>
<summary>Table 67 - tables___________tab (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | p.i à: (To) | R | Alpha |
| B | p.i Fichier Joint         Mode1 | R | Alpha |
| C | p.o Code Retour Envoi OK | R | Logical |
| D | p.i viens de : | R | Alpha |
| E | p.i Langue | R | Alpha |
| F | p.i copie (CC) | R | Alpha |
| G | p.i TypeTraitement | R | Alpha |
| H | p.i Prenom | R | Alpha |
| I | p.i Nom | R | Alpha |
| J | p.i.Date Demande | R | Alpha |
| K | p.i.Heure Demande | R | Alpha |
| L | p.i.Url | R | Alpha |
| M | p.i.Date application | R | Date |
| N | p.i.Complément | R | Unicode |
| O | p.i Chemin des fichiers Mode2 | R | Unicode |
| P | p.i Liste des fichiers    Mode2 | R | Unicode |
| Q | v.Retour Envoi Mail | R | Numeric |
| R | v.Mail from | R | Alpha |
| S | v.Fichier(s) Joint(s) | R | Alpha |
| T | v.Sujet | R | Unicode |
| U | v.Corps | R | Unicode |
| V | v.Date | R | Date |
| W | v.Code erreur mail | R | Numeric |
| X | v.Message erreur mail | R | Alpha |
| Y | v.CodeService | R | Unicode |
| Z | v.Destinataire village ? | R | Logical |
| BA | v.Destinaire service ? | R | Logical |
| BB | v.Destinataire interne ? | R | Logical |
| BC | v.Chemin_fichier_n°1 | R | Unicode |
| BD | v.Chemin_fichier_n°2 | R | Unicode |
| BE | v.Chemin_fichier_n°3 | R | Unicode |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (16)

Variables recues en parametre.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | p.i à: (To) | Alpha | 5x parametre entrant |
| B | p.i Fichier Joint         Mode1 | Alpha | - |
| C | p.o Code Retour Envoi OK | Logical | [787](#t1) |
| D | p.i viens de : | Alpha | 1x parametre entrant |
| E | p.i Langue | Alpha | - |
| F | p.i copie (CC) | Alpha | 1x parametre entrant |
| G | p.i TypeTraitement | Alpha | 1x parametre entrant |
| H | p.i Prenom | Alpha | 1x parametre entrant |
| I | p.i Nom | Alpha | 1x parametre entrant |
| J | p.i.Date Demande | Alpha | - |
| K | p.i.Heure Demande | Alpha | - |
| L | p.i.Url | Alpha | - |
| M | p.i.Date application | Date | - |
| N | p.i.Complément | Unicode | - |
| O | p.i Chemin des fichiers Mode2 | Unicode | - |
| P | p.i Liste des fichiers    Mode2 | Unicode | - |

### 11.2 Variables de session (15)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| Q | v.Retour Envoi Mail | Numeric | [787](#t1) |
| R | v.Mail from | Alpha | 3x session |
| S | v.Fichier(s) Joint(s) | Alpha | 2x session |
| T | v.Sujet | Unicode | - |
| U | v.Corps | Unicode | 2x session |
| V | v.Date | Date | 1x session |
| W | v.Code erreur mail | Numeric | - |
| X | v.Message erreur mail | Alpha | - |
| Y | v.CodeService | Unicode | 1x session |
| Z | v.Destinataire village ? | Logical | - |
| BA | v.Destinaire service ? | Logical | - |
| BB | v.Destinataire interne ? | Logical | - |
| BC | v.Chemin_fichier_n°1 | Unicode | - |
| BD | v.Chemin_fichier_n°2 | Unicode | - |
| BE | v.Chemin_fichier_n°3 | Unicode | - |

<details>
<summary>Toutes les 31 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| P0 | **A** | p.i à: (To) | Alpha |
| P0 | **B** | p.i Fichier Joint         Mode1 | Alpha |
| P0 | **C** | p.o Code Retour Envoi OK | Logical |
| P0 | **D** | p.i viens de : | Alpha |
| P0 | **E** | p.i Langue | Alpha |
| P0 | **F** | p.i copie (CC) | Alpha |
| P0 | **G** | p.i TypeTraitement | Alpha |
| P0 | **H** | p.i Prenom | Alpha |
| P0 | **I** | p.i Nom | Alpha |
| P0 | **J** | p.i.Date Demande | Alpha |
| P0 | **K** | p.i.Heure Demande | Alpha |
| P0 | **L** | p.i.Url | Alpha |
| P0 | **M** | p.i.Date application | Date |
| P0 | **N** | p.i.Complément | Unicode |
| P0 | **O** | p.i Chemin des fichiers Mode2 | Unicode |
| P0 | **P** | p.i Liste des fichiers    Mode2 | Unicode |
| V. | **Q** | v.Retour Envoi Mail | Numeric |
| V. | **R** | v.Mail from | Alpha |
| V. | **S** | v.Fichier(s) Joint(s) | Alpha |
| V. | **T** | v.Sujet | Unicode |
| V. | **U** | v.Corps | Unicode |
| V. | **V** | v.Date | Date |
| V. | **W** | v.Code erreur mail | Numeric |
| V. | **X** | v.Message erreur mail | Alpha |
| V. | **Y** | v.CodeService | Unicode |
| V. | **Z** | v.Destinataire village ? | Logical |
| V. | **BA** | v.Destinaire service ? | Logical |
| V. | **BB** | v.Destinataire interne ? | Logical |
| V. | **BC** | v.Chemin_fichier_n°1 | Unicode |
| V. | **BD** | v.Chemin_fichier_n°2 | Unicode |
| V. | **BE** | v.Chemin_fichier_n°3 | Unicode |

</details>

## 12. EXPRESSIONS

**54 / 54 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONDITION | 11 | 5 |
| CONSTANTE | 15 | 0 |
| DATE | 1 | 0 |
| FORMAT | 2 | 0 |
| OTHER | 16 | 0 |
| CAST_LOGIQUE | 1 | 0 |
| STRING | 4 | 0 |
| CONCATENATION | 4 | 0 |

### 12.2 Expressions cles par type

#### CONDITION (11 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 24 | `IF(p.o Code Retour Envoi OK [C], 'OK', 'ERR')` | [RM-001](#rm-RM-001) |
| CONDITION | 44 | `StrTokenCnt([AJ],',')>3` | - |
| CONDITION | 43 | `StrTokenCnt([AJ],',')>=3` | - |
| CONDITION | 35 | `Trim([AH])<>''` | - |
| CONDITION | 37 | `Trim(p.i Fichier Joint     ... [B])<>''` | - |
| ... | | *+6 autres* | |

#### CONSTANTE (15 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 50 | `'Anthony'` | - |
| CONSTANTE | 49 | `'TICKETMOB'` | - |
| CONSTANTE | 48 | `'Mail Ticket Vente mobilité'` | - |
| CONSTANTE | 51 | `'01/09/2022'` | - |
| CONSTANTE | 54 | `'Receipt_SKIN_3767_20220831.pdf,SKIN_Sales_Terms&Conditions.pdf,SKIN_Rentals_Terms&Conditions.pdf'` | - |
| ... | | *+10 autres* | |

#### DATE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| DATE | 3 | `Date()` | - |

#### FORMAT (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| FORMAT | 8 | `MailError(v.Corps [U]) & ' Code Erreur : ' & Trim(Str(v.Corps [U],'N6'))` | - |
| FORMAT | 4 | `'%club_exportdata%'&'trace_mail_'&DStr(Date(),'YYYYMM')&'.txt'` | - |

#### OTHER (16 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 25 | `v.Date [V]` | - |
| OTHER | 28 | `v.Fichier(s) Joint(s) [S]` | - |
| OTHER | 21 | `StrBuild('Email to @1@ for @2@', p.i à: (To) [A], p.i TypeTraitement [G])` | - |
| OTHER | 22 | `StrBuild('Origin @1@', p.i viens de : [D])` | - |
| OTHER | 32 | `File2Blb ([AH])` | - |
| ... | | *+11 autres* | |

#### CAST_LOGIQUE (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 47 | `'FALSE'LOG` | - |

#### STRING (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| STRING | 33 | `Flip(StrToken(Flip(Trim(p.i Fichier Joint     ... [B])), 1, '.'))` | - |
| STRING | 34 | `Flip(StrToken(Flip(Trim([AH])), 1, '.'))` | - |
| STRING | 5 | `MailSend(Trim(p.i Liste des fichiers... [P]),Trim(p.i à: (To) [A]),Trim(p.i copie (CC) [F]),'',Trim(v.Mail from [R]),Trim(v.Fichier(s) Joint(s) [S]),Trim(v.Retour Envoi Mail [Q]))` | - |
| STRING | 12 | `StrToken(Trim(p.i Fichier Joint     ... [B]),2,'_')` | - |

#### CONCATENATION (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 40 | `Trim([AH])&Trim(StrToken([AJ],2,','))` | - |
| CONCATENATION | 41 | `Trim([AH])&Trim(StrToken([AJ],3,','))` | - |
| CONCATENATION | 9 | `Trim([AK])
&IF(Trim([AL])='','',','&Trim([AL]))
&IF(Trim([AM])='','',','&Trim([AM]))` | - |
| CONCATENATION | 39 | `Trim([AH])&Trim(StrToken([AJ],1,','))` | - |

### 12.3 Toutes les expressions (54)

<details>
<summary>Voir les 54 expressions</summary>

#### CONDITION (11)

| IDE | Expression Decodee |
|-----|-------------------|
| 24 | `IF(p.o Code Retour Envoi OK [C], 'OK', 'ERR')` |
| 6 | `p.i Chemin des fichier... [O]=0 OR v.Corps [U]=0` |
| 14 | `NOT(p.o Code Retour Envoi OK [C]) OR Translate('%club_tracemail%')='O'` |
| 17 | `p.i à: (To) [A]<>'' AND ([AD] OR [AF])` |
| 26 | `Translate('%club_tracemail%')='O'` |
| 42 | `StrTokenCnt([AJ],',')>=2` |
| 43 | `StrTokenCnt([AJ],',')>=3` |
| 44 | `StrTokenCnt([AJ],',')>3` |
| 35 | `Trim([AH])<>''` |
| 36 | `Trim([AH])<>'' AND Trim([AJ])<>''` |
| 37 | `Trim(p.i Fichier Joint     ... [B])<>''` |

#### CONSTANTE (15)

| IDE | Expression Decodee |
|-----|-------------------|
| 10 | `'VSERV'` |
| 19 | `'EMAIL'` |
| 20 | `'Error sending email'` |
| 23 | `'ERR'` |
| 27 | `'Send mail'` |
| 29 | `'txt'` |
| 45 | `'anthony.leberre.ext@clubmed.com'` |
| 46 | `''` |
| 48 | `'Mail Ticket Vente mobilité'` |
| 49 | `'TICKETMOB'` |
| 50 | `'Anthony'` |
| 51 | `'01/09/2022'` |
| 52 | `'11:12'` |
| 53 | `'c:\migration\xpa\pms\pdf\'` |
| 54 | `'Receipt_SKIN_3767_20220831.pdf,SKIN_Sales_Terms&Conditions.pdf,SKIN_Rentals_Terms&Conditions.pdf'` |

#### DATE (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 3 | `Date()` |

#### FORMAT (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 4 | `'%club_exportdata%'&'trace_mail_'&DStr(Date(),'YYYYMM')&'.txt'` |
| 8 | `MailError(v.Corps [U]) & ' Code Erreur : ' & Trim(Str(v.Corps [U],'N6'))` |

#### OTHER (16)

| IDE | Expression Decodee |
|-----|-------------------|
| 1 | `p.i à: (To) [A]` |
| 2 | `Time()` |
| 7 | `MailLastRC()` |
| 11 | `v.CodeService [Y]` |
| 13 | `NOT(VG28)` |
| 15 | `p.i à: (To) [A]` |
| 16 | `StrBuild('[@1@ @2@] @3@', p.i Prenom [H], p.i Nom [I], v.Mail from [R])` |
| 18 | `[AG]` |
| 21 | `StrBuild('Email to @1@ for @2@', p.i à: (To) [A], p.i TypeTraitement [G])` |
| 22 | `StrBuild('Origin @1@', p.i viens de : [D])` |
| 25 | `v.Date [V]` |
| 28 | `v.Fichier(s) Joint(s) [S]` |
| 30 | `v.Mail from [R]` |
| 31 | `File2Blb (p.i Fichier Joint     ... [B])` |
| 32 | `File2Blb ([AH])` |
| 38 | `p.i Fichier Joint     ... [B]` |

#### CAST_LOGIQUE (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 47 | `'FALSE'LOG` |

#### STRING (4)

| IDE | Expression Decodee |
|-----|-------------------|
| 5 | `MailSend(Trim(p.i Liste des fichiers... [P]),Trim(p.i à: (To) [A]),Trim(p.i copie (CC) [F]),'',Trim(v.Mail from [R]),Trim(v.Fichier(s) Joint(s) [S]),Trim(v.Retour Envoi Mail [Q]))` |
| 12 | `StrToken(Trim(p.i Fichier Joint     ... [B]),2,'_')` |
| 33 | `Flip(StrToken(Flip(Trim(p.i Fichier Joint     ... [B])), 1, '.'))` |
| 34 | `Flip(StrToken(Flip(Trim([AH])), 1, '.'))` |

#### CONCATENATION (4)

| IDE | Expression Decodee |
|-----|-------------------|
| 9 | `Trim([AK])
&IF(Trim([AL])='','',','&Trim([AL]))
&IF(Trim([AM])='','',','&Trim([AM]))` |
| 39 | `Trim([AH])&Trim(StrToken([AJ],1,','))` |
| 40 | `Trim([AH])&Trim(StrToken([AJ],2,','))` |
| 41 | `Trim([AH])&Trim(StrToken([AJ],3,','))` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

**Chemin**: (pas de callers directs)

```mermaid
graph LR
    T787[787 Mail Envoi Multi_PJ]
    style T787 fill:#58a6ff
    NONE[Aucun caller]
    NONE -.-> T787
    style NONE fill:#6b7280,stroke-dasharray: 5 5
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| - | (aucun) | - |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T787[787 Mail Envoi Multi_PJ]
    style T787 fill:#58a6ff
    C829[829 Log batch]
    T787 --> C829
    style C829 fill:#3fb950
    C789[789 Search FromSujetCo...]
    T787 --> C789
    style C789 fill:#3fb950
    C804[804 SendHtmlMail]
    T787 --> C804
    style C804 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [829](REF-IDE-829.md) | Log batch | 4 | Sous-programme |
| [789](REF-IDE-789.md) | Search From&Sujet&Corps Mul_PJ | 1 | Sous-programme |
| [804](REF-IDE-804.md) | SendHtmlMail | 1 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 119 | Programme compact |
| Expressions | 54 | Logique moderee |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 3 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 14.3% (17 / 119) | A verifier |
| Regles metier | 1 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (1 tache: 1 ecran, 0 traitement)

- **Strategie** : 1 composant(s) UI (Razor/React) avec formulaires et validation.
- 3 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| [Log batch (IDE 829)](REF-IDE-829.md) | Sous-programme | 4x | **CRITIQUE** - Sous-programme |
| [SendHtmlMail (IDE 804)](REF-IDE-804.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Search From&Sujet&Corps Mul_PJ (IDE 789)](REF-IDE-789.md) | Sous-programme | 1x | Normale - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 14:22*
