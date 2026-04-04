# PBP IDE 176 - Imprim AVPBDR toutes GM

> **Analyse**: Phases 1-4 2026-02-03 15:38 -> 15:39 (12s) | Assemblage 15:39
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | PBP |
| IDE Position | 176 |
| Nom Programme | Imprim AVPBDR toutes GM |
| Fichier source | `Prg_176.xml` |
| Dossier IDE | Liste |
| Taches | 4 (1 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 1 |

## 2. DESCRIPTION FONCTIONNELLE

**Imprim AVPBDR toutes GM** assure la gestion complete de ce processus, accessible depuis [  Liste CLients arrivant (IDE 156)](PBP-IDE-156.md), [  Liste Clients present (IDE 162)](PBP-IDE-162.md), [  Liste CLients depart (IDE 168)](PBP-IDE-168.md), [Liste CLients AVPBDR (IDE 174)](PBP-IDE-174.md), [  Affichage AVPBDR toutes GM (IDE 175)](PBP-IDE-175.md).

Le flux de traitement s'organise en **3 blocs fonctionnels** :

- **Traitement** (2 taches) : traitements metier divers
- **Impression** (1 tache) : generation de tickets et documents
- **Calcul** (1 tache) : calculs de montants, stocks ou compteurs

**Donnees modifiees** : 1 tables en ecriture (tempo_heures).

**Logique metier** : 25 regles identifiees couvrant conditions metier, valeurs par defaut.

<details>
<summary>Detail : phases du traitement</summary>

#### Phase 1 : Traitement (2 taches)

- **176** - Veuillez patienter... **[[ECRAN]](#ecran-t1)**
- **176.2** - Ligne commentaire

Delegue a : [  Suppression nationalite (IDE 166)](PBP-IDE-166.md)

#### Phase 2 : Calcul (1 tache)

- **176.1** - Calcul pied

#### Phase 3 : Impression (1 tache)

- **176.3** - Edition Nationalite

#### Tables impactees

| Table | Operations | Role metier |
|-------|-----------|-------------|
| tempo_heures | **W**/L (2 usages) | Table temporaire ecran |

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Traitement (2 taches)

Traitements internes.

---

#### <a id="t1"></a>176 - Veuillez patienter... [[ECRAN]](#ecran-t1)

**Role** : Traitement : Veuillez patienter....
**Ecran** : 426 x 58 DLU (MDI) | [Voir mockup](#ecran-t1)
**Delegue a** : [  Suppression nationalite (IDE 166)](PBP-IDE-166.md)

---

#### <a id="t3"></a>176.2 - Ligne commentaire

**Role** : Traitement : Ligne commentaire.
**Delegue a** : [  Suppression nationalite (IDE 166)](PBP-IDE-166.md)


### 3.2 Calcul (1 tache)

Calculs metier : montants, stocks, compteurs.

---

#### <a id="t2"></a>176.1 - Calcul pied

**Role** : Calcul : Calcul pied.
**Variables liees** : A (>DateCalcul), Z (w0_NomPied01), BA (w0_NbPied01), BB (w0_NomPied02), BC (w0_NbPied02)


### 3.3 Impression (1 tache)

Generation des documents et tickets.

---

#### <a id="t4"></a>176.3 - Edition Nationalite

**Role** : Generation du document : Edition Nationalite.
**Variables liees** : Q (w0_LibelleEdition)


## 5. REGLES METIER

25 regles identifiees:

### Autres (25 regles)

#### <a id="rm-RM-001"></a>[RM-001] Si VG126 AND [FW] alors 'X' sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `VG126 AND [FW]` |
| **Si vrai** | 'X' |
| **Si faux** | '') |
| **Expression source** | Expression 5 : `IF (VG126 AND [FW],'X','')` |
| **Exemple** | Si VG126 AND [FW] â†’ 'X'. Sinon â†’ '') |

#### <a id="rm-RM-002"></a>[RM-002] Si >TopListe [D]='AG' OR >TopListe [D]='BB' OR >TopListe [D]='EN' alors 'Naissance' sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='AG' OR >TopListe [D]='BB' OR >TopListe [D]='EN'` |
| **Si vrai** | 'Naissance' |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 7 : `IF (>TopListe [D]='AG' OR >TopListe [D]='BB' OR >TopListe [D` |
| **Exemple** | Si >TopListe [D]='AG' OR >TopListe [D]='BB' OR >TopListe [D]='EN' â†’ 'Naissance'. Sinon â†’ '') |

