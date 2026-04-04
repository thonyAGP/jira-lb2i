# WEL IDE 96 - Ventes

> **Analyse**: Phases 1-4 2026-02-03 21:43 -> 21:43 (18s) | Assemblage 21:43
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | WEL |
| IDE Position | 96 |
| Nom Programme | Ventes |
| Fichier source | `Prg_96.xml` |
| Dossier IDE | Workflow |
| Taches | 41 (7 ecrans visibles) |
| Tables modifiees | 7 |
| Programmes appeles | 6 |

## 2. DESCRIPTION FONCTIONNELLE

**Ventes** assure la gestion complete de ce processus, accessible depuis [Lancement ventes (IDE 95)](WEL-IDE-95.md).

Le flux de traitement s'organise en **9 blocs fonctionnels** :

- **Traitement** (20 taches) : traitements metier divers
- **Creation** (4 taches) : insertion d'enregistrements en base (mouvements, prestations)
- **Transfert** (4 taches) : transferts de donnees entre modules ou deversements
- **Initialisation** (4 taches) : reinitialisation d'etats et de variables de travail
- **Calcul** (3 taches) : calculs de montants, stocks ou compteurs
- **Saisie** (2 taches) : ecrans de saisie utilisateur (formulaires, champs, donnees)
- **Reglement** (2 taches) : gestion des moyens de paiement et reglements
- **Impression** (1 tache) : generation de tickets et documents
- **Consultation** (1 tache) : ecrans de recherche, selection et consultation

**Donnees modifiees** : 7 tables en ecriture (reseau_cloture___rec, compte_gm________cgm, compteurs________cpt, trf_transfert_new, saisie_od_taiforfait, type_prestation, total_jour_forfait_ski).

**Logique metier** : 3 regles identifiees couvrant conditions metier.

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (20 taches)

