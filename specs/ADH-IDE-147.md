# ADH IDE 147 - Devises des tickets WS

> **Analyse**: Phases 1-4 2026-02-23 18:22 -> 18:22 (1s) | Assemblage 12:26
> **Pipeline**: V7.2 Enrichi
> **Structure**: 4 onglets (Resume | Ecrans | Donnees | Connexions)

<!-- TAB:Resume -->

## 1. FICHE D'IDENTITE

| Attribut | Valeur |
|----------|--------|
| Projet | ADH |
| IDE Position | 147 |
| Nom Programme | Devises des tickets WS |
| Fichier source | `Prg_147.xml` |
| Dossier IDE | Change |
| Taches | 14 (0 ecrans visibles) |
| Tables modifiees | 1 |
| Programmes appeles | 1 |
| Complexite | **BASSE** (score 19/100) |

## 2. DESCRIPTION FONCTIONNELLE

**Devises des tickets WS** enregistre les informations multi-devise associees aux tickets de webservices lors des operations de caisse. Appele par les flux d'ouverture ([IDE 122](ADH-IDE-122.md), [IDE 297](ADH-IDE-297.md)) et de fermeture ([IDE 131](ADH-IDE-131.md), [IDE 299](ADH-IDE-299.md)), il cree des enregistrements temporaires dans pv_invoiceprintfiliationtmp. Programme sans ecran (14 taches), delegue les calculs a [Devises finales F/F Qte WS (IDE 145)](ADH-IDE-145.md).

### Contexte ticket ouverture

La branche ouverture (147.2) applique la devise de la session courante (147.3, variables EO = devise locale, EP = session, ES = quantite) puis cree les enregistrements temporaires correspondants. Le sous-programme [IDE 145](ADH-IDE-145.md) est appele pour recuperer les quantites et montants finalises par devise.

<details>
<summary>3 taches : 147.2, 147.3, 147.4</summary>

- **147.2** - Ticket ouverture (branche ouverture caisse)
- **147.3** - Avec devise session (applique devise EO, session EP)
- **147.4** - Creation enregistrement ouverture (ecrit pv_invoiceprintfiliationtmp)

</details>

### Contexte ticket fermeture

La branche fermeture (147.5) est plus complexe : elle traite d'abord la devise session (147.6), puis gere le contexte historique devise (147.8). Les soldes de fermeture sont calcules en plusieurs passes (147.10, 147.11, 147.13) avec un total consolide (147.12, 147.14). Chaque passe delegue a [IDE 145](ADH-IDE-145.md) pour garantir la coherence des montants multi-devise.

<details>
<summary>8 taches : 147.5, 147.6, 147.7, 147.8, 147.9, 147.10, 147.11, 147.12</summary>

- **147.5** - Ticket fermeture (branche fermeture caisse)
- **147.6** - Avec devise session (applique devise EO, session EP pour fermeture)
- **147.7** - Creation enregistrement fermeture
- **147.8** - Avec histo devise (contexte devise historique)
- **147.9** - Creation enregistrement histo
- **147.10** - Solde fermeture (calcul solde devise)
- **147.11** - Solde fermeture (calcul solde histo)
- **147.12** - Total solde final (consolidation multi-devise)

</details>

### Creation des enregistrements temporaires

Les 3 taches de creation (147.4, 147.7, 147.9) ecrivent dans la table pv_invoiceprintfiliationtmp en mode Create. Ces enregistrements temporaires servent de source de verite pour les editions et rapports de cloture, assurant la tracabilite multi-devise du point de vente.

<details>
<summary>3 taches : 147.4, 147.7, 147.9</summary>

- **147.4** - Creation ticket ouverture (ecrit pv_invoiceprintfiliationtmp)
- **147.7** - Creation ticket fermeture (ecrit pv_invoiceprintfiliationtmp)
- **147.9** - Creation ticket histo devise (ecrit pv_invoiceprintfiliationtmp)

</details>

## 3. BLOCS FONCTIONNELS

### 3.1 Impression (3 taches)

Generation des documents et tickets.