#### <a id="rm-RM-003"></a>[RM-003] Si >TopListe [D]='GR' alors MlsTrans ('GROUPE') sinon IF (>TopListe [D]='CA',MlsTrans ('DATE'),MlsTrans ('DATE / HEURE')))

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='GR'` |
| **Si vrai** | MlsTrans ('GROUPE') |
| **Si faux** | IF (>TopListe [D]='CA',MlsTrans ('DATE'),MlsTrans ('DATE / HEURE'))) |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 11 : `IF (>TopListe [D]='GR',MlsTrans ('GROUPE'),IF (>TopListe [D]` |
| **Exemple** | Si >TopListe [D]='GR' â†’ MlsTrans ('GROUPE') |

#### <a id="rm-RM-004"></a>[RM-004] Si >CodeListe [C]='A' alors MlsTrans ('arrivants') sinon IF (>CodeListe [C]='V',MlsTrans ('arrivees'),IF (>CodeListe [C]='P',MlsTrans ('presents'),IF (>CodeListe [C]='D',MlsTrans ('departs'),IF (>CodeListe [C]='R',MlsTrans ('partants'),MlsTrans ('absents'))))))

| Element | Detail |
|---------|--------|
| **Condition** | `>CodeListe [C]='A'` |
| **Si vrai** | MlsTrans ('arrivants') |
| **Si faux** | IF (>CodeListe [C]='V',MlsTrans ('arrivees'),IF (>CodeListe [C]='P',MlsTrans ('presents'),IF (>CodeListe [C]='D',MlsTrans ('departs'),IF (>CodeListe [C]='R',MlsTrans ('partants'),MlsTrans ('absents')))))) |
| **Variables** | C (>CodeListe) |
| **Expression source** | Expression 22 : `IF (>CodeListe [C]='A',MlsTrans ('arrivants'),IF (>CodeListe` |
| **Exemple** | Si >CodeListe [C]='A' â†’ MlsTrans ('arrivants') |

#### <a id="rm-RM-005"></a>[RM-005] Si >TopListe [D]='PL' alors 'planning' sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='PL'` |
| **Si vrai** | 'planning' |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 23 : `IF (>TopListe [D]='PL','planning','')` |
| **Exemple** | Si >TopListe [D]='PL' â†’ 'planning'. Sinon â†’ '') |

#### <a id="rm-RM-006"></a>[RM-006] Si >TopListe [D]='RE' alors MlsTrans ('heure') sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='RE'` |
| **Si vrai** | MlsTrans ('heure') |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 24 : `IF (>TopListe [D]='RE',MlsTrans ('heure'),'')` |
| **Exemple** | Si >TopListe [D]='RE' â†’ MlsTrans ('heure'). Sinon â†’ '') |

#### <a id="rm-RM-007"></a>[RM-007] Si >TopListe [D]='CA' alors MlsTrans ('caisse') sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='CA'` |
| **Si vrai** | MlsTrans ('caisse') |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 26 : `IF (>TopListe [D]='CA',MlsTrans ('caisse'),'')` |
| **Exemple** | Si >TopListe [D]='CA' â†’ MlsTrans ('caisse'). Sinon â†’ '') |

#### <a id="rm-RM-008"></a>[RM-008] Si >TopListe [D]='MI' alors MlsTrans ('millesias') sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='MI'` |
| **Si vrai** | MlsTrans ('millesias') |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 27 : `IF (>TopListe [D]='MI',MlsTrans ('millesias'),'')` |
| **Exemple** | Si >TopListe [D]='MI' â†’ MlsTrans ('millesias'). Sinon â†’ '') |

#### <a id="rm-RM-009"></a>[RM-009] Si >TopListe [D]='BB' alors MlsTrans ('bebe') sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='BB'` |
| **Si vrai** | MlsTrans ('bebe') |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 28 : `IF (>TopListe [D]='BB',MlsTrans ('bebe'),'')` |
| **Exemple** | Si >TopListe [D]='BB' â†’ MlsTrans ('bebe'). Sinon â†’ '') |

#### <a id="rm-RM-010"></a>[RM-010] Si >TopListe [D]='EN' alors MlsTrans ('enfant') sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='EN'` |
| **Si vrai** | MlsTrans ('enfant') |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 29 : `IF (>TopListe [D]='EN',MlsTrans ('enfant'),'')` |
| **Exemple** | Si >TopListe [D]='EN' â†’ MlsTrans ('enfant'). Sinon â†’ '') |

#### <a id="rm-RM-011"></a>[RM-011] Si >TopListe [D]='SI' alors MlsTrans ('single') sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='SI'` |
| **Si vrai** | MlsTrans ('single') |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 30 : `IF (>TopListe [D]='SI',MlsTrans ('single'),'')` |
| **Exemple** | Si >TopListe [D]='SI' â†’ MlsTrans ('single'). Sinon â†’ '') |

#### <a id="rm-RM-012"></a>[RM-012] Si >TopListe [D]='NS' alors 'non single' sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='NS'` |
| **Si vrai** | 'non single' |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 31 : `IF (>TopListe [D]='NS','non single','')` |
| **Exemple** | Si >TopListe [D]='NS' â†’ 'non single'. Sinon â†’ '') |

#### <a id="rm-RM-013"></a>[RM-013] Si >TopListe [D]='PY' alors MlsTrans ('pays') sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='PY'` |
| **Si vrai** | MlsTrans ('pays') |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 32 : `IF (>TopListe [D]='PY',MlsTrans ('pays'),'')` |
| **Exemple** | Si >TopListe [D]='PY' â†’ MlsTrans ('pays'). Sinon â†’ '') |

#### <a id="rm-RM-014"></a>[RM-014] Si >TopListe [D]='HM' alors 'honey moon' sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='HM'` |
| **Si vrai** | 'honey moon' |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 33 : `IF (>TopListe [D]='HM','honey moon','')` |
| **Exemple** | Si >TopListe [D]='HM' â†’ 'honey moon'. Sinon â†’ '') |

#### <a id="rm-RM-015"></a>[RM-015] Si >TopListe [D]='VV' alors 'Vil/Vil' sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='VV'` |
| **Si vrai** | 'Vil/Vil' |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 34 : `IF (>TopListe [D]='VV','Vil/Vil','')` |
| **Exemple** | Si >TopListe [D]='VV' â†’ 'Vil/Vil'. Sinon â†’ '') |

#### <a id="rm-RM-016"></a>[RM-016] Si >TopListe [D]='NV' alors 'non Vil/Vil' sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='NV'` |
| **Si vrai** | 'non Vil/Vil' |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 35 : `IF (>TopListe [D]='NV','non Vil/Vil','')` |
| **Exemple** | Si >TopListe [D]='NV' â†’ 'non Vil/Vil'. Sinon â†’ '') |

#### <a id="rm-RM-017"></a>[RM-017] Si >TopListe [D]='AG' alors MlsTrans ('age du')&' '&Str (>AgeMin [H] sinon '2')&' / '&Str (>AgeMax [I],'2')&' '&MlsTrans ('ans'),'')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='AG'` |
| **Si vrai** | MlsTrans ('age du')&' '&Str (>AgeMin [H] |
| **Si faux** | '2')&' / '&Str (>AgeMax [I],'2')&' '&MlsTrans ('ans'),'') |
| **Variables** | D (>TopListe), H (>AgeMin), I (>AgeMax) |
| **Expression source** | Expression 36 : `IF (>TopListe [D]='AG',MlsTrans ('age du')&' '&Str (>AgeMin ` |
| **Exemple** | Si >TopListe [D]='AG' â†’ MlsTrans ('age du')&' '&Str (>AgeMin [H]. Sinon â†’ '2')&' / '&Str (>AgeMax [I],'2')&' '&MlsTrans ('ans'),'') |

