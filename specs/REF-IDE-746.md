# REF IDE 746 - Purge caisse

> **Analyse**: Phases 1-4 2026-02-03 14:07 -> 14:07 (16s) | Assemblage 14:07
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | REF |
| IDE Position | 746 |
| Nom Programme | Purge caisse |
| Fichier source | `Prg_746.xml` |
| Dossier IDE | Caisse |
| Taches | 41 (2 ecrans visibles) |
| Tables modifiees | 12 |
| Programmes appeles | 1 |

## 2. DESCRIPTION FONCTIONNELLE

**Purge caisse** assure la gestion complete de ce processus, accessible depuis [Lancement Purge (IDE 748)](REF-IDE-748.md).

Le flux de traitement s'organise en **2 blocs fonctionnels** :

- **Traitement** (40 taches) : traitements metier divers
- **Calcul** (1 tache) : calculs de montants, stocks ou compteurs

**Donnees modifiees** : 12 tables en ecriture (comptage_coffre_devise_histo, comptage_coffre_histo, comptage_coffre_montant_histo, comptage_caisse_devise_histo, comptage_caisse_histo, comptage_caisse_montant_histo, histo_sessions_caisse, histo_sessions_caisse_article, histo_sessions_caisse_detail, histo_sessions_caisse_devise, histo_sessions_caisse_remise, liste_user_pour_la_purge).

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (40 taches)