---

#### <a id="t1"></a>T1 - Devises des tickets WS

**Role** : Generation du document : Devises des tickets WS.
**Delegue a** : [Devises finales F/F Qte WS (IDE 145)](ADH-IDE-145.md)

---

#### <a id="t2"></a>T2 - Ticket ouverture

**Role** : Generation du document : Ticket ouverture.

---

#### <a id="t5"></a>T5 - Ticket fermeture

**Role** : Generation du document : Ticket fermeture.


### 3.2 Traitement (8 taches)

Traitements internes.

---

#### <a id="t3"></a>T3 - Avec devise session

**Role** : Traitement : Avec devise session.
**Variables liees** : EO (Param devise locale), EP (Param N° session), ES (Quantite devise)
**Delegue a** : [Devises finales F/F Qte WS (IDE 145)](ADH-IDE-145.md)

---

#### <a id="t6"></a>T6 - Avec devise session

**Role** : Traitement : Avec devise session.
**Variables liees** : EO (Param devise locale), EP (Param N° session), ES (Quantite devise)
**Delegue a** : [Devises finales F/F Qte WS (IDE 145)](ADH-IDE-145.md)

---

#### <a id="t8"></a>T8 - Avec histo devise

**Role** : Traitement : Avec histo devise.
**Variables liees** : EO (Param devise locale), ES (Quantite devise)
**Delegue a** : [Devises finales F/F Qte WS (IDE 145)](ADH-IDE-145.md)

---

#### <a id="t10"></a>T10 - Solde fermeture

**Role** : Consultation/chargement : Solde fermeture.
**Delegue a** : [Devises finales F/F Qte WS (IDE 145)](ADH-IDE-145.md)

---

#### <a id="t11"></a>T11 - Solde fermeture

**Role** : Consultation/chargement : Solde fermeture.
**Delegue a** : [Devises finales F/F Qte WS (IDE 145)](ADH-IDE-145.md)

---

#### <a id="t12"></a>T12 - Total solde final

**Role** : Consultation/chargement : Total solde final.
**Delegue a** : [Devises finales F/F Qte WS (IDE 145)](ADH-IDE-145.md)

---

#### <a id="t13"></a>T13 - Solde fermeture

**Role** : Consultation/chargement : Solde fermeture.
**Delegue a** : [Devises finales F/F Qte WS (IDE 145)](ADH-IDE-145.md)

---

#### <a id="t14"></a>T14 - Total solde final

**Role** : Consultation/chargement : Total solde final.
**Delegue a** : [Devises finales F/F Qte WS (IDE 145)](ADH-IDE-145.md)


### 3.3 Creation (3 taches)

Insertion de nouveaux enregistrements en base.

---

#### <a id="t4"></a>T4 - Creation

**Role** : Creation d'enregistrement : Creation.

---

#### <a id="t7"></a>T7 - Creation

**Role** : Creation d'enregistrement : Creation.

---

#### <a id="t9"></a>T9 - creation

**Role** : Creation d'enregistrement : creation.


## 5. REGLES METIER

2 regles identifiees:

### Autres (2 regles)

#### <a id="rm-RM-001"></a>[RM-001] Condition: Param Quand [D] egale 'O'

| Element | Detail |
|---------|--------|
| **Condition** | `Param Quand [D]='O'` |
| **Si vrai** | Action si vrai |
| **Variables** | EQ (Param Quand) |
| **Expression source** | Expression 1 : `Param Quand [D]='O'` |
| **Exemple** | Si Param Quand [D]='O' â†’ Action si vrai |

#### <a id="rm-RM-002"></a>[RM-002] Condition: Param Quand [D] egale 'F'

| Element | Detail |
|---------|--------|
| **Condition** | `Param Quand [D]='F'` |
| **Si vrai** | Action si vrai |
| **Variables** | EQ (Param Quand) |
| **Expression source** | Expression 2 : `Param Quand [D]='F'` |
| **Exemple** | Si Param Quand [D]='F' â†’ Action si vrai |

## 6. CONTEXTE