- **96** - Sales **[[ECRAN]](#ecran-t1)**
- **96.1** - Produits **[[ECRAN]](#ecran-t2)**
- **96.1.1** - Affectation Auto
- **96.1.3** - Gratuite ?
- **96.1.5.3** - Affectation **[[ECRAN]](#ecran-t12)**
- **96.1.5.4** - Test reseau
- **96.1.5.7** - VRL
- **96.1.5.8** - ourcentage
- **96.2** - Dé-Affecition
- **96.5** - Test si cloture en cours v1
- **96.5.1** - Blocage cloture v1
- **96.6** - Deblocage cloture v1
- **96.7** - garantie?
- **96.10** - Affectation Auto
- **96.11** - Services **[[ECRAN]](#ecran-t33)**
- **96.12** - Suppression ligne a 0
- **96.1.5.6.2.1** - Supprime enregs non affectés
- **96.14** - Solde gift pass
- **96.5.2** - Blocage cloture v1
- **96.15** - Deblocage cloture v1

Delegue a : [Traitement des mails (IDE 89)](WEL-IDE-89.md), [Search client avec liste (IDE 17)](WEL-IDE-17.md)

#### Phase 2 : Initialisation (4 taches)

- **96.1.2** - RAZ 269
- **96.1.5.1** - RAZ 269
- **96.3** - RAZ 269
- **96.8** - RAZ 269

#### Phase 3 : Consultation (1 tache)

- **96.1.3.1** - Recherche imputation/ssimput

Delegue a : [Zoom Mode paiement (IDE 110)](WEL-IDE-110.md)

#### Phase 4 : Creation (4 taches)

- **96.1.4** - Creation Tempo
- **96.1.5.2.1** - Creation
- **96.1.5.3.1** - Creation Enregistrement Transf **[[ECRAN]](#ecran-t13)**
- **96.1.5.10** - Creation Tempo

Delegue a : [Create logbook (IDE 81)](WEL-IDE-81.md)

#### Phase 5 : Saisie (2 taches)

- **96.1.5** - Ventes **[[ECRAN]](#ecran-t8)**
- **96.4** - VRL : Saisie identité **[[ECRAN]](#ecran-t25)**

Delegue a : [Saisie Signature (IDE 82)](WEL-IDE-82.md), [Saisie Signature Validation (IDE 83)](WEL-IDE-83.md)

#### Phase 6 : Reglement (2 taches)

- **96.1.5.2** - Creation reglement
- **96.13** - Maj reglement

Delegue a : [Zoom Mode paiement (IDE 110)](WEL-IDE-110.md)

#### Phase 7 : Impression (1 tache)

- **96.1.5.5** - Increment Num. Ticket(VRL/VSL)

Delegue a : [Search client avec liste (IDE 17)](WEL-IDE-17.md)

#### Phase 8 : Transfert (4 taches)

- **96.1.5.6** - Type transfert
- **96.1.5.6.1** - Affiche Transfert A/R **[[ECRAN]](#ecran-t17)**
- **96.9** - Raz Affectation Transfert
- **96.1.5.6.2** - Affectation PAX / Transfert **[[ECRAN]](#ecran-t45)**

#### Phase 9 : Calcul (3 taches)

- **96.1.5.9** - Compte Enregs affectés
- **96.1.5.11** - Debloque compte
- **96.1.5.6.2.2** - Compte Enregs affectés

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| total_jour_forfait_ski | R/**W**/L (9 usages) |  |
| type_prestation | **W**/L (7 usages) | Prestations/services vendus |
| saisie_od_taiforfait | **W**/L (6 usages) |  |
| reseau_cloture___rec | R/**W** (5 usages) | Donnees reseau/cloture |
| compte_gm________cgm | **W** (2 usages) | Comptes GM (generaux) |
| compteurs________cpt | **W** (1 usages) | Comptes GM (generaux) |
| trf_transfert_new | **W** (1 usages) |  |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (20 taches)

Traitements internes.

---

#### <a id="t1"></a>96 - Sales [[ECRAN]](#ecran-t1)

**Role** : Tache d'orchestration : point d'entree du programme (20 sous-taches). Coordonne l'enchainement des traitements.
**Ecran** : 1313 x 744 DLU | [Voir mockup](#ecran-t1)

<details>
<summary>19 sous-taches directes</summary>

| Tache | Nom | Bloc |
|-------|-----|------|
| [96.1](#t2) | Produits **[[ECRAN]](#ecran-t2)** | Traitement |
| [96.1.1](#t3) | Affectation Auto | Traitement |
| [96.1.3](#t5) | Gratuite ? | Traitement |
| [96.1.5.3](#t12) | Affectation **[[ECRAN]](#ecran-t12)** | Traitement |
| [96.1.5.4](#t14) | Test reseau | Traitement |
| [96.1.5.7](#t18) | VRL | Traitement |
| [96.1.5.8](#t19) | ourcentage | Traitement |
| [96.2](#t23) | Dé-Affecition | Traitement |
| [96.5](#t26) | Test si cloture en cours v1 | Traitement |
| [96.5.1](#t27) | Blocage cloture v1 | Traitement |
| [96.6](#t28) | Deblocage cloture v1 | Traitement |
| [96.7](#t29) | garantie? | Traitement |
| [96.10](#t32) | Affectation Auto | Traitement |
| [96.11](#t33) | Services **[[ECRAN]](#ecran-t33)** | Traitement |
| [96.12](#t34) | Suppression ligne a 0 | Traitement |
| [96.1.5.6.2.1](#t46) | Supprime enregs non affectés | Traitement |
| [96.14](#t49) | Solde gift pass | Traitement |
| [96.5.2](#t60) | Blocage cloture v1 | Traitement |
| [96.15](#t63) | Deblocage cloture v1 | Traitement |

</details>

---

#### <a id="t2"></a>96.1 - Produits [[ECRAN]](#ecran-t2)

**Role** : Traitement : Produits.
**Ecran** : 901 x 598 DLU (Modal) | [Voir mockup](#ecran-t2)

---

#### <a id="t3"></a>96.1.1 - Affectation Auto

**Role** : Traitement : Affectation Auto.

---

#### <a id="t5"></a>96.1.3 - Gratuite ?

**Role** : Traitement : Gratuite ?.
**Variables liees** : DM (W0 gratuite ?)

---

#### <a id="t12"></a>96.1.5.3 - Affectation [[ECRAN]](#ecran-t12)

**Role** : Traitement : Affectation.
**Ecran** : 584 x 253 DLU | [Voir mockup](#ecran-t12)

---

#### <a id="t14"></a>96.1.5.4 - Test reseau

**Role** : Verification : Test reseau.
**Variables liees** : DE (W0 reseau)

---

#### <a id="t18"></a>96.1.5.7 - VRL

**Role** : Traitement interne.

---

#### <a id="t19"></a>96.1.5.8 - ourcentage

**Role** : Traitement : ourcentage.
**Variables liees** : CE (W0 Pourcentage reduction)

---

#### <a id="t23"></a>96.2 - Dé-Affecition

**Role** : Traitement : Dé-Affecition.

---

#### <a id="t26"></a>96.5 - Test si cloture en cours v1

**Role** : Verification : Test si cloture en cours v1.
**Variables liees** : T (W0 Cloture en cours)

---

#### <a id="t27"></a>96.5.1 - Blocage cloture v1

**Role** : Traitement : Blocage cloture v1.
**Variables liees** : T (W0 Cloture en cours)

---

#### <a id="t28"></a>96.6 - Deblocage cloture v1

**Role** : Traitement : Deblocage cloture v1.
**Variables liees** : T (W0 Cloture en cours)

---

#### <a id="t29"></a>96.7 - garantie?

**Role** : Traitement : garantie?.

---

#### <a id="t32"></a>96.10 - Affectation Auto

**Role** : Traitement : Affectation Auto.

---

#### <a id="t33"></a>96.11 - Services [[ECRAN]](#ecran-t33)

**Role** : Traitement : Services.
**Ecran** : 157 x 600 DLU (Modal) | [Voir mockup](#ecran-t33)

---

#### <a id="t34"></a>96.12 - Suppression ligne a 0

**Role** : Traitement : Suppression ligne a 0.
**Variables liees** : EQ (V Nbre de Ligne Saisies), ER (v Nbre ligne de reglement Saisi), ES (V.Num ligne vente), ET (V.Total reglement ligne), EU (V.Multi reglement ligne)

---

#### <a id="t46"></a>96.1.5.6.2.1 - Supprime enregs non affectés

**Role** : Traitement : Supprime enregs non affectés.

---

#### <a id="t49"></a>96.14 - Solde gift pass

**Role** : Consultation/chargement : Solde gift pass.
**Variables liees** : D (P0 solde compte), I (P0 date solde), FO (V0.montant - Gift pass), FP (V0.Solde gift pass)

---

#### <a id="t60"></a>96.5.2 - Blocage cloture v1

**Role** : Traitement : Blocage cloture v1.
**Variables liees** : T (W0 Cloture en cours)

---

#### <a id="t63"></a>96.15 - Deblocage cloture v1

**Role** : Traitement : Deblocage cloture v1.
**Variables liees** : T (W0 Cloture en cours)


### 3.2 Initialisation (4 taches)

Reinitialisation d'etats et variables de travail.

---

#### <a id="t4"></a>96.1.2 - RAZ 269

**Role** : Reinitialisation : RAZ 269.

---

#### <a id="t9"></a>96.1.5.1 - RAZ 269

**Role** : Reinitialisation : RAZ 269.

---

#### <a id="t24"></a>96.3 - RAZ 269

**Role** : Reinitialisation : RAZ 269.

---

#### <a id="t30"></a>96.8 - RAZ 269

**Role** : Reinitialisation : RAZ 269.


### 3.3 Consultation (1 tache)

Ecrans de recherche et consultation.

---

#### <a id="t6"></a>96.1.3.1 - Recherche imputation/ssimput

**Role** : Traitement : Recherche imputation/ssimput.


### 3.4 Creation (4 taches)

Insertion de nouveaux enregistrements en base.

---

#### <a id="t7"></a>96.1.4 - Creation Tempo

**Role** : Creation d'enregistrement : Creation Tempo.
**Delegue a** : [Create logbook (IDE 81)](WEL-IDE-81.md)

---

#### <a id="t11"></a>96.1.5.2.1 - Creation

**Role** : Creation d'enregistrement : Creation.
**Delegue a** : [Create logbook (IDE 81)](WEL-IDE-81.md)

---

#### <a id="t13"></a>96.1.5.3.1 - Creation Enregistrement Transf [[ECRAN]](#ecran-t13)

**Role** : Creation d'enregistrement : Creation Enregistrement Transf.
**Ecran** : 672 x 58 DLU | [Voir mockup](#ecran-t13)
**Variables liees** : BK (W0 Sens du transfert Aller), BL (W0 Date du transfert Aller), BM (W0 Heure du transfert Aller), BN (W0 b.Date du transfert), BT (W0 Sens du transfert Retour)
**Delegue a** : [Create logbook (IDE 81)](WEL-IDE-81.md)

---

#### <a id="t21"></a>96.1.5.10 - Creation Tempo

**Role** : Creation d'enregistrement : Creation Tempo.
**Delegue a** : [Create logbook (IDE 81)](WEL-IDE-81.md)


### 3.5 Saisie (2 taches)

L'operateur saisit les donnees de la transaction via 2 ecrans (Ventes, VRL : Saisie identité).

---

#### <a id="t8"></a>96.1.5 - Ventes [[ECRAN]](#ecran-t8)

**Role** : Saisie des donnees : Ventes.
**Ecran** : 618 x 586 DLU (Modal) | [Voir mockup](#ecran-t8)
**Delegue a** : [Saisie Signature (IDE 82)](WEL-IDE-82.md), [Saisie Signature Validation (IDE 83)](WEL-IDE-83.md)

---

#### <a id="t25"></a>96.4 - VRL : Saisie identité [[ECRAN]](#ecran-t25)

**Role** : Saisie des donnees : VRL : Saisie identité.
**Ecran** : 1313 x 744 DLU | [Voir mockup](#ecran-t25)
**Variables liees** : R (W0 FIN SAISIE OD date), CA (W0 b.Saisie PAX), EQ (V Nbre de Ligne Saisies), S (Bouton FIN SAISIE OD)
**Delegue a** : [Saisie Signature (IDE 82)](WEL-IDE-82.md), [Saisie Signature Validation (IDE 83)](WEL-IDE-83.md)


### 3.6 Reglement (2 taches)

Gestion des moyens de paiement : 2 taches de reglement.

---

#### <a id="t10"></a>96.1.5.2 - Creation reglement

**Role** : Gestion du reglement : Creation reglement.
**Variables liees** : EJ (V.Reglement premier article), ER (v Nbre ligne de reglement Saisi), ET (V.Total reglement ligne), EU (V.Multi reglement ligne)
**Delegue a** : [Zoom Mode paiement (IDE 110)](WEL-IDE-110.md)

---

#### <a id="t35"></a>96.13 - Maj reglement

**Role** : Gestion du reglement : Maj reglement.
**Variables liees** : EJ (V.Reglement premier article), ER (v Nbre ligne de reglement Saisi), ET (V.Total reglement ligne), EU (V.Multi reglement ligne)
**Delegue a** : [Zoom Mode paiement (IDE 110)](WEL-IDE-110.md)


### 3.7 Impression (1 tache)

Generation des documents et tickets.

---

#### <a id="t15"></a>96.1.5.5 - Increment Num. Ticket(VRL/VSL)

**Role** : Generation du document : Increment Num. Ticket(VRL/VSL).
**Variables liees** : EN (v.IncrémentTicket(VRL/VSL) OK), EO (v.NumeroTicket(VRL/VSL))


### 3.8 Transfert (4 taches)

Transfert de donnees entre modules.

---

#### <a id="t16"></a>96.1.5.6 - Type transfert

**Role** : Transfert de donnees : Type transfert.
**Variables liees** : X (W0.Type article), BK (W0 Sens du transfert Aller), BL (W0 Date du transfert Aller), BM (W0 Heure du transfert Aller), BN (W0 b.Date du transfert)

---

#### <a id="t17"></a>96.1.5.6.1 - Affiche Transfert A/R [[ECRAN]](#ecran-t17)

**Role** : Reinitialisation : Affiche Transfert A/R.
**Ecran** : 1127 x 450 DLU (MDI) | [Voir mockup](#ecran-t17)
**Variables liees** : BK (W0 Sens du transfert Aller), BL (W0 Date du transfert Aller), BM (W0 Heure du transfert Aller), BN (W0 b.Date du transfert), BT (W0 Sens du transfert Retour)

---

#### <a id="t31"></a>96.9 - Raz Affectation Transfert

**Role** : Reinitialisation : Raz Affectation Transfert.
**Variables liees** : BK (W0 Sens du transfert Aller), BL (W0 Date du transfert Aller), BM (W0 Heure du transfert Aller), BN (W0 b.Date du transfert), BT (W0 Sens du transfert Retour)

---

#### <a id="t45"></a>96.1.5.6.2 - Affectation PAX / Transfert [[ECRAN]](#ecran-t45)

**Role** : Transfert de donnees : Affectation PAX / Transfert.
**Ecran** : 1313 x 744 DLU | [Voir mockup](#ecran-t45)
**Variables liees** : BK (W0 Sens du transfert Aller), BL (W0 Date du transfert Aller), BM (W0 Heure du transfert Aller), BN (W0 b.Date du transfert), BT (W0 Sens du transfert Retour)


### 3.9 Calcul (3 taches)

Calculs metier : montants, stocks, compteurs.

---

#### <a id="t20"></a>96.1.5.9 - Compte Enregs affectés

**Role** : Traitement : Compte Enregs affectés.
**Variables liees** : D (P0 solde compte), H (P0 etat compte), DX (W0 Compte garanti)

---

#### <a id="t22"></a>96.1.5.11 - Debloque compte

**Role** : Traitement : Debloque compte.
**Variables liees** : D (P0 solde compte), H (P0 etat compte), DX (W0 Compte garanti)

---

#### <a id="t47"></a>96.1.5.6.2.2 - Compte Enregs affectés

**Role** : Traitement : Compte Enregs affectés.
**Variables liees** : D (P0 solde compte), H (P0 etat compte), DX (W0 Compte garanti)


## 5. REGLES METIER

3 regles identifiees:

### Saisie (3 regles)

#### <a id="rm-RM-001"></a>[RM-001] Si V0.Fichier sans chemin [FN] est nul, choix conditionnel selon [AC] (valeur 'VSL')

| Element | Detail |
|---------|--------|
| **Condition** | `V0.Fichier sans chemin [FN]=0` |
| **Si vrai** | IF([AC]='VSL' |
| **Si faux** | P0.Date debut sejour [M],Date()),W0 Motif annulation [CK]) |
| **Variables** | M (P0.Date debut sejour), CK (W0 Motif annulation), FN (V0.Fichier sans chemin) |
| **Expression source** | Expression 1 : `IF(V0.Fichier sans chemin [FN]=0,IF([AC]='VSL',P0.Date debut` |
| **Exemple** | Si V0.Fichier sans chemin [FN]=0 â†’ IF([AC]='VSL'. Sinon â†’ P0.Date debut sejour [M],Date()),W0 Motif annulation [CK]) |
| **Impact** | Bloc Saisie |

#### <a id="rm-RM-002"></a>[RM-002] Traitement si W0 Commune [CQ] est renseigne

| Element | Detail |
|---------|--------|
| **Condition** | `W0 Commune [CQ]<>''` |
| **Si vrai** | RTrim (W0 Nom de la rue [CP])&Fill (' ' |
| **Si faux** | Len (RTrim (W0 Nom de la rue [CP]))-1)&RTrim (W0 Commune [CQ])&' '&W0 CP [CR],Trim(P0 Nom & prenom [K])) |
| **Variables** | K (P0 Nom & prenom), CM (W0 Nom), CP (W0 Nom de la rue), CQ (W0 Commune), CR (W0 CP) |
| **Expression source** | Expression 42 : `IF(W0 Commune [CQ]<>'',RTrim (W0 Nom de la rue [CP])&Fill ('` |
| **Exemple** | Si W0 Commune [CQ]<>'' â†’ RTrim (W0 Nom de la rue [CP])&Fill (' ' |
| **Impact** | Bloc Saisie |

#### <a id="rm-RM-003"></a>[RM-003] Si V.Num ligne vente [ES] alors V.MOP TPE [EV] sinon VG43)

| Element | Detail |
|---------|--------|
| **Condition** | `V.Num ligne vente [ES]` |
| **Si vrai** | V.MOP TPE [EV] |
| **Si faux** | VG43) |
| **Variables** | ES (V.Num ligne vente), EV (V.MOP TPE) |
| **Expression source** | Expression 44 : `IF(V.Num ligne vente [ES],V.MOP TPE [EV],VG43)` |
| **Exemple** | Si V.Num ligne vente [ES] â†’ V.MOP TPE [EV]. Sinon â†’ VG43) |
| **Impact** | Bloc Saisie |

## 6. CONTEXTE

- **Appele par**: [Lancement ventes (IDE 95)](WEL-IDE-95.md)
- **Appelle**: 6 programmes | **Tables**: 25 (W:7 R:11 L:15) | **Taches**: 41 | **Expressions**: 112

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (7 / 41)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 96 | 96 | Sales | Type0 | 1313 | 744 | Traitement |
| 2 | 96.1 | 96.1 | Produits | Modal | 901 | 598 | Traitement |
| 3 | 96.1.5 | 96.1.5 | Ventes | Modal | 618 | 586 | Saisie |
| 4 | 96.1.5.6.2 | 96.1.5.6.1 | Affiche Transfert A/R | MDI | 1127 | 450 | Transfert |
| 5 | 96.4 | 96.4 | VRL : Saisie identité | Type0 | 1313 | 744 | Saisie |
| 6 | 96.12 | 96.11 | Services | Modal | 157 | 600 | Traitement |
| 7 | 96.1.5.6.1 | 96.1.5.6.2 | Affectation PAX / Transfert | Type0 | 1313 | 744 | Transfert |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>96 - Sales
**Tache** : [96](#t1) | **Type** : Type0 | **Dimensions** : 1313 x 744 DLU
**Bloc** : Traitement | **Titre IDE** : Sales

<!-- FORM-DATA:
{
    "width":  1313,
    "vFactor":  100,
    "type":  "Type0",
    "hFactor":  100,
    "controls":  [
                     {
                         "x":  183,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  1130,
                         "fmt":  "",
                         "name":  "",
                         "h":  66,
                         "color":  "212",
                         "text":  "SALES",
                         "parent":  null
                     },
                     {
                         "x":  1138,
                         "type":  "label",
                         "var":  "",
                         "y":  68,
                         "w":  175,
                         "fmt":  "",
                         "name":  "",
                         "h":  675,
                         "color":  "212",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  11,
                         "type":  "label",
                         "var":  "",
                         "y":  85,
                         "w":  53,
                         "fmt":  "",
                         "name":  "",
                         "h":  43,
                         "color":  "",
                         "text":  "QTY",
                         "parent":  null
                     },
                     {
                         "x":  12,
                         "type":  "label",
                         "var":  "",
                         "y":  171,
                         "w":  51,
                         "fmt":  "",
                         "name":  "0",
                         "h":  41,
                         "color":  "219",
                         "text":  "0",
                         "parent":  null
                     },
                     {
                         "x":  12,
                         "type":  "label",
                         "var":  "",
                         "y":  217,
                         "w":  51,
                         "fmt":  "",
                         "name":  "1",
                         "h":  41,
                         "color":  "219",
                         "text":  "1",
                         "parent":  null
                     },
                     {
                         "x":  12,
                         "type":  "label",
                         "var":  "",
                         "y":  263,
                         "w":  51,
                         "fmt":  "",
                         "name":  "2",
                         "h":  41,
                         "color":  "219",
                         "text":  "2",
                         "parent":  null
                     },
                     {
                         "x":  12,
                         "type":  "label",
                         "var":  "",
                         "y":  309,
                         "w":  51,
                         "fmt":  "",
                         "name":  "3",
                         "h":  41,
                         "color":  "219",
                         "text":  "3",
                         "parent":  null
                     },
                     {
                         "x":  12,
                         "type":  "label",
                         "var":  "",
                         "y":  355,
                         "w":  51,
                         "fmt":  "",
                         "name":  "4",
                         "h":  41,
                         "color":  "219",
                         "text":  "4",
                         "parent":  null
                     },
                     {
                         "x":  12,
                         "type":  "label",
                         "var":  "",
                         "y":  401,
                         "w":  51,
                         "fmt":  "",
                         "name":  "5",
                         "h":  41,
                         "color":  "219",
                         "text":  "5",
                         "parent":  null
                     },
                     {
                         "x":  12,
                         "type":  "label",
                         "var":  "",
                         "y":  447,
                         "w":  51,
                         "fmt":  "",
                         "name":  "6",
                         "h":  41,
                         "color":  "219",
                         "text":  "6",
                         "parent":  null
                     },
                     {
                         "x":  12,
                         "type":  "label",
                         "var":  "",
                         "y":  493,
                         "w":  51,
                         "fmt":  "",
                         "name":  "7",
                         "h":  41,
                         "color":  "219",
                         "text":  "7",
                         "parent":  null
                     },
                     {
                         "x":  12,
                         "type":  "label",
                         "var":  "",
                         "y":  539,
                         "w":  51,
                         "fmt":  "",
                         "name":  "8",
                         "h":  41,
                         "color":  "219",
                         "text":  "8",
                         "parent":  null
                     },
                     {
                         "x":  12,
                         "type":  "label",
                         "var":  "",
                         "y":  585,
                         "w":  51,
                         "fmt":  "",
                         "name":  "9",
                         "h":  41,
                         "color":  "219",
                         "text":  "9",
                         "parent":  null
                     },
                     {
                         "x":  12,
                         "type":  "label",
                         "var":  "",
                         "y":  631,
                         "w":  51,
                         "fmt":  "",
                         "name":  "CLEAR",
                         "h":  41,
                         "color":  "219",
                         "text":  "Clear",
                         "parent":  null
                     },
                     {
                         "x":  12,
                         "type":  "edit",
                         "var":  "",
                         "y":  127,
                         "w":  51,
                         "fmt":  "",
                         "name":  "QTE",
                         "h":  41,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  67,
                         "type":  "subform",
                         "var":  "",
                         "y":  84,
                         "w":  162,
                         "fmt":  "",
                         "name":  "Service/Produits",
                         "h":  608,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  1,
                         "type":  "image",
                         "var":  "",
                         "y":  0,
                         "w":  173,
                         "fmt":  "",
                         "name":  "Bouton ABANDON",
                         "h":  66,
                         "color":  "226",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  1146,
                         "type":  "edit",
                         "var":  "",
                         "y":  77,
                         "w":  158,
                         "fmt":  "30",
                         "name":  "Bouton FIN SAISIE OD",
                         "h":  79,
                         "color":  "214",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  1146,
                         "type":  "edit",
                         "var":  "",
                         "y":  166,
                         "w":  158,
                         "fmt":  "30",
                         "name":  "IDENTITY",
                         "h":  79,
                         "color":  "214",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  231,
                         "type":  "subform",
                         "var":  "",
                         "y":  82,
                         "w":  903,
                         "fmt":  "",
                         "name":  "Produits",
                         "h":  653,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "96",
    "height":  744
}
-->

<details>
<summary><strong>Champs : 3 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 12,127 | QTE | - | edit |
| 1146,77 | Bouton FIN SAISIE OD | - | edit |
| 1146,166 | IDENTITY | - | edit |

</details>

---

#### <a id="ecran-t2"></a>96.1 - Produits
**Tache** : [96.1](#t2) | **Type** : Modal | **Dimensions** : 901 x 598 DLU
**Bloc** : Traitement | **Titre IDE** : Produits

<!-- FORM-DATA:
{
    "width":  901,
    "vFactor":  8,
    "type":  "Modal",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  220,
                         "fmt":  "",
                         "name":  "",
                         "h":  43,
                         "color":  "",
                         "text":  "PRODUCTS",
                         "parent":  null
                     },
                     {
                         "x":  2,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "",
                         "w":  217,
                         "y":  42,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  46,
                         "h":  554,
                         "cols":  [
                                      {
                                          "title":  "",
                                          "layer":  1,
                                          "w":  210
                                      }
                                  ],
                         "rows":  1
                     },
                     {
                         "x":  219,
                         "type":  "button",
                         "var":  "",
                         "y":  0,
                         "w":  56,
                         "fmt":  "",
                         "name":  "",
                         "h":  299,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  279,
                         "type":  "subform",
                         "var":  "",
                         "y":  0,
                         "w":  620,
                         "fmt":  "",
                         "name":  "Ventes",
                         "h":  598,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  6,
                         "type":  "edit",
                         "var":  "",
                         "y":  45,
                         "w":  138,
                         "fmt":  "",
                         "name":  "BT_ARTICLE",
                         "h":  40,
                         "color":  "214",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  144,
                         "type":  "edit",
                         "var":  "",
                         "y":  45,
                         "w":  73,
                         "fmt":  "## ### ### ###.###Z",
                         "name":  "BT_PRIX",
                         "h":  40,
                         "color":  "214",
                         "text":  "",
                         "parent":  4
                     },
                     {
                         "x":  219,
                         "type":  "button",
                         "var":  "",
                         "y":  298,
                         "w":  56,
                         "fmt":  "",
                         "name":  "",
                         "h":  298,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "96.1",
    "height":  598
}
-->

<details>
<summary><strong>Champs : 2 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 6,45 | BT_ARTICLE | - | edit |
| 144,45 | BT_PRIX | - | edit |

</details>

<details>
<summary><strong>Boutons : 2 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| (sans nom) | 219,0 | Action declenchee |
| (sans nom) | 219,298 | Action declenchee |

</details>

---

#### <a id="ecran-t8"></a>96.1.5 - Ventes
**Tache** : [96.1.5](#t8) | **Type** : Modal | **Dimensions** : 618 x 586 DLU
**Bloc** : Saisie | **Titre IDE** : Ventes

<!-- FORM-DATA:
{
    "width":  618,
    "vFactor":  8,
    "type":  "Modal",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  5,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  147,
                         "fmt":  "",
                         "name":  "",
                         "h":  43,
                         "color":  "",
                         "text":  "PRODUCTS",
                         "parent":  null
                     },
                     {
                         "x":  150,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  52,
                         "fmt":  "",
                         "name":  "",
                         "h":  43,
                         "color":  "",
                         "text":  "QTY",
                         "parent":  null
                     },
                     {
                         "x":  201,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  145,
                         "fmt":  "",
                         "name":  "",
                         "h":  43,
                         "color":  "",
                         "text":  "UNIT PRICE",
                         "parent":  null
                     },
                     {
                         "x":  344,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  60,
                         "fmt":  "",
                         "name":  "",
                         "h":  43,
                         "color":  "",
                         "text":  "- %",
                         "parent":  null
                     },
                     {
                         "x":  403,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  156,
                         "fmt":  "",
                         "name":  "",
                         "h":  43,
                         "color":  "",
                         "text":  "PRICE",
                         "parent":  null
                     },
                     {
                         "x":  285,
                         "type":  "label",
                         "var":  "",
                         "y":  325,
                         "w":  52,
                         "fmt":  "",
                         "name":  "",
                         "h":  38,
                         "color":  "",
                         "text":  "TOTAL",
                         "parent":  null
                     },
                     {
                         "x":  202,
                         "type":  "label",
                         "var":  "",
                         "y":  383,
                         "w":  135,
                         "fmt":  "",
                         "name":  "",
                         "h":  38,
                         "color":  "",
                         "text":  "Payment mode",
                         "parent":  null
                     },
                     {
                         "x":  12,
                         "type":  "line",
                         "var":  "",
                         "y":  435,
                         "w":  599,
                         "fmt":  "",
                         "name":  "",
                         "h":  0,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  79,
                         "type":  "label",
                         "var":  "",
                         "y":  456,
                         "w":  135,
                         "fmt":  "",
                         "name":  "",
                         "h":  44,
                         "color":  "",
                         "text":  "Discount reason",
                         "parent":  null
                     },
                     {
                         "x":  79,
                         "type":  "label",
                         "var":  "",
                         "y":  512,
                         "w":  135,
                         "fmt":  "",
                         "name":  "",
                         "h":  65,
                         "color":  "",
                         "text":  "Comment",
                         "parent":  null
                     },
                     {
                         "x":  6,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "",
                         "w":  551,
                         "y":  42,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  46,
                         "h":  278,
                         "cols":  [
                                      {
                                          "title":  "",
                                          "layer":  1,
                                          "w":  143
                                      },
                                      {
                                          "title":  "",
                                          "layer":  2,
                                          "w":  50
                                      },
                                      {
                                          "title":  "",
                                          "layer":  3,
                                          "w":  144
                                      },
                                      {
                                          "title":  "",
                                          "layer":  4,
                                          "w":  58
                                      },
                                      {
                                          "title":  "",
                                          "layer":  5,
                                          "w":  151
                                      }
                                  ],
                         "rows":  5
                     },
                     {
                         "x":  556,
                         "type":  "button",
                         "var":  "",
                         "y":  0,
                         "w":  56,
                         "fmt":  "",
                         "name":  "",
                         "h":  161,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  9,
                         "type":  "edit",
                         "var":  "",
                         "y":  45,
                         "w":  138,
                         "fmt":  "",
                         "name":  "BOUTON_ARTICLE",
                         "h":  38,
                         "color":  "220",
                         "text":  "",
                         "parent":  15
                     },
                     {
                         "x":  154,
                         "type":  "edit",
                         "var":  "",
                         "y":  46,
                         "w":  43,
                         "fmt":  "3Z",
                         "name":  "sod_quantite",
                         "h":  38,
                         "color":  "",
                         "text":  "",
                         "parent":  15
                     },
                     {
                         "x":  205,
                         "type":  "edit",
                         "var":  "",
                         "y":  46,
                         "w":  134,
                         "fmt":  "N## ### ### ###.###Z",
                         "name":  "sod_prix_unitaire",
                         "h":  38,
                         "color":  "",
                         "text":  "",
                         "parent":  15
                     },
                     {
                         "x":  350,
                         "type":  "edit",
                         "var":  "",
                         "y":  46,
                         "w":  48,
                         "fmt":  "3%",
                         "name":  "sod_pourcentage_reduction",
                         "h":  38,
                         "color":  "",
                         "text":  "",
                         "parent":  15
                     },
                     {
                         "x":  404,
                         "type":  "edit",
                         "var":  "",
                         "y":  46,
                         "w":  146,
                         "fmt":  "N## ### ### ###.###Z",
                         "name":  "sod_montant_0001",
                         "h":  38,
                         "color":  "",
                         "text":  "",
                         "parent":  15
                     },
                     {
                         "x":  556,
                         "type":  "button",
                         "var":  "",
                         "y":  159,
                         "w":  56,
                         "fmt":  "",
                         "name":  "",
                         "h":  161,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  347,
                         "type":  "edit",
                         "var":  "",
                         "y":  327,
                         "w":  209,
                         "fmt":  "N## ### ### ###.###Z",
                         "name":  "W0 montant",
                         "h":  44,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  347,
                         "type":  "edit",
                         "var":  "",
                         "y":  383,
                         "w":  209,
                         "fmt":  "",
                         "name":  "V1.Mode paiement_0001",
                         "h":  44,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  224,
                         "type":  "combobox",
                         "var":  "",
                         "y":  460,
                         "w":  388,
                         "fmt":  "",
                         "name":  "sod_code_reduction",
                         "h":  20,
                         "color":  "",
                         "text":  "SANS",
                         "parent":  null
                     },
                     {
                         "x":  224,
                         "type":  "edit",
                         "var":  "",
                         "y":  512,
                         "w":  388,
                         "fmt":  "",
                         "name":  "sod_commentaire_0001",
                         "h":  65,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "96.1.5",
    "height":  586
}
-->

<details>
<summary><strong>Champs : 9 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 9,45 | BOUTON_ARTICLE | - | edit |
| 154,46 | sod_quantite | - | edit |
| 205,46 | sod_prix_unitaire | - | edit |
| 350,46 | sod_pourcentage_reduction | - | edit |
| 404,46 | sod_montant_0001 | - | edit |
| 347,327 | W0 montant | - | edit |
| 347,383 | V1.Mode paiement_0001 | - | edit |
| 224,460 | sod_code_reduction | - | combobox |
| 224,512 | sod_commentaire_0001 | - | edit |

</details>

<details>
<summary><strong>Boutons : 2 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| (sans nom) | 556,0 | Action declenchee |
| (sans nom) | 556,159 | Action declenchee |

</details>

---

#### <a id="ecran-t17"></a>96.1.5.6.2 - Affiche Transfert A/R
**Tache** : [96.1.5.6.1](#t17) | **Type** : MDI | **Dimensions** : 1127 x 450 DLU
**Bloc** : Transfert | **Titre IDE** : Affiche Transfert A/R

<!-- FORM-DATA:
{
    "width":  1127,
    "vFactor":  100,
    "type":  "MDI",
    "hFactor":  100,
    "controls":  [
                     {
                         "x":  4,
                         "type":  "label",
                         "var":  "",
                         "y":  16,
                         "w":  556,
                         "fmt":  "",
                         "name":  "",
                         "h":  44,
                         "color":  "",
                         "text":  "ARRIVING",
                         "parent":  null
                     },
                     {
                         "x":  568,
                         "type":  "label",
                         "var":  "",
                         "y":  16,
                         "w":  556,
                         "fmt":  "",
                         "name":  "",
                         "h":  44,
                         "color":  "",
                         "text":  "DEPARTING",
                         "parent":  null
                     },
                     {
                         "x":  569,
                         "type":  "label",
                         "var":  "",
                         "y":  57,
                         "w":  555,
                         "fmt":  "",
                         "name":  "",
                         "h":  380,
                         "color":  "220",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  5,
                         "type":  "label",
                         "var":  "",
                         "y":  58,
                         "w":  555,
                         "fmt":  "",
                         "name":  "",
                         "h":  380,
                         "color":  "220",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  590,
                         "type":  "label",
                         "var":  "",
                         "y":  105,
                         "w":  101,
                         "fmt":  "",
                         "name":  "",
                         "h":  44,
                         "color":  "",
                         "text":  "Transfer date",
                         "parent":  null
                     },
                     {
                         "x":  824,
                         "type":  "label",
                         "var":  "",
                         "y":  105,
                         "w":  163,
                         "fmt":  "",
                         "name":  "",
                         "h":  44,
                         "color":  "",
                         "text":  "Airport/Station Code",
                         "parent":  null
                     },
                     {
                         "x":  21,
                         "type":  "label",
                         "var":  "",
                         "y":  106,
                         "w":  101,
                         "fmt":  "",
                         "name":  "",
                         "h":  44,
                         "color":  "",
                         "text":  "Transfer date",
                         "parent":  null
                     },
                     {
                         "x":  260,
                         "type":  "label",
                         "var":  "",
                         "y":  106,
                         "w":  163,
                         "fmt":  "",
                         "name":  "",
                         "h":  44,
                         "color":  "",
                         "text":  "Airport/Station Code",
                         "parent":  null
                     },
                     {
                         "x":  590,
                         "type":  "label",
                         "var":  "",
                         "y":  187,
                         "w":  101,
                         "fmt":  "",
                         "name":  "",
                         "h":  44,
                         "color":  "",
                         "text":  "Transfer time",
                         "parent":  null
                     },
                     {
                         "x":  824,
                         "type":  "label",
                         "var":  "",
                         "y":  187,
                         "w":  163,
                         "fmt":  "",
                         "name":  "",
                         "h":  44,
                         "color":  "",
                         "text":  "Flight/Train number",
                         "parent":  null
                     },
                     {
                         "x":  21,
                         "type":  "label",
                         "var":  "",
                         "y":  188,
                         "w":  101,
                         "fmt":  "",
                         "name":  "",
                         "h":  44,
                         "color":  "",
                         "text":  "Transfer time",
                         "parent":  null
                     },
                     {
                         "x":  260,
                         "type":  "label",
                         "var":  "",
                         "y":  188,
                         "w":  163,
                         "fmt":  "",
                         "name":  "",
                         "h":  44,
                         "color":  "",
                         "text":  "Flight/Train number",
                         "parent":  null
                     },
                     {
                         "x":  590,
                         "type":  "label",
                         "var":  "",
                         "y":  269,
                         "w":  101,
                         "fmt":  "",
                         "name":  "",
                         "h":  44,
                         "color":  "",
                         "text":  "Type Endroit",
                         "parent":  null
                     },
                     {
                         "x":  824,
                         "type":  "label",
                         "var":  "",
                         "y":  269,
                         "w":  163,
                         "fmt":  "",
                         "name":  "",
                         "h":  44,
                         "color":  "",
                         "text":  "Compagnie",
                         "parent":  null
                     },
                     {
                         "x":  21,
                         "type":  "label",
                         "var":  "",
                         "y":  270,
                         "w":  101,
                         "fmt":  "",
                         "name":  "",
                         "h":  44,
                         "color":  "",
                         "text":  "Type Endroit",
                         "parent":  null
                     },
                     {
                         "x":  260,
                         "type":  "label",
                         "var":  "",
                         "y":  270,
                         "w":  163,
                         "fmt":  "",
                         "name":  "",
                         "h":  44,
                         "color":  "",
                         "text":  "Compagnie",
                         "parent":  null
                     },
                     {
                         "x":  590,
                         "type":  "label",
                         "var":  "",
                         "y":  351,
                         "w":  101,
                         "fmt":  "",
                         "name":  "",
                         "h":  44,
                         "color":  "",
                         "text":  "Comment",
                         "parent":  null
                     },
                     {
                         "x":  21,
                         "type":  "label",
                         "var":  "",
                         "y":  352,
                         "w":  101,
                         "fmt":  "",
                         "name":  "",
                         "h":  44,
                         "color":  "",
                         "text":  "Comment",
                         "parent":  null
                     },
                     {
                         "x":  700,
                         "type":  "edit",
                         "var":  "",
                         "y":  105,
                         "w":  101,
                         "fmt":  "##/##/####Z",
                         "name":  "Date_transfert_aller",
                         "h":  44,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  989,
                         "type":  "edit",
                         "var":  "",
                         "y":  105,
                         "w":  130,
                         "fmt":  "",
                         "name":  "W1 Code Aeroport/Gare Ret_0001",
                         "h":  44,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  136,
                         "type":  "edit",
                         "var":  "",
                         "y":  106,
                         "w":  101,
                         "fmt":  "##/##/####Z",
                         "name":  "Date_transfert_aller",
                         "h":  44,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  425,
                         "type":  "edit",
                         "var":  "",
                         "y":  106,
                         "w":  130,
                         "fmt":  "",
                         "name":  "Code Aeroport/Gare",
                         "h":  44,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  700,
                         "type":  "edit",
                         "var":  "",
                         "y":  187,
                         "w":  101,
                         "fmt":  "",
                         "name":  "W1 Heure transfert Retour_0001",
                         "h":  44,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  989,
                         "type":  "edit",
                         "var":  "",
                         "y":  187,
                         "w":  130,
                         "fmt":  "",
                         "name":  "W1 Num Vol/Train Retour_0001",
                         "h":  44,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  136,
                         "type":  "edit",
                         "var":  "",
                         "y":  188,
                         "w":  101,
                         "fmt":  "",
                         "name":  "Heure transfert",
                         "h":  44,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  425,
                         "type":  "edit",
                         "var":  "",
                         "y":  188,
                         "w":  130,
                         "fmt":  "",
                         "name":  "Num Vol/Train",
                         "h":  44,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  989,
                         "type":  "edit",
                         "var":  "",
                         "y":  269,
                         "w":  130,
                         "fmt":  "",
                         "name":  "W1 Compagnie Retour_0001",
                         "h":  44,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  425,
                         "type":  "edit",
                         "var":  "",
                         "y":  270,
                         "w":  130,
                         "fmt":  "",
                         "name":  "Compagnie",
                         "h":  44,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  700,
                         "type":  "combobox",
                         "var":  "",
                         "y":  272,
                         "w":  119,
                         "fmt":  "",
                         "name":  "W1 Type Endroit Retour_0001",
                         "h":  20,
                         "color":  "",
                         "text":  "TR,PL",
                         "parent":  null
                     },
                     {
                         "x":  136,
                         "type":  "combobox",
                         "var":  "",
                         "y":  273,
                         "w":  119,
                         "fmt":  "",
                         "name":  "Type Endroit Aller",
                         "h":  20,
                         "color":  "",
                         "text":  "TR,PL",
                         "parent":  null
                     },
                     {
                         "x":  700,
                         "type":  "edit",
                         "var":  "",
                         "y":  351,
                         "w":  419,
                         "fmt":  "",
                         "name":  "W1 Commentaire Retour_0001",
                         "h":  44,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  136,
                         "type":  "edit",
                         "var":  "",
                         "y":  352,
                         "w":  419,
                         "fmt":  "",
                         "name":  "Commentaire Aller",
                         "h":  44,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "96.1.5.6.2",
    "height":  450
}
-->

<details>
<summary><strong>Champs : 14 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 700,105 | Date_transfert_aller | - | edit |
| 989,105 | W1 Code Aeroport/Gare Ret_0001 | - | edit |
| 136,106 | Date_transfert_aller | - | edit |
| 425,106 | Code Aeroport/Gare | - | edit |
| 700,187 | W1 Heure transfert Retour_0001 | - | edit |
| 989,187 | W1 Num Vol/Train Retour_0001 | - | edit |
| 136,188 | Heure transfert | - | edit |
| 425,188 | Num Vol/Train | - | edit |
| 989,269 | W1 Compagnie Retour_0001 | - | edit |
| 425,270 | Compagnie | - | edit |
| 700,272 | W1 Type Endroit Retour_0001 | - | combobox |
| 136,273 | Type Endroit Aller | - | combobox |
| 700,351 | W1 Commentaire Retour_0001 | - | edit |
| 136,352 | Commentaire Aller | - | edit |

</details>

---

#### <a id="ecran-t25"></a>96.4 - VRL : Saisie identité
**Tache** : [96.4](#t25) | **Type** : Type0 | **Dimensions** : 1313 x 744 DLU
**Bloc** : Saisie | **Titre IDE** : VRL : Saisie identité

<!-- FORM-DATA:
{
    "width":  1313,
    "vFactor":  8,
    "type":  "Type0",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  182,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  1130,
                         "fmt":  "",
                         "name":  "",
                         "h":  66,
                         "color":  "212",
                         "text":  "VRL : ENTER IDENTITY",
                         "parent":  null
                     },
                     {
                         "x":  1138,
                         "type":  "label",
                         "var":  "",
                         "y":  69,
                         "w":  175,
                         "fmt":  "",
                         "name":  "",
                         "h":  675,
                         "color":  "212",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  381,
                         "type":  "label",
                         "var":  "",
                         "y":  201,
                         "w":  35,
                         "fmt":  "",
                         "name":  "",
                         "h":  36,
                         "color":  "",
                         "text":  "Title",
                         "parent":  null
                     },
                     {
                         "x":  285,
                         "type":  "label",
                         "var":  "",
                         "y":  252,
                         "w":  131,
                         "fmt":  "",
                         "name":  "",
                         "h":  44,
                         "color":  "",
                         "text":  "Last name",
                         "parent":  null
                     },
                     {
                         "x":  279,
                         "type":  "label",
                         "var":  "",
                         "y":  315,
                         "w":  137,
                         "fmt":  "",
                         "name":  "",
                         "h":  44,
                         "color":  "",
                         "text":  "First name",
                         "parent":  null
                     },
                     {
                         "x":  302,
                         "type":  "label",
                         "var":  "",
                         "y":  376,
                         "w":  114,
                         "fmt":  "",
                         "name":  "",
                         "h":  44,
                         "color":  "",
                         "text":  "Address",
                         "parent":  null
                     },
                     {
                         "x":  0,
                         "type":  "image",
                         "var":  "",
                         "y":  0,
                         "w":  175,
                         "fmt":  "",
                         "name":  "RETOUR",
                         "h":  66,
                         "color":  "226",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  1146,
                         "type":  "edit",
                         "var":  "",
                         "y":  78,
                         "w":  158,
                         "fmt":  "30",
                         "name":  "VALIDATE",
                         "h":  79,
                         "color":  "214",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  421,
                         "type":  "combobox",
                         "var":  "",
                         "y":  201,
                         "w":  140,
                         "fmt":  "",
                         "name":  "W2 Titre",
                         "h":  36,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  421,
                         "type":  "edit",
                         "var":  "",
                         "y":  254,
                         "w":  326,
                         "fmt":  "",
                         "name":  "W2 Nom",
                         "h":  44,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  421,
                         "type":  "edit",
                         "var":  "",
                         "y":  315,
                         "w":  326,
                         "fmt":  "",
                         "name":  "W2 Prenom",
                         "h":  44,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  421,
                         "type":  "edit",
                         "var":  "",
                         "y":  376,
                         "w":  117,
                         "fmt":  "",
                         "name":  "W2 Num rue",
                         "h":  44,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  544,
                         "type":  "edit",
                         "var":  "",
                         "y":  376,
                         "w":  316,
                         "fmt":  "",
                         "name":  "W2 Nom rue",
                         "h":  44,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  421,
                         "type":  "edit",
                         "var":  "",
                         "y":  437,
                         "w":  439,
                         "fmt":  "",
                         "name":  "W2 Commune",
                         "h":  44,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  421,
                         "type":  "edit",
                         "var":  "",
                         "y":  498,
                         "w":  117,
                         "fmt":  "",
                         "name":  "W2 CP",
                         "h":  44,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  544,
                         "type":  "edit",
                         "var":  "",
                         "y":  498,
                         "w":  316,
                         "fmt":  "",
                         "name":  "W2 Ville",
                         "h":  44,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "96.4",
    "height":  744
}
-->

<details>
<summary><strong>Champs : 9 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 1146,78 | VALIDATE | - | edit |
| 421,201 | W2 Titre | - | combobox |
| 421,254 | W2 Nom | - | edit |
| 421,315 | W2 Prenom | - | edit |
| 421,376 | W2 Num rue | - | edit |
| 544,376 | W2 Nom rue | - | edit |
| 421,437 | W2 Commune | - | edit |
| 421,498 | W2 CP | - | edit |
| 544,498 | W2 Ville | - | edit |

</details>

---

#### <a id="ecran-t33"></a>96.12 - Services
**Tache** : [96.11](#t33) | **Type** : Modal | **Dimensions** : 157 x 600 DLU
**Bloc** : Traitement | **Titre IDE** : Services

<!-- FORM-DATA:
{
    "width":  157,
    "vFactor":  8,
    "type":  "Modal",
    "hFactor":  4,
    "controls":  [
                     {
                         "x":  0,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  97,
                         "fmt":  "",
                         "name":  "",
                         "h":  43,
                         "color":  "",
                         "text":  "SERVICES",
                         "parent":  null
                     },
                     {
                         "x":  0,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "",
                         "w":  96,
                         "y":  42,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  46,
                         "h":  552,
                         "cols":  [
                                      {
                                          "title":  "",
                                          "layer":  1,
                                          "w":  91
                                      }
                                  ],
                         "rows":  1
                     },
                     {
                         "x":  96,
                         "type":  "button",
                         "var":  "",
                         "y":  0,
                         "w":  56,
                         "fmt":  "",
                         "name":  "",
                         "h":  299,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  4,
                         "type":  "edit",
                         "var":  "",
                         "y":  45,
                         "w":  88,
                         "fmt":  "",
                         "name":  "tab_code_alpha5",
                         "h":  38,
                         "color":  "",
                         "text":  "",
                         "parent":  3
                     },
                     {
                         "x":  96,
                         "type":  "button",
                         "var":  "",
                         "y":  298,
                         "w":  56,
                         "fmt":  "",
                         "name":  "",
                         "h":  298,
                         "color":  "",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "96.12",
    "height":  600
}
-->

<details>
<summary><strong>Champs : 1 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 4,45 | tab_code_alpha5 | - | edit |

</details>

<details>
<summary><strong>Boutons : 2 boutons</strong></summary>

| Bouton | Pos (x,y) | Action |
|--------|-----------|--------|
| (sans nom) | 96,0 | Action declenchee |
| (sans nom) | 96,298 | Action declenchee |

</details>

---

#### <a id="ecran-t45"></a>96.1.5.6.1 - Affectation PAX / Transfert
**Tache** : [96.1.5.6.2](#t45) | **Type** : Type0 | **Dimensions** : 1313 x 744 DLU
**Bloc** : Transfert | **Titre IDE** : Affectation PAX / Transfert

<!-- FORM-DATA:
{
    "width":  1313,
    "vFactor":  8,
    "type":  "Type0",
    "hFactor":  100,
    "controls":  [
                     {
                         "x":  140,
                         "type":  "table",
                         "var":  "",
                         "name":  "",
                         "titleH":  12,
                         "color":  "",
                         "w":  876,
                         "y":  155,
                         "fmt":  "",
                         "parent":  null,
                         "text":  "",
                         "rowH":  46,
                         "h":  508,
                         "cols":  [
                                      {
                                          "title":  "Choix",
                                          "layer":  1,
                                          "w":  60
                                      },
                                      {
                                          "title":  "Code GM",
                                          "layer":  2,
                                          "w":  92
                                      },
                                      {
                                          "title":  "Filiation",
                                          "layer":  3,
                                          "w":  114
                                      },
                                      {
                                          "title":  "Nom",
                                          "layer":  4,
                                          "w":  231
                                      },
                                      {
                                          "title":  "Prénom",
                                          "layer":  5,
                                          "w":  157
                                      },
                                      {
                                          "title":  "Début de séjour",
                                          "layer":  6,
                                          "w":  111
                                      },
                                      {
                                          "title":  "Fin de séjour",
                                          "layer":  7,
                                          "w":  106
                                      }
                                  ],
                         "rows":  7
                     },
                     {
                         "x":  182,
                         "type":  "label",
                         "var":  "",
                         "y":  0,
                         "w":  1130,
                         "fmt":  "",
                         "name":  "",
                         "h":  66,
                         "color":  "212",
                         "text":  "PAX ASSIGN",
                         "parent":  null
                     },
                     {
                         "x":  1137,
                         "type":  "label",
                         "var":  "",
                         "y":  69,
                         "w":  175,
                         "fmt":  "",
                         "name":  "",
                         "h":  675,
                         "color":  "212",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  139,
                         "type":  "label",
                         "var":  "",
                         "y":  113,
                         "w":  63,
                         "fmt":  "",
                         "name":  "",
                         "h":  43,
                         "color":  "",
                         "text":  "CHOIX",
                         "parent":  null
                     },
                     {
                         "x":  201,
                         "type":  "label",
                         "var":  "",
                         "y":  113,
                         "w":  94,
                         "fmt":  "",
                         "name":  "",
                         "h":  43,
                         "color":  "",
                         "text":  "GM CODE",
                         "parent":  null
                     },
                     {
                         "x":  294,
                         "type":  "label",
                         "var":  "",
                         "y":  113,
                         "w":  113,
                         "fmt":  "",
                         "name":  "",
                         "h":  43,
                         "color":  "",
                         "text":  "AFFILIATION",
                         "parent":  null
                     },
                     {
                         "x":  406,
                         "type":  "label",
                         "var":  "",
                         "y":  113,
                         "w":  234,
                         "fmt":  "",
                         "name":  "",
                         "h":  43,
                         "color":  "",
                         "text":  "LAST NAME",
                         "parent":  null
                     },
                     {
                         "x":  639,
                         "type":  "label",
                         "var":  "",
                         "y":  113,
                         "w":  157,
                         "fmt":  "",
                         "name":  "",
                         "h":  43,
                         "color":  "",
                         "text":  "FIRST NAME",
                         "parent":  null
                     },
                     {
                         "x":  794,
                         "type":  "label",
                         "var":  "",
                         "y":  113,
                         "w":  114,
                         "fmt":  "",
                         "name":  "",
                         "h":  43,
                         "color":  "",
                         "text":  "ARR",
                         "parent":  null
                     },
                     {
                         "x":  907,
                         "type":  "label",
                         "var":  "",
                         "y":  113,
                         "w":  110,
                         "fmt":  "",
                         "name":  "",
                         "h":  43,
                         "color":  "",
                         "text":  "DEP",
                         "parent":  null
                     },
                     {
                         "x":  0,
                         "type":  "image",
                         "var":  "",
                         "y":  0,
                         "w":  173,
                         "fmt":  "",
                         "name":  "RETOUR",
                         "h":  66,
                         "color":  "226",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  1145,
                         "type":  "edit",
                         "var":  "",
                         "y":  78,
                         "w":  158,
                         "fmt":  "30",
                         "name":  "SEARCH",
                         "h":  79,
                         "color":  "214",
                         "text":  "",
                         "parent":  null
                     },
                     {
                         "x":  144,
                         "type":  "edit",
                         "var":  "",
                         "y":  159,
                         "w":  56,
                         "fmt":  "U",
                         "name":  "CHECK",
                         "h":  38,
                         "color":  "",
                         "text":  "",
                         "parent":  6
                     },
                     {
                         "x":  204,
                         "type":  "edit",
                         "var":  "",
                         "y":  159,
                         "w":  86,
                         "fmt":  "",
                         "name":  "gmr_code_gm",
                         "h":  38,
                         "color":  "6",
                         "text":  "",
                         "parent":  6
                     },
                     {
                         "x":  297,
                         "type":  "edit",
                         "var":  "",
                         "y":  159,
                         "w":  108,
                         "fmt":  "",
                         "name":  "gmr_filiation_villag",
                         "h":  38,
                         "color":  "6",
                         "text":  "",
                         "parent":  6
                     },
                     {
                         "x":  410,
                         "type":  "edit",
                         "var":  "",
                         "y":  159,
                         "w":  223,
                         "fmt":  "",
                         "name":  "gmr_nom__30_",
                         "h":  38,
                         "color":  "6",
                         "text":  "",
                         "parent":  6
                     },
                     {
                         "x":  641,
                         "type":  "edit",
                         "var":  "",
                         "y":  159,
                         "w":  151,
                         "fmt":  "",
                         "name":  "gmr_prenom__8_",
                         "h":  38,
                         "color":  "6",
                         "text":  "",
                         "parent":  6
                     },
                     {
                         "x":  798,
                         "type":  "edit",
                         "var":  "",
                         "y":  159,
                         "w":  104,
                         "fmt":  "##/##/####",
                         "name":  "gmr_debut_sejour",
                         "h":  38,
                         "color":  "6",
                         "text":  "",
                         "parent":  6
                     },
                     {
                         "x":  908,
                         "type":  "edit",
                         "var":  "",
                         "y":  159,
                         "w":  105,
                         "fmt":  "##/##/####",
                         "name":  "gmr_fin_sejour",
                         "h":  38,
                         "color":  "6",
                         "text":  "",
                         "parent":  6
                     },
                     {
                         "x":  1145,
                         "type":  "edit",
                         "var":  "",
                         "y":  167,
                         "w":  158,
                         "fmt":  "30",
                         "name":  "VALIDATE",
                         "h":  79,
                         "color":  "214",
                         "text":  "",
                         "parent":  null
                     }
                 ],
    "taskId":  "96.1.5.6.1",
    "height":  744
}
-->

<details>
<summary><strong>Champs : 9 champs</strong></summary>

| Pos (x,y) | Nom | Variable | Type |
|-----------|-----|----------|------|
| 1145,78 | SEARCH | - | edit |
| 144,159 | CHECK | - | edit |
| 204,159 | gmr_code_gm | - | edit |
| 297,159 | gmr_filiation_villag | - | edit |
| 410,159 | gmr_nom__30_ | - | edit |
| 641,159 | gmr_prenom__8_ | - | edit |
| 798,159 | gmr_debut_sejour | - | edit |
| 908,159 | gmr_fin_sejour | - | edit |
| 1145,167 | VALIDATE | - | edit |

</details>

## 9. NAVIGATION

### 9.1 Enchainement des ecrans

```mermaid
flowchart TD
    START([Entree])
    style START fill:#3fb950
    VF1[96 Sales]
    style VF1 fill:#58a6ff
    VF2[96.1 Produits]
    style VF2 fill:#58a6ff
    VF8[96.1.5 Ventes]
    style VF8 fill:#58a6ff
    VF17[96.1.5.6.1 Affiche Transfert AR]
    style VF17 fill:#58a6ff
    VF25[96.4 VRL : Saisie identité]
    style VF25 fill:#58a6ff
    VF33[96.11 Services]
    style VF33 fill:#58a6ff
    VF45[96.1.5.6.2 Affectation PAX Tr...]
    style VF45 fill:#58a6ff
    EXT89[IDE 89 Traitement des ...]
    style EXT89 fill:#3fb950
    EXT17[IDE 17 Search client a...]
    style EXT17 fill:#3fb950
    EXT81[IDE 81 Create logbook]
    style EXT81 fill:#3fb950
    EXT82[IDE 82 Saisie Signature]
    style EXT82 fill:#3fb950
    EXT83[IDE 83 Saisie Signatur...]
    style EXT83 fill:#3fb950
    EXT110[IDE 110 Zoom Mode paie...]
    style EXT110 fill:#3fb950
    FIN([Sortie])
    style FIN fill:#f85149
    START --> VF1
    VF1 -->|Sous-programme| EXT89
    VF1 -->|Configuration impression| EXT17
    VF1 -->|Sous-programme| EXT81
    VF1 -->|Sous-programme| EXT82
    VF1 -->|Sous-programme| EXT83
    VF1 -->|Selection/consultation| EXT110
    EXT110 --> FIN
```

**Detail par enchainement :**

| Depuis | Action | Vers | Retour |
|--------|--------|------|--------|
| Sales | Sous-programme | [Traitement des mails (IDE 89)](WEL-IDE-89.md) | Retour ecran |
| Sales | Configuration impression | [Search client avec liste (IDE 17)](WEL-IDE-17.md) | Retour ecran |
| Sales | Sous-programme | [Create logbook (IDE 81)](WEL-IDE-81.md) | Retour ecran |
| Sales | Sous-programme | [Saisie Signature (IDE 82)](WEL-IDE-82.md) | Retour ecran |
| Sales | Sous-programme | [Saisie Signature Validation (IDE 83)](WEL-IDE-83.md) | Retour ecran |
| Sales | Selection/consultation | [Zoom Mode paiement (IDE 110)](WEL-IDE-110.md) | Retour ecran |

### 9.3 Structure hierarchique (41 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **96.1** | [**Sales** (96)](#t1) [mockup](#ecran-t1) | - | 1313x744 | Traitement |
| 96.1.1 | [Produits (96.1)](#t2) [mockup](#ecran-t2) | Modal | 901x598 | |
| 96.1.2 | [Affectation Auto (96.1.1)](#t3) | - | - | |
| 96.1.3 | [Gratuite ? (96.1.3)](#t5) | MDI | - | |
| 96.1.4 | [Affectation (96.1.5.3)](#t12) [mockup](#ecran-t12) | - | 584x253 | |
| 96.1.5 | [Test reseau (96.1.5.4)](#t14) | MDI | - | |
| 96.1.6 | [VRL (96.1.5.7)](#t18) | MDI | - | |
| 96.1.7 | [ourcentage (96.1.5.8)](#t19) | MDI | - | |
| 96.1.8 | [Dé-Affecition (96.2)](#t23) | - | - | |
| 96.1.9 | [Test si cloture en cours v1 (96.5)](#t26) | MDI | - | |
| 96.1.10 | [Blocage cloture v1 (96.5.1)](#t27) | MDI | - | |
| 96.1.11 | [Deblocage cloture v1 (96.6)](#t28) | MDI | - | |
| 96.1.12 | [garantie? (96.7)](#t29) | MDI | - | |
| 96.1.13 | [Affectation Auto (96.10)](#t32) | - | - | |
| 96.1.14 | [Services (96.11)](#t33) [mockup](#ecran-t33) | Modal | 157x600 | |
| 96.1.15 | [Suppression ligne a 0 (96.12)](#t34) | - | - | |
| 96.1.16 | [Supprime enregs non affectés (96.1.5.6.2.1)](#t46) | - | - | |
| 96.1.17 | [Solde gift pass (96.14)](#t49) | - | - | |
| 96.1.18 | [Blocage cloture v1 (96.5.2)](#t60) | MDI | - | |
| 96.1.19 | [Deblocage cloture v1 (96.15)](#t63) | MDI | - | |
| **96.2** | [**RAZ 269** (96.1.2)](#t4) | MDI | - | Initialisation |
| 96.2.1 | [RAZ 269 (96.1.5.1)](#t9) | MDI | - | |
| 96.2.2 | [RAZ 269 (96.3)](#t24) | MDI | - | |
| 96.2.3 | [RAZ 269 (96.8)](#t30) | MDI | - | |
| **96.3** | [**Recherche imputation/ssimput** (96.1.3.1)](#t6) | MDI | - | Consultation |
| **96.4** | [**Creation Tempo** (96.1.4)](#t7) | MDI | - | Creation |
| 96.4.1 | [Creation (96.1.5.2.1)](#t11) | - | - | |
| 96.4.2 | [Creation Enregistrement Transf (96.1.5.3.1)](#t13) [mockup](#ecran-t13) | - | 672x58 | |
| 96.4.3 | [Creation Tempo (96.1.5.10)](#t21) | MDI | - | |
| **96.5** | [**Ventes** (96.1.5)](#t8) [mockup](#ecran-t8) | Modal | 618x586 | Saisie |
| 96.5.1 | [VRL : Saisie identité (96.4)](#t25) [mockup](#ecran-t25) | - | 1313x744 | |
| **96.6** | [**Creation reglement** (96.1.5.2)](#t10) | - | - | Reglement |
| 96.6.1 | [Maj reglement (96.13)](#t35) | - | - | |
| **96.7** | [**Increment Num. Ticket(VRL/VSL)** (96.1.5.5)](#t15) | - | - | Impression |
| **96.8** | [**Type transfert** (96.1.5.6)](#t16) | MDI | - | Transfert |
| 96.8.1 | [Affiche Transfert A/R (96.1.5.6.1)](#t17) [mockup](#ecran-t17) | MDI | 1127x450 | |
| 96.8.2 | [Raz Affectation Transfert (96.9)](#t31) | - | - | |
| 96.8.3 | [Affectation PAX / Transfert (96.1.5.6.2)](#t45) [mockup](#ecran-t45) | - | 1313x744 | |
| **96.9** | [**Compte Enregs affectés** (96.1.5.9)](#t20) | - | - | Calcul |
| 96.9.1 | [Debloque compte (96.1.5.11)](#t22) | - | - | |
| 96.9.2 | [Compte Enregs affectés (96.1.5.6.2.2)](#t47) | - | - | |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Produits]
    UPDATE[MAJ 7 tables]
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

### Tables utilisees (25)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 23 | reseau_cloture___rec | Donnees reseau/cloture | DB | R | **W** |   | 5 |
| 26 | comptes_speciaux_spc | Comptes GM (generaux) | DB |   |   | L | 1 |
| 30 | gm-recherche_____gmr | Index de recherche | DB | R |   | L | 2 |
| 34 | hebergement______heb | Hebergement (chambres) | DB |   |   | L | 1 |
| 39 | depot_garantie___dga | Depots et garanties | DB | R |   |   | 1 |
| 47 | compte_gm________cgm | Comptes GM (generaux) | DB |   | **W** |   | 2 |
| 67 | tables___________tab |  | DB | R |   | L | 3 |
| 68 | compteurs________cpt | Comptes GM (generaux) | DB |   | **W** |   | 1 |
| 70 | date_comptable___dat |  | DB |   |   | L | 1 |
| 77 | articles_________art | Articles et stock | DB | R |   | L | 3 |
| 79 | gratuites________gra |  | DB | R |   |   | 1 |
| 89 | moyen_paiement___mop |  | DB | R |   |   | 6 |
| 103 | logement_client__loc |  | DB |   |   | L | 1 |
| 109 | table_utilisateurs |  | DB | R |   |   | 1 |
| 131 | fichier_validation |  | DB | R |   |   | 1 |
| 197 | articles_en_stock | Articles et stock | DB |   |   | L | 1 |
| 268 | cc_total_par_type |  | DB | R |   |   | 1 |
| 285 | email |  | DB |   |   | L | 1 |
| 461 | trf_transfert_new |  | DB |   | **W** |   | 1 |
| 578 | saisie_od_taiforfait |  | TMP |   | **W** | L | 6 |
| 677 | parametres_caisse | Sessions de caisse | DB |   |   | L | 1 |
| 707 | parametre_generaux |  | DB |   |   | L | 1 |
| 764 | trace_modif_package |  | DB |   |   | L | 2 |
| 802 | type_prestation | Prestations/services vendus | DB |   | **W** | L | 7 |
| 849 | total_jour_forfait_ski |  | DB | R | **W** | L | 9 |

### Colonnes par table (17 / 16 tables avec colonnes identifiees)

<details>
<summary>Table 23 - reseau_cloture___rec (R/**W**) - 5 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | W1 fin tache | W | Alpha |
| B | W1 cloture en cours | W | Numeric |

</details>

<details>
<summary>Table 30 - gm-recherche_____gmr (R/L) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 39 - depot_garantie___dga (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | V garantie trouvee | R | Logical |

</details>

<details>
<summary>Table 47 - compte_gm________cgm (**W**) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| C | P compte | W | Numeric |
| D | P0 solde compte | W | Numeric |
| DX | W0 Compte garanti | W | Logical |
| H | P0 etat compte | W | Alpha |

</details>

<details>
<summary>Table 67 - tables___________tab (R/L) - 3 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P0 societe | R | Alpha |
| B | P0 devise locale | R | Alpha |
| C | P0 masque montant | R | Alpha |
| D | P0 solde compte | R | Numeric |
| E | P0 code GM | R | Numeric |
| F | P0 filiation | R | Numeric |
| G | P0 date fin sejour | R | Date |
| H | P0 etat compte | R | Alpha |
| I | P0 date solde | R | Date |
| J | P0 garanti O/N | R | Alpha |
| K | P0 Nom & prenom | R | Alpha |
| L | P0 UNI/BI | R | Alpha |
| M | P0.Date debut sejour | R | Date |
| N | P0.Valide ? | R | Numeric |
| O | P0.Nb decimales | R | Numeric |
| P | Bouton IDENTITE | R | Alpha |
| Q | Bouton ABANDON | R | Alpha |
| R | W0 FIN SAISIE OD date | R | Logical |
| S | Bouton FIN SAISIE OD | R | Alpha |
| T | W0 Cloture en cours | R | Logical |
| U | V0.Qte | R | Alpha |
| V | W0 nbre articles | R | Numeric |
| W | W0 code article | R | Numeric |
| X | W0.Type article | R | Alpha |
| Y | W0 imputation | R | Numeric |
| Z | W0 sous-imput. | R | Numeric |
| BA | W0 date d'achat | R | Date |
| BB | W0 annulation | R | Alpha |
| BC | W0 service village | R | Alpha |
| BD | W0 libelle article | R | Alpha |
| BE | W0 article dernière minute | R | Logical |
| BF | W0 prix unitaire | R | Numeric |
| BG | W0 Categorie de chambre | R | Alpha |
| BH | W0 Lieu sejour | R | Alpha |
| BI | W0 Code reduction | R | Alpha |
| BJ | v Sens Transfert Global | R | Alpha |
| BK | W0 Sens du transfert Aller | R | Alpha |
| BL | W0 Date du transfert Aller | R | Date |
| BM | W0 Heure du transfert Aller | R | Time |
| BN | W0 b.Date du transfert | R | Alpha |
| BO | W0 Type d'endroit Aller | R | Alpha |
| BP | W0 Code Gare/Aéroport Aller | R | Alpha |
| BQ | W0 Numéro du vol Aller | R | Alpha |
| BR | W0 Compagnie Aller | R | Alpha |
| BS | W0 Commentaire Aller | R | Alpha |
| BT | W0 Sens du transfert Retour | R | Alpha |
| BU | W0 Date du transfert Retour | R | Date |
| BV | W0 Heure du transfert Retour | R | Time |
| BW | W0 Type d'endroit Retour | R | Alpha |
| BX | W0 Code Gare/Aéroport Retour | R | Alpha |
| BY | W0 Numéro du vol Retour | R | Alpha |
| BZ | W0 Compagnie Retour | R | Alpha |
| CA | W0 b.Saisie PAX | R | Alpha |
| CB | W0 Nbre de PAX enregistré | R | Numeric |
| CC | W0 Commentaire Retour | R | Alpha |
| CD | W0 montant avant reduction | R | Numeric |
| CE | W0 Pourcentage reduction | R | Numeric |
| CF | W0 Montant reduction | R | Numeric |
| CG | W0.Date consommation | R | Date |
| CH | W0.Date fin sejour | R | Date |
| CI | W0 Motif de non enreg NA | R | Numeric |
| CJ | W0 Commentaire | R | Alpha |
| CK | W0 Motif annulation | R | Alpha |
| CL | W0 Titre | R | Alpha |
| CM | W0 Nom | R | Alpha |
| CN | W0 Prenom | R | Alpha |
| CO | W0 Num rue | R | Alpha |
| CP | W0 Nom de la rue | R | Alpha |
| CQ | W0 Commune | R | Alpha |
| CR | W0 CP | R | Alpha |
| CS | W0 Ville | R | Alpha |
| CT | W0 libelle supplem | R | Alpha |
| CU | W0 article trouve | R | Logical |
| CV | W0 Stock produit | R | Numeric |
| CW | W0 montant | R | Numeric |
| CX | W0 mode de paiement | R | Alpha |
| CY | Existe mode de paiement | R | Logical |
| CZ | W0 Libelle MOP | R | Alpha |
| DA | WO Classe MOP | R | Alpha |
| DB | V0 memo-service | R | Alpha |
| DC | V0 memo-nom GM | R | Alpha |
| DD | V0 validation | R | Logical |
| DE | W0 reseau | R | Alpha |
| DF | W0 fin tache | R | Alpha |
| DG | W0 forfait (O/N) | R | Alpha |
| DH | W0 effacement (O/N) | R | Alpha |
| DI | W0 forfait date(O/N) | R | Alpha |
| DJ | W0 code forfait | R | Alpha |
| DK | W0 date debut | R | Date |
| DL | W0 date fin | R | Date |
| DM | W0 gratuite ? | R | Alpha |
| DN | W0 ret lien special | R | Numeric |
| DO | W0 Code Devise | R | Numeric |
| DP | W0 Retour Transmission TPE | R | Logical |
| DQ | W0 Forcer Transaction Manuelle | R | Logical |
| DR | W0 Message TPE | R | Alpha |
| DS | W0 Retour Lecture TPE | R | Logical |
| DT | W0 Fin Transaction TPE | R | Logical |
| DU | v. titre | R | Alpha |
| DV | W0 Total | R | Numeric |
| DW | W0 Annulation OD active | R | Logical |
| DX | W0 Compte garanti | R | Logical |
| DY | W0 confirmation si non garanti | R | Numeric |
| DZ | W0 Abandon | R | Logical |
| EA | W0 validation | R | Logical |
| EB | W0 choix personne absente | R | Numeric |
| EC | W0 choix transac manuelle | R | Numeric |
| ED | Bouton Ok | R | Alpha |
| EE | W0 Lien Logement Lieu Séjour | R | Logical |
| EF | V.VADA ? | R | Logical |
| EG | V.VADV ? | R | Logical |
| EH | V.VAD ? | R | Logical |
| EI | V.Nbre ecriture | R | Numeric |
| EJ | V.Reglement premier article | R | Alpha |
| EK | V.Type premier article | R | Alpha |
| EL | V.Premier article VSL NA ? | R | Logical |
| EM | V.Article VSL NA ? | R | Logical |
| EN | v.IncrémentTicket(VRL/VSL) OK | R | Logical |
| EO | v.NumeroTicket(VRL/VSL) | R | Numeric |
| EP | v Réponse mode paiement | R | Numeric |
| EQ | V Nbre de Ligne Saisies | R | Numeric |
| ER | v Nbre ligne de reglement Saisi | R | Numeric |
| ES | V.Num ligne vente | R | Numeric |
| ET | V.Total reglement ligne | R | Numeric |
| EU | V.Multi reglement ligne | R | Logical |
| EV | V.MOP TPE | R | Alpha |
| EW | V.Id transaction PMS | R | Alpha |
| EX | V.Id transaction AXIS | R | Alpha |
| EY | V.Transaction TPE validee | R | Logical |
| EZ | V.Message erreur transac TPE | R | Alpha |
| FA | V.Total carte | R | Numeric |
| FB | V.Transaction ok | R | Logical |
| FC | V.Nombre de carte | R | Numeric |
| FD | b.type de transfert | R | Alpha |
| FE | v is the First time | R | Numeric |
| FF | V0.refresh | R | Logical |
| FG | V0.Au moins une ligne | R | Logical |
| FH | V0.Nom fichier | R | Alpha |
| FI | V0.Force record suffix | R | Logical |
| FJ | V0.Nb strokes | R | Alpha |
| FK | V0.Filename signature | R | Alpha |
| FL | V0.Email | R | Alpha |
| FM | V0.Decline Email receipt | R | Logical |
| FN | V0.Fichier sans chemin | R | Alpha |
| FO | V0.montant - Gift pass | R | Numeric |
| FP | V0.Solde gift pass | R | Numeric |
| FQ | V0.valider? | R | Logical |
| FR | V.N° de Ticket OD | R | Numeric |
| FS | V.N° de Ticket Autre Moyen paie | R | Numeric |
| FT | CHG_REASON_W0 nbre articles | R | Numeric |
| FU | CHG_PRV_W0 nbre articles | R | Numeric |

</details>

<details>
<summary>Table 68 - compteurs________cpt (**W**) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 77 - articles_________art (R/L) - 3 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P.Service | R | Alpha |
| B | V2.Existe MOP ? | R | Logical |
| C | V2.OK saisie | R | Logical |
| D | V.Existe mode de paiement | R | Logical |
| E | CHG_REASON_sod_code_reduction | R | Numeric |
| F | CHG_PRV_sod_code_reduction | R | Alpha |
| G | CHG_REASON_sod_prix_unitaire | R | Numeric |
| H | CHG_PRV_sod_prix_unitaire | R | Numeric |
| I | CHG_REASON_sod_code_reduction | R | Numeric |
| J | CHG_PRV_sod_code_reduction | R | Alpha |

</details>

<details>
<summary>Table 79 - gratuites________gra (R) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 89 - moyen_paiement___mop (R) - 6 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | V1.Mode paiement | R | Alpha |
| CX | W0 mode de paiement | R | Alpha |
| CY | Existe mode de paiement | R | Logical |
| D | V.Existe mode de paiement | R | Logical |
| EP | v Réponse mode paiement | R | Numeric |
| FS | V.N° de Ticket Autre Moyen paie | R | Numeric |

</details>

<details>
<summary>Table 109 - table_utilisateurs (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | W2 Titre | R | Alpha |
| B | W2 Nom | R | Alpha |
| C | W2 Prenom | R | Alpha |
| D | W2 Num rue | R | Alpha |
| E | W2 Nom rue | R | Alpha |
| F | W2 Commune | R | Alpha |
| G | W2 CP | R | Alpha |
| H | W2 Ville | R | Alpha |
| I | Bouton Ok | R | Alpha |
| J | V.Chaine OK | R | Alpha |

</details>

<details>
<summary>Table 131 - fichier_validation (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | V4 Nom recherche | R | Alpha |
| B | V4.Prenom recherche | R | Alpha |
| C | V4 Nbre de Pax Enregistrés | R | Numeric |

</details>

<details>
<summary>Table 268 - cc_total_par_type (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P Type transfert Global | R | Alpha |
| BO | W0 Type d'endroit Aller | R | Alpha |
| BW | W0 Type d'endroit Retour | R | Alpha |
| C | V1.Total | R | Numeric |
| D | W1 Type Endroit Aller | R | Alpha |
| DV | W0 Total | R | Numeric |
| EK | V.Type premier article | R | Alpha |
| ET | V.Total reglement ligne | R | Numeric |
| FA | V.Total carte | R | Numeric |
| FD | b.type de transfert | R | Alpha |
| K | W1 Type Endroit Retour | R | Alpha |
| X | W0.Type article | R | Alpha |

</details>

<details>
<summary>Table 461 - trf_transfert_new (**W**) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P sens | W | Alpha |
| B | P societe | W | Alpha |
| C | P compte | W | Numeric |
| D | P filiation | W | Numeric |

</details>

<details>
<summary>Table 578 - saisie_od_taiforfait (**W**/L) - 6 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| C | V2.OK saisie | W | Logical |
| CA | W0 b.Saisie PAX | W | Alpha |
| EQ | V Nbre de Ligne Saisies | W | Numeric |
| F | v.Controle saisie 1 3 | W | Numeric |
| G | v.Controle saisie 2 | W | Numeric |
| R | W0 FIN SAISIE OD date | W | Logical |
| S | Bouton FIN SAISIE OD | W | Alpha |
| T | v.Controle saisie 2 | W | Numeric |
| U | v Erreur saisie 1 / 3 ? | W | Logical |
| V | v Erreur saisie 2 ? | W | Logical |

</details>

<details>
<summary>Table 802 - type_prestation (**W**/L) - 7 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | P.Ligne | W | Numeric |
| B | V.Existe ligne reglement multi? | W | Logical |

</details>

<details>
<summary>Table 849 - total_jour_forfait_ski (R/**W**/L) - 9 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| BH | W0 Lieu sejour | W | Alpha |
| C | V1.Total | W | Numeric |
| CH | W0.Date fin sejour | W | Date |
| DG | W0 forfait (O/N) | W | Alpha |
| DI | W0 forfait date(O/N) | W | Alpha |
| DJ | W0 code forfait | W | Alpha |
| DV | W0 Total | W | Numeric |
| EE | W0 Lien Logement Lieu Séjour | W | Logical |
| ET | V.Total reglement ligne | W | Numeric |
| FA | V.Total carte | W | Numeric |
| G | P0 date fin sejour | W | Date |
| M | P0.Date debut sejour | W | Date |

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (15)

Variables recues du programme appelant ([Lancement ventes (IDE 95)](WEL-IDE-95.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | P0 societe | Alpha | 3x parametre entrant |
| B | P0 devise locale | Alpha | - |
| C | P0 masque montant | Alpha | - |
| D | P0 solde compte | Numeric | - |
| E | P0 code GM | Numeric | 12x parametre entrant |
| F | P0 filiation | Numeric | 12x parametre entrant |
| G | P0 date fin sejour | Date | 1x parametre entrant |
| H | P0 etat compte | Alpha | - |
| I | P0 date solde | Date | - |
| J | P0 garanti O/N | Alpha | - |
| K | P0 Nom & prenom | Alpha | 2x parametre entrant |
| L | P0 UNI/BI | Alpha | - |
| M | P0.Date debut sejour | Date | 1x parametre entrant |
| N | P0.Valide ? | Numeric | - |
| O | P0.Nb decimales | Numeric | - |

### 11.2 Variables de session (29)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| BJ | v Sens Transfert Global | Alpha | - |
| DU | v. titre | Alpha | - |
| EF | V.VADA ? | Logical | 1x session |
| EG | V.VADV ? | Logical | 4x session |
| EH | V.VAD ? | Logical | - |
| EI | V.Nbre ecriture | Numeric | - |
| EJ | V.Reglement premier article | Alpha | - |
| EK | V.Type premier article | Alpha | - |
| EL | V.Premier article VSL NA ? | Logical | - |
| EM | V.Article VSL NA ? | Logical | - |
| EN | v.IncrémentTicket(VRL/VSL) OK | Logical | - |
| EO | v.NumeroTicket(VRL/VSL) | Numeric | - |
| EP | v Réponse mode paiement | Numeric | - |
| EQ | V Nbre de Ligne Saisies | Numeric | [96.12](#t34) |
| ER | v Nbre ligne de reglement Saisi | Numeric | - |
| ES | V.Num ligne vente | Numeric | [96.1.5](#t8), [96.12](#t34) |
| ET | V.Total reglement ligne | Numeric | - |
| EU | V.Multi reglement ligne | Logical | - |
| EV | V.MOP TPE | Alpha | 1x session |
| EW | V.Id transaction PMS | Alpha | - |
| EX | V.Id transaction AXIS | Alpha | - |
| EY | V.Transaction TPE validee | Logical | - |
| EZ | V.Message erreur transac TPE | Alpha | - |
| FA | V.Total carte | Numeric | - |
| FB | V.Transaction ok | Logical | - |
| FC | V.Nombre de carte | Numeric | 1x session |
| FE | v is the First time | Numeric | - |
| FR | V.N° de Ticket OD | Numeric | - |
| FS | V.N° de Ticket Autre Moyen paie | Numeric | - |

### 11.3 Variables de travail (82)

Variables internes au programme.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| R | W0 FIN SAISIE OD date | Logical | [96.4](#t25) |
| T | W0 Cloture en cours | Logical | - |
| V | W0 nbre articles | Numeric | 3x calcul interne |
| W | W0 code article | Numeric | 3x calcul interne |
| X | W0.Type article | Alpha | 2x calcul interne |
| Y | W0 imputation | Numeric | - |
| Z | W0 sous-imput. | Numeric | - |
| BA | W0 date d'achat | Date | - |
| BB | W0 annulation | Alpha | - |
| BC | W0 service village | Alpha | [96.11](#t33) |
| BD | W0 libelle article | Alpha | - |
| BE | W0 article dernière minute | Logical | - |
| BF | W0 prix unitaire | Numeric | - |
| BG | W0 Categorie de chambre | Alpha | - |
| BH | W0 Lieu sejour | Alpha | 1x calcul interne |
| BI | W0 Code reduction | Alpha | 1x calcul interne |
| BK | W0 Sens du transfert Aller | Alpha | - |
| BL | W0 Date du transfert Aller | Date | - |
| BM | W0 Heure du transfert Aller | Time | - |
| BN | W0 b.Date du transfert | Alpha | - |
| BO | W0 Type d'endroit Aller | Alpha | - |
| BP | W0 Code Gare/Aéroport Aller | Alpha | - |
| BQ | W0 Numéro du vol Aller | Alpha | - |
| BR | W0 Compagnie Aller | Alpha | - |
| BS | W0 Commentaire Aller | Alpha | - |
| BT | W0 Sens du transfert Retour | Alpha | - |
| BU | W0 Date du transfert Retour | Date | - |
| BV | W0 Heure du transfert Retour | Time | - |
| BW | W0 Type d'endroit Retour | Alpha | - |
| BX | W0 Code Gare/Aéroport Retour | Alpha | - |
| BY | W0 Numéro du vol Retour | Alpha | - |
| BZ | W0 Compagnie Retour | Alpha | - |
| CA | W0 b.Saisie PAX | Alpha | - |
| CB | W0 Nbre de PAX enregistré | Numeric | - |
| CC | W0 Commentaire Retour | Alpha | - |
| CD | W0 montant avant reduction | Numeric | - |
| CE | W0 Pourcentage reduction | Numeric | - |
| CF | W0 Montant reduction | Numeric | - |
| CG | W0.Date consommation | Date | - |
| CH | W0.Date fin sejour | Date | - |
| CI | W0 Motif de non enreg NA | Numeric | - |
| CJ | W0 Commentaire | Alpha | - |
| CK | W0 Motif annulation | Alpha | 1x calcul interne |
| CL | W0 Titre | Alpha | 1x calcul interne |
| CM | W0 Nom | Alpha | 1x calcul interne |
| CN | W0 Prenom | Alpha | - |
| CO | W0 Num rue | Alpha | - |
| CP | W0 Nom de la rue | Alpha | 1x calcul interne |
| CQ | W0 Commune | Alpha | 1x calcul interne |
| CR | W0 CP | Alpha | 1x calcul interne |
| CS | W0 Ville | Alpha | - |
| CT | W0 libelle supplem | Alpha | - |
| CU | W0 article trouve | Logical | - |
| CV | W0 Stock produit | Numeric | - |
| CW | W0 montant | Numeric | - |
| CX | W0 mode de paiement | Alpha | - |
| CZ | W0 Libelle MOP | Alpha | - |
| DE | W0 reseau | Alpha | - |
| DF | W0 fin tache | Alpha | - |
| DG | W0 forfait (O/N) | Alpha | - |
| DH | W0 effacement (O/N) | Alpha | - |
| DI | W0 forfait date(O/N) | Alpha | - |
| DJ | W0 code forfait | Alpha | - |
| DK | W0 date debut | Date | - |
| DL | W0 date fin | Date | 1x calcul interne |
| DM | W0 gratuite ? | Alpha | - |
| DN | W0 ret lien special | Numeric | - |
| DO | W0 Code Devise | Numeric | - |
| DP | W0 Retour Transmission TPE | Logical | - |
| DQ | W0 Forcer Transaction Manuelle | Logical | - |
| DR | W0 Message TPE | Alpha | - |
| DS | W0 Retour Lecture TPE | Logical | - |
| DT | W0 Fin Transaction TPE | Logical | 2x calcul interne |
| DV | W0 Total | Numeric | - |
| DW | W0 Annulation OD active | Logical | - |
| DX | W0 Compte garanti | Logical | - |
| DY | W0 confirmation si non garanti | Numeric | - |
| DZ | W0 Abandon | Logical | - |
| EA | W0 validation | Logical | - |
| EB | W0 choix personne absente | Numeric | - |
| EC | W0 choix transac manuelle | Numeric | 2x calcul interne |
| EE | W0 Lien Logement Lieu Séjour | Logical | - |

### 11.4 Autres (25)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| P | Bouton IDENTITE | Alpha | - |
| Q | Bouton ABANDON | Alpha | 1x refs |
| S | Bouton FIN SAISIE OD | Alpha | [96.4](#t25) |
| U | V0.Qte | Alpha | 12x refs |
| CY | Existe mode de paiement | Logical | - |
| DA | WO Classe MOP | Alpha | 1x refs |
| DB | V0 memo-service | Alpha | 1x refs |
| DC | V0 memo-nom GM | Alpha | - |
| DD | V0 validation | Logical | 2x refs |
| ED | Bouton Ok | Alpha | 1x refs |
| FD | b.type de transfert | Alpha | - |
| FF | V0.refresh | Logical | - |
| FG | V0.Au moins une ligne | Logical | - |
| FH | V0.Nom fichier | Alpha | 1x refs |
| FI | V0.Force record suffix | Logical | - |
| FJ | V0.Nb strokes | Alpha | - |
| FK | V0.Filename signature | Alpha | - |
| FL | V0.Email | Alpha | - |
| FM | V0.Decline Email receipt | Logical | - |
| FN | V0.Fichier sans chemin | Alpha | 3x refs |
| FO | V0.montant - Gift pass | Numeric | - |
| FP | V0.Solde gift pass | Numeric | - |
| FQ | V0.valider? | Logical | - |
| FT | CHG_REASON_W0 nbre articles | Numeric | - |
| FU | CHG_PRV_W0 nbre articles | Numeric | - |

<details>
<summary>Toutes les 151 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| P0 | **A** | P0 societe | Alpha |
| P0 | **B** | P0 devise locale | Alpha |
| P0 | **C** | P0 masque montant | Alpha |
| P0 | **D** | P0 solde compte | Numeric |
| P0 | **E** | P0 code GM | Numeric |
| P0 | **F** | P0 filiation | Numeric |
| P0 | **G** | P0 date fin sejour | Date |
| P0 | **H** | P0 etat compte | Alpha |
| P0 | **I** | P0 date solde | Date |
| P0 | **J** | P0 garanti O/N | Alpha |
| P0 | **K** | P0 Nom & prenom | Alpha |
| P0 | **L** | P0 UNI/BI | Alpha |
| P0 | **M** | P0.Date debut sejour | Date |
| P0 | **N** | P0.Valide ? | Numeric |
| P0 | **O** | P0.Nb decimales | Numeric |
| W0 | **R** | W0 FIN SAISIE OD date | Logical |
| W0 | **T** | W0 Cloture en cours | Logical |
| W0 | **V** | W0 nbre articles | Numeric |
| W0 | **W** | W0 code article | Numeric |
| W0 | **X** | W0.Type article | Alpha |
| W0 | **Y** | W0 imputation | Numeric |
| W0 | **Z** | W0 sous-imput. | Numeric |
| W0 | **BA** | W0 date d'achat | Date |
| W0 | **BB** | W0 annulation | Alpha |
| W0 | **BC** | W0 service village | Alpha |
| W0 | **BD** | W0 libelle article | Alpha |
| W0 | **BE** | W0 article dernière minute | Logical |
| W0 | **BF** | W0 prix unitaire | Numeric |
| W0 | **BG** | W0 Categorie de chambre | Alpha |
| W0 | **BH** | W0 Lieu sejour | Alpha |
| W0 | **BI** | W0 Code reduction | Alpha |
| W0 | **BK** | W0 Sens du transfert Aller | Alpha |
| W0 | **BL** | W0 Date du transfert Aller | Date |
| W0 | **BM** | W0 Heure du transfert Aller | Time |
| W0 | **BN** | W0 b.Date du transfert | Alpha |
| W0 | **BO** | W0 Type d'endroit Aller | Alpha |
| W0 | **BP** | W0 Code Gare/Aéroport Aller | Alpha |
| W0 | **BQ** | W0 Numéro du vol Aller | Alpha |
| W0 | **BR** | W0 Compagnie Aller | Alpha |
| W0 | **BS** | W0 Commentaire Aller | Alpha |
| W0 | **BT** | W0 Sens du transfert Retour | Alpha |
| W0 | **BU** | W0 Date du transfert Retour | Date |
| W0 | **BV** | W0 Heure du transfert Retour | Time |
| W0 | **BW** | W0 Type d'endroit Retour | Alpha |
| W0 | **BX** | W0 Code Gare/Aéroport Retour | Alpha |
| W0 | **BY** | W0 Numéro du vol Retour | Alpha |
| W0 | **BZ** | W0 Compagnie Retour | Alpha |
| W0 | **CA** | W0 b.Saisie PAX | Alpha |
| W0 | **CB** | W0 Nbre de PAX enregistré | Numeric |
| W0 | **CC** | W0 Commentaire Retour | Alpha |
| W0 | **CD** | W0 montant avant reduction | Numeric |
| W0 | **CE** | W0 Pourcentage reduction | Numeric |
| W0 | **CF** | W0 Montant reduction | Numeric |
| W0 | **CG** | W0.Date consommation | Date |
| W0 | **CH** | W0.Date fin sejour | Date |
| W0 | **CI** | W0 Motif de non enreg NA | Numeric |
| W0 | **CJ** | W0 Commentaire | Alpha |
| W0 | **CK** | W0 Motif annulation | Alpha |
| W0 | **CL** | W0 Titre | Alpha |
| W0 | **CM** | W0 Nom | Alpha |
| W0 | **CN** | W0 Prenom | Alpha |
| W0 | **CO** | W0 Num rue | Alpha |
| W0 | **CP** | W0 Nom de la rue | Alpha |
| W0 | **CQ** | W0 Commune | Alpha |
| W0 | **CR** | W0 CP | Alpha |
| W0 | **CS** | W0 Ville | Alpha |
| W0 | **CT** | W0 libelle supplem | Alpha |
| W0 | **CU** | W0 article trouve | Logical |
| W0 | **CV** | W0 Stock produit | Numeric |
| W0 | **CW** | W0 montant | Numeric |
| W0 | **CX** | W0 mode de paiement | Alpha |
| W0 | **CZ** | W0 Libelle MOP | Alpha |
| W0 | **DE** | W0 reseau | Alpha |
| W0 | **DF** | W0 fin tache | Alpha |
| W0 | **DG** | W0 forfait (O/N) | Alpha |
| W0 | **DH** | W0 effacement (O/N) | Alpha |
| W0 | **DI** | W0 forfait date(O/N) | Alpha |
| W0 | **DJ** | W0 code forfait | Alpha |
| W0 | **DK** | W0 date debut | Date |
| W0 | **DL** | W0 date fin | Date |
| W0 | **DM** | W0 gratuite ? | Alpha |
| W0 | **DN** | W0 ret lien special | Numeric |
| W0 | **DO** | W0 Code Devise | Numeric |
| W0 | **DP** | W0 Retour Transmission TPE | Logical |
| W0 | **DQ** | W0 Forcer Transaction Manuelle | Logical |
| W0 | **DR** | W0 Message TPE | Alpha |
| W0 | **DS** | W0 Retour Lecture TPE | Logical |
| W0 | **DT** | W0 Fin Transaction TPE | Logical |
| W0 | **DV** | W0 Total | Numeric |
| W0 | **DW** | W0 Annulation OD active | Logical |
| W0 | **DX** | W0 Compte garanti | Logical |
| W0 | **DY** | W0 confirmation si non garanti | Numeric |
| W0 | **DZ** | W0 Abandon | Logical |
| W0 | **EA** | W0 validation | Logical |
| W0 | **EB** | W0 choix personne absente | Numeric |
| W0 | **EC** | W0 choix transac manuelle | Numeric |
| W0 | **EE** | W0 Lien Logement Lieu Séjour | Logical |
| V. | **BJ** | v Sens Transfert Global | Alpha |
| V. | **DU** | v. titre | Alpha |
| V. | **EF** | V.VADA ? | Logical |
| V. | **EG** | V.VADV ? | Logical |
| V. | **EH** | V.VAD ? | Logical |
| V. | **EI** | V.Nbre ecriture | Numeric |
| V. | **EJ** | V.Reglement premier article | Alpha |
| V. | **EK** | V.Type premier article | Alpha |
| V. | **EL** | V.Premier article VSL NA ? | Logical |
| V. | **EM** | V.Article VSL NA ? | Logical |
| V. | **EN** | v.IncrémentTicket(VRL/VSL) OK | Logical |
| V. | **EO** | v.NumeroTicket(VRL/VSL) | Numeric |
| V. | **EP** | v Réponse mode paiement | Numeric |
| V. | **EQ** | V Nbre de Ligne Saisies | Numeric |
| V. | **ER** | v Nbre ligne de reglement Saisi | Numeric |
| V. | **ES** | V.Num ligne vente | Numeric |
| V. | **ET** | V.Total reglement ligne | Numeric |
| V. | **EU** | V.Multi reglement ligne | Logical |
| V. | **EV** | V.MOP TPE | Alpha |
| V. | **EW** | V.Id transaction PMS | Alpha |
| V. | **EX** | V.Id transaction AXIS | Alpha |
| V. | **EY** | V.Transaction TPE validee | Logical |
| V. | **EZ** | V.Message erreur transac TPE | Alpha |
| V. | **FA** | V.Total carte | Numeric |
| V. | **FB** | V.Transaction ok | Logical |
| V. | **FC** | V.Nombre de carte | Numeric |
| V. | **FE** | v is the First time | Numeric |
| V. | **FR** | V.N° de Ticket OD | Numeric |
| V. | **FS** | V.N° de Ticket Autre Moyen paie | Numeric |
| Autre | **P** | Bouton IDENTITE | Alpha |
| Autre | **Q** | Bouton ABANDON | Alpha |
| Autre | **S** | Bouton FIN SAISIE OD | Alpha |
| Autre | **U** | V0.Qte | Alpha |
| Autre | **CY** | Existe mode de paiement | Logical |
| Autre | **DA** | WO Classe MOP | Alpha |
| Autre | **DB** | V0 memo-service | Alpha |
| Autre | **DC** | V0 memo-nom GM | Alpha |
| Autre | **DD** | V0 validation | Logical |
| Autre | **ED** | Bouton Ok | Alpha |
| Autre | **FD** | b.type de transfert | Alpha |
| Autre | **FF** | V0.refresh | Logical |
| Autre | **FG** | V0.Au moins une ligne | Logical |
| Autre | **FH** | V0.Nom fichier | Alpha |
| Autre | **FI** | V0.Force record suffix | Logical |
| Autre | **FJ** | V0.Nb strokes | Alpha |
| Autre | **FK** | V0.Filename signature | Alpha |
| Autre | **FL** | V0.Email | Alpha |
| Autre | **FM** | V0.Decline Email receipt | Logical |
| Autre | **FN** | V0.Fichier sans chemin | Alpha |
| Autre | **FO** | V0.montant - Gift pass | Numeric |
| Autre | **FP** | V0.Solde gift pass | Numeric |
| Autre | **FQ** | V0.valider? | Logical |
| Autre | **FT** | CHG_REASON_W0 nbre articles | Numeric |
| Autre | **FU** | CHG_PRV_W0 nbre articles | Numeric |

</details>

## 12. EXPRESSIONS

**112 / 112 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONCATENATION | 11 | 0 |
| CONDITION | 23 | 3 |
| CONSTANTE | 23 | 0 |
| DATE | 2 | 0 |
| FORMAT | 11 | 0 |
| OTHER | 31 | 0 |
| CAST_LOGIQUE | 3 | 0 |
| NEGATION | 4 | 0 |
| REFERENCE_VG | 2 | 0 |
| STRING | 2 | 0 |

### 12.2 Expressions cles par type

#### CONCATENATION (11 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 73 | `Trim(V0.Qte [U])&'6'` | - |
| CONCATENATION | 72 | `Trim(V0.Qte [U])&'5'` | - |
| CONCATENATION | 74 | `Trim(V0.Qte [U])&'7'` | - |
| CONCATENATION | 76 | `Trim(V0.Qte [U])&'9'` | - |
| CONCATENATION | 75 | `Trim(V0.Qte [U])&'8'` | - |
| ... | | *+6 autres* | |

#### CONDITION (23 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 42 | `IF(W0 Commune [CQ]<>'',RTrim (W0 Nom de la rue [CP])&Fill (' ',Len (RTrim (W0 Nom de la rue [CP]))-1)&RTrim (W0 Commune [CQ])&' '&W0 CP [CR],Trim(P0 Nom & prenom [K]))` | [RM-002](#rm-RM-002) |
| CONDITION | 44 | `IF(V.Num ligne vente [ES],V.MOP TPE [EV],VG43)` | [RM-003](#rm-RM-003) |
| CONDITION | 1 | `IF(V0.Fichier sans chemin [FN]=0,IF([AC]='VSL',P0.Date debut sejour [M],Date()),W0 Motif annulation [CK])` | [RM-001](#rm-RM-001) |
| CONDITION | 81 | `DbRecs('{578,4}'DSOURCE,'')>0` | - |
| CONDITION | 85 | `LastClicked()<>'Bouton FIN SAISIE OD'` | - |
| ... | | *+18 autres* | |

#### CONSTANTE (23 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 55 | `'VADV'` | - |
| CONSTANTE | 65 | `''` | - |
| CONSTANTE | 54 | `'VADA'` | - |
| CONSTANTE | 50 | `'H'` | - |
| CONSTANTE | 52 | `'PL'` | - |
| ... | | *+18 autres* | |

#### DATE (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| DATE | 27 | `Date ()` | - |
| DATE | 6 | `Date ()` | - |

#### FORMAT (11 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| FORMAT | 108 | `Trim(VG67) &'TICKET_OD_'&Trim(Str(P0 code GM [E],'8P0'))&'_'&Trim(Str(P0 filiation [F],'###'))&'_'&Trim(VG15)&'_'&DStr(Date(),'YYMMDD')&TStr(Time(),'HHMMSS')&'.pdf'` | - |
| FORMAT | 107 | `Translate('%club_exportdata%')&'WELCOME\'&'TICKET_OD_'&Trim(Str(P0 code GM [E],'8P0'))&'_'&Trim(Str(P0 filiation [F],'###'))&'_'&Trim(VG15)&'_'&DStr(Date(),'YYMMDD')&TStr(Time(),'HHMMSS')&'.pdf'` | - |
| FORMAT | 109 | `'TICKET_OTHER_PAYMENT_'&Trim(Str(P0 code GM [E],'8P0'))&'_'&Trim(Str(P0 filiation [F],'###'))&'_'&Trim(VG15)&'_'&DStr(Date(),'YYMMDD')&TStr(Time(),'HHMMSS')&'.pdf'` | - |
| FORMAT | 84 | `MlsTrans('Total')&' '&Trim(Str(ABS(W0 choix transac manuelle [EC]),VG47))` | - |
| FORMAT | 83 | `MlsTrans('Validate transaction for a total of')&Trim(Str(ABS(W0 choix transac manuelle [EC]),VG47))` | - |
| ... | | *+6 autres* | |

#### OTHER (31 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 53 | `W0 Code reduction [BI]` | - |
| OTHER | 56 | `V.Nombre de carte [FC] OR V0.Nom fichier [FH]` | - |
| OTHER | 60 | `ASCIIChr(13)&MlsTrans('CONTINUE')` | - |
| OTHER | 51 | `W0 Lieu sejour [BH]` | - |
| OTHER | 40 | `GetParam('CODELANGUE')` | - |
| ... | | *+26 autres* | |

#### CAST_LOGIQUE (3 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CAST_LOGIQUE | 86 | `'TRUE'LOG` | - |
| CAST_LOGIQUE | 36 | `'FALSE'LOG` | - |
| CAST_LOGIQUE | 20 | `'TRUE'LOG` | - |

#### NEGATION (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| NEGATION | 92 | `NOT ExpCalc('90'EXP)` | - |
| NEGATION | 111 | `NOT VG70` | - |
| NEGATION | 22 | `NOT (W0 Lien Logement Lieu ... [EE])` | - |
| NEGATION | 35 | `NOT ExpCalc('34'EXP)` | - |

#### REFERENCE_VG (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 112 | `VG70` | - |
| REFERENCE_VG | 30 | `VG38` | - |

#### STRING (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| STRING | 88 | `Trim([GM])` | - |
| STRING | 78 | `Val(Trim(V0.Qte [U]),'3')` | - |

### 12.3 Toutes les expressions (112)

<details>
<summary>Voir les 112 expressions</summary>

#### CONCATENATION (11)

| IDE | Expression Decodee |
|-----|-------------------|
| 59 | `MlsTrans('SALES')&' - '&Trim(P0 Nom & prenom [K])` |
| 67 | `Trim(V0.Qte [U])&'0'` |
| 68 | `Trim(V0.Qte [U])&'1'` |
| 69 | `Trim(V0.Qte [U])&'2'` |
| 70 | `Trim(V0.Qte [U])&'3'` |
| 71 | `Trim(V0.Qte [U])&'4'` |
| 72 | `Trim(V0.Qte [U])&'5'` |
| 73 | `Trim(V0.Qte [U])&'6'` |
| 74 | `Trim(V0.Qte [U])&'7'` |
| 75 | `Trim(V0.Qte [U])&'8'` |
| 76 | `Trim(V0.Qte [U])&'9'` |

#### CONDITION (23)

| IDE | Expression Decodee |
|-----|-------------------|
| 1 | `IF(V0.Fichier sans chemin [FN]=0,IF([AC]='VSL',P0.Date debut sejour [M],Date()),W0 Motif annulation [CK])` |
| 39 | `IF(V0.Fichier sans chemin [FN]=0,IF([AC]='VSL',P0 date fin sejour [G],W0 Titre [CL]),W0 Titre [CL])` |
| 42 | `IF(W0 Commune [CQ]<>'',RTrim (W0 Nom de la rue [CP])&Fill (' ',Len (RTrim (W0 Nom de la rue [CP]))-1)&RTrim (W0 Commune [CQ])&' '&W0 CP [CR],Trim(P0 Nom & prenom [K]))` |
| 44 | `IF(V.Num ligne vente [ES],V.MOP TPE [EV],VG43)` |
| 11 | `W0 nbre articles [V]=0 AND NOT V.VADV ? [EG]` |
| 13 | `W0 nbre articles [V]>V0 memo-service [DB] AND NOT (V.VADV ? [EG])` |
| 19 | `DbRecs ('{578,4}'DSOURCE,'')>0 AND W0 FIN SAISIE OD date [R]` |
| 21 | `LastClicked()<>'Bouton ABANDON' AND NOT (V.VADV ? [EG]) AND DbRecs ('{578,4}'DSOURCE,'')=0` |
| 33 | `V0 validation [DD]=''` |
| 45 | `VG31>1` |
| 57 | `[GX]>1 AND W0 nbre articles [V]=1` |
| 58 | `[AC]='TRF' AND VG41` |
| 62 | `W0.Type article [X]='VRL' AND W0 Fin Transaction TPE [DT]=0` |
| 63 | `W0.Type article [X]='VRL' AND W0 Fin Transaction TPE [DT]=0 AND V0.Fichier sans chemin [FN]=0` |
| 64 | `V.VADA ? [EF]<>6` |
| 80 | `W0 date fin [DL]='F' OR V.VADV ? [EG]` |
| 81 | `DbRecs('{578,4}'DSOURCE,'')>0` |
| 85 | `LastClicked()<>'Bouton FIN SAISIE OD'` |
| 15 | `Trim (INIGet ('[MAGIC_LOGICAL_NAMES]club_editod'))='O' AND Trim (INIGet ('[MAGIC_LOGICAL_NAMES]club_formation'))<>'O'` |
| 77 | `Len(Trim(V0.Qte [U]))<3` |
| 91 | `Trim(V0 validation [DD])='OD'` |
| 99 | `Trim([GO])<>'0'` |
| 100 | `Trim([GO])<>'0' AND NOT [GV]` |

#### CONSTANTE (23)

| IDE | Expression Decodee |
|-----|-------------------|
| 5 | `'F'` |
| 7 | `'N'` |
| 8 | `0` |
| 9 | `'CAISSE'` |
| 17 | `'A&bandonner'` |
| 23 | `30` |
| 28 | `'H'` |
| 31 | `'VISA'` |
| 41 | `''` |
| 43 | `'SANS'` |
| 47 | `'...'` |
| 48 | `'2'` |
| 50 | `'H'` |
| 52 | `'PL'` |
| 54 | `'VADA'` |
| 55 | `'VADV'` |
| 65 | `''` |
| 66 | `0` |
| 79 | `''` |
| 82 | `'VALSALES'` |
| 93 | `'VSERV'` |
| 94 | `'O'` |
| 105 | `'WELSALES'` |

#### DATE (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 6 | `Date ()` |
| 27 | `Date ()` |

#### FORMAT (11)

| IDE | Expression Decodee |
|-----|-------------------|
| 87 | `Translate('%club_exportdata%')&'WELCOME\'&'TICKET_OD_'&Trim(Str(P0 code GM [E],'8P0'))&'_'&Trim(Str(P0 filiation [F],'###'))&'_'&Trim(VG15)&'_'&DStr(Date(),'YYMMDD')&TStr(Time(),'HHMMSS')&'.pdf'` |
| 89 | `Translate('%club_exportdata%')&'WELCOME\'&'TICKET_OTHER_PAYMENT_'&Trim(Str(P0 code GM [E],'8P0'))&'_'&Trim(Str(P0 filiation [F],'###'))&'_'&Trim(VG15)&'_'&DStr(Date(),'YYMMDD')&TStr(Time(),'HHMMSS')&'.pdf'` |
| 90 | `Trim(VG67) &'TICKET_OTHER_PAYMENT_'&Trim(Str(P0 code GM [E],'8P0'))&'_'&Trim(Str(P0 filiation [F],'###'))&'_'&Trim(VG15)&'_'&DStr(Date(),'YYMMDD')&TStr(Time(),'HHMMSS')&'.pdf'` |
| 101 | `Translate('%club_exportdata%')&'WELCOME\'&'SIGN_'&Trim(Str(P0 code GM [E],'8P0'))&'_'&Trim(Str(P0 filiation [F],'###'))&'_'&Trim(VG15)&'_'&DStr(Date(),'YYMMDD')&TStr(Time(),'HHMMSS')&'.gif'` |
| 102 | `Trim(VG68) &'SIGN_'&Trim(Str(P0 code GM [E],'8P0'))&'_'&Trim(Str(P0 filiation [F],'###'))&'_'&Trim(VG15)&'_'&DStr(Date(),'YYMMDD')&TStr(Time(),'HHMMSS')&'.gif'` |
| 106 | `'TICKET_OD_'&Trim(Str(P0 code GM [E],'8P0'))&'_'&Trim(Str(P0 filiation [F],'###'))&'_'&Trim(VG15)&'_'&DStr(Date(),'YYMMDD')&TStr(Time(),'HHMMSS')&'.pdf'` |
| 107 | `Translate('%club_exportdata%')&'WELCOME\'&'TICKET_OD_'&Trim(Str(P0 code GM [E],'8P0'))&'_'&Trim(Str(P0 filiation [F],'###'))&'_'&Trim(VG15)&'_'&DStr(Date(),'YYMMDD')&TStr(Time(),'HHMMSS')&'.pdf'` |
| 108 | `Trim(VG67) &'TICKET_OD_'&Trim(Str(P0 code GM [E],'8P0'))&'_'&Trim(Str(P0 filiation [F],'###'))&'_'&Trim(VG15)&'_'&DStr(Date(),'YYMMDD')&TStr(Time(),'HHMMSS')&'.pdf'` |
| 109 | `'TICKET_OTHER_PAYMENT_'&Trim(Str(P0 code GM [E],'8P0'))&'_'&Trim(Str(P0 filiation [F],'###'))&'_'&Trim(VG15)&'_'&DStr(Date(),'YYMMDD')&TStr(Time(),'HHMMSS')&'.pdf'` |
| 83 | `MlsTrans('Validate transaction for a total of')&Trim(Str(ABS(W0 choix transac manuelle [EC]),VG47))` |
| 84 | `MlsTrans('Total')&' '&Trim(Str(ABS(W0 choix transac manuelle [EC]),VG47))` |

#### OTHER (31)

| IDE | Expression Decodee |
|-----|-------------------|
| 2 | `P0 societe [A]` |
| 3 | `P0 code GM [E]` |
| 4 | `P0 filiation [F]` |
| 10 | `W0 code article [W]` |
| 12 | `WO Classe MOP [DA]` |
| 14 | `Bouton Ok [ED]` |
| 16 | `MlsTrans('Identité')` |
| 18 | `MlsTrans ('&Fin Transaction')` |
| 24 | `P0 societe [A]` |
| 25 | `P0 code GM [E]` |
| 26 | `P0 filiation [F]` |
| 29 | `ASCIIChr (33)` |
| 32 | `W0 code article [W]` |
| 34 | `W0 Lien Logement Lieu ... [EE]` |
| 37 | `W0 service village [BC]` |
| 38 | `W0 code article [W]` |
| 40 | `GetParam('CODELANGUE')` |
| 46 | `[GG]` |
| 49 | `V Nbre de Ligne Saisies [EQ]` |
| 51 | `W0 Lieu sejour [BH]` |
| 53 | `W0 Code reduction [BI]` |
| 56 | `V.Nombre de carte [FC] OR V0.Nom fichier [FH]` |
| 60 | `ASCIIChr(13)&MlsTrans('CONTINUE')` |
| 61 | `ASCIIChr(13)&MlsTrans('IDENTITY')` |
| 95 | `[GT]` |
| 96 | `P0 societe [A]` |
| 97 | `P0 code GM [E]` |
| 98 | `P0 filiation [F]` |
| 103 | `FileDelete([GP])` |
| 104 | `FileExist([GP])` |
| 110 | `[HB]` |

#### CAST_LOGIQUE (3)

| IDE | Expression Decodee |
|-----|-------------------|
| 20 | `'TRUE'LOG` |
| 36 | `'FALSE'LOG` |
| 86 | `'TRUE'LOG` |

#### NEGATION (4)

| IDE | Expression Decodee |
|-----|-------------------|
| 22 | `NOT (W0 Lien Logement Lieu ... [EE])` |
| 35 | `NOT ExpCalc('34'EXP)` |
| 92 | `NOT ExpCalc('90'EXP)` |
| 111 | `NOT VG70` |

#### REFERENCE_VG (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 30 | `VG38` |
| 112 | `VG70` |

#### STRING (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 78 | `Val(Trim(V0.Qte [U]),'3')` |
| 88 | `Trim([GM])` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Lancement ventes (IDE 95)](WEL-IDE-95.md) -> **Ventes (IDE 96)**

```mermaid
graph LR
    T96[96 Ventes]
    style T96 fill:#58a6ff
    CC95[95 Lancement ventes]
    style CC95 fill:#8b5cf6
    CC95 --> T96
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [95](WEL-IDE-95.md) | Lancement ventes | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T96[96 Ventes]
    style T96 fill:#58a6ff
    C89[89 Traitement des mails]
    T96 --> C89
    style C89 fill:#3fb950
    C17[17 Search client avec ...]
    T96 --> C17
    style C17 fill:#3fb950
    C81[81 Create logbook]
    T96 --> C81
    style C81 fill:#3fb950
    C82[82 Saisie Signature]
    T96 --> C82
    style C82 fill:#3fb950
    C83[83 Saisie Signature Va...]
    T96 --> C83
    style C83 fill:#3fb950
    C110[110 Zoom Mode paiement]
    T96 --> C110
    style C110 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [89](WEL-IDE-89.md) | Traitement des mails | 2 | Sous-programme |
| [17](WEL-IDE-17.md) | Search client avec liste | 1 | Configuration impression |
| [81](WEL-IDE-81.md) | Create logbook | 1 | Sous-programme |
| [82](WEL-IDE-82.md) | Saisie Signature | 1 | Sous-programme |
| [83](WEL-IDE-83.md) | Saisie Signature Validation | 1 | Sous-programme |
| [110](WEL-IDE-110.md) | Zoom Mode paiement | 1 | Selection/consultation |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 1412 | Programme volumineux |
| Expressions | 112 | Logique moderee |
| Tables WRITE | 7 | Fort impact donnees |
| Sous-programmes | 6 | Dependances moderees |
| Ecrans visibles | 7 | Interface complexe multi-ecrans |
| Code desactive | 0.9% (13 / 1412) | Code sain |
| Regles metier | 3 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Traitement (20 taches: 4 ecrans, 16 traitements)

- **Strategie** : Orchestrateur avec 4 ecrans (Razor/React) et 16 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 6 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Initialisation (4 taches: 0 ecran, 4 traitements)

- **Strategie** : Constructeur/methode `InitAsync()` dans l'orchestrateur.

#### Consultation (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Composants de recherche/selection en modales.

#### Creation (4 taches: 1 ecran, 3 traitements)

- **Strategie** : Repository pattern avec Entity Framework Core.
- Insertion via `IRepository<T>.CreateAsync()`

#### Saisie (2 taches: 2 ecrans, 0 traitement)

- **Strategie** : Formulaire React/Blazor avec validation Zod/FluentValidation.
- Reproduire 2 ecrans : Ventes, VRL : Saisie identité
- Validation temps reel cote client + serveur

#### Reglement (2 taches: 0 ecran, 2 traitements)

- **Strategie** : Service `IReglementService` avec pattern Strategy par mode de paiement.
- Integration TPE si applicable

#### Impression (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Templates HTML -> PDF via wkhtmltopdf ou Puppeteer.
- `PrintService` injectable avec choix imprimante

#### Transfert (4 taches: 2 ecrans, 2 traitements)

- **Strategie** : Service `ITransfertService` avec logique de deversement.

#### Calcul (3 taches: 0 ecran, 3 traitements)

- **Strategie** : Services de calcul purs (Domain Services).
- Migrer la logique de calcul (stock, compteurs, montants)

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| reseau_cloture___rec | Table WRITE (Database) | 4x | Schema + repository |
| compte_gm________cgm | Table WRITE (Database) | 2x | Schema + repository |
| compteurs________cpt | Table WRITE (Database) | 1x | Schema + repository |
| trf_transfert_new | Table WRITE (Database) | 1x | Schema + repository |
| saisie_od_taiforfait | Table WRITE (Temp) | 3x | Schema + repository |
| type_prestation | Table WRITE (Database) | 1x | Schema + repository |
| total_jour_forfait_ski | Table WRITE (Database) | 6x | Schema + repository |
| [Traitement des mails (IDE 89)](WEL-IDE-89.md) | Sous-programme | 2x | Haute - Sous-programme |
| [Saisie Signature Validation (IDE 83)](WEL-IDE-83.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Zoom Mode paiement (IDE 110)](WEL-IDE-110.md) | Sous-programme | 1x | Normale - Selection/consultation |
| [Saisie Signature (IDE 82)](WEL-IDE-82.md) | Sous-programme | 1x | Normale - Sous-programme |
| [Search client avec liste (IDE 17)](WEL-IDE-17.md) | Sous-programme | 1x | Normale - Configuration impression |
| [Create logbook (IDE 81)](WEL-IDE-81.md) | Sous-programme | 1x | Normale - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 21:44*
