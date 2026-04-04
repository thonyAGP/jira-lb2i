# PVE IDE 185 - Menu

> **Analyse**: Phases 1-4 2026-02-03 18:45 -> 18:45 (23s) | Assemblage 18:45
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PVE |
| IDE Position | 185 |
| Nom Programme | Menu |
| Fichier source | `Prg_185.xml` |
| Dossier IDE | Mobile |
| Taches | 3 (1 ecrans visibles) |
| Tables modifiees | 0 |
| Programmes appeles | 14 |

## 2. DESCRIPTION FONCTIONNELLE

**Menu** assure la gestion complete de ce processus, accessible depuis [START (IDE 143)](PVE-IDE-143.md).

Le flux de traitement s'organise en **2 blocs fonctionnels** :

- **Traitement** (2 taches) : traitements metier divers
- **Calcul** (1 tache) : calculs de montants, stocks ou compteurs

**Logique metier** : 5 regles identifiees couvrant conditions metier, valeurs par defaut.

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (2 taches)

- **185** - Main (TPE) **[[ECRAN]](#ecran-t1)**
- **185.2** - Exist place

Delegue a : [Menu Check IN / Exchange (IDE 183)](PVE-IDE-183.md), [Main Sale (IDE 186)](PVE-IDE-186.md), [Main Sale-664 (IDE 187)](PVE-IDE-187.md), [Main Sale Sale Bar Code (IDE 214)](PVE-IDE-214.md), [FindAppointmentsToClose (IDE 172)](PVE-IDE-172.md), [Menu Administration (IDE 178)](PVE-IDE-178.md), [Menu Cloture du service (IDE 180)](PVE-IDE-180.md), [Menu Reports (IDE 182)](PVE-IDE-182.md), [Menu Equipment inventory (IDE 184)](PVE-IDE-184.md), [Get Bank accounting date (IDE 297)](PVE-IDE-297.md)

#### Phase 2 : Calcul (1 tache)

- **185.1** - Lecture solde du compte

Delegue a : [Menu Stocks Management (IDE 179)](PVE-IDE-179.md)

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (2 taches)

Traitements internes.

---

#### <a id="t1"></a>185 - Main (TPE) [[ECRAN]](#ecran-t1)

**Role** : Traitement : Main (TPE).
**Ecran** : 994 x 432 DLU | [Voir mockup](#ecran-t1)
**Delegue a** : [Menu Check IN / Exchange (IDE 183)](PVE-IDE-183.md), [Main Sale (IDE 186)](PVE-IDE-186.md), [Main Sale-664 (IDE 187)](PVE-IDE-187.md)

---

#### <a id="t3"></a>185.2 - Exist place

**Role** : Traitement : Exist place.
**Variables liees** : F (v.LieuExist)
**Delegue a** : [Menu Check IN / Exchange (IDE 183)](PVE-IDE-183.md), [Main Sale (IDE 186)](PVE-IDE-186.md), [Main Sale-664 (IDE 187)](PVE-IDE-187.md)


### 3.2 Calcul (1 tache)

Calculs metier : montants, stocks, compteurs.

---

#### <a id="t2"></a>185.1 - Lecture solde du compte

**Role** : Consultation/chargement : Lecture solde du compte.
**Variables liees** : G (v.Solde du compte)
**Delegue a** : [Menu Stocks Management (IDE 179)](PVE-IDE-179.md)


## 5. REGLES METIER

5 regles identifiees:

### Autres (5 regles)

#### <a id="rm-RM-001"></a>[RM-001] Valeur par defaut si Trim(v.MENU [B]) est vide

| Element | Detail |
|---------|--------|
| **Condition** | `Trim(v.MENU [B])=''` |
| **Si vrai** | 'POS' |
| **Si faux** | v.MENU [B]) |
| **Variables** | B (v.MENU) |
| **Expression source** | Expression 2 : `IF(Trim(v.MENU [B])='','POS',v.MENU [B])` |
| **Exemple** | Si Trim(v.MENU [B])='' â†’ 'POS'. Sinon â†’ v.MENU [B]) |

#### <a id="rm-RM-002"></a>[RM-002] Si VG41 alors 'v.Retour ? [C]'FORM sinon 'v.MENU [B]'FORM)