- **Appele par**: [Fermeture caisse (IDE 131)](ADH-IDE-131.md), [Fermeture caisse 144 (IDE 299)](ADH-IDE-299.md), [Ouverture caisse (IDE 122)](ADH-IDE-122.md), [Ouverture caisse 143 (IDE 297)](ADH-IDE-297.md)
- **Appelle**: 1 programmes | **Tables**: 5 (W:1 R:4 L:4) | **Taches**: 14 | **Expressions**: 3

<!-- TAB:Ecrans -->

## 8. ECRANS

*(Programme sans ecran visible)*

## 9. NAVIGATION

### 9.3 Structure hierarchique (14 taches)

| Position | Tache | Type | Dimensions | Bloc |
|----------|-------|------|------------|------|
| **147.1** | [**Devises des tickets WS** (T1)](#t1) | MDI | - | Impression |
| 147.1.1 | [Ticket ouverture (T2)](#t2) | MDI | - | |
| 147.1.2 | [Ticket fermeture (T5)](#t5) | MDI | - | |
| **147.2** | [**Avec devise session** (T3)](#t3) | MDI | - | Traitement |
| 147.2.1 | [Avec devise session (T6)](#t6) | MDI | - | |
| 147.2.2 | [Avec histo devise (T8)](#t8) | MDI | - | |
| 147.2.3 | [Solde fermeture (T10)](#t10) | MDI | - | |
| 147.2.4 | [Solde fermeture (T11)](#t11) | MDI | - | |
| 147.2.5 | [Total solde final (T12)](#t12) | MDI | - | |
| 147.2.6 | [Solde fermeture (T13)](#t13) | MDI | - | |
| 147.2.7 | [Total solde final (T14)](#t14) | MDI | - | |
| **147.3** | [**Creation** (T4)](#t4) | MDI | - | Creation |
| 147.3.1 | [Creation (T7)](#t7) | MDI | - | |
| 147.3.2 | [creation (T9)](#t9) | MDI | - | |

### 9.4 Algorigramme

```mermaid
flowchart TD
    START([Appel depuis caisse])
    CTXTYPE{Ouverture ou Fermeture}
    DEVSESS1[Devise session ouverture]
    CREATEOUV[Creer enreg ouverture]
    DEVSESS2[Devise session fermeture]
    CREATEFERM[Creer enreg fermeture]
    HISTODEV[Devise historique]
    CREATEHIST[Creer enreg histo]
    SOLDES[Calcul soldes devise]
    TOTAL[Total solde consolide]
    ENDOK([Fin OK])

    START --> CTXTYPE
    CTXTYPE -->|Ouverture| DEVSESS1
    DEVSESS1 --> CREATEOUV
    CREATEOUV --> ENDOK
    CTXTYPE -->|Fermeture| DEVSESS2
    DEVSESS2 --> CREATEFERM
    CREATEFERM --> HISTODEV
    HISTODEV --> CREATEHIST
    CREATEHIST --> SOLDES
    SOLDES --> TOTAL
    TOTAL --> ENDOK

    style START fill:#3fb950,color:#000
    style ENDOK fill:#3fb950,color:#000
    style CTXTYPE fill:#58a6ff,color:#000
    style CREATEOUV fill:#ffeb3b,color:#000
    style CREATEFERM fill:#ffeb3b,color:#000
    style CREATEHIST fill:#ffeb3b,color:#000
    style TOTAL fill:#ffeb3b,color:#000
```

> **Legende**: Vert = START/END OK | Jaune = Flux devises WS | Bleu = Decisions

| Noeud | Source | Justification |
|-------|--------|---------------|
| CTXTYPE | Tache 147.1 | Branchement ouverture (147.2) vs fermeture (147.5) |
| DEVSESS1 | Tache 147.3 | Applique devise session EO pour ouverture |
| CREATEOUV | Tache 147.4 | Ecrit pv_invoiceprintfiliationtmp (ouverture) |
| DEVSESS2 | Tache 147.6 | Applique devise session EO pour fermeture |
| CREATEFERM | Tache 147.7 | Ecrit pv_invoiceprintfiliationtmp (fermeture) |
| HISTODEV | Tache 147.8 | Contexte devise historique |
| CREATEHIST | Tache 147.9 | Ecrit pv_invoiceprintfiliationtmp (histo) |
| SOLDES | Taches 147.10-147.11 | Calcul soldes par devise via IDE 145 |
| TOTAL | Taches 147.12-147.14 | Consolidation totaux multi-devise |

<!-- TAB:Donnees -->

## 10. TABLES

### Tables utilisees (5)

| ID | Nom | Description | Type | R | W | L | Usages |
|----|-----|-------------|------|---|---|---|--------|
| 513 | pv_invoiceprintfiliationtmp | Services / filieres | TMP |   | **W** | L | 6 |
| 232 | gestion_devise_session | Sessions de caisse | DB | R |   | L | 3 |
| 139 | moyens_reglement_mor | Reglements / paiements | DB | R |   | L | 2 |
| 250 | histo_sessions_caisse_devise | Sessions de caisse | DB | R |   | L | 2 |
| 50 | moyens_reglement_mor | Reglements / paiements | DB | R |   |   | 2 |

### Colonnes par table (2 / 5 tables avec colonnes identifiees)

<details>
<summary>Table 513 - pv_invoiceprintfiliationtmp (**W**/L) - 6 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 232 - gestion_devise_session (R/L) - 3 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| EO | Param devise locale | R | Alpha |
| EP | Param N° session | R | Numeric |
| ES | Quantite devise | R | Numeric |

</details>

<details>
<summary>Table 139 - moyens_reglement_mor (R/L) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

<details>
<summary>Table 250 - histo_sessions_caisse_devise (R/L) - 2 usages</summary>

| Lettre | Variable | Acces | Type |
|--------|----------|-------|------|
| EO | Param devise locale | R | Alpha |
| ES | Quantite devise | R | Numeric |

</details>

<details>
<summary>Table 50 - moyens_reglement_mor (R) - 2 usages</summary>

*Table utilisee uniquement en Link ou aucune colonne Real identifiee dans le DataView.*

</details>

## 11. VARIABLES

### 11.1 Autres (6)

Variables diverses.

| Lettre | Nom | Type | Usage dans |
|--------|-----|------|-----------|
| EN | Param societe | Alpha | - |
| EO | Param devise locale | Alpha | - |
| EP | Param N° session | Numeric | - |
| EQ | Param Quand | Alpha | 2x refs |
| ER | Param UNI/BI | Alpha | - |
| ES | Quantite devise | Numeric | - |

## 12. EXPRESSIONS

**3 / 3 expressions decodees (100%)**

### 12.1 Repartition par type

| Type | Expressions | Regles |
|------|-------------|--------|
| CONDITION | 2 | 2 |
| OTHER | 1 | 0 |

### 12.2 Expressions cles par type

#### CONDITION (2 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| CONDITION | 2 | `Param Quand [D]='F'` | [RM-002](#rm-RM-002) |
| CONDITION | 1 | `Param Quand [D]='O'` | [RM-001](#rm-RM-001) |

#### OTHER (1 expressions)

| Type | IDE | Expression | Regle |
|------|-----|------------|-------|
| OTHER | 3 | `DbDel ('{513,4}'DSOURCE,'')` | - |

<!-- TAB:Connexions -->

## 13. GRAPHE D'APPELS

### 13.1 Chaine depuis Main (Callers)

Main -> ... -> [Fermeture caisse (IDE 131)](ADH-IDE-131.md) -> **Devises des tickets WS (IDE 147)**

Main -> ... -> [Fermeture caisse 144 (IDE 299)](ADH-IDE-299.md) -> **Devises des tickets WS (IDE 147)**

Main -> ... -> [Ouverture caisse (IDE 122)](ADH-IDE-122.md) -> **Devises des tickets WS (IDE 147)**

Main -> ... -> [Ouverture caisse 143 (IDE 297)](ADH-IDE-297.md) -> **Devises des tickets WS (IDE 147)**

```mermaid
graph LR
    T147[147 Devises des ticket...]
    style T147 fill:#58a6ff
    CC1[1 Main Program]
    style CC1 fill:#8b5cf6
    CC163[163 Menu caisse GM - s...]
    style CC163 fill:#f59e0b
    CC281[281 Fermeture Sessions]
    style CC281 fill:#f59e0b
    CC298[298 Gestion caisse 142]
    style CC298 fill:#f59e0b
    CC121[121 Gestion caisse]
    style CC121 fill:#f59e0b
    CC131[131 Fermeture caisse]
    style CC131 fill:#3fb950
    CC122[122 Ouverture caisse]
    style CC122 fill:#3fb950
    CC299[299 Fermeture caisse 144]
    style CC299 fill:#3fb950
    CC297[297 Ouverture caisse 143]
    style CC297 fill:#3fb950
    CC121 --> CC122
    CC298 --> CC122
    CC121 --> CC131
    CC298 --> CC131
    CC121 --> CC297
    CC298 --> CC297
    CC121 --> CC299
    CC298 --> CC299
    CC163 --> CC121
    CC281 --> CC121
    CC163 --> CC298
    CC281 --> CC298
    CC1 --> CC163
    CC1 --> CC281
    CC122 --> T147
    CC131 --> T147
    CC297 --> T147
    CC299 --> T147
```

### 13.2 Callers

| IDE | Nom Programme | Nb Appels |
|-----|---------------|-----------|
| [131](ADH-IDE-131.md) | Fermeture caisse | 2 |
| [299](ADH-IDE-299.md) | Fermeture caisse 144 | 2 |
| [122](ADH-IDE-122.md) | Ouverture caisse | 1 |
| [297](ADH-IDE-297.md) | Ouverture caisse 143 | 1 |

### 13.3 Callees (programmes appeles)

```mermaid
graph LR
    T147[147 Devises des ticket...]
    style T147 fill:#58a6ff
    C145[145 Devises finales FF...]
    T147 --> C145
    style C145 fill:#3fb950
```

### 13.4 Detail Callees avec contexte

| IDE | Nom Programme | Appels | Contexte |
|-----|---------------|--------|----------|
| [145](ADH-IDE-145.md) | Devises finales F/F Qte WS | 2 | Sous-programme |

## 14. RECOMMANDATIONS MIGRATION

### 14.1 Profil du programme

| Metrique | Valeur | Impact migration |
|----------|--------|-----------------|
| Lignes de logique | 149 | Programme compact |
| Expressions | 3 | Peu de logique |
| Tables WRITE | 1 | Impact faible |
| Sous-programmes | 1 | Peu de dependances |
| Ecrans visibles | 0 | Ecran unique ou traitement batch |
| Code desactive | 0% (0 / 149) | Code sain |
| Regles metier | 2 | Quelques regles a preserver |

### 14.2 Plan de migration par bloc

#### Impression (3 taches: 0 ecran, 3 traitements)

- **Strategie** : Templates HTML -> PDF via wkhtmltopdf ou Puppeteer.
- `PrintService` injectable avec choix imprimante

#### Traitement (8 taches: 0 ecran, 8 traitements)

- **Strategie** : 8 service(s) backend injectable(s) (Domain Services).
- 1 sous-programme(s) a migrer ou a reutiliser depuis les services existants.
- Decomposer les taches en services unitaires testables.

#### Creation (3 taches: 0 ecran, 3 traitements)

- **Strategie** : Repository pattern avec Entity Framework Core.
- Insertion via `IRepository<T>.CreateAsync()`

### 14.3 Dependances critiques

| Dependance | Type | Appels | Impact |
|------------|------|--------|--------|
| pv_invoiceprintfiliationtmp | Table WRITE (Temp) | 5x | Schema + repository |
| [Devises finales F/F Qte WS (IDE 145)](ADH-IDE-145.md) | Sous-programme | 2x | Haute - Sous-programme |

---
*Spec DETAILED generee par Pipeline V7.2 - 2026-02-25 12:27*
