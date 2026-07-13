# Génératrices — essence, diesel et démarrage automatique

**Niveau :** pratique de base → intermédiaire  
**Focus :** types de carburant, portable vs secours résidentiel, démarrage auto / transfert, **meilleur choix pour le Canada** (dont climat froid et réalité Québec)  
**Complète :** [`../Solar_Energy_Gathering_And_Storage/`](../Solar_Energy_Gathering_And_Storage/) — le solaire réduit le carburant ; la génératrice couvre les pannes hivernales multi-jours et les fortes charges de démarrage.

**English :** [`../../Generators_Gas_Diesel_Auto_Start/README.md`](../../Generators_Gas_Diesel_Auto_Start/README.md)

## Ce que vous saurez faire

1. Choisir **essence, diesel, propane (LP) ou gaz naturel** selon le cas.  
2. Distinguer matériel **portable** et **secours résidentiel** et dimensionner watts (frigo, pompe, soufflerie fournaise, puisard).  
3. Expliquer **démarrage auto / auto-allumage** et **ATS (commutateur de transfert automatique)** quand le réseau tombe.  
4. Choisir marques et chemin d’installation adaptés au **Canada** (code, carburant, froid, service).  
5. Combiner génératrice + solaire/batterie sans réinjecter le réseau (illégal et mortel).

## Ordre d’étude

| # | Dossier | Sujet |
|---|---------|--------|
| 01 | [`01_Fuel_Types_Gas_Diesel/`](./01_Fuel_Types_Gas_Diesel/) | Essence, diesel, propane, gaz naturel |
| 02 | [`02_Portable_vs_Standby/`](./02_Portable_vs_Standby/) | Classes de machines, dimensionnement, connecteurs |
| 03 | [`03_Auto_Start_ATS_Outage/`](./03_Auto_Start_ATS_Outage/) | Capteurs, ATS, interverrouillages, exercice hebdo |
| 04 | [`04_Canadian_Brands_Best_Fit/`](./04_Canadian_Brands_Best_Fit/) | Canada/Québec, CSA, matrice de marques |
| 05 | [`05_Cold_Climate_Safe_Ops/`](./05_Cold_Climate_Safe_Ops/) | Démarrage hiver, CO, stockage carburant, verglas |
| 06 | [`06_Hybrid_With_Solar/`](./06_Hybrid_With_Solar/) | Génératrice + EcoFlow / solaire DIY sans conflit |
| — | [`LEARNING_PATH.md`](./LEARNING_PATH.md) | Liste de contrôle |
| — | [`reference/`](./reference/) | Aide-mémoire |

## Chemin d’énergie (génératrice)

```
CARBURANT (essence / diesel / propane / GN)
   ↓
MOTEUR  →  ALTERNATEUR  →  puissance CA (120/240 V)
   ↓
Cordon manuel / entrée  OU  commutateur de transfert auto (ATS)
   ↓
CIRCUITS SÉLECTIONNÉS DE LA MAISON  (ou panneau entier si dimensionné)
```

**Chemin démarrage auto (secours) :**

```
Panne du réseau
   → ATS ou contrôleur détecte la perte
   → Moteur démarre (démarrage électrique / allumage auto)
   → Génératrice stabilise tension / fréquence
   → ATS bascule les charges sur la génératrice
   → Retour du réseau → refroidissement → bascule retour → arrêt moteur
```

## Socle de sécurité (ce module)

- **Le monoxyde de carbone tue** — jamais de portable à l’intérieur, dans un garage (même « ouvert »), ni près des prises d’air.  
- **Réinjecter** une prise de sécheuse dans le panneau sans interverrouillage/ATS peut **tuer des monteurs de ligne** et brûler la maison.  
- Carburant = risque d’incendie : limites de stockage, ventilation, séparation des espaces de vie.  
- Secours permanent + ATS = **électricien licencié** (et souvent monteur gaz pour GN/propane). Au Québec : **RBQ** / permis.  
- Contenu éducatif — pas un substitut aux installations CSA/CEC ou manuels fabricant.

## Démarrage rapide

1. Lire les carburants (01).  
2. Choisir portable (budget / chalet) vs secours (maison auto-panne) en 02.  
3. Étudier ATS démarrage auto (03) avant d’acheter « toute la maison ».  
4. Utiliser la matrice **Canada** (04).  
5. Relier au solaire en 06.

Suivant → [`01_Fuel_Types_Gas_Diesel/README.md`](./01_Fuel_Types_Gas_Diesel/README.md)
