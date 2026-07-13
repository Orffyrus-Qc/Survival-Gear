# 06 — Hybride : génératrice + solaire / batterie

Génératrice et solaire résolvent des pannes différentes. Ensemble ils réduisent le carburant et couvrent les hivers canadiens multi-jours.

---

## 1. Puissance en couches (modèle mental recommandé)

| Couche | Durée | Outil |
|--------|-------|-------|
| 0–secondes | Continuïté pour certains appareils | UPS / pass-through PPS |
| Minutes–heures | Silencieux | Batterie (classe EcoFlow ou banque DIY) |
| Récupération diurne | Renouvelable | Panneaux solaires |
| Multi-jours / crête / hiver profond | Carburant | Génératrice |
| Maison sans surveillance | Auto | Secours + ATS |

---

## 2. Façons sûres de combiner

### A. La génératrice charge une station portable

```
Génératrice à onduleur → chargeur CA EcoFlow/Bluetti/etc. → charges CC + plus tard CA depuis la station
```

- Préférer génératrice **à onduleur** (CA plus propre, efficace à charge partielle)  
- Charger la station, puis couper la gen pour économiser  
- Éviter de faire tourner la gen 24/7 pour de petits USB  

### B. La génératrice charge une batterie DIY via chargeur / onduleur-chargeur

```
Génératrice → chargeur CA ou onduleur-chargeur type Victron → banque batterie → onduleur → charges
```

- Réglages = chimie batterie  
- Fusibles et section de câble comme au module solaire  

### C. Secours ATS maison + station solaire séparée

```
Le secours gère les circuits câblés critiques
Solaire/PPS gère téléphones, lumières, îlot bureau — optionnel
```

Ne **pas** réinjecter la sortie d’un onduleur solaire dans un bus génératrice sauf si l’onduleur est **explicitement** listé pour entrée génératrice / interaction hybride.

### D. Onduleurs hybrides avec entrée génératrice

Certains AIO hors réseau acceptent la génératrice comme entrée CA pour charger les batteries. Suivre les règles de taille et de mise à la terre de cette marque.

---

## 3. Motifs dangereux / illégaux

| Motif | Pourquoi mauvais |
|-------|------------------|
| Deux sources sur une prise sans transfert | Réinjection / combat / incendie |
| Micro-onduleurs solaires + gen portable sur un circuit au hasard | Protections complexes |
| Cordon « suicide » DIY | Danger pour monteurs de ligne |
| Gen et utilité liées sans interverrouillage | Idem |

---

## 4. Stratégie d’économie de carburant

1. Solaire + batterie portent les charges silencieuses.  
2. Démarrer la génératrice quand le SoC batterie touche un plancher (ex. 20–40 %) **ou** quand une forte charge de démarrage est nécessaire.  
3. Faire tourner la gen sous **bonne charge** (charge dure + chauffage/pompe) plutôt qu’au ralenti pour un téléphone.  
4. Arrêter quand le SoC est haut à nouveau.  
5. L’exercice hebdo du secours s’applique même si le solaire existe.

---

## 5. Dimensionnement hybride pour une semaine de panne canadienne

Esquisse (pas un sceau d’ingénieur) :

| Élément | Rôle |
|---------|------|
| Batterie / PPS 2–5 kWh | Nuits + silence |
| Solaire 400–2000 W | Recharge diurne s’il y a du soleil |
| Portable onduleur 2–7 kW **ou** secours 10–22 kW | Tempête, puits, long nuage |

Semaines de verglas nuageux → le **plan carburant domine** ; le solaire est un bonus.

---

## 6. Lien vers le module solaire

- ID composants, polarité, fusibles : `Solar_Energy_Gathering_And_Storage`  
- Charge EcoFlow depuis gen = entrée **CA**, pas XT60 solaire  
- Bac solaire récup peut garder les lumières pendant que la gen fait tourner la pompe de puits  

---

Retour module → [`../README.md`](../README.md)