#### <a id="rm-RM-018"></a>[RM-018] Si >TopListe [D]='CO' alors MlsTrans ('commentaire') sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='CO'` |
| **Si vrai** | MlsTrans ('commentaire') |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 37 : `IF (>TopListe [D]='CO',MlsTrans ('commentaire'),'')` |
| **Exemple** | Si >TopListe [D]='CO' â†’ MlsTrans ('commentaire'). Sinon â†’ '') |

#### <a id="rm-RM-019"></a>[RM-019] Si >TopListe [D]='CP' alors MlsTrans ('comptage') sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='CP'` |
| **Si vrai** | MlsTrans ('comptage') |
| **Si faux** | '') |
| **Variables** | D (>TopListe) |
| **Expression source** | Expression 38 : `IF (>TopListe [D]='CP',MlsTrans ('comptage'),'')` |
| **Exemple** | Si >TopListe [D]='CP' â†’ MlsTrans ('comptage'). Sinon â†’ '') |

#### <a id="rm-RM-020"></a>[RM-020] Si >TopListe [D]='SM' alors MlsTrans ('seminaire')&' '&>NomSeminaire [K] sinon '')

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]='SM'` |
| **Si vrai** | MlsTrans ('seminaire')&' '&>NomSeminaire [K] |
| **Si faux** | '') |
| **Variables** | D (>TopListe), K (>NomSeminaire) |
| **Expression source** | Expression 39 : `IF (>TopListe [D]='SM',MlsTrans ('seminaire')&' '&>NomSemina` |
| **Exemple** | Si >TopListe [D]='SM' â†’ MlsTrans ('seminaire')&' '&>NomSeminaire [K]. Sinon â†’ '') |

#### <a id="rm-RM-021"></a>[RM-021] Valeur par defaut si >TopListe [D]<>'CP' AND >TopListe [D]<>'GR','',IF (Trim(>CodeGroupe [J]) est vide

| Element | Detail |
|---------|--------|
| **Condition** | `>TopListe [D]<>'CP' AND >TopListe [D]<>'GR'` |
| **Si vrai** | '' |
| **Si faux** | IF (Trim(>CodeGroupe [J])='',MlsTrans ('Toutes categories'),MlsTrans ('categorie')&' '&Trim(>CodeGroupe [J]))) |
| **Variables** | D (>TopListe), J (>CodeGroupe) |
| **Expression source** | Expression 47 : `IF (>TopListe [D]<>'CP' AND >TopListe [D]<>'GR','',IF (Trim(` |
| **Exemple** | Si >TopListe [D]<>'CP' AND >TopListe [D]<>'GR' â†’ '' |

#### <a id="rm-RM-022"></a>[RM-022] Si [EP] OR [ES] OR [EY] alors 'EA'&Trim([FE])&' ' sinon Trim([FO]))&IF(VG29,CASE([EQ],'C','CRE','D','DEB','S','SET',''),'')

| Element | Detail |
|---------|--------|
| **Condition** | `[EP] OR [ES] OR [EY]` |
| **Si vrai** | 'EA'&Trim([FE])&' ' |
| **Si faux** | Trim([FO]))&IF(VG29,CASE([EQ],'C','CRE','D','DEB','S','SET',''),'') |
| **Expression source** | Expression 59 : `IF([EP] OR [ES] OR [EY],'EA'&Trim([FE])&' ',Trim([FO]))&IF(V` |
| **Exemple** | Si [EP] OR [ES] OR [EY] â†’ 'EA'&Trim([FE])&' ' |

#### <a id="rm-RM-023"></a>[RM-023] Traitement si Trim(ExpCalc('62'EXP)) est renseigne

| Element | Detail |
|---------|--------|
| **Condition** | `Trim(ExpCalc('62'EXP))<>'' AND VG114 AND Trim([FO])<>''` |
| **Si vrai** | Trim(ExpCalc('62'EXP))&'-'&Trim([FO]) |
| **Si faux** | ExpCalc('62'EXP)) |
| **Expression source** | Expression 60 : `IF(Trim(ExpCalc('62'EXP))<>'' AND VG114 AND Trim([FO])<>'',T` |
| **Exemple** | Si Trim(ExpCalc('62'EXP))<>'' AND VG114 AND Trim([FO])<>'' â†’ Trim(ExpCalc('62'EXP))&'-'&Trim([FO]). Sinon â†’ ExpCalc('62'EXP)) |

#### <a id="rm-RM-024"></a>[RM-024] Si [EP] alors Trim(VG61) sinon '')&IF([ES],Trim(VG62),'')&IF([EY],Trim(VG63),'')

| Element | Detail |
|---------|--------|
| **Condition** | `[EP]` |
| **Si vrai** | Trim(VG61) |
| **Si faux** | '')&IF([ES],Trim(VG62),'')&IF([EY],Trim(VG63),'') |
| **Expression source** | Expression 64 : `IF([EP],Trim(VG61),'')&IF([ES],Trim(VG62),'')&IF([EY],Trim(V` |
| **Exemple** | Si [EP] â†’ Trim(VG61). Sinon â†’ '')&IF([ES],Trim(VG62),'')&IF([EY],Trim(VG63),'') |

#### <a id="rm-RM-025"></a>[RM-025] Si [FJ] alors [FK]&[FL]&Str([AK] sinon '###P0'),Trim(W0_libelle logement [T])&Str([AK],'3P0'))

| Element | Detail |
|---------|--------|
| **Condition** | `[FJ]` |
| **Si vrai** | [FK]&[FL]&Str([AK] |
| **Si faux** | '###P0'),Trim(W0_libelle logement [T])&Str([AK],'3P0')) |
| **Variables** | T (W0_libelle logement) |
| **Expression source** | Expression 69 : `IF([FJ],[FK]&[FL]&Str([AK],'###P0'),Trim(W0_libelle logement` |
| **Exemple** | Si [FJ] â†’ [FK]&[FL]&Str([AK]. Sinon â†’ '###P0'),Trim(W0_libelle logement [T])&Str([AK],'3P0')) |

## 6. CONTEXTE

- **Appele par**: [  Liste CLients arrivant (IDE 156)](PBP-IDE-156.md), [  Liste Clients present (IDE 162)](PBP-IDE-162.md), [  Liste CLients depart (IDE 168)](PBP-IDE-168.md), [Liste CLients AVPBDR (IDE 174)](PBP-IDE-174.md), [  Affichage AVPBDR toutes GM (IDE 175)](PBP-IDE-175.md)
- **Appelle**: 1 programmes | **Tables**: 9 (W:1 R:3 L:6) | **Taches**: 4 | **Expressions**: 78

<!-- TAB:Ecrans -->

## 8. ECRANS

### 8.1 Forms visibles (1 / 4)

| # | Position | Tache | Nom | Type | Largeur | Hauteur | Bloc |
|---|----------|-------|-----|------|---------|---------|------|
| 1 | 176 | 176 | Veuillez patienter... | MDI | 426 | 58 | Traitement |

### 8.2 Mockups Ecrans

---

#### <a id="ecran-t1"></a>176 - Veuillez patienter...
**Tache** : [176](#t1) | **Type** : MDI | **Dimensions** : 426 x 58 DLU
**Bloc** : Traitement | **Titre IDE** : Veuillez patienter...

<!-- FORM-DATA:
{
    "width":  426,
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
                         "x":  72,
                         "type":  "label",
                         "var":  "",
                         "y":  38,
                         "w":  280,
                         "fmt":  "",
                         "name":  "",
                         "h":  8,
                         "color":  "",
                         "text":  "Edition AVPBDR",
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
    "taskId":  "176",
    "height":  58
}
-->

## 9. NAVIGATION

Ecran unique: **Veuillez patienter...**

### 9.3 Structure hierarchique (4 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **176.1** | [**Veuillez patienter...** (176)](#t1) [mockup](#ecran-t1) | MDI | 426x58 | Traitement |
| 176.1.1 | [Ligne commentaire (176.2)](#t3) | MDI | - | |
| **176.2** | [**Calcul pied** (176.1)](#t2) | MDI | - | Calcul |
| **176.3** | [**Edition Nationalite** (176.3)](#t4) | MDI | - | Impression |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([START])
    INIT[Init controles]
    SAISIE[Traitement principal]
    UPDATE[MAJ 1 tables]
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

### Tables utilisees (9)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 31 | gm-complet_______gmc |  | DB | R |   |   | 1 |
| 121 | tables_pays_ventes | Donnees de ventes | DB |   |   | L | 1 |
| 171 | commentaire______com |  | DB | R |   |   | 1 |
| 358 | import_mod |  | DB |   |   | L | 1 |
| 366 | pms_print_param |  | DB |   |   | L | 1 |
| 598 | tempo_ecr_previsions | Table temporaire ecran | TMP | R |   |   | 1 |
| 600 | tempo_heures | Table temporaire ecran | TMP |   | **W** | L | 2 |
| 619 | tempo_userlist | Table temporaire ecran | TMP |   |   | L | 1 |
| 804 | valeur_credit_bar_defaut |  | DB |   |   | L | 1 |

### Colonnes par table (2 / 4 tables avec colonnes identifiees)

<details>
<summary>Table 31 - gm-complet_______gmc (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | >DateCalcul | R | Date |
| B | >HeurePresence | R | Alpha |
| C | >CodeListe | R | Alpha |
| D | >TopListe | R | Alpha |
| E | >NomLogement | R | Alpha |
| F | >Total | R | Numeric |
| G | >NbSelect | R | Numeric |
| H | >AgeMin | R | Numeric |
| I | >AgeMax | R | Numeric |
| J | >CodeGroupe | R | Alpha |
| K | >NomSeminaire | R | Alpha |
| L | > heure debut | R | Alpha |
| M | >Grouper par filiation | R | Logical |
| N | >Libellé Sélection du Solde* | R | Unicode |
| O | >Soldé,Non_soldé,Tous | R | Unicode |
| P | P.I Départ Village | R | Logical |
| Q | w0_LibelleEdition | R | Alpha |
| R | w0_f(CodeListe) | R | Alpha |
| S | w0_g(TopListe) | R | Alpha |
| T | W0_libelle logement | R | Alpha |
| U | V.Existe ECI (Q60 Location) | R | Logical |
| V | V.Existe ECI (Q61 Cours) | R | Logical |
| W | V.Existe ECI (Q62 Enfant) | R | Logical |
| X | v Libelle affichage ECI | R | Alpha |
| Y | v. abs? | R | Logical |
| Z | w0_NomPied01 | R | Alpha |
| BA | w0_NbPied01 | R | Numeric |
| BB | w0_NomPied02 | R | Alpha |
| BC | w0_NbPied02 | R | Numeric |
| BD | w0_NomPied03 | R | Alpha |
| BE | w0_NbPied03 | R | Numeric |
| BF | w0_NomPied04 | R | Alpha |
| BG | w0_NbPied04 | R | Numeric |
| BH | w0_NomPied05 | R | Alpha |
| BI | w0_NbPied05 | R | Numeric |
| BJ | w0_TotalSelect | R | Numeric |
| BK | v.dernier n° adherent | R | Alpha |
| BL | v.Ordre de Tri | R | Alpha |

</details>

<details>
<summary>Table 171 - commentaire______com (R) - 1 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 598 - tempo_ecr_previsions (R) - 1 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| A | w1_Rupture | R | Numeric |
| B | w1_TotalSelect | R | Numeric |

</details>

<details>
<summary>Table 600 - tempo_heures (**W**/L) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Parametres entrants (1)

Variables recues du programme appelant ([  Liste CLients arrivant (IDE 156)](PBP-IDE-156.md)).

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| P | P.I Départ Village | Logical | - |

### 11.2 Variables de session (7)

Variables persistantes pendant toute la session.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| U | V.Existe ECI (Q60 Location) | Logical | - |
| V | V.Existe ECI (Q61 Cours) | Logical | - |
| W | V.Existe ECI (Q62 Enfant) | Logical | - |
| X | v Libelle affichage ECI | Alpha | - |
| Y | v. abs? | Logical | - |
| BK | v.dernier n° adherent | Alpha | - |
| BL | v.Ordre de Tri | Alpha | - |

### 11.3 Autres (30)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| A | >DateCalcul | Date | 4x refs |
| B | >HeurePresence | Alpha | 2x refs |
| C | >CodeListe | Alpha | 7x refs |
| D | >TopListe | Alpha | 29x refs |
| E | >NomLogement | Alpha | - |
| F | >Total | Numeric | - |
| G | >NbSelect | Numeric | 1x refs |
| H | >AgeMin | Numeric | 1x refs |
| I | >AgeMax | Numeric | 1x refs |
| J | >CodeGroupe | Alpha | 5x refs |
| K | >NomSeminaire | Alpha | 1x refs |
| L | > heure debut | Alpha | 1x refs |
| M | >Grouper par filiation | Logical | 1x refs |
| N | >Libellé Sélection du Solde* | Unicode | - |
| O | >Soldé,Non_soldé,Tous | Unicode | 4x refs |
| Q | w0_LibelleEdition | Alpha | 2x refs |
| R | w0_f(CodeListe) | Alpha | - |
| S | w0_g(TopListe) | Alpha | - |
| T | W0_libelle logement | Alpha | 2x refs |
| Z | w0_NomPied01 | Alpha | 1x refs |
| BA | w0_NbPied01 | Numeric | - |
| BB | w0_NomPied02 | Alpha | - |
| BC | w0_NbPied02 | Numeric | 1x refs |
| BD | w0_NomPied03 | Alpha | - |
| BE | w0_NbPied03 | Numeric | - |
| BF | w0_NomPied04 | Alpha | - |
| BG | w0_NbPied04 | Numeric | 1x refs |
| BH | w0_NomPied05 | Alpha | - |
| BI | w0_NbPied05 | Numeric | - |
| BJ | w0_TotalSelect | Numeric | - |

<details>
<summary>Toutes les 38 variables (liste complete)</summary>

| Cat | Lettre | Nom Variable | Type |
|-----|--------|--------------|------|
| P0 | **P** | P.I Départ Village | Logical |
| V. | **U** | V.Existe ECI (Q60 Location) | Logical |
| V. | **V** | V.Existe ECI (Q61 Cours) | Logical |
| V. | **W** | V.Existe ECI (Q62 Enfant) | Logical |
| V. | **X** | v Libelle affichage ECI | Alpha |
| V. | **Y** | v. abs? | Logical |
| V. | **BK** | v.dernier n° adherent | Alpha |
| V. | **BL** | v.Ordre de Tri | Alpha |
| Autre | **A** | >DateCalcul | Date |
| Autre | **B** | >HeurePresence | Alpha |
| Autre | **C** | >CodeListe | Alpha |
| Autre | **D** | >TopListe | Alpha |
| Autre | **E** | >NomLogement | Alpha |
| Autre | **F** | >Total | Numeric |
| Autre | **G** | >NbSelect | Numeric |
| Autre | **H** | >AgeMin | Numeric |
| Autre | **I** | >AgeMax | Numeric |
| Autre | **J** | >CodeGroupe | Alpha |
| Autre | **K** | >NomSeminaire | Alpha |
| Autre | **L** | > heure debut | Alpha |
| Autre | **M** | >Grouper par filiation | Logical |
| Autre | **N** | >Libellé Sélection du Solde* | Unicode |
| Autre | **O** | >Soldé,Non_soldé,Tous | Unicode |
| Autre | **Q** | w0_LibelleEdition | Alpha |
| Autre | **R** | w0_f(CodeListe) | Alpha |
| Autre | **S** | w0_g(TopListe) | Alpha |
| Autre | **T** | W0_libelle logement | Alpha |
| Autre | **Z** | w0_NomPied01 | Alpha |
| Autre | **BA** | w0_NbPied01 | Numeric |
| Autre | **BB** | w0_NomPied02 | Alpha |
| Autre | **BC** | w0_NbPied02 | Numeric |
| Autre | **BD** | w0_NomPied03 | Alpha |
| Autre | **BE** | w0_NbPied03 | Numeric |
| Autre | **BF** | w0_NomPied04 | Alpha |
| Autre | **BG** | w0_NbPied04 | Numeric |
| Autre | **BH** | w0_NomPied05 | Alpha |
| Autre | **BI** | w0_NbPied05 | Numeric |
| Autre | **BJ** | w0_TotalSelect | Numeric |

</details>

## 12. EXPRESSIONS

**78 / 78 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONCATENATION | 13 | 3 |
| CALCULATION | 1 | 0 |
| CONDITION | 43 | 22 |
| CONSTANTE | 4 | 0 |
| FORMAT | 2 | 0 |
| REFERENCE_VG | 5 | 0 |
| OTHER | 10 | 0 |

### 12.2 Expressions cles par type

#### CONCATENATION (13 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONCATENATION | 39 | `IF (>TopListe [D]='SM',MlsTrans ('seminaire')&' '&>NomSeminaire [K],'')` | [RM-020](#rm-RM-020) |
| CONCATENATION | 36 | `IF (>TopListe [D]='AG',MlsTrans ('age du')&' '&Str (>AgeMin [H],'2')&' / '&Str (>AgeMax [I],'2')&' '&MlsTrans ('ans'),'')` | [RM-017](#rm-RM-017) |
| CONCATENATION | 47 | `IF (>TopListe [D]<>'CP' AND >TopListe [D]<>'GR','',IF (Trim(>CodeGroupe [J])='',MlsTrans ('Toutes categories'),MlsTrans ('categorie')&' '&Trim(>CodeGroupe [J])))` | [RM-021](#rm-RM-021) |
| CONCATENATION | 72 | `MlsTrans('Heure de fin :')&' '&MlsTrans(IF(VG88 AND [FN], 'Libération logement','Départ Village'))` | - |
| CONCATENATION | 46 | `MlsTrans ('Depart le')&' '&DStr ([AB],'DD/MM/YYYY')&' '&MlsTrans ('à')&' '&[AC]&'  '&MlsTrans ('Retour le')&'  '&DStr ([AD],'DD/MM/YYYY')&' '&MlsTrans ('à')&' '&[AE]` | - |
| ... | | *+8 autres* | |

#### CALCULATION (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CALCULATION | 54 | `w0_NbPied04 [BG]+1` | - |

#### CONDITION (43 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 32 | `IF (>TopListe [D]='PY',MlsTrans ('pays'),'')` | [RM-013](#rm-RM-013) |
| CONDITION | 33 | `IF (>TopListe [D]='HM','honey moon','')` | [RM-014](#rm-RM-014) |
| CONDITION | 34 | `IF (>TopListe [D]='VV','Vil/Vil','')` | [RM-015](#rm-RM-015) |
| CONDITION | 29 | `IF (>TopListe [D]='EN',MlsTrans ('enfant'),'')` | [RM-010](#rm-RM-010) |
| CONDITION | 30 | `IF (>TopListe [D]='SI',MlsTrans ('single'),'')` | [RM-011](#rm-RM-011) |
| ... | | *+38 autres* | |

#### CONSTANTE (4 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONSTANTE | 62 | `61` | - |
| CONSTANTE | 63 | `62` | - |
| CONSTANTE | 53 | `'PNT'` | - |
| CONSTANTE | 61 | `60` | - |

#### FORMAT (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| FORMAT | 68 | `DStr([AD],'DD/MM/YYYY')&' '&
IF(NOT VG88 OR NOT [FN],[AE],TStr([FM],'HHhMMZ'))` | - |
| FORMAT | 67 | `DStr([AB],'DD/MM/YYYY')&' '&[AC]` | - |

#### REFERENCE_VG (5 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| REFERENCE_VG | 65 | `VG5` | - |
| REFERENCE_VG | 73 | `VG88` | - |
| REFERENCE_VG | 52 | `VG1` | - |
| REFERENCE_VG | 4 | `VG126` | - |
| REFERENCE_VG | 17 | `VG1` | - |

#### OTHER (10 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 55 | `w0_LibelleEdition [Q]` | - |
| OTHER | 18 | `Counter (0)` | - |
| OTHER | 56 | `w0_NomPied01 [Z]` | - |
| OTHER | 70 | `Left([AA],12)` | - |
| OTHER | 57 | `w0_NbPied02 [BC]` | - |
| ... | | *+5 autres* | |

### 12.3 Toutes les expressions (78)

<details>
<summary>Voir les 78 expressions</summary>

#### CONCATENATION (13)

| IDE | Expression Decodee |
|-----|-------------------|
| 48 | `'- '&Str (Page (0,1),'3P0Z0')&' -'` |
| 36 | `IF (>TopListe [D]='AG',MlsTrans ('age du')&' '&Str (>AgeMin [H],'2')&' / '&Str (>AgeMax [I],'2')&' '&MlsTrans ('ans'),'')` |
| 39 | `IF (>TopListe [D]='SM',MlsTrans ('seminaire')&' '&>NomSeminaire [K],'')` |
| 47 | `IF (>TopListe [D]<>'CP' AND >TopListe [D]<>'GR','',IF (Trim(>CodeGroupe [J])='',MlsTrans ('Toutes categories'),MlsTrans ('categorie')&' '&Trim(>CodeGroupe [J])))` |
| 41 | `MlsTrans ('Liste des')&' '&Trim (>Libellé Sélection du ... [N])&' '&Trim (>Soldé,Non_soldé,Tous [O])&' '&IF (>TopListe [D]='CP' OR >TopListe [D]='GR',Trim (>CodeGroupe [J]),'')&IF (>TopListe [D]='GR',' '&>HeurePresence [B]&' h','')&' '&MlsTrans ('le')&' '&DStr (>DateCalcul [A],'DD/MM/YYYY')` |
| 42 | `MlsTrans ('Liste des')&' '&Trim (>Libellé Sélection du ... [N])&' '&Trim (>Soldé,Non_soldé,Tous [O])&' '&IF (>TopListe [D]='RE',> heure debut [L]&' h ',IF (>TopListe [D]='CP' OR >TopListe [D]='GR',MlsTrans ('Toutes categories')&' ',''))&MlsTrans ('le')&' '&DStr (>DateCalcul [A],'DD/MM/YYYY')` |
| 43 | `MlsTrans ('Liste des')&' '&Trim (>Libellé Sélection du ... [N])&' '&Trim (>Soldé,Non_soldé,Tous [O])&' '&IF (>TopListe [D]='CP' OR >TopListe [D]='GR',Trim(>CodeGroupe [J]),'')&' '&MlsTrans ('le')&' '&DStr (>DateCalcul [A],'DD/MM/YYYY')` |
| 45 | `MlsTrans ('Edition du')&' '&DStr (Date (),'DD/MM/YYYY')&' '&MlsTrans ('à')&' '&TStr (Time (),'HH:MM:SS')` |
| 46 | `MlsTrans ('Depart le')&' '&DStr ([AB],'DD/MM/YYYY')&' '&MlsTrans ('à')&' '&[AC]&'  '&MlsTrans ('Retour le')&'  '&DStr ([AD],'DD/MM/YYYY')&' '&MlsTrans ('à')&' '&[AE]` |
| 72 | `MlsTrans('Heure de fin :')&' '&MlsTrans(IF(VG88 AND [FN], 'Libération logement','Départ Village'))` |
| 44 | `Trim (>Grouper par filiation [M])&' '&IF (>CodeListe [C]='P',>HeurePresence [B]&' h','')` |
| 58 | `Trim([ER])&IF(VG125 AND [FV]='O','N','')` |
| 66 | `Trim(W0_libelle logement [T])&' '&Trim(V.Existe ECI (Q60 Loca... [U])` |

#### CALCULATION (1)

| IDE | Expression Decodee |
|-----|-------------------|
| 54 | `w0_NbPied04 [BG]+1` |

#### CONDITION (43)

| IDE | Expression Decodee |
|-----|-------------------|
| 5 | `IF (VG126 AND [FW],'X','')` |
| 7 | `IF (>TopListe [D]='AG' OR >TopListe [D]='BB' OR >TopListe [D]='EN','Naissance','')` |
| 11 | `IF (>TopListe [D]='GR',MlsTrans ('GROUPE'),IF (>TopListe [D]='CA',MlsTrans ('DATE'),MlsTrans ('DATE / HEURE')))` |
| 12 | `IF (>TopListe [D]='GR',MlsTrans ('DEPART'),IF (>TopListe [D]='CA',MlsTrans ('FERMETURE'),MlsTrans ('DEPART')))` |
| 13 | `IF (>TopListe [D]='GR',MlsTrans ('GROUPE'),IF (>TopListe [D]='CA',MlsTrans ('DATE'),MlsTrans ('DATE / HEURE')))` |
| 14 | `IF (>TopListe [D]='GR',MlsTrans ('ARRIVEE'),IF (>TopListe [D]='CA',MlsTrans ('OUVERTURE'),MlsTrans ('ARRIVEE')))` |
| 22 | `IF (>CodeListe [C]='A',MlsTrans ('arrivants'),IF (>CodeListe [C]='V',MlsTrans ('arrivees'),IF (>CodeListe [C]='P',MlsTrans ('presents'),IF (>CodeListe [C]='D',MlsTrans ('departs'),IF (>CodeListe [C]='R',MlsTrans ('partants'),MlsTrans ('absents'))))))` |
| 23 | `IF (>TopListe [D]='PL','planning','')` |
| 24 | `IF (>TopListe [D]='RE',MlsTrans ('heure'),'')` |
| 25 | `IF (>TopListe [D]='GR',MlsTrans ('vol'),'')` |
| 26 | `IF (>TopListe [D]='CA',MlsTrans ('caisse'),'')` |
| 27 | `IF (>TopListe [D]='MI',MlsTrans ('millesias'),'')` |
| 28 | `IF (>TopListe [D]='BB',MlsTrans ('bebe'),'')` |
| 29 | `IF (>TopListe [D]='EN',MlsTrans ('enfant'),'')` |
| 30 | `IF (>TopListe [D]='SI',MlsTrans ('single'),'')` |
| 31 | `IF (>TopListe [D]='NS','non single','')` |
| 32 | `IF (>TopListe [D]='PY',MlsTrans ('pays'),'')` |
| 33 | `IF (>TopListe [D]='HM','honey moon','')` |
| 34 | `IF (>TopListe [D]='VV','Vil/Vil','')` |
| 35 | `IF (>TopListe [D]='NV','non Vil/Vil','')` |
| 37 | `IF (>TopListe [D]='CO',MlsTrans ('commentaire'),'')` |
| 38 | `IF (>TopListe [D]='CP',MlsTrans ('comptage'),'')` |
| 59 | `IF([EP] OR [ES] OR [EY],'EA'&Trim([FE])&' ',Trim([FO]))&IF(VG29,CASE([EQ],'C','CRE','D','DEB','S','SET',''),'')` |
| 60 | `IF(Trim(ExpCalc('62'EXP))<>'' AND VG114 AND Trim([FO])<>'',Trim(ExpCalc('62'EXP))&'-'&Trim([FO]),ExpCalc('62'EXP))` |
| 64 | `IF([EP],Trim(VG61),'')&IF([ES],Trim(VG62),'')&IF([EY],Trim(VG63),'')` |
| 69 | `IF([FJ],[FK]&[FL]&Str([AK],'###P0'),Trim(W0_libelle logement [T])&Str([AK],'3P0'))` |
| 1 | `>CodeListe [C]='P'` |
| 6 | `>TopListe [D]='AG' OR >TopListe [D]='BB' OR >TopListe [D]='EN'` |
| 19 | `[AO]=''` |
| 20 | `[AO]='' AND >TopListe [D]='CO'` |
| 21 | `[AO]='CIRCUIT'` |
| 40 | `>Soldé,Non_soldé,Tous [O]=''` |
| 49 | `INIGet ('[MAGIC_LOGICAL_NAMES]preview')='O'` |
| 50 | `>NbSelect [G]>0` |
| 51 | `[AI]<>'H' OR >TopListe [D]='CP'` |
| 74 | `>DateCalcul [A]` |
| 75 | `>CodeListe [C]='B' AND [FU]` |
| 76 | `>CodeListe [C]='B'` |
| 78 | `[FZ]='T'` |
| 2 | `>CodeListe [C]<>'P' AND Trim(>CodeGroupe [J])<>''` |
| 3 | `>CodeListe [C]<>'P' AND Trim(>CodeGroupe [J])=''` |
| 71 | `[FJ] AND Left([AA],12)<>Trim([FI])AND Counter(0)>1` |
| 77 | `CndRange(Trim([FY])<>'' AND [FZ]<>'T',IF([FZ]='N','X',''))` |

#### CONSTANTE (4)

| IDE | Expression Decodee |
|-----|-------------------|
| 53 | `'PNT'` |
| 61 | `60` |
| 62 | `61` |
| 63 | `62` |

#### FORMAT (2)

| IDE | Expression Decodee |
|-----|-------------------|
| 67 | `DStr([AB],'DD/MM/YYYY')&' '&[AC]` |
| 68 | `DStr([AD],'DD/MM/YYYY')&' '&
IF(NOT VG88 OR NOT [FN],[AE],TStr([FM],'HHhMMZ'))` |

#### REFERENCE_VG (5)

| IDE | Expression Decodee |
|-----|-------------------|
| 4 | `VG126` |
| 17 | `VG1` |
| 52 | `VG1` |
| 65 | `VG5` |
| 73 | `VG88` |

#### OTHER (10)

| IDE | Expression Decodee |
|-----|-------------------|
| 8 | `w0_LibelleEdition [Q]` |
| 9 | `[AJ]` |
| 10 | `[AK]` |
| 15 | `GetParam ('SOCIETE')` |
| 16 | `'Village '&GetParam ('VILLAGE')` |
| 18 | `Counter (0)` |
| 55 | `w0_LibelleEdition [Q]` |
| 56 | `w0_NomPied01 [Z]` |
| 57 | `w0_NbPied02 [BC]` |
| 70 | `Left([AA],12)` |

</details>

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [  Liste CLients arrivant (IDE 156)](PBP-IDE-156.md) -> **Imprim AVPBDR toutes GM (IDE 176)**

Main -> ... -> [  Liste Clients present (IDE 162)](PBP-IDE-162.md) -> **Imprim AVPBDR toutes GM (IDE 176)**

Main -> ... -> [  Liste CLients depart (IDE 168)](PBP-IDE-168.md) -> **Imprim AVPBDR toutes GM (IDE 176)**

Main -> ... -> [Liste CLients AVPBDR (IDE 174)](PBP-IDE-174.md) -> **Imprim AVPBDR toutes GM (IDE 176)**

Main -> ... -> [  Affichage AVPBDR toutes GM (IDE 175)](PBP-IDE-175.md) -> **Imprim AVPBDR toutes GM (IDE 176)**

```mermaid
graph LR
    T176[176 Imprim AVPBDR tout...]
    style T176 fill:#58a6ff
    CC161[161 Liste des presents]
    style CC161 fill:#8b5cf6
    CC173[173 Liste des Absents]
    style CC173 fill:#8b5cf6
    CC167[167 Liste des departs]
    style CC167 fill:#8b5cf6
    CC172[172 Liste des partants]
    style CC172 fill:#8b5cf6
    CC160[160 Liste des arrivees]
    style CC160 fill:#8b5cf6
    CC155[155 Liste des arrivants]
    style CC155 fill:#8b5cf6
    CC162[162 Liste Clients present]
    style CC162 fill:#3fb950
    CC156[156 Liste CLients arri...]
    style CC156 fill:#3fb950
    CC175[175 Affichage AVPBDR t...]
    style CC175 fill:#3fb950
    CC174[174 Liste CLients AVPBDR]
    style CC174 fill:#3fb950
    CC168[168 Liste CLients depart]
    style CC168 fill:#3fb950
    CC155 --> CC156
    CC161 --> CC156
    CC167 --> CC156
    CC160 --> CC156
    CC172 --> CC156
    CC173 --> CC156
    CC155 --> CC162
    CC161 --> CC162
    CC167 --> CC162
    CC160 --> CC162
    CC172 --> CC162
    CC173 --> CC162
    CC155 --> CC168
    CC161 --> CC168
    CC167 --> CC168
    CC160 --> CC168
    CC172 --> CC168
    CC173 --> CC168
    CC155 --> CC174
    CC161 --> CC174
    CC167 --> CC174
    CC160 --> CC174
    CC172 --> CC174
    CC173 --> CC174
    CC155 --> CC175
    CC161 --> CC175
    CC167 --> CC175
    CC160 --> CC175
    CC172 --> CC175
    CC173 --> CC175
    CC156 --> T176
    CC162 --> T176
    CC168 --> T176
    CC174 --> T176
    CC175 --> T176
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [156](PBP-IDE-156.md) |   Liste CLients arrivant | 1 |
| [162](PBP-IDE-162.md) |   Liste Clients present | 1 |
| [168](PBP-IDE-168.md) |   Liste CLients depart | 1 |
| [174](PBP-IDE-174.md) | Liste CLients AVPBDR | 1 |
| [175](PBP-IDE-175.md) |   Affichage AVPBDR toutes GM | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T176[176 Imprim AVPBDR tout...]
    style T176 fill:#58a6ff
    C166[166 Suppression nation...]
    T176 --> C166
    style C166 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [166](PBP-IDE-166.md) |   Suppression nationalite | 1 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 235 | Taille moyenne |
| Expressions | 78 | Logique moderee |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 1 | Peu de dependances |
| Ecrans visibles | 1 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 235) | Code sain |
| Regles metier | 25 | Logique metier riche |

### 14.2 Plan de migration par bloc

#### Traitement (2 taches: 1 ecran, 1 traitement)

- **Strategie** : Orchestrateur avec 1 ecrans (Razor/React) et 1 traitements backend (services).
- Les ecrans deviennent des composants UI, les traitements invisibles deviennent des services injectables.
- 1 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Calcul (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Services de calcul purs (Domain Services).
- Migrer la logique de calcul (stock, compteurs, montants)

#### Impression (1 tache: 0 ecran, 1 traitement)

- **Strategie** : Templates HTML -> PDF via wkhtmltopdf ou Puppeteer.
- `PrintService` injectable avec choix imprimante

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| tempo_heures | Table WRITE (Temp) | 1x | Schema + repository |
| [  Suppression nationalite (IDE 166)](PBP-IDE-166.md) | Sous-programme | 1x | Normale - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-03 15:39*