- **746** - Veuillez patienter ... **[[ECRAN]](#ecran-t1)**
- **746.1** - Paramètres
- **746.2** - Liste USER
- **746.2.1** - Delete User
- **746.2.2** - Table USER
- **746.2.3** - Sessions
- **746.2.3.1** - Pointe USER
- **746.2.4** - Coffre
- **746.2.4.1** - Pointe USER
- **746.3** - (sans nom) **[[ECRAN]](#ecran-t10)**
- **746.3.1** - Session maxi
- **746.3.2** - Coffre maxi
- **746.3.3.1** - Montant
- **746.3.3.2** - Devise
- **746.3.4** - session
- **746.3.4.1** - detail
- **746.3.4.2** - article
- **746.3.4.3** - devise
- **746.3.4.4** - remise
- **746.3.5** - coffre
- **746.3.5.1** - montant
- **746.3.5.2** - devise
- **746.4** - session
- **746.4.1** - detail
- **746.4.2** - article
- **746.4.3** - devise
- **746.4.4** - remise
- **746.5** - session
- **746.5.1** - detail
- **746.5.2** - detail
- **746.5.3** - article
- **746.5.4** - devise
- **746.5.5** - remise
- **746.6** - session
- **746.6.1** - detail
- **746.6.2** - detail
- **746.6.3** - article
- **746.6.4** - devise
- **746.6.5** - remise
- **746.7** - Intégrité Pointage Appro Remis

Delegue a : [Purge caisse PMS-690 (IDE 747)](REF-IDE-747.md)

#### Phase 2 : Calcul (1 tache)

- **746.3.3** - comptage caisse

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| histo_sessions_caisse | **W**/L (7 usages) | Sessions de caisse |
| histo_sessions_caisse_detail | **W**/L (7 usages) | Sessions de caisse |
| histo_sessions_caisse_article | **W** (4 usages) | Articles et stock |
| liste_user_pour_la_purge | **W** (4 usages) |  |
| histo_sessions_caisse_remise | **W** (4 usages) | Sessions de caisse |
| histo_sessions_caisse_devise | **W** (4 usages) | Sessions de caisse |
| comptage_coffre_histo | **W** (3 usages) | Etat du coffre |
| comptage_caisse_histo | **W** (1 usages) | Sessions de caisse |
| comptage_coffre_devise_histo | **W** (1 usages) | Etat du coffre |
| comptage_caisse_devise_histo | **W** (1 usages) | Sessions de caisse |
| comptage_caisse_montant_histo | **W** (1 usages) | Sessions de caisse |
| comptage_coffre_montant_histo | **W** (1 usages) | Etat du coffre |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (40 taches)

Traitements internes.

---

#### <a id="t1"></a>746 - Veuillez patienter ... [[ECRAN]](#ecran-t1)

**Role** : Tache d'orchestration : point d'entree du programme (40 sous-taches). Coordonne l'enchainement des traitements.
**Ecran** : 424 x 112 DLU (MDI) | [Voir mockup](#ecran-t1)

<details>
<summary>39 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [746.1](#t2) | Paramètres | Traitement |
| [746.2](#t3) | Liste USER | Traitement |
| [746.2.1](#t4) | Delete User | Traitement |
| [746.2.2](#t5) | Table USER | Traitement |
| [746.2.3](#t6) | Sessions | Traitement |
| [746.2.3.1](#t7) | Pointe USER | Traitement |
| [746.2.4](#t8) | Coffre | Traitement |
| [746.2.4.1](#t9) | Pointe USER | Traitement |
| [746.3](#t10) | (sans nom) **[[ECRAN]](#ecran-t10)** | Traitement |
| [746.3.1](#t11) | Session maxi | Traitement |
| [746.3.2](#t12) | Coffre maxi | Traitement |
| [746.3.3.1](#t14) | Montant | Traitement |
| [746.3.3.2](#t15) | Devise | Traitement |
| [746.3.4](#t16) | session | Traitement |
| [746.3.4.1](#t17) | detail | Traitement |
| [746.3.4.2](#t18) | article | Traitement |
| [746.3.4.3](#t19) | devise | Traitement |
| [746.3.4.4](#t20) | remise | Traitement |
| [746.3.5](#t21) | coffre | Traitement |
| [746.3.5.1](#t22) | montant | Traitement |
| [746.3.5.2](#t23) | devise | Traitement |
| [746.4](#t24) | session | Traitement |
| [746.4.1](#t25) | detail | Traitement |
| [746.4.2](#t26) | article | Traitement |
| [746.4.3](#t27) | devise | Traitement |
| [746.4.4](#t28) | remise | Traitement |
| [746.5](#t29) | session | Traitement |
| [746.5.1](#t30) | detail | Traitement |
| [746.5.2](#t31) | detail | Traitement |
| [746.5.3](#t32) | article | Traitement |
| [746.5.4](#t33) | devise | Traitement |
| [746.5.5](#t34) | remise | Traitement |
| [746.6](#t35) | session | Traitement |
| [746.6.1](#t36) | detail | Traitement |
| [746.6.2](#t37) | detail | Traitement |
| [746.6.3](#t38) | article | Traitement |
| [746.6.4](#t39) | devise | Traitement |
| [746.6.5](#t40) | remise | Traitement |
| [746.7](#t41) | Intégrité Pointage Appro Remis | Traitement |

</details>

---

#### <a id="t2"></a>746.1 - Paramètres

**Role** : Traitement : Paramètres.

---

#### <a id="t3"></a>746.2 - Liste USER

**Role** : Traitement : Liste USER.
**Variables liees** : D (Session maxi à purger du user), E (Chrono coffre maxi du user)

---

#### <a id="t4"></a>746.2.1 - Delete User

**Role** : Traitement : Delete User.
**Variables liees** : D (Session maxi à purger du user), E (Chrono coffre maxi du user)

---

#### <a id="t5"></a>746.2.2 - Table USER

**Role** : Traitement : Table USER.
**Variables liees** : D (Session maxi à purger du user), E (Chrono coffre maxi du user)

---

#### <a id="t6"></a>746.2.3 - Sessions

**Role** : Traitement : Sessions.
**Variables liees** : B (Sessions caisse à conserver)

---

#### <a id="t7"></a>746.2.3.1 - Pointe USER

**Role** : Traitement : Pointe USER.
**Variables liees** : D (Session maxi à purger du user), E (Chrono coffre maxi du user)

---

#### <a id="t8"></a>746.2.4 - Coffre

**Role** : Traitement : Coffre.
**Variables liees** : C (Comptages coffre à conserver), E (Chrono coffre maxi du user)

---

#### <a id="t9"></a>746.2.4.1 - Pointe USER

**Role** : Traitement : Pointe USER.
**Variables liees** : D (Session maxi à purger du user), E (Chrono coffre maxi du user)

---

#### <a id="t10"></a>746.3 - (sans nom) [[ECRAN]](#ecran-t10)

**Role** : Traitement interne.
**Ecran** : 326 x 63 DLU (MDI) | [Voir mockup](#ecran-t10)

---

#### <a id="t11"></a>746.3.1 - Session maxi

**Role** : Traitement : Session maxi.
**Variables liees** : B (Sessions caisse à conserver), D (Session maxi à purger du user), E (Chrono coffre maxi du user)

---

#### <a id="t12"></a>746.3.2 - Coffre maxi

**Role** : Traitement : Coffre maxi.
**Variables liees** : C (Comptages coffre à conserver), D (Session maxi à purger du user), E (Chrono coffre maxi du user)

---

#### <a id="t14"></a>746.3.3.1 - Montant

**Role** : Traitement : Montant.

---

#### <a id="t15"></a>746.3.3.2 - Devise

**Role** : Traitement : Devise.

---

#### <a id="t16"></a>746.3.4 - session

**Role** : Traitement : session.
**Variables liees** : B (Sessions caisse à conserver), D (Session maxi à purger du user)

---

#### <a id="t17"></a>746.3.4.1 - detail

**Role** : Traitement : detail.

---

#### <a id="t18"></a>746.3.4.2 - article

**Role** : Traitement : article.

---

#### <a id="t19"></a>746.3.4.3 - devise

**Role** : Traitement : devise.

---

#### <a id="t20"></a>746.3.4.4 - remise

**Role** : Calcul fidelite/avantage : remise.

---

#### <a id="t21"></a>746.3.5 - coffre

**Role** : Traitement : coffre.
**Variables liees** : C (Comptages coffre à conserver), E (Chrono coffre maxi du user)

---

#### <a id="t22"></a>746.3.5.1 - montant

**Role** : Traitement : montant.

---

#### <a id="t23"></a>746.3.5.2 - devise

**Role** : Traitement : devise.

---

#### <a id="t24"></a>746.4 - session

**Role** : Traitement : session.
**Variables liees** : B (Sessions caisse à conserver), D (Session maxi à purger du user)

---

#### <a id="t25"></a>746.4.1 - detail

**Role** : Traitement : detail.

---

#### <a id="t26"></a>746.4.2 - article

**Role** : Traitement : article.

---

#### <a id="t27"></a>746.4.3 - devise

**Role** : Traitement : devise.

---

#### <a id="t28"></a>746.4.4 - remise

**Role** : Calcul fidelite/avantage : remise.

---

#### <a id="t29"></a>746.5 - session

**Role** : Traitement : session.
**Variables liees** : B (Sessions caisse à conserver), D (Session maxi à purger du user)

---

#### <a id="t30"></a>746.5.1 - detail

**Role** : Traitement : detail.

---

#### <a id="t31"></a>746.5.2 - detail

**Role** : Traitement : detail.

---

#### <a id="t32"></a>746.5.3 - article

**Role** : Traitement : article.

---

#### <a id="t33"></a>746.5.4 - devise

**Role** : Traitement : devise.

---

#### <a id="t34"></a>746.5.5 - remise

**Role** : Calcul fidelite/avantage : remise.

---

#### <a id="t35"></a>746.6 - session

**Role** : Traitement : session.
**Variables liees** : B (Sessions caisse à conserver), D (Session maxi à purger du user)

---

#### <a id="t36"></a>746.6.1 - detail

**Role** : Traitement : detail.

---

#### <a id="t37"></a>746.6.2 - detail

**Role** : Traitement : detail.

---

#### <a id="t38"></a>746.6.3 - article

**Role** : Traitement : article.

---

#### <a id="t39"></a>746.6.4 - devise

**Role** : Traitement : devise.

---

#### <a id="t40"></a>746.6.5 - remise

**Role** : Calcul fidelite/avantage : remise.

---

#### <a id="t41"></a>746.7 - Intégrité Pointage Appro Remis

**Role** : Traitement : Intégrité Pointage Appro Remis.


### 3.2 Calcul (1 tache)

Calculs metier : montants, stocks, compteurs.

---

#### <a id="t13"></a>746.3.3 - comptage caisse

**Role** : Traitement : comptage caisse.
**Variables liees** : B (Sessions caisse à conserver), C (Comptages coffre à conserver)


## 5. REGLES METIER

*(Aucune regle metier identifiee)*

## 6. CONTEXTE

- **Appele par**: [Lancement Purge (IDE 748)](REF-IDE-748.md)
- **Appelle**: 1 programmes | **Tables**: 14 (W:12 R:1 L:3) | **Taches**: 41 | **Expressions**: 3

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (2 / 41)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 746 | 746 | Veuillez patienter ... | MDI | 424 | 112 | Traitement |
| 2 | 746.3 | 746.3 | (sans nom) | MDI | 326 | 63 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>746 - Veuillez patienter ...
**Tache** : [746](#t1) | **Type** : MDI | **Dimensions** : 424 x 112 DLU
**Bloc** : Traitement | **Titre IDE** : Veuillez patienter ...

<!-- FORM-DATA:
{
    "width":  424,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  91,
                         "type":  "label",
                         "var":  "",
                         "y":  9,
                         "w":  326,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "7",
                         "text":  "Purge caisse en cours ...",
                         "parent":  null
                     },
                     {
                         "x":  7,
                         "type":  "image",
                         "var":  "",
                         "y":  1,
                         "w":  72,
                         "fmt":  "",
                         "name":  "",
                         "h":  25,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "746",
    "height":  112
}
-->

---

#### <a id="ecran-t10"></a>746.3 - (sans nom)
**Tache** : [746.3](#t10) | **Type** : MDI | **Dimensions** : 326 x 63 DLU
**Bloc** : Traitement | **Titre IDE** : (sans nom)

<!-- FORM-DATA:
{
    "width":  326,
    "vFactor":  8,
    "type":  "MDI",
    "hFactor":  8,
    "controls":  [
                     {
                         "x":  71,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "110",
                         "w":  186,
                         "y":  0,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  14,
                         "h":  54,
                         "cols":  [
                                      {
                                          "title":  "User",
                                          "layer":  1,
                                          "w":  177
                                      }
                                  ],
                         "rows":  1
                     },
                     {
                         "x":  75,
                         "type":  "edit",
                         "var":  "",
                         "y":  14,
                         "w":  104,
                         "fmt":  "",
                         "name":  "",
                         "h":  10,
                         "color":  "110",
                         "text":  "",
                         "parent":  1
                     }
                 ],
    "taskId":  "746.3",
    "height":  63
}
-->

<details>
<summary><strong>Champs : 1 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 75,14 | (sans nom) | - | edit |

</details>

## 9. NAVIGATION

### 9.1 Enchainement des ecrans

```mermaid
flowchart TD
    START([Entree])
    style START fill:#3fb950
    VF1[746 Veuillez patienter ...]
    style VF1 fill:#58a6ff
    VF10[746.3 sans nom]
    style VF10 fill:#58a6ff
    EXT747[IDE 747 Purge caisse P...]
    style EXT747 fill:#3fb950
    FIN([Sortie])
    style FIN fill:#f85149
    START --> VF1
    VF1 -->|Sous-programme| EXT747
    EXT747 --> FIN
```

**Detail par enchainement :**

| Depuis | Action | Vers | Retour |
|--------|--------|------|--------|
| Veuillez patienter ... | Sous-programme | [Purge caisse PMS-690 (IDE 747)](REF-IDE-747.md) | Retour ecran |

### 9.3 Structure hierarchique (41 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **746.1** | [**Veuillez patienter ...** (746)](#t1) [mockup](#ecran-t1) | MDI | 424x112 | Traitement |
| 746.1.1 | [Paramètres (746.1)](#t2) | MDI | - | |
| 746.1.2 | [Liste USER (746.2)](#t3) | MDI | - | |
| 746.1.3 | [Delete User (746.2.1)](#t4) | - | - | |
| 746.1.4 | [Table USER (746.2.2)](#t5) | MDI | - | |
| 746.1.5 | [Sessions (746.2.3)](#t6) | MDI | - | |
| 746.1.6 | [Pointe USER (746.2.3.1)](#t7) | MDI | - | |
| 746.1.7 | [Coffre (746.2.4)](#t8) | MDI | - | |
| 746.1.8 | [Pointe USER (746.2.4.1)](#t9) | MDI | - | |
| 746.1.9 | [(sans nom) (746.3)](#t10) [mockup](#ecran-t10) | MDI | 326x63 | |
| 746.1.10 | [Session maxi (746.3.1)](#t11) | MDI | - | |
| 746.1.11 | [Coffre maxi (746.3.2)](#t12) | MDI | - | |
| 746.1.12 | [Montant (746.3.3.1)](#t14) | MDI | - | |
| 746.1.13 | [Devise (746.3.3.2)](#t15) | MDI | - | |
| 746.1.14 | [session (746.3.4)](#t16) | MDI | - | |
| 746.1.15 | [detail (746.3.4.1)](#t17) | MDI | - | |
| 746.1.16 | [article (746.3.4.2)](#t18) | MDI | - | |
| 746.1.17 | [devise (746.3.4.3)](#t19) | MDI | - | |
| 746.1.18 | [remise (746.3.4.4)](#t20) | MDI | - | |
| 746.1.19 | [coffre (746.3.5)](#t21) | MDI | - | |
| 746.1.20 | [montant (746.3.5.1)](#t22) | MDI | - | |
| 746.1.21 | [devise (746.3.5.2)](#t23) | MDI | - | |
| 746.1.22 | [session (746.4)](#t24) | MDI | - | |
| 746.1.23 | [detail (746.4.1)](#t25) | MDI | - | |
| 746.1.24 | [article (746.4.2)](#t26) | MDI | - | |
| 746.1.25 | [devise (746.4.3)](#t27) | MDI | - | |
| 746.1.26 | [remise (746.4.4)](#t28) | MDI | - | |
| 746.1.27 | [session (746.5)](#t29) | MDI | - | |
| 746.1.28 | [detail (746.5.1)](#t30) | MDI | - | |
| 746.1.29 | [detail (746.5.2)](#t31) | MDI | - | |
| 746.1.30 | [article (746.5.3)](#t32) | MDI | - | |
| 746.1.31 | [devise (746.5.4)](#t33) | MDI | - | |
| 746.1.32 | [remise (746.5.5)](#t34) | MDI | - | |
| 746.1.33 | [session (746.6)](#t35) | MDI | - | |
| 746.1.34 | [detail (746.6.1)](#t36) | MDI | - | |
| 746.1.35 | [detail (746.6.2)](#t37) | MDI | - | |
| 746.1.36 | [article (746.6.3)](#t38) | MDI | - | |
| 746.1.37 | [devise (746.6.4)](#t39) | MDI | - | |
| 746.1.38 | [remise (746.6.5)](#t40) | MDI | - | |
| 746.1.39 | [Intégrité Pointage Appro Remis (746.7)](#t41) | - | - | |
| **746.2** | [**comptage caisse** (746.3.3)](#t13) | MDI | - | Calcul |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[user]
    UPDATE[MAJ 12 tables]
    ENDOK([END OK])

    START --> INIT --> SAISIE
    SAISIE --> UPDATE --> ENDOK

    style START fill:#3fb950,color:#000
    style ENDOK fill:#3fb950,color:#000
```

> **Legende**: Vert = START/END OK | Rouge = END KO | Bleu = Decisions
> *Algorigramme auto-genere. Utiliser `/algorigramme` pour une synthese metier detaillee.*

<!-- TAB:Donnees -->

## 10. TABLES

### Tables utilisees (14)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 215 | comptage_coffre_devise_histo | Etat du coffre | DB |   | **W** |   | 1 |
| 217 | comptage_coffre_histo | Etat du coffre | DB |   | **W** |   | 3 |
| 218 | comptage_coffre_montant_histo | Etat du coffre | DB |   | **W** |   | 1 |
| 220 | comptage_caisse_devise_histo | Sessions de caisse | DB |   | **W** |   | 1 |
| 222 | comptage_caisse_histo | Sessions de caisse | DB |   | **W** |   | 1 |
| 223 | comptage_caisse_montant_histo | Sessions de caisse | DB |   | **W** |   | 1 |
| 246 | histo_sessions_caisse | Sessions de caisse | DB |   | **W** | L | 7 |
| 247 | histo_sessions_caisse_article | Articles et stock | DB |   | **W** |   | 4 |
| 249 | histo_sessions_caisse_detail | Sessions de caisse | DB |   | **W** | L | 7 |
| 250 | histo_sessions_caisse_devise | Sessions de caisse | DB |   | **W** |   | 4 |
| 251 | histo_sessions_caisse_remise | Sessions de caisse | DB |   | **W** |   | 4 |
| 262 | liste_user_pour_la_purge |  | DB |   | **W** |   | 4 |
| 677 | parametres_caisse | Sessions de caisse | DB | R |   |   | 1 |
| 718 | utilisateur______uti |  | DB |   |   | L | 2 |

### Colonnes par table (14 / 13 tables avec colonnes identifiees)

<details>
<summary>Table 215 - comptage_coffre_devise_histo (**W**) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | L.Clot_auto_comptage | W | Logical |
| C | Comptages coffre à conserver | W | Numeric |
| E | Chrono coffre maxi du user | W | Numeric |

</details>

<details>
<summary>Table 217 - comptage_coffre_histo (**W**) - 3 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | L.Clot_auto_comptage | W | Logical |
| C | Comptages coffre à conserver | W | Numeric |
| E | Chrono coffre maxi du user | W | Numeric |

</details>

<details>
<summary>Table 218 - comptage_coffre_montant_histo (**W**) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | L.Clot_auto_comptage | W | Logical |
| C | Comptages coffre à conserver | W | Numeric |
| E | Chrono coffre maxi du user | W | Numeric |

</details>

<details>
<summary>Table 220 - comptage_caisse_devise_histo (**W**) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | L.Clot_auto_comptage | W | Logical |
| B | Sessions caisse à conserver | W | Numeric |
| C | Comptages coffre à conserver | W | Numeric |

</details>

<details>
<summary>Table 222 - comptage_caisse_histo (**W**) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | L.Clot_auto_comptage | W | Logical |
| B | Sessions caisse à conserver | W | Numeric |
| C | Comptages coffre à conserver | W | Numeric |

</details>

<details>
<summary>Table 223 - comptage_caisse_montant_histo (**W**) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | L.Clot_auto_comptage | W | Logical |
| B | Sessions caisse à conserver | W | Numeric |
| C | Comptages coffre à conserver | W | Numeric |

</details>

<details>
<summary>Table 246 - histo_sessions_caisse (**W**/L) - 7 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | L.Clot_auto_caisse | W | Logical |
| B | Sessions caisse à conserver | W | Numeric |

</details>

<details>
<summary>Table 247 - histo_sessions_caisse_article (**W**) - 4 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | L.Clot_auto_caisse | W | Logical |
| B | Sessions caisse à conserver | W | Numeric |

</details>

<details>
<summary>Table 249 - histo_sessions_caisse_detail (**W**/L) - 7 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | L.Clot_auto_caisse | W | Logical |
| B | Sessions caisse à conserver | W | Numeric |

</details>

<details>
<summary>Table 250 - histo_sessions_caisse_devise (**W**) - 4 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | L.Clot_auto_caisse | W | Logical |
| B | Sessions caisse à conserver | W | Numeric |

</details>

<details>
<summary>Table 251 - histo_sessions_caisse_remise (**W**) - 4 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | L.Clot_auto_caisse | W | Logical |
| B | Sessions caisse à conserver | W | Numeric |

</details>

<details>
<summary>Table 262 - liste_user_pour_la_purge (**W**) - 4 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | Trouver_user | W | Logical |
| D | Session maxi à purger du user | W | Numeric |
| E | Chrono coffre maxi du user | W | Numeric |

</details>

<details>
<summary>Table 677 - parametres_caisse (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | L.Clot_auto_caisse | R | Logical |
| B | Sessions caisse à conserver | R | Numeric |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (1)

Variables recues du programme appelant ([Lancement Purge (IDE 748)](REF-IDE-748.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P.i.Utilisateur | Unicode | 2x parametre entrant |

### 11.2 Autres (4)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| B | Sessions caisse à conserver | Numeric | - |
| C | Comptages coffre à conserver | Numeric | - |
| D | Session maxi à purger du user | Numeric | - |
| E | Chrono coffre maxi du user | Numeric | - |

## 12. EXPRESSIONS

**3 / 3 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| NEGATION | 1 | 0 |
| CONDITION | 2 | 0 |

### 12.2 Expressions cles par type

#### NEGATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| NEGATION | 3 | `NOT VG47` | - |

#### CONDITION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 2 | `Trim(P.i.Utilisateur [A])<>''` | - |
| CONDITION | 1 | `Trim(P.i.Utilisateur [A])=''` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Lancement Purge (IDE 748)](REF-IDE-748.md) -> **Purge caisse (IDE 746)**

```mermaid
graph LR
    T746[746 Purge caisse]
    style T746 fill:#58a6ff
    CC748[748 Lancement Purge]
    style CC748 fill:#8b5cf6
    CC748 --> T746
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [748](REF-IDE-748.md) | Lancement Purge | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T746[746 Purge caisse]
    style T746 fill:#58a6ff
    C747[747 Purge caisse PMS-690]
    T746 --> C747
    style C747 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [747](REF-IDE-747.md) | Purge caisse PMS-690 | 1 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 235 | Taille moyenne |
| Expressions | 3 | Peu de logique |
| Tables WRITE | 12 | Fort impact donnees |
| Sous-programmes | 1 | Peu de dependances |
| Ecrans visibles | 2 | Quelques ecrans |
| Code desactive | 0% (0 / 235) | Code sain |
| Regles metier | 0 | Pas de regle identifiee |

### 14.2 Plan de migration par bloc

#### Traitement (40 taches: 2 ecrans, 38 traitements)

- **Strategie** : Orchestrateur avec 2 ecrans (Razor/React) et 38 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 1 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Calcul (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Services de calcul purs (Domain Services).
- Migrer la logique de calcul (stock, compteurs, montants)

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| comptage_coffre_devise_histo | Table WRITE (Database) | 1x | Schema + repository |
| comptage_coffre_histo | Table WRITE (Database) | 3x | Schema + repository |
| comptage_coffre_montant_histo | Table WRITE (Database) | 1x | Schema + repository |
| comptage_caisse_devise_histo | Table WRITE (Database) | 1x | Schema + repository |
| comptage_caisse_histo | Table WRITE (Database) | 1x | Schema + repository |
| comptage_caisse_montant_histo | Table WRITE (Database) | 1x | Schema + repository |
| histo_sessions_caisse | Table WRITE (Database) | 6x | Schema + repository |
| histo_sessions_caisse_article | Table WRITE (Database) | 4x | Schema + repository |
| histo_sessions_caisse_detail | Table WRITE (Database) | 4x | Schema + repository |
| histo_sessions_caisse_devise | Table WRITE (Database) | 4x | Schema + repository |
| histo_sessions_caisse_remise | Table WRITE (Database) | 4x | Schema + repository |
| liste_user_pour_la_purge | Table WRITE (Database) | 4x | Schema + repository |
| [Purge caisse PMS-690 (IDE 747)](REF-IDE-747.md) | Sous-programme | 1x | Normale - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 14:07*
