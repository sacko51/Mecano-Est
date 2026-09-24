# Dossier 1 - Contrôle de Gestion Industriel : PME Mécano-Est SAS

Application de contrôle de gestion industriel réalisée sur une PME manufacturière fictive de mécanique de précision (**Mécano-Est SAS**). Projet personnel réalisé par un étudiant en Master 2 CGAO. Objectif : mesurer l'impact des choix méthodologiques de calcul des coûts sur la prise de décision (politique tarifaire, gestion des stocks, maîtrise du risque d'exploitation).

Fichiers : [`Dossier1_Mecano_Est.xlsx`](./Dossier1_Mecano_Est.xlsx) · [`Dossier1_Note_Cadrage_Mecano_Est.docx`](./Dossier1_Note_Cadrage_Mecano_Est.docx)

---

## Synthèse des enseignements clés

- **Subventionnement croisé majeur** : la méthode traditionnelle (imputation par les heures de MOD) déclarait les deux gammes rentables. La méthode ABC révèle que la gamme sur-mesure détruit de la valeur (**-41,50 € / unité, soit -29,6 %**), subventionnée par la gamme standard (**+26,8 %** de marge).
- **Résultat global inchangé** : le résultat d'exploitation de l'entreprise (**78 000 €, soit 8,9 % du CA**) est strictement identique entre les deux méthodes, seule la répartition du coût entre les deux gammes change. L'ABC ne crée pas de profit, elle révèle où il se forme réellement.
- **Impact de l'inflation sur les stocks** : en période de hausse continue du prix de l'acier, la méthode FIFO conduit à un résultat d'exploitation supérieur de **+156,82 €** à celui obtenu en PUMP.
- **Risque d'exploitation encadré** : seuil de rentabilité à **676 923 €** de chiffre d'affaires (**277 jours d'activité**, soit le 8 octobre), marge de sécurité de **23,1 %** (203 077 € de baisse de volume tolérable).

---

## Architecture du classeur

| Onglet | Objet | Décision managériale |
|---|---|---|
| `00_Sommaire` | Cadrage général | Cartographie des livrables |
| `01_Methode_ABC` | Coûts complets : traditionnel vs ABC (5 inducteurs) | Révision tarifaire de la gamme sur-mesure |
| `02_Valorisation_Stocks` | Fiche de stock chronologique : FIFO vs PUMP | Arbitrage entre valorisation de bilan et stabilité du résultat |
| `03_Seuil_Rentabilite` | Compte différentiel, seuil de rentabilité, levier | Pilotage du plan de charge annuel |

Le classeur est entièrement **piloté par formules** (aucune valeur figée) : changer un volume, un prix ou une charge en entrée recalcule automatiquement les coûts de revient, les marges et le seuil de rentabilité.

---

## Détail des modélisations

### 1. Comptabilité par activités (ABC) vs méthode classique

L'usine fabrique deux familles de pièces (CA global : 880 000 €) pour 360 000 € de charges indirectes :

- **Standard (S)** : 10 000 unités/an, prix de vente 60,00 €, charges directes 30,00 €/u.
- **Spéciale (P)** : 2 000 unités/an, prix de vente 140,00 €, charges directes 71,00 €/u.

| | Méthode classique (clé = heures MOD) | Méthode ABC (5 inducteurs) |
|---|---|---|
| Coût de revient S | 54,32 € (marge +5,68 € / +9,5 %) | **43,90 €** (marge **+16,10 € / +26,8 %**) |
| Coût de revient P | 129,38 € (marge +10,62 € / +7,6 %) | **181,50 €** (marge **-41,50 € / -29,6 %**) |

**Recommandation :** rehausser le tarif de la gamme spéciale au-dessus de son coût de revient ABC (181,50 €) ou imposer une taille minimale de lot pour réduire la fréquence des réglages de machines.

### 2. Gestion et valorisation des stocks (acier haute résistance)

- Stock disponible : 900 kg (11 000,00 €).
- **FIFO** : sorties = 7 625,00 € · stock final (250 kg) = 3 375,00 €.
- **PUMP** : sorties = 7 781,82 € · stock final (250 kg) = 3 218,18 €.
- Bouclage d'inventaire parfait (écart nul) dans les deux méthodes.

### 3. Risque d'exploitation & point mort

- CA 880 000 € → charges variables 542 000 € (61,6 %) → MCV 338 000 € (38,41 %) → charges fixes 260 000 € → résultat 78 000 € (8,9 %).
- **Seuil de rentabilité :** 676 923 € · **Point mort :** 277 jours (base 360, soit le 8 octobre).
- **Levier opérationnel :** 4,33 (une hausse de 10 % du CA génère +43,3 % de résultat).

---

## Compétences mobilisées

- Comptabilité analytique & contrôle de gestion : méthode des sections homogènes vs Activity-Based Costing, identification des inducteurs de coûts.
- Audit & contrôle interne des stocks : règles d'inventaire permanent, détection des biais d'évaluation liés à l'inflation.
- Modélisation Excel : classeur intégralement formulé, auditable cellule par cellule, sans valeur figée.