| Element | Detail |
|---------|--------|
| **Condition** | `VG41` |
| **Si vrai** | 'v.Retour ? [C]'FORM |
| **Si faux** | 'v.MENU [B]'FORM) |
| **Variables** | B (v.MENU), C (v.Retour ?) |
| **Expression source** | Expression 4 : `IF(VG41,'v.Retour ? [C]'FORM,'v.MENU [B]'FORM)` |
| **Exemple** | Si VG41 â†’ 'v.Retour ? [C]'FORM. Sinon â†’ 'v.MENU [B]'FORM) |

#### <a id="rm-RM-003"></a>[RM-003] Si VG104 alors VG25 sinon Str(VG105,'8P0'))

| Element | Detail |
|---------|--------|
| **Condition** | `VG104` |
| **Si vrai** | VG25 |
| **Si faux** | Str(VG105,'8P0')) |
| **Expression source** | Expression 30 : `IF(VG104, VG25, Str(VG105,'8P0'))` |
| **Exemple** | Si VG104 â†’ VG25. Sinon â†’ Str(VG105,'8P0')) |

#### <a id="rm-RM-004"></a>[RM-004] Si VG33 vaut 'TB' alors 'TABLET', sinon 'WORKSTATION'

| Element | Detail |
|---------|--------|
| **Condition** | `VG33='TB'` |
| **Si vrai** | 'TABLET' |
| **Si faux** | 'WORKSTATION') |
| **Expression source** | Expression 38 : `IF(VG33='TB','TABLET','WORKSTATION')` |
| **Exemple** | Si VG33='TB' â†’ 'TABLET'. Sinon â†’ 'WORKSTATION') |

#### <a id="rm-RM-005"></a>[RM-005] Si VG136 alors '{284 sinon -1}'PROG,IF(VG44,'{181,-1}'PROG,'{180,-1}'PROG))

| Element | Detail |
|---------|--------|
| **Condition** | `VG136` |
| **Si vrai** | '{284 |
| **Si faux** | -1}'PROG,IF(VG44,'{181,-1}'PROG,'{180,-1}'PROG)) |
| **Expression source** | Expression 54 : `IF(VG136,'{284,-1}'PROG,IF(VG44,'{181,-1}'PROG,'{180,-1}'PRO` |
| **Exemple** | Si VG136 â†’ '{284. Sinon â†’ -1}'PROG,IF(VG44,'{181,-1}'PROG,'{180,-1}'PROG)) |

## 6. CONTEXTE

