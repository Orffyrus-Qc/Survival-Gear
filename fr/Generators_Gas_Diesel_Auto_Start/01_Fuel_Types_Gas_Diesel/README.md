# 01 — Types de carburant : essence, diesel, propane et gaz naturel

On dit « génératrice à gaz » pour n’importe quelle unité fossile. Le niveau intermédiaire, c’est nommer le **carburant** et le **rôle** (portable vs secours).

---

## 1. Matrice de comparaison

| Carburant | Machines typiques | Logistique / autonomie | Climat froid (Canada) | Notes |
|-----------|-------------------|------------------------|------------------------|--------|
| **Essence** | La plupart des portables | Heures par réservoir ; se dégrade en mois | OK si frais + huile hiver ; dur après long stockage | Facile à acheter ; pire stockage long |
| **Diesel** | Gros portables, commercial, certains secours | Excellent pour long run ; dense en énergie | Excellent une fois chaud ; diesel d’hiver / anti-gel | Efficace sous charge ; plus lourd/bruyant |
| **Propane (LP)** | Dual-fuel portables, beaucoup de secours maison | Stockage long si bonbonne pleine | Excellent démarrage froid ; un peu moins de W parfois | Favori rural Canada ; pas de vernis de carbu |
| **Gaz naturel (GN)** | Secours maison (conduite utilité) | « Illimité » tant que le réseau gaz tient | Excellent ; pas de jerricans | Urbain/banlieue ; le gaz reste souvent pendant panne électrique |
| **Tri-fuel** | Certains portables | Essence + LP + kit GN | Flexible | Commodité > rendement max |

---

## 2. Essence

### Fonctionnement

Liquide → carburateur ou injection → combustion → moteur → alternateur → CA.

### Avantages

- Entrée la moins chère en portable  
- Carburant partout  
- Grand choix de modèles (Honda, Yamaha, Champion, Westinghouse, Generac…)

### Inconvénients

- L’**éthanol** vieillit mal (carbus collants après des mois)  
- Stockage utile court sans stabilisant (~3–12 mois)  
- Risque feu / vapeurs  
- Moins idéal comme seule stratégie multi-semaines sans rotation

### Habitudes survie

- Stabiliser ; faire tourner les jerricans chaque saison  
- Procédures de stockage selon manuel  
- Préférer les **onduleurs (inverter)** pour l’électronique

---

## 3. Diesel

### Fonctionnement

Allumage par compression — **pas de bougies d’allumage** (différent de l’essence). Bougies de préchauffage / réchauffeurs aident par froid. Régulateur tient le régime ; alternateur fait 60 Hz (Amérique du Nord).

### Avantages

- Efficace en charge continue  
- Se stocke mieux que l’essence (attention eau/algues)  
- Courant fermes, chantiers, télécom  
- Couple élevé pour gros alternateurs

### Inconvénients

- Prix d’achat plus haut  
- Plus lourd ; bruit/vibrations sur unités cheap  
- **Gélification hivernale** — diesel de saison / additifs au Canada  
- Secours résidentiel diesel moins courant que GN/propane (émissions, odeur) mais excellent pour sites éloignés

### Quand le diesel est le bon choix canadien

- Site éloigné, longues pannes, vous stockez déjà du diesel en vrac  
- Atelier / ferme / hutte télécom  
- Moins d’heures de logistique carburant par kWh

---

## 4. Propane (LP)

### Fonctionnement

Liquide sous pression en bonbonne → détendeur → gaz → moteur (souvent dual-fuel avec essence).

### Avantages

- **Se stocke indéfiniment** en bonbonne scellée (préparation)  
- Moins de vernis de carbu  
- Fort bon démarrage froid  
- Livraison courante (compagnies propane canadiennes)

### Inconvénients

- Un peu moins de watts max sur beaucoup de dual-fuel en mode propane  
- Gel / givrage de détendeur si sous-dimensionné par grand froid  
- Règles de placement des bonbonnes

### Note canadienne

Souvent le **meilleur carburant liquide pour secours et dual-fuel** en rural Québec / Prairies / Atlantique sans gaz naturel.

---

## 5. Gaz naturel

### Fonctionnement

Conduite utilité → compteur → train gaz génératrice → moteur. Pas de jerricans.

### Avantages

- Autonomie « illimitée » sur pannes multi-jours **si** le réseau gaz reste sous pression  
- Idéal pour **secours automatique**  
- Pas de dégradation d’essence

### Inconvénients

- Seulement là où le service GN existe  
- Pannes de gaz régionales rares mais possibles  
- Installation monteur gaz + électricien  
- Légèrement moins dense en énergie → déclassement vs LP sur certains modèles

### Note canadienne

Beaucoup de banlieues avec fournaise GN ont déjà le bon service pour un secours **10–24 kW**. Confirmer la charge : chauffage électrique / thermopompes demandent beaucoup plus ou seulement des circuits critiques.

---

## 6. Guide de décision essence vs diesel vs propane/GN

| Choisir **essence / dual-fuel portable** si… | Choisir **diesel** si… | Choisir **propane / GN secours** si… |
|----------------------------------------------|------------------------|--------------------------------------|
| Budget, camping, pannes courtes | Long run continu | Maison sans surveillance auto-start |
| Vous pouvez faire tourner le carburant | Vous avez déjà le vrac | Plan verglas multi-jours |
| Onduleur silencieux pour électronique | Chantier / ferme | Zéro jerrican hebdomadaire |

---

## 7. Qualité d’alimentation (tous carburants)

| Type | Idéal pour |
|------|------------|
| **Open-frame conventionnel** | Outils, chauffage — THD plus élevé, plus bruyant |
| **Génératrice à onduleur (inverter)** | Portables, commandes fournaise modernes, charge EcoFlow |
| **Secours (GN/LP)** | Maison entière ou partielle ; conçu pour ATS |

---

## 8. Vocabulaire intermédiaire

| Terme | Sens |
|-------|------|
| Dual-fuel | Essence + propane |
| Tri-fuel | Essence + LP + GN |
| Derate | Moins de watts dispo sur LP/GN ou altitude |
| Wet stacking | Diesel trop peu chargé → suie (faire tourner sous charge correcte) |
| Commutateur de transfert | Façon sûre d’alimenter la maison |
| Neutre lié (bonded neutral) | Schéma neutre-terre — doit matcher l’installation |

Suite → [`../02_Portable_vs_Standby/README.md`](../02_Portable_vs_Standby/README.md)