- **Appele par**: [START (IDE 143)](PVE-IDE-143.md)
- **Appelle**: 14 programmes | **Tables**: 4 (W:0 R:3 L:1) | **Taches**: 3 | **Expressions**: 60

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 3)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 185 | 185 | Main (TPE) | Type0 | 994 | 432 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>185 - Main (TPE)
**Tache** : [185](#t1) | **Type** : Type0 | **Dimensions** : 994 x 432 DLU
**Bloc** : Traitement | **Titre IDE** : Main (TPE)

<!-- FORM-DATA:
{
    "width":  994,
    "vFactor":  8,
    "type":  "Type0",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  2,
                         "w":  992,
                         "fmt":  "",
                         "name":  "",
                         "h":  32,
                         "color":  "103",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  0,
                         "type":  "subform",
                         "var":  "",
                         "y":  35,
                         "w":  992,
                         "fmt":  "",
                         "name":  "SB_MAIN_TPE",
                         "h":  395,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  4,
                         "type":  "button",
                         "var":  "",
                         "y":  6,
                         "w":  258,
                         "fmt":  "LIEU",
                         "name":  "LIEU",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  451,
                         "type":  "button",
                         "var":  "",
                         "y":  6,
                         "w":  125,
                         "fmt":  "20",
                         "name":  "v.bouton mode",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  577,
                         "type":  "button",
                         "var":  "",
                         "y":  6,
                         "w":  96,
                         "fmt":  "CHECK IN",
                         "name":  "CHECKIN",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  775,
                         "type":  "button",
                         "var":  "",
                         "y":  6,
                         "w":  108,
                         "fmt":  "INVENTORY",
                         "name":  "INVENTORY",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  884,
                         "type":  "button",
                         "var":  "",
                         "y":  6,
                         "w":  103,
                         "fmt":  "EXIT",
                         "name":  "EXIT",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  265,
                         "type":  "combobox",
                         "var":  "",
                         "y":  7,
                         "w":  180,
                         "fmt":  "",
                         "name":  "v.MENU",
                         "h":  23,
                         "color":  "103",
                         "text":  "POS,CLOSING,REPORTS,STOCK,SERVICES,ADMIN",
                         "parent":  null
                     },
                     {
                         "x":  674,
                         "type":  "button",
                         "var":  "",
                         "y":  6,
                         "w":  100,
                         "fmt":  "EXCHANGE",
                         "name":  "EXCHANGE",
                         "h":  24,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "185",
    "height":  432
}
-->

<details>
<summary><strong>Champs : 1 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 265,7 | v.MENU | - | combobox |

</details>

<details>
<summary><strong>Boutons : 6 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| LIEU | 4,6 | Bouton fonctionnel |
| 20 | 451,6 | Bouton fonctionnel |
| CHECK IN | 577,6 | Appel [Menu Check IN / Exchange (IDE 183)](PVE-IDE-183.md) |
| INVENTORY | 775,6 | Appel [Menu Equipment inventory (IDE 184)](PVE-IDE-184.md) |
| EXIT | 884,6 | Quitte le programme |
| EXCHANGE | 674,6 | Appel [Menu Check IN / Exchange (IDE 183)](PVE-IDE-183.md) |

</details>

## 9. NAVIGATION

Ecran unique: **Main (TPE)**

### 9.3 Structure hierarchique (3 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **185.1** | [**Main (TPE)** (185)](#t1) [mockup](#ecran-t1) | - | 994x432 | Traitement |
| 185.1.1 | [Exist place (185.2)](#t3) | - | - | |
| **185.2** | [**Lecture solde du compte** (185.1)](#t2) | - | - | Calcul |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Traitement principal]
    DECISION{v.MENU}
    PROCESS[Traitement]
    ENDOK([END OK])
    ENDKO([END KO])

    START --> INIT --> SAISIE --> DECISION
    DECISION -->|OUI| PROCESS
    DECISION -->|NON| ENDKO
    PROCESS --> ENDOK

    style START fill:#3fb950,color:#000
    style ENDOK fill:#3fb950,color:#000
    style ENDKO fill:#f85149,color:#fff
    style DECISION fill:#58a6ff,color:#000
```

> **Legende**: Vert = START/END OK | Rouge = END KO | Bleu = Decisions
> *Algorigramme auto-genere. Utiliser `/algorigramme` pour une synthese metier detaillee.*

<!-- TAB:Donnees -->

## 10. TABLES

### Tables utilisees (4)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 47 | compte_gm________cgm | Comptes GM (generaux) | DB | R |   |   | 1 |
| 734 | arc_pv_cust_packages |  | DB | R |   |   | 1 |
| 766 | temp_forfait_ski |  | DB | R |   |   | 1 |
| 786 | qualite_avant_reprise |  | DB |   |   | L | 1 |

### Colonnes par table (2 / 3 tables avec colonnes identifiees)

<details>
<summary>Table 47 - compte_gm________cgm (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| G | v.Solde du compte | R | Numeric |

</details>

<details>
<summary>Table 734 - arc_pv_cust_packages (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | v.Lieu de vente | R | Alpha |
| B | v.MENU | R | Alpha |
| C | v.Retour ? | R | Numeric |
| D | v.Passage | R | Logical |
| E | v.End | R | Logical |
| F | v.LieuExist | R | Logical |
| G | v.Solde du compte | R | Numeric |
| H | v.confirm closure | R | Numeric |
| I | v.bouton mode | R | Alpha |
| J | v.Continuer Booking | R | Logical |
| K | v.Fin de journée lancée ? | R | Logical |
| L | v.Accounting Date | R | Date |
| M | P.Change Reason | R | Numeric |
| N | P.Prev Value | R | Alpha |

</details>

<details>
<summary>Table 766 - temp_forfait_ski (R) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (2)

Variables recues du programme appelant ([START (IDE 143)](PVE-IDE-143.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| M | P.Change Reason | Numeric | - |
| N | P.Prev Value | Alpha | 2x parametre entrant |

### 11.2 Variables de session (12)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | v.Lieu de vente | Alpha | - |
| B | v.MENU | Alpha | 16x session |
| C | v.Retour ? | Numeric | 2x session |
| D | v.Passage | Logical | 1x session |
| E | v.End | Logical | 1x session |
| F | v.LieuExist | Logical | 1x session |
| G | v.Solde du compte | Numeric | [185.1](#t2) |
| H | v.confirm closure | Numeric | 1x session |
| I | v.bouton mode | Alpha | - |
| J | v.Continuer Booking | Logical | 1x session |
| K | v.Fin de journée lancée ? | Logical | 1x session |
| L | v.Accounting Date | Date | 1x session |

## 12. EXPRESSIONS

**60 / 60 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONCATENATION | 2 | 0 |
| CONDITION | 27 | 5 |
| CALCULATION | 1 | 0 |
| CONSTANTE | 10 | 0 |
| OTHER | 13 | 0 |
| CAST_LOGIQUE | 3 | 0 |
| REFERENCE_VG | 2 | 0 |
| NEGATION | 2 | 0 |

### 12.2 Expressions cles par type

#### CONCATENATION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 43 | `'POS,CLOSING,REPORTS,STOCK,SERVICES,ADMIN'&IF(VG24,',TPE INIT,TPE DIARY','')&IF(GetParam('RENTAL'),',EQUIPMENT STATUS','')` | - |
| CONCATENATION | 1 | `Trim(GetParam ('SERVICELIB'))&'  -  POS '&Trim(VG6)` | - |

#### CONDITION (27 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 30 | `IF(VG104, VG25, Str(VG105,'8P0'))` | [RM-003](#rm-RM-003) |
| CONDITION | 38 | `IF(VG33='TB','TABLET','WORKSTATION')` | [RM-004](#rm-RM-004) |
| CONDITION | 4 | `IF(VG41,'v.Retour ? [C]'FORM,'v.MENU [B]'FORM)` | [RM-002](#rm-RM-002) |
| CONDITION | 54 | `IF(VG136,'{284,-1}'PROG,IF(VG44,'{181,-1}'PROG,'{180,-1}'PROG))` | [RM-005](#rm-RM-005) |
| CONDITION | 2 | `IF(Trim(v.MENU [B])='','POS',v.MENU [B])` | [RM-001](#rm-RM-001) |
| ... | | *+22 autres* | |

#### CALCULATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 47 | `v.Accounting Date [L]-7` | - |

#### CONSTANTE (10 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 35 | `'J'` | - |
| CONSTANTE | 32 | `'I'` | - |
| CONSTANTE | 46 | `'C'` | - |
| CONSTANTE | 53 | `'E'` | - |
| CONSTANTE | 52 | `'C'` | - |
| ... | | *+5 autres* | |

#### OTHER (13 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 51 | `SetCrsr(1)` | - |
| OTHER | 50 | `SetCrsr(2)` | - |
| OTHER | 49 | `Time()` | - |
| OTHER | 59 | `NOT(VG13)` | - |
| OTHER | 57 | `NOT(VG44) AND VG136` | - |
| ... | | *+8 autres* | |

#### CAST_LOGIQUE (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 14 | `'TRUE'LOG` | - |
| CAST_LOGIQUE | 11 | `'TRUE'LOG` | - |
| CAST_LOGIQUE | 5 | `GetParam ('RENTAL')='TRUE'LOG` | - |

#### REFERENCE_VG (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 56 | `VG44` | - |
| REFERENCE_VG | 7 | `VG14` | - |

#### NEGATION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| NEGATION | 42 | `NOT VG10` | - |
| NEGATION | 13 | `NOT v.Passage [D]` | - |

### 12.3 Toutes les expressions (60)

<details>
<summary>Voir les 60 expressions</summary>

#### CONCATENATION (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 1 | `Trim(GetParam ('SERVICELIB'))&'  -  POS '&Trim(VG6)` |
| 43 | `'POS,CLOSING,REPORTS,STOCK,SERVICES,ADMIN'&IF(VG24,',TPE INIT,TPE DIARY','')&IF(GetParam('RENTAL'),',EQUIPMENT STATUS','')` |

#### CONDITION (27)

| IDE | Expression Decodee |
|-----|-------------------|
| 23 | `Trim(v.MENU [B])='SERVICES' AND IN(GetParam ('GROUP'),'INFORMATICIEN','GESTION','C D V - H S M','CDV - R Pole')` |
| 2 | `IF(Trim(v.MENU [B])='','POS',v.MENU [B])` |
| 4 | `IF(VG41,'v.Retour ? [C]'FORM,'v.MENU [B]'FORM)` |
| 30 | `IF(VG104, VG25, Str(VG105,'8P0'))` |
| 31 | `IF(VG104, VG25, Str(VG105,'8P0'))` |
| 38 | `IF(VG33='TB','TABLET','WORKSTATION')` |
| 39 | `IF(VG33='TB','WS','TB')` |
| 54 | `IF(VG136,'{284,-1}'PROG,IF(VG44,'{181,-1}'PROG,'{180,-1}'PROG))` |
| 58 | `IF(VG104,VG105,Term())` |
| 6 | `v.Retour ? [C]=6` |
| 36 | `v.Solde du compte [G]<>0` |
| 37 | `v.Solde du compte [G]=0 OR (v.Solde du compte [G]<>0 AND v.confirm closure [H]=6)` |
| 41 | `MID(VG34,5,2)='TB' OR VG9 OR VG10` |
| 60 | `VG13 AND GetParam('SERVICE')<>P.Prev Value [N]` |
| 15 | `Trim(v.MENU [B])='POS'` |
| 16 | `Trim(v.MENU [B])='CLOSING' AND VG13 AND GetParam('SERVICE')=P.Prev Value [N]` |
| 18 | `Trim(v.MENU [B])='CLOSING'` |
| 19 | `Trim(v.MENU [B])='REPORTS' AND VG13` |
| 20 | `Trim(v.MENU [B])='REPORTS'` |
| 21 | `Trim(v.MENU [B])='STOCK' AND VG13` |
| 22 | `Trim(v.MENU [B])='STOCK'` |
| 24 | `Trim(v.MENU [B])='SERVICES'` |
| 25 | `Trim(v.MENU [B])='ADMIN' AND VG9` |
| 26 | `Trim(v.MENU [B])='ADMIN'` |
| 29 | `Trim(v.MENU [B])='TPE INIT'` |
| 34 | `Trim(v.MENU [B])='TPE DIARY'` |
| 44 | `Trim(v.MENU [B])='EQUIPMENT STATUS'` |

#### CALCULATION (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 47 | `v.Accounting Date [L]-7` |

#### CONSTANTE (10)

| IDE | Expression Decodee |
|-----|-------------------|
| 8 | `''` |
| 9 | `0` |
| 10 | `'C'` |
| 27 | `'POS'` |
| 28 | `'SB_MAIN_TPE'` |
| 32 | `'I'` |
| 35 | `'J'` |
| 46 | `'C'` |
| 52 | `'C'` |
| 53 | `'E'` |

#### OTHER (13)

| IDE | Expression Decodee |
|-----|-------------------|
| 3 | `v.LieuExist [F]` |
| 12 | `v.End [E]` |
| 17 | `GetParam ('SERVICE')` |
| 33 | `[P]` |
| 40 | `CtrlGoto('SB_MAIN_TPE',0,0)` |
| 45 | `VG65 AND v.Continuer Booking [J] AND v.Fin de journée lancée ? [K]` |
| 48 | `'00:00:00'TIME` |
| 49 | `Time()` |
| 50 | `SetCrsr(2)` |
| 51 | `SetCrsr(1)` |
| 55 | `NOT(VG44) AND NOT(VG136)` |
| 57 | `NOT(VG44) AND VG136` |
| 59 | `NOT(VG13)` |

#### CAST_LOGIQUE (3)

| IDE | Expression Decodee |
|-----|-------------------|
| 5 | `GetParam ('RENTAL')='TRUE'LOG` |
| 11 | `'TRUE'LOG` |
| 14 | `'TRUE'LOG` |

#### REFERENCE_VG (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 7 | `VG14` |
| 56 | `VG44` |

#### NEGATION (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 13 | `NOT v.Passage [D]` |
| 42 | `NOT VG10` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [START (IDE 143)](PVE-IDE-143.md) -> **Menu (IDE 185)**

```mermaid
graph LR
    T185[185 Menu]
    style T185 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC143[143 START]
    style CC143 fill:#3fb950
    CC1 --> CC143
    CC143 --> T185
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [143](PVE-IDE-143.md) | START | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T185[185 Menu]
    style T185 fill:#58a6ff
    C183[183 Menu Check IN Exch...]
    T185 --> C183
    style C183 fill:#3fb950
    C186[186 Main Sale]
    T185 --> C186
    style C186 fill:#3fb950
    C187[187 Main Sale-664]
    T185 --> C187
    style C187 fill:#3fb950
    C214[214 Main Sale Sale Bar...]
    T185 --> C214
    style C214 fill:#3fb950
    C129[129 Ligne Non Validées...]
    T185 --> C129
    style C129 fill:#3fb950
    C172[172 FindAppointmentsTo...]
    T185 --> C172
    style C172 fill:#3fb950
    C178[178 Menu Administration]
    T185 --> C178
    style C178 fill:#3fb950
    C179[179 Menu Stocks Manage...]
    T185 --> C179
    style C179 fill:#3fb950
    C180[180 Menu Cloture du se...]
    T185 --> C180
    style C180 fill:#3fb950
    C182[182 Menu Reports]
    T185 --> C182
    style C182 fill:#3fb950
    C184[184 Menu Equipment inv...]
    T185 --> C184
    style C184 fill:#3fb950
    C297[297 Get Bank accountin...]
    T185 --> C297
    style C297 fill:#3fb950
    C331[331 Sales place - select]
    T185 --> C331
    style C331 fill:#3fb950
    C332[332 Choix - Services]
    T185 --> C332
    style C332 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [183](PVE-IDE-183.md) | Menu Check IN / Exchange | 2 | Navigation menu |
| [186](PVE-IDE-186.md) | Main Sale | 2 | Sous-programme |
| [187](PVE-IDE-187.md) | Main Sale-664 | 2 | Sous-programme |
| [214](PVE-IDE-214.md) | Main Sale Sale Bar Code | 2 | Sous-programme |
| [129](PVE-IDE-129.md) | Ligne Non Validées & Edit Book | 1 | Sous-programme |
| [172](PVE-IDE-172.md) | FindAppointmentsToClose | 1 | Fermeture session |
| [178](PVE-IDE-178.md) | Menu Administration | 1 | Navigation menu |
| [179](PVE-IDE-179.md) | Menu Stocks Management | 1 | Calcul de donnees |
| [180](PVE-IDE-180.md) | Menu Cloture du service | 1 | Fermeture session |
| [182](PVE-IDE-182.md) | Menu Reports | 1 | Navigation menu |
| [184](PVE-IDE-184.md) | Menu Equipment inventory | 1 | Navigation menu |
| [297](PVE-IDE-297.md) | Get Bank accounting date | 1 | Recuperation donnees |
| [331](PVE-IDE-331.md) | Sales place - select | 1 | Selection/consultation |
| [332](PVE-IDE-332.md) | Choix - Services | 1 | Selection/consultation |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 185 | Programme compact |
| Expressions | 60 | Logique moderee |
| Tables WRITE | 0 | Impact faible |
| Sous-programmes | 14 | Forte dependance |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 4.3% (8 / 185) | Code sain |
| Regles metier | 5 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (2 taches: 1 ecran, 1 traitement)

- **Strategie** : Orchestrateur avec 1 ecrans (Razor/React) et 1 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 14 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Calcul (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Services de calcul purs (Domain Services).
- Migrer la logique de calcul (stock, compteurs, montants)

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| [Main Sale-664 (IDE 187)](PVE-IDE-187.md) | Sous-programme | 2x | Haute - Sous-programme |
| [Main Sale Sale Bar Code (IDE 214)](PVE-IDE-214.md) | Sous-programme | 2x | Haute - Sous-programme |
| [Menu Check IN / Exchange (IDE 183)](PVE-IDE-183.md) | Sous-programme | 2x | Haute - Navigation menu |
| [Main Sale (IDE 186)](PVE-IDE-186.md) | Sous-programme | 2x | Haute - Sous-programme |
| [Menu Equipment inventory (IDE 184)](PVE-IDE-184.md) | Sous-programme | 1x | Normale - Navigation menu |
| [Menu Reports (IDE 182)](PVE-IDE-182.md) | Sous-programme | 1x | Normale - Navigation menu |
| [Get Bank accounting date (IDE 297)](PVE-IDE-297.md) | Sous-programme | 1x | Normale - Recuperation donnees |
| [Choix - Services (IDE 332)](PVE-IDE-332.md) | Sous-programme | 1x | Normale - Selection/consultation |
| [Sales place - select (IDE 331)](PVE-IDE-331.md) | Sous-programme | 1x | Normale - Selection/consultation |
| [FindAppointmentsToClose (IDE 172)](PVE-IDE-172.md) | Sous-programme | 1x | Normale - Fermeture session |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 18:45*
